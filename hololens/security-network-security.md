---
title: 네트워크 보안
description: 네트워크 보안
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, Hololens, 네트워크, 네트워크 보안
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009426"
---
# 네트워크 보안

## 네트워크 프로토콜

오래된 NetBIOS(네트워크 기본 입출력 시스템)는 과거에는 종종 컴퓨터와 공유 폴더에 이름 확인을 제공하는 용도로 주로 LAN 시나리오에서 사용되었습니다. 하지만 시간이 지나면서 NetBIOS가 여러 공격에 취약한 것으로 입증되고 다른 더 보안성 있는 프로토콜을 선호하면서 이것의 타당성이 줄었습니다. 이 취약점 문제를 제거하기 위해 HoloLens 2에서 운영 체제의 NetBIOS 관련 코드를 제거했습니다.

TLS(전송 계층 보안) 프로토콜은 꾸준히 진화하고 있습니다. 이 영역에서 발견된 다양한 보안 악용을 방지하기 위해 컴퓨팅 업계는 더 최신 버전 및 보다 효과적인 버전으로 변화되었습니다. 모든 서버 배포에서 새 TLS 프로토콜 버전을 채택하는데 필요한 시간 때문에 다른 기본 프로토콜 버전의 클라이언트와 서버에서 전환 기간 동안 계속 통신할 수 있도록 하는 대체 메커니즘을 구현할 수 있습니다.

## 보안 연결 

Windows Defender 방화벽은 장치 연결 보안을 위한 중요한 기능을 제공합니다. HoloLens 2를 사용하면 방화벽이 항상 사용되고 있으며 이것을 프로그래밍 방식으로 또는 UI를 통해 사용하지 않도록 설정할 방법이 없습니다.

모바일 클라이언트에 대한 원격 액세스 및 연결 개인정보 보호는 [UWP VPN 플러그인 플랫폼](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)을 통해 보장될 수 있습니다. 타사 VPN 공급자는 AppContainer 샌드박스 내에서 실행되는 WinRT API를 사용하여 고유한 플러그인을 만들 수 있으며, 시스템 수준 드라이버 작성에 자주 관련되는 복잡성과 문제를 해결할 수 있습니다.
