---
title: HoloLens 키오스크 참조 정보
description: HoloLens 장치에서 키오스크를 위한 정보 및 샘플입니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033205"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens 키오스크 참조 정보

이 페이지에는 HoloLens 장치의 키오스크 모드를 설정 하는 데 유용한 정보가 포함 되어 있습니다. 이 참조에는 수신함 앱에 대 한 AUMIDs가 포함 되어 있으며, 키오스크 모드에 대 한 몇 가지 XML 샘플은 몇 가지 다른 시나리오에 사용할 준비가 되지 않은 몇 가지 편집이 있습니다. 키오스크를 설정 하는 방법에 대 한 자세한 내용은 [키오스크 설정 페이지를 참조 하세요.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens 응용 프로그램 사용자 모델 Id (AUMIDs)  

키오스크 앱을 선택 하는 방법에 대 한 일반 정보는 [할당 된 액세스를 위해 앱을 선택 하기 위한 지침 (키오스크 모드)](/windows/configuration/guidelines-for-assigned-access-app)을 참조 하세요.

MDM (모바일 장치 관리) 시스템 또는 프로 비전 패키지를 사용 하 여 키오스크 모드를 구성 하는 경우 [ASSIGNEDACCESS CSP (구성 서비스 공급자)](/windows/client-management/mdm/assignedaccess-csp) 를 사용 하 여 응용 프로그램을 지정 합니다. CSP는 [응용 프로그램 사용자 모델 id (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 를 사용 하 여 응용 프로그램을 식별 합니다. 다음 표에는 다중 앱 키오스크에서 사용할 수 있는 일부 기본 제공 응용 프로그램의 AUMIDs가 나와 있습니다.

<a id="aumids"></a>

|앱 이름 |AUMID |
| --- | --- |
|3D 뷰어 |Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|달력 |windowscommunicationsapps \_ 8wekyb3d8bbwe \! live |
|카메라<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |549981C3F5F10 \_ 8wekyb3d8bbwe \! 앱 |
|HoloLens 장치 선택 (첫 번째 gen) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2의 장치 선택 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Windows. DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. remoteassist |
|피드백 &nbsp; 허브 |WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 앱 |
|파일 탐색기 |c5e2524a-ea46-4f67-6a9465d9d515_cw5n1h2txyewy! 다운로드 |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! live |
|이전 Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|새로운 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! 다운로드 |
|Miracast<sup>4</sup> | &nbsp; |
|영화 및 TV |Microsoft 8wekyb3d8bbwe-zunevideo \_ \! |
|OneDrive |microsoftskydrive \_ 8wekyb3d8bbwe \! 앱 |
|사진 |Microsoft. Windows. 사진 \_ 8wekyb3d8bbwe \! 앱 |
|이전 설정 |HolographicSystemSettings_cw5n1h2txyewy! 다운로드 |
|새 설정 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 다운로드 |
|팁 |HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 사진 또는 비디오 캡처를 사용 하도록 설정 하려면 카메라 앱을 키오스크 앱으로 사용 하도록 설정 해야 합니다.  
> <sup>2</sup> 카메라 앱을 사용 하도록 설정 하는 경우 다음 조건을 알고 있어야 합니다.
> - 빠른 작업 메뉴에는 사진 및 비디오 단추가 포함 됩니다.
> - 또한 사진을 조작 하거나 검색할 수 있는 앱 (예: 사진, 메일 또는 OneDrive)을 사용 하도록 설정 해야 합니다.  
>  
> <sup>3</sup> 키오스크 앱으로 Cortana를 사용 하도록 설정 하지 않은 경우에도 기본 제공 음성 명령이 사용 됩니다. 그러나 비활성화 된 기능과 관련 된 명령은 아무런 영향을 주지 않습니다.  
> <sup>4</sup> Miracast를 직접 사용 하도록 설정할 수 없습니다. 키오스크 앱으로 Miracast 사용 하도록 설정 하려면 카메라 앱 및 장치 선택 앱을 사용 하도록 설정 합니다.

또한 혼합 현실 홈을 키오스크 앱으로 설정할 수 없습니다.

[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

## <a name="kiosk-xml-code-samples"></a>키오스크 XML 코드 샘플

1. [여러 앱 전역 할당 된 액세스 프로필](#multiple-app-global-assigned-access-profile)
1. [장치 소유자를 제외한 여러 앱 전역 할당 액세스 프로필](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [로컬 계정 또는 AAD 사용자 계정에 대 한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [두 AAD 사용자에 대 한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [하나의 AAD 그룹에 대 한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [두 AAD 그룹에 대 한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [하나의 AAD 계정 및 하나의 AAD 그룹에 대 한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [방문자에 게 할당 된 여러 앱 액세스 프로필](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> 사용자 요구 사항에 따라 TODO 동작을 대체 합니다.

### <a name="multiple-app-global-assigned-access-profile"></a>여러 앱 전역 할당 된 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>장치 소유자를 제외한 여러 앱 전역 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>로컬 계정 또는 AAD 사용자 계정에 대 한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>두 AAD 사용자에 대 한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>하나의 AAD 그룹에 대 한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>두 AAD 그룹에 대 한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>하나의 AAD 계정 및 하나의 AAD 그룹에 대 한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>방문자에 게 할당 된 여러 앱 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
[Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아가기
