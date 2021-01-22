---
title: 배포 가이드 - 원격 지원으로 클라우드 연결 HoloLens 2 배포 대규모 배포 - 구성
description: 원격 지원을 사용하여 클라우드 연결 네트워크를 통해 대규모로 HoloLens 장치를 등록하는 구성을 설정하는 방법을 자세히 알아보고
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283889"
---
# <span data-ttu-id="8d236-104">구성 - 클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="8d236-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="8d236-105">이 가이드 섹션에서는 테넌트에&#39;설정하는 방법과 Intune 및 원격 지원 둘 다에 대한 라이선스를 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="8d236-106">Azure 사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="8d236-106">Azure Users and Groups</span></span>

<span data-ttu-id="8d236-107">Azure 및 해당 확장에 따라 Intune은 사용자 및 그룹을 사용하여 구성 및 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="8d236-108">이 배포 흐름의 유효성을 검사하고 한 사용자에서 다른 사용자로 원격 지원 전화를 걸 수 있도록&#39;계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="8d236-109">라이선스를 할당하기 위해 단일 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="8d236-110">두 사용자를 동일한 그룹에 가입하고 해당 그룹에 Intune 및 원격 지원에 대한 라이선스를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="8d236-111">사용자 그룹에서&#39;Azure AD 계정에 대한 액세스 권한이 없는 경우 사용할 수 있습니다. 다음은 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="8d236-112">사용자를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="8d236-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="8d236-113">그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="8d236-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="8d236-114">[그룹에 사용자 추가](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) - 그룹을 만들기 위해 만든 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="8d236-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="8d236-115">[사용자 그룹이](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 디바이스에 가입할 수 있도록 Azure AD 구성 - 새 사용자 그룹에 Azure AD에 장치를 등록할 수 있는 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8d236-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <span data-ttu-id="8d236-116">HoloLens 2의 자동 등록</span><span class="sxs-lookup"><span data-stu-id="8d236-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="8d236-117">원활하고 원활한 환경을 제공하기 위해 HoloLens 2 장치에 대해 Azure Active Directory 가입(AADJ) 및 Intune에 자동 등록을 설정하는 것이 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="8d236-118">이렇게 하면 사용자가 OOBE 중에 조직 로그인 자격 증명을 입력하고 Azure AD에 자동으로 등록하고 디바이스를 MDM에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="8d236-119">Microsoft [Endpoint Manager를](https://endpoint.microsoft.com/#home)사용하여 서비스를 선택하고 일부 페이지를 탐색하여 Premium 평가판 다운로드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="8d236-120">자동 등록 P1의 경우 Azure Active Directory Premium 1과 2가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="8d236-121">Intune을 선택하고 자동 등록에 대한 사용자 범위를 선택하고 이전에 만든 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="8d236-122">전체 세부 정보 및 단계는 [Intune에](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)대해 자동 등록을 사용하도록 설정하는 방법에 대한 가이드를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="8d236-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="8d236-123">응용 프로그램 라이선스</span><span class="sxs-lookup"><span data-stu-id="8d236-123">Application Licenses</span></span>

<span data-ttu-id="8d236-124">응용 프로그램 라이선스를 통해 사용자는 앱을 구입한 회사를 설치하거나 무료 평가판에서 앱의 정식 버전으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="8d236-125">응용 프로그램 라이선스는 사용자, 사용자 그룹 또는 장치 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="8d236-126">원격&#39;사용하려면 조직의 사용자에게 원격 지원 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="8d236-127">이 가이드의 목적을 위해 Azure 사용자 및 그룹에서 위에서 만든 사용자 그룹에 원격 지원 라이선스를 [할당합니다.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="8d236-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="8d236-128">라이선스 요구 사항은 사용자가 장치에서 원격 지원 전화를 걸지 또는 Microsoft Teams의 원격 공동 작업자가 될지 여부에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="8d236-129">기본적으로 원격 지원 및 Teams 확인란은 둘 다 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="8d236-130">이 가이드의 목적을 위해 기본 상자를 선택된 채로 두는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="8d236-131">역할당 다양한 [라이선싱 및 제품 요구 사항에 대해 자세히 알아보습니다.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)</span><span class="sxs-lookup"><span data-stu-id="8d236-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="8d236-132">몇 가지 다른 유형의 원격 지원 라이선스가 있으므로 요구에 맞는 라이선스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="8d236-133">라이선스를&#39;수 [있습니다.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="8d236-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="8d236-134">[그룹에 라이선스를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d236-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="8d236-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8d236-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8d236-136">클라우드 연결 배포 - 배포</span><span class="sxs-lookup"><span data-stu-id="8d236-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)