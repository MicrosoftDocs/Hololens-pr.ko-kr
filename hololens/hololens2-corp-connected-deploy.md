---
title: 배포 가이드 – Dynamics 365 Guides 통해 회사 연결 HoloLens 2 - 배포
description: Dynamics 365 Guides 사용하여 회사 연결된 네트워크를 통해 HoloLens 2 디바이스의 배포를 설정하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile 장치 관리
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
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033492"
---
# <a name="deploy---corporate-connected-guide"></a>배포 - 회사 연결 가이드

각 배포의 중요한 부분은 최종 사용자에게 원활한 환경을 보장하기 위해 직접 테스트하기 전에 배포를 올바르게 설정하는 것입니다.

MDM을 통해 Wi-Fi 인증서를 배포하기 때문에 처음에는 HoloLens 설정하고 열려 있는 Wi-Fi 네트워크 또는 인증서가 필요하지 않은 네트워크에 디바이스를 등록해야 합니다. HoloLens OOBE 및 등록을 완료하면 디바이스는 이전에 구성된 네트워크 인증서와 LOB를 수신하고 디바이스에서 두 인증서가 수신되었는지 확인할 수 있습니다.

그런 다음 테스트 가이드를 작성하고 운영할 수 있다는 것을 확인할 수 있습니다.

## <a name="enrollment-validation"></a>등록 유효성 검사

이제 모든 것이 Azure AD 및 MDM 등록에 대해 올바르게 구성되었으며 나머지는 이제 맞춤이어야 합니다. Wi-Fi 연결과 HoloLens 디바이스와 이전에 구성된 Azure AD 사용자 계정 중 하나가 필요합니다.

디바이스가 현재 공장 설정 상태에 있지 않은 경우 이제 [디바이스를 다시 반사하는](/hololens/hololens-recovery#clean-reflash-the-device)것이 좋습니다.

1. 디바이스가 OOBE에 있으면 상호 작용을 시작하고 프롬프트를 따라야 합니다.

2. Wi-Fi에 가입하기 위해 인증서가 필요하지 않은 개방형 Wi-Fi 네트워크에 커넥트. 이렇게 하면 초기 설정 후 디바이스가 조직의 Wi-Fi 사용할 인증서를 다운로드할 수 있습니다.

3. 중요한 프롬프트는 **이 HoloLens 소유할 Who** 묻는 메시지가 표시될 때입니다. **내 직장 또는 학교 소유를** 선택하고 Azure AD 계정 자격 증명을 입력합니다.

4. 등록에 성공하면 PIN을 설정하라는 메시지가 표시됩니다. 이 PIN은 이 사용자에 대해 이 디바이스에 고유합니다. 또한 아이리스 스캔, 음성 데이터 및 원격 분석 설정을 묻는 메시지가 표시되며, 마지막으로 시작 메뉴를 열고 OOBE를 완료하는 방법을 배울 수 있습니다.

5. Mixed Reality Home에 도착하면 방금 배운 **시작 제스처를** 사용하여 시작 메뉴 엽니다.

6. **설정** 앱을 선택하고 **시스템** 을 선택합니다. 표시되는 첫 번째 정보는 디바이스 이름이며, HoloLens 2 디바이스의 경우 &quot; HOLOLENS, &quot; 6자 문자열이 있습니다.

7. 이 이름을 기록해 둡다.

    ![HoloLens 2 설정 화면.](./images/hololens2-settings-about.jpg)

8. 디바이스가 Azure AD에 성공적으로 조인되었는지 확인합니다. 두 가지 방법이 있습니다.

    1.  설정 앱입니다. **설정**   ->  **계정회사 또는 학교 액세스를** 선택합니다. 이 화면에서 nameofAAD&#39;Azure AD에 연결됨을 확인하여 성공적으로 등록되었는지 확인할 수 &quot; 있습니다. 에 의해 *yourusername@nameofAAD.onmicrosoft.com* 연결됨 그러면 디바이스가 조직&#39;Azure AD에 가입되어 있는지 확인합니다.

    1. [Azure Portal](https://portal.azure.com/#home) Azure Active Directory   ->  **디바이스**  ->  **모든 디바이스로** 이동하여 디바이스 이름을 검색합니다. 조인 유형에서 'Azure AD 조인됨'으로 표시됩니다.
        ![Azure AD에서 조인 유형을 확인합니다.](./images/hololens2-devices-all-devices.png)

9. 디바이스가 MDM에 등록되어 있는지 확인합니다. 두 가지 방법이 있습니다.

    1. **설정** 에서   ->  **계정회사 또는 학교 액세스를** 선택합니다. 이 화면에서 nameofAAD&#39;Azure AD에 연결됨을 확인하여 성공적으로 등록되었는지 확인할 수 &quot; 있습니다. 에 의해 *yourusername@nameofAAD.onmicrosoft.com* 연결됨 이 액세스 작업 또는 학교 계정에서 &quot; 이름에 연결됨AAD&#39;Azure AD를 선택합니다. 연결한 yourusername@nameofAAD.onmicrosoft.com &quot; 후 **정보** 단추를 선택합니다.

    1. [관리 센터 를 Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) 로그인하고  **디바이스를**  선택한  **다음, 모든 디바이스를** 선택합니다. 여기에서 HoloLens 디바이스&#39;이름을 검색할 수 있습니다. Intune에 나열된 HoloLens 볼 수 있어야 합니다.

        ![Azure AD의 Intune에서 관리되는지 확인합니다.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>인증서 유효성 검사 Wi-Fi

이제 디바이스에서 Wi-Fi 인증서를 받았어야 합니다. 수행할 수 있는 가장 간단한 유효성 검사는 인증서를 받은&#39;Wi-Fi 연결에 연결을 시도하는 것입니다. **설정** 앱을 열고 **네트워크 &amp; 인터넷**  ->  **Wi-Fi로 이동하여 Wi-fi** 연결을 선택합니다. 연결되면 Microsoft Edge 앱을 열고 웹 사이트로 이동할 수 있도록 확인합니다.

디바이스에서 인증서를 받았는지 확인하려면 [인증서 관리자](/hololens/certificate-manager)를 사용하면 됩니다.

## <a name="validate-lob-app-install"></a>LOB 앱 설치 유효성 검사

관리되는 앱의 설치 진행 상황을 확인하려면 앱이 설치되어 있는지 확인하거나 설정 확인합니다. LOB 앱을 그룹에 필요한 설치로 구성하면 할당된 그룹의 사용자로 HoloLens 등록하면 앱이 자동으로 HoloLens 다운로드됩니다.

시작 메뉴 열고 **모든 앱** 선택합니다. 앱 수에 따라 **페이지 위로** 또는 **페이지 아래로** 단추를 사용해야 할 수 있습니다.

디바이스에서 앱 설치의 유효성을 검사하려면 **계정회사** 또는 학교 액세스를 설정 계정을  ->    ->  선택하고 **정보** 단추를 선택한 다음 아래로 스크롤하여 MDM에서 디바이스에 적용된 다양한 구성 및 앱을 확인할 수 있습니다.

Intune에서 설치의 유효성을 검사하려면 [MEM 포털](https://endpoint.microsoft.com/#home)  ->  **앱** -> 모든 **앱**  -> *TheNameOfYourApp*  ->  **디바이스 설치 상태** 페이지로 이동합니다.

자세한 내용: [HoloLens Intune 앱 배포](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 Guides 유효성 검사

HoloLens, 작성 및 운영에 대한 가이드 앱 모드가 있습니다. 가이드를 운영하기 전에 작성을 완료해야 합니다.

### <a name="authoring-the-guide"></a>가이드 작성

이 빠른 유효성 검사를 위해 많은 작업을 수행할 필요가 없습니다. PC에서 준비한 가이드를 선택하기만 하면 됩니다. 빠른 유효성 검사를 위해 [홀로그램 앵커를](/dynamics365/mixed-reality/guides/hololens-app-anchor)사용할 수 있도록 가이드를 고정해야 합니다. 그런 다음 [단계 및 모델을 배치해야](/dynamics365/mixed-reality/guides/hololens-app-orientation)합니다.

>[!NOTE]
> PC에 로그인하고 HoloLens 작성하려면 **Authoring** 역할이 필요합니다. 운영자 역할은 읽기 전용이며 PC 앱에 액세스할 수 없습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>가이드 운영

홀로그램이 배치되면 가이드의 작동을 테스트할 수 있습니다. 
- **연산자 모드** 선택
- 가이드의 단계를 클릭합니다.

가이드를 운영하는 방법에 대한 자세한 지침은 다음 리소스를 확인하세요.

[Dynamics 365 Guides 가이드 운영 개요](/dynamics365/mixed-reality/guides/operator-overview)

[에서 단계 카드를 연산자로 Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 유지 관리](hololens2-corp-connected-maintain.md)
