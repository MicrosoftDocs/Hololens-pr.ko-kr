---
title: 공통 장치 제한
description: HoloLens 혼합 현실 장치에 대한 일반적인 장치 제한 및 설정을 최신으로 유지하세요.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283359"
---
# 공통 장치 제한 

이 가이드는 IT 전문가가 엔터프라이즈의 Windows 10 Holographic OS에 사용할 수 있는 보다 일반적으로 사용되는 관리 옵션을 이해하는 데 도움이 됩니다. MDM 공급업체에서 이러한 정책을 설정하는 방법은 MDM 시스템 설명서를 참조하세요. MDM 시스템에 따라 이 가이드에 설명된 일부 설정을 지원하지 않을 수 있습니다. 일부 시스템은 OMA-URI XML 파일을 통해 사용자 지정 정책을 지원합니다. [사용자 지정 정책에 대한 Microsoft Intune 지원](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)을 참조하세요. 명명 규칙도 MDM 공급업체마다 다를 수 있습니다.

## 설정 변경 방지
IT 전문가는 회사 장치에서 특정 개인 장치 설정을 잠그기를 바라지만 대개 직원은 이 설정을 변경할 수 있습니다. 직원은 설정 UI를 통해 HoloLens의 특정 설정을 대화형으로 조정할 수 있습니다. MDM을 사용하면 변경을 허용할 사용자를 제한할 수 있습니다. 다음 목록에는 Windows 10 Holographic에서 설정 제한을 구성하기 위해 지원하는 일반적으로 사용되는 MDM 설정이 나열됩니다.
-   [VPN 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 사용자가 VPN 설정을 변경할 수 있도록 허용
-   [수동 WiFi 구성 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 사용자가 MDM 프로비전된 Wi-Fi 외부에서 연결을 만들 수 있도록 허용
-   [Allow Manual MDM Unenrollment(수동 MDM 허용)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 사용자가 회사 계정을 삭제할 수 있는지 여부(예: MDM 시스템에서 디바이스의 로그인을 제거)

HoloLens 2 디바이스용 [Windows Holographic 버전 20H2에](hololens-release-notes.md#windows-holographic-version-20h2) 추가되었습니다.
- [프로비저닝 패키지 추가 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 사용자가 새 프로비저닝 패키지를 추가할 수 있는 경우 토글합니다. 새 값으로 덮어입습니다.
- [프로비저닝 패키지 제거 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 사용자가 프로비저닝 패키지를 제거할 수 있는 경우 토글하여 이전에 잠긴 설정을 전환할 수 있습니다.

HoloLens 지원 정책 [CSP에서](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 정책 옵션에 대한 자세한 정보 찾기

## 하드웨어 제한
Windows 10 Holographic 장치는 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스 및 Wi-Fi와 같은 인기 하드웨어 기능을 포함하는 최첨단 기술을 사용합니다. 이러한 기능의 가용성을 제어하는 데 하드웨어 제한을 사용할 수 있습니다.
다음 목록에는 Windows 10 Holographic에서 하드웨어 제한을 구성하기 위해 지원하는 일반적으로 사용되는 MDM 설정이 나열됩니다.

> [!NOTE]
> 이러한 하드웨어 제한 중 일부는 연결에 영향을 주며 데이터 보호를 지원합니다.

-   [Wi-Fi 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 장치에서 WiFi 라디오를 사용하도록 설정하고 사용할 수 있는지 여부입니다.
-   [USB 연결 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 연결을 사용할 수 있는지 여부(USB 충전에는 영향을 주지 않습니다.)
-   [다음 Bluetooth.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 디바이스에서 디바이스에서 Bluetooth 사용할 수 있는지 여부입니다.
-   [카메라 제한:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows 앱이 카메라에 액세스할 수 있는지 여부를 지정합니다.
-   [마이크 제한:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows 앱이 마이크에 액세스할 수 있는지 여부를 지정합니다.

HoloLens 2 디바이스용 [Windows Holographic, verison 20H2에](hololens-release-notes.md#windows-holographic-version-20h2) 추가되었습니다. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 디스플레이가 꺼질 때까지 시간을 설정하고 디스플레이를 끄면 디바이스가 잠겨집니다. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 디스플레이가 꺼질 때까지 시간을 설정하고 디스플레이를 끄면 디바이스가 잠겨집니다. 
