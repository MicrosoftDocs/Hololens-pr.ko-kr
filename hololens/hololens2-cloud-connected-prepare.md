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
# <a name="prepare---cloud-connected-guide"></a><span data-ttu-id="0dfe3-104">준비 - 클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="0dfe3-104">Prepare - Cloud connected Guide</span></span>

<span data-ttu-id="0dfe3-105">이 문서의 끝부분에서는 Azure AD, MDM을 설정하고 Azure AD 계정 및 네트워크 요구 사항을 사용하는 것에 대해 자세히 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-105">By the end of this article you will have set up Azure AD, MDM, and understand more about using Azure AD accounts and network requirements.</span></span> <span data-ttu-id="0dfe3-106">가이드의 이 섹션은 사용자와 조직이 클라우드에 HoloLens 2 배포하고 Dynamics 365 Remote Assist 사용할 준비를 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-106">This section of the guide will help you and your organization get prepared to deploy HoloLens 2 to the cloud and use Dynamics 365 Remote Assist.</span></span> <span data-ttu-id="0dfe3-107">인프라의 각 부분의 중요성을 넘어가며, 필요에 따라 이러한 부분을 설정하는 데 도움이 되는 가이드 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-107">It will go over the importance of each piece of your infrastructure as well as providing links to guides to help you set up those pieces as needed.</span></span>

## <a name="infrastructure-essentials"></a><span data-ttu-id="0dfe3-108">Infrastructure Essentials</span><span class="sxs-lookup"><span data-stu-id="0dfe3-108">Infrastructure Essentials</span></span>

<span data-ttu-id="0dfe3-109">개인 및 회사 배포 시나리오의 경우 MDM 시스템은 Windows 10 Holographic 디바이스를 배포하고 관리하는 데 필요한 필수 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-109">For both personal and corporate deployment scenarios, an MDM system is the essential infrastructure required to deploy and manage Windows 10 Holographic devices.</span></span> <span data-ttu-id="0dfe3-110">Azure AD 프리미엄 구독은 ID 공급자로 권장되며 특정 기능을 지원하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-110">An Azure AD premium subscription is recommended as an identity provider and required to support certain capabilities.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="0dfe3-111">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0dfe3-111">Azure Active Directory</span></span>

<span data-ttu-id="0dfe3-112">Azure AD는 ID 및 액세스 관리를 제공하는 클라우드 기반 디렉터리 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-112">Azure AD is a cloud-based directory service that provides identity and access management.</span></span> <span data-ttu-id="0dfe3-113">Microsoft Office 365 또는 Intune을 사용하는 조직은 이미 무료, Premium P1 및 Premium P2의 세 가지 버전이 있는 Azure AD를 사용하고 [있습니다(Azure Active Directory 버전](https://azure.microsoft.com/documentation/articles/active-directory-editions)참조). 모든 버전은 Azure AD 디바이스 등록을 지원하지만 나중에 이 가이드에서 사용할 MDM 자동 등록을 사용하도록 설정하려면 Premium P1이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-113">Organizations that use Microsoft Office 365 or Intune are already using Azure AD, which has three editions: Free, Premium P1, and Premium P2 (see [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) All editions support Azure AD device registration, but Premium P1 is required to enable MDM auto-enrollment which we will be using in this guide later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dfe3-114">HoloLens 디바이스가 온-프레미스 AD 조인을 지원하지 않기 때문에 Azure Active Directory 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-114">It is essential to have an Azure Active Directory as HoloLens devices do not support on-premises AD join.</span></span> <span data-ttu-id="0dfe3-115">Azure Active Directory 설정하지&#39;경우 Azure Active Directory [새 테넌트 만들기로](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-115">If you don&#39;t already have an Azure Active Directory set up, go to [Create a new tenant in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).</span></span>

## <a name="identity-management"></a><span data-ttu-id="0dfe3-116">ID 관리</span><span class="sxs-lookup"><span data-stu-id="0dfe3-116">Identity Management</span></span>

<span data-ttu-id="0dfe3-117">직원은 하나의 계정만 사용하여 디바이스를 초기화할 수 있으므로 조직에서 먼저 사용하도록 설정된 계정을 제어해야&#39;.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-117">Employees can use only one account to initialize a device so it&#39;s imperative that your organization controls which account is enabled first.</span></span> <span data-ttu-id="0dfe3-118">선택한 계정은 디바이스를 제어하는 사람을 결정하고 관리 기능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-118">The account chosen will determine who controls the device and influence your management capabilities.</span></span>

<span data-ttu-id="0dfe3-119">이 가이드에서는 사용된 [ID에](/hololens/hololens-identity) 대해 Azure AD 계정 또는 Azure Active Directory 계정을 사용하도록 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-119">In this guide we have chosen that for the [Identity](/hololens/hololens-identity) used we will use Azure AD accounts, or Azure Active Directory accounts.</span></span> <span data-ttu-id="0dfe3-120">사용하려는 Azure AD 계정에는 다음과 같은 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-120">There are several benefits to Azure AD accounts we would like to use, such as:</span></span>

- <span data-ttu-id="0dfe3-121">직원은 Azure AD 계정을 사용하여 Azure AD에 디바이스를 등록하고 조직의&#39;MDM 솔루션에 자동으로 등록합니다(Azure AD+MDM – Azure AD Premium 필요).</span><span class="sxs-lookup"><span data-stu-id="0dfe3-121">Employees use their Azure AD account to register the device in Azure AD and automatically enroll it with the organization&#39;s MDM solution (Azure AD+MDM – requires Azure AD Premium).</span></span>
- <span data-ttu-id="0dfe3-122">Azure AD 계정은 [Single #A0](/azure/active-directory/manage-apps/what-is-single-sign-on)지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-122">Azure AD accounts support [Single Sign On](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span> <span data-ttu-id="0dfe3-123">사용자가 Remote Assist 로그인하면 로그인한 Azure AD 사용자의 ID가 인식되고 사용자가 간소화된 환경을 위해 앱에 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-123">When a user signs into Remote Assist, their Identity from the signed in Azure AD user will be recognized and the user will be signed into the app for a streamlined experience.</span></span>
- <span data-ttu-id="0dfe3-124">Azure AD 계정에는 [비즈니스용 Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)통해 추가 [인증 옵션이](/hololens/hololens-identity) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-124">Azure AD accounts have additional [authentication options](/hololens/hololens-identity) via [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).</span></span> <span data-ttu-id="0dfe3-125">아이리스 로그인 외에도 사용자는 다른 디바이스에서 로그인하거나 FIDO 보안 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-125">In addition to Iris log-in users can sign in from another device or use FIDO security keys.</span></span>

### <a name="mobile-device-management"></a><span data-ttu-id="0dfe3-126">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="0dfe3-126">Mobile Device Management</span></span>

<span data-ttu-id="0dfe3-127">Enterprise Mobility + Security 일부인 Microsoft [Intune은](/mem/intune/fundamentals/what-is-intune)테넌트 연결 디바이스를 관리하는 클라우드 기반 MDM 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-127">Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), part of the Enterprise Mobility + Security, is a cloud-based MDM system that manages devices connected to your tenant.</span></span> <span data-ttu-id="0dfe3-128">Office 365 마찬가지로 Intune은 ID 관리에 Azure AD를 사용하므로 직원은 동일한 자격 증명을 사용하여 Intune에 디바이스를 등록하고 Office 365 로그인하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-128">Like Office 365, Intune uses Azure AD for identity management, so employees use the same credentials to enroll devices in Intune that they use to sign into Office 365.</span></span> <span data-ttu-id="0dfe3-129">또한 Intune은 iOS 및 Android와 같은 다른 운영 체제를 실행하는 디바이스를 지원하여 완전한 MDM 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-129">Intune also supports devices that run other operating systems, such as iOS and Android, to provide a complete MDM solution.</span></span> <span data-ttu-id="0dfe3-130">이 가이드의 목적을 위해&#39;HoloLens 2 대규모로 클라우드 배포를 사용하도록 설정하기 위해 Intune을 사용하는 데 중점을 두겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-130">For the purposes of this guide, we&#39;ll be focusing on using Intune for enabling a cloud deployment at scale with HoloLens 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dfe3-131">모바일 장치 관리 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-131">It is essential to have Mobile Device Management.</span></span> <span data-ttu-id="0dfe3-132">&#39;설정하지 않은 경우 이 가이드 및 [Intune 시작에](/mem/intune/fundamentals/free-trial-sign-up)따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-132">If you don&#39;t already have it set up follow this guide and [Get started with Intune](/mem/intune/fundamentals/free-trial-sign-up).</span></span>

> [!NOTE]
> <span data-ttu-id="0dfe3-133">여러 MDM 시스템은 Windows 10 지원하며 대부분의 경우 개인 및 회사 디바이스 배포 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-133">Multiple MDM systems support Windows 10 and most support personal and corporate device deployment scenarios.</span></span> <span data-ttu-id="0dfe3-134">현재 Windows 10 Holographic 지원하는 MDM 공급자에는 AirWatch, MobileIron 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-134">MDM providers that support Windows 10 Holographic currently include: AirWatch, MobileIron, and others.</span></span> <span data-ttu-id="0dfe3-135">대부분의 업계 최고의 MDM 공급업체는 이미 Azure AD와의 통합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-135">Most industry-leading MDM vendors already support integration with Azure AD.</span></span> <span data-ttu-id="0dfe3-136">[Azure Marketplace](https://azure.microsoft.com/marketplace/)Azure AD를 지원하는 MDM 공급업체를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-136">You can find the MDM vendors that support Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).</span></span>

## <a name="network"></a><span data-ttu-id="0dfe3-137">네트워크</span><span class="sxs-lookup"><span data-stu-id="0dfe3-137">Network</span></span>

<span data-ttu-id="0dfe3-138">이 설정에서는 사용 가능한 모든 열린 Wi-Fi 네트워크에서 인터넷에 연결하는 HoloLens 2 디바이스를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-138">In this setup, we anticipate HoloLens 2 devices connecting to the Internet from any available open Wi-Fi network.</span></span> <span data-ttu-id="0dfe3-139">사용자는 위치에 따라 네트워크 연결을 변경해야 할 수 있기 때문에 [HoloLens 디바이스를 Wi-Fi에 연결하는](/hololens/hololens-network) 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-139">Since a user could need to change the network connection based on location, they should learn how to [connect HoloLens devices to Wi-Fi.](/hololens/hololens-network)</span></span>

<span data-ttu-id="0dfe3-140">Dynamics 365 Remote Assist 경우 대역폭, 대기 시간, 지터 및 패킷 손실을 포함하여 비디오 통화 환경에 영향을 줄 수 있는 다양한 네트워크 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-140">For Dynamics 365 Remote Assist there are a variety of network conditions, including bandwidth, latency, jitter, and packet loss, that can impact your video calling experience.</span></span> <span data-ttu-id="0dfe3-141">대역폭이 감소된 환경에서는 오디오 및 비디오 호출이 가능할 수 있지만 기능 저하가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-141">Although audio and video calls might be possible in environments with reduced bandwidth, you might experience feature degradation.</span></span> <span data-ttu-id="0dfe3-142">HoloLens Dynamics 365 Remote Assist 사용하는 경우 다음 네트워크 요구 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-142">When using Dynamics 365 Remote Assist on HoloLens here are the network requirements to keep in mind:</span></span>

<span data-ttu-id="0dfe3-143">**최소** : 30fps에서 HD 1080p 해상도를 사용하여 피어 투 피어 HD 품질 비디오 통화에 1.5Mbps의 업/다운이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-143">**Minimum** : 1.5 Mbps up/down is required for peer-to-peer HD quality video calling with resolution of HD 1080p at 30 fps.</span></span>

<span data-ttu-id="0dfe3-144">**최적:** HD 1080p 해상도를 사용하여 피어 투 피어 HD 품질 비디오 통화의 경우 4-5Mbps 업/다운이 예상되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-144">**Optimal:** For peer-to-peer HD quality video calling with resolution of HD 1080p, 4-5 Mbps up/down should be expected.</span></span>

<span data-ttu-id="0dfe3-145">추가 정보:</span><span class="sxs-lookup"><span data-stu-id="0dfe3-145">More information:</span></span>

- [<span data-ttu-id="0dfe3-146">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dfe3-146">Network requirements</span></span>](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [<span data-ttu-id="0dfe3-147">네트워크 최적화 권장 사항</span><span class="sxs-lookup"><span data-stu-id="0dfe3-147">Network optimization recommendations</span></span>](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a><span data-ttu-id="0dfe3-148">선택 사항: VPN에 HoloLens 커넥트</span><span class="sxs-lookup"><span data-stu-id="0dfe3-148">Optional: Connect your HoloLens to VPN</span></span>

<span data-ttu-id="0dfe3-149">이 가이드에 연결된 디바이스는 및 외부 클라우드 네트워크를 통해 네트워크에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-149">The devices being connected into this guide are going to connect to the network via and external cloud network.</span></span> <span data-ttu-id="0dfe3-150">&#39;회사 리소스에 액세스하려면 VPN을 통해 디바이스를 연결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-150">It may be that to access company resources you&#39;ll need to connect your devices via VPN.</span></span> <span data-ttu-id="0dfe3-151">디바이스를 VPN에 연결하는 방법에는 여러 가지가 있습니다. 두 방법 모두 최종 사용자가 디바이스 UI를 사용하여 연결할 수 있거나 디바이스를 관리하고 PPKG 또는 MDM에서 VPN 프로필을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfe3-151">There are several different ways to connect your devices to VPN, both where the end user can connect via using the device UI, or the devices can be managed and receive the VPN profile from either a PPKG or MDM.</span></span> <span data-ttu-id="0dfe3-152">VPN을 설정하는 방법은 이 문서에서 다루지&#39;&#39;. 따라서 다양한 VPN 프로토콜 또는 VPN을 관리하는 방법에 대해 자세히 알아보려면 [HoloLens 및 VPN에 대한 자세한 내용은 이 가이드를 참조하세요.](/hololens/hololens-network#vpn)</span><span class="sxs-lookup"><span data-stu-id="0dfe3-152">How to set up VPN won&#39;t be covered in this article, so if you&#39;d like to learn more about the different VPN protocols or ways to manage VPN visit [these guides for information on HoloLens and VPN.](/hololens/hololens-network#vpn)</span></span>

## <a name="next-step"></a><span data-ttu-id="0dfe3-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0dfe3-153">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0dfe3-154">클라우드 연결 배포 - 구성</span><span class="sxs-lookup"><span data-stu-id="0dfe3-154">Cloud connected deployment - Configure</span></span>](hololens2-cloud-connected-configure.md)
