---
title: 일반 배포 시나리오
description: 인프라, Azure Active Directory 및 모바일 장치 관리를 포함 하 여 엔터프라이즈 환경에서 HoloLens 배포 및 관리에 대해 자세히 알아보세요.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635469"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="112ef-103">일반 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="112ef-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="112ef-104">개요</span><span class="sxs-lookup"><span data-stu-id="112ef-104">Overview</span></span>

<span data-ttu-id="112ef-105">이 페이지에서는 기업 내에서 2 대의 장치 Microsoft HoloLens을 배포 하 고 관리할 때 세 가지 일반적인 시나리오에 대 한 개략적인 아키텍처 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="112ef-106">일반적으로 장치를 관리 하 고 조직의 리소스에 액세스 하는 방법은 이미 마련 된 요인에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="112ef-107">기존 인프라에 따라 다음과 같은 시나리오에서 일반적인 MDM (장치 관리 스타일)을 검토 하 고 [상업적 환경에서 HoloLens 2 배포 계획](hololens-core-components.md) 을 읽어 요구 사항과 일치 하는 시나리오를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="112ef-108">배포 하는 동안 사용할 수 있는 세 가지 해당 가이드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="112ef-109">클라우드 연결 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="112ef-110">클라우드 연결 환경(외부 클라이언트) 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="112ef-111">회사 네트워크 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="112ef-112">오프라인 보안 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="112ef-113">시나리오 A: 클라우드 연결 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="112ef-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="112ef-114">이 시나리오는 회사 내에서 관리 되는 모바일 장치를 배포 하는 것과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="112ef-115">HoloLens 2는 주로 회사 네트워크 외부 환경에서 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="112ef-116">회사 리소스에 액세스 하지 않거나 VPN을 통해 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="112ef-117">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="112ef-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="112ef-118">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열립니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="112ef-119">MDM (모바일 장치 관리) 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="112ef-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="112ef-120">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="112ef-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="112ef-121">지원 되는 장치 당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="112ef-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="112ef-122">다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="112ef-123">MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="112ef-124">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="112ef-124">Common Challenges</span></span>
   * <span data-ttu-id="112ef-125">시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="112ef-126">[![시나리오 A 다이어그램 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="112ef-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="112ef-127">해당 클라우드 연결 가이드에서는 장치 관리에 HoloLens 2를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설치 시 원격 지원을 즉시 사용할 수 있는지 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="112ef-128">외부 클라이언트 가이드를 사용 하 여 단기 또는 장기 외부 사용을 위해 원격 사이트에 장치를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="112ef-129">클라우드 연결 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="112ef-130">클라우드 연결 환경(외부 클라이언트) 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="112ef-131">시나리오 B: 조직의 네트워크 내에 배포</span><span class="sxs-lookup"><span data-stu-id="112ef-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="112ef-132">이 시나리오는 대부분의 Windows 10 pc에 대 한 클래식 배포와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="112ef-133">HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 대 한 액세스 권한이 있는 회사 네트워크에서 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="112ef-134">인터넷 및 클라우드 서비스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="112ef-135">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="112ef-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="112ef-136">Wi-Fi 네트워크는 내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 이며 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="112ef-137">MDM 자동 등록을 사용 하는 Azure AD 조인</span><span class="sxs-lookup"><span data-stu-id="112ef-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="112ef-138">MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="112ef-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="112ef-139">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="112ef-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="112ef-140">지원 되는 장치 당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="112ef-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="112ef-141">다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="112ef-142">MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="112ef-143">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="112ef-143">Common Challenges</span></span>
   * <span data-ttu-id="112ef-144">HoloLens 2 온-프레미스 AD 조인 또는 SCCM을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="112ef-145">MDM을 사용 하는 Azure AD 조인만</span><span class="sxs-lookup"><span data-stu-id="112ef-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="112ef-146">오늘날 대부분의 회사는이 시나리오에서 Windows 10 pc를 온-프레미스 AD 조인 된 장치로 배포 하 고 (SCCM), 클라우드 기반 MDM 솔루션 System Center Configuration Manager을 통해 내부 Windows 10 장치를 관리 하기 위해 인프라를 배포/구성 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="112ef-147">HoloLens 2은 클라우드 우선 장치 이며, 사용자 인증, OS 업데이트, MDM 관리 등에 대해 인터넷 및 클라우드 연결 된 서비스에 크게 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="112ef-148">회사 네트워크에 연결 하는 경우 HoloLens 2 및 해당 응용 프로그램에서 실행 되는 응용 프로그램에 대 한 액세스를 가능 하 게 하기 위해 프록시/방화벽 규칙을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="112ef-149">회사 Wi-Fi 연결에는 일반적으로 네트워크에 대 한 장치 또는 사용자를 인증 하기 위한 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="112ef-150">MDM을 통해 Windows 10 장치에 인증서를 배포 하는 데 필요한 인프라 또는 설정은 구성 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="112ef-151">[![시나리오 B1 다이어그램 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="112ef-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="112ef-152">[![시나리오 B2 다이어그램 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="112ef-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="112ef-153">해당 회사 네트워크 가이드는 기존 장치 관리에 HoloLens 2를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 Dynamics 365 가이드를 작동할 수 있는지 확인 하 고, 장치가 설정 된 후에 사용자 지정 lob (기간 업무) 앱을 사용할 수 있는지 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="112ef-154">회사 네트워크 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="112ef-155">시나리오 C: 보안 오프 라인 환경에서 배포</span><span class="sxs-lookup"><span data-stu-id="112ef-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="112ef-156">이는 보안 수준이 높은 또는 기밀 위치의 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="112ef-157">HoloLens 2는 네트워크 또는 인터넷에 액세스 하지 않고 주로 오프 라인으로 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="112ef-158">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="112ef-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="112ef-159">Wi-Fi 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="112ef-160">필요한 경우 USB를 통한 이더넷 LAN 연결을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="112ef-161">관리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-161">Not Managed.</span></span>
   * <span data-ttu-id="112ef-162">장치 로그인에 대 한 로컬 사용자 계정.</span><span class="sxs-lookup"><span data-stu-id="112ef-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="112ef-163">HoloLens 2는 하나의 로컬 계정만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="112ef-164">다양 한 수준의 장치 잠금 구성은 특정 사용 사례에 따라 프로 비전 패키지를 통해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="112ef-165">이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="112ef-166">프로 비전 패키지를 통해 하나 이상의 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="112ef-167">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="112ef-167">Common Challenges</span></span>
   * <span data-ttu-id="112ef-168">프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="112ef-169">클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="112ef-170">이러한 장치를 수동으로 설정 하 고 구성 하 고 업데이트 해야 하기 때문에 관리 오버 헤드가 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="112ef-171">[![오프 라인 보안 다이어그램 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="112ef-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="112ef-172">해당 오프 라인 보안 가이드에서는 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로 비전 패키지를 적용 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="112ef-173">오프라인 보안 환경 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="112ef-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


