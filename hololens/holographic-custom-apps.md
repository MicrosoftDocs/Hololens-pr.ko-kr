---
title: HoloLens에 대한 사용자 지정 앱 관리
description: HoloLens에서 사용자 지정 앱을 테스트용 로드합니다. 홀로그램 앱 설치 및 설치에 대해 자세히 알아보습니다.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, 테스트용 로드, 테스트용 로드, 저장소, uwp, 앱, 설치
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218635"
---
# <span data-ttu-id="d6d6d-105">HoloLens에 대한 사용자 지정 앱 관리</span><span class="sxs-lookup"><span data-stu-id="d6d6d-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="d6d6d-106">HoloLens는 Microsoft Store 뿐만 아니라 HoloLens를 위해 특별히 만들어진 모든 새로운 앱에서 다양하고 흥미로운 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="d6d6d-107">이 문서에서는 사용자 지정 홀로그램 응용 프로그램에 초점을 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="d6d6d-108">스토어 앱에 대한 자세한 내용은 스토어에서 [앱 관리를 참조하세요.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="d6d6d-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6d6d-109">다음 정보는 당시 HoloLens 개발자 버전이라고도 하는 HoloLens(1세대)에 대해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="d6d6d-110">장치 포털을 통해 앱을 사이드로드하고 앱을 설치하는 Visual Studio 일반적인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="d6d6d-111">엔터프라이즈 배포의 경우 개발자 모드를 사용하도록 설정하지 않는 것이 좋습니다. 개발자 모드는 이러한 두 가지 방법을 모두 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="d6d6d-112">보안 앱 배포 방법에 관심이 있는 경우 앱 관리: 개요를 [검토하세요.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d6d6d-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="d6d6d-113">HoloLens 2 장치에 대한 앱 설치 개발자 방법을 찾고 있는 경우 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="d6d6d-114">디바이스 포털: 앱 설치</span><span class="sxs-lookup"><span data-stu-id="d6d6d-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="d6d6d-115">앱 Visual Studio 배포 및 디버그</span><span class="sxs-lookup"><span data-stu-id="d6d6d-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="d6d6d-116">사용자 지정 앱 설치</span><span class="sxs-lookup"><span data-stu-id="d6d6d-116">Install custom apps</span></span>

<span data-ttu-id="d6d6d-117">장치 포털을 사용하거나 디바이스 포털에서 앱을 배포하여 HoloLens에 자체 응용 프로그램을 설치할 수 Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="d6d6d-118">Device Portal을 사용하여 응용 프로그램 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="d6d6d-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="d6d6d-119">디바이스 [포털에서](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 대상 HoloLens로의 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="d6d6d-120">왼쪽 탐색에서 앱 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="d6d6d-121">앱 **패키지 아래에서** 응용 프로그램과 연결된 .appx 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="d6d6d-122">관련된 종속성 및 인증서 파일을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="d6d6d-123">Go를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-123">Select **Go**.</span></span>
   ![Microsoft HoloLens의 Windows Device Portal에 앱 양식 설치](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="d6d6d-125">Microsoft Visual Studio 2015에서 배포</span><span class="sxs-lookup"><span data-stu-id="d6d6d-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="d6d6d-126">앱의 Visual Studio 솔루션(.sln 파일)을 니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="d6d6d-127">프로젝트의 속성을 **여는 경우**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="d6d6d-128">**Master/x86/Remote Machine 빌드 구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="d6d6d-129">원격 컴퓨터 **선택:**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="d6d6d-130">주소가 HoloLens의 Wi-Fi IP 주소를 설정하는지 확인</span><span class="sxs-lookup"><span data-stu-id="d6d6d-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="d6d6d-131">인증을 **유니버설(암호화되지 않은 프로토콜)로 설정**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="d6d6d-132">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-132">Build your solution.</span></span>
1. <span data-ttu-id="d6d6d-133">개발 PC에서 HoloLens로 앱을 배포하려면 원격 **머신을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="d6d6d-134">HoloLens에 기존 빌드가 이미 있는 경우 **예를** 선택하여 이 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Microsoft HoloLens에 앱을 위한 원격 컴퓨터 Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="d6d6d-136">응용 프로그램이 HoloLens에 설치 및 자동 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6d-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="d6d6d-137">앱을 설치한 후 모든 앱 목록(모든 \*\*\*\* 앱 시작)에서\*\*\*\*  >  **찾을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d6d6d-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
