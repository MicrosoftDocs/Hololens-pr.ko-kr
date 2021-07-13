---
title: 개요 - 앱 관리
description: 모바일 디바이스 관리, 비즈니스용 Microsoft 스토어 및 패키지 프로비저닝을 사용하여 혼합 현실 앱 관리에 대한 개요를 시작합니다.
keywords: HoloLens, 사용자, 계정, 앱, 애플리케이션 관리,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635554"
---
# <a name="app-management-overview"></a>앱 관리: 개요

**MDM(모바일 장치 관리), 비즈니스용 Microsoft Store,** **Microsoft Store** 또는 **프로비저닝을** 통해 설치하여 앱을 배포할 수 있습니다.

## <a name="mobile-device-management-mdm"></a>MDM(모바일 디바이스 관리)

MDM 솔루션을 사용하면 IT 의사 결정자와 관리자가 사내, 사업장 앱을 비공개로 자동 설치(푸시)하거나 사용자 그룹을 위해 스토어를 통해 앱을 구매할 수 있습니다. HoloLens 디바이스는 [애플리케이션 관리를](app-deploy-intune.md)위해 Microsoft Endpoint Manager(Intune)에서 가장 잘 작동합니다. 또한 Intune은 회사 포털 다운로드 가능한 환경을 통해 IT 관리 앱에 대한 세밀한 제어를 사용자에게 제공합니다.

> [!NOTE]
> 다음 지침은 Intune을 사용하여 애플리케이션을 관리하려는 사용자를 위한 것입니다. 애플리케이션 및 디바이스 관리에 Intune을 사용하는 것이 좋습니다.

MDM(모바일 장치 관리)은 다음을 위해 적용됩니다.

* MDM 배포 + 회사 포털
* 사업장(비공용) 앱
* 회사 포털 통해 사용 가능한 애플리케이션 수동 설치
* MDM 정책을 통한 관리자 푸시
* MDM을 통한 자동 업데이트

## <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store

[이 비즈니스용 Microsoft Store](app-deploy-store-business.md) 비즈니스의 IT 의사 결정자와 관리자가 무료 및 유료 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다. IT 관리자는 하나의 인벤토리에서 Microsoft Store 앱 및 프라이빗 사업장 앱을 관리하고 필요에 따라 라이선스를 할당하고 다시 사용할 수 있습니다. 자세한 내용은 [비즈니스용 Microsoft Store 사용하기 위한 필수 구성요약을](/microsoft-store/prerequisites-microsoft-store-for-business)방문하세요.

비즈니스용 Microsoft Store 적용할 수 있는 내용은 다음과 같습니다.

* 퍼블릭 또는 사업장 앱
* MDM 연결을 통해 필수 애플리케이션 자동 설치
* 사용자가 수동으로 앱 다운로드
* 자동 업데이트

## <a name="microsoft-store-apps"></a>Microsoft Store 앱

이 Microsoft Store 기업에서 IT 의사 결정자와 관리자에게 퍼블릭 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다.

이 Microsoft Store 적용할 수 있는 내용은 다음과 같습니다.

* 퍼블릭 앱만
* 사용자가 수동으로 앱 다운로드
* 인터넷에 연결된 경우 자동 업데이트

자세한 내용은 [Holographic Store 앱을 방문하세요.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>프로비전 패키지를 통해 설치

[프로비전 패키지를](app-deploy-provisioning-package.md) 사용하면 사용자 지정 또는 사업장 앱을 설치할 수 있어 IT 담당자와 관리자가 USB를 통해 로컬 디바이스에 앱을 빠르게 설치할 수 있습니다. 이 설치는 인터넷에 연결하지 않고 모든 ID 유형에 대해 수행할 수 있습니다.

프로비전 패키지를 통한 설치는 다음을 위해 적용됩니다.

* 사업장/자체 개발(비공용) 앱
* 공용 앱(오프라인 설치 관리자를 사용할 수 있는 경우)
* USB 쪽 로드만
* 자동 업데이트 없음(프로비전 패키지를 통한 수동 업데이트 필요)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>앱 설치 관리자 통해 HoloLens 2 앱 설치

[앱 설치 관리자](app-deploy-app-installer.md) 사용하면 로컬 디바이스에 앱을 설치하거나 HoloLens 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유하는 데 간단한 환경을 사용할 수 있습니다. 개발자 모드를 사용하도록 설정하거나 장치 포털 사용하지 않고도 이 작업을 수행할 수 있습니다. 완전히 빌드된 앱을 배포하는 간단한 방법입니다. 단순히 HoloLens 사용하여 앱을 다른 사용자에게 시연하려는 경우 또는 앱을 배포하려는 경우 이 방법이 쉽게 작동합니다.

앱 설치 관리자 통해 설치하는 것은 다음을 위해 적용됩니다.

* 사업장/자체 개발(비공용) 앱
* 사이드로드 전용
* 개발자 모드 또는 디바이스 포털이 필요하지 않음
* 최종 사용자가 쉽게 설치할 수 있습니다.
