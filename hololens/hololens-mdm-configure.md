---
title: Microsoft의 Endpoint Manager Intune을 사용하여 HoloLens 장치 관리
description: MDM을 사용하여 Intune을 사용하여 HoloLens 혼합 현실 장치를 대규모로 구성하고 관리하는 방법을 학습합니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283959"
---
# Microsoft의 Endpoint Manager Intune을 사용하여 HoloLens 장치 관리

MDM을 통해 관리할 수 있는 다양한 설정이 있습니다. Intune 장치를 함께 사용하여 그룹화할 수 있으며 이러한 사용자 또는 장치 그룹에 구성을 배포할 수 있습니다. 앱을 배포 및 관리하고, 네트워크에 연결할 디바이스를 설정할 수 있을 뿐만 아니라, 필요한 시기와 필요한 업데이트 링에서 발생할 업데이트를 구성할 수도 있습니다. 

## Intune을 통해 관리하는 방법

### 장치 범주 및 그룹
Intune을 사용하여 장치 범주를 만들어 엔지니어링, 의료, 개발자 등 사용자가 만든 범주에 따라 그룹에 장치를 자동으로 추가할 수 있습니다. 비즈니스용 Windows Holographic을 실행하는 장치를 더 쉽게 관리할 수 있도록 하는 것입니다.
자세히 읽기: [디바이스를 그룹으로 분류](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### 장치 구성 프로필
Intune에는 조직 내의 여러 장치에서 활성화하거나 사용하지 않도록 설정할 수 있는 설정 및 기능이 포함되어 있습니다. 이러한 설정 및 기능은 프로필을 사용하여 관리됩니다. 예를 들어 Cortana를 사용할 수 있도록 설정하거나 비즈니스용 Windows Holographic을 실행하는 디바이스에서 Microsoft Defender 스마트 화면을 사용하는 프로필을 만들 수 있습니다.
프로필에서 OMA-URI를 사용하여 일부 설정을 사용자 지정하고, 장치 제한을 만들고, VPN(가상 사설망) 및 Wi-Fi를 구성할 수 있습니다.
[구성 프로필 및](https://docs.microsoft.com/mem/intune/configuration/device-profiles)프로필 [개요를 시작하세요.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## 관리 및 구성할 수 있는 경우의 예

MDM을 사용하여 디바이스를 관리하면 선택할 수 있는 다양한 항목이 표시됩니다. 

### Wi-Fi
[Wi-Fi 설정은](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 사용자 및 장치에 무선 네트워크 설정을 할당합니다. 사용자 프로필을 Wi-Fi 사용자가 직접 구성하지 않고도 회사 Wi-Fi 액세스할 수 있습니다.
[HoloLens에](hololens-commercial-infrastructure.md) 대한 네트워크 구성에 대한 자세한 내용은

### 인증서
인증서는 웹 콘텐츠의 계정 인증, Wi-Fi 인증, VPN 암호화 및 SSL 암호화를 제공하여 보안을 향상시키는 데 도움이 됩니다. 관리자는 프로비저닝 패키지를 통해 장치에서 인증서를 수동으로 관리할 수 있지만 등록부터 갱신 및 해지까지 전체 수명 주기 동안 MDM 시스템을 사용하여 인증서를 관리하는 것이 가장 좋은 것입니다. MDM 시스템에서 SCEP(Simple Certificate Enrollment Protocol) 또는 PKCS#12(공개 키 암호화 표준)를 지원하는 경우)를 등록한 후 MDM 시스템에서 이러한 인증서를 장치의 인증서 저장소에 #12 수 있습니다. 또한 MDM은 등록된 클라이언트 인증서를 쿼리 및 삭제하거나 현재 인증서가 만료되기 전에 새 등록 요청을 트리거할 수 있습니다. 

### Proxy (프록시)
대부분의 회사 인트라넷 네트워크는 프록시를 사용하여 내부 트래픽을 관리합니다. HoloLens 2를 사용하면 이더넷 및 서버 연결에 대한 프록시 Wi-Fi 수 있습니다. 이 설정은 VPN 연결에 적용되지 않습니다. Windows 10의 프록시 설정에 대한 자세한 내용은 [NetworkProxy CSP를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

### VPN
조직은 회사 인트라넷에 있는 앱과 리소스에 대한 액세스를 제어하기 위해 VPN을 많이 사용합니다. HoloLens 2는 Microsoft Store에서 다운로드 가능한 플러그 인이 필요하며 선택한 VPN 공급업체와 관련이 있는 SSL VPN 연결을 지원합니다. 
- [HoloLens의 VPN에 대해 자세히 읽어 읽습니다.](hololens-network.md#vpn)
- VPN 프로필에 대한 자세한 내용은 [VPNv2 CSP를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### 앱 배포 및 관리
Intune을 사용하여 비즈니스용 Windows Holographic을 실행하는 장치에 앱을 추가할 수 있습니다. MDM 솔루션을 사용하면 IT 의사 결정권자 및 관리자가 사용자 그룹을 위해 스토어를 통해 사내, 업무용 앱을 개인적으로 자동 설치(푸시)할 수 있습니다. 앱을 배포하는 방법에는 다음을 비롯한 여러 가지가 있습니다.
-   [Intune 및 회사 포털]( app-deploy-intune.md)
-   [비즈니스용 Microsoft Store]( app-deploy-store-business.md)

Intune을 통한 앱 관리에 대해 자세히 알아보습니다.
-   [Intune에 앱 추가](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft Store 앱 추가](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [만든 앱 추가](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [그룹에 앱 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### 소프트웨어 업데이트
Intune에는 Windows 10 디바이스용 업데이트 링이라는 기능이 포함되어 있습니다. 이러한 업데이트 링에는 업데이트 설치 방법을 결정하는 설정 그룹이 포함되어 있습니다. 예를 들어 업데이트를 설치하는 유지 관리 창을 만들거나 업데이트를 설치한 후 다시 시작 하도록 선택할 수 있습니다. 비즈니스용 Windows Holographic을 실행하는 여러 장치에 업데이트 링을 적용할 수 있습니다.
Intune을 통해 [HoloLens](hololens-updates.md) 업데이트를 관리하고 소프트웨어 업데이트를 관리하는 [방법에 대해 자세히 읽어 읽습니다.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### 키오스크 모드 구성
Intune에서 사용할 수 있는 공유 또는 게스트 PC 기능을 사용하여 비즈니스용 Windows Holographic 장치를 키오스크로 실행하도록 구성할 수 있습니다. 이러한 장치는 하나의 앱(단일 앱 키오스크 모드)을 실행하거나 여러 앱(다중 앱 키오스크 모드)을 실행할 수 있습니다. 키오스크 모드는 기본적으로 어떤 앱에 액세스할 수 있는 ID를 제어하는 UI입니다.
[HoloLens를]( hololens-kiosk.md) 키오스크로 설정하는 방법 학습

