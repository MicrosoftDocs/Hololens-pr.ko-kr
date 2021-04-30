---
title: 여러 사람과 HoloLens 공유
description: 여러 Azure Active Directory 계정이 나 단일 계정을 사용 하는 여러 사용자가 공유 하도록 HoloLens를 구성할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309549"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="6925e-103">여러 사람과 HoloLens 공유</span><span class="sxs-lookup"><span data-stu-id="6925e-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="6925e-104">한 HoloLens를 많은 사용자와 공유 하거나 여러 사람이 HoloLens 장치 집합을 공유 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="6925e-105">이 문서에서는 장치를 공유할 수 있는 여러 가지 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="6925e-106">각자의 계정을 사용 하 여 여러 사람과 공유</span><span class="sxs-lookup"><span data-stu-id="6925e-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="6925e-107">**필수 구성 요소**: HoloLens 장치에서 Windows 10 버전 1803 이상을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="6925e-108">HoloLens (첫 번째 gen)도 [비즈니스용 Windows Holographic로 업그레이드](hololens-upgrade-enterprise.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="6925e-109">사용자가 자신의 고유한 Azure Active Directory (Azure AD) 계정을 사용 하는 경우 여러 사용자가 장치에서 고유한 사용자 설정 및 사용자 데이터를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="6925e-110">여러 사람이 HoloLens에서 자신의 계정을 사용할 수 있도록 하려면 다음 단계를 수행 하 여 구성 하세요.</span><span class="sxs-lookup"><span data-stu-id="6925e-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="6925e-111">장치에서 Windows 10 버전 1803 이상을 실행 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="6925e-112">HoloLens (첫 번째 gen) 장치를 사용 하는 경우 [Windows Holographic For Business로 장치를 업그레이드](hololens1-upgrade-enterprise.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="6925e-113">장치를 설정 하는 경우 **내 회사 또는 학교 소유의 회사 또는 학교** 를 선택 하 고 Azure AD 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="6925e-114">설치를 완료 한 후 계정 설정 (**설정**  >  **계정**)에 **다른 사용자가** 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="6925e-115">HoloLens를 사용 하기 위해 각 사용자는 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="6925e-116">다른 사용자가 장치를 사용 하 고 있는 경우 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="6925e-117">전원 단추를 한 번 눌러 대기로 이동한 다음 전원 단추를 다시 클릭 하 여 잠금 화면으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="6925e-118">HoloLens 2 사용자가 시작 메뉴에서 사용자 타일을 선택 하 여 현재 사용자를 로그 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="6925e-119">Azure AD 계정 자격 증명을 사용 하 여 장치에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="6925e-120">장치를 처음 사용 하는 경우 HoloLens를 사용자의 눈에 맞게 [조정](hololens-calibration.md) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="6925e-121">장치 사용자 목록을 보거나 장치에서 사용자를 제거 하려면 **설정**  >  **계정**  >  **다른 사용자** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="6925e-122">동일한 계정을 사용 하 여 여러 사람과 공유</span><span class="sxs-lookup"><span data-stu-id="6925e-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="6925e-123">여러 사용자가 단일 사용자 계정을 사용 하는 동안 HoloLens 장치를 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="6925e-124">**HoloLens 2에서** 새 사용자가 처음으로 장치를 처음으로 배치 하는 경우 (동일한 계정에 로그인 된 상태를 유지 하는 동안), 장치는 새 사용자에 게 보기 환경을 신속 하 게 보정 하 고 개인 설정 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="6925e-125">장치에서 보정 정보를 저장할 수 있으므로 나중에 장치는 각 사용자의 보기 환경에 대 한 품질 및 편안 함을 자동으로 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="6925e-126">사용자는 장치를 다시 보정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="6925e-127">**HoloLens (첫 번째 gen)에서** 계정을 공유 하는 사용자는 설정 앱에서 보정을 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6925e-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="6925e-128">[보정](hololens-calibration.md)에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6925e-128">Read more about [calibration](hololens-calibration.md).</span></span>
