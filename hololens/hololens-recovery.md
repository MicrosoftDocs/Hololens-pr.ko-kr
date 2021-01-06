---
title: HoloLens 다시 시작, 초기화 또는 복구
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 고급 복구 도우미를 사용하여 이미지를 HoloLens 2로 플래시하는 방법
keywords: 사용 방법, 다시 부팅, 초기화, 복구, 하드 초기화, 소프트 초기화, 전원 주기, HoloLens, 종료, acr, 고급 복구 도우미
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
ms.openlocfilehash: ad162d1f415430e22e683280089cacf2e1cef02a
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253584"
---
# <span data-ttu-id="50446-104">HoloLens 2 다시 시작, 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="50446-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="50446-105">장치 충전</span><span class="sxs-lookup"><span data-stu-id="50446-105">Charge the device</span></span>

<span data-ttu-id="50446-106">문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 20~40%정도 충전되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="50446-107">HoloLens 2 장치와 함께 제공되는 충전기와 USB 유형 C 케이블을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="50446-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="50446-108">디바이스와 함께 제공되는 전원 공급 장치와 USB-C-to-C 케이블이 HoloLens 2를 충전하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="50446-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="50446-109">충전기는 18W의 전력을 공급합니다(2A에서 9V).</span><span class="sxs-lookup"><span data-stu-id="50446-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="50446-110">제공된 벽면 충전기를 사용하여 HoloLens 2 장치는 장치가 대기 중일 때 65분 이내에 배터리를 완전 충전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="50446-111">해당 액세서리를 사용할 수 없는 경우 사용할 수 있는 충전기가 최소 15W의 전원을 지원할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="50446-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="50446-112">가능하면 PC에 USB를 연결해 장치를 충전하지 마세요. 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="50446-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="50446-113">장치가 제대로 부팅되고 실행되고 있는 경우에는 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="50446-114">HoloLens 장치 UI의 주 메뉴에서 확인</span><span class="sxs-lookup"><span data-stu-id="50446-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="50446-115">전원 버튼 가까이 있는 LED로 확인(40%에서는 LED가 최소 2개 켜진 것을 볼 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="50446-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="50446-116">디바이스가 충전 중일 때 배터리 표시등이 켜지면서 현재 충전 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="50446-117">마지막 표시등은 활성 충전을 나타내기 위해 안 페이드 인/페이드 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="50446-118">HoloLens가 켜져 있으면 배터리 표시등에 배터리 수준이 5단계로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50446-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="50446-119">5개의 표시등 중 하나만 켜져 있으면 배터리 잔량이 20% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="50446-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="50446-120">배터리 잔량이 매우 낮은 상태에서 장치를 켜려고 하면 한 개의 표시등이 잠깐 깜박인 다음 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="50446-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="50446-121">호스트 PC에서 **파일 탐색기**를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="50446-122">장치를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="50446-123">대화 상자에 배터리 충전 수준이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50446-123">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됩니다.](images/ResetRecovery2.png)

<span data-ttu-id="50446-125">장치가 시작 메뉴로 부팅할 수 없는 경우 호스트 PC에 LED 모양과 장치 열거형을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="50446-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="50446-126">그런 다음 [문제 해결 가이드](https://docs.microsoft.com/hololens/hololens-troubleshooting)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="50446-127">장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않으면 장치를 호스트 PC가 아닌 전원 공급 장치에 연결하고 [하드 초기화 절차](hololens-recovery.md#hard-reset-procedure)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="50446-128">장치가 충전될 때까지 1시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="50446-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="50446-129">장치 초기화</span><span class="sxs-lookup"><span data-stu-id="50446-129">Reset the device</span></span>

<span data-ttu-id="50446-130">특정 상황에서는 소프트웨어 UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="50446-131">표준 절차</span><span class="sxs-lookup"><span data-stu-id="50446-131">Standard procedure</span></span>
1. <span data-ttu-id="50446-132">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="50446-133">**전원** 버튼을 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="50446-134">모든 LED가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="50446-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="50446-135">2-3초 후 **전원** 버튼을 짧게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="50446-136">전원 버튼 옆에 있는 LED가 켜지며 장치가 시작되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="50446-137">호스트 PC에 장치를 연결한 다음 장치 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50446-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="50446-138">(Windows 10에서는 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자**를 클릭) 아래 이미지에 표시된 것처럼 장치가 *Microsoft HoloLens*로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 장치 관리자](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="50446-140">하드 초기화 절차</span><span class="sxs-lookup"><span data-stu-id="50446-140">Hard-reset procedure</span></span>

<span data-ttu-id="50446-141">표준 초기화 절차로 문제가 해결되지 않는 경우에는 하드 초기화 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="50446-142">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="50446-143">**볼륨 작게** + **전원** 단추를 15초 동안 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="50446-144">장치가 자동으로 재부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="50446-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="50446-145">장치를 호스트 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="50446-146">장치 관리자를 엽니다.(Windows 10에서는 \*\* Windows\*\* 키를 누른 다음 **X** 키를 누르고 **장치 관리자**를 선택)</span><span class="sxs-lookup"><span data-stu-id="50446-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="50446-147">아래 이미지에 표시된 것처럼 장치에서 *Microsoft HoloLens*로 제대로 열거 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 장치 관리자 2](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="50446-149">장치 클린 리플래시</span><span class="sxs-lookup"><span data-stu-id="50446-149">Clean-reflash the device</span></span>

<span data-ttu-id="50446-150">드물게 일부 상황에서 HoloLens 2를 ‘클린 플래시’해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="50446-151">클린 리플래시는 다음 문제에 영향을 주지 않을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="50446-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="50446-152">색상 균일성 표시</span><span class="sxs-lookup"><span data-stu-id="50446-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="50446-153">부팅시 소리가 나지만 디스플레이 출력이 없음</span><span class="sxs-lookup"><span data-stu-id="50446-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="50446-154">1-3-5-LED 패턴</span><span class="sxs-lookup"><span data-stu-id="50446-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="50446-155">과열</span><span class="sxs-lookup"><span data-stu-id="50446-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="50446-156">OS 충돌(응용 프로그램 충돌과는 다름)</span><span class="sxs-lookup"><span data-stu-id="50446-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="50446-157">장치를 리플래시하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="50446-158">둘 다 Windows 스토어에서 고급 복구 도우미를 먼저 [설치해야 합니다.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="50446-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="50446-159">장치를 리플래시하면 TPM 초기화 정보를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="50446-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="50446-160">기본적으로 고급 복구 도우미는 최신 기능 릴리스 빌드를 다운로드할 수 있도록 설정되어 있습니다. 여기를 체크표시하여 [릴리스 노트](hololens-release-notes.md#)를 읽어보고 최신 기능 릴리스에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="50446-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="50446-161">최신 HoloLens 2 FFU(Full Flash Update) 패키지를 다운로드하여 고급 복구 도우미를 통해 장치를 리플래시하려면 [여기를 클릭하여 최신 월간 HoloLens 2 이미지를 다운로드하세요](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="50446-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="50446-162">이 버전은 일반적으로 사용할 수 있는 최신 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="50446-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="50446-163">리플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 감지할 준비가 되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 클린 리플래시 스크린샷](images/ARC1.png)

### <span data-ttu-id="50446-165">일반 절차</span><span class="sxs-lookup"><span data-stu-id="50446-165">Normal procedure</span></span>

1. <span data-ttu-id="50446-166">HoloLens 장치가 실행 중일 때 고급 복구 도우미 앱을 미리 열려 있는 Windows 10 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="50446-167">장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 클린 리플래시 초기 화면](images/ARC2.png)

3. <span data-ttu-id="50446-169">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="50446-170">수동 절차</span><span class="sxs-lookup"><span data-stu-id="50446-170">Manual procedure</span></span>

<span data-ttu-id="50446-171">장치가 제대로 시작되지 않는 경우에는 HoloLens 2 장치를 복구 모드로 전환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-171">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="50446-172">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="50446-173">**전원** 버튼을 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="50446-174">모든 LED가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="50446-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="50446-175">**볼륨 크게 버튼**을 누른 상태에서 **전원 버튼**을 눌렀다가 놓아 장치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="50446-176">15초 후 **볼륨 크게** 버튼을 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="50446-177">LED 5개 중 가운데 LED만 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="50446-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="50446-178">호스트 PC에 장치를 연결하고 장치 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50446-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="50446-179">(Windows 10에서는 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자**를 클릭) 아래 이미지에 표시된 것처럼 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="50446-181">장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 클린 리플래시 화면](images/ARC2.png)

6. <span data-ttu-id="50446-183">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="50446-184">앱 스토어를 사용하지 않고 ARC 다운로드</span><span class="sxs-lookup"><span data-stu-id="50446-184">Download ARC without using the app store</span></span>

<span data-ttu-id="50446-185">IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자가 '오프라인' 배포 경로를 통해 이 앱을 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-185">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="50446-186">IT 관리자가 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-186">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="50446-187">이 가이드는 고급 복구 도우미에 중점을 두지만 다른 ‘오프라인’ 앱에 대해서도 이 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-187">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="50446-188">배포 경로를 설정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-188">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="50446-189">[비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com)로 이동하고 Azure Active Directory ID를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-189">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="50446-190">**관리 – 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-190">Go to **Manage – Settings**.</span></span> <span data-ttu-id="50446-191">**장바구니**에서 **오프라인 앱 표시**를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="50446-191">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="50446-192">**내 그룹샵**으로 이동하여 [\**_고급 복구 도우미_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-192">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="50446-193">_\*라이선스 유형\*\*을 \*\*_오프라인_\*_ 으로 변경하고 _\*관리\*\*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-193">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="50446-194">**오프라인으로 사용하기 위해 패키지 다운로드**에서 두 번째 파란색 **다운로드** 버튼을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-194">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="50446-195">파일 확장명이 *.appxbundle*인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-195">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="50446-196">이 단계에서 데스크톱 PC에서 인터넷에 액세스할 수 있으면 패키지를 두 번 클릭하여 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-196">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="50446-197">대상 PC가 인터넷에 연결되어 있지 않으면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="50446-197">If the destination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="50446-198">인코딩되지 않은 라이선스를 선택한 다음 **라이선스 생성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-198">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="50446-199">**필수 프레임워크**에서 **다운로드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-199">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="50446-200">DISM을 통해 종속성과 라이선스를 사용하여 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-200">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="50446-201">관리자 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-201">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="50446-202">이 코드 예제에 나와있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-202">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="50446-203">예제의 위치와 다른 다운로드 위치를 선택했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-203">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="50446-204">필요에 따라 명령을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="50446-204">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="50446-205">고급 복구 도우미를 사용하여 FFU를 오프라인으로 설치하려는 경우 플래시 이미지를 다운로드하면 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50446-205">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="50446-206">[**HoloLens 2의 현재 이미지를 다운로드합니다**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="50446-206">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="50446-207">다른 리소스:</span><span class="sxs-lookup"><span data-stu-id="50446-207">Other resources:</span></span>
- [<span data-ttu-id="50446-208">오프라인 앱 배포</span><span class="sxs-lookup"><span data-stu-id="50446-208">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="50446-209">DISM 앱 패키지 (.appx 또는 .appxbundle) 서비스 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="50446-209">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
