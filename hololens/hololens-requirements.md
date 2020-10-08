---
title: 상업적 환경에서 HoloLens 설정
description: 엔터프라이즈 환경에서 HoloLens를 배포 하 고 관리 하는 방법에 대해 자세히 알아보세요.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/30/2020
ms.openlocfilehash: b7523b8ab38cfc37795ea6c99f9b22953baffe47
ms.sourcegitcommit: 30e910348f5d5b68e914219c8eadb34d93770eab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "11099807"
---
# HoloLens 2 엔터프라이즈 배포 및 관리

이 개요는 IT 전문가가 엔터프라이즈 내에서 Microsoft HoloLens 2 디바이스를 배포 하 고 관리 하기 위한 고려 사항을 이해 하는 데 도움을 주기 위한 것입니다.

HoloLens 2는 조직에 강력 하 고 유연한 기본 제공 모바일 장치 및 앱 관리 기술을 제공 하는 Windows 10 홀로그램에서 실행 됩니다. Windows 10 홀로그램는 회사에서 장치, 데이터 및 앱을 제어할 수 있도록 종단 간 디바이스 수명 주기 관리를 지원 합니다. HoloLens 2는 표준 수명 주기 방법, 장치 등록, 구성, 응용 프로그램 관리에서 종합적인 모바일 장치 관리 솔루션을 사용 하 여 유지 관리 및 폐기에 간편 하 게 통합할 수 있습니다.

## 준비

HoloLens 2를 회사 엔터프라이즈 환경에 배포 하려고 할 때 HoloLens 2 배포 계획을 수립할 때 검토 및 이해 해야 할 몇 가지 고려 사항이 있습니다.

### 인프라 주요 사항

기업 엔터프라이즈 배포 시나리오에서 HoloLens 2의 경우 전체 기능을 지 원하는 데 필요한 특정 인프라 서비스가 있습니다. HoloLens 2는 배포 및 관리에 대 한 [최신 모바일 장치 관리](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 를 염두에 두어야 합니다. 다양 한 모바일 인력을 구현 하는 주요 방법으로 Azure AD 참가 + MDM을 사용 합니다. 다음 항목에서는 HoloLens 2 배포 계획에서 고려해 야 하는 각 인프라 구성 요소에 대해 간략하게 설명 합니다.

### Azure Active Directory
Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. 기존 온-프레미스 디렉터리와 통합하여 하이브리드 ID 솔루션을 만들 수 있습니다. Microsoft Office 365 또는 Intune을 사용 하는 조직에는 무료, Premium P1 및 Premium P2와 같은 세 가지 버전이 있는 Azure AD가 이미 사용 중입니다 ( [Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions/)참조). 모든 에디션은 Azure AD device registration을 지원 하지만, MDM 자동 등록을 사용 하려면 Premium P1이 필요 합니다. HoloLens 2에서는 대부분의 enterprise 수준 기능을 사용 하도록 설정 하는 데 Azure Active Directory 조인이 필요 합니다.

> [!NOTE]
> 온-프레미스 Active Directory 조인은 HoloLens 2에서 지원 되지 않습니다.

### 모바일 장치 관리
HoloLens 2는 엔터프라이즈 환경에서 MDM (모바일 디바이스 관리) 시스템을 통해 관리 하도록 특별히 설계 되었습니다. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)(enterprise Mobility + Security의 일부)은 엔터프라이즈에서 장치를 관리 하는 클라우드 기반 MDM 시스템입니다. Office 365와 마찬가지로 Intune에서는 id 관리에 Azure AD를 사용 하므로, 직원이 Office 365에 로그인 하는 데 사용 하는 것과 동일한 자격 증명을 사용 하 여 Intune에서 디바이스를 등록 합니다. 여러 MDM 시스템이 Windows 10을 지원하고 개인 및 회사 장치 배포 시나리오를 지원합니다. 또한, MDM 시스템은 HoloLens 2에 대 한 응용 프로그램 배포 및 업데이트만 관리할 수 있습니다. 다음은 HoloLens 2를 지 원하는 다른 MDM 공급자에 게는 현재 MobileIron입니다. 모든 MDM 시스템 공급 업체는 Windows 10 장치 관리 서비스 공급자 (CSP)에 동일한 액세스 권한을 가지 며, IT 조직이 해당 관리 요구 사항에 가장 적합 한 시스템 (Microsoft Intune 또는 타사 MDM 제품)을 선택할 수 있는 자유를 제공 합니다.

> [!NOTE]
> 시스템 센터 구성 관리자와 같은 전통적인 온 온 프레미스 PC 관리 시스템은 HoloLens 2에서 지원 되지 않습니다.

### 비즈니스용 Windows 업데이트
Microsoft는 장치 그룹에 업데이트를 배포하고 업데이트 설치를 위해 유지 관리 기간을 정의하는 기능 같은 추가 Windows 업데이트 중심 관리 기능을 IT 관리자에게 제공하는 비즈니스용 Windows 업데이트를 설계했습니다. HoloLens 2 업데이트를 관리 하는 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/hololens/hololens-updates)를 참조 하세요.

### 인증서
HoloLens 2는 환경에 Corp Wi-fi 네트워크 인증 또는 다른 리소스에 대 한 액세스를 위한 인증서가 필요한 경우 MDM을 통한 인증서 배포를 지원 합니다. 일부 MDM 인프라 구성은 HoloLens 2에 대 한 인증서 배포를 사용 하도록 설정 해야 할 수 있습니다. [HoloLens 2에 대 한 인증서 및 네트워크 프로필을 준비](https://docs.microsoft.com/hololens/hololens-certificates-network)하는 방법에 대해 자세히 알아보세요. Intune 세부 정보는 [여기](https://docs.microsoft.com/mem/intune/protect/certificates-configure)에서 찾을 수 있습니다.

## 구성

MDM 관리자는 MDM 시스템에 등록 된 모든 회사 장치에서 정책 설정을 정의 하 고 구현할 수 있습니다. 사용 하는 구성 설정은 배포 시나리오에 따라 다릅니다. Windows 10의 경우 CSP (구성 서비스 공급자)는 디바이스에서 구성 설정을 읽고, 설정, 수정 또는 삭제 하는 인터페이스입니다. 이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다. HoloLens 2 용 Windows 10 장치 관리 Csp에 대 한 자세한 내용은 [hololens 장치에서 지원 되는 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)의 전체 목록을 참조 하세요.

HoloLens 2는 또한 사용자 지정 배포 패키지를 통해 제한 된 CSP 구성 집합을 설정할 수 있도록 지원 합니다. 일반적으로 프로 비전 패키지는 MDM이 아닌 관리 장치에 활용 되며 각 장치에 수동으로 적용 해야 합니다. 사용자 지정 프로비저닝 패키지를 작성 하는 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/hololens/hololens-provisioning)를 참조 하세요.

> [!NOTE]
> HoloLens 2는 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)지원 하 여 기업 windows 10 장치 구성을 관리 하기 위한 쉽고 간단한 프로세스를 제공 합니다.

### Id 관리

직원은 하나의 계정만 사용 하 여 장치를 초기화할 수 있으므로, 조직에서 어떤 계정이 먼저 설정 되었는지 제어 하도록 하는 것을 필수적으로&#39;합니다. 선택하는 계정이 장치를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다. HoloLens 2는 세 가지 계정 유형 (로컬 사용자 계정, 개인 Microsoft 계정, Azure Active Directory 계정)을 지원 합니다. HoloLens 2 장치에서 모든 기능을 사용할 수 있으므로 엔터프라이즈 id 관리 솔루션에 대해 Azure Active Directory를 활용 하는 것이 좋습니다. HoloLens 2의 Id에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/hololens/hololens-identity)를 참조 하세요.

### 네트워크 및 연결

HoloLens 2는 클라우드 첫 번째 장치 이므로 모든 기능을 사용할 수 있도록 온라인 리소스에 대 한 네트워크 액세스가 필요 합니다. 회사 인트라넷 네트워크에 대 한 연결을 사용 하 여 HoloLens 2 장치를 배포 하는 경우 HoloLens 2 클라우드 서비스에 대 한 액세스를 허용 하도록 프록시/방화벽 규칙을 업데이트 해야 할 수 있습니다. HoloLens 2 운영 체제에 필요한 공통 끝점 목록은 [여기](https://docs.microsoft.com/hololens/hololens-offline)에서 찾을 수 있습니다. 다른 끝점에 대 한 액세스는 HoloLens 2에서 응용 프로그램 또는 기타 클라우드 서비스를 실행 하는 데 필요할 수 있습니다.

추가 끝점 액세스가 필요한 일부 일반적인 HoloLens 2 서비스는 다음과 같습니다.

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 가이드](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 원격 지원 (O365 팀 인프라)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 인증서 배포

기업 Wi-fi 네트워크 또는 조직 내 다른 서비스에 액세스 하기 위해 인증서가 필요한 경우 HoloLens 2는 MDM을 통해 사용자 및 장치 인증서 배포를 지원 합니다. 참고: MDM 솔루션에는 Windows 10 장치에 인증서를 배포 하기 위한 추가 인프라 구성이 필요할 수 있습니다.

### 보안 검토

대부분의 엔터프라이즈 IT 부서에서는 회사 엔터프라이즈 네트워크에 배포 되는 새 장치에 대 한 평가 및 검토가 필요 합니다. 조직에 HoloLens 2에 대 한 보안 검토가 필요한 경우 [에는 보안 승인을 받기 위해 여기에 대 한 세부 정보를 확인할](https://docs.microsoft.com/hololens/security-overview)수 있습니다.

### 일반 HoloLens 2 장치 설정

HoloLens 2 장치를 기업 엔터프라이즈 환경에 배포 하는 경우 HoloLens 2 배포를 계획할 때 고려해 야 할 몇 가지 일반적인 장치 구성이 있습니다. 이 목록에는 매우 일반적으로 사용 되는 구성 및 설정이 강조 표시 되어 있으며 사용할 수 있는 옵션의 전체 목록으로 구성 되어 있지 않습니다.

| 장치 설정 | 간략 한 설명입니다.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [하드웨어 제한](hololens-requirements.md#hardware-restrictions)               | 하드웨어 제한은 데이터 보호에 대 한 연결성을 줄이며 지원 합니다.                        |
| [Wi-Fi 프로필](hololens-requirements.md#wi-fi-profiles)               | 사용자 간섭 또는 조작 없이 Wi-fi 프로필을 구성 합니다.                              |
| [인증서](hololens-requirements.md#certificates-1)               | 계정 및/또는 Wi-fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공 합니다. |
| [Proxy (프록시)](hololens-requirements.md#proxy)              | 내부 트래픽을 관리 합니다.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 회사 인트라넷의 앱 및 리소스에 대 한 액세스를 제어 합니다.                               |
| [키오스크 모드](hololens-requirements.md#kiosk-mode) | UI를 통해 사용자에 게 제공 되는 응용 프로그램을 제한 합니다. |

#### 하드웨어 제한

HoloLens 2는 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스, Wi-fi 등 인기 있는 하드웨어 기능을 포함 하는 최신 기술을 사용 합니다. 이러한 기능의 가용성을 제어하는 데 하드웨어 제한을 사용할 수 있습니다.

다음 목록에는 HoloLens 2에서 하드웨어 제한을 구성할 수 있도록 가장 일반적으로 사용 되는 MDM 설정이 나와 있습니다. 이러한 하드웨어 제한 중 일부는 연결을 제공하고 데이터 보호에 도움이 됩니다.

- [**WiFi 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 장치에서 Wi-fi 라디오를 사용 하도록 설정 하 고 사용할 수 있는지 여부
- [**USB 연결 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 연결이 사용 되는지 여부 (&#39;t USB 충전에 영향을 미치지 않음)
- [**블루투스 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 장치에서 Bluetooth 라디오를 사용 하도록 설정 하 고 사용할 수 있는지 여부

다른 [일반적인 장치 제한 사항](https://docs.microsoft.com/hololens/hololens-common-device-restrictions) 에 대해 자세히 알아보세요.

#### Wi-Fi 프로필

대부분의 회사 Wi-Fi 네트워크에서는 인증서와 기타 복잡한 정보를 요구하여 사용자 액세스를 제한하고 보안을 유지합니다. 이 고급 Wi-fi 정보는 일반적인 사용자가 구성 하는 데 어려움이 있지만, MDM 시스템은 사용자 간섭 없이 이러한 Wi-fi 프로필을 완전히 구성할 수 있습니다. MDM 시스템에서는 여러 개의 Wi-Fi 프로필을 만들 수 있습니다.

Windows 10 용 Wi-fi 설정에 대 한 자세한 내용은 [엔터프라이즈 프로필 WiFi 설정을](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)참조 하세요.

#### 인증서

인증서는 계정 인증, Wi-fi 인증, VPN 암호화, 웹 콘텐츠의 SSL 암호화를 제공 하 여 보안을 개선 하는 데 도움이 됩니다. 관리자는 프로 비전 패키지를 통해 디바이스에서 수동으로 인증서를 관리할 수 있지만, 사용자는 MDM 시스템을 사용 하 여 전체 수명 주기 동안 해당 인증서를 관리 하는 것&#39;이 좋습니다 (등록-갱신 및 해지). Mdm 시스템에서 SCEP (단순 인증서 등록 프로토콜) 또는 공개 키 암호화 표준 #12 (PKCS # 12))을 지 원하는 경우 디바이스를 등록 한 후 해당 장치&#39; 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다. 또한 현재 인증서가 만료 되기 전에, MDM이 등록 된 클라이언트 인증서를 쿼리하거나 삭제 하거나 새 등록 요청을 트리거할 수 있습니다.

[HoloLens 2에 대 한 인증서 및 네트워크 프로필을 준비](https://docs.microsoft.com/hololens/hololens-certificates-network) 하는 방법에 대해 자세히 알아보세요.

#### Proxy (프록시)

대부분의 기업 인트라넷 네트워크는 프록시를 이용 하 여 내부 트래픽을 관리 합니다. HoloLens 2를 사용 하 여 이더넷과 Wi-fi 연결을 위한 프록시 서버를 구성할 수 있습니다. 이 설정은 VPN 연결에 적용되지 않습니다.

Windows 10의 프록시 설정에 대 한 자세한 내용은 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)를 참조 하세요.

#### VPN

조직에서 VPN을 사용 하 여 회사&#39;s 인트라넷에 있는 앱과 리소스에 대 한 액세스를 제어 하는 경우가 많습니다. HoloLens 2는 Microsoft Store에서 다운로드할 수 있는 플러그인이 필요한 SSL VPN 연결을 지원 하며, 사용자가 선택한 VPN 공급 업체에만 해당 됩니다.

VPN 프로필에 대한 자세한 내용은 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)를 참조하세요.

#### 키오스크 모드

장치를 키오스크 모드로 실행 하도록 구성 하 여 HoloLens 2 장치를 고정 용도의 디바이스 (키오스크이 라고도 함)로 작동 하도록 구성할 수 있습니다. 키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램 (또는 사용자)을 제한 합니다. 키오스크 모드는 HoloLens 2 장치를 비즈니스 앱으로 전용 또는 앱 데모에서 HoloLens 2 장치를 사용 하는 데 사용할 수 있는 편리한 기능입니다.

키오스크 모드에서 HoloLens 2를 구성 하는 방법에 대 한 자세한 내용은 [hololens를 키오스크로 설정](https://docs.microsoft.com/hololens/hololens-kiosk)

## 배포

### MDM 장치 등록

엔터프라이즈 배포의 경우 Azure AD 조인과 자동 MDM 등록 (AAD + MDM)을 사용 하 여 디바이스를 MDM에 회사 장치로 [등록](https://docs.microsoft.com/hololens/hololens-enroll-mdm) 하는 것이 좋습니다. Azure AD Premium을 요구 하 고 Intune을 비롯 한 여러 MDM 공급자에 대 한 자동 등록을 지원 합니다.

자동 배포 등록 방법 [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)에 대해 자세히 알아보세요.

### 응용 프로그램 배포

모바일 장치에서 사용자 생산성은 앱을 통해 상승되는 경우가 많습니다.

Windows 10에서는 Windows 앱용 UWP(유니버설 Windows 플랫폼)를 사용하여 여러 장치에서 원활하게 작동하는 앱을 개발할 수 있습니다.

HoloLens 2 장치에 응용 프로그램을 배포 하는 방법에는 여러 가지가 있습니다. MDM, Microsoft Store Business 또는 프로비저닝 패키지를 통해 테스트용으로 로드를 통해 직접 앱을 배포할 수 있습니다. [앱 배포에 대 한 자세한 내용은 여기를 참조](https://docs.microsoft.com/hololens/app-deploy-overview)하세요.

> [!NOTE]
> HoloLens 2는 UWP ARM64 앱의 실행만 지원 합니다.

## 유지 관리

엔터프라이즈 IT 환경에서는 보안과 비용 조정에 대한 필요성과 사용자에게 최신 기술을 제공하고 싶은 욕구 사이에 균형을 맞춰야 합니다. Cyberattacks는 일상적인 항목이 되기 때문에 Windows 10 장치의 상태를 적절히 유지 관리 하는 것이 중요 합니다. IT 부서는 내부 응용 프로그램에 액세스할 수 있는 장치를 적용할 뿐 아니라 구성 설정을 관리하여 규정을 준수하도록 관리해야 합니다. HoloLens 2는 장치가 회사 정책을 준수 하 고 있는지 확인 하는 데 필요한 모바일 작업 관리 기능을 제공 합니다.

### OS 서비스 옵션

**간소화된 업데이트 프로세스**

Microsoft는 Windows 제품 엔지니어링 및 릴리스 주기를 간소화하였기 때문에, 그 어느 때보다도 빠르게 시장에서 원하는 새 기능과 환경, 특징을 제공할 수 있습니다. Microsoft는 1년(12개월간)에 기능 업데이트를 두 번 제공할 예정입니다. **기능 업데이트** 는 현재 분기 또는 CB를 설정 하 고 관련 버전이 있습니다.

Microsoft는 또한 HoloLens 2 장치에 대 한 업데이트를 제공 하 고 보안 및 안정성을 위해 바로 설치 합니다. 이 **품질 업데이트** 는 Windows Update를 통해 Microsoft control에 공개 되며 매달 사용할 수 있습니다. HoloLens 2는 동일한 표준 업데이트 프로세스의 일부로 기능 업데이트 및 품질 업데이트를 사용 합니다.

엔터프라이즈 고객은 MDM 시스템을 사용 하 여 HoloLens 2s의 업데이트 환경 및 프로세스를 관리할 수 있습니다. 대부분의 경우 업데이트 프로세스 관리 정책이 기능 업데이트와 품질 업데이트에 모두 적용됩니다. [HoloLens 업데이트에 대 한 MDM 구성](https://docs.microsoft.com/hololens/hololens-updates)에 자세히 설명 되어 있습니다.

### 응용 프로그램 관리 

IT 관리자는 HoloLens 2에 설치할 수 있는 앱을 제어 하 고 최신 상태를 유지 하는 방법을 제어할 수 있습니다.

HoloLens 2는 관리자가 Microsoft Store에서 앱 목록을 만들거나 허용 하거나 허용 하지 않도록 설정 하는 [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)를 지원 합니다. 이 접근 권한 값은 기본 제공 앱으로도 확장 됩니다. 앱을 허용 하거나 거부 하는 기능은 사용자가 원하는 목적으로 장치를 사용할 수 있도록 하는 데 도움이 됩니다. 그러나 직원이 필요로 하는 것이나 요청한 것과 보안 문제의 균형점을 찾으려는 것이 늘 쉽지만은 않습니다. 허용 또는 비허용 목록을 만들려면 Microsoft Store의 변하는 앱 환경을 잘 알고 있어야 합니다.

자세한 내용은 [응용 프로그램 컨트롤 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)를 참조 하세요.

### 사용 중지

장치 만료는 디바이스 수명의 마지막 단계입니다. 데이터의 기밀성을 훼손 시킬 수 있는 삭제 된 장치에서 회사 데이터를 보존 하 고 있지 않은&#39;경우 새로운 모델로 대체 되는 장치가 안전 하 게 만료&#39;. IT 부서는 분실하거나 도난당한 장치를 지워야 하는 사용자를 올바르게 지원할 수 있는 방법도 있어야 합니다.

HoloLens 2는 장치를 초기화 하는 3 가지 방법을 지원 합니다.

**MDM 팩토리 지우기:** 관리자가 시작한 MDM 명령을 통해 HoloLens 2를 출하시 이미지로 다시 설정 합니다. 장치에 저장 된 모든 데이터를 지웁니다.

**설정 내에서 장치 재설정:** 최종 사용자는 디바이스의 설정 앱 내에서 HoloLens 2를 수동으로 초기화할 수 있습니다. 장치에 저장 된 모든 데이터를 지웁니다.

**고급 복구 도우미 (호):** ARC 도구를 실행 하는 PC에서 사용자 또는 관리자는 USB 케이블을 통해 PC에 연결 된 HoloLens 2를 플래시 할 수 있습니다. 장치에 저장 된 모든 데이터를 지웁니다.
