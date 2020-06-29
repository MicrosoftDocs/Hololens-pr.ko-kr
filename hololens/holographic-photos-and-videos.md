---
title: 혼합 현실 사진 및 동영상 캡처 및 관리
description: HoloLens를 사용 하 여 혼합 현실 사진과 비디오를 캡처, 보기 및 공유 하는 방법에 대해 알아봅니다.
keywords: hololens, 사진, 비디오, 캡처, mrc, 혼합 현실 캡처, 사진, 카메라, 스트림, livestream, 데모
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1be4e80c040d5b8e451c07fb931c7c7fb8d5ab48
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829108"
---
# <span data-ttu-id="e75c8-104">혼합 현실 사진 및 비디오 만들기</span><span class="sxs-lookup"><span data-stu-id="e75c8-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="e75c8-105">HoloLens를 통해 사용자는 디지털 세계와 실제 세계를 함께 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="e75c8-106">MRC (혼합 현실 캡처)를 사용 하 여 해당 환경을 사진 또는 비디오로 캡처 하거나 다른 사용자와 실시간으로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="e75c8-107">Mixed reality 캡처는 첫 번째 사용자의 보기를 사용 하 여 다른 사용자가 홀로그램 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="e75c8-108">세 번째 사용자의 관점에서는 [spectator 보기](https://docs.microsoft.com/windows/mixed-reality/spectator-view)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="e75c8-109">Spectator view는 데모에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="e75c8-110">친구와 동료 간에 비디오를 공유 하는 것은 재미 있지만, 비디오를 통해 다른 사용자가 앱을 사용 하거나 앱과 환경에 문제를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c8-111">Mixed reality 캡처 환경을 시작할 수 없고 HoloLens가 작업 장치인 경우에는 시스템 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e75c8-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="e75c8-112">카메라에 대 한 액세스는 회사 정책을 통해 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="e75c8-113">Mixed reality 사진 캡처</span><span class="sxs-lookup"><span data-stu-id="e75c8-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="e75c8-114">HoloLens에서 혼합 현실 사진을 촬영 하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="e75c8-115">사진을 촬영 하는 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="e75c8-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="e75c8-116">현재 보기의 빠른 사진을 찍으려면 볼륨을 위로 길게 누르고 볼륨을 아래로 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="e75c8-117">이는 HoloLens 버전의 스크린샷 또는 인쇄 화면 처럼 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="e75c8-118">HoloLens 2의 단추 위치</span><span class="sxs-lookup"><span data-stu-id="e75c8-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="e75c8-119">HoloLens의 단추 위치 (첫번째 gen)</span><span class="sxs-lookup"><span data-stu-id="e75c8-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="e75c8-120">**볼륨** 을 길게 누르고 3 초간 **볼륨 작게** 단추를 누르면 사진을 촬영 하는 대신 비디오 녹화가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="e75c8-121">녹화를 중지 하려면 볼륨을 **위로** 또는 **볼륨 아래로** 단추를 동시에 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="e75c8-122">사진을 촬영 하는 음성 명령</span><span class="sxs-lookup"><span data-stu-id="e75c8-122">Voice commands to take photos</span></span>

<span data-ttu-id="e75c8-123">HoloLens 2, 버전 2004 (이상)에서 "사진 찍기" 라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="e75c8-124">HoloLens (첫번째 gen) 또는 HoloLens 2, 버전 1903, "안녕 코타 나, 사진 찍기" 라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="e75c8-125">사진을 찍을 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="e75c8-125">Start menu to take photos</span></span>

<span data-ttu-id="e75c8-126">시작 제스처를 사용 하 여 **시작**으로 이동한 다음 **카메라** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="e75c8-127">캡처하려는 방향으로 원하는 위치를 가리킨 다음 [air을 탭](hololens2-basic-usage.md#touch-holograms-near-you) 하 여 사진을 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="e75c8-128">계속 해 서 air을 탭 하 여 추가 사진을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="e75c8-129">캡처한 사진은 모두 장치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="e75c8-130">시작 제스처를 다시 사용 하 여 사진 캡처를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="e75c8-131">혼합 현실 비디오 캡처</span><span class="sxs-lookup"><span data-stu-id="e75c8-131">Capture a mixed reality video</span></span>

<span data-ttu-id="e75c8-132">여러 가지 방법으로 HoloLens에 혼합 현실 비디오를 녹화할 수 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="e75c8-133">비디오 녹화를 위한 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="e75c8-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="e75c8-134">비디오를 녹화 하는 가장 빠른 방법은 3 초 카운트다운이 시작 될 때까지 **볼륨** 을 길게 누르고 **볼륨 다운** 단추를 동시에 누르고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="e75c8-135">녹화를 중지 하려면 두 단추를 동시에 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c8-136">동시에 **볼륨** 을 길게 누르고 **볼륨 아래로** 단추를 누르면 비디오가 녹화 되는 것이 아니라 사진이 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="e75c8-137">음성에서 비디오 녹화</span><span class="sxs-lookup"><span data-stu-id="e75c8-137">Voice to record videos</span></span>

<span data-ttu-id="e75c8-138">HoloLens 2, 버전 2004 (이상)에서 "기록 시작" 이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="e75c8-139">녹음을 중지 하려면 "기록 중지" 라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="e75c8-140">HoloLens (첫번째 gen) 또는 HoloLens 2, 버전 1903, "안녕 코타 나 기록 시작" 이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="e75c8-141">녹음을 중지 하려면 "안녕 코타 나 기록 중지" 라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="e75c8-142">비디오 녹화를 위한 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="e75c8-142">Start menu to record videos</span></span>

<span data-ttu-id="e75c8-143">시작 제스처를 사용 하 여 **시작**으로 이동한 다음 **비디오** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="e75c8-144">캡처하려는 방향으로 원하는 위치를 가리킨 다음 [air을 탭](hololens2-basic-usage.md#touch-holograms-near-you) 하 여 녹화를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="e75c8-145">3 초 동안 기록이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="e75c8-146">녹화를 중지 하려면 시작 제스처를 사용 하 여 강조 표시 된 **비디오** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="e75c8-147">비디오가 장치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="e75c8-148">HoloLens에 적용 (첫번째 gen)</span><span class="sxs-lookup"><span data-stu-id="e75c8-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="e75c8-149">[Windows 10 10 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 는 HoloLens (1 회 gen)에서 시작 제스처 및 Windows 단추가 작동 하는 방법을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="e75c8-150">업데이트 하기 전에 시작 제스처 또는 Windows 단추를 클릭 하면 비디오 녹화가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="e75c8-151">그러나 업데이트 후 시작 제스처 또는 Windows 단추는 **시작** 메뉴 (또는 몰입 형 앱을 사용할 경우 **빠른 작업 메뉴** )를 열고 강조 표시 된 **비디오** 아이콘을 선택 하 여 녹화를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="e75c8-152">실시간으로 표시 되는 내용 공유</span><span class="sxs-lookup"><span data-stu-id="e75c8-152">Share what you see in real-time</span></span>

<span data-ttu-id="e75c8-153">친구 및 동료와 동시에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="e75c8-154">사용할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-154">There are a few methods available:</span></span>

1. <span data-ttu-id="e75c8-155">TV를 시청 하기 위해 Miracast 지원 장치나 어댑터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="e75c8-156">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 을 사용 하 여 PC에서 시청</span><span class="sxs-lookup"><span data-stu-id="e75c8-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="e75c8-157">[Microsoft HoloLens 도우미 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 사용 하 여 PC 시청</span><span class="sxs-lookup"><span data-stu-id="e75c8-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="e75c8-158">사용자가 원격 전문가에 게 표시 되는 내용을 스트리밍할 수 있도록 하는 [Microsoft Dynamics 365 원격 지원](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="e75c8-159">그런 다음 원격 전문가는 프런트 라인의 작업자 구두로를 안내 하거나, 전세계에 주석을 달아 지 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c8-160">Windows Device Portal 또는 Microsoft HoloLens 도우미 앱을 통해 표시 되는 내용을 공유 하려면 HoloLens [가 개발자 모드](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="e75c8-161">Miracast를 사용 하 여 비디오 스트리밍</span><span class="sxs-lookup"><span data-stu-id="e75c8-161">Stream video with Miracast</span></span>

<span data-ttu-id="e75c8-162">시작 제스처를 사용 하 여 **시작**으로 이동한 다음 **연결** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="e75c8-163">표시 되는 선택기에서 연결 하려는 Miracast 사용 장치 또는 어댑터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="e75c8-164">공유를 중지 하려면 시작 제스처를 사용 하 여 강조 표시 된 **연결** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="e75c8-165">스트리밍 중이기 때문에 장치에 아무 것도 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c8-166">Miracast 지원은 [Windows 10 10 월 2018 업데이트로](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)시작 되는 HoloLens (1 회 gen)에서 사용 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="e75c8-167">Windows Device Portal을 사용한 실시간 비디오</span><span class="sxs-lookup"><span data-stu-id="e75c8-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="e75c8-168">Windows 디바이스 포털을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정 하 고 Windows Device Portal을 탐색](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="e75c8-169">Microsoft HoloLens 도우미 앱</span><span class="sxs-lookup"><span data-stu-id="e75c8-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="e75c8-170">Microsoft HoloLens 도우미 앱을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="e75c8-171">그런 다음 [Microsoft hololens 도우미 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 다운로드 하 고 앱 내의 지침에 따라 HoloLens에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="e75c8-172">HoloLens를 사용 하 여 앱을 설정한 후에는 앱의 주 메뉴에서 **라이브 스트림** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="e75c8-173">혼합 현실 사진 및 동영상 보기</span><span class="sxs-lookup"><span data-stu-id="e75c8-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="e75c8-174">혼합 현실 사진과 비디오는 장치의 "카메라 롤"에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="e75c8-175">파일 탐색기 앱을 사용 하 여 HoloLens에서이 폴더의 콘텐츠를 탐색할 수 있습니다 (그림 > 카메라 앨범으로 이동).</span><span class="sxs-lookup"><span data-stu-id="e75c8-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="e75c8-176">또한 HoloLens에 사전 설치 되어 있는 사진 앱에서 혼합 현실 사진과 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="e75c8-177">세상에서 사진을 고정 하려면 사진 앱에서 선택 하 고 **혼합 세계에서 배치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="e75c8-178">사진을 배치한 후에는 전세계에 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="e75c8-179">HoloLens에 연결 된 PC에서 혼합 현실 사진과 비디오를 보고/또는 저장 하려면 MTP를 통해 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 [PC의 파일 탐색기](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

## <span data-ttu-id="e75c8-180">혼합 현실 사진 및 동영상 공유</span><span class="sxs-lookup"><span data-stu-id="e75c8-180">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="e75c8-181">혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-181">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="e75c8-182">미리 보기 위의 **공유** 아이콘을 선택 하 여 공유 도우미를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-182">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="e75c8-183">여기서 해당 사진이 나 비디오를 공유할 끝점을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-183">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="e75c8-184">혼합 현실 사진과 비디오를 자동으로 업로드 하 여 OneDrive에서 혼합 현실 사진과 비디오를 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-184">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="e75c8-185">HoloLens에서 OneDrive 앱을 열고 아직 계정이 없는 경우 개인 [Microsoft 계정](https://account.microsoft.com) 으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-185">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="e75c8-186">**설정** 아이콘을 선택 하 고 **카메라 업로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-186">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="e75c8-187">카메라 업로드를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-187">Turn Camera upload on.</span></span> <span data-ttu-id="e75c8-188">이제 HoloLens에서 앱을 시작할 때마다 혼합 현실 사진과 비디오가 OneDrive에 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-188">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c8-189">개인 Microsoft 계정으로 OneDrive에 로그인 한 경우 OneDrive 에서만 카메라를 업로드 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-189">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="e75c8-190">회사 또는 학교 계정을 사용 하 여 HoloLens를 설정 하는 경우 OneDrive 앱에 개인 Microsoft 계정을 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-190">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="e75c8-191">Mixed reality 캡처의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e75c8-191">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="e75c8-192">Mixed reality 캡처를 사용 하는 동안 HoloLens의 프레임 속도는 halved로 최대 30hz입니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-192">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="e75c8-193">비디오의 최대 길이는 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-193">Videos have a maximum length of five minutes.</span></span>
- <span data-ttu-id="e75c8-194">사진/비디오 카메라가 이미 다른 응용 프로그램에서 사용 중이거나 라이브 스트리밍 중 이거나 시스템 리소스가 부족 한 경우 사진 및 비디오의 해상도를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75c8-194">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

## <span data-ttu-id="e75c8-195">기본 파일 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="e75c8-195">Default file format and resolution</span></span>

### <span data-ttu-id="e75c8-196">기본 사진 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="e75c8-196">Default photo format and resolution</span></span>

|  <span data-ttu-id="e75c8-197">장치</span><span class="sxs-lookup"><span data-stu-id="e75c8-197">Device</span></span>  |  <span data-ttu-id="e75c8-198">형식</span><span class="sxs-lookup"><span data-stu-id="e75c8-198">Format</span></span>  |  <span data-ttu-id="e75c8-199">확장</span><span class="sxs-lookup"><span data-stu-id="e75c8-199">Extension</span></span>  |  <span data-ttu-id="e75c8-200">해상도</span><span class="sxs-lookup"><span data-stu-id="e75c8-200">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="e75c8-201">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e75c8-201">HoloLens 2</span></span> | [<span data-ttu-id="e75c8-202">JPEG</span><span class="sxs-lookup"><span data-stu-id="e75c8-202">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="e75c8-203">.jpg</span><span class="sxs-lookup"><span data-stu-id="e75c8-203">.jpg</span></span> | <span data-ttu-id="e75c8-204">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="e75c8-204">3904x2196px</span></span> |
| <span data-ttu-id="e75c8-205">HoloLens (첫번째 gen)</span><span class="sxs-lookup"><span data-stu-id="e75c8-205">HoloLens (1st gen)</span></span> | [<span data-ttu-id="e75c8-206">JPEG</span><span class="sxs-lookup"><span data-stu-id="e75c8-206">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="e75c8-207">.jpg</span><span class="sxs-lookup"><span data-stu-id="e75c8-207">.jpg</span></span> | <span data-ttu-id="e75c8-208">1408x792px</span><span class="sxs-lookup"><span data-stu-id="e75c8-208">1408x792px</span></span> |

### <span data-ttu-id="e75c8-209">녹화 된 비디오 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="e75c8-209">Recorded video format and resolution</span></span>

| <span data-ttu-id="e75c8-210">장치</span><span class="sxs-lookup"><span data-stu-id="e75c8-210">Device</span></span> | <span data-ttu-id="e75c8-211">형식</span><span class="sxs-lookup"><span data-stu-id="e75c8-211">Format</span></span> | <span data-ttu-id="e75c8-212">확장</span><span class="sxs-lookup"><span data-stu-id="e75c8-212">Extension</span></span> | <span data-ttu-id="e75c8-213">해상도</span><span class="sxs-lookup"><span data-stu-id="e75c8-213">Resolution</span></span> | <span data-ttu-id="e75c8-214">속력과</span><span class="sxs-lookup"><span data-stu-id="e75c8-214">Speed</span></span> | <span data-ttu-id="e75c8-215">Audio</span><span class="sxs-lookup"><span data-stu-id="e75c8-215">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="e75c8-216">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e75c8-216">HoloLens 2</span></span> | [<span data-ttu-id="e75c8-217">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="e75c8-217">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="e75c8-218">.mp4</span><span class="sxs-lookup"><span data-stu-id="e75c8-218">.mp4</span></span> | <span data-ttu-id="e75c8-219">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="e75c8-219">1920x1080px</span></span> | <span data-ttu-id="e75c8-220">30fps</span><span class="sxs-lookup"><span data-stu-id="e75c8-220">30fps</span></span> | <span data-ttu-id="e75c8-221">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="e75c8-221">48kHz Stereo</span></span> |
| <span data-ttu-id="e75c8-222">HoloLens (첫번째 gen)</span><span class="sxs-lookup"><span data-stu-id="e75c8-222">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="e75c8-223">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="e75c8-223">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="e75c8-224">.mp4</span><span class="sxs-lookup"><span data-stu-id="e75c8-224">.mp4</span></span> | <span data-ttu-id="e75c8-225">1216x684px</span><span class="sxs-lookup"><span data-stu-id="e75c8-225">1216x684px</span></span> | <span data-ttu-id="e75c8-226">24fps</span><span class="sxs-lookup"><span data-stu-id="e75c8-226">24fps</span></span> | <span data-ttu-id="e75c8-227">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="e75c8-227">48kHz Stereo</span></span> |
