---
title: 상용 환경에서 HoloLens 2 배포 계획
description: 인프라, azure active directory 및 모바일 장치 관리를 포함 하 여 엔터프라이즈 환경에서 HoloLens를 배포 하 고 관리 하기 위한 핵심 요구 사항에 대해 알아봅니다.
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
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639083"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="25a37-103">상용 환경에서 HoloLens 2 배포 계획</span><span class="sxs-lookup"><span data-stu-id="25a37-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="25a37-104">개요</span><span class="sxs-lookup"><span data-stu-id="25a37-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="25a37-105">이 개요는 IT 전문가가 조직 내에서 Microsoft HoloLens 2 장치를 배포 및 관리 하기 위한 고려 사항을 이해 하는 데 도움을 주기 위해 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="25a37-106">장치 최종 사용자의 경우 시작 하는 데 [사용할 수 있는 HoloLens 2 준비](hololens2-setup.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25a37-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="25a37-107">HoloLens 2는 강력 하 고 유연 하며 기본 제공 되는 모바일 장치 및 앱 관리 기술로 조직을 제공 하는 Windows 10 Holographic에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="25a37-108">Windows 10 Holographic는 회사에서 장치, 데이터 및 앱에 대 한 제어를 제공 하는 종단 간 장치 수명 주기 관리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="25a37-109">HoloLens 2는 포괄적인 모바일 장치 관리 솔루션을 사용 하 여 장치 등록, 구성 및 응용 프로그램 관리에서 유지 관리 및 사용 중지에 이르기까지 표준 수명 주기 방식에 쉽게 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="25a37-110">다음 단계와 비디오는 조직 내에서 채택을 HoloLens 2 하는 과정을 안내 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![1단계](images/1green.png)| <br/> <span data-ttu-id="25a37-112">**[일반적인 배포 시나리오](hololens-requirements.md)**: 배포 시나리오를 이해 하 고 HoloLens 2 장치를 배포 하는 데 필요한 핵심 구성 요소를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![2단계](images/2green.png)| <br/> <span data-ttu-id="25a37-114">**[준비](#prepare)**: HoloLens 2에 필요한 인프라 essentials에 익숙해져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![3단계](images/3green.png) | <br/> <span data-ttu-id="25a37-116">**[구성](#configure)**: 클라우드 기반 배포에 대 한 필수 구성 요소를 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![4단계](images/4green.png) | <br/> <span data-ttu-id="25a37-118">**[배포](#deploy)**: 장치를 배포 하 고 안전 하 고 효율적으로 응용 프로그램을 배포 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![5단계](images/5green.png) | <br/> <span data-ttu-id="25a37-120">**[유지 관리](#maintain)**: HoloLens 2 장치 상태를 적절 하 게 유지 관리 하 고 회사 정책을 준수 하는지 확인 하는 데 필요한 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="25a37-121">준비</span><span class="sxs-lookup"><span data-stu-id="25a37-121">Prepare</span></span>

<span data-ttu-id="25a37-122">전체 HoloLens 2 기능 집합을 지 원하는 데 필요한 필수 인프라 서비스에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="25a37-123">구성 요소</span><span class="sxs-lookup"><span data-stu-id="25a37-123">Component</span></span> | <span data-ttu-id="25a37-124">Description</span><span class="sxs-lookup"><span data-stu-id="25a37-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="25a37-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="25a37-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="25a37-126">HoloLens 2에 대 한 id 및 액세스 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="25a37-127">모바일 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="25a37-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="25a37-128">테 넌 트에 연결 된 HoloLens 2 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="25a37-129">Wi-fi 네트워크</span><span class="sxs-lookup"><span data-stu-id="25a37-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="25a37-130">Wi-Fi를 사용할 수 있으며 장치를 인터넷에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="25a37-131">구성</span><span class="sxs-lookup"><span data-stu-id="25a37-131">Configure</span></span>

<span data-ttu-id="25a37-132">Intune 및 Autopilot를 사용 하 여 조직의 Azure AD 테 넌 트 및 MDM에 HoloLens 2를 등록 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="25a37-133">구성 요소</span><span class="sxs-lookup"><span data-stu-id="25a37-133">Component</span></span> | <span data-ttu-id="25a37-134">Description</span><span class="sxs-lookup"><span data-stu-id="25a37-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="25a37-135">자동 등록</span><span class="sxs-lookup"><span data-stu-id="25a37-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="25a37-136">초기 로그인 후 장치는 Azure AD에 자동으로 등록 되 고 MDM에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="25a37-137">응용 프로그램 라이선스</span><span class="sxs-lookup"><span data-stu-id="25a37-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="25a37-138">사용자, 사용자 그룹 또는 장치 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="25a37-139">Azure 사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="25a37-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="25a37-140">HoloLens 2에 대 한 구성과 라이선스를 할당 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="25a37-141">배포</span><span class="sxs-lookup"><span data-stu-id="25a37-141">Deploy</span></span>

<span data-ttu-id="25a37-142">HoloLens 2 장치를 배포 하 고 구성의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="25a37-143">구성 요소</span><span class="sxs-lookup"><span data-stu-id="25a37-143">Component</span></span> | <span data-ttu-id="25a37-144">Description</span><span class="sxs-lookup"><span data-stu-id="25a37-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="25a37-145">등록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="25a37-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="25a37-146">장치가 설정 또는 Azure Portal에서 Azure AD에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="25a37-147">인증서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="25a37-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="25a37-148">설정을 확인 하 고 올바르게 배포 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="25a37-149">앱 설치 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="25a37-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="25a37-150">앱이 있고 HoloLens 2 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="25a37-151">유지 관리</span><span class="sxs-lookup"><span data-stu-id="25a37-151">Maintain</span></span>

<span data-ttu-id="25a37-152">MDM 시스템 또는 Microsoft Store와 함께 비즈니스에 대 한 Windows 업데이트를 사용 하 여 HoloLens 2와 앱의 업데이트를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a37-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="25a37-153">구성 요소</span><span class="sxs-lookup"><span data-stu-id="25a37-153">Component</span></span> | <span data-ttu-id="25a37-154">Description</span><span class="sxs-lookup"><span data-stu-id="25a37-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="25a37-155">업데이트 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="25a37-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="25a37-156">비즈니스에 대 한 Windows 업데이트를 통해 필요에 따라 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="25a37-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="25a37-157">앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="25a37-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="25a37-158">MDM 시스템 또는 Microsoft Store를 통해 구성</span><span class="sxs-lookup"><span data-stu-id="25a37-158">Configure through your MDM system or the Microsoft Store</span></span>
