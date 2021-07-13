---
title: 배포 가이드 – Dynamics 365 Guides-배포를 사용 하 여 회사에 연결 된 HoloLens 2
description: Dynamics 365 Guides를 사용 하 여 회사에 연결 된 네트워크를 통해 HoloLens 2 장치 배포를 설정 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사에 연결 된 Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637067"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="9ea9e-104">배포-회사에 연결 된 가이드</span><span class="sxs-lookup"><span data-stu-id="9ea9e-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="9ea9e-105">각 배포의 중요 한 부분은 최종 사용자에 게 원활한 환경을 제공 하기 위해 테스트 하기 전에 배포가 적절히 설정 되었는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="9ea9e-106">MDM을 통해 Wi-Fi 인증서를 배포 하기 때문에 처음에 HoloLens를 설정 하 고 열린 Wi-Fi 네트워크 또는 인증서가 필요 없는 네트워크에 장치를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="9ea9e-107">HoloLens OOBE를 완료 하 고 등록 한 후에는 장치에서 이전에 구성 된 네트워크 인증서 및 LOB를 수신 하 고 장치에서 수신 된 모든 유효성을 검사할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="9ea9e-108">그런 다음 테스트 가이드를 작성 하 고 운영할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="9ea9e-109">등록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9ea9e-109">Enrollment Validation</span></span>

<span data-ttu-id="9ea9e-110">이제 Azure AD 및 MDM 등록에 대해 모든 것이 올바르게 구성 되었으므로 나머지는 이제 snap 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="9ea9e-111">Wi-Fi 연결 및 HoloLens 장치와 이전에 구성 된 Azure AD 사용자 계정 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="9ea9e-112">장치가 현재 공장 설정 상태에 있지 않은 경우 이제 [장치를 경감 하기 위해](/hololens/hololens-recovery#clean-reflash-the-device)하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="9ea9e-113">장치가 OOBE에 있으면 상호 작용을 시작 하 고 메시지를 따라 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="9ea9e-114">Wi-fi에 연결 하는 데 인증서가 필요 하지 않은 열려 있는 Wi-Fi 네트워크에 커넥트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="9ea9e-115">이렇게 하면 초기 설치 후 장치에서 조직의 Wi-Fi에 사용할 인증서를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="9ea9e-116">**이 HoloLens를 소유 Who** 묻는 메시지가 표시 되 면 중요 한 프롬프트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="9ea9e-117">**회사 또는 학교 소유의 회사** 를 선택 하 고 Azure AD 계정 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="9ea9e-118">성공적으로 등록 되 면 PIN을 설정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="9ea9e-119">이 PIN은이 사용자에 대해이 장치에 대해 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="9ea9e-120">또한 Iri 검색, 음성 데이터 및 원격 분석 설정을 입력 하 라는 메시지가 표시 되 고 마지막으로 시작 메뉴를 열고 OOBE를 완료 하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="9ea9e-121">Mixed Reality 홈에 도착 하면 방금 배운 **시작 제스처** 를 사용 하 여 시작 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="9ea9e-122">**설정** 앱을 선택 하 고 **시스템** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="9ea9e-123">표시 되는 첫 번째 정보는 장치 이름입니다 .이 이름에는 HoloLens 2 장치에 대 한 &quot; HoloLens와 &quot; 6 개의 문자열이 차례로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="9ea9e-124">이 이름을 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-124">Take note of this name.</span></span>

    ![HoloLens 2 설정 화면](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="9ea9e-126">장치가 Azure AD에 성공적으로 조인 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="9ea9e-127">두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-127">There are two ways;</span></span>

    1.  <span data-ttu-id="9ea9e-128">설정 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-128">The Settings app.</span></span> <span data-ttu-id="9ea9e-129">**설정** 에서   ->  **회사 또는 학교 액세스** 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="9ea9e-130">이 화면에서 &quot; nameofAAD&#39;s AZURE AD에 연결 된 것을 확인 하 여 성공적으로 등록 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="9ea9e-131">로 연결 *yourusername@nameofAAD.onmicrosoft.com* 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="9ea9e-132">그러면 장치가 조직&#39;s Azure AD에 가입 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="9ea9e-133">[Azure Portal](https://portal.azure.com/#home)입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="9ea9e-134">**Azure Active Directory**  ->  **장치**  ->  **모든 장치** 로 이동 하 여 장치 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="9ea9e-135">조인 유형 아래에서 ' Azure AD 조인 됨 '으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="9ea9e-136">![Azure AD에서 조인 유형 확인](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="9ea9e-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="9ea9e-137">장치가 MDM에 등록 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="9ea9e-138">두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-138">There are two ways;</span></span>

    1. <span data-ttu-id="9ea9e-139">**설정** 에서 **계정**  ->  **회사 또는 학교 액세스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="9ea9e-140">이 화면에서 &quot; nameofAAD&#39;s AZURE AD에 연결 된 것을 확인 하 여 성공적으로 등록 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="9ea9e-141">로 연결 *yourusername@nameofAAD.onmicrosoft.com* 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="9ea9e-142">이 액세스 회사 또는 학교 계정에서 &quot; nameofAAD&#39;s AZURE AD에 연결 됨을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="9ea9e-143">연결 방법 yourusername@nameofAAD.onmicrosoft.com &quot; 및 **정보** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="9ea9e-144">[관리 센터를 Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="9ea9e-145">로그인 하 고  **장치**  ,  **모든 장치** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="9ea9e-146">여기에서 HoloLens 장치&#39;이름으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="9ea9e-147">Intune에 나열 된 HoloLens를 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Azure AD에서 Intune에서 관리 확인](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="9ea9e-149">인증서 유효성 검사 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9ea9e-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="9ea9e-150">이제 장치가 Wi-Fi 인증서를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="9ea9e-151">가장 간단한 유효성 검사는 인증서를&#39;ve Wi-Fi 연결에 연결 하려고 시도 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="9ea9e-152">**설정** 앱을 열고 **Network &amp; Internet** wi-fi로 이동 하  ->   여 wi-fi 연결을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="9ea9e-153">연결 되 면 Microsoft Edge 앱을 열고 웹 사이트로 이동할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="9ea9e-154">장치에서 인증서를 받았는지 확인 하려면 [인증서 관리자](/hololens/certificate-manager)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="9ea9e-155">LOB 앱 설치 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9ea9e-155">Validate LOB app install</span></span>

<span data-ttu-id="9ea9e-156">관리 되는 앱의 설치 진행률을 보려면 앱이 설치 되어 있는지 확인 하거나 설정 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="9ea9e-157">LOB 앱을 그룹에 대 한 필수 설치로 구성 하면 할당 된 그룹의 사용자에 게 HoloLens을 등록 한 후 앱이 HoloLens 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="9ea9e-158">시작 메뉴를 열고 **모든 앱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="9ea9e-159">보유 한 앱의 수에 따라 **page up** 또는 **page down** 단추를 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="9ea9e-160">장치에서 앱 설치의 유효성을 검사 하려면 **설정**  ->  **계정을** 통해  ->  **회사 또는 학교에 액세스** 하 고, 계정을 선택한 다음 **정보** 단추를 선택 하 고 아래로 스크롤하여 MDM에서 장치에 적용 되는 다양 한 구성 및 앱을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="9ea9e-161">Intune에서 설치의 유효성을 검사 하려면 [메모리 포털](https://endpoint.microsoft.com/#home)  ->  **앱** -> 모든 **앱**  -> *TheNameOfYourApp*  ->  **장치 설치 상태** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="9ea9e-162">자세히 보기: [Intune 앱 배포 HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="9ea9e-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="9ea9e-163">유효성 검사 Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="9ea9e-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="9ea9e-164">HoloLens, 제작 및 운영에 대 한 가이드 앱의 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="9ea9e-165">작업을 수행 하기 전에 가이드 작성을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="9ea9e-166">가이드 작성</span><span class="sxs-lookup"><span data-stu-id="9ea9e-166">Authoring the Guide</span></span>

<span data-ttu-id="9ea9e-167">이 빠른 유효성 검사에 대해 많은 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="9ea9e-168">PC에서 준비한 가이드를 선택 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="9ea9e-169">빠른 유효성 검사를 위해 holographic 앵커를 사용할 수 있도록 [가이드를 고정](/dynamics365/mixed-reality/guides/hololens-app-anchor)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="9ea9e-170">그런 [다음 단계와 모델](/dynamics365/mixed-reality/guides/hololens-app-orientation)을 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="9ea9e-171">HoloLens에서 PC 및 작성자에 로그인 하려면 **제작** 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="9ea9e-172">운영자 역할은 읽기 전용 이며 PC 앱에 대 한 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="9ea9e-173">가이드 운영</span><span class="sxs-lookup"><span data-stu-id="9ea9e-173">Operating the Guide</span></span>

<span data-ttu-id="9ea9e-174">Holograms 준비 되 면 가이드 운영을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="9ea9e-175">**연산자 모드** 선택</span><span class="sxs-lookup"><span data-stu-id="9ea9e-175">Select **Operator mode**</span></span>
- <span data-ttu-id="9ea9e-176">가이드의 단계를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="9ea9e-177">가이드를 작동 하는 방법에 대 한 자세한 지침을 보려면 다음 리소스를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ea9e-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="9ea9e-178">Dynamics 365 Guides에서 가이드 운영 개요</span><span class="sxs-lookup"><span data-stu-id="9ea9e-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="9ea9e-179">Dynamics 365 Guides에서 운영자로 단계 카드를 사용 하 여 시작</span><span class="sxs-lookup"><span data-stu-id="9ea9e-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="9ea9e-180">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9ea9e-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="9ea9e-181">회사에 연결 된 배포-유지 관리</span><span class="sxs-lookup"><span data-stu-id="9ea9e-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
