---
title: HoloLens 2 배터리 및 충전
description: HoloLens를 충전하고 외부 배터리 팩을 사용하는 방법입니다.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923587"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="13731-103">HoloLens 2 배터리 및 충전</span><span class="sxs-lookup"><span data-stu-id="13731-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="13731-104">이 페이지에서는 HoloLens 2 충전 및 외부 배터리 팩 사용에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="13731-105">장치 충전</span><span class="sxs-lookup"><span data-stu-id="13731-105">Charging the device</span></span>

<span data-ttu-id="13731-106">HoloLens 2와 함께 제공된 [충전기와 USB Type-C 케이블](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)을 사용하는 것이 장치를 충전하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="13731-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="13731-107">HoloLens 2에 포함된 충전기는 최대 9V/2A(18W)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="13731-108">제공된 벽면 충전기를 사용하는 경우 HoloLens 2 장치는 장치가 대기 중일 때 65분 이내에 배터리를 완전 충전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="13731-109">해당 액세서리를 사용할 수 없는 경우 사용 가능한 충전기가 최소 15W의 전력을 지원할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="13731-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="13731-110">가능하면 PC에 연결하여 USB를 통해 장치를 충전하지 마세요. 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="13731-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="13731-111">배터리 충전 수준 확인</span><span class="sxs-lookup"><span data-stu-id="13731-111">Checking the battery charge level</span></span>
<span data-ttu-id="13731-112">장치가 제대로 부팅되고 실행되고 있으면 다음과 같은 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="13731-113">HoloLens 장치 UI의 주 메뉴에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="13731-114">전원 단추 가까이에 있는 LED로 확인합니다(40% 충전의 경우 LED가 최소 2개 켜진 것을 볼 수 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="13731-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="13731-115">장치가 충전 중일 때는 배터리 표시등이 켜져 있고 현재 충전 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13731-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="13731-116">마지막 표시등은 페이드 인/페이드 아웃하여 활성 충전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13731-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="13731-117">HoloLens가 켜져 있으면 배터리 표시등이 배터리 잔량을 5단계로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="13731-118">5개의 표시등 중 하나만 켜져 있으면 배터리 잔량이 20% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="13731-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="13731-119">배터리 잔량이 매우 낮은 상태에서 장치를 켜려고 하면 표시등 1개가 잠깐 깜박인 다음 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="13731-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="13731-120">호스트 PC에서 **파일 탐색기** 를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="13731-121">장치를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="13731-122">대화 상자에 배터리 충전 잔량이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13731-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됨](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="13731-124">대체 충전 사양</span><span class="sxs-lookup"><span data-stu-id="13731-124">Alternative charging specifications</span></span>

<span data-ttu-id="13731-125">HoloLens 2는 최대 27W의 [USB 전력 전송](https://www.usb.org/usb-charger-pd) 소스로 충전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="13731-126">소스에서 최소 10W를 제공할 수 있는 경우 HoloLens 작동 시간을 연장할 수 있습니다(일부 워크로드의 경우 거의 무기한).</span><span class="sxs-lookup"><span data-stu-id="13731-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="13731-127">USB-A-USB-C 충전 케이블을 사용하면 충전이 7.5W로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="13731-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="13731-128">작동 시간은 연장되지만, USB-C-C로 사용하는 만큼 길지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="13731-129">HoloLens가 대기 모드인 경우 18W는 내부 배터리의 최대 충전율에 도달하기에 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="13731-130">HoloLens가 사용 중인 경우 HoloLens는 충전보다 작동에 우선 순위를 두므로 충전율이 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13731-131">HoloLens 2를 최소 5V/1.5A로 충전하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="13731-132">최소 5V/1.5를 제공할 수 없는 충전기는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="13731-133">외부 배터리 팩</span><span class="sxs-lookup"><span data-stu-id="13731-133">External Battery Packs</span></span>

<span data-ttu-id="13731-134">위의 사양을 충족하는 배터리 팩은 HoloLens 2와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="13731-135">그러나 일부 USB-C 배터리 팩은 동일한 USB-C 포트를 통해 재충전하고 전력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="13731-136">이러한 배터리 팩에서 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)를 구현하여 배터리 팩이 HoloLens에서 충전되지 않고 HoloLens를 충전하도록 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="13731-137">열 관리</span><span class="sxs-lookup"><span data-stu-id="13731-137">Managing Heat</span></span>

<span data-ttu-id="13731-138">모든 장치와 마찬가지로 HoloLens에는 열이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="13731-139">충전이 빠를수록 더 많은 열이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="13731-140">또한 낮은 배터리 수준에서 충전을 시작하면 배터리가 거의 가득 찬 상태에서 충전을 시작하는 것보다 더 많은 열이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="13731-141">뜨거운 환경에서 장시간 HoloLens를 작동해야 하는 고객은 다음과 같은 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="13731-142">내부 배터리가 완전히 충전된 경우에도 HoloLens 2를 외부 전원에 연결하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="13731-143">외부 배터리가 고갈되면 HoloLens는 내부 배터리로 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="13731-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="13731-144">위의 단계를 수행한 후에도 발열 문제가 있는 경우 충전을 1.5A로 제한하는 충전기 또는 배터리 팩을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="13731-145">내부 배터리는 계속 천천히 고갈되므로 이 옵션은 용량만큼의 작동 시간을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="13731-146">문제 해결</span><span class="sxs-lookup"><span data-stu-id="13731-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="13731-147">HoloLens 외부 배터리 충전</span><span class="sxs-lookup"><span data-stu-id="13731-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="13731-148">HoloLens 2가 외부 배터리로 충전되는 것이 아니라 HoloLens 2가 외부 배터리를 충전하는 경우 이는 배터리가 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)를 구현하지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13731-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="13731-149">이 문제를 해결하려면 최신 배터리 팩으로 전환하는 것이 좋지만 대신 USB-A를 USB-C 케이블로 전환해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13731-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="13731-150">이 경우 충전율은 7.5W로 제한된다는 점을 유념하세요.</span><span class="sxs-lookup"><span data-stu-id="13731-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
