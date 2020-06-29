---
title: HoloLens를 키오스크로 설정
description: 키오스크 구성을 사용 하 여 HoloLens에서 앱을 잠급니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0163e028756743922302b46f04309f3d7f738233
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829313"
---
# <span data-ttu-id="0056f-103">HoloLens를 키오스크로 설정</span><span class="sxs-lookup"><span data-stu-id="0056f-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="0056f-104">장치를 키오스크 모드로 실행 하도록 구성 하 여 HoloLens 장치가 고정 용도의 디바이스 ( *키오스크*이 라고도 함)로 작동 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="0056f-105">키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램 (또는 사용자)을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="0056f-106">키오스크 모드는 HoloLens 장치를 비즈니스 앱으로 전용 또는 앱 데모에서 HoloLens 장치를 사용 하는 데 사용할 수 있는 편리한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="0056f-107">이 문서에서는 HoloLens 디바이스와 관련 된 키오스크 구성의 측면에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="0056f-108">다양 한 유형의 Windows 기반 키오스크 및이를 구성 하는 방법에 대 한 일반적인 내용은 [windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성을](https://docs.microsoft.com/windows/configuration/kiosk-methods)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="0056f-109">키오스크 모드는 사용자가 장치에 로그인 할 때 사용할 수 있는 앱을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="0056f-110">그러나 키오스크 모드는 보안 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="0056f-111">"허용" 된 앱이 허용 되지 않는 다른 앱을 여는 것은 중지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="0056f-112">앱 또는 프로세스를 열지 못하도록 차단 하려면 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 를 사용 하 여 적절 한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>  

<span data-ttu-id="0056f-113">단일 앱 또는 다중 앱 구성에서 키오스크 모드를 사용할 수 있으며, 세 가지 프로세스 중 하나를 사용 하 여 키오스크 구성을 설정 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-113">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="0056f-114">다중 앱 구성을 삭제 하면 할당 된 액세스 기능에서 만든 사용자 잠금 프로필이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-114">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="0056f-115">그러나 모든 정책 변경 사항은 되돌리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-115">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="0056f-116">이러한 정책을 되돌리려면 디바이스를 공장 설정으로 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-116">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="0056f-117">키오스크 배포 계획</span><span class="sxs-lookup"><span data-stu-id="0056f-117">Plan the kiosk deployment</span></span>

### <span data-ttu-id="0056f-118">키오스크 모드 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0056f-118">Kiosk mode requirements</span></span>

<span data-ttu-id="0056f-119">키오스크 모드를 사용 하도록 HoloLens 2 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-119">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="0056f-120">키오스크 모드를 사용 하도록 HoloLens (첫번째 gen) 장치를 구성 하려면 먼저 장치가 Windows 10, 버전 1803 또는 이후 버전을 실행 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-120">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="0056f-121">Windows 장치 복구 도구를 사용 하 여 HoloLens (첫번째 gen) 장치를 기본 빌드로 복구 하거나 최신 업데이트를 설치한 경우 장치를 구성할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-121">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="0056f-122">키오스크 모드에서 실행 되는 장치를 보호 하기 위해 USB 연결과 같은 기능을 해제 하는 장치 관리 정책을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-122">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="0056f-123">또한 업데이트 링 설정을 확인 하 여 업무 시간 동안 자동 업데이트가 발생 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-123">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="0056f-124">단일 앱 키오스크 또는 다중 앱 키오스크 중에서 결정</span><span class="sxs-lookup"><span data-stu-id="0056f-124">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="0056f-125">단일 앱 키오스크는 사용자가 장치에 로그인 할 때 지정 된 앱을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-125">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="0056f-126">Cortana 인 시작 메뉴를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-126">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="0056f-127">HoloLens 2 장치가 [시작](hololens2-basic-usage.md#start-gesture) 제스처에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-127">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="0056f-128">HoloLens (1 gen) 장치가 [블 룸](hololens1-basic-usage.md) 제스처에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-128">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="0056f-129">앱을 하나만 실행할 수 있으므로 사용자는 다른 앱을 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-129">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="0056f-130">다중 앱 키오스크는 사용자가 장치에 로그인 할 때 시작 메뉴를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-130">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="0056f-131">키오스크 구성은 시작 메뉴에서 사용할 수 있는 앱을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-131">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="0056f-132">다중 앱 키오스크를 사용 하 여 사용자에 게 쉽게 이해할 수 있는 환경을 제공 하 고,이를 사용 하는 데 필요한 작업만 표시 하 고, 사용 하지 않아도 되는 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-132">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="0056f-133">다음 표에는 여러 키오스크 모드의 기능 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-133">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="0056f-134">시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="0056f-134">Start menu</span></span> |<span data-ttu-id="0056f-135">빠른 작업 메뉴</span><span class="sxs-lookup"><span data-stu-id="0056f-135">Quick Actions menu</span></span> |<span data-ttu-id="0056f-136">카메라 및 비디오</span><span class="sxs-lookup"><span data-stu-id="0056f-136">Camera and video</span></span> |<span data-ttu-id="0056f-137">Miracast</span><span class="sxs-lookup"><span data-stu-id="0056f-137">Miracast</span></span> |<span data-ttu-id="0056f-138">Cortana</span><span class="sxs-lookup"><span data-stu-id="0056f-138">Cortana</span></span> |<span data-ttu-id="0056f-139">기본 제공 음성 명령</span><span class="sxs-lookup"><span data-stu-id="0056f-139">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="0056f-140">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="0056f-140">Single-app kiosk</span></span> |<span data-ttu-id="0056f-141">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0056f-141">Disabled</span></span> |<span data-ttu-id="0056f-142">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0056f-142">Disabled</span></span>   |<span data-ttu-id="0056f-143">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0056f-143">Disabled</span></span> |<span data-ttu-id="0056f-144">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0056f-144">Disabled</span></span>   |<span data-ttu-id="0056f-145">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0056f-145">Disabled</span></span> |<span data-ttu-id="0056f-146">사용 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="0056f-146">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="0056f-147">다중 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="0056f-147">Multi-app kiosk</span></span> |<span data-ttu-id="0056f-148">설정됨</span><span class="sxs-lookup"><span data-stu-id="0056f-148">Enabled</span></span> |<span data-ttu-id="0056f-149">사용 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="0056f-149">Enabled<sup>2</span></span></sup> |<span data-ttu-id="0056f-150">사용 가능 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="0056f-150">Available<sup>2</span></span></sup> |<span data-ttu-id="0056f-151">사용 가능 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="0056f-151">Available<sup>2</span></span></sup> |<span data-ttu-id="0056f-152">사용 가능한 <sup> 2, 3</span><span class="sxs-lookup"><span data-stu-id="0056f-152">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="0056f-153">사용 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="0056f-153">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="0056f-154"></sup>사용 안 함 기능과 관련 된 1 개의 음성 명령이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-154">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="0056f-155">2 </sup> 이러한 기능을 구성 하는 방법에 대 한 자세한 내용은 [키오스크 앱 선택을](#plan-kiosk-apps)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-155">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="0056f-156">3 </sup> Cortana를 사용할 수 없는 경우에도 기본 제공 음성 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-156">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="0056f-157">다음 표에는 여러 키오스크 모드의 사용자 지원 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-157">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="0056f-158">지원 되는 사용자 유형</span><span class="sxs-lookup"><span data-stu-id="0056f-158">Supported user types</span></span> | <span data-ttu-id="0056f-159">자동 로그인</span><span class="sxs-lookup"><span data-stu-id="0056f-159">Automatic sign-in</span></span> | <span data-ttu-id="0056f-160">여러 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="0056f-160">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="0056f-161">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="0056f-161">Single-app kiosk</span></span> |<span data-ttu-id="0056f-162">AAD (Azure Active Directory) 또는 로컬 계정의 MSA (관리 서비스 계정)</span><span class="sxs-lookup"><span data-stu-id="0056f-162">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="0056f-163">예</span><span class="sxs-lookup"><span data-stu-id="0056f-163">Yes</span></span> |<span data-ttu-id="0056f-164">아니오</span><span class="sxs-lookup"><span data-stu-id="0056f-164">No</span></span> |
|<span data-ttu-id="0056f-165">다중 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="0056f-165">Multi-app kiosk</span></span> |<span data-ttu-id="0056f-166">AAD 계정</span><span class="sxs-lookup"><span data-stu-id="0056f-166">AAD account</span></span> |<span data-ttu-id="0056f-167">아니오</span><span class="sxs-lookup"><span data-stu-id="0056f-167">No</span></span> |<span data-ttu-id="0056f-168">예</span><span class="sxs-lookup"><span data-stu-id="0056f-168">Yes</span></span> |

<span data-ttu-id="0056f-169">이러한 기능을 사용 하는 방법에 대 한 예제는 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-169">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="0056f-170">다음에 단일 앱 키오스크 사용:</span><span class="sxs-lookup"><span data-stu-id="0056f-170">Use a single-app kiosk for:</span></span> |<span data-ttu-id="0056f-171">다음에 대해 다중 앱 키오스크 사용:</span><span class="sxs-lookup"><span data-stu-id="0056f-171">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="0056f-172">새 직원에 대 한 Dynamics 365 가이드만 실행 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-172">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="0056f-173">직원 범위에 대해 가이드 및 원격 지원을 둘 다 실행 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-173">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="0056f-174">사용자 지정 앱만 실행 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-174">A device that runs only a custom app.</span></span> |<span data-ttu-id="0056f-175">사용자 지정 앱만 실행 하 여 대부분의 사용자에 게 키오스크 역할을 하는 장치로, 특정 사용자 그룹에 대 한 표준 장치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-175">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="0056f-176">키오스크 앱 계획</span><span class="sxs-lookup"><span data-stu-id="0056f-176">Plan kiosk apps</span></span>

<span data-ttu-id="0056f-177">키오스크 앱을 선택 하는 방법에 대 한 일반적인 정보는 [할당 된 액세스에 대 한 앱 선택 (키오스크 모드)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)에 대 한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-177">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="0056f-178">Windows Device Portal을 사용 하 여 단일 앱 키오스크를 구성 하는 경우 설정 프로세스 중에 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-178">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="0056f-179">MDM (모바일 디바이스 관리) 시스템 또는 배포 패키지를 사용 하 여 키오스크 모드를 구성 하는 경우 [ASSIGNEDACCESS CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 를 사용 하 여 응용 프로그램을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-179">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="0056f-180">CSP는 [응용 프로그램 사용자 모델 id (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 를 사용 하 여 응용 프로그램을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-180">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="0056f-181">다음 표에는 다중 앱 키오스크에서 사용할 수 있는 일부 응용 프로그램의 AUMIDs가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-181">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!CAUTION]
> <span data-ttu-id="0056f-182">셸 앱을 키오스크 앱으로 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-182">You cannot select the Shell app as a kiosk app.</span></span> <span data-ttu-id="0056f-183">또한 Microsoft Edge, Microsoft Store 또는 파일 탐색기를 키오스크 앱으로 선택 **하지** 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-183">Addition, we recommend that you do **not** select Microsoft Edge, Microsoft Store, or File Explorer as a kiosk app.</span></span>  

<a id="aumids"></a>

|<span data-ttu-id="0056f-184">앱 이름</span><span class="sxs-lookup"><span data-stu-id="0056f-184">App Name</span></span> |<span data-ttu-id="0056f-185">AUMID</span><span class="sxs-lookup"><span data-stu-id="0056f-185">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="0056f-186">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="0056f-186">3D Viewer</span></span> |<span data-ttu-id="0056f-187">Microsoft Microsoft3DViewer _8wekyb3d8bbwe \! Microsoft Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="0056f-187">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="0056f-188">Calendar</span><span class="sxs-lookup"><span data-stu-id="0056f-188">Calendar</span></span> |<span data-ttu-id="0056f-189">windowscommunicationsapps \ _8wekyb3d8bbwe \! windowslive. 일정</span><span class="sxs-lookup"><span data-stu-id="0056f-189">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="0056f-190">카메라 <sup> 1, 2</span><span class="sxs-lookup"><span data-stu-id="0056f-190">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="0056f-191">HoloCamera _cw5n1h2txyewy \! HoloCamera</span><span class="sxs-lookup"><span data-stu-id="0056f-191">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="0056f-192">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="0056f-192">Cortana<sup>3</span></span></sup> |<span data-ttu-id="0056f-193">Microsoft 549981C3F5F10 _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="0056f-193">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="0056f-194">장치 선택기</span><span class="sxs-lookup"><span data-stu-id="0056f-194">Device Picker</span></span> |<span data-ttu-id="0056f-195">HoloDevicesFlow _cw5n1h2txyewy \! HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="0056f-195">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="0056f-196">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="0056f-196">Dynamics 365 Guides</span></span> |<span data-ttu-id="0056f-197">Dynamics365 _8wekyb3d8bbwe \! MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="0056f-197">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="0056f-198">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="0056f-198">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="0056f-199">Microsoft MicrosoftRemoteAssist _8wekyb3d8bbwe \! Microsoft. RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="0056f-199">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="0056f-200">피드백 &nbsp; 허브</span><span class="sxs-lookup"><span data-stu-id="0056f-200">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="0056f-201">Microsoft WindowsFeedbackHub _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="0056f-201">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="0056f-202">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="0056f-202">File Explorer</span></span> |<span data-ttu-id="0056f-203">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="0056f-203">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="0056f-204">Mail</span><span class="sxs-lookup"><span data-stu-id="0056f-204">Mail</span></span> |<span data-ttu-id="0056f-205">microsoft. windowscommunicationsapps_8wekyb3d8bbwe! windowslive</span><span class="sxs-lookup"><span data-stu-id="0056f-205">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="0056f-206">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0056f-206">Microsoft Store</span></span> |<span data-ttu-id="0056f-207">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="0056f-207">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="0056f-208">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="0056f-208">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="0056f-209">영화 및 TV</span><span class="sxs-lookup"><span data-stu-id="0056f-209">Movies & TV</span></span> |<span data-ttu-id="0056f-210">Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="0056f-210">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="0056f-211">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0056f-211">OneDrive</span></span> |<span data-ttu-id="0056f-212">microsoft microsoftskydrive _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="0056f-212">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="0056f-213">사진</span><span class="sxs-lookup"><span data-stu-id="0056f-213">Photos</span></span> |<span data-ttu-id="0056f-214">Microsoft. 사진 \ _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="0056f-214">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="0056f-215">설정</span><span class="sxs-lookup"><span data-stu-id="0056f-215">Settings</span></span> |<span data-ttu-id="0056f-216">HolographicSystemSettings _cw5n1h2txyewy \! 내</span><span class="sxs-lookup"><span data-stu-id="0056f-216">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="0056f-217">팁</span><span class="sxs-lookup"><span data-stu-id="0056f-217">Tips</span></span> |<span data-ttu-id="0056f-218">Microsoft HoloLensTips _8wekyb3d8bbwe \! HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="0056f-218">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="0056f-219">1 </sup> 사진 또는 비디오 캡처를 사용 하도록 설정 하려면 카메라 앱을 키오스크 앱으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-219">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="0056f-220">2 </sup> 카메라 앱을 사용 하도록 설정 하는 경우 다음 조건에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-220">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="0056f-221">빠른 동작 메뉴에는 사진 및 비디오 단추가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-221">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="0056f-222">또한 그림을 조작 하거나 검색할 수 있는 앱 (예: 사진, 메일 또는 OneDrive)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-222">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="0056f-223">3 </sup> Cortana를 키오스크 앱으로 사용 하지 않는 경우에도 기본 제공 음성 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-223">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="0056f-224">그러나 비활성 기능과 관련 된 명령은 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-224">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="0056f-225">4 </sup> Miracast를 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-225">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="0056f-226">Kiosk 앱으로 Miracast를 사용 하도록 설정 하려면 카메라 앱 및 장치 선택기 앱을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-226">To enable Miracast as a kiosk app, enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="0056f-227">사용자 및 장치 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="0056f-227">Plan user and device groups</span></span>

<span data-ttu-id="0056f-228">MDM 환경에서는 그룹을 사용 하 여 장치 구성 및 사용자 액세스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-228">In an MDM environment, you use groups to manage device configurations and user access.</span></span> 

<span data-ttu-id="0056f-229">키오스크 구성 프로필에는 **사용자 로그온 유형** 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-229">The kiosk configuration profile includes the **User logon type** setting.</span></span> <span data-ttu-id="0056f-230">**사용자 로그온 유형은** 추가 하는 앱을 사용할 수 있는 사용자 (또는 사용자가 포함 된 그룹)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-230">**User logon type** identifies the user (or group that contains the users) who can use the app or apps that you add.</span></span> <span data-ttu-id="0056f-231">사용자가 구성 프로필에 포함 되지 않은 계정을 사용 하 여 로그인 하는 경우 해당 사용자는 키오스크에서 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-231">If a user signs in by using an account that is not included in the configuration profile, that user cannot use apps on the kiosk.</span></span>  

> [!NOTE]  
> <span data-ttu-id="0056f-232">단일 앱 키오스크의 **사용자 로그온 유형은** 단일 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-232">The **User logon type** of a single-app kiosk specifies a single user account.</span></span> <span data-ttu-id="0056f-233">키오스크이 실행 되는 사용자 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-233">This is the user context under which the kiosk runs.</span></span> <span data-ttu-id="0056f-234">다중 앱 키오스크의 **사용자 로그온 유형에** 는 키오스크를 사용할 수 있는 하나 이상의 사용자 계정 또는 그룹이 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-234">The **User logon type** of a multi-app kiosk can specify one or more user accounts or groups that can use the kiosk.</span></span>

<span data-ttu-id="0056f-235">키오스크 구성을 장치에 배포 하려면 먼저 디바이스 또는 장치에 로그인 할 수 있는 사용자를 포함 하는 그룹에 키오스크 구성 프로필을 *할당* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-235">Before you can deploy the kiosk configuration to a device, you have to *assign* the kiosk configuration profile to a group that contains the device or a user who can sign in to the device.</span></span> <span data-ttu-id="0056f-236">이 설정은 다음과 같은 동작을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-236">This setting produces behavior such as the following.</span></span>

- <span data-ttu-id="0056f-237">장치가 할당 된 그룹의 구성원 인 경우 사용자가 장치에 처음 로그인 할 때 키오스크 구성이 장치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-237">If the device is a member of the assigned group, the kiosk configuration deploys to the device the first time that any user signs in on the device.</span></span>  
- <span data-ttu-id="0056f-238">장치가 할당 된 그룹의 구성원이 아니지만 해당 그룹의 구성원 인 사용자가 로그인 하면 해당 시간에 키오스크 구성이 디바이스에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-238">If the device is not a member of the assigned group, but a user who is a member of that group signs in, the kiosk configuration deploys to the device at that time.</span></span>

<span data-ttu-id="0056f-239">Intune에서 구성 프로필을 할당 하는 효과에 대 한 자세한 내용은 [Microsoft Intune에서 사용자 및 장치 프로필 할당](https://docs.microsoft.com/intune/configuration/device-profile-assign)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-239">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

> [!NOTE]  
> <span data-ttu-id="0056f-240">다음 예제에서는 다중 앱 키오스크에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-240">The following examples describe multi-app kiosks.</span></span> <span data-ttu-id="0056f-241">단일 앱 키오스크도 비슷한 방식으로 작동 하지만, 키오스크 환경을 제공 하는 사용자 계정은 한 명만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-241">Single-app kiosks behave in a similar manner, but only one user account gets the kiosk experience.</span></span>

**<span data-ttu-id="0056f-242">예제 1</span><span class="sxs-lookup"><span data-stu-id="0056f-242">Example 1</span></span>**

<span data-ttu-id="0056f-243">장치 및 사용자 둘 다에 단일 그룹 (그룹 1)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-243">You use a single group (Group 1) for both devices and users.</span></span> <span data-ttu-id="0056f-244">하나의 장치 및 사용자 A, B, C는이 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-244">One device and users A, B, and C are members of this group.</span></span> <span data-ttu-id="0056f-245">아래와 같이 키오스크 구성 프로필을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-245">You configure the kiosk configuration profile as follows:</span></span>  

- <span data-ttu-id="0056f-246">**사용자 로그온 유형**: 그룹 1</span><span class="sxs-lookup"><span data-stu-id="0056f-246">**User logon type**: Group 1</span></span>
- <span data-ttu-id="0056f-247">**배정 된 그룹**: 그룹 1</span><span class="sxs-lookup"><span data-stu-id="0056f-247">**Assigned group**: Group 1</span></span>

<span data-ttu-id="0056f-248">장치에 먼저 로그인 하는 사용자와 관계 없이 (기본 제공 경험 또는 OOBE를 통해) 키오스크 구성은 장치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-248">Regardless of which user signs on to the device first (and goes through the Out-of-Box Experience, or OOBE), the kiosk configuration deploys to the device.</span></span> <span data-ttu-id="0056f-249">사용자 A, B, C가 모든 장치에 로그인 하 여 키오스크 환경을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-249">Users A, B, and C can all sign in to the device and get the kiosk experience.</span></span>

**<span data-ttu-id="0056f-250">예제 2</span><span class="sxs-lookup"><span data-stu-id="0056f-250">Example 2</span></span>**

<span data-ttu-id="0056f-251">장치를 서로 다른 키오스크 환경을 필요로 하는 두 가지 다른 공급 업체에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-251">You contract out devices to two different vendors who need different kiosk experiences.</span></span> <span data-ttu-id="0056f-252">두 공급 업체 모두 사용자를 보유 하 고 있으며 모든 사용자가 자신의 공급 업체와 다른 공급 업체 로부터 키오스크에 액세스할 수 있도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="0056f-252">Both vendors have users, and you want all the users to have access to kiosks from both their own vendor and the other vendor.</span></span> <span data-ttu-id="0056f-253">다음과 같이 그룹을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-253">You configure groups as follows:</span></span>

- <span data-ttu-id="0056f-254">장치 그룹 1:</span><span class="sxs-lookup"><span data-stu-id="0056f-254">Device Group 1:</span></span>
  - <span data-ttu-id="0056f-255">장치 1 (공급 업체 1)</span><span class="sxs-lookup"><span data-stu-id="0056f-255">Device 1 (Vendor 1)</span></span>
  - <span data-ttu-id="0056f-256">장치 2 (공급 업체 1)</span><span class="sxs-lookup"><span data-stu-id="0056f-256">Device 2 (Vendor 1)</span></span>

- <span data-ttu-id="0056f-257">장치 그룹 2:</span><span class="sxs-lookup"><span data-stu-id="0056f-257">Device Group 2:</span></span>
  - <span data-ttu-id="0056f-258">장치 3 (공급 업체 2)</span><span class="sxs-lookup"><span data-stu-id="0056f-258">Device 3 (Vendor 2)</span></span>
  - <span data-ttu-id="0056f-259">장치 4 (공급 업체 2)</span><span class="sxs-lookup"><span data-stu-id="0056f-259">Device 4 (Vendor 2)</span></span>

- <span data-ttu-id="0056f-260">사용자 그룹:</span><span class="sxs-lookup"><span data-stu-id="0056f-260">User Group:</span></span>
  - <span data-ttu-id="0056f-261">사용자 A (공급 업체 1)</span><span class="sxs-lookup"><span data-stu-id="0056f-261">User A (Vendor 1)</span></span>
  - <span data-ttu-id="0056f-262">사용자 B (공급 업체 2)</span><span class="sxs-lookup"><span data-stu-id="0056f-262">User B (Vendor 2)</span></span>

<span data-ttu-id="0056f-263">다음 설정을 사용 하는 두 개의 키오스크 구성 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-263">You create two kiosk configuration profiles that have the following settings:</span></span>

- <span data-ttu-id="0056f-264">키오스크 프로필 1:</span><span class="sxs-lookup"><span data-stu-id="0056f-264">Kiosk Profile 1:</span></span>
   - <span data-ttu-id="0056f-265">**사용자 로그온 유형**: 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="0056f-265">**User logon type**: User Group</span></span>
   - <span data-ttu-id="0056f-266">**할당 된 그룹**: 장치 그룹 1</span><span class="sxs-lookup"><span data-stu-id="0056f-266">**Assigned group**: Device Group 1</span></span>

- <span data-ttu-id="0056f-267">키오스크 프로필 2:</span><span class="sxs-lookup"><span data-stu-id="0056f-267">Kiosk Profile 2:</span></span>
   - <span data-ttu-id="0056f-268">**사용자 로그온 유형**: 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="0056f-268">**User logon type**: User Group</span></span>
   - <span data-ttu-id="0056f-269">**할당 된 그룹**: 장치 그룹 2</span><span class="sxs-lookup"><span data-stu-id="0056f-269">**Assigned group**: Device Group 2</span></span>

<span data-ttu-id="0056f-270">이러한 구성은 다음과 같은 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-270">These configurations produce the following results:</span></span>

- <span data-ttu-id="0056f-271">사용자가 장치 1 또는 장치 2에 로그인 하면 Intune에서 키오스크 프로필 1을 해당 장치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-271">When any user signs in to Device 1 or Device 2, Intune deploys Kiosk Profile 1 to that device.</span></span>
- <span data-ttu-id="0056f-272">사용자가 장치 3 또는 장치 4에 로그인 하면 Intune에서 키오스크 프로필 2를 해당 장치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-272">When any user signs in to Device 3 or Device 4, Intune deploys Kiosk Profile 2 to that device.</span></span>
- <span data-ttu-id="0056f-273">사용자 A와 사용자 B는 네 가지 장치 중 하나에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-273">User A and user B can sign in to any of the four devices.</span></span> <span data-ttu-id="0056f-274">장치 1 또는 장치 2에 로그인 하는 경우 공급 업체 1 키오스크 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-274">If they sign in to Device 1 or Device 2, they see the Vendor 1 kiosk experience.</span></span> <span data-ttu-id="0056f-275">장치 3 또는 장치 4에 로그인 하는 경우 공급 업체 2 키오스크 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-275">If they sign in to Device 3 or Device 4, they see the Vendor 2 kiosk experience.</span></span>

#### <span data-ttu-id="0056f-276">프로필 충돌</span><span class="sxs-lookup"><span data-stu-id="0056f-276">Profile conflicts</span></span>

<span data-ttu-id="0056f-277">두 개 이상의 키오스크 구성 프로필이 동일한 장치를 대상으로 하는 경우 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-277">If two or more kiosk configuration profiles target the same device, they conflict.</span></span> <span data-ttu-id="0056f-278">Intune 관리 장치의 경우 Intune은 충돌 하는 프로필을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-278">In the case of Intune-managed devices, Intune does not apply any of the conflicting profiles.</span></span>

<span data-ttu-id="0056f-279">키오스크 구성 프로필과 관련 되지 않은 장치 제한과 같은 다른 종류의 프로필 및 정책은 키오스크 구성 프로필과 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-279">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>

### <span data-ttu-id="0056f-280">배포 방법 선택</span><span class="sxs-lookup"><span data-stu-id="0056f-280">Select a deployment method</span></span>

<span data-ttu-id="0056f-281">다음 방법 중 하나를 선택 하 여 키오스크 구성을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-281">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="0056f-282">Microsoft Intune 또는 기타 MDM (모바일 디바이스 관리) 서비스</span><span class="sxs-lookup"><span data-stu-id="0056f-282">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="0056f-283">프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="0056f-283">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="0056f-284">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="0056f-284">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="0056f-285">이 방법을 사용 하려면 디바이스에서 개발자 모드를 사용 하도록 설정 해야 하므로 데모 에서만 사용할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-285">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="0056f-286">다음 표에서는 각 배포 방법의 기능 및 장점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-286">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="0056f-287">Windows Device Portal을 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-287">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="0056f-288">프로비저닝 패키지를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-288">Deploy by using a provisioning package</span></span> |<span data-ttu-id="0056f-289">MDM을 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-289">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="0056f-290">단일 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-290">Deploy single-app kiosks</span></span>   | <span data-ttu-id="0056f-291">예</span><span class="sxs-lookup"><span data-stu-id="0056f-291">Yes</span></span>           | <span data-ttu-id="0056f-292">예</span><span class="sxs-lookup"><span data-stu-id="0056f-292">Yes</span></span>                  | <span data-ttu-id="0056f-293">예</span><span class="sxs-lookup"><span data-stu-id="0056f-293">Yes</span></span>  |
|<span data-ttu-id="0056f-294">다중 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-294">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="0056f-295">아니오</span><span class="sxs-lookup"><span data-stu-id="0056f-295">No</span></span>            | <span data-ttu-id="0056f-296">예</span><span class="sxs-lookup"><span data-stu-id="0056f-296">Yes</span></span>                  | <span data-ttu-id="0056f-297">예</span><span class="sxs-lookup"><span data-stu-id="0056f-297">Yes</span></span>  |
|<span data-ttu-id="0056f-298">로컬 장치에만 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-298">Deploy to local devices only</span></span> | <span data-ttu-id="0056f-299">예</span><span class="sxs-lookup"><span data-stu-id="0056f-299">Yes</span></span>           | <span data-ttu-id="0056f-300">예</span><span class="sxs-lookup"><span data-stu-id="0056f-300">Yes</span></span>                  | <span data-ttu-id="0056f-301">아니오</span><span class="sxs-lookup"><span data-stu-id="0056f-301">No</span></span>   |
|<span data-ttu-id="0056f-302">개발자 모드를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-302">Deploy by using Developer Mode</span></span> |<span data-ttu-id="0056f-303">필수</span><span class="sxs-lookup"><span data-stu-id="0056f-303">Required</span></span>       | <span data-ttu-id="0056f-304">필수 아님</span><span class="sxs-lookup"><span data-stu-id="0056f-304">Not required</span></span>            | <span data-ttu-id="0056f-305">필수 아님</span><span class="sxs-lookup"><span data-stu-id="0056f-305">Not required</span></span>   |
|<span data-ttu-id="0056f-306">AAD (Azure Active Directory)를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-306">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="0056f-307">필수 아님</span><span class="sxs-lookup"><span data-stu-id="0056f-307">Not required</span></span>            | <span data-ttu-id="0056f-308">필수 아님</span><span class="sxs-lookup"><span data-stu-id="0056f-308">Not required</span></span>                   | <span data-ttu-id="0056f-309">필수</span><span class="sxs-lookup"><span data-stu-id="0056f-309">Required</span></span>  |
|<span data-ttu-id="0056f-310">자동으로 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-310">Deploy automatically</span></span>      | <span data-ttu-id="0056f-311">아니오</span><span class="sxs-lookup"><span data-stu-id="0056f-311">No</span></span>            | <span data-ttu-id="0056f-312">아니오</span><span class="sxs-lookup"><span data-stu-id="0056f-312">No</span></span>                   | <span data-ttu-id="0056f-313">예</span><span class="sxs-lookup"><span data-stu-id="0056f-313">Yes</span></span>  |
|<span data-ttu-id="0056f-314">배포 속도</span><span class="sxs-lookup"><span data-stu-id="0056f-314">Deployment speed</span></span>            | <span data-ttu-id="0056f-315">가장 빠른</span><span class="sxs-lookup"><span data-stu-id="0056f-315">Fastest</span></span>       | <span data-ttu-id="0056f-316">빠름</span><span class="sxs-lookup"><span data-stu-id="0056f-316">Fast</span></span>                 | <span data-ttu-id="0056f-317">슬로우</span><span class="sxs-lookup"><span data-stu-id="0056f-317">Slow</span></span> |
|<span data-ttu-id="0056f-318">배율에 배치</span><span class="sxs-lookup"><span data-stu-id="0056f-318">Deploy at scale</span></span> | <span data-ttu-id="0056f-319">권장 되지 않음</span><span class="sxs-lookup"><span data-stu-id="0056f-319">Not recommended</span></span>    | <span data-ttu-id="0056f-320">권장 되지 않음</span><span class="sxs-lookup"><span data-stu-id="0056f-320">Not recommended</span></span>        | <span data-ttu-id="0056f-321">권장 사항</span><span class="sxs-lookup"><span data-stu-id="0056f-321">Recommended</span></span> |

## <span data-ttu-id="0056f-322">Microsoft Intune 또는 기타 MDM을 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정</span><span class="sxs-lookup"><span data-stu-id="0056f-322">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="0056f-323">Microsoft Intune 또는 다른 MDM 시스템을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-323">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="0056f-324">[장치 등록을 준비](#mdmenroll)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-324">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="0056f-325">[키오스크 구성 프로필을 만듭니다](#mdmprofile).</span><span class="sxs-lookup"><span data-stu-id="0056f-325">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="0056f-326">키오스크를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-326">Configure the kiosk.</span></span>
   - <span data-ttu-id="0056f-327">[단일 앱 키오스크에 대 한 설정을 구성](#mdmconfigsingle)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-327">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="0056f-328">[다중 앱 키오스크에 대 한 설정을 구성](#mdmconfigmulti)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-328">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="0056f-329">[키오스크 구성 프로필을 그룹에 할당](#mdmassign)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-329">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="0056f-330">장치를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-330">Deploy the devices.</span></span>
   - <span data-ttu-id="0056f-331">[단일 앱 키오스크 배포](#mdmsingledeploy)</span><span class="sxs-lookup"><span data-stu-id="0056f-331">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="0056f-332">[다중 앱 키오스크 배포](#mdmmultideploy)</span><span class="sxs-lookup"><span data-stu-id="0056f-332">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="0056f-333">MDM, 1 단계 &ndash; 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="0056f-333">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="0056f-334">사용자가 처음 로그인 할 때 HoloLens 장치를 자동으로 등록 하도록 MDM 시스템을 구성 하거나 사용자가 디바이스를 수동으로 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-334">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="0056f-335">또한 디바이스를 Azure AD 도메인에 가입 하 고 해당 그룹에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-335">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="0056f-336">장치를 등록 하는 방법에 대 한 자세한 내용은 [Windows 장치용 MDM 및 Intune 등록 방법](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods) [에서 HoloLens 등록](hololens-enroll-mdm.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-336">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="0056f-337">MDM, 2 단계 &ndash; 키오스크 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="0056f-337">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="0056f-338">[Azure](https://portal.azure.com/) 포털을 열고 Intune 관리자 계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-338">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="0056f-339">**Microsoft Intune**  >  **장치 구성-** 프로필  >  **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-339">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="0056f-340">프로필 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-340">Enter a profile name.</span></span>
1. <span data-ttu-id="0056f-341">**플랫폼**  >  **Windows 10 이상을**선택한 다음 **프로필 형식**  > **장치 제한을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-341">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="0056f-342">키오스크 **구성을**선택  >  **Kiosk**하 고 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-342">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="0056f-343">단일 앱 키오스크를 만들려면 **키오스크 모드**  >  **단일 앱 키오스크**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-343">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="0056f-344">다중 앱 키오스크를 만들려면 **키오스크 모드**  >  **다중 앱 키오스크**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-344">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="0056f-345">키오스크 구성을 시작 하려면 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-345">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="0056f-346">다음 단계는 원하는 키오스크 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-346">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="0056f-347">자세한 내용을 보려면 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-347">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="0056f-348">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="0056f-348">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="0056f-349">다중 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="0056f-349">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="0056f-350">키오스크 구성 프로필을 만드는 방법에 대 한 자세한 내용은 Intune을 [사용 하 여 전용 키오스크로 실행 하기 위한 windows 10 및 Windows 홀로그램 비즈니스 장치 설정을](https://docs.microsoft.com/intune/configuration/kiosk-settings)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-350">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="0056f-351">MDM, 3 단계 (단일 앱) &ndash; 단일 앱 키오스크에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0056f-351">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="0056f-352">이 섹션에서는 단일 앱 키오스크에 필요한 설정을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-352">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="0056f-353">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-353">For more details, see the following articles:</span></span>

- <span data-ttu-id="0056f-354">Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune을 사용 하 여 키오스크 모드를 구성 하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-354">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="0056f-355">Intune의 단일 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [단일 전체 화면 앱 키오스크](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-355">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="0056f-356">다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-356">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="0056f-357">MDM 서비스에서 사용자 지정 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 XML 파일을 만듭니다](#ppkioskconfig).</span><span class="sxs-lookup"><span data-stu-id="0056f-357">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="0056f-358">**사용자 로그온 유형**  >  **로컬 사용자 계정을**선택한 다음 키오스크에 로그인 할 수 있는 로컬 (장치) 계정이 나 Microsoft 계정 (MSA)의 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-358">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="0056f-359">**자동 로그온** 사용자 계정 유형은 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-359">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="0056f-360">**응용 프로그램 종류**  >  **스토어 앱**을 선택한 다음 목록에서 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-360">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="0056f-361">다음 단계는 프로필을 그룹에 [할당](#mdmassign) 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-361">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="0056f-362">MDM, 3 단계 (다중 앱) &ndash; 다중 앱 키오스크에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0056f-362">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="0056f-363">이 섹션에서는 다중 앱 키오스크에 필요한 설정을 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-363">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="0056f-364">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-364">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="0056f-365">Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune을 사용 하 여 키오스크 모드를 구성 하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-365">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="0056f-366">Intune의 다중 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [다중 앱 키오스크](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-366">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="0056f-367">다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-367">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="0056f-368">MDM 서비스에서 사용자 지정 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 XML 파일을 만듭니다](#ppkioskconfig).</span><span class="sxs-lookup"><span data-stu-id="0056f-368">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="0056f-369">XML 파일을 사용 하는 경우 [시작 레이아웃](#start-layout-for-hololens)을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-369">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="0056f-370">선택적으로 Intune 또는 기타 MDM 서비스에서 사용자 지정 시작 레이아웃을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-370">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="0056f-371">자세한 내용은 [MDM (Intune 및 기타)의 시작 레이아웃 파일](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-371">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="0056f-372">**대상 Windows 10의 S 모드 장치**  >  **번호**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-372">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="0056f-373">S 모드는 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-373">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="0056f-374">**사용자 로그온 유형**  >  **Azure AD 사용자 또는 그룹** 또는 **사용자 로그온**  >  에**HoloLens 방문자**를 입력 하 고 하나 이상의 사용자 그룹 또는 계정 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-374">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="0056f-375">**사용자 로그온 유형에** 지정 하는 그룹 또는 계정에 속한 사용자만 키오스크 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-375">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="0056f-376">다음 옵션을 사용 하 여 앱을 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-376">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="0056f-377">업로드 된 lob (기간 업무) 앱을 추가 하려면 **스토어 앱 추가** 를 선택한 다음 원하는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-377">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="0056f-378">AUMID를 지정 하 여 앱을 추가 하려면 **AUMID에서 추가** 를 선택 하 고 앱의 AUMID를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-378">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="0056f-379">사용할 수 있는 AUMIDs 목록 보기</span><span class="sxs-lookup"><span data-stu-id="0056f-379">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="0056f-380">다음 단계는 프로필을 그룹에 [할당](#mdmassign) 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-380">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="0056f-381">MDM, 4 단계 &ndash; 키오스크 구성 프로필을 그룹에 할당</span><span class="sxs-lookup"><span data-stu-id="0056f-381">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="0056f-382">키오스크 구성 프로필의 **지정** 페이지를 사용 하 여 키오스크 구성을 배포할 위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-382">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="0056f-383">가장 간단한 경우에는 디바이스에서 MDM에 등록할 때 HoloLens 장치를 포함할 그룹에 키오스크 구성 프로필을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-383">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="0056f-384">MDM, 5 단계 (단일 앱) &ndash; 단일 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-384">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="0056f-385">MDM 시스템을 사용 하는 경우 OOBE 중에 MDM에서 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-385">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="0056f-386">OOBE가 완료 된 후에는 장치에 간편 하 게 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-386">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="0056f-387">OOBE 중에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-387">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="0056f-388">키오스크 구성 프로필에 지정한 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-388">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="0056f-389">장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-389">Enroll the device.</span></span> <span data-ttu-id="0056f-390">키오스크 구성 프로필이 할당 된 그룹에 장치가 추가 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-390">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="0056f-391">OOBE가 완료 될 때까지, 스토어 앱을 다운로드 및 설치 하 고 정책을 적용할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-391">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="0056f-392">그런 다음 장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-392">Then restart the device.</span></span>

<span data-ttu-id="0056f-393">다음에 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-393">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="0056f-394">이 시점에서 키오스크 구성이 표시 되지 않으면 [과제 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-394">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="0056f-395">MDM, 5 단계 (다중 앱) &ndash; 다중 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="0056f-395">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="0056f-396">MDM 시스템을 사용 하는 경우 Azure AD 테 넌 트에 디바이스를 연결 하 고 OOBE 중에 MDM에서 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-396">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="0056f-397">필요에 따라 사용자에 게 등록 정보를 제공 하 여 OOBE 프로세스 중에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-397">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="0056f-398">사용자를 포함 하는 그룹에 키오스크 구성 프로필을 할당 한 경우 해당 사용자 계정 중 하나가 장치에 로그인 하는 첫 번째 계정 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-398">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="0056f-399">OOBE 중에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-399">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="0056f-400">**사용자 로그온 유형** 그룹에 속하는 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-400">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="0056f-401">장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-401">Enroll the device.</span></span>
1. <span data-ttu-id="0056f-402">키오스크 구성 프로필의 일부인 앱을 다운로드 하 여 설치 하는 경우를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-402">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="0056f-403">또한 정책이 적용 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-403">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="0056f-404">OOBE가 완료 되 면 Microsoft store 또는 테스트용 로드를 통해 추가 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-404">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="0056f-405">장치가 속한 그룹의 [필수 앱](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 이 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-405">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="0056f-406">설치가 완료 되 면 장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-406">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="0056f-407">다음에 **사용자 로그온 유형에**속하는 계정을 사용 하 여 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-407">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="0056f-408">이 시점에서 키오스크 구성이 표시 되지 않으면 [과제 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-408">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="0056f-409">배포 패키지를 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정</span><span class="sxs-lookup"><span data-stu-id="0056f-409">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="0056f-410">배포 패키지를 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-410">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="0056f-411">[키오스크 구성을 정의 하는 XML 파일](#ppkioskconfig)( [시작 레이아웃](#start-layout-for-hololens)포함)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-411">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="0056f-412">배포 패키지에 XML 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-412">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="0056f-413">HoloLens에 프로비저닝 패키지를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-413">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="0056f-414">프로비저닝 패키지, 1 단계 &ndash; 키오스크 구성 XML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="0056f-414">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="0056f-415">일반 지침에 따라 다음을 제외 하 고 [Windows 데스크톱용 키오스크 구성 XML 파일을 만듭니다](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).</span><span class="sxs-lookup"><span data-stu-id="0056f-415">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="0056f-416">클래식 Windows 응용 프로그램 (Win32)을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-416">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="0056f-417">HoloLens는 이러한 응용 프로그램을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-417">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="0056f-418">HoloLens 용 [자리 표시자 시작 레이아웃 XML](#start-layout-for-hololens) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-418">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="0056f-419">선택 사항: 키오스크 구성에 게스트 액세스 추가</span><span class="sxs-lookup"><span data-stu-id="0056f-419">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="0056f-420">선택 사항: 키오스크 구성에 게스트 액세스 추가</span><span class="sxs-lookup"><span data-stu-id="0056f-420">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="0056f-421">[XML 파일의 **Configs** 섹션](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)에서 게스트가 키오스크를 사용할 수 있도록 **방문자** 라는 특별 한 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-421">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="0056f-422">방문객이 **방문자** 특별 그룹을 지원 하도록 구성 된 경우 "**게스트**" 옵션이 로그인 페이지에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-422">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="0056f-423">**Guest** 계정에는 암호가 필요 하지 않으며 계정이 로그 아웃 될 때 계정에 연결 된 모든 데이터가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-423">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="0056f-424">**게스트** 계정을 사용 하도록 설정 하려면 다음 코드 조각을 키오스크 구성 XML에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-424">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="0056f-425">HoloLens의 개체 틀 시작 레이아웃</span><span class="sxs-lookup"><span data-stu-id="0056f-425">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="0056f-426">[배포 패키지](##use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 를 사용 하 여 다중 앱 키오스크를 구성 하는 경우에는 절차에 시작 레이아웃이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-426">If you use a [provisioning package](##use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="0056f-427">시작 레이아웃 사용자 지정은 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-427">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="0056f-428">따라서 자리 표시자 시작 레이아웃을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-428">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="0056f-429">단일 앱 키오스크는 사용자가 로그인 할 때 키오스크 앱을 시작 하므로 시작 메뉴를 사용 하지 않으며 시작 레이아웃을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-429">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="0056f-430">[MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 을 사용 하 여 다중 앱 키오스크를 설정 하는 경우 필요에 따라 시작 레이아웃을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-430">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="0056f-431">자세한 내용은 [MDM (Intune 및 기타)에 대 한 자리 표시자 시작 레이아웃 파일](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-431">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="0056f-432">시작 레이아웃의 경우 kiosk 프로비저닝 XML 파일에 다음 **Startlayout** 섹션을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-432">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="0056f-433">MDM (Intune 및 기타)의 개체 틀 시작 레이아웃 파일</span><span class="sxs-lookup"><span data-stu-id="0056f-433">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="0056f-434">다음 샘플을 XML 파일로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-434">Save the following sample as an XML file.</span></span> <span data-ttu-id="0056f-435">Microsoft Intune 또는 키오스크 프로필을 제공 하는 다른 MDM 서비스에서 다중 앱 키오스크을 구성할 때이 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-435">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="0056f-436">MDM 서비스에서 사용자 지정 설정과 전체 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [에는 프로비저닝 패키지에 대 한 시작 레이아웃 지침](#start-layout-for-hololens)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-436">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a><span data-ttu-id="0056f-437">Prov.</span><span class="sxs-lookup"><span data-stu-id="0056f-437">Prov.</span></span> <span data-ttu-id="0056f-438">패키지, 2 단계 &ndash; 에서 kiosk 구성 XML 파일을 프로비저닝 패키지에 추가</span><span class="sxs-lookup"><span data-stu-id="0056f-438">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="0056f-439">[Windows 구성 디자이너](https://www.microsoft.com/store/apps/9nblggh4tx22)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-439">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="0056f-440">**고급 프로비저닝을**선택 하 고 프로젝트의 이름을 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-440">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="0056f-441">**Windows 10 홀로그램**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-441">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="0056f-442">**마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-442">Select **Finish**.</span></span> <span data-ttu-id="0056f-443">패키지에 대한 작업 영역이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-443">The workspace for your package opens.</span></span>
1. <span data-ttu-id="0056f-444">**런타임 설정**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-444">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="0056f-445">가운데 창에서 **찾아보기를** 선택 하 여 직접 만든 KIOSK 구성 XML 파일을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-445">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 구성 디자이너의 MultiAppAssignedAccessSettings 필드 스크린샷](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="0056f-447">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-447">**Optional**.</span></span> <span data-ttu-id="0056f-448">(디바이스의 초기 설정 후에 제공 되는 프로비저닝 패키지를 적용 하려는 경우 키오스크 장치에서 이미 관리자 사용자를 사용할 수 있는 경우이 단계를 건너뛰십시오.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-448">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="0056f-449">사용자 이름 및 암호를 입력 한 다음 **UserGroup**  >  **관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-449">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="0056f-450">이 계정을 사용 하 여 프로비저닝 상태와 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-450">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="0056f-451">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-451">**Optional**.</span></span> <span data-ttu-id="0056f-452">(키오스크 장치에 관리자 이외의 계정이 이미 있는 경우에는이 단계를 건너뛰십시오.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 로컬 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-452">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="0056f-453">사용자 이름이 구성 XML에서 지정 하는 계정과 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-453">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="0056f-454">**UserGroup**  >  **표준 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-454">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="0056f-455">**파일**  >  **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-455">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="0056f-456">**Export**  >  **배포 패키지**내보내기를 선택 하 고 **소유자**  >  **IT 관리자**를 선택 합니다. 이렇게 하면 다른 원본에서이 디바이스에 적용 되는 프로 비전 패키지 보다 높은 우선 순위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-456">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="0056f-457">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-457">Select **Next**.</span></span>
1. <span data-ttu-id="0056f-458">**배포 패키지 보안** 페이지에서 보안 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-458">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="0056f-459">**패키지 서명 사용**을 선택 하는 경우 패키지에 서명 하는 데 사용할 유효한 인증서도 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-459">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="0056f-460">이렇게 하려면 **찾아보기를** 선택 하 고 패키지에 서명 하는 데 사용할 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-460">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="0056f-461">**패키지 암호화 사용**을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-461">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="0056f-462">HoloLens 장치에서는이 설정으로 인해 프로비저닝이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-462">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="0056f-463">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-463">Select **Next**.</span></span>
1. <span data-ttu-id="0056f-464">프로 비전 패키지를 빌드할 때 이동할 출력 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-464">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="0056f-465">기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-465">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="0056f-466">출력 위치를 변경 하려면 **찾아보기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-466">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="0056f-467">완료 되 면 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-467">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="0056f-468">**빌드** 를 선택 하 여 패키지 빌드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-468">Select **Build** to start building the package.</span></span> <span data-ttu-id="0056f-469">프로비저닝 패키지를 빌드하는 데는 오랜 시간이 걸리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-469">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="0056f-470">빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-470">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="0056f-471">프로비저닝 패키지, 3 단계에서 &ndash; 배포 패키지를 HoloLens에 적용</span><span class="sxs-lookup"><span data-stu-id="0056f-471">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="0056f-472">"프로비저닝 패키지를 사용 하 여 HoloLens 구성" 문서에서는 다음과 같은 경우에 배포 패키지를 적용 하기 위한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-472">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="0056f-473">[설치 하는 동안 처음으로 HoloLens에 프로비저닝 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-473">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="0056f-474">[설치 후에 HoloLens에 제공 패키지를 적용할](hololens-provisioning.md#4-apply-a-provisioning-package-to-hololens-after-setup)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-474">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#4-apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="0056f-475">Windows Device Portal을 사용 하 여 단일 앱 키오스크 설정</span><span class="sxs-lookup"><span data-stu-id="0056f-475">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="0056f-476">Windows Device Portal을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-476">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0056f-477">키오스크 모드는 장치에 [비즈니스용 Windows 홀로그램](hololens1-upgrade-enterprise.md) 설치 되어 있는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-477">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="0056f-478">[Windows Device Portal을 사용 하도록 HoloLens 장치를 설정](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-478">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="0056f-479">Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-479">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="0056f-480">장치 포털을 사용 하도록 HoloLens를 설정 하는 경우 장치에서 개발자 모드를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-480">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="0056f-481">비즈니스용 Windows 홀로그램을 사용 하는 디바이스의 개발자 모드에서 앱을 로드 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-481">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="0056f-482">그러나이 설정은 사용자가 Microsoft Store에서 인증 되지 않은 앱을 설치할 수 있다는 위험을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-482">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="0056f-483">관리자는 [정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)의 **Applicationmanagement/allowdeveloper Unlock** 설정을 사용 하 여 개발자 모드를 사용 하도록 설정 하는 기능을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-483">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="0056f-484">개발자 모드에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-484">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="0056f-485">컴퓨터에서 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 또는 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)를 사용 하 여 HoloLens에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-485">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="0056f-486">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-486">Do one of the following:</span></span>
   - <span data-ttu-id="0056f-487">Windows Device Portal에 처음 연결 하는 경우 [사용자 이름 및 암호 만들기](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="0056f-487">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="0056f-488">이전에 설정한 사용자 이름 및 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-488">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="0056f-489">브라우저에서 인증서 오류가 표시되는 경우 [문제 해결 단계](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-489">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="0056f-490">Windows 디바이스 포털에서 **키오스크 모드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-490">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="0056f-491">**키오스크 모드 사용**을 선택 하 고 장치가 시작 될 때 실행할 앱을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-491">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![키오스크 모드](images/kiosk.png)
1. <span data-ttu-id="0056f-493">HoloLens를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-493">Restart HoloLens.</span></span> <span data-ttu-id="0056f-494">디바이스 포털 페이지가 열려 있는 경우 페이지 맨 위에 있는 **다시 시작** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0056f-494">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

## <span data-ttu-id="0056f-495">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0056f-495">More information</span></span>

<span data-ttu-id="0056f-496">배포 패키지를 사용 하 여 키오스크를 구성 하는 방법을 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="0056f-496">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
