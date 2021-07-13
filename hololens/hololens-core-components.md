---
title: 상용 환경에서 HoloLens 2 배포 계획
description: 인프라, Azure Active Directory 및 모바일 디바이스 관리를 포함하여 엔터프라이즈 환경에서 HoloLens 배포하고 관리하기 위한 핵심 요구 사항에 대해 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635792"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="63816-103">상용 환경에서 HoloLens 2 배포 계획</span><span class="sxs-lookup"><span data-stu-id="63816-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="63816-104">개요</span><span class="sxs-lookup"><span data-stu-id="63816-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="63816-105">이 개요는 IT 전문가가 조직 내의 Microsoft HoloLens 2개 디바이스를 배포하고 관리하기 위한 고려 사항을 이해할 수 있도록 돕기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="63816-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="63816-106">디바이스 최종 사용자의 경우 [시작하기 위해 사용할 HoloLens 2 준비를 참조하세요.](hololens2-setup.md)</span><span class="sxs-lookup"><span data-stu-id="63816-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="63816-107">HoloLens 2 조직에 강력하고 유연한 기본 제공 모바일 디바이스 및 앱 관리 기술을 제공하는 Windows 10 Holographic 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="63816-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="63816-108">Windows 10 Holographic 엔드 투 엔드 디바이스 수명 주기 관리를 지원하여 회사에서 디바이스, 데이터 및 앱을 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="63816-109">HoloLens 2 디바이스 등록, 구성 및 애플리케이션 관리에서 포괄적인 모바일 디바이스 관리 솔루션을 사용하는 유지 관리 및 사용 중지에 이르기까지 표준 수명 주기 사례에 쉽게 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63816-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="63816-110">다음 단계와 비디오는 조직 내에서 HoloLens 2 채택 프로세스를 안내하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63816-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![1단계](images/1green.png)| <br/> <span data-ttu-id="63816-112">**[일반적인 배포 시나리오:](hololens-requirements.md)** 배포 시나리오를 이해하고 HoloLens 2 디바이스를 배포하는 데 필요한 핵심 구성 요소를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="63816-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![2단계](images/2green.png)| <br/> <span data-ttu-id="63816-114">**[준비:](#prepare)** HoloLens 2 필요한 인프라 필수 요소에 익숙해집니다.</span><span class="sxs-lookup"><span data-stu-id="63816-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![3단계](images/3green.png) | <br/> <span data-ttu-id="63816-116">**[구성:](#configure)** 클라우드 기반 배포를 위한 필수 구성 요소를 구성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="63816-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![4단계](images/4green.png) | <br/> <span data-ttu-id="63816-118">**[배포:](#deploy)** 디바이스를 배포하고 애플리케이션을 안전하고 효율적으로 배포하는 방법을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![5단계](images/5green.png) | <br/> <span data-ttu-id="63816-120">**[유지 관리:](#maintain)** HoloLens 2 디바이스의 상태를 올바르게 유지 관리하고 회사 정책을 준수하는 데 필요한 내용을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="63816-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="63816-121">준비</span><span class="sxs-lookup"><span data-stu-id="63816-121">Prepare</span></span>

<span data-ttu-id="63816-122">전체 HoloLens 2 기능을 지원하는 데 필요한 필수 인프라 서비스에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="63816-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="63816-123">구성 요소</span><span class="sxs-lookup"><span data-stu-id="63816-123">Component</span></span> | <span data-ttu-id="63816-124">Description</span><span class="sxs-lookup"><span data-stu-id="63816-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="63816-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="63816-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="63816-126">HoloLens 2 대한 ID 및 액세스 관리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="63816-127">모바일 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="63816-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="63816-128">테넌트 HoloLens 2 연결된 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="63816-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="63816-129">Wi-Fi 네트워크</span><span class="sxs-lookup"><span data-stu-id="63816-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="63816-130">Wi-Fi 사용할 수 있으며 디바이스를 인터넷에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63816-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="63816-131">구성</span><span class="sxs-lookup"><span data-stu-id="63816-131">Configure</span></span>

<span data-ttu-id="63816-132">조직의 Azure AD 테넌트 및 MDM에 HoloLens 2 등록하고 구성하기 위한 저사양 솔루션으로 Intune 및 Autopilot을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="63816-133">구성 요소</span><span class="sxs-lookup"><span data-stu-id="63816-133">Component</span></span> | <span data-ttu-id="63816-134">Description</span><span class="sxs-lookup"><span data-stu-id="63816-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="63816-135">자동 등록</span><span class="sxs-lookup"><span data-stu-id="63816-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="63816-136">초기 로그인 후 디바이스가 Azure AD에 자동으로 등록되고 MDM에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="63816-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="63816-137">애플리케이션 라이선스</span><span class="sxs-lookup"><span data-stu-id="63816-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="63816-138">사용자, 사용자 그룹 또는 디바이스 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63816-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="63816-139">Azure 사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="63816-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="63816-140">HoloLens 2 대한 구성 및 라이선스를 할당하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63816-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="63816-141">배포</span><span class="sxs-lookup"><span data-stu-id="63816-141">Deploy</span></span>

<span data-ttu-id="63816-142">HoloLens 2 디바이스를 배포하고 해당 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="63816-143">구성 요소</span><span class="sxs-lookup"><span data-stu-id="63816-143">Component</span></span> | <span data-ttu-id="63816-144">Description</span><span class="sxs-lookup"><span data-stu-id="63816-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="63816-145">등록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="63816-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="63816-146">설정 또는 Azure Portal에서 디바이스에 Azure AD가 조인되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="63816-147">인증서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="63816-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="63816-148">설정을 확인하고 올바르게 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="63816-149">앱 설치 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="63816-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="63816-150">앱이 있고 HoloLens 2 작업 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="63816-151">유지 관리</span><span class="sxs-lookup"><span data-stu-id="63816-151">Maintain</span></span>

<span data-ttu-id="63816-152">MDM 시스템 또는 Microsoft Store 함께 비즈니스용 Windows 업데이트를 사용하여 HoloLens 2 및 앱을 업데이트된 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="63816-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="63816-153">구성 요소</span><span class="sxs-lookup"><span data-stu-id="63816-153">Component</span></span> | <span data-ttu-id="63816-154">Description</span><span class="sxs-lookup"><span data-stu-id="63816-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="63816-155">업데이트 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="63816-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="63816-156">비즈니스용 Windows 업데이트를 통해 필요에 따라 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="63816-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="63816-157">앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="63816-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="63816-158">MDM 시스템 또는 Microsoft Store 통해 구성</span><span class="sxs-lookup"><span data-stu-id="63816-158">Configure through your MDM system or the Microsoft Store</span></span>
