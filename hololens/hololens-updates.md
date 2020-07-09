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
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: f8d0c788756b0a24ac8a26b8258b267483f1a890
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857756"
---
# <span data-ttu-id="519c4-103">HoloLens 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="519c4-103">Manage HoloLens Updates</span></span>

<span data-ttu-id="519c4-104">HoloLens는 다른 Windows 10 장치와 같은 방식으로 Windows 업데이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="519c4-105">업데이트가 사용 가능하게 되면 자동으로 다운로드 되고 장치가 충전되고 인터넷에 연결 되면 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="519c4-106">이 문서에서는 엔터프라이즈 또는 기타 관리되는 환경에서 업데이트를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="519c4-107">개별 HoloLens 장치에 대한 업데이트를 관리하는 방법에 대한 자세한 내용은 [HoloLens 업데이트](hololens-update-hololens.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-107">For information about managing updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="519c4-108">자동으로 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="519c4-108">Manage updates automatically</span></span>

<span data-ttu-id="519c4-109">비즈니스용 Windows Holographic은 [비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)를 사용하여 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-109">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="519c4-110">모든 HoloLens 2 장치에서 비즈니스용 Windows Holographic을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-110">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="519c4-111">비즈니스용 Windows Holographic 빌드 10.0.18362.1042 이상을 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-111">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="519c4-112">HoloLens(1세대) 장치를 보유하고 있는 경우에는 [비즈니스용 Windows Holographic로 업그레이드](hololens1-upgrade-enterprise.md) 해야 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-112">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) to manage their updates.</span></span>

<span data-ttu-id="519c4-113">비즈니스용 Windows 업데이트는 HoloLens 장치를 Windows Update 서비스에 직접 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-113">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="519c4-114">비즈니스용 Windows Update를 사용하여 업데이트 프로세스&mdash;의 여러 측면을 제어할 수 있습니다. 즉, 어떤 장치가 어떤 시간에 업데이트 되는지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-114">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="519c4-115">예를 들어 테스트를 위해 장치 하위 집합에 대한 업데이트를 하고 나중에 나머지 장치에 대한 업데이트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-115">For example, you can roll out updates to a subset of devices for testing, then roll out updates to the remaining devices at a later date.</span></span> <span data-ttu-id="519c4-116">또는 다른 업데이트 유형에 대해 서로 다른 업데이트 일정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-116">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="519c4-117">HoloLens 장치의 경우 기능 업데이트(1년에 2번 릴리스) 및 품질 업데이트 (긴급 보안 업데이트를 포함하여 월간 또는 필요에 따라 릴리스)를 자동으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-117">For HoloLens devices, you can automatically manage feature updates (released twice a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="519c4-118">업데이트 유형에 대한 자세한 내용은 [비즈니스용 Windows Updated에서 관리되는 업데이트 유형](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-118">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="519c4-119">Microsoft Intune과 같은 MDM (모바일 장치 관리) 솔루션에서 정책을 사용하여 HoloLens에 대한 Windows 업데이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-119">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

<span data-ttu-id="519c4-120">Intune을 사용하여 비즈니스용 Windows 업데이트를 구성 하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-120">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="519c4-121">Intune에서는 업데이트를 관리하기 위한 두 가지 정책 유형 (*Windows 10 업데이트 링* 및 *Windows 10 기능 업데이트*)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-121">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature updates*.</span></span> <span data-ttu-id="519c4-122">Windows 10 기능 업데이트 정책 유형은 현재 공개 미리 보기에 있습니다. 이는 HoloLens에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-122">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="519c4-123">Windows 10 업데이트 링 정책을 사용하여 HoloLens 2 업데이트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-123">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="519c4-124">HoloLens 2 또는 HoloLens(1세대)에 대한 업데이트 정책 구성</span><span class="sxs-lookup"><span data-stu-id="519c4-124">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="519c4-125">이 섹션에서는 HoloLens 2 또는 HoloLens (1 세대) 업데이트를 관리 하는데 사용할 수 있는 정책에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-125">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="519c4-126">HoloLens 2에서 사용할 수 있는 추가 기능에 대한 자세한 내용은 [HoloLens 2에 대한 업데이트 실시 계획 및 구성](#plan-and-configure-update-rollouts-for-hololens-2)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-126">For information about additional functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="519c4-127">[정책 CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)는 비즈니스용 Windows 업데이트를 구성하는 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-127">The [Policy configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="519c4-128">특정 버전의 HoloLens에서 지원되는 특별 정책에 대한 자세한 내용은 [HoloLens 장치에서 지원 되는 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-128">For details about specific policies that are supported by specific editions of HoloLens, see [Policies supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="519c4-129">업데이트 자동 검사 구성</span><span class="sxs-lookup"><span data-stu-id="519c4-129">Configure automatic checks for updates</span></span>

<span data-ttu-id="519c4-130">**Update/AllowAutoUpdate** 정책을 사용하여 업데이트 검색, 다운로드 및 설치와 같은 자동 업데이트 동작을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-130">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span>

<span data-ttu-id="519c4-131">이 정책은 다음의 값을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-131">This policy supports the following values:</span></span>

- <span data-ttu-id="519c4-132">**0**-장치에 적용 되는 업데이트를 다운로드 할 준비가 되면 사용자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-132">**0** - Notify the user when there is an update that is ready to download that applies to the device.</span></span>
- <span data-ttu-id="519c4-133">**1** - 자동으로 업데이트를 설치한 다음 장치 다시 시작 예약을 사용자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-133">**1** - Automatically install the update, and then notify the user to schedule a device restart.</span></span>  
- <span data-ttu-id="519c4-134">**2** - 업데이트를 자동으로 설치하고 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-134">**2** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="519c4-135">이 값은 권장 값이며 이 정책의 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-135">This is the recommended value, and it is the default value for this policy.</span></span>  

- <span data-ttu-id="519c4-136">**3** - 업데이트를 자동으로 설치하고 특정 시간에 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-136">**3** - Automatically install the update, and then restart at a specified time.</span></span> <span data-ttu-id="519c4-137">설치 일과 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-137">Specify the installation day and time.</span></span> <span data-ttu-id="519c4-138">날짜와 시간을 지정하지 않으면 매일 오전 3시가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-138">If no day and time are specified, the default is daily at 3 A.M.</span></span>  

- <span data-ttu-id="519c4-139">**4** - 업데이트를 자동으로 설치하고 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-139">**4** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="519c4-140">이 옵션을 선택 하면 설정 페이지는 읽기 전용으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-140">This option also sets the Settings page to read-only.</span></span>

- <span data-ttu-id="519c4-141">**5** - 자동 업데이트를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-141">**5** - Turn off automatic updates.</span></span>

<span data-ttu-id="519c4-142">이 정책에서 사용 가능한 설정에 대한 자세한 내용은 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-142">For more details about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="519c4-143">Microsoft Intune에서 **자동 업데이트 동작**을 사용하여 이 정책을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-143">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="519c4-144">자세한 내용은 [Microsoft Intune에서 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/windows-update-for-business-configure)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="519c4-144">For more information, see [Manage software updates in Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="519c4-145">업데이트 일정 구성</span><span class="sxs-lookup"><span data-stu-id="519c4-145">Configure an update schedule</span></span>

<span data-ttu-id="519c4-146">업데이트를 적용하는 방법과 시기를 구성 하려면 다음 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-146">To configure how and when updates are applied, use the following policies:</span></span>

- <span data-ttu-id="519c4-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).</span><span class="sxs-lookup"><span data-stu-id="519c4-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).</span></span>  
   - <span data-ttu-id="519c4-148">값: **0**-**7** (0 = 매일, 1 = 일요일, 7 = 토요일)</span><span class="sxs-lookup"><span data-stu-id="519c4-148">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
   - <span data-ttu-id="519c4-149">기본값: **0** (매일)</span><span class="sxs-lookup"><span data-stu-id="519c4-149">Default value: **0** (every day)</span></span>
- <span data-ttu-id="519c4-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).</span><span class="sxs-lookup"><span data-stu-id="519c4-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).</span></span>
   - <span data-ttu-id="519c4-151">값: 0-23 (0 = 자정, 23 = 오후 11시)</span><span class="sxs-lookup"><span data-stu-id="519c4-151">Values: 0–23 (0 = midnight, 23 = 11 P.M.)</span></span>
   - <span data-ttu-id="519c4-152">기본값: 오후 3시</span><span class="sxs-lookup"><span data-stu-id="519c4-152">Default value: 3 P.M.</span></span>

#### <span data-ttu-id="519c4-153">Windows 10에서 실행되는 장치에는 버전 1607만 해당</span><span class="sxs-lookup"><span data-stu-id="519c4-153">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="519c4-154">다음 업데이트 정책을 사용하여 Windows 업데이트 대신 WSUS(Windows Server Update Service)에서 업데이트를 받을 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-154">You can use the following update policies to configure devices to get updates from the Windows Server Update Service (WSUS), instead of Windows Update:</span></span>

- [<span data-ttu-id="519c4-155">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="519c4-155">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="519c4-156">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="519c4-156">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="519c4-157">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="519c4-157">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="519c4-158">HoloLens 2에 대한 업데이트 실행 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="519c4-158">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="519c4-159">HoloLens 2는 HoloLens (1세대) 보다 더 많은 업데이트 자동화 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-159">HoloLens 2 supports more update automation features than HoloLens (1st gen).</span></span> <span data-ttu-id="519c4-160">Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트를 관리하는 경우에는 더 많이 적용 받습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-160">this is especially true if you use Microsoft Intune to manage Windows Update for Business policy.</span></span> <span data-ttu-id="519c4-161">이러한 기능을 사용하면 조직 전체에서 간편하게 업데이트 시행을 계획하고 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-161">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="519c4-162">업데이트 전략 계획</span><span class="sxs-lookup"><span data-stu-id="519c4-162">Plan the update strategy</span></span>

<span data-ttu-id="519c4-163">비즈니스용 Windows 업데이트는 지연 정책을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-163">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="519c4-164">Microsoft에서 업데이트기 릴리스 된 후 지연 정책을 사용하여 장치에 업데이트를 설치하기 전에 대기 기간을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-164">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="519c4-165">다양한 지연 정책을 통해 장치의 하위 집합 (*업데이트 링*)을 연결하여 조직의 업데이트 시행 전략을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-165">By associating subsets of your devices (referred to as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="519c4-166">1,000개의 장치를 보유하고 있고 5 가지 방법으로 업데이트를 해야하는 조직을 예로 들어보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-166">For example, consider an organization that has 1,000 devices and has to update them in five ways.</span></span> <span data-ttu-id="519c4-167">조직은 다음 표에 표시 된 대로 5개의 업데이트 링을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-167">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="519c4-168">그룹</span><span class="sxs-lookup"><span data-stu-id="519c4-168">Group</span></span> |<span data-ttu-id="519c4-169">장치 수</span><span class="sxs-lookup"><span data-stu-id="519c4-169">Number of devices</span></span> |<span data-ttu-id="519c4-170">지연 (일)</span><span class="sxs-lookup"><span data-stu-id="519c4-170">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="519c4-171">Grp 1 (IT 담당자)</span><span class="sxs-lookup"><span data-stu-id="519c4-171">Grp 1 (IT staff)</span></span> |<span data-ttu-id="519c4-172">5</span><span class="sxs-lookup"><span data-stu-id="519c4-172">5</span></span> |<span data-ttu-id="519c4-173">0</span><span class="sxs-lookup"><span data-stu-id="519c4-173">0</span></span> |
|<span data-ttu-id="519c4-174">Grp 2 (이른 도입자)</span><span class="sxs-lookup"><span data-stu-id="519c4-174">Grp 2 (early adopters)</span></span> |<span data-ttu-id="519c4-175">50</span><span class="sxs-lookup"><span data-stu-id="519c4-175">50</span></span> |<span data-ttu-id="519c4-176">60</span><span class="sxs-lookup"><span data-stu-id="519c4-176">60</span></span> |
|<span data-ttu-id="519c4-177">Grp 3 (정 1)</span><span class="sxs-lookup"><span data-stu-id="519c4-177">Grp 3 (main 1)</span></span> |<span data-ttu-id="519c4-178">250</span><span class="sxs-lookup"><span data-stu-id="519c4-178">250</span></span> |<span data-ttu-id="519c4-179">120</span><span class="sxs-lookup"><span data-stu-id="519c4-179">120</span></span> |
|<span data-ttu-id="519c4-180">Grp 4 (정 2)</span><span class="sxs-lookup"><span data-stu-id="519c4-180">Grp 4 (main 2)</span></span> |<span data-ttu-id="519c4-181">300</span><span class="sxs-lookup"><span data-stu-id="519c4-181">300</span></span> |<span data-ttu-id="519c4-182">150</span><span class="sxs-lookup"><span data-stu-id="519c4-182">150</span></span> |
|<span data-ttu-id="519c4-183">Grp 5 (정 3)</span><span class="sxs-lookup"><span data-stu-id="519c4-183">Grp 5 (main 3)</span></span> |<span data-ttu-id="519c4-184">395</span><span class="sxs-lookup"><span data-stu-id="519c4-184">395</span></span> |<span data-ttu-id="519c4-185">180</span><span class="sxs-lookup"><span data-stu-id="519c4-185">180</span></span> |

<span data-ttu-id="519c4-186">시간에 따라 전체 조직에 시행되는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-186">Here's how the rollout progresses over time to the entire organization.</span></span>

![업데이트를 배포하기 위한 타임라인](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="519c4-188">업데이트 지연 정책 구성</span><span class="sxs-lookup"><span data-stu-id="519c4-188">Configure an update deferral policy</span></span>

<span data-ttu-id="519c4-189">지연 정책은 업데이트를 사용 할 수 있게 된 날부터 해당 업데이트가 장치에 제공 되는 날 사이의 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-189">A deferral policy specifies the number of days between the date that an update becomes available and the date that the update is offered to a device.</span></span>

<span data-ttu-id="519c4-190">기능 업데이트 및 품질 업데이트에 대해 서로 다른 지연을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-190">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="519c4-191">다음 표에서는 각 유형에 사용할 특정 정책과 각 유형에 대한 최대 지연 기간을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-191">The following table lists the specific policies to use for each type, as well as the maximum deferral for each.</span></span>

|<span data-ttu-id="519c4-192">범주</span><span class="sxs-lookup"><span data-stu-id="519c4-192">Category</span></span> |<span data-ttu-id="519c4-193">정책</span><span class="sxs-lookup"><span data-stu-id="519c4-193">Policy</span></span> |<span data-ttu-id="519c4-194">최대 지연</span><span class="sxs-lookup"><span data-stu-id="519c4-194">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="519c4-195">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="519c4-195">Feature updates</span></span> |<span data-ttu-id="519c4-196">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="519c4-196">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="519c4-197">365일</span><span class="sxs-lookup"><span data-stu-id="519c4-197">365 days</span></span> |
|<span data-ttu-id="519c4-198">품질 업데이트</span><span class="sxs-lookup"><span data-stu-id="519c4-198">Quality updates</span></span> |<span data-ttu-id="519c4-199">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="519c4-199">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="519c4-200">30일</span><span class="sxs-lookup"><span data-stu-id="519c4-200">30 days</span></span> |

####  <span data-ttu-id="519c4-201">예: Intune을 사용하여 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="519c4-201">Examples: Using Intune to manage updates</span></span>

**<span data-ttu-id="519c4-202">예1: 업데이트 링 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="519c4-202">Example 1: Create and assign an update ring</span></span>**

<span data-ttu-id="519c4-203">이 예제에 대한 자세한 내용은 [업데이트 링 만들기 및 할당](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-203">For a more detailed version of this example, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

1. <span data-ttu-id="519c4-204">[Microsoft 끝점 관리자 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인하여 Intune 프로필로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-204">Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), and navigate to your Intune profiles.</span></span>
1. <span data-ttu-id="519c4-205">**소프트웨어 업데이트** > **Windows 10 업데이트 링** > **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-205">Select **Software Updates** > **Windows 10 update rings** > **Create**.</span></span>
1. <span data-ttu-id="519c4-206">**기초**에서 이름과 설명을 지정(선택 사항)하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-206">Under **Basics**, specify a name and a description (optional), and then select **Next**.</span></span>
1. <span data-ttu-id="519c4-207">**업데이트 링 설정**의 **서비스 채널**에서 **반기 채널**을 선택한 다음 **기능 업데이트 지연 기간**을 **120**으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-207">Under **Update ring settings**, for **Servicing channel**, select **Semi-Annual Channel**, and then change **Feature update deferral period** to **120**.</span></span> <span data-ttu-id="519c4-208">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-208">Then, select **Next**.</span></span>
1. <span data-ttu-id="519c4-209">**과제**에서 **+ 그룹을 선택하여 포함**을 선택하고 업데이트 링을 하나 이상의 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-209">Under **Assignments**, select **+ Select groups to include**, and then assign the update ring to one or more groups.</span></span> <span data-ttu-id="519c4-210">**+ 그룹을 선택하여 제외**를 사용하여 과제를 세부조정 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-210">Use **+ Select groups to exclude** to fine-tune the assignments.</span></span> <span data-ttu-id="519c4-211">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-211">Then, select **Next**.</span></span>
1. <span data-ttu-id="519c4-212">**검토 + 만들기**에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-212">Under **Review + create**, review the settings.</span></span> <span data-ttu-id="519c4-213">업데이트 링 구성을 저장할 준비가 되면 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-213">When you're ready to save the update ring configuration, select **Create**.</span></span>

<span data-ttu-id="519c4-214">이제 업데이트 링 목록에 새 Windows 10 업데이트 링이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-214">The list of update rings now includes the new Windows 10 update ring.</span></span>

**<span data-ttu-id="519c4-215">예2: 업데이트 링 일시 중지</span><span class="sxs-lookup"><span data-stu-id="519c4-215">Example 2: Pause an update ring</span></span>**

<span data-ttu-id="519c4-216">기능 또는 품질 업데이트를 배포할 때 문제가 발생하는 경우 업데이트를 35일(지정 된 날짜부터 시작)간 일시 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-216">If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="519c4-217">이 일시 중지를 수행하면 문제가 해결 되거나 완화 될 때까지 다른 장치에서 업데이트를 설치 하지 못 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-217">This pause prevents other devices from installing the update until you resolve or mitigate the issue.</span></span> <span data-ttu-id="519c4-218">기능 업데이트를 일시 중지해도 장치 품질 업데이트는 계속 제공되기 때문에 계속해서 보안을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-218">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="519c4-219">지정 된 시간이 경과되면 일시 중지가 자동으로 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-219">After the specified time has passed, the pause automatically expires.</span></span> <span data-ttu-id="519c4-220">해당 시점에 업데이트 프로세스가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-220">At that point, the update process resumes.</span></span>

<span data-ttu-id="519c4-221">Intune에서 업데이트 링을 일시 중지 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-221">To pause an update ring in Intune, follow these steps:</span></span>

1. <span data-ttu-id="519c4-222">업데이트 링 개요 페이지에서 **일시 중지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-222">On the overview page for the update ring, select **Pause**.</span></span>
1. <span data-ttu-id="519c4-223">업데이트 유형(**기능** 또는 **품질**)을 선택하여 일시 중지 한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-223">Select the type of update (**Feature** or **Quality**) to pause, and then select **OK**.</span></span>

<span data-ttu-id="519c4-224">업데이트 유형 하나를 일시 중지 하면 해당 링의 개요 창에 해당 업데이트 유형을 다시 시작 하기까지 남은 일수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-224">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span>

<span data-ttu-id="519c4-225">업데이트 링이 일시 중지 된 상태에서 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-225">While the update ring is paused, you can select either of the following options:</span></span>

- <span data-ttu-id="519c4-226">해당 업데이트 유형에 대해 35일간의 일시 중지 기간을 연장 하려면 **확장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-226">To extend the pause period for an update type for 35 days, select **Extend**.</span></span>
- <span data-ttu-id="519c4-227">해당 링에 대한 업데이트를 활성 작업으로 복원하려면 **다시 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-227">To restore updates for that ring to active operation, select **Resume**.</span></span> <span data-ttu-id="519c4-228">필요한 경우 업데이트 링을 다시 일시 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-228">You can pause the update ring again if it is necessary.</span></span>

> [!NOTE]  
> <span data-ttu-id="519c4-229">HoloLens 2 장치에서는 업데이트 링에 대한 **제거** 작업이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-229">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="519c4-230">업데이트 수동으로 확인</span><span class="sxs-lookup"><span data-stu-id="519c4-230">Manually check for updates</span></span>

<span data-ttu-id="519c4-231">HoloLens가 정기적으로 시스템 업데이트를 확인하기 때문에 사용자가 하지 않아도 되지만 사용자가 수동으로 확인하고자 할 때도 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-231">Although HoloLens periodically checks for system updates so that you don't have to, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="519c4-232">수동으로 업데이트를 확인하려면 **설정** > **업데이트 및 보안** > **으로 이동하여 업데이트를 확인하세요**.</span><span class="sxs-lookup"><span data-stu-id="519c4-232">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="519c4-233">설정 앱에서 장치가 최신 상태로 나타나면 현재 사용 가능한 모든 업데이트를 사용 중인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-233">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="519c4-234">수동으로 업데이트 되돌리기</span><span class="sxs-lookup"><span data-stu-id="519c4-234">Manually revert an update</span></span>

<span data-ttu-id="519c4-235">경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아갈 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-235">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="519c4-236">HoloLens 2 또는 HoloLens (1세대)를 사용 여부에 따라 해당 과정이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-236">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="519c4-237">이전 버전으로 돌아가기 (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="519c4-237">Go back to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="519c4-238">고급 복구 도우미를 사용하여 HoloLens 2를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens 2로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-238">You can roll back updates and return to a previous version of HoloLens 2 by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="519c4-239">이전 버전으로 되돌리면 개인 파일과 설정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-239">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="519c4-240">HoloLens 2의 이전 버전으로 돌아가려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-240">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="519c4-241">컴퓨터에 연결 된 휴대폰 또는 Windows 장치가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-241">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="519c4-242">컴퓨터의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-242">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="519c4-243">[최근 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-243">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="519c4-244">다운로드가 끝나면 **파일 탐색기** > **다운로드**를 열고 방금 다운로드 받은 압축된(zip) 폴더를 오른쪽 클릭한 후 **모두 압축 풀기** > **압축풀기**를 선택하여 파일을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-244">When you have finished these downloads, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="519c4-245">USB-A나 USB-C 케이블을 사용하여 컴퓨터에 HoloLens 장치를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-245">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="519c4-246">그동안 다른 케이블을 사용하여 HoloLens를 연결 했더라도 이 케이블이 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-246">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="519c4-247">고급 복구 도우미는 HoloLens 장치를 자동으로 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-247">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="519c4-248">**Microsoft HoloLens** 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-248">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="519c4-249">다음 화면에서 **수동 패키지 선택**을 선택한 다음 이전에 확장 한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-249">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="519c4-250">설치 파일을 선택 합니다(.ffu 확장명을 가진 파일).</span><span class="sxs-lookup"><span data-stu-id="519c4-250">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="519c4-251">**소프트웨어 설치**를 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-251">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="519c4-252">이전 버전으로 돌아가기 (HoloLens(1세대))</span><span class="sxs-lookup"><span data-stu-id="519c4-252">Go back to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="519c4-253">고급 복구 도우미를 사용하여 HoloLens(1세대)를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-253">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="519c4-254">이전 버전으로 되돌리면 개인 파일과 설정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-254">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="519c4-255">HoloLens(1세대)의 이전 버전으로 돌아가려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-255">To go back to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="519c4-256">컴퓨터에 연결 된 휴대폰 또는 Windows 장치가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-256">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="519c4-257">컴퓨터에서 [(WDRT) Windows 장치 복구 도구](https://support.microsoft.com/help/12379)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-257">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="519c4-258">[HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-258">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="519c4-259">다운로드가 끝나면 **파일 탐색기** > **다운로드**를 열고 방금 다운로드 받은 압축된(zip) 폴더를 오른쪽 클릭한 후 **모두 압축 풀기** > **압축풀기**를 선택하여 파일을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-259">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="519c4-260">Hololens 장치와 함께 제공 된 마이크로 USB 케이블을 사용하여 HoloLens 장치를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-260">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="519c4-261">그동안 다른 케이블을 사용하여 HoloLens를 연결 했더라도 이 케이블이 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-261">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="519c4-262">WDRT는 HoloLens 장치를 자동으로 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-262">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="519c4-263">**Microsoft HoloLens** 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-263">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="519c4-264">다음 화면에서 **수동 패키지 선택**을 선택한 다음 이전에 확장 한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-264">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="519c4-265">설치 파일을 선택 합니다(.ffu 확장명을 가진 파일).</span><span class="sxs-lookup"><span data-stu-id="519c4-265">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="519c4-266">**소프트웨어 설치**를 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-266">Select **Install software**, and then follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="519c4-267">WDRT에서 HoloLens 장치가 자동으로 감지되지 않으면 컴퓨터를 다시 시작 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="519c4-267">If the WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="519c4-268">그래도 문제가 해결 되지 않으면 **장치가 감지 되지 않음**을 선택하고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="519c4-268">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="519c4-269">관련 문서</span><span class="sxs-lookup"><span data-stu-id="519c4-269">Related articles</span></span>

- [<span data-ttu-id="519c4-270">비즈니스용 Windows 업데이트를 사용하여 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="519c4-270">Deploy updates using Windows Update for Business</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="519c4-271">Windows 10 업데이트용 서비스 채널에 장치 할당</span><span class="sxs-lookup"><span data-stu-id="519c4-271">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="519c4-272">Intune에서 Windows 10 소프트웨어 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="519c4-272">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
