---
title: HoloLens 보안 아키텍처
description: 보안 아키텍처
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, hololens 2, hololens2 보안, 보안 개요, 보안 아키텍처, 아키텍처, hololens 2 아키텍처
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034720"
---
# <a name="security-overview-and-architecture"></a>보안 개요 및 아키텍처

HoloLens 2 보안 아키텍처는 처음부터 레거시 보안 문제가 없도록 설계 및 엔지니어링되었으며, 공격 영역을 최소화했습니다. 이 새롭고 혁신적인 아키텍처는 운영 체제를 잠재적인 위협과 취약성으로부터 보호할 수 있는 메커니즘과 함께 안전한 스토리지 위치와 고급 보안 요소를 제공합니다.

HoloLens 2는 하드웨어, 소프트웨어, 네트워킹 및 서비스를 결합하여 사용자에게 최적의 환경을 제공하는 동시에 엔드투엔드 보안을 제공합니다. HoloLens 2를 사용하면 대부분의 보안 기능이 자동으로 켜지며, 운영 체제를 올바르게 설정하고 구성하는 데 필요한 노력이 최소화됩니다.

Windows HoloLens 2 및 운영 체제 아키텍처는 다음과 같은 혁신적인 보안 기능을 제공합니다.

  * **상태 분리 및 격리**: 이 새로운 아키텍처는 핵심 운영 체제가 신뢰할 수 있는 상태로 부팅하는 데 필요한 것과 같은 HoloLens 2 운영 체제의 중요한 부분이 변경되지 않도록 보호합니다. 격리 기술은 샌드박스 영역에서 신뢰할 수 없는 앱을 제한하여 시스템 보안에 영향을 주지 않도록 하는 데 사용됩니다. 전체 운영 체제는 안전한 섹션으로 분할되고 각 섹션은 다양한 보안 기술의 조합으로 보호됩니다.
  
  * **데이터 보호**: 디바이스 분실 또는 도난 발생 시 HoloLens 2에서 데이터의 BitLocker 암호화를 사용하여 권한이 없는 애플리케이션에서 민감한 정보를 읽지 못하도록 합니다. 
  
  * **암호 없는 운영 체제**: 이전의 암호 기반 운영 체제는 사용자를 피싱 위험에 실수로 노출하고 계정을 위험에 노출되도록 하는 경우가 많았습니다. Windows Holographic for Business는 MSA 및 Azure AD 로그인에 암호를 사용하지 않으며 Windows Hello™ 및 FIDO2 로그인을 사용하여 사용자 ID 보호를 강화합니다. 
  
    > [!NOTE]
    > FIDO2 지원을 받으려면 디바이스가 19041 이상의 빌드에서 작동해야 합니다. 

  * **네트워크 보안**: HoloLens 2는 향상된 프로토콜과 기본 설정을 통해 사용자에게 강화된 네트워크 보안을 제공합니다.
