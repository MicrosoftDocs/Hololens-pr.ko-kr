---
title: 키오스크 참조 정보 HoloLens
description: HoloLens 디바이스의 키오스크에 대한 정보 및 샘플입니다.
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
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863946"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens 키오스크 참조 정보

이 페이지에는 HoloLens 디바이스의 키오스크 모드를 설정하는 데 유용한 정보가 포함되어 있습니다. 이 참조에는 받은 편지함 앱 및 사용자 찾기에 대한 AUMID와 키오스크 모드에 대한 여러 XML 샘플이 포함됩니다. 이 샘플은 몇 가지 다른 시나리오에 사용할 준비가 되어 있는 몇 가지 편집에 불과합니다. 키오스크 설정에 대한 자세한 내용은 [키오스크 설정 페이지를 읽어보십시오.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens 애플리케이션 사용자 모델 ID(AUMID)  

키오스크 앱을 선택하는 방법에 대한 일반적인 내용은 [할당된 액세스용 앱 선택 지침(키오스크 모드)을](/windows/configuration/guidelines-for-assigned-access-app)참조하세요.

MDM(모바일 장치 관리) 시스템 또는 프로비전 패키지를 사용하여 키오스크 모드를 구성하는 경우 [AssignedAccess CSP(구성 서비스 공급자)를](/windows/client-management/mdm/assignedaccess-csp) 사용하여 애플리케이션을 지정합니다. CSP는 [AUMID(애플리케이션 사용자 모델 ID)를](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 사용하여 애플리케이션을 식별합니다. 다음 표에서는 다중 앱 키오스크에서 사용할 수 있는 일부 바로 사용 애플리케이션의 AUMID를 나열합니다.

<a id="aumids"></a>

|앱 이름 |AUMID |
| --- | --- |
|3D 뷰어 |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|달력 |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
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
|새로운 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! 앱 |
|Miracast<sup>4</sup> | &nbsp; |
|영화 및 TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|사진 |Microsoft. Windows. \_사진 8wekyb3d8bbwe \! 앱 |
|이전 설정 |HolographicSystemSettings_cw5n1h2txyewy! 앱 |
|새 설정 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 앱 |
|팁 |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 사진 또는 비디오 캡처를 사용하도록 설정하려면 카메라 앱을 키오스크 앱으로 사용하도록 설정해야 합니다.  
> <sup>2</sup> 카메라 앱을 사용하도록 설정하는 경우 다음 조건을 알고 있어야 합니다.
> - 빠른 작업 메뉴에는 사진 및 비디오 단추가 포함됩니다.
> - 그림과 상호 작용하거나 사진을 검색할 수 있는 앱(예: 사진, 메일 또는 OneDrive)도 사용하도록 설정해야 합니다.  
>  
> <sup>3</sup> 키오스크 앱으로 Cortana 사용하도록 설정하지 않은 경우에도 기본 제공 음성 명령이 사용하도록 설정됩니다. 그러나 비활성화된 기능과 관련된 명령은 아무런 영향을 미치지 않습니다.  
> <sup>4</sup> Miracast 직접 사용하도록 설정할 수 없습니다. 키오스크 앱으로 Miracast 사용하도록 설정하려면 카메라 앱 및 디바이스 선택기 앱을 사용하도록 설정합니다.

또한 Mixed Reality 홈은 키오스크 앱으로 설정할 수 없습니다.

ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

## <a name="kiosk-xml-code-samples"></a>키오스크 XML 코드 샘플

1. [여러 앱 전역 할당 액세스 프로필](#multiple-app-global-assigned-access-profile)
1. [디바이스 소유자를 제외한 여러 앱 전역 할당 액세스 프로필](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [로컬 계정 또는 AAD 사용자 계정에 대한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [두 명의 AAD 사용자에 대한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [하나의 AAD 그룹에 대한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [두 개의 AAD 그룹 이상에 대한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [하나의 AAD 계정 및 하나의 AAD 그룹에 대한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [방문자를 위한 여러 앱 할당 액세스 프로필](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> 요구 사항에 따라 TODO 작업을 바꿉니다.

### <a name="multiple-app-global-assigned-access-profile"></a>여러 앱 전역 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>디바이스 소유자를 제외한 여러 앱 전역 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>로컬 계정 또는 AAD 사용자 계정에 대한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>두 명의 AAD 사용자에 대한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>하나의 AAD 그룹에 대한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>두 개의 AAD 그룹 이상에 대한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>하나의 AAD 계정 및 하나의 AAD 그룹에 대한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>방문자를 위한 여러 앱 할당 액세스 프로필

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[목록으로 돌아가기](#kiosk-xml-code-samples) <br>
ID [유형에 따라 키오스크 모드에 대해 지원되는 시나리오로](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) 돌아갑니다.
