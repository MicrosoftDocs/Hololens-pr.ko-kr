---
title: HoloLens 1 다시 시작, 초기화 또는 복구
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Windows Device Recovery Tool을 사용하여 이미지를 HoloLens 1세대로 플래시하는 방법
keywords: 사용 방법, 다시 부팅, 초기화, 복구, 하드 초기화, 소프트 초기화, 전원 주기, HoloLens, 종료, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 837a019f110a58c490618d3d5c47e83e58231d18
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828583"
---
# <span data-ttu-id="39197-104">HoloLens 1세대 다시 시작, 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="39197-104">Restart, reset, or recover HoloLens 1st Gen</span></span>

<span data-ttu-id="39197-105">HoloLens에 문제가 발생한 경우 장치 복구를 사용하여 다시 시작하거나 초기화 또는 리플래시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="39197-106">HoloLens가 제대로 작동하지 않는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="39197-107">이 문서에서는 권장되는 복구 단계를 연속해서 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="39197-108">HoloLens 2를 복구하려면 프로세스에 차이가 있으므로 [](https://docs.microsoft.com/hololens/hololens-recovery)HoloLens 2복구[ 페이지를 확인하세요.](https://docs.microsoft.com/hololens/hololens-recovery)</span><span class="sxs-lookup"><span data-stu-id="39197-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="39197-109">이 문서에서는 HoloLens 장치 및 소프트웨어에 중점을 두며 홀로그램이 제대로 보이지 않는 경우 [이 문서](hololens-environment-considerations.md)에서 홀로그램 품질을 개선하는 환경적 요인에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="39197-110">다시 시작</span><span class="sxs-lookup"><span data-stu-id="39197-110">Restart</span></span>

### <span data-ttu-id="39197-111">Cortana를 사용하여 안전하게 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="39197-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="39197-112">HoloLens를 다시 시작하는 가장 안전한 방법은 Cortana를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39197-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="39197-113">이는 일반적으로 HoloLens에 문제가 발생했을 때 쉽게 해 볼 수 있는 첫 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="39197-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="39197-114">일부 장치에서는 Cortana를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="39197-115">Cortana는 모든 HoloLens (1세대) 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="39197-116">Cortana는 Windows Holograpic, 버전 2004 업데이트 이전 빌드의HoloLens 2 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="39197-117">장치를 착용합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-117">Put on your device</span></span>
1. <span data-ttu-id="39197-118">전원이 켜져 있는지, 사용자가 로그인했는지, 장치에서 잠금 해제를 위해 암호 입력을 기다리고 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="39197-119">‘안녕 코타나, 재부팅’ 또는 ‘안녕 코타나, 다시 시작’이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="39197-120">Cortana가 인식 후 사용자에게 확인을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="39197-121">Cortana가 질문을 마친 후 사용자의 응답을 듣고 있다는 것을 나타내는 소리가 재생될 때까지 기다린 후 ‘예’라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="39197-122">이제 장치가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="39197-122">The device will now restart.</span></span>

### <span data-ttu-id="39197-123">전원 버튼을 사용하여 안전하게 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="39197-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="39197-124">여전히 장치를 다시 시작할 수 없는 경우 전원 버튼을 사용하여 다시 시작할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="39197-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="39197-125">전원 버튼을 5초간 길게 누릅니다. </span><span class="sxs-lookup"><span data-stu-id="39197-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="39197-126">1초 후 5개의 LED가 모두 켜지고 오른쪽에서 왼쪽으로 천천히 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="39197-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="39197-127">5초 후에는 모든 LED가 꺼지며 종료 명령이 성공적으로 실행되었다는 것을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39197-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="39197-128">모든 LED가 꺼지면 바로 버튼을 놓는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="39197-129">종료가 제대로 완료될 때까지 1분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="39197-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="39197-130">디스플레이가 꺼져 있는 경우에도 종료가 계속 진행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="39197-131">전원 버튼을 1초간 길게 눌러 장치를 다시 켭니다.</span><span class="sxs-lookup"><span data-stu-id="39197-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="39197-132">Windows 장치 포털을 사용하여 안전하게 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="39197-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="39197-133">이를 수행하려면 HoloLens가 개발자 장치로 구성되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="39197-134">[Windows 장치 포털에 대해 자세히 알아보기](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="39197-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="39197-135">이전 절차로 다시 시작할 수 없는 경우 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용하여 장치를 다시 시작해 보세요.</span><span class="sxs-lookup"><span data-stu-id="39197-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="39197-136">오른쪽 위 모서리에 장치를 다시 시작하거나 종료하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="39197-137">안전하지 않은 강제 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="39197-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="39197-138">이전 모든 방법으로 장치를 다시 시작할 수 없는 경우 강제로 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="39197-139">이 방법은 HoloLens에서 배터리를 당겨 분리하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="39197-140">장치를 손상된 상태로 만들 수 있는 위험한 작업입니다. </span><span class="sxs-lookup"><span data-stu-id="39197-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="39197-141">장치가 손상된 경우 HoloLens를 플래시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="39197-142">이는 잠재적으로 위험한 방법이므로 위의 모든 방법으로 다시 시작할 수 없을 때만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="39197-143">전원 버튼을 최소 10초간 길게 누릅니다. </span><span class="sxs-lookup"><span data-stu-id="39197-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="39197-144">10초 이상 버튼을 길게 눌러도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39197-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="39197-145">모든 LED 활동을 무시해도 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="39197-146">버튼을 놓고 2-3초간 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="39197-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="39197-147">전원 버튼을 1초간 길게 눌러 장치를 다시 켭니다.</span><span class="sxs-lookup"><span data-stu-id="39197-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="39197-148">그래도 문제가 해결되지 않으면 모든 배터리 표시등이 꺼지고 화면에 홀로그램이 표시되지 않을 때까지 전원 버튼을 4초간 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="39197-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="39197-149">1분 정도 기다렸다가 전원 버튼을 다시 눌러 장치를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="39197-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="39197-150">공장 설정으로 초기화</span><span class="sxs-lookup"><span data-stu-id="39197-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="39197-151">초기화하려면 배터리가 적어도 40% 충전되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="39197-152">다시 시작한 후에도 계속 HoloLens에 문제가 발생하는 경우 공장 상태로 다시 초기화해 보세요.</span><span class="sxs-lookup"><span data-stu-id="39197-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="39197-153">HoloLens를 초기화하면 해당 장치에 설치된 Windows Holographic 소프트웨어의 버전이 유지되며 다른 모든 항목은 공장 기본 설정으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="39197-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="39197-154">장치를 초기화하면 TPM 초기화를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="39197-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="39197-155">초기화하면 최신 설치된 버전의 Windows Holographic만 설치되며 모든 초기화 단계(보정, Wi-Fi 연결, 사용자 계정 만들기, 앱 다운로드 등)를 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="39197-156">설정 앱을 시작하고 **업데이트** > **재설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="39197-157">**장치 초기화** 옵션을 선택하고 확인 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="39197-158">장치 초기화 동의하면 장치가 다시 시작되고 진행률 표시줄과 함께 회전하는 톱니바퀴가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="39197-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="39197-159">프로세스가 완료될 때까지 30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="39197-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="39197-160">초기화가 완료되면 장치가 기본 제공 환경으로 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="39197-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="39197-161">운영 체제 재설치</span><span class="sxs-lookup"><span data-stu-id="39197-161">Re-install the operating system</span></span>

<span data-ttu-id="39197-162">다시 부팅하고 초기화한 후에도 계속 장치에 문제가 있는 경우 컴퓨터에서 복구 도구를 사용하여 HoloLens의 운영 체제와 펌웨어를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="39197-163">HoloLens 초기화에 필요한 모든 데이터는 FFU(Full Flash Update)에 패키지화되어 있습니다. </span><span class="sxs-lookup"><span data-stu-id="39197-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="39197-164">이는 iso, wim 또는 vhd와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="39197-165">FFU 이미지 파일 형식에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="39197-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="39197-166">필요한 경우 Windows Device Recovery Tool을 사용하여 HoloLens(1세대)에 완전히 새로운 운영 체제를 설치할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="39197-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="39197-167">이 도구를 사용하기 전에 HoloLens를 다시 시작하거나 초기화하여 문제를 해결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="39197-168">복구 프로세스에 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-168">The recovery process may take some time.</span></span>  <span data-ttu-id="39197-169">작업이 완료되면 HoloLens에 대해 승인된 최신 버전의 Windows Holographic 소프트웨어가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="39197-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="39197-170">이 도구를 사용하려면 Windows 10 이상을 실행하며 4GB의 사용 가능한 저장소 공간이 있는 컴퓨터를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="39197-171">이 도구는 가상 컴퓨터에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39197-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="39197-172">HoloLens 복구:</span><span class="sxs-lookup"><span data-stu-id="39197-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="39197-173">PC에서 [Windows Device Recovery Tool(WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="39197-174">HoloLens와 함께 제공된 마이크로 USB 케이블을 사용하여 컴퓨터에 HoloLens(1세대)를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="39197-175">Windows Device Recovery Tool을 실행하여 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39197-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="39197-176">HoloLens(1세대)가 자동으로 검색되지 않는 경우 **장치가 검색되지 않음**을 선택하고 지침에 따라 장치를 복구 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="39197-177">수동 플래시 모드:</span><span class="sxs-lookup"><span data-stu-id="39197-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="39197-178">장치가 검색되지 않는 경우 다음 방법을 사용하여 수동으로 플래시 모드로 전환하세요.</span><span class="sxs-lookup"><span data-stu-id="39197-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="39197-179">모든 전원에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="39197-180">장치가 켜져 있는 경우 완전히 꺼질 때까지 전원 버튼을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="39197-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="39197-181">**볼륨 크게** 버튼을 누른 다음 **전원 버튼**을 가볍게 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-181">Hold the **Volume Up** button, and breifly tap the **Power button**.</span></span> 
1. <span data-ttu-id="39197-182">장치가 부팅되고 중간 LED 표시등이 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="39197-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="39197-183">PC에 장치를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="39197-184">Windows Device Recovery Tool을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="39197-185">\*장치가 검색되지 않음\*\*을 선택한 다음 **HoloLens**를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="39197-186">지침에 따라 장치를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="39197-186">Follow the instructions to recover your device.</span></span>
