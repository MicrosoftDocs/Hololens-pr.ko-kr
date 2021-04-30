---
title: HoloLens를 키오스크로 설정
description: 키오스크 구성을 설정 하 고 사용 하 여 HoloLens 장치에서 앱을 잠그는 방법에 대해 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309570"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens를 키오스크로 설정

키오스크 모드에서 실행 되도록 장치를 구성 하 여 *키오스크* 라고도 하는 고정 용도의 장치로 작동 하도록 HoloLens 장치를 구성할 수 있습니다. 키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램 (또는 사용자)을 제한 합니다. 키오스크 모드는 HoloLens 장치를 비즈니스 앱에 전용으로 사용 하거나 앱 데모에서 HoloLens 장치를 사용 하는 데 사용할 수 있는 편리한 기능입니다.

이 문서에서는 HoloLens 장치와 관련 된 키오스크 구성의 여러 측면에 대 한 정보를 제공 합니다. 다양 한 종류의 Windows 기반 키오스크 및 구성 방법에 대 한 일반적인 내용은 [windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성](https://docs.microsoft.com/windows/configuration/kiosk-methods)을 참조 하세요.  

> [!IMPORTANT]  
> 키오스크 모드는 사용자가 장치에 로그인 할 때 사용할 수 있는 앱을 결정 합니다. 그러나 키오스크 모드는 보안 방법이 아닙니다. 허용 되지 않는 다른 앱을 열 때 "허용 된" 앱을 중지 하지 않습니다. 앱 또는 프로세스를 열지 못하도록 차단 하려면 [Windows Defender 응용 프로그램 제어 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 를 사용 하 여 적절 한 정책을 만듭니다.
>
> 사용자에 게 HoloLens 2에서 사용 하는 고급 보안 수준을 제공 하는 Microsoft 서비스에 대 한 자세한 내용은 [상태 구분 및 격리-Defender 보호](security-state-separation-isolation.md#defender-protections)에 대해 자세히 알아보세요. 또는 Microsoft Intune를 사용 하 여 [HoloLens 2 장치에서 앱을 허용 하거나 차단 하는 데 WDAC 및 Windows PowerShell을 사용](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법을 알아봅니다.

단일 앱 또는 다중 앱 구성에서 키오스크 모드를 사용할 수 있으며, 세 가지 프로세스 중 하나를 사용 하 여 키오스크 구성을 설정 하 고 배포할 수 있습니다.

> [!IMPORTANT]  
> 다중 앱 구성을 삭제 하면 할당 된 액세스 기능이 만든 사용자 잠금 프로필이 제거 됩니다. 그러나 모든 정책 변경 내용은 되돌리지 않습니다. 이러한 정책을 되돌리려면 장치를 공장 설정으로 다시 설정 해야 합니다.

## <a name="plan-the-kiosk-deployment"></a>키오스크 배포 계획

키오스크를 계획할 때 다음 질문에 답할 수 있어야 합니다. 이 페이지를 읽는 동안 고려해 야 할 몇 가지 결정과 이러한 질문에 대 한 몇 가지 고려 사항은 다음과 같습니다.
1. **키오스크를 사용 하는 사용자와 사용 되는 [계정 유형](hololens-identity.md)** 이는 이미 작성 되어 키오스크를 위해 조정 되어서는 안 되는 결정 이며, 키오스크를 나중에 할당 하는 방법에 영향을 줍니다.
1. **사용자/그룹 마다 다른 키오스크를 사용 하거나 키오스크를 사용 하지 않도록 설정 해야 하나요?** 그렇다면 XML을 통해 키오스크를 만들려고 합니다. 
1. **키오스크에 얼마나 많은 앱이 있나요?** 앱이 2 개 이상 있는 경우 다중 앱 키오스크가 필요 합니다. 
1. **키오스크에는 어떤 앱이 있나요?** 아래 AUMIDs 목록을 사용 하 여 사용자 고유의 앱 외에도 In-Box 앱을 추가 하세요.
1. **키오스크를 어떻게 배포할 계획 입니까?** MDM에서 장치를 등록 하는 경우 MDM을 사용 하 여 키오스크를 배포 하는 것이 좋습니다. MDM을 사용 하지 않는 경우 프로 비전 패키지를 사용 하 여 배포할 수 있습니다.  

### <a name="kiosk-mode-requirements"></a>키오스크 모드 요구 사항

키오스크 모드를 사용 하도록 HoloLens 2 장치를 구성할 수 있습니다.

> [!IMPORTANT]
> 키오스크 모드는 장치에 비즈니스용 Windows Holographic 있는 경우에만 사용할 수 있습니다. 모든 HoloLens 2 장치는 비즈니스용 Windows Holographic 함께 제공 되며 다른 버전은 없습니다. 모든 HoloLens 2 장치는 즉시 키오스크 모드를 실행할 수 있습니다.
>
> HoloLens (첫 번째 gen) 장치는 OS 빌드 및 OS 버전 측면에서 모두 업그레이드 해야 합니다. HoloLens (첫 번째 gen)를 [Windows Holographic For Business](hololens1-upgrade-enterprise.md) 버전으로 업데이트 하는 방법에 대 한 자세한 내용은 다음과 같습니다. 키오스크 모드를 사용 하도록 HoloLens (첫 번째 gen) 장치를 업데이트 하려면 먼저 장치가 Windows 10, 버전 1803 이상 버전을 실행 하는지 확인 해야 합니다. Windows 장치 복구 도구를 사용 하 여 HoloLens (첫 번째 gen) 장치를 기본 빌드로 복구 하거나 최신 업데이트를 설치한 경우 장치를 구성할 준비가 된 것입니다.

> [!IMPORTANT]  
> 키오스크 모드에서 실행 되는 장치를 보호 하려면 USB 연결과 같은 기능을 해제 하는 장치 관리 정책을 추가 하는 것이 좋습니다. 또한 업데이트 링 설정을 확인 하 여 업무 시간 동안 자동 업데이트가 발생 하지 않는지 확인 합니다.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>단일 앱 키오스크 또는 다중 앱 키오스크를 결정 합니다.

단일 앱 키오스크는 사용자가 장치에 로그인 할 때 지정 된 앱을 시작 합니다. Cortana와 마찬가지로 시작 메뉴는 비활성화 되어 있습니다. HoloLens 2 장치는 [시작](hololens2-basic-usage.md#start-gesture) 제스처에 응답 하지 않습니다. HoloLens (첫 번째 gen) 장치가 [블 룸](hololens1-basic-usage.md) 제스처에 응답 하지 않습니다. 앱을 하나만 실행할 수 있으므로 사용자는 다른 앱을 추가할 수 없습니다.

다중 앱 키오스크는 사용자가 장치에 로그인 할 때 시작 메뉴를 표시 합니다. 키오스크 구성은 시작 메뉴에서 사용할 수 있는 앱을 결정 합니다. 다중 앱 키오스크를 사용 하 여 사용자가 사용 해야 하는 항목만 제시 하 고 사용할 필요가 없는 항목을 제거 하 여 사용자에 게 이해 하기 쉬운 환경을 제공할 수 있습니다.

다음 표에서는 다양 한 키오스크 모드의 기능 기능을 보여 줍니다.

| &nbsp; |시작 메뉴 |빠른 작업 메뉴 |카메라 및 비디오 |Miracast |Cortana |기본 제공 음성 명령 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|단일 앱 키오스크 |사용 안 함 |사용 안 함   |사용 안 함 |사용 안 함   |사용 안 함 |사용<sup>1</sup> |
|다중 앱 키오스크 |사용 |사용<sup>2</sup> |사용 가능<sup>2</sup> |사용 가능<sup>2</sup> |사용 가능한<sup>2, 3</sup>  |사용<sup>1</sup> |

> <sup>1</sup> 비활성화 된 기능과 관련 된 음성 명령은 작동 하지 않습니다.  
> <sup>2</sup> 이러한 기능을 구성 하는 방법에 대 한 자세한 내용은 [키오스크 앱 선택](#plan-kiosk-apps)을 참조 하세요.  
> <sup>3</sup> Cortana가 사용 하지 않도록 설정 된 경우에도 기본 제공 음성 명령이 사용 됩니다.

다음 표에서는 다양 한 키오스크 모드의 사용자 지원 기능을 보여 줍니다.

| &nbsp; |지원 되는 사용자 유형 | 자동 로그인 | 여러 액세스 수준 |
| --- | --- | --- | --- |
|단일 앱 키오스크 |Azure Active Directory (Azure AD) 또는 로컬 계정에서 MSA (관리 서비스 계정) |예 |예 |
|다중 앱 키오스크 |Azure AD 계정 |예 |예 |

이러한 기능을 사용 하는 방법에 대 한 예제는 다음 표를 참조 하세요.

|단일 앱 키오스크 사용: |다중 앱 키오스크 사용: |
| --- | --- |
|새 직원에 대해 Dynamics 365 가이드만 실행 하는 장치입니다. |여러 직원에 대해 가이드와 원격 지원을 모두 실행 하는 장치입니다. |
|사용자 지정 앱만 실행 하는 장치입니다. |사용자 지정 앱만 실행 하는 대부분의 사용자에 게 키오스크로 작동 하지만 특정 사용자 그룹의 표준 장치로 작동 하는 장치입니다. |

### <a name="plan-kiosk-apps"></a>키오스크 앱 계획

키오스크 앱을 선택 하는 방법에 대 한 일반 정보는 [할당 된 액세스를 위해 앱을 선택 하기 위한 지침 (키오스크 모드)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)을 참조 하세요.

Windows 장치 포털을 사용 하 여 단일 앱 키오스크를 구성 하는 경우 설치 과정에서 앱을 선택 합니다.  

MDM (모바일 장치 관리) 시스템 또는 프로 비전 패키지를 사용 하 여 키오스크 모드를 구성 하는 경우 [ASSIGNEDACCESS CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 를 사용 하 여 응용 프로그램을 지정 합니다. CSP는 [응용 프로그램 사용자 모델 id (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 를 사용 하 여 응용 프로그램을 식별 합니다. 다음 표에는 다중 앱 키오스크에서 사용할 수 있는 일부 기본 제공 응용 프로그램의 AUMIDs가 나와 있습니다.

> [!IMPORTANT]
> 키오스크 모드는 사용자가 장치에 로그인 할 때 사용할 수 있는 앱을 결정 합니다. 그러나 키오스크 모드는 보안 방법이 아닙니다. 허용 되지 않는 다른 앱을 열 때 "허용 된" 앱을 중지 하지 않습니다. 이 동작은 제한 하지 않으므로 Edge, 파일 탐색기 및 Microsoft Store apps에서 앱을 계속 실행할 수 있습니다. 키오스크에서 시작 하지 않으려는 특정 앱이 있는 경우 [Windows Defender 응용 프로그램 제어 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 를 사용 하 여 적절 한 정책을 만듭니다. 
> 
> 또한 혼합 현실 홈을 키오스크 앱으로 설정할 수 없습니다.

<a id="aumids"></a>

|앱 이름 |AUMID |
| --- | --- |
|3D 뷰어 |Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|일정 |windowscommunicationsapps \_ 8wekyb3d8bbwe \! live |
|카메라<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |549981C3F5F10 \_ 8wekyb3d8bbwe \! 앱 |
|HoloLens의 장치 선택 (첫 번째 gen) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2의 장치 선택 |DevicesFlowHost cw5n1h2txyewy (DevicesFlowHost) \_ \! |
|Dynamics 365 Guides |Dynamics365 \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. remoteassist |
|피드백 &nbsp; 허브 |WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 앱 |
|파일 탐색기 |c5e2524a-ea46-4f67-6a9465d9d515_cw5n1h2txyewy! 다운로드 |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! live |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! 다운로드 |
|Miracast<sup>4</sup> |&nbsp; |
|TV & 영상 |Microsoft 8wekyb3d8bbwe-zunevideo \_ \! |
|OneDrive |microsoftskydrive \_ 8wekyb3d8bbwe \! 앱 |
|사진 |\_8wekyb3d8bbwe \! 앱 |
|설정 |HolographicSystemSettings \_ cw5n1h2txyewy \! 앱 |
|팁 |HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 사진 또는 비디오 캡처를 사용 하도록 설정 하려면 카메라 앱을 키오스크 앱으로 사용 하도록 설정 해야 합니다.  
> <sup>2</sup> 카메라 앱을 사용 하도록 설정 하는 경우 다음 조건을 알고 있어야 합니다.
> - 빠른 작업 메뉴에는 사진 및 비디오 단추가 포함 됩니다.  
> - 또한 사진을 조작 하거나 검색할 수 있는 앱 (예: 사진, 메일 또는 OneDrive)을 사용 하도록 설정 해야 합니다.  
>  
> <sup>3</sup> Cortana를 키오스크 앱으로 사용 하도록 설정 하지 않은 경우에도 기본 제공 음성 명령이 사용 됩니다. 그러나 비활성화 된 기능과 관련 된 명령은 아무런 영향을 주지 않습니다.  
> <sup>4</sup> Miracast를 직접 사용 하도록 설정할 수 없습니다. Miracast를 키오스크 앱으로 사용 하도록 설정 하려면 카메라 앱 및 장치 선택 앱을 사용 하도록 설정 합니다.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>사용자 또는 그룹에 대 한 키오스크 프로필 계획

Xml 파일을 만들거나 Intune UI를 사용 하 여 키오스크를 설정 하는 경우 키오스크 사용자를 고려해 야 합니다. 키오스크 구성은 개별 계정 또는 Azure AD 그룹으로 제한 될 수 있습니다. 

일반적으로 키오스크는 사용자 또는 사용자 그룹에 대해 사용 하도록 설정 됩니다. 그러나 사용자 고유의 XML 키오스크를 작성할 계획인 경우 Id에 관계 없이 장치 수준에서 키오스크가 적용 되는 전역 할당 액세스를 고려할 수 있습니다. 이 끕니다에 [대 한 자세한 내용은 할당 된 글로벌 액세스 키오스크를 참조 하세요.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>XML 파일을 만드는 경우:
-   여러 키오스크 프로필을 만들고 각 사용자/그룹에 할당 합니다. 많은 앱을 포함 하는 Azure AD 그룹의 키오스크 및 단일 앱이 있는 여러 앱 키오스크를 포함 하는 방문자 등
-   키오스크 구성은 **프로필 Id** 라고 하며 GUID가 포함 됩니다.
-   사용자 유형을 지정 하 고 **Defaultprofile Id** 에 동일한 GUID를 사용 하 여 configs 섹션에서 해당 프로필을 할당 합니다.
- 사용자 지정 OMA URI 장치 구성 프로필을 만들고 URI 값../Device/Vendor/MSFT/AssignedAccess/Configuration을 사용 하 여 HoloLens 장치 그룹에 적용 하 여 XML 파일을 만들 수 있지만 MDM을 통해 장치에 적용할 수 있습니다.

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune에서 키오스크를 만드는 경우
-   각 장치는 단일 키오스크 프로필을 받을 수 있습니다. 그렇지 않으면 충돌을 만들고 키오스크 구성을 받지 않습니다. 
    -   키오스크 구성 프로필과 관련이 없는 장치 제한과 같은 다른 종류의 프로필 및 정책은 키오스크 구성 프로필과 충돌 하지 않습니다.
-   키오스크는 사용자 로그온 유형에 속하는 모든 사용자에 대해 사용 하도록 설정 되며, 사용자 또는 Azure AD 그룹을 사용 하 여 설정 됩니다. 
-   키오스크 구성이 설정 되 고 **사용자 로그온 유형** (키오스크에 로그인 할 수 있는 사용자) 및 앱이 선택 된 후에는 장치 구성을 그룹에 계속 할당 해야 합니다. 할당 된 그룹에 따라 키오스크 장치 구성을 수신 하는 장치가 결정 됩니다. 그러나 키오스크를 사용 하는 경우에는 상호 작용 하지 않습니다. 
    - Intune에서 구성 프로필을 할당 하는 효과에 대 한 자세한 내용은 [Microsoft Intune에서 사용자 및 장치 프로필 할당](https://docs.microsoft.com/intune/configuration/device-profile-assign)을 참조 하세요.

### <a name="select-a-deployment-method"></a>배포 방법 선택

다음 방법 중 하나를 선택 하 여 키오스크 구성을 배포할 수 있습니다.

- [Microsoft Intune 또는 기타 MDM (모바일 장치 관리) 서비스](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [프로 비전 패키지](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 이 방법을 사용 하려면 장치에서 개발자 모드를 사용 하도록 설정 해야 하므로 데모에만 사용 하는 것이 좋습니다.

다음 표에는 각 배포 방법의 기능 및 이점이 정리 되어 있습니다.

| &nbsp; |Windows 장치 포털을 사용 하 여 배포 |프로 비전 패키지를 사용 하 여 배포 |MDM을 사용 하 여 배포 |
| --------------------------- | ------------- | -------------------- | ---- |
|단일 앱 키오스크 배포   | 예           | 예                  | 예  |
|다중 앱 키오스크 배포    | 예            | 예                  | 예  |
|로컬 장치에만 배포 | 예           | 예                  | 예   |
|개발자 모드를 사용 하 여 배포 |필수       | 필요 없음            | 필요 없음   |
|Azure Active Directory (Azure AD)를 사용 하 여 배포  | 필요 없음            | 필요 없음                   | 필수  |
|자동으로 배포      | 예            | 예                   | 예  |
|배포 속도            | 빠름       | 빠름                 | 느림 |
|대규모 배포 | 권장하지 않음    | 권장        | 권장 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Microsoft Intune 또는 다른 MDM을 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정

Microsoft Intune 또는 다른 MDM 시스템을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 수행 합니다.

1. [장치 등록을 준비](#mdmenroll)합니다.
1. [키오스크 구성 프로필을 만듭니다](#mdmprofile).
1. 키오스크를 구성 합니다.
   - [단일 앱 키오스크에 대 한 설정을 구성](#mdmconfigsingle)합니다.
   - [다중 앱 키오스크에 대 한 설정을 구성](#mdmconfigmulti)합니다.
1. [키오스크 구성 프로필을 그룹에 할당](#mdmassign)합니다.
1. 장치를 배포 합니다.
   - [단일 앱 키오스크를 배포](#mdmsingledeploy)합니다.
   - [다중 앱 키오스크를 배포](#mdmmultideploy)합니다.

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, 1 단계 &ndash; 장치 등록 준비

사용자가 처음으로 로그인 하거나 사용자가 장치를 수동으로 등록할 때 장치를 자동으로 등록 하도록 MDM 시스템을 구성할 수 있습니다. 또한 장치는 Azure AD 도메인에 가입 되 고 적절 한 그룹에 할당 되어야 합니다.

장치를 등록 하는 방법에 대 한 자세한 내용은 [Windows 장치에 대 한 MDM 및 Intune 등록 방법](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods) [에서 HoloLens 등록](hololens-enroll-mdm.md) 을 참조 하세요.

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, 2 단계 &ndash; 키오스크 구성 프로필 만들기

1. [Azure](https://portal.azure.com/) portal을 열고 Intune 관리자 계정에 로그인 합니다.
1. **Microsoft Intune**  >  **장치 구성-** 프로필  >  **프로필 만들기** 를 선택 합니다.
1. 프로필 이름을 입력 합니다.
1. **플랫폼**  >  **Windows 10 이상** 을 선택 하 고 **프로필 유형**  > **장치 제한** 을 선택 합니다.
1. 키오스크 **구성**  >  을 선택 하 고 다음 중 하나를 선택 합니다.
   - 단일 앱 키오스크를 만들려면 **키오스크 모드**  >  **단일 앱 키오스크** 를 선택 합니다.
   - 다중 앱 키오스크를 만들려면 **키오스크 모드**  >  **다중 앱 키오스크** 를 선택 합니다.
1. 키오스크 구성을 시작 하려면 **추가** 를 선택 합니다.

다음 단계는 원하는 키오스크 유형에 따라 달라 집니다. 자세한 내용을 보려면 다음 옵션 중 하나를 선택 하십시오.  

- [단일 앱 키오스크](#mdmconfigsingle)
- [다중 앱 키오스크](#mdmconfigmulti)

키오스크 구성 프로필을 만드는 방법에 대 한 자세한 내용은 Intune을 [사용 하 여 전용 키오스크로 실행 하기 위한 windows 10 및 Windows Holographic For Business 장치 설정](https://docs.microsoft.com/intune/configuration/kiosk-settings)을 참조 하세요.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, 3 단계 (단일 앱) &ndash;  단일 앱 키오스크에 대 한 설정 구성

이 섹션에서는 단일 앱 키오스크에 필요한 설정을 요약 합니다. 자세한 내용은 다음 문서를 참조 하세요.

- Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune를 사용 하 여 키오스크 모드를 구성 하는 방법](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)을 참조 하세요.
- Intune의 단일 앱 키오스크에 대해 사용 가능한 설정에 대 한 자세한 내용은 [단일 전체 화면 앱 키오스크](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) 를 참조 하세요.
- 다른 MDM 서비스의 경우 공급자 설명서에서 지침을 확인 하세요. MDM 서비스에서 키오스크를 설정 하기 위해 사용자 지정 XML 구성을 사용 해야 하는 경우 [키오스크 구성을 정의 하는 xml 파일을 만듭니다](#ppkioskconfig).

1. **사용자 로그온 유형**  >  **로컬 사용자 계정** 을 선택한 다음 키오스크에 로그인 할 수 있는 로컬 (장치) 계정 또는 Microsoft 계정 (MSA)의 사용자 이름을 입력 합니다.
   > [!NOTE]  
   > **자동 로그온** 사용자 계정 유형은 Windows Holographic for Business에서 지원되지 않습니다.
1. **응용 프로그램 종류**  >  **저장소 앱** 을 선택 하 고 목록에서 앱을 선택 합니다.

다음 단계는 그룹에 프로필을 [할당](#mdmassign) 하는 것입니다.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, 3 단계 (다중 앱) &ndash; 다중 앱 키오스크에 대 한 설정 구성

이 섹션에서는 다중 앱 키오스크에 필요한 설정을 요약 합니다. 자세한 내용은 다음 문서를 참조하세요.

- Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune를 사용 하 여 키오스크 모드를 구성 하는 방법](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)을 참조 하세요.
- Intune의 다중 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [다중 앱 키오스크](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) 를 참조 하세요.
- 다른 MDM 서비스의 경우 공급자 설명서에서 지침을 확인 하세요. 사용자 지정 XML 구성을 사용 하 여 MDM 서비스에서 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 xml 파일을 만듭니다](#ppkioskconfig). XML 파일을 사용 하는 경우 [시작 레이아웃](#start-layout-for-hololens)을 포함 해야 합니다.  
- 필요에 따라 Intune 또는 기타 MDM 서비스에서 사용자 지정 시작 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM의 시작 레이아웃 파일 (Intune 및 기타)](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.

1. **S 모드 장치 아니요에서 대상 Windows 10을** 선택  >  합니다.  
   >[!NOTE]  
   > Windows Holographic for Business에서는 S 모드가 지원되지 않습니다.
1. **사용자 로그온 유형**  >  **Azure AD 사용자 또는 그룹** 또는 **사용자 로그온 유형**  >  **HoloLens 방문자** 를 선택 하 고 하나 이상의 사용자 그룹 또는 계정을 추가 합니다.  

   **사용자 로그온 유형에** 지정한 그룹 또는 계정에 속한 사용자만 키오스크 환경을 사용할 수 있습니다.

1. 다음 옵션을 사용 하 여 앱을 하나 이상 선택 합니다.
   - 업로드 된 lob (기간 업무) 앱을 추가 하려면 **스토어 앱 추가** 를 선택한 다음 원하는 앱을 선택 합니다.
   - AUMID를 지정 하 여 앱을 추가 하려면 **AUMID** 를 선택 하 고 앱의 AUMID를 입력 합니다. [사용 가능한 AUMIDs 목록 참조](#aumids)

다음 단계는 그룹에 프로필을 [할당](#mdmassign) 하는 것입니다.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, 4 단계 &ndash; 키오스크 구성 프로필을 그룹에 할당

키오스크 구성 프로필의 **할당** 페이지를 사용 하 여 키오스크 구성을 배포할 위치를 설정할 수 있습니다. 가장 간단한 경우 장치가 MDM에 등록 될 때 HoloLens 장치를 포함 하는 그룹에 키오스크 구성 프로필을 할당 합니다.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5 단계 (단일 앱) &ndash; 단일 앱 키오스크 배포

MDM 시스템을 사용 하는 경우 OOBE를 실행 하는 동안 MDM에서 장치를 등록할 수 있습니다. OOBE가 완료 된 후에는 장치에 쉽게 로그인 할 수 있습니다.

OOBE 중에 다음 단계를 수행 합니다.

1. 키오스크 구성 프로필에서 지정한 계정을 사용 하 여 로그인 합니다.
1. 디바이스를 등록합니다. 키오스크 구성 프로필이 할당 된 그룹에 장치가 추가 되었는지 확인 합니다.
1. 저장소 앱을 다운로드 하 여 설치 하 고 정책을 적용할 수 있도록 OOBE가 완료 될 때까지 기다립니다. 그런 다음 장치를 다시 시작 합니다.

다음에 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.

이 시점에서 키오스크 구성이 표시 되지 않으면 [할당 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5 단계 (다중 앱) &ndash; 다중 앱 키오스크 배포

MDM 시스템을 사용 하는 경우 Azure AD 테 넌 트에 장치를 연결 하 고 OOBE 중 MDM에서 장치를 등록할 수 있습니다. 해당 하는 경우 OOBE 프로세스 중에 사용할 수 있도록 사용자에 게 등록 정보를 제공 합니다.

> [!NOTE]  
> 사용자가 포함 된 그룹에 키오스크 구성 프로필을 할당 한 경우 해당 사용자 계정 중 하나가 장치에 로그인 하는 첫 번째 계정 인지 확인 합니다.

OOBE 중에 다음 단계를 수행 합니다.

1. **사용자 로그온 유형** 그룹에 속한 계정을 사용 하 여 로그인 합니다.
1. 디바이스를 등록합니다.
1. 키오스크 구성 프로필의 일부인 앱이 다운로드 및 설치 될 때까지 기다립니다. 또한 정책이 적용 될 때까지 기다립니다.  
1. OOBE가 완료 되 면 Microsoft 스토어 또는 테스트용 로드에서 추가 앱을 설치할 수 있습니다. 자동으로 설치 하기 위해 장치가 속한 그룹에 대 한 [필수 앱](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 입니다.
1. 설치가 완료 되 면 장치를 다시 시작 합니다.

다음에 **사용자 로그온 유형에** 속한 계정을 사용 하 여 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.

이 시점에서 키오스크 구성이 표시 되지 않으면 [할당 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>프로 비전 패키지를 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정

프로 비전 패키지를 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 수행 합니다.

1. [시작 레이아웃](#start-layout-for-hololens)을 포함 하 여 [키오스크 구성을 정의 하는 XML 파일을 만듭니다.](#ppkioskconfig)
2. [프로 비전 패키지에 XML 파일을 추가 합니다.](#ppconfigadd)
3. [HoloLens에 프로 비전 패키지를 적용 합니다.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>프로 비전 패키지, 1 단계 &ndash; 키오스크 구성 XML 파일 만들기

일반 지침에 따라 다음을 제외 하 고 [Windows 데스크톱용 키오스크 구성 XML 파일을 만듭니다](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).

- 클래식 Windows 응용 프로그램 (Win32)을 포함 하지 않습니다. HoloLens는 이러한 응용 프로그램을 지원 하지 않습니다.
- HoloLens에 대 한 [자리 표시자 시작 레이아웃 XML](#start-layout-for-hololens) 을 사용 합니다.
- 선택 사항: 키오스크 구성에 게스트 액세스 추가

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>선택 사항: 키오스크 구성에 게스트 액세스 추가

[XML 파일의 **Configs** 섹션](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)에서 방문자가 키오스크를 사용할 수 있도록 **방문자** 라는 특수 그룹을 구성할 수 있습니다. 키오스크가 **방문자** 특별 그룹을 지원 하도록 구성 된 경우 "**게스트**" 옵션이 로그인 페이지에 추가 됩니다. **Guest** 계정에는 암호가 필요 하지 않으며 계정에 연결 된 모든 데이터는 계정이 로그 아웃 될 때 삭제 됩니다.

**게스트** 계정을 사용 하도록 설정 하려면 다음 코드 조각을 키오스크 구성 XML에 추가 합니다.

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens의 자리 표시자 시작 레이아웃

[프로 비전 패키지](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 를 사용 하 여 다중 앱 키오스크를 구성 하는 경우이 절차에는 시작 레이아웃이 필요 합니다. 시작 레이아웃 사용자 지정은 비즈니스용 Windows Holographic에서 지원 되지 않습니다. 따라서 자리 표시자 시작 레이아웃을 사용 해야 합니다.

> [!NOTE]  
> 단일 앱 키오스크는 사용자가 로그인 할 때 키오스크 앱을 시작 하므로 시작 메뉴를 사용 하지 않고 시작 레이아웃을 가질 필요가 없습니다.

> [!NOTE]  
> [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 을 사용 하 여 다중 앱 키오스크를 설정 하는 경우 필요에 따라 시작 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM의 자리 표시자 시작 레이아웃 파일 (Intune 및 기타)](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.

시작 레이아웃에 대해 키오스크 프로 비전 XML 파일에 다음 **startlayout** 섹션을 추가 합니다.

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM에 대 한 자리 표시자 시작 레이아웃 파일 (Intune 및 기타)

다음 샘플을 XML 파일로 저장 합니다. Microsoft Intune (또는 키오스크 프로필을 제공 하는 다른 MDM 서비스)에서 다중 앱 키오스크를 구성할 때이 파일을 사용할 수 있습니다.

> [!NOTE]
> MDM 서비스에서 키오스크를 설정 하기 위해 사용자 지정 설정과 전체 XML 구성을 사용 해야 하는 경우 [프로 비전 패키지의 시작 레이아웃 지침](#start-layout-for-hololens)을 사용 합니다.

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. 패키지, 2 단계 &ndash; 프로 비전 패키지에 키오스크 구성 XML 파일 추가

1. [Windows 구성 디자이너](https://www.microsoft.com/store/apps/9nblggh4tx22)를 엽니다.
1. **고급 프로 비전** 을 선택 하 고 프로젝트의 이름을 입력 한 후 **다음** 을 선택 합니다.
1. **Windows 10 Holographic** 을 선택 하 고 **다음** 을 선택 합니다.
1. **완료** 를 선택합니다. 패키지에 대 한 작업 영역이 열립니다.
1. **런타임 설정**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings** 을 선택 합니다.
1. 가운데 창에서 **찾아보기** 를 선택 하 여 만든 키오스크 구성 XML 파일을 찾아 선택 합니다.

   ![Windows 구성 디자이너의 MultiAppAssignedAccessSettings 필드 스크린샷](./images/multiappassignedaccesssettings.png)

1. **선택 사항입니다**. (장치 초기 설치 후 프로 비전 패키지를 적용 하려는 경우 키오스크 장치에서 이미 관리 사용자를 사용할 수 있는 경우이 단계를 건너뜁니다.) **런타임 설정** &gt; **계정** &gt; **사용자** 를 선택 하 고 사용자 계정을 만듭니다. 사용자 이름 및 암호를 입력 한 다음 **UserGroup**  >  **Administrators** 를 선택 합니다.  
  
     이 계정을 사용 하 여 프로 비전 상태 및 로그를 볼 수 있습니다.  
1. **선택 사항입니다**. 키오스크 장치에 관리자가 아닌 계정이 이미 있는 경우이 단계를 건너뜁니다. **런타임 설정** &gt; **계정** &gt; **사용자** 를 선택 하 고 로컬 사용자 계정을 만듭니다. 사용자 이름이 구성 XML에서 지정한 계정과 동일한 지 확인 합니다. **UserGroup**  >  **Standard Users** 를 선택 합니다.
1. **파일** > **저장** 을 선택합니다.
1.   >  **프로 비전 패키지** 내보내기를 선택한 다음 **소유자**  >  **IT 관리자** 를 선택 합니다. 이는 다른 원본에서이 장치에 적용 되는 패키지를 프로 비전 하는 것 보다 더 높은이 프로 비전 패키지의 우선 순위를 설정 합니다.
1. **다음** 을 선택합니다.
1. **프로 비전 패키지 보안** 페이지에서 보안 옵션을 선택 합니다.
   > [!IMPORTANT]  
   > **패키지 서명 사용** 을 선택 하는 경우 패키지 서명에 사용할 올바른 인증서도 선택 해야 합니다. 이렇게 하려면 **찾아보기** 를 선택 하 고 패키지에 서명 하는 데 사용할 인증서를 선택 합니다.
   
   > [!CAUTION]  
   > **패키지 암호화 사용** 을 선택 하지 않습니다. HoloLens 장치에서이 설정으로 인해 프로 비전이 실패 합니다.
1. **다음** 을 선택합니다.
1. 프로 비전 패키지를 빌드할 때 사용할 출력 위치를 지정 합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용 합니다. 출력 위치를 변경 하려면 **찾아보기** 를 선택 합니다. 작업을 마쳤으면 **다음** 을 선택합니다.
1. **빌드** 를 선택 하 여 패키지 빌드를 시작 합니다. 프로 비전 패키지를 빌드하는 데 시간이 오래 걸리지 않습니다. 빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>프로 비전 패키지, 3 단계 &ndash; HoloLens에 프로 비전 패키지 적용

"프로 비전 패키지를 사용 하 여 HoloLens 구성" 문서에서는 다음과 같은 경우에 프로 비전 패키지를 적용 하기 위한 자세한 지침을 제공 합니다.

- 처음에는 [설치 중 HoloLens에 프로 비전 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)수 있습니다.

- [설치 후 HoloLens에 프로 비전 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)수도 있습니다.

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Windows 장치 포털을 사용 하 여 단일 앱 키오스크 설정

Windows 장치 포털을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 수행 합니다.

1. [Windows 장치 포털을 사용 하도록 HoloLens 장치를 설정](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)합니다. Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.

    > [!CAUTION]
    > 장치 포털을 사용 하도록 HoloLens를 설정 하는 경우 장치에서 개발자 모드를 사용 하도록 설정 해야 합니다. Windows Holographic for Business를 사용 하는 장치에서 개발자 모드를 사용 하면 앱을 테스트용으로 로드할 수 있습니다. 그러나이 설정은 사용자가 Microsoft Store에 의해 인증 되지 않은 앱을 설치할 수 있는 위험을 만듭니다. 관리자는 [정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)의 **Applicationmanagement/Allowdeveloper 잠금 해제** 설정을 사용 하 여 개발자 모드를 사용 하도록 설정 하는 기능을 차단할 수 있습니다. [개발자 모드에 대해 자세히 알아보세요.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
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

이 새로운 기능을 통해 IT 관리자는 시스템 수준에서 적용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성할 수 있으며, 시스템의 id를 사용 하는 선호도는 없으며 장치에 로그인 하는 모든 사용자에 게 적용 됩니다. 이 새로운 기능에 대 한 자세한 내용은 [HoloLens global 할당 된 액세스 키오스크](hololens-global-assigned-access-kiosk.md) 설명서를 참조 하세요.

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
- 키오스크 모드 오류 시 사용 가능한 앱을 제거 하 여 더 안전한 키오스크 모드. 

이전에는 키오스크 모드 적용에 오류가 발생 하 여 시작 메뉴에 모든 응용 프로그램을 표시 하는 데 사용 되는 HoloLens가 있습니다. 이제 Windows Holographic 버전 20H2에서 오류가 발생 하는 경우 아래와 같이 시작 메뉴에 앱이 표시 되지 않습니다. 

![이제 실패할 때 표시 되는 키오스크 모드 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>오프 라인 키오스크를 위한 Azure AD 그룹 멤버 자격 캐시
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
1. 이제 Azure AD 사용자 1은 HoloLens 오프 라인으로 전환 하 고, 정책 값이 X 일 수를 허용 하는 경우 키오스크 모드에 사용할 수 있습니다. 
1. 다른 모든 Azure AD 사용자에 대해 4 단계와 5 단계를 반복할 수 있습니다. 중요 한 점은 Azure AD 사용자가 인터넷을 사용 하 여 장치에 로그인 해야 하는 것입니다 .이는 적어도 한 번은 키오스크 구성이 대상으로 하는 Azure AD 그룹의 구성원 인지 확인할 수 있습니다. 
 
> [!NOTE]
> Azure AD 사용자에 대해 4 단계를 수행 하기 전에는 "연결이 끊어진" 환경에서 언급 한 오류 동작이 발생 합니다. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens 용 XML 키오스크 코드 샘플

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure AD 그룹을 대상으로 하는 여러 앱 키오스크 모드입니다. 
이 키오스크는 Azure AD 그룹의 사용자를 위해 키오스크를 사용 하도록 설정 하 고 3 개 앱 (설정, 원격 지원 및 피드백 허브)을 포함 하는 키오스크를 배포 합니다. 이 샘플을 즉시 사용할 수 있도록 수정 하려면 아래에 강조 표시 된 GUID를 자신의 Azure AD 그룹에 맞게 변경 해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD 계정을 대상으로 하는 여러 앱 키오스크 모드입니다.
이 키오스크는 단일 사용자를 위해 키오스크를 배포 하 고 3 개의 앱 인 설정, 원격 지원 및 피드백 허브를 포함 하는 키오스크를 사용 하도록 설정 합니다. 이 샘플을 즉시 사용할 수 있도록 수정 하려면 아래에 강조 표시 된 계정을 자신의 Azure AD 계정과 일치 하도록 변경 해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

