---
title: 라이선스 요구 사항
description: ''
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
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956764"
---
# 라이선스 요구 사항

## MDM(모바일 장치 관리) 라이선스 지침

HoloLens 장치 관리 계획을 수립할 때 Azure AD와 MDM이 필요합니다. AD(활성 디렉터)는 HoloLens 장치를 관리 하는 데 사용할 수 없습니다.
Intune 이외의 MDM을 사용하려는 경우 [Azure Active Directory 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)가 필요합니다.
Intune을 MDM으로 사용하는 경우 [다음](https://docs.microsoft.com/intune/fundamentals/licenses)은 Intune 라이선스가 포함된 제품군의 목록입니다. **Azure AD는 이러한 제품군의 대부분에 포함되어 있다는 점을 기억하세요.**

## 시나리오 및 제품에 필요한 라이선스 식별

### HoloLens(1세대) 라이선스 요구 사항

HoloLens(1세대) 장치를 비즈니스용 Windows Holographic으로 업그레이드해야 할 수 있습니다. (업그레이드해야 하는지 여부를 결정하기 위해 [HoloLens 상업용 기능](holoLens-commercial-features.md#feature-comparison-between-editions)을 참조하세요.)

 업그레이드가 필요한 경우 다음을 수행해야 합니다.

- HoloLens Enterprise 라이선스 XML 파일 획득
- HoloLens에 XML 파일 적용 [프로비저닝 패키지](hololens-provisioning.md) 또는 [모바일 장치 관리자](https://docs.microsoft.com/intune/configuration/holographic-upgrade)를 통해 이 작업을 수행할 수 있습니다.

### 원격 지원 라이선스 요구 사항

필수 라이선싱 및 장치를 사용하고 있는지 확인합니다. 업데이트된 라이선스 및 제품 요구 사항은 [여기](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)에서 찾을 수 있습니다.

1. [원격 지원 라이선스](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. 또는 [원격 지원 평가판을 사용해 보세요](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure AD(Azure Active Directory) 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

**[이 교차 테넌트 시나리오](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** 를 구현하려면 정보 장벽 라이선스가 필요할 수 있습니다. 정보 장벽 라이선스가 필요한지 여부를 확인하려면 [이 문서](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)를 참조하세요.

### 라이선스 요구 사항 가이드

업데이트된 라이선스 및 장치 요구 사항은 [여기](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)에서 찾을 수 있습니다.

1. [Azure AD(Azure Active Directory) 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [가이드](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
