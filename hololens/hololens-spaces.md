---
title: HoloLens를 사용하여 물리적 공간 매핑
description: HoloLens는 시간 경과에 따른 공간의 모양을 학습합니다. 사용자는 특정 방식으로 공간을 통과하여 HoloLens를 이동함으로써 이 프로세스가 가능하게 만듭니다.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, 설계, 공간 매핑, HoloLens, 표면 재구성, 메시, 머리 추적, 매핑
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 992b17160eb6ba6ca2f6c8b12e112b98ab154774
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829028"
---
# <span data-ttu-id="7b50b-105">HoloLens를 사용하여 물리적 공간 매핑</span><span class="sxs-lookup"><span data-stu-id="7b50b-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="7b50b-106">HoloLens는 홀로그램과 실제 세계를 혼합합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="7b50b-107">그러기 위해 HoloLens는 사용자 주위의 실제 세계에 대해 학습하고 해당 공간 내에 홀로그램 배치 위치를 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="7b50b-108">시간이 지남에 따라 HoloLens는 관찰한 환경의 *공간 맵*을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="7b50b-109">HoloLens는 환경 변화에 따라 맵을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="7b50b-110">로그인한 상태에서 장치가 켜져 있으면 HoloLens는 공간 맵을 만들고 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="7b50b-111">카메라가 공간을 향한 장치를 소지하거나 착용하는 경우 HoloLens는 해당 영역을 매핑하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="7b50b-112">HoloLens는 시간이 지남에 따라 자연스럽게 공간을 학습하는 반면에, HoloLens가 더 빠르고 효율적으로 공간을 매핑하도록 지원할 수 있는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="7b50b-113">HoloLens가 공간을 매핑하지 못하거나 보정 범위를 벗어나는 경우에는 HoloLens가 제한적 모드로 전환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="7b50b-114">제한적 모드에서는 사용자 주변에 홀로그램을 배치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="7b50b-115">이 문서에서는 HoloLens가 공간을 매핑하는 방법, 공간 매핑을 개선하는 방법 및 HoloLens에서 수집하는 공간 데이터를 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="7b50b-116">공간 선택 및 설정</span><span class="sxs-lookup"><span data-stu-id="7b50b-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="7b50b-117">환경의 특징으로 인해 HoloLens가 공간을 해석하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="7b50b-118">조도, 공간의 물질, 개체의 배치 등은 모두 HoloLens가 영역을 매핑하는 방식에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="7b50b-119">HoloLens는 특정 유형의 환경에서 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="7b50b-120">최적의 공간 맵을 만들려면 충분한 빛과 공간이 있는 방을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="7b50b-121">어두운 공간 및 어둡거나, 반짝거리거나, 반투명 표면(예를 들어 거울이나 얇게 비치는 커튼)이 많은 방을 피합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="7b50b-122">HoloLens는 실내 사용에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="7b50b-123">공간 매핑은 네트워크에 연결할 필요가 없는 경우에도 Wi-Fi가 켜졌을 때 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="7b50b-124">HoloLens는 연결되거나 인증되지 않은 경우에도 Wi-Fi 액세스 포인트를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="7b50b-125">HoloLens 기능은 액세스 포인트가 인터넷에 연결되든지, 인트라넷/로컬 전용인지에 관계없이 바뀌지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="7b50b-126">넘어질 위험이 없는 안전한 장소에서만 HoloLens를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="7b50b-127">[안전 관련 추가 정보](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="7b50b-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="7b50b-128">공간 매핑</span><span class="sxs-lookup"><span data-stu-id="7b50b-128">Mapping your space</span></span>

<span data-ttu-id="7b50b-129">이제 공간 매핑을 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="7b50b-130">HoloLens가 사용자 주변 환경을 매핑하기 시작하면 공간을 가로질러 메시 그래픽이 펼쳐지는 것이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="7b50b-131">혼합 현실 홈에서 매핑된 표면을 선택하여 맵이 표시되도록 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="7b50b-132">다음은 멋진 공간 맵을 만들기 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="7b50b-133">영역에 대한 시나리오 이해</span><span class="sxs-lookup"><span data-stu-id="7b50b-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="7b50b-134">HoloLens를 사용할 공간에 가장 많은 시간을 투자해야만 맵이 관련성 있고 완전하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="7b50b-135">예를 들어, HoloLens 사용자 시나리오에 A지점에서 B지점으로 이동이 포함된 경우 이동 중에 모든 방향을 보면서 해당 경로를 2 ~ 3회 걸어봅니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="7b50b-136">공간 주변을 천천히 탐색</span><span class="sxs-lookup"><span data-stu-id="7b50b-136">Walk slowly around the space</span></span>

<span data-ttu-id="7b50b-137">영역을 지나치게 빠르게 탐색하는 경우 HoloLens가 매핑 영역을 놓칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="7b50b-138">공간 주변을 천천히 탐색하고 1.50-2.40m마다 멈추고 주변을 둘러봅니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="7b50b-139">원활하게 움직일 경우 HoloLens 매핑이 더 효율적으로 작동하는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="7b50b-140">모든 방향 살펴보기</span><span class="sxs-lookup"><span data-stu-id="7b50b-140">Look in all directions</span></span>

<span data-ttu-id="7b50b-141">공간을 매핑하는 모습을 살펴봄으로써 HoloLens는 지점 간에 관련 있는 위치에 대한 더 많은 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="7b50b-142">예를 들어 조회하지 않으면 HoloLens가 방 천장의 위치를 인식하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="7b50b-143">공간을 매핑할 때 바닥을 확인하는 것을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7b50b-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="7b50b-144">주요 영역에 여러 번 적용</span><span class="sxs-lookup"><span data-stu-id="7b50b-144">Cover key areas multiple times</span></span>

<span data-ttu-id="7b50b-145">한 영역을 여러 번 통과하여 이동하면 처음 둘러볼 때 놓쳤을지 모르는 특징을 알아차리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="7b50b-146">이상적인 맵을 작성하기 위해 영역을 두 세 번 통과해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7b50b-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="7b50b-147">가능하면 이러한 움직임을 반복하는 동안 한 방향으로 영역을 이동한 다음 방향을 돌려 왔던 길로 다시 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="7b50b-148">시간을 들여 영역 매핑하기</span><span class="sxs-lookup"><span data-stu-id="7b50b-148">Take your time mapping the area</span></span>

<span data-ttu-id="7b50b-149">HoloLens가 완벽하게 매핑하고 주변에 맞게 자동 조정하는 데 15분에서 20분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="7b50b-150">HoloLens를 자주 사용하려는 공간이 있는 경우 해당 시간을 앞에 두고 공간을 매핑하면 나중에 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="7b50b-151">공간 맵에서 발생 가능한 오류</span><span class="sxs-lookup"><span data-stu-id="7b50b-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="7b50b-152">공간 매핑 데이터의 오류는 다음 몇 가지 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="7b50b-153">*허점*: 실제 표면이 공간 매핑 데이터에서 누락되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="7b50b-154">*환영*: 실제 세계에 존재하지 않는 표면이 공간 매핑 데이터에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="7b50b-155">*웜홀*: HoloLens는 맵에서 실제와 다른 맵 부분에 있다고 생각하여 공간 맵의 일부를 '잃어버립니다'.</span><span class="sxs-lookup"><span data-stu-id="7b50b-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="7b50b-156">*바이어스*: 공간 매핑 데이터의 표면이 밀어 넣어지거나 빠져서 실제 표면과 불완전하게 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="7b50b-157">이러한 오류가 표시되는 경우 [FeedbackHub](hololens-feedback.md)를 사용하여 의견을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="7b50b-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="7b50b-158">공간 데이터의 보안 및 저장</span><span class="sxs-lookup"><span data-stu-id="7b50b-158">Security and storage for spatial data</span></span>

<span data-ttu-id="7b50b-159">Microsoft HoloLens용 Windows 10 버전 1803 업데이트 및 이상 버전의 경우 로컬(장치) 데이터베이스에 매핑 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="7b50b-160">HoloLens 사용자는 장치가 PC에 연결되어 있거나 파일 탐색기 앱을 사용하는 경우에도 맵 데이터베이스에 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="7b50b-161">HoloLens에서 BitLocker를 사용하도록 설정한 경우 저장된 맵 데이터도 전체 볼륨과 함께 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="7b50b-162">HoloLens에서 맵 데이터 및 알려진 공간 제거</span><span class="sxs-lookup"><span data-stu-id="7b50b-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="7b50b-163">**설정 > 시스템 > 홀로그램**에서 맵 데이터를 삭제하는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="7b50b-164">인근의 홀로그램을 삭제하려면 **인접한 홀로그램 제거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="7b50b-165">이 명령을 실행하면 맵 데이터 및 현재 공간에 고정된 홀로그램이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="7b50b-166">동일한 공간에서 장치를 계속 사용하는 경우 삭제된 정보를 대체하는 완전히 새로운 맵 섹션을 만들고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7b50b-167">"인접한" 홀로그램이란 현재 공간의 동일한 맵 섹션 내에 고정된 홀로그램을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="7b50b-168">예를 들어, 이 옵션을 사용하여 홈 관련 맵 데이터에 영향을 주지 않으면서 회사 관련 맵 데이터를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="7b50b-169">모든 홀로그램을 삭제하려면 **모든 홀로그램 제거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="7b50b-170">이 명령을 실행하면 모든 고정된 홀로그램뿐만 아니라 장치에 저장된 모든 맵 데이터가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="7b50b-171">사용자는 홀로그램을 명시적으로 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="7b50b-172">이전에 배치한 홀로그램은 다시 검색할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="7b50b-173">인접 또는 모든 홀로그램을 제거하면 HoloLens가 즉시 스캐닝 및 현재 공간 매핑을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="7b50b-174">공간 맵의 Wi-Fi 데이터</span><span class="sxs-lookup"><span data-stu-id="7b50b-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="7b50b-175">HoloLens는 홀로그램 위치와 HoloLens 알려진 공간 데이터베이스에 저장된 맵 섹션을 서로 연결하는 데 도움이 되는 Wi-Fi 특성을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="7b50b-176">Wi-Fi 특성에 대한 정보는 사용자가 액세스할 수 없으며 클라우드를 사용하거나 원격 분석을 사용하여 Microsoft로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="7b50b-177">Wi-Fi를 사용하는 경우 HoloLens는 맵 데이터와 인접한 Wi-Fi 액세스 포인트를 서로 연관시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="7b50b-178">네트워크에 연결되어 있든 방금 주변에서 검색되었든 동작의 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="7b50b-179">Wi-Fi가 해제된 경우에도 HoloLens는 계속 공간을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="7b50b-180">그러나 HoloLens는 공간 데이터베이스에서 더 많은 맵 데이터를 검색해야 하며 홀로그램을 찾는 데 시간이 더 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="7b50b-181">Wi-Fi 정보를 사용하지 않는 경우 맵의 정확한 부분을 찾기 위해 HoloLens가 활성인 검색을 모든 홀로그램 앵커 및 장치에 저장된 맵 섹션과 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b50b-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="7b50b-182">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7b50b-182">Related topics</span></span>

- [<span data-ttu-id="7b50b-183">공간 매핑 디자인</span><span class="sxs-lookup"><span data-stu-id="7b50b-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
