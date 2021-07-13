---
title: 혼합 현실 사진 및 비디오 캡처, 기록 및 공유
description: HoloLens 혼합 현실 디바이스를 사용하여 혼합 현실 사진 및 비디오를 캡처, 녹화 및 보는 방법을 알아봅니다. Miracast 또는 수집된 파일을 통해 공유하는 방법을 알아봅니다.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
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
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635962"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="494b0-105">혼합 현실 사진 및 비디오 만들기</span><span class="sxs-lookup"><span data-stu-id="494b0-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="494b0-106">HoloLens 통해 사용자는 실제 세계와 디지털 세계를 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="494b0-107">MRC(혼합 현실 캡처)를 사용하면 해당 환경을 사진 또는 비디오로 캡처하거나 다른 사람과 실시간으로 볼 수 있는 내용을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="494b0-108">혼합 현실 캡처는 1인칭 시점을 사용하므로 다른 사람이 볼 때 홀로그램을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="494b0-109">3인칭 시점의 경우 [을](/windows/mixed-reality/spectator-view)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-109">For a third-person point of view, use [spectator view](/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="494b0-110">데모에는 특히 유용한 보기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="494b0-111">친구 및 동료 간에 비디오를 공유하는 것은 재미있지만 비디오는 다른 사람들이 앱을 사용하거나 앱 및 환경과 문제를 전달하도록 교육하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-112">혼합 현실 캡처 환경을 시작할 수 없고 HoloLens 작업 디바이스인 경우 시스템 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="494b0-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="494b0-113">카메라 액세스는 회사 정책을 통해 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="494b0-114">혼합 현실 사진 캡처</span><span class="sxs-lookup"><span data-stu-id="494b0-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="494b0-115">HoloLens 혼합 현실 사진을 찍는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="494b0-116">사진을 찍는 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="494b0-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="494b0-117">현재 보기의 빠른 사진을 찍려면 볼륨을 위로 누르고 볼륨 다운 단추를 동시에 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="494b0-118">이는 스크린샷 또는 인쇄 화면의 HoloLens 버전과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="494b0-119">HoloLens 2 단추 위치</span><span class="sxs-lookup"><span data-stu-id="494b0-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="494b0-120">HoloLens 단추 위치(1세대)</span><span class="sxs-lookup"><span data-stu-id="494b0-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="494b0-121">**볼륨을 위로** 누르고 3초 동안 **볼륨을 낮추면** 사진을 찍는 대신 비디오 녹화가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="494b0-122">기록을 중지하려면 **볼륨 위로** 및 **볼륨 다운** 단추를 동시에 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="494b0-123">사진을 찍는 음성 명령</span><span class="sxs-lookup"><span data-stu-id="494b0-123">Voice commands to take photos</span></span>

<span data-ttu-id="494b0-124">HoloLens 2 버전 2004 이상에서는 "Take a picture"이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="494b0-125">HoloLens(1세대) 또는 HoloLens 2 버전 1903에서는 "Hey Cortana, take a picture."라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="494b0-126">사진을 찍는 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="494b0-126">Start menu to take photos</span></span>

<span data-ttu-id="494b0-127">시작 제스처를 사용하여 **시작으로** 이동한 **다음, 카메라** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-127">Use the Start gesture to go to **Start**, then select the **Camera** icon.</span></span>

<span data-ttu-id="494b0-128">캡처하려는 방향을 머리로 가리킨 [다음, 에어 탭하여](hololens2-basic-usage.md#touch-holograms-near-you) 사진을 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="494b0-129">계속 에어 탭하고 추가 사진을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="494b0-130">캡처한 모든 사진이 디바이스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="494b0-131">시작 제스처를 다시 사용하여 사진 캡처를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="494b0-132">혼합 현실 비디오 캡처</span><span class="sxs-lookup"><span data-stu-id="494b0-132">Capture a mixed reality video</span></span>

<span data-ttu-id="494b0-133">HoloLens 혼합 현실 비디오를 녹화하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="494b0-134">비디오를 녹화하는 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="494b0-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="494b0-135">비디오를 녹화하는 가장 빠른 방법은 3초 카운트다운이 시작될 때까지 **볼륨을 길게** 누르고 볼륨 **다운** 단추를 동시에 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="494b0-136">기록을 중지하려면 두 단추를 동시에 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-137">**볼륨을** 빠르게 누르고 동시에 **볼륨을 줄이면** 비디오를 녹화하는 대신 사진을 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="494b0-138">비디오를 녹음하는 음성</span><span class="sxs-lookup"><span data-stu-id="494b0-138">Voice to record videos</span></span>

<span data-ttu-id="494b0-139">HoloLens 2 버전 2004 이상에서는 "기록 시작"이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="494b0-140">기록을 중지하려면 "Stop recording"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="494b0-141">HoloLens(1세대) 또는 HoloLens 2 버전 1903에서는 "Hey Cortana, start recording"이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="494b0-142">기록을 중지하려면 "Hey Cortana, 기록 중지"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="494b0-143">비디오를 녹화하는 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="494b0-143">Start menu to record videos</span></span>

<span data-ttu-id="494b0-144">시작 제스처를 사용하여 **시작으로** 이동한 **다음, 비디오** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-144">Use the Start gesture to go to **Start**, then select the **Video** icon.</span></span> <span data-ttu-id="494b0-145">캡처하려는 방향을 머리로 가리킨 [다음, 에어 탭하여](hololens2-basic-usage.md#touch-holograms-near-you) 기록을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="494b0-146">3초 카운트다운이 있고 녹음이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="494b0-147">기록을 중지하려면 시작 제스처를 사용하고 강조 표시된 **비디오** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-147">To stop recording, use the Start gesture and select the highlighted **Video** icon.</span></span> <span data-ttu-id="494b0-148">비디오는 디바이스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-149">**HoloLens(1세대)에만 적용됩니다.**</span><span class="sxs-lookup"><span data-stu-id="494b0-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="494b0-150">[Windows 10 2018년 10월 업데이트](/windows/mixed-reality/release-notes-october-2018) 시작 제스처 및 Windows 단추가 HoloLens(1세대)에서 동작하는 방식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-150">The [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="494b0-151">업데이트하기 전에 시작 제스처 또는 Windows 단추는 비디오 녹화를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="494b0-152">그러나 업데이트 후에 시작 제스처 또는 Windows 단추는 **시작** 메뉴(또는 몰입형 앱에 있는 경우 **빠른 작업 메뉴)를** 엽니다. 이 메뉴에서 강조 표시된 **비디오** 아이콘을 선택하여 녹화를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="494b0-153">실시간으로 표시되는 내용 공유</span><span class="sxs-lookup"><span data-stu-id="494b0-153">Share what you see in real-time</span></span>

<span data-ttu-id="494b0-154">HoloLens 보는 내용을 실시간으로 친구 및 동료와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="494b0-155">다음과 같은 몇 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-155">There are a few methods available:</span></span>

1. <span data-ttu-id="494b0-156">MIRACAST 지원 디바이스 또는 어댑터에 연결하여 TV에서 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="494b0-157">[Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal) 사용하여 PC에서 시청</span><span class="sxs-lookup"><span data-stu-id="494b0-157">Using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="494b0-158">Microsoft HoloLens [도우미 앱을](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 사용하여 PC에서 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="494b0-159">[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱을 배포하면 일선 작업자가 원격 전문가에게 표시되는 내용을 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="494b0-160">그런 다음 원격 전문가는 자신의 세계에 주석을 추가하거나 언어적으로 일선 작업자를 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-161">Windows 장치 포털 또는 Microsoft HoloLens 도우미 앱을 통해 표시되는 내용을 공유하려면 HoloLens [개발자 모드여야](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="494b0-162">Miracast 비디오 스트리밍</span><span class="sxs-lookup"><span data-stu-id="494b0-162">Stream video with Miracast</span></span>

<span data-ttu-id="494b0-163">시작 제스처를 사용하여 **시작으로** 이동한 **다음, 커넥트** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-163">Use the Start gesture to go to **Start**, then select the **Connect** icon.</span></span> <span data-ttu-id="494b0-164">표시되는 선택기에서 연결하려는 Miracast 사용 가능한 디바이스 또는 어댑터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="494b0-165">공유를 중지하려면 시작 제스처를 사용하고 강조 표시된 **커넥트** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-165">To stop sharing, use the Start gesture and select the highlighted **Connect** icon.</span></span> <span data-ttu-id="494b0-166">스트리밍 중이므로 아무 것도 디바이스에 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-167">Miracast 지원은 Windows 10 2018년 10월 업데이트 HoloLens(1세대)에서 사용하도록 [설정되었습니다.](/windows/mixed-reality/release-notes-october-2018)</span><span class="sxs-lookup"><span data-stu-id="494b0-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="494b0-168">Windows 장치 포털 실시간 비디오</span><span class="sxs-lookup"><span data-stu-id="494b0-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="494b0-169">Windows 장치 포털 통해 공유하려면 HoloLens 개발자 모드를 사용하도록 설정해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정하고 Windows 장치 포털 탐색합니다.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="494b0-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="494b0-170">Microsoft HoloLens 도우미 앱</span><span class="sxs-lookup"><span data-stu-id="494b0-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="494b0-171">Microsoft HoloLens 도우미 앱을 통해 공유하려면 HoloLens 개발자 모드를 사용하도록 설정해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정합니다.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="494b0-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="494b0-172">그런 [다음, Microsoft HoloLens 도우미 앱을](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 다운로드하고 앱 내의 지침에 따라 HoloLens 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="494b0-173">앱이 HoloLens 설정되면 앱의 주 메뉴에서 **라이브 스트림** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="494b0-174">혼합 현실 사진 및 비디오 보기</span><span class="sxs-lookup"><span data-stu-id="494b0-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="494b0-175">혼합 현실 사진 및 비디오는 디바이스의 "카메라 롤"에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="494b0-176">파일 탐색기 앱을 사용하여 HoloLens 이 폴더의 내용을 찾아볼 수 있습니다(사진 **> 카메라 롤로** 이동).</span><span class="sxs-lookup"><span data-stu-id="494b0-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to **Pictures > Camera Roll**).</span></span>

<span data-ttu-id="494b0-177">HoloLens 미리 설치된 사진 앱에서 혼합 현실 사진 및 비디오를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="494b0-178">세계에 사진을 고정하려면 사진 앱에서 선택하고 **혼합 세계 에 배치를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="494b0-179">사진을 배치한 후 전 세계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="494b0-180">HoloLens 연결된 PC에서 혼합 현실 사진 및 비디오를 보거나/또는 저장하려면 [MTP를 통해](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens) [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 PC의 파일 탐색기 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="494b0-181">파일 탐색기 사용하여 사진, 비디오 및 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="494b0-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="494b0-182">다른 모바일 디바이스와 마찬가지로 HoloLens PC에 연결하여 쉽게 전송할 수 있도록 HoloLens 라이브러리(사진, 비디오, 문서)에 액세스하는 파일 탐색기 불러올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="494b0-183">이 방법은 사용하기 쉽고 디바이스 포털 또는 Wi-Fi를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="494b0-184">디바이스 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-184">Unlock the device.</span></span>
1. <span data-ttu-id="494b0-185">USB를 통해 디바이스를 PC에 커넥트.</span><span class="sxs-lookup"><span data-stu-id="494b0-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="494b0-186">파일 탐색기 PC에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="494b0-187">다음으로 이동합니다. 이 PC \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="494b0-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="494b0-188">PC에 필요한 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="494b0-189">팁:</span><span class="sxs-lookup"><span data-stu-id="494b0-189">Tips:</span></span>
- <span data-ttu-id="494b0-190">파일이 표시되지 않으면 HoloLens 로그인하여 데이터에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="494b0-191">Documents 폴더에서 진단 파일과 같은 다른 [폴더의](hololens-diagnostic-logs.md#offline-diagnostics) 다른 파일을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="494b0-192">PC의 파일 탐색기 디바이스 속성을 선택하여 Windows Holographic OS 버전 번호(펌웨어 버전), 디바이스 일련 번호 및 배터리 백분율을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="494b0-193">조직에서 MDM을 사용하여 [연결/AllowUSBConnection을](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 사용하지 않도록 설정하면 디바이스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="494b0-194">혼합 현실 사진 및 비디오 공유</span><span class="sxs-lookup"><span data-stu-id="494b0-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="494b0-195">[Holographic 버전 21H1을 Windows](hololens-release-notes.md#windows-holographic-version-21h1)전에 혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-195">Prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="494b0-196">미리 보기 위의 **공유** 아이콘을 선택하여 공유 도우미를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-196">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="494b0-197">이 위치에서 해당 사진 또는 비디오를 공유하려는 끝점을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="494b0-198">Windows Holographic 버전 21H1에서는 혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-198">With Windows Holographic, version 21H1, after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="494b0-199">미리 보기 위의 **공유** 아이콘을 선택하여 공유 도우미를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-199">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="494b0-200">이 위치에서 해당 사진 또는 비디오를 공유하려는 끝점(메일, OneDrive 등)을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-200">From there, you can select the end point (Mail, OneDrive, etc.) to which you'd like to share that photo or video.</span></span> <span data-ttu-id="494b0-201">**설정 > 시스템 > 공유 환경** 으로 이동 하 여 HoloLens 주변 장치와 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-201">You can also enable your HoloLens to share with nearby devices by going to **Settings -> System -> Shared Experiences**.</span></span> <span data-ttu-id="494b0-202">자세한 내용은 [Windows 10에서 주변 장치와 공유 항목](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="494b0-202">For more details, read [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

> [!TIP] 
> <span data-ttu-id="494b0-203">혼합 현실 사진과 비디오를 자동으로 업로드 하 여 OneDrive에서 혼합 된 현실 사진과 비디오를 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-203">You can also share mixed reality photos and videos from OneDrive by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="494b0-204">HoloLens에서 OneDrive 앱을 열고 **개인 [Microsoft 계정](https://account.microsoft.com)**(아직 없는 경우)로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-204">Open the OneDrive app on HoloLens and sign in with a **personal [Microsoft account](https://account.microsoft.com)**, if you haven't already.</span></span> <span data-ttu-id="494b0-205">**설정** 아이콘을 선택 하 고 **카메라 업로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-205">Select the **Settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="494b0-206">카메라 업로드를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-206">Turn Camera upload on.</span></span> <span data-ttu-id="494b0-207">이제 HoloLens에서 앱을 시작할 때마다 혼합 현실 사진과 비디오가 OneDrive 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-207">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-208">개인 Microsoft 계정를 사용 하 여 OneDrive에 로그인 한 경우에만 OneDrive에서 카메라 업로드를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-208">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="494b0-209">회사 또는 학교 계정을 사용 하 여 HoloLens를 설정 하는 경우 OneDrive 앱에 개인 Microsoft 계정를 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-209">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="494b0-210">혼합 현실 캡처의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="494b0-210">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="494b0-211">혼합 현실 캡처를 사용 하는 동안 HoloLens의 프레임 비율은 30 Hz로 반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-211">While using mixed reality capture, the frame rate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="494b0-212">사진/비디오 카메라가 다른 응용 프로그램에서 이미 사용 중이거나 라이브 스트리밍 또는 시스템 리소스가 부족 한 경우 사진 및 비디오의 해상도가 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-212">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="494b0-213">최대 기록 길이</span><span class="sxs-lookup"><span data-stu-id="494b0-213">Maximum recording length</span></span>

<span data-ttu-id="494b0-214">Windows Holographic, 버전 20h2 이전의 HoloLens 2 장치에서는 장치에 기록 된 비디오가 최대 5 분 길이로 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-214">On HoloLens 2 devices before the Windows Holographic, version 20H2, videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="494b0-215">고객의 의견 때문에 [혼합 현실 캡처](holographic-photos-and-videos.md)의 기록 길이가 증가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-215">Due to customer feedback, we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="494b0-216">혼합 현실 캡처는 기본적으로 더 이상 5 분으로 제한 되지 않으며, 대신 사용 가능한 디스크 공간을 기준으로 최대 기록 길이를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-216">Mixed reality captures will no longer be limited to 5 minutes by default, but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="494b0-217">장치는 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 예상 하며 총 디스크 공간의 80%까지 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-217">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="494b0-218">다음 중 하나가 발생 하는 경우 HoloLens는 기본 비디오 녹화 길이 (5 분)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-218">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="494b0-219">예상 최대 기록 기간은 기본값 5 분 보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-219">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="494b0-220">사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="494b0-220">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="494b0-221">기본 파일 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="494b0-221">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="494b0-222">기본 사진 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="494b0-222">Default photo format and resolution</span></span>

|  <span data-ttu-id="494b0-223">디바이스</span><span class="sxs-lookup"><span data-stu-id="494b0-223">Device</span></span>  |  <span data-ttu-id="494b0-224">서식</span><span class="sxs-lookup"><span data-stu-id="494b0-224">Format</span></span>  |  <span data-ttu-id="494b0-225">확장명</span><span class="sxs-lookup"><span data-stu-id="494b0-225">Extension</span></span>  |  <span data-ttu-id="494b0-226">해결 방법</span><span class="sxs-lookup"><span data-stu-id="494b0-226">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="494b0-227">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="494b0-227">HoloLens 2</span></span> | [<span data-ttu-id="494b0-228">JPEG</span><span class="sxs-lookup"><span data-stu-id="494b0-228">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="494b0-229">.jpg</span><span class="sxs-lookup"><span data-stu-id="494b0-229">.jpg</span></span> | <span data-ttu-id="494b0-230">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="494b0-230">3904x2196px</span></span> |
| <span data-ttu-id="494b0-231">HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="494b0-231">HoloLens (1st gen)</span></span> | [<span data-ttu-id="494b0-232">JPEG</span><span class="sxs-lookup"><span data-stu-id="494b0-232">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="494b0-233">.jpg</span><span class="sxs-lookup"><span data-stu-id="494b0-233">.jpg</span></span> | <span data-ttu-id="494b0-234">1408x792px</span><span class="sxs-lookup"><span data-stu-id="494b0-234">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="494b0-235">녹화 된 비디오 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="494b0-235">Recorded video format and resolution</span></span>

| <span data-ttu-id="494b0-236">디바이스</span><span class="sxs-lookup"><span data-stu-id="494b0-236">Device</span></span> | <span data-ttu-id="494b0-237">서식</span><span class="sxs-lookup"><span data-stu-id="494b0-237">Format</span></span> | <span data-ttu-id="494b0-238">확장명</span><span class="sxs-lookup"><span data-stu-id="494b0-238">Extension</span></span> | <span data-ttu-id="494b0-239">해결 방법</span><span class="sxs-lookup"><span data-stu-id="494b0-239">Resolution</span></span> | <span data-ttu-id="494b0-240">속도</span><span class="sxs-lookup"><span data-stu-id="494b0-240">Speed</span></span> | <span data-ttu-id="494b0-241">오디오</span><span class="sxs-lookup"><span data-stu-id="494b0-241">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="494b0-242">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="494b0-242">HoloLens 2</span></span> | [<span data-ttu-id="494b0-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="494b0-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="494b0-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="494b0-244">.mp4</span></span> | <span data-ttu-id="494b0-245">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="494b0-245">1920x1080px</span></span> | <span data-ttu-id="494b0-246">30fps</span><span class="sxs-lookup"><span data-stu-id="494b0-246">30fps</span></span> | <span data-ttu-id="494b0-247">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="494b0-247">48kHz Stereo</span></span> |
| <span data-ttu-id="494b0-248">HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="494b0-248">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="494b0-249">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="494b0-249">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="494b0-250">.mp4</span><span class="sxs-lookup"><span data-stu-id="494b0-250">.mp4</span></span> | <span data-ttu-id="494b0-251">1216x684px</span><span class="sxs-lookup"><span data-stu-id="494b0-251">1216x684px</span></span> | <span data-ttu-id="494b0-252">24fps</span><span class="sxs-lookup"><span data-stu-id="494b0-252">24fps</span></span> | <span data-ttu-id="494b0-253">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="494b0-253">48kHz Stereo</span></span> |
