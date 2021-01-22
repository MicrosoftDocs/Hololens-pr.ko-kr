---
title: 배포 가이드 - 원격 지원으로 클라우드 연결 HoloLens 2 배포 대규모 배포 - 배포
description: 클라우드 연결 네트워크를 통해 HoloLens 장치에 대한 등록 및 원격 지원의 유효성을 검사하는 방법을 확인합니다.
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282939"
---
# <span data-ttu-id="aa92b-104">배포 - 클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="aa92b-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="aa92b-105">이제 모든 구성이 완료되었습니다. 이제 장치를 배포할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="aa92b-106">그러나 이제는 먼저 설치의 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="aa92b-107">먼저 Azure AD 가입 및 MDM 등록 프로세스의 유효성을 검사한 다음 원격 지원 통화가 걸 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <span data-ttu-id="aa92b-108">등록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="aa92b-108">Enrollment Validation</span></span>

<span data-ttu-id="aa92b-109">이제 모든 것이 Azure AD 및 MDM 등록에 맞게 제대로 구성되면 나머지는 스냅인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="aa92b-110">이전에&#39;AAD 사용자 Wi-Fi 및 HoloLens 디바이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="aa92b-111">장치가 현재&#39;설정 상태로 있지 않은 경우 이제 장치를 다시 래시하는 [것이 좋습니다.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="aa92b-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="aa92b-112">디바이스가 OOBE에 있는 경우&#39;및 프롬프트에 따라 상호 작용을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="aa92b-113">이 **HoloLens를** 누가 소유하고 있나요?</span><span class="sxs-lookup"><span data-stu-id="aa92b-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="aa92b-114">내 **직장 또는 학교** 소유를 선택하고 Azure AD 계정 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="aa92b-115">등록에 성공하면&#39;설정하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="aa92b-116">이 PIN은 이 사용자에 대해 이 장치에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="aa92b-117">또한 홍채 검사, 음성 데이터 및 원격 분석 설정에 대한 메시지가 표시되고 마지막으로&#39;메뉴를 열고 OOBE를 완료하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="aa92b-118">Mixed Reality 홈에 착수하면 방금 \*\*\*\* 배운 시작 제스처를 사용하여 시작 메뉴를 니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="aa92b-119">설정 **앱을 선택하고** 시스템을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aa92b-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="aa92b-120">첫 번째&#39;볼 수 있는 정보는 장치 이름입니다. HoloLens 2 디바이스의 경우 HOLOLENS와 6개의 문자 문자열이 &quot; &quot; 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="aa92b-121">이 이름을 메모해 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-121">Take note of this name.</span></span>

![HoloLens 2 설정 - 정보](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="aa92b-123">설정 앱 내에서 장치가 Azure AD에 성공적으로 등록된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="aa92b-124">**설정에서** **계정 액세스**직장 또는  ->  **학교를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aa92b-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="aa92b-125">이 화면에서 &quot; Azure AD의 _nameofAAD에_ 연결&#39;확인하여 성공적으로 등록되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="aa92b-126">_yourusername_ @ _nameofAAD_.onmicrosoft.com. &quot;</span><span class="sxs-lookup"><span data-stu-id="aa92b-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="aa92b-127">Azure AD에 가입된 장치의 유효성을 검사하기 위해 [Azure Portal](https://portal.azure.com/#home)Azure Active Directory 장치 모든 디바이스에서 Azure Active  ->  **Directory를**확인하고  ->  \*\*\*\*  ->  \*\*\*\* 장치 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="aa92b-128">Azure&#39;디바이스가 Azure Active Directory의 일부인지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory - 장치](./images/aad-enrollment.png)

<span data-ttu-id="aa92b-130">다음으로&#39;Microsoft Endpoint Manager 관리 센터에 [로그인해야 합니다.](https://endpoint.microsoft.com/#home)</span><span class="sxs-lookup"><span data-stu-id="aa92b-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="aa92b-131">로그인하고 **디바이스를** 선택한 **다음 모든 장치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aa92b-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="aa92b-132">여기에서 HoloLens 장치 이름과&#39;수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="aa92b-133">Intune에 나열된 HoloLens를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune - 장치](./images/endpoint-all-devices-enrolled.png)

## <span data-ttu-id="aa92b-135">원격 지원 통화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="aa92b-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="aa92b-136">AAD&#39;MDM 모두에 장치가 등록되어 있는 것을 확인한 후&#39;원격 지원 통화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="aa92b-137">이 유효성 검사를&#39;HoloLens 장치 및 Windows 10 PC와 PC에 대한 두 번째 Azure AD 사용자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="aa92b-138">이 유효성 검사 단계에서는 사용자가 이전에 마지막 유효성 검사 단계를 완료하고 장치가 등록된 경우 Azure AD 사용자가 장치에 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="aa92b-139">PC에 Microsoft Teams가 설치되어 있지 않은 경우 여기에서 [Teams를 다운로드할 수 있습니다.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)</span><span class="sxs-lookup"><span data-stu-id="aa92b-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="aa92b-140">현재 HoloLens에 로그인한 계정보다 두 번째 Azure AD 사용자 계정을 사용하여 Teams에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="aa92b-141">PC에 로그인하면 전화를 받을 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="aa92b-142">HoloLens 잠금을 해제하고 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="aa92b-143">원격 지원 앱을 시작하려면 시작 메뉴를 **열고** 원격 지원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aa92b-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="aa92b-144">원격 도우미는 받은 편지함 앱으로 번들화할 뿐만 아니라 HoloLens 2&#39;시작 메뉴에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="aa92b-145">시작 메뉴에&#39;없는 경우 모든 앱 목록을 열어서 찾아야 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="aa92b-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="aa92b-146">원격 지원이 시작되면 [SSO를](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 통해 디바이스 사용자를 식별하고 앱에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="aa92b-147">앱에서 PC에서 **두** 번째 사용자 검색을 선택하고 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="aa92b-148">통화를 시작할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="aa92b-149">PC에서 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-149">From your PC, answer the call.</span></span>

<span data-ttu-id="aa92b-150">축하합니다&#39;성공적으로 연결되고 원격 지원 통화에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="aa92b-151">다음과 같은 특정 원격 지원 기능을 사용해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa92b-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="aa92b-152">Inking annotations</span><span class="sxs-lookup"><span data-stu-id="aa92b-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="aa92b-153">혼합 현실에서 파일 공유 및 보기</span><span class="sxs-lookup"><span data-stu-id="aa92b-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="aa92b-154">다른 HoloLens 앱에서 도움말 다운로드</span><span class="sxs-lookup"><span data-stu-id="aa92b-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <span data-ttu-id="aa92b-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="aa92b-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="aa92b-156">클라우드 연결 배포 - 유지 관리</span><span class="sxs-lookup"><span data-stu-id="aa92b-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)