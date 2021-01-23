---
title: 라이선스 요구 사항
description: 모바일 장치 관리, HoloLens 및 원격 지원에 필요한 모든 라이선스 요구 사항 및 지침을 최신으로 유지하세요.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283969"
---
# <span data-ttu-id="aafeb-103">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aafeb-103">License requirements</span></span>

## <span data-ttu-id="aafeb-104">MDM(모바일 장치 관리) 라이선스 지침</span><span class="sxs-lookup"><span data-stu-id="aafeb-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="aafeb-105">HoloLens 장치 관리 계획을 수립할 때 Azure AD와 MDM이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="aafeb-106">AD(활성 디렉터)는 HoloLens 장치를 관리 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="aafeb-107">Intune 이외의 MDM을 사용하려는 경우 [Azure Active Directory 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="aafeb-108">Intune을 MDM으로 사용할 계획이라면 Intune 라이선스가 포함된 [제품군 목록](https://docs.microsoft.com/intune/fundamentals/licenses)을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="aafeb-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="aafeb-109">Azure AD는 이러한 제품군의 대부분에 포함되어 있다는 점을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="aafeb-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="aafeb-110">시나리오 및 제품에 필요한 라이선스 식별</span><span class="sxs-lookup"><span data-stu-id="aafeb-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="aafeb-111">HoloLens(1세대) 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aafeb-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="aafeb-112">HoloLens(1세대) 장치를 비즈니스용 Windows Holographic으로 업그레이드해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="aafeb-113">(업그레이드해야 하는지 여부를 결정하기 위해 [HoloLens 상업용 기능](holoLens-commercial-features.md#feature-comparison-between-editions)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="aafeb-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="aafeb-114">업그레이드가 필요한 경우 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="aafeb-115">HoloLens Enterprise 라이선스 XML 파일 획득</span><span class="sxs-lookup"><span data-stu-id="aafeb-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="aafeb-116">HoloLens에 XML 파일 적용</span><span class="sxs-lookup"><span data-stu-id="aafeb-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="aafeb-117">[프로비저닝 패키지](hololens-provisioning.md) 또는 [모바일 장치 관리자](https://docs.microsoft.com/intune/configuration/holographic-upgrade)를 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="aafeb-118">원격 지원 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aafeb-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="aafeb-119">[요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) 설명서에서 확인할 수 있는 필수 라이선스 및 장치가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="aafeb-120">원격 지원 라이선스</span><span class="sxs-lookup"><span data-stu-id="aafeb-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="aafeb-121">또는 [원격 지원 평가판을 사용해 보세요](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="aafeb-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="aafeb-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="aafeb-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="aafeb-123">Azure AD(Azure Active Directory) 라이선스</span><span class="sxs-lookup"><span data-stu-id="aafeb-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="aafeb-124">**[이 교차 테넌트 시나리오](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** 를 구현하려면 정보 장벽 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="aafeb-125">정보 장벽 라이선스가 필요한지 여부를 확인하려면 [이 문서](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aafeb-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="aafeb-126">라이선스 요구 사항 가이드</span><span class="sxs-lookup"><span data-stu-id="aafeb-126">Guides License Requirements</span></span>

<span data-ttu-id="aafeb-127">[업데이트된 라이선스 및 장치 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aafeb-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="aafeb-128">Azure AD(Azure Active Directory) 라이선스</span><span class="sxs-lookup"><span data-stu-id="aafeb-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="aafeb-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="aafeb-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="aafeb-130">가이드</span><span class="sxs-lookup"><span data-stu-id="aafeb-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
