---
title: 상용 환경에서 HoloLens 설정
description: 인프라, Azure Active Directory 및 모바일 디바이스 관리를 포함하여 엔터프라이즈 환경에서 HoloLens를 배포하고 관리하는 방법에 대해 자세히 알아봅니다.
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
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397224"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>엔터프라이즈 배포 및 관리 HoloLens 2

이 개요는 IT 전문가가 기업 내에서 Microsoft HoloLens 2개 디바이스를 배포하고 관리하기 위한 고려 사항을 이해할 수 있도록 돕기 위한 것입니다.

HoloLens 2 조직에 강력하고 유연한 기본 제공 모바일 디바이스 및 앱 관리 기술을 제공하는 Windows 10 Holographic 실행됩니다. Windows 10 Holographic 엔드 투 엔드 디바이스 수명 주기 관리를 지원하여 회사에서 디바이스, 데이터 및 앱을 제어할 수 있도록 합니다. HoloLens 2 디바이스 등록, 구성 및 애플리케이션 관리에서 포괄적인 모바일 디바이스 관리 솔루션을 사용하는 유지 관리 및 사용 중지에 이르기까지 표준 수명 주기 사례에 쉽게 통합할 수 있습니다.

## <a name="prepare"></a>준비

회사 엔터프라이즈 환경에 HoloLens 2 배포할 준비를 할 때 HoloLens 2 규모 배포를 계획할 때 검토하고 이해해야 하는 몇 가지 고려 사항이 있습니다.

### <a name="infrastructure-essentials"></a>Infrastructure Essentials

회사 엔터프라이즈 배포 시나리오에서 HoloLens 2 경우 전체 기능 집합을 지원하는 데 필요한 특정 필수 인프라 서비스가 있습니다. HoloLens 2 배포 및 관리를 위해 [Modern Mobile 장치 관리](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 염두에 두고 빌드되었습니다. 점점 증가하는 모바일 인력에서 이를 달성하는 기본 수단으로 Azure AD 조인 + MDM을 추가합니다. 아래 항목에서는 HoloLens 2 배포 계획에서 고려해야 하는 각 인프라 구성 요소에 대한 간략한 개요를 제공합니다.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. 기존 온-프레미스 디렉터리에 통합하여 하이브리드 ID 솔루션을 만들 수 있습니다. Microsoft Office 365 또는 Intune을 사용 하는 조직은 Azure AD를 이미 사용 하 고 있습니다 .이는 무료, 프리미엄 P1 및 Premium P2의 세 가지 버전이 있습니다 ( [Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions/)참조). 모든 버전은 Azure AD 장치 등록을 지원 하지만 MDM 자동 등록을 사용 하려면 프리미엄 P1이 필요 합니다. HoloLens 2를 사용 하려면 대부분의 엔터프라이즈 수준 기능과 기능을 사용 하도록 Azure Active Directory 조인이 필요 합니다.

> [!NOTE]
> 온-프레미스 Active Directory 조인은 HoloLens 2에서 지원 되지 않습니다.

### <a name="mobile-device-management"></a>Mobile Device Management
HoloLens 2는 엔터프라이즈 환경에서 MDM (모바일 장치 관리) 시스템에 의해 관리 되도록 특별히 설계 되었습니다. Enterprise Mobility + Security의 일부인 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)은 기업에서 장치를 관리 하는 클라우드 기반 MDM 시스템입니다. Office 365 처럼 Intune은 id 관리를 위해 Azure AD를 사용 하므로 직원 들은 동일한 자격 증명을 사용 하 여 Office 365에 로그인 하는 데 사용 하는 장치를 Intune에 등록 합니다. 여러 MDM 시스템은 Windows 10을 지원 하 고 개인 및 회사 장치 배포 시나리오를 지원 합니다. 또한 MDM 시스템은 HoloLens 2에 대 한 응용 프로그램 배포 및 업데이트도 관리할 수 있습니다. 현재 HoloLens 2를 지 원하는 다른 MDM 공급자에는 현재 MobileIron 및 기타 항목이 포함 됩니다. 모든 MDM 시스템 공급 업체는 Windows 10 CSP (장치 관리 구성 서비스 공급자)에 대 한 동일한 액세스를 제공 하 여 IT 조직에서 Microsoft Intune 또는 타사 MDM 제품에 해당 하는 관리 요구 사항에 가장 적합 한 시스템을 자유롭게 선택할 수 있습니다.

> [!NOTE]
> System Center Configuration Manager와 같은 전통적인 온 프레미스 PC 관리 시스템은 HoloLens 2에서 지원 되지 않습니다.

### <a name="windows-update-for-business"></a>Windows Update for Business
Microsoft는 IT 관리자에 게 장치 그룹에 업데이트를 배포 하 고 업데이트를 설치 하기 위한 유지 관리 기간을 정의 하는 기능과 같은 추가 Windows 업데이트 중심 관리 기능을 제공 하도록 Windows 업데이트 설계 되었습니다. HoloLens 2 업데이트 관리에 대 한 자세한 내용은 [hololens 업데이트](https://docs.microsoft.com/hololens/hololens-updates) 설명서를 참조 하세요.

### <a name="certificates"></a>인증서
HoloLens 2 환경에서 Corp Wi-Fi 네트워크 인증 또는 다른 리소스에 대한 액세스용 인증서가 필요한 경우 MDM을 통한 인증서 배포를 지원합니다. 인증서 배포를 HoloLens 2 위해 일부 MDM 인프라 구성이 필요할 수 있습니다. HoloLens 2 위해 [인증서 및 네트워크 프로필을 준비하는](https://docs.microsoft.com/hololens/hololens-certificates-network)방법에 대해 읽어보기 Intune을 사용하는 경우 [인증 구성](https://docs.microsoft.com/mem/intune/protect/certificates-configure) 세부 정보를 확인하세요.

## <a name="configure"></a>구성

MDM 관리자는 MDM 시스템에 등록된 모든 회사 디바이스에서 정책 설정을 정의하고 구현할 수 있습니다. 사용하는 구성 설정은 배포 시나리오에 따라 달라집니다. Windows 10 CSP(구성 서비스 공급자)는 디바이스에서 구성 설정을 읽고, 설정하고, 수정하거나, 삭제하는 인터페이스입니다. 이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다. HoloLens 2 Windows 10 디바이스 관리 CSP에 대한 자세한 내용은 [HoloLens 디바이스에서 지원되는 CSP의](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)전체 목록을 참조하세요.

HoloLens 2 사용자 지정 프로비저닝 패키지를 통해 제한된 CSP 구성 집합 설정도 지원합니다. 프로비전 패키지는 일반적으로 MDM이 아닌 관리 디바이스에 활용되며 각 디바이스에 수동으로 적용해야 합니다. 사용자 지정 프로비저닝 패키지 빌드에 대한 자세한 내용은 [HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) 프로비저닝 설명서를 참조하세요.

> [!NOTE]
> HoloLens 2 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)를 지원하여 회사 Windows 10 디바이스 구성을 관리하는 쉽고 간단한 프로세스를 제공합니다.

### <a name="identity-management"></a>ID 관리

직원은 하나의 계정만 사용하여 디바이스를 초기화할 수 있으므로 조직에서 먼저 사용하도록 설정된 계정을 제어해야&#39;. 선택한 계정은 디바이스를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다. HoloLens 2 로컬 사용자 계정, 개인 Microsoft 계정 및 Azure Active Directory 계정의 세 가지 계정 유형을 지원합니다. HoloLens 2 디바이스에서 전체 기능을 사용할 수 있도록 하려면 엔터프라이즈 ID 관리 솔루션에 Azure Active Directory 활용하는 것이 좋습니다. Hololens id에 대 한 자세한 내용은 hololens [id](https://docs.microsoft.com/hololens/hololens-identity) 를 확인 하세요.

### <a name="network-and-connectivity"></a>네트워크 및 연결

HoloLens 2는 클라우드 우선 장치 이므로 모든 기능을 사용할 수 있도록 하려면 온라인 리소스에 대 한 네트워크 액세스가 필요 합니다. 회사 인트라넷 네트워크에 연결 된 HoloLens 2 장치를 배포 하는 경우 HoloLens 2 클라우드 서비스에 대 한 액세스를 허용 하도록 프록시/방화벽 규칙을 업데이트 해야 할 수 있습니다. 자세한 내용은 [HoloLens 2 운영 체제에 대 한 일반 끝점](https://docs.microsoft.com/hololens/hololens-offline)목록을 살펴보세요. 응용 프로그램 또는 다른 클라우드 서비스를 HoloLens 2에서 성공적으로 실행 하려면 추가 끝점에 대 한 액세스가 필요할 수 있습니다.

추가 끝점 액세스가 필요한 몇 가지 일반적인 HoloLens 2 서비스는 다음과 같습니다.

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 가이드](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 원격 지원 (O365 팀 인프라)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>인증서 배포

조직 내의 회사 Wi-Fi 네트워크 또는 기타 서비스에 액세스 하기 위해 인증서가 필요한 경우 HoloLens 2는 MDM을 통한 사용자 및 장치 인증서 배포를 지원 합니다. 참고: Windows 10 장치에 인증서를 배포 하려면 MDM 솔루션에 추가 인프라 구성이 필요할 수 있습니다.

### <a name="security-review"></a>보안 검토

대부분의 엔터프라이즈 IT 부서에서는 회사 엔터프라이즈 네트워크에 배포 되는 새 장치를 평가 하 고 검토 해야 합니다. 조직에서 HoloLens 2에 대 한 보안 검토를 요구 하는 경우 [보안 승인을 받는](https://docs.microsoft.com/hololens/security-overview)데 도움이 되는 자세한 정보를 찾을 수 있습니다.

### <a name="common-hololens-2-device-settings"></a>일반적인 HoloLens 2 장치 설정

HoloLens 2 장치를 회사 엔터프라이즈 환경에 배포 하는 경우 HoloLens 2 배포를 계획할 때 고려해 야 할 몇 가지 일반적인 장치 구성이 있습니다. 이 목록에는 매우 일반적인 구성 및 설정이 표시 되며, 사용 가능한 옵션의 전체 목록으로 구성 되지 않습니다.

| 장치 설정 | 간단한 설명입니다.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [하드웨어 제한](hololens-requirements.md#hardware-restrictions)               | 하드웨어 제한은 연결을 줄이고 데이터 보호를 지원합니다.                        |
| [Wi-Fi 프로필](hololens-requirements.md#wi-fi-profiles)               | 사용자 개입 또는 상호 작용 없이 Wi-Fi 프로필을 구성합니다.                              |
| [인증서](hololens-requirements.md#certificates-1)               | 계정 및/또는 Wi-Fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공합니다. |
| [프록시](hololens-requirements.md#proxy)              | 내부 트래픽을 관리합니다.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 회사 인트라넷에서 앱 및 리소스에 대한 액세스를 제어합니다.                               |
| [키오스크 모드](hololens-requirements.md#kiosk-mode) | UI를 통해 사용자에게 제공된 애플리케이션을 제한합니다. |

#### <a name="hardware-restrictions"></a>하드웨어 제한

HoloLens 2 카메라, 마이크, 스피커, USB 인터페이스, Bluetooth 인터페이스 및 Wi-Fi와 같은 인기 있는 하드웨어 기능을 포함하는 최첨단 기술을 사용합니다. 하드웨어 제한을 사용하여 이러한 기능의 가용성을 제어할 수 있습니다.

다음은 하드웨어 제한을 구성하기 위해 HoloLens 2 지원하는 가장 일반적으로 사용되는 MDM 설정을 나열합니다. 이러한 하드웨어 제한 사항 중 일부는 연결을 제공하고 데이터 보호를 지원합니다.

- [**WiFi 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 사용자가 디바이스에서 Wi-Fi 라디오를 사용하도록 설정하고 사용할 수 있는지 여부
- [**USB 연결 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 연결 사용 여부(USB 충전에 영향을&#39;)
- [**Bluetooth 허용:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용자가 디바이스에서 Bluetooth 라디오를 사용하도록 설정하고 사용할 수 있는지 여부

다른 일반적인 [디바이스 제한에](https://docs.microsoft.com/hololens/hololens-common-device-restrictions) 대해 자세히 읽어 보세요.

#### <a name="wi-fi-profiles"></a>Wi-Fi 프로필

대부분의 회사 Wi-Fi 네트워크에서는 사용자 액세스를 제한하고 보호하기 위해 인증서 및 기타 복잡한 정보가 필요합니다. 이 고급 Wi-Fi 정보는 일반 사용자가 구성하기 어렵지만 MDM 시스템은 사용자 개입 없이 이러한 Wi-Fi 프로필을 완전히 구성할 수 있습니다. MDM 시스템에서 여러 Wi-Fi 프로필을 만들 수 있습니다.

Windows 10 대한 Wi-Fi 설정에 대한 자세한 내용은 [엔터프라이즈 프로필 WiFi 설정을 참조하세요.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>인증서

인증서를 사용하면 계정 인증, Wi-Fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공하여 보안을 향상시킬 수 있습니다. 관리자는 프로 비전 패키지를 통해 수동으로 장치에서 인증서를 관리할 수 있지만 등록에서 갱신 및 해지를 통해 MDM 시스템을 사용 하 여 전체 수명 주기 동안 해당 인증서를 관리 하는 것&#39;이 모범 사례입니다. Mdm 시스템은 장치를 등록 한 후 장치를 등록 한 후 인증서 저장소&#39; 장치에 이러한 인증서를 자동으로 배포할 수 있습니다 (MDM 시스템이 단순 인증서 등록 프로토콜 (SCEP) 또는 공개 키 암호화 표준 #12 (PKCS # 12)를 지 원하는 경우). 현재 인증서가 만료 되기 전에 MDM에서 등록 된 클라이언트 인증서를 쿼리 및 삭제 하거나 새 등록 요청을 트리거할 수도 있습니다.

[HoloLens 2에 대 한 인증서 및 네트워크 프로필을 준비](https://docs.microsoft.com/hololens/hololens-certificates-network) 하는 방법에 대해 자세히 알아보세요.

#### <a name="proxy"></a>프록시

대부분의 회사 인트라넷 네트워크는 프록시를 활용 하 여 내부 트래픽을 관리 합니다. HoloLens 2를 사용 하 여 이더넷 및 Wi-Fi 연결에 대 한 프록시 서버를 구성할 수 있습니다. 이러한 설정은 VPN 연결에는 적용 되지 않습니다.

Windows 10의 프록시 설정에 대 한 자세한 내용은 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)를 참조 하세요.

#### <a name="vpn"></a>VPN

조직에서는 일반적으로 VPN을 사용 하 여 회사&#39;s 인트라넷의 앱 및 리소스에 대 한 액세스를 제어 합니다. HoloLens 2는 Microsoft Store에서 다운로드할 수 있는 플러그 인이 필요한 SSL VPN 연결을 지원 하며 사용자가 선택한 VPN 공급 업체에만 적용 됩니다.

VPN 프로필에 대 한 자세한 내용은 [VPNV2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) 를 참조 하세요.

#### <a name="kiosk-mode"></a>키오스크 모드

키오스크 모드에서 실행 되도록 장치를 구성 하 여 장치를 키오스크 라고도 하는 고정 목적의 장치로 작동 하도록 구성할 수 있습니다. 키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램 (또는 사용자)을 제한 합니다. 키오스크 모드는 HoloLens 2 장치를 비즈니스 앱에 전용으로 사용 하거나 앱 데모에서 HoloLens 2 장치를 사용 하는 데 사용할 수 있는 편리한 기능입니다.

키오스크 모드에서 HoloLens 2를 구성 하는 방법에 대 한 자세한 내용은 [hololens를 키오스크로 설정](https://docs.microsoft.com/hololens/hololens-kiosk) 을 참조 하세요.

## <a name="deploy"></a>배포

### <a name="mdm-device-enrollment"></a>MDM 장치 등록

엔터프라이즈 배포의 경우 Azure AD 조인 및 자동 MDM [등록(Azure](https://docs.microsoft.com/hololens/hololens-enroll-mdm) AD+MDM)을 통해서만 디바이스를 회사 디바이스로 MDM에 등록하는 것이 좋습니다. 이렇게 하려면 Azure AD Premium 필요하며 Intune을 비롯한 여러 MDM 공급자에 대한 자동 등록을 지원합니다.

자동 배포 등록 방법 [Autopilot에](https://docs.microsoft.com/hololens/hololens2-autopilot)대해 자세히 알아봅니다.

### <a name="application-deployment"></a>애플리케이션 개발

모바일 디바이스의 사용자 생산성은 앱에 의해 구동되는 경우가 많습니다.

Windows 10 사용하면 Windows 앱용 UWP(유니버설 Windows 플랫폼)를 사용하여 여러 디바이스에서 원활하게 작동하는 앱을 개발할 수 있습니다.

HoloLens 2 디바이스에 애플리케이션을 배포하는 방법에는 여러 가지가 있습니다. 앱은 MDM, 비즈니스용 Microsoft Store 통해 직접 배포하거나 프로비전 패키지를 통해 테스트용으로 로드할 수 있습니다. 자세한 내용은 [앱 배포](https://docs.microsoft.com/hololens/app-deploy-overview) 설명서를 확인하세요.

> [!NOTE]
> HoloLens 2 UWP ARM64 앱의 실행만 지원합니다.

## <a name="maintain"></a>유지 관리

엔터프라이즈 IT 환경에서 보안 및 비용 제어의 필요성은 사용자에게 최신 기술을 제공하려는 요구와 균형을 이겨야 합니다. 사이버 공격은 일상적으로 발생하게 되었으므로 Windows 10 디바이스의 상태를 제대로 유지하는 것이 중요합니다. IT 부서에서는 구성 설정을 제어하여 규정 준수를 벗어나지 않도록 하고 내부 애플리케이션에 액세스할 수 있는 디바이스를 적용해야 합니다. HoloLens 2 디바이스가 회사 정책을 준수하는지 확인하는 데 필요한 모바일 운영 관리 기능을 제공합니다.

### <a name="os-servicing-options"></a>OS 서비스 옵션

**간소화된 업데이트 프로세스**

Microsoft는 Windows 제품 엔지니어링 및 릴리스 주기를 간소화하여 시장에서 요구하는 새로운 기능, 환경 및 기능을 이전보다 더 빠르게 제공할 수 있습니다. Microsoft는 연간 두 가지 기능 업데이트를 제공할 계획입니다(12개월 기간). **기능 업데이트는** 현재 분기 또는 CB를 설정하고 연결된 버전을 갖습니다.

또한 Microsoft는 보안 및 안정성에 대한 업데이트를 HoloLens 2 디바이스에 직접 제공하고 설치합니다. Windows 업데이트를 통해 Microsoft 제어에서 릴리스된 이러한 **품질 업데이트** 는 매월 사용할 수 있습니다. HoloLens 2는 동일한 표준 업데이트 프로세스의 일부로 기능 업데이트 및 품질 업데이트를 사용 합니다.

기업 고객은 MDM 시스템을 사용 하 여 HoloLens 2 s에서 업데이트 환경 및 프로세스를 관리할 수 있습니다. 대부분의 경우 업데이트 프로세스를 관리 하는 정책은 기능 및 품질 업데이트 모두에 적용 됩니다. [HoloLens 업데이트를 위한 MDM 구성](https://docs.microsoft.com/hololens/hololens-updates)에서 자세한 내용을 참조 하세요.

### <a name="managing-applications"></a>애플리케이션 관리

IT 관리자는 HoloLens 2에 설치 하도록 허용 된 앱과 이러한 앱을 최신 상태로 유지 하는 방법을 제어할 수 있습니다.

HoloLens 2는 관리자가 Microsoft Store에서 앱 목록을 만들거나 허용 하거나 허용 하지 않을 수 있는 [Windows Defender 응용 프로그램 제어 (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)를 지원 합니다. 이 기능은 기본 제공 앱으로도 확장 됩니다. 앱을 허용 하거나 거부 하는 기능은 사용자가 자신의 장치를 사용 하도록 하는 데 도움이 됩니다. 그러나 직원의 요구 또는 요청 및 보안 관련 문제 간에 균형을 유지 하는 것이 항상 쉬운 방법은 아닙니다. 허용 또는 허용 안 함 목록을 만드는 경우에도 Microsoft Store에서 변경 하는 앱의 가로를 유지 해야 합니다.

자세한 내용은 [응용 프로그램 제어 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)를 참조 하세요.

### <a name="retire"></a>사용 중지

장치 사용 중지는 장치 수명 주기의 마지막 단계입니다. 데이터의 기밀성을 손상 시킬 수 있는 삭제 된 장치에서 회사 데이터를 유지 하려고 하지 않기&#39;때문에 최신 모델로 교체 되는 장치가 안전 하 게 사용 중지&#39;. 또한 분실 하거나 도난당 한 장치를 초기화 해야 하는 사용자를 적절 하 게 지원 하는 방법이 필요 합니다.

HoloLens 2는 장치를 초기화 하는 3 가지 방법을 지원 합니다.

**MDM 팩터리 초기화:** 관리자가 시작한 MDM 명령을 통해 HoloLens 2를 공장 이미지로 다시 설정 합니다. 장치에 저장 된 모든 데이터를 지웁니다.

**설정 내에서 장치 다시 설정:** 최종 사용자는 장치에서 설정 앱 내에서 HoloLens 2를 수동으로 다시 설정할 수 있습니다. 장치에 저장 된 모든 데이터를 지웁니다.

**ARC(Advanced Recovery Companion):** ARC 도구를 실행하는 PC에서 사용자 또는 관리자는 USB 케이블을 통해 PC에 연결된 HoloLens 2 플래시할 수 있습니다. 디바이스에 저장된 모든 데이터를 지웁니다.

> [!div class="nextstepaction"]
> [일반적인 배포 시나리오](common-scenarios.md)
