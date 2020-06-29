---
title: HoloLens(1세대) 설정
description: 이 가이드는 처음 설정하는 과정을 안내합니다.  Wi-Fi 네트워크와 Microsoft(MSA) 또는 Azure AD(Azure Active Directory) 계정이 필요합니다.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 042856de2b89395fa0168d90515a7700298087f1
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829467"
---
# <span data-ttu-id="99b7e-104">HoloLens(1세대) 설정</span><span class="sxs-lookup"><span data-stu-id="99b7e-104">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="99b7e-105">HoloLens를 처음 켜면 장치 보정, 장치 설정 및 로그인 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-105">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="99b7e-106">이 문서는 HoloLens(1세대)의 첫 번째 시작 및 설정 환경에 대해 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-106">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="99b7e-107">다음 섹션에서는 HoloLens와 작업하고 홀로그램과 상호 작용하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="99b7e-108">해당 문서를 건너뛰려면 [HoloLens(1세대) 시작](hololens1-basic-usage.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99b7e-108">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <span data-ttu-id="99b7e-109">시작하기 전 확인 사항</span><span class="sxs-lookup"><span data-stu-id="99b7e-109">Before you start</span></span>

<span data-ttu-id="99b7e-110">시작하려면 먼저 다음 항목이 준비되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="99b7e-111">**Wi-Fi 연결**.</span><span class="sxs-lookup"><span data-stu-id="99b7e-111">**A Wi-Fi connection**.</span></span> <span data-ttu-id="99b7e-112">Wi-Fi 네트워크를 설정하려면 HoloLens를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-112">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="99b7e-113">처음 연결할 때 웹 사이트로 이동하거나 인증서를 사용하여 연결할 필요가 없는 열려 있거나 암호로 보호된 네트워크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-113">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="99b7e-114">[HoloLens에서 사용하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="99b7e-114">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="99b7e-115">**Microsoft 계정 또는 회사 계정**</span><span class="sxs-lookup"><span data-stu-id="99b7e-115">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="99b7e-116">또한 Microsoft 계정(또는 조직에서 장치를 소유한 경우, 회사 계정)을 사용하여 HoloLens에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-116">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="99b7e-117">Microsoft 계정이 아직 없으면 [account.microsoft.com](https://account.microsoft.com)으로 이동하여 무료로 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-117">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="99b7e-118">**넘어질 위험이 없는 안전하고 밝은 공간**.</span><span class="sxs-lookup"><span data-stu-id="99b7e-118">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="99b7e-119">[상태 및 보안 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="99b7e-119">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="99b7e-120">HoloLens와 함께 제공되어 가장 편안한 착용감을 제공하는 **옵션 편의 액세서리**.</span><span class="sxs-lookup"><span data-stu-id="99b7e-120">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="99b7e-121">[핏 및 편안함에 대해 자세히 알아보기](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span><span class="sxs-lookup"><span data-stu-id="99b7e-121">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="99b7e-122">HoloLens를 처음 사용하는 경우 [Cortana](hololens-cortana.md)는 이미 켜져 있으며 안내할 준비가 되어 있습니다(단, 장치를 설정한 후에야 질문에 응답할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="99b7e-122">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="99b7e-123">사용자는 언제라도 Cortana 설정에서 Cortana 기능을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-123">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="99b7e-124">중국어 또는 일본어 버전의 HoloLens로 전환하려면 PC에서 언어 빌드를 다운로드한 다음 HoloLens에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-124">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="99b7e-125">자세한 내용은 [지역화된 버전의 HoloLens(1세대) 설치](hololens1-install-localized.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99b7e-125">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <span data-ttu-id="99b7e-126">HoloLens 시작 및 Windows 설정</span><span class="sxs-lookup"><span data-stu-id="99b7e-126">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="99b7e-127">HoloLens를 처음 시작할 때 첫 번째 작업은 장치에 Windows Holographic을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-127">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="99b7e-128">인터넷에 연결합니다(HoloLens에서는 Wi-Fi 네트워크를 선택하도록 안내합니다).</span><span class="sxs-lookup"><span data-stu-id="99b7e-128">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="99b7e-129">사용자 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-129">Sign in to your user account.</span></span> <span data-ttu-id="99b7e-130">**회사 또는 학교 소유** 또는 **내 소유** 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-130">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="99b7e-131">**회사 또는 학교 소유**를 선택하면 Azure AD 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-131">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="99b7e-132">조직에서 Azure AD Premium을 사용하고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-132">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="99b7e-133">조직에서 Azure AD Premium을 사용하지 않는 경우에는 자동 MDM 등록을 사용할 수 없으므로 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#enroll-through-settings-app)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-133">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#enroll-through-settings-app).</span></span> <span data-ttu-id="99b7e-134">회사 또는 학교 계정을 사용하여 처음으로 장치에 로그인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-134">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="99b7e-135">조직 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-135">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="99b7e-136">개인정보처리방침에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-136">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="99b7e-137">Azure AD 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-137">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="99b7e-138">조직의 로그인 페이지로 다시 이동하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-138">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="99b7e-139">장치 설정을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-139">Continue setting up the device.</span></span>
    - <span data-ttu-id="99b7e-140">**내 소유**를 선택하면 Microsoft 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-140">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="99b7e-141">설정이 완료되면 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#enroll-through-settings-app)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-141">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#enroll-through-settings-app).</span></span>
        1. <span data-ttu-id="99b7e-142">Microsoft 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-142">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="99b7e-143">암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-143">Enter your password.</span></span> <span data-ttu-id="99b7e-144">Microsoft 계정에 [2FA(2단계 인증)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)가 필요한 경우 인증 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-144">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="99b7e-145">장치는 Wi-Fi 네트워크에서 가져오는 정보에 따라 표준 시간대를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-145">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <span data-ttu-id="99b7e-146">보정</span><span class="sxs-lookup"><span data-stu-id="99b7e-146">Calibration</span></span>

<span data-ttu-id="99b7e-147">Cortana가 자신을 소개하면 다음 설정 단계는 보정입니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-147">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="99b7e-148">최상의 HoloLens 환경을 위해 설정 중에 보정 프로세스를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-148">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="99b7e-149">HoloLens(1세대)는 동공 사이의 거리(IPD 또는 [동공 간 거리](https://en.wikipedia.org/wiki/Interpupillary_distance))를 사용하여 홀로그램을 선명하고 쉽게 상호작용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-149">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="99b7e-150">IPD가 올바르지 않으면 홀로그램이 불안정하거나 잘못된 거리에 있는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-150">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="99b7e-151">보정하는 동안 HoloLens에서는 눈 하나당 6개의 대상에 손가락을 정렬하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-151">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="99b7e-152">HoloLens는 이 프로세스를 사용하여 눈에 맞는 IPD를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-152">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="99b7e-153">새 사용자에 대해 보정을 업데이트하거나 조정해야 하는 경우 새 사용자는 설정 외부에서 보정 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-153">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![두 번째 단계에서 IPD 손가락 맞춤 화면](./images/ipd-finger-alignment-300px.jpg)

*<span data-ttu-id="99b7e-155">두 번째 단계에서 IPD 손가락 맞춤 화면</span><span class="sxs-lookup"><span data-stu-id="99b7e-155">IPD finger-alignment screen at second step</span></span>*

<span data-ttu-id="99b7e-156">축하합니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-156">Congratulations!</span></span> <span data-ttu-id="99b7e-157">설정이 완료되었으며 HoloLens 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b7e-157">Setup is complete and you can begin using HoloLens.</span></span>

## <span data-ttu-id="99b7e-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="99b7e-158">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99b7e-159">HoloLens(1세대) 시작하기</span><span class="sxs-lookup"><span data-stu-id="99b7e-159">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
