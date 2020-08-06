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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915972"
---
# <span data-ttu-id="c4245-104">HoloLens 2 다시 시작, 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="c4245-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="c4245-105">장치 충전</span><span class="sxs-lookup"><span data-stu-id="c4245-105">Charge the device</span></span>

<span data-ttu-id="c4245-106">문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 20~40%정도 충전되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="c4245-107">HoloLens 2 장치와 함께 제공되는 충전기와 USB 유형 C 케이블을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c4245-107">Use the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="c4245-108">해당 액세서리를 사용할 수 없는 경우 사용할 수 있는 충전기가 최소 15W의 전원을 지원할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c4245-108">If those accessories aren't available, make sure the charger that's available can support at least 15 W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="c4245-109">가능하면 PC에 USB를 연결해 장치를 충전하지 마세요. 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-109">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="c4245-110">장치가 제대로 부팅되고 실행되고 있는 경우에는 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-110">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="c4245-111">HoloLens 장치 UI의 주 메뉴에서 확인</span><span class="sxs-lookup"><span data-stu-id="c4245-111">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="c4245-112">전원 버튼 가까이 있는 LED로 확인(40%에서는 LED가 최소 2개 켜진 것을 볼 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c4245-112">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
- <span data-ttu-id="c4245-113">호스트 PC에서 파일 탐색기를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾아서 확인</span><span class="sxs-lookup"><span data-stu-id="c4245-113">On your host PC, open File Explorer and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="c4245-114">장치를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-114">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="c4245-115">대화 상자에 배터리 충전 수준이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-115">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됩니다.](images/ResetRecovery2.png)

<span data-ttu-id="c4245-117">장치가 시작 메뉴로 부팅할 수 없는 경우 호스트 PC에 LED 모양과 장치 열거형을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-117">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="c4245-118">그런 다음 [문제 해결 가이드](https://docs.microsoft.com/hololens/hololens-troubleshooting)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-118">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="c4245-119">장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않으면 장치를 호스트 PC가 아닌 전원 공급 장치에 연결하고 *하드 초기화 절차*를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-119">If the state of the device doesn't match any of the states listed in the troubleshooting guide, do the *hard reset procedure* with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="c4245-120">장치가 충전될 때까지 1시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-120">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="c4245-121">장치 초기화</span><span class="sxs-lookup"><span data-stu-id="c4245-121">Reset the device</span></span>

<span data-ttu-id="c4245-122">특정 상황에서는 소프트웨어 UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-122">Under certain circumstances, you may have to manually reset the device without using the SW UI.</span></span>

### <span data-ttu-id="c4245-123">표준 절차</span><span class="sxs-lookup"><span data-stu-id="c4245-123">Standard procedure</span></span>
1. <span data-ttu-id="c4245-124">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-124">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="c4245-125">**전원** 버튼을 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-125">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="c4245-126">모든 LED가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="c4245-127">2-3초 후 **전원** 버튼을 짧게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-127">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="c4245-128">전원 버튼 옆에 있는 LED가 켜지며 장치가 시작되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-128">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="c4245-129">호스트 PC에 장치를 연결한 다음 장치 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-129">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="c4245-130">(Windows 10에서는 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자**를 클릭) 아래 이미지에 표시된 것처럼 장치가 *Microsoft HoloLens*로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-130">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="c4245-132">하드 초기화 절차</span><span class="sxs-lookup"><span data-stu-id="c4245-132">Hard-reset procedure</span></span>

<span data-ttu-id="c4245-133">표준 초기화 절차로 문제가 해결되지 않는 경우에는 하드 초기화 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-133">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="c4245-134">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-134">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="c4245-135">**볼륨 작게** + **전원** 단추를 15초 동안 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-135">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="c4245-136">장치가 자동으로 재부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-136">The device will automatically restart.</span></span>

4. <span data-ttu-id="c4245-137">장치를 호스트 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-137">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="c4245-138">장치 관리자를 엽니다.(Windows 10에서는 \*\* Windows\*\* 키를 누른 다음 **X** 키를 누르고 **장치 관리자**를 선택)</span><span class="sxs-lookup"><span data-stu-id="c4245-138">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="c4245-139">아래 이미지에 표시된 것처럼 장치에서 *Microsoft HoloLens*로 제대로 열거 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-139">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="c4245-141">장치 클린 리플래시</span><span class="sxs-lookup"><span data-stu-id="c4245-141">Clean-reflash the device</span></span>

<span data-ttu-id="c4245-142">드물게 일부 상황에서 HoloLens 2를 ‘클린 플래시’해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-142">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="c4245-143">장치를 리플래시하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-143">There are two ways to reflash the device.</span></span> <span data-ttu-id="c4245-144">두 가지 방법 모두 [Windows 스토어에서 고급 복구 도우미](https://www.microsoft.com/store/productId/9P74Z35SFRS8)를 먼저 설치해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="c4245-144">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="c4245-145">장치를 리플래시하면 TPM 초기화 정보를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-145">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="c4245-146">현재 고급 복구 도우미는 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004)에 대한 기능 릴리스 빌드를 다운로드하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-146">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="c4245-147">최신 HoloLens 2 FFU(Full Flash Update) 패키지를 다운로드하여 고급 복구 도우미를 통해 장치를 리플래시하려면 [여기에서 패키지를 다운로드하세요](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="c4245-147">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="c4245-148">이 버전은 일반적으로 사용할 수 있는 최신 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-148">This version is the latest generally available build.</span></span>

<span data-ttu-id="c4245-149">리플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 감지할 준비가 되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-149">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 클린 리플래시 스크린샷](images/ARC1.png)

### <span data-ttu-id="c4245-151">일반 절차</span><span class="sxs-lookup"><span data-stu-id="c4245-151">Normal procedure</span></span>

1. <span data-ttu-id="c4245-152">HoloLens 장치가 실행 중일 때 고급 복구 도우미 앱을 미리 열려 있는 Windows 10 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-152">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="c4245-153">장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-153">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 클린 리플래시 초기 화면](images/ARC2.png)

3. <span data-ttu-id="c4245-155">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-155">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="c4245-156">수동 절차</span><span class="sxs-lookup"><span data-stu-id="c4245-156">Manual procedure</span></span>

<span data-ttu-id="c4245-157">장치가 제대로 시작되지 않는 경우에는 HoloLens 2 장치를 복구 모드로 전환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-157">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="c4245-158">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-158">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="c4245-159">**전원** 버튼을 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-159">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="c4245-160">모든 LED가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-160">All LEDs should turn off.</span></span>

3. <span data-ttu-id="c4245-161">**볼륨 크게 버튼**을 누른 상태에서 **전원 버튼**을 눌렀다가 놓아 장치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-161">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="c4245-162">15초 후 **볼륨 크게** 버튼을 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-162">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="c4245-163">LED 5개 중 가운데 LED만 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-163">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="c4245-164">호스트 PC에 장치를 연결하고 장치 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-164">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="c4245-165">(Windows 10에서는 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자**를 클릭) 아래 이미지에 표시된 것처럼 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-165">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="c4245-167">장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 클린 리플래시 화면](images/ARC2.png)

6. <span data-ttu-id="c4245-169">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="c4245-170">앱 스토어를 사용하지 않고 ARC 다운로드</span><span class="sxs-lookup"><span data-stu-id="c4245-170">Download ARC without using the app store</span></span>

<span data-ttu-id="c4245-171">IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자가 '오프라인' 배포 경로를 통해 이 앱을 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-171">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="c4245-172">IT 관리자가 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-172">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="c4245-173">이 가이드는 고급 복구 도우미에 중점을 두지만 다른 ‘오프라인’ 앱에 대해서도 이 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-173">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="c4245-174">배포 경로를 설정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-174">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="c4245-175">[비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com)로 이동하고 Azure Active Directory ID를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-175">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="c4245-176">**관리 – 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-176">Go to **Manage – Settings**.</span></span> <span data-ttu-id="c4245-177">**장바구니**에서 **오프라인 앱 표시**를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-177">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="c4245-178">**내 그룹샵**으로 이동하여 [***고급 복구 도우미***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-178">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="c4245-179">**라이선스 유형**을 ***오프라인***으로 변경하고 **관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-179">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="c4245-180">**오프라인으로 사용하기 위해 패키지 다운로드**에서 두 번째 파란색 **다운로드** 버튼을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-180">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="c4245-181">파일 확장명이 *.appxbundle*인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-181">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="c4245-182">이 단계에서 데스크톱 PC에서 인터넷에 액세스할 수 있으면 패키지를 두 번 클릭하여 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-182">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="c4245-183">대상 PC가 인터넷에 연결되어 있지 않으면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-183">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="c4245-184">인코딩되지 않은 라이선스를 선택한 다음 **라이선스 생성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-184">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="c4245-185">**필수 프레임워크**에서 **다운로드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-185">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="c4245-186">DISM을 통해 종속성과 라이선스를 사용하여 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-186">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="c4245-187">관리자 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-187">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="c4245-188">이 코드 예제에 나와있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-188">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="c4245-189">예제의 위치와 다른 다운로드 위치를 선택했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-189">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="c4245-190">필요에 따라 명령을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-190">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="c4245-191">고급 복구 도우미를 사용하여 FFU를 오프라인으로 설치하려는 경우 플래시 이미지를 다운로드하면 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4245-191">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="c4245-192">[**HoloLens 2의 현재 이미지를 다운로드합니다**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="c4245-192">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="c4245-193">다른 리소스:</span><span class="sxs-lookup"><span data-stu-id="c4245-193">Other resources:</span></span>
- [<span data-ttu-id="c4245-194">오프라인 앱 배포</span><span class="sxs-lookup"><span data-stu-id="c4245-194">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="c4245-195">DISM 앱 패키지 (.appx 또는 .appxbundle) 서비스 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="c4245-195">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
