---
title: 개요-앱 관리
description: 앱, 관리, 앱 관리
keywords: HoloLens, 사용자, 계정, 앱, 응용 프로그램 관리
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857956"
---
# <span data-ttu-id="0bb42-104">앱 관리: 개요</span><span class="sxs-lookup"><span data-stu-id="0bb42-104">App Management: Overview</span></span>

<span data-ttu-id="0bb42-105">4 가지 경로, 즉 **MDM (모바일 디바이스 관리)**, Microsoft store **비즈니스**에디션, **microsoft store**또는 **프로 비전**을 통해 설치 하 여 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="0bb42-106">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="0bb42-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="0bb42-107">MDM 솔루션을 사용 하면 IT 의사 결정권자와 관리자가 개인적으로 사내 앱을 자동으로 설치 (푸시) 하거나 사용자 그룹을 위해 스토어를 통해 앱을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="0bb42-108">HoloLens 장치는 [응용 프로그램 관리](app-deploy-intune.md)를 위해 Microsoft Intune (Endpoint Manager 관리자)에서 가장 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="0bb42-109">Intune은 또한 사용자가 회사 포털 다운로드 가능 환경을 통해 관리 되는 앱에 대 한 세부적인 제어 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="0bb42-110">다음 지침은 Intune을 사용 하 여 응용 프로그램을 관리 하려는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="0bb42-111">Microsoft는 응용 프로그램 및 장치 관리에 Intune을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="0bb42-112">다음에 해당 하는 MDM (모바일 장치 관리)이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="0bb42-113">MDM 배포 + 회사 포털</span><span class="sxs-lookup"><span data-stu-id="0bb42-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="0bb42-114">앱 라인 (비 공용)</span><span class="sxs-lookup"><span data-stu-id="0bb42-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="0bb42-115">회사 포털을 통해 사용 가능한 응용 프로그램의 수동 설치</span><span class="sxs-lookup"><span data-stu-id="0bb42-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="0bb42-116">관리자 푸시 MDM 정책</span><span class="sxs-lookup"><span data-stu-id="0bb42-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="0bb42-117">MDM을 통한 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="0bb42-117">Auto update through MDM</span></span>

## <span data-ttu-id="0bb42-118">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0bb42-118">Microsoft Store for Business</span></span>

<span data-ttu-id="0bb42-119">[비즈니스용 Microsoft Store](app-deploy-store-business.md) 는 비즈니스에서 무료 및 유료 앱을 찾고, 얻고, 관리 하 고, 배포 하는 의사 결정권자와 관리자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="0bb42-120">IT 관리자는 Microsoft Store 앱 및 전용 LOB(기간 업무) 앱을 하나의 인벤토리에서 관리하고 필요에 따라 라이선스를 할당하고 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="0bb42-121">자세한 내용은 [Microsoft 비즈니스용 스토어를 사용 하기 위한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bb42-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="0bb42-122">비즈니스용 Microsoft Store는 다음에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="0bb42-123">비즈니스 앱 공개 또는 줄</span><span class="sxs-lookup"><span data-stu-id="0bb42-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="0bb42-124">MDM 연결을 통해 필수 응용 프로그램의 자동 설치</span><span class="sxs-lookup"><span data-stu-id="0bb42-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="0bb42-125">사용자가 앱을 수동으로 다운로드</span><span class="sxs-lookup"><span data-stu-id="0bb42-125">User manually downloads apps</span></span>
* <span data-ttu-id="0bb42-126">자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="0bb42-126">Auto Update</span></span>

## <span data-ttu-id="0bb42-127">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="0bb42-127">Microsoft Store apps</span></span>

<span data-ttu-id="0bb42-128">Microsoft Store는 비즈니스에서 공용 앱을 찾고, 가져오고, 관리 하 고, 배포 하는 의사 결정권자와 관리자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="0bb42-129">이 Microsoft Store는 다음에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="0bb42-130">공용 앱만</span><span class="sxs-lookup"><span data-stu-id="0bb42-130">Public apps only</span></span>
* <span data-ttu-id="0bb42-131">사용자가 앱을 수동으로 다운로드</span><span class="sxs-lookup"><span data-stu-id="0bb42-131">User manually downloads apps</span></span>
* <span data-ttu-id="0bb42-132">인터넷에 연결 된 경우 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="0bb42-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="0bb42-133">자세한 내용은 [홀로그램 스토어 앱](https://docs.microsoft.com/hololens/holographic-store-apps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bb42-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="0bb42-134">프로비저닝 패키지를 통해 설치</span><span class="sxs-lookup"><span data-stu-id="0bb42-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="0bb42-135">[배포 패키지](app-deploy-provisioning-package.md) 를 사용 하 여 사용자 지정 또는 lob 앱을 설치할 수 있으며, IT 전문가와 관리자는 USB를 통해 로컬 장치에 앱을 빠르게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="0bb42-136">이 작업은 인터넷에 연결 되지 않고 모든 id 유형에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="0bb42-137">다음과 같은 경우에는 프로비저닝 패키지를 통해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb42-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="0bb42-138">앱 라인 (비 공용)</span><span class="sxs-lookup"><span data-stu-id="0bb42-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="0bb42-139">공용 앱 (오프 라인 설치 관리자를 사용할 수 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="0bb42-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="0bb42-140">USB 쪽만 로드</span><span class="sxs-lookup"><span data-stu-id="0bb42-140">USB side-load only</span></span>
* <span data-ttu-id="0bb42-141">자동 업데이트 없음 (프로비저닝 패키지를 통해 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="0bb42-141">No auto update (requires manual updates via Provisioning Package)</span></span>
