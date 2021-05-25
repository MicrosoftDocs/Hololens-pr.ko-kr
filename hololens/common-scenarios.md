---
title: 일반적인 인프라 배포 시나리오
description: 혼합 현실에 대한 다양한 인프라 배포를 기반으로 하는 가장 일반적인 배포 시나리오 중 일부에 대해 알아봅니다.
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397428"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="ea9b0-104">일반적인 인프라 배포 시나리오 개요</span><span class="sxs-lookup"><span data-stu-id="ea9b0-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="ea9b0-105">다음 정보는 기업 내에서 Microsoft HoloLens 2개의 디바이스를 배포하고 관리할 때 세 가지 일반적인 시나리오에 대한 대략적인 아키텍처 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="ea9b0-106">종종 디바이스를 관리하는 방법과 조직의 리소스에 액세스하는 방법은 이미 있는 요인에 따라 크게 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="ea9b0-107">기존 인프라에 따라 다음 시나리오에서 일반적인 디바이스 관리 스타일을 검토하고 요구 사항에 맞는 시나리오에서 배포하기 위한 가이드를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="ea9b0-108">시나리오</span><span class="sxs-lookup"><span data-stu-id="ea9b0-108">Scenarios</span></span>

<span data-ttu-id="ea9b0-109">아래 다이어그램은 HoloLens 2 배포에 대한 두 가지 일반적인 관리형 시나리오를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="ea9b0-110">오프라인 보안 배포를 허용하는 세 번째 시나리오도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="ea9b0-111">시나리오 A: 클라우드 연결 디바이스에 배포</span><span class="sxs-lookup"><span data-stu-id="ea9b0-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="ea9b0-112">HoloLens 2 주로 회사 네트워크 외부 환경에서 사용하기 위해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="ea9b0-113">회사 리소스는 액세스되지 않거나 VPN을 통해 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="ea9b0-114">이 배포는 회사 내의 관리되는 모바일 디바이스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="ea9b0-115">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="ea9b0-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="ea9b0-116">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="ea9b0-117">MDM(모바일 장치 관리) 자동 등록을 사용하여 Azure AD 조인--MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="ea9b0-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="ea9b0-118">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="ea9b0-119">지원되는 디바이스당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="ea9b0-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="ea9b0-120">디바이스 잠금 구성의 다양한 수준은 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="ea9b0-121">MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="ea9b0-122">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="ea9b0-122">Common Challenges</span></span>
   * <span data-ttu-id="ea9b0-123">시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정</span><span class="sxs-lookup"><span data-stu-id="ea9b0-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="ea9b0-124">[![시나리오 A 다이어그램 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ea9b0-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="ea9b0-125">이 시나리오와 유사한 배포 가이드는 [클라우드 연결 환경 배포](hololens2-cloud-connected-overview.md)가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ea9b0-126">클라우드 연결 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="ea9b0-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="ea9b0-127">클라우드 연결 환경 (외부 클라이언트) 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="ea9b0-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="ea9b0-128">시나리오 B: 조직의 네트워크 내에 배포</span><span class="sxs-lookup"><span data-stu-id="ea9b0-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="ea9b0-129">HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 대 한 액세스 권한이 있는 회사 네트워크에서 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="ea9b0-130">인터넷 및 클라우드 서비스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="ea9b0-131">이 배포는 대부분의 Windows 10 Pc에 대 한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="ea9b0-132">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="ea9b0-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="ea9b0-133">Wi-Fi 네트워크는 내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 이며 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="ea9b0-134">MDM 자동 등록을 사용 하는 Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="ea9b0-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="ea9b0-135">MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="ea9b0-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="ea9b0-136">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="ea9b0-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="ea9b0-137">지원 되는 장치 당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="ea9b0-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="ea9b0-138">다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="ea9b0-139">MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="ea9b0-140">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="ea9b0-140">Common Challenges</span></span>
   * <span data-ttu-id="ea9b0-141">HoloLens 2는 온-프레미스 AD 조인 또는 SCCM을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="ea9b0-142">MDM과 Azure AD 조인만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="ea9b0-143">오늘날 많은 회사에서 온-프레미스 AD 조인 디바이스로 이 시나리오에서 여전히 Windows 10 PC를 배포하고 있으며, SCCM(System Center 구성 관리자)으로 관리되며 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 디바이스를 관리하기 위해 인프라를 배포/구성하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="ea9b0-144">HoloLens 2 클라우드 우선 디바이스이므로 사용자 인증, OS 업데이트, MDM 관리 등을 위해 인터넷 및 클라우드 연결 서비스에 크게 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="ea9b0-145">회사 네트워크에 연결할 때 프록시/방화벽 규칙을 조정하여 HoloLens 2 및 해당 네트워크에서 실행되는 애플리케이션에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="ea9b0-146">회사 Wi-Fi 연결에는 일반적으로 네트워크에 대한 디바이스 또는 사용자를 인증하기 위한 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="ea9b0-147">MDM을 통해 Windows 10 디바이스에 인증서를 배포하는 데 필요한 인프라 또는 설정은 구성하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="ea9b0-148">[![시나리오 B1 다이어그램 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ea9b0-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="ea9b0-149">[![시나리오 B2 다이어그램 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ea9b0-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="ea9b0-150">이 시나리오와 유사한 배포 가이드는 회사 [네트워크 배포 가이드](hololens2-corp-connected-overview.md)에 대한 가이드를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ea9b0-151">회사 네트워크 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="ea9b0-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="ea9b0-152">시나리오 C: 안전한 오프라인 환경에 배포</span><span class="sxs-lookup"><span data-stu-id="ea9b0-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="ea9b0-153">HoloLens 2 네트워크 또는 인터넷 액세스 없이 주로 오프라인에서 사용하도록 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="ea9b0-154">이는 매우 안전한 위치 또는 기밀 위치에 대한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="ea9b0-155">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="ea9b0-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="ea9b0-156">Wi-Fi 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="ea9b0-157">필요한 경우 USB를 통한 이더넷에서 LAN 연결을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="ea9b0-158">관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-158">Not Managed.</span></span>
   * <span data-ttu-id="ea9b0-159">디바이스 로그인에 대한 로컬 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="ea9b0-160">HoloLens 2 하나의 로컬 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="ea9b0-161">디바이스 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 프로비전 패키지를 통해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="ea9b0-162">이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="ea9b0-163">프로 비전 패키지를 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="ea9b0-164">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="ea9b0-164">Common Challenges</span></span>
   * <span data-ttu-id="ea9b0-165">프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="ea9b0-166">클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="ea9b0-167">이러한 장치를 수동으로 설정 하 고 구성 하 고 업데이트 해야 하기 때문에 관리 오버 헤드가 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="ea9b0-168">[![오프 라인 보안 다이어그램 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ea9b0-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="ea9b0-169">이 시나리오와 유사한 배포 가이드는 [오프 라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea9b0-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ea9b0-170">오프 라인 보안 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="ea9b0-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
