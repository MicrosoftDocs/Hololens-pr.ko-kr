---
title: 배포 가이드 - 원격 지원으로 클라우드에 연결된 HoloLens 2 배포 대규모 - 준비
description: 클라우드 연결 네트워크를 통해 HoloLens 장치 등록을 준비하는 방법
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
ms.openlocfilehash: 0e9222df2c387fab8f61a585d3a7f3966b9ecd31
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196354"
---
# 준비 - 클라우드 연결 가이드

이 문서가 끝나면 AAD, MDM을 설정하고 AAD 계정 및 네트워크 요구 사항을 사용하는 방법을 더 이해하게 됩니다. 이 가이드 섹션에서는 사용자와 조직이 클라우드에 HoloLens 2를 배포하고 Dynamics 365 원격 지원을 사용할 준비를 하는 데 도움이 됩니다. 또한 인프라의 각 조각의 중요성을 설명하고, 필요한 경우 이러한 조각을 설정하는 데 도움이 되는 안내에 대한 링크를 제공합니다.

## Infrastructure Essentials

개인 및 회사 배포 시나리오에서 MDM 시스템은 Windows 10 Holographic 장치를 배포하고 관리하는 데 필요한 필수 인프라입니다. Azure AD Premium 구독을 ID 공급자로 사용하는 것이 좋으며 특정 기능을 지원하려면 Azure AD Premium 구독이 필요합니다.

### Azure Active Directory

Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다. Microsoft Office 365 또는 Intune을 사용하는 조직은 이미 무료, 프리미엄 P1 및 Premium P2의 세 가지 버전이 있는 Azure AD를 사용하고 [있습니다(Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 장치 등록을 지원하지만, 나중에 이 가이드에서 사용하게 될 MDM 자동 등록을 사용하려면 Premium P1이 필요합니다.

> [!IMPORTANT]
> HoloLens 장치에서는 프레미스 AD 가입을 지원하지 않는 Azure Active Directory가 필요합니다. Azure Active Directory를&#39;아직 설정하지 않은 경우 이 링크의 지침에 따라 [시작하고 Azure Active Directory에서](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)새 테넌트 만들기.

## ID 관리

직원은 하나의 계정만 사용하여 장치를 초기화할 수 있으므로 조직에서 먼저&#39;계정을 제어해야 합니다. 선택하는 계정이 장치를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다.

이 가이드에서는 사용된 [ID에](https://docs.microsoft.com/hololens/hololens-identity) 대해 AAD 계정 또는 Azure Active Directory 계정을 사용하기로 선택했습니다. 사용하 고자 하는 AAD 계정에는 몇 가지 이점이 있습니다.

- 직원은 자신의 Azure AD 계정을 사용하여 Azure AD에 디바이스를 등록하고 조직&#39;MDM 솔루션(AAD+MDM – Azure AD Premium 필요)에 자동으로 등록합니다.
- AAD 계정은 [Single Sign-On을 지원합니다.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 사용자가 원격 지원에 로그인하면 AAD에 로그인한 사용자의 ID가 인식됩니다. 사용자는 간소화된 환경을 위해 앱에 로그인됩니다.
- AAD 계정에는 [비즈니스용](https://docs.microsoft.com/hololens/hololens-identity) Windows Hello를 통한 추가 인증 [옵션이 있습니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 홍채 로그인 사용자는 다른 장치에서 로그인하거나 FIDO 보안 키를 사용할 수 있습니다.

### 모바일 장치 관리

Enterprise Mobility + Security의 일부인 Microsoft [Intune은](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)테넌트에 연결된 장치를 관리하는 클라우드 기반 MDM 시스템입니다. Office 365와 마찬가지로 Intune은 ID 관리를 위해 Azure AD를 사용 하여 직원이 Office 365에 로그인하는 데 사용하는 동일한 자격 증명을 사용하여 Intune에 장치를 등록합니다. 또한 Intune은 iOS 및 Android와 같은 다른 운영 체제를 실행하여 완전한 MDM 솔루션을 제공하는 장치를 지원합니다. 이 가이드에서는 HoloLens&#39;대규모로 클라우드 배포를 사용하도록 설정하기 위해 Intune을 사용하는 데 중점을 두는 것이 좋습니다.

> [!IMPORTANT]
> 모바일 장치 관리는 반드시 필요합니다. 이 가이드를&#39;아직 설정하지 않은 경우 [Intune으로 시작하세요.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> 여러 MDM 시스템이 Windows 10을 지원하고 개인 및 회사 장치 배포 시나리오를 지원합니다. Windows 10 Holographic을 지원하는 MDM 공급자는 현재 AirWatch, MobileIron 등입니다. 업계 최고의 MDM 공급업체가 대부분 Azure AD와의 통합을 이미 지원하고 있습니다. [Azure 마켓플레이스](https://azure.microsoft.com/marketplace/)에서 Azure AD를 지원하는 MDM 공급업체를 찾을 수 있습니다.

## 네트워크

이 설치에서는 사용 가능한 열려 있는 모든 네트워크에서 인터넷에 연결하는 HoloLens 2 Wi-Fi 있습니다. 사용자는 위치에 따라 네트워크 연결을 변경해야 할 수 있습니다. [HoloLens 장치를 Wi-Fi에](https://docs.microsoft.com/hololens/hololens-network) 연결하는 방법을 배워야 합니다.

Dynamics 365 Remote Assist의 경우 비디오 통화 환경에 영향을 줄 수 있는 대역폭, 대기 시간, 지터 및 패킷 손실을 비롯한 다양한 네트워크 조건이 있습니다. 대역폭이 감소된 환경에서는 오디오 및 비디오 통화가 가능하기는 하지만 기능 저하가 발생할 수 있습니다. HoloLens에서 Dynamics 365 원격 도우미를 사용하는 경우 유의해야 할 네트워크 요구 사항은 다음과 같습니다.

**최소값:** 30ps의 HD 1080p 해상도를 사용한 피어 투 피어 HD 화질 비디오 통화의 경우 1.5Mbps의 업/다운이 필요합니다.

**최적:** 해상도가 HD 1080p인 피어 투 피어 HD 품질 비디오 통화의 경우 4-5Mbps의 업/다운이 예상됩니다.

추가 정보:

- [네트워크 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [네트워크 최적화 권장 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### 선택 사항: HoloLens를 VPN에 연결

이 가이드에 연결되는 장치는 외부 클라우드 네트워크를 통해 네트워크에 연결합니다. 회사 리소스에 액세스하려면 VPN을&#39;장치를 연결해야 할 수 있습니다. 최종 사용자가 장치 UI를 사용하여 연결할 수 있는 경우 또는 장치를 관리하고 PPKG 또는 MDM에서 VPN 프로필을 수신할 수 있는 VPN에 장치를 연결하는 방법에는 여러 가지가 있습니다. VPN을 설정하는&#39;내용은 이 문서에서 다루지 않습니다. 따라서 다른 VPN 프로토콜 또는 VPN 관리&#39;방법에 대해 자세히 알아보고자 하는 경우 [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) 및 VPN에 대한 정보를 참조하세요.

## 다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 구성](hololens2-cloud-connected-configure.md)
