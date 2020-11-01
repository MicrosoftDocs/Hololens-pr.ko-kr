---
title: HoloLens2 용 Windows Autopilot(비공개 미리 보기)
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 6851249ab9ed79e7dcdea6afc853fee66fdddf19
ms.sourcegitcommit: a51f2e409f0207fc7457e97403b5298f1e0ad7dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145659"
---
# <span data-ttu-id="87318-103">HoloLens용 Windows 자동 실행 2</span><span class="sxs-lookup"><span data-stu-id="87318-103">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="87318-104">Windows Autopilot 프로그램에 HoloLens 2 장치를 설정할 때 사용자는 간단한 프로세스를 따라 클라우드에서 장치를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-104">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="87318-105">이 Autopilot 프로그램은 Autopilot 자체 배포 모드를 지원하여 테넌트에서 HoloLens 2 장치를 공유 장치로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-105">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="87318-106">자체 배포 모드는 프로비저닝 프로세스 중에 장치에 사전 설치된 OEM 이미지 및 드라이버를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-106">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="87318-107">사용자는 장치를 켜고 첫 실행 경험(OOBE)을 거치지 않고 장치를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-107">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span> <span data-ttu-id="87318-108">Windows 10용 Windows Autopilot에 대해 자세히 알아보려면 [여기](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-108">To learn more about Windows Autopilot for Windows 10 click [here](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

<span data-ttu-id="87318-109">사용자가 Autopilot 자체 배포 프로세스를 시작하면 프로세스에서 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-109">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="87318-110">장치를 Azure AD(Azure Active Directory)에 가입시킵니다.</span><span class="sxs-lookup"><span data-stu-id="87318-110">Join the device to Azure Active Directory (Azure AD).</span></span>
   > [!NOTE]  
   > <span data-ttu-id="87318-111">HoloLens용 Autopilot은 Active Directory 가입 또는 하이브리드 Azure AD 가입을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-111">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
1. <span data-ttu-id="87318-112">Azure AD를 사용하여 Microsoft Intune(또는 다른 MDM 서비스)에 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-112">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="87318-113">장치 대상 정책, 사용자 대상 앱, 인증서, 네트워킹 프로필을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-113">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="87318-114">장치를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-114">Provision the device.</span></span>
1. <span data-ttu-id="87318-115">사용자에게 로그인 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-115">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="87318-116">HoloLens2 용 Windows Autopilot(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="87318-116">Windows Autopilot for HoloLens 2 Private Preview</span></span>

<span data-ttu-id="87318-117">비공개 미리 보기를 위한 환경을 설정하려면 아래 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-117">Please follow the steps below to set up your environment for the private preview:</span></span>

1. <span data-ttu-id="87318-118">HoloLens2용 Windows Autopilot의 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="87318-118">Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>
1. <span data-ttu-id="87318-119">HoloLens 2용 Windows Autopilot 비공개 미리 보기 프로그램 등록</span><span class="sxs-lookup"><span data-stu-id="87318-119">Enroll in the Windows Autopilot for HoloLens 2 private preview program</span></span>
1. <span data-ttu-id="87318-120">테넌트가 플라이트 중인지(프로그램 참여를 위해 등록되어 있는지) 확인</span><span class="sxs-lookup"><span data-stu-id="87318-120">Verify that your tenant is flighted (enrolled to participate in the program)</span></span>
1. <span data-ttu-id="87318-121">Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="87318-121">Register your devices in Windows Autopilot</span></span>
1. <span data-ttu-id="87318-122">장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="87318-122">Create a device group</span></span>
1. <span data-ttu-id="87318-123">배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="87318-123">Create a deployment profile</span></span>
1. <span data-ttu-id="87318-124">ESP 구성 확인</span><span class="sxs-lookup"><span data-stu-id="87318-124">Verify the ESP configuration</span></span>
1. <span data-ttu-id="87318-125">HoloLens 장치에 대한 사용자 지정 구성 프로필 구성(알려진 문제)</span><span class="sxs-lookup"><span data-stu-id="87318-125">Configure a custom configuration profile for HoloLens devices (known issue)</span></span>
1. <span data-ttu-id="87318-126">HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="87318-126">Verify the profile status of the HoloLens devices</span></span>


### <span data-ttu-id="87318-127">1. HoloLens2용 Windows Autopilot의 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="87318-127">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="87318-128">Windows Autopilot 요구 사항 문서의 다음 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-128">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="87318-129">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="87318-129">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="87318-130">라이선싱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="87318-130">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="87318-131">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="87318-131">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**<span data-ttu-id="87318-132">Windows Autopilot 자체 배포 모드 문서의 "[요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" 섹션을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-132">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="87318-133">사용자 환경은 표준 Windows Autopilot 요구 사항뿐만 아니라 이러한 요구 사항도 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-133">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="87318-134">문서의 "단계별 안내” 및 "유효성 검사" 섹션은 검토할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-134">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="87318-135">이 문서의 뒷부분에 나오는 절차는 HoloLens에 특정하여 해당되는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-135">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="87318-136">장치를 등록하고 프로필을 구성하는 방법에 대한 자세한 내용은 이 문서의 [4. Windows Autopilot에서 장치 등록](#4-register-devices-in-windows-autopilot) 및 [6. 배포 프로필 만들기](#6-create-a-deployment-profile)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-136">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="87318-137">이 섹션에서는 HoloLens에 특정된 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-137">These sections provide steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="87318-138">HoloLens 2용 Windows 자동 실행에는 특정 운영 체제 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-138">Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span> <span data-ttu-id="87318-139">오토파일럿은 HoloLens 장치에 사전 설치된 Windows 홀로그래픽 버전 2004(빌드 19041.1103 이상)에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-139">Autopilot relies on Windows Holographic, version 2004 (build 19041.1103 or later) being pre-installed on HoloLens devices.</span></span> <span data-ttu-id="87318-140">2020년 9월 말까지 제공되는 장치에는 Windows Holographic 버전 1903이 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-140">Devices delivered until late September 2020 have Windows Holographic, version 1903 pre-installed.</span></span> <span data-ttu-id="87318-141">Autopilot 지원 장치 배송 기간은 대리점에 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="87318-141">Please contact your distributor to learn about when Autopilot-ready devices can be shipped to you.</span></span> <span data-ttu-id="87318-142">비공개 미리 보기에 참여하려면 아래 지침 및 요구 사항을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-142">If you wish to participate to the private preview, please review instructions and requirements below.</span></span>

**<span data-ttu-id="87318-143">Autopilot 미리 보기를 시도하려면 OOBE 및 프로비저닝 프로세스를 시작하기 전에 HoloLens 장치가 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-143">If you wish to try the Autopilot preview, before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>**

- <span data-ttu-id="87318-144">장치가 Windows 홀로그래픽 버전 2004에 있는지 확인합니다(빌드 19041.1103 이상).</span><span class="sxs-lookup"><span data-stu-id="87318-144">Ensure your device is on Windows Holographic, version 2004 (build 19041.1103 or later).</span></span> <span data-ttu-id="87318-145">최신 OS가 미리 설치되어 있지 않으면 [ARC(Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)을(를) 사용하여 수동으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-145">If the latest OS is not pre-installed you must manually update using the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="87318-146">[여기](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)에서 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-146">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> 
- <span data-ttu-id="87318-147">Windows Autopilot에서 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-147">Your devices must be registered in Windows Autopilot.</span></span> <span data-ttu-id="87318-148">장치를 등록하는 방법에 대한 자세한 내용은 [4. Windows Autopilot에서 장치 등록](#4-register-devices-in-windows-autopilot)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-148">For information about how to register devices see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot).</span></span> <span data-ttu-id="87318-149">권장 경로는 대리점 또는 대리점이 사용자를 위해 장치를 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87318-149">The recommended path is for your reseller or distributor to register devices for you.</span></span>     
- <span data-ttu-id="87318-150">현재 릴리스에서는 HoloLens를 켜고 Autopilot 프로비저닝 프로세스를 시작하기 전에 장치를 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-150">In the current release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="87318-151">유선 인터넷 연결의 "USB-C에서 이더넷" 어댑터를 사용하여 장치를 이더넷에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-151">Connect your device to Ethernet using a "USB-C to Ethernet" adapter for wired internet connectivity.</span></span> 
- <span data-ttu-id="87318-152">장치가 아직 Azure AD에 속하지 않으며 Intune(또는 다른 MDM 시스템)에 등록되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-152">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="87318-153">Autopilot 자체 배포 프로세스가 이러한 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-153">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="87318-154">모든 장치 관련 정보를 정리하려면 Azure AD 및 Intune 포털 모두에서 **장치** 페이지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-154">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span>
- <span data-ttu-id="87318-155">Autopilot 자체 배포 모드 프로필을 구성하고 관리하려면 [Microsoft 엔드포인트 관리자 관리 센터](https://endpoint.microsoft.com)에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-155">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>


### <span data-ttu-id="87318-156">2. HoloLens 2용 Windows Autopilot 프로그램 등록</span><span class="sxs-lookup"><span data-stu-id="87318-156">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

**<span data-ttu-id="87318-157">프로그램에 참여하려면 테넌트가 개인 미리보기 프로그램에 등록되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-157">To participate in the program, you must have your tenant enrolled to the Private Preview program.</span></span> <span data-ttu-id="87318-158">이렇게 하면 자동 조종에 대한 HoloLens별 Intune(MEM) UI 컨트롤이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-158">This enables HoloLens-specific Intune (aka MEM) UI controls for Autopilot.</span></span>** <span data-ttu-id="87318-159">이렇게 하려면 [HoloLens용 Windows Autopilot 비공개 미리 보기 요청](https://aka.ms/APHoloLensTAP)으로 이동하거나 다음 QR 코드를 사용하여 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-159">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR 코드](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="87318-161">Microsoft는 일주일에 한 번 테넌트를 비행합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-161">Microsoft flights tenants once a week.</span></span> <span data-ttu-id="87318-162">비행이 완료되면 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-162">You will receive an email notification once the flighting is complete.</span></span> 

<span data-ttu-id="87318-163">이 요청에서 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-163">In this request, provide the following information:</span></span>

- <span data-ttu-id="87318-164">테넌트 도메인</span><span class="sxs-lookup"><span data-stu-id="87318-164">Tenant domain</span></span>
- <span data-ttu-id="87318-165">테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="87318-165">Tenant ID</span></span>
- <span data-ttu-id="87318-166">이 평가에 참여하는 HoloLens 2 장치 수</span><span class="sxs-lookup"><span data-stu-id="87318-166">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="87318-167">Autopilot 자체 배포 모드를 사용하여 배포할 HoloLens 2 장치 수</span><span class="sxs-lookup"><span data-stu-id="87318-167">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="87318-168">3. 테넌트가 플라이트 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="87318-168">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="87318-169">요청을 제출한 후 테넌트가 Autopilot 프로그램에서 플라이트 중인지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-169">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="87318-170">[Microsoft 엔드포인트 관리자 관리 센터](https://endpoint.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-170">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>
1. <span data-ttu-id="87318-171">**장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-171">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![프로필 만들기 드롭다운에는 HoloLens 항목이 포함됩니다.](./images/hololens-ap-enrollment-profiles.png)
  <span data-ttu-id="87318-173">**HoloLens**를 포함하는 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-173">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="87318-174">이 옵션이 표시되지 않는 경우 [피드백](#feedback) 옵션 중 하나를 사용하여 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-174">If this option is not present, use one of the [Feedback](#feedback) options to contact us.</span></span>

### <span data-ttu-id="87318-175">4. Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="87318-175">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="87318-176">준비 단계에서는 Windows Autopilot에 장치를 등록할 수 있는 두 가지 기본 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-176">In the preparation phase, there are two primary ways you can register devices to Windows Autopilot:</span></span> 

1. <span data-ttu-id="87318-177">**장치를 등록하거나 주문한 배포자나 대리점에 문의**하거나</span><span class="sxs-lookup"><span data-stu-id="87318-177">**Contact your distributor or reseller when you place an order to have your devices registered** or</span></span>
2. **<span data-ttu-id="87318-178">하드웨어 해시(하드웨어 ID라고도 함)를 검색하고 장치를 수동으로 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-178">Retrieve the hardware hash (also known as the hardware ID) and register the device manually.</span></span>** 

<span data-ttu-id="87318-179">장치 등록에 대한 자세한 내용은 [Autopilot에 장치 추가](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) 설명서를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-179">For more information on device registration please review the [Adding devices to Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) documentation.</span></span>  

**<span data-ttu-id="87318-180">장치 하드웨어 해시 검색</span><span class="sxs-lookup"><span data-stu-id="87318-180">Retrieve a device hardware hash</span></span>**

<span data-ttu-id="87318-181">장치는 OOBE 프로세스가 진행되는 동안 또는 나중에 장치 소유자가 진단 로그 수집 프로세스(다음 절차에 설명)를 시작할 때 CSV 파일에서 하드웨어 해시를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-181">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="87318-182">일반적으로 장치 소유자는 처음에 장치에 로그인하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="87318-182">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="87318-183">HoloLens 2 장치 시작</span><span class="sxs-lookup"><span data-stu-id="87318-183">Start the HoloLens 2 device.</span></span>
1. <span data-ttu-id="87318-184">장치에서 전원 및 볼륨 작게 단추를 동시에 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-184">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="87318-185">장치에서 진단 로그와 하드웨어 해시를 수집하여 .zip 파일 집합에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-185">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>
1. <span data-ttu-id="87318-186">USB-C 케이블을 사용하여 장치를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-186">Use a USB-C cable to connect the device to a computer.</span></span>
1. <span data-ttu-id="87318-187">컴퓨터에서 파일 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="87318-187">On the computer, open File Explorer.</span></span> <span data-ttu-id="87318-188">**내 PC\\\<*HoloLens device name*>\\내부 저장소\\문서**를 열고, AutopilotDiagnostics.zip 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-188">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="87318-189">.zip 파일을 즉시 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-189">The .zip file may not immediately be available.</span></span> <span data-ttu-id="87318-190">파일이 아직 준비되지 않은 경우 문서 폴더에 HoloLensDiagnostics.temp 파일이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-190">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="87318-191">파일 목록을 업데이트하려면 창을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-191">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="87318-192">AutopilotDiagnostics.zip 파일의 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-192">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>
1. <span data-ttu-id="87318-193">추출된 파일에서 파일 이름 접두사가 "DeviceHash"인 CSV 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-193">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="87318-194">해당 파일을 컴퓨터의 드라이브에 복사하여 나중에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-194">Copy that file to a drive on the computer where you can access it later.</span></span>  
   > [!IMPORTANT]  
   > <span data-ttu-id="87318-195">CSV 파일의 데이터는 다음 헤더 및 줄 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-195">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="87318-196">Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="87318-196">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="87318-197">Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록**을 선택한 다음 **Windows Autopilot 배포 프로그램**아래에서 **장치** > **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-197">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="87318-198">**Windows Autopilot 장치 추가** 아래에서 DeviceHash CSV 파일을 선택하고 **열기**를 선택한 다음 **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-198">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![가져오기 명령을 사용하여 하드웨어 해시를 가져옵니다.](./images/hololens-ap-hash-import.png)
1. <span data-ttu-id="87318-200">가져오기가 완료되면 **장치** > **Windows** > **Windows 등록** > **장치** > **동기화**를 선택합니다. 동기화되는 장치 수에 따라 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-200">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="87318-201">등록된 장치를 보려면 **새로 고침**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-201">To see the registered device, select **Refresh**.</span></span>  
   
   ![동기화 및 새로 고침 명령을 사용하여 장치 목록을 표시합니다.](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="87318-203">5. 장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="87318-203">5. Create a device group</span></span>

1. <span data-ttu-id="87318-204">Microsoft 엔드포인트 관리자 관리 센터에서 **그룹** > **새 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-204">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>
1. <span data-ttu-id="87318-205">**그룹 유형**에 대해 **보안**을 선택한 다음 그룹 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-205">For **Group type**, select **Security**, and then enter a group name and description.</span></span>
1. <span data-ttu-id="87318-206">**구성원 자격 유형**에 대해 **할당됨** 또는 **동적 장치**중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-206">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>
1. <span data-ttu-id="87318-207">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-207">Do one of the following:</span></span>  
   
   - <span data-ttu-id="87318-208">이전 단계에서 **구성원 자격 유형**에 대해 **할당됨**을 선택한 경우 **구성원**을 선택한 다음 그룹에 Autopilot 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-208">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="87318-209">아직 등록되지 않은 Autopilot 장치는 장치 일련 번호를 장치 이름으로 사용하여 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-209">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="87318-210">이전 단계에서 **구성원 자격 유형**에 대해 **구성원 자격 유형**을 선택한 경우 **동적 장치 구성원**을 선택한 다음 다음과 유사한 **고급 규칙**에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-210">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="87318-211">모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-211">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="87318-212">Intune의 그룹 태그 필드는 Azure AD 장치의 **OrderID** 특성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-212">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="87318-213">특정 그룹 태그(Azure AD 장치 OrderID)가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-213">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="87318-214">특정 구매 주문 ID가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-214">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="87318-215">이러한 규칙은 Autopilot 장치에 고유한 특성을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-215">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="87318-216">**확인**을 선택하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-216">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="87318-217">6. 배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="87318-217">6. Create a deployment profile</span></span>

1. <span data-ttu-id="87318-218">Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기** > **HoloLens**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-218">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="87318-219">프로필 이름과 설명을 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-219">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![프로필 이름 및 설명 추가](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="87318-221">**첫 실행 경험(OOBE)** 페이지에서 대부분의 설정이 이 평가에 대한 OOBE를 간소화하도록 사전 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-221">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="87318-222">선택적으로 구성할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-222">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="87318-223">**언어(지역)**: OOBE의 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-223">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="87318-224">[HoloLens 2에 지원되는 언어](hololens2-language-support.md) 목록에서 언어를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-224">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="87318-225">**키보드 자동 구성**: 키보드가 선택한 언어와 일치하도록 하려면 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-225">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="87318-226">**장치 이름 템플릿 적용**: OOBE 중에 장치 이름을 자동으로 설정하려면 **예**를 선택한 다음 템플릿 문구 및 자리 표시자를 **이름 입력**에 입력합니다. 예를 들어, 접두어와 4 자리 난수의 `%RAND:4%`&mdash;자리 표시자를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-226">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="87318-227">장치 이름 템플릿을 사용하는 경우 OOBE 프로세스는 장치 이름을 적용한 후 장치를 Azure AD에 가입시키기 전에 한 번 더 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-227">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="87318-228">다시 시작하면 새 이름이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87318-228">This restart enables the new name to take effect.</span></span>  

   ![OOBE 설정 구성](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="87318-230">설정을 구성한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-230">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="87318-231">**범위 태그** 페이지에서 이 프로필에 적용하려는 범위 태그를 선택적으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-231">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="87318-232">범위 태그에 대한 자세한 내용은 [분산 IT에 역할 기반 액세스 제어 및 범위 태그 사용](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87318-232">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="87318-233">작업이 완료되면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-233">When finished, select **Next**.</span></span>
1. <span data-ttu-id="87318-234">**할당** 페이지에서 **할당 대상**으로 **선택된 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-234">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="87318-235">**선택된 그룹**에서 **+ 포함할 그룹 선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-235">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="87318-236">**포함할 그룹 선택** 목록에서 Autopilot HoloLens 장치에 대해 생성한 장치 그룹을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-236">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="87318-237">그룹을 제외하려면 **제외할 그룹 선택**을 선택하고 제외하려는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-237">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![장치 그룹을 프로필에 할당합니다.](./images/hololens-ap-profile-assign-devicegroup.png)
1. <span data-ttu-id="87318-239">**검토 + 만들기** 페이지에서 설정을 검토한 후 **만들기**를 선택하여 프로필을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-239">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![검토 + 만들기](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="87318-241">7. ESP 구성 확인</span><span class="sxs-lookup"><span data-stu-id="87318-241">7. Verify the ESP configuration</span></span>

<span data-ttu-id="87318-242">등록 상태 페이지(ESP)는 MDM 관리 사용자가 처음으로 장치에 로그인할 때 실행되는 전체 장치 구성 프로세스의 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-242">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="87318-243">ESP 구성이 다음과 유사한지 확인하고 할당이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-243">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

![ESP 구성](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="87318-245">8. HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="87318-245">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="87318-246">Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-246">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>
1. <span data-ttu-id="87318-247">HoloLens 장치가 나열되어 있고 프로필 상태가 **할당됨**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-247">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  
   > [!NOTE]  
   > <span data-ttu-id="87318-248">프로필이 장치에 할당되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-248">It may take a few minutes for the profile to be assigned to the device.</span></span>  
   
   ![장치 및 프로필 할당](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="87318-250">HoloLens 2용 Windows Autopilot 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="87318-250">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="87318-251">위의 지침이 완료되면 HoloLens 2 사용자는 다음과 같은 환경을 통해 HoloLens 장치를 프로비저닝할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-251">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

> [!NOTE]
> <span data-ttu-id="87318-252">Autopilot를 사용 하면 [장치 소유자](security-adminless-os.md#device-owner)에게 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87318-252">Using Autopilot will have an effect on the [device owner](security-adminless-os.md#device-owner).</span></span>

1. <span data-ttu-id="87318-253">앞서 언급한 바와 같이 현재 릴리스에서는 HoloLens를 켜고 Autopilot 프로비저닝 프로세스를 시작하기 전에 장치를 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-253">As mentioned, in the current release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="87318-254">유선 인터넷 연결을 위한 "이더넷 연결 USB C" 어댑터나 무선 인터넷 연결을 위한 "Wi-Fi 연결 USB C" 어댑터를 사용해 장치를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-254">Connect your device to Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity or "USB-C to Wifi" adapters for wireless internet connectivity.</span></span>
   
   > [!IMPORTANT]  
   > <span data-ttu-id="87318-255">첫 실행 경험(OOBE)이 시작되기 전에 장치를 네트워크에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-255">You must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="87318-256">첫 번째 OOBE 화면에서 장치는 Autopilot 장치로 프로비전 중인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-256">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="87318-257">장치를 네트워크에 연결할 수 없거나 장치를 Autopilot 장치로 프로비전하지 않도록 선택하는 경우 나중에 Autopilot 프로비전으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-257">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="87318-258">대신 장치를 Autopilot 장치로 프로비전하려면 이 절차를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-258">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="87318-259">장치가 자동으로 OOBE를 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87318-259">The device should automatically start OOBE.</span></span> <span data-ttu-id="87318-260">OOBE는 신경쓰지 마세요.</span><span class="sxs-lookup"><span data-stu-id="87318-260">Do not interact with OOBE.</span></span> <span data-ttu-id="87318-261">그 대신 잠시 기다려 주세요.</span><span class="sxs-lookup"><span data-stu-id="87318-261">Instead sit, back and relax!</span></span> <span data-ttu-id="87318-262">HoloLens 2에서 네트워크 연결을 검색하여 OOBE를 자동으로 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-262">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="87318-263">OOBE가 진행되는 동안 장치가 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-263">The device may restart during OOBE.</span></span> <span data-ttu-id="87318-264">OOBE 화면은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-264">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="87318-265">![OOBE 1단계](./images/hololens-ap-uex-1.png)
   ![OOBE 2단계](./images/hololens-ap-uex-2.png)
   ![OOBE 3단계](./images/hololens-ap-uex-3.png)
   ![OOBE 4단계](./images/hololens-ap-uex-4.png)</span><span class="sxs-lookup"><span data-stu-id="87318-265">![OOBE step 1](./images/hololens-ap-uex-1.png)
![OOBE step 2](./images/hololens-ap-uex-2.png)
![OOBE step 3](./images/hololens-ap-uex-3.png)
![OOBE step 4](./images/hololens-ap-uex-4.png)</span></span>

1. <span data-ttu-id="87318-266">OOBE가 끝나면 사용자 이름과 암호를 사용하여 장치에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-266">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

  ![OOBE 5단계](./images/hololens-ap-uex-5.png)

## <span data-ttu-id="87318-268">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="87318-268">Known Issues</span></span>

- <span data-ttu-id="87318-269">장치 보안 컨텍스트를 사용하는 응용 프로그램을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-269">You cannot install applications that use the device security context.</span></span>

## <span data-ttu-id="87318-270">사용자 의견</span><span class="sxs-lookup"><span data-stu-id="87318-270">Feedback</span></span>

<span data-ttu-id="87318-271">피드백을 제공하거나 문제를 신고하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-271">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="87318-272">피드백 허브 앱 사용</span><span class="sxs-lookup"><span data-stu-id="87318-272">Use the Feedback Hub app.</span></span> <span data-ttu-id="87318-273">HoloLens에 연결된 컴퓨터에서 이 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-273">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="87318-274">피드백 허브에서 **엔터프라이즈 관리** > **장치** 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-274">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>  

  <span data-ttu-id="87318-275">피드백을 제공하거나 문제를 신고할 때 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-275">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="87318-276">해당하는 경우 스크린샷 및 로그를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-276">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="87318-277">[hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)으로 전자 메일 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="87318-277">Send an email message to [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com).</span></span> <span data-ttu-id="87318-278">전자 메일 제목으로 **\<*Tenant*> HoloLens 2용 Autopilot 평가 피드백**(여기에서 \<*Tenant*>은(는) 사용자의 Intune 테넌트 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-278">For the email subject, enter **\<*Tenant*> Autopilot for HoloLens 2 evaluation feedback** (where \<*Tenant*> is the name of your Intune tenant).</span></span>

  <span data-ttu-id="87318-279">메시지에 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87318-279">Provide a detailed description in your message.</span></span> <span data-ttu-id="87318-280">그러나 지원 담당자가 특별히 요청하지 않는 한 스크린샷이나 로그와 같은 데이터는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-280">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="87318-281">이러한 데이터에는 개인 또는 개인 식별 정보(PII)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87318-281">Such data might include private or personally identifiable information (PII).</span></span>
