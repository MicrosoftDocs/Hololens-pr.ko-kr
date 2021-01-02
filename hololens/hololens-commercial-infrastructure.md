---
title: HoloLens 인프라 가이드라인
description: HoloLens 장치 인프라 가이드라인
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a67aaa5df4c74531b5bed88abaa266b00de5c406
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253165"
---
# <span data-ttu-id="b5eb4-103">HoloLens 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="b5eb4-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="b5eb4-104">문서의 이 부분에는 다음과 같은 사용자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="b5eb4-105">Proxy/방화벽을 변경할 수 있는 권한이 있는 네트워크 관리자</span><span class="sxs-lookup"><span data-stu-id="b5eb4-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="b5eb4-106">Azure Active Directory 관리자</span><span class="sxs-lookup"><span data-stu-id="b5eb4-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="b5eb4-107">모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="b5eb4-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="b5eb4-108">인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5eb4-108">Infrastructure Requirements</span></span>

<span data-ttu-id="b5eb4-109">HoloLens는 핵심적으로 Azure와 통합된 Windows 모바일 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="b5eb4-110">무선 네트워크 가용성(wi-fi) 및 Microsoft 서비스에 액세스할 수 있는 상업적 환경에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="b5eb4-111">중요한 클라우드 서비스에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-111">Critical cloud services include:</span></span>

- <span data-ttu-id="b5eb4-112">Azure AD(Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="b5eb4-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="b5eb4-113">Windows 업데이트(WU)</span><span class="sxs-lookup"><span data-stu-id="b5eb4-113">Windows Update (WU)</span></span>

<span data-ttu-id="b5eb4-114">상업적 고객이 HoloLens 장치를 대규모로 관리하려면 엔터프라이즈 이동성 관리(EMM) 또는 모바일 장치 관리(MDM) 인프라가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="b5eb4-115">이 가이드에서는 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune)을 예제로 사용하지만 Microsoft 정책을 완벽하게 지원하는 모든 공급자는 HoloLens를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="b5eb4-116">모바일 장치 관리 공급자에게 HoloLens 2를 지원하는지 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="b5eb4-117">HoloLens는 제한된 클라우드 연결 해제 환경을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="b5eb4-118">무선 네트워크 EAP 지원</span><span class="sxs-lookup"><span data-stu-id="b5eb4-118">Wireless network EAP support</span></span>

- <span data-ttu-id="b5eb4-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b5eb4-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="b5eb4-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="b5eb4-120">PEAP-TLS</span></span>
- <span data-ttu-id="b5eb4-121">TLS</span><span class="sxs-lookup"><span data-stu-id="b5eb4-121">TLS</span></span>
- <span data-ttu-id="b5eb4-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="b5eb4-122">TTLS-CHAP</span></span>
- <span data-ttu-id="b5eb4-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b5eb4-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="b5eb4-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b5eb4-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="b5eb4-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="b5eb4-125">TTLS-PAP</span></span>
- <span data-ttu-id="b5eb4-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="b5eb4-126">TTLS-TLS</span></span>

### <span data-ttu-id="b5eb4-127">HoloLens 관련 네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5eb4-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="b5eb4-128">이 끝점 [목록](hololens-offline.md)이 네트워크 방화벽에서 허용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="b5eb4-129">그러면 HoloLens가 제대로 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="b5eb4-130">원격 지원 특정 네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5eb4-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="b5eb4-131">원격 지원에서 최적의 성능을 내도록 권장되는 대역폭은 1.5 Mbps입니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="b5eb4-132">자세한 네트워크 요구 사항과 추가 정보는 [여기](https://docs.microsoft.com/MicrosoftTeams/prepare-network)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-132">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="b5eb4-133">(네트워크 속도가 1.5Mbps 이상인 네트워크가 아닌 경우에도 Remote Assist는 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="b5eb4-134">그러나 품질이 저하될 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b5eb4-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="b5eb4-135">이러한 포트와 URL이 네트워크 방화벽에서 허용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-135">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="b5eb4-136">이를 통해 Microsoft Teams가 실행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-136">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="b5eb4-137">최신 목록은[여기](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-137">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="b5eb4-138">[원격 지원의 특정 네트워크 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-138">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="b5eb4-139">[Microsoft Teams에 맞게 조직의 네트워크를 준비](https://docs.microsoft.com/MicrosoftTeams/prepare-network)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-139">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="b5eb4-140">특정 네트워크 요구 사항 가이드</span><span class="sxs-lookup"><span data-stu-id="b5eb4-140">Guides Specific Network Requirements</span></span>

<span data-ttu-id="b5eb4-141">가이드는 앱을 다운로드하고 사용하기 위해 네트워크 액세스만을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-141">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="b5eb4-142">Azure Active Directory 지침</span><span class="sxs-lookup"><span data-stu-id="b5eb4-142">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="b5eb4-143">이 단계는 회사에서 HoloLens 관리를 계획하는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-143">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="b5eb4-144">Azure AD 라이선스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-144">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="b5eb4-145">자세한 내용은 [HoloLens 라이선스 요구 사항](hololens-licenses-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-145">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="b5eb4-146">자동 등록을 사용하려는 경우 [Azure AD 등록을 구성](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-146">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="b5eb4-147">회사의 사용자가 Azure Active Directory (Azure AD)에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-147">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="b5eb4-148">사용자 추가 지침은 [여기](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-148">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="b5eb4-149">유사한 라이선스가 필요한 사용자를 같은 그룹에 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-149">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="b5eb4-150">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="b5eb4-150">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="b5eb4-151">그룹에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="b5eb4-151">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="b5eb4-152">회사의 사용자(또는 사용자 그룹)에게 필수 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-152">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="b5eb4-153">라이선스 할당에 대한 지시사항은 [여기](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-153">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="b5eb4-154">사용자가 HoloLens/모바일 장치를 사용자에게 등록해야 하는 경우에만이 단계를 수행하세요(세 가지 옵션이 있음). 이 단계는 회사의 사용자(또는 사용자 그룹)가 장치를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-154">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="b5eb4-155">**옵션 1:** 모든 사용자에 게 Azure AD에 장치를 연결할 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-155">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="b5eb4-156">**관리자로 Azure Portal에 로그인** > \**Azure Active Directory \*\* > **장치** > **장치 설정** >
**설정된 사용자는 다음을 위해 장치를 Azure AD에 연결할 수 있음\*모두***</span><span class="sxs-lookup"><span data-stu-id="b5eb4-156">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="b5eb4-157">**옵션 2 :** 선택한 사용자/그룹에게 장치를 Azure AD에 연결할 수 있는 권한 부여 **관리자로 Azure Portal에 로그인** > **Azure Active Directory** > **장치** > **장치 설정** >
\**설정된 사용자는 다음을 위해 장치를 Azure AD에 연결할 수 있음*선택한\*\*\*
![Azure AD 연결 장치의 구성을 보여주는 이미지</span><span class="sxs-lookup"><span data-stu-id="b5eb4-157">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="b5eb4-158">**옵션 3:** 모든 사용자가 자신의 장치를 도메인에 연결하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-158">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="b5eb4-159">즉, 모든 장치를 수동으로 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-159">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="b5eb4-160">모바일 장치 관리자 지침</span><span class="sxs-lookup"><span data-stu-id="b5eb4-160">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="b5eb4-161">지속적인 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="b5eb4-161">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="b5eb4-162">이 단계는 회사에서 HoloLens 관리를 계획하는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-162">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="b5eb4-163">지속적인 디바이스 관리는 모바일 디바이스 관리 인프라에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-163">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="b5eb4-164">일반적인 기능은 거의 같지만 사용자 인터페이스는 크게 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-164">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="b5eb4-165">[CSP(구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)를 사용하면 네트워크의 디바이스에 대한 관리 설정을 만들고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-165">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="b5eb4-166">HoloLens 에 대한 CSP 목록은 [여기](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-166">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="b5eb4-167">[준수 정책](https://docs.microsoft.com/intune/device-compliance-get-started)은 디바이스가 회사 인프라에서 준수를 위해 충족해야 하는 규칙 및 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-167">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="b5eb4-168">이 정책을 조건부 액세스와 함께 사용하여 비준수 장치의 회사 리소스에 대한 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-168">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="b5eb4-169">예를 들어, Bitlocker를 사용하도록 설정해야 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-169">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="b5eb4-170">[준수 정책 생성](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="b5eb4-170">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="b5eb4-171">조건부 액세스는 모바일 장치 및 모바일 애플리케이션이 회사 리소스에 액세스하는 것을 허용/거부합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-171">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="b5eb4-172">도움이 될 만한 두 가지 문서는 [CA 배포 계획 ](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 및 [모범 사례](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)입니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-172">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="b5eb4-173">[이 문서](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)에서는 HoloLens용 Intune 관리 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-173">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="b5eb4-174">장치 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="b5eb4-174">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="b5eb4-175">업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="b5eb4-175">Manage updates</span></span>

<span data-ttu-id="b5eb4-176">Intune에는 HoloLens 2 및 HoloLens v1(Holographic for Business 포함)을 포함하여 Windows 10 장치용 업데이트 링이라는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-176">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="b5eb4-177">업데이트 링에는 업데이트 설치 방법 및 시기를 결정하는 설정 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-177">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="b5eb4-178">예를 들어 업데이트를 설치하는 유지 관리 창을 만들거나 업데이트를 설치한 후 다시 시작 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-178">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="b5eb4-179">업데이트할 준비가 될 때까지 업데이트를 무기한 일시 중지하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-179">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="b5eb4-180">[Intune으로 업데이트 링 구성](https://docs.microsoft.com/intune/windows-update-for-business-configure)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-180">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="b5eb4-181">응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="b5eb4-181">Application management</span></span>

<span data-ttu-id="b5eb4-182">다음을 통해 HoloLens 응용 프로그램을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-182">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="b5eb4-183">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b5eb4-183">Microsoft Store</span></span>  
  <span data-ttu-id="b5eb4-184">Microsoft 스토어는 HoloLens에서 응용 프로그램을 배포하고 사용하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-184">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="b5eb4-185">주요 HoloLens 응용 프로그램이 이미 상점에서 사용 가능하고, 사용자가 [직접 게시](https://docs.microsoft.com/windows/uwp/publish/)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-185">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="b5eb4-186">상점의 모든 응용 프로그램은 모든 사람이 공개적으로 사용할 수 있지만, 허용되지 않는 경우 비즈니스용 Microsoft Store를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-186">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="b5eb4-187">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b5eb4-187">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="b5eb4-188">비즈니스 및 교육용 Microsoft Store는 기업 환경을 위한 사용자 지정 스토어입니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-188">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="b5eb4-189">Windows 10 및 HoloLens에 내장된 Microsoft Store를 사용하여 조직을 위한 앱을 찾고 수집하고 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-189">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="b5eb4-190">또한 전 세계가 아닌 사용자의 상업적 환경에만 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-190">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="b5eb4-191">Intune 또는 다른 모바일 장치 관리 솔루션을 통한 응용 프로그램 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="b5eb4-191">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="b5eb4-192">Intune을 비롯한 대부분의 모바일 장치 관리 솔루션은 일련의 비즈니스 응용 프로그램을 등록된 장치 집합에 직접 배포할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-192">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="b5eb4-193">[Intune 앱 설치](https://docs.microsoft.com/intune/apps-deploy)에 대한 이 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-193">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="b5eb4-194">_권장되지 않는_ 장치 포털</span><span class="sxs-lookup"><span data-stu-id="b5eb4-194">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="b5eb4-195">Windows 장치 포털을 사용하여 HoloLens에 직접 응용 프로그램을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-195">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="b5eb4-196">장치 포털을 사용하려면 개발자 모드를 활성화해야 하므로 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-196">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="b5eb4-197">[HoloLens에 앱을 설치하는 방법](https://docs.microsoft.com/hololens/hololens-install-apps)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-197">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="b5eb4-198">인증서</span><span class="sxs-lookup"><span data-stu-id="b5eb4-198">Certificates</span></span>

<span data-ttu-id="b5eb4-199">MDM 공급자를 통해 인증서를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-199">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="b5eb4-200">회사에 인증서가 필요한 경우 Intune에서 PKCS, PFX 및 SCEP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-200">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="b5eb4-201">어떤 인증서가 회사에 적합한지를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-201">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="b5eb4-202">사용자에게 가장 적합한 인증서를 확인하려면 [여기](https://docs.microsoft.com/intune/protect/certificates-configure)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-202">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="b5eb4-203">HoloLens 인증에 인증서를 사용하려는 경우 PFX 또는 SCEP가 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-203">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="b5eb4-204">SCEP 단계는 [여기](https://docs.microsoft.com/intune/protect/certificates-profile-scep)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-204">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="b5eb4-205">Holographics for Business Commercial 제품군으로 업그레이드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5eb4-205">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="b5eb4-206">Windows Holographics for Business(상업용 제품군)는 HoloLens 1세대 장치에만 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-206">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="b5eb4-207">HoloLens 2 장치에는 프로필이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-207">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="b5eb4-208">상업용 제품군으로 업그레이드하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/intune/configuration/holographic-upgrade)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-208">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="b5eb4-209">Microsoft Intune을 사용하여 키오스크 모드를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5eb4-209">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="b5eb4-210">Microsoft Store와 Intune 동기화([여기](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span><span class="sxs-lookup"><span data-stu-id="b5eb4-210">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="b5eb4-211">앱 설정 확인</span><span class="sxs-lookup"><span data-stu-id="b5eb4-211">Check your app settings</span></span>
    1. <span data-ttu-id="b5eb4-212">Microsoft Store Business 계정에 로그인</span><span class="sxs-lookup"><span data-stu-id="b5eb4-212">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="b5eb4-213">관리 > 제품 및 서비스 > 앱 및 소프트웨어 > 동기화하려는 앱 선택 > 개인 저장소 가용성 > "모두" 또는 "특정 그룹" 선택</span><span class="sxs-lookup"><span data-stu-id="b5eb4-213">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="b5eb4-214">원하는 앱이 표시되지 않을 경우 스토어에서 앱을 검색하여 앱을 "가져와야" 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-214">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="b5eb4-215">**오른쪽 상단에서 "검색" 막대를 클릭하고 앱 이름을 입력한 다음 해당 앱을 클릭하고 "가져오기"를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b5eb4-215">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="b5eb4-216">**Intune > 클라이언트 앱 > 앱**에 앱이 표시되지 않는다면 다시 [앱을 동기화](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-216">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="b5eb4-217">키오스크 모드용 디바이스 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="b5eb4-217">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="b5eb4-218">"Azure AD"를 "사용자 로그온 유형"으로 사용하여 다른 사용자가 다른 키오스크 모드 환경을 갖도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-218">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="b5eb4-219">그러나 이 옵션은 다중 앱 키오스크 모드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-219">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="b5eb4-220">다중 앱 키오스크 모드는 여러 앱뿐만 아니라 하나의 앱에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-220">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Intune에서 키오스크 모드 구성을 보여주는 이미지](images/aad-kioskmode.png)

<span data-ttu-id="b5eb4-222">다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-222">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="b5eb4-223">MDM 서비스에서 키오스크를 설정하기 위해 사용자 지정 설정 및 전체 XML 구성을 사용해야 하는 경우 [여기](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)에서 추가 지침을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-223">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="b5eb4-224">인증서 및 인증</span><span class="sxs-lookup"><span data-stu-id="b5eb4-224">Certificates and Authentication</span></span>

<span data-ttu-id="b5eb4-225">MDM을 통해 인증서를 배포할 수 있습니다([MDM 섹션](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)의 "인증서" 참조).</span><span class="sxs-lookup"><span data-stu-id="b5eb4-225">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="b5eb4-226">패키지 프로비저닝을 통해 HoloLens에 인증서를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-226">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="b5eb4-227">추가 정보는 [HoloLens 프로비저닝](hololens-provisioning.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-227">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="b5eb4-228">추가 Intune 빠른 링크</span><span class="sxs-lookup"><span data-stu-id="b5eb4-228">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="b5eb4-229">[프로필 생성:](https://docs.microsoft.com/intune/configuration/device-profile-create) 프로필을 사용하면 조직의 기기에 푸시될 설정을 추가하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5eb4-229">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

