---
title: Csp 및 장치 관리 개요 구성
description: Csp, 정책 및 장치 관리를 구성 하는 방법
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016800"
---
# <span data-ttu-id="c9bb2-103">Csp 및 장치 관리 개요 구성</span><span class="sxs-lookup"><span data-stu-id="c9bb2-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="c9bb2-104">IT 관리자는 HoloLens 2에서 정책 설정을 정의 하 고 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="c9bb2-105">사용할 구성 설정은 배포 시나리오에 따라 다르며, IT 부서에 가장 광범위한 제어 범위를 제공하는 것은 회사 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="c9bb2-106">Windows 10의 경우 CSP (구성 서비스 공급자)는 디바이스에서 구성 설정을 읽고, 설정, 수정 또는 삭제 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="c9bb2-107">이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="c9bb2-108">일부 구성 서비스 공급자는 WAP 형식, 일부 지원, 그리고 두 가지를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span> 

<span data-ttu-id="c9bb2-109">Windows 10 홀로그램 장치 관리 Csp에 대 한 자세한 내용은 [HoloLens 장치에서 지원 되는 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)의 전체 목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span> <span data-ttu-id="c9bb2-110">IT 관리자는 디바이스에서 정책 CSP를 관리할 수도 있으며, [HoloLens 2에서 지원 되는 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)csp의 전체 목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="c9bb2-111">구성 방법</span><span class="sxs-lookup"><span data-stu-id="c9bb2-111">Configuration methods</span></span>

### <span data-ttu-id="c9bb2-112">MDM으로 구성</span><span class="sxs-lookup"><span data-stu-id="c9bb2-112">Configure with MDM</span></span>
<span data-ttu-id="c9bb2-113">사용자는 MDM 시스템에 등록 된 개인 또는 회사 장치에서 Csp 및 정책을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="c9bb2-114">장치가 MDM 솔루션에 등록 되 면 장치 구성을 사용 하 여 해당 장치 또는 장치 집합을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="c9bb2-115">[MDM을 통해 HoloLens 장치를 관리](hololens-mdm-configure.md)하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="c9bb2-116">배포 패키지를 사용 하 여 구성</span><span class="sxs-lookup"><span data-stu-id="c9bb2-116">Configure with Provisioning Packages</span></span>
<span data-ttu-id="c9bb2-117">HoloLens 2는 또한 사용자 지정 프로비저닝 패키지를 통해 HoloLens 2 장치에 대해 제한 된 CSP 구성 집합을 설정 하는 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="c9bb2-118">일반적으로 프로 비전 패키지는 MDM이 아닌 관리 장치에 활용 되며 각 장치에 수동으로 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="c9bb2-119">[HoloLens에 대 한 사용자 지정 프로비저닝 패키지](https://docs.microsoft.com/hololens/hololens-provisioning)빌드에 대 한 정보를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> 

## <span data-ttu-id="c9bb2-120">구성</span><span class="sxs-lookup"><span data-stu-id="c9bb2-120">Configurations</span></span> 

### <span data-ttu-id="c9bb2-121">일반적인 장치 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c9bb2-121">Common device restrictions</span></span>
<span data-ttu-id="c9bb2-122">일부 장치 제한은 간단 하며 장치에 대 한 기능 또는 연결을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="c9bb2-123">[일반적인 장치 제한 사항](hololens-common-device-restrictions.md) 에 대 한 자세한 내용은 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="c9bb2-124">키오스크 모드</span><span class="sxs-lookup"><span data-stu-id="c9bb2-124">Kiosk modes</span></span>
<span data-ttu-id="c9bb2-125">키오스크 모드를 사용 하 여 기본적으로 어떤 앱에 액세스할 수 있는 id를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="c9bb2-126">키오스크는 단일 앱 또는 여러 앱 UI 환경에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="c9bb2-127">키오스크 구성은 장치를 사용 하는 모든 사용자가 다른 그룹에 대 한 앱을 다양 하 게 선택 하는 단일 앱의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="c9bb2-128">이는 다른 앱을 실행 하는 것이 아니라 "허용 된 앱"이 중지 되지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-128">This does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="c9bb2-129">자세한 내용은 [키오스크 모드 및 사용 방법에 대 한 읽기 시작](hololens-kiosk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-129">To learn more [start reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="c9bb2-130">설정 페이지 표시 여부</span><span class="sxs-lookup"><span data-stu-id="c9bb2-130">Settings Page Visibility</span></span>
<span data-ttu-id="c9bb2-131">설정 앱 정책을 사용 하 여 기본적으로 설정에 액세스할 수 있는 id를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="c9bb2-132">이 정책에서는 설정 앱을 구성 하 여 선택 페이지만 표시 하거나 선택한 모든 페이지를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-132">With this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="c9bb2-133">[사용 가능한 페이지를 구성 하는 방법에 대해 자세히](settings-uri-list.md)알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="c9bb2-134">이 기능은 현재 [Windows 참가자 빌드](hololens-insider.md)에만 avalible.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-134">This feature is currently only avalible in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="c9bb2-135">이를 사용 하려는 장치가 빌드 19041.1349 +에 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-135">Please ensure devices you intend to use this for are on build 19041.1349+.</span></span>

### <span data-ttu-id="c9bb2-136">설정만</span><span class="sxs-lookup"><span data-stu-id="c9bb2-136">WDAC</span></span>
<span data-ttu-id="c9bb2-137">WDAC 구성을 사용 하 여 시스템이 키오스크 모드 인지 여부에 관계 없이 실행할 수 있거나 허용 되지 않는 앱/프로세스를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="c9bb2-138">WDAC에 대 한 개요를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
