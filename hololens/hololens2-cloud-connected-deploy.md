---
title: 배포 가이드 – 클라우드로 연결 된 HoloLens 2 배포, 원격 지원-배포
description: 클라우드 연결 네트워크를 통해 HoloLens 장치에 대 한 등록 및 원격 지원의 유효성을 검사 하는 방법을 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309795"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="f21ce-104">배포-클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="f21ce-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="f21ce-105">모든 항목을 구성 했으므로 이제 장치를 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="f21ce-106">그러나 이제는 먼저 설치의 유효성을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="f21ce-107">먼저 Azure AD 조인 및 MDM 등록 프로세스의 유효성을 검사 한 후 원격 지원 전화를 걸 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="f21ce-108">등록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f21ce-108">Enrollment Validation</span></span>

<span data-ttu-id="f21ce-109">이제 Azure AD 및 MDM 등록에 대해 모든 것이 올바르게 구성 되었으므로 나머지는 이제 snap 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="f21ce-110">이전에 구성 된 AAD 사용자 계정 중 하나를 비롯 하 여 Wi-Fi 연결 및 HoloLens 장치가 필요&#39;.</span><span class="sxs-lookup"><span data-stu-id="f21ce-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="f21ce-111">현재 공장 설정 상태에 있는 장치를&#39;하지 않는 경우 이제 [장치를 경감 하기 위해](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="f21ce-112">장치가 OOBE에 있으면 상호 작용을 시작 하 고 메시지를 따라&#39;합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="f21ce-113">**이 HoloLens를 소유 하는 사용자** 를 묻는 메시지가 표시 되 면 중요 한 프롬프트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="f21ce-114">**회사 또는 학교 소유의 회사** 를 선택 하 고 Azure AD 계정 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="f21ce-115">성공적으로 등록 되 면 PIN을 설정 하 라는 메시지가 표시&#39;.</span><span class="sxs-lookup"><span data-stu-id="f21ce-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="f21ce-116">이 PIN은이 사용자에 대해이 장치에 대해 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="f21ce-117">또한 Iri 검색, 음성 데이터 및 원격 분석 설정을 입력 하 라는 메시지가 표시 되 고, 마지막으로 시작 메뉴를 열고 OOBE를 완료 하는 방법을 배울 수&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="f21ce-118">Mixed Reality 홈에 도착 하면 방금 배운 **시작 제스처** 를 사용 하 여 시작 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="f21ce-119">**설정** 앱을 선택 하 고 **시스템을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f21ce-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="f21ce-120">&#39;하는 첫 번째 정보는 HoloLens 2 장치에 hololens를 적용 한 &quot; &quot; 후 6 개의 문자열이 표시 되는 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="f21ce-121">이 이름을 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-121">Take note of this name.</span></span>

![HoloLens 2 설정-정보](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="f21ce-123">설정 앱 내에서 장치가 Azure AD에 성공적으로 등록 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="f21ce-124">**설정** 에서 **계정**  ->  에 **회사 또는 학교 액세스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="f21ce-125">이 화면에서 &quot; _nameofAAD_&#39;s Azure AD에 연결 된 것을 확인 하 여 성공적으로 등록 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="f21ce-126">_사용자 이름_ @ _nameofAAD_. onmicrosoft.com로 연결 &quot; 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="f21ce-127">장치에 연결 된 Azure AD의 유효성을 검사 하려면 모든 장치에서 [Azure Portal](https://portal.azure.com/#home)Azure Active Directory 장치에서 Azure Active Directory를 확인 하  ->    ->    ->  고 장치 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="f21ce-128">장치가 Azure Active Directory의 일부임을 확인할 수&#39;.</span><span class="sxs-lookup"><span data-stu-id="f21ce-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory-장치](./images/aad-enrollment.png)

<span data-ttu-id="f21ce-130">다음으로 [Microsoft 끝점 관리자 관리 센터](https://endpoint.microsoft.com/#home)에 로그인 해야&#39;.</span><span class="sxs-lookup"><span data-stu-id="f21ce-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="f21ce-131">로그인 하 고 **장치** , **모든 장치** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="f21ce-132">여기에서 HoloLens 장치&#39;s 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="f21ce-133">HoloLens가 Intune에 나열 된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-장치](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="f21ce-135">원격 지원 통화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f21ce-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="f21ce-136">장치가 AAD 및 MDM 모두에 등록 되었는지 확인 한 후에는 테스트 원격 지원 전화를&#39;하는 시간이&#39;.</span><span class="sxs-lookup"><span data-stu-id="f21ce-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="f21ce-137">이 유효성 검사를 수행 하려면 HoloLens 장치 및 Windows 10 PC와 PC에 대 한 두 번째 Azure AD 사용자 계정이 있어야&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="f21ce-138">이 유효성 검사 단계에서는 이전에 마지막 유효성 검사 단계를 완료 했으며 장치가 등록 되었고 Azure AD 사용자가 장치에 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="f21ce-139">PC에 Microsoft 팀이 아직 설치 되어 있지 않은 경우 [여기에서 팀을 다운로드할](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="f21ce-140">현재 HoloLens에 로그인 한 사용자가 아닌 다른 Azure AD 사용자 계정을 사용 하 여 팀에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="f21ce-141">PC에서 로그인 하면 전화를 받을 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="f21ce-142">HoloLens의 잠금을 해제 하 고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="f21ce-143">원격 지원 앱을 시작 하려면 **시작 메뉴** 를 열고 **원격 지원** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="f21ce-144">원격 지원 기능은 받은 편지함 앱으로 번들로 제공 되는 것이 아니라 HoloLens 2&#39;s 시작 메뉴에 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="f21ce-145">시작 메뉴에 고정 되어&#39;하지 않은 이벤트의 경우 **모든 앱** 목록을 열어 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="f21ce-146">원격 지원이 시작 되 면 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 를 통해 장치 사용자를 식별 하 고 앱에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="f21ce-147">앱 내에서 **검색** 을 선택 하 고 PC에서 두 번째 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="f21ce-148">사용자를 선택 하 여 호출을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="f21ce-149">PC에서 호출에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-149">From your PC, answer the call.</span></span>

<span data-ttu-id="f21ce-150">축 하 합니다. 성공적으로 연결 되 고 원격 지원 전화를&#39;합니다.</span><span class="sxs-lookup"><span data-stu-id="f21ce-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="f21ce-151">다음을 사용 하는 등의 특정 원격 지원 기능을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f21ce-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="f21ce-152">주석 입력</span><span class="sxs-lookup"><span data-stu-id="f21ce-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="f21ce-153">혼합 현실에서 파일 및 뷰 공유</span><span class="sxs-lookup"><span data-stu-id="f21ce-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="f21ce-154">다른 HoloLens 앱에서 도움 받기</span><span class="sxs-lookup"><span data-stu-id="f21ce-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="f21ce-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f21ce-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f21ce-156">클라우드 연결 배포-유지 관리</span><span class="sxs-lookup"><span data-stu-id="f21ce-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)