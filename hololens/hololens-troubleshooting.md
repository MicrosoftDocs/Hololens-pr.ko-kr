---
title: HoloLens 디바이스 문제 해결
description: 디바이스 문제를 HoloLens 및 문제 해결 기술에 대한 가장 일반적인 솔루션을 최신 상태로 유지합니다.
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
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635452"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="09469-104">디바이스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="09469-104">Device Troubleshooting</span></span>

<span data-ttu-id="09469-105">이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="09469-106">문제 해결 절차를 시작하기 전에 가능한 경우 디바이스에 배터리 용량의 **20~40%가** 청구되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="09469-107">전원 단추 아래에 있는 [배터리 표시등은](hololens2-setup.md#lights-that-indicate-the-battery-level) 디바이스에 로그인하지 않고 배터리 용량을 확인하는 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="09469-108">**알려진 문제**</span><span class="sxs-lookup"><span data-stu-id="09469-108">**Known Issues**</span></span>
- [<span data-ttu-id="09469-109">Remote Assist 비디오가 20분 후에 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="09469-110">자동 로그인에서 로그인 요청</span><span class="sxs-lookup"><span data-stu-id="09469-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="09469-111">Microsoft Edge 시작하지 못함</span><span class="sxs-lookup"><span data-stu-id="09469-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="09469-112">키보드가 특수 문자로 전환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="09469-113">잠긴 파일을 다운로드해도 오류가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="09469-114">파일 업로드/다운로드 시간 장치 포털</span><span class="sxs-lookup"><span data-stu-id="09469-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="09469-115">Insider 빌드로 깜박이는 디바이스의 Insider 미리 보기에서 등록을 취소한 후의 파란색 화면</span><span class="sxs-lookup"><span data-stu-id="09469-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="09469-116">OneDrive 사진을 자동으로 업로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="09469-117">**일반**</span><span class="sxs-lookup"><span data-stu-id="09469-117">**General**</span></span>
- [<span data-ttu-id="09469-118">HoloLens 응답하지 않거나 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="09469-119">"디스크 공간 부족" 오류</span><span class="sxs-lookup"><span data-stu-id="09469-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="09469-120">보정 실패</span><span class="sxs-lookup"><span data-stu-id="09469-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="09469-121">내 HoloLens 이전에 다른 사람을 위해 설정되었으므로 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="09469-122">Unity가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="09469-123">Windows 장치 포털 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="09469-124">HoloLens Emulator 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="09469-125">**입력**</span><span class="sxs-lookup"><span data-stu-id="09469-125">**Input**</span></span>
- [<span data-ttu-id="09469-126">음성 명령이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="09469-127">손 입력이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="09469-128">**연결**</span><span class="sxs-lookup"><span data-stu-id="09469-128">**Connectivity**</span></span>
- [<span data-ttu-id="09469-129">Wi-Fi에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="09469-130">**외부 디바이스**</span><span class="sxs-lookup"><span data-stu-id="09469-130">**External Devices**</span></span> 
- [<span data-ttu-id="09469-131">Bluetooth 디바이스가 페어링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="09469-132">USB-C 마이크가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="09469-133">설정 사용할 수 있는 것으로 나열된 디바이스가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="09469-134">Remote Assist 비디오가 20분 후에 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="09469-135">이 문제에 대한 수정이 있는 최신 버전의 Remote Assist 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="09469-136">이 문제를 방지하려면 Remote Assist 최신 버전으로 [업데이트하세요.](holographic-store-apps.md#update-apps)</span><span class="sxs-lookup"><span data-stu-id="09469-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="09469-137">이 알려진 문제의 심각도로 인해 Windows Holographic 버전 21H1의 가용성을 일시적으로 일시 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="09469-138">이제 21H1 빌드를 다시 사용할 수 있으므로 디바이스가 다시 최신 21H1 빌드로 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="09469-139">[Windows Holographic 버전 21H1의](hololens-release-notes.md#windows-holographic-version-21h1)최신 릴리스에서는 Remote Assist 일부 사용자가 20분 넘게 통화하는 동안 비디오 중지를 경험했습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="09469-140">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="09469-141">해결 방법</span><span class="sxs-lookup"><span data-stu-id="09469-141">Workarounds</span></span>

<span data-ttu-id="09469-142">최신 빌드로 Remote Assist 업데이트할 수 없는 경우 다음 해결 방법을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="09469-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="09469-143">호출 간에 다시 시작</span><span class="sxs-lookup"><span data-stu-id="09469-143">Restart in between calls</span></span>

<span data-ttu-id="09469-144">호출이 20분을 초과하고 이 문제가 발생하는 경우 디바이스를 다시 부팅해 보세요.</span><span class="sxs-lookup"><span data-stu-id="09469-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="09469-145">Remote Assist 호출 사이에 디바이스를 다시 부팅하면 디바이스가 새로 고쳐지고 다시 양호한 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="09469-146">Windows Holographic에서 디바이스를 신속하게 다시 시작하려면 [버전 21H1에서](hololens-release-notes.md#windows-holographic-version-21h1) 시작 메뉴를 열고 사용자 아이콘을 선택한 다음, **다시 시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="09469-147">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="09469-148">자동 로그인에서 로그인 요청</span><span class="sxs-lookup"><span data-stu-id="09469-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="09469-149">설정 계정 로그인 옵션 **->** 및 필수에서 값을 안 됨으로 설정하여 자동으로  ->    ->   로그인하도록 HoloLens 2  디바이스를 구성할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="09469-150">일부 사용자는 기능 업데이트와 같이 상당히 큰 업데이트로 디바이스를 업데이트할 때 디바이스에 다시 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="09469-151">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-151">This is a **known issue**.</span></span>

<span data-ttu-id="09469-152">이 문제가 발생할 수 있는 경우의 예:</span><span class="sxs-lookup"><span data-stu-id="09469-152">Example of when this could occur:</span></span>

- <span data-ttu-id="09469-153">Windows Holographic 버전 2004(빌드 19041.xxxx)에서 Windows Holographic 버전 21H1로 디바이스 업데이트(빌드 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="09469-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="09469-154">동일한 주 빌드에서 대규모 업데이트를 사용하도록 디바이스 업데이트(예: Windows Holographic 버전 2004에서 Windows Holographic 버전 20H2로 업데이트)</span><span class="sxs-lookup"><span data-stu-id="09469-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="09469-155">공장 이미지에서 최신 이미지로 디바이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="09469-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="09469-156">다음 중에는 이 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-156">This should not occur during:</span></span>

- <span data-ttu-id="09469-157">월간 서비스 업데이트를 받는 디바이스</span><span class="sxs-lookup"><span data-stu-id="09469-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="09469-158">메서드 해결:</span><span class="sxs-lookup"><span data-stu-id="09469-158">Work around methods:</span></span>

- <span data-ttu-id="09469-159">PIN, 암호, 아이리스, 웹 인증 또는 FIDO2 키와 같은 로그인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="09469-160">디바이스 PIN을 기억할 수 없고 다른 인증 방법을 사용할 수 없는 경우 사용자는 [수동 리플래시 모드 를](hololens-recovery.md#manual-procedure)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="09469-161">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="09469-162">Microsoft Edge 시작하지 못함</span><span class="sxs-lookup"><span data-stu-id="09469-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="09469-163">이 문제는 원래 Microsoft Edge 배송 버전을 염두에 두고 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="09469-164">이 문제는 [새 Microsoft Edge](hololens-new-edge.md)해결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="09469-165">그렇지 않은 경우 피드백을 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="09469-166">일부 고객은 Microsoft Edge 시작하지 못하는 문제를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="09469-167">이러한 고객의 경우 다시 부팅을 통해 문제가 지속되며 Windows 또는 애플리케이션 업데이트로 해결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="09469-168">이 문제가 발생하고 [Windows](hololens-updates.md#manually-check-for-updates)최신인지 확인한 경우 Windows 업데이트 다운로드, 설치 및 구성을 > 설치 및 업데이트 범주 및 하위 범주를 사용하여 피드백 허브 [앱에서](hololens-feedback.md) 버그를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="09469-169">지금까지 문제의 근본 원인을 알 수 없으므로 알려진 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="09469-170">피드백 허브 통해 버그를 신고하면 조사에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="09469-171">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-171">This is a **known issue**.</span></span>

[<span data-ttu-id="09469-172">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="09469-173">키보드가 특수 문자로 전환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="09469-174">OOBE 중에는 사용자가 직장 또는 학교 계정을 선택하고 암호를 입력한 후 &123 단추를 탭하여 키보드의 특수 문자로 전환하려고 하면 특수 문자로 변경되지 않는 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="09469-175">이것은 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-175">This is a **known issue**.</span></span>

<span data-ttu-id="09469-176">해결 작업:</span><span class="sxs-lookup"><span data-stu-id="09469-176">Work-arounds:</span></span>
-   <span data-ttu-id="09469-177">키보드를 닫고 텍스트 필드를 탭하여 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09469-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="09469-178">암호를 잘못 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-178">Incorrectly enter your password.</span></span> <span data-ttu-id="09469-179">다음에 키보드가 다시 시작되면 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="09469-180">웹 인증에서 키보드를 닫고 **다른 디바이스에서 로그인을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="09469-181">숫자만 입력하는 경우 사용자는 특정 키를 누르고 확장된 메뉴를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="09469-182">USB 키보드 사용.</span><span class="sxs-lookup"><span data-stu-id="09469-182">Using a USB keyboard.</span></span>

<span data-ttu-id="09469-183">이는 다음에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-183">This does not affect:</span></span>
- <span data-ttu-id="09469-184">개인 계정을 사용하도록 선택한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="09469-185">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="09469-186">잠긴 파일을 다운로드해도 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="09469-187">이는 Windows Insider 빌드 버전 20348.1403에서 해결된 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="09469-188">Windows Holographic의 이전 빌드에서 잠긴 파일을 다운로드하려고 할 때 결과는 HTTP 오류 페이지가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="09469-189">Windows Holographic 버전 21H1 업데이트에서 잠긴 파일을 다운로드하려고 시도하면 아무 것도 표시되지 않습니다. 파일이 다운로드되지 않고 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="09469-190">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="09469-191">파일 업로드/다운로드 시간 장치 포털</span><span class="sxs-lookup"><span data-stu-id="09469-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="09469-192">이는 Windows Insider 빌드 버전 20348.1403에서 해결된 **알려진 문제입니다.**</span><span class="sxs-lookup"><span data-stu-id="09469-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="09469-193">이전에 해결 방법의 일부로 SSL 연결을 사용하지 않도록 설정한 경우 다시 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="09469-194">일부 고객은 파일을 업로드하거나 다운로드하려고 할 때 작업이 중단된 다음 시간 부족하거나 완료되지 않을 수 있음을 발견했습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="09469-195">이는 알려진['파일 잠김' 문제와는](#downloading-locked-files-doesnt-error) 별개입니다. 이는 Holographic 버전 2004, 20H2 및 21H1 시장 내 빌드에 Windows 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="09469-196">이 문제는 장치 포털 특정 요청을 처리하는 버그로 인해 발생했으며, https를 사용할 때 가장 일관되게 발생합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="09469-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="09469-197">해결 방법</span><span class="sxs-lookup"><span data-stu-id="09469-197">Workaround</span></span>

<span data-ttu-id="09469-198">Wi-Fi 및 UsbNcm에도 동일하게 적용되는 이 해결 방법은 "SSL 연결"에서 "필수" 옵션을 사용하지 않도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="09469-199">이렇게 하려면 장치 포털 **시스템** 으로 이동하여 **기본 설정** 페이지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="09469-200">디바이스 **보안** 섹션에서 **SSL 연결** 를 찾은 다음, **필수** 를 사용하지 않도록 설정하려면 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="09469-201">그런 다음 사용자는 https://(IP 주소)가 아닌 http://로 이동 하 고 파일 업로드 및 다운로드와 같은 기능이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="09469-202">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="09469-203">Insider build를 사용 하 여 제공 된 장치에서 Insider preview 등록 취소 이후 파란색 화면</span><span class="sxs-lookup"><span data-stu-id="09469-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="09469-204">이 문제는 insider preview 빌드에 있었던 사용자에 게 영향을 주는 문제 이며, 새 insider preview 빌드를 사용 하 여 HoloLens 2를 reflashed 다음, 참가자 프로그램에서 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="09469-205">이것은 **알려진 문제** 입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-205">This is a **known issue**.</span></span>

<span data-ttu-id="09469-206">이는 다음에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-206">This does not affect:</span></span>
- <span data-ttu-id="09469-207">Windows Insider에 등록 되지 않은 사용자</span><span class="sxs-lookup"><span data-stu-id="09469-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="09469-208">참가자</span><span class="sxs-lookup"><span data-stu-id="09469-208">Insiders:</span></span>
    - <span data-ttu-id="09469-209">Insider 빌드된 버전이 18362 이므로 장치가 등록 된 경우</span><span class="sxs-lookup"><span data-stu-id="09469-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="09469-210">Insider 19041 빌드 되었으며 Insider program에 등록 된 상태를 유지 하는 경우</span><span class="sxs-lookup"><span data-stu-id="09469-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="09469-211">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="09469-211">Work-around:</span></span> 
- <span data-ttu-id="09469-212">문제 방지</span><span class="sxs-lookup"><span data-stu-id="09469-212">Avoid the issue</span></span> 
    - <span data-ttu-id="09469-213">비-insider build를 플래시 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-213">Flash a non-insider build.</span></span> <span data-ttu-id="09469-214">정기 매월 업데이트 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="09469-215">Insider Preview 유지</span><span class="sxs-lookup"><span data-stu-id="09469-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="09469-216">장치 경감 하기 위해</span><span class="sxs-lookup"><span data-stu-id="09469-216">Reflash the device</span></span>

    1. <span data-ttu-id="09469-217">연결 되지 않은 상태에서 전원을 끄고 수동으로 [HoloLens 2를 깜박임 모드로](hololens-recovery.md) 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="09469-218">그런 다음 볼륨을 유지 하는 동안 전원 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="09469-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="09469-219">PC에 커넥트 하 고 고급 복구 도우미를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09469-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="09469-220">HoloLens 2를 기본 빌드로 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="09469-221">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="09469-222">자동으로 그림을 업로드 하지 OneDrive</span><span class="sxs-lookup"><span data-stu-id="09469-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="09469-223">HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="09469-224">이것은 **알려진 문제** 입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-224">This is a **known issue**.</span></span>

<span data-ttu-id="09469-225">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="09469-225">Workarounds:</span></span>

- <span data-ttu-id="09469-226">비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09469-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="09469-227">회사 또는 학교 계정 외에도 Microsoft 계정에 로그인 할 수 있습니다. OneDrive 앱은 이중 로그인을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="09469-228">OneDrive 내의 Microsoft 계정 프로필에서 자동, 배경 카메라 롤 업로드를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="09469-229">회사를 자동으로 업로드 하는 데 소비자 Microsoft 계정를 안전 하 게 사용할 수 없는 경우 OneDrive 앱에서 회사 또는 학교 계정에 사진을 수동으로 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="09469-230">이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="09469-231">단추를 선택 **+** 하 고 **업로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="09469-232">**사진 > 카메라 롤** 로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="09469-233">업로드 하려는 사진 또는 비디오를 선택 하 고 **열기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="09469-234">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="09469-235">HoloLens 응답 하지 않거나 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="09469-236">HoloLens 시작 되지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="09469-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="09469-237">전원 단추 옆의 Led가 켜지 지 않거나 LED가 잠시 깜박일 경우 [HoloLens 요금을 청구](hololens2-charging.md#charging-the-device) 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="09469-238">전원 단추를 누를 때 Led가 켜져 있지만 디스플레이에 아무것도 표시 되지 않으면 [장치의 하드 리셋을 수행](hololens-recovery.md#hard-reset-procedure)합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="09469-239">HoloLens 고정 되거나 응답 하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="09469-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="09469-240">5 개의 led가 모두 꺼질 때까지 전원 단추를 누르거나 led가 응답 하지 않는 경우 15 초 동안 HoloLens를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="09469-241">HoloLens를 시작 하려면 전원 단추를 다시 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="09469-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="09469-242">이러한 단계가 작동 하지 않는 경우 [HoloLens 2 장치](hololens-recovery.md) 또는 [HoloLens (첫 번째 gen) 장치](hololens1-recovery.md) 를 복구 해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="09469-243">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="09469-244">"디스크 공간 부족" 오류</span><span class="sxs-lookup"><span data-stu-id="09469-244">"Low Disk Space" error</span></span>

<span data-ttu-id="09469-245">다음 중 하나 이상을 수행 하 여 저장소 공간을 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="09469-246">사용 하지 않는 공간을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-246">Delete some unused spaces.</span></span> <span data-ttu-id="09469-247">**설정** 시스템 공간으로 이동 하 여  >    >  더 이상 필요 하지 않은 공간을 선택 하 고 **제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="09469-248">배치한 holograms 중 일부를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="09469-249">사진 앱에서 일부 그림과 비디오를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="09469-250">HoloLens에서 일부 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="09469-251">**모든 앱** 목록에서 제거 하려는 앱을 탭 하 고 누른 다음 **제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="09469-252">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="09469-253">보정 실패</span><span class="sxs-lookup"><span data-stu-id="09469-253">Calibration fails</span></span>

<span data-ttu-id="09469-254">보정은 대부분의 사용자에 게 작동 하지만 보정에 실패 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="09469-255">몇 가지 잠재적인 보정 실패 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="09469-256">보정 대상을 따르지 않고 무시 가져오기</span><span class="sxs-lookup"><span data-stu-id="09469-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="09469-257">더티 또는 긁힌 장치 센터 또는 장치 센터의 위치가 올바르게 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="09469-258">더티 또는 긁힌</span><span class="sxs-lookup"><span data-stu-id="09469-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="09469-259">특정 유형의 연락처 lenses 및 고 사양 (컬러 연락처 lenses, 일부 toric 연락처 lenses, IR 차단, 일부 높은 prescription, 선글라스 또는 비슷함)</span><span class="sxs-lookup"><span data-stu-id="09469-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="09469-260">더 많은 발음을 구성을 및 eyelash 확장</span><span class="sxs-lookup"><span data-stu-id="09469-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="09469-261">장치가 눈동자를 보지 못하도록 차단 하는 경우에는 머리카락 또는 두꺼운 eyeglass 프레임</span><span class="sxs-lookup"><span data-stu-id="09469-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="09469-262">좁은 눈동자, 긴 eyelashes, amblyopia, nystagmus, LASIK 또는 기타 아이 surgeries의 일부 사례와 같은 특정 눈동자 physiology, 아이 조건 또는 눈 수술</span><span class="sxs-lookup"><span data-stu-id="09469-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="09469-263">보정에 실패 한 경우 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="09469-264">장치 센터 정리</span><span class="sxs-lookup"><span data-stu-id="09469-264">Cleaning your device visor</span></span>
- <span data-ttu-id="09469-265">고가를 청소 하는 중</span><span class="sxs-lookup"><span data-stu-id="09469-265">Cleaning your glasses</span></span>
- <span data-ttu-id="09469-266">최대한 눈에 가까운 장치 센터 푸시</span><span class="sxs-lookup"><span data-stu-id="09469-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="09469-267">방식으로 센터에서 개체 이동 (예: 헤어)</span><span class="sxs-lookup"><span data-stu-id="09469-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="09469-268">대화방에서 광원을 설정 하거나 직접 광선 이동</span><span class="sxs-lookup"><span data-stu-id="09469-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="09469-269">모든 지침을 따르고 보정에 여전히 오류가 발생 한 경우 설정에서 보정 프롬프트를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="09469-270">[피드백 허브](hololens-feedback.md)에서 사용자 의견을 보내 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="09469-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="09469-271">또한 [이미지 색 또는 밝기 문제 해결](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) 에 대 한 관련 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="09469-272">IPD 설정은 시스템에서 눈 위치를 계산 하므로 HoloLens 2에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="09469-273">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="09469-274">이전에 다른 사용자에 대해 HoloLens를 설정 했기 때문에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="09469-275">[장치를 **깜박임 모드로** 전환 하 고 고급 복구 도우미를 사용](hololens-recovery.md#clean-reflash-the-device) 하 여 장치를 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="09469-276">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="09469-277">Unity가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-277">Unity isn't working</span></span>

- <span data-ttu-id="09469-278">HoloLens 개발에 권장 되는 최신 버전의 Unity 용 [도구 설치](/windows/mixed-reality/install-the-tools) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="09469-279">unity HoloLens Technical Preview의 알려진 문제는 [HoloLens unity 포럼](https://forum.unity3d.com/threads/known-issues.394627/)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="09469-280">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="09469-281">Windows 장치 포털이 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="09469-282">혼합 현실 캡처의 실시간 미리 보기 기능은 몇 초 동안 대기 시간을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="09469-283">가상 입력 페이지에서 가상 제스처 섹션 아래의 제스처 및 스크롤 컨트롤이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="09469-284">이를 사용 하면 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-284">Using them will have no effect.</span></span> <span data-ttu-id="09469-285">가상 입력 페이지의 가상 키보드가 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="09469-286">설정에서 개발자 모드를 사용 하도록 설정한 후 장치 포털을 켜는 스위치를 사용 하도록 설정 하는 데 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="09469-287">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="09469-288">HoloLens Emulator 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="09469-289">HoloLens 에뮬레이터에 대 한 정보는 개발자 설명서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="09469-290">[HoloLens 에뮬레이터 문제 해결을](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="09469-291">Microsoft Store의 모든 앱은 에뮬레이터와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="09469-292">예를 들어, 에뮬레이터에서 젊은 Conker 및 조각은 재생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="09469-293">Emulator PC 웹캠을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="09469-294">Windows 장치 포털의 실시간 미리 보기 기능은 에뮬레이터에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="09469-295">여전히 혼합 현실 비디오 및 이미지를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="09469-296">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="09469-297">음성 명령이 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-297">Voice commands aren't working</span></span>

<span data-ttu-id="09469-298">Cortana 음성 명령에 응답 하지 않는 경우 Cortana 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="09469-299">모든 앱 목록에서 **Cortana**  >  **Menu**  >  **노트북**  >  **설정** 를 선택 하 여 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="09469-300">말할 수 있는 내용에 대 한 자세한 내용은 [HoloLens에 음성 사용](hololens-cortana.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="09469-301">HoloLens (첫 번째 gen)에서는 기본 제공 음성 인식을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="09469-302">항상 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-302">It is always turned on.</span></span> <span data-ttu-id="09469-303">HoloLens 2에서 장치를 설치 하는 동안 음성 인식 및 Cortana를 모두 켤 지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="09469-304">HoloLens 2 음성에 응답 하지 않는 경우 음성 인식이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="09469-305">**시작**  >  **설정**  >  **개인 정보**  >  **음성** 으로 이동 하 여 **음성 인식을** 켭니다.</span><span class="sxs-lookup"><span data-stu-id="09469-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="09469-306">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="09469-307">손으로 입력이 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-307">Hand input isn't working</span></span>

<span data-ttu-id="09469-308">HoloLens 사용자의 손을 볼 수 있도록 하려면 제스처 프레임에 보관 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="09469-309">혼합 현실 홈은 사용자가 손을 추적 하는 시기를 알 수 있는 피드백을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="09469-310">사용자 의견은 다양 한 버전의 HoloLens에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="09469-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="09469-311">HoloLens (첫 번째 gen)에서 응시 커서는 점에서 링으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="09469-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="09469-312">HoloLens 2에서 손 모양이 슬레이트에 가까이 있을 때 fingertip 커서가 나타나고 슬레이트이 더 멀리 떨어져 있을 때 손 모양으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="09469-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="09469-313">많은 모던 앱은 혼합 현실 집과 비슷한 입력 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="09469-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="09469-314">[HoloLens (첫 번째 gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) 및 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)에서 직접 입력을 사용 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="09469-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="09469-315">글러브를 입고 있는 경우 일부 종류의 장갑은 수동 추적에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="09469-316">일반적인 예로는 검정 고무 장갑이 있습니다 .이는 적외선을 흡수 하 고 깊이 카메라에 의해 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="09469-317">작업에 고무 장갑이 포함 되어 있는 경우 파란색 또는 회색 등의 더 밝은 색을 사용해 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="09469-318">또 다른 예로는 긴 baggy 장갑이 있습니다 .이를 통해 손 모양에는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="09469-319">최상의 결과를 위해 가능한 한 폼 피팅으로 글러브를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="09469-320">센터에 지문 또는 얼룩이 있는 경우 HoloLens와 함께 제공 되는 마이크로 파이버 클리닝 천을 사용 하 여 센터를 천천히 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="09469-321">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="09469-322">Wi-Fi에 연결할 수 없음</span><span class="sxs-lookup"><span data-stu-id="09469-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="09469-323">HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="09469-324">Wi-Fi 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="09469-325">확인 하려면 시작 제스처를 사용 하 **설정**  >  **네트워크 &amp; 인터넷**  >  **wi-fi** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="09469-326">Wi-Fi 설정 되어 있으면 해제 한 후 다시 설정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09469-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="09469-327">라우터 또는 액세스 지점에 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="09469-328">Wi-Fi 라우터를 다시 시작한 다음 [HoloLens를 다시 시작](hololens-recovery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="09469-329">다시 연결해 보세요.</span><span class="sxs-lookup"><span data-stu-id="09469-329">Try connecting again.</span></span>
- <span data-ttu-id="09469-330">이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="09469-331">이 정보는 제조업체 웹 사이트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="09469-332">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="09469-333">Bluetooth 장치가 페어링 하지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="09469-334">[Bluetooth 장치를 페어링 하는](hololens-connect-devices.md)데 문제가 있는 경우 다음을 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="09469-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="09469-335">**설정** 장치로 이동 하 여  >  Bluetooth 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="09469-336">이 경우 다시 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="09469-337">Bluetooth 장치가 완전히 충전 되어 있거나 새 배터리가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="09469-338">그래도 연결할 수 없으면 HoloLens를 [다시 시작](hololens-recovery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="09469-339">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="09469-340">USB-C 마이크가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="09469-341">일부 USB-C 마이크는 마이크 *와* 스피커로 잘못 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="09469-342">이는 HoloLens 아닌 마이크의 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="09469-343">이러한 마이크 중 하나를 HoloLens에 연결 하는 경우 소리가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="09469-344">다행히 간단한 해결 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="09469-345">**설정**  ->  **시스템**  ->  **소리** 에서 기본 제공 스피커 **(아날로그 기능 오디오 드라이버)** 를 **기본 장치로** 명시적으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="09469-346">마이크가 제거 되 고 나중에 다시 연결 된 경우에도이 설정을 기억할 HoloLens.</span><span class="sxs-lookup"><span data-stu-id="09469-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB 문제 해결-C 마이크](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="09469-348">설정에서 사용 가능으로 나열 된 장치가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="09469-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="09469-349">HoloLens (첫 번째 gen) Bluetooth 오디오 프로필을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="09469-350">스피커 및 헤드셋과 같은 Bluetooth 오디오 장치는 HoloLens 설정에서 사용할 수 있는 것 처럼 보일 수 있지만 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="09469-351">HoloLens 2은 스테레오 재생을 위한 Bluetooth A2DP 오디오 프로필을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="09469-352">Bluetooth 주변 장치에서 마이크 캡처가 가능 하도록 하는 Bluetooth 손 무료 프로필은 HoloLens 2에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="09469-353">Bluetooth 장치를 사용 하는 데 문제가 있는 경우 지원 되는 장치 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09469-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="09469-354">지원 되는 장치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-354">Supported devices include the following:</span></span>

- <span data-ttu-id="09469-355">영어 Bluetooth 키보드 (holographic 키보드를 사용 하는 모든 곳에서 사용할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="09469-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="09469-356">Bluetooth 마우스.</span><span class="sxs-lookup"><span data-stu-id="09469-356">Bluetooth mice.</span></span>
- <span data-ttu-id="09469-357">[HoloLens clicker](hololens1-clicker.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="09469-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="09469-358">다른 Bluetooth HID 및 GATT 장치를 HoloLens와 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="09469-359">그러나 실제로 장치를 사용 하려면 Microsoft Store에서 해당 하는 관련 앱을 설치 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09469-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="09469-360">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="09469-360">Back to list</span></span>](#list)
