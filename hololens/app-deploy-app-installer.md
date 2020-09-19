---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 로드 하 고 설치 하는 방법
description: UI를 통해 앱 로드 및 설치
keywords: 앱 관리, 앱, hololens, 앱 설치 관리자
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027482"
---
# <span data-ttu-id="4000d-104">앱 설치 관리자를 통해 HoloLens 2에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="4000d-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="4000d-105">이제 개발자 모드를 사용 하도록 설정 하거나 Device Portal을 사용할 필요 없이 이제 Appx 번들을 통해 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="4000d-106">이 환경은 로컬 장치에 앱을 설치 하거나 HoloLens의 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유 하는 것을 간단 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4000d-107">이 기능은 현재 Windows 참가자 빌드 19041.1377 +에만 avalible 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="4000d-108">[Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="4000d-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4000d-109">앱 설치 관리자가 스토어의 종속성을 사용 하므로 앱의 솔루션 구성이 **Master** 또는 **Release** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="4000d-110">[앱 패키지 만들기](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4000d-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="4000d-111">HoloLens 2 디바이스의 전원이 켜져 있고 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="4000d-112">PC에서 사용자 지정 앱으로 이동 하 고 yourapp를 yourdevicename\Internal Storage\Downloads.에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="4000d-113">파일 복사가 완료 되 면 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="4000d-114">HoloLens 2 장치에서 **시작 메뉴**를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="4000d-115">다운로드 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="4000d-116">앱의 왼쪽 창에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="4000d-117">Yourapp 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="4000d-118">앱 설치 관리자가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-118">The App Installer will launch.</span></span> <span data-ttu-id="4000d-119">**설치** 단추를 선택 하 여 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="4000d-120">설치가 완료 되 면 설치 된 앱이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="4000d-122">앱을 설치 하지 못한 경우 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="4000d-123">앱이 마스터 또는 릴리스 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="4000d-124">[인터넷에 연결](hololens-network.md)되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="4000d-125">[Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4000d-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
