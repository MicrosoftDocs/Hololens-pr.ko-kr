---
title: 배포 가이드 – Remote Assist 통해 대규모로 클라우드 연결 HoloLens 2 배포 - 구성
description: Remote Assist 사용하여 클라우드 연결 네트워크를 통해 HoloLens 디바이스를 대규모로 등록하도록 구성을 설정하는 방법을 알아봅니다.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635146"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="4c42f-104">구성 - 클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="4c42f-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="4c42f-105">가이드의 이 섹션에서는 테넌트에서 자동 등록을 설정하는 방법과 Intune 및 Remote Assist 모두에 대한 라이선스를 적용하는 방법을&#39;.</span><span class="sxs-lookup"><span data-stu-id="4c42f-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="4c42f-106">Azure 사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="4c42f-106">Azure Users and Groups</span></span>

<span data-ttu-id="4c42f-107">해당 확장의 Azure 및 Intune은 사용자 및 그룹을 사용하여 구성 및 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="4c42f-108">이 배포 흐름의 유효성을 검사하고 한 사용자에서 다른 사용자로 Remote Assist 호출할 수 있으려면&#39;두 개의 사용자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="4c42f-109">라이선스를 할당하기 위해 단일 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="4c42f-110">두 사용자를 동일한 그룹에 조인하고 Intune 및 Remote Assist 대한 라이선스를 해당 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="4c42f-111">사용자 그룹의 두 Azure AD 계정에 대한 액세스 권한이&#39;없는 경우 다음을 사용할 수 있습니다. 다음은 에 대한 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="4c42f-112">사용자를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="4c42f-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="4c42f-113">그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="4c42f-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="4c42f-114">[그룹에 사용자 추가](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자를 추가하여 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="4c42f-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="4c42f-115">[사용자 그룹이 디바이스에 조인할 수 있도록 Azure AD 구성](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 새 사용자 그룹에 Azure AD에 디바이스를 등록할 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="4c42f-116">HoloLens 2 자동 등록</span><span class="sxs-lookup"><span data-stu-id="4c42f-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="4c42f-117">원활하고 원활한 환경을 위해 HoloLens 2 디바이스에 대한 AADJ(Azure Active Directory 조인) 및 Intune에 자동 등록을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="4c42f-118">이렇게 하면 사용자가 OOBE 중에 조직 로그인 자격 증명을 입력하고 Azure AD에 자동으로 등록하고 디바이스를 MDM에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="4c42f-119">[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)사용하여 서비스를 선택하고 Premium 평가판 받기를 선택할 수 있을 때까지 몇 페이지를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="4c42f-120">자동 등록 P1의 경우 Azure Active Directory Premium 1과 2로 충분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="4c42f-121">Intune을 선택하고 자동 등록에 대한 사용자 범위를 선택하고 이전에 만든 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="4c42f-122">자세한 내용 및 단계는 [Intune에 자동 등록을 사용하도록 설정하는 방법에 대한 가이드를 참조하세요.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="4c42f-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="4c42f-123">애플리케이션 라이선스</span><span class="sxs-lookup"><span data-stu-id="4c42f-123">Application Licenses</span></span>

<span data-ttu-id="4c42f-124">애플리케이션 라이선스를 사용하면 사용자가 회사에서 구매한 앱을 설치하거나 평가판에서 앱의 전체 버전으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="4c42f-125">애플리케이션 라이선스는 사용자, 사용자 그룹 또는 디바이스 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="4c42f-126">조직의 사용자가 Remote Assist 사용하려면 Remote Assist 라이선스가 필요할&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="4c42f-127">이 가이드의 목적을 위해 Azure 사용자 및 그룹 에서 위에서 만든 사용자 그룹에 Remote Assist [라이선스를 할당합니다.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="4c42f-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="4c42f-128">라이선스에 대한 요구 사항은 사용자가 디바이스에서 Remote Assist 전화를 걸거나 Microsoft Teams 원격 협력자가 될 것인지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="4c42f-129">기본적으로 Remote Assist 및 Teams 확인란이 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="4c42f-130">이 가이드에서는 기본 확인란을 선택된 상태로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="4c42f-131">역할당 다양한 [라이선스 및 제품 요구 사항에](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4c42f-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="4c42f-132">몇 가지 유형의 Remote Assist 라이선스가 있으므로 요구 사항에 맞게 올바른 라이선스를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="4c42f-133">[&#39;라이선스를 획득해야](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42f-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="4c42f-134">그룹에 [라이선스를 적용합니다.](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="4c42f-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="4c42f-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4c42f-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4c42f-136">클라우드 연결 배포 - 배포</span><span class="sxs-lookup"><span data-stu-id="4c42f-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)