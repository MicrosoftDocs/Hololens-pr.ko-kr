---
title: 일반적인 장치 제한 사항
description: 장치 restrctions 일반적으로 HoloLens에 설정 됩니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016797"
---
# 일반적인 장치 제한 사항 

이 가이드에서는 IT 전문가가 엔터프라이즈의 Windows 10 홀로그램 OS에서 사용할 수 있는 보다 일반적으로 사용 되는 관리 옵션을 이해 하는 데 도움이 됩니다. MDM 공급업체에서 이러한 정책을 설정하는 방법은 MDM 시스템 설명서를 참조하세요. MDM 시스템에 따라 이 가이드에 설명된 일부 설정을 지원하지 않을 수 있습니다. 일부 시스템은 OMA-URI XML 파일을 통해 사용자 지정 정책을 지원합니다. [사용자 지정 정책에 대한 Microsoft Intune 지원](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)을 참조하세요. 명명 규칙도 MDM 공급업체마다 다를 수 있습니다.

## 설정 변경 방지
IT 전문가는 회사 장치에서 특정 개인 장치 설정을 잠그기를 바라지만 대개 직원은 이 설정을 변경할 수 있습니다. 직원은 설정 UI를 통해 HoloLens의 특정 설정을 대화형으로 조정할 수 있습니다. MDM을 사용하면 변경을 허용할 사용자를 제한할 수 있습니다. 다음 목록에는 Windows 10 홀로그램에서 설정 제한을 구성할 수 있도록 지 원하는 일반적으로 사용 되는 MDM 설정이 나와 있습니다.
-   [VPN 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 사용자가 VPN 설정을 변경할 수 있도록 허용 합니다.
-   [WiFi 수동 구성 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 사용자가 MDM 프로 비전 네트워크 외부에서 Wi-fi 연결을 만들 수 있도록 허용 합니다.
-   [수동 MDM Unenrollment 허용](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 사용자가 작업 공간 계정을 삭제할 수 있는지 여부 (즉, MDM 시스템에서 디바이스를 등록 해제)

HoloLens 지원 [정책 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 의 정책 옵션에 대 한 자세한 내용 찾기

## 하드웨어 제한
Windows 10 홀로그램 디바이스는 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스, Wi-fi 등 인기 있는 하드웨어 기능을 포함 하는 최신 기술을 사용 합니다. 이러한 기능의 가용성을 제어하는 데 하드웨어 제한을 사용할 수 있습니다.
다음 목록에는 Windows 10 홀로그램에서 하드웨어 제한을 구성할 수 있도록 지 원하는 일반적으로 사용 되는 MDM 설정이 나와 있습니다.

> [!NOTE]
> 이러한 하드웨어 제한 중 일부는 데이터 보호의 연결 및 지원에 영향을 줍니다.

-   [Wi-fi 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 장치에서 WiFi 라디오를 활성화 하 고 사용할 수 있는지 여부.
-   [USB 연결 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 연결이 활성화 되어 있는지 여부 (USB 충전에는 영향을 주지 않음)
-   [블루투스 허용:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 장치에서 Bluetooth 라디오를 사용 하도록 설정 하 고 사용할 수 있는지 여부
-   [카메라 제한:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows 앱에서 카메라에 액세스할 수 있는지 여부를 지정 합니다.
-   [마이크 제한:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows 앱에서 마이크에 액세스할 수 있는지 여부를 지정 합니다.
