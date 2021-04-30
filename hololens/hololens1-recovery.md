---
title: HoloLens 다시 시작, 다시 설정 또는 복구 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows 장치 복구 도구를 사용 하 여 이미지를 플래시 하는 첫 번째 Gen로 이미지를 만드는 방법입니다.
keywords: 방법, 재부팅, 다시 설정, 복구, 하드 리셋, 소프트 리셋, 전원 주기, HoloLens, 종료, wdrt, windows 장치 복구 도구
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
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309392"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="2270e-104">HoloLens 다시 시작, 다시 설정 또는 복구 (첫 번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="2270e-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="2270e-105">HoloLens에 문제가 발생 하는 경우 다시 시작 하거나 다시 설정 하거나 장치 복구를 사용 하 여 장치를 경감 하기 위해 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="2270e-106">이 문서에서는 권장 되는 복구 단계를 순서 대로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="2270e-107">HoloLens 2를 복구 하려는 경우 해당 프로세스가 서로 다르므로 [hololens 2 복구](https://docs.microsoft.com/hololens/hololens-recovery)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2270e-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="2270e-108">이 문서에서는 HoloLens 장치 및 소프트웨어에 대해 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="2270e-109">Holograms 적절 하지 않은 경우 홀로그램 품질을 개선 하는 요소에 대 한 자세한 내용은 **[HoloLens 환경 고려 사항](hololens-environment-considerations.md)** 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2270e-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="2270e-110">재시작</span><span class="sxs-lookup"><span data-stu-id="2270e-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="2270e-111">Cortana를 사용 하 여 안전 하 게 다시 시작</span><span class="sxs-lookup"><span data-stu-id="2270e-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="2270e-112">HoloLens를 가장 안전 하 게 다시 시작 하는 방법은 Cortana를 사용 하는 것입니다 .이는 일반적으로 HoloLens에서 문제가 발생할 때 가장 먼저 시도할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="2270e-113">Cortana는 모든 장치에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="2270e-114">Cortana는 모든 HoloLens (첫 번째 Gen) 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="2270e-115">Cortana는 Windows Holograpic 버전 2004 업데이트 이전의 빌드에 대 한 HoloLens 2 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="2270e-116">HoloLens를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="2270e-117">사용자가 로그인 되어 있고 장치에서 잠금을 해제 하기 위해 대기 하 고 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="2270e-118">"안녕하세요 Cortana, restart" 또는 "안녕하세요 Cortana, restart" 라고 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="2270e-119">Cortana가 응답 하 고 확인 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="2270e-120">사운드가 질문 후에 재생 될 때까지 기다렸다가 "예"를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="2270e-121">장치가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="2270e-122">전원 단추를 사용 하 여 안전 하 게 다시 시작</span><span class="sxs-lookup"><span data-stu-id="2270e-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="2270e-123">그래도 장치를 다시 시작할 수 없는 경우에는 **전원** 단추를 사용 하 여 다시 시작 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2270e-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="2270e-124">5 초 동안 **전원** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="2270e-125">1 초 후에는 5 개의 Led가 모두 켜 지 며, 오른쪽에서 왼쪽으로 하나씩 천천히 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="2270e-126">5 초 후에 모든 Led가 꺼지고 성공적으로 종료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="2270e-127">모든 Led가 꺼진 직후에 단추 누르기를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="2270e-128">종료가 완료 될 때까지 1 분 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="2270e-129">표시 기능이 해제 된 후에도 종료는 계속 진행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="2270e-130">**전원** 단추를 1 초 동안 누르고 있으면 장치를 다시 켭니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="2270e-131">Windows 장치 포털을 사용 하 여 안전 하 게 다시 시작</span><span class="sxs-lookup"><span data-stu-id="2270e-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="2270e-132">이 프로세스의 경우 HoloLens를 개발자 장치로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="2270e-133">[Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)에서 자세한 정보를 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2270e-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="2270e-134">이전 절차가 작동 하지 않는 경우 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용 하 여 장치를 다시 시작 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2270e-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="2270e-135">오른쪽 위 모서리에서 장치를 다시 시작 하거나 종료 하는 옵션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="2270e-136">안전 하 게 강제 다시 시작 수행</span><span class="sxs-lookup"><span data-stu-id="2270e-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="2270e-137">이전 방법으로 HoloLens를 다시 시작 하지 않은 경우 강제로 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="2270e-138">이 방법은 배터리를 제거 하 고 다시 설치 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="2270e-139">장치가 손상 된 상태로 남을 수 있으므로 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="2270e-140">이런 경우 HoloLens를 플래시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="2270e-141">이는 잠재적으로 유해한 방법 이며 이전에 언급 한 메서드가 작동 하지 않은 경우에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="2270e-142">최소 10 초 동안 **전원** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="2270e-143">단추를 10 초 이상 길게 유지 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="2270e-144">모든 LED 작업을 무시 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="2270e-145">단추를 눌렀다가 2-3 초 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="2270e-146">1 초 동안 **전원** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="2270e-147">문제가 여전히 발생 하는 경우 모든 배터리 표시기가 페이드 아웃 되 고 화면이 holograms 표시를 중지 하기 전까지 4 초간 **전원** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="2270e-148">1 분 정도 기다린 다음 **전원** 단추를 다시 눌러 장치를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="2270e-149">공장 설정으로 다시 설정</span><span class="sxs-lookup"><span data-stu-id="2270e-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="2270e-150">배터리를 다시 설정 하려면 적어도 40% 요금이 청구 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="2270e-151">HoloLens에 여전히 문제가 있는 경우 공장 상태로 다시 설정 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2270e-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="2270e-152">이 단계에서는 설치 된 Windows Holographic 소프트웨어의 버전을 유지 하 고 다른 모든 항목을 공장 설정으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="2270e-153">장치를 다시 설정 하는 경우 TPM 다시 설정 정보를 포함 하 여 모든 개인 데이터, 앱 및 설정이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="2270e-154">다시 설정 하면 설치 된 최신 버전의 Windows Holographic 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="2270e-155">모든 초기화 단계 (보정, Wi-fi에 연결, 사용자 계정 만들기, 앱 다운로드 등)를 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="2270e-156">설정 앱을 열고 **업데이트**  >  **복구** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="2270e-157">**장치 다시 설정** 옵션을 선택 하 고 확인 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="2270e-158">다시 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-158">Confirm the reset.</span></span> <span data-ttu-id="2270e-159">장치가 다시 시작 되 고 회전 하는 기어 집합과 진행률 표시줄이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="2270e-160">이 프로세스가 완료 될 때까지 30 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="2270e-161">완료 되 면 장치가 "기본 제공" 환경으로 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="2270e-162">운영 체제 다시 설치</span><span class="sxs-lookup"><span data-stu-id="2270e-162">Reinstall the operating system</span></span>

<span data-ttu-id="2270e-163">다시 시작 하 고 다시 설정한 후에도 장치에 문제가 발생 하는 경우 컴퓨터의 복구 도구를 사용 하 여 HoloLens 운영 체제 및 펌웨어를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="2270e-164">HoloLens가 다시 설정 하는 데 필요한 데이터는 .iso, .wim 또는 .vhd 파일과 유사한 FFU (전체 플래시 업데이트)로 패키지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="2270e-165">FFU 이미지 파일 형식에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="2270e-166">Windows 장치 복구 도구를 사용 하 여 HoloLens (첫 번째 gen)에 새 운영 체제를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="2270e-167">해당 도구를 사용 하기 전에 HoloLens를 다시 시작 하거나 다시 설정 하면 문제가 해결 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="2270e-168">복구 프로세스는 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-168">The recovery process may take a while.</span></span> <span data-ttu-id="2270e-169">완료 되 면 Windows Holographic 소프트웨어의 최신 버전이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="2270e-170">이 도구를 사용 하려면 최소 4gb의 사용 가능한 저장소 공간이 있는 Windows 10 이상을 실행 하는 컴퓨터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="2270e-171">가상 머신에서는이 도구를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="2270e-172">HoloLens 복구</span><span class="sxs-lookup"><span data-stu-id="2270e-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="2270e-173">컴퓨터에 [Windows 장치 복구 도구](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="2270e-174">HoloLens와 함께 제공 되는 마이크로 USB 케이블을 사용 하 여 HoloLens (첫 번째 gen)를 컴퓨터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="2270e-175">Windows 장치 복구 도구를 열고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="2270e-176">HoloLens (첫 번째 gen)가 자동으로 검색 되지 않는 경우 **내 장치를 검색 하지 못했습니다**.를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="2270e-177">그런 다음 지침에 따라 장치를 복구 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="2270e-178">수동 깜박임 모드</span><span class="sxs-lookup"><span data-stu-id="2270e-178">Manual flashing mode</span></span>

<span data-ttu-id="2270e-179">장치가 검색 되지 않은 경우 다음 단계에 따라 플래시 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="2270e-180">전원에서 장치를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="2270e-181">장치가 켜져 있으면 완전히 꺼질 때까지 **전원** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="2270e-182">**볼륨 위로** 단추를 누른 상태에서 **전원** 단추를 잠시 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="2270e-183">장치를 시작 하 고 중간 LED 라이트만 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="2270e-184">장치를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="2270e-185">Windows 장치 복구 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="2270e-186">**장치를 검색 하지 못했습니다** .를 선택 하 고 **HoloLens** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="2270e-187">지침에 따라 장치를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="2270e-187">Follow the instructions to recover your device.</span></span>
