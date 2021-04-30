---
title: 혼합 현실 사진 및 비디오 캡처, 기록 및 공유
description: HoloLens mixed reality 장치를 사용 하 여 현실 사진과 비디오를 캡처, 기록 및 확인 하는 방법을 알아봅니다. Miracast 또는 수집 된 파일을 통해 공유 하는 방법에 대해 알아봅니다.
keywords: hololens, 사진, 비디오, 캡처, mrc, 혼합 현실 캡처, 사진, 카메라, miracast, 스트림, 라이브 스트림, 데모, 레코드
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309181"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="3e2e4-105">혼합 현실 사진 및 비디오 만들기</span><span class="sxs-lookup"><span data-stu-id="3e2e4-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="3e2e4-106">HoloLens는 사용자에 게 실제 세계와 세계를 혼합 하는 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="3e2e4-107">혼합 현실 캡처 (MRC)를 사용 하면 해당 환경을 사진 또는 비디오로 캡처하거나 다른 사용자와 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="3e2e4-108">혼합 현실 캡처는 첫 번째 사람의 관점을 사용 하 여 다른 사람들이 볼 때 holograms를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="3e2e4-109">세 번째 사용자 관점은 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="3e2e4-110">Spectator view는 데모에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="3e2e4-111">친구나 동료 간에 비디오를 공유 하는 것은 재미 있지만 비디오를 사용 하면 다른 사용자가 앱을 사용 하거나 앱과 환경에 문제를 전달 하는 데 도움이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-112">혼합 현실 캡처 환경을 시작할 수 없고 HoloLens가 작업 장치인 경우 시스템 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="3e2e4-113">회사 정책을 통해 카메라에 대 한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="3e2e4-114">혼합 현실 사진 캡처</span><span class="sxs-lookup"><span data-stu-id="3e2e4-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="3e2e4-115">HoloLens에서 혼합 현실 사진을 사용 하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="3e2e4-116">사진을 찍을 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="3e2e4-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="3e2e4-117">현재 보기에 대 한 빠른 사진을 만들려면 볼륨 위로 및 볼륨 아래로 단추를 동시에 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="3e2e4-118">이는 스크린샷 또는 인쇄 화면의 HoloLens 버전과 약간 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="3e2e4-119">HoloLens 2의 단추 위치</span><span class="sxs-lookup"><span data-stu-id="3e2e4-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="3e2e4-120">HoloLens의 단추 위치 (첫 번째 gen)</span><span class="sxs-lookup"><span data-stu-id="3e2e4-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="3e2e4-121">**볼륨 위로** 및 **볼륨 작게** 단추를 세 초 동안 보관 하면 사진을 촬영 하는 대신 비디오 기록을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="3e2e4-122">기록을 중지 하려면 **볼륨 위로** 및 **볼륨 아래로** 단추를 동시에 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="3e2e4-123">사진을 찍을 음성 명령</span><span class="sxs-lookup"><span data-stu-id="3e2e4-123">Voice commands to take photos</span></span>

<span data-ttu-id="3e2e4-124">HoloLens 2, 버전 2004 (이상)에서 "그림을 찍습니다." 라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="3e2e4-125">HoloLens (첫 번째 gen) 또는 HoloLens 2, 버전 1903, 예: "Cortana, 사진 찍기"</span><span class="sxs-lookup"><span data-stu-id="3e2e4-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="3e2e4-126">사진을 가져오는 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="3e2e4-126">Start menu to take photos</span></span>

<span data-ttu-id="3e2e4-127">시작 제스처를 사용 하 여 **시작** 으로 이동한 다음 **카메라** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-127">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="3e2e4-128">캡처 하려는 방향으로 헤드를 가리킨 다음, [공중 탭](hololens2-basic-usage.md#touch-holograms-near-you) 을 클릭 하 여 사진을 촬영 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="3e2e4-129">계속 해 서 더 많은 사진을 길게 탭 하 고 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="3e2e4-130">캡처한 사진은 모두 장치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="3e2e4-131">시작 제스처를 다시 사용 하 여 사진 캡처를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="3e2e4-132">혼합 현실 비디오 캡처</span><span class="sxs-lookup"><span data-stu-id="3e2e4-132">Capture a mixed reality video</span></span>

<span data-ttu-id="3e2e4-133">HoloLens에서 혼합 현실 비디오를 기록 하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="3e2e4-134">비디오를 기록 하는 하드웨어 단추</span><span class="sxs-lookup"><span data-stu-id="3e2e4-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="3e2e4-135">비디오를 기록 하는 가장 빠른 방법은 3 초 카운트다운이 시작 될 때까지 **볼륨** 을 동시에 누르고 **볼륨을 아래로 이동** 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="3e2e4-136">기록을 중지 하려면 두 단추를 동시에 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-137">**볼륨 위로** 및 **볼륨 아래로** 단추를 동시에 빠르게 누르면 비디오를 기록 하는 대신 사진이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="3e2e4-138">음성 녹음 비디오</span><span class="sxs-lookup"><span data-stu-id="3e2e4-138">Voice to record videos</span></span>

<span data-ttu-id="3e2e4-139">HoloLens 2, 버전 2004 (이상)에서 "기록 시작"을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="3e2e4-140">기록을 중지 하려면 "기록 중지" 라고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="3e2e4-141">HoloLens (첫 번째 gen) 또는 HoloLens 2 버전 1903, 예: "안녕하세요 Cortana, 녹화 시작"</span><span class="sxs-lookup"><span data-stu-id="3e2e4-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="3e2e4-142">기록을 중지 하려면 "안녕 코타 나 녹음 중지" 라고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="3e2e4-143">비디오를 기록 하는 시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="3e2e4-143">Start menu to record videos</span></span>

<span data-ttu-id="3e2e4-144">시작 제스처를 사용 하 여 **시작** 으로 이동한 다음 **비디오** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-144">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="3e2e4-145">캡처 하려는 방향으로 헤드를 가리킨 다음, [공중 탭](hololens2-basic-usage.md#touch-holograms-near-you) 하 여 기록을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="3e2e4-146">세 초 카운트다운이 발생 하 고 기록이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="3e2e4-147">기록을 중지 하려면 시작 제스처를 사용 하 고 강조 표시 된 **비디오** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-147">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="3e2e4-148">비디오는 장치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-149">**HoloLens (첫 번째 gen)에만 적용 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3e2e4-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="3e2e4-150">[Windows 10 10 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 는 HoloLens (첫 번째 gen)에서 시작 제스처와 Windows 단추가 동작 하는 방식을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="3e2e4-151">업데이트 하기 전에 시작 제스처 또는 Windows 단추가 비디오 녹화를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="3e2e4-152">그러나 업데이트 후 시작 제스처 또는 Windows 단추를 클릭 하 여 **시작** 메뉴 (또는 몰입 형 앱에 있는 경우 **빠른 작업 메뉴** )를 열면 강조 표시 된 **비디오** 아이콘을 선택 하 여 기록을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="3e2e4-153">실시간으로 표시 되는 항목 공유</span><span class="sxs-lookup"><span data-stu-id="3e2e4-153">Share what you see in real-time</span></span>

<span data-ttu-id="3e2e4-154">HoloLens에 표시 되는 내용을 실시간으로 친구와 동료와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="3e2e4-155">사용할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-155">There are a few methods available:</span></span>

1. <span data-ttu-id="3e2e4-156">TV를 시청 하려면 Miracast 사용 장치 또는 어댑터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="3e2e4-157">[Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 을 사용 하 여 PC 시청</span><span class="sxs-lookup"><span data-stu-id="3e2e4-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="3e2e4-158">[Microsoft HoloLens 부록 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 사용 하 여 PC를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="3e2e4-159">[Microsoft Dynamics 365 원격 지원](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱 배포 .이 앱을 통해 프런트 라인 작업자는 원격 전문가에 게 표시 되는 내용을 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="3e2e4-160">그러면 원격 전문가는 전 세계에 주석을 추가 하 여 프런트 라인 작업자 구두로을 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-161">Windows 장치 포털 또는 Microsoft HoloLens 부록 앱을 통해 표시 되는 내용을 공유 하려면 HoloLens [가 개발자 모드](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="3e2e4-162">Miracast를 사용 하 여 비디오 스트리밍</span><span class="sxs-lookup"><span data-stu-id="3e2e4-162">Stream video with Miracast</span></span>

<span data-ttu-id="3e2e4-163">시작 제스처를 사용 하 여 **시작** 으로 이동한 다음 **연결** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-163">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="3e2e4-164">표시 되는 선택에서 연결 하려는 Miracast 사용 장치 또는 어댑터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="3e2e4-165">공유를 중지 하려면 시작 제스처를 사용 하 고 강조 표시 된 **연결** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-165">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="3e2e4-166">스트리밍 중이기 때문에 장치에 아무 것도 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-167">Miracast 지원은 [Windows 10 10 월 2018 업데이트로](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)시작 하는 HoloLens (1 세대)에서 사용 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="3e2e4-168">Windows 장치 포털을 사용한 실시간 비디오</span><span class="sxs-lookup"><span data-stu-id="3e2e4-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="3e2e4-169">Windows 장치 포털을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정 하 고 Windows Device Portal로 이동](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="3e2e4-170">Microsoft HoloLens 부록 앱</span><span class="sxs-lookup"><span data-stu-id="3e2e4-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="3e2e4-171">Microsoft HoloLens 부록 앱을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="3e2e4-172">그런 다음 [Microsoft hololens 부록 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 다운로드 하 고 앱 내의 지침에 따라 HoloLens에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="3e2e4-173">앱이 HoloLens로 설정 되 면 앱의 주 메뉴에서 **라이브 스트림** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="3e2e4-174">혼합 현실 사진 및 비디오 보기</span><span class="sxs-lookup"><span data-stu-id="3e2e4-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="3e2e4-175">혼합 현실 사진과 비디오는 장치의 "카메라 롤"에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="3e2e4-176">파일 탐색기 앱 (사진 > 카메라 롤로 이동)을 사용 하 여 HoloLens에서이 폴더의 내용을 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="3e2e4-177">또한 HoloLens에 미리 설치 되어 있는 사진 앱에서 혼합 현실 사진과 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="3e2e4-178">전 세계에 사진을 고정 하려면 사진 앱에서 해당 사진을 선택 하 고 **혼합 세계에 있는 장소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="3e2e4-179">배치 된 후 전 세계에 사진을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="3e2e4-180">HoloLens에 연결 된 PC에서 혼합 현실 사진과 비디오를 보거나 저장 하려면 MTP를 통해 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 [Pc의 파일 탐색기](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="3e2e4-181">파일 탐색기를 사용 하 여 사진, 동영상 및 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="3e2e4-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="3e2e4-182">다른 모바일 장치와 마찬가지로 HoloLens를 PC에 연결 하 여 파일 탐색기에서 HoloLens 라이브러리 (사진, 동영상, 문서)에 액세스 하 여 쉽게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="3e2e4-183">이 방법은 사용 하기 쉬우며 장치 포털 또는 Wi-fi를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="3e2e4-184">장치를 잠금 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-184">Unlock the device.</span></span>
1. <span data-ttu-id="3e2e4-185">USB를 통해 PC에 장치를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="3e2e4-186">PC에서 파일 탐색기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="3e2e4-187">이동:이 PC \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="3e2e4-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="3e2e4-188">필요한 모든 파일을 PC에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="3e2e4-189">팁:</span><span class="sxs-lookup"><span data-stu-id="3e2e4-189">Tips:</span></span>
- <span data-ttu-id="3e2e4-190">파일이 표시 되지 않는 경우 HoloLens에 로그인 하 여 데이터에 액세스할 수 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="3e2e4-191">문서 폴더에서 [진단 파일](hololens-diagnostic-logs.md#offline-diagnostics) 같은 다른 폴더의 다른 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="3e2e4-192">PC의 파일 탐색기에서 장치 속성을 선택 하 여 Windows Holographic OS 버전 번호 (펌웨어 버전), 장치 일련 번호 및 배터리 비율을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="3e2e4-193">조직에서 MDM을 사용 하 여 [연결/](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) a c c 연결을 사용 하지 않도록 설정한 경우 장치에 연결할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="3e2e4-194">혼합 현실 사진과 비디오 공유</span><span class="sxs-lookup"><span data-stu-id="3e2e4-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="3e2e4-195">혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-195">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="3e2e4-196">미리 보기 위에 있는 **공유** 아이콘을 선택 하 여 공유 길잡이를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-196">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="3e2e4-197">여기에서 해당 사진 또는 비디오를 공유할 끝점을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="3e2e4-198">혼합 현실 사진과 비디오를 자동으로 업로드 하 여 OneDrive에서 혼합 된 현실 사진과 비디오를 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-198">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="3e2e4-199">HoloLens에서 OneDrive 앱을 열고 아직 개인 [Microsoft 계정](https://account.microsoft.com) 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-199">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="3e2e4-200">**설정** 아이콘을 선택 하 고 **카메라 업로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-200">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="3e2e4-201">카메라 업로드를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-201">Turn Camera upload on.</span></span> <span data-ttu-id="3e2e4-202">이제 HoloLens에서 앱을 시작할 때마다 혼합 현실 사진과 비디오가 OneDrive에 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-202">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-203">Onedrive에 개인 Microsoft 계정 로그인 하는 경우에만 OneDrive에서 카메라 업로드를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-203">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="3e2e4-204">회사 또는 학교 계정을 사용 하 여 HoloLens를 설정 하는 경우 OneDrive 앱에서 개인 Microsoft 계정을 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-204">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="3e2e4-205">혼합 현실 캡처의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3e2e4-205">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="3e2e4-206">혼합 현실 캡처를 사용 하는 동안 HoloLens의 프레임 속도가 30 Hz로 반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-206">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="3e2e4-207">사진/비디오 카메라가 다른 응용 프로그램에서 이미 사용 중이거나 라이브 스트리밍 또는 시스템 리소스가 부족 한 경우 사진 및 비디오의 해상도가 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-207">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="3e2e4-208">최대 기록 길이</span><span class="sxs-lookup"><span data-stu-id="3e2e4-208">Maximum recording length</span></span>

<span data-ttu-id="3e2e4-209">Windows Holographic 이전에 HoloLens 2 장치에서 장치에 기록 된 버전 20H2 비디오는 5 분의 최대 길이로 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-209">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="3e2e4-210">고객의 의견 때문에 [혼합 현실 캡처](holographic-photos-and-videos.md)의 녹화 길이가 증가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-210">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="3e2e4-211">혼합 현실 캡처는 기본적으로 더 이상 5 분으로 제한 되지 않으며, 대신 사용 가능한 디스크 공간을 기준으로 최대 기록 길이를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-211">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="3e2e4-212">장치는 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 예상 하며 총 디스크 공간의 80%까지 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-212">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2e4-213">다음 중 하나가 발생 하는 경우 HoloLens는 기본 비디오 녹화 길이 (5 분)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-213">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="3e2e4-214">예상 최대 기록 기간은 기본값 5 분 보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-214">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="3e2e4-215">사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e4-215">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="3e2e4-216">기본 파일 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="3e2e4-216">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="3e2e4-217">기본 사진 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="3e2e4-217">Default photo format and resolution</span></span>

|  <span data-ttu-id="3e2e4-218">디바이스</span><span class="sxs-lookup"><span data-stu-id="3e2e4-218">Device</span></span>  |  <span data-ttu-id="3e2e4-219">서식</span><span class="sxs-lookup"><span data-stu-id="3e2e4-219">Format</span></span>  |  <span data-ttu-id="3e2e4-220">내선 번호</span><span class="sxs-lookup"><span data-stu-id="3e2e4-220">Extension</span></span>  |  <span data-ttu-id="3e2e4-221">해결 방법</span><span class="sxs-lookup"><span data-stu-id="3e2e4-221">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="3e2e4-222">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3e2e4-222">HoloLens 2</span></span> | [<span data-ttu-id="3e2e4-223">JPEG</span><span class="sxs-lookup"><span data-stu-id="3e2e4-223">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="3e2e4-224">.jpg</span><span class="sxs-lookup"><span data-stu-id="3e2e4-224">.jpg</span></span> | <span data-ttu-id="3e2e4-225">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="3e2e4-225">3904x2196px</span></span> |
| <span data-ttu-id="3e2e4-226">HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="3e2e4-226">HoloLens (1st gen)</span></span> | [<span data-ttu-id="3e2e4-227">JPEG</span><span class="sxs-lookup"><span data-stu-id="3e2e4-227">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="3e2e4-228">.jpg</span><span class="sxs-lookup"><span data-stu-id="3e2e4-228">.jpg</span></span> | <span data-ttu-id="3e2e4-229">1408x792px</span><span class="sxs-lookup"><span data-stu-id="3e2e4-229">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="3e2e4-230">녹화 된 비디오 형식 및 해상도</span><span class="sxs-lookup"><span data-stu-id="3e2e4-230">Recorded video format and resolution</span></span>

| <span data-ttu-id="3e2e4-231">디바이스</span><span class="sxs-lookup"><span data-stu-id="3e2e4-231">Device</span></span> | <span data-ttu-id="3e2e4-232">서식</span><span class="sxs-lookup"><span data-stu-id="3e2e4-232">Format</span></span> | <span data-ttu-id="3e2e4-233">내선 번호</span><span class="sxs-lookup"><span data-stu-id="3e2e4-233">Extension</span></span> | <span data-ttu-id="3e2e4-234">해결 방법</span><span class="sxs-lookup"><span data-stu-id="3e2e4-234">Resolution</span></span> | <span data-ttu-id="3e2e4-235">속도</span><span class="sxs-lookup"><span data-stu-id="3e2e4-235">Speed</span></span> | <span data-ttu-id="3e2e4-236">오디오</span><span class="sxs-lookup"><span data-stu-id="3e2e4-236">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="3e2e4-237">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3e2e4-237">HoloLens 2</span></span> | [<span data-ttu-id="3e2e4-238">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="3e2e4-238">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="3e2e4-239">.mp4</span><span class="sxs-lookup"><span data-stu-id="3e2e4-239">.mp4</span></span> | <span data-ttu-id="3e2e4-240">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="3e2e4-240">1920x1080px</span></span> | <span data-ttu-id="3e2e4-241">30fps</span><span class="sxs-lookup"><span data-stu-id="3e2e4-241">30fps</span></span> | <span data-ttu-id="3e2e4-242">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="3e2e4-242">48kHz Stereo</span></span> |
| <span data-ttu-id="3e2e4-243">HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="3e2e4-243">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="3e2e4-244">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="3e2e4-244">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="3e2e4-245">.mp4</span><span class="sxs-lookup"><span data-stu-id="3e2e4-245">.mp4</span></span> | <span data-ttu-id="3e2e4-246">1216x684px</span><span class="sxs-lookup"><span data-stu-id="3e2e4-246">1216x684px</span></span> | <span data-ttu-id="3e2e4-247">24fps</span><span class="sxs-lookup"><span data-stu-id="3e2e4-247">24fps</span></span> | <span data-ttu-id="3e2e4-248">48kHz 스테레오</span><span class="sxs-lookup"><span data-stu-id="3e2e4-248">48kHz Stereo</span></span> |
