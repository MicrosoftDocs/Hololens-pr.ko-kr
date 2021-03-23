---
title: HoloLens를 키오스크로 설정
description: 키오스크 구성을 설정하고 사용하여 HoloLens 장치에서 앱을 잠그는 방법을 배워야 합니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445378"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens를 키오스크로 설정

키오스크 모드에서 실행하도록 디바이스를 구성하여 HoloLens 장치가 ** 키오스크라고도 하는 고정 용도 장치로 작동하도록 구성할 수 있습니다. 키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램(또는 사용자)을 제한합니다. 키오스크 모드는 HoloLens 장치를 비즈니스 앱에 전담하거나 앱 데모에서 HoloLens 장치를 사용하는 데 사용할 수 있는 편리한 기능입니다.

이 문서에서는 HoloLens 장치와 관련한 키오스크 구성의 측면에 대한 정보를 제공합니다. 다양한 유형의 Windows 기반 키오스크 및 키오스크를 구성하는 방법에 대한 일반적인 내용은 Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성을 [참조하세요.](https://docs.microsoft.com/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> 키오스크 모드는 사용자가 장치에 로그인할 때 사용할 수 있는 앱을 확인합니다. 그러나 키오스크 모드는 보안 방법이 아니며, "허용" 앱이 허용되지 않는 다른 앱을 열지 못하도록 중지하지는 않습니다. 앱 또는 프로세스가 열리지 못하도록 차단하기 위해 [WDAC(Windows Defender 응용 프로그램 제어) CSP를](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 사용하여 적절한 정책을 만드십시오.
>
> HoloLens 2에서 사용하는 고급 보안 수준을 사용자에게 제공하는 Microsoft 서비스에 대해 자세히 알아보고 상태 분리 및 분리 [- Defender 보호에 대해 자세히 읽어보아야 합니다.](security-state-separation-isolation.md#defender-protections) 또는 WDAC 및 Windows PowerShell [사용하여 Microsoft Intune을 사용하여 HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)장치에서 앱을 허용하거나 차단하는 방법을 배울 수 있습니다.

단일 앱 또는 다중 앱 구성에서 키오스크 모드를 사용할 수 있으며, 세 가지 프로세스 중 하나를 사용하여 키오스크 구성을 설정하고 배포할 수 있습니다.

> [!IMPORTANT]  
> 다중 앱 구성을 삭제하면 할당된 액세스 기능이 만든 사용자 잠금 프로필이 제거됩니다. 그러나 정책 변경 내용을 모두 되버리진 않습니다. 이러한 정책을 되전하려면 장치를 공장 설정으로 다시 설정해야 합니다.

## <a name="plan-the-kiosk-deployment"></a>키오스크 배포 계획

키오스크를 계획할 때 다음 질문에 답변할 수 있는 것이 필요합니다. 다음은 이 페이지를 읽는 동안 고려할 몇 가지 결정 사항과 이러한 질문에 대한 몇 가지 고려 사항입니다.
1. **키오스크를 사용할 사용자와 어떤 [](hololens-identity.md) 유형의 계정을 사용할 것인가?** 이는 이미 결정했기 때문에 키오스크를 위해 조정하면 안 되지만 나중에 키오스크가 할당되는 방식에 영향을 줄 수 있습니다.
1. **사용자/그룹당 서로 다른 키오스크 또는 일부 사용자에 대해 키오스크를 사용하도록 설정하지 않은 것이 필요한가요?** 그렇다면 XML을 통해 키오스크를 만들 수 있습니다. 
1. **키오스크에 있는 앱의 수** 앱이 1개 이상인 경우 다중 앱 키오스크가 필요합니다. 
1. **키오스크에 어떤 앱이 있나요?** 아래 AUMID 목록을 사용하여 사용자 자신과 함께 In-Box 앱을 추가하세요.
1. **키오스크를 배포할 계획은 어떻게 하나요?** MDM에 장치를 등록하는 경우 MDM을 사용하여 키오스크를 배포하는 것이 제안됩니다. MDM을 사용하지 않는 경우 프로비저닝 패키지와 함께 배포를 사용할 수 있습니다.  

### <a name="kiosk-mode-requirements"></a>키오스크 모드 요구 사항

키오스크 모드를 사용하도록 HoloLens 2 장치를 구성할 수 있습니다.

> [!IMPORTANT]
> 키오스크 모드는 디바이스에 비즈니스용 Windows Holographic이 있는 경우만 사용할 수 있습니다. 모든 HoloLens 2 장치는 비즈니스용 Windows Holographic과 함께 제공하며 다른 버전은 없습니다. 모든 HoloLens 2 장치는 키오스크 모드를 실행할 수 있습니다.
>
> HoloLens(1세대) 장치는 OS 빌드와 OS 버전 면에서 모두 업그레이드해야 합니다. 다음은 HoloLens(1세대)를 [비즈니스용 Windows Holographic](hololens1-upgrade-enterprise.md) 버전으로 업데이트하는 데 대한 자세한 정보입니다. HoloLens(1세대) 장치를 키오스크 모드를 사용하기 위해 업데이트하려면 먼저 장치가 Windows 10 버전 1803 이상 버전을 실행해야 합니다. Windows 장치 복구 도구를 사용하여 HoloLens(1세대) 장치를 기본 빌드로 복구하거나 최신 업데이트를 설치한 경우 장치를 구성할 준비가 된 것입니다.

> [!IMPORTANT]  
> 키오스크 모드로 실행되는 장치를 보호하려면 USB 연결 등의 기능을 해제하는 장치 관리 정책을 추가하는 것이 있습니다. 또한 업데이트 링 설정을 확인하여 업무 시간 중에 자동 업데이트가 발생하지 않는지 확인합니다.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>단일 앱 키오스크 또는 다중 앱 키오스크 간에 결정

단일 앱 키오스크는 사용자가 장치에 로그인할 때 지정된 앱을 시작합니다. 시작 메뉴는 Cortana와 같은 사용되지 않습니다. HoloLens 2 장치는 시작 제스처에 [응답하지](hololens2-basic-usage.md#start-gesture) 않습니다. HoloLens(1세대) 장치는 블룸 제스처에 [응답하지](hololens1-basic-usage.md) 않습니다. 한 앱만 실행할 수 있기 때문에 사용자는 다른 앱을 실행할 수 없습니다.

다중 앱 키오스크는 사용자가 장치에 로그인할 때 시작 메뉴를 표시합니다. 키오스크 구성에 따라 시작 메뉴에서 사용할 수 있는 앱이 결정됩니다. 다중 앱 키오스크를 사용하여 사용자에게 필요한 것만 제공하고 사용하지 않고도 사용할 수 있는 것만 제거하여 사용자에게 이해하기 쉬운 환경을 제공할 수 있습니다.

다음 표에는 서로 다른 키오스크 모드의 기능 목록이 나열되어 있습니다.

| &nbsp; |시작 메뉴 |빠른 작업 메뉴 |카메라 및 비디오 |Miracast |Cortana |기본 제공 음성 명령 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|단일 앱 키오스크 |사용 안 함 |사용 안 함   |사용 안 함 |사용 안 함   |사용 안 함 |사용 <sup> 1</sup> |
|복수 앱 키오스크 |설정됨 |사용 <sup> 2</sup> |사용 <sup> 가능한 2</sup> |사용 <sup> 가능한 2</sup> |<sup>사용 가능한 2, 3</sup>  |사용 <sup> 1</sup> |

> <sup>1 비활성화된 기능과 관련된 음성 명령이 </sup> 작동하지 않습니다.  
> <sup>2 이러한 기능을 구성하는 방법에 대한 자세한 내용은 키오스크 앱 </sup> [선택을 참조하세요.](#plan-kiosk-apps)  
> <sup>3 Cortana를 사용하지 않도록 설정한 경우에도 기본 제공 음성 명령을 </sup> 사용할 수 있습니다.

다음 표에는 다양한 키오스크 모드의 사용자 지원 기능이 나열됩니다.

| &nbsp; |지원되는 사용자 유형 | 자동 로그인 | 여러 액세스 수준 |
| --- | --- | --- | --- |
|단일 앱 키오스크 |Azure AD(Azure Active Directory) 또는 로컬 계정의 MSA(관리 서비스 계정) |예 |아니오 |
|복수 앱 키오스크 |Azure AD 계정 |아니오 |예 |

이러한 기능을 사용하는 방법에 대한 예제는 다음 표를 참조합니다.

|단일 앱 키오스크를 사용하여 다음을 할 수 있습니다. |다중 앱 키오스크를 사용하여 다음을 할 수 있습니다. |
| --- | --- |
|신입 사원을 위한 Dynamics 365 가이드만 실행되는 장치입니다. |다양한 직원에 대해 가이드 및 원격 지원을 모두 실행하는 장치입니다. |
|사용자 지정 앱만 실행되는 장치입니다. |대부분의 사용자에 대한 키오스크로 작동하지만(사용자 지정 앱만 실행) 특정 사용자 그룹에 대한 표준 장치로 기능하는 장치입니다. |

### <a name="plan-kiosk-apps"></a>키오스크 앱 계획

키오스크 앱을 선택하는 방법에 대한 일반적인 내용은 할당된 액세스용 앱 선택 지침(키오스크 [모드)을 참조하세요.](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Windows Device Portal을 사용하여 단일 앱 키오스크를 구성하는 경우 설치 프로세스 중에 앱을 선택합니다.  

MDM(모바일 장치 관리) 시스템 또는 프로비저닝 패키지를 사용하여 키오스크 모드를 구성하는 경우 [AssignedAccess CSP(구성](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 서비스 공급자)를 사용하여 응용 프로그램을 지정합니다. CSP는 [AUMID(응용](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 프로그램 사용자 모델 ID)를 사용하여 응용 프로그램을 식별합니다. 다음 표에는 다중 앱 키오스크에서 사용할 수 있는 일부 인박스 응용 프로그램의 AUMID가 나열됩니다.

> [!IMPORTANT]
> 키오스크 모드는 사용자가 장치에 로그인할 때 사용할 수 있는 앱을 확인합니다. 그러나 키오스크 모드는 보안 방법이 아니며, "허용" 앱이 허용되지 않는 다른 앱을 열지 못하도록 중지하지는 않습니다. 이 동작은 제한하지 않는 것이 에지, 파일 탐색기 및 Microsoft Store 앱에서 계속 실행될 수 있습니다. 키오스크에서 시작하지 않는 특정 앱이 있는 경우 [WDAC(Windows Defender 응용 프로그램 제어) CSP를](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 사용하여 적절한 정책을 만들 수 있습니다. 
> 
> 또한 혼합 현실 홈을 키오스크 앱으로 설정할 수 없습니다.

<a id="aumids"></a>

|앱 이름 |AUMID |
| --- | --- |
|3D 뷰어 |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendar |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|카메라 <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! 앱 |
|HoloLens(1세대)의 디바이스 선택 |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|HoloLens 2의 장치 선택 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|피드백 &nbsp; 허브 |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! 앱 |
|파일 탐색기 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|영화 및 TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! 앱 |
|사진 |Microsoft.Windows.사진\_8wekyb3d8bbwe\! 앱 |
|설정 |HolographicSystemSettings\_cw5n1h2txyewy\! 앱 |
|팁 |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 사진 또는 비디오 캡처를 사용하도록 설정하려면 카메라 앱을 키오스크 앱으로 </sup> 사용하도록 설정해야 합니다.  
> <sup>2 </sup> 카메라 앱을 사용하도록 설정하는 경우 다음 조건을 알고 있어야 합니다.
> - 빠른 작업 메뉴에는 사진 및 비디오 단추가 포함되어 있습니다.  
> - 그림을 조작하거나 검색할 수 있는 앱(예: 사진, 메일 또는 OneDrive)도 사용하도록 설정해야 합니다.  
>  
> <sup>3 Cortana를 키오스크 앱으로 사용하도록 설정하지 않은 경우에도 기본 제공 </sup> 음성 명령이 사용하도록 설정됩니다. 그러나 사용하지 않도록 설정한 기능과 관련된 명령은 아무 효과가 없습니다.  
> <sup>4 </sup> Miracast를 직접 사용하도록 설정할 수 없습니다. Miracast를 키오스크 앱으로 사용하도록 설정하려면 카메라 앱 및 장치 선택 앱을 사용하도록 설정할 수 있습니다.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>사용자 또는 그룹에 대한 키오스크 프로필 계획

xml 파일을 만들거나 Intune의 UI를 사용하여 키오스크를 설정할 때 키오스크를 사용할 사용자를 고려해야 합니다. 키오스크 구성은 개별 계정 또는 Azure AD 그룹으로 제한될 수 있습니다. 

일반적으로 키오스크는 사용자 또는 사용자 그룹에 대해 사용하도록 설정됩니다. 그러나 자체 XML 키오스크를 작성하려는 경우 ID에 관계없이 장치 수준에서 키오스크가 적용되는 전역 할당된 액세스를 고려할 수 있습니다. 이 내용을 통해 전역 할당된 액세스 키오스크에 대해 자세히 [읽어보는 것이 더 어필할 수 있습니다.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>XML 파일을 만드는 경우:
-   많은 사용자가 여러 개의 키오스크 프로필을 만들고 각 프로필을 서로 다른 사용자/그룹에 할당합니다. 앱 수가 많은 Azure AD 그룹의 키오스크, 단일 앱이 있는 여러 앱 키오스크가 있는 방문자 등의 경우
-   키오스크 구성은 프로필 **ID로** 불리며 GUID가 있습니다.
-   사용자 유형을 지정하고 **DefaultProfile Id에**동일한 GUID를 사용하여 구성 섹션에서 해당 프로필을 할당합니다.
- XML 파일은 만들 수 있지만 사용자 지정 OMA URI 장치 구성 프로필을 만들고 URI 값을 사용하여 HoloLens 장치 그룹에 적용하여 MDM을 통해 장치에 계속 적용할 수 있습니다. ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune에서 키오스크를 만드는 경우
-   각 디바이스는 단일 키오스크 프로필만 수신할 수 있으며, 그렇지 않으면 충돌이 생성되어 키오스크 구성을 수신하지 않습니다. 
    -   키오스크 구성 프로필과 관련이 없는 장치 제한과 같은 다른 종류의 프로필 및 정책은 키오스크 구성 프로필과 충돌하지 않습니다.
-   사용자 로그온 유형의 일부인 모든 사용자에 대해 키오스크가 사용하도록 설정됩니다. 이 설정은 사용자 또는 Azure AD 그룹으로 설정됩니다. 
-   키오스크 구성을 설정하고 사용자 **** 로그온 유형(키오스크에 로그인할 수 있는 사용자)과 앱을 선택한 후에도 장치 구성을 그룹에 할당해야 합니다. 할당된 그룹은 키오스크 장치 구성을 받는 장치를 결정하나 키오스크가 활성화되어 있는지 여부를 확인하지는 않습니다. 
    - Intune에서 구성 프로필을 할당하는 경우의 영향에 대한 자세한 내용은 [Microsoft Intune에서](https://docs.microsoft.com/intune/configuration/device-profile-assign)사용자 및 장치 프로필 할당을 참조하세요.

### <a name="select-a-deployment-method"></a>배포 방법 선택

다음 방법 중 하나를 선택하여 키오스크 구성을 배포할 수 있습니다.

- [Microsoft Intune 또는 기타 MDM(모바일 장치 관리) 서비스](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [프로비저닝 패키지](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 이 방법을 사용하려면 디바이스에서 개발자 모드를 사용하도록 설정해야 하기 때문에 데모에만 사용하는 것이 좋습니다.

다음 표에는 각 배포 방법의 기능과 이점이 나열되어 있습니다.

| &nbsp; |Windows Device Portal을 사용하여 배포 |프로비저닝 패키지를 사용하여 배포 |MDM을 사용하여 배포 |
| --------------------------- | ------------- | -------------------- | ---- |
|단일 앱 키오스크 배포   | 예           | 예                  | 예  |
|다중 앱 키오스크 배포    | 아니오            | 예                  | 예  |
|로컬 장치에만 배포 | 예           | 예                  | 아니오   |
|개발자 모드를 사용하여 배포 |필수       | 필수 아님            | 필수 아님   |
|Azure AD(Azure Active Directory)를 사용하여 배포  | 필수 아님            | 필수 아님                   | 필수  |
|자동으로 배포      | 아니오            | 아니오                   | 예  |
|배포 속도            | 빠름       | 빠름                 | 슬로우 |
|대규모 배포 | 권장하지 않음    | 권장 사항        | 권장 사항 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Microsoft Intune 또는 기타 MDM을 사용하여 단일 앱 또는 다중 앱 키오스크 설정

Microsoft Intune 또는 다른 MDM 시스템을 사용하여 키오스크 모드를 설정하기 위해 다음 단계를 수행합니다.

1. [장치를 등록할 준비를 합니다.](#mdmenroll)
1. [키오스크 구성 프로필을 생성합니다.](#mdmprofile)
1. 키오스크를 구성합니다.
   - [단일 앱 키오스크에 대한 설정을 구성합니다.](#mdmconfigsingle)
   - [다중 앱 키오스크에 대한 설정을 구성합니다.](#mdmconfigmulti)
1. [키오스크](#mdmassign)구성 프로필을 그룹에 할당합니다.
1. 장치를 배포합니다.
   - [단일 앱 키오스크를 배포합니다.](#mdmsingledeploy)
   - [다중 앱 키오스크를 배포합니다.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, 1단계 &ndash; 장치 등록 준비

사용자가 처음 로그인할 때 HoloLens 장치를 자동으로 등록하거나 사용자가 장치를 수동으로 등록하도록 MDM 시스템을 구성할 수 있습니다. 디바이스도 Azure AD 도메인에 가입하고 적절한 그룹에 할당해야 합니다.

디바이스를 등록하는 방법에 대한 자세한 내용은 [MDM에서 HoloLens](hololens-enroll-mdm.md) 등록 및 Windows 장치에 [대한 Intune 등록 방법을 참조하세요.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, 2단계 &ndash; 키오스크 구성 프로필 만들기

1. [Azure](https://portal.azure.com/) Portal을 열고 Intune 관리자 계정에 로그인합니다.
1. **Microsoft Intune**  >  **장치 구성 - 프로필 프로필**  >  **만들기를 선택합니다.**
1. 프로필 이름을 입력합니다.
1. 플랫폼 ****  >  **Windows 10 이상을**선택한 다음 프로필 유형 **장치**제한  > **을 선택합니다.**
1. ****  >  **키오스크 구성을 선택하고**다음 중 하나를 선택합니다.
   - 단일 앱 키오스크를 만들하려면 **키오스크**모드 단일 앱  >  **키오스크 를 선택합니다.**
   - 다중 앱 키오스크를 만들하려면 **키오스크**모드 다중 앱  >  **키오스크 를 선택합니다.**
1. 키오스크 구성을 시작하려면 추가 를 **선택합니다.**

다음 단계는 원하는 키오스크 유형에 따라 다릅니다. 자세한 내용은 다음 옵션 중 하나를 선택합니다.  

- [단일 앱 키오스크](#mdmconfigsingle)
- [복수 앱 키오스크](#mdmconfigmulti)

키오스크 구성 프로필을 만드는 방법에 대한 자세한 내용은 Intune을 사용하여 전용 키오스크로 실행할 [Windows 10 및 비즈니스용 Windows Holographic](https://docs.microsoft.com/intune/configuration/kiosk-settings)장치 설정을 참조하세요.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, 3단계(단일 앱) 단일 앱 키오스크에 대한 &ndash;  설정 구성

이 섹션에서는 단일 앱 키오스크에 필요한 설정에 대해 간소하게 설명합니다. 자세한 내용은 다음 문서를 참조합니다.

- Intune에서 키오스크 구성 프로필을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune을 사용하여 키오스크 모드를](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)구성하는 방법을 참조하세요.
- Intune에서 단일 앱 키오스크의 사용 가능한 설정에 대한 자세한 내용은 단일 전체 화면 앱 [키오스크를 참조하세요.](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. 사용자 지정 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 키오스크 구성을 정의하는 XML 파일을 [생성합니다.](#ppkioskconfig)

1. 사용자 **로그온 유형**로컬 사용자 계정을 선택한 다음 키오스크에 로그인할 수 있는 로컬(장치) 계정 또는 Microsoft  >  **** 계정(MSA)의 사용자 이름을 입력합니다.
   > [!NOTE]  
   > **Autologon** 사용자 계정 유형은 비즈니스용 Windows Holographic에서 지원되지 않습니다.
1. 응용 **프로그램 유형**스토어 앱을  >  **선택한**다음 목록에서 앱을 선택합니다.

다음 단계는 [프로필을](#mdmassign) 그룹에 할당하는 것입니다.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, 3단계(다중 앱) 다중 앱 키오스크에 대한 &ndash; 설정 구성

이 섹션에서는 다중 앱 키오스크에 필요한 설정에 대해 간소하게 설명합니다. 자세한 내용은 다음 문서를 참조하세요.

- Intune에서 키오스크 구성 프로필을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune을 사용하여 키오스크 모드를](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)구성하는 방법을 참조하세요.
- Intune에서 다중 앱 키오스크에 사용할 수 있는 설정에 대한 자세한 내용은 다중 앱 [키오스크를 참조하세요.](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. 사용자 지정 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 키오스크 구성을 정의하는 XML 파일을 [생성합니다.](#ppkioskconfig) XML 파일을 사용하는 경우 시작 화면 레이아웃을 [포함해야 합니다.](#start-layout-for-hololens)  
- 필요한 경우 Intune 또는 다른 MDM 서비스에서 사용자 지정 시작 화면 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM의 시작 레이아웃 파일(Intune 등)을 참조하세요.](#start-layout-file-for-mdm-intune-and-others)

1. **S 모드 디바이스에서 Windows 10**대상 지정  >  **아니요를 선택합니다.**  
   >[!NOTE]  
   > S 모드는 비즈니스용 Windows Holographic에서 지원되지 않습니다.
1. 사용자 **로그온 유형**Azure AD 사용자 또는 그룹 또는 사용자 로그온  >  **** **유형**  >  **HoloLens 방문자를**선택한 다음 하나 이상의 사용자 그룹 또는 계정을 추가합니다.  

   사용자 로그온 유형에서 지정한 그룹 **** 또는 계정에 속하는 사용자만 키오스크 환경을 사용할 수 있습니다.

1. 다음 옵션을 사용하여 하나 이상의 앱을 선택합니다.
   - 업로드된 업무용 앱을 추가하려면 스토어 **** 앱 추가를 선택한 다음 원하는 앱을 선택합니다.
   - AUMID를 지정하여 앱을 추가하려면 **AUMID로** 추가를 선택한 다음 앱의 AUMID를 입력합니다. [사용 가능한 AUMID 목록 보기](#aumids)

다음 단계는 [프로필을](#mdmassign) 그룹에 할당하는 것입니다.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, 4단계 그룹에 키오스크 구성 프로필 &ndash; 할당

**키오스크** 구성 프로필의 할당 페이지를 사용하여 키오스크 구성을 배포할 위치를 설정할 수 있습니다. 가장 간단한 경우 장치가 MDM에 등록할 때 HoloLens 장치를 포함할 그룹에 키오스크 구성 프로필을 할당합니다.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5단계(단일 앱) 단일 앱 &ndash; 키오스크 배포

MDM 시스템을 사용하는 경우 OOBE 중에 MDM에 장치를 등록할 수 있습니다. OOBE가 완료되면 디바이스에 쉽게 로그인할 수 있습니다.

OOBE 중에 다음 단계를 수행합니다.

1. 키오스크 구성 프로필에 지정한 계정을 사용하여 로그인합니다.
1. 디바이스를 등록합니다. 키오스크 구성 프로필이 할당된 그룹에 장치가 추가되어 있는지 확인합니다.
1. OOBE가 완료될 때까지, 스토어 앱이 다운로드 및 설치될 때까지, 그리고 정책이 적용될 때까지 기다렸다가 그런 다음 장치를 다시 시작합니다.

다음에 장치에 로그인하면 키오스크 앱이 자동으로 시작됩니다.

이때 키오스크 구성이 없는 경우 배정 [상태를 확인 합니다.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5단계(다중 앱) 다중 앱 &ndash; 키오스크 배포

MDM 시스템을 사용하는 경우 장치를 Azure AD 테넌트에 가입하고 OOBE 중에 MDM에 장치를 등록할 수 있습니다. 필요한 경우 OOBE 프로세스 중에 등록 정보를 사용할 수 있도록 사용자에게 등록 정보를 제공합니다.

> [!NOTE]  
> 사용자가 포함된 그룹에 키오스크 구성 프로필을 할당한 경우 해당 사용자 계정 중 하나를 디바이스에 로그인하는 첫 번째 계정으로 지정해야 합니다.

OOBE 중에 다음 단계를 수행합니다.

1. 사용자 로그온 유형 그룹에 속한 계정을 사용하여 **로그인합니다.**
1. 디바이스를 등록합니다.
1. 키오스크 구성 프로필의 일부인 모든 앱이 다운로드하여 설치할 때까지 기다릴 수 있습니다. 또한 정책이 적용될 때까지 기다릴 수 있습니다.  
1. OOBE가 완료되면 Microsoft Store 또는 사이드로드를 통해 추가 앱을 설치할 수 있습니다. [장치가 속한](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 그룹에 필요한 앱은 자동으로 설치됩니다.
1. 설치가 완료되면 장치를 다시 시작합니다.

다음에 사용자 로그온 유형에 속하는 계정을 사용하여 **** 장치에 로그인하면 키오스크 앱이 자동으로 시작됩니다.

이때 키오스크 구성이 없는 경우 배정 [상태를 확인 합니다.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>프로비저닝 패키지를 사용하여 단일 앱 또는 다중 앱 키오스크 설정

프로비저닝 패키지를 사용하여 키오스크 모드를 설정하기 위해 다음 단계를 수행합니다.

1. [키오스크](#ppkioskconfig)구성을 정의하는 XML 파일을 만들고 시작 화면 레이아웃 [을 포함 합니다.](#start-layout-for-hololens)
2. [프로비저닝 패키지에 XML 파일을 추가합니다.](#ppconfigadd)
3. [HoloLens에 프로비저닝 패키지를 적용합니다.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>프로비저닝 패키지, 1단계 &ndash; 키오스크 구성 XML 파일 만들기

다음을 [제외하고 일반적인 지침에](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)따라 Windows 데스크톱용 키오스크 구성 XML 파일을 만들 수 있습니다.

- 클래식 Windows 응용 프로그램(Win32)은 포함하지 않습니다. HoloLens는 이러한 응용 프로그램을 지원하지 않습니다.
- HoloLens에 대한 자리 표시자 시작 레이아웃 [XML을](#start-layout-for-hololens) 사용합니다.
- 선택 사항: 키오스크 구성에 게스트 액세스 추가

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>선택 사항: 키오스크 구성에 게스트 액세스 추가

XML 파일의 [ **구성** ](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)섹션에서 방문자라는 특수 그룹을 구성하여 **** 게스트가 키오스크를 사용할 수 있도록 할 수 있습니다. 방문자 특별 그룹을 지원하도록 키오스크를 구성하면 로그인 페이지에 "**게스트"** 옵션이 추가됩니다. **** 게스트 **계정에는** 암호가 필요하지 않습니다. 계정이 로그인하면 계정과 연결된 데이터가 삭제됩니다.

게스트 계정을 사용하도록 **설정하려면** 키오스크 구성 XML에 다음 코드퍼킷을 추가합니다.

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens의 자리 표시자 시작 화면 레이아웃

프로비저닝 [패키지를](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 사용하여 다중 앱 키오스크를 구성하는 경우 절차에 시작 화면 레이아웃이 필요합니다. 시작 화면 레이아웃 사용자 지정은 비즈니스용 Windows Holographic에서 지원되지 않습니다. 따라서 자리 표시자 시작 레이아웃을 사용해야 합니다.

> [!NOTE]  
> 단일 앱 키오스크는 사용자가 로그인할 때 키오스크 앱을 시작하기 때문에 시작 메뉴를 사용하지 않을 뿐만 아니라 시작 화면 레이아웃도 사용할 수 없습니다.

> [!NOTE]  
> [MDM을](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 사용하여 다중 앱 키오스크를 설정하는 경우 선택적으로 시작 화면 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM(Intune](#start-layout-file-for-mdm-intune-and-others)및 기타)에 대한 자리 표시자 시작 레이아웃 파일을 참조하세요.

시작 화면 레이아웃의 경우 키오스크 프로비전 XML 파일에 다음 **StartLayout** 섹션을 추가합니다.

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM의 자리 표시자 시작 화면 레이아웃 파일(Intune 등)

다음 샘플을 XML 파일로 저장합니다. Microsoft Intune(또는 키오스크 프로필을 제공하는 다른 MDM 서비스)에서 다중 앱 키오스크를 구성할 때 이 파일을 사용할 수 있습니다.

> [!NOTE]
> 사용자 지정 설정 및 전체 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 프로비저닝 패키지에 대한 시작 화면 레이아웃 지침을 [사용합니다.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. 패키지, 2단계 프로비저닝 패키지에 키오스크 구성 XML 파일 &ndash; 추가

1. [Windows 구성 디자이너 를 열 수 있습니다.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. 고급 **프로비전 을**선택하고 프로젝트 이름을 입력한 후 다음 을 **선택합니다.**
1. **Windows 10 Holographic을 선택하고**다음 을 **선택합니다.**
1. 마친 **을 선택합니다.** 패키지에 대한 작업 영역이 열립니다.
1. ****  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings 런타임 설정을 선택합니다.**
1. 가운데 창에서 찾아보기를 선택하여 만든 키오스크 구성 XML 파일을 찾아 선택합니다. ****

   ![Windows 구성 디자이너의 MultiAppAssignedAccessSettings 필드 스크린샷](./images/multiappassignedaccesssettings.png)

1. **선택 사항.** (디바이스를 처음 설치한 후 프로비저닝 패키지를 적용하려는 경우 키오스크 장치에서 이미 사용할 수 있는 관리자 사용자가 있는 경우 이 단계를 건너뜁니다.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 사용자 계정을 생성합니다. 사용자 이름과 암호를 입력한 다음 **UserGroup**  >  **Administrators 를 선택합니다.**  
  
     이 계정을 사용하면 프로비저닝 상태 및 로그를 볼 수 있습니다.  
1. **선택 사항.** 키오스크 장치에 관리자가 아닌 계정이 이미 있는 경우 이 단계를 건너뜁니다. **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 로컬 사용자 계정을 생성합니다. 사용자 이름이 구성 XML에서 지정한 계정과 동일한지 확인 **UserGroup**  >  **Standard Users 를 선택합니다.**
1. 파일 **저장**  >  **을 선택합니다.**
1. ****  >  **프로비저닝 패키지 내보내기 를**선택한 다음 소유자 IT ****  >  **관리자 를 선택합니다.** 이렇게 하면 이 프로비저닝 패키지의 우선 순위가 다른 소스에서 이 장치에 적용되는 프로비저닝 패키지보다 더 높게 설정됩니다.
1. **다음**을 선택합니다.
1. **프로비저닝 패키지 보안 페이지에서** 보안 옵션을 선택합니다.
   > [!IMPORTANT]  
   > 패키지 서명 **사용을 선택하는**경우 패키지 서명에 사용할 유효한 인증서도 선택해야 합니다. 이렇게하려면 **찾아보기를** 선택하고 패키지에 서명하는 데 사용할 인증서를 선택합니다.
   
   > [!CAUTION]  
   > 패키지 암호화 사용 **을 선택하지 않습니다.** HoloLens 장치에서 이 설정을 사용하면 프로비전이 실패합니다.
1. **다음**을 선택합니다.
1. 프로비저닝 패키지를 구축할 때 사용할 출력 위치를 지정합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다. 출력 위치를 변경하려면 찾아보기를 **선택합니다.** 완료되면 다음 을 **선택합니다.**
1. **빌드를** 선택하여 패키지 빌드를 시작합니다. 프로비저닝 패키지를 빌드하는 데는 오랜 시간이 걸리지 않습니다. 빌드 페이지에 프로젝트 정보가 표시되고 진행률 표시줄에 빌드 상태가 표시됩니다.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>프로비저닝 패키지, 3단계 HoloLens에 프로비저닝 패키지 &ndash; 적용

"프로비저닝 패키지를 사용하여 HoloLens 구성" 문서에서는 다음과 같은 상황에서 프로비저닝 패키지를 적용하기 위한 자세한 지침을 제공합니다.

- 설치하는 동안 [처음에 HoloLens에 프로비저닝 패키지를 적용할 수 있습니다.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- 설치 후 [HoloLens에](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)프로비저닝 패키지를 적용할 수도 있습니다.

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Windows Device Portal을 사용하여 단일 앱 키오스크 설정

Windows Device Portal을 사용하여 키오스크 모드를 설정하려면 다음 단계를 수행합니다.

1. [Windows Device Portal을 사용할 HoloLens 장치를 설치합니다.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.

    > [!CAUTION]
    > 장치 포털을 사용하도록 HoloLens를 설정할 때 디바이스에서 개발자 모드를 사용하도록 설정해야 합니다. 비즈니스용 Windows Holographic이 있는 장치의 개발자 모드를 사용하면 앱을 테스트용 로드할 수 있습니다. 그러나 이 설정은 사용자가 Microsoft Store에서 인증되지 않은 앱을 설치할 수 있는 위험을 만듭니다. 관리자는 정책 [CSP의](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) **ApplicationManagement/AllowDeveloper Unlock** 설정을 사용하여 개발자 모드를 사용하도록 설정하는 기능을 차단할 수 있습니다. [개발자 모드에 대해 자세히 알아보세요.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 컴퓨터에서 [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 또는 USB를 사용하여 HoloLens에 [연결합니다.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. 다음 중 하나를 수행합니다.
   - Windows Device Portal에 처음으로 연결하는 경우 사용자 이름 및 [암호를 생성합니다.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 이전에 설정한 사용자 이름과 암호를 입력합니다.

    > [!TIP]
    > 브라우저에서 인증서 오류가 표시되는 경우 [문제 해결 단계](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)를 따릅니다.

1. Windows Device Portal에서 **키오스크**모드를 선택합니다.

1. **키오스크 모드 사용 을**선택하고 장치가 시작되면 실행할 앱을 선택한 다음 저장을 **선택합니다.**

    ![키오스크 모드](images/kiosk.png)
1. HoloLens를 다시 시작합니다. 여전히 디바이스 포털 페이지가 열려 있는 경우 페이지 맨 위에 **있는** 다시 시작을 선택할 수 있습니다.

> [!NOTE]
> 키오스크 모드는 하나의 필수 쿼리 문자열 매개 변수("kioskModeEnabled"와 값이 "true" 또는 "false"인 "kioskModeEnabled") 및 하나의 선택적 매개 변수(패키지 이름 값이 있는 "startupApp")를 사용하여 /api/holographic/kioskmode/settings에 POST를 수행하여 장치 포털의 REST API를 통해 설정할 수 있습니다. Device Portal은 개발자 전용으로, 개발자가 아닌 장치에서는 사용하도록 설정되어 있지 않습니다. REST API는 향후 업데이트/릴리스에서 변경될 수 있습니다.

## <a name="more-information"></a>추가 정보

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>프로비저닝 패키지를 사용하여 키오스크를 구성하는 방법을 시청합니다.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>전역 할당된 액세스 - 키오스크 모드
- 시스템 수준에서 키오스크 모드를 적용하는 새 Kiosk 메서드를 사용하도록 설정하여 키오스크의 ID 관리를 줄입니다.

이 새로운 기능을 통해 IT 관리자는 시스템 수준에서 적용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성할 수 있으며, 시스템의 ID와 관련이 없습니다. 이 기능은 장치에 로그인하는 모든 사용자에 적용됩니다. 이 새로운 기능에 대한 자세한 내용은 [HoloLens](hololens-global-assigned-access-kiosk.md) 전역 할당 액세스 키오스크 설명서를 참조하세요.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>다중 앱 키오스크 모드에서 응용 프로그램 자동 실행 
- 자동 앱 실행에 집중된 환경으로 키오스크 모드 환경을 위해 선택된 UI 및 앱 선택을 추가로 늘려야 합니다.

다중 앱 키오스크 모드에만 적용하며 할당된 액세스 구성에서 아래의 강조 표시된 특성을 사용하여 1개 앱만 자동 실행으로 지정될 수 있습니다. 

사용자가 로그인하면 응용 프로그램이 자동으로 시작됩니다. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리를 위한 키오스크 모드 동작 변경
- 키오스크 모드 오류 시 사용 가능한 앱을 제거하여 보다 안전한 키오스크 모드 

앞에서 키오스크 모드 적용에 오류가 발생했기 전에 HoloLens는 시작 메뉴에 모든 응용 프로그램을 표시하는 데 사용되었습니다. 이제 Windows Holographic 버전 20H2에서 오류가 발생하면 아래와 같이 시작 메뉴에 앱이 표시되지 않습니다. 

![키오스크 모드가 실패할 때 어떻게 보이는지의 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>오프라인 Kiosk에 대한 Azure AD 그룹 멤버 자격 캐시
- 오프라인 키오스크를 최대 60일 동안 Azure AD 그룹과 함께 사용할 수 있습니다.

이 정책은 로그인한 사용자의 Azure AD 그룹을 대상으로 하는 할당된 액세스 구성에 Azure AD 그룹 구성원 캐시를 사용할 수 있는 일 수를 제어합니다. 이 정책 값을 0보다 큰 값으로 설정하면 캐시가 사용되지 않습니다.  

이름: AADGroupMembershipCacheValidityInDays URI 값: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

최소 - 0일  
최대 - 60일 

이 정책을 올바르게 사용하는 단계: 
1. Azure AD 그룹을 대상으로 하는 키오스크에 대한 장치 구성 프로필을 만들고 HoloLens 디바이스에 할당합니다. 
1. 이 정책 값을 원하는 일 수(> 0)로 설정하고 HoloLens 장치에 할당하는 사용자 지정 OMA URI 기반 장치 구성을 생성합니다. 
    1. URI 값은 OMA-URI 텍스트 상자에 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays로 입력해야 합니다.
    1. 값은 최소/최대 허용 사이일 수 있습니다.
1. HoloLens 장치를 등록하고 두 구성이 장치에 적용되는지 확인합니다. 
1. 사용자가 로그인하고 Azure AD 그룹 구성원 자격이 확인되면 인터넷을 사용할 수 있는 경우 Azure AD 사용자 1 로그인이 가능하도록 설정하면 캐시가 만들어집니다. 
1. 이제 Azure AD 사용자 1은 HoloLens를 오프라인으로 전환하고 정책 값이 X일 수에 한해 키오스크 모드에 사용할 수 있습니다. 
1. 다른 Azure AD 사용자 N에 대해 4단계와 5단계를 반복할 수 있습니다. 여기서 핵심은 Azure AD 사용자가 적어도 Kiosk 구성이 대상으로 지정되는 Azure AD 그룹의 구성원인지 확인할 수 있도록 인터넷을 사용하여 장치에 로그인해야 하다는 것입니다. 
 
> [!NOTE]
> Azure AD 사용자에 대해 4단계를 수행할 때까지 "연결이 끊어진" 환경에 언급된 오류 동작이 발생합니다. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens용 XML 키오스크 코드 샘플

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure AD 그룹을 대상으로 하는 여러 앱 키오스크 모드입니다. 
이 키오스크는 Azure AD 그룹의 사용자에 대해 설정, 원격 지원 및 피드백 허브의 3개 앱을 포함하는 키오스크를 사용하도록 설정하는 키오스크를 배포합니다. 이 샘플을 즉시 사용하려면 아래 강조 표시된 GUID를 자신의 Azure AD 그룹과 일치하도록 변경해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD 계정을 대상으로 하는 여러 앱 키오스크 모드입니다.
이 키오스크는 단일 사용자에 대해 키오스크를 배포하며 설정, 원격 지원 및 피드백 허브의 3개 앱을 포함하는 키오스크를 사용하도록 설정합니다. 이 샘플을 즉시 사용하려면 아래 강조 표시된 계정을 자신의 Azure AD 계정과 일치하도록 변경해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

