---
title: 전체 할당된 액세스
description: 전체 할당된 액세스 키오스크에 OMA-URI를 사용하는 방법 안내
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, 할당된 액세스, 키오스크
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c2be1123d0e8a09d6955fb6e5da782daebc96bcf
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052627"
---
# <span data-ttu-id="58fa1-104">전체 할당된 액세스 - 키오스크</span><span class="sxs-lookup"><span data-stu-id="58fa1-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="58fa1-105">이 기능은 시스템 수준에서 적용되고, 시스템의 ID에 대한 선호도가 없으며, 장치에 로그인하는 모든 사용자에게 적용되는 복수 앱 키오스크 모드로 HoloLens 2 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="58fa1-106">이 기능은 현재 Windows 참가자 빌드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="58fa1-107">HoloLens 릴리스로 일반에 제공되기 전에 이 기능을 시험삼아 사용해 보려면 [Windows 참가자](hololens-insider.md) 빌드에 대해 자세히 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="58fa1-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="58fa1-108">Intune에서 이 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="58fa1-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="58fa1-109">"<!-"(으)로 표시된 영역에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="58fa1-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="58fa1-110">이러한 영역을 사용하려면 기본 설정에 따라 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="58fa1-111">다음과 같은 방법으로 사용자 지정 OMA URI 장치 구성 프로필을 만들어 HoloLens 장치 그룹에 적용합니다. ![Intune에서 전체 할당된 액세스 OMA-URI</span><span class="sxs-lookup"><span data-stu-id="58fa1-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="58fa1-112">값을 업데이트하고 다음 콘텐츠를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-112">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="58fa1-113">Windows 구성 디자이너에서 이 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="58fa1-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="58fa1-114">XML 파일 형식으로 앞서 설명한 XML BLOB를 업데이트 및 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="58fa1-115">[프로비전 패키지를 사용하여 단일 앱 또는 복수 앱 키오스크 설정](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)의 단계, 특히 "프로비전</span><span class="sxs-lookup"><span data-stu-id="58fa1-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="58fa1-116">패키지 2단계 - 프로비전 패키지에 키오스크 구성 XML 파일 추가" 부분을 따르고 이전 단계에서 저장한 XML 파일을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="58fa1-117">전역이 모든 사용자에게 적용되고 별도의 구성이 하나의 AAD 계정 또는 AAD 그룹에 적용되는 구성을 만들 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="58fa1-117">Can I create a configuration where global applies to everyone and separate configuration applies to 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="58fa1-118">예. 아래의 XML BLOB 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58fa1-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="58fa1-119">로그인한 사용자의 특정 프로필을 찾을 수 없는 경우 전체 할당된 액세스 프로필이 HoloLens에 적용되어 로그인한 사용자에 대한 기본 키오스크 모드 구성으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="58fa1-120">다음은 사용할 XML BLOB의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="58fa1-121"><!- 강조 표시된 영역에 유의하세요. 이러한 영역을 사용하려면 기본 설정에 따라 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-121">Please be aware of the highlighted areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="58fa1-122">전체 할당된 액세스 프로필에서 DeviceOwners 제외</span><span class="sxs-lookup"><span data-stu-id="58fa1-122">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="58fa1-123">이 기능을 사용하면 Hololens에서 "[장치 소유자](security-adminless-os.md)"로 간주되는 사용자를 전체 할당된 액세스에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-123">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="58fa1-124">이 기능을 이용하려면 다중 앱 키오스크 구성용 XML BLOB에서 강조 표시된 줄이 추가되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58fa1-124">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
