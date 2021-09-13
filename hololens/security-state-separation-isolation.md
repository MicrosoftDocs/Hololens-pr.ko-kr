---
title: 상태 구분 및 격리
description: HoloLens 2 혼합 현실 디바이스에서 상태 분리, 격리, 코드 서명 및 Defender 애플리케이션에 대해 알아봅니다.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, 상태 분리, 상태 분리 및 격리, hololens 2, hololens2 보안, 보안 개요, 보안 아키텍처, 아키텍처, hololens 2 아키텍처
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034702"
---
# <a name="state-separation-and-isolation"></a>상태 구분 및 격리

상태 분리 및 격리는 운영 체제가 신뢰할 수 있는 상태로 부팅하는 데 필요한 것과 같은 Hololens 2 운영 체제의 중요한 부분을 변경으로부터 보호합니다. 격리 기술을 사용하면 신뢰할 수 없는 앱이 시스템 보안에 영향을 미치지 않도록 격리된 샌드박스 환경으로 이동됩니다.

## <a name="state-separation"></a>상태 분리

HoloLens 2의 상태 분리는 보안 및 서비스 가능성을 크게 향상시키고(업데이트) 애플리케이션 데이터를 보호하는 데 도움이 됩니다.  상태 분리는 다음과 같이 작동합니다.
  * 핵심 운영 체제는 핵심 운영 체제 볼륨(신뢰되거나 검증된 Microsoft OS 운영 체제 업데이트)에 저장됩니다.
  * 런타임에 변경할 수 있는 운영 체제 부분(예: 다운로드 가능한 드라이버 및 구성)은 추가 상태 분리를 사용하여 데이터를 파티셔닝하고 안전한 별도의 스토리지 위치에 저장합니다.
  * 각 보안 스토리지 위치에는 서로 다른 보안 정책이 연결되어 있어 다음 절에서 자세히 설명한 다양한 보안 이점을 제공합니다.

## <a name="state-separation-benefits"></a>상태 분리 이점

  * 보안: HoloLens 2에 포함된 상태 분리는 플랫폼 무결성, 맬웨어 저항성 및 사용자 데이터 보호를 크게 향상시킵니다. 운영 체제의 변경할 수 없는 부분을 분리하고 읽기 전용 또는 무결성 보호로 설정함으로써 상태 분리는 맬웨어가 콜드 재부팅 동안 지속되는 것을 매우 어렵게 만듭니다. 
  * 업데이트: HoloLens 2를 사용하면 핵심 운영 체제를 수정할 수 없고 디바이스의 나머지 데이터와 완전히 분리하면 업데이트가 간단하고 안정적입니다.  또한 상태 분리는 매우 빠른 업데이트를 위한 중요한 토대를 마련하므로 운영 체제를 단일 단계(원자 장치)로 교체할 수 있습니다.
  * 디바이스 재설정: HoloLens 2 재설정은 내부 및 외부 스토리지 위치를 포함하여 사용자가 생성한 데이터와 사용자 앱 데이터를 디바이스에서 지웁니다. 현재 OS 앱과 보안에 중요한 앱, 그리고 현재 Microsoft 및 OEM 사용자 지정 앱(사전 설치)을 보존합니다. 이러한 사전 설치된 앱은 재설정이 완료된 후 디바이스에서 다시 원상 복구할 수 있습니다.

### <a name="state-separation-states"></a>상태 분리 상태

상태 분리를 통해 운영 체제는 Microsoft의 신뢰할 수 있는 디바이스 구성 요소에 의해서만 변경될 수 있으며 재부팅 시에도 중요한 상태만 지속되도록 허용됩니다. 다른 시스템 상태는 부팅 세션 동안만 존재하며 재부팅 후 삭제됩니다. 상태 분리를 사용하면 디바이스를 초기 상태로 빠르게 되돌립니다. Windows Holographic for Business 상태는 다음과 같은 고유 범주로 나눌 수 있습니다.
  * 핵심 운영 체제 – 변경할 수 없는 상태
  * 운영 체제 데이터 – 변경할 수 있는 상태 
  * 사용자 데이터 – 변경할 수 있는 상태

각 HoloLens 2 작동 상태는 다음 섹션에 설명되어 있습니다.

#### <a name="core-operating-system"></a>핵심 운영 체제

변경할 수 없는 상태는 변경할 수 없는 실행 파일 및 데이터로 구성되며 업데이트 설치 중에만 Microsoft에서 변경할 수 있습니다. 이러한 핵심 운영 체제 업데이트 중에 원하는 최신 운영 상태를 포함하는 새 이미지가 활성화됩니다.
변경할 수 없는 상태가 읽기 전용으로 표시되거나 무결성이 보호되어 상승된 권한을 가진 모든 맬웨어의 지속성을 방지합니다. 다음 실행 파일 및 데이터는 변경할 수 없는 상태로 보호됩니다.
  * Windows Holographic 받은 편지함 드라이버
  * 운영 체제 바이너리
  * Windows 받은 편지함 드라이버
  * Windows 레지스트리 하이브(HKLM)에 저장된 정적 Windows 홀로그램 설정
    * 예: HKLM은 시스템에 설치된 앱의 구성 정보를 저장합니다. 또한 하드웨어 및 해당 드라이버를 검색하기 위한 정보를 저장합니다.
이를 불변(무결성 및 읽기 전용 보호) 상태에서 보호함으로써 핵심 운영 체제가 항상 신뢰할 수 있는 상태로 부팅되도록 보장합니다. 또한 디바이스를 재설정할 때 디바이스가 이 불변 섹션에 있는 구성 요소에만 부팅되도록 할 수 있습니다. 

#### <a name="operating-system-data"></a>운영 체제 데이터 

런타임에 변경할 수 있고 운영 체제 기능에 중요하지 않은 실행 파일 및 데이터는 데이터가 손상되거나 손상되었을 때 삭제 및 다시 생성될 수 있습니다. 높은 값의 변경 가능 상태는 운영 체제에서 유지되어야 하거나 운영 체제 종료 시 또는 지원되는 Windows 운영 체제 및 디바이스 시나리오에서 재부팅 후에도 유지되어야 합니다. 높은 값의 변경 가능한 상태의 예는 다음과 같습니다.
  * IT 관리자가 구성한 전역 디바이스 설정(예: 모든 사용자의 위치 사용 안 함)
  * Wi-Fi 네트워크 연결은 데이터-디바이스-기억 네트워크 및 관련 연결 암호에 액세스합니다.
  * 설정, 로그를 포함한 크래시 덤프.
  * 새로 검색된 디바이스에 대해 요청 시 다운로드된 드라이버.
HoloLens 2의 높은 값의 변경 가능 상태는 운영 체제 데이터 보안 위치(디스크에 저장된 파일 또는 지속형 레지스트리 하이브)에 있습니다.

#### <a name="user-data"></a>사용자 데이터

마지막 상태 범주는 UWP 애플리케이션 또는 운영 체제에서 생성되거나 유지되는 사용자 데이터를 나타냅니다. 다운로드, 문서, 비디오, 사용자 프로필 및 HKEY_CURRENT_USER 하이브와 같은 알려진 모든 사용자 폴더도 이 위치에 저장됩니다. 올바른 자격 증명 없이는 이 데이터를 추출할 수 없습니다. 데이터 보호 방법에 대한 자세한 내용은 [암호화 및 데이터 보호](security-encryption-data-protection.md)를 참조하세요.

##  <a name="isolation"></a>격리

이러한 균형을 이루기 위해 HoloLens 2에는 부팅, 하드웨어 제어, 로그인 등의 기본 기능에 사용되는 핵심 운영 체제가 있습니다. 핵심 운영 체제에서 실행되는 애플리케이션 세트는 사전 설치된 애플리케이션과 UWP 애플리케이션 두 가지뿐입니다.

## <a name="code-signing"></a>코드 서명

디지털 서명 코드를 사용하면 신뢰할 수 있는 소스에 의해 서명된 이후 실행 파일과 스크립트가 수정되지 않았음을 입증하여 신뢰성과 무결성을 제공할 수 있습니다. HoloLens 2가 기본적으로 신뢰하는 기관은 Microsoft 및 Microsoft Store입니다. IT 관리자는 [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) 및 [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) CSP를 통해 디바이스에 새 인증서를 추가할 수 있습니다. 또한 [AllowAllTrustedApps 정책](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)을 사용하여 추가 테스트용 로드 또는 [기간 업무 앱](/intune/apps/lob-apps-windows)을 신뢰할 수 있습니다. 인증서는 "디바이스"를 사용할 경우 HKLM/루트에 저장되거나 "사용자"를 사용할 경우 HKCU에 저장되는 로컬 시스템 인증서 저장소에 있습니다.

## <a name="defender-protections"></a>Defender 보호
HoloLens 2는 Microsoft 서비스를 사용하여 사용자에게 고급 보안 수준을 제공합니다.

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)은 OS에 의해 Windows Holographic에서 자동으로 사용하도록 설정되며 피싱 및 악성 프로그램뿐만 아니라 잠재적인 악성 파일이 Edge에서 다운로드되는 것을 방지합니다. 사용자가 끌 수 없지만 정책을 통해 비활성화할 수 있습니다.

* [Defender 방화벽](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)은 디바이스를 드나드는 무단 네트워크 트래픽을 차단합니다. 기본적으로 사용되며 로컬 작업 또는 정책을 통해 고객이 구성할 수 없습니다. 

* [Windows Defender 애플리케이션 제어](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2는 IT 관리자가 애플리케이션 제어 정책을 디바이스에 푸시할 수 있는 WDAC를 지원합니다. 자세한 내용은 [MSFT Intune으로 HoloLens 2 디바이스에서 WDAC 사용](/mem/intune/configuration/custom-profile-hololens)에서 찾을 수 있습니다. 

IT 관리자는 [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)을 통해 SmartScreen 동작을 관리하고 [이 정책](/windows/client-management/mdm/policy-csps-supported-by-hololens2)을 통해 브라우저 동작을 관리할 수 있습니다. 

