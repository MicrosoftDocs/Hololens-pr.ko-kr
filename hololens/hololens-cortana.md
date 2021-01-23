---
title: Voiceover를 사용하여 HoloLens 작동
description: Cortana가 음성 명령, 받아쓰기 및 홀로그램 상호 작용을 포함하여 HoloLens 혼합 현실 장치에서 모든 종류의 작업을 수행하는 데 어떻게 도움이 되는지 알아보세요.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: dd99744dfe27f52bb4ec51ad9fa9af4bfd1f0e96
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283329"
---
# <span data-ttu-id="23c09-104">Voiceover를 사용하여 HoloLens 작동</span><span class="sxs-lookup"><span data-stu-id="23c09-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="23c09-105">음성을 사용하여 빠른 사진 촬영 또는 앱 열기 등의 HoloLens에서 거의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="23c09-106">대부분의 음성 명령은 HoloLens에 기본으로 제공되지만, Cortana를 통해 사용할 수 있는 명령도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="23c09-107">이 문서에서는 음성과 Cortana를 사용하여 HoloLens와 홀로그램 세계를 제어하는 방법을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="23c09-108">음성 명령은 [일부 언어](hololens2-language-support.md)에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="23c09-109">음성 언어는 키보드 언어가 아니라 Windows 표시 언어를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="23c09-110">**설정** > **시간 및 언어** > **언어**를 선택하여 Windows 표시 언어를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <span data-ttu-id="23c09-111">기본 제공 음성 명령</span><span class="sxs-lookup"><span data-stu-id="23c09-111">Built-in voice commands</span></span>

<span data-ttu-id="23c09-112">이러한 기본 명령을 사용하여 HoloLens를 더욱 빠르게 즐기세요.</span><span class="sxs-lookup"><span data-stu-id="23c09-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="23c09-113">이러한 기능을 사용하려면 장치를 처음 실행 하는 동안 또는 **설정 \*\* > **개인 정보** > \*\* 음성**에서 음성을 사용하도록 정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="23c09-114">시작 메뉴의 맨 위에 있는 상태에서 언제든지 음성 명령을 사용가능 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="23c09-115">최상의 음성 인식 결과를 위해 HoloLens 2에서 Microsoft 클라우드 기반 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="23c09-116">그러나 설정에서 이 기능 사용을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="23c09-117">이렇게 하려면 설정에서 **온라인 음성 인식**을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="23c09-118">이 설정을 변경한 후에는 HoloLens 2가 명령과 발성을 이해하기 위해 로컬 음성 데이터만 사용하고 Cortana를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <span data-ttu-id="23c09-119">일반 음성 명령</span><span class="sxs-lookup"><span data-stu-id="23c09-119">General speech commands</span></span>

<span data-ttu-id="23c09-120">Windows Mixed Reality에서 이러한 명령을 사용하여 더 빠르게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="23c09-121">몇 가지 명령은 "선택"을 말하여 가져올 수 있는 응시 커서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="23c09-122">손 광선은 HoloLens(1세대)에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="23c09-123">다음을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-123">Say this</span></span> | <span data-ttu-id="23c09-124">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="23c09-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="23c09-125">"Select"</span><span class="sxs-lookup"><span data-stu-id="23c09-125">"Select"</span></span> | <span data-ttu-id="23c09-126">"선택"이라고 말하여 응시 커서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="23c09-127">그런 다음 고개를 돌려 선택할 항목에 커서를 놓고 "선택"이라고 다시 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
|<span data-ttu-id="23c09-128">Open the Start menu</span><span class="sxs-lookup"><span data-stu-id="23c09-128">Open the Start menu</span></span> | <span data-ttu-id="23c09-129">"시작으로 이동"</span><span class="sxs-lookup"><span data-stu-id="23c09-129">"Go to Start"</span></span> |
|<span data-ttu-id="23c09-130">Close the Start menu</span><span class="sxs-lookup"><span data-stu-id="23c09-130">Close the Start menu</span></span> | <span data-ttu-id="23c09-131">"닫기"</span><span class="sxs-lookup"><span data-stu-id="23c09-131">"Close"</span></span> |
|<span data-ttu-id="23c09-132">Leave an immersive app</span><span class="sxs-lookup"><span data-stu-id="23c09-132">Leave an immersive app</span></span> | <span data-ttu-id="23c09-133">"시작으로 이동"이라고 말해 바로 가기 메뉴를 표시한 다음 "혼합 현실 홈"이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-133">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span> |
|<span data-ttu-id="23c09-134">Hide and show hand ray</span><span class="sxs-lookup"><span data-stu-id="23c09-134">Hide and show hand ray</span></span> | <span data-ttu-id="23c09-135">"손 광선 숨기기" / "손 관성 표시"</span><span class="sxs-lookup"><span data-stu-id="23c09-135">"Hide hand ray" / "Show hand ray"</span></span> |
|<span data-ttu-id="23c09-136">See available speech commands</span><span class="sxs-lookup"><span data-stu-id="23c09-136">See available speech commands</span></span> | <span data-ttu-id="23c09-137">"이렇게 말 하세요~"</span><span class="sxs-lookup"><span data-stu-id="23c09-137">"What can I say?"</span></span> |

<span data-ttu-id="23c09-138">HoloLens 2의 버전 19041.x부터 다음 명령을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="23c09-139">다음을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-139">Say this</span></span> | <span data-ttu-id="23c09-140">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="23c09-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="23c09-141">"Restart device"</span><span class="sxs-lookup"><span data-stu-id="23c09-141">"Restart device"</span></span> | <span data-ttu-id="23c09-142">장치를 다시 시작할지 확인하는 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="23c09-143">다시 시작하려면 "yes"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="23c09-144">"Shutdown device"</span><span class="sxs-lookup"><span data-stu-id="23c09-144">"Shutdown device"</span></span> | <span data-ttu-id="23c09-145">장치를 끌지 확인하는 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="23c09-146">"yes"라고 말하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="23c09-147">"Brightness up/down"</span><span class="sxs-lookup"><span data-stu-id="23c09-147">"Brightness up/down"</span></span> | <span data-ttu-id="23c09-148">디스플레이 밝기를 10%씩 늘리거나 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="23c09-149">"Volume up/down"</span><span class="sxs-lookup"><span data-stu-id="23c09-149">"Volume up/down"</span></span> | <span data-ttu-id="23c09-150">볼륨을 10%씩 늘리거나 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="23c09-151">"What's my IP address"</span><span class="sxs-lookup"><span data-stu-id="23c09-151">"What's my IP address"</span></span> | <span data-ttu-id="23c09-152">로컬 네트워크에서 장치의 현재 IP 주소를 나타내는 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="23c09-153">"Take a picture"</span><span class="sxs-lookup"><span data-stu-id="23c09-153">"Take a picture"</span></span> | <span data-ttu-id="23c09-154">현재 보고 있는 혼합 현실 사진을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="23c09-155">"Take a video"</span><span class="sxs-lookup"><span data-stu-id="23c09-155">"Take a video"</span></span> | <span data-ttu-id="23c09-156">혼합 현실 비디오 녹화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="23c09-157">"Stop recording"</span><span class="sxs-lookup"><span data-stu-id="23c09-157">"Stop recording"</span></span> | <span data-ttu-id="23c09-158">현재 진행 중인 혼합 현실 비디오 녹화를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <span data-ttu-id="23c09-159">홀로그램 명령</span><span class="sxs-lookup"><span data-stu-id="23c09-159">Hologram commands</span></span>

<span data-ttu-id="23c09-160">이러한 명령을 사용하려면 3D 개체, 홀로그램 또는 앱 창에서 응시하세요.</span><span class="sxs-lookup"><span data-stu-id="23c09-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="23c09-161">다음을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-161">Say this</span></span> | <span data-ttu-id="23c09-162">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="23c09-163">"Bigger"</span><span class="sxs-lookup"><span data-stu-id="23c09-163">"Bigger"</span></span> | <span data-ttu-id="23c09-164">크게 만들기</span><span class="sxs-lookup"><span data-stu-id="23c09-164">Make it bigger</span></span> |
| <span data-ttu-id="23c09-165">"Smaller"</span><span class="sxs-lookup"><span data-stu-id="23c09-165">"Smaller"</span></span> | <span data-ttu-id="23c09-166">작게 만들기</span><span class="sxs-lookup"><span data-stu-id="23c09-166">Make it smaller</span></span> |
| <span data-ttu-id="23c09-167">"Face me"</span><span class="sxs-lookup"><span data-stu-id="23c09-167">"Face me"</span></span> | <span data-ttu-id="23c09-168">나를 보게 돌리기</span><span class="sxs-lookup"><span data-stu-id="23c09-168">Turn it to face you</span></span> |
| <span data-ttu-id="23c09-169">"Move this"</span><span class="sxs-lookup"><span data-stu-id="23c09-169">"Move this"</span></span> | <span data-ttu-id="23c09-170">이동(응시 따르기)</span><span class="sxs-lookup"><span data-stu-id="23c09-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="23c09-171">"Close"</span><span class="sxs-lookup"><span data-stu-id="23c09-171">"Close"</span></span> | <span data-ttu-id="23c09-172">닫기</span><span class="sxs-lookup"><span data-stu-id="23c09-172">Close it</span></span> |
| <span data-ttu-id="23c09-173">"Follow me" / "Stop following"</span><span class="sxs-lookup"><span data-stu-id="23c09-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="23c09-174">사용자가 이동하는 대로 함께 움직입니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-174">Make it follow you as you move around</span></span> |

### <span data-ttu-id="23c09-175">보고 말하세요</span><span class="sxs-lookup"><span data-stu-id="23c09-175">See it, say it</span></span>

<span data-ttu-id="23c09-176">HoloLens의 많은 단추와 기타 요소는 사용자의 음성에도 응답합니다 (예: 앱 바에서 **날 따라와** 및 **닫기** 또는 Edge에서 **뒤로** 단추)</span><span class="sxs-lookup"><span data-stu-id="23c09-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="23c09-177">버튼이 음성작동 가능한지 여부를 확인하려면 **응시 커서**,**터치 커서**혹은 한 **손 광선**을 일시적으로 올려놓습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-177">To find out if a button is voice-enabled, rest your **gaze cursor**,**touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="23c09-178">음성 작동이 가능하면 음성 팁이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <span data-ttu-id="23c09-179">받아쓰기 모드</span><span class="sxs-lookup"><span data-stu-id="23c09-179">Dictation mode</span></span>

<span data-ttu-id="23c09-180">입력하기 지겨우시죠?</span><span class="sxs-lookup"><span data-stu-id="23c09-180">Tired of typing?</span></span> <span data-ttu-id="23c09-181">키보드가 활성화되어 있을 때 언제든지 받아쓰기 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-181">Switch to dictation mode any time that the holographic keyboard is active.</span></span> <span data-ttu-id="23c09-182">시작하려면 마이크 버튼을 선택하거나 "받아쓰기 시작"이라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="23c09-183">받아쓰기를 중지하려면 버튼을 다시 선택하거나 "받아쓰기 중지"라고 말하세요.</span><span class="sxs-lookup"><span data-stu-id="23c09-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="23c09-184">방금 받아쓴 내용을 삭제하려면 "이 텍스트 삭제"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="23c09-185">받아쓰기 모드를 사용하려면 인터넷에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="23c09-186">HoloLens 받아쓰기는 명시적 문장 부호를 사용하여 사용하려는 문장 부호의 이름을 말하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="23c09-187">예를 들어, "안녕 **쉼표** 지금 뭐해 **물음표**"라고 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="23c09-188">다음은 사용할 수 있는 문장 부호 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="23c09-189">마침표, 쉼표, 물음표, 느낌표</span><span class="sxs-lookup"><span data-stu-id="23c09-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="23c09-190">새 줄/새 단락</span><span class="sxs-lookup"><span data-stu-id="23c09-190">New line/new paragraph</span></span>
- <span data-ttu-id="23c09-191">세미콜론, 콜론</span><span class="sxs-lookup"><span data-stu-id="23c09-191">Semicolon, colon</span></span>
- <span data-ttu-id="23c09-192">여는 따옴표, 닫는 따옴표</span><span class="sxs-lookup"><span data-stu-id="23c09-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="23c09-193">해시태그, 웃는 얼굴, 찡그린, 윙크</span><span class="sxs-lookup"><span data-stu-id="23c09-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="23c09-194">달러, 퍼센트</span><span class="sxs-lookup"><span data-stu-id="23c09-194">Dollar, percent</span></span>

<span data-ttu-id="23c09-195">경우에 따라 이메일 주소 등의 철자를 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="23c09-196">예를 들어 example@outlook.com을 받아쓰려면 "outlook 닷 컴 엣 E X A M P L E"라고 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <span data-ttu-id="23c09-197">Cortana로 더 많은 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="23c09-197">Do more with Cortana</span></span>

<span data-ttu-id="23c09-198">Cortana를 사용하여 HoloLens에서 모든 종류의 작업을 수행할 수 있지만 사용 중인 Windows Holographic 버전에 따라 기능이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capablities may be different.</span></span> <span data-ttu-id="23c09-199">[여기](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)에서 Cortana 최신 버전의 업데이트된 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-199">You can learn more about the updated capabilites of the latest version of Cortana [here](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![안녕 코타나!](images/cortana-on-hololens.png)

<span data-ttu-id="23c09-201">다음처럼 말할 수 있습니다("안녕 코타나"를 먼저 말해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="23c09-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="23c09-202">**Hey, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="23c09-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="23c09-203">What can I say?</span><span class="sxs-lookup"><span data-stu-id="23c09-203">What can I say?</span></span>
- <span data-ttu-id="23c09-204">Launch <*앱 이름*></span><span class="sxs-lookup"><span data-stu-id="23c09-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="23c09-205">What time is it?</span><span class="sxs-lookup"><span data-stu-id="23c09-205">What time is it?</span></span>
- <span data-ttu-id="23c09-206">Show me the latest NBA scores.</span><span class="sxs-lookup"><span data-stu-id="23c09-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="23c09-207">Tell me a joke.</span><span class="sxs-lookup"><span data-stu-id="23c09-207">Tell me a joke.</span></span>

<span data-ttu-id="23c09-208">*버전 18362.x 또는 이전 버전*을 사용하는 경우 다음 명령을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="23c09-209">**Hey, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="23c09-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="23c09-210">Increase the volume.</span><span class="sxs-lookup"><span data-stu-id="23c09-210">Increase the volume.</span></span>
- <span data-ttu-id="23c09-211">Decrease the brightness.</span><span class="sxs-lookup"><span data-stu-id="23c09-211">Decrease the brightness.</span></span>
- <span data-ttu-id="23c09-212">Shut down.</span><span class="sxs-lookup"><span data-stu-id="23c09-212">Shut down.</span></span>
- <span data-ttu-id="23c09-213">Restart.</span><span class="sxs-lookup"><span data-stu-id="23c09-213">Restart.</span></span>
- <span data-ttu-id="23c09-214">Go to sleep.</span><span class="sxs-lookup"><span data-stu-id="23c09-214">Go to sleep.</span></span>
- <span data-ttu-id="23c09-215">Mute.</span><span class="sxs-lookup"><span data-stu-id="23c09-215">Mute.</span></span>
- <span data-ttu-id="23c09-216">Move <*앱 이름*> here (앱을 이동하고자 하는 지점을 응시).</span><span class="sxs-lookup"><span data-stu-id="23c09-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="23c09-217">Go to Start.</span><span class="sxs-lookup"><span data-stu-id="23c09-217">Go to Start.</span></span>
- <span data-ttu-id="23c09-218">Take a picture.</span><span class="sxs-lookup"><span data-stu-id="23c09-218">Take a picture.</span></span>
- <span data-ttu-id="23c09-219">Start recording.</span><span class="sxs-lookup"><span data-stu-id="23c09-219">Start recording.</span></span> <span data-ttu-id="23c09-220">(동영상 녹화 시작.)</span><span class="sxs-lookup"><span data-stu-id="23c09-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="23c09-221">Stop recording.</span><span class="sxs-lookup"><span data-stu-id="23c09-221">Stop recording.</span></span> <span data-ttu-id="23c09-222">(동영상 녹화 중지.)</span><span class="sxs-lookup"><span data-stu-id="23c09-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="23c09-223">How much battery do I have left?</span><span class="sxs-lookup"><span data-stu-id="23c09-223">How much battery do I have left?</span></span>

<span data-ttu-id="23c09-224">Microsoft HoloLens에서는 PC 또는 휴대폰(예: 미리 알림 및 알림)의 Windows에서 사용하는 일부 Cortana 기능이 지원되지 않으며 Cortana 환경은 환경마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <span data-ttu-id="23c09-225">Cortana 끄기</span><span class="sxs-lookup"><span data-stu-id="23c09-225">Turn Cortana off</span></span>

<span data-ttu-id="23c09-226">음성 명령을 사용하도록 설정한 경우 처음으로 HoloLens를 사용할 때 Cortana가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="23c09-227">Cortana 설정에서 이 기능을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="23c09-228">**모든 앱** 목록에서 **Cortana** > **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="23c09-229">그런 다음 끕니다. Cortana는 제안 사항, 아이디어, 미리 알림, 경고 등을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="23c09-230">Cortana가 "안녕 코타나"에 응답하지 않으면 시작에서 음성 명령이 사용할 수 있도록 되어 있는지 확인하고 Cortana 설정으로 이동하여 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23c09-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
