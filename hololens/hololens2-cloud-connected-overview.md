---
title: Remote Assist 클라우드 연결 HoloLens 2 개요
description: Dynamics 365 Remote Assist 사용하여 클라우드 연결 네트워크를 통해 HoloLens 2 디바이스를 등록하는 방법을 알아봅니다.
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635129"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>배포 가이드 – Remote Assist 있는 클라우드 연결 HoloLens 2 - 개요

이 가이드는 IT 전문가가 Remote Assist Microsoft HoloLens 2개 디바이스를 계획하고 조직에 배포하는 데 도움이 됩니다. 다양한 HoloLens 2 사용 사례에서 조직에 개념 증명 배포를 위한 모델로 사용할 수 있습니다. 설정은 시나리오 [A: 클라우드 연결 디바이스에 배포와](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)비슷합니다. 

이 가이드에서는 디바이스를 디바이스 관리에 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 디바이스 설정 시 Remote Assist 즉시 사용할 수 있는지 확인하는 방법을 설명합니다. 이를 위해 설정하고 실행하는 데 필요한 인프라의 중요한 부분을 살펴보며 HoloLens 2 사용하여 대규모 배포를 달성합니다. 이 가이드에는 다른 디바이스 제한 또는 구성이 적용되지 않습니다. 그러나 완료한 후에는 이러한 옵션을 살펴보는 것이 좋습니다.

## <a name="prerequisites"></a>사전 요구 사항

HoloLens 2 배포하려면 다음 인프라가 있어야 합니다. 그렇지 않은 경우 Azure 및 Intune 설정이 이 가이드에 포함되어 있습니다.

이는 [시나리오 A: 클라우드 연결 디바이스에 배포와](/hololens/common-scenarios#scenario-a)유사한 설정으로, 다음을 포함하는 여러 개념 증명 배포에 적합한 옵션입니다.

- Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.
- MDM 자동 등록을 사용하여 Azure AD 조인 -- MDM(Intune) 관리
- 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
    - 디바이스당 단일 또는 여러 사용자가 지원됩니다.

:::image type="content" alt-text="클라우드 연결 시나리오" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Remote Assist 대해 알아보기

Remote Assist 통해 공동 유지 관리 및 복구, 원격 검사, 지식 공유 및 학습이 가능합니다. 다른 역할 및 위치에 있는 사람들을 연결하여 Remote Assist 사용하는 기술자는 Microsoft Teams 원격 협력자와 연결할 수 있습니다. 비디오, 스크린샷 및 주석을 결합하여 동일한 위치에 있지 않은 경우에도 실시간으로 문제를 해결할&#39;있습니다. 원격 협력자는 기술&#39;물리적 공간에 참조 이미지, 도형 및 기타 유용한 정보를 삽입할 수 있으므로 HoloLens 헤드업 및 실습을 진행하면서 도형을 참조할 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist 라이선스 및 요구 사항

- Azure AD 계정(구독 구매 및 라이선스 할당에 필요)
- [Remote Assist 구독(또는](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) [Remote Assist 평가판)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 사용자

- Remote Assist 라이선스
- 네트워크 연결

#### <a name="microsoft-teams-user"></a>Microsoft Teams 사용자

- [freemium](https://products.office.com/microsoft-teams/free)을 Microsoft Teams 또는 Teams.
- 네트워크 연결

이 [테넌트 간 시나리오를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)구현하려는 경우 Information Barriers 라이선스가 필요할 수 있습니다. Information Barrier 라이선스가 필요한지 확인하려면 [이 문서를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) 참조하세요.

## <a name="in-this-guide-you-will"></a>이 가이드에서는 다음을 수행합니다.

준비:

> [!div class="checklist"]
> - [HoloLens 2 디바이스의 인프라 필수 요소에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD에 대해 자세히 알아보고, Azure AD가&#39;없는 경우 설정합니다.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM에 대해 자세히 알아보고, 준비되지 않은 경우 intune을&#39;설정합니다.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Remote Assist 네트워킹 요구 사항에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#network)
> - [선택 사항: 조직 리소스에 연결하는 VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

구성:

> [!div class="checklist"]
> - [사용자 및 그룹을 만드는 방법](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD 내에서 자동 등록을 설정하는 방법](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [애플리케이션 라이선스를 할당하는 방법](hololens2-cloud-connected-configure.md#application-licenses)

배포:

> [!div class="checklist"]
> - [HoloLens 2 설정하고 등록의 유효성을 검사합니다.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Remote Assist 호출할 수 있는지 확인합니다.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

유지 관리:

> [!div class="checklist"]
> - [Microsoft Store 앱을 사용하여 Remote Assist 업데이트하는 방법입니다.](hololens2-cloud-connected-maintain.md#updates)
> - [지원 계획 수립](hololens2-cloud-connected-maintain.md#support-plan)
> - [개발 계획.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 준비](hololens2-cloud-connected-prepare.md)

