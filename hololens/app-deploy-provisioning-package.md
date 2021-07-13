---
title: 프로비전 패키지
description: HoloLens 디바이스용 앱 패키징, 프로비저닝, 배포 및 엔터프라이즈 앱 배포에 대해 알아봅니다.
keywords: 앱, 앱 배포, 엔터프라이즈 앱 배포, 프로비전
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635520"
---
# <a name="provisioning-package"></a><span data-ttu-id="a95a7-104">프로비전 패키지</span><span class="sxs-lookup"><span data-stu-id="a95a7-104">Provisioning Package</span></span>

<span data-ttu-id="a95a7-105">프로비전 패키지는 엔드포인트 관리에 액세스하지 않고 환경에서 디바이스를 준비하고 구성하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="a95a7-106">사용자 ID, 등록 상태, OOBE(첫 실행 경험) 중 또는 [설치 중에 프로비전 패키지를 적용하여](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)디바이스에 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="a95a7-107">패키지 프로비전 고려 사항:</span><span class="sxs-lookup"><span data-stu-id="a95a7-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="a95a7-108">비공용 앱</span><span class="sxs-lookup"><span data-stu-id="a95a7-108">Non-Public apps</span></span>
* <span data-ttu-id="a95a7-109">USB 쪽 로드 전용</span><span class="sxs-lookup"><span data-stu-id="a95a7-109">USB side-load only</span></span>
* <span data-ttu-id="a95a7-110">자동 업데이트 없음(PPKG를 통한 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="a95a7-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="a95a7-111">프로비전 패키지를 통해 설치된 앱은 로컬 머신 저장소의 인증서로 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="a95a7-112">프로비전 패키지는 디바이스(로컬 머신) 저장소에만 인증서를 설치할 수 있으므로 동일한 프로비전 패키지를 통해 앱과 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="a95a7-113">MDM에서 인증서를 배포하거나 [인증서 관리자를](certificate-manager.md)통해 설치하는 경우 로컬 컴퓨터 저장소에 인증서를 배포하여 이러한 방식으로 설치된 앱에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="a95a7-114">HoloLens 디바이스용 프로비저닝 패키지를 만드는 기본 사항 알아보려면 [HoloLens 프로비전 을](/hololens/hololens-provisioning)방문하세요.</span><span class="sxs-lookup"><span data-stu-id="a95a7-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="a95a7-115">앱을 배포하려면 고급 프로비저닝으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="a95a7-116">HoloLens(1세대)는 프로비전 패키지를 사용하여 앱 **설치(UniversalAppInstall)를** 제한했습니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="a95a7-117">HoloLens(1세대) 디바이스는 OOBE 중에만 PPKG를 통해서만 사용자 컨텍스트 설치를 통해서만 앱 설치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="a95a7-118">설치 프로그램</span><span class="sxs-lookup"><span data-stu-id="a95a7-118">Setup</span></span>

<span data-ttu-id="a95a7-119">[Windows 내에서 구성 디자이너는](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 다음 네 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="a95a7-120">ApplicationManagement/AllowAllTrustedApps를 "예"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="a95a7-121">[ApplicationManagement/AllowAllTrustedApps를 참조하세요.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)</span><span class="sxs-lookup"><span data-stu-id="a95a7-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="a95a7-122">**UniversalAppInstall**  >  **UserContextAppLicense로** 이동하여 **PackageFamilyName 을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="a95a7-123">[UniversalAppInstall을](/windows/configuration/wcd/wcd-universalappinstall)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a95a7-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="a95a7-124">참고 항목: [UserContextAppLicense.](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)</span><span class="sxs-lookup"><span data-stu-id="a95a7-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="a95a7-125">앱을 이미 설치한 디바이스에서 장치 포털 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="a95a7-126">앱 페이지를 방문하여 PackageRelativeID 줄, "!" 앞에 있는 모든 정보를 살펴봅 **PackageFamilyName 입니다.**</span><span class="sxs-lookup"><span data-stu-id="a95a7-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="a95a7-127">그러면 **ApplicationFile이라는** 새 섹션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="a95a7-128">이 영역을 사용하여 appx 번들을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="a95a7-129">앱을 구입했거나 사용자 고유의 LOB 앱을 빌드한 경우에 따라 라이선스 파일 또는 보안 인증서를 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="a95a7-130">라이선스 파일의 경우: **UniversalAppInstall**  >  **UserContextAppLicence로** 이동하여 라이선스의 위치를 찾아서 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="a95a7-131">보안 파일의 경우 **인증서로** 이동하여 .appx 번들과 함께 설치할 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="a95a7-132">프로젝트를 안전한 위치에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a95a7-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="a95a7-133">그런 다음 **프로비전 패키지로** **내보냅니다.**</span><span class="sxs-lookup"><span data-stu-id="a95a7-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="a95a7-134">참고: [프로비전 패키지를 HoloLens 적용합니다.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="a95a7-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
