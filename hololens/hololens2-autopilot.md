---
title: HoloLens2 용 Windows Autopilot(비공개 미리 보기)
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
ms.openlocfilehash: be9da0ec2f301705a0691bcfc9dcf9d75eac8922
ms.sourcegitcommit: cfbcdf562f949eef9cd797bbb08dfdf9f29e8fcd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168545"
---
# <span data-ttu-id="631a2-104">HoloLens용 Windows 자동 실행 2</span><span class="sxs-lookup"><span data-stu-id="631a2-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="631a2-105">Windows Autopilot 프로그램에 HoloLens 2 장치를 설정할 때 사용자는 간단한 프로세스를 따라 클라우드에서 장치를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-105">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="631a2-106">이 Autopilot 프로그램은 Autopilot 자체 배포 모드를 지원하여 테넌트에서 HoloLens 2 장치를 공유 장치로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-106">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="631a2-107">자체 배포 모드는 프로비저닝 프로세스 중에 장치에 사전 설치된 OEM 이미지 및 드라이버를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-107">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="631a2-108">사용자는 장치를 켜고 첫 실행 경험(OOBE)을 거치지 않고 장치를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-108">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span> <span data-ttu-id="631a2-109">Windows 10용 Windows Autopilot에 대해 자세히 알아보려면 [여기](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-109">To learn more about Windows Autopilot for Windows 10 click [here](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

<span data-ttu-id="631a2-110">사용자가 Autopilot 자체 배포 프로세스를 시작하면 프로세스에서 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-110">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="631a2-111">장치를 Azure AD(Azure Active Directory)에 가입시킵니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-111">Join the device to Azure Active Directory (Azure AD).</span></span>

   > [!NOTE]  
   > <span data-ttu-id="631a2-112">HoloLens용 Autopilot은 Active Directory 가입 또는 하이브리드 Azure AD 가입을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-112">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
   
1. <span data-ttu-id="631a2-113">Azure AD를 사용하여 Microsoft Intune(또는 다른 MDM 서비스)에 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-113">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>

1. <span data-ttu-id="631a2-114">장치 대상 정책, 사용자 대상 앱, 인증서, 네트워킹 프로필을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-114">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>

1. <span data-ttu-id="631a2-115">장치를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-115">Provision the device.</span></span>

1. <span data-ttu-id="631a2-116">사용자에게 로그인 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-116">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="631a2-117">HoloLens2 용 Windows Autopilot(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="631a2-117">Windows Autopilot for HoloLens 2 Private Preview</span></span>

<span data-ttu-id="631a2-118">비공개 미리 보기를 위한 환경을 설정하려면 아래 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-118">Please follow the steps below to set up your environment for the private preview:</span></span>

1. <span data-ttu-id="631a2-119">HoloLens 2용 Windows Autopilot 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-119">Make sure that you meet the requirements for Windows Autopilot for HoloLens 2.</span></span>

1. <span data-ttu-id="631a2-120">Windows Autopilot에서 HoloLens 2 전용 미리 보기 프로그램에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-120">Enroll in the Windows Autopilot for HoloLens 2 private preview program.</span></span>

1. <span data-ttu-id="631a2-121">테넌트가 플라이트되었는지(프로그램 참여를 위해 등록되었는지) 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-121">Verify that your tenant is flighted (enrolled to participate in the program).</span></span>

1. <span data-ttu-id="631a2-122">Windows Autopilot에서 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-122">Register your devices in Windows Autopilot.</span></span>

1. <span data-ttu-id="631a2-123">장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="631a2-123">Create a device group.</span></span>

1. <span data-ttu-id="631a2-124">배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="631a2-124">Create a deployment profile.</span></span>

1. <span data-ttu-id="631a2-125">ESP 구성 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-125">Verify the ESP configuration.</span></span>

1. <span data-ttu-id="631a2-126">HoloLens 장치에 대한 사용자 지정 구성 프로필 구성(알려진 문제)</span><span class="sxs-lookup"><span data-stu-id="631a2-126">Configure a custom configuration profile for HoloLens devices (known issue).</span></span>

1. <span data-ttu-id="631a2-127">HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-127">Verify the profile status of the HoloLens devices.</span></span>


### <span data-ttu-id="631a2-128">1. HoloLens2용 Windows Autopilot의 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-128">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="631a2-129">Windows Autopilot 요구 사항 문서의 다음 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-129">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="631a2-130">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="631a2-130">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="631a2-131">라이선싱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="631a2-131">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="631a2-132">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="631a2-132">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**<span data-ttu-id="631a2-133">Windows Autopilot 자체 배포 모드 문서의 "[요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" 섹션을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-133">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="631a2-134">사용자 환경은 표준 Windows Autopilot 요구 사항뿐만 아니라 이러한 요구 사항도 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-134">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="631a2-135">문서의 "단계별 안내” 및 "유효성 검사" 섹션은 검토할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-135">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="631a2-136">이 문서의 뒷부분에 나오는 절차는 HoloLens에 특정하여 해당되는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-136">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="631a2-137">장치를 등록하고 프로필을 구성하는 방법에 대한 자세한 내용은 이 문서의 [4. Windows Autopilot에서 장치 등록](#4-register-devices-in-windows-autopilot) 및 [6. 배포 프로필 만들기](#6-create-a-deployment-profile)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-137">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="631a2-138">이 섹션에서는 HoloLens에 특정된 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-138">These sections provide steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="631a2-139">HoloLens 2용 Windows 자동 실행에는 특정 운영 체제 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-139">Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span> <span data-ttu-id="631a2-140">오토파일럿은 HoloLens 장치에 사전 설치된 Windows 홀로그래픽 버전 2004(빌드 19041.1103 이상)에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-140">Autopilot relies on Windows Holographic, version 2004 (build 19041.1103 or later) being pre-installed on HoloLens devices.</span></span> <span data-ttu-id="631a2-141">2020년 9월 말까지 제공되는 장치에는 Windows Holographic 버전 1903이 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-141">Devices delivered until late September 2020 have Windows Holographic, version 1903 pre-installed.</span></span> <span data-ttu-id="631a2-142">Autopilot 지원 장치 배송 기간은 대리점에 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-142">Please contact your distributor to learn about when Autopilot-ready devices can be shipped to you.</span></span> <span data-ttu-id="631a2-143">비공개 미리 보기에 참여하려면 아래 지침 및 요구 사항을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-143">If you wish to participate to the private preview, please review instructions and requirements below.</span></span>

<span data-ttu-id="631a2-144">HoloLens OS 릴리스당 Autopilot 특정 정보</span><span class="sxs-lookup"><span data-stu-id="631a2-144">Autopilot specific information per HoloLens OS releases.</span></span>
- <span data-ttu-id="631a2-145">Autopilot를 사용하려면 장치에 [Windows Holographic, 버전 2004](hololens-release-notes.md#windows-holographic-version-2004) 릴리스 이상이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-145">In order to use Autopilot a device must have the [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) release or newer.</span></span>

- <span data-ttu-id="631a2-146">Wi-Fi를 사용하여 Autopilot를 사용하려면 장치에 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 릴리스 이상이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-146">In order to use Autopilot by use of Wi-Fi a device must have the [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) release or newer.</span></span> <span data-ttu-id="631a2-147">그러나 이러한 빌드는 여전히 이더넷 어댑터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-147">However these builds may still use ethernet adapters.</span></span> 

- <span data-ttu-id="631a2-148">빌드 [Windows Holographic의 경우 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 에서 새 장치 관리 옵션 [tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-148">On builds [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) a new device management option [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) has been enabled.</span></span>  

<span data-ttu-id="631a2-149">장치에서 빌드 버전을 확인하거나 업데이트하려면 Windows 10 PC에 연결하고 [고급 복구 도우미](https://www.microsoft.com/store/productId/9P74Z35SFRS8)를 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-149">If you would like to either confirm the build version on your device or update it, please connect it to your Windows 10 PC and launch [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> 

**<span data-ttu-id="631a2-150">Autopilot 미리 보기를 시도하려면 OOBE 및 프로비저닝 프로세스를 시작하기 전에 HoloLens 장치가 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-150">If you wish to try the Autopilot preview, before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>**

- <span data-ttu-id="631a2-151">장치가 Windows 홀로그래픽 버전 2004에 있는지 확인합니다(빌드 19041.1103 이상).</span><span class="sxs-lookup"><span data-stu-id="631a2-151">Ensure your device is on Windows Holographic, version 2004 (build 19041.1103 or later).</span></span> <span data-ttu-id="631a2-152">최신 OS가 미리 설치되어 있지 않으면 [ARC(Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)을(를) 사용하여 수동으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-152">If the latest OS is not pre-installed you must manually update using the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="631a2-153">[여기](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)에서 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-153">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> 

- <span data-ttu-id="631a2-154">Windows Autopilot에서 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-154">Your devices must be registered in Windows Autopilot.</span></span> <span data-ttu-id="631a2-155">장치를 등록하는 방법에 대한 자세한 내용은 [4. Windows Autopilot에서 장치 등록](#4-register-devices-in-windows-autopilot)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-155">For information about how to register devices see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot).</span></span> <span data-ttu-id="631a2-156">권장 경로는 대리점 또는 대리점이 사용자를 위해 장치를 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-156">The recommended path is for your reseller or distributor to register devices for you.</span></span>  

- <span data-ttu-id="631a2-157">[Windows Holographic 버전 2004](hololens-release-notes.md#windows-holographic-version-2004) 릴리스에서는 HoloLens를 켜고 Autopilot 프로비저닝 프로세스를 시작하기 전에 장치가 인터넷에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-157">In the [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="631a2-158">유선 인터넷 연결의 "USB-C에서 이더넷" 어댑터를 사용하여 장치를 이더넷에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-158">Connect your device to Ethernet using a "USB-C to Ethernet" adapter for wired internet connectivity.</span></span>

- <span data-ttu-id="631a2-159">[Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 릴리스의 장치는 OOBE에서 Wi-Fi에 연결하여 Autopilot을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-159">In the [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) release, devices may connect to Wi-Fi in OOBE to detect Autopilot.</span></span> 

- <span data-ttu-id="631a2-160">장치가 아직 Azure AD에 속하지 않으며 Intune(또는 다른 MDM 시스템)에 등록되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-160">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="631a2-161">Autopilot 자체 배포 프로세스가 이러한 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-161">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="631a2-162">모든 장치 관련 정보를 정리하려면 Azure AD 및 Intune 포털 모두에서 **장치** 페이지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-162">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span>

- <span data-ttu-id="631a2-163">Autopilot 자체 배포 모드 프로필을 구성하고 관리하려면 [Microsoft 엔드포인트 관리자 관리 센터](https://endpoint.microsoft.com)에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-163">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>


### <span data-ttu-id="631a2-164">2. HoloLens 2용 Windows Autopilot 프로그램 등록</span><span class="sxs-lookup"><span data-stu-id="631a2-164">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

**<span data-ttu-id="631a2-165">프로그램에 참여하려면 테넌트가 개인 미리보기 프로그램에 등록되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-165">To participate in the program, you must have your tenant enrolled to the Private Preview program.</span></span> <span data-ttu-id="631a2-166">이렇게 하면 자동 조종에 대한 HoloLens별 Intune(MEM) UI 컨트롤이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-166">This enables HoloLens-specific Intune (aka MEM) UI controls for Autopilot.</span></span>** <span data-ttu-id="631a2-167">이렇게 하려면 [HoloLens용 Windows Autopilot 비공개 미리 보기 요청](https://aka.ms/APHoloLensTAP)으로 이동하거나 다음 QR 코드를 사용하여 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-167">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR 코드](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="631a2-169">Microsoft는 일주일에 한 번 테넌트를 비행합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-169">Microsoft flights tenants once a week.</span></span> <span data-ttu-id="631a2-170">비행이 완료되면 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-170">You will receive an email notification once the flighting is complete.</span></span> 

<span data-ttu-id="631a2-171">이 요청에서 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-171">In this request, provide the following information:</span></span>

- <span data-ttu-id="631a2-172">테넌트 도메인</span><span class="sxs-lookup"><span data-stu-id="631a2-172">Tenant domain</span></span>
- <span data-ttu-id="631a2-173">테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="631a2-173">Tenant ID</span></span>
- <span data-ttu-id="631a2-174">이 평가에 참여하는 HoloLens 2 장치 수</span><span class="sxs-lookup"><span data-stu-id="631a2-174">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="631a2-175">Autopilot 자체 배포 모드를 사용하여 배포할 HoloLens 2 장치 수</span><span class="sxs-lookup"><span data-stu-id="631a2-175">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="631a2-176">3. 테넌트가 플라이트 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-176">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="631a2-177">요청을 제출한 후 테넌트가 Autopilot 프로그램에서 플라이트 중인지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-177">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="631a2-178">[Microsoft 엔드포인트 관리자 관리 센터](https://endpoint.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-178">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

1. <span data-ttu-id="631a2-179">**장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-179">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![프로필 만들기 드롭다운에는 HoloLens 항목이 포함됩니다.](./images/hololens-ap-enrollment-profiles.png)
   
   <span data-ttu-id="631a2-181">**HoloLens**를 포함하는 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-181">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="631a2-182">이 옵션이 표시되지 않는 경우 [피드백](hololens2-autopilot.md#feedback-for-autopilot) 옵션 중 하나를 사용하여 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-182">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-for-autopilot) options to contact us.</span></span>

### <span data-ttu-id="631a2-183">4. Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="631a2-183">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="631a2-184">준비 단계에서는 Windows Autopilot에 장치를 등록할 수 있는 두 가지 기본 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-184">In the preparation phase, there are two primary ways you can register devices to Windows Autopilot:</span></span> 

1. <span data-ttu-id="631a2-185">**디바이스를 등록하기 위해서는 배포자 또는 대리점에 문의합니다**.</span><span class="sxs-lookup"><span data-stu-id="631a2-185">**Contact your distributor or reseller when you place an order to have your devices registered**.</span></span>

   <span data-ttu-id="631a2-186">또는</span><span class="sxs-lookup"><span data-stu-id="631a2-186">or</span></span>
   
2. <span data-ttu-id="631a2-187">**하드웨어 해시(하드웨어 ID 라고도 함)를 검색하고 수동으로 장치를 등록합니다**.</span><span class="sxs-lookup"><span data-stu-id="631a2-187">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually**.</span></span> 

<span data-ttu-id="631a2-188">장치 등록에 대한 자세한 내용은 [Autopilot에 장치 추가](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) 설명서를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-188">For more information on device registration please review the [Adding devices to Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) documentation.</span></span>  

**<span data-ttu-id="631a2-189">장치 하드웨어 해시 검색</span><span class="sxs-lookup"><span data-stu-id="631a2-189">Retrieve a device hardware hash</span></span>**

<span data-ttu-id="631a2-190">장치는 OOBE 프로세스가 진행되는 동안 또는 나중에 장치 소유자가 진단 로그 수집 프로세스(다음 절차에 설명)를 시작할 때 CSV 파일에서 하드웨어 해시를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-190">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="631a2-191">일반적으로 장치 소유자는 처음에 장치에 로그인하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-191">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="631a2-192">HoloLens 2 장치 시작</span><span class="sxs-lookup"><span data-stu-id="631a2-192">Start the HoloLens 2 device.</span></span>

1. <span data-ttu-id="631a2-193">장치에서 전원 및 볼륨 작게 단추를 동시에 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-193">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="631a2-194">장치에서 진단 로그와 하드웨어 해시를 수집하여 .zip 파일 집합에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-194">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span> 

   1. <span data-ttu-id="631a2-195">이 기능을 수행하는 방법에 대한 자세한 내용과 교육 비디오를 보려면 [오프라인 진단](hololens-diagnostic-logs.md#offline-diagnostics)정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-195">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> 
   
1. <span data-ttu-id="631a2-196">USB-C 케이블을 사용하여 장치를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-196">Use a USB-C cable to connect the device to a computer.</span></span>

1. <span data-ttu-id="631a2-197">컴퓨터에서 파일 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-197">On the computer, open File Explorer.</span></span> <span data-ttu-id="631a2-198">**내 PC\\\<*HoloLens device name*>\\내부 저장소\\문서**를 열고, AutopilotDiagnostics.zip 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-198">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="631a2-199">.zip 파일을 즉시 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-199">The .zip file may not immediately be available.</span></span> <span data-ttu-id="631a2-200">파일이 아직 준비되지 않은 경우 문서 폴더에 HoloLensDiagnostics.temp 파일이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-200">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="631a2-201">파일 목록을 업데이트하려면 창을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-201">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="631a2-202">AutopilotDiagnostics.zip 파일의 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-202">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

1. <span data-ttu-id="631a2-203">추출된 파일에서 파일 이름 접두사가 "DeviceHash"인 CSV 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-203">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="631a2-204">해당 파일을 컴퓨터의 드라이브에 복사하여 나중에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-204">Copy that file to a drive on the computer where you can access it later.</span></span>  

   > [!IMPORTANT]  
   > <span data-ttu-id="631a2-205">CSV 파일의 데이터는 다음 헤더 및 줄 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-205">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="631a2-206">Windows Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="631a2-206">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="631a2-207">Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록**을 선택한 다음 **Windows Autopilot 배포 프로그램**아래에서 **장치** > **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-207">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="631a2-208">**Windows Autopilot 장치 추가** 아래에서 DeviceHash CSV 파일을 선택하고 **열기**를 선택한 다음 **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-208">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![가져오기 명령을 사용하여 하드웨어 해시를 가져옵니다.](./images/hololens-ap-hash-import.png)
   
1. <span data-ttu-id="631a2-210">가져오기가 완료되면 **장치** > **Windows** > **Windows 등록** > **장치** > **동기화**를 선택합니다. 동기화되는 장치 수에 따라 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-210">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="631a2-211">등록된 장치를 보려면 **새로 고침**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-211">To see the registered device, select **Refresh**.</span></span>  
   
   ![동기화 및 새로 고침 명령을 사용하여 장치 목록을 표시합니다.](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="631a2-213">5. 장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="631a2-213">5. Create a device group</span></span>

1. <span data-ttu-id="631a2-214">Microsoft 엔드포인트 관리자 관리 센터에서 **그룹** > **새 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-214">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="631a2-215">**그룹 유형**에 대해 **보안**을 선택한 다음 그룹 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-215">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="631a2-216">**구성원 자격 유형**에 대해 **할당됨** 또는 **동적 장치**중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-216">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="631a2-217">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-217">Do one of the following:</span></span>  
   
   - <span data-ttu-id="631a2-218">이전 단계에서 **구성원 자격 유형**에 대해 **할당됨**을 선택한 경우 **구성원**을 선택한 다음 그룹에 Autopilot 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-218">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="631a2-219">아직 등록되지 않은 Autopilot 장치는 장치 일련 번호를 장치 이름으로 사용하여 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-219">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="631a2-220">이전 단계에서 **구성원 자격 유형**에 대해 **구성원 자격 유형**을 선택한 경우 **동적 장치 구성원**을 선택한 다음 다음과 유사한 **고급 규칙**에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-220">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="631a2-221">모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-221">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="631a2-222">Intune의 그룹 태그 필드는 Azure AD 장치의 **OrderID** 특성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-222">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="631a2-223">특정 그룹 태그(Azure AD 장치 OrderID)가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-223">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="631a2-224">특정 구매 주문 ID가 있는 모든 Autopilot 장치를 포함하는 그룹을 만들려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-224">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="631a2-225">이러한 규칙은 Autopilot 장치에 고유한 특성을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-225">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="631a2-226">**확인**을 선택하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-226">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="631a2-227">6. 배포 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="631a2-227">6. Create a deployment profile</span></span>

1. <span data-ttu-id="631a2-228">Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **Windows Autopilot 배포 프로필** > **프로필 만들기** > **HoloLens**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-228">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="631a2-229">프로필 이름과 설명을 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-229">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![프로필 이름 및 설명 추가](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="631a2-231">**첫 실행 경험(OOBE)** 페이지에서 대부분의 설정이 이 평가에 대한 OOBE를 간소화하도록 사전 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-231">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="631a2-232">선택적으로 구성할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-232">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="631a2-233">**언어(지역)**: OOBE의 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-233">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="631a2-234">[HoloLens 2에 지원되는 언어](hololens2-language-support.md) 목록에서 언어를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-234">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="631a2-235">**키보드 자동 구성**: 키보드가 선택한 언어와 일치하도록 하려면 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-235">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="631a2-236">**장치 이름 템플릿 적용**: OOBE 중에 장치 이름을 자동으로 설정하려면 **예**를 선택한 다음 템플릿 문구 및 자리 표시자를 **이름 입력**에 입력합니다. 예를 들어, 접두어와 4 자리 난수의 `%RAND:4%`&mdash;자리 표시자를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-236">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="631a2-237">장치 이름 템플릿을 사용하는 경우 OOBE 프로세스는 장치 이름을 적용한 후 장치를 Azure AD에 가입시키기 전에 한 번 더 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-237">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="631a2-238">다시 시작하면 새 이름이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-238">This restart enables the new name to take effect.</span></span>  

   ![OOBE 설정 구성](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="631a2-240">설정을 구성한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-240">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="631a2-241">**범위 태그** 페이지에서 이 프로필에 적용하려는 범위 태그를 선택적으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-241">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="631a2-242">범위 태그에 대한 자세한 내용은 [분산 IT에 역할 기반 액세스 제어 및 범위 태그 사용](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-242">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="631a2-243">작업이 완료되면 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-243">When finished, select **Next**.</span></span>
1. <span data-ttu-id="631a2-244">**할당** 페이지에서 **할당 대상**으로 **선택된 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-244">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="631a2-245">**선택된 그룹**에서 **+ 포함할 그룹 선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-245">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="631a2-246">**포함할 그룹 선택** 목록에서 Autopilot HoloLens 장치에 대해 생성한 장치 그룹을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-246">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="631a2-247">그룹을 제외하려면 **제외할 그룹 선택**을 선택하고 제외하려는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-247">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![장치 그룹을 프로필에 할당합니다.](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. <span data-ttu-id="631a2-249">**검토 + 만들기** 페이지에서 설정을 검토한 후 **만들기**를 선택하여 프로필을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-249">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![검토 + 만들기](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="631a2-251">7. ESP 구성 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-251">7. Verify the ESP configuration</span></span>

<span data-ttu-id="631a2-252">등록 상태 페이지(ESP)는 MDM 관리 사용자가 처음으로 장치에 로그인할 때 실행되는 전체 장치 구성 프로세스의 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-252">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="631a2-253">ESP 구성이 다음과 유사한지 확인하고 할당이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-253">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> ![ESP 구성](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="631a2-255">8. HoloLens 장치의 프로필 상태 확인</span><span class="sxs-lookup"><span data-stu-id="631a2-255">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="631a2-256">Microsoft 엔드포인트 관리자 관리 센터에서 **장치** > **Windows** > **Windows 등록** > **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-256">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="631a2-257">HoloLens 장치가 나열되어 있고 프로필 상태가 **할당됨**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-257">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="631a2-258">프로필이 장치에 할당되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-258">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]   
   > ![장치 및 프로필 할당](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="631a2-260">HoloLens 2용 Windows Autopilot 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="631a2-260">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="631a2-261">위의 지침이 완료되면 HoloLens 2 사용자는 다음과 같은 환경을 통해 HoloLens 장치를 프로비저닝할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-261">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="631a2-262">Autopilot 환경에는 인터넷 액세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-262">Autopilot experience requires internet access.</span></span> <span data-ttu-id="631a2-263">다음 옵션 중 하나를 사용하여 인터넷 액세스를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-263">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="631a2-264">OOBE의 Wi-Fi 네트워크에 장치를 연결한 다음 자동으로 Autopilot 환경을 감지하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-264">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="631a2-265">이는 Autopilot 경험이 자체적으로 완료될 때까지 OOBE와 상호 작용해야 할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-265">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="631a2-266">기본적으로 HoloLens 2는 인터넷 검색 후 Autopilot를 감지하기 위해 10초 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-266">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="631a2-267">10초 내에 autopilot 프로필이 검색되지 않으면 OOBE에 EULA가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-267">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="631a2-268">이 문제가 발생하는 경우 장치를 다시 부팅하여 다시 Autopilot를 검색해 보세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-268">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="631a2-269">또한 Autopilot에는 TenantLockdown 정책이 장치에 설정된 경우에만 OOBE가 무한정 대기할 수 있다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-269">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>
    
    - <span data-ttu-id="631a2-270">유선 인터넷 연결에 "USB-C to Ethernet" 어댑터를 사용하여 디바이스를 이더넷에 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-270">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>
    
    - <span data-ttu-id="631a2-271">무선 인터넷 연결을 위한 "USB-C to Wifi" 어댑터를 사용하여 장치를 연결하고 HoloLens 2 완전 Autopilot 환경을 자동으로 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-271">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

       > [!NOTE]
       > <span data-ttu-id="631a2-272">Autopilot를 사용 하면 [장치 소유자](security-adminless-os.md#device-owner)에게 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-272">Using Autopilot will have an effect on the [device owner](security-adminless-os.md#device-owner).</span></span>
   
       > [!IMPORTANT]  
       > <span data-ttu-id="631a2-273">Autopilot 용 OOBE에서 Wi-Fi 네트워크를 사용 하려고 하는 장치 [는 Windows Holographic, Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-273">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="631a2-274">이더넷 어댑터를 사용하는 디바이스의 경우 OOBE(사용자 환경)가 시작되기 전에 디바이스를 네트워크에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-274">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="631a2-275">첫 번째 OOBE 화면에서 장치는 Autopilot 장치로 프로비전 중인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-275">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="631a2-276">장치를 네트워크에 연결할 수 없거나 장치를 Autopilot 장치로 프로비전하지 않도록 선택하는 경우 나중에 Autopilot 프로비전으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-276">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="631a2-277">대신 장치를 Autopilot 장치로 프로비전하려면 이 절차를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-277">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="631a2-278">장치가 자동으로 OOBE를 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-278">The device should automatically start OOBE.</span></span> <span data-ttu-id="631a2-279">OOBE는 신경쓰지 마세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-279">Do not interact with OOBE.</span></span> <span data-ttu-id="631a2-280">그 대신 잠시 기다려 주세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-280">Instead sit, back and relax!</span></span> <span data-ttu-id="631a2-281">HoloLens 2에서 네트워크 연결을 검색하여 OOBE를 자동으로 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-281">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="631a2-282">OOBE가 진행되는 동안 장치가 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-282">The device may restart during OOBE.</span></span> <span data-ttu-id="631a2-283">OOBE 화면은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-283">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="631a2-284">![OOBE 단계 1](./images/autopilot-welcome.jpg)
   ![OOBE 단계 2](./images/autopilot-step-complete.jpg)
   ![OOBE 단계 3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="631a2-284">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="631a2-285">OOBE가 끝나면 사용자 이름과 암호를 사용하여 장치에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-285">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" width="450" height="700" />

## <span data-ttu-id="631a2-286">Tenantlockdown CSP 및 Autopilot</span><span class="sxs-lookup"><span data-stu-id="631a2-286">Tenantlockdown CSP and Autopilot</span></span>
- <span data-ttu-id="631a2-287">장치 재설정이나 reflash를 통해 장치를 테넌트로 잠가 조직의 테넌트에 디바이스를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-287">Keeps devices on the organization's tenant by locking them to the tenant even through device reset or reflash.</span></span> <span data-ttu-id="631a2-288">프로비저닝을 통해 계정 생성을 허용하지 않도록 하여 추가 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-288">With further security by disallowing account creation in via provisioning.</span></span> 

<span data-ttu-id="631a2-289">HoloLens 2 장치는 이제 Windows Holographic 버전 20H2로 TenantLockdown CSP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-289">HoloLens 2 devices now support TenantLockdown CSP as of Windows Holographic version 20H2.</span></span> 

<span data-ttu-id="631a2-290">[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용하여 HoloLens 2를 MDM 등록에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-290">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="631a2-291">TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false (초기 설정) 값으로 설정되고, 다시 깜박이는 경우, OS 업데이트 등의 장치에도 해당 값이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-291">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span> 

<span data-ttu-id="631a2-292">HoloLens 2에서 TenantLockdown Csp의 RequireNetworkInOOBE 노드가 true로 설정되면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드되고 적용될 때까지 무기한 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-292">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span> 

<span data-ttu-id="631a2-293">RequireNetworkInOOBE는 HoloLens 2에서 TenantLockdown Csp의 a 노드가 true로 설정되 면 OOBE에서 다음 작업을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-293">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span> 
- <span data-ttu-id="631a2-294">런타임 프로비저닝을 사용하여 로컬 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="631a2-294">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="631a2-295">런타임 프로비저닝을 통해 AAD 참여 작업 수행</span><span class="sxs-lookup"><span data-stu-id="631a2-295">Performing AAD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="631a2-296">OOBE 환경에서 장치를 소유하는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="631a2-296">Selecting who owns the device in OOBE experience</span></span> 

### <span data-ttu-id="631a2-297">Intune을 사용하여 설정하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="631a2-297">How to set this using Intune?</span></span> 
1. <span data-ttu-id="631a2-298">사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-298">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="631a2-299">OMA URI 값은/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-299">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 tennant 잠금 설정](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="631a2-301">그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-301">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="631a2-302">이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-302">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="631a2-303">장치 구성이 성공적으로 적용되었는지 Intune 포털에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-303">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="631a2-304">이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-304">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

### <span data-ttu-id="631a2-305">Intune을 사용하여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제하는 방법</span><span class="sxs-lookup"><span data-stu-id="631a2-305">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span> 
1. <span data-ttu-id="631a2-306">위에서 만든 장치 구성이 이전에 할당된 장치 그룹에서 HoloLens 2를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-306">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span> 

1. <span data-ttu-id="631a2-307">사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE에 대해 false를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-307">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span> <span data-ttu-id="631a2-308">OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-308">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="631a2-310">그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-310">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="631a2-311">이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-311">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="631a2-312">장치 구성이 성공적으로 적용되었는지 Intune 포털에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-312">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="631a2-313">이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-313">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span> 

### <span data-ttu-id="631a2-314">TenantLockdown true로 설정된 후 HoloLens에서 Autopilot 프로필이 할당되지 않은 경우 OOBE 중에 무슨 문제가 발생하나요?</span><span class="sxs-lookup"><span data-stu-id="631a2-314">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="631a2-315">OOBE는 Autopilot 프로필이 다운로드될 때까지 무기한 대기하고 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-315">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="631a2-316">TenantLockdown 효과를 제거하려면 장치를 원래 테넌트만 사용하여 먼저 등록해야 하며, 이전 단계에서 설명한 대로 Autopilot를 설정하지 않아야 합니다. TenantLockdown CSP에서 도입된 제한이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-316">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span> 

![장치에서 정책이 적용되는 시기에 대한 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="631a2-318">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="631a2-318">Known Issues</span></span>

- <span data-ttu-id="631a2-319">Intune에서 구성된 디바이스 컨텍스트 기반 응용 프로그램 설치가 아직 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-319">Device context based application install configured in Intune does not work yet.</span></span>
- <span data-ttu-id="631a2-320">Wi-Fi를 통해 Autopilot를 설정하는 동안 인터넷 연결이 처음 설정 되고 최종 사용자 사용권 계약(EULA)이 표시되고 사용자가 비 Autopilot 설치 환경을 진행할 수 있는 옵션이 있는 경우 Autopilot 프로필이 다운로드되지 않는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-320">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established and the End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experiences.</span></span> <span data-ttu-id="631a2-321">Autopilot를 사용하여 설정을 다시 시도하려면, 장치를 절전 모드로 전환한 다음 전원을 켜고 장치를 재부팅하여 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-321">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>

### <span data-ttu-id="631a2-322">문제 해결</span><span class="sxs-lookup"><span data-stu-id="631a2-322">Troubleshooting</span></span>

<span data-ttu-id="631a2-323">다음 문서는 자세한 정보를 알아보고 Autopilot 문제를 해결 하는 데 유용한 리소스가 될 수 있지만, 이러한 문서는 Windows 10 데스크톱을 기반으로 하며 모든 정보가 HoloLens에 적용되는 것이 아니라는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-323">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>
- [<span data-ttu-id="631a2-324">Windows Autopilot - 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="631a2-324">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="631a2-325">Microsoft Intune에서 Windows 장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="631a2-325">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="631a2-326">Windows Autopilot - 정책 충돌</span><span class="sxs-lookup"><span data-stu-id="631a2-326">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <span data-ttu-id="631a2-327">Autopilot에 대한 피드백</span><span class="sxs-lookup"><span data-stu-id="631a2-327">Feedback for Autopilot</span></span>

<span data-ttu-id="631a2-328">피드백을 제공하거나 문제를 신고하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-328">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="631a2-329">피드백 허브 앱 사용</span><span class="sxs-lookup"><span data-stu-id="631a2-329">Use the Feedback Hub app.</span></span> <span data-ttu-id="631a2-330">HoloLens에 연결된 컴퓨터에서 이 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-330">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="631a2-331">피드백 허브에서 **엔터프라이즈 관리** > **장치** 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-331">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span> <span data-ttu-id="631a2-332">피드백을 제공하거나 문제를 신고할 때 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-332">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="631a2-333">해당하는 경우 스크린샷 및 로그를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-333">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="631a2-334">디바이스를 등록 하는 동안 Intune에서 문제가 발생하거나 Autopilot 프로필이 할당되지 않은 경우 [https://aka.ms/apsupport](https://aka.ms/apsupport)에서 지원 티켓을 여세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-334">If you encounter issues in Intune during registration of device or Autopilot profile not getting assigned, please open a support ticket at [https://aka.ms/apsupport](https://aka.ms/apsupport) .</span></span>
- <span data-ttu-id="631a2-335">Autopilot 환경에서 HoloLens 장치에 문제가 발생하는 경우 [https://aka.ms/hlsupport](https://aka.ms/hlsupport)에서 [오프라인 진단 로그](hololens-diagnostic-logs.md#offline-diagnostics)를 사용하여 지원 티켓을 여세요.</span><span class="sxs-lookup"><span data-stu-id="631a2-335">If you encounter issues on HoloLens device during the Autopilot experience, please open a support ticket at [https://aka.ms/hlsupport](https://aka.ms/hlsupport) with [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

  <span data-ttu-id="631a2-336">메시지에 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-336">Provide a detailed description in your message.</span></span> <span data-ttu-id="631a2-337">그러나 지원 담당자가 특별히 요청하지 않는 한 스크린샷이나 로그와 같은 데이터는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-337">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="631a2-338">이러한 데이터에는 개인 또는 개인 식별 정보(PII)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631a2-338">Such data might include private or personally identifiable information (PII).</span></span>
