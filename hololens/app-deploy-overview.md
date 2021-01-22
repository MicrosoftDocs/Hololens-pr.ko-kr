---
title: 개요 - 앱 관리
description: 모바일 장치 관리, 비즈니스용 Microsoft Store 및 프로비저닝 패키지를 사용하여 혼합 현실 앱 관리에 대한 개요를 시작하세요.
keywords: HoloLens, 사용자, 계정, 앱, 응용 프로그램 관리,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283709"
---
# <span data-ttu-id="37ee1-104">앱 관리: 개요</span><span class="sxs-lookup"><span data-stu-id="37ee1-104">App Management: Overview</span></span>

<span data-ttu-id="37ee1-105">**MDM(모바일**장치 관리), 비즈니스용 **Microsoft Store, Microsoft Store의** \*\*\*\* 네 가지 경로에 앱을 배포하거나 프로비저닝을 통해 앱을 설치할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="37ee1-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="37ee1-106">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="37ee1-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="37ee1-107">MDM 솔루션을 사용하면 IT 의사 결정권자 및 관리자가 사용자 그룹을 위해 스토어를 통해 사내, 업무용 앱을 개인적으로 자동 설치(푸시)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="37ee1-108">HoloLens 장치는 응용 프로그램 관리를 위해 Microsoft Endpoint Manager(Intune)와 [가장 잘 작동합니다.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="37ee1-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="37ee1-109">또한 Intune은 사용자가 회사 포털에서 다운로드 가능한 환경을 통해 IT 관리 앱에 대한 세분화된 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="37ee1-110">다음 지침은 Intune을 사용하여 응용 프로그램을 관리하려는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="37ee1-111">응용 프로그램 및 장치 관리에 Intune을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="37ee1-112">MDM(모바일 장치 관리)은 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="37ee1-113">MDM 배포 + 회사 포털</span><span class="sxs-lookup"><span data-stu-id="37ee1-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="37ee1-114">업무(비공용) 앱</span><span class="sxs-lookup"><span data-stu-id="37ee1-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="37ee1-115">회사 포털을 통해 사용 가능한 응용 프로그램 수동 설치</span><span class="sxs-lookup"><span data-stu-id="37ee1-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="37ee1-116">MDM 정책을 통한 관리자 푸시</span><span class="sxs-lookup"><span data-stu-id="37ee1-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="37ee1-117">MDM을 통한 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="37ee1-117">Auto update through MDM</span></span>

## <span data-ttu-id="37ee1-118">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="37ee1-118">Microsoft Store for Business</span></span>

<span data-ttu-id="37ee1-119">비즈니스용 [Microsoft Store는](app-deploy-store-business.md) 비즈니스의 IT 의사 결정권자 및 관리자가 무료 및 유료 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="37ee1-120">IT 관리자는 Microsoft Store 앱 및 개인 기간 업무(기간 업무) 앱을 하나의 인벤토리에서 관리할 수 있으며, 필요한 경우 라이선스를 할당하고 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="37ee1-121">자세한 내용은 비즈니스용 Microsoft Store를 사용하기 위한 사전 준비 [사이트를 방문하세요.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="37ee1-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="37ee1-122">비즈니스용 Microsoft Store는 다음에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="37ee1-123">공용 또는 비즈니스용 앱</span><span class="sxs-lookup"><span data-stu-id="37ee1-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="37ee1-124">MDM 연결로 필수 응용 프로그램 자동 설치</span><span class="sxs-lookup"><span data-stu-id="37ee1-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="37ee1-125">사용자가 수동으로 앱을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-125">User manually downloads apps</span></span>
* <span data-ttu-id="37ee1-126">자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="37ee1-126">Auto Update</span></span>

## <span data-ttu-id="37ee1-127">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="37ee1-127">Microsoft Store apps</span></span>

<span data-ttu-id="37ee1-128">Microsoft Store는 비즈니스의 IT 의사 결정권자 및 관리자가 공용 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="37ee1-129">이 Microsoft Store는 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="37ee1-130">공용 앱만</span><span class="sxs-lookup"><span data-stu-id="37ee1-130">Public apps only</span></span>
* <span data-ttu-id="37ee1-131">사용자가 수동으로 앱을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-131">User manually downloads apps</span></span>
* <span data-ttu-id="37ee1-132">인터넷에 연결된 경우 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="37ee1-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="37ee1-133">자세한 내용은 [Holographic Store 앱을 방문하세요.](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="37ee1-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="37ee1-134">프로비저닝 패키지를 통해 설치</span><span class="sxs-lookup"><span data-stu-id="37ee1-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="37ee1-135">[프로비저닝 패키지를](app-deploy-provisioning-package.md) 사용하면 사용자 지정 또는 업무용 앱을 설치할 수 있으며, IT 프로비저닝 및 관리자는 USB를 통해 로컬 디바이스에 앱을 빠르게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="37ee1-136">이 설치는 인터넷에 연결하지 않고 ID 유형에 대해 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="37ee1-137">프로비저닝 패키지를 통해 설치하는 것은 다음에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="37ee1-138">업무(LINE OF BUSINESS) / 자체 개발(비공용) 앱</span><span class="sxs-lookup"><span data-stu-id="37ee1-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="37ee1-139">공용 앱(오프라인 설치 관리자를 사용할 수 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="37ee1-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="37ee1-140">USB 테스트용 로드만</span><span class="sxs-lookup"><span data-stu-id="37ee1-140">USB side-loading only</span></span>
* <span data-ttu-id="37ee1-141">자동 업데이트 없음(프로비저닝 패키지를 통한 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="37ee1-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="37ee1-142">앱 설치 관리자를 통해 HoloLens 2에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="37ee1-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="37ee1-143">앱 [설치](app-deploy-app-installer.md) 관리자 사용자는 로컬 장치에 앱을 설치하거나 HoloLens의 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유하는 간단한 환경을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="37ee1-144">개발자 모드를 사용하도록 설정하거나 디바이스 포털을 사용하지 않고도 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="37ee1-145">이는 완전히 구축된 앱을 배포하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="37ee1-146">HoloLens를 사용하여 다른 사용자에게 앱을 데모하거나 앱을 쉽게 배포할지와 관계없이 이 방법을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="37ee1-147">앱 설치 관리자를 통해 설치하는 것은 다음에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="37ee1-148">업무(LINE OF BUSINESS) / 자체 개발(비공용) 앱</span><span class="sxs-lookup"><span data-stu-id="37ee1-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="37ee1-149">테스트용 로드만</span><span class="sxs-lookup"><span data-stu-id="37ee1-149">Side-load only</span></span>
* <span data-ttu-id="37ee1-150">개발자 모드 또는 디바이스 포털이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="37ee1-151">최종 사용자가 쉽게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ee1-151">Easy for end user to install</span></span>
