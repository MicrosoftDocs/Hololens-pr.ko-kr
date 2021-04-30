---
title: 프로 비전 패키지
description: HoloLens 장치에 대 한 앱 패키징, 프로 비전, 배포 및 엔터프라이즈 앱 배포에 대해 알아봅니다.
keywords: 앱, 앱 배포, 엔터프라이즈 앱 배포, 프로 비전
author: evmill
ms.author: v-evmill
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309408"
---
# <a name="provisioning-package"></a><span data-ttu-id="074e9-104">프로 비전 패키지</span><span class="sxs-lookup"><span data-stu-id="074e9-104">Provisioning Package</span></span>

<span data-ttu-id="074e9-105">프로 비전 패키지를 사용 하 여 끝점 관리에 액세스 하지 않고도 환경에서 장치를 준비 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="074e9-106">또한 OOBE (첫 실행 경험)를 사용 하거나 [설치 중에 프로 비전 패키지를 적용](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)하 여 사용자 id, 등록 상태에 관계 없이 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="074e9-107">프로 비전 패키지 고려 사항:</span><span class="sxs-lookup"><span data-stu-id="074e9-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="074e9-108">공용이 아닌 앱</span><span class="sxs-lookup"><span data-stu-id="074e9-108">Non-Public apps</span></span>
* <span data-ttu-id="074e9-109">USB 테스트용 로드만</span><span class="sxs-lookup"><span data-stu-id="074e9-109">USB side-load only</span></span>
* <span data-ttu-id="074e9-110">자동 업데이트 없음 (PPKGs를 통한 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="074e9-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="074e9-111">프로 비전 패키지를 통해 설치 된 앱은 로컬 컴퓨터 저장소에 있는 인증서로 서명 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="074e9-112">프로 비전 패키지는 장치 (로컬 컴퓨터) 저장소에 인증서를 설치할 수 있으므로 동일한 프로 비전 패키지를 통해 앱과 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="074e9-113">MDM에서 인증서를 배포 하거나 [인증서 관리자](certificate-manager.md)를 통해 설치 하는 경우이 방식으로 설치 된 앱에 서명 하려면 인증서를 로컬 컴퓨터 저장소에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="074e9-114">HoloLens 장치에 대 한 프로 비전 패키지를 만드는 기본 사항을 알아보려면 [Hololens 프로 비전](https://docs.microsoft.com/hololens/hololens-provisioning)을 방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="074e9-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="074e9-115">앱을 배포 하려면 고급 프로 비전으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="074e9-116">HoloLens (첫 번째 gen)는 프로 비전 패키지를 사용 하 여 앱 설치 (**UniversalAppInstall**)를 제한적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="074e9-117">HoloLens (첫 번째 gen) 장치는 OOBE 중에만 PPKG를 통해 앱을 설치 하 고 사용자 컨텍스트 설치만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="074e9-118">설치</span><span class="sxs-lookup"><span data-stu-id="074e9-118">Setup</span></span>

<span data-ttu-id="074e9-119">[Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 내에서 다음 네 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="074e9-120">ApplicationManagement/AllowAllTrustedApps을 "Yes"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="074e9-121">[Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="074e9-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="074e9-122">**UniversalAppInstall**  >  **UserContextAppLicense** **PackageFamilyName** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="074e9-123">[UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="074e9-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="074e9-124">참고 항목: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)</span><span class="sxs-lookup"><span data-stu-id="074e9-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="074e9-125">앱을 이미 설치한 장치에서 장치 포털을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="074e9-126">앱 페이지를 방문 하 여 "!" 앞에 있는 모든 정보를 PackageRelativeID. **PackageFamilyName** 입니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="074e9-127">그러면 새 섹션인 **Applicationfile** 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="074e9-128">이 영역을 사용 하 여 appx 번들을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="074e9-129">앱을 구입 했거나 사용자 고유의 LOB 앱을 빌드 했는지에 따라 라이선스 파일이 나 보안 인증서를 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="074e9-130">라이선스 파일의 경우: **UniversalAppInstall**  >  **usercontext** 로 이동 하 여 라이선스의 위치로 이동 하 여 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="074e9-131">보안 파일에 대해 **인증서** 로 이동 하 고 .appx 번들과 함께 설치할 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="074e9-132">프로젝트를 안전한 위치에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074e9-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="074e9-133">그런 다음 **프로 비전 패키지로** **내보냅니다** .</span><span class="sxs-lookup"><span data-stu-id="074e9-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="074e9-134">참고 항목: [HoloLens에 프로 비전 패키지 적용을](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="074e9-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
