---
title: Bluetooth 및 USB-C 디바이스에 연결
description: HoloLens 혼합 현실 장치에서 Bluetooth 및 USB-C 장치 및 액세서리에 연결을 시작하세요.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924182"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="1d1ff-103">Bluetooth 및 USB-C 디바이스에 연결</span><span class="sxs-lookup"><span data-stu-id="1d1ff-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="1d1ff-104">Bluetooth 장치 페어링</span><span class="sxs-lookup"><span data-stu-id="1d1ff-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="1d1ff-105">HoloLens 2는 다음 Bluetooth 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="1d1ff-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="1d1ff-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="1d1ff-107">마우스</span><span class="sxs-lookup"><span data-stu-id="1d1ff-107">Mouse</span></span>
    - <span data-ttu-id="1d1ff-108">Keyboard</span><span class="sxs-lookup"><span data-stu-id="1d1ff-108">Keyboard</span></span>
- <span data-ttu-id="1d1ff-109">오디오 출력(A2DP) 장치</span><span class="sxs-lookup"><span data-stu-id="1d1ff-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="1d1ff-110">HoloLens 2는 다음과 같은 Bluetooth API를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="1d1ff-111">GATT [서버](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) 및 [클라이언트](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="1d1ff-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="1d1ff-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="1d1ff-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="1d1ff-113">실제로 HID 및 GATT 장치를 사용하려면 Microsoft Store에서 해당하는 도우미 앱을 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="1d1ff-114">HoloLens(1세대)는 다음 Bluetooth 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="1d1ff-115">마우스</span><span class="sxs-lookup"><span data-stu-id="1d1ff-115">Mouse</span></span>
- <span data-ttu-id="1d1ff-116">Keyboard</span><span class="sxs-lookup"><span data-stu-id="1d1ff-116">Keyboard</span></span>
- [<span data-ttu-id="1d1ff-117">HoloLens(1세대) 클릭커</span><span class="sxs-lookup"><span data-stu-id="1d1ff-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="1d1ff-118">다른 유형의 Bluetooth 장치(예: 스피커, 헤드셋, 스마트폰, 게임 패드)가 HoloLens 설정에서 사용 가능한 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="1d1ff-119">그러나 이러한 장치는 HoloLens(1세대)에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="1d1ff-120">자세한 내용은 [HoloLens 설정에 장치를 사용 가능으로 표시되지만 장치가 작동하지 않음](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="1d1ff-121">Bluetooth 키보드 또는 마우스 연결</span><span class="sxs-lookup"><span data-stu-id="1d1ff-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="1d1ff-122">키보드 또는 마우스를 켜고 검색 가능하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="1d1ff-123">장치를 검색 가능하게 만드는 방법에 대한 자세한 내용은 장치(또는 해당 문서) 정보를 참고하거나 제조업체의 웹 사이트를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="1d1ff-124">블룸 동작(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작** 으로 이동한 다음 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="1d1ff-125">**장치** 를 선택하고 Bluetooth가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="1d1ff-126">장치 이름이 표시되면 **페어링** 을 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="1d1ff-127">Bluetooth 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1d1ff-127">Disable Bluetooth</span></span>

<span data-ttu-id="1d1ff-128">이 절차는 Bluetooth 라디오의 RF 구성 요소를 끄고 Microsoft HoloLens에서 모든 Bluetooth 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="1d1ff-129">블룸 동작(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작** 으로 이동한 다음 **설정** > **장치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="1d1ff-130">**Bluetooth** 에 대한 슬라이더 스위치를 **Off** 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="1d1ff-131">HoloLens 2: USB-C 장치 연결</span><span class="sxs-lookup"><span data-stu-id="1d1ff-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="1d1ff-132">HoloLens 2는 다음 USB-C 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="1d1ff-133">대용량 저장 장치(예: 휴대용 드라이브)</span><span class="sxs-lookup"><span data-stu-id="1d1ff-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="1d1ff-134">이더넷 어댑터(이더넷 및 충전 포함)</span><span class="sxs-lookup"><span data-stu-id="1d1ff-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="1d1ff-135">USB-C-3.5mm 디지털 오디오 어댑터</span><span class="sxs-lookup"><span data-stu-id="1d1ff-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="1d1ff-136">USB-C 디지털 오디오 헤드셋(헤드셋 어댑터 및 충전 포함)</span><span class="sxs-lookup"><span data-stu-id="1d1ff-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="1d1ff-137">USB-C 외부 마이크([Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 이상)</span><span class="sxs-lookup"><span data-stu-id="1d1ff-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="1d1ff-138">유선 마우스</span><span class="sxs-lookup"><span data-stu-id="1d1ff-138">Wired mouse</span></span>
- <span data-ttu-id="1d1ff-139">유선 키보드</span><span class="sxs-lookup"><span data-stu-id="1d1ff-139">Wired keyboard</span></span>
- <span data-ttu-id="1d1ff-140">콤비네이션 PD 허브(USB A 및 PD 충전)</span><span class="sxs-lookup"><span data-stu-id="1d1ff-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="1d1ff-141">고객 피드백에 따라 USB-C를 통해 HoloLens에 직접 테더링되는 셀룰러 연결에 대한 제한된 지원을 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="1d1ff-142">자세한 내용은 [셀룰러 및 5G에 연결](hololens-cellular.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="1d1ff-143">USB-C 외부 마이크 지원</span><span class="sxs-lookup"><span data-stu-id="1d1ff-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d1ff-144">**USB 마이크를 꽂으면 입력 장치로 자동으로 설정되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="1d1ff-145">USB-C 헤드폰 세트를 연결하는 경우 사용자는 헤드폰의 오디오가 자동으로 헤드폰으로 리디렉션되는 것을 볼 수 있지만, HoloLens OS는 다른 입력 장치보다 내부 마이크 배열에 우선 순위를 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="1d1ff-146">**USB-C 마이크를 사용하려면 다음 단계를 수행합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d1ff-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="1d1ff-147">외부 마이크는 [Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 이상보다 이전 빌드에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="1d1ff-148">사용자는 **소리** 설정 패널을 사용하여 USB C 연결 외부 마이크를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="1d1ff-149">USB-C 마이크는 호출, 기록 등에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="1d1ff-150">**설정** 앱을 열고 **시스템** > **소리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="1d1ff-152">**Remote Assist** 에서 외부 마이크를 사용하려면 사용자가 “소리 장치 관리” 하이퍼링크를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="1d1ff-153">그런 다음 드롭다운을 사용하여 외부 마이크를 **기본값** 또는 **Communications Default** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="1d1ff-154">**기본값** 을 선택하면 외부 마이크가 어디에서나 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="1d1ff-155">**Communications Default** 를 선택하면 외부 마이크가 Remote Assist 및 기타 통신 앱에서 사용되지만 다른 작업에는 여전히 HoloLens 마이크 배열이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![소리 장치 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="1d1ff-158">Bluetooth 마이크 지원이란?</span><span class="sxs-lookup"><span data-stu-id="1d1ff-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="1d1ff-159">안타깝게도 Bluetooth 마이크는 현재 HoloLens 2에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="1d1ff-160">USB-C 허브</span><span class="sxs-lookup"><span data-stu-id="1d1ff-160">USB-C Hubs</span></span>

<span data-ttu-id="1d1ff-161">일부 사용자는 한 번에 여러 장치를 연결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="1d1ff-162">다른 연결된 장치와 함께 [USB-C 마이크](#usb-c-external-microphone-support)를 사용하려는 사용자의 경우 USB-C 허브가 고객의 요구에 맞을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="1d1ff-163">Microsoft는 이러한 장치를 테스트하지 않았으며 특정 브랜드를 추천할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="1d1ff-164">**USB-C 허브 및 연결된 장치에 대한 요구 사항:**</span><span class="sxs-lookup"><span data-stu-id="1d1ff-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="1d1ff-165">연결된 장치에는 드라이버를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="1d1ff-166">연결된 모든 장치의 총 소비전력은 4.5W 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="1d1ff-167">Miracast에 연결</span><span class="sxs-lookup"><span data-stu-id="1d1ff-167">Connect to Miracast</span></span>

<span data-ttu-id="1d1ff-168">Miracst를 사용하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="1d1ff-169">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-169">Do one of the following:</span></span>  

   - <span data-ttu-id="1d1ff-170">**시작** 메뉴를 열고 **디스플레이** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="1d1ff-171">**시작** 메뉴를 응시하면서 "Connect"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="1d1ff-172">나타나는 장치 목록에서 사용 가능한 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="1d1ff-173">페어링이 완료되면 프로젝션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ff-173">Complete the pairing to begin projecting.</span></span>
