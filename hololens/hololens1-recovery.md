---
title: HoloLens 1 다시 시작, 다시 설정 또는 복구
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows Device Recovery 도구를 사용하여 이미지를 HoloLens 1세대로 플래시하는 방법입니다.
keywords: 방법, 다시 부팅, 다시 설정, 복구, 하드 재설정, 소프트 재설정, 전원 주기, HoloLens, 종료, wdrt, Windows 디바이스 복구 도구
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397694"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="7fa21-104">HoloLens 다시 시작, 다시 설정 또는 복구(1세대)</span><span class="sxs-lookup"><span data-stu-id="7fa21-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="7fa21-105">HoloLens에 문제가 발생하는 경우 다시 시작하거나 다시 설정하거나 디바이스 복구를 사용하여 디바이스를 리플래시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="7fa21-106">이 문서에서는 권장되는 복구 단계를 순서대로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="7fa21-107">HoloLens 2 복구하려는 경우 프로세스가 다르므로 HoloLens 2 [복구를](https://docs.microsoft.com/hololens/hololens-recovery)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fa21-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="7fa21-108">이 문서에서는 HoloLens 디바이스 및 소프트웨어에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="7fa21-109">홀로그램이 제대로 표시되지 않는 경우 홀로그램 품질을 향상시키는 요인에 대한 자세한 내용은 **[HoloLens 환경 고려 사항을](hololens-environment-considerations.md)** 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fa21-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="7fa21-110">재시작</span><span class="sxs-lookup"><span data-stu-id="7fa21-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="7fa21-111">Cortana를 사용하여 안전하게 다시 시작</span><span class="sxs-lookup"><span data-stu-id="7fa21-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="7fa21-112">HoloLens를 다시 시작하는 가장 안전한 방법은 일반적으로 HoloLens에 문제가 발생할 때 가장 먼저 시도하는 Cortana를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="7fa21-113">Cortana는 일부 디바이스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="7fa21-114">Cortana는 모든 HoloLens(1세대) 디바이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="7fa21-115">Cortana는 Windows Holograpic 버전 2004 업데이트 이전 빌드의 HoloLens 2 디바이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="7fa21-116">HoloLens를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="7fa21-117">사용자가 로그인되어 있고 디바이스가 암호 잠금을 해제할 때까지 기다리고 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="7fa21-118">"Hey Cortana, 다시 부팅" 또는 "Hey Cortana, 다시 시작"이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="7fa21-119">Cortana가 응답하고 확인하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="7fa21-120">질문 후에 소리가 재생되기를 기다린 다음, "예"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="7fa21-121">디바이스가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="7fa21-122">전원 단추를 사용 하 여 안전 하 게 다시 시작</span><span class="sxs-lookup"><span data-stu-id="7fa21-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="7fa21-123">그래도 장치를 다시 시작할 수 없는 경우에는 **전원** 단추를 사용 하 여 다시 시작 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7fa21-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="7fa21-124">5 초 동안 **전원** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="7fa21-125">1 초 후에는 5 개의 Led가 모두 켜 지 며, 오른쪽에서 왼쪽으로 하나씩 천천히 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="7fa21-126">5 초 후에 모든 Led가 꺼지고 성공적으로 종료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="7fa21-127">모든 Led가 꺼진 직후에 단추 누르기를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="7fa21-128">종료가 완료 될 때까지 1 분 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="7fa21-129">표시 기능이 해제 된 후에도 종료는 계속 진행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="7fa21-130">**전원** 단추를 1 초 동안 누르고 있으면 장치를 다시 켭니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="7fa21-131">Windows 장치 포털을 사용 하 여 안전 하 게 다시 시작</span><span class="sxs-lookup"><span data-stu-id="7fa21-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="7fa21-132">이 프로세스의 경우 HoloLens를 개발자 장치로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="7fa21-133">[Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)에서 자세한 정보를 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7fa21-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="7fa21-134">이전 절차가 작동 하지 않는 경우 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용 하 여 장치를 다시 시작 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7fa21-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="7fa21-135">오른쪽 위 모서리에서 장치를 다시 시작 하거나 종료 하는 옵션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="7fa21-136">안전 하 게 강제 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="7fa21-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="7fa21-137">이전 방법으로 HoloLens를 다시 시작 하지 않은 경우 강제로 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="7fa21-138">이 방법은 배터리를 제거 하 고 다시 설치 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="7fa21-139">장치가 손상 된 상태로 남을 수 있으므로 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="7fa21-140">이런 경우 HoloLens를 플래시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="7fa21-141">이는 잠재적으로 유해한 방법 이며 이전에 언급 한 메서드가 작동 하지 않은 경우에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="7fa21-142">**전원** 단추를 10초 이상 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="7fa21-143">단추를 10초 넘게 유지해도 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="7fa21-144">LED 작업은 무시해도 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="7fa21-145">단추를 해제하고 2-3초 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="7fa21-146">**전원** 단추를 1초 동안 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="7fa21-147">여전히 문제가 있는 경우 모든 배터리 표시기가 페이드 아웃되고 화면이 홀로그램 표시를 중지할 때까지 4초 동안 **전원** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="7fa21-148">1분 정도 기다린 다음 **전원** 단추를 다시 눌러 디바이스를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="7fa21-149">공장 설정으로 다시 설정</span><span class="sxs-lookup"><span data-stu-id="7fa21-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="7fa21-150">배터리를 다시 설정하려면 40% 이상의 충전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="7fa21-151">HoloLens에 여전히 문제가 있는 경우 공장 상태로 다시 설정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7fa21-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="7fa21-152">이 단계에서는 설치된 Windows Holographic 소프트웨어의 버전을 유지하고 다른 모든 것을 공장 설정으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="7fa21-153">디바이스를 다시 설정하면 TPM 재설정 정보를 포함하여 모든 개인 데이터, 앱 및 설정이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="7fa21-154">다시 설정하면 설치된 최신 버전의 Windows Holographic만 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="7fa21-155">모든 초기화 단계를 다시 수행해야 합니다(보정, Wi-Fi에 연결, 사용자 계정 만들기, 앱 다운로드 등).</span><span class="sxs-lookup"><span data-stu-id="7fa21-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="7fa21-156">설정 앱을 열고 **복구 업데이트를**  >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="7fa21-157">디바이스 **다시 설정** 옵션을 선택하고 확인 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="7fa21-158">다시 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-158">Confirm the reset.</span></span> <span data-ttu-id="7fa21-159">디바이스가 다시 시작되고 회전 기어 세트와 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="7fa21-160">이 프로세스가 완료되기까지 약 30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="7fa21-161">완료되면 디바이스가 "바로" 환경으로 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="7fa21-162">운영 체제 다시 설치</span><span class="sxs-lookup"><span data-stu-id="7fa21-162">Reinstall the operating system</span></span>

<span data-ttu-id="7fa21-163">다시 시작 하 고 다시 설정한 후에도 장치에 문제가 발생 하는 경우 컴퓨터의 복구 도구를 사용 하 여 HoloLens 운영 체제 및 펌웨어를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="7fa21-164">HoloLens가 다시 설정 하는 데 필요한 데이터는 .iso, .wim 또는 .vhd 파일과 유사한 FFU (전체 플래시 업데이트)로 패키지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="7fa21-165">FFU 이미지 파일 형식에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="7fa21-166">Windows 장치 복구 도구를 사용 하 여 HoloLens (첫 번째 gen)에 새 운영 체제를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="7fa21-167">해당 도구를 사용 하기 전에 HoloLens를 다시 시작 하거나 다시 설정 하면 문제가 해결 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="7fa21-168">복구 프로세스는 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-168">The recovery process may take a while.</span></span> <span data-ttu-id="7fa21-169">완료 되 면 Windows Holographic 소프트웨어의 최신 버전이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="7fa21-170">이 도구를 사용 하려면 최소 4gb의 사용 가능한 저장소 공간이 있는 Windows 10 이상을 실행 하는 컴퓨터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="7fa21-171">가상 머신에서는이 도구를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="7fa21-172">HoloLens 복구</span><span class="sxs-lookup"><span data-stu-id="7fa21-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="7fa21-173">컴퓨터에 [Windows 장치 복구 도구](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="7fa21-174">HoloLens와 함께 제공 되는 마이크로 USB 케이블을 사용 하 여 HoloLens (첫 번째 gen)를 컴퓨터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="7fa21-175">Windows 장치 복구 도구를 열고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="7fa21-176">HoloLens (첫 번째 gen)가 자동으로 검색 되지 않는 경우 **내 장치를 검색 하지 못했습니다**.를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="7fa21-177">그런 다음 지침에 따라 장치를 복구 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="7fa21-178">수동 깜박임 모드</span><span class="sxs-lookup"><span data-stu-id="7fa21-178">Manual flashing mode</span></span>

<span data-ttu-id="7fa21-179">장치가 검색 되지 않은 경우 다음 단계에 따라 플래시 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="7fa21-180">전원에서 장치를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="7fa21-181">장치가 켜져 있으면 완전히 꺼질 때까지 **전원** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="7fa21-182">볼륨 **위로** 단추를 누르고 **전원** 단추를 잠깐 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="7fa21-183">디바이스가 시작되고 중간 LED만 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="7fa21-184">디바이스를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="7fa21-185">Windows Device Recovery 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="7fa21-186">**내 디바이스가 검색되지 않음을** 선택한 **다음, HoloLens 를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="7fa21-187">지침에 따라 디바이스를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa21-187">Follow the instructions to recover your device.</span></span>
