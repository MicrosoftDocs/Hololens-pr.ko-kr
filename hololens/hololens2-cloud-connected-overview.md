---
title: 배포 가이드 - 원격 지원이 있는 클라우드 연결 HoloLens 2 - 개요
description: 클라우드 연결 네트워크를 통해 HoloLens 장치 등록
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253185"
---
# <span data-ttu-id="cb3f4-104">배포 가이드 - 원격 지원이 있는 클라우드 연결 HoloLens 2 - 개요</span><span class="sxs-lookup"><span data-stu-id="cb3f4-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="cb3f4-105">이 가이드는 IT 전문가가 Dynamics 365 원격 도우미를 사용하여 조직에 클라우드로 연결되는 전체적인 목표를 사용하여 Microsoft HoloLens 2 장치를 계획하고 조직에 배포하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="cb3f4-106">이 모델은 다양한 HoloLens 2 사용 사례에서 조직에 개념 증명 배포를 위한 모델로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="cb3f4-107">이 가이드에서는 디바이스를 장치 관리에 등록하고, 필요한 경우 라이선스를 적용하고, 최종 사용자가 장치 설정 시 원격 지원을 즉시 사용할 수 있는지 검증하는 방법을 다를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="cb3f4-108">이를 위해 HoloLens 2를 통해 대규모로 배포를 구현하는 설정 및 실행에 필요한 인프라의 중요한 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="cb3f4-109">이 가이드의 설명</span><span class="sxs-lookup"><span data-stu-id="cb3f4-109">In this Guide</span></span>

<span data-ttu-id="cb3f4-110">이 가이드는 HoloLens 디바이스에서 조직 내에서 원격 지원을 설정하는 구체적인 목표를 습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="cb3f4-111">이 목표를 달성하는 데 필요한 필요성을 다루게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="cb3f4-112">이 목표에 초점을 맞추기 위해 특정 준비 및 구성은 이 배포에 최적화하거나 구성에 필요한 항목을 줄이기 위해 미리 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="cb3f4-113">이러한 선택 사항을 알리고 비즈니스 요구에 따라 배포를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="cb3f4-114">이 설정은 시나리오 [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)클라우드 연결 장치에 배포와 유사한 설정으로, 다음을 포함할 많은 개념 증명 배포에 좋은 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="cb3f4-115">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="cb3f4-116">MDM 자동 등록을 사용하여 Azure AD 가입 -- MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="cb3f4-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="cb3f4-117">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="cb3f4-118">지원되는 장치당 사용자 한명 또는 여러명</span><span class="sxs-lookup"><span data-stu-id="cb3f4-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="cb3f4-119">완전히 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 다양한 수준의 장치 잠금 구성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![클라우드 연결 시나리오](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="cb3f4-121">이 가이드에서는 다른 장치 제한 또는 구성이 적용되지는 않습니다. 그러나 완료 후 이러한 옵션을 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="cb3f4-122">원격 지원에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="cb3f4-122">Learn about Remote Assist</span></span>

<span data-ttu-id="cb3f4-123">원격 도우미를 사용하면 공동 유지 관리 및 복구, 원격 검사뿐만 아니라 지식 공유 및 교육을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="cb3f4-124">원격 지원을 사용하여 다른 역할 및 위치에 있는 사람을 연결하면 기술자가 Microsoft Teams의 원격 공동 작업자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="cb3f4-125">비디오, 스크린샷 및 주석을 결합하여 동일한 위치에 있지 않은 경우에도 실시간으로 문제를&#39;수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="cb3f4-126">원격 공동 작업자는 HoloLens에서 헤드업 및 핸즈&#39;동안에는 기술자가 물리적 공간을 참조할 수 있도록 참조 이미지, 도형 및 기타 유용한 정보를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="cb3f4-127">이 가이드에서는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-127">In this guide you will:</span></span>

<span data-ttu-id="cb3f4-128">준비:</span><span class="sxs-lookup"><span data-stu-id="cb3f4-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="cb3f4-129">HoloLens 2 디바이스의 인프라 필수 요소에 대해 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="cb3f4-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="cb3f4-130">Azure AD에 대해 자세히 알아보고, 없는 경우 azure AD를&#39;설정하세요.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="cb3f4-131">ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="cb3f4-132">MDM에 대해 자세히 알아보고, 아직 준비되지 않은 경우 Intune을&#39;수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="cb3f4-133">원격 지원의 네트워킹 요구 사항에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="cb3f4-134">선택 사항: 조직 리소스에 연결하기 위한 VPN</span><span class="sxs-lookup"><span data-stu-id="cb3f4-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="cb3f4-135">구성:</span><span class="sxs-lookup"><span data-stu-id="cb3f4-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="cb3f4-136">사용자 및 그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="cb3f4-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="cb3f4-137">Azure AD 내에서 자동 등록을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb3f4-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="cb3f4-138">응용 프로그램 라이선스를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb3f4-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="cb3f4-139">배포:</span><span class="sxs-lookup"><span data-stu-id="cb3f4-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="cb3f4-140">HoloLens 2를 설정하고 등록의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="cb3f4-141">원격 지원 전화를 걸 수 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="cb3f4-142">유지 관리:</span><span class="sxs-lookup"><span data-stu-id="cb3f4-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="cb3f4-143">Microsoft Store 앱을 사용하여 원격 도우미를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb3f4-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="cb3f4-144">지원 계획 수립</span><span class="sxs-lookup"><span data-stu-id="cb3f4-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="cb3f4-145">개발 계획.</span><span class="sxs-lookup"><span data-stu-id="cb3f4-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="cb3f4-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cb3f4-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cb3f4-147">클라우드 연결 배포 - 준비</span><span class="sxs-lookup"><span data-stu-id="cb3f4-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)
