---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 준비
description: Dynamics 365 가이드를 통해 회사 연결 네트워크를 통해 HoloLens 2 장치 등록을 준비하는 방법을 알아보세요.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448597"
---
# <a name="prepare---corporate-connected-guide"></a>준비 - 회사 연결 가이드
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
개인 및 회사 배포 시나리오에서 MDM(모바일 장치 관리) 시스템은 Windows 10 장치, 특히 HoloLens 2를 배포하고 관리하는 데 필요한 필수 인프라입니다. [Azure AD Premium 구독은](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) ID 공급자로 권장되는 것이 며 특정 기능을 지원하는 데 필요합니다. ****

> [!NOTE]
> HoloLens 2는 모바일 장치처럼 배포 및 관리되는 데는 일반적으로 여러 사용자 간의 공유 장치로 사용됩니다.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. Microsoft Office 365 또는 Intune을 사용하는 조직은 이미 무료, 프리미엄 P1 및 Premium P2의 세 가지 버전이 있는 Azure AD를 사용하고 [있습니다(Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 장치 등록을 지원하지만, 이 가이드의 나중에 사용할 MDM 자동 등록을 사용하도록 설정하려면 Premium P1이 필요합니다.
> [!Important]
> HoloLens 장치에서는 프레미스 AD 가입을 지원하지 않는 Azure AD가 반드시 필요합니다. 아직 Azure AD를 설정하지 않은 경우 지침에 따라 시작하고 Azure Active Directory에서 새 테넌트 [만들기 를 시작하세요.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>ID 관리
이 가이드에서 사용되는 [ID는](https://docs.microsoft.com/hololens/hololens-identity) Azure AD 계정입니다. Azure AD 계정에는 몇 가지 이점이 있습니다.
- 직원은 Azure AD 계정을 사용하여 Azure AD에 장치를 등록하고 조직의 MDM 솔루션에 자동으로 등록할 수 있습니다(Azure AD+MDM – Azure AD Premium 구독 [필요).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD 계정에는 [비즈니스용](https://docs.microsoft.com/hololens/hololens-identity) Windows Hello를 통한 추가 [인증 옵션이 있습니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Iris 로그인 외에도 사용자는 다른 장치에서 로그인하거나 FIDO 보안 키를 사용할 수 있습니다.

> [!WARNING] 
> 직원은 하나의 계정만 사용하여 장치를 초기화할 수 있으므로 조직에서 먼저 사용하도록 설정된 계정을 **제어해야 합니다.** 선택하는 계정이 장치를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다.

## <a name="mobile-device-management"></a>모바일 장치 관리
Enterprise Mobility + Security의 일부인 Microsoft Intune은 테넌트에 연결된 장치를 관리하는 클라우드 기반 MDM 시스템입니다. Office 365와 마찬가지로 Intune은 ID 관리를 위해 Azure AD를 사용 하여 직원이 Office 365에 로그인하는 데 사용하는 동일한 자격 증명을 사용하여 Intune에 장치를 등록합니다. 또한 Intune은 iOS 및 Android와 같은 다른 운영 체제를 실행하여 완전한 MDM 솔루션을 제공하는 장치를 지원합니다. 이 가이드에서는 HoloLens 2를 사용하여 내부 네트워크에 배포할 수 있도록 Intune을 사용하는 데 집중할 것입니다.
> [!Important] 
> 모바일 장치 관리를 반드시 설정해야 합니다. 아직 설정하지 않은 경우 이 가이드를 따르고 Intune 시작을 참조하세요.

> [!Important]
> 가이드를 사용하려면 Azure AD 계정이 필요합니다.

> [!Note] 
> 여러 MDM 시스템이 Windows 10을 지원하고 개인 및 회사 장치 배포 시나리오를 지원합니다. Windows 10 Holographic을 지원하는 MDM 공급자에는 AirWatch, MobileIron 등이 포함됩니다. 업계 최고의 MDM 공급업체가 대부분 Azure AD와의 통합을 이미 지원하고 있습니다. Azure 마켓플레이스에서 Azure AD를 지원하는 MDM 공급업체의 가장 최근 목록을 [찾을 수 있습니다.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>네트워크 액세스 
Dynamics 365 가이드는 클라우드 기반 응용 프로그램입니다. 네트워크 관리자에게 승인 목록이 있는 경우 Dynamics 365 서버에 연결하는 데 필요한 IP 주소 및/또는 끝점을 추가해야 할 수 있습니다. IP 주소 및 URL 차단 [해제에 대해 자세히 알아보하세요.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>인증서
인증서는 웹 콘텐츠의 계정 인증, Wi-Fi 인증, VPN 암호화 및 SSL 암호화를 제공하여 보안을 향상시키는 데 도움이 됩니다. 관리자는 프로비저닝 패키지를 통해 디바이스에서 인증서를 수동으로 관리할 수 있지만 등록부터 갱신 및 해지까지 전체 수명 주기 동안 MDM 시스템을 사용하여 인증서를 관리하는 것이 가장 좋은 것입니다. 

MDM 시스템에서 **SCEP(Simple Certificate Enrollment Protocol)** 또는 **PKCS#12(공개**키 암호화 표준)를 지원하는 경우 MDM 시스템에서 인증서를 등록한 후 장치의 인증서 저장소에 이러한 인증서를 자동으로 배포할 #12 수 있습니다. [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/protect/certificates-configure)사용하는 인증서 유형 및 프로필에 대해 알아보세요. 또한 MDM은 등록된 클라이언트 인증서를 쿼리 및 삭제하거나 현재 인증서가 만료되기 전에 새 등록 요청을 트리거할 수 있습니다.
 
MDM 시스템이 인증서에 대해 이미 구성되어 있는 경우 [HoloLens 2용](https://docs.microsoft.com/hololens/hololens-certificates-network) 인증서 및 네트워크 프로필 준비를 참조하여 HoloLens 2 장치에 대한 인증서 및 프로필 배포를 시작하세요.

## <a name="scep"></a>SCEP

다음 서비스는 웹 응용 프로그램 프록시 서버를 제외하고 SCEP 배포에 필요합니다.
- [인증 기관](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 서버 역할](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 커넥터](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

또한 Azure AD 응용 프로그램 프록시 또는 웹 액세스 프록시를 사용하여 회사 네트워크 외부에 [NDES URL을 게시해야 합니다.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) 원하는 다른 역방향 프록시를 사용할 수도 있습니다.

![SCEP 데이터 흐름](./images/hololens2-scep-info-flow.png)

네트워크에서 SCEP를 아직 지원하지 않는 경우 또는 Intune을 통해 네트워크가 SCEP에 올바르게 설정되어 있는지 잘 알고 있지 않은 경우  [Intune을 통해 SCEP를](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)지원하도록 인프라 구성을 참조합니다.

인프라에서 이미 SCEP를 지원하는 경우 [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) HoloLens 2에서 사용할 각 SCEP 인증서에 대한 프로필을 만들어야 합니다. [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) SCEP에 문제가 있는 경우 SCEP 인증서 프로필 사용 문제 해결을 사용하여 [Microsoft Intune으로 인증서를 프로비전합니다.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Intune에서는 개인 및 PKCS(공개 키 쌍) 인증서도 사용할 수 있습니다. 참조 [자세한 내용은 Microsoft Intune에서](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) 개인 및 공개 키 인증서를 사용하세요.

## <a name="proxy"></a>Proxy (프록시)
대부분의 회사 인트라넷 네트워크는 프록시를 사용하여 외부 트래픽을 관리합니다. HoloLens 2를 사용하면 이더넷, 서버 및 VPN 연결에 Wi-Fi 수 있습니다.

몇 가지 유형의 프록시 및 프록시를 구성하는 방법이 있습니다. 이 가이드의 목적을 위해 Wi-Fi 프록시를 선택하고 PAC URL을 통해 설정하며 **MDM을 통해 배포할 수 있습니다.** 이는 MDM을 통해 자동으로 배포되고, server:port 구성을 사용하는 대신 PAC 파일을 업데이트할 수 있는 이점과 마지막으로 Wi-Fi 프록시를 사용하여 단일 Wi-Fi 연결에만 적용하도록 프록시를 구성하여 장치를 다른 위치에 연결된 경우 계속 사용할 수 있는 이점이 있습니다. 


Windows 10의 프록시 설정에 대한 자세한 내용은 Microsoft Intune - Azure에서 디바이스에 Wi-Fi 프로필 [만들기를 참조하세요.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>업무용 앱 
Microsoft Store를 통해 여러 앱을 설치할 수 있는 경우 혼합 현실에서 사용하기 위해 특별히 만든 사용자 지정 앱이 있을 수 있습니다. 비즈니스를 위해 조직 전체에 배포된 이러한 사용자 지정 앱을 LOB(LoB) 앱이라고 합니다.
  
HoloLens 2 장치에 응용 프로그램을 배포하는 방법에는 여러 가지가 있습니다. 앱은 MDM, 비즈니스용 Microsoft Store(MSfB)를 통해 직접 배포하거나 프로비저닝 패키지를 통해 사이드로드할 수 있습니다. 이 가이드를 위해 필요한 앱 설치를 사용하여 MDM을 통해 앱을 배포합니다. 이렇게 하면 등록이 완료되면 LOB 앱이 HoloLens 장치에 자동으로 다운로드될 수 있습니다.

LOB가 없는 사용자들을 위해 이 배포 흐름을 테스트하기 위한 샘플 앱을 제공합니다. 이 앱은 [MRTK 예제](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 앱으로, 개념 증명을 테스트하기 위해 이미 미리 준비되고 패키지되어 있습니다.
 
앱 배포에 대한 자세한 내용은 [앱 관리: 개요에서 확인할 수 있습니다.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2는 UWP ARM64 앱의 실행만 지원합니다.

## <a name="guides-playbook"></a>가이드 플레이북
가이드는 Microsoft Dataverse 환경을 가이드 앱의 데이터 스토어로 사용 합니다. Dataverse 환경이 가이드 앱 및 테넌트와 상호 작용하는 방식에 대한 더 큰 그림을 이해하는 것이 중요합니다. 이 가이드에서는 데이터버스를 관리하는 방법을 다루지 않지만 [Dynamics 365 가이드- Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)배포를 위한 기본 개념을 검토하세요.

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 구성](hololens2-corp-connected-configure.md)