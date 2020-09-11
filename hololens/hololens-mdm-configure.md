---
title: Microsoft의 끝점 관리자 Intune을 사용 하 여 HoloLens 장치 관리
description: 확장할 때 MDM을 사용 하 여 CSP 및 정책을 구성 하 고 HoloLens를 관리 합니다.
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009643"
---
# Microsoft의 끝점 관리자 Intune을 사용 하 여 HoloLens 장치 관리

MDM을 통해 관리할 수 있는 다양 한 설정이 있습니다. Intune 장치를 함께 그룹화 하 여 해당 사용자 또는 장치 그룹에 구성을 배포할 수 있습니다. 또한 앱을 배포 및 관리 하 고, 장치를 설정 하 여 네트워크에 연결 하 고, 필요한 경우 업데이트 링에서 발생 하도록 업데이트를 구성할 수 있습니다. 

## Intune을 통해 관리 하는 방법

### 장치 범주 및 그룹
Intune을 사용 하 여 디바이스 범주를 만들어 엔지니어링, 의료, 개발자 등 자신이 만든 범주에 따라 그룹에 디바이스를 자동으로 추가할 수 있습니다. 이 개념은 비즈니스용 Windows 홀로그램를 실행 하는 장치를 쉽게 관리할 수 있도록 하는 것입니다.
자세한 정보: [장치를 그룹으로 분류](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### 장치 구성 프로필
Intune에는 조직 내 여러 장치에서 사용 하거나 사용 하지 않도록 설정할 수 있는 설정 및 기능이 포함 되어 있습니다. 이러한 설정 및 기능은 프로필을 사용 하 여 관리 됩니다. 예를 들어 비즈니스용 Windows 홀로그램를 실행 하는 장치에서 Cortana를 사용 하거나 Microsoft Defender 스마트 화면을 사용 하는 프로필을 만들 수 있습니다.
프로필에서 OMA-URI를 사용 하 여 일부 설정을 사용자 지정 하 고, 장치 제한을 만들고, VPN (가상 사설망) 및 Wi-fi를 구성할 수 있습니다.
[구성 프로필](https://docs.microsoft.com/mem/intune/configuration/device-profiles)및 [프로필 개요](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)를 시작 하세요.

## 관리 및 구성할 수 있는 항목의 예

MDM을 사용 하 여 디바이스를 관리 하는 경우 선택할 수 있는 광범위 한 항목 배열을 제공 합니다. 

### Wi-Fi
[Wi-fi 설정은](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 사용자 및 장치에 무선 네트워크 설정을 지정 합니다. Wi-fi 프로필을 할당 하면 사용자가 직접 구성할 필요 없이 회사 Wi-fi에 대 한 액세스 권한을 얻을 수 있습니다.
[HoloLens 용 네트워크 구성](hololens-commercial-infrastructure.md) 에 대 한 자세한 정보

### 인증서
인증서는 계정 인증, Wi-fi 인증, VPN 암호화, 웹 콘텐츠의 SSL 암호화를 제공 하 여 보안을 개선 하는 데 도움이 됩니다. 관리자는 프로 비전 패키지를 통해 디바이스에서 수동으로 인증서를 관리할 수 있지만, 사용자의 전체 수명 주기 동안 해당 인증서를 관리 하는 데 사용 하는 것이 좋습니다 (등록에서 갱신 및 해지). Mdm 시스템에서 SCEP (단순 인증서 등록 프로토콜) 또는 공개 키 암호화 표준 #12 (PKCS # 12))을 지 원하는 경우 디바이스를 등록 한 후 장치 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다. 또한 현재 인증서가 만료 되기 전에, MDM이 등록 된 클라이언트 인증서를 쿼리하거나 삭제 하거나 새 등록 요청을 트리거할 수 있습니다. 

### Proxy (프록시)
대부분의 기업 인트라넷 네트워크는 프록시를 이용 하 여 내부 트래픽을 관리 합니다. HoloLens 2를 사용 하 여 이더넷과 Wi-fi 연결을 위한 프록시 서버를 구성할 수 있습니다. 이 설정은 VPN 연결에 적용되지 않습니다. Windows 10의 프록시 설정에 대 한 자세한 내용은 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)를 참조 하세요.

### VPN
조직은 회사 인트라넷에 있는 앱과 리소스에 대한 액세스를 제어하기 위해 VPN을 많이 사용합니다. HoloLens 2는 Microsoft Store에서 다운로드할 수 있는 플러그인이 필요한 SSL VPN 연결을 지원 하며, 사용자가 선택한 VPN 공급 업체에만 해당 됩니다. 
- [HoloLens의 VPN](hololens-network.md#vpn)에 대 한 자세한 내용을 읽으십시오.
- VPN 프로필에 대 한 자세한 내용은 [VPNV2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)를 참조 하세요.

### 앱 배포 및 관리
Intune을 사용 하 여 비즈니스용 Windows 홀로그램를 실행 하는 장치에 앱을 추가할 수 있습니다. MDM 솔루션을 사용 하면 IT 의사 결정권자와 관리자가 개인적으로 사내 앱을 자동으로 설치 (푸시) 하거나 사용자 그룹을 위해 스토어를 통해 앱을 구매할 수 있습니다. 다음과 같은 여러 가지 방법으로 앱을 배포할 수 있습니다.
-   [Intune 및 회사 포털]( app-deploy-intune.md)
-   [비즈니스용 Microsoft Store]( app-deploy-store-business.md)

Intune을 통해 앱 관리에 대해 자세히 알아보세요.
-   [Intune에 앱 추가](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft 스토어 앱 추가](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [만든 앱 추가](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [앱을 그룹에 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### 소프트웨어 업데이트
Intune에는 Windows 10 장치용 업데이트 링 이라는 기능이 포함 되어 있습니다. 이러한 업데이트 링에는 업데이트가 설치 되는 방법을 결정 하는 설정 그룹이 포함 됩니다. 예를 들어 업데이트를 설치하는 유지 관리 창을 만들거나 업데이트를 설치한 후 다시 시작 하도록 선택할 수 있습니다. 비즈니스를 위해 Windows 홀로그램를 실행 하는 여러 장치에 업데이트 링을 적용할 수 있습니다.
Intune을 통해 [HoloLens 업데이트를 관리](hololens-updates.md) 하 고 [소프트웨어 업데이트를 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)하는 방법에 대해 자세히 알아보세요.

### 키오스크 모드 구성
Intune에서 사용할 수 있는 공유 또는 게스트 PC 기능을 사용 하 여 비즈니스용 Windows 홀로그램을 키오스크로 실행 하도록 구성할 수 있습니다. 이러한 장치는 하나의 앱 (단일 앱 키오스크 모드)을 실행 하거나 여러 앱 (다중 앱 키오스크 모드)을 실행할 수 있습니다. 키오스크 모드는 기본적으로 어떤 앱에 액세스할 수 있는지를 id를 제어 하는 UI입니다.
[HoloLens를 키오스크로 설정]( hololens-kiosk.md) 하는 방법 알아보기

