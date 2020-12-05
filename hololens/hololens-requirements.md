---
title: 상용 환경에서 HoloLens 설정
description: 엔터프라이즈 환경에서 HoloLens를 배포하고 관리하는 방법을 자세히 알아보십시오.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
ms.openlocfilehash: 5f24d62193f083f96144b7e8c3518dc97c14be68
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195591"
---
# HoloLens 2 엔터프라이즈 배포 및 관리

이 개요는 IT 전문가가 엔터프라이즈 내에서 Microsoft HoloLens 2 장치를 배포하고 관리하기 위한 고려 사항을 이해하는 데 도움이 됩니다.

HoloLens 2는 강력하고 유연한 기본 제공 모바일 장치 및 앱 관리 기술을 조직에 제공하는 Windows 10 Holographic에서 실행됩니다. Windows 10 Holographic은 종단 내 장치 수명 주기 관리를 지원하여 회사에서 장치, 데이터 및 앱을 제어할 수 있도록 합니다. HoloLens 2는 포괄적인 모바일 장치 관리 솔루션을 사용하여 장치 등록, 구성 및 응용 프로그램 관리에서 유지 관리 및 사용 중지까지 표준 수명 주기 관행에 쉽게 통합할 수 있습니다.

## 준비

회사 엔터프라이즈 환경에 HoloLens 2를 배포할 준비를 할 때 HoloLens 2의 확장 배포 계획을 시작할 때 검토하고 이해해야 할 몇 가지 고려 사항이 있습니다.

### Infrastructure Essentials

회사 엔터프라이즈 배포 시나리오의 HoloLens 2에는 전체 기능 집합을 지원하는 데 필요한 특정 필수 인프라 서비스가 있습니다. HoloLens 2는 배포 및 관리를 [위해](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 최신 모바일 장치 관리를 염두에 두어 설계되었습니다. Azure AD 가입 + MDM을 통해 모바일 인력이 증가하고 있습니다. 아래 항목에서는 HoloLens 2에 대한 배포 계획에서 고려해야 하는 각 인프라 구성 요소에 대한 간략한 개요를 제공합니다.

### Azure Active Directory
Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. 기존 온-프레미스 디렉터리와 통합하여 하이브리드 ID 솔루션을 만들 수 있습니다. Microsoft Office 365 또는 Intune을 사용하는 조직은 이미 무료, 프리미엄 P1 및 Premium P2의 세 가지 버전이 있는 Azure AD를 사용하고 [있습니다(Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions/)참조). 모든 버전은 Azure AD 장치 등록을 지원하지만 MDM 자동 등록을 사용하려면 Premium P1이 필요합니다. HoloLens 2에서는 대부분의 엔터프라이즈 수준 기능을 사용하려면 Azure Active Directory 가입이 필요합니다.

> [!NOTE]
> HoloLens 2에서는 프레미스 Active Directory 조인이 지원되지 않습니다.

### 모바일 장치 관리
HoloLens 2는 엔터프라이즈 환경에서 MDM(모바일 장치 관리) 시스템에서 관리하도록 특별히 설계되었습니다. Enterprise Mobility + Security의 일부인 Microsoft [Intune은](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)엔터프라이즈에서 장치를 관리하는 클라우드 기반 MDM 시스템입니다. Office 365와 마찬가지로 Intune은 ID 관리를 위해 Azure AD를 사용 하여 직원이 Office 365에 로그인하는 데 사용하는 동일한 자격 증명을 사용하여 Intune에 장치를 등록합니다. 여러 MDM 시스템이 Windows 10을 지원하고 개인 및 회사 장치 배포 시나리오를 지원합니다. MDM 시스템은 HoloLens 2에 대한 응용 프로그램 배포 및 업데이트도 관리할 수 있습니다. HoloLens 2를 지원하는 다른 MDM 공급자에는 현재 AirWatch, MobileIron 등이 포함됩니다. 모든 MDM 시스템 공급업체는 Windows 10 CSP(장치 관리 구성 서비스 공급자)에 동등하게 액세스할 수 있습니다. 이를 통해 IT 조직은 Microsoft Intune 또는 타사 MDM 제품 등 관리 요구 사항에 가장 적합한 시스템을 자유롭게 선택할 수 있습니다.

> [!NOTE]
> System Center Configuration Manager와 같은 기존 프레미스 PC 관리 시스템은 HoloLens 2에서 지원되지 않습니다.

### 비즈니스용 Windows 업데이트
Microsoft는 장치 그룹에 업데이트를 배포하고 업데이트 설치를 위해 유지 관리 기간을 정의하는 기능 같은 추가 Windows 업데이트 중심 관리 기능을 IT 관리자에게 제공하는 비즈니스용 Windows 업데이트를 설계했습니다. HoloLens 2 업데이트 관리에 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://docs.microsoft.com/hololens/hololens-updates)

### 인증서
환경에서 Corp 네트워크 인증 또는 다른 리소스에 대한 액세스 또는 Corp Wi-Fi 인증서가 필요한 경우 HoloLens 2는 MDM을 통해 인증서 배포를 지원합니다. 일부 MDM 인프라 구성은 HoloLens 2에 인증서를 배포할 수 있도록 설정해야 할 수 있습니다. [HoloLens 2에](https://docs.microsoft.com/hololens/hololens-certificates-network)대한 인증서 및 네트워크 프로필을 준비하는 방법을 읽어 읽습니다. Intune 세부 정보는 여기에서 찾을 수 [있습니다.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## 구성

MDM 관리자는 MDM 시스템에 등록된 모든 회사 장치에서 정책 설정을 정의하고 구현할 수 있습니다. 사용하는 구성 설정은 배포 시나리오에 따라 다릅니다. Windows 10에서 CSP(구성 서비스 공급자)는 장치에서 구성 설정을 읽고, 설정하고, 수정하거나, 삭제할 수 있는 인터페이스입니다. 이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다. HoloLens 2용 Windows 10 장치 관리 CSP에 대한 자세한 내용은 HoloLens 장치에서 지원되는 [CSP의 전체 목록을 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2는 사용자 지정 프로비저닝 패키지를 통해 제한된 CSP 구성 집합 설정도 지원됩니다. 프로비저닝 패키지는 일반적으로 MDM이 아닌 관리 장치에 활용되고 각 장치에 수동으로 적용해야 합니다. 사용자 지정 프로비저닝 패키지를 구축하는 데 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://docs.microsoft.com/hololens/hololens-provisioning)

> [!NOTE]
> HoloLens 2는 회사 Windows 10 장치 구성을 관리하기 위한 쉽고 간단한 프로세스를 제공하는 [Windows Autopilot을](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)지원합니다.

### ID 관리

직원은 하나의 계정만 사용하여 장치를 초기화할 수 있으므로 조직에서 먼저&#39;계정을 제어해야 합니다. 선택하는 계정이 장치를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다. HoloLens 2는 로컬 사용자 계정, 개인 Microsoft 계정 및 Azure Active Directory 계정의 세 가지 계정 유형을 지원합니다. HoloLens 2 디바이스에서 모든 기능을 사용할 수 있도록 하여 엔터프라이즈 ID 관리 솔루션에 Azure Active Directory를 활용하는 것이 좋습니다. HoloLens 2의 ID에 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://docs.microsoft.com/hololens/hololens-identity)

### 네트워크 및 연결

HoloLens 2는 클라우드 첫 번째 장치이기 위해 모든 기능을 사용하려면 온라인 리소스에 대한 네트워크 액세스가 필요합니다. 회사 인트라넷 네트워크에 연결하여 HoloLens 2 장치를 배포하는 경우 HoloLens 2 클라우드 서비스에 대한 액세스를 허용하도록 프록시/방화벽 규칙을 업데이트해야 할 수 있습니다. HoloLens 2 운영 체제에 필요한 공통 끝점 목록은 여기에서 찾을 수 [있습니다.](https://docs.microsoft.com/hololens/hololens-offline) HoloLens 2에서 응용 프로그램 또는 기타 클라우드 서비스를 성공적으로 실행하려면 추가 끝점에 액세스해야 할 수 있습니다.

추가 끝점 액세스가 필요한 몇 가지 일반적인 HoloLens 2 서비스는 다음과 같습니다.

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 가이드](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 원격 지원(O365 Teams 인프라)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 인증서 배포

회사 Wi-Fi 네트워크 또는 조직 내의 다른 서비스에 액세스하는 데 인증서가 필요한 경우 HoloLens 2는 MDM을 통한 사용자 및 장치 인증서 배포를 지원합니다. 참고: MDM 솔루션에서 Windows 10 디바이스에 인증서를 배포하려면 추가 인프라 구성이 필요할 수 있습니다.

### 보안 검토

대부분의 엔터프라이즈 IT 부서에서는 회사 엔터프라이즈 네트워크에 배포되는 새 장치를 평가하고 검토해야 합니다. 조직에서 HoloLens 2에 대한 보안 검토를 요구하는 경우 여기에서 보안 승인 획득을 지원하기 위해 더 많은 세부 정보를 찾을 [수 있습니다.](https://docs.microsoft.com/hololens/security-overview)

### 일반적인 HoloLens 2 장치 설정

HoloLens 2 장치를 회사 엔터프라이즈 환경에 배포할 때 HoloLens 2의 배포를 계획할 때 고려할 수 있는 여러 일반적인 장치 구성이 있습니다. 이 목록에서는 매우 일반적인 것으로 확인된 구성 및 설정을 강조 표시하며 사용 가능한 옵션의 전체 목록으로 구성되지 않습니다.

| 장치 설정 | 간단한 설명입니다.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [하드웨어 제한](hololens-requirements.md#hardware-restrictions)               | 하드웨어 제한으로 인해 연결이 줄어들고 데이터 보호가 지원됩니다.                        |
| [Wi-Fi 프로필](hololens-requirements.md#wi-fi-profiles)               | 사용자 Wi-Fi 조작 없이 프로필을 구성합니다.                              |
| [인증서](hololens-requirements.md#certificates-1)               | 웹 콘텐츠의 계정 및/또는 Wi-Fi, VPN 암호화 및 SSL 암호화를 제공합니다. |
| [Proxy (프록시)](hololens-requirements.md#proxy)              | 내부 트래픽 관리                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 회사 인트라넷의 앱 및 리소스에 대한 액세스를 제어합니다.                               |
| [키오스크 모드](hololens-requirements.md#kiosk-mode) | UI를 통해 사용자에게 제공된 응용 프로그램을 제한합니다. |

#### 하드웨어 제한

HoloLens 2는 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스 및 Wi-Fi와 같은 인기 하드웨어 기능을 포함하는 최첨단 기술을 사용합니다. 이러한 기능의 가용성을 제어하는 데 하드웨어 제한을 사용할 수 있습니다.

다음 목록에는 HoloLens 2에서 하드웨어 제한을 구성하기 위해 지원하는 가장 일반적으로 사용되는 MDM 설정이 나열됩니다. 이러한 하드웨어 제한 중 일부는 연결을 제공하고 데이터 보호에 도움이 됩니다.

- [**WiFi 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 디바이스에서 디바이스에서 Wi-Fi 및 사용할 수 있는지 여부
- [**USB 연결을 허용합니다.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 연결을 사용할 수 있는지 여부(USB&#39;영향을 주지 않습니다.
- [**다음 Bluetooth.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 디바이스에서 디바이스에서 Bluetooth 및 사용할 수 있는지 여부

다른 일반적인 장치 [제한에 대해 자세히 읽어 읽습니다.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Wi-Fi 프로필

대부분의 회사 Wi-Fi 네트워크에서는 인증서와 기타 복잡한 정보를 요구하여 사용자 액세스를 제한하고 보안을 유지합니다. 이 고급 Wi-Fi 정보는 일반 사용자가 구성하기는 어렵지만 MDM 시스템은 사용자 개입 없이 이러한 Wi-Fi 프로필을 완전히 구성할 수 있습니다. MDM 시스템에서는 여러 개의 Wi-Fi 프로필을 만들 수 있습니다.

Windows 10에 대한 Wi-Fi 설정에 대한 자세한 내용은 엔터프라이즈 프로필 WiFi 설정을 [참조하세요.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### 인증서

인증서는 웹 콘텐츠의 계정 인증, Wi-Fi 인증, VPN 암호화 및 SSL 암호화를 제공하여 보안을 향상시키는 데 도움이 됩니다. 관리자는 프로비저닝 패키지를 통해 장치에서 인증서를 수동으로 관리할 수 있지만&#39;MDM 시스템을 사용하여 등록부터 갱신 및 해지까지 전체 수명 주기 동안 해당 인증서를 관리하는 것이 가장 좋은 모범 사례입니다. MDM 시스템에서 SCEP(Simple Certificate Enrollment Protocol) 또는 PKCS##12 12(공개 키 암호화 표준)를 지원하는 경우&#39; 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다. 또한 MDM은 등록된 클라이언트 인증서를 쿼리 및 삭제하거나 현재 인증서가 만료되기 전에 새 등록 요청을 트리거할 수 있습니다.

[HoloLens 2에](https://docs.microsoft.com/hololens/hololens-certificates-network) 대한 인증서 및 네트워크 프로필을 준비하는 방법에 대해 자세히 알아보세요.

#### Proxy (프록시)

대부분의 회사 인트라넷 네트워크는 프록시를 사용하여 내부 트래픽을 관리합니다. HoloLens 2를 사용하면 이더넷 및 서버 연결에 대한 프록시 Wi-Fi 수 있습니다. 이 설정은 VPN 연결에 적용되지 않습니다.

Windows 10의 프록시 설정에 대한 자세한 내용은 [NetworkProxy CSP를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### VPN

조직은 종종 VPN을 사용하여 회사 또는 인트라넷에서 앱 및 리소스에&#39;제어합니다. HoloLens 2는 Microsoft Store에서 다운로드 가능한 플러그 인이 필요하며 선택한 VPN 공급업체와 관련이 있는 SSL VPN 연결을 지원합니다.

VPN 프로필에 대한 자세한 내용은 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)를 참조하세요.

#### 키오스크 모드

키오스크 모드에서 실행하도록 디바이스를 구성하여 HoloLens 2 장치가 키오스크라고도 하는 고정 용도의 장치로 작동하도록 구성할 수 있습니다. 키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램(또는 사용자)을 제한합니다. 키오스크 모드는 비즈니스 앱에 HoloLens 2 장치를 전담하거나 앱 데모에서 HoloLens 2 장치를 사용하는 데 사용할 수 있는 편리한 기능입니다.

키오스크 모드에서 HoloLens 2를 구성하는 자세한 내용은 [설치 HoloLens를 키오스크로 참조](https://docs.microsoft.com/hololens/hololens-kiosk)

## 배포

### MDM 장치 등록

엔터프라이즈 배포의 경우 Azure [enroll devices](https://docs.microsoft.com/hololens/hololens-enroll-mdm) AD 가입 및 자동 MDM 등록(AAD+MDM)을 사용하여 장치를 회사 장치로 MDM에 등록하는 것이 좋습니다. 이를 위해서는 Azure AD Premium이 필요하며 Intune을 비롯한 여러 MDM 공급자에 대한 자동 등록이 지원됩니다.

자동 배포 등록 방법 [Autopilot에 대해 자세히 알아보고](https://docs.microsoft.com/hololens/hololens2-autopilot)

### 응용 프로그램 배포

모바일 장치에서 사용자 생산성은 앱을 통해 상승되는 경우가 많습니다.

Windows 10에서는 Windows 앱용 UWP(유니버설 Windows 플랫폼)를 사용하여 여러 장치에서 원활하게 작동하는 앱을 개발할 수 있습니다.

HoloLens 2 장치에 응용 프로그램을 배포하는 방법에는 여러 가지가 있습니다. MDM, 비즈니스용 Microsoft Store를 통해 직접 앱을 배포하거나 프로비저닝 패키지를 통해 테스트용 로드할 수 있습니다. 앱 [배포에 대한 자세한 내용은 여기에서 찾을 수 있습니다.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2는 UWP ARM64 앱 실행만 지원합니다.

## 유지 관리

엔터프라이즈 IT 환경에서는 보안과 비용 조정에 대한 필요성과 사용자에게 최신 기술을 제공하고 싶은 욕구 사이에 균형을 맞춰야 합니다. 사이버 공격이 일상적으로 발생하고 있는 것이기 때문에 Windows 10 장치의 상태를 제대로 유지 관리하는 것이 중요합니다. IT 부서는 내부 응용 프로그램에 액세스할 수 있는 장치를 적용할 뿐 아니라 구성 설정을 관리하여 규정을 준수하도록 관리해야 합니다. HoloLens 2는 장치가 회사 정책을 준수하는지 보장하는 데 필요한 모바일 작업 관리 기능을 제공합니다.

### OS 서비스 옵션

**간소화된 업데이트 프로세스**

Microsoft는 Windows 제품 엔지니어링 및 릴리스 주기를 간소화하였기 때문에, 그 어느 때보다도 빠르게 시장에서 원하는 새 기능과 환경, 특징을 제공할 수 있습니다. Microsoft는 1년(12개월간)에 기능 업데이트를 두 번 제공할 예정입니다. **기능 업데이트는** 현재 분기 또는 CB를 설정하고 연결된 버전을 가 있습니다.

Microsoft는 또한 HoloLens 2 장치에 보안 및 안정성을 위한 업데이트를 직접 전달하고 설치합니다. Windows **업데이트를 통해** Microsoft 제어에 따라 릴리스된 이러한 품질 업데이트는 월간 사용할 수 있습니다. HoloLens 2는 동일한 표준 업데이트 프로세스의 일부로 기능 업데이트 및 품질 업데이트를 사용 합니다.

엔터프라이즈 고객은 MDM 시스템을 사용하여 HoloLens 2s에서 업데이트 환경 및 프로세스를 관리할 수 있습니다. 대부분의 경우 업데이트 프로세스 관리 정책이 기능 업데이트와 품질 업데이트에 모두 적용됩니다. [HoloLens 업데이트에 대한 MDM](https://docs.microsoft.com/hololens/hololens-updates)구성에 대한 자세한 내용입니다.

### 응용 프로그램 관리

IT 관리자는 HoloLens 2에 설치할 수 있는 앱과 최신으로 유지되는 방법을 제어할 수 있습니다.

HoloLens 2는 Windows Defender 응용 프로그램 [제어(WDAC)를](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)지원하여 관리자가 Microsoft Store에서 앱 목록을 만들거나 허용하거나 허용하지 않습니다. 이 기능은 기본 제공 앱으로도 확장됩니다. 앱을 허용하거나 거부하는 기능은 사용자가 의도한 용도로 디바이스를 사용할 수 있도록 하는 데 도움이 됩니다. 그러나 직원이 필요로 하는 것이나 요청한 것과 보안 문제의 균형점을 찾으려는 것이 늘 쉽지만은 않습니다. 허용 또는 비허용 목록을 만들려면 Microsoft Store의 변하는 앱 환경을 잘 알고 있어야 합니다.

자세한 내용은 응용 프로그램 제어 [CSP를 참조합니다.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### 사용 중지

장치 사용 중지는 장치 수명 주기의 마지막 단계입니다. 또한&#39;기밀성을 손상시킬 수 있는 삭제된 장치에 회사 데이터를&#39;원하지 않는 경우 새 모델로 교체되는 장치를 안전하게 폐기하는 것이 중요합니다. IT 부서는 분실하거나 도난당한 장치를 지워야 하는 사용자를 올바르게 지원할 수 있는 방법도 있어야 합니다.

HoloLens 2는 장치를 지우는 세 가지 방법을 지원

**MDM 공장 지우기:** 관리자가 시작한 MDM 명령을 통해 HoloLens 2를 공장 이미지로 다시 초기화합니다. 디바이스에 저장된 모든 데이터를 지울 수 있습니다.

**설정 내에서 장치 초기화:** 최종 사용자는 디바이스의 설정 앱 내에서 HoloLens 2를 수동으로 다시 설정할 수 있습니다. 디바이스에 저장된 모든 데이터를 지울 수 있습니다.

**ARC(Advanced Recovery Companion):** ARC 도구를 실행하는 PC에서 사용자 또는 관리자는 USB 케이블을 통해 PC에 연결된 HoloLens 2를 플래시할 수 있습니다. 디바이스에 저장된 모든 데이터를 지울 수 있습니다.

> [!div class="nextstepaction"]
> [일반적인 배포 시나리오](common-scenarios.md)