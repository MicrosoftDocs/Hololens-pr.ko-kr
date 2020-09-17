---
title: 보안 관리자가 없는 OS
description: 관리자가 없는 OS 및 HoloLens 보안
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
ms.openlocfilehash: ea35012e63f4c0d8868f9604809c1552c3212e72
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016642"
---
# <span data-ttu-id="9687f-104">관리자가 없는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="9687f-104">Admin-less operating system</span></span>

<span data-ttu-id="9687f-105">HoloLens 2는 관리자 그룹에 대한 지원을 사용하지 않고 모든 타사 UWP 응용 프로그램 코드를 AppContainer 샌드박스 내의 표준 사용자로만 실행하도록 제한하여 권한 에스컬레이션에 대한 노출 영역을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="9687f-106">이 코드에는 에스컬레이션되지 않은 사용자를 위해 응용 프로그램에 명시적으로 매니페스트되는 기능으로 보호를 받는 리소스와 모든 AppContainers에 액세스할 수 있는 리소스에게 액세스 권한만 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="9687f-107">이러한 응용 프로그램 기능은 계속해서 세 개의 계층 분류 모델을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="9687f-108">일반 사항</span><span class="sxs-lookup"><span data-stu-id="9687f-108">General</span></span>
  * <span data-ttu-id="9687f-109">Restricted (제한됨)</span><span class="sxs-lookup"><span data-stu-id="9687f-109">Restricted</span></span>
  * <span data-ttu-id="9687f-110">Windows</span><span class="sxs-lookup"><span data-stu-id="9687f-110">Windows</span></span>

<span data-ttu-id="9687f-111">Windows 구성 요소는 또한 시스템 UWP를 통해 AppContainer 샌드박스를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="9687f-112">UWP(유니버설 Windows 플랫폼)에 대한 자세한 정보는 [UWP 설명서](https://docs.microsoft.com/windows/uwp/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9687f-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="9687f-113">또한 더 큰 권한 축소 요구 사항(예: 브라우저 콘텐츠 페이지, 파서)을 포함하는 Windows 구성 요소는 모든 AppContainers에 액세스 가능한 리소스 집합에 대한 액세스를 잘라내는 LPAC(낮은 권한 수준의 AppContainer) 샌드박스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-113">Additionally, Windows components with greater privilege reduction needs (e.g. browser content pages, parsers) use the Less Privileged AppContainer (LPAC) sandbox which cuts off access to the set of resources accessible to all AppContainers.</span></span>

<span data-ttu-id="9687f-114">마지막으로 장치를 테넌트 또는 사용자 관리에 연결하는 것과 같은 특정 장치 차원의 작업 실행은 "장치 소유자"에만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-114">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="9687f-115">장치의 사용자는 다음 단계 중 하나를 통해 이 그룹을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-115">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="9687f-116">장치의 첫 사용자는 항상 소유자로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-116">The first user on the device is always designated an Owner.</span></span> 
    * <span data-ttu-id="9687f-117">이 규칙의 예외는 장치가 AAD에 연결된 경우 연결 작업을 수행한 사용자가 장치 소유자가 되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-117">The exception to this rule is that if the device is AAD joined, the user that performed the join is made device owner.</span></span> <span data-ttu-id="9687f-118">예를 들어 장치가 Autopilot를 통해 AAD에 연결된 경우 장치에 로그인하는 첫 사용자가 장치를 AAD에 연결하지 않아서 장치 소유자가 되지 않는 경우 이에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-118">This is applicable, for example, if a device is AAD joined via Autopilot in which case the first user to sign into the device did not AAD join the device and therefore will not be made a device owner.</span></span> <span data-ttu-id="9687f-119">AAD에 연결한 장치의 장치 소유자가 된 사용자에 대한 자세한 내용은 [‘로컬 관리자 할당’ 설명서](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)(HoloLens에는 관리자가 없기 때문에 ‘로컬 관리자’를 ‘장치 소유자라’라 함)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9687f-119">To understand more about who is made a device owner on an AAD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>
  * <span data-ttu-id="9687f-120">사용자의 수준이 장치의 다른 사용자에 의해 설정 UX에서 소유자로 상승한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-120">When a user is promoted to be an Owner from Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="9687f-121">장치 소유자를 더 이상 가용할 수 없고(예: 퇴사) 장치가 AAD에 연결된 경우 테넌트 관리자가 Azure Portal에서 장치 소유자를 새 사용자로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-121">If the device owner is no longer available (e.g. leaves the company) and the device is AAD joined, the Tenant Admin can change the device owner to a new user in Azure Portal.</span></span>
<span data-ttu-id="9687f-122">Azure AD 테넌트의 전역 관리자는 이전 단계 중 하나를 요구하지 않고도 장치의 소유자로 암시적으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-122">Global Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span> 

<span data-ttu-id="9687f-123">IT 관리자는 [개인 정보](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 정책을 통해 액세스할 수 있는 앱을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9687f-123">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 
