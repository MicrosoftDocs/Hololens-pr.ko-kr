---
title: 일반적인 인프라 배포 시나리오
description: 혼합 현실에 대해 다양 한 인프라 배포를 기반으로 하는 가장 일반적인 배포 시나리오 중 일부에 대해 알아봅니다.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309480"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="78a39-104">일반적인 인프라 배포 시나리오 개요</span><span class="sxs-lookup"><span data-stu-id="78a39-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="78a39-105">다음 정보는 기업 내에서 Microsoft HoloLens 2 장치를 배포 및 관리 하는 세 가지 일반적인 시나리오에 대 한 개략적인 아키텍처 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="78a39-106">일반적으로 장치를 관리 하는 방법과 조직의 리소스에 액세스 하는 방법은 이미 사용 되는 요인에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="78a39-107">기존 인프라에 따라 다음과 같은 시나리오에서 일반적인 장치 관리 스타일을 검토 하 고 필요에 맞는 시나리오에서 배포를 위한 가이드를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="78a39-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="78a39-108">시나리오</span><span class="sxs-lookup"><span data-stu-id="78a39-108">Scenarios</span></span>

<span data-ttu-id="78a39-109">아래 다이어그램은 HoloLens 2 배포에 대 한 세 가지 일반적인 시나리오를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
<span data-ttu-id="78a39-110">![시나리오 다이어그램](images/scenarios.jpg)</span><span class="sxs-lookup"><span data-stu-id="78a39-110">![Scenarios diagram](images/scenarios.jpg)</span></span>

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="78a39-111">시나리오 A: 클라우드 연결 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="78a39-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="78a39-112">HoloLens 2는 주로 회사 네트워크 외부 환경에서 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="78a39-113">회사 리소스에 액세스 하지 않거나 VPN을 통해 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="78a39-114">이 배포는 회사 내에서 관리 되는 모바일 장치와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="78a39-115">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="78a39-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="78a39-116">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열립니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="78a39-117">MDM (모바일 장치 관리) 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="78a39-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="78a39-118">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="78a39-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="78a39-119">지원 되는 장치 당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="78a39-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="78a39-120">다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="78a39-121">MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="78a39-122">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="78a39-122">Common Challenges</span></span>
   * <span data-ttu-id="78a39-123">시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정</span><span class="sxs-lookup"><span data-stu-id="78a39-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="78a39-124">시나리오와 유사한 배포 가이드는 [원격 지원에 대 한 클라우드 연결 HoloLens 2](hololens2-cloud-connected-overview.md)가이드를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="78a39-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78a39-125">배포 가이드-클라우드 연결 HoloLens 2 (원격 지원 포함)</span><span class="sxs-lookup"><span data-stu-id="78a39-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="78a39-126">시나리오 B: 조직의 네트워크 내에 배포</span><span class="sxs-lookup"><span data-stu-id="78a39-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="78a39-127">HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 대 한 액세스 권한이 있는 회사 네트워크에서 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="78a39-128">인터넷 및 클라우드 서비스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="78a39-129">이 배포는 대부분의 Windows 10 Pc에 대 한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="78a39-130">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="78a39-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="78a39-131">Wi-Fi 네트워크는 내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 이며 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="78a39-132">MDM 자동 등록을 사용 하는 Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="78a39-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="78a39-133">MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="78a39-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="78a39-134">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="78a39-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="78a39-135">지원 되는 장치 당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="78a39-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="78a39-136">다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="78a39-137">MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="78a39-138">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="78a39-138">Common Challenges</span></span>
   * <span data-ttu-id="78a39-139">HoloLens 2는 온-프레미스 AD 조인 또는 SCCM을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="78a39-140">MDM을 사용 하는 Azure AD 조인만</span><span class="sxs-lookup"><span data-stu-id="78a39-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="78a39-141">오늘날 대부분의 회사에서는이 시나리오에서 Windows 10 Pc를 System Center Configuration Manager (SCCM)에서 관리 하는 온-프레미스 AD 조인 장치에 배포 하 고, 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 장치를 관리 하기 위해 인프라를 배포/구성 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="78a39-142">HoloLens 2는 클라우드 우선 장치 이며, 사용자 인증, OS 업데이트, MDM 관리 등에 대 한 인터넷 및 클라우드 연결 서비스에 크게 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="78a39-143">회사 네트워크에 연결 하는 경우 HoloLens 2 및이를 실행 하는 응용 프로그램에 대 한 액세스를 사용 하도록 설정 하기 위해 프록시/방화벽 규칙을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="78a39-144">회사 Wi-Fi 연결에는 일반적으로 네트워크에 대 한 장치 또는 사용자를 인증 하기 위한 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="78a39-145">MDM을 통해 Windows 10 장치에 인증서를 배포 하는 데 필요한 인프라 또는 설정은 구성 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78a39-146">배포 가이드 – Dynamics 365 가이드를 사용 하 여 회사에 연결 된 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="78a39-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="78a39-147">시나리오 C: 보안 오프 라인 환경에서 배포</span><span class="sxs-lookup"><span data-stu-id="78a39-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="78a39-148">HoloLens 2는 네트워크 또는 인터넷 액세스 없이 주로 오프 라인으로 사용 하기 위해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="78a39-149">이는 보안 수준이 높은 또는 기밀 위치의 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="78a39-150">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="78a39-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="78a39-151">Wi-Fi 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="78a39-152">필요한 경우 USB를 통한 이더넷 LAN 연결을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="78a39-153">관리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-153">Not Managed.</span></span>
   * <span data-ttu-id="78a39-154">장치 로그인에 대 한 로컬 사용자 계정.</span><span class="sxs-lookup"><span data-stu-id="78a39-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="78a39-155">HoloLens 2는 하나의 로컬 계정만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="78a39-156">다양 한 수준의 장치 잠금 구성은 특정 사용 사례에 따라 프로 비전 패키지를 통해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="78a39-157">이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="78a39-158">프로 비전 패키지를 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="78a39-159">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="78a39-159">Common Challenges</span></span>
   * <span data-ttu-id="78a39-160">프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="78a39-161">클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="78a39-162">이러한 장치를 수동으로 설정 하 고 구성 하 고 업데이트 해야 하기 때문에 관리 오버 헤드가 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="78a39-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="78a39-163">이 시나리오와 유사한 배포 가이드는 [오프 라인 보안 배포 가이드](hololens-common-scenarios-offline-secure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78a39-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78a39-164">배포 가이드-오프 라인 보안 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="78a39-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
