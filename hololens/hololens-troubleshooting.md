---
title: 문제 해결
description: 일반적인 HoloLens 문제에 대한 해결 방법
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: 문제, 버그, 문제 해결, 도움말, 지원, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 4f077a8bb2592ab9b650e2e8021c97d3d8524dcc
ms.sourcegitcommit: d20f610edd7db452ccc2ac554fc8d21bd89b0b99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195284"
---
# 문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결하는 방법을 설명합니다.

## 내 HoloLens가 응답하지 않는 경우 또는 시작되지 않습니다.

HoloLens가 시작되지 않는 경우:

- 전원 단추 옆에 있는 LED가 켜지거나 한 LED만 잠시 깜박이면 [HoloLens를 충전해야 할 수 있습니다.](hololens-recovery.md#charge-the-device)
- 전원 단추를 누를 때 디스플레이에 아무 것도 볼 수 없는 경우 장치의 하드 재설정을 [준비합니다.](hololens-recovery.md#hard-reset-procedure)

HoloLens가 고정되거나 응답하지 않는 경우:

- 5개의 LED가 모두 꺼질 때까지 전원 단추를 누르거나, LED가 응답하지 않는 경우 15초 동안 HoloLens를 끄세요. HoloLens를 시작하고 전원 단추를 다시 누릅니다.

이러한 단계가 작동하지 않는 경우 HoloLens 2 장치 또는 [HoloLens(1세대)](hololens1-recovery.md) 장치를 복구해 볼 수 있습니다. [recovering your HoloLens 2 device](hololens-recovery.md)

## 홀로그램이 잘 보이지 않습니다.

홀로그램이 불안정하거나 뛰거나, 모양이 맞지 않는 경우 다음을 시도해 봐야 합니다.

- HoloLens 앞쪽의 장치 바이너리 및 센서 막대를 청소합니다.
- 방에서 조명을 늘려야 합니다.
- HoloLens가 더 완전히 스캔할 수 있도록 주변을 따라 걸고 주변을 보고 있습니다.
- 눈에 대한 HoloLens 보정. 설정 **시스템**  >  **System**  >  **유틸리티로 이동합니다.** **보정**에서**보정 열기**를 선택합니다.
 
### 홀로그램이 불안정하거나 모양이 맞지 않는 문제 보고
 
1. 문제의 혼합 현실 [캡처 비디오를](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 녹화해 주세요. 이 비디오는 나중에 피드백 허브를 통해 첨부 파일로 업로드할 수 있습니다.  
1. 설정 앱 -> 개인 **Settings** 정보 진단& **Privacy**  ->  **피드백을** 통해 전체 원격 분석 **Optional diagnostics data** 사용 및 선택적 진단 데이터에서 토글이 설정되어 있도록 **설정**
1. 최신 [Windows Holographic OS(20H2 이상)로](hololens-release-notes.md#windows-holographic-version-20h2)업데이트하여 최신 홀로그램 배율 및 안정성 수정을 다운로드합니다. 업데이트 후 다음을 수행하십시오.
    1. 설정 앱 -> **Settings** 시스템 홀로그램스 **System**-> 모든 홀로그램 제거를 선택하고 새 지도로  ->  **Holograms** 시작하세요. **Remove all holograms**
    1. HoloLens를 착용하고 방을 따라 걸고 공간의 모든 영역과 표면을 보고 공간의 새 맵을 만드십시오. 이 작업을 2-3분 동안 진행합니다.
    1. IPD 보정을 수행합니다. 설정 **시스템**  >  **System**  >  **유틸리티로 이동합니다.** **보정**에서**보정 열기**를 선택합니다.
    1. 시나리오를 다시 테스트하고 계속 유지될지 설명합니다.
1. 업데이트로도 문제가 해결되지 않는 경우 피드백 허브 문제를 [제출하십시오.](hololens-feedback.md) 피드백을 작성한 후 공유 **Share** 단추를 사용하여 지원에 문의할 때 전송할 수 있는 간편한 공유 링크를 만들 수 있습니다.

## HoloLens가 손 입력에 응답하지 않습니다.

HoloLens가 손을 볼 수 있도록 제스처 프레임에 유지해야 합니다.  혼합 현실 홈은 손을 추적하는 경우를 알 수 있는 피드백을 제공합니다.  각 HoloLens 버전에서는 피드백이 다릅니다.
- HoloLens(1세대)에서 시선 커서가 점에서 링으로 변경됩니다.
- HoloLens 2에서 손이 슬레이트에 가까이 있는 경우 손가락 끝 커서가 나타나고 슬레이트가 더 멀리 떨어져 있는 경우 손 광선이 나타납니다.

많은 몰입형 앱은 Mixed Reality Home과 유사한 입력 패턴을 따르고 있습니다.  [HoloLens(1세대)](hololens1-basic-usage.md#use-hololens-with-your-hands) 및 [HoloLens 2에서](hololens2-basic-usage.md#the-hand-tracking-frame)손 입력을 사용하는 방법을 자세히 알아보시고.

글러브를 착용하는 경우 일부 유형의 글러브는 손 추적에서 작동하지 않습니다.  일반적인 예는 적외선 광원을 들이는 경향이 있으며 깊이 카메라에 의해 선택되지 않는 검은색 입체 글러브입니다.  작업에서 경미한 글러브가 포함되는 경우 파랑 또는 회색과 같이 더 밝은 색을 시도하는 것이 좋습니다.  또 다른 예로는 손 모양을 가리게 하는 큰 밝게 글러브가 있습니다. 최상의 결과를 얻기 위해 양식에 최대한 잘 맞는 글러브를 사용하는 것이 좋습니다.

바이너리에 지문이나 지문이 있는 경우 HoloLens와 함께 나온 마이크로픽스 정리를 사용하여 바이스를 부드럽게 정리합니다.

## HoloLens가 내 음성 명령에 응답하지 않습니다.

Cortana가 음성 명령에 응답하지 않는 경우 Cortana가 켜져 있는지 확인 합니다. 모든 앱 목록에서 **Cortana**메뉴 전자 필기장 설정을 선택하여  >  **Menu**  >  **Notebook**  >  **Settings** 변경합니다. 말할 수 있는 내용에 대한 자세한 내용은 [음성으로 HoloLens 사용](hololens-cortana.md)을 참조하세요.

## 이전에 배치한 홀로그램을 배치하거나 홀로그램을 볼 수 없습니다.

HoloLens가 공간을 매핑하거나 로드할 수 없는 경우 제한된 모드로 전환되어 홀로그램을 배치하거나 배치한 홀로그램을 볼 수 없습니다. 다음의 몇 가지 조치를 시도해 볼 수 있습니다.

- 환경에 충분한 빛이 있는지 확인하여 HoloLens가 공간을 보고 매핑할 수 있도록 합니다.
- 네트워크 연결에 연결되어 있는지 Wi-Fi 확인합니다. Wi-Fi에 연결되지 않은 경우 HoloLens는 알려진 공간을 식별하고 로드할 수 없습니다.
- 새 공간을 만들어야 하는 경우 Wi-Fi에 연결한 다음 HoloLens를 다시 시작합니다.
- 올바른 공간이 활성화된지 확인하거나 공백을 수동으로 로드하려면 설정 시스템 **Settings**  >  **공간으로**  >  **이동합니다.**
- 올바른 공간이 로드되어도 여전히 문제가 있는 경우 공간이 손상될 수 있습니다. 이 문제를 해결하려면 공백을 선택한 다음 제거를 **선택합니다.** 공간을 제거하고 나면 HoloLens가 주변을 매핑하고 새 공간을 만들기 시작합니다.

## My HoloLens can't tell what space I't tell what space I't in

HoloLens에서 현재 사용중인 공간을 자동으로 식별하고 로드할 수 없는 경우 다음 요인을 검사합니다.

- 네트워크에 연결되어 있는지 Wi-Fi
- 방에 충분한 조명이 있는지 확인
- 주변이 변경되지 않은지 확인

설정 시스템 공간으로 이동하여 공간을 수동으로 로드하거나 공간을 **Settings**  >  **관리할**  >  **수도 있습니다.**

## "낮은 디스크 공간" 오류가 발생했습니다.

다음 중 하나 이상을 수행하여 일부 저장소 공간을 비우는 것이 필요합니다.

- 일부 사용되지 않는 공백을 삭제합니다. 설정 **시스템**  >  **공간으로**이동하여 더 이상 필요 없는 공간을 선택한 다음 제거를  >  **Spaces** **선택합니다.**
- 배치한 홀로그램 중 일부를 제거합니다.
- 앱의 앱에서 일부 사진과 사진 삭제합니다.
- HoloLens에서 일부 앱을 제거합니다. 모든 앱 **목록에서** 제거하려는 앱을 탭하고 누르고 있는 다음 **제거를 선택합니다.**

## My HoloLens에서 새 공간을 만들 수 없습니다.

가장 가능성이 높은 문제는 저장소 공간이 부족하다는 것입니다. 일부 디스크 공간을 [비우기](#im-getting-a-low-disk-space-error) 위해 이전 팁 중 하나를 시도해 보세요.

## HoloLens 에뮬레이터가 작동하지 않습니다.

HoloLens 에뮬레이터에 대한 정보는 개발자 설명서에 있습니다.  [HoloLens 에뮬레이터](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)문제 해결에 대해 자세히 읽어 읽습니다.
