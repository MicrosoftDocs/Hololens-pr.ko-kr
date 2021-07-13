---
title: 배포 가이드 – Remote Assist 대규모로 클라우드 연결 HoloLens 2 배포 - 배포
description: 클라우드 연결 네트워크를 통해 HoloLens 디바이스에 대한 등록 및 Remote Assist 유효성을 검사하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 클라우드 연결, Remote Assist, AAD, Azure AD, MDM, Mobile 장치 관리
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635180"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="11ff5-104">배포 - 클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="11ff5-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="11ff5-105">이제 모든 것을 구성했으므로 디바이스를 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="11ff5-106">그러나 이제는 설치의 유효성을 먼저 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="11ff5-107">먼저 Azure AD 조인 및 MDM 등록 프로세스의 유효성을 검사한 다음 Remote Assist 호출을 배치할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="11ff5-108">등록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="11ff5-108">Enrollment Validation</span></span>

<span data-ttu-id="11ff5-109">이제 모든 것이 Azure AD 및 MDM 등록에 대해 올바르게 구성되었으며 나머지는 이제 맞춤이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="11ff5-110">&#39;Wi-Fi 연결과 HoloLens 디바이스뿐만 아니라 이전에 구성된 AAD 사용자 계정 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="11ff5-111">디바이스가 현재 공장 설정 상태에 있지&#39;경우 이제 [디바이스를 다시 반사하는](/hololens/hololens-recovery#clean-reflash-the-device)것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="11ff5-112">디바이스가 OOBE에 있으면&#39;상호 작용을 시작하고 프롬프트를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="11ff5-113">중요한 프롬프트는 **이 HoloLens 소유할 Who** 묻는 메시지가 표시될 때입니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="11ff5-114">**내 직장 또는 학교 소유를** 선택하고 Azure AD 계정 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="11ff5-115">등록에 성공하면 PIN을 설정하라는 메시지가&#39;.</span><span class="sxs-lookup"><span data-stu-id="11ff5-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="11ff5-116">이 PIN은 이 사용자에 대해 이 디바이스에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="11ff5-117">또한 아이리스 스캔, 음성 데이터 및 원격 분석 설정에 대한 메시지가 표시되고 마지막으로 시작 메뉴를 열고 OOBE를 완료하는 방법을 배울 수&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="11ff5-118">Mixed Reality Home에 도착하면 방금 배운 **시작 제스처를** 사용하여 시작 메뉴 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="11ff5-119">**설정** 앱을 선택하고 시스템을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="11ff5-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="11ff5-120">&#39;표시되는 첫 번째 정보는 디바이스 이름이며, HoloLens 2 디바이스의 경우 &quot; HOLOLENS- &quot; 뒤에 6개의 문자열이 잇습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="11ff5-121">이 이름을 기록해 둡다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-121">Take note of this name.</span></span>

![HoloLens 2 설정 - 정보](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="11ff5-123">디바이스가 설정 앱 내의 Azure AD에 성공적으로 등록되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="11ff5-124">**설정**   ->  **계정회사 또는 학교 액세스를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="11ff5-125">이 화면에서 &quot; _nameofAAD_&#39;Azure AD에 연결됨을 확인하여 성공적으로 등록되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="11ff5-126">_yourusername_ @ _nameofAAD_.onmicrosoft.com 연결합니다. &quot;</span><span class="sxs-lookup"><span data-stu-id="11ff5-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="11ff5-127">디바이스에 Azure AD 조인이 있는지 확인하려면 [Azure Portal Azure Active Directory](https://portal.azure.com/#home)모든 디바이스에서 Azure Active Directory 확인하고  ->    ->    ->  **디바이스** 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="11ff5-128">&#39;디바이스가 Azure Active Directory 일부임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory - 디바이스](./images/aad-enrollment.png)

<span data-ttu-id="11ff5-130">다음으로&#39;[Microsoft Endpoint Manager 관리 센터에](https://endpoint.microsoft.com/#home)로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="11ff5-131">로그인하고 **디바이스를** 선택한 **다음, 모든 디바이스를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="11ff5-132">여기에서 HoloLens 디바이스&#39;이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="11ff5-133">Intune에 나열된 HoloLens 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune - 디바이스](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="11ff5-135">Remote Assist 호출 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="11ff5-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="11ff5-136">디바이스가 AAD 및 MDM 둘 다에 등록되어 있는지&#39;확인한 후에는 테스트 Remote Assist 호출을&#39;.</span><span class="sxs-lookup"><span data-stu-id="11ff5-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="11ff5-137">이 유효성 검사를 위해&#39;HoloLens 디바이스와 Windows 10 PC뿐만 아니라 PC에 대한 두 번째 Azure AD 사용자 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="11ff5-138">이 유효성 검사 단계에서는 이전에 마지막 유효성 검사 단계를 완료했고 디바이스가 등록되었고 Azure AD 사용자가 디바이스에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="11ff5-139">PC에 Microsoft Teams 설치되어 있지 않은 경우 여기에서 Teams [다운로드할](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="11ff5-140">현재 HoloLens 로그인한 계정보다 두 번째 Azure AD 사용자 계정을 사용하여 Teams 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="11ff5-141">PC에 로그인하면 전화를 받을 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="11ff5-142">HoloLens 잠금 해제하고 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="11ff5-143">Remote Assist 앱을 시작하려면 시작 **메뉴를** 열고 **Remote Assist** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="11ff5-144">Remote Assist 받은 편지함 앱으로 번들로 제공될 뿐만 아니라 HoloLens 2&#39;시작 메뉴에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="11ff5-145">시작 메뉴 고정된 것을 볼&#39;없는 경우 **모든 앱** 목록을 열어 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="11ff5-146">Remote Assist 시작되면 [SSO를](/azure/active-directory/manage-apps/what-is-single-sign-on) 통해 디바이스 사용자를 식별하고 앱에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-146">Once Remote Assist starts it should identify the user of the device via [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="11ff5-147">앱 내에서 **검색을** 선택하고 PC에서 두 번째 사용자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="11ff5-148">통화를 시작할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="11ff5-149">PC에서 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-149">From your PC, answer the call.</span></span>

<span data-ttu-id="11ff5-150">축하합니다.&#39;성공적으로 연결되었으며 원격 지원 통화에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ff5-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="11ff5-151">다음과 같은 특정 원격 지원 기능을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="11ff5-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="11ff5-152">수동 주석</span><span class="sxs-lookup"><span data-stu-id="11ff5-152">Inking annotations</span></span>](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="11ff5-153">혼합 현실에서 파일 및 보기 공유</span><span class="sxs-lookup"><span data-stu-id="11ff5-153">Share a file and view in mixed reality</span></span>](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="11ff5-154">다른 HoloLens 앱에서 도움말 받기</span><span class="sxs-lookup"><span data-stu-id="11ff5-154">Get help in another HoloLens app</span></span>](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="11ff5-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="11ff5-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="11ff5-156">클라우드 연결 배포 - 유지 관리</span><span class="sxs-lookup"><span data-stu-id="11ff5-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)