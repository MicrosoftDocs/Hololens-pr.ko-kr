---
title: 배포 가이드 – Dynamics 365 Guides-배포를 사용 하 여 회사에 연결 된 HoloLens 2
description: Dynamics 365 Guides를 사용 하 여 회사에 연결 된 네트워크를 통해 HoloLens 2 장치 배포를 설정 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사에 연결 된 Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637067"
---
# <a name="deploy---corporate-connected-guide"></a>배포-회사에 연결 된 가이드

각 배포의 중요 한 부분은 최종 사용자에 게 원활한 환경을 제공 하기 위해 테스트 하기 전에 배포가 적절히 설정 되었는지 확인 하는 것입니다.

MDM을 통해 Wi-Fi 인증서를 배포 하기 때문에 처음에 HoloLens를 설정 하 고 열린 Wi-Fi 네트워크 또는 인증서가 필요 없는 네트워크에 장치를 등록 해야 합니다. HoloLens OOBE를 완료 하 고 등록 한 후에는 장치에서 이전에 구성 된 네트워크 인증서 및 LOB를 수신 하 고 장치에서 수신 된 모든 유효성을 검사할 수 있게 됩니다.

그런 다음 테스트 가이드를 작성 하 고 운영할 수 있는지 확인할 수 있습니다.

## <a name="enrollment-validation"></a>등록 유효성 검사

이제 Azure AD 및 MDM 등록에 대해 모든 것이 올바르게 구성 되었으므로 나머지는 이제 snap 여야 합니다. Wi-Fi 연결 및 HoloLens 장치와 이전에 구성 된 Azure AD 사용자 계정 중 하나가 필요 합니다.

장치가 현재 공장 설정 상태에 있지 않은 경우 이제 [장치를 경감 하기 위해](/hololens/hololens-recovery#clean-reflash-the-device)하는 것이 좋습니다.

1. 장치가 OOBE에 있으면 상호 작용을 시작 하 고 메시지를 따라 시작 해야 합니다.

2. Wi-fi에 연결 하는 데 인증서가 필요 하지 않은 열려 있는 Wi-Fi 네트워크에 커넥트 합니다. 이렇게 하면 초기 설치 후 장치에서 조직의 Wi-Fi에 사용할 인증서를 다운로드할 수 있습니다.

3. **이 HoloLens를 소유 Who** 묻는 메시지가 표시 되 면 중요 한 프롬프트가 표시 됩니다. **회사 또는 학교 소유의 회사** 를 선택 하 고 Azure AD 계정 자격 증명을 입력 합니다.

4. 성공적으로 등록 되 면 PIN을 설정 하 라는 메시지가 표시 됩니다. 이 PIN은이 사용자에 대해이 장치에 대해 고유 합니다. 또한 Iri 검색, 음성 데이터 및 원격 분석 설정을 입력 하 라는 메시지가 표시 되 고 마지막으로 시작 메뉴를 열고 OOBE를 완료 하는 방법을 배울 수 있습니다.

5. Mixed Reality 홈에 도착 하면 방금 배운 **시작 제스처** 를 사용 하 여 시작 메뉴를 엽니다.

6. **설정** 앱을 선택 하 고 **시스템** 을 선택 합니다. 표시 되는 첫 번째 정보는 장치 이름입니다 .이 이름에는 HoloLens 2 장치에 대 한 &quot; HoloLens와 &quot; 6 개의 문자열이 차례로 표시 됩니다.

7. 이 이름을 적어 둡니다.

    ![HoloLens 2 설정 화면](./images/hololens2-settings-about.jpg)

8. 장치가 Azure AD에 성공적으로 조인 되었는지 확인 합니다. 두 가지 방법이 있습니다.

    1.  설정 앱입니다. **설정** 에서   ->  **회사 또는 학교 액세스** 계정을 선택 합니다. 이 화면에서 &quot; nameofAAD&#39;s AZURE AD에 연결 된 것을 확인 하 여 성공적으로 등록 되었는지 확인할 수 있습니다. 로 연결 *yourusername@nameofAAD.onmicrosoft.com* 됩니다. 그러면 장치가 조직&#39;s Azure AD에 가입 되어 있는지 확인할 수 있습니다.

    1. [Azure Portal](https://portal.azure.com/#home)입니다. **Azure Active Directory**  ->  **장치**  ->  **모든 장치** 로 이동 하 여 장치 이름을 검색 합니다. 조인 유형 아래에서 ' Azure AD 조인 됨 '으로 표시 됩니다.
        ![Azure AD에서 조인 유형 확인](./images/hololens2-devices-all-devices.png)

9. 장치가 MDM에 등록 되었는지 확인 합니다. 두 가지 방법이 있습니다.

    1. **설정** 에서 **계정**  ->  **회사 또는 학교 액세스** 를 선택 합니다. 이 화면에서 &quot; nameofAAD&#39;s AZURE AD에 연결 된 것을 확인 하 여 성공적으로 등록 되었는지 확인할 수 있습니다. 로 연결 *yourusername@nameofAAD.onmicrosoft.com* 됩니다. 이 액세스 회사 또는 학교 계정에서 &quot; nameofAAD&#39;s AZURE AD에 연결 됨을 선택 합니다. 연결 방법 yourusername@nameofAAD.onmicrosoft.com &quot; 및 **정보** 단추를 선택 합니다.

    1. [관리 센터를 Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)합니다. 로그인 하 고  **장치**  ,  **모든 장치** 를 차례로 선택 합니다. 여기에서 HoloLens 장치&#39;이름으로 검색할 수 있습니다. Intune에 나열 된 HoloLens를 확인할 수 있어야 합니다.

        ![Azure AD에서 Intune에서 관리 확인](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>인증서 유효성 검사 Wi-Fi

이제 장치가 Wi-Fi 인증서를 받아야 합니다. 가장 간단한 유효성 검사는 인증서를&#39;ve Wi-Fi 연결에 연결 하려고 시도 하는 것입니다. **설정** 앱을 열고 **Network &amp; Internet** wi-fi로 이동 하  ->   여 wi-fi 연결을 선택 합니다. 연결 되 면 Microsoft Edge 앱을 열고 웹 사이트로 이동할 수 있는지 확인 합니다.

장치에서 인증서를 받았는지 확인 하려면 [인증서 관리자](/hololens/certificate-manager)를 사용할 수 있습니다.

## <a name="validate-lob-app-install"></a>LOB 앱 설치 유효성 검사

관리 되는 앱의 설치 진행률을 보려면 앱이 설치 되어 있는지 확인 하거나 설정 확인 합니다. LOB 앱을 그룹에 대 한 필수 설치로 구성 하면 할당 된 그룹의 사용자에 게 HoloLens을 등록 한 후 앱이 HoloLens 자동으로 다운로드 됩니다.

시작 메뉴를 열고 **모든 앱** 을 선택 합니다. 보유 한 앱의 수에 따라 **page up** 또는 **page down** 단추를 사용 해야 할 수 있습니다.

장치에서 앱 설치의 유효성을 검사 하려면 **설정**  ->  **계정을** 통해  ->  **회사 또는 학교에 액세스** 하 고, 계정을 선택한 다음 **정보** 단추를 선택 하 고 아래로 스크롤하여 MDM에서 장치에 적용 되는 다양 한 구성 및 앱을 확인 합니다.

Intune에서 설치의 유효성을 검사 하려면 [메모리 포털](https://endpoint.microsoft.com/#home)  ->  **앱** -> 모든 **앱**  -> *TheNameOfYourApp*  ->  **장치 설치 상태** 페이지로 이동 합니다.

자세히 보기: [Intune 앱 배포 HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>유효성 검사 Dynamics 365 Guides

HoloLens, 제작 및 운영에 대 한 가이드 앱의 모드가 있습니다. 작업을 수행 하기 전에 가이드 작성을 완료 해야 합니다.

### <a name="authoring-the-guide"></a>가이드 작성

이 빠른 유효성 검사에 대해 많은 작업을 수행할 필요가 없습니다. PC에서 준비한 가이드를 선택 하면 됩니다. 빠른 유효성 검사를 위해 holographic 앵커를 사용할 수 있도록 [가이드를 고정](/dynamics365/mixed-reality/guides/hololens-app-anchor)해야 합니다. 그런 [다음 단계와 모델](/dynamics365/mixed-reality/guides/hololens-app-orientation)을 두어야 합니다.

>[!NOTE]
> HoloLens에서 PC 및 작성자에 로그인 하려면 **제작** 역할이 필요 합니다. 운영자 역할은 읽기 전용 이며 PC 앱에 대 한 액세스 권한이 없습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>가이드 운영

Holograms 준비 되 면 가이드 운영을 테스트할 수 있습니다. 
- **연산자 모드** 선택
- 가이드의 단계를 클릭 합니다.

가이드를 작동 하는 방법에 대 한 자세한 지침을 보려면 다음 리소스를 확인 하세요.

[Dynamics 365 Guides에서 가이드 운영 개요](/dynamics365/mixed-reality/guides/operator-overview)

[Dynamics 365 Guides에서 운영자로 단계 카드를 사용 하 여 시작](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사에 연결 된 배포-유지 관리](hololens2-corp-connected-maintain.md)
