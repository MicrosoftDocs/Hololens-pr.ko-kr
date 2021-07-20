---
title: HoloLens 2용 Windows Autopilot
description: HoloLens 2 장치에서 Autopilot을 설정 및 구성하고 문제를 해결하는 방법을 알아봅니다.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: cc73f5cbb438119f4c626ae76db9c91373e19aff
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635367"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2용 Windows Autopilot

Windows Holographic 버전 2004부터 HoloLens 2는 Microsoft Intune(타사 MDM은 지원되지 않음)에서 Windows Autopilot [자체 배포 모드](/mem/autopilot/self-deploying)를 지원합니다. 관리자는 Microsoft Endpoint Manager에서 OOBE(첫 실행 경험)를 구성하여 최종 사용자가 상호 작용을 거의 또는 전혀 하지 않고도 비즈니스용 장치를 준비할 수 있도록 할 수 있습니다. 이를 통해 인벤토리 관리 오버헤드, 실습 장치 준비 비용 및 설치하는 동안 직원의 지원 요청을 줄일 수 있습니다. 자세한 내용은 [Windows Autopilot](/mem/autopilot/windows-autopilot) 설명서를 참조하세요.

Surface 장치와 마찬가지로 고객은 Microsoft [클라우드 솔루션 공급자](https://partner.microsoft.com/cloud-solution-provider)(재판매인 또는 배포자)와 협력하여 파트너 센터를 통해 Autopilot 서비스에 등록된 장치를 구입하는 것이 좋습니다. Microsoft의 채널 파트너를 활용하면 가장 효과적인 엔드투엔드 경로가 보장되지만, 장치 등록을 위한 다른 방법은 [장치 추가](/mem/autopilot/add-devices) 설명서에 간략하게 설명되어 있습니다.

> [!NOTE]
> 2020년 11월 20일 현재 Microsoft Endpoint Manager의 HoloLens용 Autopilot 구성은 **공개 미리 보기** 로 전환되고 있습니다. 고객이 더 이상 비공개 미리 보기에 등록할 필요가 없으며 모든 테넌트는 MEM 관리 센터에서 Autopilot을 설정할 수 있습니다.

사용자가 Autopilot 자체 배포 프로세스를 시작하면 Autopilot에서 다음 단계를 완료합니다.

1. 장치를 Azure AD(Azure Active Directory)에 조인합니다. HoloLens용 Autopilot은 Active Directory 조인 또는 하이브리드 Azure AD 조인을 지원하지 않습니다.

1. Azure AD를 사용하여 Microsoft Endpoint Manager(또는 다른 MDM 서비스)에 장치를 등록합니다.

1. 장치 대상 정책, 인증서, 네트워킹 프로필 및 응용 프로그램을 다운로드하여 적용합니다.

1. 장치를 프로비전합니다.

1. 사용자에게 로그인 화면을 표시합니다.

## <a name="configuring-autopilot-for-hololens-2"></a>HoloLens 2용 Autopilot 구성

환경을 설정하려면 다음 단계를 따르세요.

1. [HoloLens 2용 Windows Autopilot의 요구 사항을 검토합니다.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [자동 MDM 등록을 사용하도록 설정합니다.](#2-enable-automatic-mdm-enrollment)

1. [Windows Autopilot에서 장치를 등록합니다.](#3-register-devices-in-windows-autopilot)

1. [장치 그룹을 만듭니다.](#4-create-a-device-group)

1. [배포 프로필을 만듭니다.](#5-create-a-deployment-profile)

1. [ESP(등록 상태 페이지) 구성을 확인합니다.](#6-verify-the-esp-configuration)

1. [HoloLens 장치의 프로필 상태를 확인합니다.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. HoloLens 2용 Windows Autopilot 요구 사항 검토

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>다음 Windows Autopilot 요구 사항 문서를 검토합니다.

- [네트워크 요구 사항](/mem/autopilot/networking-requirements)  
- [라이선싱 요구 사항](/mem/autopilot/licensing-requirements)  
- [구성 요구 사항](/mem/autopilot/configuration-requirements)

**Windows Autopilot 자체 배포 모드 문서의 "[요구 사항](/windows/deployment/windows-autopilot/self-deploying#requirements)" 섹션을 검토합니다.** 사용자 환경은 표준 Windows Autopilot 요구 사항뿐만 아니라 이러한 요구 사항도 충족해야 합니다. 문서의 "단계별 안내" 및 "유효성 검사" 섹션은 검토할 필요가 없습니다. 이 문서의 뒷부분에 나오는 절차는 HoloLens와 관련된 해당 단계를 제공합니다.

장치를 등록하고 프로필을 구성하는 방법에 대한 자세한 내용은 이 문서의 [2. Windows Autopilot에서 장치 등록](#3-register-devices-in-windows-autopilot)과 [4. 배포 프로필 만들기](#5-create-a-deployment-profile)를 참조하세요. Autopilot 자체 배포 모드 프로필을 구성하고 관리하려면 [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에 액세스할 수 있어야 합니다.

#### <a name="review-hololens-os-requirements"></a>다음과 같은 HoloLens OS 요구 사항을 검토합니다.

- 장치가 [Windows Holographic, 버전 2004](hololens-release-notes.md#windows-holographic-version-2004)(빌드 19041.1103) 이상이어야 합니다. 장치에서 빌드 버전을 확인하거나 최신 OS로 다시 플래시하려면 [ARC(고급 복구 도우미)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 및 [장치 리플래시 지침](/hololens/hololens-recovery#clean-reflash-the-device)을 사용하세요. 2020년 9월 말까지 제공되는 장치에는 Windows Holographic 버전 1903이 사전 설치되어 있습니다. Autopilot 지원 장치가 배송되는지 확인하려면 재판매인에게 문의하세요.

- Windows Holographic, 버전 2004는 이더넷 연결을 통해서만 Autopilot을 지원합니다. HoloLens를 **켜기 전** 에 "USB-C to Ethernet" 어댑터를 사용하여 HoloLens가 이더넷에 연결되어 있는지 확인합니다. 장치 부팅 시 사용자 상호 작용이 필요하지 않습니다. 다수의 HoloLens 장치에 대한 Autopilot 롤아웃을 계획하고 있는 경우 어댑터 인프라에 대한 계획을 세우는 것이 좋습니다. USB 허브는 HoloLens에서 지원되지 않는 타사 드라이버를 추가로 설치해야 하는 경우가 많기 때문에 권장하지 않습니다.

- 여전히 이더넷 어댑터를 사용할 수 있지만 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)(빌드 19041.1128) 이상은 Wi-Fi를 통해 Autopilot을 지원합니다. Wi-Fi를 통해 연결된 장치의 경우 사용자는 다음 작업만 수행해야 합니다.

     - 벌새 장면을 봅니다.
     - 언어 및 로캘을 선택합니다.
     - 눈 보정을 실행합니다.
     - 네트워크 연결을 설정합니다.

- Windows Holographic, 버전 20H2는 [Tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)을 지원하므로 테넌트에 장치를 잠그고 우발적이거나 의도적인 재설정 또는 삭제 시 장치가 해당 테넌트에 바인딩된 상태를 유지하도록 합니다.  

- 장치가 아직 Azure AD의 멤버가 아니고 Intune(또는 다른 MDM 시스템)에 등록되지 않았는지 확인합니다. Autopilot 자체 배포 프로세스는 다음 단계를 완료합니다. 모든 장치 관련 정보를 정리하려면 Azure AD 및 Intune 포털 모두에서 **장치** 페이지를 확인하세요. 현재 HoloLens에서는 "모든 대상 장치를 Autopilot으로 변환" 기능이 지원되지 않습니다.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. 자동 MDM 등록을 사용하도록 설정:

Autopilot이 성공하려면 Azure Portal에서 자동 MDM 등록을 활성화해야 합니다. 이렇게 하면 사용자 없이 장치를 등록할 수 있습니다.

[Azure Portal](https://portal.azure.com/#home)에 로그인하고, **Azure Active Directory** -> **Mobility(MDM 및 MAM)**  -> **Microsoft Intune** 을 선택합니다. 그런 다음 **MDM 사용자 범위** 를 구성하고 **모두** 를 선택해야 합니다.

간단한 다음 [MDM 자동 등록 사용 설정 가이드](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 또는 [자동 등록 빠른 시작 가이드](/mem/intune/enrollment/quickstart-setup-auto-enrollment)를 검토하여 설정에 대한 자세한 내용을 확인하세요.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Windows Autopilot에서 장치 등록

장치를 처음 설치하기 전에 Windows Autopilot에 등록해야 합니다. 장치 등록에 대한 MEM 설명서는 [Autopilot에 장치 추가](/mem/autopilot/add-devices)를 참조하세요.  

HoloLens 장치를 등록하는 기본 방법은 다음 세 가지가 있습니다.

 - **재판매인은 사용자가 주문을 할 때 파트너 센터에 장치를 등록할 수 있습니다.**

   > [!NOTE]  
   > Autopilot 서비스에 장치를 추가하는 데 권장되는 경로입니다. [자세히 알아보기](/mem/autopilot/partner-registration).  

 - **Microsoft에 직접 [지원 요청을 제출](hololens2-autopilot-registration-support.md)할 수 있습니다.**
 - **하드웨어 해시(하드웨어 ID라고도 함)를 검색하고 MEM 관리 센터에서 수동으로 장치를 등록합니다.**

#### <a name="obtain-hardware-hash"></a>하드웨어 해시 가져오기
하드웨어 해시를 가져오는 방법은 두 가지가 있습니다.
1. Microsoft에 직접 [지원 요청을 제출](hololens2-autopilot-registration-support.md)할 수 있습니다.
2. 장치에서 가져올 수 있습니다. 장치는 OOBE 프로세스 중에 또는 나중에 장치 소유자가 진단 로그 수집 프로세스를 시작(다음 절차에 설명됨)할 때 하드웨어 해시를 CSV 파일에 기록합니다. 일반적으로 장치 소유자는 장치에 처음으로 로그인한 사용자입니다.
     > [!WARNING]
     > 20H2 이전 빌드에서 OOBE를 완료했고 원격 분석이 필수로 설정된 경우 이 방법을 통해 Autopilot에 대한 하드웨어 해시를 수집할 수 없습니다. 이 방법을 통해 하드웨어 해시를 수집하려면 설정 앱을 통해 원격 분석 옵션을 전체로 설정하고 개인 정보 -> 진단을 선택합니다.

    1. HoloLens 2 장치를 시작합니다.

    1. 장치에서 **전원** 및 **Volume Down** 단추를 동시에 누른 다음 해제합니다. 장치는 진단 로그와 하드웨어 해시를 수집하여 .zip 파일 세트에 저장합니다.

   1. 전체 세부 정보 및 이를 수행하는 방법에 대한 지침 비디오를 보려면 [오프라인 진단](hololens-diagnostic-logs.md#offline-diagnostics)에 대해 읽어보세요.

    1. USB-C 케이블을 사용하여 장치를 컴퓨터에 연결합니다.

    1. 컴퓨터에서 파일 탐색기를 엽니다. **이 PC\\\<*HoloLens device name*>\\Internal Storage\\문서** 를 열고 AutopilotDiagnostics.zip 파일을 찾습니다.  

       > [!NOTE]  
       > .zip 파일을 즉시 사용하지 못할 수도 있습니다. 파일이 아직 준비되지 않은 경우 문서 폴더에 HoloLensDiagnostics.temp 파일이 표시될 수 있습니다. 파일 목록을 업데이트하려면 창을 새로 고칩니다.
    
    1. AutopilotDiagnostics.zip 파일의 내용을 추출합니다.

    1. 추출된 파일에서 파일 이름 접두사가 "DeviceHash"인 CSV 파일을 찾습니다. 해당 파일을 나중에 액세스할 수 있는 컴퓨터의 드라이브에 복사합니다.  

       > [!IMPORTANT]  
       > CSV 파일의 데이터는 다음 헤더와 선 형식을 사용해야 합니다.
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>MEM을 통해 장치를 등록합니다.

1. [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **장치** > **Windows** > **Windows enrollment** 를 선택한 다음, **Windows Autopilot Deployment Program** 아래에서 **장치** > **가져오기** 를 선택합니다.

1. **Windows Autopilot 장치 추가** 에서 DeviceHash CSV 파일을 선택하고, **열기** 를 선택한 다음, **가져오기** 를 선택합니다.  

   > [!div class="mx-imgBorder"]
   > ![가져오기 명령을 사용하여 하드웨어 해시를 가져옵니다.](./images/hololens-ap-hash-import.png)

1. 가져오기가 완료되면 **장치** > **Windows** > **Windows enrollment** > **장치** > **동기화** 를 선택합니다. 동기화하고 있는 장치 수에 따라 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다. 등록된 장치를 보려면 **새로 고침** 을 선택합니다.  

   > [!div class="mx-imgBorder"]
   > ![동기화 및 새로 고침 명령을 사용하여 장치 목록을 표시합니다.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. 장치 그룹 만들기

1. [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **그룹** > **새 그룹** 을 선택합니다.

1. **그룹 유형** 에서 **보안** 을 선택하고 그룹 이름과 설명을 입력합니다.

1. **Membership type** 에서 **할당됨** 또는 **Dynamic Device** 를 선택합니다.

1. 다음 중 하나를 수행합니다.  

   - 이전 단계에서 **멤버 자격 유형** 으로 **할당됨** 을 선택한 경우 **멤버** 를 선택한 후 그룹에 Autopilot 장치를 추가합니다. 아직 등록되지 않은 Autopilot 장치는 장치 일련 번호를 장치 이름으로 사용하여 목록에 표시됩니다.
   - 이전 단계에서 **Membership type** 으로 **Dynamic Devices** 를 선택한 경우 **Dynamic device members** 를 선택하고 **고급 규칙** 에 다음과 같은 코드를 입력합니다.
     - Autopilot 디바이스를 모두 포함한 그룹을 만들려는 경우 `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`를 입력합니다.
     - Intune의 그룹 태그 필드는 Azure AD 장치의 **OrderID** 특성에 해당합니다. 특정 그룹 태그(Azure AD 장치 OrderID)가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`을(를) 입력해야 합니다.
     - 특정 구매 주문 ID가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`을(를) 입력합니다.

     > [!NOTE]  
     > 이러한 규칙은 Autopilot 장치에 고유한 특성을 대상으로 합니다.
1. **저장** 을 선택한 후 **Create** 를 선택합니다.

### <a name="5-create-a-deployment-profile"></a>5. 배포 프로필 만들기

1. [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **장치** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens** 를 선택합니다.
   ![프로필 만들기 드롭다운에는 HoloLens 항목이 포함됩니다.](./images/hololens-ap-enrollment-profiles.png)

1. 프로필 이름과 설명을 입력하고 **다음** 을 선택합니다.  
   **HoloLens** 를 포함하는 목록이 표시됩니다. 이 옵션이 표시되지 않는 경우 [피드백](hololens2-autopilot.md#feedback-and-support-for-autopilot) 옵션 중 하나를 사용하여 문의하세요.

   > [!div class="mx-imgBorder"]
   > ![프로필 이름 및 설명 추가](./images/hololens-ap-profile-name.png)

1. **OOBE(첫 실행 경험)** 페이지에서 대부분의 설정은 이 평가를 위해 OOBE를 간소화하도록 미리 구성되어 있습니다. 필요에 따라 선택하여 구성할 수 있는 설정은 다음과 같습니다.  

   - **언어(지역)** : OOBE의 언어를 선택합니다. [HoloLens 2에 대해 지원되는 언어](hololens2-language-support.md) 목록에서 언어를 선택하는 것이 좋습니다.
   - **자동으로 키보드 구성**: 선택한 언어와 일치하는 키보드가 있는지 확인하려면 **예** 를 선택합니다.
   - **장치 이름 템플릿 적용**: OOBE 중에 장치 이름을 자동으로 설정하려면 **예** 를 선택한 다음 **이름 입력** 에 템플릿 구 및 자리 표시자를 입력합니다. 예를 들어 접두사와 `%RAND:4%`&mdash;네 자리 난수에 대한 자리 표시자를 입력합니다.
     > [!NOTE]  
     > 장치 이름 템플릿을 사용하는 경우 OOBE 프로세스는 장치 이름을 적용한 후 장치를 Azure AD에 조인하기 전에 장치를 한 번 더 다시 시작합니다. 다시 시작하면 새 이름이 적용됩니다.  

   > [!div class="mx-imgBorder"]
   > ![OOBE 설정 구성](./images/hololens-ap-profile-oobe.png)

1. 설정을 구성한 후 **다음** 을 선택합니다.
1. **범위 태그** 페이지에서 필요에 따라 이 프로필에 적용하려는 범위 태그를 추가합니다. 범위 태그에 대한 자세한 내용은 [분산형 IT에 역할 기반 액세스 제어 및 범위 태그 사용](/mem/intune/fundamentals/scope-tags.md)을 참조하세요. 완료되면 **다음** 을 선택합니다.
1. **할당** 페이지에서 **할당 대상** 으로 **선택한 그룹** 을 선택합니다.
1. **선택한 그룹** 에서 **+ 포함할 그룹 선택** 을 선택합니다.
1. **포함할 그룹 선택** 목록에서 Autopilot HoloLens 장치에 대해 생성한 장치 그룹을 선택한 후 **다음** 을 선택합니다.  
  
   모든 그룹을 제외하려는 경우 **제외할 그룹 선택** 을 선택하고 제외하려는 그룹을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![장치 그룹을 프로필에 할당합니다.](./images/hololens-ap-profile-assign-devicegroup.png)

1. **검토 + 만들기** 페이지에서 설정을 검토한 다음 **Create** 를 선택하여 프로필을 만듭니다.  

   > [!div class="mx-imgBorder"]
   > ![검토 + 만들기](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. ESP 구성 확인

ESP(등록 상태 페이지)는 MDM 관리 사용자가 처음으로 장치에 로그인할 때 실행되는 전체 장치 구성 프로세스의 상태를 표시합니다. ESP 구성이 다음과 유사한지 확인하고 할당이 올바른지 확인합니다.  

> [!div class="mx-imgBorder"]
> ![ESP 구성](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. HoloLens 장치의 프로필 상태 확인

1. Microsoft Endpoint Manager 관리 센터에서 **장치** > **Windows** > **Windows enrollment** > **장치** 를 선택합니다.

1. HoloLens 장치가 나열되어 있고 프로필 상태가 **할당됨** 인지 확인합니다.  

   > [!NOTE]  
   > 장치에 프로필을 할당하는 데 몇 분 정도 걸릴 수 있습니다.  

   > [!div class="mx-imgBorder"]
   > ![장치 및 프로필 할당.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>HoloLens 2용 Windows Autopilot 사용자 환경

위의 지침이 완료되면 HoloLens 2 사용자는 다음과 같은 환경을 통해 HoloLens 장치를 프로비전할 수 있습니다.  

1. Autopilot 환경에는 인터넷 액세스가 필요합니다. 다음 옵션 중 하나를 사용하여 인터넷 액세스를 제공하세요.

    - OOBE의 Wi-Fi 네트워크에 장치를 연결한 다음 자동으로 Autopilot 환경을 감지하도록 합니다. 이는 Autopilot 환경이 자체적으로 완료될 때까지 OOBE와 상호 작용해야 할 때만 필요합니다. 기본적으로 HoloLens 2는 인터넷 감지 후 Autopilot을 감지하기 위해 10초 동안 대기합니다. 10초 이내에 Autopilot 프로필이 검색되지 않으면 OOBE에 EULA가 표시됩니다. 이 문제가 발생하는 경우 장치를 다시 부팅하여 다시 Autopilot을 검색해 보세요. 또한 장치에 TenantLockdown 정책이 설정된 경우에만 OOBE가 Autopilot을 무기한 대기할 수 있으므로 유의하세요.

    - 유선 인터넷 연결에 "USB-C to Ethernet" 어댑터를 사용하여 장치를 이더넷에 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.

    - 무선 인터넷 연결에 "USB-C to Wifi" 어댑터를 사용하여 장치를 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.

        > [!IMPORTANT]  
       > Autopilot을 위해 OOBE에서 Wi-Fi 네트워크를 사용하려는 장치는 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에 있어야 합니다.
       >
       > 이더넷 어댑터를 사용하는 장치의 경우 OOBE(첫 실행 경험)가 시작되기 전에 장치를 네트워크에 연결해야 합니다. 장치가 첫 OOBE 화면에서 Autopilot 장치로 프로비전할지를 결정합니다. 장치를 네트워크에 연결할 수 없거나 장치를 Autopilot 장치로 프로비전하지 않도록 선택하면 나중에 Autopilot 프로비전으로 변경할 수 없습니다. 대신 장치를 Autopilot 장치로 프로비전하려면 이 절차를 다시 시작해야 합니다.

1. 장치가 자동으로 OOBE를 시작해야 합니다. OOBE와 상호 작용하지 마세요. 그 대신 잠시 기다려 주세요. HoloLens 2에서 네트워크 연결을 검색하여 OOBE를 자동으로 완료할 수 있도록 합니다. OOBE가 진행되는 동안 장치가 다시 시작될 수 있습니다. OOBE 화면은 다음과 유사합니다.

   ![OOBE 1단계](./images/autopilot-welcome.jpg)
   ![OOBE 2단계](./images/autopilot-step-complete.jpg)
   ![OOBE 3단계](./images/autopilot-device-setup.jpg)

1. OOBE가 끝나면 사용자 이름과 암호를 사용하여 장치에 로그인할 수 있습니다.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 및 Autopilot

HoloLens 2 장치는 Windows Holographic, 버전 20H2의 TenantLockdown CSP를 지원합니다. 이 CSP는 장치 초기화나 리플래시를 통해 장치를 조직의 테넌트에 잠가 장치를 해당 테넌트에 유지합니다.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용하여 HoloLens 2를 MDM 등록에 연결할 수 있습니다. TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false(초기 설정) 값으로 설정되면 리플래시, OS 업데이트 등을 수행해도 해당 값이 장치에 그대로 유지됩니다.

HoloLens 2에서 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드되고 적용될 때까지 무기한 대기합니다.

HoloLens 2에서 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면 OOBE에서 다음 작업을 수행할 수 없습니다.

- 런타임 프로비전을 사용하여 로컬 사용자 만들기 
- 런타임 프로비전을 통해 Azure AD 조인 작업 수행 
- OOBE 환경에서 장치를 소유하는 사용자 선택 

#### <a name="how-to-set-this-using-intune"></a>Intune을 사용하여 설정하는 방법은 무엇인가요? 
1. 사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.
OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 테넌트 잠금 설정](images/hololens-tenant-lockdown.png)

1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다.

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 시작합니다.  

Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 활성화됩니다.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune을 사용하여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제하는 방법은 무엇인가요?

1. 위에서 만든 장치 구성이 이전에 할당되었던 장치 그룹에서 HoloLens 2를 제거합니다.

1. 사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE를 false로 지정합니다.
OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 시작합니다.

Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 비활성화됩니다.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true로 설정된 후 HoloLens에서 Autopilot 프로필이 할당되지 않은 경우 OOBE 중에 무슨 문제가 발생하나요? 
Autopilot 프로필이 다운로드될 때까지 OOBE가 무기한 대기하고 다음 대화 상자가 표시됩니다. TenantLockdown 효과를 제거하려면 먼저 Autopilot만 사용하여 장치를 원래 테넌트에 등록해야 하며, TenantLockdown CSP에서 도입한 제한 사항이 제거되기 전에 이전 단계에서 설명한 대로 RequireNetworkInOOBE를 설정 해제해야 합니다.

![장치에서 정책이 시행될 때의 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>알려진 문제 및 제한 사항

- MEM에 구성된 디바이스 컨텍스트 기반 응용 프로그램 설치가 HoloLens에 적용되지 않는 문제를 조사 중입니다. [디바이스 컨텍스트 및 사용자 컨텍스트 설치에 대해 자세히 알아보세요.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Wi-Fi를 통해 Autopilot을 설정하는 동안 인터넷 연결이 처음 설정될 때 Autopilot 프로필이 다운로드되지 않는 인스턴스가 있을 수 있습니다. 이 경우 EULA(최종 사용자 사용권 계약)가 표시되며 사용자가 Autopilot이 아닌 설치 환경을 진행할 수 있는 옵션이 있습니다. Autopilot을 사용하여 다시 설정하려면, 장치를 절전 모드로 전환한 다음 전원을 켜고 장치를 다시 부팅하여 다시 시도합니다.
- "모든 대상 장치를 Autopilot으로 변환" 기능은 현재 HoloLens에서 지원되지 않습니다.  

### <a name="troubleshooting"></a>문제 해결

다음 문서는 자세한 정보를 알아보고 Autopilot 문제를 해결하는 데 유용한 리소스가 될 수 있지만, 이러한 문서가 Windows 10 데스크톱을 기반으로 하며 모든 정보가 HoloLens에 적용되는 것은 아니라는 점에 유의하세요.

- [Windows Autopilot - 알려진 문제](/mem/autopilot/known-issues)
- [Microsoft Intune에서 iOS 디바이스 등록 문제 해결](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - 정책 충돌](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot에 대한 피드백 및 지원

피드백이나 보고서 문제를 제공하려면 다음 방법 중 하나를 사용합니다.

- 장치 등록에 대한 지원이 필요한 경우 재판매인 또는 배포자에게 문의하세요.
- Windows Autopilot에 대한 일반적인 지원 질문 또는 프로필 할당, 그룹 만들기 또는 MEM 포털 컨트롤과 같은 문제에 대한 자세한 내용은 [Microsoft Endpoint Manager 고객 지원팀에 문의하세요.](/mem/get-support)  
- 장치가 Autopilot 서비스에 등록되어 있고 프로필이 MEM 포털에 할당된 경우 HoloLens [고객 지원팀](/hololens/)('지원' 카드 참조)에 문의하세요. 지원 티켓을 열고 해당하는 경우 OOBE(첫 실행 경험) 중에 [오프라인 진단 로그](hololens-diagnostic-logs.md#offline-diagnostics)를 캡처하여 스크린샷과 로그를 포함하세요.
- 장치에서 문제를 보고하려면 HoloLens의 피드백 허브 앱을 사용합니다. 피드백 허브에서 **Enterprise Management** > **장치** 범주를 선택합니다.
- HoloLens용 Autopilot에 대한 일반적인 피드백을 제공하려면 이 [설문 조사](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)를 제출하세요.
