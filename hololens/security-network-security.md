---
title: 네트워크 보안
description: 네트워크 보안
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, 네트워크, 네트워크 보안
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640494"
---
# <a name="network-security"></a>네트워크 보안

## <a name="network-protocols"></a>네트워크 프로토콜

구식 NetBIOS(Network Basic Input/Output System)는 과거에 종종 컴퓨터와 공유 폴더에 이름 확인을 제공하는 용도로 LAN 시나리오에서 널리 사용되었습니다. 하지만 시간이 지나면서 NetBIOS는 여러 공격에 취약한 것으로 판명되었으며 다른 보다 안전한 프로토콜을 선호하면서 관련성이 줄어들었습니다. 이 취약점 문제를 제거하기 위해 HoloLens 2에서 운영 체제의 NetBIOS 관련 코드를 제거했습니다.

TLS(전송 계층 보안) 프로토콜은 꾸준히 진화하고 있습니다. 이 영역에서 발견된 다양한 보안 악용을 방지하기 위해 컴퓨팅 업계는 더 최신 버전 및 보다 효과적인 버전으로 변화되었습니다. 모든 서버 배포에서 새 TLS 프로토콜 버전을 채택하는데 필요한 시간 때문에 다른 기본 프로토콜 버전의 클라이언트와 서버에서 전환 기간 동안 계속 통신할 수 있도록 하는 대체 메커니즘을 구현할 수 있습니다.

## <a name="secure-connectivity"></a>보안 연결 

Windows Defender 방화벽은 디바이스 연결 보안을 위한 중요한 기능을 제공합니다. HoloLens 2를 사용하면 방화벽이 항상 사용되고 있으며 이것을 프로그래밍 방식으로 또는 UI를 통해 사용하지 않도록 설정할 방법이 없습니다.

모바일 클라이언트에 대한 원격 액세스 및 연결 개인 정보는 [UWP VPN 플러그 인 플랫폼](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)을 통해 보장할 수 있습니다. 타사 VPN 공급자는 AppContainer 샌드박스 내에서 실행되는 WinRT API를 사용하여 고유한 플러그 인을 만들 수 있으며, 시스템 수준 드라이버 작성과 관련된 복잡성과 문제를 해결할 수 있습니다.
