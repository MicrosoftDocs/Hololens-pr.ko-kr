---
title: 라이선스 요구 사항
description: ''
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
ms.openlocfilehash: 18a583f407b19c5b86870a49b8182d45f46a45f5
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857806"
---
# <span data-ttu-id="a21ba-102">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a21ba-102">License requirements</span></span>

## <span data-ttu-id="a21ba-103">MDM(모바일 장치 관리) 라이선스 지침</span><span class="sxs-lookup"><span data-stu-id="a21ba-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="a21ba-104">HoloLens 장치 관리 계획을 수립할 때 Azure AD와 MDM이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="a21ba-105">AD(활성 디렉터)는 HoloLens 장치를 관리 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="a21ba-106">Intune 이외의 MDM을 사용하려는 경우 [Azure Active Directory 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="a21ba-107">Intune을 MDM으로 사용하는 경우 [다음](https://docs.microsoft.com/intune/fundamentals/licenses)은 Intune 라이선스가 포함된 제품군의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="a21ba-108">Azure AD는 이러한 제품군의 대부분에 포함되어 있다는 점을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="a21ba-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="a21ba-109">시나리오 및 제품에 필요한 라이선스 식별</span><span class="sxs-lookup"><span data-stu-id="a21ba-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="a21ba-110">HoloLens 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a21ba-110">HoloLens Licenses Requirements</span></span>

<span data-ttu-id="a21ba-111">HoloLens 1 Gen 장치를 비즈니스용 Windows Holographic으로 업그레이드해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-111">You may need to upgrade your HoloLens 1st Gen Device to Windows Holographic for Business.</span></span> <span data-ttu-id="a21ba-112">(업그레이드해야 하는지 여부를 결정하기 위해 [HoloLens 상업용 기능](holoLens-commercial-features.md#feature-comparison-between-editions)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="a21ba-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="a21ba-113">업그레이드가 필요한 경우 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="a21ba-114">HoloLens Enterprise 라이선스 XML 파일 획득</span><span class="sxs-lookup"><span data-stu-id="a21ba-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="a21ba-115">HoloLens에 XML 파일 적용</span><span class="sxs-lookup"><span data-stu-id="a21ba-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="a21ba-116">[프로비저닝 패키지](hololens-provisioning.md) 또는 [모바일 장치 관리자](https://docs.microsoft.com/intune/configuration/holographic-upgrade)를 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="a21ba-117">원격 지원 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a21ba-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="a21ba-118">필수 라이선싱 및 장치를 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="a21ba-119">업데이트된 라이선스 및 제품 요구 사항은 [여기](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="a21ba-120">원격 지원 라이선스</span><span class="sxs-lookup"><span data-stu-id="a21ba-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [<span data-ttu-id="a21ba-121">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="a21ba-121">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="a21ba-122">Azure AD(Azure Active Directory) 라이선스</span><span class="sxs-lookup"><span data-stu-id="a21ba-122">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="a21ba-123">**[이 교차 테넌트 시나리오](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** 를 구현하려면 정보 장벽 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-123">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="a21ba-124">정보 장벽 라이선스가 필요한지 여부를 확인하려면 [이 문서](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a21ba-124">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="a21ba-125">라이선스 요구 사항 가이드</span><span class="sxs-lookup"><span data-stu-id="a21ba-125">Guides License Requirements</span></span>

<span data-ttu-id="a21ba-126">업데이트된 라이선스 및 장치 요구 사항은 [여기](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21ba-126">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="a21ba-127">Azure AD(Azure Active Directory) 라이선스</span><span class="sxs-lookup"><span data-stu-id="a21ba-127">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="a21ba-128">Power BI</span><span class="sxs-lookup"><span data-stu-id="a21ba-128">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="a21ba-129">가이드</span><span class="sxs-lookup"><span data-stu-id="a21ba-129">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
