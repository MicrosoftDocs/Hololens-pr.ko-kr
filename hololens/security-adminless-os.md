---
title: 관리자 없는 운영 체제 보안
description: HoloLens 혼합 현실 장치의 관리자 없는 운영 체제, 장치 소유자 및 보안에 대해 자세히 알아보세요.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, HoloLens, 관리자가 없는, 관리자가 없는, 운영 체제, 관리자가 없는 운영 체제, 관리자 os, 관리자가 없는 os, HoloLens 2, HoloLens2 보안,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440339"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="52560-104">관리자가 없는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="52560-104">Admin-less operating system</span></span>

<span data-ttu-id="52560-105">HoloLens 2는 관리자 그룹에 대한 지원을 사용하지 않고 모든 타사 UWP 응용 프로그램 코드를 AppContainer 샌드박스 내의 표준 사용자로만 실행하도록 제한하여 권한 에스컬레이션에 대한 노출 영역을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="52560-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="52560-106">이 코드에는 에스컬레이션되지 않은 사용자를 위해 응용 프로그램에 명시적으로 매니페스트되는 기능으로 보호를 받는 리소스와 모든 AppContainers에 액세스할 수 있는 리소스에게 액세스 권한만 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="52560-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="52560-107">이러한 응용 프로그램 기능은 계속해서 세 개의 계층 분류 모델을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="52560-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="52560-108">일반 사항</span><span class="sxs-lookup"><span data-stu-id="52560-108">General</span></span>
  * <span data-ttu-id="52560-109">Restricted (제한됨)</span><span class="sxs-lookup"><span data-stu-id="52560-109">Restricted</span></span>
  * <span data-ttu-id="52560-110">Windows</span><span class="sxs-lookup"><span data-stu-id="52560-110">Windows</span></span>

<span data-ttu-id="52560-111">Windows 구성 요소는 또한 시스템 UWP를 통해 AppContainer 샌드박스를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52560-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="52560-112">UWP(유니버설 Windows 플랫폼)에 대한 자세한 정보는 [UWP 설명서](https://docs.microsoft.com/windows/uwp/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52560-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="52560-113">또한 더 큰 권한 축소 요구 사항(예: 브라우저 콘텐츠 페이지 또는 파서)을 포함하는 Windows 구성 요소는 모든 AppContainers에 액세스 가능한 리소스 집합에 대한 액세스를 잘라내는 LPAC(낮은 권한 수준의 AppContainer) 샌드박스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52560-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="52560-114">장치 소유자</span><span class="sxs-lookup"><span data-stu-id="52560-114">Device owner</span></span>

<span data-ttu-id="52560-115">마지막으로 장치를 테넌트 또는 사용자 관리에 연결하는 것과 같은 특정 장치 차원의 작업 실행은 "장치 소유자"에만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52560-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="52560-116">장치의 사용자는 다음 단계 중 하나를 통해 이 그룹을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="52560-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="52560-117">장치의 첫 사용자는 항상 소유자로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52560-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="52560-118">Azure AD 사용자의 경우 이 규칙의 예외는 장치가 비 실제 사용자를 사용하는 Autopilot 또는 대량 Azure AD 등록을 통해 가입된 Azure AD인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="52560-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="52560-119">이 경우 장치에 로그인한 첫 번째 AAD 사용자는 해당 사용자에게 Azure Portal에 할당된 "전역 관리자"또는 "장치 관리자" 역할이 없으면 자동으로 장치 소유자가 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52560-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="52560-120">자세한 내용은 아래 메모를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52560-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="52560-121">사용자의 수준이 장치의 다른 사용자에 의해 설정 UX에서 소유자로 상승한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="52560-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="52560-122">장치 소유자를 더 이상 가용할 수 없고(퇴사) 장치가 Azure AD에 연결된 경우 테넌트 관리자가 Azure Portal에서 장치 소유자를 새 사용자로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52560-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="52560-123">Azure AD 테넌트의 전역 관리자 및 장치 관리자는 이전 단계 중 하나를 요구하지 않고도 장치의 소유자로 암시적으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="52560-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="52560-124">IT 관리자는 [개인 정보](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 정책을 통해 액세스할 수 있는 앱을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52560-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="52560-125">Azure AD에 연결한 장치의 장치 소유자가 된 사용자에 대한 자세한 내용은 [‘로컬 관리자 할당’ 설명서](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)(HoloLens에는 관리자가 없기 때문에 ‘로컬 관리자’를 ‘장치 소유자라’라 함)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52560-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>