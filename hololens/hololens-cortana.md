---
title: 음성을 사용하여 HoloLens 작동
description: Cortana가 음성 명령, 받아쓰기 및 홀로그램 상호 작용을 포함하여 HoloLens 혼합 현실 디바이스에서 모든 종류의 작업을 수행하는 데 어떻게 도움이 되는지 알아보세요.
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
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034224"
---
# <a name="use-your-voice-to-operate-hololens"></a>음성을 사용하여 HoloLens 작동

HoloLens에서는 음성을 사용하여 빠른 사진 촬영 또는 앱 열기 등 거의 모든 작업을 수행할 수 있습니다. 대부분의 음성 명령은 HoloLens에 기본으로 제공되지만, Cortana를 통해 사용할 수 있는 명령도 많습니다.

이 문서에서는 음성과 Cortana를 사용하여 HoloLens와 홀로그램 세계를 제어하는 방법을 알려줍니다.

> [!NOTE]
> 음성은 [일부 언어](hololens2-language-support.md)로만 지원됩니다. 음성 언어는 키보드 언어가 아니라 Windows 표시 언어를 기반으로 합니다.  
>  
> **설정** > **시간 및 언어** > **언어** 를 선택하여 Windows 표시 언어를 확인할 수 있습니다.

## <a name="built-in-voice-commands"></a>기본 제공 음성 명령

이러한 기본 명령을 사용하여 HoloLens를 더욱 빠르게 즐기세요. 이러한 기능을 사용하려면 디바이스를 처음 실행하는 동안 또는 **설정** > **개인 정보** > **음성** 에서 음성을 사용하도록 설정해야 합니다. 시작 메뉴의 맨 위에 있는 상태에서 언제든지 음성 명령의 사용 가능 여부를 확인할 수 있습니다. 최상의 음성 인식 결과를 위해 HoloLens 2에서 Microsoft 클라우드 기반 서비스를 사용합니다. 그러나 설정에서 이 기능을 사용하지 않도록 설정할 수 있습니다. 이렇게 하려면 설정에서 **온라인 음성 인식** 을 비활성화합니다. 이 설정을 변경한 후에는 HoloLens 2가 명령과 발성을 이해하기 위해 로컬 음성 데이터만 사용하고 Cortana를 사용할 수 없게 됩니다.

### <a name="general-speech-commands"></a>일반 음성 명령

Windows Mixed Reality에서 이러한 명령을 사용하여 더 빠르게 탐색할 수 있습니다. 몇 가지 명령은 "select"라고 말하여 가져올 수 있는 응시 커서를 사용합니다.

> [!NOTE]
> 손 광선은 HoloLens(1세대)에서 지원되지 않습니다.

| 다음과 같이 말하기 | 원하는 작업 |
| - | - |
| "Select" | "select"라고 말하여 응시 커서를 표시합니다. 그런 다음, 고개를 돌려 커서를 선택할 항목에 놓고 "select"라고 다시 말합니다. |
| "Go to Start" |  시작 메뉴 열기 |
| "Close"  | 시작 메뉴 닫기 |
| "Go to Start"라고 말해 바로 가기 메뉴를 표시한 다음, "Mixed reality home"이라고 말합니다.  | 몰입형 앱 나가기 |
| "Hide hand ray" / "Show hand ray" | 손 광선 숨기기 및 표시 |
| "이렇게 말 하세요~"  | 사용 가능한 음성 명령 보기 |

HoloLens 2의 버전 19041.x부터 다음 명령을 사용할 수도 있습니다.

| 다음과 같이 말하기 | 원하는 작업 |
| - | - |
| "Restart device" | 디바이스를 다시 시작할지 확인하는 대화 상자를 표시합니다. 다시 시작하려면 "yes"라고 말합니다. |
| "Shutdown device" | 디바이스를 활성화할지 확인하는 대화 상자를 표시합니다. "yes"라고 말하여 확인할 수 있습니다. |
| "Brightness up/down" | 디스플레이 밝기를 10%씩 높이거나 낮춥니다. |
| "Volume up/down" | 볼륨을 10%씩 높이거나 낮춥니다. |
| "What's my IP address" | 로컬 네트워크에서 디바이스의 현재 IP 주소를 나타내는 대화 상자를 표시합니다. |
| "Take a picture" | 현재 보고 있는 혼합 현실 사진을 캡처합니다. |
| "Take a video" | 혼합 현실 비디오 녹화를 시작합니다. | 
| "Stop recording" | 현재 진행 중인 혼합 현실 비디오 녹화를 중지합니다. |

### <a name="hologram-commands"></a>홀로그램 명령

이러한 명령을 사용하려면 3D 개체, 홀로그램 또는 앱 창에서 응시하세요.

| 다음과 같이 말하기 | 원하는 작업 |
| - | - |
| "Bigger" | 더 크게 만들기 |
| "Smaller" | 더 작게 만들기 |
| "Face me" | 얼굴로 전환 |
| "Move this" | 이동(응시 따르기) |
| "Close" | 닫기 |
| "Follow me" / "Stop following" | 사용자가 이동하는 대로 함께 움직이기 |

### <a name="see-it-say-it"></a>보기, 말하기

HoloLens의 많은 단추와 기타 요소는 사용자의 음성에도 응답합니다(예: 앱 표시줄의 **Follow me** 및 **Close** 또는 Edge의 **뒤로** 단추). 단추를 음성으로 사용할 수 있는지 확인하려면 **응시 커서**, **터치 커서** 또는 한 **손 광선** 을 해당 단추 위에 잠시 놓습니다. 단추를 음성으로 사용할 수 있으면 음성 팁이 표시됩니다.

### <a name="dictation-mode"></a>받아쓰기 모드

입력하기 지겨우시죠? 홀로그램 키보드가 활성화되어 있을 때마다 받아쓰기 모드로 전환하세요. 시작하려면 마이크 단추를 선택하거나 "Start dictating"이라고 말합니다. 받아쓰기를 중지하려면 단추를 다시 선택하거나 "Stop dictating"이라고 말하세요. 방금 받아쓴 내용을 삭제하려면 "Delete that"이라고 말합니다. 

> [!NOTE]
> 받아쓰기 모드를 사용하려면 인터넷에 연결되어 있어야 합니다.

HoloLens 받아쓰기는 명시적 문장 부호를 사용하여 사용하려는 문장 부호의 이름을 말하면 됩니다. 예를 들어 "Hey **comma** what are you up to **question mark**"라고 말할 수 있습니다.

다음은 사용할 수 있는 문장 부호 키워드입니다.

- 마침표, 쉼표, 물음표, 느낌표
- 새 줄/새 단락
- 세미콜론, 콜론
- 여는 따옴표, 닫는 따옴표
- 해시태그, 웃는 얼굴, 찡그린, 윙크
- 달러, 퍼센트

경우에 따라 이메일 주소 등의 철자를 말할 수 있습니다. 예를 들어 example@outlook.com을 받아쓰려면 "E X A M P L E at outlook dot com"이라고 말할 수 있습니다.

## <a name="do-more-with-cortana"></a>Cortana로 더 많은 작업 수행

Cortana를 사용하여 HoloLens에서 모든 종류의 작업을 수행할 수 있지만 사용 중인 Windows Holographic 버전에 따라 기능이 달라질 수 있습니다. 최신 Cortana 버전의 업데이트된 기능에 대한 자세한 내용은 [곧 출시될 Windows 10 릴리스의 Cortana: 향상된 보안 및 개인 정보 보호를 통해 생산성에 집중](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)에서 확인할 수 있습니다. 

![Hey Cortana!](images/cortana-on-hololens.png)

다음처럼 말할 수 있습니다("Hey Cortana"를 먼저 말해야 합니다).

**Hey, Cortana**...

- 어떤 말을 할 수 있나요?
- Launch <*app name*>.
- What time is it?
- Show me the latest NBA scores.
- Tell me a joke.

*18362.x 또는 이전 버전* 을 사용 중인 경우 다음 명령을 사용할 수도 있습니다.

**Hey, Cortana**...

- Increase the volume.
- Decrease the brightness.
- Shut down.
- 다시 시작.
- Go to sleep.
- Mute.
- Move <*app name*> here(앱을 이동하고자 하는 지점을 응시).
- 시작으로 이동하여
- Take a picture.
- 기록을 시작합니다. (동영상 녹화를 시작합니다.)
- Stop recording. (동영상 녹화를 중지합니다.)
- How much battery do I have left?

Microsoft HoloLens에서는 PC 또는 휴대폰의 Windows에서 사용하는 일부 Cortana 기능(예: 미리 알림 및 알림)이 지원되지 않으며 Cortana 환경은 환경마다 다를 수 있습니다.

### <a name="turn-cortana-off"></a>Cortana 비활성화

음성 명령을 사용하도록 설정한 경우 HoloLens를 처음 사용할 때 Cortana가 켜져 있습니다. Cortana 설정에서 이 기능을 비활성화할 수 있습니다. **모든 앱** 목록에서 **Cortana** > **설정** 을 선택합니다. 그런 다음, 비활성화합니다. Cortana는 제안 사항, 아이디어, 미리 알림, 경고 등을 제공할 수 있습니다.

Cortana가 "Hey Cortana"에 응답하지 않으면 시작에서 음성 명령이 사용하도록 설정되어 있는지 확인하고 Cortana 설정으로 이동하여 활성화되어 있는지 확인합니다.
