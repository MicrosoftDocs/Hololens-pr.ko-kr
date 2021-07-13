---
title: 배포 가이드 – Remote Assist 대규모로 클라우드 연결 HoloLens 2 배포 - 준비
description: Azure Active Directory 및 ID 관리를 사용하여 클라우드 연결 네트워크를 통해 HoloLens 디바이스 등록을 준비하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 클라우드 연결, Remote Assist, AAD, Azure AD, MDM, Mobile 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639661"
---
# <a name="prepare---cloud-connected-guide"></a>준비 - 클라우드 연결 가이드

이 문서의 끝부분에서는 Azure AD, MDM을 설정하고 Azure AD 계정 및 네트워크 요구 사항을 사용하는 것에 대해 자세히 이해하게 됩니다. 가이드의 이 섹션은 사용자와 조직이 클라우드에 HoloLens 2 배포하고 Dynamics 365 Remote Assist 사용할 준비를 하는 데 도움이 됩니다. 인프라의 각 부분의 중요성을 넘어가며, 필요에 따라 이러한 부분을 설정하는 데 도움이 되는 가이드 링크를 제공합니다.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

개인 및 회사 배포 시나리오의 경우 MDM 시스템은 Windows 10 Holographic 디바이스를 배포하고 관리하는 데 필요한 필수 인프라입니다. Azure AD 프리미엄 구독은 ID 공급자로 권장되며 특정 기능을 지원하는 데 필요합니다.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. Microsoft Office 365 또는 Intune을 사용하는 조직은 이미 무료, Premium P1 및 Premium P2의 세 가지 버전이 있는 Azure AD를 사용하고 [있습니다(Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 디바이스 등록을 지원하지만 나중에 이 가이드에서 사용할 MDM 자동 등록을 사용하도록 설정하려면 Premium P1이 필요합니다.

> [!IMPORTANT]
> HoloLens 디바이스가 온-프레미스 AD 조인을 지원하지 않기 때문에 Azure Active Directory 있어야 합니다. Azure Active Directory 설정하지&#39;경우 Azure Active Directory [새 테넌트 만들기로](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)이동합니다.

## <a name="identity-management"></a>ID 관리

직원은 하나의 계정만 사용하여 디바이스를 초기화할 수 있으므로 조직에서 먼저 사용하도록 설정된 계정을 제어해야&#39;. 선택한 계정은 디바이스를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다.

이 가이드에서는 사용된 [ID에](/hololens/hololens-identity) 대해 Azure AD 계정 또는 Azure Active Directory 계정을 사용하도록 선택했습니다. 사용하려는 Azure AD 계정에는 다음과 같은 몇 가지 이점이 있습니다.

- 직원은 Azure AD 계정을 사용하여 Azure AD에 디바이스를 등록하고 조직의&#39;MDM 솔루션에 자동으로 등록합니다(Azure AD+MDM – Azure AD Premium 필요).
- Azure AD 계정은 [Single #A0](/azure/active-directory/manage-apps/what-is-single-sign-on)지원합니다. 사용자가 Remote Assist 로그인하면 로그인한 Azure AD 사용자의 ID가 인식되고 사용자가 간소화된 환경을 위해 앱에 로그인됩니다.
- Azure AD 계정에는 [비즈니스용 Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)통해 추가 [인증 옵션이](/hololens/hololens-identity) 있습니다. 아이리스 로그인 외에도 사용자는 다른 디바이스에서 로그인하거나 FIDO 보안 키를 사용할 수 있습니다.

### <a name="mobile-device-management"></a>Mobile Device Management

Enterprise Mobility + Security 일부인 Microsoft [Intune은](/mem/intune/fundamentals/what-is-intune)테넌트 연결 디바이스를 관리하는 클라우드 기반 MDM 시스템입니다. Office 365 마찬가지로 Intune은 ID 관리에 Azure AD를 사용하므로 직원은 동일한 자격 증명을 사용하여 Intune에 디바이스를 등록하고 Office 365 로그인하는 데 사용합니다. 또한 Intune은 iOS 및 Android와 같은 다른 운영 체제를 실행하는 디바이스를 지원하여 완전한 MDM 솔루션을 제공합니다. 이 가이드의 목적을 위해&#39;HoloLens 2 대규모로 클라우드 배포를 사용하도록 설정하기 위해 Intune을 사용하는 데 중점을 두겠습니다.

> [!IMPORTANT]
> 모바일 장치 관리 있어야 합니다. &#39;설정하지 않은 경우 이 가이드 및 [Intune 시작에](/mem/intune/fundamentals/free-trial-sign-up)따릅니다.

> [!NOTE]
> 여러 MDM 시스템은 Windows 10 지원하며 대부분의 경우 개인 및 회사 디바이스 배포 시나리오를 지원합니다. 현재 Windows 10 Holographic 지원하는 MDM 공급자에는 AirWatch, MobileIron 등이 포함됩니다. 대부분의 업계 최고의 MDM 공급업체는 이미 Azure AD와의 통합을 지원합니다. [Azure Marketplace](https://azure.microsoft.com/marketplace/)Azure AD를 지원하는 MDM 공급업체를 찾을 수 있습니다.

## <a name="network"></a>네트워크

이 설정에서는 사용 가능한 모든 열린 Wi-Fi 네트워크에서 인터넷에 연결하는 HoloLens 2 디바이스를 예상합니다. 사용자는 위치에 따라 네트워크 연결을 변경해야 할 수 있기 때문에 [HoloLens 디바이스를 Wi-Fi에 연결하는](/hololens/hololens-network) 방법을 알아야 합니다.

Dynamics 365 Remote Assist 경우 대역폭, 대기 시간, 지터 및 패킷 손실을 포함하여 비디오 통화 환경에 영향을 줄 수 있는 다양한 네트워크 조건이 있습니다. 대역폭이 감소된 환경에서는 오디오 및 비디오 호출이 가능할 수 있지만 기능 저하가 발생할 수 있습니다. HoloLens Dynamics 365 Remote Assist 사용하는 경우 다음 네트워크 요구 사항을 염두에 두어야 합니다.

**최소** : 30fps에서 HD 1080p 해상도를 사용하여 피어 투 피어 HD 품질 비디오 통화에 1.5Mbps의 업/다운이 필요합니다.

**최적:** HD 1080p 해상도를 사용하여 피어 투 피어 HD 품질 비디오 통화의 경우 4-5Mbps 업/다운이 예상되어야 합니다.

추가 정보:

- [네트워크 요구 사항](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [네트워크 최적화 권장 사항](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>선택 사항: VPN에 HoloLens 커넥트

이 가이드에 연결된 디바이스는 및 외부 클라우드 네트워크를 통해 네트워크에 연결됩니다. &#39;회사 리소스에 액세스하려면 VPN을 통해 디바이스를 연결해야 할 수 있습니다. 디바이스를 VPN에 연결하는 방법에는 여러 가지가 있습니다. 두 방법 모두 최종 사용자가 디바이스 UI를 사용하여 연결할 수 있거나 디바이스를 관리하고 PPKG 또는 MDM에서 VPN 프로필을 수신할 수 있습니다. VPN을 설정하는 방법은 이 문서에서 다루지&#39;&#39;. 따라서 다양한 VPN 프로토콜 또는 VPN을 관리하는 방법에 대해 자세히 알아보려면 [HoloLens 및 VPN에 대한 자세한 내용은 이 가이드를 참조하세요.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 구성](hololens2-cloud-connected-configure.md)
