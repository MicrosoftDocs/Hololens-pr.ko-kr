---
title: 문제 해결
description: 일반적인 HoloLens 문제에 대 한 해결 방법
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: 문제, 버그, 문제 해결, 수정, 도움말, 지원, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: e00226852f92cf5b3137d8d41cfde0f01394f5bc
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902293"
---
# 문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결 하는 방법을 설명 합니다.

## 내 HoloLens가 응답 하지 않거나 시작 되지 않음

HoloLens가 시작 되지 않는 경우:

- 전원 단추 옆에 있는 Led가 켜지 지 않거나 LED 중 하나만 잠시 깜박이는 경우 [HoloLens를 충전](hololens-recovery.md#charging-the-device) 해야 할 수 있습니다.
- 전원 단추를 눌러도 Led가 켜지 지만 디스플레이에 아무것도 표시 되지 않으면 [디바이스의 하드 리셋을 preform](hololens-recovery.md#hard-reset-procedure).

HoloLens가 고정 또는 응답 하지 않는 경우:

- 5 개의 Led가 모두 꺼질 때까지 전원 단추를 누르고, Led가 응답 하지 않으면 15 초 동안 클릭 하 여 HoloLens를 끕니다. HoloLens를 시작 하려면 전원 단추를 다시 누릅니다.

이 단계가 작동 하지 않으면 [hololens 2 장치](hololens-recovery.md) 또는 [hololens (1 gen) 장치](hololens1-recovery.md) 를 복구 해 볼 수 있습니다.

## 홀로그램 좋은 모양이 아닙니다.

홀로그램이 불안정 하거나 jumpy 적절 하지 않은 경우 다음을 시도해 보세요.

- HoloLens 전면의 장치 센터 및 센서 표시줄을 정리 합니다.
- 채팅방의 빛을 늘립니다.
- HoloLens가 더 완벽 하 게 스캔 될 수 있도록 주변을 탐색 하 고 검토 합니다.
- 눈을 위해 HoloLens를 보정 합니다. **설정**  >  **시스템**  >  **유틸리티로**이동 합니다. **보정**에서**보정 열기**를 선택합니다.

## HoloLens가 직접 입력에 응답 하지 않습니다.

HoloLens가 손을 볼 수 있도록 하려면이를 제스처 프레임에 유지 해야 합니다.  Mixed Reality 홈은 손을 추적 하는 시기를 알 수 있는 피드백을 제공 합니다.  피드백은 여러 버전의 HoloLens에 따라 다릅니다.
- HoloLens (1 회 gen)에서 응시 커서는 점에서 링으로 바뀝니다.
- HoloLens 2에서 손가락 끝 커서는 손으로 가까이에 있을 때 표시 되며, slates 더 멀리 있으면 손 모양으로 표시 됩니다.

많은 몰입 형 앱은 Mixed Reality Home과 유사한 입력 패턴을 따릅니다.  [Hololens (첫번째 gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) 및 [hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)에서 직접 입력 하는 방법에 대해 자세히 알아보세요.

장갑을 착용 하 고 있다면 일부 유형의 장갑이 손으로 추적 하는 것이 아니라는 것을 참고 하세요.  일반적으로 검정색 고무 장갑으로 적외선을 흡수 하는 경향이 있으며 깊이 카메라에 의해 선택 되지 않습니다.  작업에 고무 장갑이 포함 되어 있는 경우 파란색 또는 회색 등 밝은 색을 사용해 보는 것이 좋습니다.  또 다른 예는 손 모양을 더 많이 숨기는 큰 baggy 장갑입니다. 최상의 결과를 위해 가능한 한 양식 피팅으로 장갑을 사용 하는 것이 좋습니다.

센터에 지문 또는 얼룩이 있는 경우 HoloLens와 함께 제공 되는 마이크로 파이버 클리닝 천을 사용 하 여 센터를 천천히 정리 합니다.

## HoloLens가 내 음성 명령에 응답 하지 않습니다.

Cortana가 음성 명령에 응답 하지 않으면 Cortana가 켜져 있는지 확인 합니다. 모든 앱 목록에서 **Cortana**  >  **메뉴**  >  **전자 필기장**  >  **설정을** 선택 하 여 변경 합니다. 말할 수 있는 내용에 대한 자세한 내용은 [음성으로 HoloLens 사용](hololens-cortana.md)을 참조하세요.

## 홀로그램를 배치할 수 없거나 이전에 배치한 홀로그램 표시 됩니다.

HoloLens에서 공간을 매핑하거나 로드할 수 없는 경우 제한 모드로 들어가고, 홀로그램을 배치할 수 없으며 홀로그램를 볼 수도 없습니다. 다음의 몇 가지 조치를 시도해 볼 수 있습니다.

- HoloLens가 공간을 보고 매핑할 수 있도록 환경에 충분 한 표시등이 있는지 확인 합니다.
- Wi-fi 네트워크에 연결 되어 있는지 확인 합니다. Wi-fi에 연결 되어 있지 않은 경우 HoloLens는 알려진 공간을 식별 하 고 로드할 수 없습니다.
- 새 공간을 만들어야 하는 경우 Wi-fi에 연결한 다음 HoloLens를 다시 시작 합니다.
- 올바른 공간이 활성 상태 인지 또는 수동으로 공간을 로드할지 여부를 확인 하려면 **설정**  >  **시스템**  >  **공간**으로 이동 합니다.
- 올바른 공간이 로드 되 고 여전히 문제가 있는 경우 공간이 손상 될 수 있습니다. 이 문제를 해결 하려면 공간을 선택한 다음 **제거**를 선택 합니다. 공간을 제거 하면 HoloLens가 주변을 매핑하고 새 공간을 만듭니다.

## 내 HoloLens에서 현재 공간을 알 수 없음

HoloLens에서 자동으로 현재 공간을 식별 하 고 로드할 수 없는 경우 다음 요인을 확인 합니다.

- Wi-fi에 연결 되어 있는지 확인 하세요.
- 채팅방에 충분 한 빛이 있는지 확인
- 주변에 중요 한 변화가 없는지 확인 합니다.

수동으로 공간을 로드 하거나 **설정**  >  **시스템**  >  **공간**으로 이동해 서 스페이스를 관리할 수도 있습니다.

## "디스크 공간 부족" 오류가 발생 하는 경우

다음 중 하나 이상을 수행 하 여 저장소 공간을 확보 해야 합니다.

- 사용 하지 않은 일부 공간을 삭제 합니다. **설정**시스템 공간으로 이동 하 여  >  **System**  >  **Spaces**더 이상 필요 하지 않은 공간을 선택한 다음 **제거**를 선택 합니다.
- 배치한 홀로그램 중 일부를 제거 합니다.
- 사진 앱에서 일부 그림과 비디오를 삭제 합니다.
- HoloLens에서 일부 앱을 제거합니다. **모든 앱** 목록에서 제거 하려는 앱을 길게 탭 한 다음 **제거**를 선택 합니다.

## 내 HoloLens에서 새 공간을 만들 수 없음

가장 가능성 높은 문제는 저장 공간 부족을 실행 하는 것입니다. [이전 팁](#im-getting-a-low-disk-space-error) 중 하나를 시도 하 여 디스크 공간을 확보 합니다.

## HoloLens 에뮬레이터가 작동 하지 않음

HoloLens 에뮬레이터에 대 한 정보는 개발자 설명서에 있습니다.  [HoloLens 에뮬레이터 문제 해결](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)에 대 한 자세한 내용을 알아보세요.
