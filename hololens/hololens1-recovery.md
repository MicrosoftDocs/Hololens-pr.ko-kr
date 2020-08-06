---
title: HoloLens 1 다시 시작, 초기화 또는 복구
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915964"
---
# <span data-ttu-id="78413-104">HoloLens 2(1세대) 다시 시작, 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="78413-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="78413-105">HoloLens에 문제가 발생한 경우 장치 복구를 사용하여 장치를 다시 시작하거나 초기화 또는 리플래시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="78413-106">이 문서에서는 권장되는 복구 단계를 순서대로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="78413-107">HoloLens 2를 복구하려는 경우에는 해당 프로세스가 다르므로 [HoloLens 2 복구](https://docs.microsoft.com/hololens/hololens-recovery)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78413-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="78413-108">이 문서에서는 HoloLens 장치와 소프트웨어를 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="78413-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="78413-109">홀로그램이 올바르게 보이지 않는 경우, 홀로그램 품질을 향상시키는 요소에 대한 정보를 보려면 **[HoloLens 환경 고려 사항](hololens-environment-considerations.md)** 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78413-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <span data-ttu-id="78413-110">다시 시작</span><span class="sxs-lookup"><span data-stu-id="78413-110">Restart</span></span>

### <span data-ttu-id="78413-111">Cortana를 사용하여 안전하게 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="78413-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="78413-112">Cortana를 사용하여 HoloLens를 다시 시작하는 것이 가장 안전합니다. 이는 일반적으로 HoloLens에 문제가 발생하는 경우 가장 먼저 시도해 볼 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="78413-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="78413-113">일부 장치에서는 Cortana를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="78413-114">Cortana는 모든 HoloLens(1세대) 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="78413-115">Cortana는 Windows Holograpic, 버전 2004 업데이트 이전 빌드의 HoloLens 2 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="78413-116">HoloLens 켜기</span><span class="sxs-lookup"><span data-stu-id="78413-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="78413-117">사용자가 로그인했는지, 장치에서 잠금 해제를 위해 암호 입력을 기다리고 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="78413-118">‘안녕 코타나, 재부팅’ 또는 ‘안녕 코타나, 다시 시작’이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="78413-119">Cortana가 응답하고 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="78413-120">질문 후에 사운드가 재생될 때까지 기다린 다음 "예"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="78413-121">장치가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-121">The device will restart.</span></span>

### <span data-ttu-id="78413-122">전원 단추를 사용하여 안전한 다시 시작</span><span class="sxs-lookup"><span data-stu-id="78413-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="78413-123">여전히 장치를 다시 시작할 수 없는 경우 **전원** 단추를 사용하여 다시 시작할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="78413-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="78413-124">**전원** 단추를 5초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78413-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="78413-125">1초 후 5개의 LED가 모두 켜진 다음, 오른쪽에서 왼쪽으로 하나씩 천천히 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="78413-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="78413-126">5초 후 모든 LED가 꺼지면 성공적인 종료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78413-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="78413-127">모든 LED가 꺼진 후 바로 단추 누르기를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="78413-128">종료가 완료될 때까지 1분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78413-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="78413-129">디스플레이가 꺼진 후에도 종료가 계속 진행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="78413-130">**전원** 단추를 1초간 길게 눌러 장치를 다시 켭니다.</span><span class="sxs-lookup"><span data-stu-id="78413-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <span data-ttu-id="78413-131">Windows 장치 포털을 사용하여 안전하게 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="78413-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="78413-132">이 프로세스를 위해 HoloLens가 개발자 장치로 구성되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="78413-133">[Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)에서 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="78413-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="78413-134">이전 절차로 다시 시작할 수 없는 경우 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용하여 장치를 다시 시작해 보세요.</span><span class="sxs-lookup"><span data-stu-id="78413-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="78413-135">오른쪽 위 모서리에 장치를 다시 시작하거나 종료하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <span data-ttu-id="78413-136">안전하지 않은 강제 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="78413-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="78413-137">이전 방법으로 HoloLens가 다시 시작되지 않는 경우 강제로 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="78413-138">이 방법은 배터리를 제거하고 다시 설치하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="78413-139">장치가 손상된 상태에서 종료할 수 있으므로 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="78413-140">장치가 손상된 경우 HoloLens를 플래시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="78413-141">이는 잠재적 위험이 있는 방법으로, 앞에 언급한 방법을 사용할 수 없는 경우에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="78413-142">**전원** 단추를 10초 이상 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78413-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="78413-143">10초 이상 버튼을 길게 눌러도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="78413-144">모든 LED 활동을 무시해도 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="78413-145">단추를 놓고 2~3초 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78413-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="78413-146">**전원** 단추를 1초간 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78413-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="78413-147">그래도 문제가 해결되지 않으면 모든 배터리 표시등이 꺼지고 화면에 홀로그램이 표시되지 않을 때까지 **전원** 단추를 4초간 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78413-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="78413-148">1분 정도 기다렸다가 **전원** 단추를 다시 눌러 장치를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="78413-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <span data-ttu-id="78413-149">공장 설정으로 초기화</span><span class="sxs-lookup"><span data-stu-id="78413-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="78413-150">초기화하려면 배터리가 적어도 40% 충전되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="78413-151">HoloLens에 계속 문제가 있는 경우 공장 상태로 다시 설정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="78413-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="78413-152">이 단계를 수행하면 해당 장치에 설치된 Windows Holographic 소프트웨어의 버전이 유지되며 다른 모든 항목은 공장 기본 설정으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="78413-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="78413-153">장치를 초기화하면 TPM 초기화 정보를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="78413-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="78413-154">초기화하면 설치된 최신 버전의 Windows Holographic만 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="78413-155">모든 초기화 단계(조정, Wi-Fi에 연결, 사용자 계정 만들기, 앱 다운로드 등)를 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="78413-156">설정 앱을 열고 **업데이트** > **복구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="78413-157">**장치 초기화** 옵션을 선택하고 확인 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="78413-158">초기화를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-158">Confirm the reset.</span></span> <span data-ttu-id="78413-159">장치가 다시 시작되고 회전하는 기어와 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="78413-160">프로세스가 완료될 때까지 30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78413-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="78413-161">작업이 완료되면 장치가 "기본 제공" 환경으로 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <span data-ttu-id="78413-162">운영 체제 다시 설치</span><span class="sxs-lookup"><span data-stu-id="78413-162">Reinstall the operating system</span></span>

<span data-ttu-id="78413-163">다시 시작하고 초기화한 후에도 계속 장치에 문제가 있는 경우 컴퓨터에서 복구 도구를 사용하여 HoloLens의 운영 체제와 펌웨어를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="78413-164">초기화를 하는데 HoloLens에 필요한 데이터가 .iso, .wim 또는 .vhd 파일과 유사한 FFU(Full Flash Update)에 패키징되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="78413-165">FFU 이미지 파일 형식에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="78413-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="78413-166">Windows Device Recovery Tool을 사용하여 HoloLens(1세대)에 새로운 운영 체제를 설치할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="78413-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="78413-167">해당 도구를 사용하기 전에 HoloLens를 다시 시작하거나 초기화하여 문제를 해결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="78413-168">복구 프로세스에 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-168">The recovery process may take a while.</span></span> <span data-ttu-id="78413-169">작업이 완료되면 최신 버전의 Windows Holographic 소프트웨어가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="78413-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="78413-170">이 도구를 사용하려면 Windows 10 이상을 실행하며 4GB의 사용 가능한 저장소 공간이 있는 컴퓨터를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="78413-171">이 도구는 가상 컴퓨터에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78413-171">You can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="78413-172">HoloLens 복구</span><span class="sxs-lookup"><span data-stu-id="78413-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="78413-173">PC에서 [Windows Device Recovery Tool(WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="78413-174">HoloLens와 함께 제공된 마이크로 USB 케이블을 사용하여 컴퓨터에 HoloLens(1세대)를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="78413-175">Windows Device Recovery Tool을 열고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="78413-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="78413-176">HoloLens(1세대)가 자동으로 검색되지 않는 경우 **내 장치가 검색되지 않음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="78413-177">그런 다음 지침에 따라 장치를 복구 모드로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <span data-ttu-id="78413-178">수동 플래시 모드</span><span class="sxs-lookup"><span data-stu-id="78413-178">Manual flashing mode</span></span>

<span data-ttu-id="78413-179">장치가 검색되지 않는 경우 다음 단계에 따라 플래시 모드로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="78413-180">모든 전원에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="78413-181">장치가 켜져 있는 경우 완전히 꺼질 때까지 **전원** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78413-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="78413-182">**볼륨 크게** 단추를 누른 다음 **전원** 단추를 짧게 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="78413-183">장치가 시작되고 중간 LED 표시등이 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="78413-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="78413-184">PC에 장치를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="78413-185">Windows Device Recovery Tool을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="78413-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="78413-186">**내 장치가 검색되지 않음**을 선택한 다음, **HoloLens**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="78413-187">지침에 따라 장치를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="78413-187">Follow the instructions to recover your device.</span></span>
