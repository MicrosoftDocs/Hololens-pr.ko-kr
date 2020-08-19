---
title: HoloLens에 대해 알려진 문제
description: HoloLens 개발자에 게 영향을 줄 수 있는 알려진 문제의 목록입니다.
keywords: 문제 해결, 알려진 문제, 도움말
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 6947fe2232701fb9451291bd07e1c896979861d5
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940198"
---
# <span data-ttu-id="faa55-104">HoloLens에 대해 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="faa55-104">Known issues for HoloLens</span></span>

<span data-ttu-id="faa55-105">이는 HoloLens 디바이스의 현재 알려진 문제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="faa55-106">이상한 동작이 표시 되는 경우 먼저 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="faa55-107">이 목록은 새로운 문제가 발견 또는 보고 되거나 향후 HoloLens 소프트웨어 업데이트에서 문제가 해결 됨에 따라 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="faa55-108">차단 하지 않는 문제를 발견 한 경우 [피드백 허브](hololens-feedback.md)를 통해 HoloLens 장치에서 보고 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="faa55-109">직면 하는 문제로 인해 사용자가 차단 하는 경우 피드백을 제공 하는 addtion에서  [지원 요청](https://aka.ms/hlsupport)을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-109">If the issue you are facing is blocking you, in addtion to filing feedback, please  [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="faa55-110">모든 HoloLens 생성에 대해 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="faa55-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="faa55-111">HoloLens 2 장치에 대 한 알려진 문제점</span><span class="sxs-lookup"><span data-stu-id="faa55-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="faa55-112">HoloLens에 대 한 알려진 문제 (첫번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="faa55-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="faa55-113">HoloLens 에뮬레이터에 대 한 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="faa55-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="faa55-114">모든 HoloLens 생성에 대해 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="faa55-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="faa55-115">Unity</span><span class="sxs-lookup"><span data-stu-id="faa55-115">Unity</span></span>

- <span data-ttu-id="faa55-116">HoloLens 개발에 권장 되는 최신 버전의 Unity에 대 한 [도구 설치](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="faa55-117">Unity HoloLens 기술 미리 보기의 알려진 문제점은 [HoloLens Unity 포럼](https://forum.unity3d.com/threads/known-issues.394627/)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="faa55-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="faa55-118">Windows Device Portal</span></span>

- <span data-ttu-id="faa55-119">Mixed Reality 캡처의 실시간 미리 보기 기능에 몇 초의 대기 시간이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>
- <span data-ttu-id="faa55-120">가상 제스처 섹션 아래의 제스처 및 스크롤 컨트롤이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="faa55-121">이 기능을 사용 해도 아무 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-121">Using them will have no effect.</span></span> <span data-ttu-id="faa55-122">같은 페이지의 가상 키보드가 올바르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-122">The virtual keyboard on the same page works correctly.</span></span>
- <span data-ttu-id="faa55-123">설정에서 개발자 모드를 사용 하도록 설정한 후 디바이스 포털을 켜기 위한 스위치가 활성화 되기까지 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="faa55-124">OneDrive 카메라 업로드</span><span class="sxs-lookup"><span data-stu-id="faa55-124">OneDrive camera upload</span></span>

<span data-ttu-id="faa55-125">HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="faa55-126">방법</span><span class="sxs-lookup"><span data-stu-id="faa55-126">Workarounds:</span></span>
- <span data-ttu-id="faa55-127">비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="faa55-128">회사 또는 학교 계정 외에 Microsoft 계정에 로그인 할 수 있습니다 (OneDrive 앱이 이중 로그인을 지원 합니다).</span><span class="sxs-lookup"><span data-stu-id="faa55-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="faa55-129">OneDrive 내 Microsoft 계정 프로필에서 자동, 백그라운드 카메라 앨범 업로드를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>
- <span data-ttu-id="faa55-130">자동으로 사진을 업로드 하는 데 소비자 Microsoft 계정을 안전 하 게 사용할 수 없는 경우에는 OneDrive 앱에서 회사 또는 학교 계정에 수동으로 사진을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="faa55-131">이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="faa55-132">단추를 선택 **+** 하 고 **업로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="faa55-133">**사진 > 카메라 앨범**으로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="faa55-134">업로드할 사진이 나 비디오를 선택 하 고 **열기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="faa55-135">HoloLens 2 장치에 대 한 알려진 문제점</span><span class="sxs-lookup"><span data-stu-id="faa55-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="faa55-136">키보드가 특수 문자로 전환 되지 않음</span><span class="sxs-lookup"><span data-stu-id="faa55-136">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="faa55-137">사용자가 회사 또는 학교 계정을 선택 하 고 암호를 입력 하는 경우, &123 단추를 탭 하 여 키보드의 특수 문자로 전환 하려고 하면 OOBE 중에 문제가 발생 하는 경우 특수 문자로 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-137">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="faa55-138">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="faa55-138">Work-arounds:</span></span>
-   <span data-ttu-id="faa55-139">키보드를 닫은 후 텍스트 필드를 눌러 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-139">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="faa55-140">비밀 번호를 잘못 입력 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-140">Incorrectly enter your password.</span></span> <span data-ttu-id="faa55-141">다음 번에 키보드가 relaunched 경우 정상적으로 작동 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-141">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="faa55-142">웹 인증, 키보드를 닫고 **다른 장치에서 로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-142">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="faa55-143">숫자만 입력 하는 경우 사용자는 특정 키를 눌러 확장 된 메뉴를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-143">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="faa55-144">USB 키보드 사용</span><span class="sxs-lookup"><span data-stu-id="faa55-144">Using a USB keyboard.</span></span>

<span data-ttu-id="faa55-145">이는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-145">This does not affect:</span></span>
- <span data-ttu-id="faa55-146">개인 계정을 사용 하기로 선택 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="faa55-146">Users who choose to use a personal account.</span></span>

### <span data-ttu-id="faa55-147">참가자 빌드를 사용 하 여 디바이스 reflashed에서 참가자 미리 보기 빌드의 unenrolling 후 파란색 화면이 표시 됨</span><span class="sxs-lookup"><span data-stu-id="faa55-147">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="faa55-148">이 문제는 참가자 미리 보기 빌드에 참여 한 사용자에 게 영향을 미치며, 새 참가자 preview 빌드를 사용 하 여 HoloLens 2를 reflashed, 참가자 프로그램에서 unenrolled 하는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-148">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="faa55-149">이는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-149">This does not affect:</span></span>
- <span data-ttu-id="faa55-150">Windows 참가자에 등록 되지 않은 사용자</span><span class="sxs-lookup"><span data-stu-id="faa55-150">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="faa55-151">참가자</span><span class="sxs-lookup"><span data-stu-id="faa55-151">Insiders:</span></span>
    - <span data-ttu-id="faa55-152">참가자 빌드가 버전 18362 때문에 디바이스가 등록 된 경우</span><span class="sxs-lookup"><span data-stu-id="faa55-152">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="faa55-153">참가자가 19041를 생성 하 고 참가자 프로그램에 등록 된 상태를 유지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="faa55-153">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="faa55-154">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="faa55-154">Work-around:</span></span> 
- <span data-ttu-id="faa55-155">문제 방지</span><span class="sxs-lookup"><span data-stu-id="faa55-155">Avoid the issue</span></span> 
    - <span data-ttu-id="faa55-156">비 참가자 빌드를 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-156">Flash a non-insider build.</span></span> <span data-ttu-id="faa55-157">정기 월간 업데이트 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-157">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="faa55-158">Insider Preview 유지</span><span class="sxs-lookup"><span data-stu-id="faa55-158">Stay on Insider Preview</span></span>
- <span data-ttu-id="faa55-159">장치 Reflash</span><span class="sxs-lookup"><span data-stu-id="faa55-159">Reflash the device</span></span>
    1. <span data-ttu-id="faa55-160">연결 하지 않는 동안 완전히 종료 하 여 [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 를 수동으로 깜박이는 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-160">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="faa55-161">그런 다음 볼륨을 들고 전원 단추를 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-161">Then while holding Volume up, tap the Power button.</span></span>
    1. <span data-ttu-id="faa55-162">PC에 연결 하 고 고급 복구 도우미를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-162">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    1. <span data-ttu-id="faa55-163">HoloLens 2를 기본 빌드로 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-163">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="faa55-164">HoloLens에 대 한 알려진 문제 (첫번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="faa55-164">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="faa55-165">Visual Studio를 통해 HoloLens에 연결 하 고 배포할 수 없음</span><span class="sxs-lookup"><span data-stu-id="faa55-165">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="faa55-166">마지막 업데이트: 8/8 @ 5:11PM-Visual Studio에서이 문제에 대 한 수정 사항이 포함 된 VS 2019 버전 16.2을 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-166">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="faa55-167">이 오류가 발생 하지 않도록 하려면이 최신 버전으로 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-167">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="faa55-168">Visual Studio에는이 문제에 대 한 수정 사항이 포함 된 VS 2019 버전 16.2이 릴리스 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-168">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="faa55-169">이 오류가 발생 하지 않도록 하려면이 최신 버전으로 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-169">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="faa55-170">문제 근본 원인: visual studio 2015 또는 초기 릴리스의 Visual Studio 2017를 사용 하 여 HoloLens에 응용 프로그램을 배포 하 고 디버그 한 다음 나중에 동일한 HoloLens로 Visual studio 2017 또는 Visual Studio 2019의 최신 버전을 사용 하는 것이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-170">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="faa55-171">Visual Studio의 최신 릴리스에서는 새 버전의 구성 요소를 배포 하지만 이전 버전의 파일은 장치에서 남아 있으므로 최신 버전이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-171">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="faa55-172">이로 인해 DEP0100: 대상 디바이스에서 개발자 모드를 사용 하도록 설정 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-172">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="faa55-173">오류 80004005 때문에 개발자 라이선스를 가져올 수 없습니다 \<ip\> .</span><span class="sxs-lookup"><span data-stu-id="faa55-173">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="faa55-174">해결 방법</span><span class="sxs-lookup"><span data-stu-id="faa55-174">Workaround</span></span>

<span data-ttu-id="faa55-175">현재 팀에서 수정 작업을 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-175">Our team is currently working on a fix.</span></span> <span data-ttu-id="faa55-176">그 동안에는 다음 단계를 사용 하 여 문제를 해결 하 고 배포 및 디버깅을 차단 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-176">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="faa55-177">Visual Studio 열기</span><span class="sxs-lookup"><span data-stu-id="faa55-177">Open Visual Studio</span></span>
1. <span data-ttu-id="faa55-178">**파일**  >  **새**  >  **프로젝트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-178">Select **File** > **New** > **Project**.</span></span>
1. <span data-ttu-id="faa55-179">**Visual c #**  >  **Windows 데스크톱**  >  **콘솔 앱 (.net Framework)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-179">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>
1. <span data-ttu-id="faa55-180">프로젝트 이름 (예: "HoloLensDeploymentFix")을 지정 하 고 프레임 워크가 최소 .NET Framework 4.5로 설정 되어 있는지 확인 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-180">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>
1. <span data-ttu-id="faa55-181">솔루션 탐색기에서 **참조** 노드를 마우스 오른쪽 단추로 클릭 하 고 다음 참조를 추가 합니다 ( **찾아보기** 섹션을 선택 하 고 **찾아보기**선택).</span><span class="sxs-lookup"><span data-stu-id="faa55-181">Right-click on the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="faa55-182">10.0.18362.0가 설치 되어 있지 않은 경우에는 최신 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-182">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="faa55-183">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **Add**  >  **기존 항목**추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-183">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>
1. <span data-ttu-id="faa55-184">C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86로 이동 하 여 필터를 \*\*모든 파일 (\ *. \ *)** 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-184">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>
1. <span data-ttu-id="faa55-185">SirepClient.dll 및 SshClient.dll을 모두 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-185">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>
1. <span data-ttu-id="faa55-186">솔루션 탐색기에서 두 파일을 찾아 선택 하 고 (파일 목록의 맨 아래에 있어야 함) **속성** 창에서 **출력 디렉터리로 복사** 를 **항상 복사**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-186">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>
1. <span data-ttu-id="faa55-187">파일의 맨 위에 있는 기존 문 목록에 다음을 추가 합니다 `using` .</span><span class="sxs-lookup"><span data-stu-id="faa55-187">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="faa55-188">내부 `static void Main(...)` 에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-188">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="faa55-189">빌드 **Build**  >  **빌드 솔루션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-189">Select **Build** > **Build Solution**.</span></span>
1. <span data-ttu-id="faa55-190">명령 프롬프트 창과 cd를 컴파일된 .exe 파일이 포함 된 폴더에 엽니다 (예: C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="faa55-190">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug)</span></span>
1. <span data-ttu-id="faa55-191">실행 파일을 실행 하 고 디바이스의 IP 주소를 명령줄 인수로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-191">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="faa55-192">(USB를 사용 하 여 연결 된 경우 127.0.0.1을 사용 하 고, 그렇지 않으면 디바이스의 Wi-fi IP 주소를 사용할 수 있습니다.)  예를 들어 "HoloLensDeploymentFix 127.0.0.1"</span><span class="sxs-lookup"><span data-stu-id="faa55-192">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1"</span></span>

1. <span data-ttu-id="faa55-193">메시지 없이 도구를 종료 한 후 (몇 초 정도 소요 되는 경우), 이제 Visual Studio 2017 이상에서 배포 및 디버그할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-193">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="faa55-194">계속 해 서 도구를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-194">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="faa55-195">사용할 수 있게 되 면 추가 업데이트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-195">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="faa55-196">HoloLens에서 Microsoft 스토어 및 앱을 시작 하는 문제</span><span class="sxs-lookup"><span data-stu-id="faa55-196">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="faa55-197">마지막 업데이트: 4/2 @ 10 AM-문제가 해결 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-197">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="faa55-198">HoloLens에서 Microsoft 스토어 및 앱을 시작 하려고 하면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-198">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="faa55-199">백그라운드 앱 업데이트가 특정 시퀀스에 최신 버전의 프레임 워크 패키지를 배포 하는 경우 해당 종속 앱이 계속 실행 되 고 있는 경우이 문제가 발생 하는 것으로 확인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-199">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="faa55-200">이 경우 자동 앱 업데이트는 이전 버전의 프레임 워크를 사용 하는 실행 중인 모든 앱에 대해 실행 중인 앱이 새 버전의 .NET 네이티브 프레임 워크 (버전 10.0.25531를 10.0.27413)를 올바르게 업데이트 하지 않은 것으로 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-200">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="faa55-201">프레임 워크 업데이트 흐름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-201">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="faa55-202">새 프레임 워크 패키지가 스토어에서 다운로드 되 고 설치 됨</span><span class="sxs-lookup"><span data-stu-id="faa55-202">The new framework package is downloaded from the store and installed</span></span>
1. <span data-ttu-id="faa55-203">최신 버전을 사용 하기 위해 이전 프레임 워크를 사용 하는 모든 앱은 ' 업데이트 됨 '입니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-203">All apps using the older framework are 'updated' to use the newer version</span></span>

<span data-ttu-id="faa55-204">2 단계가 완료 되기 전에 중단 되 면 최신 프레임 워크가 등록 되지 않은 모든 앱이 시작 메뉴에서 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-204">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="faa55-205">이 문제로 인해 HoloLens의 모든 앱이 영향을 받을 수 있다고 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-205">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="faa55-206">일부 사용자가 중단 된 앱을 종료 하 고 피드백 허브, 3D 뷰어 또는 사진 등의 다른 앱을 실행 하 여 문제를 해결 했다고 보고 한 경우 &mdash; ,이는 해당 시간의 100%로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-206">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="faa55-207">이 문제가 발생 하 여 업데이트 자체는 발생 되지 않았지만 .NET 네이티브 프레임 워크 업데이트를 잘못 처리 하는 OS의 버그로 인해 근본 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-207">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="faa55-208">픽스를 확인 하 고 수정 프로그램을 포함 하는 업데이트 (OS 버전 17763.380)를 릴리스 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-208">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="faa55-209">장치에서 업데이트를 받을 수 있는지 확인 하려면 다음을 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-209">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="faa55-210">설정 앱으로 이동 하 여 **업데이트 & 보안**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-210">Go to the Settings app and open **Update & Security**.</span></span>
1. <span data-ttu-id="faa55-211">**업데이트 확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-211">Select **Check for Updates**.</span></span>
1. <span data-ttu-id="faa55-212">17763.380에 대 한 업데이트를 사용할 수 있는 경우이 빌드로 업데이트 하 여 앱 중지 버그 수정을 수신 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-212">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug</span></span>
1. <span data-ttu-id="faa55-213">이 버전의 OS를 업데이트 하면 앱이 예상 대로 작동 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-213">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="faa55-214">또한 모든 HoloLens OS 릴리스부터는 [Microsoft 다운로드 센터](https://aka.ms/hololensdownload/10.0.17763.380)에 ffu 이미지를 게시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-214">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="faa55-215">업데이트를 수행 하지 않으려면 3/29에서 Microsoft Store UWP 앱의 새 버전을 출시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-215">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="faa55-216">스토어의 업데이트 된 버전을 설치한 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-216">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="faa55-217">스토어를 열고 로드 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-217">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="faa55-218">블 룸 제스처를 사용 하 여 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-218">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="faa55-219">이전에 중단 된 앱을 열어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-219">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="faa55-220">여전히 실행할 수 없는 경우 손상 된 앱의 아이콘을 길게 탭 하 고 제거를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-220">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="faa55-221">스토어에서 이러한 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-221">Resinstall these apps from the store.</span></span>

<span data-ttu-id="faa55-222">장치가 여전히 앱을 로드할 수 없는 경우 다음 단계에 따라 다운로드 센터를 통해 .NET 네이티브 프레임 워크 및 런타임 버전을 테스트용으로 로드 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-222">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="faa55-223">Microsoft 다운로드 센터에서 [이 zip 파일](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-223">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="faa55-224">압축을 푸는 경우 두 가지 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-224">Unzipping will produce two files.</span></span>  <span data-ttu-id="faa55-225">Microsoft NET.TCP. e. t e t. e t e. t e t. e 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="faa55-225">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx</span></span>
1. <span data-ttu-id="faa55-226">디바이스의 개발이 해제 되었는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-226">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="faa55-227">[이 작업](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 수행 하기 위한 지침 이전에 완료 하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="faa55-227">If you haven't done that before the instructions to do that are [here](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="faa55-228">그런 다음 Windows 디바이스 포털에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-228">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="faa55-229">이는 USB를 통해이 작업을 수행 하 고 브라우저에 입력 하 여 수행 하는 것이 좋습니다 http://127.0.0.1:10080 .</span><span class="sxs-lookup"><span data-stu-id="faa55-229">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>
1. <span data-ttu-id="faa55-230">Windows Device Portal을 설치한 후에는 다운로드 한 두 개의 파일을 "로드" 하는 것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-230">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="faa55-231">이를 위해서는 **apps** 섹션으로 이동 하 고 **앱**을 선택할 때까지 왼쪽 막대를 아래로 이동해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-231">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>
1. <span data-ttu-id="faa55-232">그러면 아래와 비슷한 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-232">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="faa55-233">**앱 설치** 의 섹션으로 이동 하 여 해당 두 APPX 파일의 압축을 푼 위치를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-233">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="faa55-234">한 번에 한 번만 수행할 수 있으므로 첫 번째 항목을 선택한 후 배포 섹션에서 "이동"을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-234">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="faa55-235">그런 다음 두 번째 APPX 파일에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-235">Then do this for the second APPX file.</span></span>

   ![로드 된 앱을 설치 하는 Windows 디바이스 포털](images/20190322-DevicePortal.png)
1. <span data-ttu-id="faa55-237">이 시점에는 응용 프로그램이 다시 작동 하 고 스토어에도 액세스할 수 있다고 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-237">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>
1. <span data-ttu-id="faa55-238">일부 경우에는 영향을 받는 앱이 시작 되기 전에 3D 뷰어 앱을 시작 하는 추가 단계를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-238">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="faa55-239">이 문제를 해결 하기 위해 프로세스를 진행 하는 과정을 완료 한 후에는 저희 커뮤니티를 계속 사용 하 여 성공적으로 혼합 된 현실 환경을 만드는 것으로 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-239">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="faa55-240">장치 업데이트</span><span class="sxs-lookup"><span data-stu-id="faa55-240">Device Update</span></span>

- <span data-ttu-id="faa55-241">새 업데이트 후 30 초가 지난 후 셸이 한 번 사라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-241">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="faa55-242">**블 룸** 제스처를 수행 하 여 세션을 다시 시작 하십시오.</span><span class="sxs-lookup"><span data-stu-id="faa55-242">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="faa55-243">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="faa55-243">Visual Studio</span></span>

- <span data-ttu-id="faa55-244">HoloLens 개발에 권장 되는 최신 버전의 Visual Studio에 대 한 [도구 설치](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-244">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>
- <span data-ttu-id="faa55-245">Visual Studio에서 HoloLens에 앱을 배포 하는 경우 오류가 표시 될 수 있습니다. **사용자 매핑 섹션이 열려 있는 파일에서 요청 된 작업을 수행할 수 없습니다. (HRESULT: 0x800704C8의 예외.)**</span><span class="sxs-lookup"><span data-stu-id="faa55-245">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="faa55-246">이 문제가 발생 하면 다시 시도 하 고 배포에는 일반적으로 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-246">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="faa55-247">API</span><span class="sxs-lookup"><span data-stu-id="faa55-247">API</span></span>

- <span data-ttu-id="faa55-248">응용 프로그램이 [포커스 지점을](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 사용자에 게 설정 하거나 기본으로 카메라로 전환 하는 경우, 홀로그램는 혼합 현실에 사진이 나 비디오를 캡처하는 것으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-248">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="faa55-249">Windows에서이 버그가 해결 될 때까지 응용 프로그램이 [포커스 지점을](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 능동적으로 설정한 경우 비행기의 수직이 반대 방향 (예: 보통 =-camera)으로 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-249">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="faa55-250">Xbox 무선 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="faa55-250">Xbox Wireless Controller</span></span>

- <span data-ttu-id="faa55-251">Xbox 무선 컨트롤러 S를 HoloLens에 사용 하려면 먼저 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-251">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="faa55-252">컨트롤러를 HoloLens와 연결 하기 전에 최신 [상태](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 를 유지 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa55-252">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>
- <span data-ttu-id="faa55-253">Xbox 무선 컨트롤러에 연결 된 상태에서 HoloLens를 재부팅 하면 컨트롤러가 HoloLens에 자동으로 다시 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-253">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="faa55-254">가이드 단추 조명은 3 분 후에도 컨트롤러가 꺼질 때까지 느리게 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-254">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="faa55-255">컨트롤러를 즉시 다시 연결 하려면 표시등이 꺼질 때까지 가이드 단추를 눌러 컨트롤러 전원을 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="faa55-255">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="faa55-256">컨트롤러를 다시 켠 후에는 HoloLens에 다시 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-256">When you power your controller on again, it will reconnect to HoloLens.</span></span>
- <span data-ttu-id="faa55-257">Xbox 무선 컨트롤러에 연결 된 상태에서 HoloLens가 대기 모드로 전환 되 면 컨트롤러의 모든 입력에 대 한 HoloLens의 절전 모드가 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-257">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="faa55-258">이 작업을 사용 하는 동안 컨트롤러의 전원을 끄면이 문제가 발생 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-258">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="faa55-259">HoloLens 에뮬레이터에 대 한 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="faa55-259">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="faa55-260">Microsoft Store의 모든 앱은 에뮬레이터와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-260">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="faa55-261">예를 들어, 젊은 Conker 및 조각은 에뮬레이터에서 재생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-261">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="faa55-262">에뮬레이터에서 PC 웹캠 사용을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-262">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="faa55-263">Windows Device Portal의 실시간 미리 보기 기능은 에뮬레이터에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-263">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="faa55-264">혼합 현실 비디오 및 이미지를 계속 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa55-264">You can still capture Mixed Reality videos and images.</span></span>
