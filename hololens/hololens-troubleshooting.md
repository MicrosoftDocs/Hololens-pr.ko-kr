---
title: 문제 해결
description: HoloLens 장치 문제 및 문제 해결 기술에 대 한 가장 일반적인 솔루션을 최신 상태로 유지 합니다.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 문제, 버그, 문제 해결, 수정, 도움말, 지원, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309517"
---
# <a name="troubleshooting"></a>문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결 하는 방법을 설명 합니다.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>HoloLens가 응답 하지 않거나 시작 되지 않음

HoloLens가 시작 되지 않는 경우:

- 전원 단추 옆의 Led가 켜지 지 않거나 LED가 잠시 깜박일 경우 [HoloLens를 청구](hololens-recovery.md#charge-the-device) 해야 할 수 있습니다.
- 전원 단추를 누를 때 Led가 켜진 경우 디스플레이에서 아무 것도 볼 수 없으면 [장치의 하드 리셋을 수행](hololens-recovery.md#hard-reset-procedure).

HoloLens가 고정 되거나 응답 하지 않는 경우:

- 5 개의 Led가 모두 꺼집니다. 또는 Led가 응답 하지 않는 경우 15 초 동안 전원 단추를 눌러 HoloLens를 끕니다. HoloLens를 시작 하려면 전원 단추를 다시 누릅니다.

이러한 단계가 작동 하지 않는 경우 [hololens 2 장치](hololens-recovery.md) 또는 [hololens (첫 번째 gen) 장치](hololens1-recovery.md) 를 복구 해 볼 수 있습니다.

## <a name="holograms-dont-look-good"></a>Holograms 양호 하지 않음

Holograms가 안정적이 지 않거나, jumpy, 적절 하지 않은 경우 다음을 시도 하세요.

- HoloLens 앞에서 장치 센터 및 센서 표시줄을 청소 합니다.
- 방에서 빛을 늘립니다.
- HoloLens를 탐색 하 고이를 통해 HoloLens를 확인 하 여 HoloLens를 보다 완벽 하 게 검사할 수 있습니다.
- 눈동자를 위한 HoloLens를 보정 합니다. **설정**  >  **시스템**  >  **유틸리티** 로 이동 합니다. **보정** 아래에서 **보정 열기** 를 선택 합니다.
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Holograms 불안정 하거나 오른쪽으로 표시 되지 않는 문제 보고
 
1. 녹화 하 고 [혼합 현실](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 에서 문제의 비디오를 캡처 하세요. 나중에이 비디오를 첨부 파일로 피드백 허브를 통해 업로드할 수 있습니다.  
1. **설정** 앱을 통해 전체 원격 분석을 사용 하도록 설정 합니다. > **개인 정보**  ->  **진단 & 피드백** 을 **사용 하** 고 **선택적 진단 데이터** 에서 토글이 설정으로 설정 되었는지 확인 합니다.
1. 최신 [Windows HOLOGRAPHIC OS (20H2 이상)](hololens-release-notes.md#windows-holographic-version-20h2)로 업데이트 하 여 최신 홀로그램 규모 및 안정성 수정을 받으세요. 업데이트 후 다음을 수행 합니다.
    1. Holograms를 통해 모든를 제거 합니다. **앱-** > **System**  ->  **Holograms** -> 다음, **모든 Holograms 제거** 를 선택 하 고 새 맵으로 시작 합니다.
    1. HoloLens를 입고 하 고 공간에 있는 모든 영역 및 표면을 확인 하 여 공간에 대 한 새 지도를 만듭니다. 2-3 분 동안이 작업을 수행 합니다.
    1. IPD 보정을 수행 합니다. **설정**  >  **시스템**  >  **유틸리티** 로 이동 합니다. **보정** 아래에서 **보정 열기** 를 선택 합니다.
    1. 시나리오를 다시 테스트 하 고 계속 되는지 확인 합니다.
1. 업데이트를 수행 해도 문제가 해결 되지 않으면 [피드백 허브 문제](hololens-feedback.md)를 파일에 입력 하세요. 사용자 의견을 채운 후에는 **공유** 단추를 사용 하 여 지원 담당자에 게 연락할 때 전송 될 수 있는 공유 하기 쉬운 링크를 만들 수 있습니다.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens가 직접 입력에 응답 하지 않습니다.

HoloLens가 손을 볼 수 있도록 하려면 제스처 프레임에 보관 해야 합니다.  혼합 현실 홈은 사용자가 손을 추적 하는 시기를 알 수 있는 피드백을 제공 합니다.  사용자 의견은 HoloLens의 서로 다른 버전에서 다릅니다.
- HoloLens (첫 번째 gen)에서 응시 커서는 점에서 링으로 바뀝니다.
- HoloLens 2에서는 fingertip 커서가 슬레이트에 가까이 있을 때 표시 되 고, 슬레이트가 더 멀리 있을 때 손 모양으로 나타납니다.

많은 모던 앱은 혼합 현실 집과 비슷한 입력 패턴을 따릅니다.  [Hololens (첫 번째 gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) 및 [hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)에서 직접 입력을 사용 하는 방법에 대해 자세히 알아보세요.

글러브를 입고 있는 경우 일부 종류의 장갑은 수동 추적에서 작동 하지 않습니다.  일반적인 예로는 검정 고무 장갑이 있습니다 .이는 적외선을 흡수 하 고 깊이 카메라에 의해 선택 되지 않습니다.  작업에 고무 장갑이 포함 되어 있는 경우 파란색 또는 회색 등의 더 밝은 색을 사용해 보는 것이 좋습니다.  또 다른 예로는 긴 baggy 장갑이 있습니다 .이를 통해 손 모양에는 경향이 있습니다. 최상의 결과를 위해 가능한 한 폼 피팅으로 글러브를 사용 하는 것이 좋습니다.

센터에 지문 또는 얼룩이 있는 경우 HoloLens와 함께 제공 되는 마이크로 파이버 클리닝 천을 사용 하 여 센터를 천천히 정리 합니다.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens는 내 음성 명령에 응답 하지 않습니다.

Cortana가 음성 명령에 응답 하지 않는 경우 Cortana가 켜져 있는지 확인 합니다. 모든 앱 목록에서 **Cortana**  >  **메뉴**  >  **노트북**  >  **설정** 을 선택 하 여 변경 합니다. 설명 하는 내용에 대 한 자세한 내용은 [HoloLens에 음성 사용](hololens-cortana.md)을 참조 하세요.

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Holograms를 배치 하거나 이전에 배치한 holograms를 볼 수 없습니다.

HoloLens가 공간을 매핑하거나 로드할 수 없는 경우 제한 된 모드로 전환 되며 holograms를 배치 하거나 holograms를 볼 수 없습니다. 다음은 시도해 볼 수 있는 몇 가지 사항입니다.

- HoloLens가 공간을 보고 매핑할 수 있도록 사용자 환경에 충분 한 조명이 있는지 확인 합니다.
- Wi-Fi 네트워크에 연결 되어 있는지 확인 합니다. Wi-fi에 연결 되지 않은 경우 HoloLens는 알려진 공간을 식별 하 고 로드할 수 없습니다.
- 새 공간을 만들어야 하는 경우 Wi-fi에 연결한 다음 HoloLens를 다시 시작 합니다.
- 올바른 공간이 활성화 되어 있는지 확인 하거나 공간을 수동으로 로드 하려면 **설정**  >  **시스템**  >  **공간** 으로 이동 합니다.
- 올바른 공간이 로드 되 고 문제가 여전히 발생 하는 경우 공간이 손상 된 것일 수 있습니다. 이 문제를 해결 하려면 공간을 선택 하 고 **제거** 를 선택 합니다. 공간을 제거한 후 HoloLens가 환경을 매핑하고 새 공간을 만듭니다.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>내 HoloLens에서 어느 공간에 있는지 알 수 없습니다.

HoloLens에서 자동으로 사용할 공간을 식별 하 고 로드할 수 없는 경우 다음 요소를 확인 합니다.

- Wi-Fi에 연결 되어 있는지 확인 하세요.
- 대화방에 충분 한 빛이 있는지 확인 합니다.
- 환경에 대 한 중요 한 변경 내용이 없는지 확인 합니다.

**설정**  >  **시스템**  >  **공간** 으로 이동 하 여 공간을 수동으로 로드 하거나 공간을 관리할 수도 있습니다.

## <a name="im-getting-a-low-disk-space-error"></a>"디스크 공간 부족" 오류가 발생 합니다.

다음 중 하나 이상을 수행 하 여 저장소 공간을 확보 해야 합니다.

- 사용 하지 않는 공간을 삭제 합니다. **설정** 시스템 공간으로 이동 하 여  >    >  더 이상 필요 하지 않은 공간을 선택 하 고 **제거** 를 선택 합니다.
- 배치한 holograms 중 일부를 제거 합니다.
- 사진 앱에서 일부 사진과 비디오를 삭제 합니다.
- HoloLens에서 일부 앱을 제거 합니다. **모든 앱** 목록에서 제거 하려는 앱을 탭 하 고 누른 다음 **제거** 를 선택 합니다.

## <a name="my-hololens-cant-create-a-new-space"></a>HoloLens에서 새 공간을 만들 수 없습니다.

가장 가능성이 높은 문제는 저장소 공간이 부족 하다는 것입니다. [이전 팁](#im-getting-a-low-disk-space-error) 중 하나를 사용 하 여 디스크 공간을 확보 하세요.

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens 에뮬레이터가 작동 하지 않습니다.

HoloLens 에뮬레이터에 대 한 정보는 개발자 설명서에 있습니다.  [HoloLens 에뮬레이터 문제 해결](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)에 대해 자세히 알아보세요.
