---
title: 상용 환경에서 HoloLens 2 배포 계획
description: 인프라, azure active directory 및 모바일 장치 관리를 포함 하 여 엔터프라이즈 환경에서 HoloLens를 배포 하 고 관리 하기 위한 핵심 요구 사항에 대해 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961483"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>상용 환경에서 HoloLens 2 배포 계획

## <a name="overview"></a>개요
> [!NOTE]
> 이 개요는 IT 전문가가 조직 내에서 Microsoft HoloLens 2 장치를 배포 및 관리 하기 위한 고려 사항을 이해 하는 데 도움을 주기 위해 작성 되었습니다. 장치 최종 사용자는 시작 하기 위한 [기본 사항](hololens2-setup.md) 을 참조 하세요.

HoloLens 2는 조직이 강력 하 고 유연 하며 기본 제공 모바일 장치 및 앱 관리 기술을 제공 하는 Windows 10 Holographic에서 실행 됩니다. Windows 10 Holographic는 종단 간 장치 수명 주기 관리를 지원 하 여 회사에서 장치, 데이터 및 앱을 제어할 수 있게 합니다. HoloLens 2는 포괄적인 모바일 장치 관리 솔루션을 사용 하 여 장치 등록, 구성 및 응용 프로그램 관리에서 유지 관리 및 사용 중지에 이르기까지 표준 수명 주기 방식으로 쉽게 통합할 수 있습니다.

다음 단계는 조직 내에서 HoloLens 2를 도입 하는 과정을 안내 하는 데 도움이 될 수 있습니다.

| | |
|--|--|
| ![1단계](images/1green.png)| <br/> **[일반적인 배포 시나리오](hololens-requirements.md)**: 배포 시나리오를 이해 하 고 HoloLens 2 장치를 배포 하는 데 필요한 핵심 구성 요소를 살펴봅니다. |
| ![2단계](images/2green.png)| <br/> **[준비](#prepare)**: HoloLens 2에 필요한 인프라 essentials에 익숙해져야 합니다. |
| ![3단계](images/3green.png) | <br/> **[구성](#configure)**: 클라우드 기반 배포에 대 한 필수 구성 요소를 구성 하는 방법을 알아봅니다. |
| ![4단계](images/4green.png) | <br/> **[배포](#deploy)**: 장치를 배포 하 고 안전 하 고 효율적으로 응용 프로그램을 배포 하는 방법을 알아봅니다. |
| ![5단계](images/5green.png) | <br/> **[유지 관리](#maintain)**: HoloLens 2 장치의 상태를 적절 하 게 유지 하 고 회사 정책을 준수 하는지 확인 하는 데 필요한 사항에 대해 알아봅니다. |

## <a name="prepare"></a>준비

전체 HoloLens 2 기능 집합을 지 원하는 데 필요한 인프라 서비스에 대해 알아보세요. 

| 구성 요소 | Description |
|-----------|------------|
| [Azure AD](hololens-identity.md) | HoloLens 2에 대 한 id 및 액세스 관리를 제공 합니다.  |
| [모바일 디바이스 관리](hololens-mdm-configure.md)| 테 넌 트에 연결 된 HoloLens 2 장치를 관리 합니다.  |
| [Wi-fi 네트워크](hololens-commercial-infrastructure.md)| Wi-Fi를 사용할 수 있으며 장치를 인터넷에 연결할 수 있습니다.  |

## <a name="configure"></a>구성

조직의 Azure AD 테 넌 트 및 MDM에 HoloLens 2를 등록 하 고 구성 하기 위한 낮은 터치 솔루션으로 Intune 및 Autopilot를 사용 합니다.

| 구성 요소 | Description |
|-----------|------------|
| [자동 등록](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 초기 로그인 후 장치는 Azure AD에 자동으로 등록 되 고 MDM에 등록 됩니다.  |
| [응용 프로그램 라이선스](hololens2-cloud-connected-configure.md#application-licenses)| 사용자, 사용자 그룹 또는 장치 그룹에 적용할 수 있습니다.  |
| [Azure 사용자 및 그룹](hololens2-cloud-connected-configure.md#azure-users-and-groups) | HoloLens 2에 대 한 구성 및 라이선스를 할당 하는 데 도움이 됩니다.  |

## <a name="deploy"></a>배포

HoloLens 2 장치를 배포 하 고 구성의 유효성을 검사 합니다. 

| 구성 요소 | Description |
|-----------|------------|
| [등록 유효성 검사](hololens2-corp-connected-deploy.md#enrollment-validation) | 장치에서 설정 또는 Azure Portal에서 Azure AD가 조인 되었는지 확인 |
| [인증서 유효성 검사](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 설정을 확인 하 고 올바르게 배포 되었는지 확인 합니다. |
| [앱 설치 유효성 검사](hololens2-corp-connected-deploy.md#validate-lob-app-install) | 앱이 있고 HoloLens에서 작업 하 고 있는지 확인 합니다. 2 |

## <a name="maintain"></a>유지 관리

MDM 시스템 또는 Microsoft Store와 함께 비즈니스에 Windows 업데이트를 사용 하 여 HoloLens 2 및 앱을 업데이트 합니다.

| 구성 요소 | Description |
|-----------|------------|
| [HoloLens 업데이트 2](hololens-updates.md) | 비즈니스용 Windows 업데이트를 통해 필요에 따라 업데이트 구성 |
| [앱 업데이트](app-deploy-overview.md) | MDM 시스템 또는 Microsoft Store를 통해 구성
