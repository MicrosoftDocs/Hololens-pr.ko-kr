---
title: 상용 환경에서 HoloLens 2 배포 계획
description: 인프라, Azure Active Directory 및 모바일 디바이스 관리를 포함하여 엔터프라이즈 환경에서 HoloLens 배포하고 관리하기 위한 핵심 요구 사항에 대해 알아봅니다.
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
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188902"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>상용 환경에서 HoloLens 2 배포 계획

## <a name="overview"></a>개요

> [!NOTE]
> 이 개요는 IT 전문가가 조직 내의 Microsoft HoloLens 2개 디바이스를 배포하고 관리하기 위한 고려 사항을 이해할 수 있도록 돕기 위한 것입니다. 디바이스 최종 사용자의 경우 [시작하기 위해 사용할 HoloLens 2 준비를 참조하세요.](hololens2-setup.md)

HoloLens 2 조직에 강력하고 유연한 기본 제공 모바일 디바이스 및 앱 관리 기술을 제공하는 Windows 10 Holographic 실행됩니다. Windows 10 Holographic 엔드 투 엔드 디바이스 수명 주기 관리를 지원하여 회사에서 디바이스, 데이터 및 앱을 제어할 수 있도록 합니다. HoloLens 2 디바이스 등록, 구성 및 애플리케이션 관리에서 포괄적인 모바일 디바이스 관리 솔루션을 사용하는 유지 관리 및 사용 중지에 이르기까지 표준 수명 주기 사례에 쉽게 통합할 수 있습니다.

다음 단계와 비디오는 조직 내에서 HoloLens 2 채택 프로세스를 안내하는 데 도움이 될 수 있습니다.

| &nbsp; | &nbsp; |
|--|--|
| ![1단계:](images/1green.png)| <br/> **[일반적인 배포 시나리오:](hololens-requirements.md)** 배포 시나리오를 이해하고 HoloLens 2 디바이스를 배포하는 데 필요한 핵심 구성 요소를 살펴봅니다. |
| ![2단계.](images/2green.png)| <br/> **[준비:](#prepare)** HoloLens 2 필요한 인프라 필수 요소에 익숙해집니다. |
| ![3단계.](images/3green.png) | <br/> **[구성:](#configure)** 클라우드 기반 배포를 위한 필수 구성 요소를 구성하는 방법을 알아봅니다. |
| ![4단계.](images/4green.png) | <br/> **[배포:](#deploy)** 디바이스를 배포하고 애플리케이션을 안전하고 효율적으로 배포하는 방법을 검색합니다. |
| ![5단계.](images/5green.png) | <br/> **[유지 관리:](#maintain)** HoloLens 2 디바이스의 상태를 올바르게 유지 관리하고 회사 정책을 준수하는 데 필요한 내용을 알아보세요. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>준비

전체 HoloLens 2 기능을 지원하는 데 필요한 필수 인프라 서비스에 대해 알아봅니다.

| 구성 요소 | 설명 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | HoloLens 2 대한 ID 및 액세스 관리를 제공합니다.  |
| [모바일 디바이스 관리](hololens-mdm-configure.md)| 테넌트 HoloLens 2 연결된 디바이스 관리  |
| [Wi-Fi 네트워크](hololens-commercial-infrastructure.md)| Wi-Fi 사용할 수 있으며 디바이스를 인터넷에 연결할 수 있습니다.  |

## <a name="configure"></a>구성

조직의 Azure AD 테넌트 및 MDM에 HoloLens 2 등록하고 구성하기 위한 저사양 솔루션으로 Intune 및 Autopilot을 사용합니다.

| 구성 요소 | 설명 |
|-----------|------------|
| [자동 등록](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 초기 로그인 후 디바이스가 Azure AD에 자동으로 등록되고 MDM에 등록됩니다.  |
| [애플리케이션 라이선스](hololens2-cloud-connected-configure.md#application-licenses)| 사용자, 사용자 그룹 또는 디바이스 그룹에 적용할 수 있습니다.  |
| [Azure 사용자 및 그룹](hololens2-cloud-connected-configure.md#azure-users-and-groups) | HoloLens 2 대한 구성 및 라이선스를 할당하는 데 도움이 됩니다.  |

## <a name="deploy"></a>배포

HoloLens 2 디바이스를 배포하고 해당 구성의 유효성을 검사합니다. 

| 구성 요소 | 설명 |
|-----------|------------|
| [등록 유효성 검사](hololens2-corp-connected-deploy.md#enrollment-validation) | 설정 또는 Azure Portal에서 디바이스에 Azure AD가 조인되어 있는지 확인합니다. |
| [인증서 유효성 검사](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 설정을 확인하고 올바르게 배포되었는지 확인합니다. |
| [앱 설치 유효성 검사](hololens2-corp-connected-deploy.md#validate-lob-app-install) | 앱이 있고 HoloLens 2 작업 중인지 확인합니다. |

## <a name="maintain"></a>유지 관리

MDM 시스템 또는 Microsoft Store 함께 비즈니스용 Windows 업데이트를 사용하여 HoloLens 2 및 앱을 업데이트된 상태로 유지합니다.

| 구성 요소 | 설명 |
|-----------|------------|
| [업데이트 HoloLens 2](hololens-updates.md) | 비즈니스용 Windows 업데이트를 통해 필요에 따라 업데이트 구성 |
| [앱 업데이트](app-deploy-overview.md) | MDM 시스템 또는 Microsoft Store 통해 구성
