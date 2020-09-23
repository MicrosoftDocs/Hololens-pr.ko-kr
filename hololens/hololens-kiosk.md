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
ms.openlocfilehash: 8844f691ec5395f9c69bce7df44125da9c838f14
ms.sourcegitcommit: 7bf0f92aaf1683c7c39ed6b17ac47231c5088365
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "11072795"
---
# <span data-ttu-id="2c7f3-103">HoloLens를 키오스크로 설정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="2c7f3-104">장치를 키오스크 모드로 실행 하도록 구성 하 여 HoloLens 장치가 고정 용도의 디바이스 ( *키오스크*이 라고도 함)로 작동 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="2c7f3-105">키오스크 모드는 장치에서 사용할 수 있는 응용 프로그램 (또는 사용자)을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="2c7f3-106">키오스크 모드는 HoloLens 장치를 비즈니스 앱으로 전용 또는 앱 데모에서 HoloLens 장치를 사용 하는 데 사용할 수 있는 편리한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="2c7f3-107">이 문서에서는 HoloLens 디바이스와 관련 된 키오스크 구성의 측면에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="2c7f3-108">다양 한 유형의 Windows 기반 키오스크 및이를 구성 하는 방법에 대 한 일반적인 내용은 [windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성을](https://docs.microsoft.com/windows/configuration/kiosk-methods)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="2c7f3-109">키오스크 모드는 사용자가 장치에 로그인 할 때 사용할 수 있는 앱을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="2c7f3-110">그러나 키오스크 모드는 보안 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="2c7f3-111">"허용" 된 앱이 허용 되지 않는 다른 앱을 여는 것은 중지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="2c7f3-112">앱 또는 프로세스를 열지 못하도록 차단 하려면 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 를 사용 하 여 적절 한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="2c7f3-113">Microsoft 서비스에 대 한 자세한 내용은 HoloLens 2 사용에 대 한 고급 보안 수준을 사용자에 게 제공 하 고 [상태 분리 및 격리-Defender 보호](security-state-separation-isolation.md#defender-protections)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="2c7f3-114">또는 [Windows PowerShell을 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="2c7f3-115">단일 앱 또는 다중 앱 구성에서 키오스크 모드를 사용할 수 있으며, 세 가지 프로세스 중 하나를 사용 하 여 키오스크 구성을 설정 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="2c7f3-116">다중 앱 구성을 삭제 하면 할당 된 액세스 기능에서 만든 사용자 잠금 프로필이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="2c7f3-117">그러나 모든 정책 변경 사항은 되돌리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="2c7f3-118">이러한 정책을 되돌리려면 디바이스를 공장 설정으로 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="2c7f3-119">키오스크 배포 계획</span><span class="sxs-lookup"><span data-stu-id="2c7f3-119">Plan the kiosk deployment</span></span>

### <span data-ttu-id="2c7f3-120">키오스크 모드 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c7f3-120">Kiosk mode requirements</span></span>

<span data-ttu-id="2c7f3-121">키오스크 모드를 사용 하도록 HoloLens 2 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-121">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="2c7f3-122">키오스크 모드를 사용 하도록 HoloLens (첫번째 gen) 장치를 구성 하려면 먼저 장치가 Windows 10, 버전 1803 또는 이후 버전을 실행 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-122">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="2c7f3-123">Windows 장치 복구 도구를 사용 하 여 HoloLens (첫번째 gen) 장치를 기본 빌드로 복구 하거나 최신 업데이트를 설치한 경우 장치를 구성할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-123">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="2c7f3-124">키오스크 모드에서 실행 되는 장치를 보호 하기 위해 USB 연결과 같은 기능을 해제 하는 장치 관리 정책을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-124">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="2c7f3-125">또한 업데이트 링 설정을 확인 하 여 업무 시간 동안 자동 업데이트가 발생 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-125">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="2c7f3-126">단일 앱 키오스크 또는 다중 앱 키오스크 중에서 결정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-126">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="2c7f3-127">단일 앱 키오스크는 사용자가 장치에 로그인 할 때 지정 된 앱을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-127">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="2c7f3-128">Cortana 인 시작 메뉴를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-128">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="2c7f3-129">HoloLens 2 장치가 [시작](hololens2-basic-usage.md#start-gesture) 제스처에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-129">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="2c7f3-130">HoloLens (1 gen) 장치가 [블 룸](hololens1-basic-usage.md) 제스처에 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-130">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="2c7f3-131">앱을 하나만 실행할 수 있으므로 사용자는 다른 앱을 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-131">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="2c7f3-132">다중 앱 키오스크는 사용자가 장치에 로그인 할 때 시작 메뉴를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-132">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="2c7f3-133">키오스크 구성은 시작 메뉴에서 사용할 수 있는 앱을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-133">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="2c7f3-134">다중 앱 키오스크를 사용 하 여 사용자에 게 쉽게 이해할 수 있는 환경을 제공 하 고,이를 사용 하는 데 필요한 작업만 표시 하 고, 사용 하지 않아도 되는 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-134">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="2c7f3-135">다음 표에는 여러 키오스크 모드의 기능 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-135">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="2c7f3-136">시작 메뉴</span><span class="sxs-lookup"><span data-stu-id="2c7f3-136">Start menu</span></span> |<span data-ttu-id="2c7f3-137">빠른 작업 메뉴</span><span class="sxs-lookup"><span data-stu-id="2c7f3-137">Quick Actions menu</span></span> |<span data-ttu-id="2c7f3-138">카메라 및 비디오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-138">Camera and video</span></span> |<span data-ttu-id="2c7f3-139">Miracast</span><span class="sxs-lookup"><span data-stu-id="2c7f3-139">Miracast</span></span> |<span data-ttu-id="2c7f3-140">Cortana</span><span class="sxs-lookup"><span data-stu-id="2c7f3-140">Cortana</span></span> |<span data-ttu-id="2c7f3-141">기본 제공 음성 명령</span><span class="sxs-lookup"><span data-stu-id="2c7f3-141">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="2c7f3-142">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2c7f3-142">Single-app kiosk</span></span> |<span data-ttu-id="2c7f3-143">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2c7f3-143">Disabled</span></span> |<span data-ttu-id="2c7f3-144">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2c7f3-144">Disabled</span></span>   |<span data-ttu-id="2c7f3-145">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2c7f3-145">Disabled</span></span> |<span data-ttu-id="2c7f3-146">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2c7f3-146">Disabled</span></span>   |<span data-ttu-id="2c7f3-147">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2c7f3-147">Disabled</span></span> |<span data-ttu-id="2c7f3-148">사용 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="2c7f3-148">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="2c7f3-149">다중 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2c7f3-149">Multi-app kiosk</span></span> |<span data-ttu-id="2c7f3-150">설정됨</span><span class="sxs-lookup"><span data-stu-id="2c7f3-150">Enabled</span></span> |<span data-ttu-id="2c7f3-151">사용 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="2c7f3-151">Enabled<sup>2</span></span></sup> |<span data-ttu-id="2c7f3-152">사용 가능 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="2c7f3-152">Available<sup>2</span></span></sup> |<span data-ttu-id="2c7f3-153">사용 가능 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="2c7f3-153">Available<sup>2</span></span></sup> |<span data-ttu-id="2c7f3-154">사용 가능한 <sup> 2, 3</span><span class="sxs-lookup"><span data-stu-id="2c7f3-154">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="2c7f3-155">사용 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="2c7f3-155">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="2c7f3-156"></sup>사용 안 함 기능과 관련 된 1 개의 음성 명령이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-156">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="2c7f3-157">2 </sup> 이러한 기능을 구성 하는 방법에 대 한 자세한 내용은 [키오스크 앱 선택을](#plan-kiosk-apps)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-157">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="2c7f3-158">3 </sup> Cortana를 사용할 수 없는 경우에도 기본 제공 음성 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-158">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="2c7f3-159">다음 표에는 여러 키오스크 모드의 사용자 지원 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-159">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="2c7f3-160">지원 되는 사용자 유형</span><span class="sxs-lookup"><span data-stu-id="2c7f3-160">Supported user types</span></span> | <span data-ttu-id="2c7f3-161">자동 로그인</span><span class="sxs-lookup"><span data-stu-id="2c7f3-161">Automatic sign-in</span></span> | <span data-ttu-id="2c7f3-162">여러 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="2c7f3-162">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="2c7f3-163">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2c7f3-163">Single-app kiosk</span></span> |<span data-ttu-id="2c7f3-164">AAD (Azure Active Directory) 또는 로컬 계정의 MSA (관리 서비스 계정)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-164">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="2c7f3-165">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-165">Yes</span></span> |<span data-ttu-id="2c7f3-166">아니오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-166">No</span></span> |
|<span data-ttu-id="2c7f3-167">다중 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2c7f3-167">Multi-app kiosk</span></span> |<span data-ttu-id="2c7f3-168">AAD 계정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-168">AAD account</span></span> |<span data-ttu-id="2c7f3-169">아니오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-169">No</span></span> |<span data-ttu-id="2c7f3-170">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-170">Yes</span></span> |

<span data-ttu-id="2c7f3-171">이러한 기능을 사용 하는 방법에 대 한 예제는 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-171">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="2c7f3-172">다음에 단일 앱 키오스크 사용:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-172">Use a single-app kiosk for:</span></span> |<span data-ttu-id="2c7f3-173">다음에 대해 다중 앱 키오스크 사용:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-173">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="2c7f3-174">새 직원에 대 한 Dynamics 365 가이드만 실행 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-174">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="2c7f3-175">직원 범위에 대해 가이드 및 원격 지원을 둘 다 실행 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-175">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="2c7f3-176">사용자 지정 앱만 실행 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-176">A device that runs only a custom app.</span></span> |<span data-ttu-id="2c7f3-177">사용자 지정 앱만 실행 하 여 대부분의 사용자에 게 키오스크 역할을 하는 장치로, 특정 사용자 그룹에 대 한 표준 장치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-177">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="2c7f3-178">키오스크 앱 계획</span><span class="sxs-lookup"><span data-stu-id="2c7f3-178">Plan kiosk apps</span></span>

<span data-ttu-id="2c7f3-179">키오스크 앱을 선택 하는 방법에 대 한 일반적인 정보는 [할당 된 액세스에 대 한 앱 선택 (키오스크 모드)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)에 대 한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-179">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="2c7f3-180">Windows Device Portal을 사용 하 여 단일 앱 키오스크를 구성 하는 경우 설정 프로세스 중에 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-180">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="2c7f3-181">MDM (모바일 디바이스 관리) 시스템 또는 배포 패키지를 사용 하 여 키오스크 모드를 구성 하는 경우 [ASSIGNEDACCESS CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 를 사용 하 여 응용 프로그램을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-181">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="2c7f3-182">CSP는 [응용 프로그램 사용자 모델 id (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 를 사용 하 여 응용 프로그램을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-182">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="2c7f3-183">다음 표에는 다중 앱 키오스크에서 사용할 수 있는 일부 응용 프로그램의 AUMIDs가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-183">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!CAUTION]
> <span data-ttu-id="2c7f3-184">셸 앱을 키오스크 앱으로 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-184">You cannot select the Shell app as a kiosk app.</span></span> <span data-ttu-id="2c7f3-185">또한 Microsoft Edge, Microsoft Store 또는 파일 탐색기를 키오스크 앱으로 선택 **하지** 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-185">Addition, we recommend that you do **not** select Microsoft Edge, Microsoft Store, or File Explorer as a kiosk app.</span></span>  

<a id="aumids"></a>

|<span data-ttu-id="2c7f3-186">앱 이름</span><span class="sxs-lookup"><span data-stu-id="2c7f3-186">App Name</span></span> |<span data-ttu-id="2c7f3-187">AUMID</span><span class="sxs-lookup"><span data-stu-id="2c7f3-187">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="2c7f3-188">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="2c7f3-188">3D Viewer</span></span> |<span data-ttu-id="2c7f3-189">Microsoft Microsoft3DViewer _8wekyb3d8bbwe \! Microsoft Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="2c7f3-189">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="2c7f3-190">Calendar</span><span class="sxs-lookup"><span data-stu-id="2c7f3-190">Calendar</span></span> |<span data-ttu-id="2c7f3-191">windowscommunicationsapps \ _8wekyb3d8bbwe \! windowslive. 일정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-191">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="2c7f3-192">카메라 <sup> 1, 2</span><span class="sxs-lookup"><span data-stu-id="2c7f3-192">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="2c7f3-193">HoloCamera _cw5n1h2txyewy \! HoloCamera</span><span class="sxs-lookup"><span data-stu-id="2c7f3-193">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="2c7f3-194">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="2c7f3-194">Cortana<sup>3</span></span></sup> |<span data-ttu-id="2c7f3-195">Microsoft 549981C3F5F10 _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="2c7f3-195">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="2c7f3-196">HoloLens의 장치 선택기 (첫번째 gen)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-196">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="2c7f3-197">HoloDevicesFlow _cw5n1h2txyewy \! HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="2c7f3-197">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="2c7f3-198">HoloLens 2의 장치 선택기</span><span class="sxs-lookup"><span data-stu-id="2c7f3-198">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="2c7f3-199">DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="2c7f3-199">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="2c7f3-200">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="2c7f3-200">Dynamics 365 Guides</span></span> |<span data-ttu-id="2c7f3-201">Dynamics365 _8wekyb3d8bbwe \! MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="2c7f3-201">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="2c7f3-202">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="2c7f3-202">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="2c7f3-203">Microsoft MicrosoftRemoteAssist _8wekyb3d8bbwe \! Microsoft. RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="2c7f3-203">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="2c7f3-204">피드백 &nbsp; 허브</span><span class="sxs-lookup"><span data-stu-id="2c7f3-204">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="2c7f3-205">Microsoft WindowsFeedbackHub _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="2c7f3-205">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="2c7f3-206">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="2c7f3-206">File Explorer</span></span> |<span data-ttu-id="2c7f3-207">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="2c7f3-207">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="2c7f3-208">Mail</span><span class="sxs-lookup"><span data-stu-id="2c7f3-208">Mail</span></span> |<span data-ttu-id="2c7f3-209">microsoft. windowscommunicationsapps_8wekyb3d8bbwe! windowslive</span><span class="sxs-lookup"><span data-stu-id="2c7f3-209">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="2c7f3-210">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="2c7f3-210">Microsoft Store</span></span> |<span data-ttu-id="2c7f3-211">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="2c7f3-211">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="2c7f3-212">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="2c7f3-212">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="2c7f3-213">영화 및 TV</span><span class="sxs-lookup"><span data-stu-id="2c7f3-213">Movies & TV</span></span> |<span data-ttu-id="2c7f3-214">Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="2c7f3-214">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="2c7f3-215">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2c7f3-215">OneDrive</span></span> |<span data-ttu-id="2c7f3-216">microsoft microsoftskydrive _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="2c7f3-216">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="2c7f3-217">사진</span><span class="sxs-lookup"><span data-stu-id="2c7f3-217">Photos</span></span> |<span data-ttu-id="2c7f3-218">Microsoft. 사진 \ _8wekyb3d8bbwe \! 내</span><span class="sxs-lookup"><span data-stu-id="2c7f3-218">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="2c7f3-219">설정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-219">Settings</span></span> |<span data-ttu-id="2c7f3-220">HolographicSystemSettings _cw5n1h2txyewy \! 내</span><span class="sxs-lookup"><span data-stu-id="2c7f3-220">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="2c7f3-221">팁</span><span class="sxs-lookup"><span data-stu-id="2c7f3-221">Tips</span></span> |<span data-ttu-id="2c7f3-222">Microsoft HoloLensTips _8wekyb3d8bbwe \! HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="2c7f3-222">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="2c7f3-223">1 </sup> 사진 또는 비디오 캡처를 사용 하도록 설정 하려면 카메라 앱을 키오스크 앱으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-223">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="2c7f3-224">2 </sup> 카메라 앱을 사용 하도록 설정 하는 경우 다음 조건에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-224">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="2c7f3-225">빠른 동작 메뉴에는 사진 및 비디오 단추가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-225">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="2c7f3-226">또한 그림을 조작 하거나 검색할 수 있는 앱 (예: 사진, 메일 또는 OneDrive)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-226">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="2c7f3-227">3 </sup> Cortana를 키오스크 앱으로 사용 하지 않는 경우에도 기본 제공 음성 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-227">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="2c7f3-228">그러나 비활성 기능과 관련 된 명령은 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-228">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="2c7f3-229">4 </sup> Miracast를 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-229">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="2c7f3-230">Miracast를 키오스크 앱으로 사용 하도록 설정 하려면 카메라 앱 및 장치 선택기 앱을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-230">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="2c7f3-231">사용자 및 장치 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="2c7f3-231">Plan user and device groups</span></span>

<span data-ttu-id="2c7f3-232">MDM 환경에서는 그룹을 사용 하 여 장치 구성 및 사용자 액세스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-232">In an MDM environment, you use groups to manage device configurations and user access.</span></span> 

<span data-ttu-id="2c7f3-233">키오스크 구성 프로필에는 **사용자 로그온 유형** 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-233">The kiosk configuration profile includes the **User logon type** setting.</span></span> <span data-ttu-id="2c7f3-234">**사용자 로그온 유형은** 추가 하는 앱을 사용할 수 있는 사용자 (또는 사용자가 포함 된 그룹)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-234">**User logon type** identifies the user (or group that contains the users) who can use the app or apps that you add.</span></span> <span data-ttu-id="2c7f3-235">사용자가 구성 프로필에 포함 되지 않은 계정을 사용 하 여 로그인 하는 경우 해당 사용자는 키오스크에서 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-235">If a user signs in by using an account that is not included in the configuration profile, that user cannot use apps on the kiosk.</span></span>  

> [!NOTE]  
> <span data-ttu-id="2c7f3-236">단일 앱 키오스크의 **사용자 로그온 유형은** 단일 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-236">The **User logon type** of a single-app kiosk specifies a single user account.</span></span> <span data-ttu-id="2c7f3-237">키오스크이 실행 되는 사용자 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-237">This is the user context under which the kiosk runs.</span></span> <span data-ttu-id="2c7f3-238">다중 앱 키오스크의 **사용자 로그온 유형에** 는 키오스크를 사용할 수 있는 하나 이상의 사용자 계정 또는 그룹이 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-238">The **User logon type** of a multi-app kiosk can specify one or more user accounts or groups that can use the kiosk.</span></span>

<span data-ttu-id="2c7f3-239">키오스크 구성을 장치에 배포 하려면 먼저 디바이스 또는 장치에 로그인 할 수 있는 사용자를 포함 하는 그룹에 키오스크 구성 프로필을 *할당* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-239">Before you can deploy the kiosk configuration to a device, you have to *assign* the kiosk configuration profile to a group that contains the device or a user who can sign in to the device.</span></span> <span data-ttu-id="2c7f3-240">이 설정은 다음과 같은 동작을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-240">This setting produces behavior such as the following.</span></span>

- <span data-ttu-id="2c7f3-241">장치가 할당 된 그룹의 구성원 인 경우 사용자가 장치에 처음 로그인 할 때 키오스크 구성이 장치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-241">If the device is a member of the assigned group, the kiosk configuration deploys to the device the first time that any user signs in on the device.</span></span>  
- <span data-ttu-id="2c7f3-242">장치가 할당 된 그룹의 구성원이 아니지만 해당 그룹의 구성원 인 사용자가 로그인 하면 해당 시간에 키오스크 구성이 디바이스에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-242">If the device is not a member of the assigned group, but a user who is a member of that group signs in, the kiosk configuration deploys to the device at that time.</span></span>

<span data-ttu-id="2c7f3-243">Intune에서 구성 프로필을 할당 하는 효과에 대 한 자세한 내용은 [Microsoft Intune에서 사용자 및 장치 프로필 할당](https://docs.microsoft.com/intune/configuration/device-profile-assign)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-243">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

> [!NOTE]  
> <span data-ttu-id="2c7f3-244">다음 예제에서는 다중 앱 키오스크에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-244">The following examples describe multi-app kiosks.</span></span> <span data-ttu-id="2c7f3-245">단일 앱 키오스크도 비슷한 방식으로 작동 하지만, 키오스크 환경을 제공 하는 사용자 계정은 한 명만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-245">Single-app kiosks behave in a similar manner, but only one user account gets the kiosk experience.</span></span>

**<span data-ttu-id="2c7f3-246">예제 1</span><span class="sxs-lookup"><span data-stu-id="2c7f3-246">Example 1</span></span>**

<span data-ttu-id="2c7f3-247">장치 및 사용자 둘 다에 단일 그룹 (그룹 1)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-247">You use a single group (Group 1) for both devices and users.</span></span> <span data-ttu-id="2c7f3-248">하나의 장치 및 사용자 A, B, C는이 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-248">One device and users A, B, and C are members of this group.</span></span> <span data-ttu-id="2c7f3-249">아래와 같이 키오스크 구성 프로필을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-249">You configure the kiosk configuration profile as follows:</span></span>  

- <span data-ttu-id="2c7f3-250">**사용자 로그온 유형**: 그룹 1</span><span class="sxs-lookup"><span data-stu-id="2c7f3-250">**User logon type**: Group 1</span></span>
- <span data-ttu-id="2c7f3-251">**배정 된 그룹**: 그룹 1</span><span class="sxs-lookup"><span data-stu-id="2c7f3-251">**Assigned group**: Group 1</span></span>

<span data-ttu-id="2c7f3-252">장치에 먼저 로그인 하는 사용자와 관계 없이 (기본 제공 경험 또는 OOBE를 통해) 키오스크 구성은 장치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-252">Regardless of which user signs on to the device first (and goes through the Out-of-Box Experience, or OOBE), the kiosk configuration deploys to the device.</span></span> <span data-ttu-id="2c7f3-253">사용자 A, B, C가 모든 장치에 로그인 하 여 키오스크 환경을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-253">Users A, B, and C can all sign in to the device and get the kiosk experience.</span></span>

**<span data-ttu-id="2c7f3-254">예제 2</span><span class="sxs-lookup"><span data-stu-id="2c7f3-254">Example 2</span></span>**

<span data-ttu-id="2c7f3-255">장치를 서로 다른 키오스크 환경을 필요로 하는 두 가지 다른 공급 업체에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-255">You contract out devices to two different vendors who need different kiosk experiences.</span></span> <span data-ttu-id="2c7f3-256">두 공급 업체 모두 사용자를 보유 하 고 있으며 모든 사용자가 자신의 공급 업체와 다른 공급 업체 로부터 키오스크에 액세스할 수 있도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="2c7f3-256">Both vendors have users, and you want all the users to have access to kiosks from both their own vendor and the other vendor.</span></span> <span data-ttu-id="2c7f3-257">다음과 같이 그룹을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-257">You configure groups as follows:</span></span>

- <span data-ttu-id="2c7f3-258">장치 그룹 1:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-258">Device Group 1:</span></span>
  - <span data-ttu-id="2c7f3-259">장치 1 (공급 업체 1)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-259">Device 1 (Vendor 1)</span></span>
  - <span data-ttu-id="2c7f3-260">장치 2 (공급 업체 1)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-260">Device 2 (Vendor 1)</span></span>

- <span data-ttu-id="2c7f3-261">장치 그룹 2:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-261">Device Group 2:</span></span>
  - <span data-ttu-id="2c7f3-262">장치 3 (공급 업체 2)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-262">Device 3 (Vendor 2)</span></span>
  - <span data-ttu-id="2c7f3-263">장치 4 (공급 업체 2)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-263">Device 4 (Vendor 2)</span></span>

- <span data-ttu-id="2c7f3-264">사용자 그룹:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-264">User Group:</span></span>
  - <span data-ttu-id="2c7f3-265">사용자 A (공급 업체 1)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-265">User A (Vendor 1)</span></span>
  - <span data-ttu-id="2c7f3-266">사용자 B (공급 업체 2)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-266">User B (Vendor 2)</span></span>

<span data-ttu-id="2c7f3-267">다음 설정을 사용 하는 두 개의 키오스크 구성 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-267">You create two kiosk configuration profiles that have the following settings:</span></span>

- <span data-ttu-id="2c7f3-268">키오스크 프로필 1:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-268">Kiosk Profile 1:</span></span>
   - <span data-ttu-id="2c7f3-269">**사용자 로그온 유형**: 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="2c7f3-269">**User logon type**: User Group</span></span>
   - <span data-ttu-id="2c7f3-270">**할당 된 그룹**: 장치 그룹 1</span><span class="sxs-lookup"><span data-stu-id="2c7f3-270">**Assigned group**: Device Group 1</span></span>

- <span data-ttu-id="2c7f3-271">키오스크 프로필 2:</span><span class="sxs-lookup"><span data-stu-id="2c7f3-271">Kiosk Profile 2:</span></span>
   - <span data-ttu-id="2c7f3-272">**사용자 로그온 유형**: 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="2c7f3-272">**User logon type**: User Group</span></span>
   - <span data-ttu-id="2c7f3-273">**할당 된 그룹**: 장치 그룹 2</span><span class="sxs-lookup"><span data-stu-id="2c7f3-273">**Assigned group**: Device Group 2</span></span>

<span data-ttu-id="2c7f3-274">이러한 구성은 다음과 같은 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-274">These configurations produce the following results:</span></span>

- <span data-ttu-id="2c7f3-275">사용자가 장치 1 또는 장치 2에 로그인 하면 Intune에서 키오스크 프로필 1을 해당 장치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-275">When any user signs in to Device 1 or Device 2, Intune deploys Kiosk Profile 1 to that device.</span></span>
- <span data-ttu-id="2c7f3-276">사용자가 장치 3 또는 장치 4에 로그인 하면 Intune에서 키오스크 프로필 2를 해당 장치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-276">When any user signs in to Device 3 or Device 4, Intune deploys Kiosk Profile 2 to that device.</span></span>
- <span data-ttu-id="2c7f3-277">사용자 A와 사용자 B는 네 가지 장치 중 하나에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-277">User A and user B can sign in to any of the four devices.</span></span> <span data-ttu-id="2c7f3-278">장치 1 또는 장치 2에 로그인 하는 경우 공급 업체 1 키오스크 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-278">If they sign in to Device 1 or Device 2, they see the Vendor 1 kiosk experience.</span></span> <span data-ttu-id="2c7f3-279">장치 3 또는 장치 4에 로그인 하는 경우 공급 업체 2 키오스크 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-279">If they sign in to Device 3 or Device 4, they see the Vendor 2 kiosk experience.</span></span>

#### <span data-ttu-id="2c7f3-280">프로필 충돌</span><span class="sxs-lookup"><span data-stu-id="2c7f3-280">Profile conflicts</span></span>

<span data-ttu-id="2c7f3-281">두 개 이상의 키오스크 구성 프로필이 동일한 장치를 대상으로 하는 경우 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-281">If two or more kiosk configuration profiles target the same device, they conflict.</span></span> <span data-ttu-id="2c7f3-282">Intune 관리 장치의 경우 Intune은 충돌 하는 프로필을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-282">In the case of Intune-managed devices, Intune does not apply any of the conflicting profiles.</span></span>

<span data-ttu-id="2c7f3-283">키오스크 구성 프로필과 관련 되지 않은 장치 제한과 같은 다른 종류의 프로필 및 정책은 키오스크 구성 프로필과 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-283">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>

### <span data-ttu-id="2c7f3-284">배포 방법 선택</span><span class="sxs-lookup"><span data-stu-id="2c7f3-284">Select a deployment method</span></span>

<span data-ttu-id="2c7f3-285">다음 방법 중 하나를 선택 하 여 키오스크 구성을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-285">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="2c7f3-286">Microsoft Intune 또는 기타 MDM (모바일 디바이스 관리) 서비스</span><span class="sxs-lookup"><span data-stu-id="2c7f3-286">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="2c7f3-287">프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="2c7f3-287">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="2c7f3-288">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="2c7f3-288">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="2c7f3-289">이 방법을 사용 하려면 디바이스에서 개발자 모드를 사용 하도록 설정 해야 하므로 데모 에서만 사용할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-289">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="2c7f3-290">다음 표에서는 각 배포 방법의 기능 및 장점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-290">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="2c7f3-291">Windows Device Portal을 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-291">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="2c7f3-292">프로비저닝 패키지를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-292">Deploy by using a provisioning package</span></span> |<span data-ttu-id="2c7f3-293">MDM을 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-293">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="2c7f3-294">단일 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-294">Deploy single-app kiosks</span></span>   | <span data-ttu-id="2c7f3-295">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-295">Yes</span></span>           | <span data-ttu-id="2c7f3-296">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-296">Yes</span></span>                  | <span data-ttu-id="2c7f3-297">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-297">Yes</span></span>  |
|<span data-ttu-id="2c7f3-298">다중 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-298">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="2c7f3-299">아니오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-299">No</span></span>            | <span data-ttu-id="2c7f3-300">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-300">Yes</span></span>                  | <span data-ttu-id="2c7f3-301">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-301">Yes</span></span>  |
|<span data-ttu-id="2c7f3-302">로컬 장치에만 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-302">Deploy to local devices only</span></span> | <span data-ttu-id="2c7f3-303">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-303">Yes</span></span>           | <span data-ttu-id="2c7f3-304">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-304">Yes</span></span>                  | <span data-ttu-id="2c7f3-305">아니오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-305">No</span></span>   |
|<span data-ttu-id="2c7f3-306">개발자 모드를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-306">Deploy by using Developer Mode</span></span> |<span data-ttu-id="2c7f3-307">필수</span><span class="sxs-lookup"><span data-stu-id="2c7f3-307">Required</span></span>       | <span data-ttu-id="2c7f3-308">필수 아님</span><span class="sxs-lookup"><span data-stu-id="2c7f3-308">Not required</span></span>            | <span data-ttu-id="2c7f3-309">필수 아님</span><span class="sxs-lookup"><span data-stu-id="2c7f3-309">Not required</span></span>   |
|<span data-ttu-id="2c7f3-310">AAD (Azure Active Directory)를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-310">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="2c7f3-311">필수 아님</span><span class="sxs-lookup"><span data-stu-id="2c7f3-311">Not required</span></span>            | <span data-ttu-id="2c7f3-312">필수 아님</span><span class="sxs-lookup"><span data-stu-id="2c7f3-312">Not required</span></span>                   | <span data-ttu-id="2c7f3-313">필수</span><span class="sxs-lookup"><span data-stu-id="2c7f3-313">Required</span></span>  |
|<span data-ttu-id="2c7f3-314">자동으로 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-314">Deploy automatically</span></span>      | <span data-ttu-id="2c7f3-315">아니오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-315">No</span></span>            | <span data-ttu-id="2c7f3-316">아니오</span><span class="sxs-lookup"><span data-stu-id="2c7f3-316">No</span></span>                   | <span data-ttu-id="2c7f3-317">예</span><span class="sxs-lookup"><span data-stu-id="2c7f3-317">Yes</span></span>  |
|<span data-ttu-id="2c7f3-318">배포 속도</span><span class="sxs-lookup"><span data-stu-id="2c7f3-318">Deployment speed</span></span>            | <span data-ttu-id="2c7f3-319">가장 빠른</span><span class="sxs-lookup"><span data-stu-id="2c7f3-319">Fastest</span></span>       | <span data-ttu-id="2c7f3-320">빠름</span><span class="sxs-lookup"><span data-stu-id="2c7f3-320">Fast</span></span>                 | <span data-ttu-id="2c7f3-321">슬로우</span><span class="sxs-lookup"><span data-stu-id="2c7f3-321">Slow</span></span> |
|<span data-ttu-id="2c7f3-322">배율에 배치</span><span class="sxs-lookup"><span data-stu-id="2c7f3-322">Deploy at scale</span></span> | <span data-ttu-id="2c7f3-323">권장 되지 않음</span><span class="sxs-lookup"><span data-stu-id="2c7f3-323">Not recommended</span></span>    | <span data-ttu-id="2c7f3-324">권장 되지 않음</span><span class="sxs-lookup"><span data-stu-id="2c7f3-324">Not recommended</span></span>        | <span data-ttu-id="2c7f3-325">권장 사항</span><span class="sxs-lookup"><span data-stu-id="2c7f3-325">Recommended</span></span> |

## <span data-ttu-id="2c7f3-326">Microsoft Intune 또는 기타 MDM을 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-326">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="2c7f3-327">Microsoft Intune 또는 다른 MDM 시스템을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-327">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="2c7f3-328">[장치 등록을 준비](#mdmenroll)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-328">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="2c7f3-329">[키오스크 구성 프로필을 만듭니다](#mdmprofile).</span><span class="sxs-lookup"><span data-stu-id="2c7f3-329">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="2c7f3-330">키오스크를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-330">Configure the kiosk.</span></span>
   - <span data-ttu-id="2c7f3-331">[단일 앱 키오스크에 대 한 설정을 구성](#mdmconfigsingle)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-331">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="2c7f3-332">[다중 앱 키오스크에 대 한 설정을 구성](#mdmconfigmulti)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-332">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="2c7f3-333">[키오스크 구성 프로필을 그룹에 할당](#mdmassign)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-333">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="2c7f3-334">장치를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-334">Deploy the devices.</span></span>
   - <span data-ttu-id="2c7f3-335">[단일 앱 키오스크 배포](#mdmsingledeploy)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-335">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="2c7f3-336">[다중 앱 키오스크 배포](#mdmmultideploy)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-336">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="2c7f3-337">MDM, 1 단계 &ndash; 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="2c7f3-337">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="2c7f3-338">사용자가 처음 로그인 할 때 HoloLens 장치를 자동으로 등록 하도록 MDM 시스템을 구성 하거나 사용자가 디바이스를 수동으로 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-338">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="2c7f3-339">또한 디바이스를 Azure AD 도메인에 가입 하 고 해당 그룹에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-339">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="2c7f3-340">장치를 등록 하는 방법에 대 한 자세한 내용은 [Windows 장치용 MDM 및 Intune 등록 방법](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods) [에서 HoloLens 등록](hololens-enroll-mdm.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-340">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="2c7f3-341">MDM, 2 단계 &ndash; 키오스크 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="2c7f3-341">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="2c7f3-342">[Azure](https://portal.azure.com/) 포털을 열고 Intune 관리자 계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-342">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="2c7f3-343">**Microsoft Intune**  >  **장치 구성-** 프로필  >  **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-343">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="2c7f3-344">프로필 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-344">Enter a profile name.</span></span>
1. <span data-ttu-id="2c7f3-345">**플랫폼**  >  **Windows 10 이상을**선택한 다음 **프로필 형식**  > **장치 제한을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-345">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="2c7f3-346">키오스크 **구성을**선택  >  **Kiosk**하 고 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-346">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="2c7f3-347">단일 앱 키오스크를 만들려면 **키오스크 모드**  >  **단일 앱 키오스크**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-347">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="2c7f3-348">다중 앱 키오스크를 만들려면 **키오스크 모드**  >  **다중 앱 키오스크**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-348">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="2c7f3-349">키오스크 구성을 시작 하려면 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-349">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="2c7f3-350">다음 단계는 원하는 키오스크 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-350">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="2c7f3-351">자세한 내용을 보려면 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-351">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="2c7f3-352">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2c7f3-352">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="2c7f3-353">다중 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2c7f3-353">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="2c7f3-354">키오스크 구성 프로필을 만드는 방법에 대 한 자세한 내용은 Intune을 [사용 하 여 전용 키오스크로 실행 하기 위한 windows 10 및 Windows 홀로그램 비즈니스 장치 설정을](https://docs.microsoft.com/intune/configuration/kiosk-settings)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-354">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="2c7f3-355">MDM, 3 단계 (단일 앱) &ndash;  단일 앱 키오스크에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="2c7f3-355">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="2c7f3-356">이 섹션에서는 단일 앱 키오스크에 필요한 설정을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-356">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="2c7f3-357">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-357">For more details, see the following articles:</span></span>

- <span data-ttu-id="2c7f3-358">Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune을 사용 하 여 키오스크 모드를 구성 하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-358">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="2c7f3-359">Intune의 단일 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [단일 전체 화면 앱 키오스크](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-359">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="2c7f3-360">다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-360">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="2c7f3-361">MDM 서비스에서 사용자 지정 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 XML 파일을 만듭니다](#ppkioskconfig).</span><span class="sxs-lookup"><span data-stu-id="2c7f3-361">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="2c7f3-362">**사용자 로그온 유형**  >  **로컬 사용자 계정을**선택한 다음 키오스크에 로그인 할 수 있는 로컬 (장치) 계정이 나 Microsoft 계정 (MSA)의 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-362">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="2c7f3-363">**자동 로그온** 사용자 계정 유형은 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-363">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="2c7f3-364">**응용 프로그램 종류**  >  **스토어 앱**을 선택한 다음 목록에서 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-364">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="2c7f3-365">다음 단계는 프로필을 그룹에 [할당](#mdmassign) 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-365">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="2c7f3-366">MDM, 3 단계 (다중 앱) &ndash; 다중 앱 키오스크에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="2c7f3-366">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="2c7f3-367">이 섹션에서는 다중 앱 키오스크에 필요한 설정을 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-367">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="2c7f3-368">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-368">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="2c7f3-369">Intune에서 키오스크 구성 프로필을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft Intune을 사용 하 여 키오스크 모드를 구성 하는 방법을](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-369">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="2c7f3-370">Intune의 다중 앱 키오스크에 사용할 수 있는 설정에 대 한 자세한 내용은 [다중 앱 키오스크](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-370">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="2c7f3-371">다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-371">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="2c7f3-372">MDM 서비스에서 사용자 지정 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [키오스크 구성을 정의 하는 XML 파일을 만듭니다](#ppkioskconfig).</span><span class="sxs-lookup"><span data-stu-id="2c7f3-372">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="2c7f3-373">XML 파일을 사용 하는 경우 [시작 레이아웃](#start-layout-for-hololens)을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-373">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="2c7f3-374">선택적으로 Intune 또는 기타 MDM 서비스에서 사용자 지정 시작 레이아웃을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-374">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="2c7f3-375">자세한 내용은 [MDM (Intune 및 기타)의 시작 레이아웃 파일](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-375">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="2c7f3-376">**대상 Windows 10의 S 모드 장치**  >  **번호**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-376">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="2c7f3-377">S 모드는 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-377">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="2c7f3-378">**사용자 로그온 유형**  >  **Azure AD 사용자 또는 그룹** 또는 **사용자 로그온**  >  에**HoloLens 방문자**를 입력 하 고 하나 이상의 사용자 그룹 또는 계정 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-378">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="2c7f3-379">**사용자 로그온 유형에** 지정 하는 그룹 또는 계정에 속한 사용자만 키오스크 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-379">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="2c7f3-380">다음 옵션을 사용 하 여 앱을 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-380">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="2c7f3-381">업로드 된 lob (기간 업무) 앱을 추가 하려면 **스토어 앱 추가** 를 선택한 다음 원하는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-381">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="2c7f3-382">AUMID를 지정 하 여 앱을 추가 하려면 **AUMID에서 추가** 를 선택 하 고 앱의 AUMID를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-382">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="2c7f3-383">사용할 수 있는 AUMIDs 목록 보기</span><span class="sxs-lookup"><span data-stu-id="2c7f3-383">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="2c7f3-384">다음 단계는 프로필을 그룹에 [할당](#mdmassign) 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-384">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="2c7f3-385">MDM, 4 단계 &ndash; 키오스크 구성 프로필을 그룹에 할당</span><span class="sxs-lookup"><span data-stu-id="2c7f3-385">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="2c7f3-386">키오스크 구성 프로필의 **지정** 페이지를 사용 하 여 키오스크 구성을 배포할 위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-386">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="2c7f3-387">가장 간단한 경우에는 디바이스에서 MDM에 등록할 때 HoloLens 장치를 포함할 그룹에 키오스크 구성 프로필을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-387">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="2c7f3-388">MDM, 5 단계 (단일 앱) &ndash; 단일 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-388">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="2c7f3-389">MDM 시스템을 사용 하는 경우 OOBE 중에 MDM에서 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-389">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="2c7f3-390">OOBE가 완료 된 후에는 장치에 간편 하 게 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-390">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="2c7f3-391">OOBE 중에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-391">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="2c7f3-392">키오스크 구성 프로필에 지정한 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-392">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="2c7f3-393">장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-393">Enroll the device.</span></span> <span data-ttu-id="2c7f3-394">키오스크 구성 프로필이 할당 된 그룹에 장치가 추가 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-394">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="2c7f3-395">OOBE가 완료 될 때까지, 스토어 앱을 다운로드 및 설치 하 고 정책을 적용할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-395">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="2c7f3-396">그런 다음 장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-396">Then restart the device.</span></span>

<span data-ttu-id="2c7f3-397">다음에 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-397">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="2c7f3-398">이 시점에서 키오스크 구성이 표시 되지 않으면 [과제 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-398">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="2c7f3-399">MDM, 5 단계 (다중 앱) &ndash; 다중 앱 키오스크 배포</span><span class="sxs-lookup"><span data-stu-id="2c7f3-399">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="2c7f3-400">MDM 시스템을 사용 하는 경우 Azure AD 테 넌 트에 디바이스를 연결 하 고 OOBE 중에 MDM에서 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-400">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="2c7f3-401">필요에 따라 사용자에 게 등록 정보를 제공 하 여 OOBE 프로세스 중에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-401">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="2c7f3-402">사용자를 포함 하는 그룹에 키오스크 구성 프로필을 할당 한 경우 해당 사용자 계정 중 하나가 장치에 로그인 하는 첫 번째 계정 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-402">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="2c7f3-403">OOBE 중에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-403">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="2c7f3-404">**사용자 로그온 유형** 그룹에 속하는 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-404">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="2c7f3-405">장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-405">Enroll the device.</span></span>
1. <span data-ttu-id="2c7f3-406">키오스크 구성 프로필의 일부인 앱을 다운로드 하 여 설치 하는 경우를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-406">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="2c7f3-407">또한 정책이 적용 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-407">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="2c7f3-408">OOBE가 완료 되 면 Microsoft store 또는 테스트용 로드를 통해 추가 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-408">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="2c7f3-409">장치가 속한 그룹의 [필수 앱](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 이 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-409">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="2c7f3-410">설치가 완료 되 면 장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-410">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="2c7f3-411">다음에 **사용자 로그온 유형에**속하는 계정을 사용 하 여 장치에 로그인 할 때 키오스크 앱이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-411">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="2c7f3-412">이 시점에서 키오스크 구성이 표시 되지 않으면 [과제 상태를 확인](https://docs.microsoft.com/intune/configuration/device-profile-monitor)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-412">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="2c7f3-413">배포 패키지를 사용 하 여 단일 앱 또는 다중 앱 키오스크 설정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-413">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="2c7f3-414">배포 패키지를 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-414">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="2c7f3-415">[키오스크 구성을 정의 하는 XML 파일](#ppkioskconfig)( [시작 레이아웃](#start-layout-for-hololens)포함)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-415">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="2c7f3-416">배포 패키지에 XML 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-416">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="2c7f3-417">HoloLens에 프로비저닝 패키지를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-417">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="2c7f3-418">프로비저닝 패키지, 1 단계 &ndash; 키오스크 구성 XML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="2c7f3-418">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="2c7f3-419">일반 지침에 따라 다음을 제외 하 고 [Windows 데스크톱용 키오스크 구성 XML 파일을 만듭니다](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).</span><span class="sxs-lookup"><span data-stu-id="2c7f3-419">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="2c7f3-420">클래식 Windows 응용 프로그램 (Win32)을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-420">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="2c7f3-421">HoloLens는 이러한 응용 프로그램을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-421">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="2c7f3-422">HoloLens 용 [자리 표시자 시작 레이아웃 XML](#start-layout-for-hololens) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-422">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="2c7f3-423">선택 사항: 키오스크 구성에 게스트 액세스 추가</span><span class="sxs-lookup"><span data-stu-id="2c7f3-423">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="2c7f3-424">선택 사항: 키오스크 구성에 게스트 액세스 추가</span><span class="sxs-lookup"><span data-stu-id="2c7f3-424">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="2c7f3-425">[XML 파일의 **Configs** 섹션](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)에서 게스트가 키오스크를 사용할 수 있도록 **방문자** 라는 특별 한 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-425">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="2c7f3-426">방문객이 **방문자** 특별 그룹을 지원 하도록 구성 된 경우 "**게스트**" 옵션이 로그인 페이지에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-426">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="2c7f3-427">**Guest** 계정에는 암호가 필요 하지 않으며 계정이 로그 아웃 될 때 계정에 연결 된 모든 데이터가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-427">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="2c7f3-428">**게스트** 계정을 사용 하도록 설정 하려면 다음 코드 조각을 키오스크 구성 XML에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-428">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="2c7f3-429">HoloLens의 개체 틀 시작 레이아웃</span><span class="sxs-lookup"><span data-stu-id="2c7f3-429">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="2c7f3-430">[배포 패키지](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 를 사용 하 여 다중 앱 키오스크를 구성 하는 경우에는 절차에 시작 레이아웃이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-430">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="2c7f3-431">시작 레이아웃 사용자 지정은 비즈니스용 Windows 홀로그램에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-431">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="2c7f3-432">따라서 자리 표시자 시작 레이아웃을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-432">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="2c7f3-433">단일 앱 키오스크는 사용자가 로그인 할 때 키오스크 앱을 시작 하므로 시작 메뉴를 사용 하지 않으며 시작 레이아웃을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-433">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="2c7f3-434">[MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 을 사용 하 여 다중 앱 키오스크를 설정 하는 경우 필요에 따라 시작 레이아웃을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-434">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="2c7f3-435">자세한 내용은 [MDM (Intune 및 기타)에 대 한 자리 표시자 시작 레이아웃 파일](#start-layout-file-for-mdm-intune-and-others)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-435">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="2c7f3-436">시작 레이아웃의 경우 kiosk 프로비저닝 XML 파일에 다음 **Startlayout** 섹션을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-436">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="2c7f3-437">MDM (Intune 및 기타)의 개체 틀 시작 레이아웃 파일</span><span class="sxs-lookup"><span data-stu-id="2c7f3-437">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="2c7f3-438">다음 샘플을 XML 파일로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-438">Save the following sample as an XML file.</span></span> <span data-ttu-id="2c7f3-439">Microsoft Intune 또는 키오스크 프로필을 제공 하는 다른 MDM 서비스에서 다중 앱 키오스크을 구성할 때이 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-439">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="2c7f3-440">MDM 서비스에서 사용자 지정 설정과 전체 XML 구성을 사용 하 여 키오스크를 설정 해야 하는 경우 [에는 프로비저닝 패키지에 대 한 시작 레이아웃 지침](#start-layout-for-hololens)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-440">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a id="ppconfigadd"></a><span data-ttu-id="2c7f3-441">Prov.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-441">Prov.</span></span> <span data-ttu-id="2c7f3-442">패키지, 2 단계 &ndash; 에서 kiosk 구성 XML 파일을 프로비저닝 패키지에 추가</span><span class="sxs-lookup"><span data-stu-id="2c7f3-442">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="2c7f3-443">[Windows 구성 디자이너](https://www.microsoft.com/store/apps/9nblggh4tx22)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-443">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="2c7f3-444">**고급 프로비저닝을**선택 하 고 프로젝트의 이름을 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-444">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="2c7f3-445">**Windows 10 홀로그램**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-445">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="2c7f3-446">**마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-446">Select **Finish**.</span></span> <span data-ttu-id="2c7f3-447">패키지에 대한 작업 영역이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-447">The workspace for your package opens.</span></span>
1. <span data-ttu-id="2c7f3-448">**런타임 설정**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-448">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="2c7f3-449">가운데 창에서 **찾아보기를** 선택 하 여 직접 만든 KIOSK 구성 XML 파일을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-449">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 구성 디자이너의 MultiAppAssignedAccessSettings 필드 스크린샷](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="2c7f3-451">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-451">**Optional**.</span></span> <span data-ttu-id="2c7f3-452">(디바이스의 초기 설정 후에 제공 되는 프로비저닝 패키지를 적용 하려는 경우 키오스크 장치에서 이미 관리자 사용자를 사용할 수 있는 경우이 단계를 건너뛰십시오.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-452">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="2c7f3-453">사용자 이름 및 암호를 입력 한 다음 **UserGroup**  >  **관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-453">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="2c7f3-454">이 계정을 사용 하 여 프로비저닝 상태와 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-454">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="2c7f3-455">**선택 사항**입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-455">**Optional**.</span></span> <span data-ttu-id="2c7f3-456">(키오스크 장치에 관리자 이외의 계정이 이미 있는 경우에는이 단계를 건너뛰십시오.) **런타임 설정** &gt; **계정** &gt; **사용자**를 선택한 다음 로컬 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-456">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="2c7f3-457">사용자 이름이 구성 XML에서 지정 하는 계정과 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-457">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="2c7f3-458">**UserGroup**  >  **표준 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-458">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="2c7f3-459">**파일**  >  **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-459">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="2c7f3-460">**Export**  >  **배포 패키지**내보내기를 선택 하 고 **소유자**  >  **IT 관리자**를 선택 합니다. 이렇게 하면 다른 원본에서이 디바이스에 적용 되는 프로 비전 패키지 보다 높은 우선 순위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-460">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="2c7f3-461">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-461">Select **Next**.</span></span>
1. <span data-ttu-id="2c7f3-462">**배포 패키지 보안** 페이지에서 보안 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-462">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="2c7f3-463">**패키지 서명 사용**을 선택 하는 경우 패키지에 서명 하는 데 사용할 유효한 인증서도 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-463">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="2c7f3-464">이렇게 하려면 **찾아보기를** 선택 하 고 패키지에 서명 하는 데 사용할 인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-464">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="2c7f3-465">**패키지 암호화 사용**을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-465">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="2c7f3-466">HoloLens 장치에서는이 설정으로 인해 프로비저닝이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-466">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="2c7f3-467">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-467">Select **Next**.</span></span>
1. <span data-ttu-id="2c7f3-468">프로 비전 패키지를 빌드할 때 이동할 출력 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-468">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="2c7f3-469">기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-469">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="2c7f3-470">출력 위치를 변경 하려면 **찾아보기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-470">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="2c7f3-471">완료 되 면 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-471">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="2c7f3-472">**빌드** 를 선택 하 여 패키지 빌드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-472">Select **Build** to start building the package.</span></span> <span data-ttu-id="2c7f3-473">프로비저닝 패키지를 빌드하는 데는 오랜 시간이 걸리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-473">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="2c7f3-474">빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-474">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="2c7f3-475">프로비저닝 패키지, 3 단계에서 &ndash; 배포 패키지를 HoloLens에 적용</span><span class="sxs-lookup"><span data-stu-id="2c7f3-475">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="2c7f3-476">"프로비저닝 패키지를 사용 하 여 HoloLens 구성" 문서에서는 다음과 같은 경우에 배포 패키지를 적용 하기 위한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-476">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="2c7f3-477">[설치 하는 동안 처음으로 HoloLens에 프로비저닝 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-477">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="2c7f3-478">[설치 후에 HoloLens에 제공 패키지를 적용할](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-478">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="2c7f3-479">Windows Device Portal을 사용 하 여 단일 앱 키오스크 설정</span><span class="sxs-lookup"><span data-stu-id="2c7f3-479">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="2c7f3-480">Windows Device Portal을 사용 하 여 키오스크 모드를 설정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-480">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c7f3-481">키오스크 모드는 장치에 [비즈니스용 Windows 홀로그램](hololens1-upgrade-enterprise.md) 설치 되어 있는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-481">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="2c7f3-482">[Windows Device Portal을 사용 하도록 HoloLens 장치를 설정](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-482">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="2c7f3-483">Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-483">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="2c7f3-484">장치 포털을 사용 하도록 HoloLens를 설정 하는 경우 장치에서 개발자 모드를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-484">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="2c7f3-485">비즈니스용 Windows 홀로그램을 사용 하는 디바이스의 개발자 모드에서 앱을 로드 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-485">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="2c7f3-486">그러나이 설정은 사용자가 Microsoft Store에서 인증 되지 않은 앱을 설치할 수 있다는 위험을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-486">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="2c7f3-487">관리자는 [정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)의 **Applicationmanagement/allowdeveloper Unlock** 설정을 사용 하 여 개발자 모드를 사용 하도록 설정 하는 기능을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-487">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="2c7f3-488">개발자 모드에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-488">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="2c7f3-489">컴퓨터에서 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 또는 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)를 사용 하 여 HoloLens에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-489">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="2c7f3-490">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-490">Do one of the following:</span></span>
   - <span data-ttu-id="2c7f3-491">Windows Device Portal에 처음 연결 하는 경우 [사용자 이름 및 암호 만들기](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="2c7f3-491">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="2c7f3-492">이전에 설정한 사용자 이름 및 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-492">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="2c7f3-493">브라우저에서 인증서 오류가 표시되는 경우 [문제 해결 단계](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-493">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="2c7f3-494">Windows 디바이스 포털에서 **키오스크 모드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-494">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="2c7f3-495">**키오스크 모드 사용**을 선택 하 고 장치가 시작 될 때 실행할 앱을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-495">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![키오스크 모드](images/kiosk.png)
1. <span data-ttu-id="2c7f3-497">HoloLens를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-497">Restart HoloLens.</span></span> <span data-ttu-id="2c7f3-498">디바이스 포털 페이지가 열려 있는 경우 페이지 맨 위에 있는 **다시 시작** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-498">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="2c7f3-499">필수 쿼리 문자열 매개 변수 1 개 ("kioskModeEnabled"에 "true" 또는 "false" 값을 사용 하 고, 선택적 매개 변수 ("startupApp" 패키지 이름 값이 포함 된))를 사용 하 여/api/holographic/kioskmode/settings에 대 한 게시를 수행 하 여 장치 포털의 REST API를 통해 키오스크 모드를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-499">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="2c7f3-500">디바이스 포털은 개발자만 사용할 수 있으며 개발자가 작성 하지 않은 장치에서 사용 하지 않도록 설정 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-500">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="2c7f3-501">REST API는 향후 업데이트/릴리스에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-501">The REST API is subject to change in future updates/releases.</span></span>

## <span data-ttu-id="2c7f3-502">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2c7f3-502">More information</span></span>

<span data-ttu-id="2c7f3-503">배포 패키지를 사용 하 여 키오스크를 구성 하는 방법을 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7f3-503">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
