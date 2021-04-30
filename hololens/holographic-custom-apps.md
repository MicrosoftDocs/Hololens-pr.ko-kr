---
title: HoloLens 용 사용자 지정 앱 관리 (첫 번째 gen)
description: 장치 포털 및 Visual Studio를 사용 하 여 HoloLens 장치에 사용자 지정 holographic apps를 설치, 제거 및 함께 로드 하는 방법을 알아봅니다.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, 테스트용으로 로드, 부하, 테스트용 부하, 스토어, uwp, 앱, 설치
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309309"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="486ed-104">HoloLens 용 사용자 지정 앱 관리 (첫 번째 gen)</span><span class="sxs-lookup"><span data-stu-id="486ed-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="486ed-105">HoloLens는 현재 HoloLens 용으로 빌드된 새로운 앱 뿐만 아니라 Microsoft Store의 많은 기존 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="486ed-106">이 문서에서는 사용자 지정 holographic 응용 프로그램에 대해 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="486ed-107">스토어 앱에 대 한 자세한 내용은 [스토어를 사용 하 여 앱 관리](holographic-store-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="486ed-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="486ed-108">HoloLens (첫 번째 gen)에 대해 다음 정보가 생성 되었습니다 .이는 시점의 HoloLens Developer Edition이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="486ed-109">이러한 테스트용 로드 앱은 장치 포털을 통해 그리고 Visual Studio를 통해 앱을 설치 하는 것이 일반적 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="486ed-110">엔터프라이즈 배포의 경우 두 방법 모두를 사용 하는 개발자 모드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="486ed-111">보안 앱 배포 방법에 관심이 있는 경우 [앱 관리: 개요](app-deploy-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="486ed-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="486ed-112">HoloLens 2 장치에 대 한 앱 설치 개발자 방법을 찾고 있는 경우 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="486ed-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="486ed-113">장치 포털: 앱 설치</span><span class="sxs-lookup"><span data-stu-id="486ed-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="486ed-114">Visual Studio를 사용 하 여 응용 프로그램 배포 및 디버그</span><span class="sxs-lookup"><span data-stu-id="486ed-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="486ed-115">사용자 지정 앱 설치</span><span class="sxs-lookup"><span data-stu-id="486ed-115">Install custom apps</span></span>

<span data-ttu-id="486ed-116">장치 포털을 사용 하거나 Visual Studio에서 앱을 배포 하 여 HoloLens에 사용자 고유의 응용 프로그램을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="486ed-117">장치 포털을 사용 하 여 응용 프로그램 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="486ed-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="486ed-118">[장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 에서 대상 HoloLens로의 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="486ed-119">왼쪽 탐색 영역에서 **앱** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="486ed-120">**앱 패키지** 아래에서 응용 프로그램과 연결 된 .appx 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="486ed-121">연결 된 종속성 및 인증서 파일을 모두 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="486ed-122">**이동** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="486ed-123">![Microsoft HoloLens의 Windows 장치 포털에서 앱 양식 설치](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="486ed-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="486ed-124">Microsoft Visual Studio 2015에서 배포</span><span class="sxs-lookup"><span data-stu-id="486ed-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="486ed-125">앱의 Visual Studio 솔루션 (.sln 파일)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="486ed-126">프로젝트의 **속성** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="486ed-127">빌드 구성: **Master/x86/원격 컴퓨터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="486ed-128">**원격 컴퓨터** 를 선택 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="486ed-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="486ed-129">주소가 HoloLens의 Wi-Fi IP 주소를 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="486ed-130">인증을 **유니버설 (암호화 되지 않은 프로토콜)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="486ed-131">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-131">Build your solution.</span></span>

1. <span data-ttu-id="486ed-132">개발 PC에서 HoloLens에 앱을 배포 하려면 **원격 컴퓨터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="486ed-133">HoloLens에 기존 빌드가 이미 있는 경우 **예** 를 선택 하 여이 최신 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio에서 Microsoft HoloLens로 앱에 대 한 원격 컴퓨터 배포](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="486ed-135">응용 프로그램이 설치 되 고 HoloLens에 자동 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="486ed-136">앱을 설치한 후에는 **모든 앱** 목록 (  >  **모든 앱** 시작)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="486ed-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
