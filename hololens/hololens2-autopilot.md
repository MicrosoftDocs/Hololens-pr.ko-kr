---
title: HoloLens 2용 Windows Autopilot
description: HoloLens 2 장치에서 Autopilot을 설정 및 구성하고 문제를 해결하는 방법을 알아봅니다.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: cc73f5cbb438119f4c626ae76db9c91373e19aff
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635367"
---
# <a name="windows-autopilot-for-hololens-2"></a><span data-ttu-id="180d2-104">HoloLens 2용 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="180d2-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="180d2-105">Windows Holographic 버전 2004부터 HoloLens 2는 Microsoft Intune(타사 MDM은 지원되지 않음)에서 Windows Autopilot [자체 배포 모드](/mem/autopilot/self-deploying)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](/mem/autopilot/self-deploying) with Microsoft Intune (3rd party MDMs are not supported).</span></span> <span data-ttu-id="180d2-106">관리자는 Microsoft Endpoint Manager에서 OOBE(첫 실행 경험)를 구성하여 최종 사용자가 상호 작용을 거의 또는 전혀 하지 않고도 비즈니스용 장치를 준비할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="180d2-107">이를 통해 인벤토리 관리 오버헤드, 실습 장치 준비 비용 및 설치하는 동안 직원의 지원 요청을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="180d2-108">자세한 내용은 [Windows Autopilot](/mem/autopilot/windows-autopilot) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-108">Learn more in the [Windows Autopilot](/mem/autopilot/windows-autopilot) documentation.</span></span>

<span data-ttu-id="180d2-109">Surface 장치와 마찬가지로 고객은 Microsoft [클라우드 솔루션 공급자](https://partner.microsoft.com/cloud-solution-provider)(재판매인 또는 배포자)와 협력하여 파트너 센터를 통해 Autopilot 서비스에 등록된 장치를 구입하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="180d2-110">Microsoft의 채널 파트너를 활용하면 가장 효과적인 엔드투엔드 경로가 보장되지만, 장치 등록을 위한 다른 방법은 [장치 추가](/mem/autopilot/add-devices) 설명서에 간략하게 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-110">Other methods for device registration are outlined in the [add device](/mem/autopilot/add-devices) documentation, though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span>

> [!NOTE]
> <span data-ttu-id="180d2-111">2020년 11월 20일 현재 Microsoft Endpoint Manager의 HoloLens용 Autopilot 구성은 **공개 미리 보기** 로 전환되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="180d2-112">고객이 더 이상 비공개 미리 보기에 등록할 필요가 없으며 모든 테넌트는 MEM 관리 센터에서 Autopilot을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="180d2-113">사용자가 Autopilot 자체 배포 프로세스를 시작하면 Autopilot에서 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="180d2-114">장치를 Azure AD(Azure Active Directory)에 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="180d2-115">HoloLens용 Autopilot은 Active Directory 조인 또는 하이브리드 Azure AD 조인을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>

1. <span data-ttu-id="180d2-116">Azure AD를 사용하여 Microsoft Endpoint Manager(또는 다른 MDM 서비스)에 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="180d2-117">장치 대상 정책, 인증서, 네트워킹 프로필 및 응용 프로그램을 다운로드하여 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="180d2-118">장치를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-118">Provision the device.</span></span>

1. <span data-ttu-id="180d2-119">사용자에게 로그인 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-119">Present the sign-in screen to the user.</span></span>

## <a name="configuring-autopilot-for-hololens-2"></a><span data-ttu-id="180d2-120">HoloLens 2용 Autopilot 구성</span><span class="sxs-lookup"><span data-stu-id="180d2-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="180d2-121">환경을 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="180d2-122">HoloLens 2용 Windows Autopilot의 요구 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="180d2-123">자동 MDM 등록을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-123">Enable Automatic MDM Enrollment</span></span>](#2-enable-automatic-mdm-enrollment)

1. [<span data-ttu-id="180d2-124">Windows Autopilot에서 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-124">Register devices in Windows Autopilot.</span></span>](#3-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="180d2-125">장치 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-125">Create a device group.</span></span>](#4-create-a-device-group)

1. [<span data-ttu-id="180d2-126">배포 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-126">Create a deployment profile.</span></span>](#5-create-a-deployment-profile)

1. [<span data-ttu-id="180d2-127">ESP(등록 상태 페이지) 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-127">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#6-verify-the-esp-configuration)

1. [<span data-ttu-id="180d2-128">HoloLens 장치의 프로필 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-128">Verify the profile status of the HoloLens devices.</span></span>](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a><span data-ttu-id="180d2-129">1. HoloLens 2용 Windows Autopilot 요구 사항 검토</span><span class="sxs-lookup"><span data-stu-id="180d2-129">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a><span data-ttu-id="180d2-130">다음 Windows Autopilot 요구 사항 문서를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-130">Review the following sections of the Windows Autopilot requirements article:</span></span>

- [<span data-ttu-id="180d2-131">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="180d2-131">Network requirements</span></span>](/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="180d2-132">라이선싱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="180d2-132">Licensing requirements</span></span>](/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="180d2-133">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="180d2-133">Configuration requirements</span></span>](/mem/autopilot/configuration-requirements)

<span data-ttu-id="180d2-134">**Windows Autopilot 자체 배포 모드 문서의 "[요구 사항](/windows/deployment/windows-autopilot/self-deploying#requirements)" 섹션을 검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="180d2-134">**Review the "[Requirements](/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.**</span></span> <span data-ttu-id="180d2-135">사용자 환경은 표준 Windows Autopilot 요구 사항뿐만 아니라 이러한 요구 사항도 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-135">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="180d2-136">문서의 "단계별 안내" 및 "유효성 검사" 섹션은 검토할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-136">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="180d2-137">이 문서의 뒷부분에 나오는 절차는 HoloLens와 관련된 해당 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-137">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span>

<span data-ttu-id="180d2-138">장치를 등록하고 프로필을 구성하는 방법에 대한 자세한 내용은 이 문서의 [2. Windows Autopilot에서 장치 등록](#3-register-devices-in-windows-autopilot)과 [4. 배포 프로필 만들기](#5-create-a-deployment-profile)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-138">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#3-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#5-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="180d2-139">Autopilot 자체 배포 모드 프로필을 구성하고 관리하려면 [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-139">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

#### <a name="review-hololens-os-requirements"></a><span data-ttu-id="180d2-140">다음과 같은 HoloLens OS 요구 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-140">Review HoloLens OS requirements:</span></span>

- <span data-ttu-id="180d2-141">장치가 [Windows Holographic, 버전 2004](hololens-release-notes.md#windows-holographic-version-2004)(빌드 19041.1103) 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-141">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="180d2-142">장치에서 빌드 버전을 확인하거나 최신 OS로 다시 플래시하려면 [ARC(고급 복구 도우미)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 및 [장치 리플래시 지침](/hololens/hololens-recovery#clean-reflash-the-device)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-142">To confirm the build version on your device or re-flash to the latest OS, use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) and our [device re-flash instructions](/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="180d2-143">2020년 9월 말까지 제공되는 장치에는 Windows Holographic 버전 1903이 사전 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="180d2-144">Autopilot 지원 장치가 배송되는지 확인하려면 재판매인에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="180d2-145">Windows Holographic, 버전 2004는 이더넷 연결을 통해서만 Autopilot을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="180d2-146">HoloLens를 **켜기 전** 에 "USB-C to Ethernet" 어댑터를 사용하여 HoloLens가 이더넷에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="180d2-147">장치 부팅 시 사용자 상호 작용이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="180d2-148">다수의 HoloLens 장치에 대한 Autopilot 롤아웃을 계획하고 있는 경우 어댑터 인프라에 대한 계획을 세우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="180d2-149">USB 허브는 HoloLens에서 지원되지 않는 타사 드라이버를 추가로 설치해야 하는 경우가 많기 때문에 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span>

- <span data-ttu-id="180d2-150">여전히 이더넷 어댑터를 사용할 수 있지만 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)(빌드 19041.1128) 이상은 Wi-Fi를 통해 Autopilot을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="180d2-151">Wi-Fi를 통해 연결된 장치의 경우 사용자는 다음 작업만 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="180d2-152">벌새 장면을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="180d2-153">언어 및 로캘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-153">Choose the language and locale</span></span>
     - <span data-ttu-id="180d2-154">눈 보정을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-154">Run eye-calibration</span></span>
     - <span data-ttu-id="180d2-155">네트워크 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-155">Establish network connection</span></span>

- <span data-ttu-id="180d2-156">Windows Holographic, 버전 20H2는 [Tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)을 지원하므로 테넌트에 장치를 잠그고 우발적이거나 의도적인 재설정 또는 삭제 시 장치가 해당 테넌트에 바인딩된 상태를 유지하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="180d2-157">장치가 아직 Azure AD의 멤버가 아니고 Intune(또는 다른 MDM 시스템)에 등록되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="180d2-158">Autopilot 자체 배포 프로세스는 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="180d2-159">모든 장치 관련 정보를 정리하려면 Azure AD 및 Intune 포털 모두에서 **장치** 페이지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="180d2-160">현재 HoloLens에서는 "모든 대상 장치를 Autopilot으로 변환" 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="2-enable-automatic-mdm-enrollment"></a><span data-ttu-id="180d2-161">2. 자동 MDM 등록을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="180d2-161">2. Enable Automatic MDM Enrollment:</span></span>

<span data-ttu-id="180d2-162">Autopilot이 성공하려면 Azure Portal에서 자동 MDM 등록을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-162">In order for Autopilot to succeed you'll need to enable Automatic MDM Enrollment in your Azure portal.</span></span> <span data-ttu-id="180d2-163">이렇게 하면 사용자 없이 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-163">This will enable the device to enroll without a user.</span></span>

<span data-ttu-id="180d2-164">[Azure Portal](https://portal.azure.com/#home)에 로그인하고, **Azure Active Directory** -> **Mobility(MDM 및 MAM)**  -> **Microsoft Intune** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-164">In the [Azure portal](https://portal.azure.com/#home) select **Azure Active Directory** -> **Mobility (MDM and MAM)** -> **Microsoft Intune**.</span></span> <span data-ttu-id="180d2-165">그런 다음 **MDM 사용자 범위** 를 구성하고 **모두** 를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-165">Then configure the **MDM user scope**, you will need to select **All**.</span></span>

<span data-ttu-id="180d2-166">간단한 다음 [MDM 자동 등록 사용 설정 가이드](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 또는 [자동 등록 빠른 시작 가이드](/mem/intune/enrollment/quickstart-setup-auto-enrollment)를 검토하여 설정에 대한 자세한 내용을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-166">Please review the following short [guide on enabling MDM Automatic Enrollment](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) or the [Auto Enrollment Quick start guide](/mem/intune/enrollment/quickstart-setup-auto-enrollment) for even more information getting set up.</span></span>

### <a name="3-register-devices-in-windows-autopilot"></a><span data-ttu-id="180d2-167">3. Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="180d2-167">3. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="180d2-168">장치를 처음 설치하기 전에 Windows Autopilot에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-168">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="180d2-169">장치 등록에 대한 MEM 설명서는 [Autopilot에 장치 추가](/mem/autopilot/add-devices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-169">For MEM documentation on device registration please see [Adding devices to Autopilot](/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="180d2-170">HoloLens 장치를 등록하는 기본 방법은 다음 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-170">There are three primary ways to register HoloLens devices:</span></span>

 - <span data-ttu-id="180d2-171">**재판매인은 사용자가 주문을 할 때 파트너 센터에 장치를 등록할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="180d2-171">**Reseller can register devices in the Partner Center when you place an order.**</span></span>

   > [!NOTE]  
   > <span data-ttu-id="180d2-172">Autopilot 서비스에 장치를 추가하는 데 권장되는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-172">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="180d2-173">[자세히 알아보기](/mem/autopilot/partner-registration).</span><span class="sxs-lookup"><span data-stu-id="180d2-173">[Learn more](/mem/autopilot/partner-registration).</span></span>  

 - <span data-ttu-id="180d2-174">**Microsoft에 직접 [지원 요청을 제출](hololens2-autopilot-registration-support.md)할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="180d2-174">**You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.**</span></span>
 - <span data-ttu-id="180d2-175">**하드웨어 해시(하드웨어 ID라고도 함)를 검색하고 MEM 관리 센터에서 수동으로 장치를 등록합니다.**</span><span class="sxs-lookup"><span data-stu-id="180d2-175">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span>

#### <a name="obtain-hardware-hash"></a><span data-ttu-id="180d2-176">하드웨어 해시 가져오기</span><span class="sxs-lookup"><span data-stu-id="180d2-176">Obtain hardware hash</span></span>
<span data-ttu-id="180d2-177">하드웨어 해시를 가져오는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-177">There are two ways to retrieve the hardware hash.</span></span>
1. <span data-ttu-id="180d2-178">Microsoft에 직접 [지원 요청을 제출](hololens2-autopilot-registration-support.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-178">You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.</span></span>
2. <span data-ttu-id="180d2-179">장치에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-179">You can retrieve it from the device.</span></span> <span data-ttu-id="180d2-180">장치는 OOBE 프로세스 중에 또는 나중에 장치 소유자가 진단 로그 수집 프로세스를 시작(다음 절차에 설명됨)할 때 하드웨어 해시를 CSV 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-180">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="180d2-181">일반적으로 장치 소유자는 장치에 처음으로 로그인한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-181">Typically, the device owner is the first user to sign in to the device.</span></span>
     > [!WARNING]
     > <span data-ttu-id="180d2-182">20H2 이전 빌드에서 OOBE를 완료했고 원격 분석이 필수로 설정된 경우 이 방법을 통해 Autopilot에 대한 하드웨어 해시를 수집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-182">In builds prior to 20H2, if you have gone through OOBE and the telemetry was set to Required, you cannot collect the hardware hash for Autopilot through this method.</span></span> <span data-ttu-id="180d2-183">이 방법을 통해 하드웨어 해시를 수집하려면 설정 앱을 통해 원격 분석 옵션을 전체로 설정하고 개인 정보 -> 진단을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-183">In          order to collect your hardware hash via this method set your telemetry option to Full via the Settings App and select Privacy -> Diagnostics.</span></span>

    1. <span data-ttu-id="180d2-184">HoloLens 2 장치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-184">Start the HoloLens 2 device.</span></span>

    1. <span data-ttu-id="180d2-185">장치에서 **전원** 및 **Volume Down** 단추를 동시에 누른 다음 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-185">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="180d2-186">장치는 진단 로그와 하드웨어 해시를 수집하여 .zip 파일 세트에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-186">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>

   1. <span data-ttu-id="180d2-187">전체 세부 정보 및 이를 수행하는 방법에 대한 지침 비디오를 보려면 [오프라인 진단](hololens-diagnostic-logs.md#offline-diagnostics)에 대해 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-187">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

    1. <span data-ttu-id="180d2-188">USB-C 케이블을 사용하여 장치를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-188">Use a USB-C cable to connect the device to a computer.</span></span>

    1. <span data-ttu-id="180d2-189">컴퓨터에서 파일 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-189">On the computer, open File Explorer.</span></span> <span data-ttu-id="180d2-190">**이 PC\\\<*HoloLens device name*>\\Internal Storage\\문서** 를 열고 AutopilotDiagnostics.zip 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-190">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

       > [!NOTE]  
       > <span data-ttu-id="180d2-191">.zip 파일을 즉시 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-191">The .zip file may not immediately be available.</span></span> <span data-ttu-id="180d2-192">파일이 아직 준비되지 않은 경우 문서 폴더에 HoloLensDiagnostics.temp 파일이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-192">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="180d2-193">파일 목록을 업데이트하려면 창을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-193">To update the list of files, refresh the window.</span></span>
    
    1. <span data-ttu-id="180d2-194">AutopilotDiagnostics.zip 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-194">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

    1. <span data-ttu-id="180d2-195">추출된 파일에서 파일 이름 접두사가 "DeviceHash"인 CSV 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-195">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="180d2-196">해당 파일을 나중에 액세스할 수 있는 컴퓨터의 드라이브에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-196">Copy that file to a drive on the computer where you can access it later.</span></span>  

       > [!IMPORTANT]  
       > <span data-ttu-id="180d2-197">CSV 파일의 데이터는 다음 헤더와 선 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-197">The data in the CSV file should use the following header and line format:</span></span>
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a><span data-ttu-id="180d2-198">MEM을 통해 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-198">Register device through MEM</span></span>

1. <span data-ttu-id="180d2-199">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **장치** > **Windows** > **Windows enrollment** 를 선택한 다음, **Windows Autopilot Deployment Program** 아래에서 **장치** > **가져오기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-199">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="180d2-200">**Windows Autopilot 장치 추가** 에서 DeviceHash CSV 파일을 선택하고, **열기** 를 선택한 다음, **가져오기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-200">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-201">![가져오기 명령을 사용하여 하드웨어 해시를 가져옵니다.](./images/hololens-ap-hash-import.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-201">![Use the Import command to import the hardware hash.](./images/hololens-ap-hash-import.png)</span></span>

1. <span data-ttu-id="180d2-202">가져오기가 완료되면 **장치** > **Windows** > **Windows enrollment** > **장치** > **동기화** 를 선택합니다. 동기화하고 있는 장치 수에 따라 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-202">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="180d2-203">등록된 장치를 보려면 **새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-203">To see the registered device, select **Refresh**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-204">![동기화 및 새로 고침 명령을 사용하여 장치 목록을 표시합니다.](./images/hololens-ap-devices-sync.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-204">![Use the Sync and Refresh commands to view the device list.](./images/hololens-ap-devices-sync.png)</span></span>  

### <a name="4-create-a-device-group"></a><span data-ttu-id="180d2-205">4. 장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="180d2-205">4. Create a device group</span></span>

1. <span data-ttu-id="180d2-206">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **그룹** > **새 그룹** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-206">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="180d2-207">**그룹 유형** 에서 **보안** 을 선택하고 그룹 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-207">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="180d2-208">**Membership type** 에서 **할당됨** 또는 **Dynamic Device** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-208">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="180d2-209">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-209">Do one of the following:</span></span>  

   - <span data-ttu-id="180d2-210">이전 단계에서 **멤버 자격 유형** 으로 **할당됨** 을 선택한 경우 **멤버** 를 선택한 후 그룹에 Autopilot 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-210">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="180d2-211">아직 등록되지 않은 Autopilot 장치는 장치 일련 번호를 장치 이름으로 사용하여 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-211">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="180d2-212">이전 단계에서 **Membership type** 으로 **Dynamic Devices** 를 선택한 경우 **Dynamic device members** 를 선택하고 **고급 규칙** 에 다음과 같은 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-212">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="180d2-213">Autopilot 디바이스를 모두 포함한 그룹을 만들려는 경우 `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-213">If you want to create a group that includes all of your Autopilot devices, type: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`</span></span>
     - <span data-ttu-id="180d2-214">Intune의 그룹 태그 필드는 Azure AD 장치의 **OrderID** 특성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-214">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="180d2-215">특정 그룹 태그(Azure AD 장치 OrderID)가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`을(를) 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-215">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span></span>
     - <span data-ttu-id="180d2-216">특정 구매 주문 ID가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`을(를) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-216">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span></span>

     > [!NOTE]  
     > <span data-ttu-id="180d2-217">이러한 규칙은 Autopilot 장치에 고유한 특성을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-217">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="180d2-218">**저장** 을 선택한 후 **Create** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-218">Select **Save**, and then select **Create**.</span></span>

### <a name="5-create-a-deployment-profile"></a><span data-ttu-id="180d2-219">5. 배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="180d2-219">5. Create a deployment profile</span></span>

1. <span data-ttu-id="180d2-220">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **장치** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-220">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   <span data-ttu-id="180d2-221">![프로필 만들기 드롭다운에는 HoloLens 항목이 포함됩니다.](./images/hololens-ap-enrollment-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-221">![Create profile dropdown includes a HoloLens item.](./images/hololens-ap-enrollment-profiles.png)</span></span>

1. <span data-ttu-id="180d2-222">프로필 이름과 설명을 입력하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-222">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="180d2-223">**HoloLens** 를 포함하는 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-223">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="180d2-224">이 옵션이 표시되지 않는 경우 [피드백](hololens2-autopilot.md#feedback-and-support-for-autopilot) 옵션 중 하나를 사용하여 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-224">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-225">![프로필 이름 및 설명 추가](./images/hololens-ap-profile-name.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-225">![Add a profile name and description](./images/hololens-ap-profile-name.png)</span></span>

1. <span data-ttu-id="180d2-226">**OOBE(첫 실행 경험)** 페이지에서 대부분의 설정은 이 평가를 위해 OOBE를 간소화하도록 미리 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-226">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="180d2-227">필요에 따라 선택하여 구성할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-227">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="180d2-228">**언어(지역)** : OOBE의 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-228">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="180d2-229">[HoloLens 2에 대해 지원되는 언어](hololens2-language-support.md) 목록에서 언어를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-229">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="180d2-230">**자동으로 키보드 구성**: 선택한 언어와 일치하는 키보드가 있는지 확인하려면 **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-230">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="180d2-231">**장치 이름 템플릿 적용**: OOBE 중에 장치 이름을 자동으로 설정하려면 **예** 를 선택한 다음 **이름 입력** 에 템플릿 구 및 자리 표시자를 입력합니다. 예를 들어 접두사와 `%RAND:4%`&mdash;네 자리 난수에 대한 자리 표시자를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-231">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="180d2-232">장치 이름 템플릿을 사용하는 경우 OOBE 프로세스는 장치 이름을 적용한 후 장치를 Azure AD에 조인하기 전에 장치를 한 번 더 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-232">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="180d2-233">다시 시작하면 새 이름이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-233">This restart enables the new name to take effect.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-234">![OOBE 설정 구성](./images/hololens-ap-profile-oobe.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-234">![Configure OOBE settings](./images/hololens-ap-profile-oobe.png)</span></span>

1. <span data-ttu-id="180d2-235">설정을 구성한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-235">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="180d2-236">**범위 태그** 페이지에서 필요에 따라 이 프로필에 적용하려는 범위 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-236">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="180d2-237">범위 태그에 대한 자세한 내용은 [분산형 IT에 역할 기반 액세스 제어 및 범위 태그 사용](/mem/intune/fundamentals/scope-tags.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-237">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="180d2-238">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-238">When finished, select **Next**.</span></span>
1. <span data-ttu-id="180d2-239">**할당** 페이지에서 **할당 대상** 으로 **선택한 그룹** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-239">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="180d2-240">**선택한 그룹** 에서 **+ 포함할 그룹 선택** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-240">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="180d2-241">**포함할 그룹 선택** 목록에서 Autopilot HoloLens 장치에 대해 생성한 장치 그룹을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-241">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="180d2-242">모든 그룹을 제외하려는 경우 **제외할 그룹 선택** 을 선택하고 제외하려는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-242">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-243">![장치 그룹을 프로필에 할당합니다.](./images/hololens-ap-profile-assign-devicegroup.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-243">![Assigning a device group to the profile.](./images/hololens-ap-profile-assign-devicegroup.png)</span></span>

1. <span data-ttu-id="180d2-244">**검토 + 만들기** 페이지에서 설정을 검토한 다음 **Create** 를 선택하여 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-244">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-245">![검토 + 만들기](./images/hololens-ap-profile-summ.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-245">![Review + create](./images/hololens-ap-profile-summ.png)</span></span>

### <a name="6-verify-the-esp-configuration"></a><span data-ttu-id="180d2-246">6. ESP 구성 확인</span><span class="sxs-lookup"><span data-stu-id="180d2-246">6. Verify the ESP configuration</span></span>

<span data-ttu-id="180d2-247">ESP(등록 상태 페이지)는 MDM 관리 사용자가 처음으로 장치에 로그인할 때 실행되는 전체 장치 구성 프로세스의 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-247">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="180d2-248">ESP 구성이 다음과 유사한지 확인하고 할당이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-248">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="180d2-249">![ESP 구성](./images/hololens-ap-profile-settings.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-249">![ESP configuration](./images/hololens-ap-profile-settings.png)</span></span>

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a><span data-ttu-id="180d2-250">7. HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="180d2-250">7. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="180d2-251">Microsoft Endpoint Manager 관리 센터에서 **장치** > **Windows** > **Windows enrollment** > **장치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-251">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="180d2-252">HoloLens 장치가 나열되어 있고 프로필 상태가 **할당됨** 인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-252">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="180d2-253">장치에 프로필을 할당하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-253">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-254">![장치 및 프로필 할당.](./images/hololens-ap-devices-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-254">![Device and profile assignments.](./images/hololens-ap-devices-assignments.png)</span></span>

## <a name="windows-autopilot-for-hololens-2-user-experience"></a><span data-ttu-id="180d2-255">HoloLens 2용 Windows Autopilot 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="180d2-255">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="180d2-256">위의 지침이 완료되면 HoloLens 2 사용자는 다음과 같은 환경을 통해 HoloLens 장치를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-256">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="180d2-257">Autopilot 환경에는 인터넷 액세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-257">Autopilot experience requires internet access.</span></span> <span data-ttu-id="180d2-258">다음 옵션 중 하나를 사용하여 인터넷 액세스를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-258">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="180d2-259">OOBE의 Wi-Fi 네트워크에 장치를 연결한 다음 자동으로 Autopilot 환경을 감지하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-259">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="180d2-260">이는 Autopilot 환경이 자체적으로 완료될 때까지 OOBE와 상호 작용해야 할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-260">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="180d2-261">기본적으로 HoloLens 2는 인터넷 감지 후 Autopilot을 감지하기 위해 10초 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-261">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="180d2-262">10초 이내에 Autopilot 프로필이 검색되지 않으면 OOBE에 EULA가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-262">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="180d2-263">이 문제가 발생하는 경우 장치를 다시 부팅하여 다시 Autopilot을 검색해 보세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-263">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="180d2-264">또한 장치에 TenantLockdown 정책이 설정된 경우에만 OOBE가 Autopilot을 무기한 대기할 수 있으므로 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-264">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>

    - <span data-ttu-id="180d2-265">유선 인터넷 연결에 "USB-C to Ethernet" 어댑터를 사용하여 장치를 이더넷에 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-265">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

    - <span data-ttu-id="180d2-266">무선 인터넷 연결에 "USB-C to Wifi" 어댑터를 사용하여 장치를 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-266">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="180d2-267">Autopilot을 위해 OOBE에서 Wi-Fi 네트워크를 사용하려는 장치는 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-267">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="180d2-268">이더넷 어댑터를 사용하는 장치의 경우 OOBE(첫 실행 경험)가 시작되기 전에 장치를 네트워크에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-268">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="180d2-269">장치가 첫 OOBE 화면에서 Autopilot 장치로 프로비전할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-269">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="180d2-270">장치를 네트워크에 연결할 수 없거나 장치를 Autopilot 장치로 프로비전하지 않도록 선택하면 나중에 Autopilot 프로비전으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-270">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="180d2-271">대신 장치를 Autopilot 장치로 프로비전하려면 이 절차를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-271">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="180d2-272">장치가 자동으로 OOBE를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-272">The device should automatically start OOBE.</span></span> <span data-ttu-id="180d2-273">OOBE와 상호 작용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-273">Do not interact with OOBE.</span></span> <span data-ttu-id="180d2-274">그 대신 잠시 기다려 주세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-274">Instead sit, back and relax!</span></span> <span data-ttu-id="180d2-275">HoloLens 2에서 네트워크 연결을 검색하여 OOBE를 자동으로 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-275">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="180d2-276">OOBE가 진행되는 동안 장치가 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-276">The device may restart during OOBE.</span></span> <span data-ttu-id="180d2-277">OOBE 화면은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-277">The OOBE screens should resemble the following.</span></span>

   <span data-ttu-id="180d2-278">![OOBE 1단계](./images/autopilot-welcome.jpg)
   ![OOBE 2단계](./images/autopilot-step-complete.jpg)
   ![OOBE 3단계](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="180d2-278">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="180d2-279">OOBE가 끝나면 사용자 이름과 암호를 사용하여 장치에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-279">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a><span data-ttu-id="180d2-280">Tenantlockdown CSP 및 Autopilot</span><span class="sxs-lookup"><span data-stu-id="180d2-280">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="180d2-281">HoloLens 2 장치는 Windows Holographic, 버전 20H2의 TenantLockdown CSP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-281">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="180d2-282">이 CSP는 장치 초기화나 리플래시를 통해 장치를 조직의 테넌트에 잠가 장치를 해당 테넌트에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-282">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span>

<span data-ttu-id="180d2-283">[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용하여 HoloLens 2를 MDM 등록에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-283">[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="180d2-284">TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false(초기 설정) 값으로 설정되면 리플래시, OS 업데이트 등을 수행해도 해당 값이 장치에 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-284">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span>

<span data-ttu-id="180d2-285">HoloLens 2에서 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드되고 적용될 때까지 무기한 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-285">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span>

<span data-ttu-id="180d2-286">HoloLens 2에서 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면 OOBE에서 다음 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-286">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span>

- <span data-ttu-id="180d2-287">런타임 프로비전을 사용하여 로컬 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="180d2-287">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="180d2-288">런타임 프로비전을 통해 Azure AD 조인 작업 수행</span><span class="sxs-lookup"><span data-stu-id="180d2-288">Performing Azure AD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="180d2-289">OOBE 환경에서 장치를 소유하는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="180d2-289">Selecting who owns the device in OOBE experience</span></span> 

#### <a name="how-to-set-this-using-intune"></a><span data-ttu-id="180d2-290">Intune을 사용하여 설정하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="180d2-290">How to set this using Intune?</span></span> 
1. <span data-ttu-id="180d2-291">사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-291">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="180d2-292">OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-292">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-293">![OMA-URI를 통해 테넌트 잠금 설정](images/hololens-tenant-lockdown.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-293">![Setting tennant lockdown via OMA-URI](images/hololens-tenant-lockdown.png)</span></span>

1. <span data-ttu-id="180d2-294">그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-294">Create a group and assign the device configuration profile to that device group.</span></span>

1. <span data-ttu-id="180d2-295">이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-295">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="180d2-296">Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-296">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="180d2-297">이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-297">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a><span data-ttu-id="180d2-298">Intune을 사용하여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="180d2-298">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span>

1. <span data-ttu-id="180d2-299">위에서 만든 장치 구성이 이전에 할당되었던 장치 그룹에서 HoloLens 2를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-299">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span>

1. <span data-ttu-id="180d2-300">사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE를 false로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-300">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span>
<span data-ttu-id="180d2-301">OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-301">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="180d2-302">![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)</span><span class="sxs-lookup"><span data-stu-id="180d2-302">![Screenshot of setting RequireNetworkInOOBE to false via OMA URI in Intune](images/hololens-tenant-lockdown-false.png)</span></span>

1. <span data-ttu-id="180d2-303">그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-303">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="180d2-304">이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-304">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="180d2-305">Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-305">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="180d2-306">이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-306">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span>

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a><span data-ttu-id="180d2-307">TenantLockdown true로 설정된 후 HoloLens에서 Autopilot 프로필이 할당되지 않은 경우 OOBE 중에 무슨 문제가 발생하나요?</span><span class="sxs-lookup"><span data-stu-id="180d2-307">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="180d2-308">Autopilot 프로필이 다운로드될 때까지 OOBE가 무기한 대기하고 다음 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-308">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="180d2-309">TenantLockdown 효과를 제거하려면 먼저 Autopilot만 사용하여 장치를 원래 테넌트에 등록해야 하며, TenantLockdown CSP에서 도입한 제한 사항이 제거되기 전에 이전 단계에서 설명한 대로 RequireNetworkInOOBE를 설정 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-309">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span>

![장치에서 정책이 시행될 때의 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a><span data-ttu-id="180d2-311">알려진 문제 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="180d2-311">Known Issues & limitations</span></span>

- <span data-ttu-id="180d2-312">MEM에 구성된 디바이스 컨텍스트 기반 응용 프로그램 설치가 HoloLens에 적용되지 않는 문제를 조사 중입니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-312">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="180d2-313">디바이스 컨텍스트 및 사용자 컨텍스트 설치에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-313">Learn more about device context and user context installs.</span></span>](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="180d2-314">Wi-Fi를 통해 Autopilot을 설정하는 동안 인터넷 연결이 처음 설정될 때 Autopilot 프로필이 다운로드되지 않는 인스턴스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-314">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="180d2-315">이 경우 EULA(최종 사용자 사용권 계약)가 표시되며 사용자가 Autopilot이 아닌 설치 환경을 진행할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-315">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="180d2-316">Autopilot을 사용하여 다시 설정하려면, 장치를 절전 모드로 전환한 다음 전원을 켜고 장치를 다시 부팅하여 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-316">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="180d2-317">"모든 대상 장치를 Autopilot으로 변환" 기능은 현재 HoloLens에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-317">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="troubleshooting"></a><span data-ttu-id="180d2-318">문제 해결</span><span class="sxs-lookup"><span data-stu-id="180d2-318">Troubleshooting</span></span>

<span data-ttu-id="180d2-319">다음 문서는 자세한 정보를 알아보고 Autopilot 문제를 해결하는 데 유용한 리소스가 될 수 있지만, 이러한 문서가 Windows 10 데스크톱을 기반으로 하며 모든 정보가 HoloLens에 적용되는 것은 아니라는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-319">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="180d2-320">Windows Autopilot - 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="180d2-320">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="180d2-321">Microsoft Intune에서 iOS 디바이스 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="180d2-321">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="180d2-322">Windows Autopilot - 정책 충돌</span><span class="sxs-lookup"><span data-stu-id="180d2-322">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a><span data-ttu-id="180d2-323">Autopilot에 대한 피드백 및 지원</span><span class="sxs-lookup"><span data-stu-id="180d2-323">Feedback and support for Autopilot</span></span>

<span data-ttu-id="180d2-324">피드백이나 보고서 문제를 제공하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-324">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="180d2-325">장치 등록에 대한 지원이 필요한 경우 재판매인 또는 배포자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-325">For support on device registration, please contact your reseller or distributor.</span></span>
- <span data-ttu-id="180d2-326">Windows Autopilot에 대한 일반적인 지원 질문 또는 프로필 할당, 그룹 만들기 또는 MEM 포털 컨트롤과 같은 문제에 대한 자세한 내용은 [Microsoft Endpoint Manager 고객 지원팀에 문의하세요.](/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="180d2-326">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](/mem/get-support)</span></span>  
- <span data-ttu-id="180d2-327">장치가 Autopilot 서비스에 등록되어 있고 프로필이 MEM 포털에 할당된 경우 HoloLens [고객 지원팀](/hololens/)('지원' 카드 참조)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-327">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="180d2-328">지원 티켓을 열고 해당하는 경우 OOBE(첫 실행 경험) 중에 [오프라인 진단 로그](hololens-diagnostic-logs.md#offline-diagnostics)를 캡처하여 스크린샷과 로그를 포함하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-328">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="180d2-329">장치에서 문제를 보고하려면 HoloLens의 피드백 허브 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-329">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="180d2-330">피드백 허브에서 **Enterprise Management** > **장치** 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="180d2-330">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>
- <span data-ttu-id="180d2-331">HoloLens용 Autopilot에 대한 일반적인 피드백을 제공하려면 이 [설문 조사](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="180d2-331">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span>
