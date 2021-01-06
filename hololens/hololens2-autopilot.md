---
title: HoloLens용 Windows 자동 실행 2
description: HoloLens 2 장치에서 Autopilot를 설정하는 방법
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
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 98f35c52091a2d477a2f0852f66ad706498ad026
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253594"
---
# <span data-ttu-id="5b173-104">HoloLens용 Windows 자동 실행 2</span><span class="sxs-lookup"><span data-stu-id="5b173-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="5b173-105">Windows Holographic 버전 2004, HoloLens 2에서Windows Autopilot [자체 배포 모드](https://docs.microsoft.com/mem/autopilot/self-deploying)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](https://docs.microsoft.com/mem/autopilot/self-deploying).</span></span> <span data-ttu-id="5b173-106">관리자는 Microsoft Endpoint Manager에서 OOBE(첫 실행 경험)를 구성하고 최종 사용자가 거의 또는 전혀 상호 작용 없이 비즈니스용으로 장치를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="5b173-107">이를 통해 인벤토리 관리 오버헤드, 실제 장치 준비 비용 및 설치 경험 중 직원의 지원 요청을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="5b173-108">Windows 자동 조종에 대해 자세히 알아보려면 [여기](https://docs.microsoft.com/mem/autopilot/windows-autopilot)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-108">To learn more about Windows Autopilot, click [here](https://docs.microsoft.com/mem/autopilot/windows-autopilot).</span></span>

<span data-ttu-id="5b173-109">Surface 디바이스와 마찬가지로 고객은 Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider)(리셀러 또는 디스트리뷰터)와 협력하여 파트너 센터를 통해 Autopilot 서비스에 등록된 디바이스를 가져오는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="5b173-110">다른 장치 등록 방법에 대한 자세한 내용은 [여기](https://docs.microsoft.com/mem/autopilot/add-devices)에 나와 있습니다. Microsoft의 채널 파트너를 활용하여 가장 효율적인 종단 간 경로를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-110">Other methods for device registration are outlined [here](https://docs.microsoft.com/mem/autopilot/add-devices), though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span>

> [!NOTE]
> <span data-ttu-id="5b173-111">11/20/2020을 기준으로 Microsoft Endpoint Manager의 HoloLens에 대한 자동 설정 구성이 **공개 미리 보기**으로 전환되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="5b173-112">고객은 더 이상 개인 미리 보기에 등록할 필요가 없으며 모든 테넌트는 MEM 관리 센터에서 Autopilot을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="5b173-113">사용자가 자동 실행 자가 배포 프로세스를 시작하면 자동 실행은 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="5b173-114">장치를 Azure Active Directory(Azure AD)에 가입시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="5b173-115">HoloLens용 Autopilot은 Active Directory 가입 또는 하이브리드 Azure AD 가입을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>

1. <span data-ttu-id="5b173-116">Azure AD를 사용하여 Microsoft Endpoint Manager(또는 다른 MDM 서비스)에 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="5b173-117">장치 대상 정책, 인증서, 네트워킹 프로파일 및 응용프로그램을 다운로드하여 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="5b173-118">장치를 프로비저닝합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-118">Provision the device.</span></span>

1. <span data-ttu-id="5b173-119">로그인 화면을 사용자에게 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-119">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="5b173-120">HoloLens 2에 대해 Autopilot을 구성하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="5b173-121">환경을 설정하려면 다음 단계를 따르시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="5b173-122">HoloLens 2에 대한 Windows 자동 실행 요구 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="5b173-123">자동 MDM 등록 사용</span><span class="sxs-lookup"><span data-stu-id="5b173-123">Enable Automatic MDM Enrollment</span></span>](#2-enable-automatic-mdm-enrollment)

1. [<span data-ttu-id="5b173-124">Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="5b173-124">Register devices in Windows Autopilot.</span></span>](#3-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="5b173-125">장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="5b173-125">Create a device group.</span></span>](#4-create-a-device-group)

1. [<span data-ttu-id="5b173-126">배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="5b173-126">Create a deployment profile.</span></span>](#5-create-a-deployment-profile)

1. [<span data-ttu-id="5b173-127">ESP (등록 상태 페이지) 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-127">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#6-verify-the-esp-configuration)

1. [<span data-ttu-id="5b173-128">HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="5b173-128">Verify the profile status of the HoloLens devices.</span></span>](#7-verify-the-profile-status-of-the-hololens-devices)

### <span data-ttu-id="5b173-129">1. HoloLens 2 용 Windows Autopilot 요구 사항 검토</span><span class="sxs-lookup"><span data-stu-id="5b173-129">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

#### <span data-ttu-id="5b173-130">Windows Autopilot 요구 사항 문서의 다음 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-130">Review the following sections of the Windows Autopilot requirements article:</span></span>

- [<span data-ttu-id="5b173-131">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b173-131">Network requirements</span></span>](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="5b173-132">라이선싱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b173-132">Licensing requirements</span></span>](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="5b173-133">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b173-133">Configuration requirements</span></span>](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**<span data-ttu-id="5b173-134">Windows Autopilot 자체 배포 모드 문서의 "[요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" 섹션을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-134">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="5b173-135">사용자 환경은 표준 Windows Autopilot 요구 사항뿐만 아니라 이러한 요구 사항도 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-135">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="5b173-136">문서의 "단계별 안내” 및 "유효성 검사" 섹션은 검토할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-136">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="5b173-137">이 문서의 뒷부분에 나오는 절차는 HoloLens에 특정하여 해당되는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-137">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span>

<span data-ttu-id="5b173-138">장치를 등록하고 프로필을 구성하는 방법에 대한 자세한 내용은 이 문서의 [2. Windows Autopilot에서 장치 등록](#3-register-devices-in-windows-autopilot) 및 [4. 배포 프로필 만들기](#5-create-a-deployment-profile)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-138">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#3-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#5-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="5b173-139">Autopilot 자체 배포 모드 프로필을 구성하고 관리하려면 [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-139">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

#### <span data-ttu-id="5b173-140">HoloLens OS 요구 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-140">Review HoloLens OS requirements:</span></span>

- <span data-ttu-id="5b173-141">디바이스는 [Windows 홀로그래픽, 버전 2004](hololens-release-notes.md#windows-holographic-version-2004)(빌드 19041.1103) 이상에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-141">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="5b173-142">디바이스의 빌드 버전을 확인하거나 최신 OS로 재플래시하려면 [고급 복구 도우미(ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-142">To confirm the build version on your device or re-flash to the latest OS, you can use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="5b173-143">[여기](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)에서 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-143">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="5b173-144">2020년 9월 말까지 제공되는 장치에는 Windows Holographic 버전 1903이 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-144">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="5b173-145">Autopilot 지원 장치가 배송되었는지 확인하려면 대리점에 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-145">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="5b173-146">Windows Holographic 버전 2004는 이더넷 연결을 통해서만 Autopilot를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-146">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="5b173-147">**HoloLens를 켜기 전에** "USB-C에서 이더넷" 어댑터를 사용하여 HoloLens가 이더넷에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-147">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="5b173-148">장치 부팅 시 사용자 상호 작용이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-148">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="5b173-149">많은 HoloLens 장치에 대한 자동 설치 롤아웃을 계획하고 있는 경우 어댑터 인프라에 대한 계획을 세우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-149">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="5b173-150">USB 허브는 HoloLens에서 지원되지 않는 타사 드라이버를 추가로 설치해야 하는 경우가 많기 때문에 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-150">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span>

- <span data-ttu-id="5b173-151">이더넷 어댑터를 계속 사용하는 경우에도 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (빌드 19041.1128) 이상 지원 Autopilot Wi-Fi를 통해 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-151">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="5b173-152">Wi-Fi를 통해 연결된 장치의 경우 사용자는 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-152">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="5b173-153">벌새 장면을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-153">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="5b173-154">언어 및 로케일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-154">Choose the language and locale</span></span>
     - <span data-ttu-id="5b173-155">눈 보정을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-155">Run eye-calibration</span></span>
     - <span data-ttu-id="5b173-156">네트워크 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-156">Establish network connection</span></span>

- <span data-ttu-id="5b173-157">Windows 홀로그래픽, 버전 20H2에서는 [Tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)을(를) 지원하므로 테넌트에 장치를 잠그고 우발적이거나 의도적인 재설정 또는 삭제 시 장치가 해당 테넌트에 바인딩된 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-157">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="5b173-158">장치가 이미 Azure AD의 구성원이 아니며 Intune(또는 다른 MDM 시스템)에 등록되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-158">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="5b173-159">Autopilot 자체 배포 프로세스는 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-159">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="5b173-160">모든 장치 관련 정보를 정리하려면 Azure AD 및 Intune 포털 모두에서 **장치** 페이지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-160">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="5b173-161">현재 HoloLens에서는 "모든 대상 장치를 자동 실행으로 변환" 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-161">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="5b173-162">2. 자동 MDM 등록을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="5b173-162">2. Enable Automatic MDM Enrollment:</span></span>

<span data-ttu-id="5b173-163">Autopilot이 성공하려면 Azure Portal에서 자동 MDM 등록을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-163">In order for Autopilot to succeed you'll need to enable Automatic MDM Enrollment in your Azure portal.</span></span> <span data-ttu-id="5b173-164">이렇게 하면 사용자 없이 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-164">This will enable the device to enroll without a user.</span></span>

<span data-ttu-id="5b173-165">[Azure Portal](https://portal.azure.com/#home)에서 **Azure Active Directory** -> **Mobility(MDM 및 MAM)** -> **Microsoft Intune**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-165">In the [Azure portal](https://portal.azure.com/#home) select **Azure Active Directory** -> **Mobility (MDM and MAM)** -> **Microsoft Intune**.</span></span> <span data-ttu-id="5b173-166">그런 다음 **MDM 사용자 범위**를 구성합니다. **모두**를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-166">Then configure the **MDM user scope**, you will need to select **All**.</span></span>

<span data-ttu-id="5b173-167">자세한 내용은 다음 [MDM 자동 등록 사용 안내](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 또는 [자동 등록 빠른 시작 가이드](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-167">Please review the following short [guide on enabling MDM Automatic Enrollment](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) or the [Auto Enrollment Quick start guide](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) for even more information getting set up.</span></span>

### <span data-ttu-id="5b173-168">3. Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="5b173-168">3. Register devices in Windows Autopilot</span></span>

#### <span data-ttu-id="5b173-169">하드웨어 해시 획득</span><span class="sxs-lookup"><span data-stu-id="5b173-169">Obtain hardware hash</span></span>

<span data-ttu-id="5b173-170">장치를 처음 설치하기 전에 Windows Autopilot에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-170">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="5b173-171">디바이스 등록에 대한 MEM 설명서는 [Autopilot에 디바이스 추가](https://docs.microsoft.com/mem/autopilot/add-devices)를 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-171">For MEM documentation on device registration please see [Adding devices to Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="5b173-172">HoloLens 장치를 등록하는 기본 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-172">There are two primary ways to register HoloLens devices:</span></span>

 - **<span data-ttu-id="5b173-173">리셀러는 사용자가 주문을 할 때 파트너 센터에 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-173">Reseller can register devices in the Partner Center when you place an order.</span></span>**

   > [!NOTE]  
   > <span data-ttu-id="5b173-174">Autopilot 서비스에 장치를 추가하는 데 권장되는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-174">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="5b173-175">[자세한 내용을 알아보세요](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).</span><span class="sxs-lookup"><span data-stu-id="5b173-175">[Learn more](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).</span></span>  

 - <span data-ttu-id="5b173-176">**하드웨어 해시(하드웨어 ID라고도 함)를 검색**하고 MEM 관리 센터에 디바이스를 수동으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-176">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span>

- **<span data-ttu-id="5b173-177">하드웨어 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-177">Retrieve hardware hash</span></span>**

<span data-ttu-id="5b173-178">장치는 OOBE 프로세스 중에 또는 나중에 장치 소유자가 진단 로그 수집 프로세스를 시작할 때 하드웨어 해시를 CSV 파일에 기록합니다(다음 절차에서 설명함).</span><span class="sxs-lookup"><span data-stu-id="5b173-178">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="5b173-179">일반적으로 장치 소유자는 장치에 처음으로 로그인한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-179">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="5b173-180">HoloLens 2 장치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-180">Start the HoloLens 2 device.</span></span>

1. <span data-ttu-id="5b173-181">장치에서 **전원** 및 **볼륨 작게 단추**를 동시에 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-181">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="5b173-182">장치는 진단 로그와 하드웨어 해시를 수집하여 .zip 파일 집합에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-182">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>

   1. <span data-ttu-id="5b173-183">이 기능을 수행하는 방법에 대한 자세한 내용과 교육 비디오를 보려면 [오프라인 진단](hololens-diagnostic-logs.md#offline-diagnostics)정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-183">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

1. <span data-ttu-id="5b173-184">USB-C 케이블을 사용하여 장치를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-184">Use a USB-C cable to connect the device to a computer.</span></span>

1. <span data-ttu-id="5b173-185">컴퓨터에서 파일 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-185">On the computer, open File Explorer.</span></span> <span data-ttu-id="5b173-186">**내 PC\\\<*HoloLens device name*>\\내부 저장소\\문서**를 열고, AutopilotDiagnostics.zip 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-186">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="5b173-187">.zip 파일을 즉시 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-187">The .zip file may not immediately be available.</span></span> <span data-ttu-id="5b173-188">파일이 아직 준비되지 않은 경우 문서 폴더에 HoloLensDiagnostics.temp 파일이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-188">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="5b173-189">파일 목록을 업데이트하려면 창을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-189">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="5b173-190">AutopilotDiagnostics.zip 파일의 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-190">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

1. <span data-ttu-id="5b173-191">추출된 파일에서 파일 이름 접두사가 "DeviceHash"인 CSV 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-191">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="5b173-192">해당 파일을 컴퓨터의 드라이브에 복사하여 나중에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-192">Copy that file to a drive on the computer where you can access it later.</span></span>  

   > [!IMPORTANT]  
   > <span data-ttu-id="5b173-193">CSV 파일의 데이터는 다음 헤더 및 줄 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-193">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <span data-ttu-id="5b173-194">MEM을 통해 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-194">Register device through MEM</span></span>

1. <span data-ttu-id="5b173-195">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **장치**  > **Windows** > **Windows 등록**을 선택한 다음 **Windows Autopilot 배포 프로그램** 아래에서 **장치** > **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-195">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="5b173-196">**Windows Autopilot 장치 추가** 아래에서 DeviceHash CSV 파일을 선택하고 **열기**를 선택한 다음 **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-196">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  

   > [!div class="mx-imgBorder"]
   > ![가져오기 명령을 사용하여 하드웨어 해시를 가져옵니다.](./images/hololens-ap-hash-import.png)

1. <span data-ttu-id="5b173-198">가져오기가 완료되면 **장치** > **Windows** > **Windows 등록** > **장치** > **동기화**를 선택합니다. 동기화되는 장치 수에 따라 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-198">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="5b173-199">등록된 장치를 보려면 **새로 고침**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-199">To see the registered device, select **Refresh**.</span></span>  

   > [!div class="mx-imgBorder"]
   > ![동기화 및 새로 고침 명령을 사용하여 장치 목록을 표시합니다.](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="5b173-201">4. 장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="5b173-201">4. Create a device group</span></span>

1. <span data-ttu-id="5b173-202">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **그룹** > **새 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-202">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="5b173-203">**그룹 유형**에 대해 **보안**을 선택한 다음 그룹 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-203">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="5b173-204">**구성원 자격 유형**에 대해 **할당됨** 또는 **동적 장치**중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-204">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="5b173-205">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-205">Do one of the following:</span></span>  

   - <span data-ttu-id="5b173-206">이전 단계에서 **구성원 자격 유형**에 대해 **할당됨**을 선택한 경우 **구성원**을 선택한 다음 그룹에 Autopilot 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-206">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="5b173-207">아직 등록되지 않은 Autopilot 장치는 장치 일련 번호를 장치 이름으로 사용하여 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-207">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="5b173-208">이전 단계에서 **구성원 자격 유형**에 대해 **구성원 자격 유형**을 선택한 경우 **동적 장치 구성원**을 선택한 다음 다음과 유사한 **고급 규칙**에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-208">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="5b173-209">모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-209">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="5b173-210">Intune의 그룹 태그 필드는 Azure AD 장치의 **OrderID** 특성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-210">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="5b173-211">특정 그룹 태그(Azure AD 장치 OrderID)가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-211">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="5b173-212">특정 구매 주문 ID가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-212">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="5b173-213">이러한 규칙은 Autopilot 장치에 고유한 특성을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-213">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="5b173-214">**확인**을 선택하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-214">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="5b173-215">5. 배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="5b173-215">5. Create a deployment profile</span></span>

1. <span data-ttu-id="5b173-216">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에서 **장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기** > **HoloLens**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-216">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   ![프로필 만들기 드롭다운에는 HoloLens 항목이 포함됩니다.](./images/hololens-ap-enrollment-profiles.png)

1. <span data-ttu-id="5b173-218">프로필 이름과 설명을 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-218">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="5b173-219">**HoloLens**를 포함하는 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-219">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="5b173-220">이 옵션이 표시되지 않는 경우 [피드백](hololens2-autopilot.md#feedback-and-support-for-autopilot) 옵션 중 하나를 사용하여 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-220">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   > [!div class="mx-imgBorder"]
   > ![프로필 이름 및 설명 추가](./images/hololens-ap-profile-name.png)

1. <span data-ttu-id="5b173-222">**첫 실행 경험(OOBE)** 페이지에서 대부분의 설정이 이 평가에 대한 OOBE를 간소화하도록 사전 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-222">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="5b173-223">선택적으로 구성할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-223">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="5b173-224">**언어(지역)**: OOBE의 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-224">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="5b173-225">[HoloLens 2에 지원되는 언어](hololens2-language-support.md) 목록에서 언어를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-225">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="5b173-226">**키보드 자동 구성**: 키보드가 선택한 언어와 일치하도록 하려면 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-226">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="5b173-227">**장치 이름 템플릿 적용**: OOBE 중에 장치 이름을 자동으로 설정하려면 **예**를 선택한 다음 템플릿 문구 및 자리 표시자를 **이름 입력**에 입력합니다. 예를 들어, 접두어와 4 자리 난수의 `%RAND:4%`&mdash;자리 표시자를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-227">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="5b173-228">장치 이름 템플릿을 사용하는 경우 OOBE 프로세스는 장치 이름을 적용한 후 장치를 Azure AD에 가입시키기 전에 한 번 더 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-228">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="5b173-229">다시 시작하면 새 이름이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-229">This restart enables the new name to take effect.</span></span>  

   > [!div class="mx-imgBorder"]
   > ![OOBE 설정 구성](./images/hololens-ap-profile-oobe.png)

1. <span data-ttu-id="5b173-231">설정을 구성한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-231">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="5b173-232">**범위 태그** 페이지에서 이 프로필에 적용하려는 범위 태그를 선택적으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-232">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="5b173-233">범위 태그에 대한 자세한 내용은 [분산 IT에 역할 기반 액세스 제어 및 범위 태그 사용](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-233">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="5b173-234">작업이 완료되면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-234">When finished, select **Next**.</span></span>
1. <span data-ttu-id="5b173-235">**할당** 페이지에서 **할당 대상**으로 **선택된 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-235">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="5b173-236">**선택된 그룹**에서 **+ 포함할 그룹 선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-236">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="5b173-237">**포함할 그룹 선택** 목록에서 Autopilot HoloLens 장치에 대해 생성한 장치 그룹을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-237">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="5b173-238">그룹을 제외하려면 **제외할 그룹 선택**을 선택하고 제외하려는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-238">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   > [!div class="mx-imgBorder"]
   > ![장치 그룹을 프로필에 할당합니다.](./images/hololens-ap-profile-assign-devicegroup.png)

1. <span data-ttu-id="5b173-240">**검토 + 만들기** 페이지에서 설정을 검토한 후 **만들기**를 선택하여 프로필을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-240">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  

   > [!div class="mx-imgBorder"]
   > ![검토 + 만들기](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="5b173-242">6. ESP 구성 확인</span><span class="sxs-lookup"><span data-stu-id="5b173-242">6. Verify the ESP configuration</span></span>

<span data-ttu-id="5b173-243">등록 상태 페이지(ESP)는 MDM 관리 사용자가 처음으로 장치에 로그인할 때 실행되는 전체 장치 구성 프로세스의 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-243">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="5b173-244">ESP 구성이 다음과 유사한지 확인하고 할당이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-244">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> ![ESP 구성](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="5b173-246">7. HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="5b173-246">7. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="5b173-247">Microsoft Endpoint Manager 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-247">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="5b173-248">HoloLens 장치가 나열되어 있고 프로필 상태가 **할당됨**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-248">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="5b173-249">프로필이 장치에 할당되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-249">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]
   > ![장치 및 프로필 할당](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="5b173-251">HoloLens 2용 Windows Autopilot 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="5b173-251">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="5b173-252">위의 지침이 완료되면 HoloLens 2 사용자는 다음과 같은 환경을 통해 HoloLens 장치를 프로비저닝할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-252">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="5b173-253">Autopilot 환경에는 인터넷 액세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-253">Autopilot experience requires internet access.</span></span> <span data-ttu-id="5b173-254">다음 옵션 중 하나를 사용하여 인터넷 액세스를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-254">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="5b173-255">OOBE의 Wi-Fi 네트워크에 장치를 연결한 다음 자동으로 Autopilot 환경을 감지하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-255">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="5b173-256">이는 Autopilot 경험이 자체적으로 완료될 때까지 OOBE와 상호 작용해야 할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-256">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="5b173-257">기본적으로 HoloLens 2는 인터넷 검색 후 Autopilot를 감지하기 위해 10초 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-257">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="5b173-258">10초 내에 autopilot 프로필이 검색되지 않으면 OOBE에 EULA가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-258">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="5b173-259">이 문제가 발생하는 경우 장치를 다시 부팅하여 다시 Autopilot를 검색해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-259">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="5b173-260">또한 Autopilot에는 TenantLockdown 정책이 장치에 설정된 경우에만 OOBE가 무한정 대기할 수 있다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-260">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>

    - <span data-ttu-id="5b173-261">유선 인터넷 연결에 "USB-C to Ethernet" 어댑터를 사용하여 디바이스를 이더넷에 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-261">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

    - <span data-ttu-id="5b173-262">무선 인터넷 연결을 위한 "USB-C to Wifi" 어댑터를 사용하여 장치를 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-262">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="5b173-263">Autopilot용 OOOBE를 위해 Wi-Fi 네트워크를 사용하려는 장치는 [Windows Holographic 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-263">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="5b173-264">이더넷 어댑터를 사용하는 디바이스의 경우 OOBE(사용자 환경)가 시작되기 전에 디바이스를 네트워크에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-264">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="5b173-265">첫 번째 OOBE 화면에서 장치는 Autopilot 장치로 프로비전 중인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-265">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="5b173-266">장치를 네트워크에 연결할 수 없거나 장치를 Autopilot 장치로 프로비전하지 않도록 선택하는 경우 나중에 Autopilot 프로비전으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-266">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="5b173-267">대신 장치를 Autopilot 장치로 프로비전하려면 이 절차를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-267">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="5b173-268">장치가 자동으로 OOBE를 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-268">The device should automatically start OOBE.</span></span> <span data-ttu-id="5b173-269">OOBE는 신경쓰지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-269">Do not interact with OOBE.</span></span> <span data-ttu-id="5b173-270">그 대신 잠시 기다려 주세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-270">Instead sit, back and relax!</span></span> <span data-ttu-id="5b173-271">HoloLens 2에서 네트워크 연결을 검색하여 OOBE를 자동으로 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-271">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="5b173-272">OOBE가 진행되는 동안 장치가 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-272">The device may restart during OOBE.</span></span> <span data-ttu-id="5b173-273">OOBE 화면은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-273">The OOBE screens should resemble the following.</span></span>

   <span data-ttu-id="5b173-274">![OOBE 단계 1](./images/autopilot-welcome.jpg)
   ![OOBE 단계 2](./images/autopilot-step-complete.jpg)
   ![OOBE 단계 3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="5b173-274">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="5b173-275">OOBE가 끝나면 사용자 이름과 암호를 사용하여 장치에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-275">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <span data-ttu-id="5b173-276">Tenantlockdown CSP 및 Autopilot</span><span class="sxs-lookup"><span data-stu-id="5b173-276">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="5b173-277">HoloLens 2 장치는 Windows 홀로그램, 버전 20H2의 TenantLockdown CSP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-277">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="5b173-278">이 CSP는 장치 재설정이나 reflash를 통해 장치를 테넌트로 잠가 조직의 테넌트에 디바이스를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-278">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span>

<span data-ttu-id="5b173-279">[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용하여 HoloLens 2를 MDM 등록에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-279">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="5b173-280">TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false (초기 설정) 값으로 설정되고, 다시 깜박이는 경우, OS 업데이트 등의 장치에도 해당 값이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-280">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span>

<span data-ttu-id="5b173-281">HoloLens 2에서 TenantLockdown Csp의 RequireNetworkInOOBE 노드가 true로 설정되면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드되고 적용될 때까지 무기한 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-281">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span>

<span data-ttu-id="5b173-282">RequireNetworkInOOBE는 HoloLens 2에서 TenantLockdown Csp의 a 노드가 true로 설정되 면 OOBE에서 다음 작업을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-282">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span>

- <span data-ttu-id="5b173-283">런타임 프로비저닝을 사용하여 로컬 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="5b173-283">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="5b173-284">런타임 프로비저닝을 통해 Azure AD 참여 작업 수행</span><span class="sxs-lookup"><span data-stu-id="5b173-284">Performing Azure AD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="5b173-285">OOBE 환경에서 장치를 소유하는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="5b173-285">Selecting who owns the device in OOBE experience</span></span> 

#### <span data-ttu-id="5b173-286">Intune을 사용하여 설정하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="5b173-286">How to set this using Intune?</span></span> 
1. <span data-ttu-id="5b173-287">사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-287">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="5b173-288">OMA URI 값은/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-288">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 tennant 잠금 설정](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="5b173-290">그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-290">Create a group and assign the device configuration profile to that device group.</span></span>

1. <span data-ttu-id="5b173-291">이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-291">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="5b173-292">장치 구성이 성공적으로 적용되었는지 Intune 포털에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-292">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="5b173-293">이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-293">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <span data-ttu-id="5b173-294">Intune을 사용하여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제하는 방법</span><span class="sxs-lookup"><span data-stu-id="5b173-294">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span>

1. <span data-ttu-id="5b173-295">위에서 만든 장치 구성이 이전에 할당된 장치 그룹에서 HoloLens 2를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-295">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span>

1. <span data-ttu-id="5b173-296">사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE에 대해 false를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-296">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span>
<span data-ttu-id="5b173-297">OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-297">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="5b173-299">그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-299">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="5b173-300">이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-300">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="5b173-301">장치 구성이 성공적으로 적용되었는지 Intune 포털에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-301">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="5b173-302">이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-302">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span>

#### <span data-ttu-id="5b173-303">TenantLockdown true로 설정된 후 HoloLens에서 Autopilot 프로필이 할당되지 않은 경우 OOBE 중에 무슨 문제가 발생하나요?</span><span class="sxs-lookup"><span data-stu-id="5b173-303">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="5b173-304">OOBE는 Autopilot 프로필이 다운로드될 때까지 무기한 대기하고 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-304">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="5b173-305">TenantLockdown 효과를 제거하려면 장치를 원래 테넌트만 사용하여 먼저 등록해야 하며, 이전 단계에서 설명한 대로 Autopilot를 설정하지 않아야 합니다. TenantLockdown CSP에서 도입된 제한이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-305">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span>

![장치에서 정책이 시행될 때의 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="5b173-307">알려진 문제 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5b173-307">Known Issues & limitations</span></span>

- <span data-ttu-id="5b173-308">MEM에 구성된 장치 컨텍스트 기반 응용 프로그램 설치가 HoloLens에 적용되지 않는 문제를 조사 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-308">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="5b173-309">장치 컨텍스트 및 사용자 컨텍스트 설치에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-309">Learn more about device context and user context installs.</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="5b173-310">Wi-Fi를 통해 Autopilot를 설정하는 동안 인터넷 연결이 처음 설정될 때 Autopilot 프로필이 다운로드되지 않는 인스턴스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-310">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="5b173-311">이 경우 EULA(최종 사용자 사용권 계약)이 표시되며 사용자는 Autopilot이 아닌 설치 환경을 진행할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-311">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="5b173-312">Autopilot를 사용하여 설정을 다시 시도하려면, 장치를 절전 모드로 전환한 다음 전원을 켜고 장치를 재부팅하여 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-312">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="5b173-313">"모든 대상 장치를 자동 실행으로 변환" 기능은 현재 HoloLens에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-313">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="5b173-314">문제 해결</span><span class="sxs-lookup"><span data-stu-id="5b173-314">Troubleshooting</span></span>

<span data-ttu-id="5b173-315">다음 문서는 자세한 정보를 알아보고 Autopilot 문제를 해결 하는 데 유용한 리소스가 될 수 있지만, 이러한 문서는 Windows 10 데스크톱을 기반으로 하며 모든 정보가 HoloLens에 적용되는 것이 아니라는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-315">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="5b173-316">Windows Autopilot - 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="5b173-316">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="5b173-317">Microsoft Intune에서 Windows 장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5b173-317">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="5b173-318">Windows Autopilot - 정책 충돌</span><span class="sxs-lookup"><span data-stu-id="5b173-318">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <span data-ttu-id="5b173-319">Autopilot에 대한 피드백 및 지원</span><span class="sxs-lookup"><span data-stu-id="5b173-319">Feedback and support for Autopilot</span></span>

<span data-ttu-id="5b173-320">피드백 또는 보고서 문제를 제공하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-320">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="5b173-321">장치 등록에 대한 지원이 필요한 경우 대리점 또는 대리점에 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-321">For support on device registration please contact your reseller or distributor.</span></span>
- <span data-ttu-id="5b173-322">Windows 자동 실행 기능에 대한 일반적인 지원 문의나 프로파일 할당, 그룹 생성 또는 MEM 포털 제어와 같은 문제는 [Microsoft Endpoint Manager 지원팀에 문의하시기 바랍니다.](https://docs.microsoft.com/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="5b173-322">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](https://docs.microsoft.com/mem/get-support)</span></span>  
- <span data-ttu-id="5b173-323">디바이스가 Autopilot 서비스에 등록되어 있고 프로파일이 MEM 포털에 할당된 경우 HoloLens [지원](https://docs.microsoft.com/hololens/)('지원' 카드 참조)에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-323">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](https://docs.microsoft.com/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="5b173-324">지원 티켓을 열고 해당하는 경우 OOBE(첫 실행 경험) 중에 [오프라인 진단 로그](hololens-diagnostic-logs.md#offline-diagnostics)를 캡처하여 스크린샷과 로그를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-324">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="5b173-325">장치에서 문제를 보고하려면 HoloLens의 피드백 허브 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-325">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="5b173-326">피드백 허브에서 **엔터프라이즈 관리** > **장치** 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b173-326">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>
- <span data-ttu-id="5b173-327">HoloLens용 Autopilot에 대한 일반적인 피드백을 제공하려면 이 [조사](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="5b173-327">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span>
