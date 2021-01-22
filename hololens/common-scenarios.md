---
title: 공통 인프라 구축 시나리오
description: 혼합 현실을 위한 다양한 인프라 배포를 기반으로 가장 일반적인 몇 가지 배포 시나리오에 대해 설명합니다.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
keywords: HoloLens
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283629"
---
# <span data-ttu-id="60413-104">일반적인 인프라 배포 시나리오 개요</span><span class="sxs-lookup"><span data-stu-id="60413-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="60413-105">다음 정보는 엔터프라이즈 내에서 Microsoft HoloLens 2 장치를 배포하고 관리할 때의 세 가지 일반적인 시나리오에 대한 간략한 아키텍처 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="60413-106">장치를 관리하는 방법과 조직의 리소스에 액세스하는 방식은 이미 설정되어 있는 요소에 따라 크게 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="60413-107">기존 인프라에 따라 다음 시나리오에서 일반적인 장치 관리 스타일을 검토할 것을 초대하고 요구에 일치하는 시나리오에서 배포에 대한 가이드를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="60413-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="60413-108">시나리오</span><span class="sxs-lookup"><span data-stu-id="60413-108">Scenarios</span></span>

<span data-ttu-id="60413-109">아래 다이어그램은 HoloLens 2 배포에 대한 세 가지 일반적인 시나리오를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![시나리오 다이어그램](images/scenarios.jpg)

### <span data-ttu-id="60413-111">시나리오 A: 클라우드 연결 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="60413-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="60413-112">HoloLens 2는 주로 회사 네트워크 외부의 환경에서 사용하기 위해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="60413-113">회사 리소스에 액세스하지 못하거나 VPN을 통해 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="60413-114">이 배포는 회사 내의 관리되는 모바일 장치와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="60413-115">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="60413-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="60413-116">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="60413-117">MDM(모바일 장치 관리) 자동 등록을 사용하여 Azure AD 가입--MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="60413-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="60413-118">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="60413-119">지원되는 장치당 사용자 한명 또는 여러명</span><span class="sxs-lookup"><span data-stu-id="60413-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="60413-120">장치 잠금 구성의 다양한 수준은 특정 사용 사례(완전히 열기에서 단일 앱 키오스크)에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="60413-121">하나 이상의 응용 프로그램이 MDM을 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="60413-122">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="60413-122">Common Challenges</span></span>
   * <span data-ttu-id="60413-123">시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정</span><span class="sxs-lookup"><span data-stu-id="60413-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="60413-124">시나리오와 유사한 배포 가이드의 경우 원격 지원이 있는 클라우드 연결 [HoloLens 2에 대한 가이드를 검토하세요.](hololens2-cloud-connected-overview.md)</span><span class="sxs-lookup"><span data-stu-id="60413-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60413-125">배포 가이드 - 원격 지원이 있는 클라우드 연결 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="60413-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="60413-126">시나리오 B: 조직의 네트워크 내부 배포</span><span class="sxs-lookup"><span data-stu-id="60413-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="60413-127">HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 액세스할 수 있도록 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="60413-128">인터넷 및 클라우드 서비스가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="60413-129">이 배포는 대부분의 Windows 10 PC에 대한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="60413-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="60413-130">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="60413-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="60413-131">Wi-Fi 네트워크는 내부 리소스에 액세스할 수 있는 내부 회사 네트워크로, 인터넷 또는 클라우드 서비스에 대한 액세스가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="60413-132">MDM 자동 등록을 사용하여 Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="60413-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="60413-133">MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="60413-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="60413-134">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="60413-135">지원되는 장치당 사용자 한명 또는 여러명</span><span class="sxs-lookup"><span data-stu-id="60413-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="60413-136">장치 잠금 구성의 다양한 수준은 특정 사용 사례(완전히 열기에서 단일 앱 키오스크)에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="60413-137">하나 이상의 응용 프로그램이 MDM을 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="60413-138">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="60413-138">Common Challenges</span></span>
   * <span data-ttu-id="60413-139">HoloLens 2는 온-프레미스 AD 조인 또는 SCCM을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="60413-140">MDM을 사용하여 Azure AD 가입만 합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="60413-141">대부분의 회사에서는 이 시나리오에서 여전히 Windows 10 PC를 SCCM(System Center Configuration Manager)에서 관리되는 온-프레미스 AD 가입 장치로 배포하고 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 디바이스를 관리하기 위한 인프라가 배포/구성되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="60413-142">HoloLens 2는 클라우드 첫 번째 장치이기 때문에 사용자 인증, OS 업데이트, MDM 관리 등 인터넷 및 클라우드 연결 서비스에 크게 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="60413-143">회사 네트워크에 연결할 때 HoloLens 2 및 해당 네트워크에서 실행된 응용 프로그램에 액세스할 수 있도록 프록시/방화벽 규칙을 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="60413-144">회사 Wi-Fi 연결하려면 일반적으로 인증서가 장치 또는 사용자를 네트워크에 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="60413-145">MDM을 통해 Windows 10 디바이스에 인증서를 배포하는 데 필요한 인프라 또는 설정은 구성하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="60413-146">시나리오 C: 안전한 오프라인 환경에 배포</span><span class="sxs-lookup"><span data-stu-id="60413-146">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="60413-147">HoloLens 2는 주로 네트워크 또는 인터넷 액세스가 없는 오프라인으로 사용하기 위해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-147">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="60413-148">이는 보안이 뛰어난 위치나 기밀 위치에 대한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="60413-148">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="60413-149">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="60413-149">Basic Common Configurations</span></span>
   * <span data-ttu-id="60413-150">Wi-Fi 연결이 사용되지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-150">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="60413-151">필요한 경우 USB를 통한 이더넷이 LAN 연결을 사용하도록 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-151">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="60413-152">관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-152">Not Managed.</span></span>
   * <span data-ttu-id="60413-153">디바이스 로그인에 대한 로컬 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="60413-153">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="60413-154">HoloLens 2는 하나의 로컬 계정만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-154">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="60413-155">장치 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 프로비저닝 패키지를 통해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-155">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="60413-156">이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-156">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="60413-157">프로비저닝 패키지를 통해 하나 이상의 응용 프로그램이 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="60413-157">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="60413-158">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="60413-158">Common Challenges</span></span>
   * <span data-ttu-id="60413-159">프로비저닝 패키지를 통해 사용할 수 있는 제한된 구성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60413-159">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="60413-160">클라우드 서비스는 사용할 수 없습니다. 따라서 HoloLens 2 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-160">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="60413-161">이러한 장치를 수동으로 설정, 구성 및 업데이트해야 하기 때문에 관리 오버헤드가 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60413-161">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="60413-162">이 시나리오와 유사한 배포 가이드의 경우 오프라인 보안 배포 [가이드를 검토하세요.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="60413-162">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60413-163">배포 가이드 - 오프라인 보안 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="60413-163">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
