---
title: 배포 가이드 – Dynamics 365 Guides를 사용 하 여 회사에 연결 된 HoloLens 2-준비
description: Dynamics 365 Guides를 사용 하 여 회사에 연결 된 네트워크를 통해 HoloLens 2 장치를 등록 하기 위해 준비 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사에 연결 된 Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 76513c2f2458119785b64d8cccac4e42c2957b5af966dfdb0c165ebeda12e069
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660087"
---
# <a name="prepare---corporate-connected-guide"></a>준비-회사에 연결 된 가이드
## <a name="infrastructure-essentials"></a>인프라 Essentials
개인 및 회사 배포 시나리오 모두에서 MDM (모바일 장치 관리) 시스템은 Windows 10 장치, 특히 HoloLens 2를 배포 하 고 관리 하는 데 필요한 필수 인프라입니다. [Azure AD Premium 구독은](/azure/active-directory/fundamentals/active-directory-get-started-premium) id 공급자로 권장 되며 특정 기능을 지 원하는 데 **필요** 합니다.

> [!NOTE]
> HoloLens 2는 모바일 장치와 같이 배포 및 관리 되지만 일반적으로 많은 사용자 간에 공유 장치로 사용 됩니다.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD는 id 및 액세스 관리를 제공 하는 클라우드 기반 디렉터리 서비스입니다. Microsoft Office 365 또는 Intune을 사용 하는 조직은 Azure AD를 이미 사용 하 고 있습니다 .이 AD는 Free, Premium P1 및 Premium P2의 세 가지 버전으로 제공 됩니다 ( [Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 장치 등록을 지원 하지만, 나중에이 가이드에서 사용할 MDM 자동 등록을 사용 하도록 설정 하려면 Premium P1이 필요 합니다.
> [!Important]
> HoloLens 장치는 온-프레미스 AD 조인을 지원 하지 않으므로 Azure AD를 반드시 포함 해야 합니다. Azure AD를 아직 설정 하지 않은 경우 지침에 따라 시작 하 고 [Azure Active Directory에 새 테 넌 트를 만듭니다](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>ID 관리
이 가이드에서 사용 되는 [id](/hololens/hololens-identity) 는 Azure AD 계정이 됩니다. Azure AD 계정에는 다음과 같은 몇 가지 이점이 있습니다.

- 직원은 azure ad 계정을 사용 하 여 azure ad에 장치를 등록 하 고 조직의 MDM 솔루션 (Azure ad + mdm – [Azure AD Premium 구독](/azure/active-directory/fundamentals/active-directory-get-started-premium)필요)에 자동으로 등록할 수 있습니다.
- Azure AD 계정 [에는 Windows Hello for Business를](/windows/security/identity-protection/hello-for-business/hello-identity-verification)통해 추가 [인증 옵션이](/hololens/hololens-identity) 있습니다. Iri 로그인 외에도 사용자는 다른 장치에서 로그인 하거나 FIDO 보안 키를 사용할 수 있습니다.

> [!WARNING] 
> 직원은 한 계정만 사용 하 여 장치를 초기화할 수 있으므로 **조직에서 먼저 사용 하도록 설정 된 계정을 제어 하는 것이 필수적입니다**. 선택한 계정은 장치를 제어 하 고 관리 기능에 영향을 주는 사용자를 결정 합니다.

## <a name="mobile-device-management"></a>Mobile Device Management
Enterprise Mobility + Security의 일부인 Microsoft Intune은 테 넌 트에 연결 된 장치를 관리 하는 클라우드 기반 MDM 시스템입니다. Office 365와 마찬가지로, intune은 id 관리에 Azure AD를 사용 하므로 직원은 동일한 자격 증명을 사용 하 여 Office 365에 로그인 하는 데 사용 하는 장치를 Intune에 등록 합니다. 또한 Intune은 iOS, Android 등의 다른 운영 체제를 실행 하는 장치를 지원 하 여 완전 한 MDM 솔루션을 제공 합니다. 이 가이드에서는 HoloLens 2를 사용 하 여 내부 네트워크에 대 한 배포를 사용 하도록 설정 하기 위해 Intune을 사용 하는 방법을 집중적으로 설명 합니다.
> [!Important] 
> 모바일 장치를 관리 하는 것이 중요 합니다. 아직 설정 하지 않은 경우이 가이드에 따라 Intune을 시작 하세요.

> [!Important]
> 가이드를 사용 하려면 Azure AD 계정이 필요 합니다.

> [!Note] 
> 여러 MDM 시스템이 Windows 10을 지원 하 고 개인 및 회사 장치 배포 시나리오를 지원 합니다. Windows 10 Holographic를 지 원하는 MDM 공급자에는 MobileIron 및 기타 항목이 포함 됩니다. 대부분의 업계 최고의 MDM 공급 업체는 이미 Azure AD와의 통합을 지원 합니다. [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)에서 Azure AD를 지 원하는 MDM 공급 업체의 최신 목록을 찾을 수 있습니다.

## <a name="network-access"></a>네트워크 액세스 
Dynamics 365 Guides은 클라우드 기반 응용 프로그램입니다. 네트워크 관리자에 게 승인 목록이 있으면 Dynamics 365 서버에 연결 하는 데 필요한 IP 주소 및/또는 끝점을 추가 해야 할 수 있습니다. [IP 주소 및 url 차단 해제에 대해 자세히 알아보세요](/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>인증서
인증서는 계정 인증, Wi-Fi 인증, VPN 암호화 및 웹 콘텐츠의 SSL 암호화를 제공 하 여 보안을 개선 하는 데 도움이 됩니다. 관리자는 프로 비전 패키지를 통해 수동으로 장치에서 인증서를 관리할 수 있지만 등록에서 갱신 및 해지를 통해 MDM 시스템을 사용 하 여 전체 수명 주기 동안 해당 인증서를 관리 하는 것이 좋습니다. 

Mdm 시스템이 **단순 인증서 등록 프로토콜 (SCEP)** 또는 **공개 키 암호화 표준 #12 (PKCS # 12)** 를 지 원하는 한, mdm 시스템에서 장치 인증서 저장소에 이러한 인증서를 자동으로 배포할 수 있습니다. [Microsoft Intune에서 사용 하는 인증서 유형 및 프로필에 대해 알아봅니다](/mem/intune/protect/certificates-configure). 현재 인증서가 만료 되기 전에 MDM에서 등록 된 클라이언트 인증서를 쿼리 및 삭제 하거나 새 등록 요청을 트리거할 수도 있습니다.

MDM 시스템이 이미 인증서에 대해 구성 된 경우에는 [HoloLens 2에 대 한 준비 인증서 및 네트워크 프로필](/hololens/hololens-certificates-network) 을 참조 하 여 HoloLens 2 장치의 인증서 및 프로필 배포를 시작할 수 있습니다.

## <a name="scep"></a>SCEP

다음 서비스는 웹 응용 프로그램 프록시 서버를 제외 하 고 SCEP 배포에 필요 합니다.

- [인증 기관](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 서버 역할](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 커넥터](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

또한 [AZURE AD 응용 프로그램 프록시 또는 웹 액세스 프록시](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)를 사용 하 여 회사 네트워크 외부에 NDES URL을 게시 해야 합니다. 선택한 다른 역방향 프록시를 사용할 수도 있습니다.

![SCEP 데이터 흐름](./images/hololens2-scep-info-flow.png)

네트워크에서 SCEP를 아직 지원 하지 않거나 네트워크가 Intune과 함께 SCEP에 올바르게 설정 되었는지 확신할 수 없는 경우  [intune을 사용 하 여 scep를 지원 하도록 인프라 구성](/mem/intune/protect/certificates-scep-configure)을 참조 하세요.

인프라가 이미 scep를 지 원하는 경우 HoloLens 2 사용할 각 SCEP 인증서에 대 한 [프로필](/mem/configmgr/protect/deploy-use/create-certificate-profiles) 을 [만들어야](/mem/intune/protect/certificates-profile-scep) 합니다. SCEP에 문제가 있는 경우 [scep 인증서 프로필의 사용 문제 해결을 사용 하 여 Microsoft Intune 인증서를 프로 비전](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)합니다.

## <a name="pkcs"></a>PKCS
또한 Intune은 개인 및 PKCS (공개 키 쌍) 인증서를 사용할 수 있도록 지원 합니다. 참조 [Microsoft Intune 개인 및 공개 키 인증서를 사용 하 여](/mem/intune/protect/certificates-pfx-configure) 자세한 내용을 참조 하세요.

## <a name="proxy"></a>Proxy (프록시)
대부분의 회사 인트라넷 네트워크는 프록시를 활용 하 여 외부 트래픽을 관리 합니다. HoloLens 2 사용 하 여 이더넷, Wi-Fi 및 VPN 연결에 대 한 프록시 서버를 구성할 수 있습니다.

프록시를 구성 하는 방법에는 몇 가지 다른 유형이 있습니다. 이 가이드의 목적에 맞게 Wi-fi 프록시를 선택 하 고 **, PAC URL을 통해 설정 하 고, MDM을 통해 배포** 합니다. 이는 MDM을 통해 자동으로 배포 하 고, 서버: 포트 구성을 사용 하는 대신 PAC 파일을 업데이트할 수 있으며, 마지막으로 Wi-Fi 프록시를 사용 하 여 단일 Wi-Fi 연결에만 적용 되도록 프록시를 구성 하 여 다른 위치에 연결 되어 있는 경우에도 장치를 사용할 수 있도록 하는 이점을 제공 합니다.

Windows 10에 대 한 프록시 설정에 대 한 자세한 내용은 [Microsoft Intune에서 장치에 대 한 Wi-Fi 프로필 만들기](/mem/intune/configuration/wi-fi-settings-configure)를 참조 하세요.

## <a name="line-of-business-apps"></a>Lob (기간 업무) 앱 
Microsoft Store를 통해 여러 앱을 설치할 수 있지만, 혼합 현실에서 사용 하기 위해 특별히 만든 사용자 지정 앱이 있을 수 있습니다. 비즈니스를 위해 조직 전체에 분산 된 이러한 사용자 지정 앱을 LOB (기간 업무) 앱 이라고 합니다.
  
응용 프로그램을 HoloLens 2 장치에 배포 하는 방법에는 여러 가지가 있습니다. 앱은 MDM, 비즈니스용 Microsoft Store (MSfB) 또는 프로 비전 패키지를 통해 테스트용으로 로드를 통해 직접 배포할 수 있습니다. 이 가이드에서는 필수 앱 설치를 사용 하 여 MDM을 통해 앱을 배포 합니다. 이렇게 하면 등록을 완료 한 후에 HoloLens 장치에 LOB 앱을 자동으로 다운로드할 수 있습니다.

사용자 고유의 LOB가 없는 사용자를 위해 샘플 앱을 제공 하 여이 배포 흐름을 테스트 합니다. 이 앱은 [Mrtk 예제](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 앱이 되며 개념 증명을 테스트 하기 위해 이미 미리 작성 되 고 패키지로 제공 됩니다.

앱 배포에 대 한 자세한 내용은 [앱 관리: 개요](/hololens/app-deploy-overview)에서 찾을 수 있습니다.

> [!NOTE]
> HoloLens 2 UWP ARM64 앱의 실행만 지원 합니다.

## <a name="guides-playbook"></a>가이드 플레이 북
가이드는 Microsoft Dataverse 환경을 가이드 앱의 데이터 저장소로 사용 합니다. Dataverse 환경에서 가이드 앱 및 테 넌 트와 상호 작용 하는 방법을 이해 하는 것이 중요 합니다. 이 가이드에서는 dataverse를 관리 하는 방법에 대해서는 다루지 않지만 [Dynamics 365 Guides Dynamics 365 혼합 현실 배포에 대 한 기본 개념](/dynamics365/mixed-reality/guides/admin-deployment-playbook)을 검토 하세요.

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사에 연결 된 배포-구성](hololens2-corp-connected-configure.md)