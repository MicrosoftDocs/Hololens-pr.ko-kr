---
title: 배포 가이드
description: HoloLens 2 배포 가이드(원격 도우미를 예로 사용)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/7/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 0cd75fdbe5f6a4e6da87770768ce9f22bce491c0
ms.sourcegitcommit: 58bffba63ed581351d80d13b1437aca74d7ed64a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "11266377"
---
# <span data-ttu-id="4f719-103">원격 지원을 사용하여 외부 클라이언트에 HoloLens 2 배포</span><span class="sxs-lookup"><span data-stu-id="4f719-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="4f719-104">이 문서는 IT 사용자가 원격 지원에 중점을 두는 HoloLens 2 장치를 계획하고 배포하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-104">This document helps IT professions plan for and deploy HoloLens 2 devices with a focus on Remote Assist.</span></span> <span data-ttu-id="4f719-105">[원격 지원에 대해 자세히 알아보시고.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="4f719-105">[Learn more about Remote Assist](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

## <span data-ttu-id="4f719-106">시나리오 설명</span><span class="sxs-lookup"><span data-stu-id="4f719-106">Scenario Description</span></span>

<span data-ttu-id="4f719-107">이 문서의 목적을 위해 Contoso Company는 단기 또는 장기 사용을 위해 HoloLens 2 장치를 외부 클라이언트의 공장에 발송하기를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-107">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="4f719-108">클라이언트가 기계를 서비스하는 데 도움이 필요한 경우 클라이언트는 Contoso Company에서 제공하는 자격 증명을 사용하여 HoloLens 2 장치에 로그인하고 원격 지원을 사용하여 Contoso 회사의 전문가에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-108">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

### <span data-ttu-id="4f719-109">이 시나리오에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f719-109">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="4f719-110">Azure AD</span><span class="sxs-lookup"><span data-stu-id="4f719-110">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="4f719-111">모바일 장치 관리자 - [Intune 등의](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="4f719-111">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="4f719-112">원격 지원 라이선스</span><span class="sxs-lookup"><span data-stu-id="4f719-112">Remote Assist License</span></span>
    1. [<span data-ttu-id="4f719-113">원격 지원 구입</span><span class="sxs-lookup"><span data-stu-id="4f719-113">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="4f719-114">평가판 원격 지원</span><span class="sxs-lookup"><span data-stu-id="4f719-114">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <span data-ttu-id="4f719-115">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="4f719-115">Common Concerns</span></span>

- [<span data-ttu-id="4f719-116">외부 클라이언트가 서로 통신할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-116">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="4f719-117">클라이언트가 회사 리소스에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-117">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="4f719-118">앱을 제한하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-118">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="4f719-119">암호를 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-119">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="4f719-120">클라이언트가 채팅 기록에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-120">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <span data-ttu-id="4f719-121">외부 클라이언트가 서로 통신할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-121">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="4f719-122">HoloLens에 대한 원격 지원 HoloLens 통화는 지원되지 않습니다. 클라이언트는 검색할 수 있지만 서로 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-122">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="4f719-123">클라이언트가 검색 및 통화를 할 수 있는 사용자에 대한 제한을 강화하기 위해  [정보](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 장벽은 클라이언트가 통신할 수 있는 사용자에 대해 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-123">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="4f719-124">고려해야 할 또 다른 옵션은 [범위가 지정한 디렉터리 검색을 사용하는 것입니다.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="4f719-124">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="4f719-125">Single Sign-On이 사용하도록 설정되어 있는 경우 [**WDAC를**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-125">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="4f719-126">외부 클라이언트가 브라우저를 열고 Teams의 웹 버전을 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-126">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <span data-ttu-id="4f719-127">클라이언트가 회사 리소스에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-127">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="4f719-128">두 가지 옵션을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-128">There are two options to consider.</span></span>

<span data-ttu-id="4f719-129">첫 번째 옵션은 다중 계층 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-129">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="4f719-130">사용자에게 필요한 라이선스만 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-130">Only assign licenses that the user requires.</span></span> <span data-ttu-id="4f719-131">사용자에게 OneDrive, Outlook, SharePoint, Yammer 등을 할당하지 않는 경우 해당 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-131">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="4f719-132">사용자에게 필요한 라이선스는 원격 지원, Intune 및 AAD 라이선스뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-132">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="4f719-133">클라이언트가 액세스하지 못하게 할 앱(예: 전자 메일)을 [차단합니다(앱](#how-to-restrict-apps)제한 방법 참조).</span><span class="sxs-lookup"><span data-stu-id="4f719-133">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="4f719-134">사용자 이름이나 암호를 클라이언트와 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-134">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="4f719-135">HoloLens 2에 로그인하려면 전자 메일 및 숫자 PIN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-135">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="4f719-136">두 번째 옵션은 클라이언트를 호스트하는 별도의 테넌트(이미지 1.1 참조)를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-136">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="4f719-137">이미지 1.1</span><span class="sxs-lookup"><span data-stu-id="4f719-137">Image 1.1</span></span>**

![서비스 테넌트 이미지](./images/hololens-service-tenant-image.png)

### <span data-ttu-id="4f719-139">앱을 제한하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-139">How to restrict apps</span></span>

<span data-ttu-id="4f719-140">[키오스크](https://docs.microsoft.com/hololens/hololens-kiosk) 모드 및/또는 [WDAC(Windows Defender 응용](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 프로그램 제어)는 응용 프로그램을 제한하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-140">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <span data-ttu-id="4f719-141">암호를 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-141">How to manage passwords</span></span>

1. <span data-ttu-id="4f719-142">암호 만료를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-142">Remove password expiration.</span></span> <span data-ttu-id="4f719-143">그러나 이렇게 하면 계정이 손상될 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-143">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="4f719-144">NIST 암호 권장은 30-90일마다 암호를 변경하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-144">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="4f719-145">HoloLens 2 장치의 암호 만료를 90일을 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-145">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="4f719-146">암호를 변경하기 위해 장치를 Contoso로 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-146">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="4f719-147">그러나 이로 인해 장치가 90일 이상 클라이언트의 공장에 있을 것으로 예상되는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-147">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="4f719-148">여러 클라이언트로 전송되는 장치의 경우 장치를 클라이언트에 전달하기 전에 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f719-148">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <span data-ttu-id="4f719-149">클라이언트가 채팅 기록에 액세스할 수 없는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f719-149">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="4f719-150">원격 지원은 각 세션 후 채팅 기록을 지우습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-150">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="4f719-151">그러나 Microsoft Teams 사용자가 채팅 기록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-151">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="4f719-152">Single Sign-On이 사용하도록 설정되어 있는 경우 [**WDAC를**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-152">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="4f719-153">외부 클라이언트가 브라우저를 열고 웹 버전의 Teams를 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-153">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <span data-ttu-id="4f719-154">일반 배포 권장 사항 및 지침</span><span class="sxs-lookup"><span data-stu-id="4f719-154">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="4f719-155">HoloLens 2 배포 단계에는 다음이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-155">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="4f719-156">최신 [HoloLens OS](https://aka.ms/hololens2download) 릴리스를 기본 빌드로 사용</span><span class="sxs-lookup"><span data-stu-id="4f719-156">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="4f719-157">사용자 기반 또는 장치 기반 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-157">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="4f719-158">사용자 기반 라이선스와 장치 기반 라이선스는 모두 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-158">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="4f719-159">[AAD에서 그룹을](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 만들고 HoloLens/RA 사용자에 대한 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-159">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="4f719-160">[이 그룹에 장치 기반](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 또는 사용자 기반 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-160">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="4f719-161">(선택 사항) MDM 정책에 대한 그룹을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-161">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="4f719-162">장치는 테넌트에 AAD에 [가입되고,](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)자동 등록되고, 자동 파일럿을 통해 [구성해야 합니다.](https://docs.microsoft.com/hololens/hololens2-autopilot)</span><span class="sxs-lookup"><span data-stu-id="4f719-162">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="4f719-163">디바이스의 첫 번째 사용자는 장치 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-163">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="4f719-164">장치가 AAD에 가입된 경우 조인을 수행한 사용자가 장치 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-164">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="4f719-165">자세한 내용은 [장치 소유자를 참조하세요.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)</span><span class="sxs-lookup"><span data-stu-id="4f719-165">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="4f719-166">[테넌트는](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 테넌트에만 가입할 수 있도록 디바이스를 잠습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-166">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="4f719-167">**추가 링크:** [테넌트 잠금 CSP.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)</span><span class="sxs-lookup"><span data-stu-id="4f719-167">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="4f719-168">여기에 대한 전역 할당 액세스를 사용하여 키오스크를 [구성합니다.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)</span><span class="sxs-lookup"><span data-stu-id="4f719-168">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="4f719-169">다음과 같은(선택 사항) 기능을 사용 안 하게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-169">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="4f719-170">여기에서 디바이스를 개발자 모드로 전환하는 [기능을 제공합니다.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)</span><span class="sxs-lookup"><span data-stu-id="4f719-170">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="4f719-171">HOloLens를 PC에 연결하여 날짜를 복사하여 [USB를 사용할 수 없습니다.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)</span><span class="sxs-lookup"><span data-stu-id="4f719-171">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="4f719-172">USB를 사용하지 않도록 설정하고 USB를 사용하여 장치에 프로비저닝 패키지를 적용하려는 경우 여기에 나열된 지침을 [**따릅니다.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)</span><span class="sxs-lookup"><span data-stu-id="4f719-172">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="4f719-173">[WDAC를 사용하여](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) HoloLens 2 장치에서 앱을 허용하거나 검은색 앱을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-173">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or black apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="4f719-174">설치의 일부로 원격 도우미를 최신 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-174">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="4f719-175">이 작업을 위한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-175">There are two options to do this:</span></span>
    1. <span data-ttu-id="4f719-176">이 수행은 Windows **Microsoft Store --> --> 앱 업데이트로 > 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4f719-176">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="4f719-177">또 다른 방법은 자동 업데이트를 위해 HoloLens 2를 밤에 플러그 인된 그대로 두는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-177">Another method is to leave the HoloLens 2 plugged in overnight for auto update.</span></span>
1. <span data-ttu-id="4f719-178">[사용자가 클라이언트 사이트에서](https://docs.microsoft.com/hololens/settings-uri-list) 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 모든 설정 페이지를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-178">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="4f719-179">HoloLens 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="4f719-179">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="4f719-180">OS 업데이트를 [제어하거나](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 자유롭게 진행할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4f719-180">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="4f719-181">[일반 장치 제한.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)</span><span class="sxs-lookup"><span data-stu-id="4f719-181">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
