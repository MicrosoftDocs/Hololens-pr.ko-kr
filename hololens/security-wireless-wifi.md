---
title: 무선 및 Wi-Fi
description: 무선 및 Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, HoloLens, 무선, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865773"
---
# 무선 및 Wi-Fi

HoloLens 2 무선 LAN 연결은 다음과 같은 놀라운 범위의 최신 Wi-Fi 보안 표준을 지원합니다.
  * WPA2(Wi-Fi 보호 액세스 2)  
  * TEAP(확장할 수 있는 터널 인증 프로토콜)  
  * OWE(편의적 무선 암호화)

차세대 엔터프라이즈 네트워크 인증 TEAP를 통해 단일 트랜잭션으로 여러 자격 증명을 안전하게 연결할 수 있습니다.  따라서 관리자는 동일한 인증 트랜잭션을 수행하는 동안 컴퓨터와 사용자 모두에 대해 유효한 ID를 요구하는 보안 태세를 적용할 수 있습니다.

HoloLens 2는 최신 무선 및 Wi-Fi 프로토콜을 통해 고객을 최대한으로 지원합니다. HoloLens 2 라디오는 프리미엄 라디오 환경을 제공하는 Qualcomm WCN3990 솔루션입니다. Wi-Fi는 802.11ac/n으로 지원됩니다. 주파수 범위는 사용자가 구성할 수 없으며 사용 국가에 따라 다릅니다. 미국에서 Wi-Fi는 2.4GHz(1~11) 채널과 5GHz(36~64, 100~165) 채널을 사용합니다. 사용자와 장치 모두 특정 주파수에 대한 허용/거부 목록을 만들 수 없습니다. Bluetooth SIC Core 5.0에는 Wi-Fi와 공유되지 않는 Bluetooth 전용 2.4GHz 안테나가 탑재되어 있습니다. HoloLens 2 소프트웨어 스택은 HID, HOGP, A2DP, GATT 등의 여러 프로토콜과 프로필을 지원합니다. 

IT 관리자는 다음 작업을 수행할 수 있습니다. 
  * [Bluetooth 액세스](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용 또는 제한
  * [로컬 Bluetooth 장치 이름](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename) 설정

  * [장치를 검색할 수 있도록](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode) 허용
  * [Wi-Fi 연결](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 허용/허용 안 함 
  * [MDM 서버를 설치한 네트워크 외부에서의 Wi-Fi 연결](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)을 허용 또는 허용 안 함
