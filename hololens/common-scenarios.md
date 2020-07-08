---
title: 일반적인 인프라 배포 시나리오
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857922"
---
# <span data-ttu-id="f1537-103">일반적인 인프라 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="f1537-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="f1537-104">다음 정보는 엔터프라이즈 내에서 Microsoft HoloLens 2 장치를 배포 하 고 관리할 때 세 가지 일반적인 시나리오에 대 한 높은 수준의 아키텍처 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="f1537-105">시나리오</span><span class="sxs-lookup"><span data-stu-id="f1537-105">Scenarios</span></span>

<span data-ttu-id="f1537-106">아래 다이어그램은 HoloLens 2 배포의 세 가지 일반적인 시나리오를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![등](images/scenarios.jpg)

### <span data-ttu-id="f1537-108">시나리오 A</span><span class="sxs-lookup"><span data-stu-id="f1537-108">Scenario A</span></span>

<span data-ttu-id="f1537-109">HoloLens 2는 주로 회사 네트워크 외부의 환경에서 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="f1537-110">회사 리소스는 액세스할 수 없거나 VPN을 통해 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="f1537-111">이 배포는 회사 내 관리 되는 모바일 장치와 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="f1537-112">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="f1537-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="f1537-113">Wi-fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완벽 하 게 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="f1537-114">MDM 자동 등록을 사용한 Azure AD 참가--MDM (Intune) 관리 됨</span><span class="sxs-lookup"><span data-stu-id="f1537-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="f1537-115">사용자의 AAD (회사 계정)를 사용 하 여 로그인</span><span class="sxs-lookup"><span data-stu-id="f1537-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="f1537-116">장치 당 한 명의 사용자나 여러 사용자 지원</span><span class="sxs-lookup"><span data-stu-id="f1537-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="f1537-117">다양 한 수준의 장치 잠금 구성은 완전히 열린 단일 앱 키오스크에서 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="f1537-118">MDM을 통해 하나 이상의 응용 프로그램이 배포 됨</span><span class="sxs-lookup"><span data-stu-id="f1537-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="f1537-119">일반적인 과제</span><span class="sxs-lookup"><span data-stu-id="f1537-119">Common Challenges</span></span>
   * <span data-ttu-id="f1537-120">시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="f1537-121">시나리오 B</span><span class="sxs-lookup"><span data-stu-id="f1537-121">Scenario B</span></span>

<span data-ttu-id="f1537-122">HoloLens 2는 주로 회사 네트워크에서 내부 기업 리소스에 대 한 액세스를 사용 하도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="f1537-123">인터넷 및 클라우드 서비스가 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="f1537-124">이는 대부분의 Windows 10 Pc에 대 한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="f1537-125">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="f1537-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="f1537-126">Wi-fi 네트워크는 내부 리소스에 대 한 액세스 권한이 있는 내부 회사 네트워크 이며 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="f1537-127">MDM 자동 등록으로 Azure AD 참가</span><span class="sxs-lookup"><span data-stu-id="f1537-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="f1537-128">MDM (Intune) 관리 됨</span><span class="sxs-lookup"><span data-stu-id="f1537-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="f1537-129">사용자의 AAD (회사 계정)를 사용 하 여 로그인</span><span class="sxs-lookup"><span data-stu-id="f1537-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="f1537-130">장치 당 한 명의 사용자나 여러 사용자 지원</span><span class="sxs-lookup"><span data-stu-id="f1537-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="f1537-131">다양 한 수준의 장치 잠금 구성은 완전히 열린 단일 앱 키오스크에서 특정 사용 사례에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="f1537-132">MDM을 통해 하나 이상의 응용 프로그램이 배포 됨</span><span class="sxs-lookup"><span data-stu-id="f1537-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="f1537-133">일반적인 과제</span><span class="sxs-lookup"><span data-stu-id="f1537-133">Common Challenges</span></span>
   * <span data-ttu-id="f1537-134">HoloLens 2는 온-프레미스 광고 참가 또는 SCCM에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="f1537-135">Azure AD에는 MDM만 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="f1537-136">현재 대부분의 회사는이 시나리오에는 SCCM (System Center Configuration Manager)에서 관리 하는 온-프레미스 AD 연결 디바이스와 같이 Windows 10 Pc를 배포 하 고 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 장치를 관리 하기 위해 배포/구성 된 인프라가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="f1537-137">HoloLens 2는 클라우드 첫 장치 이므로 사용자 인증, OS 업데이트, MDM 관리 등을 위해 인터넷 및 클라우드 연결 서비스에 크게 의존 합니다. 회사 네트워크에 연결 하는 경우, HoloLens 2 및이에 실행 되는 응용 프로그램에 대 한 액세스를 사용 하도록 프록시/방화벽 규칙을 조정 해야 할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="f1537-138">일반적으로 회사 Wi-fi 연결에서는 디바이스 또는 사용자를 네트워크에 인증 하는 데 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="f1537-139">MDM을 통해 Windows 10 장치에 인증서를 배포 하는 데 필요한 인프라 또는 설정은 구성을 하는 것이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="f1537-140">시나리오 C</span><span class="sxs-lookup"><span data-stu-id="f1537-140">Scenario C</span></span>

<span data-ttu-id="f1537-141">HoloLens 2는 주로 네트워크 또는 인터넷 액세스 없이 오프 라인으로 사용할 수 있도록 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="f1537-142">이는 매우 안전한 위치나 기밀 위치에 대 한 일반적인 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="f1537-143">기본 일반 구성</span><span class="sxs-lookup"><span data-stu-id="f1537-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="f1537-144">Wi-fi 연결이 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="f1537-145">USB를 통한 이더넷을 필요한 경우 LAN 연결을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="f1537-146">관리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-146">Not Managed.</span></span>
   * <span data-ttu-id="f1537-147">장치에 대 한 로컬 사용자 계정 로그인</span><span class="sxs-lookup"><span data-stu-id="f1537-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="f1537-148">HoloLens 2는 1 개의 로컬 계정만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="f1537-149">다양 한 수준의 디바이스 잠금 구성은 특정 사용 사례를 기반으로 하는 프로비저닝 패키지를 통해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="f1537-150">이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 매우 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="f1537-151">하나 이상의 응용 프로그램이 프로 비전 패키지를 통해 배포 됨</span><span class="sxs-lookup"><span data-stu-id="f1537-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="f1537-152">일반적인 과제</span><span class="sxs-lookup"><span data-stu-id="f1537-152">Common Challenges</span></span>
   * <span data-ttu-id="f1537-153">프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합</span><span class="sxs-lookup"><span data-stu-id="f1537-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="f1537-154">클라우드 서비스를 활용할 수 없으므로 HoloLens 2 기능이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="f1537-155">이러한 장치를 설정 하 고 구성 하 고 수동으로 업데이트 해야 하므로 관리 오버 헤드가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="f1537-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
