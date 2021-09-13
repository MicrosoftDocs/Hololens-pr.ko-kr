---
title: 배포 가이드 – Dynamics 365 Guides 통해 회사 연결 HoloLens 2 - 준비
description: Dynamics 365 Guides 사용하여 회사 연결 네트워크를 통해 HoloLens 2 디바이스 등록을 준비하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033415"
---
# <a name="prepare---corporate-connected-guide"></a>준비 - 회사 연결 가이드
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
개인 및 회사 배포 시나리오의 경우 MDM(모바일 장치 관리) 시스템은 Windows 10 디바이스, 특히 HoloLens 2 배포하고 관리하는 데 필요한 필수 인프라입니다. [Azure AD Premium 구독은](/azure/active-directory/fundamentals/active-directory-get-started-premium) ID 공급자로 권장되며 특정 기능을 지원하는 **데 필요합니다.**

> [!NOTE]
> HoloLens 2 모바일 디바이스처럼 배포되고 관리되지만 일반적으로 많은 사용자 간에 공유 디바이스로 사용됩니다.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. Microsoft Office 365 또는 Intune을 사용하는 조직은 이미 무료, Premium P1 및 Premium P2의 세 가지 버전이 있는 Azure AD를 사용하고 [있습니다(Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 디바이스 등록을 지원하지만 나중에 이 가이드에서 사용할 MDM 자동 등록을 사용하도록 설정하려면 Premium P1이 필요합니다.
> [!Important]
> 디바이스가 온-프레미스 AD 조인을 지원하지 HoloLens Azure AD가 있어야 합니다. Azure AD를 설정하지 않은 경우 지침에 따라 를 시작하고 [Azure Active Directory 새 테넌트 만들기를](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)시작합니다.

## <a name="identity-management"></a>ID 관리
이 가이드에서 사용되는 [ID는](/hololens/hololens-identity) Azure AD 계정입니다. Azure AD 계정에는 다음과 같은 몇 가지 이점이 있습니다.

- 직원은 Azure AD 계정을 사용하여 Azure AD에 디바이스를 등록하고 조직의 MDM 솔루션에 자동으로 등록할 수 있습니다(Azure AD+MDM – [Azure AD Premium 구독](/azure/active-directory/fundamentals/active-directory-get-started-premium)필요).
- Azure AD 계정에는 [비즈니스용 Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)통해 추가 [인증 옵션이](/hololens/hololens-identity) 있습니다. Iris 로그인 외에도 사용자는 다른 디바이스에서 로그인하거나 FIDO 보안 키를 사용할 수 있습니다.

> [!WARNING] 
> 직원은 하나의 계정만 사용하여 디바이스를 초기화할 수 있으므로 **조직에서 먼저 사용하도록 설정된 계정을 제어해야 합니다.** 선택한 계정은 디바이스를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다.

## <a name="mobile-device-management"></a>Mobile Device Management
Enterprise Mobility + Security 일부인 Microsoft Intune 테넌트 연결 디바이스를 관리하는 클라우드 기반 MDM 시스템입니다. Office 365 마찬가지로 Intune은 ID 관리에 Azure AD를 사용하므로 직원은 동일한 자격 증명을 사용하여 Office 365 로그인하는 데 사용하는 디바이스를 Intune에 등록합니다. 또한 Intune은 iOS 및 Android와 같은 다른 운영 체제를 실행하는 디바이스를 지원하여 완전한 MDM 솔루션을 제공합니다. 이 가이드에서는 HoloLens 2 사용하여 내부 네트워크에 배포할 수 있도록 Intune을 사용하는 데 집중합니다.
> [!Important] 
> 모바일 장치 관리 있어야 합니다. 설정하지 않은 경우 이 가이드 및 Intune 시작을 따릅니다.

> [!Important]
> 가이드를 사용하려면 Azure AD 계정이 필요합니다.

> [!Note] 
> 여러 MDM 시스템은 Windows 10 지원하며 대부분의 경우 개인 및 회사 디바이스 배포 시나리오를 지원합니다. Windows 10 Holographic 지원하는 MDM 공급자에는 AirWatch, MobileIron 등이 있습니다. 대부분의 업계 최고의 MDM 공급업체는 이미 Azure AD와의 통합을 지원합니다. [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)Azure AD를 지원하는 MDM 공급업체의 최신 목록을 찾을 수 있습니다.

## <a name="network-access"></a>네트워크 액세스 
Dynamics 365 Guides 클라우드 기반 애플리케이션입니다. 네트워크 관리자에게 승인 목록이 있는 경우 Dynamics 365 서버에 연결하는 데 필요한 IP 주소 및/또는 엔드포인트를 추가해야 할 수 있습니다. [IP 주소 및 URL의 차단을 해제하는 방법에 대해 자세히 알아봅니다.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>인증서
인증서를 사용하면 계정 인증, Wi-Fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공하여 보안을 향상시킬 수 있습니다. 관리자는 프로비전 패키지를 통해 디바이스의 인증서를 수동으로 관리할 수 있지만 등록부터 갱신 및 해지까지 전체 수명 주기 동안 MDM 시스템을 사용하여 해당 인증서를 관리하는 것이 가장 좋습니다. 

MDM 시스템은 등록한 후 디바이스의 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다(MDM 시스템에서 **SCEP(단순 인증서 등록 프로토콜)** 또는 **PKCS #12(공개 키 암호화 표준) #12).** [Microsoft Intune 에서 사용하는 인증서 유형 및 프로필에 대해 알아봅니다.](/mem/intune/protect/certificates-configure) MDM은 현재 인증서가 만료되기 전에 등록된 클라이언트 인증서를 쿼리 및 삭제하거나 새 등록 요청을 트리거할 수도 있습니다.

MDM 시스템이 인증서에 대해 이미 구성된 경우 HoloLens 2 인증서 [및 네트워크 프로필 준비를](/hololens/hololens-certificates-network) 참조하여 HoloLens 2 디바이스에 대한 인증서 및 프로필 배포를 시작합니다.

## <a name="scep"></a>SCEP

웹 애플리케이션 프록시 서버를 제외하고 SCEP 배포에는 다음 서비스가 필요합니다.

- [인증 기관](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 서버 역할](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 커넥터](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

또한 [Azure AD 애플리케이션 프록시 또는 웹 액세스 프록시를](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)사용하여 회사 네트워크 외부에 NDES URL을 게시해야 합니다. 선택한 다른 역방향 프록시를 사용할 수도 있습니다.

![SCEP 데이터 흐름.](./images/hololens2-scep-info-flow.png)

네트워크에서 SCEP를 아직 지원하지 않거나 네트워크가 Intune을 사용하여 SCEP에 대해 올바르게 설정되어 있는지 확실하지 않은 경우  [Intune을 사용하여 SCEP를 지원하도록 인프라 구성을](/mem/intune/protect/certificates-scep-configure)참조하세요.

인프라가 이미 SCEP를 지원하는 경우 HoloLens 2 사용할 각 SCEP 인증서에 대한 [프로필을](/mem/configmgr/protect/deploy-use/create-certificate-profiles) [만들어야](/mem/intune/protect/certificates-profile-scep) 합니다. SCEP에 문제가 있는 경우 [SCEP 인증서 프로필 사용 문제 해결을 사용하여 Microsoft Intune 인증서를 프로비전합니다.](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Intune은 PKCS(프라이빗 및 퍼블릭 키 쌍) 인증서의 사용도 지원합니다. 자세한 내용은 [Microsoft Intune 프라이빗 및 퍼블릭 키 인증서 사용을](/mem/intune/protect/certificates-pfx-configure) 참조하세요.

## <a name="proxy"></a>프록시
대부분의 회사 인트라넷 네트워크는 프록시를 활용하여 외부 트래픽을 관리합니다. HoloLens 2 사용하면 이더넷, Wi-Fi 및 VPN 연결에 대한 프록시 서버를 구성할 수 있습니다.

프록시에는 몇 가지 유형과 프록시를 구성하는 방법이 있습니다. 이 가이드에서는 **Wi-Fi 프록시를 선택하고, PAC URL을 통해 설정하고, MDM을 통해 배포하도록** 선택합니다. 이는 MDM을 통해 자동으로 배포되고, 서버:포트 구성을 사용하는 대신 PAC 파일을 업데이트할 수 있고, 마지막으로 Wi-Fi 프록시를 사용하여 단일 Wi-Fi 연결에만 적용되도록 프록시를 구성하여 디바이스가 다른 위치에 연결된 경우 계속 사용할 수 있다는 장점이 있습니다.

Windows 10 프록시 설정에 대한 자세한 내용은 Microsoft Intune [디바이스에 대한 Wi-Fi 프로필 만들기 - Azure를 참조하세요.](/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>사업장 앱 
Microsoft Store 통해 여러 앱을 설치할 수 있지만, 혼합 현실에서 사용하기 위해 특별히 만든 사용자 지정 앱이 있을 수 있습니다. 비즈니스를 위해 조직 전체에 분산된 이러한 사용자 지정 앱을 LOB(기간 업무) 앱이라고 합니다.
  
HoloLens 2 디바이스에 애플리케이션을 배포하는 방법에는 여러 가지가 있습니다. 앱은 MDM, MSfB(비즈니스용 Microsoft Store)를 통해 직접 배포하거나 프로비전 패키지를 통해 테스트용으로 로드할 수 있습니다. 이 가이드에서는 필수 앱 설치를 사용하여 MDM을 통해 앱을 배포합니다. 이렇게 하면 등록이 완료되면 LOB 앱을 HoloLens 디바이스에 자동으로 다운로드할 수 있습니다.

사용자 고유의 LOB가 없는 사용자의 경우 이 배포 흐름을 테스트하는 샘플 앱을 제공합니다. 이 앱은 [MRTK 예제](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 앱이 되며, 개념 증명을 테스트하기 위해 이미 미리 붙고 패키지되었습니다.

앱 배포에 대한 자세한 내용은 [앱 관리: 개요에서](/hololens/app-deploy-overview)찾을 수 있습니다.

> [!NOTE]
> HoloLens 2 UWP ARM64 앱의 실행만 지원합니다.

## <a name="guides-playbook"></a>가이드 플레이북
가이드는 Microsoft Dataverse 환경을 가이드 앱의 데이터 저장소로 사용합니다. Dataverse 환경이 가이드 앱 및 테넌트와 상호 작용하는 방법에 대한 더 큰 그림을 이해하는 것이 중요합니다. 이 가이드에서는 데이터버스를 관리하는 방법을 다루지 않지만 Dynamics 365 Guides [배포하기 위한 기본 개념인 Dynamics 365 Mixed Reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook)을 검토하세요.

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 구성](hololens2-corp-connected-configure.md)