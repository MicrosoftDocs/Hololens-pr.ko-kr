---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: Insider 빌드를 시작 하 고 다음 주요 HoloLens 운영 체제 업데이트에 대 한 귀중 한 피드백을 제공 하는 방법에 대해 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924369"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="e8478-103">Microsoft HoloLens에 대한 참가자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="e8478-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="e8478-104">HoloLens의 최신 Insider Preview 빌드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="e8478-105">간단 하 게 [시작](hololens-insider.md#start-receiving-insider-builds) 하 고 HoloLens의 다음 주요 운영 체제 업데이트에 대 한 유용한 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="e8478-106">Windows 참가자 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="e8478-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="e8478-107">Windows 참가자에 게 새 기능을 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="e8478-108">새 빌드는 최신 업데이트에 대 한 개발 및 베타 채널에 대 한 플 라이팅 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="e8478-109">Windows 참가자 빌드에 더 많은 기능과 업데이트를 추가 하는 경우이 페이지를 계속 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="e8478-110">이러한 업데이트를 현실에 맞게 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="e8478-111">HoloLens의 CSP 변경 내용</span><span class="sxs-lookup"><span data-stu-id="e8478-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="e8478-112">Windows 참가자 빌드, 20348.1403에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="e8478-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="e8478-113">DevDetail CSP</span></span>

<span data-ttu-id="e8478-114">이제 DevDetail CSP는 HoloLens 장치에서 사용 가능한 저장소 공간을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="e8478-115">이 값은 설정 앱의 저장소 페이지에 표시 된 값과 거의 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="e8478-116">다음은이 정보를 포함 하는 특정 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="e8478-117">./DevDetail/Ext/Microsoft/FreeStorage (GET 작업에만 해당)</span><span class="sxs-lookup"><span data-stu-id="e8478-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="e8478-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="e8478-118">DeviceStatus CSP</span></span>

<span data-ttu-id="e8478-119">이제 DeviceStatus CSP는 HoloLens가 현재 연결 되어 있는 Wifi 네트워크의 SSID와 BSSID도 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="e8478-120">다음은이 정보를 포함 하는 특정 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="e8478-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi 어댑터의 mac 주소 (*/ssid)</span><span class="sxs-lookup"><span data-stu-id="e8478-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="e8478-122">Wi-Fi 어댑터/Bssid의./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac 주소*</span><span class="sxs-lookup"><span data-stu-id="e8478-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="e8478-123">NetworkIdentifiers (MDM 공급 업체) 예제를 통해 NetworkIdentifiers 쿼리</span><span class="sxs-lookup"><span data-stu-id="e8478-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="e8478-124">수정 사항 및 향상 된 기능:</span><span class="sxs-lookup"><span data-stu-id="e8478-124">Fixes and improvements:</span></span>

- <span data-ttu-id="e8478-125">[잠긴 파일 다운로드 프롬프트가 없는 장치 포털의 알려진 문제를 수정 했습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="e8478-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="e8478-126">[파일 업로드 및 다운로드 시간 제한이 있는 장치 포털의 알려진 문제를 수정 했습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="e8478-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="e8478-127">Insider 빌드 수신을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="e8478-128">최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="e8478-129">"장치 다시 부팅" 음성 명령은 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="e8478-130">설정/Windows 참가자 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="e8478-131">사용자가 발생 시킨 백 엔드에 대 한 버그가 있었으며이로 인해 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="e8478-132">HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동 하 고 **시작** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="e8478-133">Windows 참가자로 등록 하는 데 사용한 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="e8478-134">이제 Windows 참가자가 채널로 이동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="e8478-135">**빠른** 링은 **Dev 채널이** 되 고, **저속** 링은 **베타 채널이** 되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="e8478-136">매핑은 ![ Windows 참가자 채널 설명에 나와 있습니다. ](images/WindowsInsiderChannels.png) 자세한 내용은 windows 블로그에서 Windows [참가자 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="e8478-137">그런 다음 **Windows의 활성 개발** 을 선택 하 고 **개발 채널** 또는 **베타 채널** 빌드를 받을지 여부를 선택한 후 프로그램 용어를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="e8478-138">확인을 선택 하 **> 지금 다시 시작** 하 여 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="e8478-139">장치를 다시 부팅 한 후에는 **설정 > 업데이트 & 보안 > 업데이트 확인** 으로 이동 하 여 최신 빌드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="e8478-140">업데이트 오류 0x80070490 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e8478-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="e8478-141">Dev 또는 Beta 채널에서 업데이트할 때 0x80070490 업데이트 오류가 발생 하는 경우 다음 단기 작업을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="e8478-142">여기에는 insider channel을 이동 하 고, 업데이트를 선택한 다음, Insider channel을 다시 이동 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="e8478-143">1 단계 릴리스 미리 보기</span><span class="sxs-lookup"><span data-stu-id="e8478-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="e8478-144">설정, 업데이트 & 보안, Windows Insider Program, **Release Preview 채널** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="e8478-145">설정, 업데이트 & 보안, Windows 업데이트 **업데이트 확인**.</span><span class="sxs-lookup"><span data-stu-id="e8478-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="e8478-146">업데이트 후 2 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="e8478-147">2 단계 개발자 채널</span><span class="sxs-lookup"><span data-stu-id="e8478-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="e8478-148">설정, 업데이트 & 보안, Windows 참가자 프로그램, **개발 채널** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="e8478-149">설정, 업데이트 & 보안, Windows 업데이트 **업데이트 확인**.</span><span class="sxs-lookup"><span data-stu-id="e8478-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="e8478-150">FFU 다운로드 및 플래시 방향</span><span class="sxs-lookup"><span data-stu-id="e8478-150">FFU download and flash directions</span></span>
<span data-ttu-id="e8478-151">비행 서명 된 ffu로 테스트 하려면 비행 서명 된 ffu를 깜박임 전에 먼저 장치 잠금을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="e8478-152">PC:</span><span class="sxs-lookup"><span data-stu-id="e8478-152">On PC:</span></span>
    1. <span data-ttu-id="e8478-153">에서 PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="e8478-154">Microsoft Store에서 ARC (고급 복구 도우미)를 설치 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="e8478-155">HoloLens 비행 잠금 해제: **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** , 등록, 다시 부팅 장치를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="e8478-156">플래시 FFU-이제 호를 사용 하 여 비행 서명 된 FFU를 깜박일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="e8478-157">사용자 의견을 제공 하 고 문제를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-157">Provide feedback and report issues</span></span>
<span data-ttu-id="e8478-158">사용자 의견을 제공 하 고 문제를 보고 하려면 HoloLens의 [피드백 허브 앱](hololens-feedback.md) 을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="e8478-159">피드백 허브를 사용 하면 엔지니어가 신속 하 게 디버그 하 고 문제를 해결 하는 데 필요한 모든 진단 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="e8478-160">HoloLens의 중국어 및 일본어 버전 문제는 동일한 방식으로 보고 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="e8478-161">사용자 의견 허브에서 문서 폴더에 액세스할 지 여부를 묻는 메시지를 수락 해야 합니다 (메시지가 표시 되 면 **예** 선택).</span><span class="sxs-lookup"><span data-stu-id="e8478-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="e8478-162">개발자를 위한 정보</span><span class="sxs-lookup"><span data-stu-id="e8478-162">Note for developers</span></span>
<span data-ttu-id="e8478-163">HoloLens의 Insider 빌드를 사용 하 여 응용 프로그램을 개발 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="e8478-164">시작 하려면 [HoloLens 개발자 설명서](https://developer.microsoft.com/windows/mixed-reality/development) 를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="e8478-165">이러한 동일한 지침은 HoloLens의 Insider 빌드에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="e8478-166">HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio의 동일한 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="e8478-167">Insider 빌드 수신을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="e8478-168">더 이상 Windows Holographic의 참가자 빌드를 수신 하지 않으려는 경우 HoloLens가 프로덕션 빌드를 실행 하 고 있을 때 옵트아웃 하거나 고급 복구 도우미를 사용 하 여 장치를 [복구](hololens-recovery.md) 하 여 비-windows Holographic 버전으로 장치를 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="e8478-169">새 미리 보기 빌드를 수동으로 다시 설치 하면 사용자에 게 Insider Preview 빌드에서 등록을 취소 하는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="e8478-170">이후에는 장치를 수동으로 복구 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="e8478-171">영향을 받는 경우에 대 한 자세한 내용은이 [알려진 문제](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="e8478-172">HoloLens가 프로덕션 빌드를 실행 하 고 있는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="e8478-173">**설정 > 시스템 > 정보** 로 이동 하 여 빌드 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="e8478-174">[프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="e8478-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="e8478-175">참가자 빌드를 옵트아웃 (opt out) 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="e8478-176">프로덕션 빌드를 실행 하는 HoloLens에서 **설정 > 업데이트 & 보안 > Windows Insider Program** 로 이동 하 여 **insider build 중지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="e8478-177">지침에 따라 장치를 옵트아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8478-177">Follow the instructions to opt out your device.</span></span>
