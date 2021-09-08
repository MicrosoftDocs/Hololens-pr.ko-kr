---
title: HoloLens 2 이동 플랫폼 모드
description: 이동 플랫폼에서 HoloLens를 사용하는 방법
keywords: 이동 플랫폼, 동적 모션, hololens, 이동 플랫폼 모드
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a0717524cd1f762c92a5b821ae90acb8474dafd2
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190398"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>저 동적 모션 이동 플랫폼의 이동 플랫폼 모드

**참가자 빌드 20348.1411** 에서 HoloLens 2의 저 동적 모션 이동 플랫폼 추적을 위한 베타 지원을 추가했습니다. 빌드를 설치하고 이동 플랫폼 모드를 사용하면, 대형 선박 등 이전에는 접근할 수 없었던 환경에서 HoloLens 2를 사용할 수 있습니다. 현재 이 기능은 이러한 특정 이동 플랫폼만 사용하는 것을 목표로 합니다. 다른 환경에서 기능을 사용해도 무방하지만, 이 기능은 우선 이러한 환경에 대한 지원을 추가하는 데 중점을 둡니다.

> [!NOTE]
> 이 기능은 현재 [Windows 참가자](hololens-insider.md)를 통해서만 사용할 수 있습니다.

![이동 플랫폼 예.](./images/mpm-compare.gif)

이 문서에서는 다음 내용을 설명합니다.

1. [이동 플랫폼이 필요한 이유](#why-moving-platform-mode-is-necessary)
1. [이동 플랫폼 모드 사용](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>이동 플랫폼 모드가 필요한 이유

HoloLens는 안정적인 홀로그램을 표시하기 위해 [6도의 자유도](https://en.wikipedia.org/wiki/Six_degrees_of_freedom)(X, Y, Z, 변환 및 롤, 피치, 요 회전)로 머리 위치를 추적할 수 있어야 합니다. 이를 위해 HoloLens는 두 개의 개별 소스에서 두 가지 유사한 정보를 추적합니다.

1. 가시광선 카메라 – 환경(예: HoloLens를 사용하는 실제 방)을 추적합니다.
1. IMU(관성 측정 단위) - 가속도계, 자이로스코프 그리고 지구를 기준으로 상대적인 머리 움직임과 방향을 추적하는 자력계로 구성

이 두 소스의 정보는 매끄러운 홀로그램을 렌더링하기 위해 낮은 대기 시간과 충분히 높은 빈도로 머리 위치를 추적하기 위해 합성됩니다.

그러나 이 접근 방식은 중요한 가정을 기반으로 합니다. (카메라에 의해 추적되는) 환경은 지구를 기준으로 정지 상태를 유지합니다(IMU가 측정 가능). 그렇지 않은 경우(예:물 위의 보트) 두 소스의 정보가 서로 충돌하여 추적기가 추적하지 못할 수 있습니다. 이 충돌은 잘못된 위치 정보를 생성하고 흐릿한 홀로그램이나 심지어 추적 상실을 초래합니다.

이동 플랫폼 모드가 이런 문제를 해결합니다. 이동 플랫폼 모드를 사용하면 두 소스를 완전히 일치시키기 위해 추적기의 센서 입력에만 의존할 수 없다는 것을 알 수 있습니다. 대신, 시각적 추적에 더 많이 의존하고 부적합한 관성 모션 데이터를 신속하게 식별하고 IMU 입력을 사용하기 전에 적절하게 필터링해야 합니다.

## <a name="supported-environments-and-known-limitations"></a>지원되는 환경 및 알려진 제한 사항

이동 플랫폼 모드는 관성 및 시각적 데이터 충돌 사례를 지능적으로 처리하기 위해 개발되었지만, 현재는 저 동적 모션을 경험할 수 있는 대형 해양 선박에 적용됩니다. 이는 확실히 제한 사항과 지원되지 않는 시나리오가 있음을 의미합니다.

### <a name="known-limitations"></a>알려진 제한 사항

- MPM(이동 플랫폼 모드)이 지원되는 유일한 환경은 저 동적 모션을 경험할 수 있는 대형 해양 선박입니다. 즉, 높은 빈도의 움직임과 높은 수준의 가속도 및 [저크](https://en.wikipedia.org/wiki/Jerk_(physics))로 인해 많은 일반적인 환경/상황에서는 아직 지원되지 **않습니다**. 예를 들면, 비행기, 기차, 자동차, 자전거, 버스, 작은 배, 엘리베이터 등이 있습니다.
- MPM을 사용하는 경우, 특히 고르지 않은 물 위에서는 홀로그램이 다소 흔들릴 수 있습니다.
- 지원되지 않는 환경에서 사용자가 MPM을 사용해도 무방하지만, 지원되지 않는 공간에서 디바이스가 계속 추적하려 한다면 사용자에게 바람직하지 않은 부작용을 발생할 수 있습니다. 예를 들어, MPM을 사용하면, 이전에는 불가능했지만, 엘리베이터에서 층을 이동하면서 사용하는 것이 가능해졌습니다. 그러나 MPM은 디바이스가 추적하도록 허용할 수 있지만, 이 경우 맵 관리를 처리하지 않습니다. 사용자는 엘리베이터에서 층을 이동하면 디바이스가 위층과 아래층을 혼동하고 맵 품질에도 부정적인 영향을 준다는 것을 알게 됩니다.

## <a name="prerequisites"></a>필수 구성 요소

이동 플랫폼 모드에 대한 베타 지원에는 몇 가지 필수 구성 요소만 필요합니다.

1. [ARC를 통해 최신 참가자 빌드를 플래시](hololens-insider.md#ffu-download-and-flash-directions)하거나 [디바이스를 등록 및 업데이트](hololens-insider.md#start-receiving-insider-builds)하여 20348.1411 이상의 빌드를 설치합니다.

   > [!NOTE]
   > 이 빌드는 현재 [참가자 개발 채널](hololens-insider.md#start-receiving-insider-builds)에서만 사용할 수 있습니다.

2. [개발자 모드와 장치 포털](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)을 사용합니다.

## <a name="enabling-moving-platform-mode"></a>이동 플랫폼 모드 사용

이동 플랫폼 모드를 사용하려면 먼저 [장치 포털을 사용](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)합니다.

1. 왼쪽 메뉴에서 **시스템** 아코디언을 선택합니다.

   ![첫 번째 이미지.](.\images\moving-platform-1w.png)

2. **이동 플랫폼 모드** 페이지를 선택하고 **이동 플랫폼 모드** 확인란을 선택합니다.

    ![두 번째 이미지.](.\images\moving-platform-2z.png)

3. 경고 메시지가 표시되면 **확인** 을 선택합니다.

   ![세 번째 이미지.](.\images\moving-platform-3w.png)

4. 오른쪽 위에 있는 장치 포털 **전원** 메뉴를 통해 수행하거나 다음의 음성 명령 &quot;디바이스 재부팅&quot;을 실행하고 &quot;예&quot;를 선택하여 디바이스를 재부팅합니다.

   ![네 번째 이미지.](.\images\moving-platform-4z.png)

장치 포털에서 이동 플랫폼 모드 옵션이 보이지 않으면 적절한 빌드가 아닐 수 있습니다. [필수 구성 요소](#prerequisites) 섹션을 참조하세요.

## <a name="reporting-issues"></a>문제 보고

위에서 설명한 것처럼 이 기능은 개발자 모드에서만 사용할 수 있는 베타 기능입니다. 즉, 문제가 발생할 수 있습니다. 문제가 발생한 경우 제품을 조사하고 개선할 수 있도록 다음을 진행해주세요.

1. **홀로그램 정확도, 안정성 및 신뢰성** 카테고리 아래의 [피드백 허브](hololens-feedback.md)를 통해 문제를 보고하되, 다음을 포함해주세요.
    1. 예상 동작 및 경험한 동작을 포함한 문제 설명
    1. 문제의 혼합 현실 [비디오 캡처](holographic-photos-and-videos.md#capture-a-mixed-reality-video)
2.  [https://aka.ms/hlsupport](https://aka.ms/hlsupport)에서 지원 사례를 열고 피드백 허브 URL을 공유하면, 후속 질문이 있는 경우 연락할 수 있습니다.