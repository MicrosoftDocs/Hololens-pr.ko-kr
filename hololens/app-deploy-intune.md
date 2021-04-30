---
title: Intune 및 회사 포털
description: Intune, 모바일 장치 관리 및 회사 포털을 사용 하 여 친숙 한 사용자 환경을 설정, 할당 및 만드는 방법을 알아봅니다.
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309730"
---
# <a name="intune--company-portal"></a><span data-ttu-id="0f796-104">Intune & 회사 포털</span><span class="sxs-lookup"><span data-stu-id="0f796-104">Intune & Company Portal</span></span>

<span data-ttu-id="0f796-105">MDM (모바일 장치 관리)을 사용 하면 사용자 고유의 사용자 지정 앱을 [Intune (Microsoft Endpoint Manager](https://docs.microsoft.com/intune/windows-holographic-for-business) )을 통해 사용 하 여 HoloLens 장치에 직접 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="0f796-106">Microsoft Intune은 MDM(모바일 디바이스 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="0f796-107">Intune은 Microsoft의 [Enterprise Mobility + Security(EMS) 제품군](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)에 포함되어 있으므로 사용자는 조직 데이터를 보호하면서 생산성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="0f796-108">Intune에 대해 자세히 알아보려면 [Intune 이란?](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f796-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="0f796-109">설치</span><span class="sxs-lookup"><span data-stu-id="0f796-109">Setup</span></span>

1. <span data-ttu-id="0f796-110">Lob (기간 업무)에 앱을 업로드 하거나 Intune 테 넌 트에 사용자 지정 앱을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="0f796-111">참고 항목: [엔터프라이즈 앱 관리](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="0f796-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="0f796-112">[앱을 그룹에 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="0f796-113">선택한 할당 유형에 따라 앱을 자동으로 배달할 수도 있고 앱을 선택 하는 경우 즉시 끌어올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="0f796-114">Appx 번들을 빌드할 때 배포 하려는 장치의 아키텍처를 포함 하는 것을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="0f796-115">HoloLens 2는 ARM64이 고 HoloLens (첫 번째 Gen)는 x86입니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="0f796-116">혼합 장치 환경을 보유 하려는 경우에는 단일 appx 번들에 둘 다 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="0f796-117">할당 형식</span><span class="sxs-lookup"><span data-stu-id="0f796-117">Assignment types</span></span>

<span data-ttu-id="0f796-118">등록 후 장치에 앱을 자동으로 설치 하려면 해당 그룹에 대해 **필수** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="0f796-119">회사 포털을 통해 등록 된 장치에 앱을 다운로드할 수 있도록 하려면 등록 된 **장치에 대해 사용 가능** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="0f796-120">최종 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="0f796-120">End-User Experience</span></span>

<span data-ttu-id="0f796-121">Intune에서 구성을 설정한 후 최종 사용자가 선택한 앱을 받을 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="0f796-122">앱을 자동으로 다운로드 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0f796-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="0f796-123">테 넌 트를 사용 하 여 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="0f796-124">장치가 등록을 완료 하면 장치에서 앱을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="0f796-125">앱을 즉시 볼 수 없는 경우 **설정**  >  **계정**  >  **회사 또는 학교**  >  *계정* 정보로 이동 하 고 아래로 스크롤하여 설치 된 앱 상태에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="0f796-126">회사 포털을 통해 앱을 가져오는 방법:</span><span class="sxs-lookup"><span data-stu-id="0f796-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="0f796-127">**시작 메뉴** 를 열고 **Microsoft Store** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="0f796-128">**회사 포털** 를 검색 하 고 앱을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="0f796-129">계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-129">Sign into your account.</span></span>
4. <span data-ttu-id="0f796-130">수신 하 고 다운로드 하려는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f796-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="0f796-131">[회사 포털 자동 설치](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 및 [Intune에서 앱 배포 및 관리](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0f796-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
