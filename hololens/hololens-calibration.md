---
title: 시각적 품질과 편안함 개선
description: HoloLens 장치에서 시각 자료의 품질을 향상시키기 위해 IPD(공동 간 거리)를 보정하는 방법에 대해 알아보세요.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: 보정, 편안함, 비주얼, 품질, ipd, HoloLens, Windows Mixed Reality, VR 헤드셋
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283549"
---
# <span data-ttu-id="1c4f6-104">시각적 품질과 편안함 개선</span><span class="sxs-lookup"><span data-stu-id="1c4f6-104">Improve visual quality and comfort</span></span>

<span data-ttu-id="1c4f6-105">HoloLens 2 및 HoloLens(1세대) 모두 사용자의 눈에 맞게 보정될 때 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-105">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="1c4f6-106">두 장치 모두 최상의 홀로그램 보기 환경을 위해 보정해야 하지만, 서로 다른 보정 기술과 기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-106">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="1c4f6-107">[HoloLens 2 보정](#calibrating-your-hololens-2) 또는 [HoloLens(1세대) 보정](#calibrating-your-hololens-1st-gen)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-107">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="1c4f6-108">HoloLens 2 보정</span><span class="sxs-lookup"><span data-stu-id="1c4f6-108">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="1c4f6-109">HoloLens 2는 눈 추적 기술을 사용하여 가상 환경을 보고 상호 작용하는 경험을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-109">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="1c4f6-110">HoloLens 2를 보정하면 사용자의 눈(및 기기를 사용하는 다른 사람의 눈)을 정확하게 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-110">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="1c4f6-111">이는 사용자 편안함, 홀로그램 맞춤, 손 추적에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-111">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="1c4f6-112">보정이 완료되면 바이저가 머리 위에서 움직여도 홀로그램이 올바르게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-112">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="1c4f6-113">HoloLens 2는 사용자에게 다음과 같은 상황에서 장치를 보정하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-113">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="1c4f6-114">사용자가 처음으로 장치를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-114">The user is using the device for the first time</span></span>
- <span data-ttu-id="1c4f6-115">사용자가 이전에 보정 프로세스에서 옵트아웃했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-115">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="1c4f6-116">사용자가 마지막으로 장치를 사용할 때 보정 프로세스가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-116">The calibration process didn't succeed the last time the user used the device</span></span>
- <span data-ttu-id="1c4f6-117">사용자가 보정 프로필을 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-117">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="1c4f6-118">장치가 제거되었다가 다시 착용되어 위의 상황이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-118">The device is taken off and puts back on and any of the above circumstances apply</span></span> 


![눈으로 조정할 수 있는 보정 프롬프트.](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="1c4f6-120">이 프로세스 중에 대상(보석)의 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-120">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="1c4f6-121">보정을 하는 동안 눈을 깜빡여도 괜찮지만 방에 있는 다른 물체보다는 보석을 응시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-121">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="1c4f6-122">보석에 초점을 맞추면 홀로그램 세계를 렌더링하기 위해 HoloLens가 눈 위치에 대해 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-122">Focusing on the gems allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![머리를 움직이지 말고 눈으로 점을 따라오라는 보정 프롬프트.](./images/07-et-hold-head-still.png)

![보석의 예가 포함된 보정 프롬프트.](./images/08-et-gems.png)

![보정 프롬프트 조정.](./images/09-et-adjusting.png)

<span data-ttu-id="1c4f6-126">보정에 성공했다면 성공 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-126">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="1c4f6-127">그렇지 않은 경우 [보정 오류를 진단하는 방법](#troubleshooting-hololens-2-calibration)에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-127">If not, read more about [diagnosing calibration failures](#troubleshooting-hololens-2-calibration).</span></span>

![보정 프롬프트 성공.](./images/10-et-success.png)

### <span data-ttu-id="1c4f6-129">장치 또는 세션을 공유할 때의 보정</span><span class="sxs-lookup"><span data-stu-id="1c4f6-129">Calibration when sharing a device or session</span></span>

<span data-ttu-id="1c4f6-130">여러 사용자가 HoloLens 2 장치를 공유할 수 있으며 각 사용자가 장치 설정을 수행할 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-130">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="1c4f6-131">새 사용자가 장치를 처음으로 머리에 착용하면 HoloLens 2는 사용자에게 시각을 보정하라는 메시지를 자동으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-131">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="1c4f6-132">이전에 시각을 보정한 사용자가 장치를 머리에 착용하면 디스플레이가 화질과 편안한 보기 환경을 위해 매끄럽게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-132">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="1c4f6-133">수동으로 보정 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="1c4f6-133">Manually starting the calibration process</span></span>

1. <span data-ttu-id="1c4f6-134">시작 제스처를 사용하여 [**시작** 메뉴](hololens2-basic-usage.md#start-gesture)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-134">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="1c4f6-135">설정 앱이 **시작**에 고정되어 있지 않으면 **모든 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-135">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="1c4f6-136">**설정**을 선택한 다음 **시스템** > **보정** > **눈 보정** > **눈 보정 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-136">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![눈 보정 실행 옵션을 보여 주는 설정 앱](./images/C-Settings.Calibration.png)

### <span data-ttu-id="1c4f6-138">자동 눈 위치 지원</span><span class="sxs-lookup"><span data-stu-id="1c4f6-138">Auto Eye Position Support</span></span>

<span data-ttu-id="1c4f6-139">HoloLens 2에서는 눈 위치를 통해 정확한 홀로그램 위치, 편안한 시야 확보, 디스플레이 품질 개선 등이 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-139">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience, and improved display quality.</span></span> <span data-ttu-id="1c4f6-140">눈 위치는 시선 추적 계산의 일부로 내부적으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-140">Eye positions are computed internally as part of the eye tracking computation.</span></span> <span data-ttu-id="1c4f6-141">그러나, 이를 위해서는 각 사용자가 시선 입력이 필요하지 않은 경우에도 시선 추적 보정을 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-141">However, this requires each user to go through eye tracking calibration, even when the experience might not require eye gaze input.</span></span>

<span data-ttu-id="1c4f6-142">**AEP(자동 눈 위치)** 를 사용하면 상호작용 없이도 사용자의 눈 위치를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-142">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span> <span data-ttu-id="1c4f6-143">자동 눈 위치 기능은 사용자가 장치를 사용하는 순간부터 백그라운드에서 자동으로 작동하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-143">Auto Eye Position starts working in the background automatically from the moment the user puts on the device.</span></span> <span data-ttu-id="1c4f6-144">사용자에게 사전 시선 추적 보정이 없는 경우, 자동 눈 위치는 20~30초의 처리 시간이 지난 후 디스플레이 시스템에 사용자의 눈 위치를 제공하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-144">If the user doesn't have a prior eye tracking calibration, Auto Eye Position will start providing the user's eye positions to the display system after a processing time of 20 - 30 seconds.</span></span> <span data-ttu-id="1c4f6-145">사용자 데이터는 장치에 유지되지 않으므로 사용자가 장치를 껐다가 다시 켜거나 장치가 재부팅되거나 절전 모드에서 깨어난 경우 이 프로세스가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-145">The user data isn't persisted on the device and this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>

<span data-ttu-id="1c4f6-146">보정되지 않은 사용자가 장치를 사용할 때 자동 눈 위치 기능을 통해 몇 가지 시스템 동작이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-146">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="1c4f6-147">이 컨텍스트에서 보정되지 않은 사용자는 이전에 장치에서 시선 추적 보정 프로세스를 거치지 않은 사용자를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-147">In this context, an uncalibrated user refers to someone who hasn't gone through the eye tracking calibration process on the device previously.</span></span>

| <span data-ttu-id="1c4f6-148">활성 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1c4f6-148">Active Application</span></span> | <span data-ttu-id="1c4f6-149">이전 동작</span><span class="sxs-lookup"><span data-stu-id="1c4f6-149">Prior Behavior</span></span> | <span data-ttu-id="1c4f6-150">Windows Holographic, 버전 20H2 업데이트의 동작</span><span class="sxs-lookup"><span data-stu-id="1c4f6-150">Behavior from Windows Holographic, version 20H2 Update</span></span> |
|:-------------------|:-----------------|:-----------------------------------|
| <span data-ttu-id="1c4f6-151">비응시 사용 앱 또는 홀로그램 셸</span><span class="sxs-lookup"><span data-stu-id="1c4f6-151">Non-gaze enabled app or Holographic Shell</span></span> |<span data-ttu-id="1c4f6-152">시선 추적 보정 프롬프트 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-152">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="1c4f6-153">프롬프트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-153">No prompt is displayed.</span></span> |
| <span data-ttu-id="1c4f6-154">응시를 사용하는 앱</span><span class="sxs-lookup"><span data-stu-id="1c4f6-154">Gaze enabled app</span></span> | <span data-ttu-id="1c4f6-155">시선 추적 보정 프롬프트 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-155">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="1c4f6-156">시선 응시 스트림에 액세스하는 경우에만 시선 추적 보정 프롬프트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-156">Eye tracking calibration prompt is displayed only when the application accesses eye gaze stream.</span></span> |

<span data-ttu-id="1c4f6-157">사용자가 비응시를 사용하는 응용 프로그램에서 응시 데이터에 액세스하는 앱으로 전환하는 경우 보정 프롬프트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-157">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> 

<span data-ttu-id="1c4f6-158">다른 모든 시스템 동작은 현재 사용자에게 활성 시선 추적 보정이 없는 경우와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-158">All other system behavior will be similar to when the current user doesn't have an active eye tracking calibration.</span></span> <span data-ttu-id="1c4f6-159">예를 들어, 일회성 시작 제스처는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-159">For example, the One-handed Start gesture won't be enabled.</span></span> <span data-ttu-id="1c4f6-160">초기 설정에 대한 OOBE(첫 실행 경험)는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-160">There will be no change to the Out-Of-Box-Experience for initial setup.</span></span>

<span data-ttu-id="1c4f6-161">시선 응시 데이터 또는 홀로그램 위치가 필요한 환경에서는 보정되지 않은 사용자가 시선 추적 보정을 실행하도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-161">For experiences that require eye gaze data or precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration.</span></span> <span data-ttu-id="1c4f6-162">시선 추적 보정 프롬프트에서 액세스하거나 시작 메뉴에서 설정 앱을 실행한 다음 **시스템 > 보정 > 눈 보정 > 눈 보정 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-162">It's accessible from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

#### <span data-ttu-id="1c4f6-163">지연된 보정 프롬프트</span><span class="sxs-lookup"><span data-stu-id="1c4f6-163">Deferred Calibration Prompt</span></span>

<span data-ttu-id="1c4f6-164">자동 눈 위치를 사용하면 응용 프로그램이 시선 응시 데이터를 요청할 때까지 시선 추적 보정 프롬프트 대화 상자가 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-164">With Auto Eye Position, the Eye Tracking Calibration prompt dialog is deferred until an application requests Eye Gaze data.</span></span> <span data-ttu-id="1c4f6-165">이렇게 하면 활성 응용 프로그램에 응시가 필요하지 않을 때 사용자에 게 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-165">This ensures that there's no prompt to the user when the active application doesn't require gaze.</span></span> <span data-ttu-id="1c4f6-166">응용 프로그램에 응시 데이터가 필요하고 현재 사용자가 보정되지 않은 경우 사용자에게 보정 프롬프트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-166">If the application does require gaze data and the current user isn't calibrated, the user is presented with a calibration prompt.</span></span> <span data-ttu-id="1c4f6-167">이 동작은 환경에 적합한 시간에 시선 추적 보정 프롬프트를 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-167">This behavior could be used to display eye tracking calibration prompt at a suitable time for the experience.</span></span> <span data-ttu-id="1c4f6-168">이 방법은 다음과 같은 이유로 권장됨</span><span class="sxs-lookup"><span data-stu-id="1c4f6-168">This method is recommended for the following reasons</span></span>

1.  <span data-ttu-id="1c4f6-169">시선 추적 보정 프롬프트 대화 상자에서는 시선 추적이 필요한 이유에 대 한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-169">The Eye Tracking Calibration Prompt dialog provides the user with details on why eye tracking is needed.</span></span>
2.  <span data-ttu-id="1c4f6-170">사용자에게 눈 보정을 거절할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-170">Presents the user a way to decline to have their eyes calibrated.</span></span>

<span data-ttu-id="1c4f6-171">사용자가 시선 추적 보정을 시작하기로 선택하면 보정을 완료한 후에 초점이 원래 응용 프로그램으로 돌아가야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-171">If the user chooses to launch the Eye Tracking Calibration, the focus should returning to the original application after calibration completes.</span></span> 

### <span data-ttu-id="1c4f6-172">HoloLens 2 보정 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1c4f6-172">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="1c4f6-173">대부분의 사람들은 보정을 사용할 수 있지만 보정이 실패하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-173">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="1c4f6-174">보정 실패의 몇 가지 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-174">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="1c4f6-175">주의가 산만해지고 보정 대상을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-175">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="1c4f6-176">더럽거나 긁힌 장치 바이저 또는 장치 바이저가 올바르게 배치되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-176">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="1c4f6-177">더럽거나 긁힌 안경</span><span class="sxs-lookup"><span data-stu-id="1c4f6-177">Dirty or scratched glasses</span></span>
- <span data-ttu-id="1c4f6-178">특정 유형의 콘택트렌즈 및 안경(컬러 콘택트렌즈, 일부 토릭 콘택트렌즈, IR 차단 안경, 일부 높은 처방 안경, 선글라스 또는 유사한 제품)</span><span class="sxs-lookup"><span data-stu-id="1c4f6-178">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="1c4f6-179">진한 메이크업 및 일부 속눈썹 연장</span><span class="sxs-lookup"><span data-stu-id="1c4f6-179">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="1c4f6-180">머리나 두꺼운 안경테 때문에 장치가 사용자의 눈을 볼 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="1c4f6-180">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="1c4f6-181">좁은 눈, 긴 속눈썹, 약시, 안구 진탕증, 일부 라식 수술, 기타 안구 수술 등과 같은 특정 안구 생리학, 눈 상태 또는 안구 수술</span><span class="sxs-lookup"><span data-stu-id="1c4f6-181">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="1c4f6-182">보정에 실패하는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-182">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="1c4f6-183">장치 바이저 청소</span><span class="sxs-lookup"><span data-stu-id="1c4f6-183">Cleaning your device visor</span></span>
- <span data-ttu-id="1c4f6-184">안경 청소</span><span class="sxs-lookup"><span data-stu-id="1c4f6-184">Cleaning your glasses</span></span>
- <span data-ttu-id="1c4f6-185">장치 바이저를 최대한 눈에 밀착</span><span class="sxs-lookup"><span data-stu-id="1c4f6-185">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="1c4f6-186">바이저에 있는 물체를 제거(예: 머리카락)</span><span class="sxs-lookup"><span data-stu-id="1c4f6-186">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="1c4f6-187">방에 불을 켜거나 직사광선을 피해 이동</span><span class="sxs-lookup"><span data-stu-id="1c4f6-187">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="1c4f6-188">모든 지침을 따랐지만 계속해서 보정에 실패하면 설정에서 보정 프롬프트를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-188">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="1c4f6-189">[피드백 허브](hololens-feedback.md)에 피드백을 입력하여 알려주시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-189">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="1c4f6-190">[이미지 색상 또는 밝기 문제 해결](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) 관련 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-190">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="1c4f6-191">IPD 설정은 시스템에서 눈 위치를 계산하므로 HoloLens 2에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-191">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="1c4f6-192">보정 데이터 및 보안</span><span class="sxs-lookup"><span data-stu-id="1c4f6-192">Calibration data and security</span></span>

<span data-ttu-id="1c4f6-193">보정 정보는 장치에 로컬로 저장되며 계정 정보와 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-193">Calibration information is stored locally on the device and isn't associated with any account information.</span></span> <span data-ttu-id="1c4f6-194">보정 없이 장치를 사용한 사람에 대한 기록은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-194">There's no record of who has used the device without calibration.</span></span> <span data-ttu-id="1c4f6-195">즉, 이전에 보정을 옵트아웃했거나 보정에 실패한 사용자와 장치를 처음 사용할 때 시각을 보정하라는 메시지가 새 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-195">This mean new users will get prompted to calibrate visuals when they use the device for the first time, and users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="1c4f6-196">장치는 최대 50개의 보정 프로필을 로컬에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-196">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="1c4f6-197">최대 개수에 도달하면 장치에서 사용되지 않은 가장 오래된 프로파일이 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-197">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="1c4f6-198">장치의 **설정** > **개인 정보** > **시선 추적기**에서 보정 정보를 언제든지 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-198">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="1c4f6-199">보정 사용 중지</span><span class="sxs-lookup"><span data-stu-id="1c4f6-199">Disable calibration</span></span>

<span data-ttu-id="1c4f6-200">다음 단계를 수행하여 보정 프롬프트를 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-200">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="1c4f6-201">**설정** > **시스템** > **보정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-201">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="1c4f6-202">**새 사용자가 이 HoloLens를 사용하는 경우 자동으로 눈 보정을 실행하도록 요청**을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-202">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c4f6-203">이 설정은 홀로그램 렌더링 품질과 편안함에 악영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-203">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="1c4f6-204">이 설정을 끄면 시선 추적에 의존하는 기능(예: 텍스트 스크롤)이 몰입형 애플리케이션에서 더 이상 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-204">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="1c4f6-205">HoloLens 2 눈 추적 기술</span><span class="sxs-lookup"><span data-stu-id="1c4f6-205">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="1c4f6-206">이 장치는 눈 추적 기술을 사용하여 디스플레이 품질을 개선하고 모든 홀로그램을 3D로 볼 수 있도록 정확하고 편안하게 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-206">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="1c4f6-207">이 장치는 눈을 이정표로 사용하기 때문에 헤드셋을 사용하는 동안 헤드셋이 약간 움직여도 모든 사용자에 맞게 조정하고 시각을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-207">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="1c4f6-208">모든 조정은 수동으로 조정할 필요 없이 즉시 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-208">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="1c4f6-209">IPD 설정은 시스템에서 눈 위치를 계산하므로 Hololens 2에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-209">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="1c4f6-210">HoloLens 애플리케이션은 시선 추적을 사용하여 실시간으로 시선의 위치를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-210">HoloLens applications use eye tracking to track where you're looking in real time.</span></span> <span data-ttu-id="1c4f6-211">이는 개발자들이 홀로그램 환경 내에서 완전히 새로운 수준의 컨텍스트, 인간 이해 및 상호 작용을 가능하게 하기 위해 활용할 수 있는 주요 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-211">This is the main capability developers can use to enable a whole new level of context, human understanding, and interactions within the Holographic experience.</span></span> <span data-ttu-id="1c4f6-212">개발자는 이러한 기능을 활용하기 위해 어떠한 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-212">Developers don’t need to do anything to use this capability.</span></span>

## <span data-ttu-id="1c4f6-213">HoloLens(1세대) 보정</span><span class="sxs-lookup"><span data-stu-id="1c4f6-213">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="1c4f6-214">HoloLens(1세대)는 [동공 간 거리](https://en.wikipedia.org/wiki/Interpupillary_distance)(IPD)에 따라 홀로그램 디스플레이를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-214">HoloLens (1st gen) adjusts hologram display according to your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="1c4f6-215">IPD가 정확하지 않으면 홀로그램이 불안정하거나 잘못된 거리에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-215">If the IPD isn't accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="1c4f6-216">장치를 동공 간 거리(IPD)로 보정하면 시각적 품질을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-216">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="1c4f6-217">HoloLens(1세대) 장치를 설정하면 Cortana가 자신을 소개한 후 시각을 보정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-217">When you set up your HoloLens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="1c4f6-218">이 설정 단계에서는 보정 단계를 완료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-218">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="1c4f6-219">그러나 Cortana가 메시지를 표시할 때까지 기다렸다가 "건너뛰기"라고 말하면 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-219">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="1c4f6-220">보정 프로세스 중에 HoloLens에서는 눈 하나당 6개의 대상에 손가락을 정렬하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-220">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="1c4f6-221">HoloLens는 이 프로세스를 통해 눈에 IPD를 올바르게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-221">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![두 번째 단계에서 IPD 손가락 맞춤 화면](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="1c4f6-223">수동으로 보정 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="1c4f6-223">Manually start the calibration process</span></span>

<span data-ttu-id="1c4f6-224">보정을 업데이트해야 하거나 새 사용자가 조정해야 하는 경우 언제든지 보정 앱을 수동으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-224">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="1c4f6-225">보정 앱은 기본적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-225">The Calibration app is installed by default.</span></span> <span data-ttu-id="1c4f6-226">**시작** 메뉴 또는 설정 앱을 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-226">You can access it by using either the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="1c4f6-227">**시작** 메뉴를 사용하여 보정 앱을 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-227">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="1c4f6-228">[블룸](hololens1-basic-usage.md) 제스처를 사용하여 **시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-228">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="1c4f6-229">모든 앱을 보려면 **+** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-229">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="1c4f6-230">**보정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-230">Select **Calibration**.</span></span>

![셸에서 보정 앱에 액세스](./images/calibration-shell.png)

![시작된 후 라이브 큐브로 표시된 보정 앱](./images/calibration-livecube-200px.png)

<span data-ttu-id="1c4f6-233">설정 앱을 사용하여 보정 앱을 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-233">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="1c4f6-234">[블룸](hololens1-basic-usage.md) 제스처를 사용하여 **시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-234">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="1c4f6-235">**설정**이 **시작**에 고정되어 있지 않은 경우 **+** 를 선택하여 모든 앱을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-235">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="1c4f6-236">**설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-236">Select **Settings**.</span></span>
1. <span data-ttu-id="1c4f6-237">**시스템** > **유틸리티** > **보정 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-237">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![설정 앱에서 보정 앱 시작](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="1c4f6-239">몰입형 헤드셋</span><span class="sxs-lookup"><span data-stu-id="1c4f6-239">Immersive headsets</span></span>

<span data-ttu-id="1c4f6-240">일부 몰입형 헤드셋은 IPD 설정을 사용자 지정할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-240">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="1c4f6-241">헤드셋의 IPD를 변경하려면 설정 앱을 열고 **혼합 현실** > **헤드셋 디스플레이**를 선택한 다음 슬라이더 컨트롤을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-241">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="1c4f6-242">헤드셋에서 실시간으로 변경 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-242">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="1c4f6-243">안경점 방문 등의 이유로 IPD를 알고 있는 경우, IPD를 직접 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-243">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="1c4f6-244">**설정** > **혼합 현실** > **헤드셋 디스플레이**을 선택하여 PC에서 이 설정을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-244">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="1c4f6-245">헤드셋에서 IPD 사용자 지정을 지원하지 않으면 이 설정이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4f6-245">If your headset doesn't support IPD customization, this setting will be disabled.</span></span>
