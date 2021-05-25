---
title: 원격 지원에 대 한 클라우드 연결 HoloLens 2 개요
description: Dynamics 365 원격 지원을 사용 하 여 클라우드 연결 네트워크를 통해 HoloLens 2 장치를 등록 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397654"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>배포 가이드-클라우드 연결 HoloLens 2 (원격 지원 포함)-개요

이 가이드를 통해 IT 전문가는 Dynamics 365 원격 지원을 사용 하도록 준비 된 상태에서 조직에 연결 된 장치 클라우드가 있는 전체 목표를 사용 하 여 조직에 Microsoft HoloLens 2 장치를 계획 하 고 배포할 수 있습니다. 이는 다양 한 HoloLens 2 사용 사례에서 조직의 개념 증명 배포를 위한 모델 역할을 한다는 점에 유의 하세요.

이 가이드에서는 장치를 장치 관리에 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설치 시 원격 지원을 즉시 사용할 수 있는지 확인 하는 방법을 설명 합니다. 이렇게 하려면 HoloLens 2를 사용 하 여 대규모로 배포를 달성 하는 데 필요한 인프라의 중요 한 부분을 살펴보겠습니다.

[![클라우드 연결 시나리오 ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>이 가이드의 내용

이 가이드에는 HoloLens 장치에서 조직 내에 원격 지원을 설정 하는 구체적인 목표가 있습니다. 이 목표를 달성 하는 데 필요한 필요성에 대해 설명 합니다. 이러한 목표에 초점을 유지 하기 위해이 배포를 최적화 하거나를 구성 하는 데 필요한 항목을 줄이기 위해 특정 준비 및 구성이 미리 선택 됩니다. 이러한 선택 항목에 대 한 알림이 표시 되며 비즈니스 요구에 따라 배포를 사용자 지정할 수 있습니다.

[시나리오 a: 클라우드 연결 장치에 배포](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)하는 것과 유사한 설정입니다 .이는 다음과 같은 개념 증명 배포의 여러 가지 유용한 옵션입니다.

- 일반적으로 인터넷 및 클라우드 서비스에 대 한 Wi-Fi 네트워크가 완전히 열립니다.
- MDM 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리
- 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
  - 지원 되는 장치 당 단일 또는 여러 사용자
- 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 다양한 수준의 디바이스 잠금 구성이 적용됩니다.



이 가이드에는 다른 디바이스 제한 또는 구성이 적용되지 않습니다. 그러나 완료 후 해당 옵션을 살펴보는 것이 좋습니다.

## <a name="learn-about-remote-assist"></a>Remote Assist 대해 알아보기

Remote Assist 통해 공동 유지 관리 및 복구, 원격 검사, 지식 공유 및 학습이 가능합니다. 다른 역할 및 위치에 있는 사람들을 연결하면 Remote Assist 사용하는 기술자가 Microsoft Teams의 원격 협력자와 연결할 수 있습니다. 비디오, 스크린샷 및 주석을 결합하여 동일한 위치에 있지 않은 경우에도 실시간으로 문제를 해결할&#39;있습니다. 원격 협력자는 HoloLens에서 헤드업 및 실습을 진행하면서 도형을 참조할 수 있도록 기술자가 물리적 공간을&#39;참조 이미지, 회로도 및 기타 유용한 정보를 삽입할 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>이 가이드에서는 다음을 수행합니다.

준비:

> [!div class="checklist"]
> - [HoloLens 2 디바이스의 인프라 필수 요소에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD에 대해 자세히 알아보고, Azure AD가 없으면 설정해야&#39;.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM에 대해 자세히 알아보고, 준비되지 않은 경우 intune을&#39;설정합니다.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Remote Assist 네트워킹 요구 사항에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#network)
> - [선택 사항: 조직 리소스에 연결하는 VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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
> - [지원 계획 수립.](hololens2-cloud-connected-maintain.md#support-plan)
> - [개발 계획.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포-준비](hololens2-cloud-connected-prepare.md)

