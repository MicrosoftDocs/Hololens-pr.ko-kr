---
title: 외부 클라이언트 배포 가이드
description: '외부 클라이언트용 HoloLens 2 배포 가이드(예: 원격 지원 사용)'
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385589"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="02ec3-103">원격 지원을 사용하여 외부 클라이언트에 HoloLens 2 배포</span><span class="sxs-lookup"><span data-stu-id="02ec3-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="02ec3-104">이 가이드는 다음 목표를 달성한 IT 전문가가 조직에 Microsoft HoloLens 2 장치를 배포하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="02ec3-105">HoloLens 2 장치 클라우드 연결</span><span class="sxs-lookup"><span data-stu-id="02ec3-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="02ec3-106">사용할 외부 클라이언트에 HoloLens 2 장치 대출</span><span class="sxs-lookup"><span data-stu-id="02ec3-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="02ec3-107">대출된 보안 장치</span><span class="sxs-lookup"><span data-stu-id="02ec3-107">Secure loaned devices</span></span>

<span data-ttu-id="02ec3-108">이 가이드에서는 대부분의 HoloLens 2 배포 시나리오에 적용할 수 있는 일반적인 [](#common-concerns) [HoloLens 2](#general-deployment-recommendations-and-instructions) 배포 권장 사항과 고객이 외부 사용을 위해 원격 지원을 배포할 때 일반적으로 우려하는 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="02ec3-109">시나리오 설명</span><span class="sxs-lookup"><span data-stu-id="02ec3-109">Scenario Description</span></span>

<span data-ttu-id="02ec3-110">이 문서의 목적을 위해 Contoso Company는 단기 또는 장기 사용을 위해 HoloLens 2 장치를 외부 클라이언트의 공장에 배송하기를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="02ec3-111">클라이언트가 기계를 서비스하는 데 도움이 필요한 경우 클라이언트는 Contoso Company에서 제공하는 자격 증명을 사용하여 HoloLens 2 장치에 로그인하고 원격 지원을 사용하여 Contoso 회사의 전문가에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="02ec3-112">원격 지원에 대한 자세한 내용은 여기를 [클릭하세요.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="02ec3-112">Learn more about Remote Assist [here](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="02ec3-113">이 시나리오에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="02ec3-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="02ec3-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="02ec3-114">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="02ec3-115">모바일 장치 관리자 - [예: Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="02ec3-115">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="02ec3-116">원격 지원 라이선스</span><span class="sxs-lookup"><span data-stu-id="02ec3-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="02ec3-117">원격 지원 구입</span><span class="sxs-lookup"><span data-stu-id="02ec3-117">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="02ec3-118">평가판 원격 지원</span><span class="sxs-lookup"><span data-stu-id="02ec3-118">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="02ec3-119">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="02ec3-119">Common Concerns</span></span>

- [<span data-ttu-id="02ec3-120">외부 클라이언트가 서로 통신할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="02ec3-121">클라이언트가 회사 리소스에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="02ec3-122">앱을 제한하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="02ec3-123">암호 관리 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="02ec3-124">클라이언트가 채팅 기록에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="02ec3-125">외부 클라이언트가 서로 통신할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="02ec3-126">HoloLens에 대한 원격 지원 HoloLens 통화는 지원되지 않습니다. 클라이언트는 검색할 수 있지만 서로 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="02ec3-127">클라이언트가 검색 및 통화를 할 수 있는 사용자 제한을 강화하기 위해  [정보](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 장벽은 클라이언트가 통신할 수 있는 사용자에 대해 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-127">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="02ec3-128">고려해야 할 또 다른 옵션은 [범위가 지정한 디렉터리 검색을 사용하는 것입니다.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="02ec3-128">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="02ec3-129">Single Sign-On이 사용하도록 설정되어 있는 경우 [**WDAC를**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="02ec3-130">외부 클라이언트가 브라우저를 열고 웹 버전의 Teams를 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="02ec3-131">클라이언트가 회사 리소스에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="02ec3-132">두 가지 옵션을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-132">There are two options to consider.</span></span>

<span data-ttu-id="02ec3-133">첫 번째 옵션은 다중 계층 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="02ec3-134">사용자에게 필요한 라이선스만 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="02ec3-135">사용자에게 OneDrive, Outlook, SharePoint, Yammer 등을 할당하지 않는 경우 해당 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="02ec3-136">사용자에게 필요한 라이선스는 원격 지원, Intune 및 AAD 라이선스뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="02ec3-137">클라이언트가 액세스하지 못하게 하려는 앱(예: 전자 메일)을 차단합니다(앱 제한 [방법 참조).](#how-to-restrict-apps)</span><span class="sxs-lookup"><span data-stu-id="02ec3-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="02ec3-138">사용자 이름이나 암호를 클라이언트와 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="02ec3-139">HoloLens 2에 로그인하려면 전자 메일 및 숫자 PIN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="02ec3-140">두 번째 옵션은 클라이언트를 호스트하는 별도의 테넌트 만들기입니다(이미지 1.1 참조).</span><span class="sxs-lookup"><span data-stu-id="02ec3-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="02ec3-141">이미지 1.1</span><span class="sxs-lookup"><span data-stu-id="02ec3-141">Image 1.1</span></span>**

![서비스 테넌트 이미지](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="02ec3-143">앱을 제한하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-143">How to restrict apps</span></span>

<span data-ttu-id="02ec3-144">[키오스크](https://docs.microsoft.com/hololens/hololens-kiosk) 모드 및/또는 [WDAC(Windows Defender 응용](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 프로그램 제어)는 응용 프로그램을 제한하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-144">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="02ec3-145">암호 관리 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-145">How to manage passwords</span></span>

1. <span data-ttu-id="02ec3-146">암호 만료를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-146">Remove password expiration.</span></span> <span data-ttu-id="02ec3-147">그러나 이렇게 하면 계정이 손상될 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-147">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="02ec3-148">NIST 암호 권장은 30-90일마다 암호를 변경하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="02ec3-149">HoloLens 2 장치의 암호 만료를 90일을 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="02ec3-150">암호를 변경하기 위해 장치를 Contoso에 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="02ec3-151">그러나 이로 인해 장치가 90일 이상 클라이언트의 공장에 있을 것으로 예상되는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="02ec3-152">여러 클라이언트로 전송되는 장치의 경우 장치를 클라이언트로 배송하기 전에 암호를 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="02ec3-153">클라이언트가 채팅 기록에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="02ec3-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="02ec3-154">Remote Assist는 각 세션 후 채팅 기록을 지우습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="02ec3-155">그러나 Microsoft Teams 사용자가 채팅 기록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="02ec3-156">Single Sign-On이 사용하도록 설정되어 있는 경우 [**WDAC를**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="02ec3-157">외부 클라이언트가 브라우저를 열고 웹 버전의 Teams를 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="02ec3-158">일반 배포 권장 사항 및 지침</span><span class="sxs-lookup"><span data-stu-id="02ec3-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="02ec3-159">HoloLens 2 배포 단계는 다음을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="02ec3-160">최신 [HoloLens OS](https://aka.ms/hololens2download) 릴리스를 기준 빌드로 사용</span><span class="sxs-lookup"><span data-stu-id="02ec3-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="02ec3-161">사용자 기반 또는 장치 기반 라이선스 할당:</span><span class="sxs-lookup"><span data-stu-id="02ec3-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="02ec3-162">사용자 기반 라이선스와 장치 기반 라이선스는 모두 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="02ec3-163">[AAD에서 그룹을](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 만들고 HoloLens/RA 사용자의 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-163">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="02ec3-164">[이 그룹에 장치 기반](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 또는 사용자 기반 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-164">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="02ec3-165">(선택 사항) MDM 정책에 대한 그룹을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="02ec3-166">장치는 테넌트에 AAD에 [가입되고,](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)자동 등록되고, 자동 파일럿을 통해 [구성됩니다.](https://docs.microsoft.com/hololens/hololens2-autopilot)</span><span class="sxs-lookup"><span data-stu-id="02ec3-166">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="02ec3-167">디바이스의 첫 번째 사용자는 장치 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="02ec3-168">장치가 AAD에 가입된 경우 조인을 수행한 사용자가 장치 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="02ec3-169">자세한 내용은 장치 소유자 [를 참조하세요.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)</span><span class="sxs-lookup"><span data-stu-id="02ec3-169">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="02ec3-170">[테넌트는](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 테넌트에만 가입할 수 있도록 장치를 잠습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-170">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="02ec3-171">**추가 링크:** [테넌트 잠금 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span><span class="sxs-lookup"><span data-stu-id="02ec3-171">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="02ec3-172">여기에 대한 전역 할당 액세스를 사용하여 키오스크를 [구성합니다.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)</span><span class="sxs-lookup"><span data-stu-id="02ec3-172">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="02ec3-173">다음과 같은(선택 사항) 기능을 사용 안 하게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="02ec3-174">여기에서 디바이스를 개발자 모드로 전환하는 [기능을 제공합니다.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)</span><span class="sxs-lookup"><span data-stu-id="02ec3-174">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="02ec3-175">HOloLens를 PC에 연결하여 날짜를 복사하여 [USB를 사용하지 않도록 설정하는 능력.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)</span><span class="sxs-lookup"><span data-stu-id="02ec3-175">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="02ec3-176">USB를 사용하지 않도록 설정하지 않지만 USB를 사용하여 장치에 프로비저닝 패키지를 적용하는 기능을 원할 경우 여기에 나열된 지침을 [**따릅니다.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)</span><span class="sxs-lookup"><span data-stu-id="02ec3-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="02ec3-177">[WDAC를 사용하여](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) HoloLens 2 장치에서 앱을 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-177">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="02ec3-178">설치의 일부로 원격 지원을 최신 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="02ec3-179">이 작업을 위한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="02ec3-180">이 경우 Windows Microsoft **Store --> 원격**지원 및 업데이트 앱으로 > 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="02ec3-181">[자동 앱 업데이트를 허용하는 ApplicationManagement/AllowAppStoreAutoUpdate는](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="02ec3-182">업데이트를 받기 위해 장치를 플러그 인된 것으로 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="02ec3-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="02ec3-183">[사용자가 클라이언트 사이트에서](https://docs.microsoft.com/hololens/settings-uri-list) 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 모든 설정 페이지를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-183">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="02ec3-184">HoloLens 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="02ec3-184">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="02ec3-185">OS 업데이트를 [제어하거나](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 자유롭게 진행할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="02ec3-185">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="02ec3-186">[일반적인 장치 제한](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span><span class="sxs-lookup"><span data-stu-id="02ec3-186">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
