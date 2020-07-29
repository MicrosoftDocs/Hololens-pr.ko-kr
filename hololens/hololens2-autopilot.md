---
title: HoloLens2 용 Windows Autopilot(비공개 미리 보기)
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 8f62c09fd569e6c5dbeb961ae023c6f3cefff879
ms.sourcegitcommit: 72be5b64e90dde339323012997440dfaca182027
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "10895792"
---
# HoloLens용 Windows 자동 실행 2

Windows Autopilot 프로그램에 HoloLens 2 장치를 설정할 때 사용자는 간단한 프로세스를 따라 클라우드에서 장치를 프로비전할 수 있습니다.

이 Autopilot 프로그램은 Autopilot 자체 배포 모드를 지원하여 테넌트에서 HoloLens 2 장치를 공유 장치로 프로비전합니다. 자체 배포 모드는 프로비저닝 프로세스 중에 장치에 사전 설치된 OEM 이미지 및 드라이버를 활용합니다. 사용자는 장치를 켜고 첫 실행 경험(OOBE)을 거치지 않고 장치를 프로비전할 수 있습니다. Windows 10용 Windows Autopilot에 대해 자세히 알아보려면 [여기](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)를 클릭하세요.

사용자가 Autopilot 자체 배포 프로세스를 시작하면 프로세스에서 다음 단계를 완료합니다.

1. 장치를 Azure AD(Azure Active Directory)에 가입시킵니다.
   > [!NOTE]  
   > HoloLens용 Autopilot은 Active Directory 가입 또는 하이브리드 Azure AD 가입을 지원하지 않습니다.
1. Azure AD를 사용하여 Microsoft Intune(또는 다른 MDM 서비스)에 장치를 등록합니다.
1. 장치 대상 정책, 사용자 대상 앱, 인증서, 네트워킹 프로필을 다운로드합니다.
1. 장치를 프로비전합니다.
1. 사용자에게 로그인 화면을 표시합니다.

## HoloLens2 용 Windows Autopilot(비공개 미리 보기)

비공개 미리 보기를 위한 환경을 설정하려면 아래 단계를 수행하세요.

1. HoloLens2용 Windows Autopilot의 요구 사항을 충족하는지 확인
1. HoloLens 2용 Windows Autopilot 비공개 미리 보기 프로그램 등록
1. 테넌트가 플라이트 중인지(프로그램 참여를 위해 등록되어 있는지) 확인
1. Windows Autopilot에서 장치 등록
1. 장치 그룹 만들기
1. 배포 프로필 만들기
1. ESP 구성 확인
1. HoloLens 장치에 대한 사용자 지정 구성 프로필 구성(알려진 문제)
1. HoloLens 장치의 프로필 상태 확인


### 1. HoloLens2용 Windows Autopilot의 요구 사항을 충족하는지 확인

**Windows Autopilot 요구 사항 문서의 다음 섹션을 검토합니다.**

- [네트워크 요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [라이선싱 요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [구성 요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Windows Autopilot 자체 배포 모드 문서의 "[요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" 섹션을 검토하세요.** 사용자 환경은 표준 Windows Autopilot 요구 사항뿐만 아니라 이러한 요구 사항도 충족해야 합니다. 문서의 "단계별 안내” 및 "유효성 검사" 섹션은 검토할 필요가 없습니다. 이 문서의 뒷부분에 나오는 절차는 HoloLens에 특정하여 해당되는 단계를 제공합니다. 장치를 등록하고 프로필을 구성하는 방법에 대한 자세한 내용은 이 문서의 [4. Windows Autopilot에서 장치 등록](#4-register-devices-in-windows-autopilot) 및 [6. 배포 프로필 만들기](#6-create-a-deployment-profile)를 참조하세요. 이 섹션에서는 HoloLens에 특정된 단계를 제공합니다.

> [!IMPORTANT]  
> 다른 Windows Autopilot 프로그램과 달리 HoloLens 2용 Windows Autopilot에는 특정 운영 체제 요구 사항이 있습니다. Autopilot은 HoloLens 장치에 미리 설치되어 있는 Windows Holoraphic 버전 2004(빌드 19041.1103 이상)를 사용합니다. 2020년 8월 말까지 제공되는 장치에는 Windows Holographic 버전 1903이 설치되어 있습니다. Autopilot 지원 장치 배송 기간은 대리점에 문의하시기 바랍니다. 비공개 미리 보기에 참여하려면 아래 지침 및 요구 사항을 검토하세요.

**Autopilot 미리 보기를 시도하려면 OOBE 및 프로비저닝 프로세스를 시작하기 전에 HoloLens 장치가 다음 요구 사항을 충족하는지 확인합니다.**

- [ARC(고급 복구 도우미)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)를 사용하여 최신 OS(Windows Holographic 버전 2004(빌드 19041.1103 이상)를 수동으로 설치해야 합니다. [여기](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)에서 지침을 확인할 수 있습니다. 
- Windows Autopilot에서 장치를 등록해야 합니다. 장치를 등록하는 방법에 대한 자세한 내용은 [4. Windows Autopilot에서 장치 등록](#4-register-devices-in-windows-autopilot)을 참조하세요. 
- 현재 릴리스에서는 HoloLens를 켜고 Autopilot 프로비저닝 프로세스를 시작하기 전에 장치를 인터넷에 연결해야 합니다. 유선 인터넷 연결을 위한 "이더넷 연결 USB C" 어댑터나 무선 인터넷 연결을 위한 "Wi-Fi 연결 USB C" 어댑터를 사용해 장치를 연결할 수 있습니다. 
- 장치가 아직 Azure AD에 속하지 않으며 Intune(또는 다른 MDM 시스템)에 등록되어 있지 않습니다. Autopilot 자체 배포 프로세스가 이러한 단계를 완료합니다. 모든 장치 관련 정보를 정리하려면 Azure AD 및 Intune 포털 모두에서 **장치** 페이지를 확인하세요.
- Autopilot 자체 배포 모드 프로필을 구성하고 관리하려면 [Microsoft 엔드포인트 관리자 관리 센터](https://endpoint.microsoft.com)에 액세스할 수 있는지 확인합니다.


### 2. HoloLens 2용 Windows Autopilot 프로그램 등록

**프로그램에 참여하려면 테넌트가 개인 미리 보기 프로그램에 등록되어 있어야 Autopilot에 대한 HoloLens별 Intune UI 컨트롤을 가져올 수 있습니다.** 이렇게 하려면 [HoloLens용 Windows Autopilot 비공개 미리 보기 요청](https://aka.ms/APHoloLensTAP)으로 이동하거나 다음 QR 코드를 사용하여 요청을 제출합니다.  

![Autopilot QR 코드](./images/hololens-ap-qrcode.png)  

이 요청에서 다음 정보를 제공합니다.

- 테넌트 도메인
- 테넌트 ID
- 이 평가에 참여하는 HoloLens 2 장치 수
- Autopilot 자체 배포 모드를 사용하여 배포할 HoloLens 2 장치 수

### 3. 테넌트가 플라이트 중인지 확인

요청을 제출한 후 테넌트가 Autopilot 프로그램에서 플라이트 중인지 확인하려면 다음 단계를 수행합니다.

1. [Microsoft 엔드포인트 관리자 관리 센터](https://endpoint.microsoft.com)에 로그인합니다.
1. **장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기**를 선택합니다.  
   
   ![프로필 만들기 드롭다운에는 HoloLens 항목이 포함됩니다.](./images/hololens-ap-enrollment-profiles.png)
  **HoloLens**를 포함하는 목록이 표시됩니다. 이 옵션이 표시되지 않는 경우 [피드백](#feedback) 옵션 중 하나를 사용하여 문의하세요.

### 4. Windows Autopilot에서 장치 등록

준비 단계에서는 Windows Autopilot에 장치를 등록할 수 있는 두 가지 기본 방법이 있습니다. 

1. **장치를 등록하거나 주문한 배포자나 대리점에 문의**하거나
2. **하드웨어 해시(하드웨어 ID라고도 함)를 검색하고 장치를 수동으로 등록할 수 있습니다.** 

장치 등록에 대한 자세한 내용은 [Autopilot에 장치 추가](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) 설명서를 확인하세요.  

**장치 하드웨어 해시 검색**

장치는 OOBE 프로세스가 진행되는 동안 또는 나중에 장치 소유자가 진단 로그 수집 프로세스(다음 절차에 설명)를 시작할 때 CSV 파일에서 하드웨어 해시를 기록할 수 있습니다. 일반적으로 장치 소유자는 처음에 장치에 로그인하는 사용자입니다.

1. HoloLens 2 장치 시작
1. 장치에서 전원 및 볼륨 작게 단추를 동시에 눌렀다 놓습니다. 장치에서 진단 로그와 하드웨어 해시를 수집하여 .zip 파일 집합에 저장합니다.
1. USB-C 케이블을 사용하여 장치를 컴퓨터에 연결합니다.
1. 컴퓨터에서 파일 탐색기를 엽니다. **내 PC\\\<*HoloLens device name*>\\내부 저장소\\문서**를 열고, AutopilotDiagnostics.zip 파일을 찾습니다.  

   > [!NOTE]  
   > .zip 파일을 즉시 사용하지 못할 수도 있습니다. 파일이 아직 준비되지 않은 경우 문서 폴더에 HoloLensDiagnostics.temp 파일이 표시될 수 있습니다. 파일 목록을 업데이트하려면 창을 새로 고칩니다.

1. AutopilotDiagnostics.zip 파일의 콘텐츠를 추출합니다.
1. 추출된 파일에서 파일 이름 접두사가 "DeviceHash"인 CSV 파일을 찾습니다. 해당 파일을 컴퓨터의 드라이브에 복사하여 나중에 액세스할 수 있도록 합니다.  
   > [!IMPORTANT]  
   > CSV 파일의 데이터는 다음 헤더 및 줄 형식을 사용해야 합니다.
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**Windows Autopilot에서 장치 등록**

1. Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록**을 선택한 다음 **Windows Autopilot 배포 프로그램**아래에서 **장치** > **가져오기**를 선택합니다.

1. **Windows Autopilot 장치 추가** 아래에서 DeviceHash CSV 파일을 선택하고 **열기**를 선택한 다음 **가져오기**를 선택합니다.  
   
   ![가져오기 명령을 사용하여 하드웨어 해시를 가져옵니다.](./images/hololens-ap-hash-import.png)
1. 가져오기가 완료되면 **장치** > **Windows** > **Windows 등록** > **장치** > **동기화**를 선택합니다. 동기화되는 장치 수에 따라 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다. 등록된 장치를 보려면 **새로 고침**을 선택합니다.  
   
   ![동기화 및 새로 고침 명령을 사용하여 장치 목록을 표시합니다.](./images/hololens-ap-devices-sync.png)  

### 5. 장치 그룹 만들기

1. Microsoft 엔드포인트 관리자 관리 센터에서 **그룹** > **새 그룹**을 선택합니다.
1. **그룹 유형**에 대해 **보안**을 선택한 다음 그룹 이름 및 설명을 입력합니다.
1. **구성원 자격 유형**에 대해 **할당됨** 또는 **동적 장치**중 하나를 선택합니다.
1. 다음 중 하나를 수행합니다.  
   
   - 이전 단계에서 **구성원 자격 유형**에 대해 **할당됨**을 선택한 경우 **구성원**을 선택한 다음 그룹에 Autopilot 장치를 추가합니다. 아직 등록되지 않은 Autopilot 장치는 장치 일련 번호를 장치 이름으로 사용하여 목록에 추가됩니다.
   - 이전 단계에서 **구성원 자격 유형**에 대해 **구성원 자격 유형**을 선택한 경우 **동적 장치 구성원**을 선택한 다음 다음과 유사한 **고급 규칙**에 코드를 입력합니다.
     - 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다. `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune의 그룹 태그 필드는 Azure AD 장치의 **OrderID** 특성에 매핑됩니다. 특정 그룹 태그(Azure AD 장치 OrderID)가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력해야 합니다. `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 특정 구매 주문 ID가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다. `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 이러한 규칙은 Autopilot 장치에 고유한 특성을 대상으로 합니다.
1. **확인**을 선택하고 **만들기**를 선택합니다.

### 6. 배포 프로필 만들기

1. Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기** > **HoloLens**를 선택합니다.
1. 프로필 이름과 설명을 입력하고 **다음**을 선택합니다.  
   
   ![프로필 이름 및 설명 추가](./images/hololens-ap-profile-name.png)
1. **첫 실행 경험(OOBE)** 페이지에서 대부분의 설정이 이 평가에 대한 OOBE를 간소화하도록 사전 구성되어 있습니다. 선택적으로 구성할 수 있는 설정은 다음과 같습니다.  

   - **언어(지역)**: OOBE의 언어를 선택합니다. [HoloLens 2에 지원되는 언어](hololens2-language-support.md) 목록에서 언어를 선택하는 것이 좋습니다.
   - **키보드 자동 구성**: 키보드가 선택한 언어와 일치하도록 하려면 **예**를 선택합니다.
   - **장치 이름 템플릿 적용**: OOBE 중에 장치 이름을 자동으로 설정하려면 **예**를 선택한 다음 템플릿 문구 및 자리 표시자를 **이름 입력**에 입력합니다. 예를 들어, 접두어와 4 자리 난수의 `%RAND:4%`&mdash;자리 표시자를 입력합니다.
     > [!NOTE]  
     > 장치 이름 템플릿을 사용하는 경우 OOBE 프로세스는 장치 이름을 적용한 후 장치를 Azure AD에 가입시키기 전에 한 번 더 장치를 다시 시작합니다. 다시 시작하면 새 이름이 적용됩니다.  

   ![OOBE 설정 구성](./images/hololens-ap-profile-oobe.png)
1. 설정을 구성한 후 **다음**을 선택합니다.
1. **범위 태그** 페이지에서 이 프로필에 적용하려는 범위 태그를 선택적으로 추가합니다. 범위 태그에 대한 자세한 내용은 [분산 IT에 역할 기반 액세스 제어 및 범위 태그 사용](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)을 참조하세요. 작업이 완료되면 **다음**을 선택합니다.
1. **할당** 페이지에서 **할당 대상**으로 **선택된 그룹**을 선택합니다.
1. **선택된 그룹**에서 **+ 포함할 그룹 선택**을 선택합니다.
1. **포함할 그룹 선택** 목록에서 Autopilot HoloLens 장치에 대해 생성한 장치 그룹을 선택한 후 **다음**을 선택합니다.  
  
   그룹을 제외하려면 **제외할 그룹 선택**을 선택하고 제외하려는 그룹을 선택합니다.

   ![장치 그룹을 프로필에 할당합니다.](./images/hololens-ap-profile-assign-devicegroup.png)
1. **검토 + 만들기** 페이지에서 설정을 검토한 후 **만들기**를 선택하여 프로필을 생성합니다.  
   
   ![검토 + 만들기](./images/hololens-ap-profile-summ.png)

### 7. ESP 구성 확인

등록 상태 페이지(ESP)는 MDM 관리 사용자가 처음으로 장치에 로그인할 때 실행되는 전체 장치 구성 프로세스의 상태를 표시합니다. ESP 구성이 다음과 유사한지 확인하고 할당이 올바른지 확인합니다.  

![ESP 구성](./images/hololens-ap-profile-settings.png)

### 8. HoloLens 장치의 프로필 상태 확인

1. Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **장치**를 선택합니다.
1. HoloLens 장치가 나열되어 있고 프로필 상태가 **할당됨**인지 확인합니다.  
   > [!NOTE]  
   > 프로필이 장치에 할당되는 데 몇 분 정도 걸릴 수 있습니다.  
   
   ![장치 및 프로필 할당](./images/hololens-ap-devices-assignments.png)

## HoloLens 2용 Windows Autopilot 사용자 환경

위의 지침이 완료되면 HoloLens 2 사용자는 다음과 같은 환경을 통해 HoloLens 장치를 프로비저닝할 수 있습니다.  

1. 앞서 언급한 바와 같이 현재 릴리스에서는 HoloLens를 켜고 Autopilot 프로비저닝 프로세스를 시작하기 전에 장치를 인터넷에 연결해야 합니다. 유선 인터넷 연결을 위한 "이더넷 연결 USB C" 어댑터나 무선 인터넷 연결을 위한 "Wi-Fi 연결 USB C" 어댑터를 사용해 장치를 연결할 수 있습니다.
   
   > [!IMPORTANT]  
   > 첫 실행 경험(OOBE)이 시작되기 전에 장치를 네트워크에 연결해야 합니다. 첫 번째 OOBE 화면에서 장치는 Autopilot 장치로 프로비전 중인지 여부를 결정합니다. 장치를 네트워크에 연결할 수 없거나 장치를 Autopilot 장치로 프로비전하지 않도록 선택하는 경우 나중에 Autopilot 프로비전으로 변경할 수 없습니다. 대신 장치를 Autopilot 장치로 프로비전하려면 이 절차를 다시 시작해야 합니다.

1. 장치가 자동으로 OOBE를 시작할 것입니다. OOBE는 신경쓰지 마세요. 그 대신 잠시 기다려 주세요. HoloLens 2에서 네트워크 연결을 검색하여 OOBE를 자동으로 완료할 수 있도록 합니다. OOBE가 진행되는 동안 장치가 다시 시작될 수 있습니다. OOBE 화면은 다음과 유사 합니다.
   
   ![OOBE 1단계](./images/hololens-ap-uex-1.png)
   ![OOBE 2단계](./images/hololens-ap-uex-2.png)
   ![OOBE 3단계](./images/hololens-ap-uex-3.png)
   ![OOBE 4단계](./images/hololens-ap-uex-4.png)

1. OOBE가 끝나면 사용자 이름과 암호를 사용하여 장치에 로그인할 수 있습니다.

  ![OOBE 5단계](./images/hololens-ap-uex-5.png)

## 알려진 문제

- 장치 보안 컨텍스트를 사용하는 응용 프로그램을 설치할 수 없습니다.

## 사용자 의견

피드백을 제공하거나 문제를 신고하려면 다음 방법 중 하나를 사용합니다.

- 피드백 허브 앱 사용 HoloLens에 연결된 컴퓨터에서 이 앱을 찾을 수 있습니다. 피드백 허브에서 **엔터프라이즈 관리** > **장치** 범주를 선택합니다.  

  피드백을 제공하거나 문제를 신고할 때 자세한 설명을 제공합니다. 해당하는 경우 스크린샷 및 로그를 포함합니다.
- [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)으로 전자 메일 메시지를 보냅니다. 전자 메일 제목으로 **\<*Tenant*> HoloLens 2용 Autopilot 평가 피드백**(여기에서 \<*Tenant*>은(는) 사용자의 Intune 테넌트 이름)을 입력합니다.

  메시지에 자세한 설명을 제공합니다. 그러나 지원 담당자가 특별히 요청하지 않는 한 스크린샷이나 로그와 같은 데이터는 포함하지 않습니다. 이러한 데이터에는 개인 또는 개인 식별 정보(PII)가 포함될 수 있습니다.
