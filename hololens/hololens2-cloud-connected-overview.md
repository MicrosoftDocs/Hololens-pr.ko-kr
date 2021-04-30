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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309111"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>배포 가이드-클라우드 연결 HoloLens 2 (원격 지원 포함)-개요

이 가이드를 통해 IT 전문가는 Dynamics 365 원격 지원을 사용 하도록 준비 된 상태에서 조직에 연결 된 장치 클라우드가 있는 전체 목표를 사용 하 여 조직에 Microsoft HoloLens 2 장치를 계획 하 고 배포할 수 있습니다. 이는 다양 한 HoloLens 2 사용 사례에서 조직의 개념 증명 배포를 위한 모델 역할을 한다는 점에 유의 하세요.

이 가이드에서는 장치를 장치 관리에 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설치 시 원격 지원을 즉시 사용할 수 있는지 확인 하는 방법을 설명 합니다. 이렇게 하려면 HoloLens 2를 사용 하 여 대규모로 배포를 달성 하는 데 필요한 인프라의 중요 한 부분을 살펴보겠습니다.

![클라우드 연결 배너](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a>이 가이드의 내용

이 가이드에는 HoloLens 장치에서 조직 내에 원격 지원을 설정 하는 구체적인 목표가 있습니다. 이 목표를 달성 하는 데 필요한 필요성에 대해 설명 합니다. 이러한 목표에 초점을 유지 하기 위해이 배포를 최적화 하거나를 구성 하는 데 필요한 항목을 줄이기 위해 특정 준비 및 구성이 미리 선택 됩니다. 이러한 선택 항목에 대 한 알림이 표시 되며 비즈니스 요구에 따라 배포를 사용자 지정할 수 있습니다.

[시나리오 a: 클라우드 연결 장치에 배포](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)하는 것과 유사한 설정입니다 .이는 다음과 같은 개념 증명 배포의 여러 가지 유용한 옵션입니다.

- 일반적으로 인터넷 및 클라우드 서비스에 대 한 Wi-Fi 네트워크가 완전히 열립니다.
- MDM 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리
- 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
  - 지원 되는 장치 당 단일 또는 여러 사용자
- 다양 한 수준의 장치 잠금 구성은 특정 사용 사례에 따라 완전히 열린 앱에서 단일 앱 키오스크까지 적용 됩니다.

![클라우드 연결 시나리오](./images/cloud-connected-guide-diagram.png)

이 가이드에서는 다른 장치 제한 사항 또는 구성이 적용 되지 않지만, 완료 한 후에는 이러한 옵션을 탐색 하는 것이 좋습니다.

## <a name="learn-about-remote-assist"></a>원격 지원에 대 한 자세한 정보

원격 지원을 통해 공동 유지 관리 및 복구, 원격 검사 뿐만 아니라 기술 자료 공유 및 교육을 수행할 수 있습니다. 여러 역할 및 위치에 있는 사용자를 연결 하 여 원격 지원을 사용 하는 기술자는 Microsoft 팀의 원격 협력자와 연결할 수 있습니다. 동일한 위치에서 t를&#39;하지 않는 경우에도 비디오, 스크린샷 및 주석을 결합 하 여 실시간으로 문제를 해결할 수 있습니다. 원격 협력자는 참조 이미지, 계통도 및 기타 유용한 정보를 삽입할 수 있습니다. 기술자는이에 대 한 작업을 수행 하는 동시에, HoloLens를 사용 하 여 작업 하는 동안 계통도를 참조할 수 있도록&#39;의 실제 공간을 제공 합니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>이 가이드에서는 다음을 수행합니다.

준비:

> [!div class="checklist"]
> - [HoloLens 2 장치에 대 한 인프라 essentials에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD에 대해 자세히 알아보고,&#39;없는 경우 하나를 설정 합니다.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Id 관리 및 Azure AD 계정을 최적으로 설정 하는 방법에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM에 대해 자세히 알아보고 아직 준비 된&#39;없는 경우 Intune을 사용 하 여 설정 합니다.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [원격 지원의 네트워킹 요구 사항에 대해 알아봅니다.](hololens2-cloud-connected-prepare.md#network)
> - [필요에 따라 조직 리소스에 연결할 VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

구성:

> [!div class="checklist"]
> - [사용자 및 그룹을 만드는 방법](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD 내에서 자동 등록을 설정 하는 방법입니다.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [응용 프로그램 라이선스를 할당 하는 방법입니다.](hololens2-cloud-connected-configure.md#application-licenses)

배포:

> [!div class="checklist"]
> - [HoloLens 2를 설정 하 고 등록의 유효성을 검사 합니다.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [유효성 검사 원격 지원 전화를 할 수 있습니다.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

유지 관리:

> [!div class="checklist"]
> - [Microsoft Store 앱을 사용 하 여 원격 지원을 업데이트 하는 방법입니다.](hololens2-cloud-connected-maintain.md#updates)
> - [지원 계획을 만드는 중입니다.](hololens2-cloud-connected-maintain.md#support-plan)
> - [개발 계획.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포-준비](hololens2-cloud-connected-prepare.md)

