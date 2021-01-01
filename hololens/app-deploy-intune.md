---
title: Intune 및 회사 포털
description: Intune, 앱 관리, 앱, 회사 포털, 포털
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
ms.openlocfilehash: 7871d5113b6803a3f702bf8d64f16fabc1c5a9bb
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252659"
---
# <span data-ttu-id="6f9b3-104">인투네 & 컴퍼니 포털</span><span class="sxs-lookup"><span data-stu-id="6f9b3-104">Intune & Company Portal</span></span>

<span data-ttu-id="6f9b3-105">MDM(모바일 장치 관리)을 사용하면 Microsoft [Endpoint Manager(Intune)를](https://docs.microsoft.com/intune/windows-holographic-for-business) 통해 사용자 지정 앱을 사용하여 HoloLens 장치에 직접 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="6f9b3-106">Microsoft Intune은 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 두는 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="6f9b3-107">Intune은 [Microsoft의 EMS(Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)제품군에 포함되어 있으며 조직 데이터를 보호하면서 생산성을 유지할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="6f9b3-108">Intune에 대한 자세한 내용은 [Intune을 읽어 읽습니다.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="6f9b3-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="6f9b3-109">Setup</span><span class="sxs-lookup"><span data-stu-id="6f9b3-109">Setup</span></span>

1. <span data-ttu-id="6f9b3-110">앱을 비즈니스용 라인에 업로드하거나 사용자 지정 앱을 Intune 테넌트에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="6f9b3-111">엔터프라이즈 앱 [관리도 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="6f9b3-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="6f9b3-112">[그룹에 앱을 할당합니다.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="6f9b3-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="6f9b3-113">선택한 할당 유형에 따라 앱을 자동으로 전달하거나, 선택한 앱이 있는 경우 앱을 쉽게 끌어서 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="6f9b3-114">appx 번들을 구축할 때 배포하는 디바이스의 아키텍처를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="6f9b3-115">HoloLens 2는 ARM64, HoloLens(1세대)는 x86입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="6f9b3-116">장치 환경이 혼합된 환경을 계획하는 경우 단일 appx 번들에 둘 다 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="6f9b3-117">배정 유형</span><span class="sxs-lookup"><span data-stu-id="6f9b3-117">Assignment types</span></span>

<span data-ttu-id="6f9b3-118">등록 후 장치에 앱을 자동으로 설치하려면 해당 그룹에 대해 \*\*\*\* 필수를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="6f9b3-119">회사 포털을 통해 등록된 디바이스에 앱을 다운로드할 수 있도록 설정하려면 등록된 장치에 대해 사용 **가능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f9b3-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="6f9b3-120">End-User 환경</span><span class="sxs-lookup"><span data-stu-id="6f9b3-120">End-User Experience</span></span>

<span data-ttu-id="6f9b3-121">Intune에서 구성을 설정한 후 최종 사용자가 선택한 앱을 받을 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="6f9b3-122">다음 단계에 따라 앱을 자동으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="6f9b3-123">테넌트에 디바이스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="6f9b3-124">디바이스가 등록을 완료하면 디바이스에서 앱을 수신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="6f9b3-125">즉시 앱이 표시되지 않는 경우 설정 \*\*\*\* 계정 작업 또는 학교 계정 정보로 이동한 다음 아래로 스크롤하여 설치된 앱 상태에 대한  >  \*\*\*\*  >  \*\*\*\*  >  \*\* 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="6f9b3-126">회사 포털을 통해 앱에 액세스하는 방법:</span><span class="sxs-lookup"><span data-stu-id="6f9b3-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="6f9b3-127">시작 **메뉴를 열고** **Microsoft Store를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f9b3-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="6f9b3-128">회사 **포털을 검색하고** 앱을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="6f9b3-129">계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-129">Sign into your account.</span></span>
4. <span data-ttu-id="6f9b3-130">수신할 앱을 선택하고 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9b3-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="6f9b3-131">회사 포털 [자동](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 설치 및 [Intune에서](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)앱 배포 및 관리에 대해 자세히 알아보고</span><span class="sxs-lookup"><span data-stu-id="6f9b3-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
