---
title: HoloLens 장치 및 holograms에 대 한 질문과 대답
description: HoloLens 또는 holograms와 상호 작용 하는 방법에 대 한 빠른 질문이 있나요?  이 문서에서는 빠른 응답 및 추가 리소스를 제공 합니다.
keywords: hololens, faq, 알려진 문제, 도움말
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924029"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="ef8a8-105">Holograms 및 상호 작용 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ef8a8-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="ef8a8-106">이 문서에서는 holograms를 배치 하 고, 공백과 작업 하 고, holograms와 관련 된 문제를 보고 하는 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="ef8a8-107">언제 든 지 문제가 발생 하면 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="ef8a8-108">작업을 [다시 시작](hololens-restart-recover.md) 하 여이 문제를 수정 하는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="ef8a8-109">문제를 해결 하기 전에 HoloLens가 [청구](hololens2-charging.md) 되는지 확인 합니다 (최소 1 시간 동안 청구 됨).</span><span class="sxs-lookup"><span data-stu-id="ef8a8-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="ef8a8-110">피드백 앱을 사용 하 여 문제에 대 한 정보를 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="ef8a8-111">[ **시작** 메뉴](holographic-home.md)에서 피드백 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="ef8a8-112">HoloLens를 착용 하는 방법에 대 한 팁은 [맞춤 조정](hololens2-setup.md#adjust-fit)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="ef8a8-113">새 공간을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="ef8a8-114">공백을 식별 하거나 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="ef8a8-115">모든 공백을 삭제 어떻게 할까요? 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="ef8a8-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="ef8a8-116">Holograms 바로 보이지 않거나 이동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="ef8a8-117">"스페이스 찾기" 메시지</span><span class="sxs-lookup"><span data-stu-id="ef8a8-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="ef8a8-118">필요한 holograms는 내 공간에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="ef8a8-119">Holograms를 배치 하거나 이전에 배치한 holograms을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="ef8a8-120">Holograms는 다른 Holograms 또는 개체에서 사라지지만이를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="ef8a8-121">Holograms는 벽의 반대쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="ef8a8-122">벽에 홀로그램을 배치 하면 부동으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="ef8a8-123">앱을 이동한 후 너무 가까이 표시</span><span class="sxs-lookup"><span data-stu-id="ef8a8-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="ef8a8-124">불안정 하거나 부정확 한 holograms 문제 보고</span><span class="sxs-lookup"><span data-stu-id="ef8a8-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="ef8a8-125">새 공간을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-125">New spaces can't be created</span></span>

<span data-ttu-id="ef8a8-126">가장 가능성이 높은 문제는 저장소 공간이 부족 하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="ef8a8-127">[디스크 공간을 확보](hololens-troubleshooting.md#low-disk-space-error) 한 후 다시 시도 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="ef8a8-128">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="ef8a8-129">공백을 식별 하거나 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="ef8a8-130">HoloLens에서 자동으로 사용할 공간을 식별 하 고 로드할 수 없는 경우 다음 요소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="ef8a8-131">Wi-Fi에 연결 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="ef8a8-132">대화방에 충분 한 빛이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="ef8a8-133">환경에 대 한 중요 한 변경 내용이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="ef8a8-134">**설정**  >  **시스템**  >  **공간** 으로 이동 하 여 공간을 수동으로 로드 하거나 공간을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="ef8a8-135">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="ef8a8-136">모든 공백을 삭제 어떻게 할까요? 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="ef8a8-136">How do I delete all spaces?</span></span>

<span data-ttu-id="ef8a8-137">*제공 예정*</span><span class="sxs-lookup"><span data-stu-id="ef8a8-137">*Coming soon*</span></span>

[<span data-ttu-id="ef8a8-138">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="ef8a8-139">Holograms 바로 보이지 않거나 이동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="ef8a8-140">Holograms 적절 하지 않은 경우 (예: 떨림 또는 흔들리는 또는 그 위에 검정색 패치가 표시 되는 경우) 다음 해결 방법 중 하나를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="ef8a8-141">[장치 센터를 청소](hololens1-hardware.md#care-and-cleaning) 하 고 어떤 것도 센서를 차단 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="ef8a8-142">직접 햇빛을 많이 사용 하지 않는 올바른 방에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="ef8a8-143">HoloLens가 더 완벽 하 게 검색할 수 있도록 주변을 탐색 하 고 gazing 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="ef8a8-144">Holograms을 많이 배치한 경우 일부를 제거해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="ef8a8-145">여전히 문제가 발생 하는 경우 보정 앱을 실행 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="ef8a8-146">이 앱은 holograms을 최대한 활용 하는 데 도움이 되도록 HoloLens를 보정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="ef8a8-147">이렇게 하려면 **설정**  >  **시스템**  >  **유틸리티** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="ef8a8-148">**보정** 아래에서 **보정 열기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="ef8a8-149">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="ef8a8-150">"스페이스 찾기" 메시지</span><span class="sxs-lookup"><span data-stu-id="ef8a8-150">"Finding your space" message</span></span>

<span data-ttu-id="ef8a8-151">HoloLens가 공간을 학습 하거나 로드 하는 경우 "공간을 찾고 있습니다." 라는 간단한 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="ef8a8-152">이 메시지가 몇 초 이상 표시 되 면 시작 메뉴 아래에 "스페이스를 찾고 있습니다." 라는 또 다른 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="ef8a8-153">이러한 메시지는 HoloLens가 공간을 매핑하는 데 문제가 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="ef8a8-154">이 경우 앱을 열 수는 있지만 사용자 환경에 holograms를 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="ef8a8-155">이러한 메시지가 자주 표시 되는 경우 다음 해결 방법 중 하나 이상을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="ef8a8-156">직접 햇빛을 많이 사용 하지 않는 올바른 방에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="ef8a8-157">장치 센터를 정리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="ef8a8-158">[센터를 정리 하는 방법을 알아봅니다](hololens1-hardware.md#care-and-cleaning).</span><span class="sxs-lookup"><span data-stu-id="ef8a8-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="ef8a8-159">강력한 Wi-Fi 신호가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="ef8a8-160">Wi-Fi 또는 약한 Wi-Fi 신호를 포함 하지 않는 새 환경을 입력 하는 경우 HoloLens에서 사용자의 공간을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="ef8a8-161">**설정**  >  **네트워크 &amp; 인터넷** wi-fi로 이동 하 여 Wi-Fi 연결을 확인  >  합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="ef8a8-162">더 느리게 이동 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-162">Try moving more slowly.</span></span>

[<span data-ttu-id="ef8a8-163">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="ef8a8-164">필요한 holograms는 내 공간에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="ef8a8-165">사용자가 배치한 holograms 표시 되지 않거나 예기치 않은 내용이 표시 되는 경우 다음 해결 방법 중 하나 이상을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="ef8a8-166">일부 조명을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-166">Turn on some lights.</span></span> <span data-ttu-id="ef8a8-167">HoloLens는 잘 켜진 공간에서 가장 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="ef8a8-168">**설정**  >  **시스템**  >  **holograms**  >  **remove 근처 holograms** 로 이동 하 여 필요 하지 않은 holograms을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="ef8a8-169">또는 필요한 경우 **모두 제거 holograms** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef8a8-170">공간의 레이아웃 또는 조명이 현저 하 게 변경 되 면 장치에서 사용자의 공간을 식별 하 고 holograms을 표시 하는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="ef8a8-171">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="ef8a8-172">Holograms를 배치 하거나 이전에 배치한 holograms을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="ef8a8-173">HoloLens가 공간을 매핑하거나 로드할 수 없는 경우 제한 된 모드로 전환 되며 holograms를 배치 하거나 holograms를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="ef8a8-174">다음은 시도해 볼 수 있는 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-174">Here are some things to try:</span></span>

- <span data-ttu-id="ef8a8-175">HoloLens가 공간을 보고 매핑할 수 있도록 사용자 환경에 충분 한 조명이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="ef8a8-176">홀로그램을 넣을 위치에서 1 ~ 3 미터 사이를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="ef8a8-177">검은색 또는 반사 표면에 holograms을 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="ef8a8-178">Wi-Fi 네트워크에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="ef8a8-179">Wi-fi에 연결 되지 않은 경우 HoloLens는 알려진 공간을 식별 하 고 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="ef8a8-180">HoloLens에서 주변을 다시 검사할 수 있도록 방을 탐색 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="ef8a8-181">이미 검사 된 항목을 보려면 마우스를 탭 하 여 매핑 메시 그래픽을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="ef8a8-182">새 공간을 만들어야 하는 경우 Wi-fi에 연결한 다음 HoloLens를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="ef8a8-183">올바른 공간이 활성화 되어 있는지 확인 하거나 공간을 수동으로 로드 하려면 **설정**  >  **시스템**  >  **공간** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="ef8a8-184">올바른 공간이 로드 되 고 문제가 여전히 발생 하는 경우 공간이 손상 된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="ef8a8-185">이 문제를 해결 하려면 공간을 선택 하 고 **제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="ef8a8-186">공간을 제거한 후 HoloLens가 환경을 매핑하고 새 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="ef8a8-187">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="ef8a8-188">Holograms는 다른 Holograms 또는 개체에서 사라지지만이를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="ef8a8-189">홀로그램에 너무 가까이 있으면 홀로그램을 복원 하기 위해 일시적으로 사라지고 &mdash; 홀로그램에서 다른 곳으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="ef8a8-190">또한 여러 holograms 가까이 배치 하면 일부가 사라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="ef8a8-191">몇 가지를 제거해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-191">Try removing a few.</span></span>

<span data-ttu-id="ef8a8-192">Holograms는 다른 Holograms 또는 벽 등의 개체에서 차단 하거나 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="ef8a8-193">이 경우 다음 해결 방법 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="ef8a8-194">홀로그램을 다른 홀로그램에 배치 하는 경우에는 encased 홀로그램을 다른 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="ef8a8-195">이렇게 하려면 **조정** 을 선택 하 고 길게를 눌러 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="ef8a8-196">홀로그램이 벽에 있는 경우 **조정** 을 선택 하 고 홀로그램이 나타날 때까지 벽을 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="ef8a8-197">길게 누른 다음 벽을 앞으로 또는 벽 밖으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="ef8a8-198">제스처를 사용 하 여 홀로그램을 이동할 수 없는 경우 음성을 사용 하 여 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="ef8a8-199">홀로그램을 응시 한 다음 "제거" 라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="ef8a8-200">그런 다음 홀로그램을 다시 열고 새 위치에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="ef8a8-201">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="ef8a8-202">Holograms는 벽의 반대쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="ef8a8-203">벽에 매우 근접 하거나 HoloLens에서 아직 벽을 검사 하지 않은 경우 다음 방에 있는 holograms을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="ef8a8-204">벽을 스캔 하려면 벽에서 1 ~ 3 미터를 그리고 응시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="ef8a8-205">벽 근처의 검정 또는 반사 개체 (예: 블랙 소파 또는 stainless 강철 냉장고)는 HoloLens가 벽을 스캔 하려고 할 때 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="ef8a8-206">이러한 개체가 있는 경우 벽의 반대쪽을 스캔 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="ef8a8-207">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="ef8a8-208">벽에 홀로그램을 배치 하면 부동으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="ef8a8-209">벽에 배치한 홀로그램은 일반적으로 벽에서 떨어져 있는 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="ef8a8-210">더 멀리 표시 되는 경우 다음 해결 방법 중 하나 이상을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="ef8a8-211">벽에 홀로그램을 놓으면 벽에서 1 미터에서 3 미터 사이를 향하게 하 고 벽을 똑바로 똑바로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="ef8a8-212">벽을 누르면 매핑 메시 그래픽이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="ef8a8-213">메쉬가 벽과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="ef8a8-214">그렇지 않으면 홀로그램을 제거 하 고 벽을 다시 검사 한 후 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="ef8a8-215">문제가 지속 되 면 보정 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="ef8a8-216">**설정**  >  **시스템**  >  **유틸리티** 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="ef8a8-217">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="ef8a8-218">앱을 이동한 후 너무 가까이 표시</span><span class="sxs-lookup"><span data-stu-id="ef8a8-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="ef8a8-219">HoloLens에서 다른 각도의 영역을 검색 하도록 앱을 배치 하는 영역을 살펴보고 탐색 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="ef8a8-220">[장치 센터를 청소 하면](hololens1-hardware.md#care-and-cleaning) 도움이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="ef8a8-221">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="ef8a8-222">불안정 하거나 부정확 한 holograms 문제 보고</span><span class="sxs-lookup"><span data-stu-id="ef8a8-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="ef8a8-223">녹화 하 고 [혼합 현실](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 에서 문제의 비디오를 캡처 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="ef8a8-224">나중에이 비디오를 첨부 파일로 피드백 허브를 통해 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="ef8a8-225">**설정** 앱을 통해 전체 원격 분석을 사용 하도록 설정 합니다. > **개인 정보**  ->  **진단 & 피드백** 을 **사용 하** 고 **선택적 진단 데이터** 에서 토글이 설정으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="ef8a8-226">최신 [Windows HOLOGRAPHIC OS (20H2 이상)](hololens-release-notes.md#windows-holographic-version-20h2)로 업데이트 하 여 최신 홀로그램 규모 및 안정성 수정을 받으세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="ef8a8-227">업데이트 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="ef8a8-228">Holograms를 통해 모든를 제거 합니다. **앱-** > **System**  ->  **Holograms** -> 다음, **모든 Holograms 제거** 를 선택 하 고 새 맵으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="ef8a8-229">HoloLens를 입고 하 고 공간에 있는 모든 영역 및 표면을 확인 하 여 공간에 대 한 새 지도를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="ef8a8-230">2-3 분 동안이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="ef8a8-231">IPD 보정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-231">Perform IPD calibration.</span></span> <span data-ttu-id="ef8a8-232">**설정**  >  **시스템**  >  **유틸리티** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="ef8a8-233">**보정** 아래에서 **보정 열기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="ef8a8-234">시나리오를 다시 테스트 하 고 계속 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="ef8a8-235">업데이트를 수행 해도 문제가 해결 되지 않으면 [피드백 허브 문제](hololens-feedback.md)를 파일에 입력 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="ef8a8-236">사용자 의견을 채운 후에는 **공유** 단추를 사용 하 여 지원 담당자에 게 연락할 때 전송 될 수 있는 공유 하기 쉬운 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="ef8a8-237">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ef8a8-237">Back to list</span></span>](#list)