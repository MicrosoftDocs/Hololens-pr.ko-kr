---
title: 라이선스 요구 사항
description: 모바일 장치 관리, HoloLens 및 Remote Assist에 필요한 모든 라이선스 요구 사항 및 지침을 최신으로 유지하세요.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640284"
---
# <a name="license-requirements"></a>라이선스 요구 사항

## <a name="hololens-2-device-managed"></a>HoloLens 2 디바이스(관리됨)

[Azure AD 계정](/azure/active-directory/)

> [!IMPORTANT]
> AD(Active Directory)는 HoloLens 디바이스를 관리하는 데 사용할 수 없습니다.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) 또는 다른 MDM.
- [HoloLens 2용 Windows Autopilot](hololens2-autopilot.md) - IT 관리자와 최종 사용자 모두를 위한 프로비전 환경을 간소화합니다. IT 관리자는 HoloLens 2 정책을 미리 구성할 수 있으며, 처음 부팅될 때 디바이스는 최종 사용자의 조작 없이 비즈니스 준비 상태로 배포됩니다. 

  > [!NOTE]
  > Windows Autopilot을 사용하려면 로우 터치 Autopilot 흐름 및 디바이스 배포를 위해 먼저 [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) 및 [자동 등록](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)을 구성해야 합니다. 

### <a name="business-use-case"></a>비즈니스 사용 사례: 

- [배포 시나리오 A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - 개념 증명 또는 파일럿 배포.

- [배포 시나리오 B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - 대규모로 배포.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 디바이스 전용(관리되지 않음)

MSA(Microsoft 계정) 또는 로컬 계정을 사용하는 경우 이러한 계정에 추가 라이선스가 필요하지 않습니다.

[로컬 계정](/windows/security/identity-protection/access-control/local-accounts)

- 이 계정은 WCD(Windows Configuration Designer)를 사용하여 미리 [프로비전](hololens-provisioning.md#provisioning-package-hololens-wizard)되어야 합니다.

[MSA(Microsoft 계정)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> 이러한 계정을 사용하는 디바이스는 여러 사용자를 지원하지 않습니다.

### <a name="business-use-case"></a>비즈니스 사용 사례: 

- [배포 시나리오 C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - 오프라인 또는 보안 배포.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 라이선스 및 요구 사항

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Admin

- Azure AD 계정(구독을 구매하고 라이선스를 할당하는 데 필요)
- [Remote Assist 구독](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)(또는 [Remote Assist 평가판](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 사용자

- Azure AD 계정

- Remote Assist 라이선스 

  > [!NOTE]
  > Microsoft Teams는 Remote Assist와 함께 번들로 제공됩니다.

- 네트워크 연결

#### <a name="microsoft-teams-user"></a>Microsoft Teams 사용자

- Azure AD 계정

- Microsoft Teams 또는 [Teams Freemium](https://products.office.com/microsoft-teams/free).

- 네트워크 연결

이 [교차 테넌트 시나리오](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)를 구현할 계획이라면 정보 장벽 라이선스가 필요할 수 있습니다. 정보 장벽 라이선스가 필요한지 확인하려면 [이 문서](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)를 참조하세요.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Admin

- Azure AD 계정(구독을 구매하고 라이선스를 할당하는 데 필요)
- Dynamics 365 [가이드 구독 또는 평가판](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>가이드 작성자

1. Azure AD 계정
1. [Dynamics 365 Guides 라이선스](/dynamics365/mixed-reality/guides/requirements)
1. PC 또는 HoloLens에 설치된 Dynamics 365 Guides 애플리케이션
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/)(Analytics 대시보드를 보는 데 사용됨)
1. 작성자 역할(가이드 생성)
1. 네트워크 연결

#### <a name="guides-user"></a>가이드 사용자

1. Azure AD 계정
1. [Dynamics 365 Guides 라이선스](/dynamics365/mixed-reality/guides/requirements)
1. HoloLens에 설치된 Dynamics 365 Guides 앱
1. 운영자 역할(가이드 테스트 또는 사용)
1. 네트워크 연결
