---
title: HoloLens를 사용하여 물리적 공간 매핑
description: HoloLens는 시간이 지남에 따라 공간이 어떻게 보이는지 학습합니다. 사용자는 공간을 통해 특정 방식으로 HoloLens를 이동하여 이 프로세스를 용이하게 할 수 있습니다.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, 디자인, 공간 매핑, HoloLens, 표면 재구성, 메시, 헤드 추적, 매핑
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640044"
---
# <a name="map-physical-spaces-with-hololens"></a>HoloLens를 사용하여 물리적 공간 매핑

HoloLens는 홀로그램을 실제 세계와 혼합합니다. 그렇게 하려면 HoloLens는 주변의 물리적 세계에 대해 배우고 해당 공간 내에서 홀로그램을 배치하는 위치를 기억해야 합니다.

시간이 지남에 따라 HoloLens는 표시된 환경의 *공간 맵* 을 구축합니다.  HoloLens는 환경 변화에 따라 맵을 업데이트합니다. 로그인하고 디바이스가 켜져 있는 동안 HoloLens는 공간 맵을 만들고 업데이트합니다. 카메라가 공간을 향한 상태에서 디바이스를 잡거나 착용하면 HoloLens가 해당 영역을 매핑하려고 합니다. HoloLens가 시간이 지남에 따라 자연스럽게 공간을 학습하는 동안, HoloLens가 더 빠르고 효율적으로 공간을 매핑하도록 지원할 수 있는 방법이 있습니다.  

> [!NOTE]
> HoloLens가 공간을 매핑하지 못하거나 보정 범위를 벗어나는 경우에는 HoloLens가 제한 모드로 전환될 수 있습니다. 제한 모드에서는 사용자 주변에 홀로그램을 배치할 수 없게 됩니다.

이 문서에서는 HoloLens가 공간을 매핑하는 방법, 공간 매핑을 개선하는 방법 및 HoloLens에서 수집하는 공간 데이터를 관리하는 방법에 대해 설명합니다.

## <a name="choosing-and-setting-up-and-your-space"></a>공간 선택 및 설정

환경의 특징으로 인해 HoloLens가 공간을 해석하기 어려울 수 있습니다. 조도, 공간의 물질, 개체의 배치 등은 모두 HoloLens가 영역을 매핑하는 방식에 영향을 미칠 수 있습니다.

HoloLens는 특정 유형의 환경에서 가장 잘 작동합니다. 최적의 공간 맵을 만들려면 충분한 빛과 공간이 있는 방을 선택합니다. 어두운 공간과 어둡거나 반짝이거나 반투명한 표면이 많은 방(예: 거울이나 거추장스러운 커튼)을 피하세요.

HoloLens는 실내 사용에 최적화되어 있습니다. 공간 매핑은 네트워크에 연결할 필요가 없는 경우에도 Wi-Fi가 켜졌을 때 가장 잘 작동합니다. HoloLens는 연결되거나 인증되지 않은 경우에도 Wi-Fi 액세스 포인트를 얻을 수 있습니다. HoloLens 기능은 액세스 포인트가 인터넷에 연결되어 있는지 또는 인트라넷/로컬 전용인지에 따라 변경하지 않습니다.

걸려 넘어질 위험이 없는 안전한 장소에서만 HoloLens를 사용하세요. [안전에 대한 추가 정보](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>공간 매핑

이제 공간 매핑을 시작할 준비가 되었습니다.  HoloLens가 주변 환경을 매핑하기 시작하면 공간 전체에 퍼져있는 메시 그래픽이 표시됩니다.  혼합 현실 홈에서 매핑된 표면을 선택하여 맵이 표시되도록 트리거할 수 있습니다.

다음은 멋진 공간 맵을 만들기 위한 지침입니다.

### <a name="understand-the-scenarios-for-the-area"></a>영역에 대한 시나리오 이해

HoloLens를 사용할 공간에 가장 많은 시간을 투자해야만 맵이 관련성 있고 완전하게 됩니다. 예를 들어 HoloLens에 대한 사용자 시나리오에 A 지점에서 B 지점으로 이동하는 경우 이동하면서 모든 방향을 바라보면서 해당 경로를 두 세 걸음을 걸어봅니다.  

### <a name="walk-slowly-around-the-space"></a>공간 주변을 천천히 탐색

영역을 너무 빠르게 탐색하는 경우 HoloLens가 매핑 영역을 놓칠 수 있습니다. 공간 주변을 천천히 탐색하고 1.50-2.40m(5-8피트)마다 멈추고 주변을 둘러봅니다.  

부드럽게 이동하면 HoloLens 매핑이 더 효율적으로 작동하는 데도 도움이 됩니다.

### <a name="look-in-all-directions"></a>모든 방향 살펴보기

공간을 매핑하는 모습을 살펴봄으로써 HoloLens는 지점 간에 관련 있는 위치에 대한 더 많은 정보를 얻게 됩니다.  

예를 들어, 위를 보지 않으면 HoloLens가 방 천장의 위치를 인식하지 못할 수 있습니다.  

공간을 매핑할 때 바닥을 보는 것도 잊지 마세요.

### <a name="cover-key-areas-multiple-times"></a>주요 영역에 여러 번 커버

한 영역을 여러 번 지나가면 처음 둘러볼 때 놓쳤을지 모르는 특징을 알아차리는 데 도움이 됩니다. 이상적인 맵을 작성하기 위해 영역을 두 세 번 횡단해 보세요.

이러한 동작을 반복할 때 가능하면 영역을 한 방향으로 이동한 다음, 방향을 돌려 왔던 길로 되돌아갑니다.

### <a name="take-your-time-mapping-the-area"></a>시간을 들여 영역 매핑하기

HoloLens가 완벽하게 매핑하고 주변에 맞게 자동 조정하는 데 15분에서 20분 정도 걸릴 수 있습니다. HoloLens를 자주 사용할 계획인 공간이 있는 경우 이러한 시간을 들여 미리 공간을 매핑하면 나중에 문제를 방지할 수 있습니다.  

## <a name="possible-errors-in-the-spatial-map"></a>공간 맵에서 발생할 수 있는 오류

공간 매핑 데이터의 오류는 다음 몇 가지 범주로 분류됩니다.

- *구멍*: 공간 매핑 데이터에서 실제 표면이 누락되었습니다.
- *환각*: 표면이 현실 세계에 존재하지 않는 공간 매핑 데이터에 존재합니다.
- *웜홀*: HoloLens는 맵의 일부가 실제와 다른 부분에 있다고 생각하여 공간 맵의 일부를 '누락합니다'.
- *편향*: 공간 매핑 데이터의 표면이 밀리거나 당겨져 실제 표면과 불완전하게 정렬됩니다.

이러한 오류가 표시되면 [FeedbackHub](hololens-feedback.md)를 사용하여 피드백을 보내주세요.

## <a name="security-and-storage-for-spatial-data"></a>공간 데이터의 보안 및 스토리지

Microsoft HoloLens용 Windows 10 버전 1803 업데이트 이상은 매핑 데이터를 로컬(디바이스 내) 데이터베이스에 저장합니다.

HoloLens 사용자는 디바이스가 PC에 연결되어 있거나 파일 탐색기 앱을 사용하는 경우에도 맵 데이터베이스에 직접 액세스할 수 없습니다. HoloLens에서 BitLocker를 사용하도록 설정한 경우 저장된 맵 데이터도 전체 볼륨과 함께 암호화됩니다.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>HoloLens에서 맵 데이터 및 알려진 공간 제거

**설정 > 시스템 > 홀로그램** 에서 맵 데이터를 삭제하는 옵션에는 다음 두 가지가 있습니다.

- 주변 홀로그램을 삭제하려면 **주변 홀로그램 제거** 를 선택합니다. 이 명령을 실행하면 맵 데이터 및 현재 공간에 고정된 홀로그램이 지워집니다. 같은 공간에서 디바이스를 계속 사용하면 삭제된 정보를 대체하기 위해 완전히 새로운 맵 섹션을 만들어 저장합니다.

   > [!NOTE]
   > "주변" 홀로그램이란 현재 공간의 동일한 맵 섹션 내에 고정된 홀로그램을 말합니다.

   예를 들어, 이 옵션을 사용하여 집 관련 맵 데이터에 영향을 주지 않고 직장 관련 맵 데이터를 지울 수 있습니다.

- 모든 홀로그램을 삭제하려면 **모든 홀로그램 제거** 를 선택합니다. 이 명령을 실행하면 모든 고정된 홀로그램뿐만 아니라 디바이스에 저장된 모든 맵 데이터가 지워집니다. 홀로그램을 명시적으로 배치해야 합니다. 이전에 배치한 홀로그램을 다시 검색할 수 없습니다.

> [!NOTE]
> 주변 또는 모든 홀로그램을 제거하면 HoloLens는 즉시 현재 공간을 스캔하고 매핑하기 시작합니다.

### <a name="wi-fi-data-in-spatial-maps"></a>공간 맵의 Wi-Fi 데이터

HoloLens는 홀로그램 위치와 HoloLens 알려진 공간 데이터베이스에 저장된 맵 섹션을 서로 연관시키기 위해 Wi-Fi 특성을 저장합니다. Wi-Fi 특성에 대한 정보는 사용자가 액세스할 수 없으며 클라우드를 사용하거나 원격 분석을 사용하여 Microsoft로 전송되지 않습니다.

Wi-Fi를 사용하는 경우 HoloLens는 맵 데이터와 주변 Wi-Fi 액세스 포인트를 서로 연관시킵니다. 네트워크에 연결되어 있든 방금 주변에서 검색되었든 동작에는 차이가 없습니다. Wi-Fi를 사용하지 않는 경우에도 HoloLens는 계속 공간을 검색합니다. 그러나 HoloLens는 공간 데이터베이스 내에서 더 많은 맵 데이터를 검색해야 하며 홀로그램을 찾는 데 더 많은 시간이 필요할 수 있습니다. Wi-Fi 정보가 없는 경우 HoloLens는 지도의 올바른 부분을 찾기 위해 디바이스에 저장된 모든 홀로그램 앵커 및 맵 섹션과 활성 스캔을 비교해야 합니다.

## <a name="related-topics"></a>관련 항목

- [공간 매핑 디자인](/windows/mixed-reality/spatial-mapping)
