---
title: 라이선스 요구 사항
description: 모바일 장치 관리, HoloLens 및 원격 지원에 필요한 모든 라이선스 요구 사항 및 지침을 최신으로 유지하세요.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283969"
---
# 라이선스 요구 사항

## MDM(모바일 장치 관리) 라이선스 지침

HoloLens 장치 관리 계획을 수립할 때 Azure AD와 MDM이 필요합니다. AD(활성 디렉터)는 HoloLens 장치를 관리 하는 데 사용할 수 없습니다.
Intune 이외의 MDM을 사용하려는 경우 [Azure Active Directory 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)가 필요합니다.
Intune을 MDM으로 사용할 계획이라면 Intune 라이선스가 포함된 [제품군 목록](https://docs.microsoft.com/intune/fundamentals/licenses)을 읽어 보세요. **Azure AD는 이러한 제품군의 대부분에 포함되어 있다는 점을 기억하세요.**

## 시나리오 및 제품에 필요한 라이선스 식별

### HoloLens(1세대) 라이선스 요구 사항

HoloLens(1세대) 장치를 비즈니스용 Windows Holographic으로 업그레이드해야 할 수 있습니다. (업그레이드해야 하는지 여부를 결정하기 위해 [HoloLens 상업용 기능](holoLens-commercial-features.md#feature-comparison-between-editions)을 참조하세요.)

 업그레이드가 필요한 경우 다음을 수행해야 합니다.

- HoloLens Enterprise 라이선스 XML 파일 획득
- HoloLens에 XML 파일 적용 [프로비저닝 패키지](hololens-provisioning.md) 또는 [모바일 장치 관리자](https://docs.microsoft.com/intune/configuration/holographic-upgrade)를 통해 이 작업을 수행할 수 있습니다.

### 원격 지원 라이선스 요구 사항

[요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) 설명서에서 확인할 수 있는 필수 라이선스 및 장치가 있는지 확인합니다.

1. [원격 지원 라이선스](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. 또는 [원격 지원 평가판을 사용해 보세요](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure AD(Azure Active Directory) 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

**[이 교차 테넌트 시나리오](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** 를 구현하려면 정보 장벽 라이선스가 필요할 수 있습니다. 정보 장벽 라이선스가 필요한지 여부를 확인하려면 [이 문서](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)를 참조하세요.

### 라이선스 요구 사항 가이드

[업데이트된 라이선스 및 장치 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)을 확인합니다.

1. [Azure AD(Azure Active Directory) 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [가이드](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
