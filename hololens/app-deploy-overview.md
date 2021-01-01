---
title: 개요 - 앱 관리
description: 앱, 관리, 앱 관리
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
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252669"
---
# 앱 관리: 개요

**MDM(모바일**장치 관리), 비즈니스용 **Microsoft Store, Microsoft Store의** **** 네 가지 경로에 앱을 배포하거나 프로비저닝을 통해 앱을 설치할 **수 있습니다.**

## MDM(모바일 장치 관리)

MDM 솔루션을 사용하면 IT 의사 결정권자 및 관리자가 사용자 그룹을 위해 스토어를 통해 사내, 업무용 앱을 개인적으로 자동 설치(푸시)할 수 있습니다. HoloLens 장치는 응용 프로그램 관리를 위해 Microsoft Endpoint Manager(Intune)와 [가장 잘 작동합니다.](app-deploy-intune.md) 또한 Intune은 사용자가 회사 포털에서 다운로드 가능한 환경을 통해 IT 관리 앱에 대한 세분화된 제어를 제공합니다.

> [!NOTE]
> 다음 지침은 Intune을 사용하여 응용 프로그램을 관리하려는 사용자를 위한 것입니다. 응용 프로그램 및 장치 관리에 Intune을 사용하는 것이 좋습니다.

MDM(모바일 장치 관리)은 해당됩니다.

* MDM 배포 + 회사 포털
* 업무(비공용) 앱
* 회사 포털을 통해 사용 가능한 응용 프로그램 수동 설치
* MDM 정책을 통한 관리자 푸시
* MDM을 통한 자동 업데이트

## 비즈니스용 Microsoft Store

비즈니스용 [Microsoft Store는](app-deploy-store-business.md) 비즈니스의 IT 의사 결정권자 및 관리자가 무료 및 유료 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다. IT 관리자는 Microsoft Store 앱 및 개인 기간 업무(기간 업무) 앱을 하나의 인벤토리에서 관리할 수 있으며, 필요한 경우 라이선스를 할당하고 다시 사용할 수 있습니다. 자세한 내용은 비즈니스용 Microsoft Store를 사용하기 위한 사전 준비 [사이트를 방문하세요.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)

비즈니스용 Microsoft Store는 다음에 해당됩니다.

* 공용 또는 비즈니스용 앱
* MDM 연결로 필수 응용 프로그램 자동 설치
* 사용자가 수동으로 앱을 다운로드합니다.
* 자동 업데이트

## Microsoft Store 앱

Microsoft Store는 비즈니스의 IT 의사 결정권자 및 관리자가 공용 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다.

이 Microsoft Store는 해당됩니다.

* 공용 앱만
* 사용자가 수동으로 앱을 다운로드합니다.
* 인터넷에 연결된 경우 자동 업데이트

자세한 내용은 [Holographic Store 앱을 방문하세요.](https://docs.microsoft.com/hololens/holographic-store-apps)

## 프로비저닝 패키지를 통해 설치

[프로비저닝 패키지를](app-deploy-provisioning-package.md) 사용하면 사용자 지정 또는 업무용 앱을 설치할 수 있으며, IT 프로비저닝 및 관리자는 USB를 통해 로컬 디바이스에 앱을 빠르게 설치할 수 있습니다. 이 설치는 인터넷에 연결하지 않고 ID 유형에 대해 수행될 수 있습니다.

프로비저닝 패키지를 통해 설치하는 것은 다음에 해당됩니다.

* 업무(LINE OF BUSINESS) / 자체 개발(비공용) 앱
* 공용 앱(오프라인 설치 관리자를 사용할 수 있는 경우)
* USB 테스트용 로드만
* 자동 업데이트 없음(프로비저닝 패키지를 통한 수동 업데이트 필요)

## 앱 설치 관리자를 통해 HoloLens 2에 앱 설치

앱 [설치](app-deploy-app-installer.md) 관리자 사용자는 로컬 장치에 앱을 설치하거나 HoloLens의 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유하는 간단한 환경을 경험할 수 있습니다. 개발자 모드를 사용하도록 설정하거나 디바이스 포털을 사용하지 않고도 이 기능을 사용할 수 있습니다. 이는 완전히 구축된 앱을 배포하는 간단한 방법입니다. HoloLens를 사용하여 다른 사용자에게 앱을 데모하거나 앱을 쉽게 배포할지와 관계없이 이 방법을 사용하면 됩니다.

앱 설치 관리자를 통해 설치하는 것은 다음에 해당됩니다.

* 업무(LINE OF BUSINESS) / 자체 개발(비공용) 앱
* 테스트용 로드만
* 개발자 모드 또는 디바이스 포털이 필요하지 않습니다.
* 최종 사용자가 쉽게 설치할 수 있습니다.
