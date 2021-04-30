---
title: 배포 가이드 – 클라우드로 연결 된 HoloLens 2 배포, 원격 지원-구성
description: 원격 지원을 통해 대규모 클라우드 연결 네트워크를 통해 HoloLens 장치를 등록 하는 구성을 설정 하는 방법에 대해 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309360"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="9b516-104">구성-클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="9b516-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="9b516-105">가이드의이 섹션에서는 테 넌 트에 대 한 자동 등록을 설정 하는 방법 및 Intune 및 원격 지원에 대 한 라이선스를 적용 하는 방법을 설명&#39;.</span><span class="sxs-lookup"><span data-stu-id="9b516-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="9b516-106">Azure 사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="9b516-106">Azure Users and Groups</span></span>

<span data-ttu-id="9b516-107">Azure 및 Intune은이 확장에 의해 사용자 및 그룹을 사용 하 여 구성과 라이선스를 할당 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="9b516-108">이 배포 흐름의 유효성을 검사 하 고 한 사용자에서 다른 사용자에 게 원격 지원을 제공할 수 있도록 하기 위해 두 개의 사용자 계정이 필요&#39;.</span><span class="sxs-lookup"><span data-stu-id="9b516-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="9b516-109">라이선스를 할당 하기 위해 단일 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="9b516-110">두 사용자를 동일한 그룹에 조인 하 고 Intune 및 원격 지원에 대 한 라이선스를 해당 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="9b516-111">사용자 그룹의 두 Azure AD 계정에 대 한 액세스 권한이 이미 있는&#39;없는 경우에는를 사용할 수 있습니다. 다음은에 대 한 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="9b516-112">사용자를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="9b516-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="9b516-113">그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="9b516-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="9b516-114">[그룹에 사용자 추가](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자를 추가 하 여 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="9b516-115">[사용자 그룹이 장치에 연결할 수 있도록 AZURE Ad 구성](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 새 사용자 그룹에 장치를 azure ad에 등록할 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="9b516-116">HoloLens에서 자동 등록 2</span><span class="sxs-lookup"><span data-stu-id="9b516-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="9b516-117">원활한 원활한 환경을 제공 하기 위해 AADJ (Azure Active Directory Join) 및 HoloLens 2 장치에 대 한 Intune에 자동 등록을 설정 하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="9b516-118">이렇게 하면 사용자가 OOBE 중에 조직 로그인 자격 증명을 입력 하 여 Azure AD에 자동으로 등록 하 고 장치를 MDM에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="9b516-119">[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)를 사용 하 여 서비스를 선택 하 고 몇 페이지로 이동 하 여 프리미엄 평가판 가져오기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="9b516-120">자동 등록에 대 한 P1이 충분 한 Azure Active Directory Premium 1 및 2가 있는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="9b516-121">Intune을 선택 하 고 자동 등록에 대 한 사용자 범위를 선택 하 고 이전에 만든 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="9b516-122">전체 세부 정보 및 단계는 [Intune에 대 한 자동 등록을 사용 하도록 설정 하는 방법](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)에 대 한 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b516-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="9b516-123">응용 프로그램 라이선스</span><span class="sxs-lookup"><span data-stu-id="9b516-123">Application Licenses</span></span>

<span data-ttu-id="9b516-124">응용 프로그램 라이선스를 통해 사용자는 회사의 구매한 앱을 설치 하거나 무료 평가판에서 앱의 정식 버전으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="9b516-125">응용 프로그램 라이선스는 사용자, 사용자 그룹 또는 장치 그룹에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="9b516-126">조직의 사용자가 원격 지원을 사용 하려면 원격 지원 라이선스가 필요&#39;.</span><span class="sxs-lookup"><span data-stu-id="9b516-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="9b516-127">이 가이드에서는 [Azure 사용자 및 그룹](hololens2-cloud-connected-configure.md#azure-users-and-groups)에서 앞서 만든 사용자 그룹에 원격 지원 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="9b516-128">라이선스에 대 한 요구 사항은 사용자가 장치에서 원격 지원을 받을 것인지 아니면 Microsoft 팀의 원격 협력자가 될 지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="9b516-129">기본적으로 원격 지원 및 팀 확인란이 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="9b516-130">이 가이드의 목적에 맞게 기본 확인란을 선택 된 상태로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="9b516-131">각 [역할별 라이선스 및 제품 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9b516-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="9b516-132">몇 가지 유형의 원격 지원 라이선스가 있으므로 요구 사항에 맞게 올바른 라이선스를 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="9b516-133">[라이선스를 취득](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)해야&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="9b516-134">[라이선스를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 그룹에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b516-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="9b516-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9b516-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b516-136">클라우드 연결 배포-배포</span><span class="sxs-lookup"><span data-stu-id="9b516-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)