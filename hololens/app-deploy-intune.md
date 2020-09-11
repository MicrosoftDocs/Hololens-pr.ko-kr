---
title: Intune 및 회사 포털
description: intune, app management, 앱, 회사 포털, 포털
keywords: intune, app management, 앱, 회사 포털, 포털, hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009466"
---
# <span data-ttu-id="602f3-104">인투네 & 컴퍼니 포털</span><span class="sxs-lookup"><span data-stu-id="602f3-104">Intune & Company Portal</span></span>

<span data-ttu-id="602f3-105">MDM (모바일 디바이스 관리)을 사용 하 여 사용자 지정 앱을 [Intune (Microsoft Endpoint Manager)](https://docs.microsoft.com/intune/windows-holographic-for-business) 을 통해 직접 HoloLens 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="602f3-106">Microsoft Intune은 MDM (모바일 디바이스 관리) 및 MAM (모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="602f3-107">Intune은 Microsoft의[엔터프라이즈 Mobility + Security (EMS) 제품군](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)에 포함 되어 있으며, 사용자는 조직 데이터를 보호 하면서 생산성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-107">Intune is included in Microsoft's[Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="602f3-108">Intune에 대 한 자세한 내용은 [intune의 기능](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="602f3-108">To learn more about Intune, please read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="602f3-109">Setup</span><span class="sxs-lookup"><span data-stu-id="602f3-109">Setup</span></span>

1. <span data-ttu-id="602f3-110">비즈니스 라인에 앱을 업로드 하거나 사용자 지정 앱을 Intune 테 넌 트에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="602f3-111">[엔터프라이즈 앱 관리](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)참고 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="602f3-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="602f3-112">[앱을 그룹에 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="602f3-113">선택한 할당 유형을 기반으로 앱을 선택 하는 경우 앱이 자동으로 제공 되도록 하거나 바로 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="602f3-114">Appx 번들을 빌드할 때에는 배포 하려는 디바이스에 대 한 아키텍처 포함을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="602f3-115">HoloLens 2는 ARM64, HoloLens (첫번째 Gen)는 x86입니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="602f3-116">혼합 디바이스 환경을 보유 하려는 경우 단일 appx 번들에 둘 다 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="602f3-117">과제 유형</span><span class="sxs-lookup"><span data-stu-id="602f3-117">Assignment types</span></span>

<span data-ttu-id="602f3-118">등록 후 앱을 장치에 자동으로 설치 하려는 경우 해당 그룹에 대해 **필수** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="602f3-119">회사 포털을 통해 등록 된 앱을 다운로드할 수 있도록 하려면 **등록 된 장치에서 사용 가능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="602f3-120">최종 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="602f3-120">End User Experience</span></span>

<span data-ttu-id="602f3-121">Intune에서 구성을 설정한 후 최종 사용자가 선택한 앱을 받을 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="602f3-122">앱을 자동으로 가져오려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="602f3-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="602f3-123">테 넌 트를 사용 하 여 디바이스를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="602f3-124">장치가 등록을 완료 하면 장치에서 앱을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="602f3-125">앱이 즉시 표시 되지 않는 경우 **설정**  >  **계정**  >  **회사 또는 학교**  >  **계정** 정보로 이동 하 고 아래로 스크롤하여 설치 된 앱 상태에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="602f3-126">회사 포털을 통해 앱에 액세스 하는 방법:</span><span class="sxs-lookup"><span data-stu-id="602f3-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="602f3-127">**시작 메뉴** 를 열고 **Microsoft Store**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="602f3-128">**회사 포털** 을 검색 하 고 앱을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="602f3-129">계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-129">Sign into your account.</span></span>
4. <span data-ttu-id="602f3-130">수신 하려는 앱을 선택 하 고 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="602f3-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="602f3-131">[회사 포털 자동 설치](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 및 [Intune에서 앱 배포 및 관리](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="602f3-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
