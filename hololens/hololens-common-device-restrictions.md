---
title: 일반적인 디바이스 제한 사항
description: HoloLens 혼합 현실 디바이스에 대한 일반적인 디바이스 제한 사항 및 설정을 최신 상태로 유지합니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639219"
---
# <a name="common-device-restrictions"></a>일반적인 디바이스 제한 사항 

이 가이드는 IT 전문가가 엔터프라이즈의 Windows 10 Holographic OS에 사용할 수 있는 보다 일반적으로 사용되는 관리 옵션을 이해하는 데 도움이 됩니다. MDM 공급업체에서 이러한 정책을 사용하도록 설정하는 방법을 이해하려면 MDM 시스템 설명서를 참조하세요. 모든 MDM 시스템이 이 가이드에 설명된 모든 설정을 지원하는 것은 아닙니다. 일부 시스템은 OMA-URI XML 파일을 통해 사용자 지정 정책을 지원합니다. [사용자 지정 정책에 대한 Microsoft Intune 지원을](/mem/intune/configuration/custom-settings-windows-10)참조하세요. 명명 규칙은 MDM 공급업체마다 다를 수 있습니다.

## <a name="prevent-changing-of-settings"></a>설정 변경 방지
직원은 일반적으로 회사 디바이스에서 잠그려는 특정 개인 디바이스 설정을 변경할 수 있습니다. 직원은 설정 UI를 통해 HoloLens 특정 설정을 대화형으로 조정할 수 있습니다. MDM을 사용하여 변경할 수 있는 사용자를 제한할 수 있습니다. 다음은 Windows 10 Holographic 설정 제한을 구성하기 위해 지원하는 일반적으로 사용되는 MDM 설정을 나열합니다.
-   [VPN 허용:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 사용자가 VPN 설정을 변경할 수 있습니다.
-   [수동 WiFi 구성 허용:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 사용자가 MDM 프로비전된 네트워크 외부에서 Wi-Fi 연결을 만들 수 있습니다.
-   [수동 MDM 등록 취소 허용](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 사용자가 작업 공간 계정을 삭제할 수 있는지 여부(예: MDM 시스템에서 디바이스 등록 취소)

HoloLens 2 디바이스용 [Windows Holographic 버전 20H2에](hololens-release-notes.md#windows-holographic-version-20h2) 추가되었습니다.
- [프로비전 패키지 추가 허용:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 사용자가 새 프로비전 패키지를 추가할 수 있는지 토글하고 새 값으로 덮어씁니다.
- [프로비전 패키지 제거 허용:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 사용자가 프로비전 패키지를 제거할 수 있으면 토글하여 이전에 잠긴 설정을 전환할 수 있습니다.

HoloLens 지원되는 정책 [CSP에서 정책](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 옵션에 대한 자세한 내용을 확인하세요.

## <a name="hardware-restrictions"></a>하드웨어 제한
Windows 10 Holographic 디바이스는 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스 및 Wi-Fi와 같은 인기 있는 하드웨어 기능을 포함하는 최첨단 기술을 사용합니다. 하드웨어 제한을 사용하여 이러한 기능의 가용성을 제어할 수 있습니다.
다음은 Windows 10 Holographic 하드웨어 제한을 구성하기 위해 지원하는 일반적으로 사용되는 MDM 설정을 나열합니다.

> [!NOTE]
> 이러한 하드웨어 제한 사항 중 일부는 연결에 영향을 미치며 데이터 보호를 지원합니다.

-   [Wi-Fi 허용:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 자신의 디바이스에서 WiFi 라디오를 사용하도록 설정하고 사용할 수 있는지 여부입니다.
-   [USB 연결 허용:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 연결 사용 여부(USB 충전에 영향을 미치지 않습니다.)
-   [Bluetooth 허용:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 디바이스에서 Bluetooth 라디오를 사용하도록 설정하고 사용할 수 있는지 여부입니다.
-   [카메라 제한:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows 앱이 카메라에 액세스할 수 있는지 여부를 지정합니다.
-   [마이크 제한:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows 앱이 마이크에 액세스할 수 있는지 여부를 지정합니다.

HoloLens 2 디바이스용 [Windows Holographic, verison 20H2에](hololens-release-notes.md#windows-holographic-version-20h2) 추가되었습니다. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 디스플레이가 꺼질 때까지의 시간을 설정하고, 디스플레이를 해제하여 디바이스를 잠깁니다. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 디스플레이가 꺼질 때까지의 시간을 설정하고, 디스플레이를 해제하여 디바이스를 잠깁니다. 
