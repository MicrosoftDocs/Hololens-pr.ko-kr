---
title: Bluetooth 및 USB-C 장치에 연결
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
ms.openlocfilehash: 1b4f95f43fc60dffa2ca75322466857a0a20a0a7
ms.sourcegitcommit: 145bbabc390f626ba6633fa49423c38656cd2224
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "11302272"
---
# <span data-ttu-id="ae893-103">Bluetooth 및 USB-C 장치에 연결</span><span class="sxs-lookup"><span data-stu-id="ae893-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="ae893-104">외부 마이크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-104">External microphones cannot be used.</span></span> <span data-ttu-id="ae893-105">HoloLens 2는 기본 제공 [마이크 배열](hololens2-hardware.md#audio-and-speech)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="ae893-106">Bluetooth 장치 페어링</span><span class="sxs-lookup"><span data-stu-id="ae893-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="ae893-107">HoloLens 2는 다음 Bluetooth 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="ae893-108">마우스</span><span class="sxs-lookup"><span data-stu-id="ae893-108">Mouse</span></span>
- <span data-ttu-id="ae893-109">키보드</span><span class="sxs-lookup"><span data-stu-id="ae893-109">Keyboard</span></span>
- <span data-ttu-id="ae893-110">A2DP(Bluetooth 오디오 출력) 장치</span><span class="sxs-lookup"><span data-stu-id="ae893-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="ae893-111">HoloLens 2(1세대)는 다음 Bluetooth 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="ae893-112">마우스</span><span class="sxs-lookup"><span data-stu-id="ae893-112">Mouse</span></span>
- <span data-ttu-id="ae893-113">키보드</span><span class="sxs-lookup"><span data-stu-id="ae893-113">Keyboard</span></span>
- <span data-ttu-id="ae893-114">HoloLens(1세대) 클릭커</span><span class="sxs-lookup"><span data-stu-id="ae893-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="ae893-115">다른 유형의 Bluetooth 장치(예: 스피커, 헤드셋, 스마트폰, 게임 패드)가 HoloLens 설정에서 사용 가능한 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="ae893-116">그러나 이 장치는 HoloLens(1세대)에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="ae893-117">[HoloLens 설정에서 사용 가능한 장치로 보이지만 작동하지 않는 장치](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae893-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="ae893-118">Bluetooth 키보드 또는 마우스 연결</span><span class="sxs-lookup"><span data-stu-id="ae893-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="ae893-119">키보드 또는 마우스를 켜고 검색 가능하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="ae893-120">장치를 검색 가능하게 하는 방법에 대한 자세한 내용은 장치(또는 해당 문서) 정보를 참고하거나 제조 업체의 웹 사이트를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="ae893-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="ae893-121">피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="ae893-122">**장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="ae893-123">장치 이름이 표시되면 **연결**을 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="ae893-124">HoloLens(1세대): 클리커 연결</span><span class="sxs-lookup"><span data-stu-id="ae893-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="ae893-125">피어오르는 동작을 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="ae893-126">**장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="ae893-127">펜 끝을 사용하여 클리커 상태 표시등이 흰색으로 깜박일 때까지 클리커 연결 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="ae893-128">상태 표시등이 깜박일 때까지 단추를 누르고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="ae893-129">페어링 단추는 클리커 아래쪽에 손가락 루프 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>

   ![페어링 단추는 손가락 루프 옆에 있습니다.](images/use-hololens-clicker-1.png)

1. <span data-ttu-id="ae893-131">페어링 화면에서 **클리커** > **연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="ae893-132">Bluetooth 해제</span><span class="sxs-lookup"><span data-stu-id="ae893-132">Disable Bluetooth</span></span>

<span data-ttu-id="ae893-133">이 절차는 Bluetooth 라디오의 RF 구성 요소를 해제하고 Microsoft HoloLens에서 모든 Bluetooth 기능을 사용 하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="ae893-134">피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정** > **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="ae893-135">**Bluetooth** 슬라이더 스위치를 **해제** 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="ae893-136">HoloLens 2: USB-C 장치 연결</span><span class="sxs-lookup"><span data-stu-id="ae893-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="ae893-137">HoloLens 2는 다음 USB-C 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="ae893-138">대용량 저장 장치 (예: 엄지 드라이브)</span><span class="sxs-lookup"><span data-stu-id="ae893-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="ae893-139">이더넷 어댑터 (이더넷 및 충전 포함)</span><span class="sxs-lookup"><span data-stu-id="ae893-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="ae893-140">USB-C 부터 3.5 mm 디지털 오디오 어댑터</span><span class="sxs-lookup"><span data-stu-id="ae893-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="ae893-141">USB-C 디지털 오디오 헤드셋(헤드셋 어댑터 및 충전 포함)</span><span class="sxs-lookup"><span data-stu-id="ae893-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="ae893-142">유선 마우스</span><span class="sxs-lookup"><span data-stu-id="ae893-142">Wired mouse</span></span>
- <span data-ttu-id="ae893-143">유선 키보드</span><span class="sxs-lookup"><span data-stu-id="ae893-143">Wired keyboard</span></span>
- <span data-ttu-id="ae893-144">콤비네이션 PD 허브(USB A 및 PD 충전)</span><span class="sxs-lookup"><span data-stu-id="ae893-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="ae893-145">HoloLens가 USB-C 연결을 사용하는 일부 모바일 장치를 이더넷 어댑터로 인식 하기 때문에 Windows Holographic 버전 2004부터 테더링 구성에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="ae893-146">별도의 드라이버 및/또는 구성을 위해 설치된 응용 프로그램이 필요한 USB LTE 모뎀은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="ae893-147">고객 의견에 따라 USB-C를 통해 HoloLens에 직접 테더링된 휴대폰 연결에 대한 제한적 지원을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="ae893-148">테더링 연결은 일반 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 드라이버 구현을 지원하고 추가 드라이버나 응용 프로그램 설치가 필요하지 않은 장치에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="ae893-149">이러한 장치를 연결하면 HoloLens 2 네트워크 설정 UI에서 자동으로 새 이더넷 연결로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="ae893-150">해당 장치 제조업체에 일반 Microsoft RNDIS 드라이버 지원 여부에 대한 자세한 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ae893-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

### <span data-ttu-id="ae893-151">USB-C 허브</span><span class="sxs-lookup"><span data-stu-id="ae893-151">USB-C Hubs</span></span>

<span data-ttu-id="ae893-152">일부 사용자는 한 번에 여러 장치를 연결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-152">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="ae893-153">다른 연결된 장치와 함께 내부자 기능을 미리 보고 [USB-C 마이크 사용](hololens-insider.md#usb-c-external-microphone-support)을 원하는 사용자의 경우 USB-C 허브가 요구에 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-153">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="ae893-154">Microsoft는 이러한 장치를 테스트하지 않았으며 특정 브랜드를 추천할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-154">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="ae893-155">USB-C 허브 및 연결된 장치에 대한 요구 사항:</span><span class="sxs-lookup"><span data-stu-id="ae893-155">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="ae893-156">연결된 장치에는 드라이버를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-156">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="ae893-157">연결된 모든 장치의 총 전력 소모량은 4.5W 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-157">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <span data-ttu-id="ae893-158">Miracast에 연결</span><span class="sxs-lookup"><span data-stu-id="ae893-158">Connect to Miracast</span></span>

<span data-ttu-id="ae893-159">Miracst를 사용 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-159">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="ae893-160">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-160">Do one of the following:</span></span>  

   - <span data-ttu-id="ae893-161">**시작** 메뉴를 열고 디스플레이 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-161">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="ae893-162">**시작** 메뉴를 응시하며 "연결" 이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-162">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="ae893-163">나타나는 장치 목록에서 사용 가능한 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-163">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="ae893-164">페어링이 완료되면 프로젝션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ae893-164">Complete the pairing to begin projecting.</span></span>
