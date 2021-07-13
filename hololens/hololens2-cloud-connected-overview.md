---
title: Remote Assist 클라우드 연결 HoloLens 2 개요
description: Dynamics 365 Remote Assist 사용하여 클라우드 연결 네트워크를 통해 HoloLens 2 디바이스를 등록하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 클라우드 연결, Remote Assist, AAD, Azure AD, MDM, Mobile 장치 관리
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635129"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="bb873-104">배포 가이드 – Remote Assist 있는 클라우드 연결 HoloLens 2 - 개요</span><span class="sxs-lookup"><span data-stu-id="bb873-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="bb873-105">이 가이드는 IT 전문가가 Remote Assist Microsoft HoloLens 2개 디바이스를 계획하고 조직에 배포하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="bb873-106">다양한 HoloLens 2 사용 사례에서 조직에 개념 증명 배포를 위한 모델로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="bb873-107">설정은 시나리오 [A: 클라우드 연결 디바이스에 배포와](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="bb873-108">이 가이드에서는 디바이스를 디바이스 관리에 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 디바이스 설정 시 Remote Assist 즉시 사용할 수 있는지 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="bb873-109">이를 위해 설정하고 실행하는 데 필요한 인프라의 중요한 부분을 살펴보며 HoloLens 2 사용하여 대규모 배포를 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="bb873-110">이 가이드에는 다른 디바이스 제한 또는 구성이 적용되지 않습니다. 그러나 완료한 후에는 이러한 옵션을 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb873-111">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb873-111">Prerequisites</span></span>

<span data-ttu-id="bb873-112">HoloLens 2 배포하려면 다음 인프라가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="bb873-113">그렇지 않은 경우 Azure 및 Intune 설정이 이 가이드에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="bb873-114">이는 [시나리오 A: 클라우드 연결 디바이스에 배포와](/hololens/common-scenarios#scenario-a)유사한 설정으로, 다음을 포함하는 여러 개념 증명 배포에 적합한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="bb873-115">Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="bb873-116">MDM 자동 등록을 사용하여 Azure AD 조인 -- MDM(Intune) 관리</span><span class="sxs-lookup"><span data-stu-id="bb873-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="bb873-117">사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="bb873-118">디바이스당 단일 또는 여러 사용자가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="클라우드 연결 시나리오" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="bb873-120">Remote Assist 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="bb873-120">Learn about Remote Assist</span></span>

<span data-ttu-id="bb873-121">Remote Assist 통해 공동 유지 관리 및 복구, 원격 검사, 지식 공유 및 학습이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="bb873-122">다른 역할 및 위치에 있는 사람들을 연결하여 Remote Assist 사용하는 기술자는 Microsoft Teams 원격 협력자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="bb873-123">비디오, 스크린샷 및 주석을 결합하여 동일한 위치에 있지 않은 경우에도 실시간으로 문제를 해결할&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="bb873-124">원격 협력자는 기술&#39;물리적 공간에 참조 이미지, 도형 및 기타 유용한 정보를 삽입할 수 있으므로 HoloLens 헤드업 및 실습을 진행하면서 도형을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="bb873-125">Remote Assist 라이선스 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb873-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="bb873-126">Azure AD 계정(구독 구매 및 라이선스 할당에 필요)</span><span class="sxs-lookup"><span data-stu-id="bb873-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="bb873-127">[Remote Assist 구독(또는](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) [Remote Assist 평가판)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="bb873-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="bb873-128">Dynamics 365 Remote Assist 사용자</span><span class="sxs-lookup"><span data-stu-id="bb873-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="bb873-129">Remote Assist 라이선스</span><span class="sxs-lookup"><span data-stu-id="bb873-129">Remote Assist license</span></span>
- <span data-ttu-id="bb873-130">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="bb873-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="bb873-131">Microsoft Teams 사용자</span><span class="sxs-lookup"><span data-stu-id="bb873-131">Microsoft Teams user</span></span>

- <span data-ttu-id="bb873-132">[freemium](https://products.office.com/microsoft-teams/free)을 Microsoft Teams 또는 Teams.</span><span class="sxs-lookup"><span data-stu-id="bb873-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="bb873-133">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="bb873-133">Network connectivity</span></span>

<span data-ttu-id="bb873-134">이 [테넌트 간 시나리오를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)구현하려는 경우 Information Barriers 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="bb873-135">Information Barrier 라이선스가 필요한지 확인하려면 [이 문서를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb873-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="bb873-136">이 가이드에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-136">In this guide you will:</span></span>

<span data-ttu-id="bb873-137">준비:</span><span class="sxs-lookup"><span data-stu-id="bb873-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bb873-138">HoloLens 2 디바이스의 인프라 필수 요소에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="bb873-139">Azure AD에 대해 자세히 알아보고, Azure AD가&#39;없는 경우 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="bb873-140">ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="bb873-141">MDM에 대해 자세히 알아보고, 준비되지 않은 경우 intune을&#39;설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="bb873-142">Remote Assist 네트워킹 요구 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="bb873-143">선택 사항: 조직 리소스에 연결하는 VPN</span><span class="sxs-lookup"><span data-stu-id="bb873-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="bb873-144">구성:</span><span class="sxs-lookup"><span data-stu-id="bb873-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bb873-145">사용자 및 그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="bb873-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="bb873-146">Azure AD 내에서 자동 등록을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bb873-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="bb873-147">애플리케이션 라이선스를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="bb873-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="bb873-148">배포:</span><span class="sxs-lookup"><span data-stu-id="bb873-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bb873-149">HoloLens 2 설정하고 등록의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="bb873-150">Remote Assist 호출할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="bb873-151">유지 관리:</span><span class="sxs-lookup"><span data-stu-id="bb873-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bb873-152">Microsoft Store 앱을 사용하여 Remote Assist 업데이트하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="bb873-153">지원 계획 수립</span><span class="sxs-lookup"><span data-stu-id="bb873-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="bb873-154">개발 계획.</span><span class="sxs-lookup"><span data-stu-id="bb873-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="bb873-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bb873-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bb873-156">클라우드 연결 배포 - 준비</span><span class="sxs-lookup"><span data-stu-id="bb873-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

