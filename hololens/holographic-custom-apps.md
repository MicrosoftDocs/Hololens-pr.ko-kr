---
title: HoloLens에 대한 사용자 지정 앱 관리
description: HoloLens에서 사용자 지정 앱을 로드 합니다. 홀로그램 앱 설치 및 제거에 대해 자세히 알아보세요.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens, 테스트용으로 로드, 사이드 부하, 측면 부하, 스토어, uwp, 앱, 설치
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828863"
---
# <span data-ttu-id="4a72e-105">HoloLens에 대한 사용자 지정 앱 관리</span><span class="sxs-lookup"><span data-stu-id="4a72e-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="4a72e-106">HoloLens는 Microsoft Store에서 제공 하는 다양 한 기존 응용 프로그램과 HoloLens 용으로 고안 된 새 앱을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="4a72e-107">이 문서에서는 사용자 지정 홀로그램 응용 프로그램에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="4a72e-108">스토어 앱에 대 한 자세한 내용은 [스토어를 사용 하 여 앱 관리](holographic-store-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a72e-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="4a72e-109">사용자 지정 앱 설치</span><span class="sxs-lookup"><span data-stu-id="4a72e-109">Install custom apps</span></span>

<span data-ttu-id="4a72e-110">디바이스 포털을 사용 하거나 Visual Studio에서 앱을 배포 하 여 HoloLens에 자신만의 응용 프로그램을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="4a72e-111">장치 포털을 사용 하 여 응용 프로그램 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="4a72e-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="4a72e-112">[장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 에서 대상 HoloLens로의 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="4a72e-113">왼쪽 탐색 창에서 **Apps** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="4a72e-114">**앱 패키지** 에서 응용 프로그램과 연결 된 .appx 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="4a72e-115">연결 된 종속성 및 인증서 파일을 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="4a72e-116">**이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-116">Select **Go**.</span></span>
   ![Microsoft HoloLens의 Windows Device Portal에서 앱 양식 설치](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="4a72e-118">Microsoft Visual Studio 2015에서 배포</span><span class="sxs-lookup"><span data-stu-id="4a72e-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="4a72e-119">앱의 Visual Studio 솔루션 (.sln 파일)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="4a72e-120">프로젝트의 **속성**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="4a72e-121">**Master/x86/원격 컴퓨터**빌드 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="4a72e-122">**원격 컴퓨터**를 선택 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="4a72e-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="4a72e-123">주소가 HoloLens의 Wi-fi IP 주소를 가리키는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a72e-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="4a72e-124">인증을 **유니버설 (암호화 되지 않은 프로토콜)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="4a72e-125">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-125">Build your solution.</span></span>
1. <span data-ttu-id="4a72e-126">개발 PC에서 HoloLens에 앱을 배포 하려면 **원격 컴퓨터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="4a72e-127">HoloLens에 이미 기존 빌드가 있는 경우 **예** 를 선택 하 여이 최신 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio에서 Microsoft HoloLens 용 앱에 대 한 원격 컴퓨터 배포](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="4a72e-129">응용 프로그램이 HoloLens에 설치 되 고 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="4a72e-130">앱을 설치한 후에는 **모든** 앱 목록 (**Start**  >  **모든 앱**시작)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a72e-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
