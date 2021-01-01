---
title: 프로비전 패키지
description: 앱, 앱 배포, 엔터프라이즈 앱 배포, 프로비저닝
keywords: 앱, 앱 배포, 엔터프라이즈 앱 배포, 프로비저닝
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
ms.openlocfilehash: 11bc83be188e1b81959690efcb2bdf26d800aae3
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252679"
---
# <span data-ttu-id="9d782-104">프로비전 패키지</span><span class="sxs-lookup"><span data-stu-id="9d782-104">Provisioning Package</span></span>

<span data-ttu-id="9d782-105">프로비저닝 패키지를 사용하여 끝점 관리에 액세스하지 않고도 환경에서 장치를 준비하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="9d782-106">또한 사용자의 ID, 등록 상태, OOBE(첫 실행 경험) 중 또는 설치 중에 프로비저닝 패키지를 적용하여 장치에 배포할 [수도 있습니다.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="9d782-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="9d782-107">프로비저닝 패키지 고려 사항:</span><span class="sxs-lookup"><span data-stu-id="9d782-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="9d782-108">비공용 앱</span><span class="sxs-lookup"><span data-stu-id="9d782-108">Non-Public apps</span></span>
* <span data-ttu-id="9d782-109">USB 테스트용 로드만</span><span class="sxs-lookup"><span data-stu-id="9d782-109">USB side-load only</span></span>
* <span data-ttu-id="9d782-110">자동 업데이트 없음(PPKG를 통한 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="9d782-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="9d782-111">프로비저닝 패키지를 통해 설치된 앱은 로컬 컴퓨터 저장소의 인증서에 의해 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="9d782-112">프로비저닝 패키지는 장치(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있으므로 동일한 프로비저닝 패키지를 통해 앱과 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="9d782-113">MDM에서 인증서를 배포하거나 인증서 관리자를 [](certificate-manager.md)통해 설치하는 경우 로컬 컴퓨터 저장소에 인증서를 배포하여 이 방식으로 설치된 앱에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="9d782-114">HoloLens 장치에 대한 프로비저닝 패키지를 만드는 기본 방법을 알아보고 [HoloLens 프로비전을 방문합니다.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="9d782-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="9d782-115">앱을 배포하려면 고급 프로비전으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="9d782-116">HoloLens(1세대)는 프로비저닝 패키지를 사용하여 앱**설치(UniversalAppInstall)를**제한적으로 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="9d782-117">HoloLens(1세대) 장치는 OOBE 중에만 PPKG를 통해 앱 설치를 지원하며 사용자 컨텍스트 설치만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="9d782-118">Setup</span><span class="sxs-lookup"><span data-stu-id="9d782-118">Setup</span></span>

<span data-ttu-id="9d782-119">[Windows 구성 디자이너 내에서는](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 4단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="9d782-120">ApplicationManagement/AllowAllTrustedApps를 "예"로 설정</span><span class="sxs-lookup"><span data-stu-id="9d782-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="9d782-121">See: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)</span><span class="sxs-lookup"><span data-stu-id="9d782-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="9d782-122">**UniversalAppInstall**  >  **UserContextAppLicense로** 이동합니다. **PackageFamilyName을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d782-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="9d782-123">[UniversalAppInstall을 참조합니다.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)</span><span class="sxs-lookup"><span data-stu-id="9d782-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="9d782-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="9d782-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="9d782-125">이미 앱을 설치한 디바이스에서 Device Portal을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="9d782-126">앱 페이지를 방문하고 PackageRelativeID 줄에서 "!" 앞에 있는 모든 정보를 살펴 봐야 합니다. **PackageFamilyName입니다.**</span><span class="sxs-lookup"><span data-stu-id="9d782-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="9d782-127">그러면 새 섹션 **ApplicationFile이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="9d782-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="9d782-128">이 영역을 사용하여 appx 번들을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="9d782-129">앱을 구매하거나 LOB 앱을 직접 구축한 경우 라이선스 파일 또는 보안 인증서를 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="9d782-130">라이선스 파일의 경우: **UniversalAppInstall**  >  **UserContextAppLicence로** 이동하여 라이선스 위치를 찾아 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="9d782-131">보안 파일의 경우 인증서로 이동하여 .appx 번들과 함께 설치할 인증서를 선택합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9d782-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="9d782-132">프로젝트를 안전한 위치에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d782-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="9d782-133">그런 **다음 프로비저닝** **패키지로 내보낼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9d782-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="9d782-134">참조: [HoloLens에](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)프로비저닝 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="9d782-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
