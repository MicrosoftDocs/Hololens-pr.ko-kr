---
title: 배포 가이드 – Dynamics 365 Guides를 사용 하 여 회사에 연결 된 HoloLens 2-개요
description: 회사 연결 네트워크를 통해 Dynamics 365 Guides에 HoloLens 2 장치를 등록 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사에 연결 된 Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637016"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="cd777-104">배포 가이드-Dynamics 365 Guides를 사용 하 여 회사에 연결 된 HoloLens 2-개요</span><span class="sxs-lookup"><span data-stu-id="cd777-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="cd777-105">이 가이드는 IT 전문가가 조직에 Dynamics 365 Guides (가이드)를 사용 하 여 Microsoft HoloLens 2 개 장치를 계획 하 고 배포 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="cd777-106">이 가이드는 파일럿 및 프로덕션 배포에 적합 하며, [시나리오 B: 조직의 네트워크 내 배포](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 가이드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="cd777-107">개념 증명을 테스트 한 후에는이 가이드를 사용 하 여 조직에 HoloLens를 통합 하 여 진행 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd777-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="cd777-108">이 가이드에서는 기존 장치 관리에 장치를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설정 후 사용자 지정 lob (기간 업무) 앱을 사용할 365 수 있는지 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cd777-109">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd777-109">Prerequisites</span></span>

<span data-ttu-id="cd777-110">다음 인프라는 이미 준비 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="cd777-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cd777-111">Wi-Fi</span></span>
    - <span data-ttu-id="cd777-112">내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 및 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스</span><span class="sxs-lookup"><span data-stu-id="cd777-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="cd777-113">장치 기반 인증서 인증.</span><span class="sxs-lookup"><span data-stu-id="cd777-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="cd777-114">MDM 자동 등록을 사용 하는 Azure Active Directory (azure ad) 가입 ([azure ad P1 구독](/azure/active-directory/fundamentals/active-directory-whatis) 필요)</span><span class="sxs-lookup"><span data-stu-id="cd777-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="cd777-115">MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="cd777-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="cd777-116">하나 이상의 응용 프로그램은 MDM을 통해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="cd777-117">네트워크</span><span class="sxs-lookup"><span data-stu-id="cd777-117">Network</span></span> 
    - <span data-ttu-id="cd777-118">인증서 (SCEP 또는 PKCS)</span><span class="sxs-lookup"><span data-stu-id="cd777-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="cd777-119">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="cd777-119">Proxy configuration</span></span>
- <span data-ttu-id="cd777-120">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="cd777-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="cd777-121">장치당 단일 또는 여러 사용자가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="cd777-122">특정 사용 사례에 따라 적용 되는 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="cd777-123">지침 라이선스 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd777-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="cd777-124">Azure AD 계정</span><span class="sxs-lookup"><span data-stu-id="cd777-124">Azure AD account</span></span>
- <span data-ttu-id="cd777-125">Dynamics 365 Guides 응용 프로그램 PC 및 HoloLens</span><span class="sxs-lookup"><span data-stu-id="cd777-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="cd777-126">Dynamics 365 Guides 구독</span><span class="sxs-lookup"><span data-stu-id="cd777-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="cd777-127">Microsoft Dataverse (포함)</span><span class="sxs-lookup"><span data-stu-id="cd777-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="cd777-128">Power Apps (포함)</span><span class="sxs-lookup"><span data-stu-id="cd777-128">Power Apps (included)</span></span>
- <span data-ttu-id="cd777-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="cd777-129">Power BI Desktop</span></span>
- <span data-ttu-id="cd777-130">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="cd777-130">Network Connectivity</span></span>

<span data-ttu-id="cd777-131">[![Corp 연결 네트워크 다이어그램, 1 ](./images/deployment-guides-revised-scenario-b-01-1.png) 단계](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cd777-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="cd777-132">[![Corp 연결 네트워크 다이어그램, 2 ](./images/deployment-guides-revised-scenario-b-02-1.png) 단계](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cd777-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="cd777-133">이 가이드에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="cd777-134">준비</span><span class="sxs-lookup"><span data-stu-id="cd777-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="cd777-135">HoloLens 2 장치에 대 한 인프라 essentials에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="cd777-136">Azure AD에 대 한 자세한 정보를 확인 하 고 없는 경우 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="cd777-137">Id 관리 및 Azure AD 계정을 최적으로 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="cd777-138">MDM에 대해 자세히 알아보고 아직 준비 하지 않은 경우 Intune을 사용 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="cd777-139">인증서 기반 Wi-fi에 익숙해져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="cd777-140">프록시를 숙지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="cd777-141">Lob (기간 업무) 앱을 사용 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="cd777-142">조직에서 가이드를 사용할 수 있는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="cd777-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="cd777-143">구성</span><span class="sxs-lookup"><span data-stu-id="cd777-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="cd777-144">사용자 및 그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="cd777-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="cd777-145">자동 등록을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="cd777-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="cd777-146">회사 Wi-Fi 연결에 대 한 Wi-Fi 인증서 및 프로필을 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="cd777-147">LOB (기간 업무) 앱 패키지를 업로드 하 고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="cd777-148">설치 Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="cd777-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="cd777-149">키오스크 모드를 구성 하는 방법 (옵션)</span><span class="sxs-lookup"><span data-stu-id="cd777-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="cd777-150">WDAC를 구성 하는 방법 (옵션).</span><span class="sxs-lookup"><span data-stu-id="cd777-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="cd777-151">배포</span><span class="sxs-lookup"><span data-stu-id="cd777-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="cd777-152">장치 및 MDM을 통해 등록의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="cd777-153">Wi-Fi 인증서의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="cd777-154">LOB 앱 설치의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="cd777-155">제작 및 운영을 통해 가이드의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="cd777-156">유지 관리</span><span class="sxs-lookup"><span data-stu-id="cd777-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="cd777-157">HoloLens 2를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="cd777-158">가이드를 업데이트 하는 방법 (스토어 앱).</span><span class="sxs-lookup"><span data-stu-id="cd777-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="cd777-159">LOB 앱을 업데이트 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="cd777-160">개발 계획.</span><span class="sxs-lookup"><span data-stu-id="cd777-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="cd777-161">지원 계획을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="cd777-162">장치 관리 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cd777-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="cd777-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cd777-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="cd777-164">회사에 연결 된 배포-준비</span><span class="sxs-lookup"><span data-stu-id="cd777-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
