---
title: 패키지 프로비저닝
description: 앱, 앱 배포, 엔터프라이즈 앱 demployment, 프로비저닝
keywords: 앱, 앱 배포, 엔터프라이즈 앱 demployment, 프로비저닝
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857951"
---
# <span data-ttu-id="7ca70-104">패키지 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="7ca70-104">Provisioning Package</span></span>

<span data-ttu-id="7ca70-105">프로 비전 패키지를 사용 하 여 끝점 관리에 대 한 액세스 권한이 없는 환경에서 디바이스를 준비 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="7ca70-106">또한 사용자의 id, 등록 상태 (OOBE) 중, [설치 중에 프로비저닝 패키지를 적용](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)하 여 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="7ca70-107">패키지 제공 고려 사항:</span><span class="sxs-lookup"><span data-stu-id="7ca70-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="7ca70-108">Public이 아닌 앱</span><span class="sxs-lookup"><span data-stu-id="7ca70-108">Non-Public apps</span></span>
* <span data-ttu-id="7ca70-109">USB 쪽만 로드</span><span class="sxs-lookup"><span data-stu-id="7ca70-109">USB side-load only</span></span>
* <span data-ttu-id="7ca70-110">자동 업데이트 없음 (PPKGs를 통한 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="7ca70-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="7ca70-111">HoloLens 장치용 프로비저닝 패키지를 만드는 방법에 대 한 기본 사항을 알아보려면 [Hololens 프로비저닝](https://docs.microsoft.com/hololens/hololens-provisioning)을 방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca70-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="7ca70-112">앱을 배포 하려면 고급 프로 비전으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="7ca70-113">Setup</span><span class="sxs-lookup"><span data-stu-id="7ca70-113">Setup</span></span>

<span data-ttu-id="7ca70-114">[Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 내에서 4 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="7ca70-115">ApplicationManagement/AllowAllTrustedApps를 "Yes"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="7ca70-116">[Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca70-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="7ca70-117">**UniversalAppInstall**  >  **UserContextAppLicense** 에서 **PackageFamilyName**를 입력 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ca70-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="7ca70-118">[UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca70-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="7ca70-119">참고 항목: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="7ca70-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="7ca70-120">이 방법을 모를 경우 앱을 이미 설치한 장치에서 디바이스 포털을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="7ca70-121">앱 페이지를 방문 하 여 PackageRelativeID 줄을 살펴보고 "!" 앞에 있는 모든 정보 **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="7ca70-122">그러면 새 섹션 **Applicationfile**이 있다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="7ca70-123">이 영역을 사용 하 여 appx 번들을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="7ca70-124">앱을 구입 했거나 고유한 LOB 앱을 빌드 했는지에 따라 라이선스 파일 또는 보안 인증서를 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="7ca70-125">라이선스 파일: **UniversalAppInstall**  >  **UserContextAppLience** 에서 라이선스의 위치로 이동 하 여 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="7ca70-126">보안 파일의 경우 **인증서** 로 이동한 다음 인증서를 선택 하 여 .appx 번들과 함께 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="7ca70-127">프로젝트를 안전한 위치에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca70-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="7ca70-128">그런 다음이를 **프로비저닝 패키지로** **내보냅니다** .</span><span class="sxs-lookup"><span data-stu-id="7ca70-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="7ca70-129">또한 [HoloLens에 provisiong 패키지 적용을](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca70-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
