---
title: 외부 클라이언트 배포 가이드
description: 외부 클라이언트에 대 한 HoloLens 2 배포 가이드 (원격 지원을 예제로 사용)
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
ms.openlocfilehash: acf4b5d730b9a7eee2dedfad2bb3f866931d7455
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636948"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="dcec4-103">원격 지원을 통해 외부 클라이언트에 HoloLens 2 배포</span><span class="sxs-lookup"><span data-stu-id="dcec4-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="dcec4-104">이 가이드는 IT 전문가 들이 조직에서 다음 목표를 Microsoft HoloLens 2 개 장치를 배포할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="dcec4-105">클라우드 연결 HoloLens 2 장치</span><span class="sxs-lookup"><span data-stu-id="dcec4-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="dcec4-106">외부 클라이언트에 대 한 대출 HoloLens 2 장치 사용</span><span class="sxs-lookup"><span data-stu-id="dcec4-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="dcec4-107">안전한 loaned 장치</span><span class="sxs-lookup"><span data-stu-id="dcec4-107">Secure loaned devices</span></span>

<span data-ttu-id="dcec4-108">이 가이드에서는 대부분의 HoloLens 2 배포 시나리오에 적용 되는 [일반적인 HoloLens 2 배포 권장 사항과](#general-deployment-recommendations-and-instructions) 외부 사용을 위한 원격 지원을 배포할 때 고객이 보유 하는 [일반적인 문제](#common-concerns) 를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="dcec4-109">시나리오 설명</span><span class="sxs-lookup"><span data-stu-id="dcec4-109">Scenario Description</span></span>

<span data-ttu-id="dcec4-110">이 문서의 목적을 위해 Contoso 회사는 단기 또는 장기 사용을 위해 외부 클라이언트의 공장에 HoloLens 2 장치를 배송 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="dcec4-111">클라이언트에서 지원 서비스를 제공 해야 하는 경우 클라이언트는 contoso 회사에서 제공 하는 자격 증명을 사용 하 여 HoloLens 2 장치에 로그인 하 고 원격 지원을 사용 하 여 contoso 회사의 전문가에 게 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="dcec4-112">[여기](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)에서 원격 지원에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dcec4-112">Learn more about Remote Assist [here](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="dcec4-113">이 시나리오에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcec4-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="dcec4-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="dcec4-114">Azure AD</span></span>](/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="dcec4-115">모바일 장치 관리자 (예: [Intune](/mem/intune/fundamentals/free-trial-sign-up) )</span><span class="sxs-lookup"><span data-stu-id="dcec4-115">Mobile Device Manager - such as [Intune](/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="dcec4-116">원격 지원 라이선스</span><span class="sxs-lookup"><span data-stu-id="dcec4-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="dcec4-117">원격 지원 구입</span><span class="sxs-lookup"><span data-stu-id="dcec4-117">Buy Remote Assist</span></span>](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="dcec4-118">평가판 원격 지원</span><span class="sxs-lookup"><span data-stu-id="dcec4-118">Trial Remote Assist</span></span>](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="dcec4-119">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="dcec4-119">Common Concerns</span></span>

- [<span data-ttu-id="dcec4-120">외부 클라이언트에 서로 통신할 수 있는 권한이 없는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="dcec4-121">클라이언트에 회사 리소스에 대 한 액세스 권한이 없도록 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="dcec4-122">앱을 제한 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="dcec4-123">암호를 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="dcec4-124">클라이언트에서 채팅 기록에 액세스할 수 없도록 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="dcec4-125">외부 클라이언트에 서로 통신할 수 있는 권한이 없는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="dcec4-126">HoloLens 호출에 대 한 원격 지원 HoloLens 지원 되지 않으므로 클라이언트는 검색할 수 있지만 서로 통신할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="dcec4-127">클라이언트에서 검색 하 고 호출할 수 있는 사용자를 제한 하기 위해  [정보 장벽을](/microsoft-365/compliance/information-barriers) 통해 클라이언트가 통신할 수 있는 사용자를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-127">To further restrict who clients can search for and call,  [Information barriers](/microsoft-365/compliance/information-barriers) can restrict who a client can communicate with.</span></span> <span data-ttu-id="dcec4-128">고려할 또 다른 옵션은 [범위 지정 디렉터리 검색](/MicrosoftTeams/teams-scoped-directory-search) 을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-128">Another option to consider is using [Scoped Directory Search](/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="dcec4-129">Single sign-on이 사용 하도록 설정 되어 있으므로 [**WDAC**](/hololens/windows-defender-application-control-wdac)를 사용 하 여 브라우저를 사용 하지 않도록 설정 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="dcec4-130">외부 클라이언트가 브라우저를 열고 웹 버전의 Teams을 사용 하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="dcec4-131">클라이언트에 회사 리소스에 대 한 액세스 권한이 없도록 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="dcec4-132">두 가지 옵션을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-132">There are two options to consider.</span></span>

<span data-ttu-id="dcec4-133">첫 번째 옵션은 다중 계층 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="dcec4-134">사용자에 게 필요한 라이선스만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="dcec4-135">사용자에 게 OneDrive, Outlook, SharePoint, Yammer 등을 할당 하지 않으면 해당 리소스에 대 한 액세스 권한이 부여 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="dcec4-136">사용자에 게 필요한 라이선스는 원격 지원, Intune 및 AAD 라이선스를 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="dcec4-137">클라이언트에서 액세스 하지 않으려는 앱 (예: 전자 메일)을 차단 합니다 ( [앱을 제한 하는 방법](#how-to-restrict-apps)참조).</span><span class="sxs-lookup"><span data-stu-id="dcec4-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="dcec4-138">사용자 이름 및 암호를 클라이언트와 공유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="dcec4-139">HoloLens 2에 로그인 하려면 전자 메일과 숫자 PIN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="dcec4-140">두 번째 옵션은 클라이언트를 호스트 하는 별도의 테 넌 트를 만드는 것입니다 (이미지 1.1 참조).</span><span class="sxs-lookup"><span data-stu-id="dcec4-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

<span data-ttu-id="dcec4-141">**이미지 1.1**</span><span class="sxs-lookup"><span data-stu-id="dcec4-141">**Image 1.1**</span></span>

![서비스 테 넌 트 이미지](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="dcec4-143">앱을 제한 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-143">How to restrict apps</span></span>

<span data-ttu-id="dcec4-144">[키오스크 모드](/hololens/hololens-kiosk) 및/또는 [WDAC (Windows Defender 응용 프로그램 컨트롤)](/hololens/windows-defender-application-control-wdac) 는 응용 프로그램을 제한 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-144">[Kiosk Mode](/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="dcec4-145">암호를 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-145">How to manage passwords</span></span>

1. <span data-ttu-id="dcec4-146">암호 만료를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-146">Remove password expiration.</span></span> <span data-ttu-id="dcec4-147">그러나 이렇게 하면 계정이 손상 될 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-147">However, this increases the chance that an account will be compromised.</span></span> <span data-ttu-id="dcec4-148">NIST 암호 권장 사항은 30-90 일 마다 암호를 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="dcec4-149">90 일을 초과 하 HoloLens 2 장치에 대 한 암호 만료를 연장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="dcec4-150">암호를 변경 하려면 장치를 Contoso로 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="dcec4-151">그러나이로 인해 장치가 클라이언트의 공장에 90 일 동안 예상 되는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="dcec4-152">여러 클라이언트에 전송 되는 장치의 경우 장치를 클라이언트에 배달 하기 전에 암호를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="dcec4-153">클라이언트에서 채팅 기록에 액세스할 수 없도록 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcec4-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="dcec4-154">원격 지원에서는 각 세션 후에 채팅 기록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="dcec4-155">그러나 Microsoft Teams 사용자에 게 채팅 기록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="dcec4-156">Single sign-on이 사용 하도록 설정 되어 있으므로 [**WDAC**](/hololens/windows-defender-application-control-wdac)를 사용 하 여 브라우저를 사용 하지 않도록 설정 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="dcec4-157">외부 클라이언트가 브라우저를 열고 웹 버전의 Teams을 사용 하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="dcec4-158">일반 배포 권장 사항 및 지침</span><span class="sxs-lookup"><span data-stu-id="dcec4-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="dcec4-159">HoloLens 2 배포 단계는 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="dcec4-160">[최신 HoloLens OS 릴리스](https://aka.ms/hololens2download) 를 기준 빌드로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="dcec4-161">사용자 기반 또는 장치 기반 라이선스 할당:</span><span class="sxs-lookup"><span data-stu-id="dcec4-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="dcec4-162">사용자 기반 라이선스와 장치 기반 라이선스는 모두 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="dcec4-163">[AAD에서 그룹을 만들고](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 사용자에 대 한 멤버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-163">[Create a group in AAD and add members](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="dcec4-164">[장치 기반 또는 사용자 기반 라이선스](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 를이 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-164">[Assign device-based or user-based licenses](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="dcec4-165">필드 MDM 정책의 그룹을 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="dcec4-166">장치는 자동 [파일럿](/hololens/hololens2-autopilot)을 통해 테 넌 트에 연결 되 고 [자동으로 등록](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)되 고 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-166">Devices should be AAD joined to your tenant, [Auto Enrolled](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="dcec4-167">장치의 첫 번째 사용자는 장치 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="dcec4-168">장치가 AAD에 연결 된 경우에는 조인을 수행한 사용자가 장치 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="dcec4-169">자세한 내용은 [장치 소유자](/hololens/security-adminless-os#device-owner)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dcec4-169">For more, see [Device Owner](/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="dcec4-170">테 넌 트는 테 넌 트에만 참가할 수 있도록 장치를 [잠급니다](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) .</span><span class="sxs-lookup"><span data-stu-id="dcec4-170">[Tenant lock](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="dcec4-171">**추가 링크:** [테 넌 트 잠금 CSP](/windows/client-management/mdm/tenantlockdown-csp).</span><span class="sxs-lookup"><span data-stu-id="dcec4-171">**Additional Link:** [Tenant lock CSP](/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="dcec4-172">[여기](/hololens/hololens-global-assigned-access-kiosk)에 대 한 전역 할당 액세스를 사용 하 여 키오스크를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-172">Configure kiosk using global assigned access to [here](/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="dcec4-173">다음 (옵션) 기능을 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="dcec4-174">[여기](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)에서 장치를 개발자 모드로 전환 하는 기능.</span><span class="sxs-lookup"><span data-stu-id="dcec4-174">Ability to put the device into developer mode [here](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="dcec4-175">HoloLens를 PC에 연결 하 여 복사 하는 기능 [USB를 사용 하지 않도록 설정](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-175">Ability to connect the HoloLens to a PC to copy date [disable USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="dcec4-176">Usb를 사용 하지 않도록 설정 하 고 USB를 사용 하 여 장치에 프로 비전 패키지를 적용 하는 기능을 사용 하려면 [**여기**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)에 나열 된 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="dcec4-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="dcec4-177">[WDAC](/hololens/windows-defender-application-control-wdac) 를 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-177">Use [WDAC](/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="dcec4-178">원격 지원을 설치의 일부로 최신 버전으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="dcec4-179">이 작업을 수행 하는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="dcec4-180">이 작업을 수행 하려면 Windows **Microsoft Store (> 원격 지원--> 및 업데이트 앱** 으로 이동 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="dcec4-181">자동 앱 업데이트를 허용 하는 [Applicationmanagement/Allowapp자동](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 업데이트-기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-181">[ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="dcec4-182">장치를 연결 된 상태로 유지 하 여 업데이트를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="dcec4-183">사용자가 클라이언트 사이트에서 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 [모든 설정 페이지를 사용 하지 않도록](/hololens/settings-uri-list) 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-183">[Disable all settings pages](/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="dcec4-184">HoloLens 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="dcec4-184">Manage HoloLens Updates</span></span>](/hololens/hololens-updates)
    1. <span data-ttu-id="dcec4-185">[OS 업데이트를 제어](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 하거나 자유롭게 이동 하도록 허용 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="dcec4-185">Option to [control OS updates](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="dcec4-186">[일반적인 장치 제한 사항](/hololens/hololens-common-device-restrictions).</span><span class="sxs-lookup"><span data-stu-id="dcec4-186">[Common Device Restrictions](/hololens/hololens-common-device-restrictions).</span></span>
