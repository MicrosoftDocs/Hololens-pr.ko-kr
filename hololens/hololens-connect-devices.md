---
title: Bluetooth 및 USB-C 장치에 연결
description: 이 가이드는 Bluetooth 및 USB-C 장치 및 액세서리에 연결하는 과정을 안내합니다.
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
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881248"
---
# <span data-ttu-id="e35e0-103">Bluetooth 및 USB-C 장치에 연결</span><span class="sxs-lookup"><span data-stu-id="e35e0-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="e35e0-104">Bluetooth 장치 페어링</span><span class="sxs-lookup"><span data-stu-id="e35e0-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="e35e0-105">HoloLens 2는 다음 Bluetooth 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="e35e0-106">마우스</span><span class="sxs-lookup"><span data-stu-id="e35e0-106">Mouse</span></span>
- <span data-ttu-id="e35e0-107">키보드</span><span class="sxs-lookup"><span data-stu-id="e35e0-107">Keyboard</span></span>
- <span data-ttu-id="e35e0-108">A2DP(Bluetooth 오디오 출력) 장치</span><span class="sxs-lookup"><span data-stu-id="e35e0-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="e35e0-109">외부 마이크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-109">External microphones cannot be used.</span></span> <span data-ttu-id="e35e0-110">HoloLens 2는 기본 제공 [마이크 배열](hololens2-hardware.md#audio-and-speech)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="e35e0-111">HoloLens 2(1세대)는 다음 Bluetooth 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="e35e0-112">마우스</span><span class="sxs-lookup"><span data-stu-id="e35e0-112">Mouse</span></span>
- <span data-ttu-id="e35e0-113">키보드</span><span class="sxs-lookup"><span data-stu-id="e35e0-113">Keyboard</span></span>
- <span data-ttu-id="e35e0-114">HoloLens(1세대) 클릭커</span><span class="sxs-lookup"><span data-stu-id="e35e0-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="e35e0-115">다른 유형의 Bluetooth 장치(예: 스피커, 헤드셋, 스마트폰, 게임 패드)가 HoloLens 설정에서 사용 가능한 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="e35e0-116">그러나 이 장치는 HoloLens(1세대)에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="e35e0-117">[HoloLens 설정에서 사용 가능한 장치로 보이지만 작동하지 않는 장치](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e35e0-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="e35e0-118">Bluetooth 키보드 또는 마우스 연결</span><span class="sxs-lookup"><span data-stu-id="e35e0-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="e35e0-119">키보드 또는 마우스를 켜고 검색 가능하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="e35e0-120">장치를 검색 가능하게 하는 방법에 대한 자세한 내용은 장치(또는 해당 문서) 정보를 참고하거나 제조 업체의 웹 사이트를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="e35e0-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="e35e0-121">피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="e35e0-122">**장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="e35e0-123">장치 이름이 표시되면 **연결**을 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="e35e0-124">HoloLens(1세대): 클리커 연결</span><span class="sxs-lookup"><span data-stu-id="e35e0-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="e35e0-125">피어오르는 동작을 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="e35e0-126">**장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="e35e0-127">펜 끝을 사용하여 클리커 상태 표시등이 흰색으로 깜박일 때까지 클리커 연결 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="e35e0-128">상태 표시등이 깜박일 때까지 단추를 누르고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="e35e0-129">페어링 단추는 클리커 아래쪽에 손가락 루프 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![페어링 단추는 손가락 루프 옆에 있습니다.](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="e35e0-131">페어링 화면에서 **클리커** > **연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="e35e0-132">HoloLens 2: USB-C 장치 연결</span><span class="sxs-lookup"><span data-stu-id="e35e0-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="e35e0-133">HoloLens 2는 다음 USB-C 장치 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="e35e0-134">대용량 저장 장치 (예: 엄지 드라이브)</span><span class="sxs-lookup"><span data-stu-id="e35e0-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="e35e0-135">이더넷 어댑터 (이더넷 및 충전 포함)</span><span class="sxs-lookup"><span data-stu-id="e35e0-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="e35e0-136">USB-C 부터 3.5 mm 디지털 오디오 어댑터</span><span class="sxs-lookup"><span data-stu-id="e35e0-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="e35e0-137">USB-C 디지털 오디오 헤드셋(헤드셋 어댑터 및 충전 포함)</span><span class="sxs-lookup"><span data-stu-id="e35e0-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="e35e0-138">유선 마우스</span><span class="sxs-lookup"><span data-stu-id="e35e0-138">Wired mouse</span></span>
- <span data-ttu-id="e35e0-139">유선 키보드</span><span class="sxs-lookup"><span data-stu-id="e35e0-139">Wired keyboard</span></span>
- <span data-ttu-id="e35e0-140">콤비네이션 PD 허브(USB A 및 PD 충전)</span><span class="sxs-lookup"><span data-stu-id="e35e0-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="e35e0-141">HoloLens가 USB-C 연결을 사용하는 일부 모바일 장치를 이더넷 어댑터로 인식 하기 때문에 Windows Holographic 버전 2004부터 테더링 구성에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="e35e0-142">별도의 드라이버 및/또는 구성을 위해 설치된 응용 프로그램이 필요한 USB LTE 모뎀은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="e35e0-143">Miracast에 연결</span><span class="sxs-lookup"><span data-stu-id="e35e0-143">Connect to Miracast</span></span>

<span data-ttu-id="e35e0-144">Miracst를 사용 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="e35e0-145">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-145">Do one of the following:</span></span>  

   - <span data-ttu-id="e35e0-146">**시작** 메뉴를 열고 디스플레이 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="e35e0-147">**시작** 메뉴를 응시하며 "연결" 이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="e35e0-148">나타나는 장치 목록에서 사용 가능한 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="e35e0-149">페어링이 완료되면 프로젝션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="e35e0-150">Bluetooth 해제</span><span class="sxs-lookup"><span data-stu-id="e35e0-150">Disable Bluetooth</span></span>

<span data-ttu-id="e35e0-151">이 절차는 Bluetooth 라디오의 RF 구성 요소를 해제하고 Microsoft HoloLens에서 모든 Bluetooth 기능을 사용 하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="e35e0-152">피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정** > **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="e35e0-153">**Bluetooth** 슬라이더 스위치를 **해제** 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35e0-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
