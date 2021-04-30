---
title: 원격 지원에 대 한 클라우드 연결 HoloLens 2 개요
description: Dynamics 365 원격 지원을 사용 하 여 클라우드 연결 네트워크를 통해 HoloLens 2 장치를 등록 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309111"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="b6ffc-104">배포 가이드-클라우드 연결 HoloLens 2 (원격 지원 포함)-개요</span><span class="sxs-lookup"><span data-stu-id="b6ffc-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="b6ffc-105">이 가이드를 통해 IT 전문가는 Dynamics 365 원격 지원을 사용 하도록 준비 된 상태에서 조직에 연결 된 장치 클라우드가 있는 전체 목표를 사용 하 여 조직에 Microsoft HoloLens 2 장치를 계획 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="b6ffc-106">이는 다양 한 HoloLens 2 사용 사례에서 조직의 개념 증명 배포를 위한 모델 역할을 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="b6ffc-107">이 가이드에서는 장치를 장치 관리에 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설치 시 원격 지원을 즉시 사용할 수 있는지 확인 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="b6ffc-108">이렇게 하려면 HoloLens 2를 사용 하 여 대규모로 배포를 달성 하는 데 필요한 인프라의 중요 한 부분을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![클라우드 연결 배너](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a><span data-ttu-id="b6ffc-110">이 가이드의 내용</span><span class="sxs-lookup"><span data-stu-id="b6ffc-110">In this Guide</span></span>

<span data-ttu-id="b6ffc-111">이 가이드에는 HoloLens 장치에서 조직 내에 원격 지원을 설정 하는 구체적인 목표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="b6ffc-112">이 목표를 달성 하는 데 필요한 필요성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="b6ffc-113">이러한 목표에 초점을 유지 하기 위해이 배포를 최적화 하거나를 구성 하는 데 필요한 항목을 줄이기 위해 특정 준비 및 구성이 미리 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="b6ffc-114">이러한 선택 항목에 대 한 알림이 표시 되며 비즈니스 요구에 따라 배포를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="b6ffc-115">[시나리오 a: 클라우드 연결 장치에 배포](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)하는 것과 유사한 설정입니다 .이는 다음과 같은 개념 증명 배포의 여러 가지 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="b6ffc-116">일반적으로 인터넷 및 클라우드 서비스에 대 한 Wi-Fi 네트워크가 완전히 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="b6ffc-117">MDM 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="b6ffc-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="b6ffc-118">사용자가 자신의 회사 계정 (Azure AD)으로 로그인</span><span class="sxs-lookup"><span data-stu-id="b6ffc-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="b6ffc-119">지원 되는 장치 당 단일 또는 여러 사용자</span><span class="sxs-lookup"><span data-stu-id="b6ffc-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="b6ffc-120">다양 한 수준의 장치 잠금 구성은 특정 사용 사례에 따라 완전히 열린 앱에서 단일 앱 키오스크까지 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![클라우드 연결 시나리오](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="b6ffc-122">이 가이드에서는 다른 장치 제한 사항 또는 구성이 적용 되지 않지만, 완료 한 후에는 이러한 옵션을 탐색 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="b6ffc-123">원격 지원에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b6ffc-123">Learn about Remote Assist</span></span>

<span data-ttu-id="b6ffc-124">원격 지원을 통해 공동 유지 관리 및 복구, 원격 검사 뿐만 아니라 기술 자료 공유 및 교육을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="b6ffc-125">여러 역할 및 위치에 있는 사용자를 연결 하 여 원격 지원을 사용 하는 기술자는 Microsoft 팀의 원격 협력자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="b6ffc-126">동일한 위치에서 t를&#39;하지 않는 경우에도 비디오, 스크린샷 및 주석을 결합 하 여 실시간으로 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="b6ffc-127">원격 협력자는 참조 이미지, 계통도 및 기타 유용한 정보를 삽입할 수 있습니다. 기술자는이에 대 한 작업을 수행 하는 동시에, HoloLens를 사용 하 여 작업 하는 동안 계통도를 참조할 수 있도록&#39;의 실제 공간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="b6ffc-128">이 가이드에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-128">In this guide you will:</span></span>

<span data-ttu-id="b6ffc-129">준비:</span><span class="sxs-lookup"><span data-stu-id="b6ffc-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="b6ffc-130">HoloLens 2 장치에 대 한 인프라 essentials에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="b6ffc-131">Azure AD에 대해 자세히 알아보고,&#39;없는 경우 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="b6ffc-132">Id 관리 및 Azure AD 계정을 최적으로 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="b6ffc-133">MDM에 대해 자세히 알아보고 아직 준비 된&#39;없는 경우 Intune을 사용 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="b6ffc-134">원격 지원의 네트워킹 요구 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="b6ffc-135">필요에 따라 조직 리소스에 연결할 VPN</span><span class="sxs-lookup"><span data-stu-id="b6ffc-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="b6ffc-136">구성:</span><span class="sxs-lookup"><span data-stu-id="b6ffc-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="b6ffc-137">사용자 및 그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="b6ffc-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="b6ffc-138">Azure AD 내에서 자동 등록을 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="b6ffc-139">응용 프로그램 라이선스를 할당 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="b6ffc-140">배포:</span><span class="sxs-lookup"><span data-stu-id="b6ffc-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="b6ffc-141">HoloLens 2를 설정 하 고 등록의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="b6ffc-142">유효성 검사 원격 지원 전화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="b6ffc-143">유지 관리:</span><span class="sxs-lookup"><span data-stu-id="b6ffc-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="b6ffc-144">Microsoft Store 앱을 사용 하 여 원격 지원을 업데이트 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="b6ffc-145">지원 계획을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="b6ffc-146">개발 계획.</span><span class="sxs-lookup"><span data-stu-id="b6ffc-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="b6ffc-147">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b6ffc-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6ffc-148">클라우드 연결 배포-준비</span><span class="sxs-lookup"><span data-stu-id="b6ffc-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

