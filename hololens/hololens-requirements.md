---
title: 일반 배포 시나리오
description: 인프라, Azure Active Directory 및 모바일 디바이스 관리를 포함하여 엔터프라이즈 환경에서 HoloLens 배포하고 관리하는 방법에 대해 자세히 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639831"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="886e4-103">일반 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="886e4-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="886e4-104">개요</span><span class="sxs-lookup"><span data-stu-id="886e4-104">Overview</span></span>

<span data-ttu-id="886e4-105">이 페이지에서는 기업 내에서 Microsoft HoloLens 2개의 디바이스를 배포하고 관리할 때 세 가지 일반적인 시나리오에 대한 개략적인 아키텍처 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="886e4-106">종종 디바이스를 관리하고 조직의 리소스에 액세스하는 방법은 대부분 이미 있는 요인에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="886e4-107">기존 인프라에 따라 다음 시나리오에서 일반적인 MDM(디바이스 관리 스타일)을 검토한 [다음, 상업용 환경에서 배포 HoloLens 2 계획을 읽어](hololens-core-components.md) 요구 사항과 일치하는 시나리오를 결정하도록 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="886e4-108">배포하는 동안 사용할 수 있는 세 가지 해당 가이드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="886e4-109">클라우드 연결 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="886e4-110">클라우드 연결 환경(외부 클라이언트) 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="886e4-111">회사 네트워크 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="886e4-112">오프라인 보안 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="886e4-113">시나리오 A: 클라우드 연결 디바이스에 배포</span><span class="sxs-lookup"><span data-stu-id="886e4-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="886e4-114">이 시나리오는 회사 내에서 관리되는 모바일 디바이스를 배포하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="886e4-115">HoloLens 2 주로 회사 네트워크 외부 환경에서 사용하기 위해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="886e4-116">회사 리소스는 액세스되지 않거나 VPN을 통해 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="886e4-117">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="886e4-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="886e4-118">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="886e4-119">MDM(모바일 장치 관리) 자동 등록을 사용하여 Azure AD 조인--MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="886e4-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="886e4-120">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="886e4-121">지원되는 디바이스당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="886e4-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="886e4-122">디바이스 잠금 구성의 다양한 수준은 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="886e4-123">MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="886e4-124">일반적인 과제</span><span class="sxs-lookup"><span data-stu-id="886e4-124">Common Challenges</span></span>
   * <span data-ttu-id="886e4-125">시나리오 요구 사항에 따라 HoloLens 2 적용할 MDM 구성 결정</span><span class="sxs-lookup"><span data-stu-id="886e4-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="886e4-126">[![시나리오 다이어그램 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="886e4-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="886e4-127">해당 클라우드 연결 가이드에서는 디바이스 관리에 HoloLens 2 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 디바이스 설정 시 Remote Assist 즉시 사용할 수 있는지 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="886e4-128">단기 또는 장기 외부 사용을 위해 외부 클라이언트 가이드를 사용하여 원격 사이트에 디바이스를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="886e4-129">클라우드 연결 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="886e4-130">클라우드 연결 환경(외부 클라이언트) 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="886e4-131">시나리오 B: 조직의 네트워크 내에 배포</span><span class="sxs-lookup"><span data-stu-id="886e4-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="886e4-132">이 시나리오는 대부분의 Windows 10 PC에 대한 클래식 배포와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="886e4-133">HoloLens 2 주로 회사 네트워크에서 내부 회사 리소스에 액세스할 수 있도록 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="886e4-134">인터넷 및 클라우드 서비스가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="886e4-135">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="886e4-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="886e4-136">Wi-Fi 네트워크는 내부 리소스에 액세스하고 인터넷 또는 클라우드 서비스에 대한 액세스가 제한된 내부 회사 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="886e4-137">MDM 자동 등록을 사용하여 Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="886e4-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="886e4-138">MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="886e4-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="886e4-139">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="886e4-140">지원되는 디바이스당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="886e4-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="886e4-141">디바이스 잠금 구성의 다양한 수준은 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="886e4-142">MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="886e4-143">일반적인 과제</span><span class="sxs-lookup"><span data-stu-id="886e4-143">Common Challenges</span></span>
   * <span data-ttu-id="886e4-144">HoloLens 2 온-프레미스 AD 조인 또는 SCCM을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="886e4-145">MDM과 Azure AD 조인만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="886e4-146">오늘날 많은 회사에서 온-프레미스 AD 조인 디바이스와 같이 이 시나리오에서 여전히 Windows 10 PC를 배포하고 있으며, SCCM(System Center Configuration Manager)으로 관리되며 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 디바이스를 관리하기 위해 인프라를 배포/구성하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="886e4-147">HoloLens 2 클라우드 우선 디바이스이므로 사용자 인증, OS 업데이트, MDM 관리 등을 위해 인터넷 및 클라우드 연결 서비스에 크게 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="886e4-148">회사 네트워크에 연결할 때 프록시/방화벽 규칙을 조정하여 HoloLens 2 및 해당 네트워크에서 실행되는 애플리케이션에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="886e4-149">회사 Wi-Fi 연결에는 일반적으로 네트워크에 대한 디바이스 또는 사용자를 인증하기 위한 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="886e4-150">MDM을 통해 Windows 10 디바이스에 인증서를 배포하는 데 필요한 인프라 또는 설정은 구성하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="886e4-151">[![시나리오 B1 다이어그램 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="886e4-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="886e4-152">[![시나리오 B2 다이어그램 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="886e4-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="886e4-153">해당 회사 네트워크 가이드에서는 디바이스를 설정한 후 기존 디바이스 관리에 HoloLens 2 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 Dynamics 365 가이드를 작동하고 사용자 지정 기간 업무 앱을 사용할 수 있는지 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="886e4-154">회사 네트워크 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="886e4-155">시나리오 C: 안전한 오프라인 환경에 배포</span><span class="sxs-lookup"><span data-stu-id="886e4-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="886e4-156">이는 매우 안전한 위치 또는 기밀 위치에 대한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="886e4-157">HoloLens 2 네트워크 또는 인터넷 액세스 없이 주로 오프라인에서 사용하도록 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="886e4-158">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="886e4-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="886e4-159">Wi-Fi 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="886e4-160">필요한 경우 USB를 통한 이더넷에서 LAN 연결을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="886e4-161">관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-161">Not Managed.</span></span>
   * <span data-ttu-id="886e4-162">디바이스 로그인에 대한 로컬 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="886e4-163">HoloLens 2 하나의 로컬 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="886e4-164">디바이스 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 프로비전 패키지를 통해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="886e4-165">이러한 구성은 일반적으로 보안 환경 요구 사항으로 인해 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="886e4-166">하나 이상의 애플리케이션이 프로비전 패키지를 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="886e4-167">일반적인 과제</span><span class="sxs-lookup"><span data-stu-id="886e4-167">Common Challenges</span></span>
   * <span data-ttu-id="886e4-168">프로비전 패키지를 통해 사용할 수 있는 제한된 구성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="886e4-169">클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="886e4-170">이러한 디바이스를 수동으로 설정, 구성 및 업데이트해야 하기 때문에 관리 오버헤드가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="886e4-171">[![오프라인 보안 다이어그램 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="886e4-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="886e4-172">해당 오프라인 보안 가이드에서는 보안 환경에서 사용하기 위해 HoloLens 2 잠그는 샘플 프로비전 패키지를 적용하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="886e4-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="886e4-173">오프라인 보안 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="886e4-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


