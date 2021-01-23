---
title: HoloLens 인프라 가이드라인
description: 무선 네트워크 지원, 원격 지원 및 모바일 장치 관리를 포함하여 HoloLens 장치에 대한 인프라 지침에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283389"
---
# <span data-ttu-id="353e0-103">HoloLens 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="353e0-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="353e0-104">문서의 이 부분에는 다음과 같은 사용자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="353e0-105">Proxy/방화벽을 변경할 수 있는 권한이 있는 네트워크 관리자</span><span class="sxs-lookup"><span data-stu-id="353e0-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="353e0-106">Azure Active Directory 관리자</span><span class="sxs-lookup"><span data-stu-id="353e0-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="353e0-107">모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="353e0-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="353e0-108">인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="353e0-108">Infrastructure Requirements</span></span>

<span data-ttu-id="353e0-109">HoloLens는 핵심적으로 Azure와 통합된 Windows 모바일 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="353e0-110">무선 네트워크 가용성(wi-fi) 및 Microsoft 서비스에 액세스할 수 있는 상업적 환경에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="353e0-111">중요한 클라우드 서비스에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-111">Critical cloud services include:</span></span>

- <span data-ttu-id="353e0-112">Azure AD(Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="353e0-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="353e0-113">Windows 업데이트(WU)</span><span class="sxs-lookup"><span data-stu-id="353e0-113">Windows Update (WU)</span></span>

<span data-ttu-id="353e0-114">상업적 고객이 HoloLens 장치를 대규모로 관리하려면 엔터프라이즈 이동성 관리(EMM) 또는 모바일 장치 관리(MDM) 인프라가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="353e0-115">이 가이드에서는 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune)을 예제로 사용하지만 Microsoft 정책을 완벽하게 지원하는 모든 공급자는 HoloLens를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="353e0-116">모바일 장치 관리 공급자에게 HoloLens 2를 지원하는지 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="353e0-117">HoloLens는 제한된 클라우드 연결 해제 환경을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="353e0-118">무선 네트워크 EAP 지원</span><span class="sxs-lookup"><span data-stu-id="353e0-118">Wireless network EAP support</span></span>

- <span data-ttu-id="353e0-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="353e0-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="353e0-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="353e0-120">PEAP-TLS</span></span>
- <span data-ttu-id="353e0-121">TLS</span><span class="sxs-lookup"><span data-stu-id="353e0-121">TLS</span></span>
- <span data-ttu-id="353e0-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="353e0-122">TTLS-CHAP</span></span>
- <span data-ttu-id="353e0-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="353e0-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="353e0-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="353e0-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="353e0-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="353e0-125">TTLS-PAP</span></span>
- <span data-ttu-id="353e0-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="353e0-126">TTLS-TLS</span></span>

### <span data-ttu-id="353e0-127">HoloLens 관련 네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="353e0-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="353e0-128">이 끝점 [목록](hololens-offline.md)이 네트워크 방화벽에서 허용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="353e0-129">그러면 HoloLens가 제대로 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="353e0-130">원격 지원 특정 네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="353e0-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="353e0-131">원격 지원에서 최적의 성능을 내도록 권장되는 대역폭은 1.5 Mbps입니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="353e0-132">추가 정보는 [자세한 네트워크 요구 사항](https://docs.microsoft.com/MicrosoftTeams/prepare-network)에서 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-132">See the [detailed network requirements](https://docs.microsoft.com/MicrosoftTeams/prepare-network) for additional information.</span></span>
**<span data-ttu-id="353e0-133">(네트워크 속도가 1.5Mbps 이상인 네트워크가 아닌 경우에도 Remote Assist는 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="353e0-134">그러나 품질이 저하될 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="353e0-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="353e0-135">Microsoft Teams의 기능이 작동하도록 네트워크 방화벽에서 이러한 포트 및 URL이 허용되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-135">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="353e0-136">[최신 포트 목록](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)을 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-136">Stay up to date with the [latest list of ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="353e0-137">[원격 지원의 특정 네트워크 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)을 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-137">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="353e0-138">[Microsoft Teams에 맞게 조직의 네트워크를 준비](https://docs.microsoft.com/MicrosoftTeams/prepare-network)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-138">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="353e0-139">특정 네트워크 요구 사항 가이드</span><span class="sxs-lookup"><span data-stu-id="353e0-139">Guides Specific Network Requirements</span></span>

<span data-ttu-id="353e0-140">가이드는 앱을 다운로드하고 사용하기 위해 네트워크 액세스만을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-140">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="353e0-141">Azure Active Directory 지침</span><span class="sxs-lookup"><span data-stu-id="353e0-141">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="353e0-142">이 단계는 회사에서 HoloLens 관리를 계획하는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-142">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="353e0-143">Azure AD 라이선스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-143">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="353e0-144">자세한 내용은 [HoloLens 라이선스 요구 사항](hololens-licenses-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-144">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="353e0-145">자동 등록을 사용하려는 경우 [Azure AD 등록을 구성](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-145">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="353e0-146">회사의 사용자가 Azure Active Directory(Azure AD)에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-146">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="353e0-147">다음 [지침](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)에서 사용자 추가 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-147">See the following [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="353e0-148">유사한 라이선스가 필요한 사용자를 같은 그룹에 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-148">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="353e0-149">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="353e0-149">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="353e0-150">그룹에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="353e0-150">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="353e0-151">회사의 사용자(또는 사용자 그룹)에게 필수 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-151">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="353e0-152">라이선스를 할당해야 하는 경우 다음 [지침](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-152">If you need to assign licenses, follow these [directions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="353e0-153">사용자가 HoloLens/모바일 장치를 사용자에게 등록해야 하는 경우에만이 단계를 수행하세요(세 가지 옵션이 있음). 이 단계는 회사의 사용자(또는 사용자 그룹)가 장치를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-153">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="353e0-154">**옵션 1:** 모든 사용자에 게 Azure AD에 장치를 연결할 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-154">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="353e0-155">**관리자로 Azure Portal에 로그인** > \**Azure Active Directory \*\* > **장치** > **장치 설정** >
**설정된 사용자는 다음을 위해 장치를 Azure AD에 연결할 수 있음\*모두***</span><span class="sxs-lookup"><span data-stu-id="353e0-155">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="353e0-156">**옵션 2 :** 선택한 사용자/그룹에게 장치를 Azure AD에 연결할 수 있는 권한 부여 **관리자로 Azure Portal에 로그인** > **Azure Active Directory** > **장치** > **장치 설정** >
\**설정된 사용자는 다음을 위해 장치를 Azure AD에 연결할 수 있음*선택한\*\*\*
![Azure AD 연결 장치의 구성을 보여주는 이미지</span><span class="sxs-lookup"><span data-stu-id="353e0-156">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="353e0-157">**옵션 3:** 모든 사용자가 자신의 장치를 도메인에 연결하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-157">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="353e0-158">즉, 모든 장치를 수동으로 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-158">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="353e0-159">모바일 장치 관리자 지침</span><span class="sxs-lookup"><span data-stu-id="353e0-159">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="353e0-160">지속적인 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="353e0-160">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="353e0-161">이 단계는 회사에서 HoloLens 관리를 계획하는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-161">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="353e0-162">지속적인 디바이스 관리는 모바일 디바이스 관리 인프라에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-162">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="353e0-163">일반적인 기능은 거의 같지만 사용자 인터페이스는 크게 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-163">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="353e0-164">[CSP(구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)를 사용하면 네트워크 장치의 관리 설정을 만들고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-164">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="353e0-165">[HoloLens CSP 목록](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)을 참고자료로 보세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-165">See the [list of HoloLens CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="353e0-166">[준수 정책](https://docs.microsoft.com/intune/device-compliance-get-started)은 회사 인프라에서 장치가 반드시 준수해야 하는 규칙 및 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-166">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="353e0-167">이 정책을 조건부 액세스와 함께 사용하여 비준수 장치의 회사 리소스에 대한 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-167">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="353e0-168">예를 들어, Bitlocker를 사용하도록 설정해야 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-168">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="353e0-169">[준수 정책 생성](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="353e0-169">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="353e0-170">조건부 액세스는 모바일 장치 및 모바일 애플리케이션이 회사 리소스에 액세스하는 것을 허용/거부합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-170">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="353e0-171">도움이 될 만한 두 가지 문서는 [CA 배포 계획 ](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 및 [모범 사례](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)입니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-171">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="353e0-172">[이 문서](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)에서는 HoloLens용 Intune 관리 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-172">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="353e0-173">장치 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="353e0-173">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="353e0-174">업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="353e0-174">Manage updates</span></span>

<span data-ttu-id="353e0-175">Intune에는 HoloLens 2 및 HoloLens v1(Holographic for Business 포함)을 포함하여 Windows 10 장치용 업데이트 링이라는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-175">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="353e0-176">업데이트 링에는 업데이트 설치 방법 및 시기를 결정하는 설정 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-176">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="353e0-177">예를 들어 업데이트를 설치하는 유지 관리 창을 만들거나 업데이트를 설치한 후 다시 시작 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-177">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="353e0-178">업데이트할 준비가 될 때까지 업데이트를 무기한 일시 중지하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-178">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="353e0-179">[Intune으로 업데이트 링 구성](https://docs.microsoft.com/intune/windows-update-for-business-configure)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-179">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="353e0-180">응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="353e0-180">Application management</span></span>

<span data-ttu-id="353e0-181">다음을 통해 HoloLens 응용 프로그램을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-181">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="353e0-182">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="353e0-182">Microsoft Store</span></span>  
  <span data-ttu-id="353e0-183">Microsoft 스토어는 HoloLens에서 응용 프로그램을 배포하고 사용하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-183">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="353e0-184">주요 HoloLens 응용 프로그램이 이미 상점에서 사용 가능하고, 사용자가 [직접 게시](https://docs.microsoft.com/windows/uwp/publish/)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-184">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="353e0-185">상점의 모든 응용 프로그램은 모든 사람이 공개적으로 사용할 수 있지만, 허용되지 않는 경우 비즈니스용 Microsoft Store를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-185">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="353e0-186">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="353e0-186">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="353e0-187">비즈니스 및 교육용 Microsoft Store는 기업 환경을 위한 사용자 지정 스토어입니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-187">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="353e0-188">Windows 10 및 HoloLens에 내장된 Microsoft Store를 사용하여 조직을 위한 앱을 찾고 수집하고 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-188">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="353e0-189">또한 전 세계가 아닌 사용자의 상업적 환경에만 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-189">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="353e0-190">Intune 또는 다른 모바일 장치 관리 솔루션을 통한 응용 프로그램 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="353e0-190">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="353e0-191">Intune을 비롯한 대부분의 모바일 장치 관리 솔루션은 일련의 비즈니스 응용 프로그램을 등록된 장치 집합에 직접 배포할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-191">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="353e0-192">[Intune 앱 설치](https://docs.microsoft.com/intune/apps-deploy)에 대한 이 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-192">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="353e0-193">_권장되지 않는_ 장치 포털</span><span class="sxs-lookup"><span data-stu-id="353e0-193">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="353e0-194">Windows 장치 포털을 사용하여 HoloLens에 직접 응용 프로그램을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-194">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="353e0-195">장치 포털을 사용하려면 개발자 모드를 활성화해야 하므로 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-195">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="353e0-196">[HoloLens에 앱을 설치하는 방법](https://docs.microsoft.com/hololens/hololens-install-apps)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-196">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="353e0-197">인증서</span><span class="sxs-lookup"><span data-stu-id="353e0-197">Certificates</span></span>

<span data-ttu-id="353e0-198">MDM 공급자를 통해 인증서를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-198">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="353e0-199">회사에 인증서가 필요한 경우 Intune에서 PKCS, PFX 및 SCEP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-199">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="353e0-200">어떤 인증서가 회사에 적합한지를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-200">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="353e0-201">[인증서 구성](https://docs.microsoft.com/intune/protect/certificates-configure) 설명서를 보고 가장 적합한 인증서를 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-201">Please visit the [certificate configurations](https://docs.microsoft.com/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="353e0-202">HoloLens 인증에 인증서를 사용하려는 경우 PFX 또는 SCEP가 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-202">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="353e0-203">[SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep) 사용을 위해 다음 단계를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-203">See the following steps for using [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="353e0-204">Holographics for Business Commercial 제품군으로 업그레이드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="353e0-204">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="353e0-205">Windows Holographics for Business(상업용 제품군)는 HoloLens 1세대 장치에만 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-205">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="353e0-206">HoloLens 2 장치에는 프로필이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-206">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="353e0-207">상용 제품군으로 업그레이드하는 방법은 [홀로그램 업그레이드](https://docs.microsoft.com/intune/configuration/holographic-upgrade) 설명서에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-207">You can find directions for upgrading to the commercial suite in the [holographic upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade) documentation.</span></span>

### <span data-ttu-id="353e0-208">Microsoft Intune을 사용하여 키오스크 모드를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="353e0-208">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="353e0-209">Microsoft Store를 Intune에 동기화합니다(다음 [지침](https://docs.microsoft.com/intune/apps/windows-store-for-business) 참고).</span><span class="sxs-lookup"><span data-stu-id="353e0-209">Sync Microsoft Store to Intune (See the following [instructions](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="353e0-210">앱 설정 확인</span><span class="sxs-lookup"><span data-stu-id="353e0-210">Check your app settings</span></span>
    1. <span data-ttu-id="353e0-211">Microsoft Store Business 계정에 로그인</span><span class="sxs-lookup"><span data-stu-id="353e0-211">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="353e0-212">관리 > 제품 및 서비스 > 앱 및 소프트웨어 > 동기화하려는 앱 선택 > 개인 저장소 가용성 > "모두" 또는 "특정 그룹" 선택</span><span class="sxs-lookup"><span data-stu-id="353e0-212">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="353e0-213">원하는 앱이 표시되지 않을 경우 스토어에서 앱을 검색하여 앱을 "가져와야" 합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-213">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="353e0-214">**오른쪽 상단에서 "검색" 막대를 클릭하고 앱 이름을 입력한 다음 해당 앱을 클릭하고 "가져오기"를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="353e0-214">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="353e0-215">**Intune > 클라이언트 앱 > 앱**에 앱이 표시되지 않는다면 다시 [앱을 동기화](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-215">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="353e0-216">키오스크 모드용 디바이스 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="353e0-216">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="353e0-217">"Azure AD"를 "사용자 로그온 유형"으로 사용하여 다른 사용자가 다른 키오스크 모드 환경을 갖도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-217">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="353e0-218">그러나 이 옵션은 다중 앱 키오스크 모드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-218">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="353e0-219">다중 앱 키오스크 모드는 여러 앱뿐만 아니라 하나의 앱에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-219">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Intune에서 키오스크 모드 구성을 보여주는 이미지](images/aad-kioskmode.png)

<span data-ttu-id="353e0-221">다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-221">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="353e0-222">사용자 지정 설정 및 전체 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 한다면 [HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 키오스크 지침을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="353e0-222">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <span data-ttu-id="353e0-223">인증서 및 인증</span><span class="sxs-lookup"><span data-stu-id="353e0-223">Certificates and Authentication</span></span>

<span data-ttu-id="353e0-224">MDM을 통해 인증서를 배포할 수 있습니다([MDM 섹션](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)의 "인증서" 참조).</span><span class="sxs-lookup"><span data-stu-id="353e0-224">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="353e0-225">패키지 프로비저닝을 통해 HoloLens에 인증서를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-225">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="353e0-226">추가 정보는 [HoloLens 프로비저닝](hololens-provisioning.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="353e0-226">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="353e0-227">추가 Intune 빠른 링크</span><span class="sxs-lookup"><span data-stu-id="353e0-227">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="353e0-228">[프로필 생성:](https://docs.microsoft.com/intune/configuration/device-profile-create) 프로필을 사용하면 조직의 기기에 푸시될 설정을 추가하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-228">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

