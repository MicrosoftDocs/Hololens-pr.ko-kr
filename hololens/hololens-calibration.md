---
title: 시각적 품질과 편안함 개선
description: IPD(동공 간 거리)를 보정하면 시각적 품질을 향상시킬 수 있습니다. HoloLens 및 Windows Mixed Reality 몰입형 헤드셋은 모두 IPD를 사용자 지정하는 방법을 제공합니다.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: 보정, 편안함, 시각적, 품질, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f2c8afffdc24eedf9cb6b462448f5ed6ffc8d5d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828773"
---
# <span data-ttu-id="93c07-105">시각적 품질과 편안함 개선</span><span class="sxs-lookup"><span data-stu-id="93c07-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="93c07-106">HoloLens 2 및 HoloLens(1세대) 모두 사용자의 눈에 맞게 보정될 때 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="93c07-107">두 장치 모두 최상의 홀로그램 보기 환경을 위해 보정해야 하지만, 서로 다른 보정 기술과 기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="93c07-108">[HoloLens 2 보정](#calibrating-your-hololens-2) 또는 [HoloLens(1세대) 보정](#calibrating-your-hololens-1st-gen)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="93c07-109">HoloLens 2 보정</span><span class="sxs-lookup"><span data-stu-id="93c07-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="93c07-110">HoloLens 2는 눈 추적 기술을 사용하여 가상 환경을 보고 상호 작용하는 경험을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="93c07-111">HoloLens 2를 보정하면 사용자의 눈(및 기기를 사용하는 다른 사람의 눈)을 정확하게 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="93c07-112">이는 사용자 편안함, 홀로그램 맞춤, 손 추적에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="93c07-113">보정이 완료되면 바이저가 머리 위에서 움직여도 홀로그램이 올바르게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="93c07-114">HoloLens 2는 사용자에게 다음과 같은 상황에서 장치를 보정하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="93c07-115">사용자가 처음으로 장치를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="93c07-116">사용자가 이전에 보정 프로세스에서 옵트아웃했습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="93c07-117">사용자가 마지막으로 장치를 사용할 때 보정 프로세스가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="93c07-118">사용자가 보정 프로필을 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="93c07-119">장치가 제거되었다가 다시 착용되어 위의 상황이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![보정 프롬프트](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="93c07-121">이 프로세스 중에 대상(보석)의 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="93c07-122">보정을 하는 동안 눈을 깜빡여도 괜찮지만 방에 있는 다른 물체보다는 보석을 응시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="93c07-123">이렇게 하면 HoloLens가 홀로그램 세계를 렌더링하기 위해 눈 위치를 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-123">This allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![보정 프롬프트](./images/07-et-hold-head-still.png)

![보정 프롬프트](./images/08-et-gems.png)

![보정 프롬프트](./images/09-et-adjusting.png)

<span data-ttu-id="93c07-127">보정에 성공했다면 성공 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="93c07-128">그렇지 않은 경우 [여기](#troubleshooting-hololens-2-calibration)에서 보정 오류를 진단하는 방법에 대한 자세한 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![보정 프롬프트](./images/10-et-success.png)

### <span data-ttu-id="93c07-130">장치 또는 세션을 공유할 때의 보정</span><span class="sxs-lookup"><span data-stu-id="93c07-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="93c07-131">여러 사용자가 HoloLens 2 장치를 공유할 수 있으며 각 사용자가 장치 설정을 수행할 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="93c07-132">새 사용자가 장치를 처음으로 머리에 착용하면 HoloLens 2는 사용자에게 시각을 보정하라는 메시지를 자동으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="93c07-133">이전에 시각을 보정한 사용자가 장치를 머리에 착용하면 디스플레이가 화질과 편안한 보기 환경을 위해 매끄럽게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="93c07-134">수동으로 보정 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="93c07-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="93c07-135">시작 제스처를 사용하여 [**시작** 메뉴](hololens2-basic-usage.md#start-gesture)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="93c07-136">설정 앱이 **시작**에 고정되어 있지 않으면 **모든 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="93c07-137">**설정**을 선택한 다음 **시스템** > **보정** > **눈 보정** > **눈 보정 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![눈 보정 실행 옵션을 보여 주는 설정 앱](./images/C-Settings.Calibration.png)

### <span data-ttu-id="93c07-139">HoloLens 2 보정 문제 해결</span><span class="sxs-lookup"><span data-stu-id="93c07-139">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="93c07-140">대부분의 사람들은 보정을 사용할 수 있지만 보정이 실패하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-140">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="93c07-141">보정 실패의 몇 가지 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-141">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="93c07-142">주의가 산만해지고 보정 대상을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-142">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="93c07-143">더럽거나 긁힌 장치 바이저 또는 장치 바이저가 올바르게 배치되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-143">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="93c07-144">더럽거나 긁힌 안경</span><span class="sxs-lookup"><span data-stu-id="93c07-144">Dirty or scratched glasses</span></span>
- <span data-ttu-id="93c07-145">특정 유형의 콘택트렌즈 및 안경(컬러 콘택트렌즈, 일부 토릭 콘택트렌즈, IR 차단 안경, 일부 높은 처방 안경, 선글라스 또는 유사한 제품)</span><span class="sxs-lookup"><span data-stu-id="93c07-145">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="93c07-146">진한 메이크업 및 일부 속눈썹 연장</span><span class="sxs-lookup"><span data-stu-id="93c07-146">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="93c07-147">머리나 두꺼운 안경테 때문에 장치가 사용자의 눈을 보지 못하는 경우</span><span class="sxs-lookup"><span data-stu-id="93c07-147">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="93c07-148">좁은 눈, 긴 속눈썹, 약시, 안구 진탕증, 일부 라식 수술, 기타 안구 수술 등과 같은 특정 안구 생리학, 눈 상태 또는 안구 수술</span><span class="sxs-lookup"><span data-stu-id="93c07-148">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="93c07-149">보정에 실패하는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-149">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="93c07-150">장치 바이저 청소</span><span class="sxs-lookup"><span data-stu-id="93c07-150">Cleaning your device visor</span></span>
- <span data-ttu-id="93c07-151">안경 청소</span><span class="sxs-lookup"><span data-stu-id="93c07-151">Cleaning your glasses</span></span>
- <span data-ttu-id="93c07-152">장치 바이저를 최대한 눈에 밀착</span><span class="sxs-lookup"><span data-stu-id="93c07-152">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="93c07-153">바이저에 있는 물체를 제거(예: 머리카락)</span><span class="sxs-lookup"><span data-stu-id="93c07-153">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="93c07-154">방에 불을 켜거나 직사광선을 피해 이동</span><span class="sxs-lookup"><span data-stu-id="93c07-154">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="93c07-155">모든 지침을 따랐지만 계속해서 보정에 실패하면 설정에서 보정 프롬프트를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-155">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="93c07-156">[피드백 허브](hololens-feedback.md)에 피드백을 입력하여 알려주시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-156">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="93c07-157">IPD 설정은 시스템에서 눈 위치를 계산하므로 Hololens 2에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-157">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="93c07-158">보정 데이터 및 보안</span><span class="sxs-lookup"><span data-stu-id="93c07-158">Calibration data and security</span></span>

<span data-ttu-id="93c07-159">보정 정보는 장치에 로컬로 저장되며 계정 정보와 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-159">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="93c07-160">보정 없이 장치를 사용한 사람에 대한 기록은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-160">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="93c07-161">즉, 이전에 보정을 옵트아웃했거나 보정에 실패한 사용자뿐만 아니라 장치를 처음 사용할 때 시각을 보정하라는 메시지가 새 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-161">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="93c07-162">장치는 최대 50개의 보정 프로필을 로컬에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-162">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="93c07-163">최대 개수에 도달하면 장치에서 사용되지 않은 가장 오래된 프로파일이 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-163">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="93c07-164">장치의 **설정** > **개인 정보** > **시선 추적기**에서 보정 정보를 언제든지 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-164">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="93c07-165">보정 사용 중지</span><span class="sxs-lookup"><span data-stu-id="93c07-165">Disable calibration</span></span>

<span data-ttu-id="93c07-166">다음 단계를 수행하여 보정 프롬프트를 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-166">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="93c07-167">**설정** > **시스템** > **보정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-167">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="93c07-168">**새 사용자가 이 HoloLens를 사용하는 경우 자동으로 눈 보정을 실행하도록 요청**을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-168">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93c07-169">이 설정은 홀로그램 렌더링 품질과 편안함에 악영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-169">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="93c07-170">이 설정을 끄면 시선 추적에 의존하는 기능(예: 텍스트 스크롤)이 몰입형 애플리케이션에서 더 이상 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-170">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="93c07-171">HoloLens 2 눈 추적 기술</span><span class="sxs-lookup"><span data-stu-id="93c07-171">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="93c07-172">이 장치는 눈 추적 기술을 사용하여 디스플레이 품질을 개선하고 모든 홀로그램을 3D로 볼 수 있도록 정확하고 편안하게 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-172">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="93c07-173">이 장치는 눈을 이정표로 사용하기 때문에 헤드셋을 사용하는 동안 헤드셋이 약간 움직여도 모든 사용자에 맞게 조정하고 시각을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-173">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="93c07-174">모든 조정은 수동으로 조정할 필요 없이 즉시 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-174">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="93c07-175">IPD 설정은 시스템에서 눈 위치를 계산하므로 Hololens 2에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-175">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="93c07-176">HoloLens 애플리케이션은 시선 추적을 사용하여 실시간으로 시선의 위치를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-176">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="93c07-177">이는 개발자들이 홀로그램 환경 내에서 완전히 새로운 수준의 컨텍스트, 인간 이해 및 상호 작용을 가능하게 하기 위해 활용할 수 있는 주요 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-177">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="93c07-178">개발자는 이러한 기능을 활용하기 위해 어떠한 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-178">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="93c07-179">HoloLens(1세대) 보정</span><span class="sxs-lookup"><span data-stu-id="93c07-179">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="93c07-180">HoloLens(1세대)는 [동공 간 거리](https://en.wikipedia.org/wiki/Interpupillary_distance)(IPD)에 따라 홀로그램 디스플레이를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-180">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="93c07-181">IPD가 정확하지 않으면 홀로그램이 불안정하거나 잘못된 거리에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-181">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="93c07-182">장치를 동공 간 거리(IPD)로 보정하면 시각적 품질을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-182">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="93c07-183">HoloLens (1세대) 장치를 설정하면 Cortana가 자신을 소개한 후 시각을 보정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-183">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="93c07-184">이 설정 단계에서는 보정 단계를 완료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-184">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="93c07-185">그러나 Cortana가 메시지를 표시할 때까지 기다렸다가 "건너뛰기"라고 말하면 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-185">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="93c07-186">보정 프로세스 중에 HoloLens에서는 눈 하나당 6개의 대상에 손가락을 정렬하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-186">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="93c07-187">HoloLens는 이 프로세스를 통해 눈에 IPD를 올바르게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-187">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![두 번째 단계에서 IPD 손가락 맞춤 화면](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="93c07-189">수동으로 보정 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="93c07-189">Manually start the calibration process</span></span>

<span data-ttu-id="93c07-190">보정을 업데이트해야 하거나 새 사용자가 조정해야 하는 경우 언제든지 보정 앱을 수동으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-190">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="93c07-191">보정 앱은 기본적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-191">The Calibration app is installed by default.</span></span> <span data-ttu-id="93c07-192">**시작** 메뉴 또는 설정 앱을 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-192">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="93c07-193">**시작** 메뉴를 사용하여 보정 앱을 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-193">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="93c07-194">[블룸](hololens1-basic-usage.md) 제스처를 사용하여 **시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-194">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="93c07-195">모든 앱을 보려면 **+** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-195">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="93c07-196">**보정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-196">Select **Calibration**.</span></span>

![셸에서 보정 앱에 액세스](./images/calibration-shell.png)

![시작된 후 라이브 큐브로 표시된 보정 앱](./images/calibration-livecube-200px.png)

<span data-ttu-id="93c07-199">설정 앱을 사용하여 보정 앱을 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-199">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="93c07-200">[블룸](hololens1-basic-usage.md) 제스처를 사용하여 **시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-200">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="93c07-201">**설정**이 **시작**에 고정되어 있지 않은 경우 **+** 를 선택하여 모든 앱을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-201">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="93c07-202">**설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-202">Select **Settings**.</span></span>
1. <span data-ttu-id="93c07-203">**시스템** > **유틸리티** > **보정 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-203">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![설정 앱에서 보정 앱 시작](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="93c07-205">몰입형 헤드셋</span><span class="sxs-lookup"><span data-stu-id="93c07-205">Immersive headsets</span></span>

<span data-ttu-id="93c07-206">일부 몰입형 헤드셋은 IPD 설정을 사용자 지정할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-206">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="93c07-207">헤드셋의 IPD를 변경하려면 설정 앱을 열고 **혼합 현실** > **헤드셋 디스플레이**를 선택한 다음 슬라이더 컨트롤을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-207">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="93c07-208">헤드셋에서 실시간으로 변경 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-208">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="93c07-209">안경점 방문 등의 이유로 IPD를 알고 있는 경우, IPD를 직접 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-209">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="93c07-210">**설정** > **혼합 현실** > **헤드셋 디스플레이**을 선택하여 PC에서 이 설정을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-210">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="93c07-211">헤드셋에서 IPD 사용자 지정을 지원하지 않으면 이 설정이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c07-211">If your headset does not support IPD customization, this setting will be disabled.</span></span>
