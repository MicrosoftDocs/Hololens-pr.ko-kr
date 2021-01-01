---
title: 배포 가이드 - 원격 지원으로 클라우드 연결 HoloLens 2 배포 대규모 배포 - 배포
description: 클라우드 연결 네트워크를 통해 HoloLens 장치에 대한 등록 및 원격 지원의 유효성을 검사하는 방법
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253195"
---
# 배포 - 클라우드 연결 가이드

이제 모든 구성이 완료되었습니다. 이제 장치를 배포할 준비가 된 것입니다. 그러나 이제는 먼저 설치의 유효성을 검사해야 합니다. 먼저 Azure AD 가입 및 MDM 등록 프로세스의 유효성을 검사한 다음 원격 지원 통화가 걸 수 있는지 확인해야 합니다.

## 등록 유효성 검사

이제 모든 것이 Azure AD 및 MDM 등록에 맞게 제대로 구성되면 나머지는 스냅인이 됩니다. 이전에&#39;AAD 사용자 Wi-Fi 및 HoloLens 디바이스가 필요합니다.

장치가 현재&#39;설정 상태로 있지 않은 경우 이제 장치를 다시 래시하는 [것이 좋습니다.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. 디바이스가 OOBE에 있는 경우&#39;및 프롬프트에 따라 상호 작용을 시작해야 합니다. 
1. 이 **HoloLens를** 누가 소유하고 있나요? 내 **직장 또는 학교** 소유를 선택하고 Azure AD 계정 자격 증명을 입력합니다.
1. 등록에 성공하면&#39;설정하라는 메시지가 표시될 수 있습니다. 이 PIN은 이 사용자에 대해 이 장치에 고유합니다. 또한 홍채 검사, 음성 데이터 및 원격 분석 설정에 대한 메시지가 표시되고 마지막으로&#39;메뉴를 열고 OOBE를 완료하는 방법을 배울 수 있습니다.
1. Mixed Reality 홈에 착수하면 방금 **** 배운 시작 제스처를 사용하여 시작 메뉴를 니다.
1. 설정 **앱을 선택하고** 시스템을 **선택합니다.** 첫 번째&#39;볼 수 있는 정보는 장치 이름입니다. HoloLens 2 디바이스의 경우 HOLOLENS와 6개의 문자 문자열이 &quot; &quot; 함께 표시됩니다.
1. 이 이름을 메모해 두면 됩니다.

![HoloLens 2 설정 - 정보](./images/hololens2-settings-about.jpg)

7. 설정 앱 내에서 장치가 Azure AD에 성공적으로 등록된 것을 확인할 수 있습니다. **설정에서** **계정 액세스**직장 또는  ->  **학교를 선택합니다.** 이 화면에서 Azure &quot; AD의 _nameofAAD에_ 연결&#39;확인하여 성공적으로 등록되어 있는지 확인할 수 있습니다. _yourusername_ @ _nameofAAD_.onmicrosoft.com. &quot;


Azure AD에 가입된 장치의 유효성을 검사하기 위해 [Azure Portal](https://portal.azure.com/#home)Azure Active Directory 장치 모든 디바이스에서 Azure Active  ->  **Directory를**확인하고  ->  ****  ->  **** 장치 이름을 검색할 수 있습니다. Azure&#39;디바이스가 Azure Active Directory의 일부인지 볼 수 있습니다.


![Azure Active Directory - 장치](./images/aad-enrollment.png)

다음으로&#39;Microsoft Endpoint Manager 관리 센터에 [로그인해야 합니다.](https://endpoint.microsoft.com/#home) 로그인하고 **디바이스를** 선택한 **다음 모든 장치를 선택합니다.** 여기에서 HoloLens 장치 이름과&#39;수 있습니다. Intune에 나열된 HoloLens를 볼 수 있습니다.

![Intune - 장치](./images/endpoint-all-devices-enrolled.png)

## 원격 지원 통화 유효성 검사

AAD&#39;MDM 모두에 장치가 등록되어 있는 것을 확인한 후&#39;원격 지원 통화를 걸 수 있습니다. 이 유효성 검사를&#39;Pc에 대한 두 번째 Azure AD 사용자 계정뿐만 아니라 HoloLens 장치 및 Windows 10 PC가 필요합니다.

이 유효성 검사 단계에서는 사용자가 이전에 마지막 유효성 검사 단계를 완료하고 장치가 등록된 경우 Azure AD 사용자가 장치에 있는 것으로 가정합니다.


1. PC에 Microsoft Teams가 설치되어 있지 않은 경우 여기에서 [Teams를 다운로드할 수 있습니다.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. 현재 HoloLens에 로그인한 계정보다 두 번째 Azure AD 사용자 계정을 사용하여 Teams에 로그인합니다. PC에 로그인하면 전화를 받을 준비가 됩니다.
3. HoloLens 잠금을 해제하고 로그인합니다.
4. 원격 지원 앱을 시작하려면 시작 메뉴를 **열고** 원격 지원을 **선택합니다.** 원격 도우미는 받은 편지함 앱으로 번들로 제공된 것이 아니라 HoloLens 2&#39;시작 메뉴에 고정됩니다. 시작 메뉴에&#39;없는 경우 모든 앱 목록을 열어서 찾아야 합니다. ****
5. 원격 지원이 시작되면 [SSO를](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 통해 디바이스 사용자를 식별하고 앱에 로그인해야 합니다.
6. 앱에서 PC에서 **두** 번째 사용자 검색을 선택하고 검색합니다. 통화를 시작할 사용자를 선택합니다.
7. PC에서 통화에 응답합니다.

축하합니다&#39;성공적으로 연결되고 원격 지원 통화에 있습니다. 다음과 같은 특정 원격 지원 기능을 사용해 보아야 합니다.

- [Inking annotations](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [혼합 현실에서 파일 공유 및 보기](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [다른 HoloLens 앱에서 도움말 다운로드](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## 다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 유지 관리](hololens2-cloud-connected-maintain.md)