---
title: 개요-앱 관리
description: 앱, 관리, 앱 관리
keywords: HoloLens, 사용자, 계정, 앱, 응용 프로그램 관리
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: e73a56e5a2fcef14e85f5f552e264dd8d796cc8f
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009456"
---
# 앱 관리: 개요

4 가지 경로, 즉 **MDM (모바일 디바이스 관리)**, Microsoft store **비즈니스**에디션, **microsoft store**또는 **프로 비전**을 통해 설치 하 여 앱을 배포할 수 있습니다. 

## MDM(모바일 장치 관리)

MDM 솔루션을 사용 하면 IT 의사 결정권자와 관리자가 개인적으로 사내 앱을 자동으로 설치 (푸시) 하거나 사용자 그룹을 위해 스토어를 통해 앱을 구매할 수 있습니다. HoloLens 장치는 [응용 프로그램 관리](app-deploy-intune.md)를 위해 Microsoft Intune (Endpoint Manager 관리자)에서 가장 잘 작동 합니다. Intune은 또한 사용자가 회사 포털 다운로드 가능 환경을 통해 관리 되는 앱에 대 한 세부적인 제어 기능을 제공 합니다.

> [!NOTE] 
> 다음 지침은 Intune을 사용 하 여 응용 프로그램을 관리 하려는 사용자를 위한 것입니다. Microsoft는 응용 프로그램 및 장치 관리에 Intune을 사용 하는 것이 좋습니다.
    
다음에 해당 하는 MDM (모바일 장치 관리)이 적용 됩니다. 
* MDM 배포 + 회사 포털 
* 앱 라인 (비 공용)
* 회사 포털을 통해 사용 가능한 응용 프로그램의 수동 설치
* 관리자 푸시 MDM 정책
* MDM을 통한 자동 업데이트

## 비즈니스용 Microsoft Store

[비즈니스용 Microsoft Store](app-deploy-store-business.md) 는 비즈니스에서 무료 및 유료 앱을 찾고, 얻고, 관리 하 고, 배포 하는 의사 결정권자와 관리자를 제공 합니다. IT 관리자는 Microsoft Store 앱 및 전용 LOB(기간 업무) 앱을 하나의 인벤토리에서 관리하고 필요에 따라 라이선스를 할당하고 다시 사용할 수 있습니다. 자세한 내용은 [Microsoft 비즈니스용 스토어를 사용 하기 위한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)를 참조 하세요.
    
비즈니스용 Microsoft Store는 다음에 적용 됩니다. 
* 비즈니스 앱 공개 또는 줄
* MDM 연결을 통해 필수 응용 프로그램의 자동 설치
* 사용자가 앱을 수동으로 다운로드
* 자동 업데이트

## Microsoft Store 앱

Microsoft Store는 비즈니스에서 공용 앱을 찾고, 가져오고, 관리 하 고, 배포 하는 의사 결정권자와 관리자를 제공 합니다.
    
이 Microsoft Store는 다음에 적용 됩니다. 
* 공용 앱만
* 사용자가 앱을 수동으로 다운로드
* 인터넷에 연결 된 경우 자동 업데이트

자세한 내용은 [홀로그램 스토어 앱](https://docs.microsoft.com/hololens/holographic-store-apps)을 참조 하세요.

## 프로비저닝 패키지를 통해 설치

[배포 패키지](app-deploy-provisioning-package.md) 를 사용 하 여 사용자 지정 또는 lob 앱을 설치할 수 있으며, IT 전문가와 관리자는 USB를 통해 로컬 장치에 앱을 빠르게 설치할 수 있습니다. 이 작업은 인터넷에 연결 되지 않고 모든 id 유형에 사용할 수 있습니다.
    
다음과 같은 경우에는 프로비저닝 패키지를 통해 설치할 수 있습니다. 
* 앱 라인 (비 공용)
* 공용 앱 (오프 라인 설치 관리자를 사용할 수 있는 경우)
* USB 쪽만 로드
* 자동 업데이트 없음 (프로비저닝 패키지를 통해 수동 업데이트 필요)
