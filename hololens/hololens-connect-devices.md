---
title: Bluetooth 및 USB-C 장치에 연결
description: 이 가이드는 Bluetooth 및 USB-C 장치 및 액세서리에 연결하는 과정을 안내합니다.
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
ms.openlocfilehash: 2f2de4d776a0fdb99555687a96719d111ffb6460
ms.sourcegitcommit: 8bf8e9196c4ea89297f210b5c1d41b31f9edd407
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "11156295"
---
# Bluetooth 및 USB-C 장치에 연결

> [!NOTE]
> 외부 마이크를 사용할 수 없습니다. HoloLens 2는 기본 제공 [마이크 배열](hololens2-hardware.md#audio-and-speech)을 사용합니다.

## Bluetooth 장치 페어링

HoloLens 2는 다음 Bluetooth 장치 클래스를 지원합니다.

- 마우스
- 키보드
- A2DP(Bluetooth 오디오 출력) 장치

HoloLens 2(1세대)는 다음 Bluetooth 장치 클래스를 지원합니다.

- 마우스
- 키보드
- HoloLens(1세대) 클릭커

> [!NOTE]
> 다른 유형의 Bluetooth 장치(예: 스피커, 헤드셋, 스마트폰, 게임 패드)가 HoloLens 설정에서 사용 가능한 것으로 표시될 수 있습니다. 그러나 이 장치는 HoloLens(1세대)에서 지원 되지 않습니다. [HoloLens 설정에서 사용 가능한 장치로 보이지만 작동하지 않는 장치](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)를 참조 하세요.

### Bluetooth 키보드 또는 마우스 연결

1. 키보드 또는 마우스를 켜고 검색 가능하도록 합니다. 장치를 검색 가능하게 하는 방법에 대한 자세한 내용은 장치(또는 해당 문서) 정보를 참고하거나 제조 업체의 웹 사이트를 방문하세요.

1. 피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.

1. **장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.  

1. 장치 이름이 표시되면 **연결**을 선택하고 지침을 따릅니다.

### HoloLens(1세대): 클리커 연결

1. 피어오르는 동작을 사용하여 **시작**으로 이동한 다음 **설정**을 선택합니다.

1. **장치**를 선택하고 Bluetooth가 켜져 있는지 확인합니다.

1. 펜 끝을 사용하여 클리커 상태 표시등이 흰색으로 깜박일 때까지 클리커 연결 단추를 길게 누릅니다. 상태 표시등이 깜박일 때까지 단추를 누르고 있어야 합니다.  

   페어링 단추는 클리커 아래쪽에 손가락 루프 옆에 있습니다.
   
   ![페어링 단추는 손가락 루프 옆에 있습니다.](images/use-hololens-clicker-1.png)
   
1. 페어링 화면에서 **클리커** > **연결**을 선택합니다.

## Bluetooth 해제

이 절차는 Bluetooth 라디오의 RF 구성 요소를 해제하고 Microsoft HoloLens에서 모든 Bluetooth 기능을 사용 하지 않도록 설정합니다.

1. 피어오르는 제스처(HoloLens(1세대)) 또는 시작 제스처(HoloLens 2)를 사용하여 **시작**으로 이동한 다음 **설정** > **장치**를 선택합니다.

1. **Bluetooth** 슬라이더 스위치를 **해제** 위치로 이동 합니다.

## HoloLens 2: USB-C 장치 연결

HoloLens 2는 다음 USB-C 장치 클래스를 지원합니다.

- 대용량 저장 장치 (예: 엄지 드라이브)
- 이더넷 어댑터 (이더넷 및 충전 포함)
- USB-C 부터 3.5 mm 디지털 오디오 어댑터
- USB-C 디지털 오디오 헤드셋(헤드셋 어댑터 및 충전 포함)
- 유선 마우스
- 유선 키보드
- 콤비네이션 PD 허브(USB A 및 PD 충전)

> [!NOTE]
> HoloLens가 USB-C 연결을 사용하는 일부 모바일 장치를 이더넷 어댑터로 인식 하기 때문에 Windows Holographic 버전 2004부터 테더링 구성에서 사용할 수 있습니다. 별도의 드라이버 및/또는 구성을 위해 설치된 응용 프로그램이 필요한 USB LTE 모뎀은 지원되지 않습니다.

고객 의견에 따라 USB-C를 통해 HoloLens에 직접 테더링된 휴대폰 연결에 대한 제한적 지원을 설정했습니다.  테더링 연결은 일반 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 드라이버 구현을 지원하고 추가 드라이버나 응용 프로그램 설치가 필요하지 않은 장치에만 사용할 수 있습니다.  이러한 장치를 연결하면 HoloLens 2 네트워크 설정 UI에서 자동으로 새 이더넷 연결로 표시됩니다. 해당 장치 제조업체에 일반 Microsoft RNDIS 드라이버 지원 여부에 대한 자세한 정보를 확인하세요.

## Miracast에 연결

Miracst를 사용 하려면 다음 단계를 따릅니다.

1. 다음 중 하나를 수행합니다.  

   - **시작** 메뉴를 열고 디스플레이 아이콘을 선택합니다.
   - **시작** 메뉴를 응시하며 "연결" 이라고 말합니다.  

1. 나타나는 장치 목록에서 사용 가능한 장치를 선택합니다.

1. 페어링이 완료되면 프로젝션을 시작합니다.
