---
title: 배포 가이드-원격 지원으로 대규모 클라우드 연결 HoloLens 2 배포-준비
description: azure active directory 및 id 관리를 사용 하 여 클라우드 연결 네트워크를 통해 HoloLens 장치를 등록 하도록 준비 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: f747a2893ed3551e91a81bdbf5971deefbf6ce46
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637135"
---
# <a name="prepare---cloud-connected-guide"></a>준비-클라우드 연결 가이드

이 문서의 끝부분에서는 azure AD 및 MDM을 설정 하 고 Azure AD 계정 및 네트워크 요구 사항을 사용 하는 방법에 대해 자세히 알아보세요. 이 가이드의 섹션은 사용자와 조직에서 클라우드에 HoloLens 2 배포 하 고 Dynamics 365 Remote Assist을 사용 하도록 준비 하는 데 도움이 됩니다. 이는 인프라의 각 부분에 대 한 중요 한 정보를 제공 하며 필요에 따라 해당 부분을 설정 하는 데 도움이 되는 가이드 링크를 제공 합니다.

## <a name="infrastructure-essentials"></a>인프라 Essentials

개인 및 회사 배포 시나리오 모두에서 MDM 시스템은 Windows 10 Holographic 장치를 배포 및 관리 하는 데 필요한 필수 인프라입니다. Azure AD premium 구독은 id 공급자로 권장 되며 특정 기능을 지 원하는 데 필요 합니다.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD는 id 및 액세스 관리를 제공 하는 클라우드 기반 디렉터리 서비스입니다. Microsoft Office 365 또는 Intune을 사용 하는 조직은 Azure AD를 이미 사용 하 고 있습니다. 여기에는 Free, Premium P1 및 Premium P2의 세 버전이 있습니다 ( [Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 장치 등록을 지원 하지만, 나중에이 가이드에서 사용할 MDM 자동 등록을 사용 하도록 설정 하려면 Premium P1이 필요 합니다.

> [!IMPORTANT]
> HoloLens 장치가 온-프레미스 AD 조인을 지원 하지 않으므로 Azure Active Directory 있어야 합니다. 이미 Azure Active Directory 설정 된&#39;없는 경우 [Azure Active Directory에서 새 테 넌 트 만들기](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)로 이동 합니다.

## <a name="identity-management"></a>ID 관리

직원은 한 계정을 사용 하 여 장치를 초기화할 수 있으므로 조직에서 먼저 사용 하도록 설정 된 계정을 제어 하는 것이 필수적&#39;. 선택한 계정은 장치를 제어 하 고 관리 기능에 영향을 주는 사용자를 결정 합니다.

이 가이드에서는 사용 되는 [id](/hololens/hololens-identity) 에 대해 Azure AD 계정 또는 Azure Active Directory 계정을 사용 하도록 선택 했습니다. 다음과 같이 사용 하려는 Azure AD 계정에 대 한 몇 가지 이점이 있습니다.

- 직원은 Azure ad 계정을 사용 하 여 Azure AD에 장치를 등록 하 고 조직&#39;s MDM 솔루션 (Azure AD + MDM – Azure AD Premium 필요)에 자동으로 등록 합니다.
- Azure AD 계정은 [Single Sign On](/azure/active-directory/manage-apps/what-is-single-sign-on)을 지원 합니다. 사용자가 원격 지원에 로그인 하면 로그인 한 Azure AD 사용자의 Id가 인식 되 고 사용자가 간소화 된 환경을 위해 앱에 로그인 됩니다.
- Azure AD 계정 [에는 Windows Hello for Business를](/windows/security/identity-protection/hello-for-business/hello-identity-verification)통해 추가 [인증 옵션이](/hololens/hololens-identity) 있습니다. 또한 Iri 로그인 사용자는 다른 장치에서 로그인 하거나 FIDO 보안 키를 사용할 수 있습니다.

### <a name="mobile-device-management"></a>Mobile Device Management

Enterprise Mobility + Security의 일부인 Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)은 테 넌 트에 연결 된 장치를 관리 하는 클라우드 기반 MDM 시스템입니다. Office 365와 마찬가지로, intune은 id 관리에 Azure AD를 사용 하므로 직원은 동일한 자격 증명을 사용 하 여 Office 365에 로그인 하는 데 사용 하는 장치를 Intune에 등록 합니다. 또한 Intune은 iOS, Android 등의 다른 운영 체제를 실행 하는 장치를 지원 하 여 완전 한 MDM 솔루션을 제공 합니다. 이 가이드에서는 HoloLens 2를 사용 하 여 대규모 클라우드 배포를 사용 하도록 설정 하기 위해 Intune을 사용 하는 방법을 집중적으로 설명&#39;.

> [!IMPORTANT]
> 모바일 장치를 관리 하는 것이 중요 합니다. 아직&#39;하지 않은 경우이 가이드에 따라 [Intune을 시작](/mem/intune/fundamentals/free-trial-sign-up)하세요.

> [!NOTE]
> 여러 MDM 시스템이 Windows 10을 지원 하 고 개인 및 회사 장치 배포 시나리오를 지원 합니다. 현재 Windows 10 Holographic를 지 원하는 MDM 공급자에는 MobileIron 및 기타가 포함 됩니다. 대부분의 업계 최고의 MDM 공급 업체는 이미 Azure AD와의 통합을 지원 합니다. [Azure Marketplace](https://azure.microsoft.com/marketplace/)에서 Azure AD를 지 원하는 MDM 공급 업체를 찾을 수 있습니다.

## <a name="network"></a>네트워크

이 설정에서는 사용 가능한 열려 있는 Wi-Fi 네트워크에서 인터넷에 연결 하는 장치를 HoloLens 2 것으로 예상 합니다. 사용자는 위치에 따라 네트워크 연결을 변경 해야 할 수 있기 때문에 [HoloLens 장치를 wi-fi에 연결](/hololens/hololens-network) 하는 방법을 알아야 합니다.

Dynamics 365 Remote Assist 대역폭, 대기 시간, 지터 및 패킷 손실을 포함 하 여 비디오 호출 환경에 영향을 줄 수 있는 다양 한 네트워크 조건이 있습니다. 대역폭이 줄어든 환경에서 오디오 및 비디오 호출이 가능 하더라도 기능 저하가 발생할 수 있습니다. HoloLens에서 Dynamics 365 Remote Assist를 사용 하는 경우 염두에 두어야 할 네트워크 요구 사항은 다음과 같습니다.

**최소** : 1.5 Mbps up/DOWN은 hd 1080p의 해상도를 사용 하 여 피어 투 피어 hd 품질 비디오를 호출 하는 데 필요 합니다 (30fps).

**최적:** HD 1080p의 해상도로 피어 투 피어 HD 품질 비디오를 호출 하는 경우 4-5 Mbps가 필요 합니다.

추가 정보:

- [네트워크 요구 사항](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [네트워크 최적화 권장 사항](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>선택 사항: VPN에 HoloLens를 커넥트 합니다.

이 가이드에 연결 되는 장치는 및 외부 클라우드 네트워크를 통해 네트워크에 연결 됩니다. 회사 리소스에 액세스 하는 것이&#39;VPN을 통해 장치를 연결 해야 하는 경우도 있습니다. 장치를 VPN에 연결 하는 방법에는 여러 가지가 있습니다. 여기에는 최종 사용자가 장치 UI를 사용 하 여 연결 하거나 장치를 관리 하 고 PPKG 또는 MDM에서 VPN 프로필을 받을 수 있습니다. vpn을 설정 하는 방법에 대 한 자세한 내용은이 문서에서 설명 합니다. 따라서 다른 vpn 프로토콜이 나 vpn을 관리 하는 방법에 대 한 자세한 내용을 확인 하는 것과 같은&#39;&#39;[HoloLens 및 vpn에 대 한 자세한 내용은 이러한 가이드](/hololens/hololens-network#vpn) 를 참조 하세요.

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포-구성](hololens2-cloud-connected-configure.md)
