---
title: HoloLens에서 파일 찾기 및 저장
description: HoloLens에서 파일 탐색기를 사용 하 여 혼합 현실 장치에서 파일을 열고, 보고, 관리 하는 방법에 대해 알아봅니다.
keywords: 방법, 파일 선택기, 파일, 사진, 비디오, 그림, OneDrive, 저장소, 파일 탐색기, hololens
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636183"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="ad01d-104">HoloLens에서 파일 찾기, 열기 및 저장</span><span class="sxs-lookup"><span data-stu-id="ad01d-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="ad01d-105">사진 및 비디오를 포함 하 여 HoloLens에서 만드는 파일은 HoloLens 장치에 직접 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="ad01d-106">Windows 10에서 파일을 관리 하는 것과 동일한 방식으로 뷰를 보고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="ad01d-107">파일 탐색기 앱을 사용 하 여 로컬 폴더에 액세스</span><span class="sxs-lookup"><span data-stu-id="ad01d-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="ad01d-108">앱의 저장소 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-108">Within an app's storage.</span></span>
- <span data-ttu-id="ad01d-109">특수 폴더 (예: 비디오 또는 음악 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="ad01d-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="ad01d-110">앱 및 파일 선택기 (예: OneDrive)를 포함 하는 저장소 서비스 사용.</span><span class="sxs-lookup"><span data-stu-id="ad01d-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="ad01d-111">MTP (미디어 전송 프로토콜) 지원을 사용 하 여 USB 케이블을 사용 하 여 HoloLens에 연결 된 데스크톱 PC를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="ad01d-112">파일 탐색기를 사용 하 여 HoloLens에서 파일 보기</span><span class="sxs-lookup"><span data-stu-id="ad01d-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="ad01d-113">[HoloLens 용 RS4 (Windows 10 4 월 2018 업데이트)](/windows/mixed-reality/release-notes-april-2018)의 모든 HoloLens 2 장치 및 HoloLens (첫 번째 gen)에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="ad01d-114">HoloLens의 파일 탐색기를 사용 하 여 3d 개체, 문서 및 그림을 비롯 한 장치에서 파일을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="ad01d-115">시작 하려면    >  **모든 앱**   >  **파일 탐색기** 시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="ad01d-116">파일 탐색기에 나열 된 파일이 없는 경우 왼쪽 위 창에서 **이 장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="ad01d-117">파일 탐색기에 파일이 표시 되지 않으면 "최근" 필터가 활성화 되어 있을 수 있습니다 (왼쪽 창에 클록 아이콘이 강조 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="ad01d-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="ad01d-118">이 문제를 해결 하려면 왼쪽 창 (시계 아이콘 아래)에서 **이 장치** 문서 아이콘을 선택 하거나 메뉴를 열고 **이 장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="ad01d-119">사진과 동영상 찾기 및 보기</span><span class="sxs-lookup"><span data-stu-id="ad01d-119">Find and view your photos and videos</span></span>

<span data-ttu-id="ad01d-120">[혼합 현실 캡처](holographic-photos-and-videos.md) 를 사용 하면 HoloLens에 대 한 현실 사진과 비디오를 혼합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="ad01d-121">이러한 사진과 비디오는 장치의 카메라 롤 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="ad01d-122">다음을 수행 하 여 HoloLens 된 사진과 비디오에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="ad01d-123">[사진 앱](holographic-photos-and-videos.md)을 통해 직접 카메라 롤에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="ad01d-124">사진과 비디오를 OneDrive에 동기화 하 여 사진 및 비디오를 클라우드 저장소에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="ad01d-125">[Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)의 혼합 현실 캡처 페이지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="ad01d-126">사진 앱</span><span class="sxs-lookup"><span data-stu-id="ad01d-126">Photos app</span></span>

<span data-ttu-id="ad01d-127">사진 앱은 **시작** 메뉴의 기본 앱 중 하나 이며 HoloLens를 사용 하 여 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="ad01d-128">[사진 앱을 사용 하 여 콘텐츠를 보는](holographic-photos-and-videos.md)방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="ad01d-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="ad01d-129">Microsoft Store에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 설치 하 여 사진을 다른 장치와 동기화 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="ad01d-130">OneDrive 앱</span><span class="sxs-lookup"><span data-stu-id="ad01d-130">OneDrive app</span></span>

<span data-ttu-id="ad01d-131">[OneDrive](https://onedrive.live.com/) 를 사용 하면 모든 장치 및 모든 사용자에 게 사진과 비디오를 액세스, 관리 및 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="ad01d-132">HoloLens에서 캡처된 사진과 비디오에 액세스 하려면 HoloLens의 Microsoft Store에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="ad01d-133">다운로드 한 후 OneDrive 앱을 열고 **설정**  >  **카메라 업로드** 를 선택한 후 **카메라 업로드** 를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="ad01d-134">PC에 커넥트</span><span class="sxs-lookup"><span data-stu-id="ad01d-134">Connect to a PC</span></span>

<span data-ttu-id="ad01d-135">HoloLens에서 [Windows 10 4 월 2018 업데이트](/windows/mixed-reality/release-notes-april-2018) 이상을 실행 하는 경우 MTP (미디어 전송 프로토콜)를 사용 하 여 장치에서 사진과 비디오를 검색 하는 데 USB 케이블을 사용 하 여 HoloLens를 Windows 10 PC에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="ad01d-136">장치에 PIN 또는 암호가 설정 되어 있는 경우 파일을 검색 하기 위해 장치의 잠금이 해제 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="ad01d-137">[Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal)을 사용 하도록 설정한 경우이를 사용 하 여 장치에 저장 된 사진과 비디오를 찾아보고 검색 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="ad01d-138">앱 내의 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="ad01d-138">Access files within an app</span></span>

<span data-ttu-id="ad01d-139">응용 프로그램이 장치에 파일을 저장 하는 경우 해당 응용 프로그램을 사용 하 여 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="ad01d-140">다른 앱에서 파일 요청</span><span class="sxs-lookup"><span data-stu-id="ad01d-140">Requesting files from another app</span></span>

<span data-ttu-id="ad01d-141">응용 프로그램은 [파일 선택기](/windows/mixed-reality/app-model#file-pickers)를 사용 하 여 파일을 저장 하거나 다른 앱에서 파일을 열도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="ad01d-142">알려진 폴더</span><span class="sxs-lookup"><span data-stu-id="ad01d-142">Known folders</span></span>

<span data-ttu-id="ad01d-143">HoloLens는 앱이 액세스할 수 있는 권한을 요청할 수 있는 많은 수의 [알려진 폴더](/windows/mixed-reality/app-model#known-folders) 를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="ad01d-144">PC에서 HoloLens 파일 보기</span><span class="sxs-lookup"><span data-stu-id="ad01d-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="ad01d-145">다른 모바일 장치와 마찬가지로, MTP (미디어 전송 프로토콜)를 사용 하 여 데스크톱 pc에 HoloLens 연결 하 고 PC에서 파일 탐색기를 열어 쉽게 전송할 수 있도록 HoloLens 라이브러리에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="ad01d-146">PC의 파일 탐색기에서 HoloLens 파일을 보려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="ad01d-147">HoloLens에 로그인 한 다음 HoloLens 함께 제공 된 USB 케이블을 사용 하 여 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="ad01d-148">**장치 열기를 선택 하 여 파일 탐색기** 에서 파일을 보거나 PC에서 파일 탐색기를 열고 장치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="ad01d-149">HoloLens에 대 한 정보를 보려면 PC의 파일 탐색기에서 장치 이름을 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="ad01d-150">HoloLens (첫 번째 gen)는 외부 하드 드라이브나 SD 카드에 연결 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="ad01d-151">클라우드로 동기화</span><span class="sxs-lookup"><span data-stu-id="ad01d-151">Sync to the cloud</span></span>

<span data-ttu-id="ad01d-152">HoloLens의 사진 및 기타 파일을 클라우드로 동기화 하려면 HoloLens에 OneDrive를 설치 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="ad01d-153">OneDrive를 얻으려면 HoloLens의 Microsoft Store에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="ad01d-154">HoloLens는 앱 파일과 데이터를 백업 하지 않으므로 OneDrive 하는 데 중요 한 내용을 저장 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="ad01d-155">이렇게 하면 장치를 초기화 하거나 앱을 제거 하는 경우 정보가 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad01d-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
