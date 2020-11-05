---
title: HoloLens를 키오스크로 설정
description: 키오스크 구성을 사용 하 여 HoloLens에서 앱을 잠급니다.
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
ms.openlocfilehash: c4c4b533538ab7998f8438d7cc0c2f3d88143ec6
ms.sourcegitcommit: 4e168380c23e8463438aa8a1388baf8d5ac1a1ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154191"
---
# HoloLens를 키오스크로 설정

장치를 키오스크 모드로 실행 하도록 구성 하 여 HoloLens 장치가 고정 용도의 디바이스 ( *키오스크*이 라고도 함)로 작동 하도록 구성할 수 있습니다. 키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램 (또는 사용자)을 제한 합니다. 키오스크 모드는 HoloLens 장치를 비즈니스 앱으로 전용 또는 앱 데모에서 HoloLens 장치를 사용 하는 데 사용할 수 있는 편리한 기능입니다.

이 문서에서는 HoloLens 디바이스와 관련 된 키오스크 구성의 측면에 대 한 정보를 제공 합니다. 다양 한 유형의 Windows 기반 키오스크 및이를 구성 하는 방법에 대 한 일반적인 내용은 [windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성을](https://docs.microsoft.com/windows/configuration/kiosk-methods)참조 하세요.  

> [!IMPORTANT]  
> 키오스크 모드는 사용자가 장치에 로그인 할 때 사용할 수 있는 앱을 결정 합니다. 그러나 키오스크 모드는 보안 방법이 아닙니다. "허용" 된 앱이 허용 되지 않는 다른 앱을 여는 것은 중지 되지 않습니다. 앱 또는 프로세스를 열지 못하도록 차단 하려면 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 를 사용 하 여 적절 한 정책을 만듭니다.
>
> Microsoft 서비스에 대 한 자세한 내용은 HoloLens 2 사용에 대 한 고급 보안 수준을 사용자에 게 제공 하 고 [상태 분리 및 격리-Defender 보호](security-state-separation-isolation.md#defender-protections)에 대해 자세히 알아보세요. 또는 [Windows PowerShell을 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법에 대해 알아봅니다.

단일 앱 또는 다중 앱 구성에서 키오스크 모드를 사용할 수 있으며, 세 가지 프로세스 중 하나를 사용 하 여 키오스크 구성을 설정 하 고 배포할 수 있습니다.

> [!IMPORTANT]  
> 다중 앱 구성을 삭제 하면 할당 된 액세스 기능에서 만든 사용자 잠금 프로필이 제거 됩니다. 그러나 모든 정책 변경 사항은 되돌리지 않습니다. 이러한 정책을 되돌리려면 디바이스를 공장 설정으로 다시 설정 해야 합니다.

## 키오스크 배포 계획

키오스크 계획을 수립할 때에는 다음 질문에 대답할 수 있어야 합니다. 이 페이지를 읽는 동안 고려해 야 할 사항과 이러한 질문에 대 한 몇 가지 고려 사항입니다.
1. **키오스크를 사용 하는 사용자 및 사용할 [계정 종류](hololens-identity.md) 를 선택 합니다.** 이는 이미 작성 했 고, 키오스크의 편의를 위해 조정할 수 없는 것이 고, 나중에 키오스크에 할당 되는 방법에 영향을 주는 결정입니다.
1. **사용자/그룹 당 다른 키오스크 또는 일부 키오스크 기능을 사용할 수 없도록 설정 해야 하나요?** 그렇다면 XML을 통해 키오스크를 만들어야 합니다. 
1. **Kiosk에는 몇 개의 앱이 있나요?** 1 개 이상의 앱을 사용 하는 경우 다중 앱 키오스크이 필요 합니다. 
1. **Kiosk에는 어떤 앱이 있나요?** 아래에 나와 있는 내 Umid 목록을 사용 하 여 자신의 In-Box 앱 외에도 추가 하세요.
1. **키오스크 배포를 계획 하는 방법은 무엇 인가요?** MDM에서 디바이스를 등록 하는 경우 MDM을 사용 하 여 키오스크를 배포 하는 것이 좋습니다. MDM을 사용 하지 않는 경우에는 배포 패키지를 사용 하는 배포가 제공 됩니다.  

### 키오스크 모드 요구 사항

키오스크 모드를 사용 하도록 HoloLens 2 장치를 구성할 수 있습니다.

키오스크 모드를 사용 하도록 HoloLens (첫번째 gen) 장치를 구성 하려면 먼저 장치가 Windows 10, 버전 1803 또는 이후 버전을 실행 하는지 확인 해야 합니다. Windows 장치 복구 도구를 사용 하 여 HoloLens (첫번째 gen) 장치를 기본 빌드로 복구 하거나 최신 업데이트를 설치한 경우 장치를 구성할 준비가 된 것입니다.

> [!IMPORTANT]  
> 키오스크 모드에서 실행 되는 장치를 보호 하기 위해 USB 연결과 같은 기능을 해제 하는 장치 관리 정책을 추가 하는 것이 좋습니다. 또한 업데이트 링 설정을 확인 하 여 업무 시간 동안 자동 업데이트가 발생 하지 않는지 확인 합니다.

### 단일 앱 키오스크 또는 다중 앱 키오스크 중에서 결정

단일 앱 키오스크는 사용자가 장치에 로그인 할 때 지정 된 앱을 시작 합니다. Cortana 인 시작 메뉴를 사용할 수 없습니다. HoloLens 2 장치가 [시작](hololens2-basic-usage.md#start-gesture) 제스처에 응답 하지 않습니다. HoloLens (1 gen) 장치가 [블 룸](hololens1-basic-usage.md) 제스처에 응답 하지 않습니다. 앱을 하나만 실행할 수 있으므로 사용자는 다른 앱을 배치할 수 없습니다.

다중 앱 키오스크는 사용자가 장치에 로그인 할 때 시작 메뉴를 표시 합니다. 키오스크 구성은 시작 메뉴에서 사용할 수 있는 앱을 결정 합니다. 다중 앱 키오스크를 사용 하 여 사용자에 게 쉽게 이해할 수 있는 환경을 제공 하 고,이를 사용 하는 데 필요한 작업만 표시 하 고, 사용 하지 않아도 되는 항목을 제거 합니다.

다음 표에는 여러 키오스크 모드의 기능 기능이 나와 있습니다.

| &nbsp; |시작 메뉴 |빠른 작업 메뉴 |카메라 및 비디오 |Miracast |Cortana |기본 제공 음성 명령 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|단일 앱 키오스크 |사용 안 함 |사용 안 함   |사용 안 함 |사용 안 함   |사용 안 함 |사용 <sup> 1</sup> |
|복수 앱 키오스크 |설정됨 |사용 <sup> 2</sup> |사용 가능 <sup> 2</sup> |사용 가능 <sup> 2</sup> |사용 가능한 <sup> 2, 3</sup>  |사용 <sup> 1</sup> |

> <sup></sup>사용 안 함 기능과 관련 된 1 개의 음성 명령이 작동 하지 않습니다.  
> <sup>2 </sup> 이러한 기능을 구성 하는 방법에 대 한 자세한 내용은 [키오스크 앱 선택을](#plan-kiosk-apps)참조 하세요.  
> <sup>3 </sup> Cortana를 사용할 수 없는 경우에도 기본 제공 음성 명령을 사용할 수 있습니다.

다음 표에는 여러 키오스크 모드의 사용자 지원 기능이 나와 있습니다.

| &nbsp; |지원 되는 사용자 유형 | 자동 로그인 | 여러 액세스 수준 |
| --- | --- | --- | --- |
|단일 앱 키오스크 |AAD (Azure Active Directory) 또는 로컬 계정의 MSA (관리 서비스 계정) |예 |아니오 |
|복수 앱 키오스크 |AAD 계정 |아니오 |예 |

이러한 기능을 사용 하는 방법에 대 한 예제는 다음 표를 참조 하세요.

|다음에 단일 앱 키오스크 사용: |다음에 대해 다중 앱 키오스크 사용: |
| --- | --- |
|새 직원에 대 한 Dynamics 365 가이드만 실행 하는 장치입니다. |직원 범위에 대해 가이드 및 원격 지원을 둘 다 실행 하는 장치입니다. |
|사용자 지정 앱만 실행 하는 장치입니다. |사용자 지정 앱만 실행 하 여 대부분의 사용자에 게 키오스크 역할을 하는 장치로, 특정 사용자 그룹에 대 한 표준 장치 역할을 합니다. |

### 키오스크 앱 계획

키오스크 앱을 선택 하는 방법에 대 한 일반적인 정보는 [할당 된 액세스에 대 한 앱 선택 (키오스크 모드)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)에 대 한 지침을 참조 하세요.

Windows Device Portal을 사용 하 여 단일 앱 키오스크를 구성 하는 경우 설정 프로세스 중에 앱을 선택 합니다.  

MDM (모바일 디바이스 관리) 시스템 또는 배포 패키지를 사용 하 여 키오스크 모드를 구성 하는 경우 [ASSIGNEDACCESS CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 를 사용 하 여 응용 프로그램을 지정 합니다. CSP는 [응용 프로그램 사용자 모델 id (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 를 사용 하 여 응용 프로그램을 식별 합니다. 다음 표에는 다중 앱 키오스크에서 사용할 수 있는 일부 응용 프로그램의 AUMIDs가 나열 되어 있습니다.

> [!IMPORTANT]
> 키오스크 모드는 사용자가 장치에 로그인 할 때 사용할 수 있는 앱을 결정 합니다. 그러나 키오스크 모드는 보안 방법이 아닙니다. "허용" 된 앱이 허용 되지 않는 다른 앱을 여는 것은 중지 되지 않습니다. 이 동작을 제한 하지 않기 때문에 Edge, 파일 탐색기 및 Microsoft 스토어 앱에서 앱을 시작할 수 있습니다. 키오스크에서 시작 하지 않으려는 특정 앱이 있는 경우 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 를 사용 하 여 적절 한 정책을 만듭니다. 
> 
> 또한 혼합 현실 홈은 키오스크 앱으로 설정할 수 없습니다.

<a id="aumids"></a>

|앱 이름 |AUMID |
| --- | --- |
|3D 뷰어 |Microsoft Microsoft3DViewer _8wekyb3d8bbwe \! Microsoft Microsoft3DViewer |
|Calendar |windowscommunicationsapps \ _8wekyb3d8bbwe \! windowslive. 일정 |
|카메라 <sup> 1, 2</sup> |HoloCamera _cw5n1h2txyewy \! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft 549981C3F5F10 _8wekyb3d8bbwe \! 내 |
|HoloLens의 장치 선택기 (첫번째 gen) |HoloDevicesFlow _cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2의 장치 선택기 |DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 _8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft MicrosoftRemoteAssist _8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|피드백 &nbsp; 허브 |Microsoft WindowsFeedbackHub _8wekyb3d8bbwe \! 내 |
|파일 탐색기 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! windowslive |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|영화 및 TV |Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |microsoft microsoftskydrive _8wekyb3d8bbwe \! 내 |
|사진 |Microsoft. 사진 \ _8wekyb3d8bbwe \! 내 |
|설정 |HolographicSystemSettings _cw5n1h2txyewy \! 내 |
|팁 |Microsoft HoloLensTips _8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 </sup> 사진 또는 비디오 캡처를 사용 하도록 설정 하려면 카메라 앱을 키오스크 앱으로 설정 해야 합니다.  
> <sup>2 </sup> 카메라 앱을 사용 하도록 설정 하는 경우 다음 조건에 유의 해야 합니다.
> - 빠른 동작 메뉴에는 사진 및 비디오 단추가 포함 되어 있습니다.  
> - 또한 그림을 조작 하거나 검색할 수 있는 앱 (예: 사진, 메일 또는 OneDrive)을 사용 하도록 설정 해야 합니다.  
>  
> <sup>3 </sup> Cortana를 키오스크 앱으로 사용 하지 않는 경우에도 기본 제공 음성 명령을 사용할 수 있습니다. 그러나 비활성 기능과 관련 된 명령은 아무런 효과가 없습니다.  
> <sup>4 </sup> Miracast를 직접 사용할 수 없습니다. Miracast를 키오스크 앱으로 사용 하도록 설정 하려면 카메라 앱 및 장치 선택기 앱을 사용 하도록 설정 합니다.

### 사용자 또는 그룹에 대 한 키오스크 프로필 계획

Xml 파일을 만들거나 Intune UI를 사용 하 여 키오스크를 설정 하는 경우에는 사용자에 게 키오스크를 지정할 사람을 고려해 야 합니다. 키오스크 구성은 개인 계정이 나 Azure AD 그룹으로 제한할 수 있습니다. 

일반적으로 사용자 또는 사용자 그룹에 게 키오스크 기능을 사용할 수 있습니다. 그러나 고유한 XML 키오스크 작성을 계획 하는 경우 Id에 관계 없이 디바이스 수준에서 키오스크가 적용 되는 전역 할당 된 액세스를 고려해 볼 수 있습니다. 이 천체 [전역 할당 된 액세스 키오스크에 대해 자세히 읽어 보세요.](hololens-global-assigned-access-kiosk.md)

#### XML 파일을 만들려면 다음을 실행 합니다.
-   여러 키오스크 프로필을 만들고 각 사용자/그룹에 게 할당 합니다. 예를 들어 앱이 여러 개 있는 AAD 그룹에 대해 키오스크를 사용 하 고 앱이 단수형 인 여러 앱 키오스크 사용자가 있는 방문자가 있습니다.
-   키오스크 구성은 **프로필 Id** 라고 하 고 GUID가 있습니다.
-   사용자 유형을 지정 하 고 **Defaultprofile Id**에 대해 동일한 GUID를 사용 하 여 configs 섹션에서 해당 프로필을 할당 합니다.
- XML 파일은 만들 수 있지만, 사용자 지정 OMA URI 장치 구성 프로필을 만들고 다음 URI 값을 사용 하 여 HoloLens 장치 그룹에 적용 하 여 MDM을 통해 디바이스에 적용 된 상태로 유지 됩니다./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Intune에서 키오스크를 만드는 경우
-   각 장치는 단일 키오스크 프로필만 받을 수 있으며, 그렇지 않으면 충돌을 만들고 키오스크 구성을 전혀 받지 않습니다. 
    -   키오스크 구성 프로필과 관련 되지 않은 장치 제한과 같은 다른 종류의 프로필 및 정책은 키오스크 구성 프로필과 충돌 하지 않습니다.
-   사용자 로그온 유형에 속하는 모든 사용자에 게 키오스크를 사용할 수 있으며,이는 사용자 또는 AAD 그룹으로 설정 됩니다. 
-   키오스크 구성을 설정 하 고 **사용자 로그온 유형** (키오스크에 로그인 할 수 있는 사용자)과 앱을 선택한 후에도 장치 구성은 그룹에 할당 되어야 합니다. 할당 된 그룹은 키오스크 장치 구성을 수신할 장치를 결정 하지만, 키오스크를 사용 하는 경우에는 상호 작용 하지 않습니다. 
    - Intune에서 구성 프로필을 할당 하는 효과에 대 한 자세한 내용은 [Microsoft Intune에서 사용자 및 장치 프로필 할당](https://docs.microsoft.com/intune/configuration/device-profile-assign)을 참조 하세요.

### 배포 방법 선택

다음 방법 중 하나를 선택 하 여 키오스크 구성을 배포할 수 있습니다.

- [Microsoft Intune 또는 기타 MDM (모바일 디바이스 관리) 서비스](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [프로비저닝 패키지](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 이 방법을 사용 하려면 디바이스에서 개발자 모드를 사용 하도록 설정 해야 하므로 데모 에서만 사용할 것을 권장 합니다.

다음 표에서는 각 배포 방법의 기능 및 장점을 보여 줍니다.

| &nbsp; |Windows Device Portal을 사용 하 여 배포 |프로비저닝 패키지를 사용 하 여 배포 |MDM을 사용 하 여 배포 |
| --------------------------- | ------------- | -------------------- | ---- |
|단일 앱 키오스크 배포   | 예           | 예                  | 예  |
|다중 앱 키오스크 배포    | 아니오            | 예                  | 예  |
|로컬 장치에만 배포 | 예           | 예                  | 아니오   |
|개발자 모드를 사용 하 여 배포 |필수       | 필수 아님            | 필수 아님   |
|AAD (Azure Active Directory)를 사용 하 여 배포  | 필수 아님            | 필수 아님                   | 필수  |
|자동으로 배포      | 아니오            | 아니오                   | 예  |
|배포 속도            | 빠름       | 빠름                 | 슬로우 |
|배율에 배치 | 권장 되지 않음    | 권장 사항        | 권장 사항 |

## Microsoft Intune 또는 기타 MDM을 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정

Microsoft Intune 또는 다른 MDM 시스템을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따릅니다.

1. [장치 등록을 준비](#mdmenroll)합니다.
1. [키오스크 구성 프로필을 만듭니다](#mdmprofile).
1. 키오스크를 구성 합니다.
   - [단일 앱 키오스크에 대 한 설정을 구성](#mdmconfigsingle)합니다.
   - [다중 앱 키오스크에 대 한 설정을 구성](#mdmconfigmulti)합니다.
1. [키오스크 구성 프로필을 그룹에 할당](#mdmassign)합니다.
1. 장치를 배포 합니다.
   - [단일 앱 키오스크 배포](#mdmsingledeploy)
   - [다중 앱 키오스크 배포](#mdmmultideploy)

### <a id="mdmenroll"></a>MDM, 1 단계 &ndash; 장치 등록 준비

사용자가 처음 로그인 할 때 HoloLens 장치를 자동으로 등록 하도록 MDM 시스템을 구성 하거나 사용자가 디바이스를 수동으로 등록할 수 있습니다. 또한 디바이스를 Azure AD 도메인에 가입 하 고 해당 그룹에 할당 해야 합니다.

장치를 등록 하는 방법에 대 한 자세한 내용은 [Windows 장치용 MDM 및 Intune 등록 방법](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods) [에서 HoloLens 등록](hololens-enroll-mdm.md) 을 참조 하세요.

### <a id="mdmprofile"></a>MDM, 2 단계 &ndash; 키오스크 구성 프로필 만들기

1. [Azure](https://portal.azure.com/) 포털을 열고 Intune 관리자 계정에 로그인 합니다.
1. **Microsoft Intune**  >  **장치 구성-** 프로필  >  **만들기**를 선택 합니다.
1. 프로필 이름을 입력 합니다.
1. **플랫폼**  >  **Windows 10 이상을**선택한 다음 **프로필 형식**  > **장치 제한을**선택 합니다.
1. 키오스크 **구성을**선택  >  **Kiosk**하 고 다음 중 하나를 선택 합니다.
   - 단일 앱 키오스크를 만들려면 **키오스크 모드**  >  **단일 앱 키오스크**을 선택 합니다.
   - 다중 앱 키오스크를 만들려면 **키오스크 모드**  >  **다중 앱 키오스크**을 선택 합니다.
1. 키오스크 구성을 시작 하려면 **추가**를 선택 합니다.

다음 단계는 원하는 키오스크 유형에 따라 달라 집니다. 자세한 내용을 보려면 다음 옵션 중 하나를 선택 합니다.  

- [단일 앱 키오스크](#mdmconfigsingle)
- [복수 앱 키오스크](#mdmconfigmulti)

키오스크 구성 프로필을 만드는 방법에 대 한 자세한 내용은 Intune을 [사용 하 여 전용 키오스크로 실행 하기 위한 windows 10 및 Windows 홀로그램 비즈니스 장치 설정을](https://docs.microsoft.com/intune/configuration/kiosk-settings)참조 하세요.

### <a id="mdmconfigsingle"></a>MDM, 3 단계 (단일 앱) &ndash;  단일 앱 키오스크에 대 한 설정 구성

이 섹션에서는 단일 앱 키오스크에 필요한 설정을 요약 합니다. 자세한 내용은 다음 문서를 참조 하세요.

- Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune을 사용 하 여 키오스크 모드를 구성 하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조 하세요.
- Intune의 단일 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [단일 전체 화면 앱 키오스크](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) 을 참조 하세요.
- 다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. MDM 서비스에서 사용자 지정 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 XML 파일을 만듭니다](#ppkioskconfig).

1. **사용자 로그온 유형**  >  **로컬 사용자 계정을**선택한 다음 키오스크에 로그인 할 수 있는 로컬 (장치) 계정이 나 Microsoft 계정 (MSA)의 사용자 이름을 입력 합니다.
   > [!NOTE]  
   > **자동 로그온** 사용자 계정 유형은 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.
1. **응용 프로그램 종류**  >  **스토어 앱**을 선택한 다음 목록에서 앱을 선택 합니다.

다음 단계는 프로필을 그룹에 [할당](#mdmassign) 하는 것입니다.

### <a id="mdmconfigmulti"></a>MDM, 3 단계 (다중 앱) &ndash; 다중 앱 키오스크에 대 한 설정 구성

이 섹션에서는 다중 앱 키오스크에 필요한 설정을 간략하게 보여 줍니다. 자세한 내용은 다음 문서를 참조 하세요.

- Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune을 사용 하 여 키오스크 모드를 구성 하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조 하세요.
- Intune의 다중 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [다중 앱 키오스크](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) 을 참조 하세요.
- 다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. MDM 서비스에서 사용자 지정 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 XML 파일을 만듭니다](#ppkioskconfig). XML 파일을 사용 하는 경우 [시작 레이아웃](#start-layout-for-hololens)을 포함 해야 합니다.  
- 선택적으로 Intune 또는 기타 MDM 서비스에서 사용자 지정 시작 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM (Intune 및 기타)의 시작 레이아웃 파일](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.

1. **대상 Windows 10의 S 모드 장치**  >  **번호**를 선택 합니다.  
   >[!NOTE]  
   > S 모드는 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.
1. **사용자 로그온 유형**  >  **Azure AD 사용자 또는 그룹** 또는 **사용자 로그온**  >  에**HoloLens 방문자**를 입력 하 고 하나 이상의 사용자 그룹 또는 계정 추가를 선택 합니다.  

   **사용자 로그온 유형에** 지정 하는 그룹 또는 계정에 속한 사용자만 키오스크 환경을 사용할 수 있습니다.

1. 다음 옵션을 사용 하 여 앱을 하나 이상 선택 합니다.
   - 업로드 된 lob (기간 업무) 앱을 추가 하려면 **스토어 앱 추가** 를 선택한 다음 원하는 앱을 선택 합니다.
   - AUMID를 지정 하 여 앱을 추가 하려면 **AUMID에서 추가** 를 선택 하 고 앱의 AUMID를 입력 합니다. [사용할 수 있는 AUMIDs 목록 보기](#aumids)

다음 단계는 프로필을 그룹에 [할당](#mdmassign) 하는 것입니다.

### <a id="mdmassign"></a>MDM, 4 단계 &ndash; 키오스크 구성 프로필을 그룹에 할당

키오스크 구성 프로필의 **지정** 페이지를 사용 하 여 키오스크 구성을 배포할 위치를 설정 합니다. 가장 간단한 경우에는 디바이스에서 MDM에 등록할 때 HoloLens 장치를 포함할 그룹에 키오스크 구성 프로필을 할당 합니다.

### <a id="mdmsingledeploy"></a>MDM, 5 단계 (단일 앱) &ndash; 단일 앱 키오스크 배포

MDM 시스템을 사용 하는 경우 OOBE 중에 MDM에서 장치를 등록할 수 있습니다. OOBE가 완료 된 후에는 장치에 간편 하 게 로그인 할 수 있습니다.

OOBE 중에 다음 단계를 수행 합니다.

1. 키오스크 구성 프로필에 지정한 계정을 사용 하 여 로그인 합니다.
1. 장치를 등록 합니다. 키오스크 구성 프로필이 할당 된 그룹에 장치가 추가 되어 있는지 확인 합니다.
1. OOBE가 완료 될 때까지, 스토어 앱을 다운로드 및 설치 하 고 정책을 적용할 때까지 기다립니다. 그런 다음 장치를 다시 시작 합니다.

다음에 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.

이 시점에서 키오스크 구성이 표시 되지 않으면 [과제 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.

### <a id="mdmmultideploy"></a>MDM, 5 단계 (다중 앱) &ndash; 다중 앱 키오스크 배포

MDM 시스템을 사용 하는 경우 Azure AD 테 넌 트에 디바이스를 연결 하 고 OOBE 중에 MDM에서 장치를 등록할 수 있습니다. 필요에 따라 사용자에 게 등록 정보를 제공 하 여 OOBE 프로세스 중에 사용할 수 있도록 합니다.

> [!NOTE]  
> 사용자를 포함 하는 그룹에 키오스크 구성 프로필을 할당 한 경우 해당 사용자 계정 중 하나가 장치에 로그인 하는 첫 번째 계정 인지 확인 합니다.

OOBE 중에 다음 단계를 수행 합니다.

1. **사용자 로그온 유형** 그룹에 속하는 계정을 사용 하 여 로그인 합니다.
1. 장치를 등록 합니다.
1. 키오스크 구성 프로필의 일부인 앱을 다운로드 하 여 설치 하는 경우를 기다립니다. 또한 정책이 적용 될 때까지 기다립니다.  
1. OOBE가 완료 되 면 Microsoft store 또는 테스트용 로드를 통해 추가 앱을 설치할 수 있습니다. 장치가 속한 그룹의 [필수 앱](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 이 자동으로 설치 됩니다.
1. 설치가 완료 되 면 장치를 다시 시작 합니다.

다음에 **사용자 로그온 유형에**속하는 계정을 사용 하 여 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.

이 시점에서 키오스크 구성이 표시 되지 않으면 [과제 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.

## 배포 패키지를 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정

배포 패키지를 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따릅니다.

1. [키오스크 구성을 정의 하는 XML 파일](#ppkioskconfig)( [시작 레이아웃](#start-layout-for-hololens)포함)을 만듭니다.
2. [배포 패키지에 XML 파일을 추가 합니다.](#ppconfigadd)
3. [HoloLens에 프로비저닝 패키지를 적용 합니다.](#ppapply)

### <a id="ppkioskconfig"></a>프로비저닝 패키지, 1 단계 &ndash; 키오스크 구성 XML 파일 만들기

일반 지침에 따라 다음을 제외 하 고 [Windows 데스크톱용 키오스크 구성 XML 파일을 만듭니다](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).

- 클래식 Windows 응용 프로그램 (Win32)을 포함 하지 않습니다. HoloLens는 이러한 응용 프로그램을 지원 하지 않습니다.
- HoloLens 용 [자리 표시자 시작 레이아웃 XML](#start-layout-for-hololens) 을 사용 합니다.
- 선택 사항: 키오스크 구성에 게스트 액세스 추가

#### <a id="ppkioskguest"></a>선택 사항: 키오스크 구성에 게스트 액세스 추가

[XML 파일의 **Configs** 섹션](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)에서 게스트가 키오스크를 사용할 수 있도록 **방문자** 라는 특별 한 그룹을 구성할 수 있습니다. 방문객이 **방문자** 특별 그룹을 지원 하도록 구성 된 경우 "**게스트**" 옵션이 로그인 페이지에 추가 됩니다. **Guest** 계정에는 암호가 필요 하지 않으며 계정이 로그 아웃 될 때 계정에 연결 된 모든 데이터가 삭제 됩니다.

**게스트** 계정을 사용 하도록 설정 하려면 다음 코드 조각을 키오스크 구성 XML에 추가 합니다.

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>HoloLens의 개체 틀 시작 레이아웃

[배포 패키지](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 를 사용 하 여 다중 앱 키오스크를 구성 하는 경우에는 절차에 시작 레이아웃이 필요 합니다. 시작 레이아웃 사용자 지정은 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다. 따라서 자리 표시자 시작 레이아웃을 사용 해야 합니다.

> [!NOTE]  
> 단일 앱 키오스크는 사용자가 로그인 할 때 키오스크 앱을 시작 하므로 시작 메뉴를 사용 하지 않으며 시작 레이아웃을 사용할 필요가 없습니다.

> [!NOTE]  
> [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 을 사용 하 여 다중 앱 키오스크를 설정 하는 경우 필요에 따라 시작 레이아웃을 사용할 수 있습니다. 자세한 내용은 [MDM (Intune 및 기타)에 대 한 자리 표시자 시작 레이아웃 파일](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.

시작 레이아웃의 경우 kiosk 프로비저닝 XML 파일에 다음 **Startlayout** 섹션을 추가 합니다.

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>MDM (Intune 및 기타)의 개체 틀 시작 레이아웃 파일

다음 샘플을 XML 파일로 저장 합니다. Microsoft Intune 또는 키오스크 프로필을 제공 하는 다른 MDM 서비스에서 다중 앱 키오스크을 구성할 때이 파일을 사용할 수 있습니다.

> [!NOTE]
> MDM 서비스에서 사용자 지정 설정과 전체 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [에는 프로비저닝 패키지에 대 한 시작 레이아웃 지침](#start-layout-for-hololens)을 사용 합니다.

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

### <a id="ppconfigadd"></a>Prov. 패키지, 2 단계 &ndash; 에서 kiosk 구성 XML 파일을 프로비저닝 패키지에 추가

1. [Windows 구성 디자이너](https://www.microsoft.com/store/apps/9nblggh4tx22)를 엽니다.
1. **고급 프로비저닝을**선택 하 고 프로젝트의 이름을 입력 한 후 **다음**을 선택 합니다.
1. **Windows 10 홀로그램**를 선택 하 고 **다음**을 선택 합니다.
1. **마침을**선택 합니다. 패키지에 대한 작업 영역이 열립니다.
1. **런타임 설정**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**를 선택 합니다.
1. 가운데 창에서 **찾아보기를** 선택 하 여 직접 만든 KIOSK 구성 XML 파일을 찾아 선택 합니다.

   ![Windows 구성 디자이너의 MultiAppAssignedAccessSettings 필드 스크린샷](./images/multiappassignedaccesssettings.png)

1. **선택 사항**입니다. (디바이스의 초기 설정 후에 제공 되는 프로비저닝 패키지를 적용 하려는 경우 키오스크 장치에서 이미 관리자 사용자를 사용할 수 있는 경우이 단계를 건너뛰십시오.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 사용자 계정을 만듭니다. 사용자 이름 및 암호를 입력 한 다음 **UserGroup**  >  **관리자**를 선택 합니다.  
  
     이 계정을 사용 하 여 프로비저닝 상태와 로그를 볼 수 있습니다.  
1. **선택 사항**입니다. (키오스크 장치에 관리자 이외의 계정이 이미 있는 경우에는이 단계를 건너뛰십시오.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 로컬 사용자 계정을 만듭니다. 사용자 이름이 구성 XML에서 지정 하는 계정과 동일한 지 확인 합니다. **UserGroup**  >  **표준 사용자**를 선택 합니다.
1. **파일**  >  **저장**을 선택 합니다.
1. **Export**  >  **배포 패키지**내보내기를 선택 하 고 **소유자**  >  **IT 관리자**를 선택 합니다. 이렇게 하면 다른 원본에서이 디바이스에 적용 되는 프로 비전 패키지 보다 높은 우선 순위를 설정할 수 있습니다.
1. **다음**을 선택합니다.
1. **배포 패키지 보안** 페이지에서 보안 옵션을 선택 합니다.
   > [!IMPORTANT]  
   > **패키지 서명 사용**을 선택 하는 경우 패키지에 서명 하는 데 사용할 유효한 인증서도 선택 해야 합니다. 이렇게 하려면 **찾아보기를** 선택 하 고 패키지에 서명 하는 데 사용할 인증서를 선택 합니다.
   
   > [!CAUTION]  
   > **패키지 암호화 사용**을 선택 하지 마세요. HoloLens 장치에서는이 설정으로 인해 프로비저닝이 실패 합니다.
1. **다음**을 선택합니다.
1. 프로 비전 패키지를 빌드할 때 이동할 출력 위치를 지정 합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다. 출력 위치를 변경 하려면 **찾아보기를**선택 합니다. 완료 되 면 **다음**을 선택 합니다.
1. **빌드** 를 선택 하 여 패키지 빌드를 시작 합니다. 프로비저닝 패키지를 빌드하는 데는 오랜 시간이 걸리지 않습니다. 빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.

### <a id="ppapply"></a>프로비저닝 패키지, 3 단계에서 &ndash; 배포 패키지를 HoloLens에 적용

"프로비저닝 패키지를 사용 하 여 HoloLens 구성" 문서에서는 다음과 같은 경우에 배포 패키지를 적용 하기 위한 자세한 지침을 제공 합니다.

- [설치 하는 동안 처음으로 HoloLens에 프로비저닝 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)수 있습니다.

- [설치 후에 HoloLens에 제공 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)수도 있습니다.

## Windows Device Portal을 사용 하 여 단일 앱 키오스크 설정

Windows Device Portal을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따르세요.

> [!IMPORTANT]
> 키오스크 모드는 장치에 [비즈니스용 Windows 홀로그램](hololens1-upgrade-enterprise.md) 설치 되어 있는 경우에만 사용할 수 있습니다.

1. [Windows Device Portal을 사용 하도록 HoloLens 장치를 설정](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)합니다. Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.

    > [!CAUTION]
    > 장치 포털을 사용 하도록 HoloLens를 설정 하는 경우 장치에서 개발자 모드를 사용 하도록 설정 해야 합니다. 비즈니스용 Windows 홀로그램을 사용 하는 디바이스의 개발자 모드에서 앱을 로드 하는 데 도움이 됩니다. 그러나이 설정은 사용자가 Microsoft Store에서 인증 되지 않은 앱을 설치할 수 있다는 위험을 만듭니다. 관리자는 [정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)의 **Applicationmanagement/allowdeveloper Unlock** 설정을 사용 하 여 개발자 모드를 사용 하도록 설정 하는 기능을 차단할 수 있습니다. [개발자 모드에 대해 자세히 알아보세요.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 컴퓨터에서 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 또는 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)를 사용 하 여 HoloLens에 연결 합니다.

1. 다음 중 하나를 수행합니다.
   - Windows Device Portal에 처음 연결 하는 경우 [사용자 이름 및 암호 만들기](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 이전에 설정한 사용자 이름 및 암호를 입력 합니다.

    > [!TIP]
    > 브라우저에서 인증서 오류가 표시되는 경우 [문제 해결 단계](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)를 따릅니다.

1. Windows 디바이스 포털에서 **키오스크 모드**를 선택 합니다.

1. **키오스크 모드 사용**을 선택 하 고 장치가 시작 될 때 실행할 앱을 선택한 다음 **저장**을 선택 합니다.

    ![키오스크 모드](images/kiosk.png)
1. HoloLens를 다시 시작 합니다. 디바이스 포털 페이지가 열려 있는 경우 페이지 맨 위에 있는 **다시 시작** 을 선택할 수 있습니다.

> [!NOTE]
> 필수 쿼리 문자열 매개 변수 1 개 ("kioskModeEnabled"에 "true" 또는 "false" 값을 사용 하 고, 선택적 매개 변수 ("startupApp" 패키지 이름 값이 포함 된))를 사용 하 여/api/holographic/kioskmode/settings에 대 한 게시를 수행 하 여 장치 포털의 REST API를 통해 키오스크 모드를 설정할 수 있습니다. 디바이스 포털은 개발자만 사용할 수 있으며 개발자가 작성 하지 않은 장치에서 사용 하지 않도록 설정 해야 한다는 점에 유의 하세요. REST API는 향후 업데이트/릴리스에서 변경 될 수 있습니다.

## 추가 정보

배포 패키지를 사용 하 여 키오스크를 구성 하는 방법을 시청 하세요.  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

## HoloLens 용 XML 키오스크 코드 샘플

### AAD 그룹을 대상으로 하는 여러 앱 키오스크 모드입니다. 
이 키오스크는 AAD 그룹의 사용자에 게 키오스크를 제공 하며, 3 개의 앱: 설정, 원격 지원 및 피드백 허브를 포함 하는 키오스크 기능을 사용 하도록 설정 합니다. 이 샘플을 즉시 사용 하도록 수정 하려면 아래에서 강조 표시 된 GUID를 변경 하 여 직접 AAD 그룹과 일치 하도록 해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### AAD 계정을 대상으로 하는 여러 앱 키오스크 모드입니다.
이 키오스크는 단일 사용자를 위해 키오스크 기능을 제공 하며, 3 개의 앱: 설정, 원격 지원 및 피드백 허브를 포함 하는 키오스크를 사용 합니다. 이 샘플을 즉시 사용 하도록 수정 하려면 아래에 강조 표시 된 계정을 변경 하 여 직접 AAD 계정과 일치 하도록 해야 합니다. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

