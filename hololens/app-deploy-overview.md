---
title: 개요 - 앱 관리
description: 모바일 디바이스 관리, 비즈니스용 Microsoft 스토어 및 패키지 프로비저닝을 사용하여 혼합 현실 앱 관리에 대한 개요를 시작합니다.
keywords: HoloLens, 사용자, 계정, 앱, 애플리케이션 관리,
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635554"
---
# <a name="app-management-overview"></a><span data-ttu-id="61a47-104">앱 관리: 개요</span><span class="sxs-lookup"><span data-stu-id="61a47-104">App Management: Overview</span></span>

<span data-ttu-id="61a47-105">**MDM(모바일 장치 관리), 비즈니스용 Microsoft Store,** **Microsoft Store** 또는 **프로비저닝을** 통해 설치하여 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="61a47-106">MDM(모바일 디바이스 관리)</span><span class="sxs-lookup"><span data-stu-id="61a47-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="61a47-107">MDM 솔루션을 사용하면 IT 의사 결정자와 관리자가 사내, 사업장 앱을 비공개로 자동 설치(푸시)하거나 사용자 그룹을 위해 스토어를 통해 앱을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="61a47-108">HoloLens 디바이스는 [애플리케이션 관리를](app-deploy-intune.md)위해 Microsoft Endpoint Manager(Intune)에서 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="61a47-109">또한 Intune은 회사 포털 다운로드 가능한 환경을 통해 IT 관리 앱에 대한 세밀한 제어를 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="61a47-110">다음 지침은 Intune을 사용하여 애플리케이션을 관리하려는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="61a47-111">애플리케이션 및 디바이스 관리에 Intune을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="61a47-112">MDM(모바일 장치 관리)은 다음을 위해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="61a47-113">MDM 배포 + 회사 포털</span><span class="sxs-lookup"><span data-stu-id="61a47-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="61a47-114">사업장(비공용) 앱</span><span class="sxs-lookup"><span data-stu-id="61a47-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="61a47-115">회사 포털 통해 사용 가능한 애플리케이션 수동 설치</span><span class="sxs-lookup"><span data-stu-id="61a47-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="61a47-116">MDM 정책을 통한 관리자 푸시</span><span class="sxs-lookup"><span data-stu-id="61a47-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="61a47-117">MDM을 통한 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="61a47-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="61a47-118">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="61a47-118">Microsoft Store for Business</span></span>

<span data-ttu-id="61a47-119">[이 비즈니스용 Microsoft Store](app-deploy-store-business.md) 비즈니스의 IT 의사 결정자와 관리자가 무료 및 유료 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="61a47-120">IT 관리자는 하나의 인벤토리에서 Microsoft Store 앱 및 프라이빗 사업장 앱을 관리하고 필요에 따라 라이선스를 할당하고 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="61a47-121">자세한 내용은 [비즈니스용 Microsoft Store 사용하기 위한 필수 구성요약을](/microsoft-store/prerequisites-microsoft-store-for-business)방문하세요.</span><span class="sxs-lookup"><span data-stu-id="61a47-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="61a47-122">비즈니스용 Microsoft Store 적용할 수 있는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="61a47-123">퍼블릭 또는 사업장 앱</span><span class="sxs-lookup"><span data-stu-id="61a47-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="61a47-124">MDM 연결을 통해 필수 애플리케이션 자동 설치</span><span class="sxs-lookup"><span data-stu-id="61a47-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="61a47-125">사용자가 수동으로 앱 다운로드</span><span class="sxs-lookup"><span data-stu-id="61a47-125">User manually downloads apps</span></span>
* <span data-ttu-id="61a47-126">자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="61a47-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="61a47-127">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="61a47-127">Microsoft Store apps</span></span>

<span data-ttu-id="61a47-128">이 Microsoft Store 기업에서 IT 의사 결정자와 관리자에게 퍼블릭 앱을 찾고, 획득하고, 관리하고, 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="61a47-129">이 Microsoft Store 적용할 수 있는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="61a47-130">퍼블릭 앱만</span><span class="sxs-lookup"><span data-stu-id="61a47-130">Public apps only</span></span>
* <span data-ttu-id="61a47-131">사용자가 수동으로 앱 다운로드</span><span class="sxs-lookup"><span data-stu-id="61a47-131">User manually downloads apps</span></span>
* <span data-ttu-id="61a47-132">인터넷에 연결된 경우 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="61a47-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="61a47-133">자세한 내용은 [Holographic Store 앱을 방문하세요.](/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="61a47-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="61a47-134">프로비전 패키지를 통해 설치</span><span class="sxs-lookup"><span data-stu-id="61a47-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="61a47-135">[프로비전 패키지를](app-deploy-provisioning-package.md) 사용하면 사용자 지정 또는 사업장 앱을 설치할 수 있어 IT 담당자와 관리자가 USB를 통해 로컬 디바이스에 앱을 빠르게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="61a47-136">이 설치는 인터넷에 연결하지 않고 모든 ID 유형에 대해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="61a47-137">프로비전 패키지를 통한 설치는 다음을 위해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="61a47-138">사업장/자체 개발(비공용) 앱</span><span class="sxs-lookup"><span data-stu-id="61a47-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="61a47-139">공용 앱(오프라인 설치 관리자를 사용할 수 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="61a47-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="61a47-140">USB 쪽 로드만</span><span class="sxs-lookup"><span data-stu-id="61a47-140">USB side-loading only</span></span>
* <span data-ttu-id="61a47-141">자동 업데이트 없음(프로비전 패키지를 통한 수동 업데이트 필요)</span><span class="sxs-lookup"><span data-stu-id="61a47-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="61a47-142">앱 설치 관리자 통해 HoloLens 2 앱 설치</span><span class="sxs-lookup"><span data-stu-id="61a47-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="61a47-143">[앱 설치 관리자](app-deploy-app-installer.md) 사용하면 로컬 디바이스에 앱을 설치하거나 HoloLens 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유하는 데 간단한 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="61a47-144">개발자 모드를 사용하도록 설정하거나 장치 포털 사용하지 않고도 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="61a47-145">완전히 빌드된 앱을 배포하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="61a47-146">단순히 HoloLens 사용하여 앱을 다른 사용자에게 시연하려는 경우 또는 앱을 배포하려는 경우 이 방법이 쉽게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="61a47-147">앱 설치 관리자 통해 설치하는 것은 다음을 위해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="61a47-148">사업장/자체 개발(비공용) 앱</span><span class="sxs-lookup"><span data-stu-id="61a47-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="61a47-149">사이드로드 전용</span><span class="sxs-lookup"><span data-stu-id="61a47-149">Side-load only</span></span>
* <span data-ttu-id="61a47-150">개발자 모드 또는 디바이스 포털이 필요하지 않음</span><span class="sxs-lookup"><span data-stu-id="61a47-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="61a47-151">최종 사용자가 쉽게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-151">Easy for end user to install</span></span>
