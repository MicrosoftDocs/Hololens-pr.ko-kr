---
title: CSP 및 장치 관리 구성 개요
description: CSP, 정책 및 장치 관리를 구성하는 방법
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
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252779"
---
# <span data-ttu-id="2c458-103">CSP 및 장치 관리 구성 개요</span><span class="sxs-lookup"><span data-stu-id="2c458-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="2c458-104">IT 관리자는 HoloLens 2에서 정책 설정을 정의하고 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="2c458-105">사용할 구성 설정은 배포 시나리오에 따라 다르며, IT 부서에 가장 광범위한 제어 범위를 제공하는 것은 회사 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="2c458-106">Windows 10에서 CSP(구성 서비스 공급자)는 장치에서 구성 설정을 읽거나 설정, 수정 또는 삭제할 수 있는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="2c458-107">이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="2c458-108">일부 구성 서비스 공급자는 WAP 형식을 지원하고, 일부는 SyncML을 지원하며, 일부는 두 가지를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="2c458-109">Windows 10 Holographic 장치 관리 CSP에 대한 자세한 내용은 HoloLens 장치에서 지원되는 [전체 CSP 목록을 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="2c458-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="2c458-110">IT 관리자는 장치에서 정책 CSP를 관리할 수 있습니다. [HoloLens 2에서](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)지원하는 정책 CSP의 전체 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c458-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="2c458-111">구성 방법</span><span class="sxs-lookup"><span data-stu-id="2c458-111">Configuration methods</span></span>

### <span data-ttu-id="2c458-112">MDM으로 구성</span><span class="sxs-lookup"><span data-stu-id="2c458-112">Configure with MDM</span></span>

<span data-ttu-id="2c458-113">CSP 및 정책은 MDM 시스템에 등록된 개인 또는 회사 장치에서 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="2c458-114">장치가 MDM 솔루션에 등록된 후 장치 구성을 사용하여 해당 장치 또는 장치 집합을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="2c458-115">[MDM을 통해 HoloLens](hololens-mdm-configure.md)장치를 관리하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="2c458-116">프로비저닝 패키지로 구성</span><span class="sxs-lookup"><span data-stu-id="2c458-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="2c458-117">HoloLens 2는 사용자 지정 프로비저닝 패키지를 통해 HoloLens 2 장치에 대한 제한된 CSP 구성 집합 설정도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="2c458-118">프로비저닝 패키지는 일반적으로 MDM이 아닌 관리 장치에 활용되고 각 장치에 수동으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="2c458-119">[HoloLens용 사용자 지정 프로비저닝 패키지를 구축하는 데 대한 정보를 읽습니다.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="2c458-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="2c458-120">구성</span><span class="sxs-lookup"><span data-stu-id="2c458-120">Configurations</span></span>

### <span data-ttu-id="2c458-121">일반적인 장치 제한 사항</span><span class="sxs-lookup"><span data-stu-id="2c458-121">Common device restrictions</span></span>

<span data-ttu-id="2c458-122">일부 장치 제한은 간단하며 디바이스에 대한 기능 또는 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="2c458-123">일반적인 장치 제한에 대해 자세히 [알아보고자 합니다.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="2c458-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="2c458-124">키오스크 모드</span><span class="sxs-lookup"><span data-stu-id="2c458-124">Kiosk modes</span></span>

<span data-ttu-id="2c458-125">키오스크 모드를 사용하여 기본적으로 어떤 앱에 액세스할 수 있는 ID를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="2c458-126">키오스크는 단일 앱 또는 여러 앱 UI 경험에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="2c458-127">키오스크 구성은 디바이스를 사용하는 모든 사용자용 단일 앱부터 그룹마다 다른 앱 선택에까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="2c458-128">키오스크 모드는 "허용된 앱"이 다른 앱을 시작하지 못하도록 중지하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="2c458-129">키오스크 모드 및 사용 방법을 읽어 [자세히 알아보십시오.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="2c458-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="2c458-130">설정 페이지 표시 여부</span><span class="sxs-lookup"><span data-stu-id="2c458-130">Settings Page Visibility</span></span>

<span data-ttu-id="2c458-131">설정 앱 정책을 사용하여 기본적으로 설정에 액세스할 수 있는 ID를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="2c458-132">이 정책을 사용하여 선택 페이지만 표시하거나 선택한 모든 페이지를 숨기도록 설정 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="2c458-133">[사용 가능한 페이지를 구성하는 방법을 읽어 읽습니다.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="2c458-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="2c458-134">이 기능은 현재 Windows [Insider 빌드에서만 사용할 수 있습니다.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="2c458-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="2c458-135">이 기능을 사용하려는 장치가 빌드 19041.1349+에 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="2c458-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="2c458-136">WDAC</span></span>

<span data-ttu-id="2c458-137">WDAC 구성을 사용하여 시스템이 키오스크 모드에 있는지 여부와는 무관하게 실행될 수 있는 앱/프로세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2c458-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="2c458-138">WDAC에 대한 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c458-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
