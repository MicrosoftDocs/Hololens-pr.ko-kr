---
title: 개요-앱 관리
description: 모바일 장치 관리, 비즈니스용 Microsoft 스토어 및 프로 비전 패키지를 사용 하 여 혼합 현실 앱 관리의 개요를 시작 하세요.
keywords: HoloLens, 사용자, 계정, 앱, 응용 프로그램 관리,
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309280"
---
# <a name="app-management-overview"></a>앱 관리: 개요

**MDM (모바일 장치 관리)**, **Microsoft Store 비즈니스용** **Microsoft Store** 또는 **프로 비전** 을 통해 설치 하 여 앱을 배포할 수 있습니다.

## <a name="mobile-device-management-mdm"></a>MDM(모바일 디바이스 관리)

MDM 솔루션을 사용 하 여 IT 의사 결정권자와 관리자는 사내 또는 기간 업무 앱을 개인적으로 자동 설치 (푸시) 하거나 사용자 그룹에 대해 스토어를 통해 앱을 구매할 수 있습니다. HoloLens 장치는 [응용 프로그램 관리](app-deploy-intune.md)를 위해 Microsoft Endpoint Manager (Intune)와 가장 잘 작동 합니다. 또한 Intune은 사용자가 회사 포털 다운로드 가능한 환경을 통해 IT 관리 앱에 대 한 세부적인 제어를 제공 합니다.

> [!NOTE]
> 다음 지침은 Intune을 사용 하 여 응용 프로그램을 관리 하려는 사용자를 위한 것입니다. 응용 프로그램 및 장치 관리를 위해 Intune을 사용 하는 것이 좋습니다.

MDM (모바일 장치 관리)은 다음에 적용 됩니다.

* MDM 배포 + 회사 포털
* Lob (기간 업무) 앱
* 회사 포털를 통해 사용 가능한 응용 프로그램 수동 설치
* MDM 정책을 통한 관리자 푸시
* MDM을 통한 자동 업데이트

## <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store

[비즈니스용 Microsoft Store](app-deploy-store-business.md) 은 IT 의사 결정권자와 관리자에 게 무료 및 유료 앱을 찾고, 관리 하 고, 배포할 수 있는 IT 의사 결정권자 및 관리자를 제공 합니다. IT 관리자는 하나의 인벤토리에 있는 Microsoft Store 앱 및 개인 lob (기간 업무) 앱을 관리 하 고 필요에 따라 라이선스를 할당 하 고 다시 사용할 수 있습니다. 자세한 내용은 [Microsoft Store For Business를 사용 하기 위한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)를 참조 하세요.

비즈니스용 Microsoft Store은 다음에 적용 됩니다.

* 공용 또는 lob (기간 업무) 앱
* MDM 연결을 통해 필수 응용 프로그램 자동 설치
* 사용자가 앱을 수동으로 다운로드
* 자동 업데이트

## <a name="microsoft-store-apps"></a>Microsoft 스토어 앱

Microsoft Store는 IT 의사 결정권자와 관리자에 게 공용 앱을 찾고, 관리 하 고, 배포 하는 관리자를 제공 합니다.

이 Microsoft Store는 다음에 적용할 수 있습니다.

* 공용 앱 전용
* 사용자가 앱을 수동으로 다운로드
* 인터넷에 연결 된 경우 자동 업데이트

자세한 내용은 [Holographic 스토어 앱](https://docs.microsoft.com/hololens/holographic-store-apps)을 참조 하세요.

## <a name="install-via-provisioning-packages"></a>프로 비전 패키지를 통해 설치

[프로 비전 패키지](app-deploy-provisioning-package.md) 를 사용 하면 사용자 지정 또는 Lob (기간 업무) 앱을 설치 하 여 IT 전문가와 관리자가 USB를 통해 로컬 장치에 앱을 신속 하 게 설치할 수 있습니다. 이 설치는 인터넷에 연결 하지 않고 모든 id 유형에 대해 수행할 수 있습니다.

프로 비전 패키지를 통한 설치는 다음에 적용 됩니다.

* Lob (기간 업무)/자체 개발 (비 공용) 앱
* 공용 앱 (오프 라인 설치 관리자를 사용할 수 있는 경우)
* USB 테스트용 로드만
* 자동 업데이트 없음 (프로 비전 패키지를 통한 수동 업데이트 필요)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>앱 설치 관리자를 통해 HoloLens 2에 앱 설치

[앱 설치 관리자](app-deploy-app-installer.md) 사용자를 사용 하면 로컬 장치에 앱을 설치 하거나 HoloLens의 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유 하는 데 간단한 환경을 사용할 수 있습니다. 개발자 모드를 사용 하도록 설정 하거나 장치 포털을 사용 하지 않고도이 작업을 수행할 수 있습니다. 이 방법은 완전히 빌드된 앱을 배포 하는 간단한 방법입니다. HoloLens를 사용 하는 다른 사용자에 게 앱을 시연 하 고 싶습니다. 또는 앱을 배포 하려는 경우에 관계 없이이 방법이 쉽게 작동 합니다.

앱 설치 관리자를 통한 설치는 다음에 적용할 수 있습니다.

* Lob (기간 업무)/자체 개발 (비 공용) 앱
* 테스트용 로드만
* 개발자 모드 또는 장치 포털이 필요 하지 않음
* 최종 사용자가 쉽게 설치할 수 있습니다.
