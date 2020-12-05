---
title: 배포 가이드 - 원격 지원이 있는 클라우드 연결 HoloLens 2 - 개요
description: 클라우드 연결 네트워크를 통해 HoloLens 장치 등록
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196356"
---
# 배포 가이드 - 원격 지원이 있는 클라우드 연결 HoloLens 2 - 개요

이 가이드는 IT 전문가가 Dynamics 365 원격 도우미를 사용하여 조직에 클라우드로 연결되는 전체적인 목표를 사용하여 Microsoft HoloLens 2 장치를 계획하고 조직에 배포하는 데 도움이 됩니다. 이 모델은 다양한 HoloLens 2 사용 사례에서 조직에 개념 증명 배포를 위한 모델로 사용할 수 있습니다.

이 가이드에서는 디바이스를 장치 관리에 등록하고, 필요한 경우 라이선스를 적용하고, 최종 사용자가 장치 설정 시 원격 지원을 즉시 사용할 수 있는지 검증하는 방법을 다를 것입니다. 이를 위해 HoloLens 2를 통해 대규모로 배포를 구현하는 설정 및 실행에 필요한 인프라의 중요한 요소에 대해 설명합니다.

## 이 가이드의 설명

이 가이드는 HoloLens 디바이스에서 조직 내에서 원격 지원을 설정하는 구체적인 목표를 습니다. 이 목표를 달성하는 데 필요한 필요성을 다루게 될 것입니다. 이 목표에 초점을 맞추기 위해 특정 준비 및 구성은 이 배포에 최적화하거나 구성에 필요한 항목을 줄이기 위해 미리 선택됩니다. 이러한 선택 사항을 알리고 비즈니스 요구에 따라 배포를 사용자 지정할 수 있습니다.

이 설정은 시나리오 [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)클라우드 연결 장치에 배포와 유사한 설정으로, 다음을 포함할 많은 개념 증명 배포에 좋은 옵션입니다.

- Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.
- MDM 자동 등록을 사용하여 Azure AD 가입 -- MDM(Intune) 관리
- 사용자가 자신의 회사 계정(AAD)으로 로그인합니다.
  - 지원되는 장치당 사용자 한명 또는 여러명
- 장치 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 완전히 열기에서 단일 앱 키오스크까지 적용됩니다.

![클라우드 연결 시나리오](./images/cloud-connected-deployment-chart.png)

이 가이드에서는 추가 장치 제한 또는 구성이 적용되지는 않습니다. 그러나 완료 후 이러한 옵션을 살펴보는 것이 좋습니다.

## 원격 지원에 대해 자세히

원격 도우미를 사용하면 공동 유지 관리 및 복구, 원격 검사뿐만 아니라 지식 공유 및 교육을 사용할 수 있습니다. 원격 지원을 사용하여 다른 역할 및 위치에 있는 사람을 연결하면 기술자가 Microsoft Teams의 원격 공동 작업자와 연결할 수 있습니다. 비디오, 스크린샷 및 주석을 결합하여 동일한 위치에 있지 않은 경우에도 실시간으로 문제를&#39;수 있습니다. 원격 공동 작업자는 HoloLens에서 머리를 업고 핸즈&#39;동안 도형을 참조할 수 있도록 기술자가 실제 공간을 참조할 수 있도록 참조 이미지, schematics 및 기타 유용한 정보를 삽입할 수 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 이 가이드에서는 다음을 할 수 있습니다.

준비:

> [!div class="checklist"]
> - [HoloLens 2 디바이스의 인프라 필수 요소에 대해 자세히 알아보고,](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [AAD에 대해 자세히 알아보고 설정하지 않은 경우&#39;합니다.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [ID 관리 및 AAD 계정을 가장 잘 설정하는 방법에 대해 자세히 알아보습니다.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM에 대해 자세히 알아보고, 아직 준비되지 않은 경우 Intune을&#39;수 있습니다.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [원격 지원의 네트워킹 요구 사항에 대해 자세히 알아보습니다.](hololens2-cloud-connected-prepare.md#network)
> - [선택 사항: 조직 리소스에 연결하기 위한 VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

구성:

> [!div class="checklist"]
> - [사용자 및 그룹을 만드는 방법](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [AAD 내에서 자동 등록을 설정하는 방법](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [응용 프로그램 라이선스를 할당하는 방법](hololens2-cloud-connected-configure.md#application-licenses)

배포:

> [!div class="checklist"]
> - [HoloLens 2를 설정하고 등록의 유효성을 검사합니다.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [원격 지원 전화를 걸 수 있는지 검사합니다.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

유지 관리:

> [!div class="checklist"]
> - [Microsoft Store 앱을 사용하여 원격 도우미를 업데이트하는 방법](hololens2-cloud-connected-maintain.md#updates)
> - [지원 계획 수립](hololens2-cloud-connected-maintain.md#support-plan)
> - [개발 계획.](hololens2-cloud-connected-maintain.md#development-plan)

## 다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 준비](hololens2-cloud-connected-prepare.md)

