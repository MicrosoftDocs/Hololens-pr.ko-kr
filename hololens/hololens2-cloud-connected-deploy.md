---
title: 배포 가이드 – Remote Assist 대규모로 클라우드 연결 HoloLens 2 배포 - 배포
description: 클라우드 연결 네트워크를 통해 HoloLens 디바이스에 대한 등록 및 Remote Assist 유효성을 검사하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 클라우드 연결, Remote Assist, AAD, Azure AD, MDM, Mobile 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 593dc65ab97eaae65591a5239cd0a978750eac9fa538364ba6bbc7ef0a2a08a4
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660519"
---
# <a name="deploy---cloud-connected-guide"></a>배포 - 클라우드 연결 가이드

이제 모든 것을 구성했으므로 디바이스를 배포할 준비가 되었습니다. 그러나 이제는 설치의 유효성을 먼저 검사해야 합니다. 먼저 Azure AD 조인 및 MDM 등록 프로세스의 유효성을 검사한 다음 Remote Assist 호출을 배치할 수 있는지 확인해야 합니다.

## <a name="enrollment-validation"></a>등록 유효성 검사

이제 모든 것이 Azure AD 및 MDM 등록에 대해 올바르게 구성되었으며 나머지는 이제 맞춤이어야 합니다. &#39;Wi-Fi 연결과 HoloLens 디바이스뿐만 아니라 이전에 구성된 AAD 사용자 계정 중 하나가 필요합니다.

디바이스가 현재 공장 설정 상태에 있지&#39;경우 이제 [디바이스를 다시 반사하는](/hololens/hololens-recovery#clean-reflash-the-device)것이 좋습니다.

1. 디바이스가 OOBE에 있으면&#39;상호 작용을 시작하고 프롬프트를 따라야 합니다. 
1. 중요한 프롬프트는 **이 HoloLens 소유할 Who** 묻는 메시지가 표시될 때입니다. **내 직장 또는 학교 소유를** 선택하고 Azure AD 계정 자격 증명을 입력합니다.
1. 등록에 성공하면 PIN을 설정하라는 메시지가&#39;. 이 PIN은 이 사용자에 대해 이 디바이스에 고유합니다. 또한 아이리스 스캔, 음성 데이터 및 원격 분석 설정에 대한 메시지가 표시되고 마지막으로 시작 메뉴를 열고 OOBE를 완료하는 방법을 배울 수&#39;있습니다.
1. Mixed Reality Home에 도착하면 방금 배운 **시작 제스처를** 사용하여 시작 메뉴 엽니다.
1. **설정** 앱을 선택하고 시스템을 **선택합니다.** &#39;표시되는 첫 번째 정보는 디바이스 이름이며, HoloLens 2 디바이스의 경우 &quot; HOLOLENS- &quot; 뒤에 6개의 문자열이 잇습니다.
1. 이 이름을 기록해 둡다.

![HoloLens 2 설정 - 정보](./images/hololens2-settings-about.jpg)

7. 디바이스가 설정 앱 내의 Azure AD에 성공적으로 등록되었는지 확인할 수 있습니다. **설정**   ->  **계정회사 또는 학교 액세스를** 선택합니다. 이 화면에서 &quot; _nameofAAD_&#39;Azure AD에 연결됨을 확인하여 성공적으로 등록되었는지 확인할 수 있습니다. _yourusername_ @ _nameofAAD_.onmicrosoft.com 연결합니다. &quot;


디바이스에 Azure AD 조인이 있는지 확인하려면 [Azure Portal Azure Active Directory](https://portal.azure.com/#home)모든 디바이스에서 Azure Active Directory 확인하고  ->    ->    ->  **디바이스** 이름을 검색할 수 있습니다. &#39;디바이스가 Azure Active Directory 일부임을 확인할 수 있습니다.


![Azure Active Directory - 디바이스](./images/aad-enrollment.png)

다음으로&#39;[Microsoft Endpoint Manager 관리 센터에](https://endpoint.microsoft.com/#home)로그인해야 합니다. 로그인하고 **디바이스를** 선택한 **다음, 모든 디바이스를** 선택합니다. 여기에서 HoloLens 디바이스&#39;이름을 검색할 수 있습니다. Intune에 나열된 HoloLens 볼 수 있어야 합니다.

![Intune - 디바이스](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist 호출 유효성 검사

디바이스가 AAD 및 MDM 둘 다에 등록되어 있는지&#39;확인한 후에는 테스트 Remote Assist 호출을&#39;. 이 유효성 검사를 위해&#39;HoloLens 디바이스와 Windows 10 PC뿐만 아니라 PC에 대한 두 번째 Azure AD 사용자 계정이 있어야 합니다.

이 유효성 검사 단계에서는 이전에 마지막 유효성 검사 단계를 완료했고 디바이스가 등록되었고 Azure AD 사용자가 디바이스에 있다고 가정합니다.


1. PC에 Microsoft Teams 설치되어 있지 않은 경우 여기에서 Teams [다운로드할](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)수 있습니다.
2. 현재 HoloLens 로그인한 계정보다 두 번째 Azure AD 사용자 계정을 사용하여 Teams 로그인합니다. PC에 로그인하면 전화를 받을 준비가 됩니다.
3. HoloLens 잠금 해제하고 로그인합니다.
4. Remote Assist 앱을 시작하려면 시작 **메뉴를** 열고 **Remote Assist** 선택합니다. Remote Assist 받은 편지함 앱으로 번들로 제공될 뿐만 아니라 HoloLens 2&#39;시작 메뉴에 고정됩니다. 시작 메뉴 고정된 것을 볼&#39;없는 경우 **모든 앱** 목록을 열어 찾습니다.
5. Remote Assist 시작되면 [SSO를](/azure/active-directory/manage-apps/what-is-single-sign-on) 통해 디바이스 사용자를 식별하고 앱에 로그인해야 합니다.
6. 앱 내에서 **검색을** 선택하고 PC에서 두 번째 사용자를 검색합니다. 통화를 시작할 사용자를 선택합니다.
7. PC에서 통화에 응답합니다.

축하합니다.&#39;성공적으로 연결되었으며 원격 지원 통화에 있습니다. 다음과 같은 특정 원격 지원 기능을 사용해 보세요.

- [수동 주석](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [혼합 현실에서 파일 및 보기 공유](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [다른 HoloLens 앱에서 도움말 받기](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 유지 관리](hololens2-cloud-connected-maintain.md)