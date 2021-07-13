---
title: HoloLens 다시 시작, 초기화 또는 복구
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: 고급 복구 도우미를 사용하여 이미지를 HoloLens 2로 플래시하는 방법.
keywords: 사용 방법, 다시 부팅, 초기화, 복구, 하드 리셋, 소프트 리셋, 전원 주기, HoloLens, 종료, acr, 고급 복구 도우미
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923638"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="1ddb7-104">HoloLens 2 다시 시작, 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="1ddb7-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1ddb7-105">문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="1ddb7-106">전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="1ddb7-107">HoloLens 2와 함께 제공된 [충전기와 USB Type-C 케이블](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)을 사용하는 것이 장치를 충전하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="1ddb7-108">충전기는 18W의 전력을 공급합니다(9V/2A).</span><span class="sxs-lookup"><span data-stu-id="1ddb7-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="1ddb7-109">HoloLens 2 장치는 제공된 벽면 충전기를 사용하여 장치가 대기 중일 때 65분 이내에 배터리를 완전 충전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="1ddb7-110">해당 액세서리를 사용할 수 없는 경우 사용 가능한 충전기가 최소 15W의 전력을 지원할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="1ddb7-111">가능하면 PC에 연결하여 USB를 통해 장치를 충전하지 마세요. 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="1ddb7-112">장치가 제대로 부팅되고 실행되고 있으면 다음과 같은 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="1ddb7-113">HoloLens 장치 UI의 주 메뉴에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="1ddb7-114">전원 단추 가까이에 있는 LED로 확인합니다(40% 충전의 경우 LED가 최소 2개 켜진 것을 볼 수 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="1ddb7-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="1ddb7-115">장치가 충전 중일 때는 배터리 표시등이 켜져 있고 현재 충전 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="1ddb7-116">마지막 표시등은 페이드 인/페이드 아웃하여 활성 충전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="1ddb7-117">HoloLens가 켜져 있으면 배터리 표시등이 배터리 잔량을 5단계로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="1ddb7-118">5개의 표시등 중 하나만 켜져 있으면 배터리 잔량이 20% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="1ddb7-119">배터리 잔량이 매우 낮은 상태에서 장치를 켜려고 하면 표시등 1개가 잠깐 깜박인 다음 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="1ddb7-120">호스트 PC에서 **파일 탐색기** 를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="1ddb7-121">장치를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="1ddb7-122">대화 상자에 배터리 충전 잔량이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됨](images/ResetRecovery2.png)

<span data-ttu-id="1ddb7-124">장치가 시작 메뉴로 부팅할 수 없는 경우 호스트 PC의 LED 모양과 장치 열거형을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="1ddb7-125">그런 다음, [문제 해결 가이드](hololens-troubleshooting.md)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="1ddb7-126">장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않으면 장치를 호스트 PC가 아닌 전원 공급 장치에 연결하고 [하드 리셋 절차](hololens-recovery.md#hard-reset-procedure)를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="1ddb7-127">장치가 충전될 때까지 1시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="1ddb7-128">디바이스 재설정</span><span class="sxs-lookup"><span data-stu-id="1ddb7-128">Reset the device</span></span>

<span data-ttu-id="1ddb7-129">특정 상황에서는 소프트웨어 UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="1ddb7-130">표준 절차</span><span class="sxs-lookup"><span data-stu-id="1ddb7-130">Standard procedure</span></span>

1. <span data-ttu-id="1ddb7-131">Type-C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치 연결을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="1ddb7-132">**전원** 단추를 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="1ddb7-133">모든 LED가 꺼져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="1ddb7-134">2~3초 후 **전원** 단추를 짧게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="1ddb7-135">전원 단추 옆에 있는 LED가 켜지고 장치가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="1ddb7-136">호스트 PC에 장치를 연결한 다음 장치 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="1ddb7-137">(Windows 10의 경우 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자** 를 선택합니다.) 아래 이미지에 표시된 것처럼 장치가 *Microsoft HoloLens* 로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 장치 관리자](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="1ddb7-139">하드 리셋 절차</span><span class="sxs-lookup"><span data-stu-id="1ddb7-139">Hard-reset procedure</span></span>

<span data-ttu-id="1ddb7-140">표준 초기화 절차가 작동하지 않는 경우에는 하드 리셋 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="1ddb7-141">Type-C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치 연결을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="1ddb7-142">**Volume down** + **전원** 단추를 15초 동안 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="1ddb7-143">장치가 자동으로 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="1ddb7-144">호스트 PC에 장치를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="1ddb7-145">장치 관리자를 엽니다(Windows 10의 경우 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자** 를 선택).</span><span class="sxs-lookup"><span data-stu-id="1ddb7-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="1ddb7-146">아래 이미지에 표시된 것처럼 장치에서 *Microsoft HoloLens* 로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 장치 관리자 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="1ddb7-148">장치 클린 리플래시</span><span class="sxs-lookup"><span data-stu-id="1ddb7-148">Clean-reflash the device</span></span>

<span data-ttu-id="1ddb7-149">드문 상황에서 HoloLens 2를 "클린 플래시"해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="1ddb7-150">클린 리플래시는 다음 문제에 영향을 주지 않을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="1ddb7-151">색 균일성 표시</span><span class="sxs-lookup"><span data-stu-id="1ddb7-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="1ddb7-152">부팅 시 소리가 나지만 디스플레이 출력이 없음</span><span class="sxs-lookup"><span data-stu-id="1ddb7-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="1ddb7-153">1-3-5-LED 패턴</span><span class="sxs-lookup"><span data-stu-id="1ddb7-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="1ddb7-154">과열</span><span class="sxs-lookup"><span data-stu-id="1ddb7-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="1ddb7-155">OS 충돌(응용 프로그램 충돌과 다름)</span><span class="sxs-lookup"><span data-stu-id="1ddb7-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="1ddb7-156">장치를 리플래시하는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="1ddb7-157">두 경우 모두 먼저 [Windows 스토어에서 고급 복구 도우미를 설치](https://www.microsoft.com/store/productId/9P74Z35SFRS8)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="1ddb7-158">장치를 리플래시하면 TPM 초기화 정보를 포함하여 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="1ddb7-159">기본적으로 고급 복구 도우미는 최신 기능 릴리스 빌드를 다운로드하도록 설정되어 있습니다. 여기를 확인하여 [릴리스 정보](hololens-release-notes.md#)를 읽어보고 최신 기능 릴리스에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="1ddb7-160">최신 HoloLens 2 FFU(Full Flash Update) 패키지를 다운로드하여 고급 복구 도우미를 통해 장치를 리플래시하려면 [여기를 클릭하여 최신 월별 HoloLens 2 이미지를 다운로드합니다](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="1ddb7-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="1ddb7-161">이 버전은 일반적으로 사용 가능한 최신 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="1ddb7-162">리플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 탐지할 준비가 되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="1ddb7-163">또한 HoloLens가 최소 40%까지 충전되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 클린 리플래시 스크린샷](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="1ddb7-165">일반 절차</span><span class="sxs-lookup"><span data-stu-id="1ddb7-165">Normal procedure</span></span>

1. <span data-ttu-id="1ddb7-166">HoloLens 장치가 실행 중일 때 이전에 고급 복구 도우미 앱을 열었던 Windows 10 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="1ddb7-167">장치가 자동으로 탐지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 클린 리플래시 초기 화면](images/ARC2.png)

3. <span data-ttu-id="1ddb7-169">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="1ddb7-170">수동 절차</span><span class="sxs-lookup"><span data-stu-id="1ddb7-170">Manual procedure</span></span>

<span data-ttu-id="1ddb7-171">HoloLens 2가 올바르게 시작되지 않거나 고급 복구 도우미가 장치를 탐지할 수 없는 경우 장치를 복구 모드로 전환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="1ddb7-172">Type-C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치 연결을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="1ddb7-173">**전원** 단추를 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="1ddb7-174">모든 LED가 꺼져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="1ddb7-175">**Volume up** 단추를 누른 상태에서 **전원** 단추를 놓아서 장치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="1ddb7-176">15초 동안 기다린 다음 **Volume up** 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="1ddb7-177">5개 LED 중 가운데 LED만 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="1ddb7-178">장치를 호스트 PC에 연결하고 장치 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="1ddb7-179">(Windows 10의 경우 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자** 선택합니다.) 아래 이미지에 표시된 것처럼 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="1ddb7-181">장치가 자동으로 탐지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 클린 리플래시 화면](images/ARC2.png)

6. <span data-ttu-id="1ddb7-183">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="1ddb7-184">고급 복구 도우미 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1ddb7-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="1ddb7-185">플래시를 시도하기 전에 장치가 40% 이상 충전되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="1ddb7-186">장치가 잠금 해제되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="1ddb7-187">ARC가 장치를 탐지하지 못하는 경우 PC의 파일 탐색기를 통해 장치에 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="1ddb7-188">연결할 수 없는 경우, 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-188">If you cannot;</span></span>

    1.  <span data-ttu-id="1ddb7-189">장치에 해당 연결을 사용하지 않도록 설정하는 USB 정책이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="1ddb7-190">이 경우 [수동 플래싱 모드](hololens-recovery.md#manual-procedure)를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="1ddb7-191">정책이 없으면 다른 USB 케이블을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="1ddb7-192">장치가 [1-3-5-LED 패턴](hololens2-setup.md#lights-to-indicate-problems)을 표시하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="1ddb7-193">앱 스토어를 사용하지 않고 ARC 다운로드</span><span class="sxs-lookup"><span data-stu-id="1ddb7-193">Download ARC without using the app store</span></span>

<span data-ttu-id="1ddb7-194">IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자는 "오프라인" 배포 경로를 통해 이 앱을 사용 가능하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="1ddb7-195">IT 관리자는 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="1ddb7-196">이 가이드는 고급 복구 도우미에 중점을 두지만 다른 "오프라인" 앱에 대해서도 이 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="1ddb7-197">배포 경로를 사용하도록 설정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="1ddb7-198">[비즈니스용 Microsoft Store](https://businessstore.microsoft.com)로 이동하여 Azure Active Directory ID를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="1ddb7-199">**관리 - 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="1ddb7-200">**Shopping experience** 에서 **Show offline apps** 를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="1ddb7-201">**shop for my group** 으로 이동하고 [**_고급 복구 도우미_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="1ddb7-202">**라이선스 형식** 을 **_오프라인_*으로 변경하고\* 관리*\* 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="1ddb7-203">**Download the package for offline use** 에서 두 번째 파란색 **다운로드** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="1ddb7-204">파일 확장명이 *.appxbundle* 인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="1ddb7-205">이 단계에서 데스크톱 PC에 인터넷이 연결되어 있으면 패키지를 두 번 클릭하여 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="1ddb7-206">대상 PC에 인터넷이 연결되어 있지 않으면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="1ddb7-207">인코딩되지 않은 라이선스를 선택하고 **Generate license** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="1ddb7-208">**Required Frameworks** 에서 **다운로드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="1ddb7-209">DISM을 사용하여 종속성과 라이선스로 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="1ddb7-210">관리자 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="1ddb7-211">이 코드 예제에 나와 있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="1ddb7-212">예제와 다른 다운로드 위치를 선택했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="1ddb7-213">필요에 따라 명령을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="1ddb7-214">고급 복구 도우미를 사용하여 오프라인으로 FFU를 설치하려는 경우 플래시 이미지를 다운로드하면 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ddb7-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="1ddb7-215">[**HoloLens 2에 대한 현재 이미지를 다운로드합니다**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="1ddb7-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="1ddb7-216">기타 리소스:</span><span class="sxs-lookup"><span data-stu-id="1ddb7-216">Other resources:</span></span>
- [<span data-ttu-id="1ddb7-217">오프라인 앱 배포</span><span class="sxs-lookup"><span data-stu-id="1ddb7-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="1ddb7-218">DISM 앱 패키지(.appx 또는 .appxbundle) 서비스 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="1ddb7-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
