---
title: 혼합 현실 사진 및 비디오 캡처, 기록 및 공유
description: HoloLens 혼합 현실 장치를 사용하여 혼합 현실 사진 및 비디오를 캡처, 기록 및 보고 보는 방법을 학습합니다. Miracast 또는 수집된 파일을 통해 공유하는 방법을 학습합니다.
keywords: hololens, 사진, 비디오, 캡처, mrc, 혼합 현실 캡처, 사진, 카메라, Miracast, 스트림, 라이브 스트림, 데모, 기록
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
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406712"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="bfc48-105">혼합 현실 사진 및 비디오 만들기</span><span class="sxs-lookup"><span data-stu-id="bfc48-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="bfc48-106">HoloLens는 사용자에게 디지털 세계와 실제 환경을 혼합하는 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="bfc48-107">MRC(혼합 현실 캡처)를 사용하면 사진 또는 비디오로 해당 환경을 캡처하거나 다른 사용자와 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="bfc48-108">혼합 현실 캡처는 다른 사람들이 홀로그램을 볼 수 있도록 1인치 시야를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="bfc48-109">3인치 보기의 경우 뷰어 [보기를 사용 합니다.](https://docs.microsoft.com/windows/mixed-reality/spectator-view)</span><span class="sxs-lookup"><span data-stu-id="bfc48-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="bfc48-110">사양자 보기는 데모에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="bfc48-111">친구 및 동료들 사이에서 비디오를 공유하는 것이 재미있는 반면 비디오는 다른 사람들이 앱을 사용하거나 앱 및 환경과 문제를 전달하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc48-112">혼합 현실 캡처 환경을 시작하지 못하고 HoloLens가 작업 장치인 경우 시스템 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="bfc48-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="bfc48-113">회사 정책을 통해 카메라에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="bfc48-114">혼합 현실 사진 캡처</span><span class="sxs-lookup"><span data-stu-id="bfc48-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="bfc48-115">HoloLens에서 혼합 현실 사진을 찍는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="bfc48-116">사진을 찍기 위해 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="bfc48-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="bfc48-117">현재 보기를 빠르게 사진을 찍기 위해 볼륨 업 및 볼륨 감소 단추를 동시에 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="bfc48-118">이는 스크린샷 또는 인쇄 화면의 HoloLens 버전과 약간 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="bfc48-119">HoloLens 2의 단추 위치</span><span class="sxs-lookup"><span data-stu-id="bfc48-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="bfc48-120">HoloLens(1세대)의 단추 위치</span><span class="sxs-lookup"><span data-stu-id="bfc48-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="bfc48-121">볼륨을 **최대화하고** 볼륨 작게 단추를 3초 동안 누르면 사진을 찍는 대신 비디오 녹화가 시작됩니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bfc48-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="bfc48-122">녹화를 중지하려면 \*\*\*\* 볼륨 업 및 볼륨 감소 단추를 **동시에** 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="bfc48-123">사진을 찍기 위해 음성 명령</span><span class="sxs-lookup"><span data-stu-id="bfc48-123">Voice commands to take photos</span></span>

<span data-ttu-id="bfc48-124">HoloLens 2, 버전 2004 이상에서 "사진 찍기"라고 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfc48-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="bfc48-125">HoloLens(1세대) 또는 HoloLens 2 버전 1903에서 "안보이는 Cortana, 사진 찍기"라고 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfc48-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="bfc48-126">사진을 찍기 위해 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="bfc48-126">Start menu to take photos</span></span>

<span data-ttu-id="bfc48-127">시작 제스처를 사용하여 **시작으로**이동한 다음 카메라 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-127">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="bfc48-128">캡처하려는 방향을 머리를 잡은 다음 에어 탭하여 [사진을](hololens2-basic-usage.md#touch-holograms-near-you) 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="bfc48-129">계속해서 에어 탭하고 추가 사진을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="bfc48-130">캡처한 모든 사진이 장치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="bfc48-131">시작 제스처를 다시 사용하여 사진 캡처를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="bfc48-132">혼합 현실 비디오 캡처</span><span class="sxs-lookup"><span data-stu-id="bfc48-132">Capture a mixed reality video</span></span>

<span data-ttu-id="bfc48-133">HoloLens에 혼합 현실의 비디오를 녹화하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="bfc48-134">비디오를 기록하기 위해 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="bfc48-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="bfc48-135">비디오를 녹화하는 가장 빠른 방법은 3초 \*\*\*\* 카운트다운이 시작될 때까지 볼륨을 길게 누르고 있는 것입니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bfc48-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="bfc48-136">녹화를 중지하려면 두 단추를 동시에 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc48-137">볼륨을 빠르게 **누르고** **볼륨** 작게 단추를 동시에 누르면 비디오를 녹음하는 대신 사진을 찍을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="bfc48-138">비디오를 녹음할 음성</span><span class="sxs-lookup"><span data-stu-id="bfc48-138">Voice to record videos</span></span>

<span data-ttu-id="bfc48-139">HoloLens 2 버전 2004 이상에서 "녹음/녹화 시작"이라고 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfc48-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="bfc48-140">녹음을 중지하기 위해 "녹음 중지"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="bfc48-141">HoloLens(1세대) 또는 HoloLens 2 버전 1903에서 "안보이는 Cortana, 녹음을 시작하십시오."라고 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfc48-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="bfc48-142">녹음을 중지하기 위해 "안보이는 Cortana, 녹음을 중지합니다."라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="bfc48-143">비디오를 녹음할 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="bfc48-143">Start menu to record videos</span></span>

<span data-ttu-id="bfc48-144">시작 제스처를 \*\*\*\* 사용하여 시작으로 이동한 다음 비디오 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-144">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="bfc48-145">캡처할 방향을 머리를 잡은 다음 [](hololens2-basic-usage.md#touch-holograms-near-you) 에어 탭하여 기록을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="bfc48-146">3초 카운트다운이 진행되면 녹음/녹화가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="bfc48-147">녹화를 중지하려면 시작 제스처를 사용하여 강조 표시된 비디오 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-147">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="bfc48-148">비디오가 장치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-148">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="bfc48-149">HoloLens(1세대)에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-149">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="bfc48-150">Windows [10 2018년 10월 업데이트는](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) HoloLens(1세대)에서 시작 제스처 및 Windows 단추가 동작하는 방법을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="bfc48-151">업데이트하기 전에 시작 제스처 또는 Windows 단추는 비디오 녹화를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="bfc48-152">그러나 업데이트 후 시작 제스처 또는 Windows 단추가 시작 \*\*\*\* 메뉴(또는 몰입형 앱인 경우 빠른 작업 메뉴)를 \*\*\*\* 열며, 이 메뉴에서 강조 표시된 비디오 아이콘을 선택하여 녹화를 중지할 수 있습니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bfc48-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="bfc48-153">실시간으로 보는 것을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-153">Share what you see in real-time</span></span>

<span data-ttu-id="bfc48-154">HoloLens에서 볼 수 있는 정보를 실시간으로 친구 및 동료와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="bfc48-155">몇 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-155">There are a few methods available:</span></span>

1. <span data-ttu-id="bfc48-156">TV에서 시청하기 위해 Miracast 지원 장치 또는 어댑터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="bfc48-157">[Windows Device Portal을](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 사용하여 PC에서 시청</span><span class="sxs-lookup"><span data-stu-id="bfc48-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="bfc48-158">Microsoft [HoloLens 도우미 앱을 사용하여](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) PC에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="bfc48-159">[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱을 배포하여 일선 근로자가 원격 전문가에게 보고 있는 정보를 스트리밍할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="bfc48-160">그러면 원격 전문가가 전 세계 일선원을 구두로 안내하거나 주석을 하여 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc48-161">Windows Device Portal 또는 Microsoft HoloLens 도우미 앱을 통해 볼 수 있는 정보를 공유하려면 HoloLens가 개발자 모드에 [있도록 합니다.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bfc48-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="bfc48-162">Miracast를 통해 비디오 스트리밍</span><span class="sxs-lookup"><span data-stu-id="bfc48-162">Stream video with Miracast</span></span>

<span data-ttu-id="bfc48-163">시작 제스처를 사용하여 **시작으로**이동한 다음 연결 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-163">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="bfc48-164">나타나는 선택기에서 연결할 Miracast 사용 장치 또는 어댑터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="bfc48-165">공유를 중지하려면 시작 제스처를 사용하여 강조 표시된 연결 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-165">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="bfc48-166">스트리밍 중이기 때문에 디바이스에 아무 것도 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc48-167">Miracast 지원은 [Windows 10 2018년 10월](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)업데이트부터 HoloLens(1세대)에서 사용하도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="bfc48-168">Windows Device Portal을 사용하여 실시간 비디오</span><span class="sxs-lookup"><span data-stu-id="bfc48-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="bfc48-169">Windows Device Portal을 통해 공유하려면 HoloLens에서 개발자 모드를 사용하도록 설정해야 하기 때문에 개발자 모드를 설정하고 Windows Device Portal 을 탐색하려면 개발자 설명서의 지침을 [따릅니다.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bfc48-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="bfc48-170">Microsoft HoloLens 도우미 앱</span><span class="sxs-lookup"><span data-stu-id="bfc48-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="bfc48-171">Microsoft HoloLens 도우미 앱을 통해 공유하려면 HoloLens에서 개발자 모드를 사용하도록 설정해야 하기 때문에 개발자 모드를 설정하려면 개발자 설명서의 지침에 [따라 를 설정합니다.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bfc48-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="bfc48-172">그런 다음 [Microsoft HoloLens 도우미](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 앱을 다운로드하고 앱 내의 지침에 따라 HoloLens에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="bfc48-173">HoloLens를 사용하여 앱을 설정한 후 \*\*\*\* 앱의 주 메뉴에서 라이브 스트림 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="bfc48-174">혼합 현실 사진 및 비디오 보기</span><span class="sxs-lookup"><span data-stu-id="bfc48-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="bfc48-175">혼합 현실 사진 및 비디오는 디바이스의 "카메라 롤"에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="bfc48-176">파일 탐색기 앱을 사용하여 HoloLens에서 이 폴더의 콘텐츠를 검색할 수 있습니다(카메라 롤에서 사진 > 탐색).</span><span class="sxs-lookup"><span data-stu-id="bfc48-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="bfc48-177">HoloLens에 미리 설치된 사진 혼합 현실 사진 및 비디오를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="bfc48-178">월드에 사진을 고정하려면 사진 앱에서 사진을 선택하고 혼합된 월드에서 **장소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bfc48-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="bfc48-179">사진을 배치한 후 전 세계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="bfc48-180">HoloLens에 연결된 PC에서 혼합 현실 사진 및 비디오를 보거나 저장하려면 [MTP를](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)통해 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 PC의 파일 탐색기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="bfc48-181">파일 탐색기를 사용하여 사진, 비디오 및 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="bfc48-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="bfc48-182">다른 모바일 장치와 마찬가지로 HoloLens를 PC에 연결하여 쉽게 전송할 수 있도록 HoloLens 라이브러리(사진, 비디오, 문서)에 액세스하기 위해 파일 탐색기를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="bfc48-183">이 방법은 사용하기 쉽고 장치 포털 또는 Wi-Fi를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="bfc48-184">디바이스 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-184">Unlock the device.</span></span>
1. <span data-ttu-id="bfc48-185">USB를 통해 장치를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="bfc48-186">PC에서 파일 탐색기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="bfc48-187">탐색: 이 PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="bfc48-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="bfc48-188">PC에 필요한 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="bfc48-189">팁:</span><span class="sxs-lookup"><span data-stu-id="bfc48-189">Tips:</span></span>
- <span data-ttu-id="bfc48-190">파일이 없는 경우 HoloLens에 로그인하여 데이터에 액세스할 수 있도록 하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="bfc48-191">문서 폴더에서 진단 파일과 같은 다른 파일을 [다른](hololens-diagnostic-logs.md#offline-diagnostics) 폴더에 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="bfc48-192">PC의 파일 탐색기에서 장치 속성을 선택하여 Windows Holographic OS 버전 번호(펌웨어 버전), 장치 일련 번호 및 배터리 백분율을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="bfc48-193">조직에서 MDM을 사용하여 [연결/AllowUSBConnection을](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 사용하지 않도록 설정한 경우 장치에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="bfc48-194">혼합 현실 사진 및 비디오 공유</span><span class="sxs-lookup"><span data-stu-id="bfc48-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="bfc48-195">혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-195">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="bfc48-196">공유 \*\*\*\* 도우미를 표시하려면 미리 보기 위에 있는 공유 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-196">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="bfc48-197">이 지점에서 해당 사진 또는 비디오를 공유할 끝점을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="bfc48-198">OneDrive에서 혼합 현실 사진 및 비디오를 자동으로 업로드하여 혼합 현실 사진 및 비디오를 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-198">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="bfc48-199">HoloLens에서 OneDrive 앱을 열고 아직 개인 [Microsoft](https://account.microsoft.com) 계정으로 로그인하지 않은 경우 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-199">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="bfc48-200">설정 **아이콘을** 선택하고 카메라 업로드 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bfc48-200">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="bfc48-201">카메라 업로드 켜기.</span><span class="sxs-lookup"><span data-stu-id="bfc48-201">Turn Camera upload on.</span></span> <span data-ttu-id="bfc48-202">이제 HoloLens에서 앱을 시작하면 혼합 현실 사진 및 비디오가 OneDrive에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-202">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc48-203">개인 Microsoft 계정을 사용하여 OneDrive에 로그인한 경우 OneDrive에서 카메라 업로드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-203">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="bfc48-204">직장 또는 학교 계정으로 HoloLens를 설정한 경우 OneDrive 앱에 개인 Microsoft 계정을 추가하여 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-204">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="bfc48-205">혼합 현실 캡처의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="bfc48-205">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="bfc48-206">혼합 현실 캡처를 사용하는 동안 HoloLens의 프레임 속도는 30Hz로 잘리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-206">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="bfc48-207">사진/비디오 카메라가 다른 응용 프로그램에서 이미 사용 중이나 라이브 스트리밍 중이나 시스템 리소스가 부족한 경우 사진 및 비디오의 해상도가 감소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-207">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="bfc48-208">최대 녹음/녹화 길이</span><span class="sxs-lookup"><span data-stu-id="bfc48-208">Maximum recording length</span></span>

<span data-ttu-id="bfc48-209">Windows Holographic 이전의 HoloLens 2 장치에서는 장치에 기록된 버전 20H2 비디오가 최대 5분으로 제한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-209">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="bfc48-210">고객 피드백으로 인해 혼합 현실 캡처의 기록 [길이를 늘렸다.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="bfc48-210">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="bfc48-211">혼합 현실 캡처는 더 이상 기본적으로 5분으로 제한되지 않지만 대신 사용 가능한 디스크 공간에 따라 최대 녹음/녹화 길이를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-211">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="bfc48-212">장치는 총 디스크 공간의 80%까지 사용 가능한 디스크 공간을 기반으로 최대 비디오 녹화 시간을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-212">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc48-213">HoloLens는 다음 중 하나에 해당하면 기본 비디오 녹화 길이(5분)를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-213">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="bfc48-214">예상 최대 녹음/녹화 기간은 기본값인 5분보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-214">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="bfc48-215">사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-215">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="bfc48-216">기본 파일 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="bfc48-216">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="bfc48-217">기본 사진 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="bfc48-217">Default photo format and resolution</span></span>

|  <span data-ttu-id="bfc48-218">Device</span><span class="sxs-lookup"><span data-stu-id="bfc48-218">Device</span></span>  |  <span data-ttu-id="bfc48-219">형식</span><span class="sxs-lookup"><span data-stu-id="bfc48-219">Format</span></span>  |  <span data-ttu-id="bfc48-220">확장</span><span class="sxs-lookup"><span data-stu-id="bfc48-220">Extension</span></span>  |  <span data-ttu-id="bfc48-221">해결 방법</span><span class="sxs-lookup"><span data-stu-id="bfc48-221">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="bfc48-222">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bfc48-222">HoloLens 2</span></span> | [<span data-ttu-id="bfc48-223">JPEG</span><span class="sxs-lookup"><span data-stu-id="bfc48-223">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="bfc48-224">.jpg</span><span class="sxs-lookup"><span data-stu-id="bfc48-224">.jpg</span></span> | <span data-ttu-id="bfc48-225">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="bfc48-225">3904x2196px</span></span> |
| <span data-ttu-id="bfc48-226">HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="bfc48-226">HoloLens (1st gen)</span></span> | [<span data-ttu-id="bfc48-227">JPEG</span><span class="sxs-lookup"><span data-stu-id="bfc48-227">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="bfc48-228">.jpg</span><span class="sxs-lookup"><span data-stu-id="bfc48-228">.jpg</span></span> | <span data-ttu-id="bfc48-229">1408x792px</span><span class="sxs-lookup"><span data-stu-id="bfc48-229">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="bfc48-230">녹화된 비디오 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="bfc48-230">Recorded video format and resolution</span></span>

| <span data-ttu-id="bfc48-231">Device</span><span class="sxs-lookup"><span data-stu-id="bfc48-231">Device</span></span> | <span data-ttu-id="bfc48-232">형식</span><span class="sxs-lookup"><span data-stu-id="bfc48-232">Format</span></span> | <span data-ttu-id="bfc48-233">확장</span><span class="sxs-lookup"><span data-stu-id="bfc48-233">Extension</span></span> | <span data-ttu-id="bfc48-234">해결 방법</span><span class="sxs-lookup"><span data-stu-id="bfc48-234">Resolution</span></span> | <span data-ttu-id="bfc48-235">속도</span><span class="sxs-lookup"><span data-stu-id="bfc48-235">Speed</span></span> | <span data-ttu-id="bfc48-236">Audio</span><span class="sxs-lookup"><span data-stu-id="bfc48-236">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="bfc48-237">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bfc48-237">HoloLens 2</span></span> | [<span data-ttu-id="bfc48-238">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="bfc48-238">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="bfc48-239">.mp4</span><span class="sxs-lookup"><span data-stu-id="bfc48-239">.mp4</span></span> | <span data-ttu-id="bfc48-240">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="bfc48-240">1920x1080px</span></span> | <span data-ttu-id="bfc48-241">30fps</span><span class="sxs-lookup"><span data-stu-id="bfc48-241">30fps</span></span> | <span data-ttu-id="bfc48-242">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="bfc48-242">48kHz Stereo</span></span> |
| <span data-ttu-id="bfc48-243">HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="bfc48-243">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="bfc48-244">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="bfc48-244">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="bfc48-245">.mp4</span><span class="sxs-lookup"><span data-stu-id="bfc48-245">.mp4</span></span> | <span data-ttu-id="bfc48-246">1216x684px</span><span class="sxs-lookup"><span data-stu-id="bfc48-246">1216x684px</span></span> | <span data-ttu-id="bfc48-247">24fps</span><span class="sxs-lookup"><span data-stu-id="bfc48-247">24fps</span></span> | <span data-ttu-id="bfc48-248">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="bfc48-248">48kHz Stereo</span></span> |
