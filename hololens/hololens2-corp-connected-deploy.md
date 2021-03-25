---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 배포
description: Dynamics 365 가이드를 통해 회사 연결 네트워크를 통해 HoloLens 2 장치의 배포를 설정하는 방법을 설명합니다.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448601"
---
# <a name="deploy---corporate-connected-guide"></a>배포 - 회사 연결 가이드

각 배포에서 중요한 부분은 최종 사용자에게 원활한 환경을 제공하도록 직접 테스트하기 전에 배포가 제대로 설정되었는지를 보장하는 것입니다.

MDM을 통해 Wi-Fi 인증서를 배포하기 때문에 초기에 HoloLens를 설정하고 열려 있는 Wi-Fi 네트워크 또는 인증서가 필요하지 않은 네트워크에 장치를 등록해야 합니다. HoloLens가 OOBE를 완료하고 등록하면 장치가 이전에 구성된 네트워크 인증서 및 LOB를 받으며 디바이스에서 받은 두 인증서의 유효성을 검사할 수 있습니다.

그런 다음 테스트 가이드를 작성 및 운영할 수 있습니다.

## <a name="enrollment-validation"></a>등록 유효성 검사

이제 모든 것이 Azure AD 및 MDM 등록에 맞게 제대로 구성되면 나머지는 스냅인이 됩니다. 연결 및 Wi-Fi 및 이전에 구성한 Azure AD 사용자 계정 중 하나가 필요합니다.

장치가 현재 공장 설정 상태로 있지 않은 경우 이제 장치를 리플래시하는 [것이 좋습니다.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. 장치가 OOBE에 있는 경우 상호 작용을 시작하고 프롬프트에 따라야 합니다.

2. 인증서가 wi-fi에 Wi-Fi 없는 열려 있는 개방형 네트워크 네트워크에 연결합니다. 이렇게 하면 장치가 초기 설정 후 조직의 조직에서 사용할 인증서를 Wi-Fi 수 있습니다.

3. 이 **HoloLens를** 누가 소유하고 있나요?를 묻는 메시지가 표시될 때 중요한 메시지가 표시될 것입니다. 내 **직장 또는 학교** 소유를 선택하고 Azure AD 계정 자격 증명을 입력합니다.

4. 등록에 성공하면 PIN을 설정하라는 메시지가 표시될 것입니다. 이 PIN은 이 사용자에 대해 이 장치에 고유합니다. 또한 홍채 검사, 음성 데이터 및 원격 분석 설정에 대한 메시지가 표시되고 마지막으로 시작 메뉴를 열고 OOBE를 완료하는 방법을 배울 수 있습니다.

5. 혼합 현실 홈에 들어오면 방금 학습한 시작 제스처를 사용하여 시작 **메뉴를** 열 수 있습니다.

6. 설정 **앱을 선택하고** 시스템 **을 선택합니다.** 첫 번째로 볼 수 있는 정보는 장치 이름입니다. HoloLens 2 디바이스의 경우 HOLOLENS- 그 다음에 6개의 문자 문자열이 &quot; &quot; 표시됩니다.

7. 이 이름을 메모해 두면 됩니다.

    ![HoloLens 2 설정 화면](./images/hololens2-settings-about.jpg)

8. 디바이스가 Azure AD에 성공적으로 가입된지 확인합니다. 두 가지 방법이 있습니다.

    1.  설정 앱. **설정에서** **계정 직장**또는 학교 액세스  ->  **를 선택합니다.** 이 화면에서 Azure &quot; AD의 nameofAAD에 연결&#39;등록 여부를 확인할 수 있습니다. 에 *의해 yourusername@nameofAAD.onmicrosoft.com.* 그러면 디바이스가 Azure AD의 조직에&#39;확인합니다.

    1. [Azure Portal](https://portal.azure.com/#home). Azure **Active Directory**  ->  **장치**  ->  **모든 장치로 이동하여**장치 이름을 검색합니다. 참가 유형에서 'Azure AD 가입'으로 표시 됩니다.
        ![Azure AD에서 가입 유형 확인](./images/hololens2-devices-all-devices.png)

9. 장치가 MDM에 등록된지 확인합니다. 두 가지 방법이 있습니다.

    1. 설정에서 **계정 액세스 직장**또는 학교 ****  ->  **를 선택합니다.** 이 화면에서 Azure &quot; AD의 nameofAAD에 연결&#39;등록 여부를 확인할 수 있습니다. 에 *의해 yourusername@nameofAAD.onmicrosoft.com.* 이 액세스 직장 또는 학교 계정에서 &quot; Azure AD의 nameofAAD&#39;선택합니다. 연결 yourusername@nameofAAD.onmicrosoft.com 정보 &quot; **단추를** 선택합니다.

    1. [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com/#home). 로그인하고 장치 다음 **모든** **장치를 선택합니다.** 여기에서 HoloLens 장치 이름과&#39;수 있습니다. Intune에 나열된 HoloLens를 볼 수 있습니다.

        ![Azure AD에서 Intune에서 관리 확인](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi 인증서 유효성 검사

지금까지 디바이스는 인증서를 Wi-Fi 합니다. 가장 간단한 유효성 검사는 인증서를 받은 Wi-Fi 연결에&#39;시도하는 것입니다. 설정 앱을 **열고** 네트워크 ** &amp; **인터넷  ->  **Wi-Fi로 이동하고** Wi-Fi 연결을 선택합니다. 연결되면 Microsoft Edge 앱을 열고 웹 사이트로 이동할 수 있는지 확인하세요.

장치에서 인증서를 받았는지 확인하려면 인증서 관리자 [를 사용할 수 있습니다.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>LOB 앱 설치 유효성 검사

관리되는 앱의 설치 진행률을 확인하려면 앱이 설치되어 있는지 확인하거나 설정을 확인합니다. LOB 앱을 그룹에 대한 필수 설치로 구성하면 할당된 그룹의 사용자에 HoloLens를 등록한 후 앱이 HoloLens에 자동으로 다운로드됩니다.

시작 메뉴를 열고 모든 **앱을 선택합니다.** 앱 수에 따라 페이지 업 또는 페이지 아래로 **** 단추를 **사용해야** 할 수 있습니다.

디바이스에 앱 설치의 유효성을 검사하려면 설정 **** 계정 직장 또는 학교에 액세스하여 계정을 선택한 다음 정보 단추를 선택하고 아래로 스크롤하여  ->  ****  ->  **** MDM에서 **** 디바이스에 적용되는 다양한 구성 및 앱을 확인할 수 있습니다.

Intune에서 설치의 유효성을 검사하려면 [MEM 포털](https://endpoint.microsoft.com/#home)앱 -> 모든 앱  ->  **** ****  -> *TheNameOfYourApp*장치 설치 상태  ->  **페이지로** 이동합니다.

자세한 내용은 [다음을 참조하세요. HoloLens용 Intune 앱 배포](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 가이드 유효성 검사

HoloLens, 제작 및 운영에 대한 가이드 앱 모드가 있습니다. 가이드를 작동하기 전에 가이드 작성을 완료해야 합니다.

### <a name="authoring-the-guide"></a>가이드 작성

이 빠른 유효성 검사에는 많은 작업을 할 필요가 없습니다. PC에서 준비한 가이드를 선택하기만 합니다. 홀로그램 [앵커를](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)사용할 수 있는 빠른 유효성 검사를 위해 가이드 를 고정해야 합니다. 그런 다음 단계와 [모델을 으로 설정해야 합니다.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> PC에 로그인하고 HoloLens를 작성하려면 제작 역할이 필요합니다. **** Operator 역할은 읽기 전용으로 PC 앱에 액세스할 수 없습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>가이드 운영

홀로그램이 설치된 후 가이드 작동을 테스트할 수 있습니다. 
- 연산자 **모드 선택**
- 가이드의 단계를 클릭합니다.

가이드를 운영하는 방법에 대한 자세한 지침은 다음 리소스를 참조하세요.

[Dynamics 365 가이드의 가이드 운영 개요](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Dynamics 365 가이드에서 단계 카드의 방향을 안내합니다.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 유지 관리](hololens2-corp-connected-maintain.md)
