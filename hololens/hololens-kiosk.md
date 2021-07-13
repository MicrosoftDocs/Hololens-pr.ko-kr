---
title: HoloLens를 키오스크로 설정
description: 키오스크 구성을 설정 및 사용하여 HoloLens 디바이스에서 앱을 잠그는 방법을 알아봅니다.
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
ms.openlocfilehash: 9d9e521f3e337b3a48a60c19e52bfeb3186507af
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640358"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens를 키오스크로 설정

키오스크 모드에서 실행하도록 디바이스를 구성하여 HoloLens 디바이스가 *키오스크라고도* 하는 고정 용도의 디바이스로 작동하도록 구성할 수 있습니다. 키오스크 모드는 디바이스에서 사용할 수 있는 애플리케이션(또는 사용자)을 제한합니다. 키오스크 모드는 HoloLens 디바이스를 비즈니스 앱에 전용으로 사용하거나 앱 데모에서 HoloLens 디바이스를 사용하는 데 사용할 수 있는 편리한 기능입니다.

이 문서에서는 HoloLens 디바이스와 관련한 키오스크 구성의 측면에 대한 정보를 제공합니다. 다양한 유형의 Windows 기반 키오스크 및 구성 방법에 대한 일반적인 내용은 [Windows 데스크톱 버전에서 키오스크 및 디지털 기호 구성을 참조하세요.](/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> 키오스크 모드는 사용자가 디바이스에 로그인할 때 사용할 수 있는 앱을 결정합니다. 그러나 키오스크 모드는 보안 방법이 아닙니다. "허용된" 앱이 허용되지 않는 다른 앱을 여는 것을 중지하지 않습니다. 앱 또는 프로세스가 열리지 않도록 차단하려면 [WDAC(Windows Defender Application Control) CSP를](/windows/client-management/mdm/applicationcontrol-csp) 사용하여 적절한 정책을 만듭니다.
>
> 사용자에게 HoloLens 2 사용하는 고급 수준의 보안을 제공하는 Microsoft 서비스 대해 자세히 [알아보고, 상태 분리 및 격리 - Defender 보호에](security-state-separation-isolation.md#defender-protections)대해 자세히 알아보세요. 또는 [WDAC 및 Windows PowerShell 사용하여 Microsoft Intune HoloLens 2 디바이스에서 앱을 허용하거나 차단하는](/mem/intune/configuration/custom-profile-hololens)방법을 알아봅니다.

단일 앱 또는 다중 앱 구성에서 키오스크 모드를 사용할 수 있으며, 세 가지 프로세스 중 하나를 사용하여 키오스크 구성을 설정하고 배포할 수 있습니다.

> [!IMPORTANT]  
> 다중 앱 구성을 삭제할 경우 할당된 액세스 기능이 만든 사용자 잠금 프로필이 제거됩니다. 그러나 모든 정책 변경 내용을 되돌리지는 않습니다. 이러한 정책을 되돌리려면 디바이스를 공장 설정으로 다시 설정해야 합니다.

## <a name="plan-the-kiosk-deployment"></a>키오스크 배포 계획

키오스크를 계획할 때 다음 질문에 대답할 수 있어야 합니다. 이 페이지를 읽는 동안 고려해야 할 몇 가지 결정 사항과 이러한 질문에 대한 몇 가지 고려 사항은 다음과 같습니다.
1. **Who 키오스크를 사용하게 되며 어떤 [유형의 계정을](hololens-identity.md) 사용하게 되나요?** 이는 이미 결정했으며 키오스크를 위해 조정해서는 안 되는 결정이지만 나중에 키오스크가 할당되는 방식에 영향을 줍니다.
1. **사용자/그룹당 다른 키오스크 또는 일부 키오스크를 사용하도록 설정하지 않았나요?** 그렇다면 XML을 통해 키오스크를 만들 수 있습니다. 
1. **키오스크에 있는 앱은 몇 개인가요?** 앱이 1개 이상 있는 경우 다중 앱 키오스크가 필요합니다. 
1. **키오스크에 있는 앱은 무엇인가요?** 아래의 AUMID 목록을 사용하여 사용자 고유의 앱 외에도 In-Box 앱을 추가하세요.
1. **키오스크를 배포하려면 어떻게 해야 할까요?** MDM에 디바이스를 등록하는 경우 MDM을 사용하여 키오스크를 배포하는 것이 좋습니다. MDM을 사용하지 않는 경우 프로비전 패키지와 함께 배포를 사용할 수 있습니다.  

### <a name="kiosk-mode-requirements"></a>키오스크 모드 요구 사항

키오스크 모드를 사용하도록 모든 HoloLens 2 디바이스를 구성할 수 있습니다.

> [!IMPORTANT]
> 키오스크 모드는 디바이스에 Windows Holographic for Business 경우에만 사용할 수 있습니다. 모든 HoloLens 2 디바이스는 Windows Holographic for Business 함께 제공되고 다른 버전은 없습니다. 모든 HoloLens 2 디바이스는 키오스크 모드를 바로 실행할 수 있습니다.
>
> os 빌드 및 OS 버전 측면에서 HoloLens(1세대) 디바이스를 모두 업그레이드해야 합니다. HoloLens(1세대)를 [Windows Holographic for Business](hololens1-upgrade-enterprise.md) 버전으로 업데이트하는 방법은 다음과 같습니다. 키오스크 모드를 사용하도록 HoloLens(1세대) 디바이스를 업데이트하려면 먼저 디바이스가 Windows 10, 버전 1803 이상에서 실행되는지 확인해야 합니다. Windows Device Recovery 도구를 사용하여 HoloLens(1세대) 디바이스를 기본 빌드로 복구했거나 최신 업데이트를 설치한 경우 디바이스를 구성할 준비가 된 것입니다.

> [!IMPORTANT]  
> 키오스크 모드에서 실행되는 디바이스를 보호하려면 USB 연결과 같은 기능을 해제하는 디바이스 관리 정책을 추가하는 것이 좋습니다. 또한 업데이트 링 설정을 확인하여 업무 시간 동안 자동 업데이트가 발생하지 않는지 확인합니다.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>단일 앱 키오스크 또는 다중 앱 키오스크 중에서 결정

단일 앱 키오스크는 사용자가 디바이스에 로그인할 때 지정된 앱을 시작합니다. Cortana 대로 시작 메뉴 사용할 수 없습니다. HoloLens 2 디바이스가 [시작](hololens2-basic-usage.md#start-gesture) 제스처에 응답하지 않습니다. HoloLens(1세대) 디바이스가 [꽃](hololens1-basic-usage.md) 제스처에 응답하지 않습니다. 하나의 앱만 실행할 수 있으므로 사용자는 다른 앱을 배치할 수 없습니다.

다중 앱 키오스크는 사용자가 디바이스에 로그인할 때 시작 메뉴 표시합니다. 키오스크 구성은 시작 메뉴 사용할 수 있는 앱을 결정합니다. 다중 앱 키오스크를 사용하면 사용자가 사용해야 하는 항목만 제시하고 사용하지 않아도 되는 항목만 제거하여 사용자에게 이해하기 쉬운 환경을 제공할 수 있습니다.

다음 표에서는 다양한 키오스크 모드의 기능 기능을 나열합니다.

| &nbsp; |시작 메뉴 |빠른 작업 메뉴 |카메라 및 비디오 |Miracast |Cortana |기본 제공 음성 명령 |
| --- | --- | --- | --- | --- | --- | --- | 
|단일 앱 키오스크 |사용 안 함 |사용 안 함 |사용 안 함 |사용 안 함   |사용 안 함 |사용<sup>1</sup> |
|다중 앱 키오스크 |사용 |사용<sup>2</sup> |사용 가능<sup>2</sup> |사용 가능<sup>2</sup> |사용 가능<sup>2, 3</sup>  |사용<sup>1</sup> |

> <sup>1</sup> 비활성화된 기능과 관련된 음성 명령이 작동하지 않습니다.  
> <sup>2</sup> 이러한 기능을 구성하는 방법에 대한 자세한 내용은 [키오스크 앱 선택을 참조하세요.](#plan-kiosk-apps)  
> <sup>3</sup> Cortana 사용하지 않도록 설정된 경우에도 기본 제공 음성 명령이 사용하도록 설정됩니다.

다음 표에서는 다양한 키오스크 모드의 사용자 지원 기능을 나열합니다.

| &nbsp; |지원되는 사용자 유형 | 자동 로그인 | 여러 액세스 수준 |
| --- | --- | --- | --- |
|단일 앱 키오스크 |Azure Active Directory(Azure AD) 또는 로컬 계정의 MSA(관리 서비스 계정) |예 |아니요 |
|다중 앱 키오스크 |Azure AD 계정 |아니요 |예 |

이러한 기능을 사용하는 방법의 예는 다음 표를 참조하세요.

|다음을 위해 단일 앱 키오스크를 사용합니다. |다음을 위해 다중 앱 키오스크를 사용합니다. |
| --- | --- |
|새 직원을 위한 Dynamics 365 가이드만 실행하는 디바이스입니다. |다양한 직원에 대한 가이드 및 원격 지원을 모두 실행하는 디바이스입니다. |
|사용자 지정 앱만 실행하는 디바이스입니다. |대부분의 사용자(사용자 지정 앱만 실행)의 키오스크로 작동하지만 특정 사용자 그룹에 대한 표준 디바이스로 작동하는 디바이스입니다. |

### <a name="plan-kiosk-apps"></a>키오스크 앱 계획

키오스크 앱을 선택하는 방법에 대한 일반적인 내용은 [할당된 액세스용 앱 선택 지침(키오스크 모드)을](/windows/configuration/guidelines-for-assigned-access-app)참조하세요.

Windows 장치 포털 사용하여 단일 앱 키오스크를 구성하는 경우 설치 프로세스 중에 앱을 선택합니다.  

MDM(모바일 장치 관리) 시스템 또는 프로비전 패키지를 사용하여 키오스크 모드를 구성하는 경우 [AssignedAccess CSP(구성 서비스 공급자)를](/windows/client-management/mdm/assignedaccess-csp) 사용하여 애플리케이션을 지정합니다. CSP는 [AUMID(애플리케이션 사용자 모델 ID)를](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 사용하여 애플리케이션을 식별합니다. 다음 표에서는 다중 앱 키오스크에서 사용할 수 있는 일부 바로 사용 애플리케이션의 AUMID를 나열합니다.

> [!IMPORTANT]
> 키오스크 모드는 사용자가 디바이스에 로그인할 때 사용할 수 있는 앱을 결정합니다. 그러나 키오스크 모드는 보안 방법이 아닙니다. "허용된" 앱이 허용되지 않는 다른 앱을 여는 것을 중지하지 않습니다. 이 동작을 제한하지 않으므로 Edge, 파일 탐색기 및 Microsoft Store 앱에서 앱을 계속 출시할 수 있습니다. 키오스크에서 시작하지 않으려는 특정 앱이 있는 경우 [WDAC(Windows Defender Application Control) CSP를](/windows/client-management/mdm/applicationcontrol-csp) 사용하여 적절한 정책을 만듭니다. 
> 
> 또한 Mixed Reality Home은 키오스크 앱으로 설정할 수 없습니다.

<a id="aumids"></a>

|앱 이름 |AUMID |
| --- | --- |
|3D 뷰어 |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|캘린더 |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|카메라<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|HoloLens 디바이스 선택기(1세대) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2 디바이스 선택기 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|피드백 &nbsp; 허브 |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|파일 탐색기 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! 앱 |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|이전 Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|새 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! 앱 |
|Miracast<sup>4</sup> |&nbsp; |
|영화 & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|사진 |Microsoft. Windows. \_사진 8wekyb3d8bbwe \! 앱 |
|이전 설정 |HolographicSystemSettings_cw5n1h2txyewy! 앱 |
|새 설정 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 앱 |
|팁 |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 사진 또는 비디오 캡처를 사용하도록 설정하려면 카메라 앱을 키오스크 앱으로 사용하도록 설정해야 합니다.  
> <sup>2</sup> 카메라 앱을 사용하도록 설정하는 경우 다음 조건에 유의하세요.
> - 빠른 작업 메뉴에는 사진 및 비디오 단추가 포함됩니다.  
> - 그림과 상호 작용하거나 사진을 검색할 수 있는 앱(예: 사진, 메일 또는 OneDrive)도 사용하도록 설정해야 합니다.  
>  
> <sup>3</sup> 키오스크 앱으로 Cortana 사용하도록 설정하지 않은 경우에도 기본 제공 음성 명령이 사용하도록 설정됩니다. 그러나 비활성화된 기능과 관련된 명령은 아무런 영향을 미치지 않습니다.  
> <sup>4</sup> Miracast 직접 사용하도록 설정할 수 없습니다. 키오스크 앱으로 Miracast 사용하도록 설정하려면 카메라 앱 및 디바이스 선택기 앱을 사용하도록 설정합니다.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>사용자 또는 그룹에 대한 키오스크 프로필 계획

xml 파일을 만들거나 Intune의 UI를 사용하여 키오스크를 설정하는 경우 키오스크 사용자가 누구인지 고려해야 합니다. 키오스크 구성은 개별 계정 또는 Azure AD 그룹으로 제한될 수 있습니다. 

일반적으로 키오스크는 사용자 또는 사용자 그룹에 대해 사용하도록 설정됩니다. 그러나 사용자 고유의 XML 키오스크를 작성하려는 경우 ID에 관계없이 키오스크가 디바이스 수준에서 적용되는 전역 할당 액세스를 고려할 수 있습니다. 이 경우 전역 [할당 액세스 키오스크에 대해 자세히 읽어 볼 수 있습니다.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>XML 파일을 만드는 경우:
-   여러 키오스크 프로필을 만들고 각 키오스크 프로필을 서로 다른 사용자/그룹에 할당합니다. 여러 앱이 있는 Azure AD 그룹에 대한 키오스크 및 단일 앱이 있는 여러 앱 키오스크가 있는 Visitor와 같은
-   키오스크 구성을 프로필 **ID라고** 하며 GUID가 있습니다.
-   사용자 유형을 지정하고 **DefaultProfile ID** 에 동일한 GUID를 사용하여 configs 섹션에서 해당 프로필을 할당합니다.
- 사용자 지정 OMA URI 디바이스 구성 프로필을 만들고 URI 값을 사용하여 HoloLens 디바이스 그룹에 적용하여 MDM을 통해 XML 파일을 만들 수 있지만 여전히 디바이스에 적용할 수 있습니다. ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune에서 키오스크를 만드는 경우
-   각 디바이스는 단일 키오스크 프로필만 받을 수 있습니다. 그렇지 않으면 충돌이 생성되고 키오스크 구성이 전혀 수신되지 않습니다. 
    -   키오스크 구성 프로필과 관련이 없는 디바이스 제한과 같은 다른 종류의 프로필 및 정책은 키오스크 구성 프로필과 충돌하지 않습니다.
-   키오스크는 사용자 로그온 유형의 일부인 모든 사용자에 대해 사용하도록 설정됩니다. 이 키오스크는 사용자 또는 Azure AD 그룹으로 설정됩니다. 
-   키오스크 구성이 설정되고 **사용자 로그온** 유형(키오스크에 로그인할 수 있는 사용자)이 선택되고 앱이 선택된 후에도 디바이스 구성을 그룹에 할당해야 합니다. 할당된 그룹은 키오스크 디바이스 구성을 수신하는 디바이스를 결정합니다. 그러나 키오스크가 활성화되어 있는지 여부는 상호 작용하지 않습니다. 
    - Intune에서 구성 프로필을 할당할 때의 영향에 대한 자세한 내용은 [Microsoft Intune 사용자 및 디바이스 프로필 할당을 참조하세요.](/intune/configuration/device-profile-assign)

### <a name="select-a-deployment-method"></a>배포 방법 선택

다음 방법 중 하나를 선택하여 키오스크 구성을 배포할 수 있습니다.

- [Microsoft Intune 또는 기타 MDM(모바일 디바이스 관리) 서비스](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [패키지 프로비전](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 이 방법을 사용하려면 디바이스에서 개발자 모드를 사용하도록 설정해야 하므로 데모에만 사용하는 것이 좋습니다.

다음 표에서는 각 배포 방법의 기능 및 이점을 나열합니다.

| &nbsp; |Windows 장치 포털 사용하여 배포 |프로비전 패키지를 사용하여 배포 |MDM을 사용하여 배포 |
| --------------------------- | ------------- | -------------------- | ---- |
|단일 앱 키오스크 배포   | 예           | 예                  | 예  |
|다중 앱 키오스크 배포    | 아니요            | 예                  | 예  |
|로컬 디바이스에만 배포 | 예           | 예                  | 아니요   |
|개발자 모드를 사용하여 배포 |필수       | 필요 없음            | 필요 없음   |
|Azure Active Directory(Azure AD)를 사용하여 배포  | 필요 없음            | 필요 없음                   | 필수  |
|자동으로 배포      | 아니요            | 아니요                   | 예  |
|배포 속도            | 빠름       | 빠름                 | 느림 |
|대규모 배포 | 권장하지 않음    | 권장        | 권장 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Microsoft Intune 또는 기타 MDM을 사용하여 단일 앱 또는 다중 앱 키오스크 설정

Microsoft Intune 또는 다른 MDM 시스템을 사용하여 키오스크 모드를 설정하려면 다음 단계를 수행합니다.

1. [디바이스 등록을 준비합니다.](#mdmenroll)
1. [키오스크 구성 프로필을 만듭니다.](#mdmprofile)
1. 키오스크를 구성합니다.
   - [단일 앱 키오스크에 대한 설정을 구성합니다.](#mdmconfigsingle)
   - [다중 앱 키오스크에 대한 설정을 구성합니다.](#mdmconfigmulti)
1. [키오스크 구성 프로필을 그룹에 할당합니다.](#mdmassign)
1. 디바이스를 배포합니다.
   - [단일 앱 키오스크](#mdmsingledeploy)를 배포합니다.
   - [다중 앱 키오스크](#mdmmultideploy)를 배포합니다.

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, 1단계 &ndash; 디바이스 등록 준비

사용자가 처음 로그인하거나 사용자가 디바이스를 수동으로 등록할 때 HoloLens 디바이스를 자동으로 등록하도록 MDM 시스템을 구성할 수 있습니다. 또한 디바이스를 Azure AD 도메인에 조인하고 적절한 그룹에 할당해야 합니다.

디바이스를 등록하는 방법에 대한 자세한 내용은 [MDM에 HoloLens 등록](hololens-enroll-mdm.md) 및 [Windows 디바이스에 대한 Intune 등록 방법을 참조하세요.](/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, 2단계 &ndash; 키오스크 구성 프로필 만들기

1. [Azure](https://portal.azure.com/) Portal을 열고 Intune 관리자 계정에 로그인합니다.
1. **Microsoft Intune** 디바이스 구성 - 프로필 프로필  >    >  **만들기를** 선택합니다.
1. 프로필 이름을 입력합니다.
1. **플랫폼**  >  **Windows 10 이상 을** 선택한 다음 **프로필 유형**  > **디바이스 제한을** 선택합니다.
1.   >  **키오스크** 구성을 선택한 다음, 다음 중 하나를 선택합니다.
   - 단일 앱 키오스크를 만들려면 **키오스크 모드**  >  **단일 앱 키오스크 를** 선택합니다.
   - 다중 앱 키오스크를 만들려면 **키오스크 모드**  >  **다중 앱 키오스크 를** 선택합니다.
1. 키오스크 구성을 시작하려면 **추가를** 선택합니다.

다음 단계는 원하는 키오스크 유형에 따라 달라집니다. 자세한 내용은 다음 옵션 중 하나를 선택합니다.  

- [단일 앱 키오스크](#mdmconfigsingle)
- [다중 앱 키오스크](#mdmconfigmulti)

키오스크 구성 프로필을 만드는 방법에 대한 자세한 내용은 [intune을 사용하여 전용 키오스크로 실행하도록 디바이스 설정 Windows 10 및 Windows Holographic for Business 참조하세요.](/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, 3단계(단일 앱) &ndash;  단일 앱 키오스크에 대한 설정 구성

이 섹션에서는 단일 앱 키오스크에 필요한 설정을 요약합니다. 자세한 내용은 다음 문서를 참조하세요.

- Intune에서 키오스크 구성 프로필을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune 사용하여 키오스크 모드를 구성하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조하세요.
- Intune에서 단일 앱 키오스크에 사용 가능한 설정에 대한 자세한 내용은 [단일 전체 화면 앱 키오스크를 참조하세요.](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. 사용자 지정 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 [키오스크 구성 을 정의하는 XML 파일을 만듭니다.](#ppkioskconfig)

1. **사용자 로그온 유형** 로컬 사용자 계정 을 선택한  >  다음, 키오스크에 로그인할 수 있는 로컬(디바이스) 계정 또는 MSA(Microsoft 계정)의 사용자 이름을 입력합니다.
   > [!NOTE]  
   > **자동 로그온** 사용자 계정 유형은 Windows Holographic for Business에서 지원되지 않습니다.
1. **애플리케이션 유형**  >  **스토어 앱을** 선택한 다음, 목록에서 앱을 선택합니다.

다음 단계는 그룹에 프로필을 [할당하는](#mdmassign) 것입니다.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, 3단계(다중 앱) &ndash; 다중 앱 키오스크에 대한 설정 구성

이 섹션에서는 다중 앱 키오스크에 필요한 설정을 요약합니다. 자세한 내용은 다음 문서를 참조하세요.

- Intune에서 키오스크 구성 프로필을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune 사용하여 키오스크 모드를 구성하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조하세요.
- Intune에서 다중 앱 키오스크에 사용할 수 있는 설정에 대한 자세한 내용은 [다중 앱 키오스크를 참조하세요.](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. 사용자 지정 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 [키오스크 구성 을 정의하는 XML 파일을 만듭니다.](#ppkioskconfig) XML 파일을 사용하는 경우 [시작 레이아웃](#start-layout-for-hololens)을 포함해야 합니다.  
- 필요에 따라 Intune 또는 다른 MDM 서비스에서 사용자 지정 시작 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM(Intune 및 기타)에 대한 레이아웃 파일 시작을](#start-layout-file-for-mdm-intune-and-others)참조하세요.

1. **S 모드 디바이스에서 대상 Windows 10**  >  아니요를 선택합니다.  
>[!NOTE]  
> Windows Holographic for Business에서는 S 모드가 지원되지 않습니다.

1. **사용자 로그온 유형** Azure  >  **AD 사용자 또는 그룹 또는** 방문자 HoloLens 사용자 **로그온 유형을** 선택한  >  다음, 하나 이상의 사용자 그룹 또는 계정을 추가합니다.  

   **사용자 로그온 유형에서** 지정한 그룹 또는 계정에 속한 사용자만 키오스크 환경을 사용할 수 있습니다.

1. 다음 옵션을 사용하여 하나 이상의 앱을 선택합니다.
   - 업로드된 사업장 앱을 추가하려면 **스토어 앱 추가를** 선택한 다음, 원하는 앱을 선택합니다.
   - AUMID를 지정하여 앱을 추가하려면 **AUMID로 추가를** 선택한 다음, 앱의 AUMID를 입력합니다. [사용 가능한 AUMID 목록을 참조하세요.](#aumids)

다음 단계는 그룹에 프로필을 [할당하는](#mdmassign) 것입니다.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, 4단계 &ndash; 그룹에 키오스크 구성 프로필 할당

키오스크 구성 프로필의 **할당** 페이지를 사용하여 키오스크 구성을 배포할 위치를 설정할 수 있습니다. 가장 간단한 경우 디바이스가 MDM에 등록될 때 HoloLens 디바이스를 포함할 그룹에 키오스크 구성 프로필을 할당합니다.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5단계(단일 앱) &ndash; 단일 앱 키오스크 배포

MDM 시스템을 사용하는 경우 OOBE 중에 MDM에 디바이스를 등록할 수 있습니다. OOBE가 완료되면 디바이스에 쉽게 로그인할 수 있습니다.

OOBE 중에 다음 단계를 수행합니다.

1. 키오스크 구성 프로필에 지정한 계정을 사용하여 로그인합니다.
1. 디바이스를 등록합니다. 키오스크 구성 프로필이 할당된 그룹에 디바이스가 추가되었는지 확인합니다.
1. OOBE가 완료되고, 스토어 앱이 다운로드 및 설치되고, 정책이 적용될 때까지 기다립니다. 그런 다음, 디바이스를 다시 시작합니다.

다음에 디바이스에 로그인하면 키오스크 앱이 자동으로 시작됩니다.

이 시점에서 키오스크 구성이 표시되지 않으면 [할당 상태를 확인합니다.](/intune/configuration/device-profile-monitor)

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5단계(다중 앱) &ndash; 다중 앱 키오스크 배포

MDM 시스템을 사용하는 경우 Azure AD 테넌트에서 디바이스를 조인하고 OOBE 중에 MDM에 디바이스를 등록할 수 있습니다. 해당하는 경우 OOBE 프로세스 중에 사용할 수 있도록 사용자에게 등록 정보를 제공합니다.

> [!NOTE]  
> 사용자가 포함된 그룹에 키오스크 구성 프로필을 할당한 경우 해당 사용자 계정 중 하나가 디바이스에 로그인하는 첫 번째 계정인지 확인합니다.

OOBE 중에 다음 단계를 수행합니다.

1. **사용자 로그온 유형** 그룹에 속한 계정을 사용하여 로그인합니다.
1. 디바이스를 등록합니다.
1. 키오스크 구성 프로필의 일부인 앱이 다운로드되어 설치되기를 기다립니다. 또한 정책이 적용될 때까지 기다립니다.  
1. OOBE가 완료되면 Microsoft 스토어에서 또는 테스트용 로드를 통해 추가 앱을 설치할 수 있습니다. 디바이스가 속한 그룹에 [필요한 앱이](/mem/intune/apps/apps-deploy#assign-an-app) 자동으로 설치됩니다.
1. 설치가 완료되면 디바이스를 다시 시작합니다.

다음에 **사용자 로그온 유형** 에 속하는 계정을 사용하여 디바이스에 로그인하면 키오스크 앱이 자동으로 시작됩니다.

이 시점에서 키오스크 구성이 표시되지 않으면 [할당 상태를 확인합니다.](/intune/configuration/device-profile-monitor)

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>프로비전 패키지를 사용하여 단일 앱 또는 다중 앱 키오스크 설정

프로비전 패키지를 사용하여 키오스크 모드를 설정하려면 다음 단계를 수행합니다.

1. [시작 레이아웃](#start-layout-for-hololens)을 포함하여 [키오스크 구성을 정의하는 XML 파일을 만듭니다.](#ppkioskconfig)
2. [프로비전 패키지에 XML 파일을 추가합니다.](#ppconfigadd)
3. [프로비전 패키지를 HoloLens 적용합니다.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>패키지 프로비전, 1단계 &ndash; 키오스크 구성 XML 파일 만들기

일반 지침에 따라 다음을 제외하고 [Windows 데스크톱용 키오스크 구성 XML 파일을 만듭니다.](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)

- 클래식 Windows 애플리케이션(Win32)은 포함하지 않습니다. HoloLens 이러한 애플리케이션을 지원하지 않습니다.
- 자리 [표시자 Start layout XML](#start-layout-for-hololens) for HoloLens 사용합니다.
- 선택 사항: 키오스크 구성에 게스트 액세스 추가

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>선택 사항: 키오스크 구성에 게스트 액세스 추가

XML [파일의 **Configs** 섹션에서](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)게스트가 키오스크를 사용할 수 있도록 **Visitor라는** 특수 그룹을 구성할 수 있습니다. 키오스크가 **Visitor** 특수 그룹을 지원하도록 구성된 경우 "**게스트"** 옵션이 로그인 페이지에 추가됩니다. **게스트** 계정에는 암호가 필요하지 않으며 계정과 연결된 모든 데이터는 계정이 로그인할 때 삭제됩니다.

**게스트** 계정을 사용하도록 설정하려면 키오스크 구성 XML에 다음 조각을 추가합니다.

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>방문자 자동 로그온 사용

빌드 Windows [Holographic 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 이상:
- AAD 및 비 ADD 구성은 모두 키오스크 모드에 대해 자동 로그온이 설정된 방문자 계정을 지원합니다.

##### <a name="non-aad-configuration"></a>비 AAD 구성

1. 다음과 같은 프로비저닝 패키지를 만듭니다.
    1. 방문자 계정을 허용하도록 런타임 설정/AssignedAccess를 구성합니다.
    1. 필요에 따라 나중에 관리될 수 있도록 MDM(런타임 설정/작업 공간/등록)에 디바이스를 등록합니다.
    1. 로컬 계정을 만들지 않음
2. [프로비전 패키지 를 적용합니다.](hololens-provisioning.md)

##### <a name="aad-configuration"></a>AAD 구성

키오스크 모드로 구성된 AAD 조인 디바이스는 로그인 화면에서 단일 단추 탭으로 방문자 계정에 로그인할 수 있습니다. 방문자 계정에 로그인하면 방문자가 시작 메뉴에서 명시적으로 로그아웃되거나 디바이스가 다시 시작될 때까지 디바이스에서 다시 로그인하라는 메시지가 표시되지 않습니다.

방문자 자동 로그온은 [사용자 지정 OMA-URI 정책을](/mem/intune/configuration/custom-settings-windows-10)통해 관리될 수 있습니다.

- URI 값: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| 정책 |설명 |구성 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 방문자가 키오스크에 자동으로 로그온할 수 있습니다. | 1(예), 0(아니요, 기본값) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens 대한 자리 표시자 시작 레이아웃

[프로비전 패키지를](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 사용하여 다중 앱 키오스크를 구성하는 경우 프로시저에 시작 레이아웃이 필요합니다. 시작 레이아웃 사용자 지정은 Windows Holographic for Business 지원되지 않습니다. 따라서 자리 표시자 시작 레이아웃을 사용해야 합니다.

> [!NOTE]  
> 단일 앱 키오스크는 사용자가 로그인할 때 키오스크 앱을 시작하므로 시작 메뉴 사용하지 않으며 시작 레이아웃을 가질 필요가 없습니다.

> [!NOTE]  
> [MDM을](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 사용하여 다중 앱 키오스크를 설정하는 경우 필요에 따라 시작 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM(Intune 및 기타)에 대한 자리 표시자 시작 레이아웃 파일을](#start-layout-file-for-mdm-intune-and-others)참조하세요.

시작 레이아웃의 경우 키오스크 프로비전 XML 파일에 다음 **StartLayout** 섹션을 추가합니다.

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM에 대한 자리 표시자 시작 레이아웃 파일(Intune 등)

다음 샘플을 XML 파일로 저장합니다. Microsoft Intune(또는 키오스크 프로필을 제공하는 다른 MDM 서비스)에서 다중 앱 키오스크를 구성할 때 이 파일을 사용할 수 있습니다.

> [!NOTE]
> 사용자 지정 설정 및 전체 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 [프로비전 패키지](#start-layout-for-hololens)에 대한 시작 레이아웃 지침을 사용합니다.

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. 패키지, 2단계 &ndash; 프로비전 패키지에 키오스크 구성 XML 파일 추가

1. Windows 구성 디자이너 를 [엽니다.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. **고급 프로비저닝을** 선택하고 프로젝트의 이름을 입력한 후 **다음을** 선택합니다.
1. **Windows 10 Holographic** 선택하고 **다음을** 선택합니다.
1. **마침** 을 선택합니다. 패키지에 대한 작업 영역이 열립니다.
1. **런타임 설정**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings 를** 선택합니다.
1. 가운데 창에서 **찾아보기를** 선택하여 만든 키오스크 구성 XML 파일을 찾아 선택합니다.

   ![Windows 구성 디자이너의 MultiAppAssignedAccessSettings 필드 스크린샷](./images/multiappassignedaccesssettings.png)

1. **선택 사항입니다**. (디바이스를 처음 설치한 후 프로비전 패키지를 적용하려는데 키오스크 디바이스에서 이미 사용할 수 있는 관리 사용자가 있는 경우 이 단계를 건너뜁니다.) **런타임 설정** 계정 사용자 를 선택한 &gt;  &gt; 다음, 사용자 계정을 만듭니다. 사용자 이름 및 암호를 입력한 **다음, UserGroup**  >  **Administrators를** 선택합니다.  
  
     이 계정을 사용하여 프로비전 상태 및 로그를 볼 수 있습니다.  
1. **선택 사항입니다**. (키오스크 디바이스에 관리자가 아닌 계정이 이미 있는 경우 이 단계를 건너뜁니다.) **런타임 설정** 계정 사용자 를 선택한 &gt;  &gt; 다음, 로컬 사용자 계정을 만듭니다. 사용자 이름이 구성 XML에서 지정한 계정과 동일한지 확인합니다. **사용자 그룹**  >  **표준 사용자** 를 선택합니다.
1. **파일** > **저장** 을 선택합니다.
1.   >  **프로비전 패키지 내보내기** 를 선택한 **다음, 소유자**  >  **IT 관리자** 를 선택합니다. 이렇게 하면 이 프로비전 패키지의 우선 순위가 다른 원본에서 이 디바이스에 적용되는 프로비저닝 패키지보다 높습니다.
1. **다음** 을 선택합니다.
1. 패키지 **보안 프로비전** 페이지에서 보안 옵션을 선택합니다.
   > [!IMPORTANT]  
   > 패키지 서명 사용을 선택하는 경우 **패키지 서명에** 사용할 유효한 인증서도 선택해야 합니다. 이렇게 하려면 **찾아보기를** 선택하고 패키지 서명에 사용할 인증서를 선택합니다.
   
   > [!CAUTION]  
   > **패키지 암호화 사용을** 선택하지 마십시오. HoloLens 디바이스에서 이 설정으로 인해 프로비전이 실패합니다.
1. **다음** 을 선택합니다.
1. 프로비전 패키지를 빌드할 때 이동하려는 출력 위치를 지정합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다. 출력 위치를 변경하려면 **찾아보기를** 선택합니다. 작업을 마쳤으면 **다음** 을 선택합니다.
1. **빌드를** 선택하여 패키지 빌드를 시작합니다. 프로비전 패키지를 빌드하는 데 시간이 오래 걸리지 않습니다. 빌드 페이지에 프로젝트 정보가 표시되고 진행률 표시줄에 빌드 상태가 표시됩니다.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>프로비전 패키지, 3단계 &ndash; 프로비전 패키지를 적용하여 HoloLens

"프로비저닝 패키지를 사용하여 HoloLens 구성" 문서에서는 다음과 같은 상황에서 프로비전 패키지를 적용하는 자세한 지침을 제공합니다.

- 처음에는 설치 [중에 프로비전 패키지를 HoloLens 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)수 있습니다.

- [설치 후 프로비전 패키지를 HoloLens 적용할](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)수도 있습니다.

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Windows 장치 포털 사용하여 단일 앱 키오스크 설정

Windows 장치 포털 사용하여 키오스크 모드를 설정하려면 다음 단계를 수행합니다.

1. [Windows 장치 포털 사용하도록 HoloLens 디바이스를 설정합니다.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.

    > [!CAUTION]
    > 장치 포털 사용하도록 HoloLens 설정하는 경우 디바이스에서 개발자 모드를 사용하도록 설정해야 합니다. Windows Holographic for Business 있는 디바이스의 개발자 모드를 사용하면 앱을 사이드로드할 수 있습니다. 그러나 이 설정은 사용자가 Microsoft Store 인증되지 않은 앱을 설치할 수 있는 위험을 만듭니다. 관리자는 [정책 CSP에서](/windows/client-management/mdm/policy-configuration-service-provider) **ApplicationManagement/AllowDeveloper 잠금 해제** 설정을 사용하여 개발자 모드를 사용하도록 설정하는 기능을 차단할 수 있습니다. [개발자 모드에 대해 자세히 알아보세요.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 컴퓨터에서 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 또는 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)를 사용 하 여 HoloLens에 연결 합니다.

1. 다음 중 하나를 수행합니다.
   - Windows 장치 포털에 처음 연결 하는 경우 [사용자 이름 및 암호를 만듭니다](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password) .
   - 이전에 설정한 사용자 이름 및 암호를 입력 합니다.

    > [!TIP]
    > 브라우저에 인증서 오류가 표시 되 면 [다음 문제 해결 단계](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)를 수행 합니다.

1. Windows 장치 포털에서 **키오스크 모드** 를 선택 합니다.

1. **키오스크 모드 사용** 을 선택 하 고 장치가 시작 될 때 실행할 앱을 선택한 다음 **저장** 을 선택 합니다.

    ![키오스크 모드](images/kiosk.png)
1. HoloLens를 다시 시작 합니다. 장치 포털 페이지가 열려 있는 상태에서 페이지 위쪽에 있는 **다시 시작** 을 선택할 수 있습니다.

> [!NOTE]
> "True&quot; 또는 &quot;false&quot; 값을 가진 필수 쿼리 문자열 매개 변수 (&quot;kioskModeEnabled")와 하나의 선택적 매개 변수 (패키지 이름 값이 있는 "startupApp")를 사용 하 여/api/holographic/kioskmode/settings에 대 한 POST를 수행 하 여 장치 포털의 REST API을 통해 키오스크 모드를 설정할 수 있습니다. 장치 포털은 개발자만을 위한 것 이며 개발자가 아닌 장치에서는 사용 하지 않도록 설정 해야 합니다. REST API 향후 업데이트/릴리스에서 변경 될 수 있습니다.

## <a name="more-information"></a>추가 정보

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>프로 비전 패키지를 사용 하 여 키오스크를 구성 하는 방법을 시청 하세요.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>전역 할당 액세스-키오스크 모드
- 시스템 수준에서 키오스크 모드를 적용 하는 새 키오스크 방법을 사용 하도록 설정 하 여 키오스크에 대 한 Id 관리를 줄였습니다.

이 새로운 기능을 사용 하면 IT 관리자가 시스템 수준에서 적용할 수 있는 여러 앱 키오스크 모드에 대 한 HoloLens 2 장치를 구성 하 고, 시스템의 id로 선호도를 적용 하지 않으며, 장치에 로그인 하는 모든 사용자에 게 적용할 수 있습니다. 이 새로운 기능에 대 한 자세한 내용은 [전역 할당 된 액세스 키오스크 설명서 HoloLens](hololens-global-assigned-access-kiosk.md) 를 참조 하세요.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>다중 앱 키오스크 모드에서 응용 프로그램 자동 시작 
- 자동 앱 시작에 초점을 맞춘 경험을 통해 키오스크 모드 환경에 대해 선택한 UI 및 앱 선택 항목을 더 늘립니다.

다중 앱 키오스크 모드에만 적용 되며 할당 된 액세스 구성에서 아래 강조 표시 된 특성을 사용 하 여 자동으로 실행 되도록 1 개의 앱만 지정할 수 있습니다. 

사용자가 로그인 하면 응용 프로그램이 자동으로 시작 됩니다. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리에 대 한 키오스크 모드 동작 변경 내용
키오스크 모드를 적용 하는 동안 오류가 발생할 경우 다음과 같은 동작이 나타납니다.

- Windows Holographic 이전 버전 20h2-HoloLens는 시작 메뉴의 모든 응용 프로그램을 표시 합니다.
- Windows Holographic, 버전 20H2-장치에 할당 된 전역 액세스 권한 및 AAD 그룹 구성원 모두의 조합에 해당 하는 키오스크 구성이 있는 경우 AAD 그룹 멤버 자격을 확인 하지 못하면 사용자에 게 "시작에 표시 되지 않음" 메뉴가 표시 됩니다.

![이제 실패할 때 표시 되는 키오스크 모드 이미지입니다.](images/hololens-kiosk-failure-behavior.png )


- [Windows Holographic, 버전 21h1](hololens-release-notes.md#windows-holographic-version-21h1)부터 키오스크 모드는 빈 시작 메뉴를 표시 하기 전에 전역 할당 된 액세스를 찾습니다. 키오스크 환경은 AAD 그룹 키오스크 모드 중 오류가 발생 하는 경우 전역 키오스크 구성 (있는 경우)으로 대체 됩니다.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>오프 라인 키오스크를 위한 Azure AD 그룹 멤버 자격 캐시

- 키오스크 모드 오류 시 사용 가능한 앱을 제거 하 여 더 안전한 키오스크 모드.
- 최대 60 일 동안 Azure AD 그룹에 오프 라인 키오스크를 사용 하도록 설정 했습니다.

이 정책은 로그인 한 사용자에 대해 Azure AD 그룹을 대상으로 하는 할당 된 액세스 구성에 사용할 수 있는 Azure AD 그룹 멤버 자격 캐시의 일 수를 제어 합니다. 이 정책 값이 0 보다 큰 값으로 설정 된 경우에만 캐시가 사용 됩니다.  

이름: AADGroupMembershipCacheValidityInDays URI 값:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

최소-0 일  
최대-60 일 

이 정책을 올바르게 사용 하는 단계: 
1. 키오스크를 대상으로 하는 Azure AD 그룹을 대상으로 하는 장치 구성 프로필을 만들고 HoloLens 장치에 할당 합니다. 
1. 이 정책 값을 원하는 일 수 (> 0)로 설정 하 고 HoloLens 장치에 할당 하는 사용자 지정 OMA URI 기반 장치 구성을 만듭니다. 
    1. URI 값은 OMA-URI 텍스트 상자에./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays로 입력 해야 합니다.
    1. 허용 되는 최소값/최대값 사이에 값을 지정할 수 있습니다.
1. HoloLens 장치를 등록 하 고 두 구성이 장치에 적용 되는지 확인 합니다. 
1. 인터넷을 사용할 수 있을 때 Azure AD 사용자 1 로그인 허용, 사용자 로그인 및 Azure AD 그룹 멤버 자격이 성공적으로 확인 되 면 캐시가 생성 됩니다. 
1. 이제 Azure AD 사용자 1이 오프 라인에서 HoloLens 하 고, 정책 값에서 X 일 수를 허용 하는 한 키오스크 모드에 사용할 수 있습니다. 
1. 다른 모든 Azure AD 사용자에 대해 4 단계와 5 단계를 반복할 수 있습니다. 중요 한 점은 Azure AD 사용자가 인터넷을 사용 하 여 장치에 로그인 해야 하는 것입니다 .이는 적어도 한 번은 키오스크 구성이 대상으로 하는 Azure AD 그룹의 구성원 인지 확인할 수 있습니다. 
 
> [!NOTE]
> Azure AD 사용자에 대해 4 단계를 수행 하기 전에는 "연결이 끊어진" 환경에서 언급 한 오류 동작이 발생 합니다. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens에 대 한 XML 키오스크 코드 샘플

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure AD 그룹을 대상으로 하는 여러 앱 키오스크 모드입니다. 
이 키오스크는 Azure AD 그룹의 사용자에 대 한 키오스크를 배포 하며, 설정, 원격 지원 및 피드백 허브의 3 개 앱을 포함 하는 키오스크를 사용 하도록 설정 합니다. 이 샘플을 즉시 사용할 수 있도록 수정 하려면 아래에 강조 표시 된 GUID를 자신의 Azure AD 그룹에 맞게 변경 해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD 계정을 대상으로 하는 여러 앱 키오스크 모드입니다.
이 키오스크는 단일 사용자를 위해 키오스크를 배포 하며, 설정, 원격 지원 및 피드백 허브의 3 개 앱을 포함 하는 키오스크를 사용 하도록 설정 합니다. 이 샘플을 즉시 사용할 수 있도록 수정 하려면 아래에 강조 표시 된 계정을 자신의 Azure AD 계정과 일치 하도록 변경 해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

