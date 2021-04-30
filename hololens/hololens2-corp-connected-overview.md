---
title: 배포 가이드 – Dynamics 365를 사용 하 여 회사에 연결 된 HoloLens 2 가이드-개요
description: 회사 연결 네트워크를 통해 Dynamics 365 가이드를 사용 하 여 HoloLens 2 장치를 등록 하는 방법을 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309775"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="2fad6-104">배포 가이드-Dynamics 365의 회사 연결 HoloLens 2 가이드-개요</span><span class="sxs-lookup"><span data-stu-id="2fad6-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="2fad6-105">이 가이드는 IT 전문가가 Dynamics 365 가이드 (가이드)를 사용 하 여 조직에 Microsoft HoloLens 2 장치를 계획 하 고 배포 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="2fad6-106">이 가이드는 파일럿 및 프로덕션 배포에 적합 하며, [시나리오 B: 조직의 네트워크 내 배포](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 가이드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="2fad6-107">개념 증명을 테스트 한 후이 가이드를 사용 하 여 HoloLens를 조직에 통합 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="2fad6-108">이 가이드에서는 기존 장치 관리에 장치를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설정 후 사용자 지정 lob (기간 업무) 앱을 사용할 365 수 있는지 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2fad6-109">필수 조건</span><span class="sxs-lookup"><span data-stu-id="2fad6-109">Prerequisites</span></span>

<span data-ttu-id="2fad6-110">다음 인프라는 이미 준비 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="2fad6-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2fad6-111">Wi-Fi</span></span>
    - <span data-ttu-id="2fad6-112">내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 및 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스</span><span class="sxs-lookup"><span data-stu-id="2fad6-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="2fad6-113">장치 기반 인증서 인증.</span><span class="sxs-lookup"><span data-stu-id="2fad6-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="2fad6-114">MDM 자동 등록을 사용 하는 Azure Active Directory (Azure AD) 가입 ([AZURE Ad P1 구독](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 필요)</span><span class="sxs-lookup"><span data-stu-id="2fad6-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="2fad6-115">MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="2fad6-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="2fad6-116">하나 이상의 응용 프로그램은 MDM을 통해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="2fad6-117">네트워크</span><span class="sxs-lookup"><span data-stu-id="2fad6-117">Network</span></span> 
    - <span data-ttu-id="2fad6-118">인증서 (SCEP 또는 PKCS)</span><span class="sxs-lookup"><span data-stu-id="2fad6-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="2fad6-119">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="2fad6-119">Proxy configuration</span></span>
- <span data-ttu-id="2fad6-120">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="2fad6-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="2fad6-121">장치당 단일 또는 여러 사용자가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="2fad6-122">특정 사용 사례에 따라 적용 되는 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="2fad6-123">지침 라이선스 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fad6-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="2fad6-124">Azure AD 계정</span><span class="sxs-lookup"><span data-stu-id="2fad6-124">Azure AD account</span></span>
- <span data-ttu-id="2fad6-125">Dynamics 365 가이드 응용 프로그램 PC 및 HoloLens</span><span class="sxs-lookup"><span data-stu-id="2fad6-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="2fad6-126">Dynamics 365 가이드 구독</span><span class="sxs-lookup"><span data-stu-id="2fad6-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="2fad6-127">Microsoft Dataverse (포함)</span><span class="sxs-lookup"><span data-stu-id="2fad6-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="2fad6-128">Power Apps (포함)</span><span class="sxs-lookup"><span data-stu-id="2fad6-128">Power Apps (included)</span></span>
- <span data-ttu-id="2fad6-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="2fad6-129">Power BI Desktop</span></span>
- <span data-ttu-id="2fad6-130">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="2fad6-130">Network Connectivity</span></span>

![Corp 연결 네트워크 다이어그램](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="2fad6-132">배포 단계</span><span class="sxs-lookup"><span data-stu-id="2fad6-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="2fad6-133">준비</span><span class="sxs-lookup"><span data-stu-id="2fad6-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="2fad6-134">HoloLens 2 장치에 대 한 인프라 essentials에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="2fad6-135">Azure AD에 대 한 자세한 정보를 확인 하 고 없는 경우 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="2fad6-136">Id 관리 및 Azure AD 계정을 최적으로 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="2fad6-137">MDM에 대해 자세히 알아보고 아직 준비 하지 않은 경우 Intune을 사용 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="2fad6-138">인증서 기반 Wi-fi에 익숙해져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="2fad6-139">프록시를 숙지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="2fad6-140">Lob (기간 업무) 앱을 사용 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="2fad6-141">조직에서 가이드를 사용할 수 있는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2fad6-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="2fad6-142">구성</span><span class="sxs-lookup"><span data-stu-id="2fad6-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="2fad6-143">사용자 및 그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="2fad6-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="2fad6-144">자동 등록을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2fad6-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="2fad6-145">회사 Wi-Fi 연결에 대 한 Wi-Fi 인증서 및 프로필을 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="2fad6-146">LOB (기간 업무) 앱 패키지를 업로드 하 고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="2fad6-147">Dynamics 365 가이드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="2fad6-148">키오스크 모드를 구성 하는 방법 (옵션)</span><span class="sxs-lookup"><span data-stu-id="2fad6-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="2fad6-149">WDAC를 구성 하는 방법 (옵션).</span><span class="sxs-lookup"><span data-stu-id="2fad6-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="2fad6-150">배포</span><span class="sxs-lookup"><span data-stu-id="2fad6-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="2fad6-151">장치 및 MDM을 통해 등록의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="2fad6-152">Wi-Fi 인증서의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="2fad6-153">LOB 앱 설치의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="2fad6-154">제작 및 운영을 통해 가이드의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="2fad6-155">유지 관리</span><span class="sxs-lookup"><span data-stu-id="2fad6-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="2fad6-156">HoloLens 2를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="2fad6-157">가이드를 업데이트 하는 방법 (스토어 앱).</span><span class="sxs-lookup"><span data-stu-id="2fad6-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="2fad6-158">LOB 앱을 업데이트 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="2fad6-159">개발 계획.</span><span class="sxs-lookup"><span data-stu-id="2fad6-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="2fad6-160">지원 계획을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="2fad6-161">장치 관리 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2fad6-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="2fad6-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2fad6-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="2fad6-163">회사에 연결 된 배포-준비</span><span class="sxs-lookup"><span data-stu-id="2fad6-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
