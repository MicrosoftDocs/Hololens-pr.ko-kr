---
title: Bluetooth 및 USB-C 장치에 연결
description: HoloLens 혼합 현실 장치에서 Bluetooth 및 USB-C 장치 및 액세서리에 연결을 시작하세요.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385490"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Bluetooth 및 USB-C 장치에 연결

> [!NOTE]
> 외부 마이크를 사용할 수 없습니다. HoloLens 2는 기본 제공 [마이크 배열](hololens2-hardware.md#audio-and-speech)을 사용합니다.

## <a name="pair-bluetooth-devices"></a>Bluetooth 장치 페어링

HoloLens 2는 다음 Bluetooth 장치 클래스를 지원합니다.

- 마우스
- 키보드
- A2DP(Bluetooth 오디오 출력) 장치

HoloLens 2(1세대)는 다음 Bluetooth 장치 클래스를 지원합니다.

- 마우스
- 키보드
- [HoloLens(1세대) 클릭커](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> 다른 유형의 Bluetooth 장치(예: 스피커, 헤드셋, 스마트폰, 게임 패드)가 HoloLens 설정에서 사용 가능한 것으로 표시될 수 있습니다. 그러나 이 장치는 HoloLens(1세대)에서 지원 되지 않습니다. [HoloLens 설정에서 사용 가능한 장치로 보이지만 작동하지 않는 장치](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)를 참조 하세요.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth 키보드 또는 마우스 연결

1. 키보드 또는 마우스를 켜고 검색 가능하도록 합니다. 장치를 검색 가능하게 하는 방법에 대한 자세한 내용은 장치(또는 해당 문서) 정보를 참고하거나 제조 업체의 웹 사이트를 방문하세요.

1. 피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.

1. **장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.  

1. 장치 이름이 표시되면 **연결**을 선택하고 지침을 따릅니다.

## <a name="disable-bluetooth"></a>Bluetooth 해제

이 절차는 Bluetooth 라디오의 RF 구성 요소를 해제하고 Microsoft HoloLens에서 모든 Bluetooth 기능을 사용 하지 않도록 설정합니다.

1. 피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정** > **장치**를 선택합니다.

1. **Bluetooth** 슬라이더 스위치를 **해제** 위치로 이동 합니다.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C 장치 연결

HoloLens 2는 다음 USB-C 장치 클래스를 지원합니다.

- 대용량 저장 장치 (예: 엄지 드라이브)
- 이더넷 어댑터 (이더넷 및 충전 포함)
- USB-C 부터 3.5 mm 디지털 오디오 어댑터
- USB-C 디지털 오디오 헤드셋(헤드셋 어댑터 및 충전 포함)
- 유선 마우스
- 유선 키보드
- 콤비네이션 PD 허브(USB A 및 PD 충전)

> [!NOTE]
> 고객 의견에 따라 USB-C를 통해 HoloLens에 직접 테더링된 휴대폰 연결에 대한 제한적 지원을 설정했습니다. [셀룰러 및 5G에 연결](hololens-cellular.md)을 참조하세요.

### <a name="usb-c-hubs"></a>USB-C 허브

일부 사용자는 한 번에 여러 장치를 연결해야 할 수 있습니다. 다른 연결된 장치와 함께 내부자 기능을 미리 보고 [USB-C 마이크 사용](hololens-insider.md#usb-c-external-microphone-support)을 원하는 사용자의 경우 USB-C 허브가 요구에 적합할 수 있습니다. Microsoft는 이러한 장치를 테스트하지 않았으며 특정 브랜드를 추천할 수도 없습니다.

**USB-C 허브 및 연결된 장치에 대한 요구 사항:**

- 연결된 장치에는 드라이버를 설치할 필요가 없습니다.
- 연결된 모든 장치의 총 전력 소모량은 4.5W 미만이어야 합니다.

## <a name="connect-to-miracast"></a>Miracast에 연결

Miracst를 사용 하려면 다음 단계를 따릅니다.

1. 다음 중 하나를 수행합니다.  

   - **시작** 메뉴를 열고 디스플레이 아이콘을 선택합니다.
   - **시작** 메뉴를 응시하며 "연결" 이라고 말합니다.  

1. 나타나는 장치 목록에서 사용 가능한 장치를 선택합니다.

1. 페어링이 완료되면 프로젝션을 시작합니다.
