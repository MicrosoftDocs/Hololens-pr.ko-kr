---
title: 상업적 환경에서 HoloLens 설정
description: 엔터프라이즈 환경에서 HoloLens를 배포 하 고 관리 하는 방법에 대해 자세히 알아보세요.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865567"
---
# <span data-ttu-id="cd4cf-103">상용 환경에서 HoloLens 배포</span><span class="sxs-lookup"><span data-stu-id="cd4cf-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="cd4cf-104">상업용 설정의 배율에서 HoloLens를 배포 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="cd4cf-105">이 문서에서는 상업적 환경에서 HoloLens 장치를 배포 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="cd4cf-106">이 가이드에서는 HoloLens에 대 한 기초적인 지식이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="cd4cf-107">[시작 가이드](hololens1-setup.md) 의 지침에 따라 처음으로 HoloLens를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="cd4cf-108">이 문서는 또한 해킹을 회사 네트워크에서 안전 하 게 사용 하는 보안 팀이 평가한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="cd4cf-109">[HoloLens 보안](security-overview.md)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="cd4cf-110">HoloLens (첫번째 Gen) 보안의 경우 [이 FAQ](hololens1-faq-security.md)를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="cd4cf-111">배포 단계 개요</span><span class="sxs-lookup"><span data-stu-id="cd4cf-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="cd4cf-112">필요한 기능 결정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="cd4cf-113">필요한 라이선스 결정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="cd4cf-114">[HoloLens에 맞게 네트워크를 구성](hololens-commercial-infrastructure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="cd4cf-115">이 섹션에서는 방화벽에 허용 해야 하는 대역폭 요구 사항, URL 및 포트를 제공 합니다. Azure AD 지침; MDM (모바일 디바이스 관리) 지침 앱 배포/관리 지침 및 인증서 지침.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="cd4cf-116">) [배포 패키지를 사용 하 여 HoloLens 구성](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="cd4cf-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="cd4cf-117">장치 등록</span><span class="sxs-lookup"><span data-stu-id="cd4cf-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="cd4cf-118">HoloLens에 대한 링 기반 업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="cd4cf-119">HoloLens에서 BitLocker 디바이스 암호화 사용</span><span class="sxs-lookup"><span data-stu-id="cd4cf-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="cd4cf-120">1단계.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-120">Step 1.</span></span> <span data-ttu-id="cd4cf-121">필요 사항 결정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-121">Determine what you need</span></span>

<span data-ttu-id="cd4cf-122">환경에서 HoloLens를 배포 하기 전에 먼저 필요한 기능, 앱 및 id 유형을 결정 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="cd4cf-123">또한 보안 팀이 회사 네트워크에서 HoloLens 사용을 승인 했는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="cd4cf-124">추가 보안에 대 한 자세한 내용은 [HoloLens2 보안](security-overview.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="cd4cf-125">Id 유형</span><span class="sxs-lookup"><span data-stu-id="cd4cf-125">Type of Identity</span></span>

<span data-ttu-id="cd4cf-126">장치에 로그인 하는 데 사용 되는 id 유형을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="cd4cf-127">**로컬 계정:** 이 계정은 디바이스 (예: windows PC의 로컬 관리자 계정)에 대해 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="cd4cf-128">이렇게 하면 1 개의 사용자만이 장치에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="cd4cf-129">**MSA:** 개인 계정 (예: outlook, hotmail, gmail, yahoo 등) 이렇게 하면 1 개의 사용자만이 장치에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="cd4cf-130">Azure **AD (Active Directory) 계정:** Azure AD에서 만든 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="cd4cf-131">이렇게 하면 회사에 HoloLens 장치를 관리할 수 있는 기능이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="cd4cf-132">이렇게 하면 여러 사용자가 HoloLens 1 Gen 상업용 Suite/HoloLens 2 장치에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="cd4cf-133">Id 형식에 대 한 자세한 내용은 [HoloLens id](hololens-identity.md) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="cd4cf-134">기능 유형</span><span class="sxs-lookup"><span data-stu-id="cd4cf-134">Type of Features</span></span>

<span data-ttu-id="cd4cf-135">기능 요구 사항에 따라 필요한 HoloLens가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="cd4cf-136">일반적으로 고객 환경에 배포 되어 표시 되는 인기 기능 중 하나는 키오스크 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="cd4cf-137">HoloLens 주요 기능 목록과이를 지 원하는 HoloLens 버전을 [여기](hololens-commercial-features.md)에서 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="cd4cf-138">키오스크 모드란?</span><span class="sxs-lookup"><span data-stu-id="cd4cf-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="cd4cf-139">키오스크 모드는 사용자가 액세스할 수 있는 앱을 제한할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="cd4cf-140">즉, 사용자가 특정 앱에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="cd4cf-141">어떤 키오스크 모드를 필요로 하나요?</span><span class="sxs-lookup"><span data-stu-id="cd4cf-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="cd4cf-142">키오스크 모드에는 단일 앱과 다중 앱의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="cd4cf-143">단일 앱 키오스크 모드에서는 사용자가 앱 하나에만 액세스할 수 있으며, 다중 앱 키오스크 모드에서는 사용자가 여러 개의 지정 된 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="cd4cf-144">회사에 적합 한 키오스크 모드를 결정 하려면 다음 두 가지 질문에 대 한 답변을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="cd4cf-145">다른 사용자가 다양 한 경험/제한을 필요로 하나요?</span><span class="sxs-lookup"><span data-stu-id="cd4cf-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="cd4cf-146">다음 예제를 참조 하세요. 사용자 A는 원격 지원에만 액세스할 수 있는 현장 서비스 엔지니어입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="cd4cf-147">사용자 B는 안내선에 대 한 액세스만 필요로 하는 trainee.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="cd4cf-148">예를 들어, 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="cd4cf-149">Azure AD 계정-장치에 로그인 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="cd4cf-150">**다중 앱** 키오스크 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="cd4cf-151">아니요, 질문을 두 번 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="cd4cf-152">다중 앱 환경이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="cd4cf-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="cd4cf-153">예를 들어 **다중 앱** 키오스크 모드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="cd4cf-154">질문 1 및 2에 대 한 대답이 모두 아니요 이면 **단일 앱** 키오스크 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="cd4cf-155">키오스크 모드를 구성 하는 방법:</span><span class="sxs-lookup"><span data-stu-id="cd4cf-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="cd4cf-156">HoloLens에 대 한 키오스크 모드를 배포 하는 두 가지 주요 방법 ([프로비저닝 패키지](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 및 [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk))이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="cd4cf-157">이러한 옵션은 문서 뒷부분에서 설명 합니다. 그러나 위의 링크를 사용 하 여이 문서의 각 섹션으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="cd4cf-158">앱 및 앱 관련 시나리오</span><span class="sxs-lookup"><span data-stu-id="cd4cf-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="cd4cf-159">이 문서에 있는 대부분의 단계는 다음 앱에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="cd4cf-160">앱</span><span class="sxs-lookup"><span data-stu-id="cd4cf-160">App</span></span> | <span data-ttu-id="cd4cf-161">앱 관련 시나리오</span><span class="sxs-lookup"><span data-stu-id="cd4cf-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="cd4cf-162">원격 지원</span><span class="sxs-lookup"><span data-stu-id="cd4cf-162">Remote Assist</span></span> | [<span data-ttu-id="cd4cf-163">교차 테 넌 트 통신</span><span class="sxs-lookup"><span data-stu-id="cd4cf-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="cd4cf-164">가이드</span><span class="sxs-lookup"><span data-stu-id="cd4cf-164">Guides</span></span>  | *<span data-ttu-id="cd4cf-165">개봉박두</span><span class="sxs-lookup"><span data-stu-id="cd4cf-165">Coming Soon</span></span>* |
|<span data-ttu-id="cd4cf-166">사용자 지정 앱</span><span class="sxs-lookup"><span data-stu-id="cd4cf-166">Custom Apps</span></span> | *<span data-ttu-id="cd4cf-167">개봉박두</span><span class="sxs-lookup"><span data-stu-id="cd4cf-167">Coming Soon</span></span>* |

### <span data-ttu-id="cd4cf-168">등록 방법 결정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="cd4cf-169">배포 패키지의 보안 토큰을 사용 하 여 일괄 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="cd4cf-170">전문가: 가장 자동화 된 접근 방법입니다. </span><span class="sxs-lookup"><span data-stu-id="cd4cf-170">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="cd4cf-171">단점: 초기 서버 쪽 설정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="cd4cf-172">사용자 로그인에 대 한 자동 등록</span><span class="sxs-lookup"><span data-stu-id="cd4cf-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="cd4cf-173">전문가: 가장 쉬운 방법</span><span class="sxs-lookup"><span data-stu-id="cd4cf-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="cd4cf-174">단점: 프로 비전 패키지를 적용 한 후에 사용자가 설정을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="cd4cf-175">_권장 하지 않음_ -설정 후 수동으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="cd4cf-176">전문가: 설정 후 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="cd4cf-177">단점: 대부분의 수동 접근 방식 및 디바이스는 수동으로 등록할 때까지 중앙에서 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="cd4cf-178">자세한 내용은 여기를 참조 [하세요](hololens-enroll-mdm.md) .</span><span class="sxs-lookup"><span data-stu-id="cd4cf-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="cd4cf-179">배포 패키지를 만들어야 하는지 결정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="cd4cf-180">HoloLens 장치 (프로비저닝 패키지 및 MDMs)를 구성 하는 데는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="cd4cf-181">MDM을 사용 하 여 HoloLens 장치를 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="cd4cf-182">하지만 배포 패키지를 사용 하는 것이 더 나은 경우도 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="cd4cf-183">OOBE (부재 중 경험)를 건너뛰기 위해 HoloLens를 구성 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="cd4cf-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="cd4cf-184">복잡 한 네트워크에서 인증서를 배포 하는 데 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="cd4cf-185">대부분의 경우에는 MDM을 사용 하 여 인증서를 배포할 수 있습니다 (복잡 한 환경에도 해당).</span><span class="sxs-lookup"><span data-stu-id="cd4cf-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="cd4cf-186">그러나 일부 시나리오에서는 인증서를 제공 하 여 프로비저닝 패키지를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="cd4cf-187">프로비저닝 패키지에 적용할 수 있는 일부 HoloLens 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="cd4cf-188">장치에 인증서 적용</span><span class="sxs-lookup"><span data-stu-id="cd4cf-188">Apply certificates to the device</span></span>
- <span data-ttu-id="cd4cf-189">Wi-Fi 연결 설정</span><span class="sxs-lookup"><span data-stu-id="cd4cf-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="cd4cf-190">언어 및 로케일과 같이 자주 묻는 질문에 대한 사전 구성</span><span class="sxs-lookup"><span data-stu-id="cd4cf-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="cd4cf-191">(HoloLens 2) 모바일 장치 관리에서 일괄 등록</span><span class="sxs-lookup"><span data-stu-id="cd4cf-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="cd4cf-192">(HoloLens v1) 비즈니스용 Windows Holographic을 사용하도록 설정하는 키 적용</span><span class="sxs-lookup"><span data-stu-id="cd4cf-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="cd4cf-193">프로비저닝 패키지를 사용 하기로 결정 한 경우 [이 가이드](hololens-provisioning.md)를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="cd4cf-194">지원 받기</span><span class="sxs-lookup"><span data-stu-id="cd4cf-194">Get support</span></span>

<span data-ttu-id="cd4cf-195">Microsoft 지원 사이트를 통해 지원을 받으세요.</span><span class="sxs-lookup"><span data-stu-id="cd4cf-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="cd4cf-196">파일 지원 요청</span><span class="sxs-lookup"><span data-stu-id="cd4cf-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
