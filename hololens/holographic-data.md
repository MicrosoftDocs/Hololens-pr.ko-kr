---
title: HoloLens에서 파일 찾기 및 저장
description: HoloLens의 파일 탐색기를 사용 하 여 장치에서 파일 보기 및 관리
keywords: HoloLens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828558"
---
# <span data-ttu-id="d3e0f-104">HoloLens에서 파일 찾기, 열기 및 저장</span><span class="sxs-lookup"><span data-stu-id="d3e0f-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="d3e0f-105">HoloLens에서 만든 사진 및 비디오 등의 파일은 HoloLens 장치에 직접 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="d3e0f-106">Windows 10에서 파일을 관리 하는 것과 동일한 방법으로 보기 및 관리:</span><span class="sxs-lookup"><span data-stu-id="d3e0f-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="d3e0f-107">파일 탐색기 앱을 사용 하 여 로컬 폴더에 액세스</span><span class="sxs-lookup"><span data-stu-id="d3e0f-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="d3e0f-108">앱 저장소 내</span><span class="sxs-lookup"><span data-stu-id="d3e0f-108">Within an app's storage.</span></span>
- <span data-ttu-id="d3e0f-109">비디오 또는 음악 라이브러리와 같은 특수 폴더</span><span class="sxs-lookup"><span data-stu-id="d3e0f-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="d3e0f-110">앱과 파일 선택 (예: OneDrive)이 포함 된 저장소 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="d3e0f-111">MTP (미디어 전송 프로토콜) 지원을 사용 하 여 HoloLens에 연결 된 데스크톱 PC를 USB 케이블로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="d3e0f-112">파일 탐색기를 사용 하 여 HoloLens에서 파일 보기</span><span class="sxs-lookup"><span data-stu-id="d3e0f-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="d3e0f-113">[Hololens에 대 한 Windows 10 4 월 2018 업데이트 (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)의 모든 HoloLens 2 장치 및 HoloLens (1 회 gen)에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="d3e0f-114">HoloLens의 파일 탐색기를 사용 하 여 3D 개체, 문서, 그림을 비롯 한 장치에서 파일을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="d3e0f-115">**Start**   >  시작 하려면**모든 앱**   >  **파일 탐색기** 시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="d3e0f-116">파일 탐색기에 파일이 나열 되어 있지 않으면 왼쪽 위 창에서 **이 장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="d3e0f-117">파일 탐색기에 파일이 표시 되지 않는 경우 "최근" 필터가 활성 상태일 수 있습니다 (시계 아이콘이 왼쪽 창에서 강조 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="d3e0f-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="d3e0f-118">이 문제를 해결 하려면 왼쪽 창에서 **이 장치** 문서 아이콘 (시계 아이콘 아래)을 선택 하거나 메뉴를 열고 **이 장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="d3e0f-119">사진 및 동영상 찾기 및 보기</span><span class="sxs-lookup"><span data-stu-id="d3e0f-119">Find and view your photos and videos</span></span>

<span data-ttu-id="d3e0f-120">[Mixed reality 캡처](holographic-photos-and-videos.md) 를 사용 하 여 HoloLens에서 실제로 사용할 수 있는 사진 및 동영상을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="d3e0f-121">이러한 사진과 비디오는 장치의 카메라 앨범 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="d3e0f-122">아래와 같은 방법으로 HoloLens를 사용 하 여 찍은 사진과 비디오에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="d3e0f-123">[사진 앱](holographic-photos-and-videos.md)을 통해 카메라 롤에 직접 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="d3e0f-124">사진과 비디오를 OneDrive에 동기화 하 여 클라우드 저장소에 사진 및 비디오를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="d3e0f-125">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)의 Mixed Reality 캡처 페이지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="d3e0f-126">사진 앱</span><span class="sxs-lookup"><span data-stu-id="d3e0f-126">Photos app</span></span>

<span data-ttu-id="d3e0f-127">사진 앱은 **시작** 메뉴의 기본 앱 중 하나 이며, HoloLens를 사용 하 여 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="d3e0f-128">[사진 앱을 사용 하 여 콘텐츠를 보는](holographic-photos-and-videos.md)방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="d3e0f-129">Microsoft Store에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 설치 하 여 사진을 다른 장치에 동기화 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="d3e0f-130">OneDrive 앱</span><span class="sxs-lookup"><span data-stu-id="d3e0f-130">OneDrive app</span></span>

<span data-ttu-id="d3e0f-131">[OneDrive](https://onedrive.live.com/) 를 사용 하면 모든 장치 및 사용자와 함께 사진과 비디오에 액세스 하 고, 관리 하 고, 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="d3e0f-132">HoloLens에서 캡처한 사진과 비디오에 액세스 하려면 HoloLens의 Microsoft 스토어에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="d3e0f-133">다운로드 되 면 OneDrive 앱을 열고 **설정**  >  **카메라 업로드**를 선택 하 고 **카메라 업로드**를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="d3e0f-134">PC에 연결</span><span class="sxs-lookup"><span data-stu-id="d3e0f-134">Connect to a PC</span></span>

<span data-ttu-id="d3e0f-135">HoloLens에서 [windows 10 4 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 이상을 실행 하는 경우 USB 케이블을 사용 하 여 WINDOWS 10 PC에 hololens를 연결 하 고 MTP (미디어 전송 프로토콜)를 사용 하 여 디바이스의 사진 및 비디오를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="d3e0f-136">장치에 PIN 또는 암호가 설정 되어 있는 경우 장치를 잠금 해제 하 여 파일을 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="d3e0f-137">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용 하도록 설정한 경우 장치에 저장 된 사진과 비디오를 찾아보고 검색 하 고 관리 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="d3e0f-138">앱 내에서 파일에 액세스</span><span class="sxs-lookup"><span data-stu-id="d3e0f-138">Access files within an app</span></span>

<span data-ttu-id="d3e0f-139">응용 프로그램이 장치에 파일을 저장 하는 경우 해당 응용 프로그램을 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="d3e0f-140">다른 앱에서 파일 요청</span><span class="sxs-lookup"><span data-stu-id="d3e0f-140">Requesting files from another app</span></span>

<span data-ttu-id="d3e0f-141">파일 [선택기](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)를 사용 하 여 응용 프로그램에서 파일을 저장 하거나 다른 앱에서 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="d3e0f-142">알려진 폴더</span><span class="sxs-lookup"><span data-stu-id="d3e0f-142">Known folders</span></span>

<span data-ttu-id="d3e0f-143">HoloLens는 앱이 액세스 권한을 요청할 수 있는 여러 개의 [알려진 폴더](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) 를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="d3e0f-144">PC에서 HoloLens 파일 보기</span><span class="sxs-lookup"><span data-stu-id="d3e0f-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="d3e0f-145">다른 모바일 장치와 유사 하 게, MTP (미디어 전송 프로토콜)를 사용 하 여 HoloLens를 데스크톱 PC에 연결 하 고 PC의 파일 탐색기를 열어 사용자 환경 전송을 위해 HoloLens 라이브러리에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="d3e0f-146">PC의 파일 탐색기에서 HoloLens 파일을 보려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="d3e0f-147">HoloLens에 로그인 한 다음 HoloLens와 함께 제공 되는 USB 케이블을 사용 하 여 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="d3e0f-148">**장치 열기를 선택 하 여 파일 탐색기를 사용 하 여 파일을 보거나**PC의 파일 탐색기를 열고 장치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="d3e0f-149">HoloLens에 대 한 정보를 보려면 PC의 파일 탐색기에서 장치 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="d3e0f-150">HoloLens (첫번째 gen)는 외부 하드 드라이브 또는 SD 카드에 대 한 연결을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="d3e0f-151">클라우드와 동기화</span><span class="sxs-lookup"><span data-stu-id="d3e0f-151">Sync to the cloud</span></span>

<span data-ttu-id="d3e0f-152">HoloLens의 사진 및 기타 파일을 클라우드와 동기화 하려면 HoloLens에 OneDrive를 설치 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="d3e0f-153">OneDrive를 다운로드 하려면 HoloLens의 Microsoft Store에서 검색 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="d3e0f-154">HoloLens는 앱 파일 및 데이터를 백업 하지 않으므로 중요 한 내용을 OneDrive에 저장 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="d3e0f-155">이렇게 하면 장치를 다시 설정 하거나 앱을 제거 하면 정보가 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e0f-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
