---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: 참가자 빌드를 시작하고 HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공하는 방법을 알아봅니다.
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977233"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="5c410-103">Microsoft HoloLens에 대한 참가자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="5c410-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="5c410-104">HoloLens에 대한 최신 Insider Preview 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="5c410-105">HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 [간단하게 시작하고](hololens-insider.md#start-receiving-insider-builds) 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="5c410-106">Windows 참가자 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="5c410-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="5c410-107">새로운 기능을 Windows 참가자로 다시 플라이팅하기 시작하게 되어 기쁘게요.</span><span class="sxs-lookup"><span data-stu-id="5c410-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="5c410-108">새 빌드는 최신 업데이트를 위해 개발 및 베타 채널로 플라이팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="5c410-109">Windows 참가자 빌드에 더 많은 기능과 업데이트를 추가함에 따라 이 페이지를 계속 업데이트할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="5c410-110">이러한 업데이트를 현실에 혼합할 준비가 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="5c410-111">기능</span><span class="sxs-lookup"><span data-stu-id="5c410-111">Feature</span></span>                 | <span data-ttu-id="5c410-112">Description</span><span class="sxs-lookup"><span data-stu-id="5c410-112">Description</span></span>                | <span data-ttu-id="5c410-113">대상 사용자</span><span class="sxs-lookup"><span data-stu-id="5c410-113">Target Users</span></span> | <span data-ttu-id="5c410-114">빌드 소개</span><span class="sxs-lookup"><span data-stu-id="5c410-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="5c410-115">HoloLens의 CSP 변경 내용</span><span class="sxs-lookup"><span data-stu-id="5c410-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="5c410-116">데이터를 쿼리하는 에 대한 새 CSP</span><span class="sxs-lookup"><span data-stu-id="5c410-116">New CSPs for to query data</span></span> | <span data-ttu-id="5c410-117">IT 관리자</span><span class="sxs-lookup"><span data-stu-id="5c410-117">IT Admins</span></span>    | <span data-ttu-id="5c410-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="5c410-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="5c410-119">HoloLens의 CSP 변경 내용</span><span class="sxs-lookup"><span data-stu-id="5c410-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="5c410-120">Windows 참가자 빌드에 도입된 20348.1403</span><span class="sxs-lookup"><span data-stu-id="5c410-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="5c410-121">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="5c410-121">DevDetail CSP</span></span>

<span data-ttu-id="5c410-122">DevDetail CSP는 이제 HoloLens 디바이스에 사용 중인 스토리지 공간도 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="5c410-123">이 값은 설정 앱의 스토리지 페이지에 표시된 값과 거의 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="5c410-124">다음은 이 정보를 포함하는 특정 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="5c410-125">./DevDetail/Ext/Microsoft/FreeStorage(GET 작업만 해당)</span><span class="sxs-lookup"><span data-stu-id="5c410-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="5c410-126">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="5c410-126">DeviceStatus CSP</span></span>

<span data-ttu-id="5c410-127">DeviceStatus CSP는 이제 HoloLens가 적극적으로 연결된 Wifi 네트워크의 SSID 및 BSSID도 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="5c410-128">다음은 이 정보를 포함하는 특정 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="5c410-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="5c410-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="5c410-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="5c410-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="5c410-131">NetworkIdentifiers를 쿼리하는 syncml Blob 예제(MDM 공급업체용)</span><span class="sxs-lookup"><span data-stu-id="5c410-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="5c410-132">수정 및 개선 사항:</span><span class="sxs-lookup"><span data-stu-id="5c410-132">Fixes and improvements:</span></span>

- <span data-ttu-id="5c410-133">잠긴 [파일을 다운로드하라는 프롬프트가 없는 장치 포털 대해 알려진 문제가 해결되었습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="5c410-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="5c410-134">파일 [업로드 및 다운로드 시간 장치 포털 대한 알려진 문제를 해결했습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="5c410-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="5c410-135">참가자 빌드 수신 시작</span><span class="sxs-lookup"><span data-stu-id="5c410-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="5c410-136">최근에 업데이트하지 않은 경우 디바이스를 다시 부팅하여 상태를 업데이트하고 최신 빌드를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="5c410-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="5c410-137">"디바이스 다시 부팅" 음성 명령이 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="5c410-138">설정/Windows 참가자 프로그램 다시 시작 단추를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="5c410-139">발생한 백 엔드에 버그가 있으므로 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="5c410-140">HoloLens 2 디바이스에서 설정 업데이트   >  **& 보안** Windows 참가자 프로그램 이동하여  >   **시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="5c410-141">Windows 참가자 등록하는 데 사용한 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="5c410-142">이제 Windows 참가자가 채널로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="5c410-143">**빠른** 링이 **개발 채널이** **되고, 느린** 링이 **베타 채널** 되고, 릴리스 **미리 보기** 링이 릴리스 미리 **보기 채널** 이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="5c410-144">매핑은 다음과 ![ 같습니다. Windows 참가자 채널 ](images/WindowsInsiderChannels.png) 설명에 대한 자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개를](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c410-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="5c410-145">그런 **다음, Windows의 활성 개발을** **선택하고, 개발 채널** 또는 **베타 채널** 빌드를 받을지 선택하고, 프로그램 용어를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="5c410-146">확인을 > **지금 다시 시작을** 선택하여 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="5c410-147">디바이스가 다시 부팅된 후 설정 > 업데이트 & 보안 > 업데이트 확인으로 이동하여 최신 빌드를 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="5c410-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="5c410-148">업데이트 오류 0x80070490 해결</span><span class="sxs-lookup"><span data-stu-id="5c410-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="5c410-149">Dev 또는 Beta 채널에서 업데이트할 때 업데이트 오류 0x80070490 발생하는 경우 다음과 같은 단기 해결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="5c410-150">여기에는 참가자 채널을 이동하고, 업데이트를 선택하고, 참가자 채널을 다시 이동하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="5c410-151">1단계 - 릴리스 미리 보기</span><span class="sxs-lookup"><span data-stu-id="5c410-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="5c410-152">설정, & 보안 업데이트 Windows 참가자 프로그램 릴리스 미리 **보기 채널을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="5c410-153">설정, 업데이트 & 보안, **Windows 업데이트, 업데이트 확인.**</span><span class="sxs-lookup"><span data-stu-id="5c410-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="5c410-154">업데이트 후 2단계로 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="5c410-155">2단계 - 개발 채널</span><span class="sxs-lookup"><span data-stu-id="5c410-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="5c410-156">설정, & 보안 업데이트, Windows 참가자 프로그램 개발 **채널을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="5c410-157">설정, 업데이트 & 보안, **Windows 업데이트, 업데이트 확인.**</span><span class="sxs-lookup"><span data-stu-id="5c410-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="5c410-158">FFU 다운로드 및 플래시 방향</span><span class="sxs-lookup"><span data-stu-id="5c410-158">FFU download and flash directions</span></span>
<span data-ttu-id="5c410-159">비행 서명 ffu를 사용하여 테스트하려면 먼저 항공편 서명 ffu를 플래시하기 전에 디바이스의 잠금을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="5c410-160">On PC:</span><span class="sxs-lookup"><span data-stu-id="5c410-160">On PC:</span></span>
    1. <span data-ttu-id="5c410-161">에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="5c410-162">Microsoft Store ARC(고급 복구 도우미)를 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="5c410-163">HoloLens - 플라이트 잠금 해제: **설정** 업데이트 & 보안 Windows 참가자 프로그램 열고  >    >   등록한 후 디바이스를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="5c410-164">Flash FFU - 이제 ARC를 사용하여 비행 서명된 FFU를 플래시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="5c410-165">피드백 제공 및 문제 보고</span><span class="sxs-lookup"><span data-stu-id="5c410-165">Provide feedback and report issues</span></span>
<span data-ttu-id="5c410-166">HoloLens에서 [피드백 허브 앱을](hololens-feedback.md) 사용하여 피드백을 제공하고 문제를 보고하세요.</span><span class="sxs-lookup"><span data-stu-id="5c410-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="5c410-167">피드백 허브 사용하면 엔지니어가 문제를 신속하게 디버그하고 해결할 수 있도록 필요한 진단 정보가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="5c410-168">중국어 및 일본어 버전의 HoloLens와 관련된 문제는 동일한 방식으로 보고되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="5c410-169">Documents 폴더에 액세스하도록 피드백 허브 여부를 묻는 프롬프트를 수락해야 합니다(메시지가 표시되면 **예** 선택).</span><span class="sxs-lookup"><span data-stu-id="5c410-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="5c410-170">개발자를 위한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="5c410-170">Note for developers</span></span>
<span data-ttu-id="5c410-171">HoloLens의 참가자 빌드를 사용하여 애플리케이션을 개발하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="5c410-172">시작하려면 [HoloLens 개발자 설명서를](https://developer.microsoft.com/windows/mixed-reality/development) 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5c410-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="5c410-173">이러한 동일한 지침은 HoloLens의 참가자 빌드에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="5c410-174">HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio 동일한 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="5c410-175">참가자 빌드 수신 중지</span><span class="sxs-lookup"><span data-stu-id="5c410-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="5c410-176">Windows Holographic의 참가자 빌드를 더 이상 수신하지 않으려는 경우 HoloLens에서 프로덕션 빌드를 실행할 때 옵트아웃하거나 고급 복구 도우미를 사용하여 [디바이스를](hololens-recovery.md) Windows Holographic의 비 참가자 버전으로 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="5c410-177">새 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 취소하는 사용자에게 파란색 화면이 발생하는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="5c410-178">그런 다음 디바이스를 수동으로 복구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="5c410-179">영향을 받을지 여부에 대한 자세한 내용은 이 [알려진 문제에](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)대한 자세한 내용을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5c410-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="5c410-180">HoloLens에서 프로덕션 빌드를 실행하고 있는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="5c410-181">설정 **> 시스템 > 정보로** 이동하여 빌드 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="5c410-182">[프로덕션 빌드 번호는 릴리스 정보 를 참조하세요.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="5c410-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="5c410-183">참가자 빌드를 옵트아웃하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="5c410-184">프로덕션 빌드를 실행하는 HoloLens에서 **설정 > 업데이트 & 보안 > Windows 참가자 프로그램** 로 이동하고 참가자 **빌드 중지를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="5c410-185">지침에 따라 디바이스를 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="5c410-185">Follow the instructions to opt out your device.</span></span>
