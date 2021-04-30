---
title: 배포 가이드 – 클라우드로 연결 된 HoloLens 2 배포, 원격 지원-배포
description: 클라우드 연결 네트워크를 통해 HoloLens 장치에 대 한 등록 및 원격 지원의 유효성을 검사 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309795"
---
# <a name="deploy---cloud-connected-guide"></a>배포-클라우드 연결 가이드

모든 항목을 구성 했으므로 이제 장치를 배포할 준비가 되었습니다. 그러나 이제는 먼저 설치의 유효성을 검사 해야 합니다. 먼저 Azure AD 조인 및 MDM 등록 프로세스의 유효성을 검사 한 후 원격 지원 전화를 걸 수 있는지 확인 해야 합니다.

## <a name="enrollment-validation"></a>등록 유효성 검사

이제 Azure AD 및 MDM 등록에 대해 모든 것이 올바르게 구성 되었으므로 나머지는 이제 snap 여야 합니다. 이전에 구성 된 AAD 사용자 계정 중 하나를 비롯 하 여 Wi-Fi 연결 및 HoloLens 장치가 필요&#39;.

현재 공장 설정 상태에 있는 장치를&#39;하지 않는 경우 이제 [장치를 경감 하기 위해](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)하는 것이 좋습니다.

1. 장치가 OOBE에 있으면 상호 작용을 시작 하 고 메시지를 따라&#39;합니다. 
1. **이 HoloLens를 소유 하는 사용자** 를 묻는 메시지가 표시 되 면 중요 한 프롬프트가 표시 됩니다. **회사 또는 학교 소유의 회사** 를 선택 하 고 Azure AD 계정 자격 증명을 입력 합니다.
1. 성공적으로 등록 되 면 PIN을 설정 하 라는 메시지가 표시&#39;. 이 PIN은이 사용자에 대해이 장치에 대해 고유 합니다. 또한 Iri 검색, 음성 데이터 및 원격 분석 설정을 입력 하 라는 메시지가 표시 되 고, 마지막으로 시작 메뉴를 열고 OOBE를 완료 하는 방법을 배울 수&#39;있습니다.
1. Mixed Reality 홈에 도착 하면 방금 배운 **시작 제스처** 를 사용 하 여 시작 메뉴를 엽니다.
1. **설정** 앱을 선택 하 고 **시스템을 선택 합니다.** &#39;하는 첫 번째 정보는 HoloLens 2 장치에 hololens를 적용 한 &quot; &quot; 후 6 개의 문자열이 표시 되는 장치 이름입니다.
1. 이 이름을 적어 둡니다.

![HoloLens 2 설정-정보](./images/hololens2-settings-about.jpg)

7. 설정 앱 내에서 장치가 Azure AD에 성공적으로 등록 되었는지 확인할 수 있습니다. **설정** 에서 **계정**  ->  에 **회사 또는 학교 액세스** 를 선택 합니다. 이 화면에서 &quot; _nameofAAD_&#39;s Azure AD에 연결 된 것을 확인 하 여 성공적으로 등록 되었는지 확인할 수 있습니다. _사용자 이름_ @ _nameofAAD_. onmicrosoft.com로 연결 &quot; 됩니다.


장치에 연결 된 Azure AD의 유효성을 검사 하려면 모든 장치에서 [Azure Portal](https://portal.azure.com/#home)Azure Active Directory 장치에서 Azure Active Directory를 확인 하  ->    ->    ->  고 장치 이름을 검색할 수 있습니다. 장치가 Azure Active Directory의 일부임을 확인할 수&#39;.


![Azure Active Directory-장치](./images/aad-enrollment.png)

다음으로 [Microsoft 끝점 관리자 관리 센터](https://endpoint.microsoft.com/#home)에 로그인 해야&#39;. 로그인 하 고 **장치** , **모든 장치** 를 차례로 선택 합니다. 여기에서 HoloLens 장치&#39;s 이름을 검색할 수 있습니다. HoloLens가 Intune에 나열 된 것을 볼 수 있습니다.

![Intune-장치](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>원격 지원 통화 유효성 검사

장치가 AAD 및 MDM 모두에 등록 되었는지 확인 한 후에는 테스트 원격 지원 전화를&#39;하는 시간이&#39;. 이 유효성 검사를 수행 하려면 HoloLens 장치 및 Windows 10 PC와 PC에 대 한 두 번째 Azure AD 사용자 계정이 있어야&#39;있습니다.

이 유효성 검사 단계에서는 이전에 마지막 유효성 검사 단계를 완료 했으며 장치가 등록 되었고 Azure AD 사용자가 장치에 있는 것으로 가정 합니다.


1. PC에 Microsoft 팀이 아직 설치 되어 있지 않은 경우 [여기에서 팀을 다운로드할](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)수 있습니다.
2. 현재 HoloLens에 로그인 한 사용자가 아닌 다른 Azure AD 사용자 계정을 사용 하 여 팀에 로그인 합니다. PC에서 로그인 하면 전화를 받을 준비가 됩니다.
3. HoloLens의 잠금을 해제 하 고 로그인 합니다.
4. 원격 지원 앱을 시작 하려면 **시작 메뉴** 를 열고 **원격 지원** 을 선택 합니다. 원격 지원 기능은 받은 편지함 앱으로 번들로 제공 되는 것이 아니라 HoloLens 2&#39;s 시작 메뉴에 고정 됩니다. 시작 메뉴에 고정 되어&#39;하지 않은 이벤트의 경우 **모든 앱** 목록을 열어 찾습니다.
5. 원격 지원이 시작 되 면 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 를 통해 장치 사용자를 식별 하 고 앱에 로그인 해야 합니다.
6. 앱 내에서 **검색** 을 선택 하 고 PC에서 두 번째 사용자를 검색 합니다. 사용자를 선택 하 여 호출을 시작 합니다.
7. PC에서 호출에 응답 합니다.

축 하 합니다. 성공적으로 연결 되 고 원격 지원 전화를&#39;합니다. 다음을 사용 하는 등의 특정 원격 지원 기능을 사용해 보세요.

- [주석 입력](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [혼합 현실에서 파일 및 뷰 공유](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [다른 HoloLens 앱에서 도움 받기](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포-유지 관리](hololens2-cloud-connected-maintain.md)