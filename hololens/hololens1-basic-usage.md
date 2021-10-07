---
title: HoloLens(1세대) 둘러보기
description: HoloLens(1세대) 인터페이스, 손 추적 기능 및 홀로그램 애플리케이션 사용에 대한 간략한 둘러보기를 시작합니다.
ms.assetid: 064f7eb0-190e-4643-abeb-ed3b09312042
ms.date: 8/9/2021
ms.reviewer: sean-kerawala
manager: sean-kerawala
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 3723a30499c0237f19d85b48109b40ca643c6bdb
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600749"
---
# <a name="getting-around-hololens-1st-gen"></a>HoloLens(1세대) 둘러보기

홀로그램의 세계를 한 단계씩 단계별로 분석할 준비가 되셨나요? 시작할 몇 가지 정보는 다음과 같습니다.

이 가이드에서는 혼합 현실에 대한 소개, 홀로그램과 상호 작용하기 위한 제스처 및 Windows Holographic에 대한 소개를 제공합니다.

## <a name="discover-mixed-reality"></a>혼합 현실 검색

HoloLens 홀로그램은 실제 환경과 혼합되어 전 세계의 일부인 것처럼 보이고 소리를 내도록 합니다. 홀로그램이 주위에 있는 경우에도 주변을 보고 자유롭게 이동하며 다른 사람 및 개체와 상호 작용할 수 있습니다. 이 환경을 "혼합 현실"이라고 합니다.

홀로그램 프레임은 홀로그램에 눈의 세부 정보를 가장 민감하게 배치하고, 통과 렌즈는 주변 시각을 가리지 않게 합니다. 공간 음향을 사용하면 홀로그램이 뒤에 있더라도 홀로그램을 정확히 파악할 수 있습니다. 또한 HoloLens 환경을 학습하고 이해하기 때문에 실제 개체 주위에 홀로그램을 배치할 수 있으며 앱과 게임도 마찬가지입니다. 따라서 게임의 문자가 화면에 맡기거나 [우주 로봇이 벽에서 깨질 수 있습니다.](https://www.microsoft.com/store/apps/9nblggh5fv3j)

## <a name="use-hololens-with-your-hands"></a>손으로 HoloLens 사용

HoloLens를 다루는 것은 스마트폰을 사용하는 것과 아주 비슷합니다. 손을 사용하여 홀로그램 창, 메뉴 및 단추를 조작할 수 있습니다.  가리키거나 클릭하거나 탭하는 대신 응시, [음성](hololens-cortana.md)및 제스처를 사용하여 앱과 홀로그램을 선택하고 HoloLens 탐색합니다.

이러한 기본 상호 작용을 알고 있는 경우 HoloLens 진행하는 것이 스냅입니다.

HoloLens 처음 사용할 때 기본 사항들을 살펴보겠습니다. **시작** 메뉴에서 제스처 자습서도 찾을 수 있습니다. 학습 제스처 앱을 찾습니다.

### <a name="the-hand-tracking-frame"></a>손 추적 프레임

HoloLens는 사용자 양쪽으로 몇 피트까지 볼 수 있는 센서를 가지고 있습니다. 손을 사용할 때는 해당 프레임 안에 손을 두어야 합니다. 그렇지 않으면 HoloLens가 손을 보지 못합니다. 이동하면 프레임이 함께 이동합니다.  

![HoloLens 손 추적 프레임을 보여주는 이미지.](./images/hololens-2-gesture-frame.png)

### <a name="open-the-start-menu-with-bloom"></a>시작 메뉴 열기

시작 메뉴를 열려면 다음을 **수행합니다.**

1. 제스처 프레임에 있도록 손을 앞에 붙입니다.
1. Bloom: 모든 손가락을 모은 다음, 손을 엽니다.
  ![꽃 제스처를 보여 주는 애니메이션입니다.](./images/hololens-bloom.gif)

### <a name="select-holograms-with-gaze-and-air-tap"></a>응시 및 에어 탭이 있는 홀로그램 선택

앱 또는 다른 홀로그램을 선택하려면 선택한 홀로그램을 직접 보는 동안 에어 탭합니다. 다음 단계를 수행하세요.

1. 선택하려는 홀로그램을 응시합니다.
1. 집게손가락을 천장을 향해 위로 가리킵니다.
1. 에어 탭: 손가락을 낮추고 빠르게 발생합니다.
   ![에어 탭 동작 애니메이션.](./images/hololens-air-tap.gif)

### <a name="select-a-hologram-by-using-your-voice"></a>음성을 사용하여 홀로그램 선택

1. 응시 커서는 헤드를 이동하여 이동하는 점입니다. 이를 사용하여 정밀도로 음성 명령을 대상으로 지정할 수 있습니다.
1. 선택하려는 홀로그램을 응시합니다.
1. 홀로그램을 선택하려면 "선택"이라고 말합니다.

## <a name="holograms-and-apps"></a>홀로그램스 및 앱

이제 테스트에 제스처를 넣을 차례입니다.

시작 메뉴 설치된 앱을 찾을 수 있으며 [Microsoft Store](holographic-home.md) HoloLens(1세대)용 앱이 더 있습니다.

**시작** 메뉴를 열고 앱을 선택합니다.

HoloLens 앱을 사용하는 것은 PC에서와 약간 다릅니다. 일부 앱은 2D 보기를 사용하고 다른 Windows 애플리케이션처럼 보입니다. 다른 앱(몰입형 앱)은 3D 보기를 사용하며, 앱을 시작하면 표시되는 유일한 앱이 됩니다.

앱 창 또는 앱 시작 관리자를 배치하면 앱 창 또는 앱 시작 관리자를 제거할 때까지 배치된 상태로 유지됩니다. 언제든지 혼합 현실 홈 이러한 홀로그램을 이동하거나 크기를 조정합니다.

## <a name="move-resize-and-rotate-apps"></a>앱 이동, 크기 조정 및 회전

HoloLens 앱 이동 및 크기 조정은 PC에서와 약간 다르게 작동합니다. 앱을 끌지 않고 [제스처](https://support.microsoft.com/help/12644/hololens-use-gestures) 또는 [클릭하여](hololens1-clicker.md)응시를 사용합니다. 3D 공간에서 앱 창을 회전할 수도 있습니다.

> [!TIP]
> 음성을 사용하여 앱 다시 정렬 - 앱을 응시하고 "Face me", "더 큽다" 또는 "작음"이라고 말합니다. 또는 Cortana 앱을 이동해야 합니다. 예를 들어 "hey Cortana, \* *move app name \** here."

### <a name="move-an-app"></a>앱 이동

앱 창의 제목 표시줄에서 앱을 응시한 후 다음 중 하나를 수행합니다.

- 길게 탭하여 앱을 선택합니다. 손을 이동하여 앱을 배치하고 손가락을 들어 놓습니다.
- **조정을** 선택하고, 길게 누른 다음, 손을 이동하여 앱을 배치합니다. 손가락을 들어 놓은 다음, **완료를** 선택합니다.
- **조정을** 선택하고 클릭하여 클릭하여 클릭하여 앱을 배치하기 위해 손을 이동합니다. 클릭하여 해제한 **다음, 완료를** 선택합니다.

> [!TIP]
> 앱을 이동할 때 앱을 놓으면 응시를 통해 따라 제스처 프레임에 손을 유지해야 합니다.

### <a name="resize-an-app"></a>앱 크기 조정

앱을 응시한 후 다음 중 하나를 수행합니다.

- 앱 창의 모서리 또는 가장자리를 응시하고 길게 누릅니다. 손을 이동하여 앱의 크기를 변경하고 완료되면 손가락을 들어 올립니다.
- **조정을** 선택합니다. 앱의 모서리에 있는 파란색 사각형 중 하나를 응시하고, 길게 누른 다음, 손을 이동하여 앱 크기를 조정합니다. 손가락을 들어 놓은 다음, **완료를** 선택합니다.
- **조정을** 선택합니다. 앱의 모서리에 있는 파란색 사각형 중 하나를 응시하고, 클릭하여 클릭하여 누른 다음, 손을 이동하여 앱 크기를 조정합니다. 클릭하여 해제한 **다음, 완료를** 선택합니다.

> [!TIP]
> 조정 모드에서는 홀로그램을 이동하거나 크기를 조정할 수 있습니다.

### <a name="rotate-an-app"></a>앱 회전

앱을 응시하고 두 손을 길게 눌러 선택합니다. 한 손을 안정적으로 유지하고 다른 손을 이동하여 앱을 회전합니다. 완료되면 두 개의 인덱스 손가락을 모두 발생합니다.

### <a name="scroll-content-in-an-app-window"></a>앱 창에서 콘텐츠 스크롤

앱 창의 콘텐츠를 응시합니다. 길게 누를 때 손을 약간 위쪽 또는 아래쪽으로 이동하여 콘텐츠를 스크롤합니다.

## <a name="share-your-hololens-with-multiple-people"></a>여러 사용자와 HoloLens 공유

한 HoloLens 많은 사람과 공유하거나 많은 사람들이 HoloLens 디바이스 세트를 공유하도록 하는 것이 일반적입니다.  

### <a name="share-with-multiple-people-each-using-their-own-account"></a>각각 자신의 계정을 사용하여 여러 사람과 공유

**필수 조건:** HoloLens(1세대)를 [Windows Holographic for Business 업그레이드해야](hololens-upgrade-enterprise.md)합니다.

자신의 Azure AD(Azure Active Directory) 계정을 사용하는 경우 여러 사용자가 각각 자신의 사용자 설정 및 사용자 데이터를 디바이스에 유지할 수 있습니다.

여러 사람이 HoloLens 자신의 계정을 사용할 수 있도록 하려면 다음 단계를 수행합니다.

1. 디바이스를 설정할 때 **내 직장 또는 학교 소유를** 선택하고 Azure AD 계정을 사용하여 로그인합니다.
1. 설정을 완료한 후 계정 **설정(설정**  >  계정)에 다른 **사용자가** 포함되어 있는지 **확인합니다.**

HoloLens 사용하려면 각 사용자가 다음 단계를 수행해야 합니다.

1. 다른 사용자가 디바이스를 사용하고 있는 경우 전원 단추를 한 번 눌러 대기로 이동합니다. 그런 다음 전원 단추를 다시 눌러 잠금 화면으로 돌아갑니다.

1. Azure AD 계정 자격 증명을 사용하여 디바이스에 로그인합니다. 디바이스를 처음 사용하는 경우 HoloLens 자신의 눈에 [맞게 보정해야](hololens-calibration.md) 합니다.

디바이스 사용자 목록을 보거나 디바이스에서 사용자를 제거하려면 **설정**  >  **계정**  >  **기타 사용자** 로 이동합니다.

### <a name="share-with-multiple-people-all-using-the-same-account"></a>동일한 계정을 사용하여 여러 사람과 공유

단일 사용자 계정을 사용 하는 동안 여러 사용자가 HoloLens 장치를 공유할 수도 있습니다.

동일한 계정을 공유 하는 사용자는 **설정** 에서 HoloLens를 보정 해야 합니다.  [보정](hololens-calibration.md)에 대 한 자세한 내용을 참조 하세요.

## <a name="meet-the-hololens-1st-gen-clicker"></a>HoloLens (첫 번째 gen) Clicker 충족

[HoloLens (첫 번째 Gen) clicker](hololens1-clicker.md) 는 holograms와 상호 작용 하는 다른 방법을 제공 합니다. HoloLens와 [쌍](hololens-connect-devices.md) 으로 연결 하 고,이를 사용자의 응시와 함께 사용 하 여 선택 하 고 스크롤합니다.

## <a name="next-steps"></a>다음 단계

축하합니다! HoloLens (첫 번째 gen)를 사용할 준비가 되었습니다.

이제 특정 요구 사항에 맞게 HoloLens (첫 번째 gen)를 구성할 수 있습니다.

[마우스 및 키보드와 같은 bluetooth 장치 커넥트](hololens-connect-devices.md)

[음성 및 Cortana에 대 한 자세한 정보](hololens-cortana.md)

### <a name="help-i-dont-see-my-holograms"></a>도와주세요! 내 holograms 표시 되지 않습니다.

HoloLens를 사용 하는 동안 holograms가 표시 되지 않으면 다음 몇 가지 작업을 수행해 보세요.

- 올바른 영역을 확인 하 고 있는지 확인 하세요 &mdash; . holograms.
- 사용자가 직접 광선을 많이 사용 하지 않고 적절 한 장소에 있는지 확인 합니다.
- 대기. HoloLens 공간을 인식 하는 데 문제가 있으면 이전에 배치 된 holograms를 다시 시작 하는 데 최대 1 분 정도 걸릴 수 있습니다.
- 문제가 지속 되 면 **설정** System 홀로그램스에서 홀로그램스 저장소 데이터  >    >  를 지운 다음 혼합 현실 홈에 Holograms를 추가 하는 것이 좋습니다.
