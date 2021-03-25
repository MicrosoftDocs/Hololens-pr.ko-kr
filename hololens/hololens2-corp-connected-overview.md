---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 개요
description: 회사 연결 네트워크를 통해 Dynamics 365 가이드를 통해 HoloLens 2 장치를 등록하는 방법을 알아보세요.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448599"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="784e9-104">배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 개요</span><span class="sxs-lookup"><span data-stu-id="784e9-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="784e9-105">이 가이드는 IT 전문가가 Dynamics 365 가이드(가이드)를 통해 Microsoft HoloLens 2 장치를 계획하고 조직에 배포하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="784e9-106">이 가이드는 파일럿 및 프로덕션 배포에 매우 잘 사용하며, 시나리오 [B:](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 조직의 네트워크 가이드 내에서 배포와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="784e9-107">개념 증명을 테스트한 후 이 가이드를 사용하여 HoloLens를 조직에 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="784e9-108">이 가이드에서는 장치를 기존 장치 관리에 등록하고, 필요한 경우 라이선스를 적용하고, 최종 사용자가 Dynamics 365 가이드를 운영하고, 장치 설정 후 사용자 지정 기간 업무(LINE)을 사용할 수 있는지 검증하는 방법에 대해 다 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="784e9-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="784e9-109">Prerequisites</span></span>

<span data-ttu-id="784e9-110">다음 인프라가 이미 구축되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="784e9-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="784e9-111">Wi-Fi</span></span>
    - <span data-ttu-id="784e9-112">내부 리소스에 대한 액세스 및 인터넷 또는 클라우드 서비스에 대한 제한된 액세스 권한이 있는 내부 회사 네트워크</span><span class="sxs-lookup"><span data-stu-id="784e9-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="784e9-113">장치 기반 인증서 인증.</span><span class="sxs-lookup"><span data-stu-id="784e9-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="784e9-114">MDM 자동 등록을 사용하여 Azure AD(Azure Active Directory) 가입([Azure AD P1 구독](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 필요)</span><span class="sxs-lookup"><span data-stu-id="784e9-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="784e9-115">MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="784e9-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="784e9-116">하나 이상의 응용 프로그램이 MDM을 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="784e9-117">네트워크</span><span class="sxs-lookup"><span data-stu-id="784e9-117">Network</span></span> 
    - <span data-ttu-id="784e9-118">인증서(SCEP 또는 PKCS)</span><span class="sxs-lookup"><span data-stu-id="784e9-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="784e9-119">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="784e9-119">Proxy configuration</span></span>
- <span data-ttu-id="784e9-120">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="784e9-121">장치당 한명 또는 여러 사용자가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="784e9-122">특정 사용 사례에 따라 적용되는 장치 잠금 구성의 다양한 수준(완전히 열기에서 단일 앱 키오스크까지)</span><span class="sxs-lookup"><span data-stu-id="784e9-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="784e9-123">라이선스 및 요구 사항 가이드</span><span class="sxs-lookup"><span data-stu-id="784e9-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="784e9-124">Azure AD 계정</span><span class="sxs-lookup"><span data-stu-id="784e9-124">Azure AD account</span></span>
- <span data-ttu-id="784e9-125">Dynamics 365 가이드 응용 프로그램 PC 및 HoloLens</span><span class="sxs-lookup"><span data-stu-id="784e9-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="784e9-126">Dynamics 365 가이드 구독</span><span class="sxs-lookup"><span data-stu-id="784e9-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="784e9-127">Microsoft Dataverse(포함)</span><span class="sxs-lookup"><span data-stu-id="784e9-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="784e9-128">Power Apps(포함)</span><span class="sxs-lookup"><span data-stu-id="784e9-128">Power Apps (included)</span></span>
- <span data-ttu-id="784e9-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="784e9-129">Power BI Desktop</span></span>
- <span data-ttu-id="784e9-130">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="784e9-130">Network Connectivity</span></span>

![Corp 연결된 네트워크 다이어그램](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="784e9-132">배포 단계</span><span class="sxs-lookup"><span data-stu-id="784e9-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="784e9-133">준비</span><span class="sxs-lookup"><span data-stu-id="784e9-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="784e9-134">HoloLens 2 장치의 인프라 필수 요소에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="784e9-135">Azure AD에 대해 자세히 알아보고 없는 경우 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="784e9-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="784e9-136">ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="784e9-137">아직 준비되지 않은 경우 MDM에 대해 자세히 알아보고 Intune을 통해 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="784e9-138">인증서 기반 Wi-Fi에 익숙해지세요.</span><span class="sxs-lookup"><span data-stu-id="784e9-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="784e9-139">프록시에 익숙해지세요.</span><span class="sxs-lookup"><span data-stu-id="784e9-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="784e9-140">업무용 앱을 사용하는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="784e9-141">조직에 대한 가이드를 사용하는 방식에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="784e9-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="784e9-142">구성</span><span class="sxs-lookup"><span data-stu-id="784e9-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="784e9-143">사용자 및 그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="784e9-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="784e9-144">자동 등록을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="784e9-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="784e9-145">회사 Wi-Fi 연결에 대한 인증서 및 프로필을 Wi-Fi 방법</span><span class="sxs-lookup"><span data-stu-id="784e9-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="784e9-146">LOB(LOB) 앱 패키지를 업로드하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="784e9-147">Dynamics 365 가이드 설정</span><span class="sxs-lookup"><span data-stu-id="784e9-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="784e9-148">키오스크 모드를 구성하는 방법(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="784e9-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="784e9-149">WDAC를 구성하는 방법(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="784e9-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="784e9-150">배포</span><span class="sxs-lookup"><span data-stu-id="784e9-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="784e9-151">장치 및 MDM을 통해 등록의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="784e9-152">인증서 Wi-Fi 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="784e9-153">LOB 앱 설치의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="784e9-154">제작 및 운영을 통해 가이드의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="784e9-155">유지 관리</span><span class="sxs-lookup"><span data-stu-id="784e9-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="784e9-156">HoloLens 2를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="784e9-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="784e9-157">가이드(스토어 앱)를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="784e9-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="784e9-158">LOB 앱을 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="784e9-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="784e9-159">개발 계획.</span><span class="sxs-lookup"><span data-stu-id="784e9-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="784e9-160">지원 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="784e9-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="784e9-161">장치 관리 옵션.</span><span class="sxs-lookup"><span data-stu-id="784e9-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="784e9-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="784e9-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="784e9-163">회사 연결 배포 - 준비</span><span class="sxs-lookup"><span data-stu-id="784e9-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
