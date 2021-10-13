---
title: 일반적인 장치 제한 사항
description: HoloLens 혼합 현실 장치에 대 한 일반적인 장치 제한 사항 및 설정을 최신으로 유지 합니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924315"
---
# <a name="common-device-restrictions"></a>일반적인 장치 제한 사항

이 가이드를 통해 IT 전문가는 엔터프라이즈의 Windows 10 Holographic OS에 대해 보다 일반적으로 사용 되는 관리 옵션을 이해할 수 있습니다. Mdm 공급 업체에서 이러한 정책을 사용 하도록 설정 하는 방법을 이해 하려면 MDM 시스템 설명서를 참조 하세요. 모든 MDM 시스템이이 가이드에서 설명 하는 모든 설정을 지원 하지는 않습니다. 일부 시스템은 OMA-URI XML 파일을 통해 사용자 지정 정책을 지원합니다. [사용자 지정 정책에 대 한 Microsoft Intune 지원을](/mem/intune/configuration/custom-settings-windows-10)참조 하세요. 명명 규칙은 MDM 공급 업체에 따라서도 다를 수 있습니다.

## <a name="prevent-changing-of-settings"></a>설정 변경 방지

직원은 일반적으로 회사 장치에서 잠글 수 있는 특정 개인 장치 설정을 변경할 수 있습니다. 직원 들은 설정 UI를 통해 HoloLens의 특정 설정을 대화형으로 조정할 수 있습니다. MDM을 사용 하 여 변경할 수 있는 사용자를 제한할 수 있습니다.
다음 목록에는 설정 제한을 구성 하기 위해 Windows 10 Holographic 지 원하는 일반적으로 사용 되는 MDM 설정이 나와 있습니다.

- [VPN 허용:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 사용자가 VPN 설정을 변경할 수 있습니다.
- [수동 WiFi 구성 허용:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 사용자가 MDM 프로 비전 된 네트워크 외부에서 Wi-Fi 연결을 만들 수 있습니다.
- [MDM 수동 등록 취소 허용](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 사용자가 작업 공간 계정을 삭제할 수 있는지 여부 (즉, MDM 시스템에서 장치 등록 취소)

HoloLens 2 장치에 대해 [Windows Holographic, 버전 20h2](hololens-release-notes.md#windows-holographic-version-20h2) 에 추가 되었습니다.

- [프로 비전 패키지 추가 허용:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 사용자가 새 프로 비전 패키지를 추가할 수 있는지 여부를 설정 하 고 새 값으로 덮어씁니다.
- [프로 비전 패키지 제거 허용:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 사용자가 프로 비전 패키지를 제거 하 여 이전에 잠근 설정을 토글할 수 있도록 설정 합니다.

[Windows Holographic, 버전 21h2](hololens-release-notes.md#windows-holographic-version-21h2)에 추가 되었습니다.

- [RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) 정책을 사용 하면 조직에 대해 구성 된 개인 저장소만 표시 하도록 Microsoft Store 앱을 구성 하 여 사용 가능 하도록 설정한 앱에만 액세스를 제한할 수 있습니다.

HoloLens 지원 되는 [정책 csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 의 정책 옵션에 대 한 자세한 내용을 확인 하세요.

## <a name="hardware-restrictions"></a>하드웨어 제한

Windows 10 Holographic 장치는 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스, wi-fi와 같은 인기 있는 하드웨어 기능을 포함 하는 최신 기술을 사용 합니다. 하드웨어 제한을 사용 하 여 이러한 기능의 가용성을 제어할 수 있습니다.
다음은 하드웨어 제한을 구성 하기 위해 Windows 10 Holographic 지 원하는 일반적으로 사용 되는 MDM 설정 목록입니다.

> [!NOTE]
> 이러한 하드웨어 제한 사항 중 일부는 연결에 영향을 주고 데이터 보호를 지원 합니다.

- [Wi-fi 허용:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 장치에서 WiFi 라디오를 사용 하도록 설정 하 고 사용할 수 있는지 여부입니다.
- [USB 연결 허용:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Usb 연결이 사용 되는지 여부 (USB 충전에 영향을 주지 않음)
- [Bluetooth 허용:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 장치에서 Bluetooth 라디오를 사용 하도록 설정 하 고 사용할 수 있는지 여부입니다.
- [카메라 제한:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows 앱에서 카메라에 액세스할 수 있는지 여부를 지정 합니다.
- [마이크 제한:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows 앱에서 마이크에 액세스할 수 있는지 여부를 지정 합니다.

HoloLens 2 장치에 대해 [Windows Holographic, 버전 20h2](hololens-release-notes.md#windows-holographic-version-20h2) 에 추가 되었습니다.

- [Displayofftimeoutonbattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 디스플레이가 꺼질 때까지 걸리는 시간을 설정 하 고 디스플레이를 끄면 장치를 잠급니다.
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 디스플레이가 꺼질 때까지 걸리는 시간을 설정 하 고 디스플레이를 끄면 장치를 잠급니다.
