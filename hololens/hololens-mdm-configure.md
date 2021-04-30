---
title: Microsoft의 Endpoint Manager Intune을 사용 하 여 HoloLens 장치 관리
description: MDM을 사용 하 여 Intune을 사용 하는 대규모로 CSP, 정책을 구성 하 고 HoloLens 혼합 현실 장치를 관리 하는 방법을 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309552"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Microsoft의 Endpoint Manager Intune을 사용 하 여 HoloLens 장치 관리

MDM을 통해 관리할 수 있는 다양 한 설정이 있습니다. Intune 장치를 함께 그룹화 하 고 해당 사용자 또는 장치 그룹에 구성을 배포할 수 있습니다. 앱을 배포 및 관리 하 고, 네트워크에 연결 하도록 장치를 설정 하 고, 필요한 시간 및 업데이트 링에 필요한 업데이트를 구성할 수도 있습니다. 

## <a name="how-to-manage-via-intune"></a>Intune을 통해 관리 하는 방법

### <a name="device-categories-and-groups"></a>디바이스 범주 및 그룹
Intune을 사용 하 여 엔지니어링, 의료, 개발자 등과 같이 사용자가 만든 범주를 기반으로 장치를 자동으로 그룹에 추가 하는 장치 범주를 만들 수 있습니다. 이를 통해 Windows Holographic for Business를 실행 중인 디바이스 관리를 더 쉽게 할 수 있습니다.
자세히 읽기: [장치를 그룹으로 분류](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>디바이스 구성 프로필
Intune은 조직 내의 다른 디바이스에서 사용하거나 사용하지 않게 할 수 있는 설정 및 기능을 포함합니다. 이러한 설정 및 기능은 프로필을 사용하여 관리됩니다. 예를 들어 Cortana를 사용하도록 설정하거나 Windows Holographic for Business를 실행하는 디바이스에서 Microsoft Defender Smart Screen을 사용하는 프로필을 만들 수 있습니다.
프로필에서 OMA URI를 사용하여 일부 설정을 사용자 지정하고 디바이스 제한을 만들고 VPN(가상 프라이빗 네트워크) 및 Wi-Fi를 구성할 수 있습니다.
[구성 프로필](https://docs.microsoft.com/mem/intune/configuration/device-profiles)및 [프로필 개요](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)를 시작 합니다.

## <a name="examples-of-what-can-be-managed-and-configured"></a>관리 및 구성할 수 있는 항목의 예

MDM을 사용 하 여 장치를 관리 하면 광범위 한 항목을 선택할 수 있습니다. 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi 설정](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)은 사용자와 디바이스에 무선 네트워크 설정을 할당합니다. Wi-Fi 프로필을 할당 하면 사용자는 직접 구성 하지 않고도 회사 Wi-Fi에 액세스할 수 있습니다.
[HoloLens 용 네트워크 구성](hololens-commercial-infrastructure.md) 에 대 한 자세한 정보

### <a name="certificates"></a>인증서
인증서는 계정 인증, Wi-Fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공 하 여 보안을 개선 하는 데 도움이 됩니다. 관리자는 프로 비전 패키지를 통해 수동으로 장치에서 인증서를 관리할 수 있지만 등록에서 갱신 및 해지를 통해 MDM 시스템을 사용 하 여 전체 수명 주기 동안 해당 인증서를 관리 하는 것이 좋습니다. Mdm 시스템은 장치를 등록 한 후 장치 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다 (MDM 시스템이 단순 인증서 등록 프로토콜 (SCEP) 또는 공개 키 암호화 표준 #12 (PKCS # 12)를 지 원하는 경우). 현재 인증서가 만료 되기 전에 MDM에서 등록 된 클라이언트 인증서를 쿼리 및 삭제 하거나 새 등록 요청을 트리거할 수도 있습니다. 

### <a name="proxy"></a>프록시
대부분의 회사 인트라넷 네트워크는 프록시를 활용 하 여 내부 트래픽을 관리 합니다. HoloLens 2를 사용 하 여 이더넷 및 Wi-Fi 연결에 대 한 프록시 서버를 구성할 수 있습니다. 이러한 설정은 VPN 연결에는 적용 되지 않습니다. Windows 10의 프록시 설정에 대 한 자세한 내용은 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)를 참조 하세요.

### <a name="vpn"></a>VPN
조직에서는 일반적으로 VPN을 사용 하 여 회사 인트라넷의 앱 및 리소스에 대 한 액세스를 제어 합니다. HoloLens 2는 Microsoft Store에서 다운로드할 수 있는 플러그 인이 필요한 SSL VPN 연결을 지원 하며 사용자가 선택한 VPN 공급 업체에만 적용 됩니다. 
- [HoloLens의 VPN](hololens-network.md#vpn)에 대해 자세히 알아보세요.
- VPN 프로필에 대 한 자세한 내용은 [VPNV2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)를 참조 하세요.

### <a name="deploy-and-manage-apps"></a>앱 배포 및 관리
Intune을 사용하여 Windows Holographic for Business를 실행하는 디바이스에 앱을 추가할 수 있습니다. MDM 솔루션을 사용 하 여 IT 의사 결정권자와 관리자는 사내 또는 기간 업무 앱을 개인적으로 자동 설치 (푸시) 하거나 사용자 그룹에 대해 스토어를 통해 앱을 구매할 수 있습니다. 다음을 포함하여 앱을 배포하는 방법은 많습니다.
-   [Intune 및 회사 포털]( app-deploy-intune.md)
-   [비즈니스용 Microsoft Store]( app-deploy-store-business.md)

Intune을 통한 앱 관리에 대해 자세히 알아보세요.
-   [Intune에 앱 추가](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft Store 앱 추가](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [만든 앱 추가](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [그룹에 앱 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>소프트웨어 업데이트
Intune에는 Windows 10 디바이스용 업데이트 링이라는 기능이 포함되어 있습니다. 이러한 업데이트 링은 업데이트를 설치하는 방법을 결정하는 설정 그룹을 포함합니다. 예를 들어 업데이트를 설치하기 위한 유지 관리 기간을 만들거나 업데이트가 설치된 후 다시 시작을 선택할 수 있습니다. 업데이트 링은 Windows Holographic for Business를 실행하는 여러 디바이스에 적용할 수 있습니다.
Intune을 통해 [HoloLens 업데이트를 관리](hololens-updates.md) 하 고 [소프트웨어 업데이트를 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)하는 방법에 대해 자세히 알아보세요.

### <a name="configure-kiosk-mode"></a>키오스크 모드 구성
Intune에서 사용할 수 있는 공유 또는 게스트 PC 기능을 사용하여 키오스크로 실행하도록 Windows Holographic for Business 디바이스를 구성할 수 있습니다. 이러한 디바이스는 하나의 앱(단일 앱 키오스크 모드)을 실행하거나 여러 앱(다중 앱 키오스크 모드)을 실행할 수 있습니다. 키오스크 모드는 기본적으로 앱에 액세스할 수 있는 id를 제어 하는 UI입니다.
[HoloLens를 키오스크로 설정]( hololens-kiosk.md) 하는 방법 알아보기

