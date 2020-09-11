---
title: 보안 엔지니어링
description: 보안 엔지니어링
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, Hololens, 보안, 엔지니어링
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cecc556841033ee394f36915f4cae8839dad08df
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009536"
---
# <span data-ttu-id="1781b-104">보안 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="1781b-104">Security engineering</span></span>

<span data-ttu-id="1781b-105">Microsoft에는 회사의 엔지니어링 프로토콜을 최적화하고 규정 준수를 처리하며 고객 신뢰를 보장하는데 소요되는 여러 리소스와 팀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781b-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="1781b-106">Microsoft의 보안 엔지니어링 개발 방법에 대한 자세한 내용은 SDL([보안 개발 수명 주기](https://www.microsoft.com/securityengineering/sdl))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1781b-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="1781b-107">따라서 HoloLens 2를 사용하면 고객은 [Microsoft의 개인정보 처리방침](https://privacy.microsoft.com/)에서 더 자세히 탐색할 수 있는 데이터를 수집하고 사용하는 방법과 이유를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781b-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="1781b-108">[MSRC(Microsoft Security Response Center)](https://www.microsoft.com/msrc)는 Defender 커뮤니티의 일부이며 효율적인 취약점 보고 환경 및 보안 버그에 대한 효과적인 분류 및 응답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1781b-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <span data-ttu-id="1781b-109">업데이트 및 패치</span><span class="sxs-lookup"><span data-stu-id="1781b-109">Updates and patches</span></span>

<span data-ttu-id="1781b-110">보안 업데이트 및 패치는 매월 두 번째 화요일에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="1781b-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="1781b-111">보고된 취약점에 대한 다음 단계를 평가하기 위해 Microsoft에서 사용하는 기준을 이해하려면 Microsoft 보안 대응 센터의 [보안 서비스 기준 페이지](https://www.microsoft.com/msrc/windows-security-servicing-criteria)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1781b-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="1781b-112">MDM을 통해 HoloLens 2 업데이트를 관리하는 방법에 대한 지침은 [HoloLens 업데이트 관리](https://docs.microsoft.com/hololens/hololens-updates)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1781b-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates).</span></span> <span data-ttu-id="1781b-113">HoloLens 2용 운영 체제 업데이트 흐름은 Windows 10에서와 일치합니다. 1년에 두 번의 업데이트, 봄에 한번, 그리고 가을에 한번 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781b-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="1781b-114">OS 업데이트 중 장치를 안전하게 보호하는 방법에 대한 자세한 내용은 [상태 분판 및 격리](security-state-separation-isolation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1781b-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="1781b-115">IT 관리자는 [정책 CSP - 업데이트](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)에서 업데이트 정책에 대한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781b-115">IT admins can learn more about update policy at [Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update).</span></span> 
