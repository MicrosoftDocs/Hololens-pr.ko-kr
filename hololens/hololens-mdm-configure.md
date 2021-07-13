---
title: Microsoft의 Endpoint Manager Intune을 사용하여 HoloLens 디바이스 관리
description: MDM을 사용하여 Intune을 사용하여 대규모로 CSP, 정책 및 HoloLens 혼합 현실 디바이스를 관리하는 방법을 알아봅니다.
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
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640283"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Microsoft의 Endpoint Manager Intune을 사용하여 HoloLens 디바이스 관리

MDM을 통해 관리할 수 있는 다양한 설정이 있습니다. Intune 디바이스를 사용하여 함께 그룹화할 수 있으며 이러한 사용자 또는 디바이스 그룹에 구성을 배포할 수 있습니다. 앱을 배포 및 관리하여 네트워크에 연결할 디바이스를 설정하고, 필요한 시간 및 필요한 업데이트 링에서 업데이트가 발생하도록 구성할 수도 있습니다. 

## <a name="how-to-manage-via-intune"></a>Intune을 통해 관리하는 방법

### <a name="device-categories-and-groups"></a>디바이스 범주 및 그룹
Intune을 사용하여 디바이스 범주를 만들어 엔지니어링, 의료, 개발자 등 사용자가 만든 범주에 따라 그룹에 디바이스를 자동으로 추가할 수 있습니다. 이를 통해 Windows Holographic for Business를 실행 중인 디바이스 관리를 더 쉽게 할 수 있습니다.
자세한 내용: [디바이스를 그룹으로 분류](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>디바이스 구성 프로필
Intune은 조직 내의 다른 디바이스에서 사용하거나 사용하지 않게 할 수 있는 설정 및 기능을 포함합니다. 이러한 설정 및 기능은 프로필을 사용하여 관리됩니다. 예를 들어 Cortana를 사용하도록 설정하거나 Windows Holographic for Business를 실행하는 디바이스에서 Microsoft Defender Smart Screen을 사용하는 프로필을 만들 수 있습니다.
프로필에서 OMA URI를 사용하여 일부 설정을 사용자 지정하고 디바이스 제한을 만들고 VPN(가상 프라이빗 네트워크) 및 Wi-Fi를 구성할 수 있습니다.
구성 프로필 및 [프로필 개요를](/mem/intune/configuration/device-profile-create) [시작합니다.](/mem/intune/configuration/device-profiles)

## <a name="examples-of-what-can-be-managed-and-configured"></a>관리 및 구성할 수 있는 작업의 예

MDM을 사용하여 디바이스를 관리하면 선택할 수 있는 다양한 항목이 있습니다. 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi 설정](/mem/intune/configuration/wi-fi-settings-configure)은 사용자와 디바이스에 무선 네트워크 설정을 할당합니다. Wi-Fi 프로필을 할당하면 사용자가 직접 구성하지 않고도 회사 Wi-Fi 액세스할 수 있습니다.
[HoloLens 네트워크 구성에](hololens-commercial-infrastructure.md) 대해 자세히 알아봅니다.

### <a name="certificates"></a>인증서
인증서를 사용하면 계정 인증, Wi-Fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공하여 보안을 향상시킬 수 있습니다. 관리자는 프로비전 패키지를 통해 디바이스의 인증서를 수동으로 관리할 수 있지만 등록부터 갱신 및 해지까지 전체 수명 주기 동안 MDM 시스템을 사용하여 해당 인증서를 관리하는 것이 가장 좋습니다. MDM 시스템은 디바이스를 등록한 후 디바이스의 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다(MDM 시스템에서 SCEP(단순 인증서 등록 프로토콜) 또는 공개 키 암호화 표준 #12(PKCS #12)을 지원하는 경우). MDM은 현재 인증서가 만료되기 전에 등록된 클라이언트 인증서를 쿼리 및 삭제하거나 새 등록 요청을 트리거할 수도 있습니다. 

### <a name="proxy"></a>Proxy (프록시)
대부분의 회사 인트라넷 네트워크는 프록시를 활용하여 내부 트래픽을 관리합니다. HoloLens 2 사용하면 이더넷 및 Wi-Fi 연결에 대한 프록시 서버를 구성할 수 있습니다. 이러한 설정은 VPN 연결에 적용되지 않습니다. Windows 10 프록시 설정에 대한 자세한 내용은 [NetworkProxy CSP 를 참조하세요.](/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
조직에서는 종종 VPN을 사용하여 회사 인트라넷의 앱 및 리소스에 대한 액세스를 제어합니다. HoloLens 2 SSL VPN 연결을 지원합니다. 이 연결은 Microsoft Store 다운로드 가능한 플러그 인이 필요하며 선택한 VPN 공급업체와 관련이 있습니다. 
- [HoloLens VPN에 대해](hololens-network.md#vpn)자세히 읽어보십시오.
- VPN 프로필에 대한 자세한 내용은 [VPNv2 CSP](/windows/client-management/mdm/vpnv2-csp)를 참조하세요.

### <a name="deploy-and-manage-apps"></a>앱 배포 및 관리
Intune을 사용하여 Windows Holographic for Business를 실행하는 디바이스에 앱을 추가할 수 있습니다. MDM 솔루션을 사용하면 IT 의사 결정자와 관리자가 사내, 사업장 앱을 비공개로 자동 설치(푸시)하거나 사용자 그룹을 위해 스토어를 통해 앱을 구매할 수 있습니다. 다음을 포함하여 앱을 배포하는 방법은 많습니다.
-   [Intune 및 회사 포털]( app-deploy-intune.md)
-   [비즈니스용 Microsoft Store]( app-deploy-store-business.md)

Intune을 통한 앱 관리에 대해 자세히 알아보세요.
-   [Intune에 앱 추가](/mem/intune/apps/apps-add)
-   [Microsoft Store 앱 추가](/mem/intune/apps/store-apps-windows)
-   [만든 앱 추가](/mem/intune/apps/lob-apps-windows)
- [그룹에 앱 할당](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>소프트웨어 업데이트
Intune에는 Windows 10 디바이스용 업데이트 링이라는 기능이 포함되어 있습니다. 이러한 업데이트 링은 업데이트를 설치하는 방법을 결정하는 설정 그룹을 포함합니다. 예를 들어 업데이트를 설치하기 위한 유지 관리 기간을 만들거나 업데이트가 설치된 후 다시 시작을 선택할 수 있습니다. 업데이트 링은 Windows Holographic for Business를 실행하는 여러 디바이스에 적용할 수 있습니다.
[Intune을 통해](/mem/intune/protect/windows-update-for-business-configure) [HoloLens 업데이트](hololens-updates.md) 관리 및 소프트웨어 업데이트 관리에 대해 자세히 읽어 보십시오.

### <a name="configure-kiosk-mode"></a>키오스크 모드 구성
Intune에서 사용할 수 있는 공유 또는 게스트 PC 기능을 사용하여 키오스크로 실행하도록 Windows Holographic for Business 디바이스를 구성할 수 있습니다. 이러한 디바이스는 하나의 앱(단일 앱 키오스크 모드)을 실행하거나 여러 앱(다중 앱 키오스크 모드)을 실행할 수 있습니다. 키오스크 모드는 기본적으로 어떤 ID가 어떤 앱에 액세스할 수 있는지 제어하는 UI입니다.
[키오스크로 HoloLens 설정하는]( hololens-kiosk.md) 방법 알아보기

