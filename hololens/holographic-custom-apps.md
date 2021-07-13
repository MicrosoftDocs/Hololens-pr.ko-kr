---
title: HoloLens(1세대)용 사용자 지정 앱 관리
description: 장치 포털 및 Visual Studio 사용하여 HoloLens 디바이스에서 사용자 지정 홀로그램 앱을 설치, 제거 및 사이드로드하는 방법을 알아봅니다.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
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
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635911"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="47656-104">HoloLens(1세대)용 사용자 지정 앱 관리</span><span class="sxs-lookup"><span data-stu-id="47656-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="47656-105">HoloLens Microsoft Store 많은 기존 애플리케이션뿐만 아니라 HoloLens 위해 특별히 빌드된 새 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="47656-106">이 문서에서는 사용자 지정 홀로그램 애플리케이션에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="47656-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="47656-107">스토어 앱에 대한 자세한 내용은 [스토어를](holographic-store-apps.md)통해 앱 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47656-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47656-108">다음 정보는 당시 HoloLens Developer Edition이라고도 하는 HoloLens(1세대)에 대해 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="47656-109">따라서 디바이스 포털을 통해 앱을 테스트용으로 로드하고 Visual Studio 통해 앱을 설치하는 것이 일반적이었습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="47656-110">엔터프라이즈 배포의 경우 두 방법 모두에 사용되는 개발자 모드를 사용하도록 설정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="47656-111">보안 앱 배포 방법에 관심이 있는 경우 [앱 관리: 개요를](app-deploy-overview.md)검토하세요.</span><span class="sxs-lookup"><span data-stu-id="47656-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="47656-112">HoloLens 2 디바이스에 대한 앱 설치의 개발자 방법을 원하는 경우 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47656-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="47656-113">장치 포털: 앱 설치</span><span class="sxs-lookup"><span data-stu-id="47656-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="47656-114">Visual Studio 사용하여 앱 배포 및 디버그</span><span class="sxs-lookup"><span data-stu-id="47656-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="47656-115">사용자 지정 앱 설치</span><span class="sxs-lookup"><span data-stu-id="47656-115">Install custom apps</span></span>

<span data-ttu-id="47656-116">장치 포털 사용하거나 Visual Studio 앱을 배포하여 HoloLens 고유한 애플리케이션을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="47656-117">장치 포털 애플리케이션 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="47656-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="47656-118">장치 포털 대상 [HoloLens](/windows/mixed-reality/using-the-windows-device-portal) 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="47656-119">왼쪽 탐색 창에서 **앱** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="47656-120">**앱 패키지** 아래에서 애플리케이션과 연결된 .appx 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="47656-121">연결된 종속성 및 인증서 파일을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="47656-122">**이동** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47656-123">![Microsoft HoloLens Windows 장치 포털 앱 양식 설치](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="47656-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="47656-124">Microsoft Visual Studio 2015에서 배포</span><span class="sxs-lookup"><span data-stu-id="47656-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="47656-125">앱의 Visual Studio 솔루션(.sln 파일)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47656-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="47656-126">프로젝트의 **속성** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47656-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="47656-127">다음 빌드 구성을 선택합니다. **Master/x86/Remote Machine.**</span><span class="sxs-lookup"><span data-stu-id="47656-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="47656-128">**원격 컴퓨터** 를 선택하는 경우:</span><span class="sxs-lookup"><span data-stu-id="47656-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="47656-129">주소가 HoloLens Wi-Fi IP 주소를 가리키는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="47656-130">인증을 **유니버설(암호화되지 않은 프로토콜) 로** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="47656-131">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-131">Build your solution.</span></span>

1. <span data-ttu-id="47656-132">개발 PC에서 HoloLens 앱을 배포하려면 원격 **컴퓨터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="47656-133">HoloLens 기존 빌드가 이미 있는 경우 **예를** 선택하여 이 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio Microsoft HoloLens 앱에 대한 원격 컴퓨터 배포](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="47656-135">애플리케이션이 HoloLens 설치 및 자동 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="47656-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="47656-136">앱을 설치한 후 모든 앱 목록에서 찾을 수 **있습니다(모든 앱**   >  시작).</span><span class="sxs-lookup"><span data-stu-id="47656-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
