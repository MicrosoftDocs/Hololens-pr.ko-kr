---
title: 네트워크에 HoloLens 연결
description: HoloLens로 인터넷에 연결하는 방법 및 장치의 IP 주소를 식별하는 방법에 대한 지침입니다.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, 무선, 인터넷, IP, IP 주소
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883152"
---
# 네트워크에 HoloLens 연결

HoloLens에서 대부분의 작업을 수행하려면 네트워크에 연결되어 있어야 합니다. 이 가이드는 다음을 지원합니다.

- Wi-Fi 또는 USB-C에서 이더넷을 사용하여(HoloLens 2에만 해당) 네트워크에 연결
- Wi-Fi를 사용하지 않도록 설정하고 다시 사용하도록 설정

[오프라인으로 HoloLens 사용](hololens-offline.md)에 대한 자세한 내용을 알아보세요.

## 처음 연결

HoloLens를 처음 사용할 때 Wi-Fi 네트워크에 연결하는 방법에 대한 안내를 받습니다. 설치하는 동안 Wi-Fi에 연결하는 데 문제가 있는 경우, 네트워크가 공개, 암호로 보호된 네트워크 또는 종속 포털 네트워크인지 확인합니다. 네트워크에 연결할 때 인증서를 사용할 필요가 없는지 확인합니다. 설정 후, 다른 유형의 Wi-Fi 네트워크에 연결할 수 있습니다.

## 설치 후 Wi-Fi에 연결

1. **Start gesture** and select **Settings**을 실행합니다. 설정 앱이 자동 배치됩니다.
1. **네트워크 및 인터넷** > **Wi-Fi**를 선택합니다. Wi-Fi가 켜져 있는지 확인합니다. 네트워크에 표시되지 않으면 목록을 아래로 스크롤합니다.
1. 네트워크를 선택하고 **연결**을 선택합니다.
1. 네트워크 암호를 묻는 메시지가 표시되면 입력하고 **다음**을 선택합니다.

HoloLens에는 802.11ac 가능, 2x2 Wi-Fi 무선 송수신 장치가 포함되어 있습니다. HoloLens를 Wi-Fi 네트워크에 연결하는 것은 Windows 10 데스크톱 또는 모바일 장치를 Wi-Fi 네트워크에 연결하는 것과 유사합니다.

![HoloLens Wi-Fi 설정](./images/wifi-hololens-600px.jpg)

**시작** 메뉴에서 Wi-Fi 상태를 확인하여 Wi-Fi 네트워크에 연결되어 있는지 확인할 수도 있습니다.

1. **시작** 메뉴를 엽니다.
1. **시작** 메뉴의 왼쪽 위에 있는 Wi-Fi 상태를 확인합니다. Wi-Fi의 상태와 연결된 네트워크의 SSID가 표시됩니다.

## Wi-Fi에 대한 연결 문제 해결

Wi-Fi에 연결하는 데 문제가 있는 경우 [Wi-Fi에 연결할 수 없음](./hololens-faq.md#i-cant-connect-to-wi-fi)을 참조하세요.

장치에서 엔터프라이즈 또는 조직 계정에 로그인하는 경우 IT 관리자가 정책을 구성한다면 MDM(모바일 장치 관리) 정책을 적용할 수도 있습니다.

## VPN
VPN 연결을 사용 하면 회사 네트워크와 인터넷에 더 안전하게 연결하고 액세스 하는데 도움이 됩니다. HoloLens 2는 기본 제공 VPN 클라이언트와 UWP(Universal Windows Platform) VPN 플러그 인을 지원합니다. 

지원되는 기본 제공 VPN 프로토콜:
- IKEv2
- L2TP
- PPTP

기본 제공 VPN 클라이언트를 인증 하는데 인증서를 사용하는 경우에는 필수 클라이언트 인증서를 사용자 인증서 저장소에 추가 해야 합니다. 타사 VPN 플러그 인이 HoloLens 2를 지원 하는지 확인 하려면 스토어로 이동하여 VPN 앱을 찾고, HoloLens가 지원 되는 장치에 표시 되는지 여부를 확인하고 시스템 요구 사항 페이지에서 ARM 또는 ARM64 아키텍처를 지원합니다. HoloLens는 타사 VPN 유니버설 Windows 플랫폼 응용 프로그램만 지원 합니다.

VPN은 기본적으로 사용 하도록 설정 되지 않지만 앱**설정**을 열고 **네트워크 및 인터넷 > VPN**으로 이동하여 수동으로 설정할 수 있습니다. [설정/허용VPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)를 통해 MDM으로 VPN을 관리하고 [Vpnv2-csp 정책](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)을 통해 설정할 수 있습니다.
[가이드를](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide) 사용하여 [VPN을 구성하는 방법](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)에 대해 자세히 알아보세요.  

## HoloLens(1세대)에서 Wi-Fi 사용 안 함

### HoloLens에서 설정 앱 사용

1. **시작** 메뉴를 엽니다.
1. **시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다. **설정** 앱이 자동 배치됩니다.
1. **네트워크 및 인터넷**을 선택합니다.
1. Wi-Fi 슬라이더 스위치를 선택하여 **끄기** 위치로 이동합니다. 이는 Wi-Fi 무선 송수신 장치의 RF 구성 요소를 끄고 HoloLens에서 모든 Wi-Fi 기능을 사용하지 않도록 설정합니다.

    > [!WARNING]
    > Wi-Fi 무선 송수신 장치를 사용하지 않도록 설정하면 HoloLens에서 자동으로 [공백을](hololens-spaces.md)로드할 수 없게 됩니다.

1. 슬라이더 스위치를 **켜기** 위치로 이동하여 Wi-Fi 무선 송수신 장치를 켜고 Microsoft HoloLens에서 Wi-Fi 기능을 복원합니다. 선택한 Wi-Fi 무선 송수신 장치 상태(**켜기** 또는 **끄기**)는 다시 부팅하는 동안 유지됩니다.

## Wi-Fi 네트워크에서 HoloLens의 IP 주소 식별

### 설정 앱 사용

1. **시작** 메뉴를 엽니다.
1. **시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다. **설정** 앱이 자동 배치됩니다.
1. **네트워크 및 인터넷**을 선택합니다.
1. 사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성**을 선택합니다.

    ![Wi-Fi 설정의 하드웨어 속성](./images/wifi-hololens-hwdetails.jpg)

   IP 주소는 **IPv4 주소**옆에 나타납니다.

### 음성 명령을 사용하여

장치 구축에 따라 기본 제공 음성 명령 또는 Cortana를 사용하여 IP 주소를 표시할 수 있습니다. [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 후 빌드에 "내 IP 주소가 무엇인가요?" 말하기 그러면 표시 됩니다. 이전 빌드 또는 HoloLens(1세대)의 경우 "안녕 Cortana 내 IP 주소가 무엇인가요?"라고 말합니다. Cortana가 IP 주소를 표시하고 읽습니다.

### Windows 장치 포털 사용

1. PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.
1. **네트워킹** 섹션으로 이동합니다.  
   이 섹션에는 IP 주소와 기타 네트워크 정보가 표시됩니다. 이 방법을 사용하여 개발 PC에서 IP 주소를 복사하여 붙여 넣을 수 있습니다.
