---
title: 셀룰러 및 5G에 연결
description: HoloLens 혼합 현실 장치에서 셀룰러 네트워크에 연결합니다.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034261"
---
# <a name="connect-to-cellular-and-5g"></a>셀룰러 및 5G에 연결

HoloLens 2는 셀룰러 및 5G 네트워크에 연결하도록 다음 두 가지 방법을 지원합니다.

- 일반적으로 "핫스팟"이라고 하는 셀룰러 장치에서 제공하는 임시 WiFi 네트워크
- USB-C 테더링 장치에 대한 제한된 지원

## <a name="hotspot-wifi"></a>핫스팟(WiFi)

셀룰러 연결이 필요한 대부분의 경우 핫스팟을 통해 충족할 수 있습니다. HoloLens 2 WiFi는 가장 일반적인 사용 사례에 필요한 대역폭과 대기 시간 요구 사항을 제공할 수 있는 802.11ac를 지원합니다. WiFi는 케이블 없이 가장 많은 수의 셀룰러 장치와 호환됩니다.

### <a name="connecting-to-a-hotspot"></a>핫스팟에 연결

1. 장치 설명서에서 핫스팟 모드를 사용하는 방법을 참조하세요.
1. 핫스팟 모드를 사용하도록 설정하여 네트워크 이름과 알려진 암호를 제공합니다.
1. HoloLens 2 네트워크 설정에서 2단계에서 만든 WiFi 네트워크를 찾아 연결합니다.

## <a name="usb-c-tethering"></a>USB-C 테더링

USB-C 테더링은 낮은 대기 시간이 필요한 고급 워크로드의 대기 시간을 줄일 수 있습니다. 예를 들어 [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)은 테더링의 이점을 누릴 수 있습니다. 테더링하려면 셀룰러 장치와 HoloLens 사이에 케이블이 필요하며 제한된 수의 장치에서 테더링이 지원됩니다.

### <a name="usb-c-compatibility"></a>USB-C 호환성

이더넷 어댑터로 표시되는 장치는 Windows Holographic 버전 2004 이상에서 사용할 수 있습니다.

이더넷 어댑터로 표시되지 않는 장치는 일반 Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 드라이버를 지원해야 합니다. 그러나 이러한 장치는 제한된 수만 HoloLens 2와 호환됩니다. 장치의 제조업체에 일반 Microsoft RNDIS 드라이버를 지원하는지를 문의하세요.

RNDIS와 호환되지 않는 장치나, 드라이버 또는 응용 프로그램을 설치해야 하는 장치는 지원되지 않습니다.

Microsoft는 호환되는 장치 목록을 유지 관리하지 않지만, [여기](https://aka.ms/HLCommunityCell)에 해당 주제에 관한 커뮤니티 토론이 있습니다.

### <a name="connecting-to-a-tethered-device"></a>테더링된 장치에 연결

1. 장치 설명서에서 USB를 통해 데이터 공유를 사용하도록 설정하는 방법을 참조하세요. 이 설정은 "USB 테더링", "데이터 공유" 또는 "USB 모뎀"이라고도 합니다.
1. USB를 통해 데이터 공유를 사용하도록 설정합니다.
1. 장치를 HoloLens USB-C 포트에 연결합니다.
1. HoloLens 2 네트워크 설정에서 이 장치가 자동으로 이더넷 연결로 표시됩니다.
