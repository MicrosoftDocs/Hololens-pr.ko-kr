---
title: HoloLens 디바이스 문제 해결
description: HoloLens 디바이스 문제 및 문제 해결 기술에 대한 가장 일반적인 솔루션을 최신 상태로 유지합니다.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 문제, 버그, 문제 해결, 수정, 도움말, 지원, HoloLens, 에뮬레이터
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924624"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="db59c-104">디바이스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="db59c-104">Device Troubleshooting</span></span>

<span data-ttu-id="db59c-105">이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="db59c-106">문제 해결 절차를 시작하기 전에 가능한 경우 디바이스에 배터리 용량의 **20~40%가** 청구되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="db59c-107">전원 단추 아래에 있는 [배터리 표시등은](hololens2-setup.md#lights-that-indicate-the-battery-level) 디바이스에 로그인하지 않고 배터리 용량을 확인하는 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="db59c-108">**알려진 문제**</span><span class="sxs-lookup"><span data-stu-id="db59c-108">**Known Issues**</span></span>
- [<span data-ttu-id="db59c-109">Remote Assist 비디오가 20분 후에 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="db59c-110">자동 로그인에서 로그인 요청</span><span class="sxs-lookup"><span data-stu-id="db59c-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="db59c-111">Microsoft Edge 시작하지 못함</span><span class="sxs-lookup"><span data-stu-id="db59c-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="db59c-112">키보드가 특수 문자로 전환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="db59c-113">잠긴 파일을 다운로드해도 오류가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="db59c-114">파일 업로드/다운로드 시간 장치 포털</span><span class="sxs-lookup"><span data-stu-id="db59c-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="db59c-115">Insider 빌드로 깜박이는 디바이스의 Insider 미리 보기에서 등록을 취소한 후의 파란색 화면</span><span class="sxs-lookup"><span data-stu-id="db59c-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="db59c-116">OneDrive는 사진을 자동으로 업로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="db59c-117">**일반**</span><span class="sxs-lookup"><span data-stu-id="db59c-117">**General**</span></span>
- [<span data-ttu-id="db59c-118">HoloLens가 응답하지 않거나 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="db59c-119">"디스크 공간 부족" 오류</span><span class="sxs-lookup"><span data-stu-id="db59c-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="db59c-120">보정 실패</span><span class="sxs-lookup"><span data-stu-id="db59c-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="db59c-121">내 HoloLens가 이전에 다른 사람을 위해 설정되었으므로 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="db59c-122">Unity가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="db59c-123">Windows 장치 포털 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="db59c-124">HoloLens 에뮬레이터가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="db59c-125">**Input**</span><span class="sxs-lookup"><span data-stu-id="db59c-125">**Input**</span></span>
- [<span data-ttu-id="db59c-126">음성 명령이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="db59c-127">손 입력이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="db59c-128">**연결**</span><span class="sxs-lookup"><span data-stu-id="db59c-128">**Connectivity**</span></span>
- [<span data-ttu-id="db59c-129">Wi-Fi에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="db59c-130">**외부 디바이스**</span><span class="sxs-lookup"><span data-stu-id="db59c-130">**External Devices**</span></span> 
- [<span data-ttu-id="db59c-131">Bluetooth 디바이스가 페어링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="db59c-132">USB-C 마이크가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="db59c-133">설정에 사용할 수 있는 것으로 나열된 디바이스가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="db59c-134">Remote Assist 비디오가 20분 후에 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="db59c-135">이 알려진 문제의 심각도로 인해 현재 Windows Holographic 버전 21H1의 가용성을 일시 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="db59c-136">여전히 디바이스를 21H1로 업데이트하려면 페이지 맨 [위에 있는 릴리스 정보의 지침을 참조하세요.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="db59c-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="db59c-137">[Windows Holographic 버전 21H1의](hololens-release-notes.md#windows-holographic-version-21h1)최신 릴리스에서는 Remote Assist 일부 사용자가 20분 넘게 통화하는 동안 비디오 중지를 경험했습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="db59c-138">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="db59c-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="db59c-139">해결 방법</span><span class="sxs-lookup"><span data-stu-id="db59c-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="db59c-140">호출 간에 다시 시작</span><span class="sxs-lookup"><span data-stu-id="db59c-140">Restart in between calls</span></span>

<span data-ttu-id="db59c-141">호출이 20분을 초과하고 이 문제가 발생하는 경우 디바이스를 다시 부팅해 보세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="db59c-142">Remote Assist 호출 사이에 디바이스를 다시 부팅하면 디바이스가 새로 고쳐지고 다시 양호한 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="db59c-143">Windows Holographic에서 디바이스를 신속하게 다시 시작하려면 [버전 21H1에서](hololens-release-notes.md#windows-holographic-version-21h1) 시작 메뉴를 열고 사용자 아이콘을 선택한 다음, **다시 시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="db59c-144">이전 빌드로 되돌리기</span><span class="sxs-lookup"><span data-stu-id="db59c-144">Revert to an older build</span></span>

<span data-ttu-id="db59c-145">일부 고객은 이전 OS 버전으로 되돌릴 때 더 이상 이 문제가 발생하지 않는다는 것을 발견했습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="db59c-146">디바이스에 이 문제가 발생한 경우 다음 단계를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="db59c-147">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="db59c-147">Workarounds:</span></span>

- <span data-ttu-id="db59c-148">비즈니스에 적합한 경우 소비자 Microsoft 계정에서 자동 카메라 업로드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="db59c-149">직장 또는 학교 계정 외에도 Microsoft 계정 로그인할 수 있습니다(OneDrive 앱은 이중 로그인을 지원함).</span><span class="sxs-lookup"><span data-stu-id="db59c-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="db59c-150">OneDrive 내의 Microsoft 계정 프로필에서 자동 백그라운드 카메라 롤 업로드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="db59c-151">사진을 자동으로 업로드하는 데 소비자 Microsoft 계정 안전하게 사용할 수 없는 경우 OneDrive 앱에서 수동으로 사진을 직장 또는 학교 계정에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="db59c-152">이렇게 하려면 OneDrive 앱에서 직장 또는 학교 계정에 로그인했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="db59c-153">단추를 선택하고 **+** **업로드를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="db59c-154">**사진 > 카메라 롤로** 이동하여 업로드하려는 사진 또는 비디오를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="db59c-155">업로드하려는 사진 또는 비디오를 선택한 다음, **열기** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="db59c-156">Windows Holographic 버전 20H2 - 2021년 5월 업데이트용 빌드 다운로드</span><span class="sxs-lookup"><span data-stu-id="db59c-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="db59c-157">지침에 따라 [이전 OS 버전으로 돌아갑니다.](hololens-update-hololens.md#go-back-to-a-previous-version)</span><span class="sxs-lookup"><span data-stu-id="db59c-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="db59c-158">[디바이스에서 OS 업데이트를 수동으로 일시 중지하거나](hololens-updates.md#pause-updates-via-device) 많은 디바이스에서 [MDM을 통해 지연을](hololens-updates.md#configure-an-update-deferral-policy)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="db59c-159">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="db59c-160">자동 로그인에서 로그인 요청</span><span class="sxs-lookup"><span data-stu-id="db59c-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="db59c-161">설정 계정 로그인 옵션 -> 및 필수에서 값을 안 됨으로 설정하여 자동으로  ->    ->  로그인하도록  HoloLens 2 디바이스를 구성할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="db59c-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="db59c-162">일부 사용자는 기능 업데이트와 같이 상당히 큰 업데이트로 디바이스를 업데이트할 때 디바이스에 다시 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="db59c-163">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="db59c-163">This is a **known issue**.</span></span>

<span data-ttu-id="db59c-164">이 문제가 발생할 수 있는 경우의 예:</span><span class="sxs-lookup"><span data-stu-id="db59c-164">Example of when this could occur:</span></span>

- <span data-ttu-id="db59c-165">Windows Holographic 버전 2004(빌드 19041.xxxx)에서 Windows Holographic 버전 21H1(빌드 20346.xxxx)로 디바이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="db59c-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="db59c-166">Windows Holographic, 버전 2004를 Windows Holographic 버전 20H2와 같은 주요 빌드에서 대규모 업데이트하도록 디바이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="db59c-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="db59c-167">공장 이미지에서 최신 이미지로 디바이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="db59c-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="db59c-168">다음 중에는 이 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-168">This should not occur during:</span></span>

- <span data-ttu-id="db59c-169">월간 서비스 업데이트를 받는 디바이스</span><span class="sxs-lookup"><span data-stu-id="db59c-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="db59c-170">메서드 해결:</span><span class="sxs-lookup"><span data-stu-id="db59c-170">Work around methods:</span></span>

- <span data-ttu-id="db59c-171">PIN, 암호, 아이리스, 웹 인증 또는 FIDO2 키와 같은 로그인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="db59c-172">디바이스 PIN을 기억할 수 없고 다른 인증 방법을 사용할 수 없는 경우 사용자는 [수동 리플래시 모드 를](hololens-recovery.md#manual-procedure)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="db59c-173">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="db59c-174">Microsoft Edge 시작하지 못함</span><span class="sxs-lookup"><span data-stu-id="db59c-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="db59c-175">이 문제는 원래 Microsoft Edge 배송 버전을 염두에 두고 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="db59c-176">이 문제는 [새 Microsoft Edge](hololens-new-edge.md)해결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="db59c-177">그렇지 않은 경우 피드백을 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="db59c-178">일부 고객은 Microsoft Edge 시작에 실패하는 문제를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="db59c-179">이러한 고객의 경우 문제는 다시 부팅을 통해 지속되며 Windows 또는 애플리케이션 업데이트로 해결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="db59c-180">이 문제가 발생하고 [Windows가 최신인지](hololens-updates.md#manually-check-for-updates)확인한 경우 [피드백 허브 앱에서](hololens-feedback.md) 다음 범주 및 하위 범주인 설치 및 업데이트 > Windows 업데이트 다운로드, 설치 및 구성으로 버그를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="db59c-181">지금까지 문제의 근본 원인을 알 수 없으므로 알려진 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="db59c-182">피드백 허브 통해 버그를 제출하면 조사에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="db59c-183">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="db59c-183">This is a **known issue**.</span></span>

[<span data-ttu-id="db59c-184">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="db59c-185">키보드가 특수 문자로 전환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="db59c-186">OOBE 중에는 사용자가 직장 또는 학교 계정을 선택하고 암호를 입력한 후 &123 단추를 탭하여 키보드의 특수 문자로 전환하려고 하면 특수 문자로 변경되지 않는 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="db59c-187">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="db59c-187">This is a **known issue**.</span></span>

<span data-ttu-id="db59c-188">해결 작업:</span><span class="sxs-lookup"><span data-stu-id="db59c-188">Work-arounds:</span></span>
-   <span data-ttu-id="db59c-189">키보드를 닫고 텍스트 필드를 탭하여 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="db59c-190">암호를 잘못 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-190">Incorrectly enter your password.</span></span> <span data-ttu-id="db59c-191">다음에 키보드가 다시 시작되면 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="db59c-192">웹 인증에서 키보드를 닫고 **다른 디바이스에서 로그인을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="db59c-193">숫자만 입력하는 경우 사용자는 특정 키를 누르고 확장된 메뉴를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="db59c-194">USB 키보드 사용.</span><span class="sxs-lookup"><span data-stu-id="db59c-194">Using a USB keyboard.</span></span>

<span data-ttu-id="db59c-195">이는 다음에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-195">This does not affect:</span></span>
- <span data-ttu-id="db59c-196">개인 계정을 사용하도록 선택한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="db59c-197">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="db59c-198">잠긴 파일을 다운로드해도 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="db59c-199">! 참고 이 **문제는** Windows 참가자 빌드 버전 20348.1403에서 해결된 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="db59c-200">Windows Holographic의 이전 빌드에서 잠긴 파일을 다운로드하려고 할 때 결과는 HTTP 오류 페이지가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="db59c-201">Windows Holographic 버전 21H1 업데이트에서 잠긴 파일을 다운로드 하려고 하면 파일이 다운로드 되지 않으며 오류가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="db59c-202">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="db59c-203">장치 포털 파일 업로드/다운로드 제한 시간</span><span class="sxs-lookup"><span data-stu-id="db59c-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="db59c-204">! 이 문제는 Windows 참가자 빌드 버전 20348.1403에서 해결 된 **알려진 문제** 입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="db59c-205">이전에 해결 방법의 일부로 SSL 연결을 사용 하지 않도록 설정한 경우 다시 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="db59c-206">일부 고객은 파일을 업로드 하거나 다운로드 하려고 할 때 작업이 중단 된 것 처럼 표시 되 고 시간이 초과 되거나 완료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="db59c-207">이는 '[파일 잠김 ' 알려진 문제와](#downloading-locked-files-doesnt-error) 는 별개입니다. 이것은 Windows Holographic, 버전 2004, 20H2 및 21h1 시장 빌드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="db59c-208">이 문제는 장치 포털의 특정 요청 처리에서 버그로 인해 발생 했으며, https를 사용 하는 경우 (기본값) 가장 일관 되 게 적중 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="db59c-209">해결 방법</span><span class="sxs-lookup"><span data-stu-id="db59c-209">Workaround</span></span>

<span data-ttu-id="db59c-210">Wi-Fi 및 a n Cm에 동일 하 게 적용 되는이 해결 방법은 "SSL 연결"에서 "필수" 옵션을 사용 하지 않도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="db59c-211">이렇게 하려면 장치 포털, **시스템** 으로 이동 하 여 **기본 설정** 페이지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="db59c-212">**장치 보안** 섹션에서 **SSL 연결** 을 찾아 선택 취소 하 여 **필수** 를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="db59c-213">그런 다음 사용자는 https://(IP 주소)가 아닌 http://로 이동 하 고 파일 업로드 및 다운로드와 같은 기능이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="db59c-214">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="db59c-215">Insider build를 사용 하 여 제공 된 장치에서 Insider preview 등록 취소 이후 파란색 화면</span><span class="sxs-lookup"><span data-stu-id="db59c-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="db59c-216">이 문제는 Insider preview 빌드에 있었던 사용자에 게 영향을 주는 문제 이며, HoloLens 2를 새 insider preview 빌드로 reflashed 다음, 참가자 프로그램에서 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="db59c-217">이것은 **알려진 문제** 입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-217">This is a **known issue**.</span></span>

<span data-ttu-id="db59c-218">이는 다음에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-218">This does not affect:</span></span>
- <span data-ttu-id="db59c-219">Windows 참가자에 등록 되지 않은 사용자</span><span class="sxs-lookup"><span data-stu-id="db59c-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="db59c-220">참가자</span><span class="sxs-lookup"><span data-stu-id="db59c-220">Insiders:</span></span>
    - <span data-ttu-id="db59c-221">Insider 빌드된 버전이 18362 이므로 장치가 등록 된 경우</span><span class="sxs-lookup"><span data-stu-id="db59c-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="db59c-222">Insider 19041 빌드 되었으며 Insider program에 등록 된 상태를 유지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="db59c-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="db59c-223">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="db59c-223">Work-around:</span></span> 
- <span data-ttu-id="db59c-224">문제 방지</span><span class="sxs-lookup"><span data-stu-id="db59c-224">Avoid the issue</span></span> 
    - <span data-ttu-id="db59c-225">비-insider build를 플래시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-225">Flash a non-insider build.</span></span> <span data-ttu-id="db59c-226">정기 매월 업데이트 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="db59c-227">Insider Preview 유지</span><span class="sxs-lookup"><span data-stu-id="db59c-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="db59c-228">장치 경감 하기 위해</span><span class="sxs-lookup"><span data-stu-id="db59c-228">Reflash the device</span></span>

    1. <span data-ttu-id="db59c-229">연결 되지 않은 상태에서 전원을 끄고, [HoloLens 2를 수동으로 플래시 모드로](hololens-recovery.md) 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="db59c-230">그런 다음 볼륨을 유지 하는 동안 전원 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="db59c-231">PC에 연결 하 고 고급 복구 도우미를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="db59c-232">HoloLens 2를 기본 빌드로 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="db59c-233">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="db59c-234">OneDrive에서 그림을 자동으로 업로드 하지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="db59c-235">HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="db59c-236">이것은 **알려진 문제** 입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-236">This is a **known issue**.</span></span>

<span data-ttu-id="db59c-237">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="db59c-237">Workarounds:</span></span>

- <span data-ttu-id="db59c-238">비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="db59c-239">회사 또는 학교 계정 외에도 Microsoft 계정에 로그인 할 수 있습니다. OneDrive 앱은 이중 로그인을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="db59c-240">OneDrive 내의 Microsoft 계정 프로필에서 자동, 배경 카메라 롤 업로드를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="db59c-241">회사를 자동으로 업로드 하는 데 소비자 Microsoft 계정를 안전 하 게 사용할 수 없는 경우 OneDrive 앱에서 회사 또는 학교 계정에 사진을 수동으로 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="db59c-242">이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="db59c-243">단추를 선택 **+** 하 고 **업로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="db59c-244">**사진 > 카메라 롤** 로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="db59c-245">업로드 하려는 사진 또는 비디오를 선택 하 고 **열기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="db59c-246">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="db59c-247">HoloLens가 응답 하지 않거나 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="db59c-248">HoloLens가 시작 되지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="db59c-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="db59c-249">전원 단추 옆의 Led가 켜지 지 않거나 LED가 잠시 깜박일 경우 [HoloLens를 청구](hololens2-charging.md#charging-the-device) 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="db59c-250">전원 단추를 누를 때 Led가 켜져 있지만 디스플레이에 아무것도 표시 되지 않으면 [장치의 하드 리셋을 수행](hololens-recovery.md#hard-reset-procedure)합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="db59c-251">HoloLens가 고정 되거나 응답 하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="db59c-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="db59c-252">5 개의 Led가 모두 꺼집니다. 또는 Led가 응답 하지 않는 경우 15 초 동안 전원 단추를 눌러 HoloLens를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="db59c-253">HoloLens를 시작 하려면 전원 단추를 다시 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="db59c-254">이러한 단계가 작동 하지 않는 경우 [hololens 2 장치](hololens-recovery.md) 또는 [hololens (첫 번째 gen) 장치](hololens1-recovery.md) 를 복구 해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="db59c-255">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="db59c-256">"디스크 공간 부족" 오류</span><span class="sxs-lookup"><span data-stu-id="db59c-256">"Low Disk Space" error</span></span>

<span data-ttu-id="db59c-257">다음 중 하나 이상을 수행 하 여 저장소 공간을 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="db59c-258">사용 하지 않는 공간을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-258">Delete some unused spaces.</span></span> <span data-ttu-id="db59c-259">**설정** 시스템 공간으로 이동 하 여  >    >  더 이상 필요 하지 않은 공간을 선택 하 고 **제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="db59c-260">배치한 holograms 중 일부를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="db59c-261">사진 앱에서 일부 사진과 비디오를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="db59c-262">HoloLens에서 일부 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="db59c-263">**모든 앱** 목록에서 제거 하려는 앱을 탭 하 고 누른 다음 **제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="db59c-264">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="db59c-265">보정 실패</span><span class="sxs-lookup"><span data-stu-id="db59c-265">Calibration fails</span></span>

<span data-ttu-id="db59c-266">보정은 대부분의 사용자에 게 작동 하지만 보정에 실패 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="db59c-267">몇 가지 잠재적인 보정 실패 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="db59c-268">보정 대상을 따르지 않고 무시 가져오기</span><span class="sxs-lookup"><span data-stu-id="db59c-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="db59c-269">더티 또는 긁힌 장치 센터 또는 장치 센터의 위치가 올바르게 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="db59c-270">더티 또는 긁힌</span><span class="sxs-lookup"><span data-stu-id="db59c-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="db59c-271">특정 유형의 연락처 lenses 및 고 사양 (컬러 연락처 lenses, 일부 toric 연락처 lenses, IR 차단, 일부 높은 prescription, 선글라스 또는 비슷함)</span><span class="sxs-lookup"><span data-stu-id="db59c-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="db59c-272">더 많은 발음을 구성을 및 eyelash 확장</span><span class="sxs-lookup"><span data-stu-id="db59c-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="db59c-273">장치가 눈동자를 보지 못하도록 차단 하는 경우에는 머리카락 또는 두꺼운 eyeglass 프레임</span><span class="sxs-lookup"><span data-stu-id="db59c-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="db59c-274">좁은 눈동자, 긴 eyelashes, amblyopia, nystagmus, LASIK 또는 기타 아이 surgeries의 일부 사례와 같은 특정 눈동자 physiology, 아이 조건 또는 눈 수술</span><span class="sxs-lookup"><span data-stu-id="db59c-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="db59c-275">보정에 실패 한 경우 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="db59c-276">장치 센터 정리</span><span class="sxs-lookup"><span data-stu-id="db59c-276">Cleaning your device visor</span></span>
- <span data-ttu-id="db59c-277">고가를 청소 하는 중</span><span class="sxs-lookup"><span data-stu-id="db59c-277">Cleaning your glasses</span></span>
- <span data-ttu-id="db59c-278">최대한 눈에 가까운 장치 센터 푸시</span><span class="sxs-lookup"><span data-stu-id="db59c-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="db59c-279">방식으로 센터에서 개체 이동 (예: 헤어)</span><span class="sxs-lookup"><span data-stu-id="db59c-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="db59c-280">대화방에서 광원을 설정 하거나 직접 광선 이동</span><span class="sxs-lookup"><span data-stu-id="db59c-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="db59c-281">모든 지침을 따르고 보정을 계속 실패 하는 경우 설정에서 보정 프롬프트를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="db59c-282">[피드백 허브](hololens-feedback.md)에서 사용자 의견을 보내 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="db59c-283">또한 [이미지 색 또는 밝기 문제 해결](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) 에 대 한 관련 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="db59c-284">시스템에서 눈 위치를 계산 하므로 IPD 설정은 HoloLens 2에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="db59c-285">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="db59c-286">이전에 다른 사용자에 대해 HoloLens를 설정 했기 때문에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="db59c-287">[장치를 **깜박임 모드로** 전환 하 고 고급 복구 도우미를 사용](hololens-recovery.md#clean-reflash-the-device) 하 여 장치를 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="db59c-288">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="db59c-289">Unity가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-289">Unity isn't working</span></span>

- <span data-ttu-id="db59c-290">HoloLens 개발에 권장 되는 최신 버전의 Unity 용 [도구 설치](/windows/mixed-reality/install-the-tools) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="db59c-291">Unity HoloLens Technical Preview의 알려진 문제는 [HoloLens Unity 포럼](https://forum.unity3d.com/threads/known-issues.394627/)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="db59c-292">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="db59c-293">Windows 장치 포털이 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="db59c-294">혼합 현실 캡처의 실시간 미리 보기 기능은 몇 초 동안 대기 시간을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="db59c-295">가상 입력 페이지에서 가상 제스처 섹션 아래의 제스처 및 스크롤 컨트롤이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="db59c-296">이를 사용 하면 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-296">Using them will have no effect.</span></span> <span data-ttu-id="db59c-297">가상 입력 페이지의 가상 키보드가 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="db59c-298">설정에서 개발자 모드를 사용 하도록 설정한 후 장치 포털을 켜는 스위치를 사용 하도록 설정 하는 데 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="db59c-299">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="db59c-300">에뮬레이터</span><span class="sxs-lookup"><span data-stu-id="db59c-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="db59c-301">HoloLens 에뮬레이터가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="db59c-302">HoloLens 에뮬레이터에 대 한 정보는 개발자 설명서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="db59c-303">[HoloLens 에뮬레이터 문제 해결](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="db59c-304">Microsoft Store의 모든 앱은 에뮬레이터와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="db59c-305">예를 들어, 에뮬레이터에서 젊은 Conker 및 조각은 재생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="db59c-306">에뮬레이터에서는 PC 웹캠를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="db59c-307">Windows 장치 포털의 실시간 미리 보기 기능은 에뮬레이터에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="db59c-308">여전히 혼합 현실 비디오 및 이미지를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="db59c-309">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="db59c-310">HoloLens 2 에뮬레이터에서 키보드를 검색 하거나 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="db59c-311">*제공 예정*</span><span class="sxs-lookup"><span data-stu-id="db59c-311">*Coming soon*</span></span>

[<span data-ttu-id="db59c-312">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="db59c-313">음성 명령이 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-313">Voice commands aren't working</span></span>

<span data-ttu-id="db59c-314">Cortana가 음성 명령에 응답 하지 않는 경우 Cortana가 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="db59c-315">모든 앱 목록에서 **Cortana**  >  **메뉴**  >  **노트북**  >  **설정** 을 선택 하 여 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="db59c-316">설명 하는 내용에 대 한 자세한 내용은 [HoloLens에 음성 사용](hololens-cortana.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="db59c-317">HoloLens (첫 번째 gen)에서 기본 제공 음성 인식은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="db59c-318">항상 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-318">It is always turned on.</span></span> <span data-ttu-id="db59c-319">HoloLens 2에서는 장치를 설치 하는 동안 음성 인식과 Cortana를 모두 켤 지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="db59c-320">HoloLens 2가 음성에 응답 하지 않는 경우 음성 인식이 켜 졌는 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="db59c-321">**시작**  >  **설정**  >  **개인 정보**  >  **음성** 으로 이동 하 여 **음성 인식을** 켭니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="db59c-322">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="db59c-323">손으로 입력이 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-323">Hand input isn't working</span></span>

<span data-ttu-id="db59c-324">HoloLens가 손을 볼 수 있도록 하려면 제스처 프레임에 보관 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="db59c-325">혼합 현실 홈은 사용자가 손을 추적 하는 시기를 알 수 있는 피드백을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="db59c-326">사용자 의견은 HoloLens의 서로 다른 버전에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="db59c-327">HoloLens (첫 번째 gen)에서 응시 커서는 점에서 링으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="db59c-328">HoloLens 2에서는 fingertip 커서가 슬레이트에 가까이 있을 때 표시 되 고, 슬레이트가 더 멀리 있을 때 손 모양으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="db59c-329">많은 모던 앱은 혼합 현실 집과 비슷한 입력 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="db59c-330">[Hololens (첫 번째 gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) 및 [hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)에서 직접 입력을 사용 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="db59c-331">글러브를 입고 있는 경우 일부 종류의 장갑은 수동 추적에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="db59c-332">일반적인 예로는 검정 고무 장갑이 있습니다 .이는 적외선을 흡수 하 고 깊이 카메라에 의해 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="db59c-333">작업에 고무 장갑이 포함 되어 있는 경우 파란색 또는 회색 등의 더 밝은 색을 사용해 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="db59c-334">또 다른 예로는 긴 baggy 장갑이 있습니다 .이를 통해 손 모양에는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="db59c-335">최상의 결과를 위해 가능한 한 폼 피팅으로 글러브를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="db59c-336">센터에 지문 또는 얼룩이 있는 경우 HoloLens와 함께 제공 되는 마이크로 파이버 클리닝 천을 사용 하 여 센터를 천천히 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="db59c-337">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="db59c-338">Wi-Fi에 연결할 수 없음</span><span class="sxs-lookup"><span data-stu-id="db59c-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="db59c-339">HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="db59c-340">Wi-Fi 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="db59c-341">확인 하려면 시작 제스처를 사용 하 고 **설정**  >  **네트워크 &amp; 인터넷**  >  **wi-fi** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="db59c-342">Wi-Fi 설정 되어 있으면 해제 한 후 다시 설정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="db59c-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="db59c-343">라우터 또는 액세스 지점에 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="db59c-344">Wi-Fi 라우터를 다시 시작한 후 [HoloLens를 다시 시작](hololens-recovery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="db59c-345">다시 연결해 보세요.</span><span class="sxs-lookup"><span data-stu-id="db59c-345">Try connecting again.</span></span>
- <span data-ttu-id="db59c-346">이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="db59c-347">이 정보는 제조업체 웹 사이트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="db59c-348">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="db59c-349">Bluetooth 장치가 페어링 되지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="db59c-350">[Bluetooth 장치를 페어링 하는](hololens-connect-devices.md)데 문제가 있는 경우 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="db59c-351">**설정** 장치로 이동 하 여  >  Bluetooth가 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="db59c-352">이 경우 다시 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="db59c-353">Bluetooth 장치가 완전히 충전 되어 있거나 새 배터리가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="db59c-354">그래도 연결할 수 없으면 HoloLens를 [다시 시작](hololens-recovery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="db59c-355">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="db59c-356">USB-C 마이크가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="db59c-357">일부 USB-C 마이크는 마이크 *와* 스피커로 잘못 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="db59c-358">이는 마이크와 관련 된 문제 이며 HoloLens와는 관련 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="db59c-359">이러한 마이크 중 하나를 HoloLens에 꽂으면 소리가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="db59c-360">다행히 간단한 해결 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="db59c-361">**설정**  ->  **시스템**  ->  **소리** 에서 기본 제공 스피커 **(아날로그 기능 오디오 드라이버)** 를 **기본 장치로** 명시적으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="db59c-362">HoloLens는 마이크가 제거 되 고 나중에 다시 연결 된 경우에도이 설정을 명심 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB 문제 해결-C 마이크](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="db59c-364">설정에서 사용 가능으로 나열 된 장치가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="db59c-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="db59c-365">HoloLens (첫 번째 gen)는 Bluetooth 오디오 프로필을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="db59c-366">스피커 및 헤드셋과 같은 Bluetooth 오디오 장치는 HoloLens 설정에서 사용할 수 있는 것 처럼 보일 수 있지만 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="db59c-367">HoloLens 2는 스테레오 재생을 위한 Bluetooth A2DP 오디오 프로필을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="db59c-368">Bluetooth 장치에서 마이크 캡처를 사용 하도록 설정 하는 Bluetooth 핸 무료 프로필은 HoloLens 2에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="db59c-369">Bluetooth 장치를 사용 하는 데 문제가 있는 경우 지원 되는 장치 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="db59c-370">지원 되는 장치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-370">Supported devices include the following:</span></span>

- <span data-ttu-id="db59c-371">영어 (holographic) 키보드를 사용 하는 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="db59c-372">Bluetooth 마우스.</span><span class="sxs-lookup"><span data-stu-id="db59c-372">Bluetooth mice.</span></span>
- <span data-ttu-id="db59c-373">[HoloLens clicker](hololens1-clicker.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="db59c-374">다른 Bluetooth HID 및 GATT 장치를 HoloLens와 함께 쌍으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="db59c-375">그러나 실제로 장치를 사용 하려면 Microsoft Store에서 해당 하는 관련 앱을 설치 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db59c-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="db59c-376">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="db59c-376">Back to list</span></span>](#list)
