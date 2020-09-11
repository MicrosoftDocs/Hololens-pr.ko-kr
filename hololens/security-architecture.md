---
title: HoloLens 보안 아키텍처
description: 보안 아키텍처
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, Hololens, Hololens 2, Hololens2 보안, 보안 개요, 보안 아키텍처, 아키텍처, Hololens 2 아키텍처
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f8434ffe2442f270d6360018bea4b64064168d0c
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009556"
---
# <span data-ttu-id="9b9a2-104">보안 개요 및 아키텍처</span><span class="sxs-lookup"><span data-stu-id="9b9a2-104">Security overview and architecture</span></span>

<span data-ttu-id="9b9a2-105">HoloLens 2 보안 아키텍처는 레거시 보안 문제를 해결하기 위해 처음부터 설계하고 엔지니어링했으며, 공격 영역을 최소화했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="9b9a2-106">이 새롭고 혁신적인 아키텍처는 운영 체제를 잠재적인 위협과 취약성으로부터 보호할 수 있는 메커니즘과 함께 안전한 저장소 위치와 고급 보안 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="9b9a2-107">HoloLens 2는 하드웨어, 소프트웨어, 네트워킹 및 서비스를 결합하여 사용자에게 최적의 환경을 제공하는 동시에 종단간 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="9b9a2-108">HoloLens 2를 사용하면 대부분의 보안 기능이 자동으로 켜지며, 운영 체제를 올바르게 설정하고 구성하는 데 필요한 노력을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="9b9a2-109">Windows HoloLens 2 및 운영 체제 아키텍처는 다음과 같은 혁신적인 보안 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="9b9a2-110">**상태 구분 및 격리**: 이 새로운 아키텍처는 코어 운영 체제가 신뢰할 수 있는 상태로 부팅하는 데 필요한 것과 같은 Hololens 2 운영 체제의 중요한 부분을 변경으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="9b9a2-111">격리 기술은 샌드박스 영역에서 신뢰할 수 없는 앱을 제한하 여 시스템 보안에 영향을 주지 않도록 하는데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="9b9a2-112">전체 운영 체제는 안전한 섹션으로 분할되고 각 섹션은 다양 한 보안 기술의 조합에 의해 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="9b9a2-113">**데이터 보호**: 사용자의 장치를 분실하거나 도난당한 경우 HoloLens 2에서 데이터의 BitLocker 암호화를 사용하여 권한이 없는 응용 프로그램에서 민감한 정보를 읽지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="9b9a2-114">**암호를 사용하지 않는 운영 체제**: 이전의 암호 기반 운영 체제는 사용자를 피싱 위험에 실수로 노출하고 계정을 위험에 노출되도록 하는 경우가 많았습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="9b9a2-115">Windows Holographic for Business는 MSA 및 AAD 로그인에 비밀번호를 사용하지 않으며 Windows Hello™ 및 FIDO2 로그인에서 사용자 ID 보호가 강화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-115">Windows Holographic for Business eliminates the use of passwords for MSA and AAD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9b9a2-116">FIDO2 지원을 받으려면 장치가 19041 이상의 빌드에서 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="9b9a2-117">**네트워크 보안**: HoloLens 2는 향상된 프로토콜과 기본 설정을 통해 사용자에게 증가된 네트워크 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
