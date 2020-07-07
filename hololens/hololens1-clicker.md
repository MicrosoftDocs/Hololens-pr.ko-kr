---
title: HoloLens 클릭커 사용
description: 이 문서에서는 클릭커 페어링, 충전 및 복구를 포함한 HoloLens 클릭커 사용 방법을 간략하게 설명합니다.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 13b86c049ba8bb6ed67be202609d27c8d47ffc53
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829472"
---
# <span data-ttu-id="76030-104">HoloLens(1세대) 클릭커 사용</span><span class="sxs-lookup"><span data-stu-id="76030-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="76030-105">클릭커는 HoloLens(1세대)용으로 맞춤 제작되었으며 다른 방식으로 홀로그램과 상호 작용하게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="76030-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="76030-106">별도의 상자에 HoloLens(1세대)와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="76030-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="76030-107">핸드 제스처 대신 사용하여 앱을 선택하고, 스크롤, 이동하고, 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <span data-ttu-id="76030-108">클릭커 하드웨어 및 페어링</span><span class="sxs-lookup"><span data-stu-id="76030-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="76030-109">HoloLens(1세대) 클릭커에는 손가락 루프가 있어 홀드하기가 더 쉬워졌으며, 표시등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![HoloLens 클릭커](images/use-hololens-clicker-1.png)

### <span data-ttu-id="76030-111">클릭커 표시등</span><span class="sxs-lookup"><span data-stu-id="76030-111">Clicker indicator lights</span></span>

<span data-ttu-id="76030-112">클릭커 표시등의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="76030-113">**흰색으로 깜박입니다**.</span><span class="sxs-lookup"><span data-stu-id="76030-113">**Blinking white**.</span></span> <span data-ttu-id="76030-114">클릭커가 페어링 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="76030-115">**흰색으로 빠르게 깜박입니다**.</span><span class="sxs-lookup"><span data-stu-id="76030-115">**Fast-blinking white**.</span></span> <span data-ttu-id="76030-116">페어링에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-116">Pairing was successful.</span></span>
- <span data-ttu-id="76030-117">**계속 흰색으로 빛납니다**.</span><span class="sxs-lookup"><span data-stu-id="76030-117">**Solid white**.</span></span> <span data-ttu-id="76030-118">클릭커가 충전 중입니다.</span><span class="sxs-lookup"><span data-stu-id="76030-118">The clicker is charging.</span></span>
- <span data-ttu-id="76030-119">**주황색으로 깜박입니다**.</span><span class="sxs-lookup"><span data-stu-id="76030-119">**Blinking amber**.</span></span> <span data-ttu-id="76030-120">배터리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-120">The battery is low.</span></span>
- <span data-ttu-id="76030-121">**계속 주황색으로 빛납니다**.</span><span class="sxs-lookup"><span data-stu-id="76030-121">**Solid amber**.</span></span> <span data-ttu-id="76030-122">클릭커에 오류가 발생하면 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="76030-123">페어링 단추를 누른 상태에서 클릭하고 15초 동안 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <span data-ttu-id="76030-124">클릭커와 HoloLens(1세대) 페어링</span><span class="sxs-lookup"><span data-stu-id="76030-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="76030-125">블룸 제스처를 사용하여 **시작**으로 이동한 다음 **설정** > **장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="76030-126">상태 표시등이 흰색으로 깜박일 때까지 클리커의 페어링 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="76030-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="76030-127">페어링 화면에서 **클릭커** > **연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <span data-ttu-id="76030-128">클릭커 충전</span><span class="sxs-lookup"><span data-stu-id="76030-128">Charge the clicker</span></span>

<span data-ttu-id="76030-129">클릭커 배터리가 부족하면 배터리 표시등이 주황색으로 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="76030-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="76030-130">마이크로 USB 케이블을 USB 전원 공급 장치에 연결하여 장치를 충전합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <span data-ttu-id="76030-131">HoloLens(1세대)에서 클릭커 사용</span><span class="sxs-lookup"><span data-stu-id="76030-131">Use the clicker with HoloLens (1st gen)</span></span>

### <span data-ttu-id="76030-132">클릭커 홀드</span><span class="sxs-lookup"><span data-stu-id="76030-132">Hold the clicker</span></span>

<span data-ttu-id="76030-133">클리커를 가동하려면 마이크로 USB 포트가 손목쪽을 향하도록 루프를 약지 또는 중지 너머로 미끄러뜨립니다.</span><span class="sxs-lookup"><span data-stu-id="76030-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="76030-134">들여쓰기에 엄지를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-134">Rest your thumb in the indentation.</span></span>

![클릭커 홀드 방법](images/use-hololens-clicker-2.png)

### <span data-ttu-id="76030-136">클릭커 제스처</span><span class="sxs-lookup"><span data-stu-id="76030-136">Clicker gestures</span></span>

<span data-ttu-id="76030-137">클릭커 제스처는 HoloLens 핸드 제스처에 사용되는 큰 움직임이 아니라 작은 손목의 회전입니다.</span><span class="sxs-lookup"><span data-stu-id="76030-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="76030-138">그리고 HoloLens는 클릭커가 [제스처 프레임](hololens1-basic-usage.md) 외부에 있는 경우에도 제스처를 인식하고 클릭하므로 사용자가 가장 편한 위치에 클리커를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="76030-139">**선택**.</span><span class="sxs-lookup"><span data-stu-id="76030-139">**Select**.</span></span> <span data-ttu-id="76030-140">홀로그램, 단추 또는 다른 요소를 선택하려면 해당 요소를 응시한 다음 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="76030-141">**클릭한 다음 유지**.</span><span class="sxs-lookup"><span data-stu-id="76030-141">**Click and hold**.</span></span> <span data-ttu-id="76030-142">홀로그램을 이동하거나 크기를 조정하는 등 탭하고 유지에서와 동일한 일부 작업을 수행하기 위해 엄지로 단추를 클릭하고 계속 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="76030-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="76030-143">**스크롤**.</span><span class="sxs-lookup"><span data-stu-id="76030-143">**Scroll**.</span></span> <span data-ttu-id="76030-144">앱 바에서 **스크롤 도구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="76030-145">클릭하고 길게 누른 다음 클릭커를 위쪽, 아래쪽, 왼쪽 또는 오른쪽으로 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="76030-146">빠르게 스크롤하려면 스크롤 도구 중앙에서 손을 더 멀리 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="76030-147">**확대/축소**.</span><span class="sxs-lookup"><span data-stu-id="76030-147">**Zoom**.</span></span> <span data-ttu-id="76030-148">앱 바에서 **확대/축소 도구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="76030-149">클릭하고 길게 누른 다음 클릭커를 위쪽으로 회전하여 확대하거나 아래쪽으로 회전하여 축소합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="76030-150">Microsoft Edge를 사용할 때 확대/축소하려면 페이지를 응시하고 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <span data-ttu-id="76030-151">클릭커 다시 시작 또는 복구</span><span class="sxs-lookup"><span data-stu-id="76030-151">Restart or recover the clicker</span></span>

<span data-ttu-id="76030-152">다음은 HoloLens 클릭커가 응답하지 않거나 제대로 작동하지 않을 때 시도해 볼 수 있는 몇 가지 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="76030-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <span data-ttu-id="76030-153">클릭커 다시 시작</span><span class="sxs-lookup"><span data-stu-id="76030-153">Restart the clicker</span></span>

<span data-ttu-id="76030-154">펜 끝을 사용하여 페어링 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="76030-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="76030-155">동시에 클릭커를 15초 동안 클릭한 채로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="76030-156">클릭커가 HoloLens와 이미 연결된 경우 다시 시작한 후에 연결된 상태가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="76030-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="76030-157">클릭커가 켜지거나 다시 시작되지 않으면 HoloLens 충전기를 사용하여 충전해 보세요.</span><span class="sxs-lookup"><span data-stu-id="76030-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="76030-158">배터리가 매우 부족한 경우 흰색 표시등이 켜지는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <span data-ttu-id="76030-159">클릭커 다시 연결</span><span class="sxs-lookup"><span data-stu-id="76030-159">Re-pair the clicker</span></span>

<span data-ttu-id="76030-160">**설정** > **장치**를 선택하고 클릭커를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="76030-161">**제거**를 선택하고 몇 초 정도 기다린 다음 클릭커를 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <span data-ttu-id="76030-162">클릭커 복구</span><span class="sxs-lookup"><span data-stu-id="76030-162">Recover the clicker</span></span>

<span data-ttu-id="76030-163">클릭커를 다시 시작하고 다시 연결해도 문제가 해결되지 않으면 Windows Device Recovery Tool을 통해 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76030-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="76030-164">복구 프로세스에 시간이 걸릴 수 있으며 최신 버전의 클릭커 소프트웨어가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="76030-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="76030-165">이 도구를 사용하려면 Windows 10 이상을 실행하며 최소 4GB의 사용 가능한 저장소 공간이 있는 컴퓨터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="76030-166">클릭커를 복구하려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="76030-166">To recover the clicker:</span></span>

1. <span data-ttu-id="76030-167">컴퓨터에서 [Windows Device Recovery Tool(WDRT)](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="76030-168">HoloLens와 함께 제공된 마이크로 USB 케이블을 사용하여 클릭커를 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="76030-169">Windows Device Recovery Tool을 실행하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="76030-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="76030-170">클릭커가 자동으로 검색되지 않는 경우 **장치가 검색되지 않음**을 선택하고 지침에 따라 장치를 복구 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="76030-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
