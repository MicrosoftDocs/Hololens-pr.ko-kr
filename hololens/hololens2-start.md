---
title: HoloLens 2 설정
description: Microsoft(MSA) 또는 AAD(Azure Active Directory) 계정을 사용하여 Wi-Fi 네트워크를 통해 HoloLens 2를 처음 설정하는 방법을 알아봅니다.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923785"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="02e13-104">HoloLens 2 설정</span><span class="sxs-lookup"><span data-stu-id="02e13-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="02e13-105">HoloLens를 처음 켜면 장치를 설정하고, 사용자 계정으로 로그인하고, 눈에 맞춰 HoloLens를 보정하는 방법이 안내됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="02e13-106">이 섹션에서는 HoloLens 2 초기 설정 환경에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="02e13-107">다음 섹션에서는 HoloLens와 작업하고 홀로그램과 상호 작용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="02e13-108">해당 문서로 건너뛰려면 [HoloLens 2 살펴보기](hololens2-basic-usage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02e13-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="02e13-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="02e13-109">Before you start</span></span>

<span data-ttu-id="02e13-110">시작하려면 먼저 다음 항목이 준비되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="02e13-111">**네트워크 연결**.</span><span class="sxs-lookup"><span data-stu-id="02e13-111">**A network connection**.</span></span> <span data-ttu-id="02e13-112">설정하려면 HoloLens를 네트워크에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="02e13-113">HoloLens 2를 사용하면 Wi-Fi에 연결하거나 이더넷을 사용하여 연결할 수 있습니다(USB-C-to-Ethernet 어댑터 필요).</span><span class="sxs-lookup"><span data-stu-id="02e13-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="02e13-114">처음 연결할 때 웹 사이트로 이동하거나 인증서를 사용하여 연결할 필요가 없는 공개 네트워크나 암호로 보호된 네트워크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="02e13-115">[HoloLens 사용하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="02e13-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="02e13-116">**Microsoft 계정**.</span><span class="sxs-lookup"><span data-stu-id="02e13-116">**A Microsoft account**.</span></span> <span data-ttu-id="02e13-117">또한 Microsoft 계정(또는 조직에서 장치를 소유한 경우, 회사 계정)을 사용하여 HoloLens에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="02e13-118">Microsoft 계정이 없는 경우 [account.microsoft.com](https://account.microsoft.com)으로 이동하여 무료로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="02e13-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="02e13-119">**넘어질 위험이 없는, 안전하고 환한 공간**.</span><span class="sxs-lookup"><span data-stu-id="02e13-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="02e13-120">[건강 및 안전 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="02e13-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="02e13-121">HoloLens와 함께 제공되는 **편안한 액세서리(선택 사항)** 로 가장 편안하게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="02e13-122">[맞춤 및 편안함에 대한 자세한 정보](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="02e13-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="02e13-123">Windows 설치</span><span class="sxs-lookup"><span data-stu-id="02e13-123">Set up Windows</span></span>

<span data-ttu-id="02e13-124">HoloLens 2를 처음 시작할 때 가장 먼저 할 작업은 Windows Holographic을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="02e13-125">HoloLens를 시작하면 음악이 들리고 Windows 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![처음 부팅 시 첫 번째 화면](images/01-magic-moment.png)

<span data-ttu-id="02e13-127">HoloLens 2에서 다음 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="02e13-128">언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-128">Select your language.</span></span>

    ![언어 선택](images/04-language.png)

1. <span data-ttu-id="02e13-130">지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-130">Select your region.</span></span>

    ![지역 선택](images/05-region.png)

1. <span data-ttu-id="02e13-132">눈에 맞춰 HoloLens를 보정합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="02e13-133">보정을 건너뛰도록 선택하면 다음에 로그인할 때 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="02e13-134">먼저 바이저를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-134">First, you'll adjust your visor.</span></span>
    
        ![보정 선택 화면](images/06-et-corners.png)

    2. <span data-ttu-id="02e13-136">보정하려면 대상 세트(보석이라고 함)를 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="02e13-137">보정을 하는 동안 눈을 깜빡이거나 눈을 감아도 괜찮지만 방에 있는 다른 물체를 응시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="02e13-138">HoloLens는 이 프로세스를 사용하여 홀로그램 세계를 렌더링하기 위해 눈 위치를 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![눈에 맞게 조정](images/07-adjust-eyes.png)

        <span data-ttu-id="02e13-140">보정이 완료되면 바이저가 머리 위에서 움직여도 홀로그램이 올바르게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="02e13-141">보정 정보는 장치에 로컬로 저장되며 계정 정보와 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="02e13-142">자세한 내용은 [보정 데이터 및 보안](hololens-calibration.md#calibration-data-and-security)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02e13-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![보정 완료](images/calibration-complete.png)

1. <span data-ttu-id="02e13-144">인터넷에 연결합니다(Wi-Fi 또는 이더넷 연결 선택).</span><span class="sxs-lookup"><span data-stu-id="02e13-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="02e13-145">HoloLens는 Wi-Fi 네트워크에서 얻은 정보에 따라 자동으로 표준 시간대를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="02e13-146">설치가 완료되면 설정 앱을 사용하여 표준 시간대를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi에 연결](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="02e13-148">2019년 10월 이후 OS 버전을 실행하는 경우 Wi-Fi 단계를 완료한 후에도 설치 중에 다른 네트워크로 전환해야 하는 경우에는 **Volume Down** 및 **전원** 단추를 동시에 눌러 이 단계로 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="02e13-149">이전 버전의 경우 [장치를 다시 설정](hololens-recovery.md)하거나 Wi-Fi 네트워크를 사용할 수 없는 위치에서 다시 시작하여 자동으로 연결되지 않도록 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="02e13-150">또한 HoloLens 설정 중에 2분의 자격 증명 제한 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="02e13-151">사용자 이름/암호를 2분 이내에 입력해야 합니다. 그렇지 않으면 사용자 이름 필드가 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="02e13-152">Autopilot 프로필이 있으면 HoloLens 2에서 검색하여 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="02e13-153">이 화면에서는 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-153">No action is needed on this screen.</span></span>
 
    ![Autopilot 프로필 검색](images/autopilot-profile-search.png) 

1. <span data-ttu-id="02e13-155">라이선스 화면에서 **Accept** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-155">Click **Accept** on the licensing screen.</span></span>

    ![Windows 사용권 계약](images/windows-license-agreement.png)

1. <span data-ttu-id="02e13-157">사용자 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-157">Sign in to your user account.</span></span> <span data-ttu-id="02e13-158">**My work or school owns it** 및 **I own it** 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="02e13-159">**회사 또는 학교 소유** 를 선택하면 Azure AD 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="02e13-160">조직에서 Azure AD Premium을 사용하고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="02e13-161">조직에서 Azure AD Premium을 사용하지 않는 경우 자동 MDM 등록을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="02e13-162">이 경우 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#different-ways-to-enroll)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="02e13-163">조직 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="02e13-164">개인정보처리방침 및 최종 사용자 라이선스 계약에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="02e13-165">Azure AD 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="02e13-166">조직의 로그인 페이지로 다시 이동하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="02e13-167">장치 설정을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="02e13-168">**내 소유** 를 선택하면 Microsoft 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="02e13-169">설정이 완료된 후 [장치 관리에서 수동으로 HoloLens를 등록](hololens-enroll-mdm.md#different-ways-to-enroll)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="02e13-170">Microsoft 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="02e13-171">암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-171">Enter your password.</span></span> <span data-ttu-id="02e13-172">Microsoft 계정에 [2FA(2단계 인증)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)가 필요한 경우 인증 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![사용자 설정](images/13-device-owner.png)

1. <span data-ttu-id="02e13-174">**다음** 을 선택하여 아이리스 로그인을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="02e13-175">눈 보정과 비슷하게 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="02e13-176">검색이 완료되면 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="02e13-177">**건너뛰기** 를 선택하여 이 단계를 건너뛸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="02e13-178">![아이리스 설정](images/setup-iris.png) ![아이리스 설정 완료](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="02e13-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="02e13-179">장치에 로그인할 PIN을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="02e13-180">이 PIN은 장치별로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-180">This PIN is device specific.</span></span> 

    ![Windows Hello 설정](images/setup-windows-hello.png)

    ![Windows Hello PIN 설정](images/windows-hello-pin.png)

    ![Windows Hello 설정 성공](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="02e13-184">HoloLens 2 음성 사용 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Cortana 사용](images/22-do-more-with-voice.png)

1. <span data-ttu-id="02e13-186">HoloLens 2에서 위치를 사용할지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![위치 서비스 사용](images/setup-location-services.png)

1. <span data-ttu-id="02e13-188">원격 분석 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-188">Select your telemetry level.</span></span> <span data-ttu-id="02e13-189">가능한 경우 선택 사항인 원격 분석을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="02e13-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="02e13-190">이 정보는 HoloLens 엔지니어링 팀에게 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-190">This information really helps the HoloLens engineering team.</span></span>

     ![원격 분석 수준](images/24-telemetry.png)

1. <span data-ttu-id="02e13-192">HoloLens 2에서 시작 제스처를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![이미지 1에서 시작 제스처를 사용하는 방법을 알아보기](images/26-01-startmenu-learning.png)

     ![이미지 2에서 시작 제스처를 사용하는 방법을 알아보기](images/26-02-startmenu-learning.png)

<span data-ttu-id="02e13-195">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="02e13-195">Congratulations!</span></span>  <span data-ttu-id="02e13-196">설치가 완료되었으며 HoloLens를 사용할 준비가 되었습니다!</span><span class="sxs-lookup"><span data-stu-id="02e13-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="02e13-197">다음 단계</span><span class="sxs-lookup"><span data-stu-id="02e13-197">Next steps</span></span>

1. <span data-ttu-id="02e13-198">곧바로 혼합 현실과 상호 작용을 시작하고 HoloLens에서 Windows 10을 탐색합니다. 손 상호 작용에 대한 실습 자습서는 **팁** 앱을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="02e13-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="02e13-199">시작 제스처를 사용하여 시작으로 이동하거나 "Go to Start"라고 말한 다음 팁을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02e13-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="02e13-200">HoloLens 2 사용 방법을 계속 읽으려면 아래를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="02e13-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="02e13-201">HoloLens 2 둘러보기</span><span class="sxs-lookup"><span data-stu-id="02e13-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
