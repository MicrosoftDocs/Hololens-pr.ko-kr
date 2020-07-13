---
title: HoloLens 업데이트 관리
description: 관리자는 모바일 장치 관리를 사용하여 HoloLens 장치에 대한 업데이트를 관리할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 07/09/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 384d33e72effd298e1874e5723e9c418061c3287
ms.sourcegitcommit: 0d4e67d8e21d34885e0eaee08646e28426c4f641
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "10861911"
---
# <span data-ttu-id="ca78d-103">HoloLens 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="ca78d-103">Manage HoloLens updates</span></span>

<span data-ttu-id="ca78d-104">HoloLens는 다른 Windows 10 장치와 같은 방식으로 Windows 업데이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="ca78d-105">업데이트가 사용 가능하게 되면 자동으로 다운로드 되고 장치가 충전되고 인터넷에 연결 되면 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="ca78d-106">이 문서에서는 엔터프라이즈 또는 기타 관리되는 환경에서 업데이트를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="ca78d-107">개별 HoloLens 장치에 대한 업데이트를 관리하는 방법에 대한 자세한 내용은 [HoloLens 업데이트](hololens-update-hololens.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-107">For information about how to manage updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="ca78d-108">자동으로 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="ca78d-108">Manage updates automatically</span></span>

### <span data-ttu-id="ca78d-109">비즈니스용 Windows 업데이트를 사용하여 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="ca78d-109">Managing updates by using Windows Update for Business</span></span>

<span data-ttu-id="ca78d-110">비즈니스용 Windows Holographic은 [비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)를 사용하여 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-110">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="ca78d-111">모든 HoloLens 2 장치에서 비즈니스용 Windows Holographic을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-111">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="ca78d-112">비즈니스용 Windows Holographic 빌드 10.0.18362.1042 이상을 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-112">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="ca78d-113">HoloLens(1세대) 장치를 보유하고 있는 경우에는 [비즈니스용 Windows Holographic로 업그레이드](hololens1-upgrade-enterprise.md) 해야 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-113">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) in order to manage their updates.</span></span>

<span data-ttu-id="ca78d-114">비즈니스용 Windows 업데이트는 HoloLens 장치를 Windows Update 서비스에 직접 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-114">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="ca78d-115">비즈니스용 Windows Update를 사용하여 업데이트 프로세스&mdash;의 여러 측면을 제어할 수 있습니다. 즉, 어떤 장치가 어떤 시간에 업데이트 되는지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-115">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="ca78d-116">예를 들어 테스트를 위해 장치 하위 집합에 대한 업데이트를 하고 나중에 나머지 장치에 대한 업데이트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-116">For example, you can roll out updates to a subset of devices for testing, then later roll out updates to the remaining devices.</span></span> <span data-ttu-id="ca78d-117">또는 다른 업데이트 유형에 대해 서로 다른 업데이트 일정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-117">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="ca78d-118">HoloLens 장치의 경우 기능 업데이트(1년에 2번 릴리스) 및 품질 업데이트 (긴급 보안 업데이트를 포함하여 월간 또는 필요에 따라 릴리스)를 자동으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-118">For HoloLens devices, you can automatically manage feature updates (released two times a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="ca78d-119">업데이트 유형에 대한 자세한 내용은 [비즈니스용 Windows Updated에서 관리되는 업데이트 유형](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-119">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="ca78d-120">Microsoft Intune과 같은 MDM (모바일 장치 관리) 솔루션에서 정책을 사용하여 HoloLens에 대한 Windows 업데이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-120">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

### <span data-ttu-id="ca78d-121">Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="ca78d-121">Managing Windows Update for Business by using Microsoft Intune</span></span>

<span data-ttu-id="ca78d-122">Intune을 사용하여 비즈니스용 Windows 업데이트를 구성 하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-122">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="ca78d-123">HoloLens에서 지원하는 특정 Intune 기능에 대한 자세한 내용은 [HoloLens에서 지원하는 Intune 업데이트 관리 기능](#intune-update-management-functions-that-hololens-supports)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-123">For more information about the specific Intune functionality that HoloLens supports, see [Intune update management functions that HoloLens supports](#intune-update-management-functions-that-hololens-supports).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="ca78d-124">Intune에서는 업데이트를 관리하기 위한 두 가지 정책 유형 (*Windows 10 업데이트 링* 및 *Windows 10 기능 업데이트*)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-124">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature update*.</span></span> <span data-ttu-id="ca78d-125">Windows 10 기능 업데이트 정책 유형은 현재 공개 미리 보기에 있습니다. 이는 HoloLens에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-125">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="ca78d-126">Windows 10 업데이트 링 정책을 사용하여 HoloLens 2 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-126">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="ca78d-127">HoloLens 2 또는 HoloLens(1세대)에 대한 업데이트 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ca78d-127">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="ca78d-128">이 섹션에서는 HoloLens 2 또는 HoloLens (1 세대) 업데이트를 관리 하는데 사용할 수 있는 정책에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-128">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="ca78d-129">HoloLens 2에서 사용할 수 있는 기능에 대한 자세한 내용은 [HoloLens 2에 대한 업데이트 실시 계획 및 구성](#plan-and-configure-update-rollouts-for-hololens-2)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-129">For more information about the functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="ca78d-130">[정책 CSP - 업데이트](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)는 비즈니스용 Windows 업데이트를 구성하는 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-130">[Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="ca78d-131">특정 버전의 HoloLens에서 지원하는 특정 CSP(구성 서비스 공급자) 목록은 [HoloLens 장치에서 지원하는 정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-131">For a list of specific policy configuration service providers (CSPs) that are supported by specific editions of HoloLens, see [Policy CSPs supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="ca78d-132">업데이트 자동 검사 구성</span><span class="sxs-lookup"><span data-stu-id="ca78d-132">Configure automatic checks for updates</span></span>

<span data-ttu-id="ca78d-133">**Update/AllowAutoUpdate** 정책을 사용하여 업데이트 검색, 다운로드 및 설치와 같은 자동 업데이트 동작을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-133">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span> <span data-ttu-id="ca78d-134">이 정책에서 사용 가능한 설정에 대한 자세한 내용은 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-134">For more information about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="ca78d-135">Microsoft Intune에서 **자동 업데이트 동작**을 사용하여 이 정책을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-135">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="ca78d-136">자세한 내용은 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/windows-update-for-business-configure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-136">For more information, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="ca78d-137">업데이트 일정 구성</span><span class="sxs-lookup"><span data-stu-id="ca78d-137">Configure an update schedule</span></span>

<span data-ttu-id="ca78d-138">업데이트를 적용하는 방법과 시기를 구성 하려면 다음 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-138">To configure how and when updates are applied, use the following policies:</span></span>

- [<span data-ttu-id="ca78d-139">Update/ScheduledInstallDay</span><span class="sxs-lookup"><span data-stu-id="ca78d-139">Update/ScheduledInstallDay</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - <span data-ttu-id="ca78d-140">값: **0**-**7** (0 = 매일, 1 = 일요일, 7 = 토요일)</span><span class="sxs-lookup"><span data-stu-id="ca78d-140">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
  - <span data-ttu-id="ca78d-141">기본값: **0** (매일)</span><span class="sxs-lookup"><span data-stu-id="ca78d-141">Default value: **0** (every day)</span></span>
- [<span data-ttu-id="ca78d-142">Update/ScheduledInstallTime</span><span class="sxs-lookup"><span data-stu-id="ca78d-142">Update/ScheduledInstallTime</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - <span data-ttu-id="ca78d-143">값: 0~23 (0 = 자정, 23 = 오후 11시)</span><span class="sxs-lookup"><span data-stu-id="ca78d-143">Values: 0–23 (0 = midnight, 23 = 11 PM)</span></span>
  - <span data-ttu-id="ca78d-144">기본값: 오후 3시</span><span class="sxs-lookup"><span data-stu-id="ca78d-144">Default value: 3 PM</span></span>

#### <span data-ttu-id="ca78d-145">Windows 10에서 실행되는 장치에는 버전 1607만 해당</span><span class="sxs-lookup"><span data-stu-id="ca78d-145">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="ca78d-146">다음 업데이트 정책을 사용하여 Windows 업데이트 대신 WSUS(Windows Server Update Service)에서 업데이트를 받을 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-146">You can use the following update policies to configure devices to get updates from Windows Server Update Service (WSUS), instead of from Windows Update:</span></span>

- [<span data-ttu-id="ca78d-147">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="ca78d-147">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="ca78d-148">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="ca78d-148">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="ca78d-149">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="ca78d-149">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="ca78d-150">HoloLens 2에 대한 업데이트 실행 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="ca78d-150">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="ca78d-151">HoloLens 2는 HoloLens(1세대)보다 더 많은 업데이트 자동화 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-151">HoloLens 2 supports more update automation features than HoloLens (1st gen) does.</span></span> <span data-ttu-id="ca78d-152">Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트를 관리하는 경우에는 더 많이 적용 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-152">This is especially true if you use Microsoft Intune to manage Windows Update for Business policies.</span></span> <span data-ttu-id="ca78d-153">이러한 기능을 사용하면 조직 전체에서 간편하게 업데이트 시행을 계획하고 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-153">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="ca78d-154">업데이트 전략 계획</span><span class="sxs-lookup"><span data-stu-id="ca78d-154">Plan the update strategy</span></span>

<span data-ttu-id="ca78d-155">비즈니스용 Windows 업데이트는 지연 정책을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-155">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="ca78d-156">Microsoft에서 업데이트기 릴리스 된 후 지연 정책을 사용하여 장치에 업데이트를 설치하기 전에 대기 기간을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-156">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="ca78d-157">다양한 지연 정책을 통해 장치의 하위 집합(*업데이트 링*이라고도 함)을 연결하여 조직의 업데이트 시행 전략을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-157">By associating subsets of your devices (also known as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="ca78d-158">1,000개의 장치를 보유하고 있고 5가지 웨이브로 업데이트를 해야 하는 조직을 예로 들어보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-158">For example, consider an organization that has 1,000 devices, and has to update the devices in five waves.</span></span> <span data-ttu-id="ca78d-159">조직은 다음 표에 표시 된 대로 5개의 업데이트 링을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-159">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="ca78d-160">그룹</span><span class="sxs-lookup"><span data-stu-id="ca78d-160">Group</span></span> |<span data-ttu-id="ca78d-161">장치 수</span><span class="sxs-lookup"><span data-stu-id="ca78d-161">Number of devices</span></span> |<span data-ttu-id="ca78d-162">지연 (일)</span><span class="sxs-lookup"><span data-stu-id="ca78d-162">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="ca78d-163">Grp 1 (IT 담당자)</span><span class="sxs-lookup"><span data-stu-id="ca78d-163">Grp 1 (IT staff)</span></span> |<span data-ttu-id="ca78d-164">5</span><span class="sxs-lookup"><span data-stu-id="ca78d-164">5</span></span> |<span data-ttu-id="ca78d-165">0</span><span class="sxs-lookup"><span data-stu-id="ca78d-165">0</span></span> |
|<span data-ttu-id="ca78d-166">Grp 2 (이른 도입자)</span><span class="sxs-lookup"><span data-stu-id="ca78d-166">Grp 2 (early adopters)</span></span> |<span data-ttu-id="ca78d-167">50</span><span class="sxs-lookup"><span data-stu-id="ca78d-167">50</span></span> |<span data-ttu-id="ca78d-168">60</span><span class="sxs-lookup"><span data-stu-id="ca78d-168">60</span></span> |
|<span data-ttu-id="ca78d-169">Grp 3 (정 1)</span><span class="sxs-lookup"><span data-stu-id="ca78d-169">Grp 3 (main 1)</span></span> |<span data-ttu-id="ca78d-170">250</span><span class="sxs-lookup"><span data-stu-id="ca78d-170">250</span></span> |<span data-ttu-id="ca78d-171">120</span><span class="sxs-lookup"><span data-stu-id="ca78d-171">120</span></span> |
|<span data-ttu-id="ca78d-172">Grp 4 (정 2)</span><span class="sxs-lookup"><span data-stu-id="ca78d-172">Grp 4 (main 2)</span></span> |<span data-ttu-id="ca78d-173">300</span><span class="sxs-lookup"><span data-stu-id="ca78d-173">300</span></span> |<span data-ttu-id="ca78d-174">150</span><span class="sxs-lookup"><span data-stu-id="ca78d-174">150</span></span> |
|<span data-ttu-id="ca78d-175">Grp 5 (정 3)</span><span class="sxs-lookup"><span data-stu-id="ca78d-175">Grp 5 (main 3)</span></span> |<span data-ttu-id="ca78d-176">395</span><span class="sxs-lookup"><span data-stu-id="ca78d-176">395</span></span> |<span data-ttu-id="ca78d-177">180</span><span class="sxs-lookup"><span data-stu-id="ca78d-177">180</span></span> |

<span data-ttu-id="ca78d-178">시간에 따라 전체 조직에 시행되는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-178">Here's how the rollout progresses over time to the whole organization.</span></span>

![업데이트를 배포하기 위한 타임라인](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="ca78d-180">업데이트 지연 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ca78d-180">Configure an update deferral policy</span></span>

<span data-ttu-id="ca78d-181">지연 정책은 업데이트를 사용 할 수 있게 된 날부터 해당 업데이트가 장치에 제공 되는 날 사이의 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-181">A deferral policy specifies the number of days between the date on which an update becomes available and the date on which the update is offered to a device.</span></span>

<span data-ttu-id="ca78d-182">기능 업데이트 및 품질 업데이트에 대해 서로 다른 지연을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-182">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="ca78d-183">다음 표에서는 각 유형에 사용할 특정 정책과 각 유형에 대한 최대 지연 기간을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-183">The following table lists the specific policies to use for each type, and the maximum deferral for each.</span></span>

|<span data-ttu-id="ca78d-184">범주</span><span class="sxs-lookup"><span data-stu-id="ca78d-184">Category</span></span> |<span data-ttu-id="ca78d-185">정책</span><span class="sxs-lookup"><span data-stu-id="ca78d-185">Policy</span></span> |<span data-ttu-id="ca78d-186">최대 지연</span><span class="sxs-lookup"><span data-stu-id="ca78d-186">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="ca78d-187">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="ca78d-187">Feature updates</span></span> |<span data-ttu-id="ca78d-188">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="ca78d-188">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="ca78d-189">365일</span><span class="sxs-lookup"><span data-stu-id="ca78d-189">365 days</span></span> |
|<span data-ttu-id="ca78d-190">품질 업데이트</span><span class="sxs-lookup"><span data-stu-id="ca78d-190">Quality updates</span></span> |<span data-ttu-id="ca78d-191">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="ca78d-191">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="ca78d-192">30일</span><span class="sxs-lookup"><span data-stu-id="ca78d-192">30 days</span></span> |

#### <span data-ttu-id="ca78d-193">HoloLens에서 지원하는 Intune 업데이트 관리 기능</span><span class="sxs-lookup"><span data-stu-id="ca78d-193">Intune update management functions that HoloLens supports</span></span>

<span data-ttu-id="ca78d-194">다음 Intune 업데이트 관리 기능을 사용하여 HoloLens에 대한 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-194">You can use the following Intune update management functions to manage updates for HoloLens.</span></span>

- <span data-ttu-id="ca78d-195">**만들기** 및 **할당**: 이 기능은 업데이트 링 목록에 Windows 10 업데이트 링을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-195">**Create** and **Assign**: These functions add a Windows 10 update ring to the list of update rings.</span></span> <span data-ttu-id="ca78d-196">자세한 내용은 [업데이트 링 만들기 및 할당](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-196">For more information, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

- <span data-ttu-id="ca78d-197">**일시 중지**: 기능 또는 품질 업데이트를 배포할 때 문제가 발생하는 경우 업데이트를 35일(지정 된 날짜부터 시작)간 일시 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-197">**Pause**: If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="ca78d-198">이 일시 중지를 수행하면 문제가 해결되거나 완화될 때까지 다른 장치에서 업데이트를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-198">This pause prevents other devices from installing the update until you resolve or mitigate the problem.</span></span> <span data-ttu-id="ca78d-199">기능 업데이트를 일시 중지해도 장치 품질 업데이트는 계속 제공되기 때문에 계속해서 보안을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-199">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="ca78d-200">업데이트 유형 하나를 일시 중지 하면 해당 링의 개요 창에 해당 업데이트 유형을 다시 시작 하기까지 남은 일수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-200">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span> <span data-ttu-id="ca78d-201">지정된 시간이 경과되면 일시 중지가 자동으로 만료되고 업데이트 프로세스가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-201">After the specified time has passed, the pause automatically expires, and the update process resumes.</span></span>

  <span data-ttu-id="ca78d-202">업데이트 링이 일시 중지 된 상태에서 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-202">While the update ring is paused, you can select either of the following options:</span></span>

  - <span data-ttu-id="ca78d-203">**연장**: 업데이트 유형에 대해 35일간의 일시 중지 기간을 연장합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-203">**Extend**: Extend the pause period for an update type for 35 days.</span></span>
  - <span data-ttu-id="ca78d-204">**다시 시작**: 해당 링에 대한 업데이트를 활성 작업으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-204">**Resume**: Restore updates for that ring to active operation.</span></span> <span data-ttu-id="ca78d-205">필요한 경우 업데이트 링을 다시 일시 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-205">You can pause the update ring again, if it is necessary.</span></span>

  > [!NOTE]  
  > <span data-ttu-id="ca78d-206">HoloLens 2 장치에서는 업데이트 링에 대한 **제거** 작업이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-206">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="ca78d-207">업데이트 수동으로 확인</span><span class="sxs-lookup"><span data-stu-id="ca78d-207">Manually check for updates</span></span>

<span data-ttu-id="ca78d-208">HoloLens가 정기적으로 시스템 업데이트를 확인하기 때문에 사용자가 수동으로 확인하고자 할 때도 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-208">Although HoloLens periodically checks for system updates, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="ca78d-209">수동으로 업데이트를 확인하려면 **설정** > **업데이트 및 보안** > **으로 이동하여 업데이트를 확인하세요**.</span><span class="sxs-lookup"><span data-stu-id="ca78d-209">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="ca78d-210">설정 앱에서 장치가 최신 상태로 나타나면 현재 사용 가능한 모든 업데이트를 사용 중인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-210">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="ca78d-211">수동으로 업데이트 롤백</span><span class="sxs-lookup"><span data-stu-id="ca78d-211">Manually roll back an update</span></span>

<span data-ttu-id="ca78d-212">경우에 따라 이전 버전의 HoloLens 소프트웨어로 되돌릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-212">In some cases, you might want to revert to a previous version of the HoloLens software.</span></span> <span data-ttu-id="ca78d-213">HoloLens 2 또는 HoloLens (1세대)를 사용 여부에 따라 해당 과정이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-213">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="ca78d-214">이전 버전으로 되돌리기(HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="ca78d-214">Revert to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="ca78d-215">[고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)를 사용하여 HoloLens 2를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens 2로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-215">You can roll back updates and return to a previous version of HoloLens 2 by using the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="ca78d-216">이전 버전으로 되돌리면 개인 파일과 설정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-216">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="ca78d-217">HoloLens 2의 이전 버전으로 되돌리려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-217">To revert to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="ca78d-218">컴퓨터에 연결 된 휴대폰 또는 Windows 장치가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-218">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="ca78d-219">컴퓨터의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-219">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="ca78d-220">[최근 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-220">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="ca78d-221">다운로드가 끝나면 **파일 탐색기** > **다운로드**를 열고 방금 다운로드받은 압축된(.zip) 폴더를 오른쪽 클릭한 후 **모두 압축 풀기** > **압축 풀기**를 선택하여 파일을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-221">After these downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="ca78d-222">USB-A나 USB-C 케이블을 사용하여 컴퓨터에 HoloLens 장치를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-222">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="ca78d-223">그동안 다른 케이블을 사용하여 HoloLens를 연결 했더라도 이 케이블이 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-223">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="ca78d-224">고급 복구 도우미는 HoloLens 장치를 자동으로 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-224">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="ca78d-225">**Microsoft HoloLens** 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-225">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="ca78d-226">다음 화면에서 **수동 패키지 선택**을 선택한 다음 이전에 확장 한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-226">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="ca78d-227">설치(.ffu) 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-227">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="ca78d-228">**소프트웨어 설치**를 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-228">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="ca78d-229">이전 버전으로 되돌리기(HoloLens(1세대))</span><span class="sxs-lookup"><span data-stu-id="ca78d-229">Revert to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="ca78d-230">[WDRT(Windows 장치 복구 도구)](https://support.microsoft.com/help/12379)를 사용하여 HoloLens(1세대)를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-230">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="ca78d-231">이전 버전의 HoloLens로 되돌리면 개인 파일과 설정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-231">Reverting to an earlier HoloLens version deletes your personal files and settings.</span></span>

<span data-ttu-id="ca78d-232">HoloLens(1세대)의 이전 버전으로 되돌리려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-232">To revert to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="ca78d-233">컴퓨터에 연결된 휴대폰 또는 Windows 장치가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-233">Make sure that you don't have any phones or Windows devices plugged into your computer.</span></span>
1. <span data-ttu-id="ca78d-234">컴퓨터에서 [(WDRT) Windows 장치 복구 도구](https://support.microsoft.com/help/12379)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-234">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="ca78d-235">[HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-235">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="ca78d-236">다운로드가 끝나면 **파일 탐색기** > **다운로드**를 열고 방금 다운로드받은 압축된(.zip) 폴더를 오른쪽 클릭한 후 **모두 압축 풀기** > **압축 풀기**를 선택하여 파일을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-236">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="ca78d-237">Hololens 장치와 함께 제공 된 마이크로 USB 케이블을 사용하여 HoloLens 장치를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-237">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="ca78d-238">그동안 다른 케이블을 사용하여 HoloLens를 연결 했더라도 이 케이블이 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-238">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="ca78d-239">WDRT는 HoloLens 장치를 자동으로 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-239">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="ca78d-240">**Microsoft HoloLens** 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-240">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="ca78d-241">다음 화면에서 **수동 패키지 선택**을 선택한 다음 이전에 확장 한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-241">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="ca78d-242">설치(.ffu) 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-242">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="ca78d-243">**소프트웨어 설치**를 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-243">Select **Install software**, and then follow the instructions.</span></span>

**<span data-ttu-id="ca78d-244">WDRT에서 장치를 감지하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="ca78d-244">If WDRT doesn't detect your device</span></span>**

<span data-ttu-id="ca78d-245">WDRT에서 HoloLens 장치를 자동으로 감지하지 않으면 컴퓨터를 다시 시작해보세요.</span><span class="sxs-lookup"><span data-stu-id="ca78d-245">If WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="ca78d-246">그래도 문제가 해결 되지 않으면 **장치가 감지 되지 않음**을 선택하고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ca78d-246">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="ca78d-247">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ca78d-247">Related articles</span></span>

- [<span data-ttu-id="ca78d-248">HoloLens 2 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="ca78d-248">HoloLens 2 release notes</span></span>](https://docs.microsoft.com/hololens/hololens-release-notes)
- [<span data-ttu-id="ca78d-249">비즈니스용 Windows 업데이트란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ca78d-249">What is Windows Update for Business?</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="ca78d-250">Windows 10 업데이트용 서비스 채널에 장치 할당</span><span class="sxs-lookup"><span data-stu-id="ca78d-250">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="ca78d-251">Intune에서 Windows 10 소프트웨어 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="ca78d-251">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
