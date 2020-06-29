---
title: HoloLens 2 설정
description: 이 가이드는 처음 설정하는 과정을 안내합니다.  Wi-Fi 네트워크와 Microsoft(MSA) 또는 AAD(Azure Active Directory) 계정이 필요합니다.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8c3d9a10533432b3e8489ffa297c16061abb9eaf
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828973"
---
# <span data-ttu-id="40972-105">HoloLens 2 설정</span><span class="sxs-lookup"><span data-stu-id="40972-105">Set up your HoloLens 2</span></span>

<span data-ttu-id="40972-106">HoloLens를 처음 켜면 장치 설정, 사용자 계정으로 로그인, 눈에 맞춰 HoloLens 보정 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-106">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="40972-107">이 섹션에서는 HoloLens 2 초기 설정 환경에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="40972-107">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="40972-108">다음 섹션에서는 HoloLens와 작업하고 홀로그램과 상호 작용하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="40972-108">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="40972-109">해당 문서 건너뛰려면 [HoloLens 2 시작](hololens2-basic-usage.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40972-109">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <span data-ttu-id="40972-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="40972-110">Before you start</span></span>

<span data-ttu-id="40972-111">시작하려면 먼저 다음 항목이 준비되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-111">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="40972-112">**네트워크 연결**.</span><span class="sxs-lookup"><span data-stu-id="40972-112">**A network connection**.</span></span> <span data-ttu-id="40972-113">설정하려면 HoloLens를 네트워크에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-113">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="40972-114">HoloLens 2를 사용하면 Wi-Fi에 연결하거나 이더넷을 사용하여 연결할 수 있습니다(USB-C-이더넷 어댑터 필요).</span><span class="sxs-lookup"><span data-stu-id="40972-114">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="40972-115">처음 연결할 때 웹 사이트로 이동하거나 인증서를 사용하여 연결할 필요가 없는 열려 있거나 암호로 보호된 네트워크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-115">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="40972-116">[HoloLens에서 사용하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="40972-116">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="40972-117">**Microsoft 계정**.</span><span class="sxs-lookup"><span data-stu-id="40972-117">**A Microsoft account**.</span></span> <span data-ttu-id="40972-118">또한 Microsoft 계정(또는 조직에서 장치를 소유한 경우, 회사 계정)을 사용하여 HoloLens에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-118">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="40972-119">Microsoft 계정이 아직 없으면 [account.microsoft.com](https://account.microsoft.com)으로 이동하여 무료로 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-119">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="40972-120">**넘어질 위험이 없는 안전하고 밝은 공간**.</span><span class="sxs-lookup"><span data-stu-id="40972-120">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="40972-121">[상태 및 보안 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="40972-121">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="40972-122">HoloLens와 함께 제공되어 가장 편안한 착용감을 제공하는 **옵션 편의 액세서리**.</span><span class="sxs-lookup"><span data-stu-id="40972-122">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="40972-123">[핏 및 편안함에 대해 자세히 알아보기](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="40972-123">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <span data-ttu-id="40972-124">Windows 설정</span><span class="sxs-lookup"><span data-stu-id="40972-124">Set up Windows</span></span>

<span data-ttu-id="40972-125">HoloLens 2를 처음 시작할 때 첫 번째 작업은 Windows Holographic을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40972-125">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="40972-126">HoloLens를 시작 하면 음악을 들을 수 있고 Windows 로고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40972-126">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![처음 부팅 중 첫 번째 화면](images/01-magic-moment.png)

<span data-ttu-id="40972-128">HoloLens 2는 다음 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-128">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="40972-129">언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-129">Select your language.</span></span>
    ![언어 선택](images/04-language.png)

1. <span data-ttu-id="40972-131">지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-131">Select your region.</span></span>
    ![지역 선택](images/05-region.png)

1. <span data-ttu-id="40972-133">눈에 맞춰 HoloLens를 보정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-133">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="40972-134">보정을 건너뛰도록 선택하면 다음에 로그인할 때 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="40972-134">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="40972-135">보정하려면 대상의 집합(보석이라고 함)을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-135">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="40972-136">보정을 하는 동안 눈을 깜빡이거나 눈을 감아도 괜찮지만 방에 있는 다른 물체를 응시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-136">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="40972-137">HoloLens는 이 프로세스를 사용하여 홀로그램 세계를 렌더링하기 위해 눈 위치를 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-137">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="40972-138">보정이 완료되면 바이저가 머리 위에서 움직여도 홀로그램이 올바르게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="40972-138">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="40972-139">보정 정보는 장치에 로컬로 저장되며 계정 정보와 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-139">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="40972-140">자세한 내용은 [보정 데이터 및 보안](hololens-calibration.md#calibration-data-and-security)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40972-140">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![보정 선택 화면](images/06-et-corners.png)

1. <span data-ttu-id="40972-142">인터넷에 연결합니다(Wi-Fi 또는 이더넷 연결 선택).</span><span class="sxs-lookup"><span data-stu-id="40972-142">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="40972-143">HoloLens는 Wi-Fi 네트워크에서 얻은 정보에 따라 자동으로 표준 시간대를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-143">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="40972-144">설치가 완료되면 설정 앱을 사용하여 표준 시간대를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-144">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi에 연결](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="40972-146">2019년 10월 이후 OS 버전을 실행하는 경우 Wi-Fi 단계를 완료한 후에도 설치 중에 다른 네트워크로 전환해야 하는 경우에는 **볼륨 작게** 및 **전원** 단추를 동시에 눌러 이 단계로 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-146">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="40972-147">이전 버전의 경우 [디바이스를 초기화](hololens-recovery.md)하거나 Wi-Fi 네트워크를 사용할 수 없는 위치에서 다시 시작하여 자동으로 연결되지 않도록 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-147">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="40972-148">또한 HoloLens 설정 중에 2분의 자격 증명 제한 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-148">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="40972-149">사용자 이름/암호를 2분 이내에 입력해야 합니다. 그렇지 않으면 사용자 이름 필드가 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="40972-149">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="40972-150">사용자 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-150">Sign in to your user account.</span></span> <span data-ttu-id="40972-151">**회사 또는 학교 소유** 또는 **내 소유** 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-151">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="40972-152">**회사 또는 학교 소유**를 선택하면 Azure AD 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-152">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="40972-153">조직에서 Azure AD Premium을 사용하고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="40972-153">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="40972-154">조직에서 Azure AD Premium을 사용 하지 않는 경우 자동 MDM 등록을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-154">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="40972-155">이 경우 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#enroll-through-settings-app)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-155">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#enroll-through-settings-app).</span></span>
        1. <span data-ttu-id="40972-156">조직 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-156">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="40972-157">개인정보처리방침 및 최종 사용자 라이선스 계약에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-157">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="40972-158">Azure AD 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-158">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="40972-159">조직의 로그인 페이지로 다시 이동하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-159">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="40972-160">장치 설정을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-160">Continue setting up the device.</span></span>
    - <span data-ttu-id="40972-161">**내 소유**를 선택하면 Microsoft 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-161">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="40972-162">설정이 완료되면 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#enroll-through-settings-app)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40972-162">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#enroll-through-settings-app).</span></span>
        1. <span data-ttu-id="40972-163">Microsoft 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-163">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="40972-164">암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-164">Enter your password.</span></span> <span data-ttu-id="40972-165">Microsoft 계정에 [2FA(2단계 인증)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)가 필요한 경우 인증 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-165">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![사용자 설정](images/13-device-owner.png)

1. <span data-ttu-id="40972-167">HoloLens 2에서 음성을 사용할지 여부와 진단 원격 분석을 보낼지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-167">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![Cortana 사용](images/22-do-more-with-voice.png)

1. <span data-ttu-id="40972-169">원격 분석 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-169">Select your telemetry level.</span></span> <span data-ttu-id="40972-170">가능한 경우, 전체 원격 분석을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-170">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="40972-171">이 정보는 HoloLens 엔지니어링 팀에게 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="40972-171">This information really helps the HoloLens engineering team.</span></span>
     ![원격 분석 수준](images/24-telemetry.png)

1. <span data-ttu-id="40972-173">HoloLens 2에서 시작 제스처를 사용하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="40972-173">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![시작 제스처를 사용하는 방법 배우기, 이미지 1](images/26-01-startmenu-learning.png) ![시작 제스처를 사용하는 방법 알아보기, 이미지 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="40972-175">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="40972-175">Congratulations!</span></span>  <span data-ttu-id="40972-176">설치가 완료되었으며 HoloLens를 사용할 준비가 되었습니다!</span><span class="sxs-lookup"><span data-stu-id="40972-176">Setup is complete and you're ready to use HoloLens!</span></span>

## <span data-ttu-id="40972-177">다음 단계</span><span class="sxs-lookup"><span data-stu-id="40972-177">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="40972-178">HoloLens 2 시작하기</span><span class="sxs-lookup"><span data-stu-id="40972-178">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
