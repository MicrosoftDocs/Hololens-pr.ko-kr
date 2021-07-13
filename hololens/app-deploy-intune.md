---
title: Intune 및 회사 포털
description: Intune, 모바일 디바이스 관리 및 회사 포털을 사용하여 익숙한 사용자 환경을 설정, 할당 및 만드는 방법을 알아봅니다.
keywords: intune, 앱 관리, 앱, 회사 포털, 포털, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635503"
---
# <a name="intune--company-portal"></a><span data-ttu-id="d4d67-104">Intune 및 회사 포털</span><span class="sxs-lookup"><span data-stu-id="d4d67-104">Intune & Company Portal</span></span>

<span data-ttu-id="d4d67-105">MDM(모바일 장치 관리)을 사용하면 [Microsoft Endpoint Manager(Intune)를](/intune/windows-holographic-for-business) 통해 사용자 지정 앱을 사용하여 HoloLens 디바이스에 직접 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="d4d67-106">Microsoft Intune은 MDM(모바일 디바이스 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="d4d67-107">Intune은 Microsoft의 [Enterprise Mobility + Security(EMS) 제품군](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)에 포함되어 있으므로 사용자는 조직 데이터를 보호하면서 생산성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="d4d67-108">Intune에 대한 자세한 내용은 [Intune이란?을](/mem/intune/fundamentals/what-is-intune)읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="d4d67-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="d4d67-109">설치 프로그램</span><span class="sxs-lookup"><span data-stu-id="d4d67-109">Setup</span></span>

1. <span data-ttu-id="d4d67-110">앱을 사업 분야에 업로드 사용자 지정 앱을 Intune 테넌트로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="d4d67-111">앱 [관리 Enterprise](/windows/client-management/mdm/enterprise-app-management)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4d67-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="d4d67-112">[그룹에 앱을 할당합니다.](/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="d4d67-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="d4d67-113">선택한 할당 유형에 따라 앱이 자동으로 배달되거나 앱 선택 항목이 있는 경우 즉시 끌어올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="d4d67-114">appx 번들을 빌드할 때 배포할 디바이스의 아키텍처를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="d4d67-115">HoloLens 2 ARM64이고 HoloLens(1세대)는 x86입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="d4d67-116">혼합 디바이스 환경을 사용하려는 경우 둘 다 단일 appx 번들에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="d4d67-117">할당 형식</span><span class="sxs-lookup"><span data-stu-id="d4d67-117">Assignment types</span></span>

<span data-ttu-id="d4d67-118">등록 후 디바이스에 앱을 자동으로 설치하려면 해당 그룹에 **대해 필수를** 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="d4d67-119">회사 포털을 통해 등록된 디바이스에 앱을 다운로드할 수 있도록 하려면 **등록된 디바이스에 사용 가능을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="d4d67-120">최종 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="d4d67-120">End-User Experience</span></span>

<span data-ttu-id="d4d67-121">Intune에서 구성을 설정하면 최종 사용자가 선택한 앱을 받을 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="d4d67-122">다음 단계에 따라 앱을 자동으로 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="d4d67-123">테넌트에서 디바이스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="d4d67-124">디바이스가 등록을 완료하면 디바이스에서 앱을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="d4d67-125">앱이 즉시 표시되지 않으면 **설정**  >    >  **계정회사 또는 학교**  >  *계정* 정보로 이동하고 아래로 스크롤하여 설치된 앱 상태에 대한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="d4d67-126">회사 포털 통해 앱에 액세스하는 방법:</span><span class="sxs-lookup"><span data-stu-id="d4d67-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="d4d67-127">시작 **메뉴를** 열고 **Microsoft Store** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="d4d67-128">**회사 포털** 검색하고 앱을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="d4d67-129">계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-129">Sign into your account.</span></span>
4. <span data-ttu-id="d4d67-130">수신하고 다운로드하려는 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="d4d67-131">[Intune에서](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps) [회사 포털 자동 설치](/mem/intune/apps/company-portal-app) 및 앱 배포 및 관리에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d4d67-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
