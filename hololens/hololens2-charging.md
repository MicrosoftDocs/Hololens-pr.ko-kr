---
title: HoloLens 2 배터리 및 충전
description: HoloLens를 충전하고 외부 배터리 팩을 사용하는 방법입니다.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034618"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 배터리 및 충전

이 페이지에서는 HoloLens 2 충전 및 외부 배터리 팩 사용에 대한 세부 정보를 제공합니다.

## <a name="charging-the-device"></a>장치 충전

HoloLens 2와 함께 제공된 [충전기와 USB Type-C 케이블](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)을 사용하는 것이 장치를 충전하는 가장 좋은 방법입니다. HoloLens 2에 포함된 충전기는 최대 9V/2A(18W)를 제공합니다. 제공된 벽면 충전기를 사용하는 경우 HoloLens 2 장치는 장치가 대기 중일 때 65분 이내에 배터리를 완전 충전할 수 있습니다. 해당 액세서리를 사용할 수 없는 경우 사용 가능한 충전기가 최소 15W의 전력을 지원할 수 있는지 확인하세요.

> [!NOTE]
> 가능하면 PC에 연결하여 USB를 통해 장치를 충전하지 마세요. 속도가 느립니다.

## <a name="checking-the-battery-charge-level"></a>배터리 충전 수준 확인
장치가 제대로 부팅되고 실행되고 있으면 다음과 같은 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.

- HoloLens 장치 UI의 주 메뉴에서 확인합니다.
- 전원 단추 가까이에 있는 LED로 확인합니다(40% 충전의 경우 LED가 최소 2개 켜진 것을 볼 수 있어야 함).
    - 장치가 충전 중일 때는 배터리 표시등이 켜져 있고 현재 충전 수준을 나타냅니다.  마지막 표시등은 페이드 인/페이드 아웃하여 활성 충전을 나타냅니다.
    - HoloLens가 켜져 있으면 배터리 표시등이 배터리 잔량을 5단계로 표시합니다.
    - 5개의 표시등 중 하나만 켜져 있으면 배터리 잔량이 20% 미만입니다.
    - 배터리 잔량이 매우 낮은 상태에서 장치를 켜려고 하면 표시등 1개가 잠깐 깜박인 다음 꺼집니다.
- 호스트 PC에서 **파일 탐색기** 를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾습니다. 장치를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다. 대화 상자에 배터리 충전 잔량이 표시됩니다.

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됩니다.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>대체 충전 사양

HoloLens 2는 최대 27W의 [USB 전력 전송](https://www.usb.org/usb-charger-pd) 소스로 충전할 수 있습니다. 소스에서 최소 10W를 제공할 수 있는 경우 HoloLens 작동 시간을 연장할 수 있습니다(일부 워크로드의 경우 거의 무기한). 

> [!NOTE]
> USB-A-USB-C 충전 케이블을 사용하면 충전이 7.5W로 제한됩니다. 작동 시간은 연장되지만, USB-C-C로 사용하는 만큼 길지 않습니다.

HoloLens가 대기 모드인 경우 18W는 내부 배터리의 최대 충전율에 도달하기에 충분합니다. HoloLens가 사용 중인 경우 HoloLens는 충전보다 작동에 우선 순위를 두므로 충전율이 줄어들 수 있습니다.

> [!IMPORTANT]
> HoloLens 2를 최소 5V/1.5A로 충전하는 것이 좋습니다. 최소 5V/1.5를 제공할 수 없는 충전기는 사용할 수 없습니다. 

### <a name="external-battery-packs"></a>외부 배터리 팩

위의 사양을 충족하는 배터리 팩은 HoloLens 2와 함께 사용할 수 있습니다. 그러나 일부 USB-C 배터리 팩은 동일한 USB-C 포트를 통해 재충전하고 전력을 제공합니다. 이러한 배터리 팩에서 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)를 구현하여 배터리 팩이 HoloLens에서 충전되지 않고 HoloLens를 충전하도록 하는 것이 중요합니다. 

### <a name="managing-heat"></a>열 관리

모든 장치와 마찬가지로 HoloLens에는 열이 발생합니다. 충전이 빠를수록 더 많은 열이 발생합니다. 또한 낮은 배터리 수준에서 충전을 시작하면 배터리가 거의 가득 찬 상태에서 충전을 시작하는 것보다 더 많은 열이 발생합니다. 뜨거운 환경에서 장시간 HoloLens를 작동해야 하는 고객은 다음과 같은 기술을 사용할 수 있습니다.

- 내부 배터리가 완전히 충전된 경우에도 HoloLens 2를 외부 전원에 연결하는 것이 좋습니다.
- 외부 배터리가 고갈되면 HoloLens는 내부 배터리로 계속 작동합니다.    
- 위의 단계를 수행한 후에도 발열 문제가 있는 경우 충전을 1.5A로 제한하는 충전기 또는 배터리 팩을 사용하는 것이 좋습니다. 내부 배터리는 계속 천천히 고갈되므로 이 옵션은 용량만큼의 작동 시간을 제공하지 않습니다.

## <a name="troubleshooting"></a>문제 해결


### <a name="hololens-charges-external-battery"></a>HoloLens 외부 배터리 충전
HoloLens 2가 외부 배터리로 충전되는 것이 아니라 HoloLens 2가 외부 배터리를 충전하는 경우 이는 배터리가 [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)를 구현하지 않았음을 나타냅니다. 이 문제를 해결하려면 최신 배터리 팩으로 전환하는 것이 좋지만 대신 USB-A를 USB-C 케이블로 전환해 볼 수 있습니다. 이 경우 충전율은 7.5W로 제한된다는 점을 유념하세요.
