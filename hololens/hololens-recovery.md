---
title: HoloLens 다시 시작, 초기화 또는 복구
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857766"
---
# <span data-ttu-id="3023c-104">HoloLens 다시 시작, 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="3023c-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="3023c-105">장치 충전</span><span class="sxs-lookup"><span data-stu-id="3023c-105">Charging the device</span></span>

<span data-ttu-id="3023c-106">가능하다면 문제 해결 절차를 시작하기 전에 적어도 장치가 20%에서 40% 정도 충전이 되어있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="3023c-107">HoloLens 2 장치와 함께 제공되는 충전기와 USB 유형 C 케이블을 사용하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3023c-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="3023c-108">사용할 수 없는 경우에는 사용 가능한 충전기가 적어도 15W의 전력을 지원하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="3023c-109">USB를 사용해 PC로 장치를 충전하면 시간이 아주 오래 걸리므로 PC는 가능하다면 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3023c-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="3023c-110">장치가 제대로 부팅되고 실행되고 있는 경우에는 세 가지 방법으로 배터리 충전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="3023c-111">HoloLens 장치 UI의 주 메뉴에서 확인</span><span class="sxs-lookup"><span data-stu-id="3023c-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="3023c-112">전원 버튼 가까이 있는 LED를 사용해서 확인 (40%에서는 LED가 최소 2개 켜진 것을 볼 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="3023c-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="3023c-113">호스트 PC에서 파일 탐색기 창을 열고 ‘이 PC’ 아래의 왼쪽에서 HoloLens 2 장치를 찾아서 확인</span><span class="sxs-lookup"><span data-stu-id="3023c-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="3023c-114">a.</span><span class="sxs-lookup"><span data-stu-id="3023c-114">a.</span></span> <span data-ttu-id="3023c-115">장치의 이름을 마우스 오른쪽 단추로 클릭하고 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="3023c-116">장치의 배터리 잔량이 표시된 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 초기화복구](images/ResetRecovery2.png)

<span data-ttu-id="3023c-118">장치를 시작 메뉴로 부팅할 수 없는 경우 호스트 PC에 있는 LED와 열거를 기록해 두고 문제 해결 가이드를 따르세요(https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="3023c-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="3023c-119">장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않는 경우 장치를 호스트 PC에 다시 연결하지 않고 \*\*\*\* 하드 초기화 절차**를 실행하되 대신 전원 공급 장치에 연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="3023c-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="3023c-120">장치가 충전될 때까지 1시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="3023c-121">장치 초기화</span><span class="sxs-lookup"><span data-stu-id="3023c-121">Reset the device</span></span>

<span data-ttu-id="3023c-122">특정 상황에서는 소프트웨어에서 SW UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="3023c-123">표준 절차</span><span class="sxs-lookup"><span data-stu-id="3023c-123">Standard procedure</span></span>
1. <span data-ttu-id="3023c-124">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="3023c-125">**전원 버튼**을 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="3023c-126">모든 LED가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="3023c-127">2-3초 후 **전원 버튼**을 짧게 누르면 전원 버튼 가까이 있는 LED가 켜진 후 불이 켜지고 장치가 부팅되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="3023c-128">장치를 호스트 PC에 연결하고 장치 관리자(Windows 10에서는 \*\*\*\*‘Windows’ 키**를 누른 후 **‘x’ 키**를 누른 다음 ‘장치 관리자’를 클릭)를 열어 아래 그림과 같이 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="3023c-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="3023c-130">하드 초기화 절차</span><span class="sxs-lookup"><span data-stu-id="3023c-130">Hard-reset procedure</span></span>

<span data-ttu-id="3023c-131">표준 초기화 절차로 문제가 해결되지 않는 경우에는 하드 초기화 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="3023c-132">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="3023c-133">**볼륨 작게 + 전원 버튼**을 15초간 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="3023c-134">장치가 자동으로 재부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="3023c-135">장치를 호스트 PC에 연결하고 장치 관리자(Windows 10에서는 \*\*\*\*‘Windows’ 키**를 누른 후 **‘x’ 키**를 누른 다음 ‘장치 관리자’를 클릭)를 열어 아래 그림과 같이 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="3023c-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="3023c-137">장치 클린 리플래시</span><span class="sxs-lookup"><span data-stu-id="3023c-137">Clean reflash the device</span></span>

<span data-ttu-id="3023c-138">드물게 일부 상황에서 장치를 클린 플래시해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="3023c-139">HoloLens 2 장치를 리플래시하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="3023c-140">모든 리플래시 절차를 수행하려면[](https://www.microsoft.com/store/productId/9P74Z35SFRS8)Windows 스토어에서 고급 복구 도우미 앱을 설치[해야 합니다.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="3023c-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="3023c-141">장치를 초기화하면 TPM 초기화를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="3023c-142">고급 복구 도우미는 현재 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004)에 대한 기능 릴리스 빌드를 다운로드하도록 설정되어 있습니다. 최신 HoloLens 2 FFU를 다운로드하여 고급 복구 도우미를 통해 장치를 플래시하려면[](https://aka.ms/hololens2download)여기[에서 다운로드할 수 있습니다.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="3023c-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="3023c-143">이 기능은 최신 상태로 유지되며 일반적으로 사용할 수 있는 최신 빌드와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="3023c-144">플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 감지할 준비가 되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 클린 리플래시](images/ARC1.png)

### <span data-ttu-id="3023c-146">일반 절차</span><span class="sxs-lookup"><span data-stu-id="3023c-146">Normal procedure</span></span>

1. <span data-ttu-id="3023c-147">HoloLens 장치가 실행 중일 때 고급 복구 도우미 앱을 미리 실행해 놓은 Windows 10 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="3023c-148">장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![HoloLens 2 클린 리플래시](images/ARC2.png)

3. <span data-ttu-id="3023c-150">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="3023c-151">수동 절차</span><span class="sxs-lookup"><span data-stu-id="3023c-151">Manual procedure</span></span>

<span data-ttu-id="3023c-152">장치가 제대로 부팅되지 않는 경우에는 HoloLens 2 장치를 복구 모드로 전환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="3023c-153">유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="3023c-154">**전원 버튼**을 15초간 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="3023c-155">모든 LED가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="3023c-156">**볼륨 크게 버튼**을 누른 상태에서 **전원 버튼**을 눌렀다가 놓아 장치를 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="3023c-157">15초 후 볼륨 크게 버튼을 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="3023c-158">장치의 5개 LED 중에서 가운데 LED만 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="3023c-159">장치를 호스트 PC에 연결하고 장치 관리자(Windows 10에서는 \*\*\*\*‘Windows’ 키**를 누른 후 **‘x’ 키**를 누른 다음 ‘장치 관리자’를 클릭)를 열어 아래 이미지와 같이 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="3023c-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="3023c-161">장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![HoloLens 2 클린 리플래시](images/ARC2.png)

6. <span data-ttu-id="3023c-163">고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 플래시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="3023c-164">앱 스토어를 사용하지 않고 ARC 다운로드</span><span class="sxs-lookup"><span data-stu-id="3023c-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="3023c-165">IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자가 다른 '오프라인' 배포 경로를 통해 이 앱을 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="3023c-166">이 프로세스는 2단계에 표시된 것처럼 다른 앱에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="3023c-167">이 가이드에서는 고급 복구 도우미에 중점을 두며 다른 오프라인 앱에 대해서는 수정될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="3023c-168">이 배포 경로는 다음 단계를 통해 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="3023c-169">[비즈니스용 스토어 웹 사이트](https://businessstore.microsoft.com)로 이동하여 Azure AD ID로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="3023c-170">관리 – 설정으로 이동하여 https://businessstore.microsoft.com/manage/settings/shop에 설명된 대로 **쇼핑 환경**에서 **오프라인 앱 표시**를 켭니다. </span><span class="sxs-lookup"><span data-stu-id="3023c-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="3023c-171">**내 그룹샵**으로 이동하여 고급 복구 도우미 앱을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="3023c-172">**라이선스 유형** 상자를 오프라인으로 변경하고 **관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="3023c-173">오프라인으로 사용하기 위해 패키지 다운로드에서 두 번째 파란색 **‘다운로드’** 버튼을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="3023c-174">파일 확장명이 .appxbundle인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="3023c-175">이 단계에서 데스크톱 PC에서 인터넷에 연결되어 있으면 두 번 클릭하여 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="3023c-176">IT 관리자가 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="3023c-177">대상 PC가 인터넷에 연결되어 있지 않으면 몇 가지 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="3023c-178">인코딩되지 않은 라이선스를 선택하고 **‘라이선스 생성’** 을 클릭한 다음 **‘필수 프레임 워크’** 에서 **‘다운로드’** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="3023c-179">인터넷에 연결할 수 없는 PC는 DISM으로 종속성과 라이선스를 사용하여 패키지를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="3023c-180">관리자 명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="3023c-181">이 코드 예제에 나와 있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="3023c-182">제공된 예제의 위치와 다른 다운로드 위치를 선택했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="3023c-183">필요에 따라 변경하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3023c-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="3023c-184">고급 복구 도우미를 사용하여 FFU(Full Flash Update)를 오프라인으로 설치하려는 경우 플래시 이미지를 사용할 수 있도록 다운로드하는 것이 유용할 수 있습니다. 여기 [](https://aka.ms/hololens2download)HoloLens 2의 현재 이미지[가 있습니다.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="3023c-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="3023c-185">다른 리소스:</span><span class="sxs-lookup"><span data-stu-id="3023c-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


