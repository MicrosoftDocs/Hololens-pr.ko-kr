---
title: 응용 프로그램 찾기, 설치 및 제거
description: Microsoft Store는 HoloLens와 작동하는 앱과 게임의 출처입니다.  홀로그램 앱을 찾고, 설치하고 제거하는 방법에 대해 자세히 알아보세요.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: Hololens, 스토어, uwp, 앱, 설치
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 44c79a41d7864cd6000ffed1bdd32dab8ffabc39
ms.sourcegitcommit: b437c738f101ac870a29bbdb7fd642eda3d67f00
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406270"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Microsoft Store에서 앱을 찾고, 설치하고 제거

HoloLens와 작동하는 앱과 게임을 얻으려면 Microsoft Store를 방문하세요. HoloLens에서 Store로 이동하면 모든 앱이 HoloLens에서 작동합니다.

HoloLens 용 앱은 2D 뷰 또는 홀로그램 뷰를 사용 합니다. 2D 뷰를 사용 하는 앱은 창과 비슷하게 보여지며 사용자 주변에 위치합니다. 홀로그램 뷰를 사용하는 앱은 사용자를 에워싸며 사용자가 볼 수 있는 유일한 앱이 됩니다.

HoloLens는 Microsoft Store와 HoloLens를 위해 특별히 만들어진 모든 새로운 앱에서 다양하고 흥미로운 앱을 지원합니다.  이 문서에서는 Microsoft Store의 홀로그램 앱에 대해 중점적으로 설명합니다.

사용자 지정 앱의 설치 및 실행 방법에 대한 자세한 내용은 [사용자 지정 홀로그램 앱](holographic-custom-apps.md)을 참조 하세요.

## <a name="find-apps"></a>앱 찾기

**시작** 메뉴에서 Microsoft Store 열기 앱과 게임을 찾습니다. [음성 명령](hololens-cortana.md)을 사용하여 "검색"이라고 말하면 검색 창이 열리고 창이 열리면 " 받아쓰기 시작"이라고 말한 다음 메시지가 나타나면 검색어를 말하기 시작합니다.

> [!NOTE]
> HoloLens 장치에 대한 시스템 요구 사항은 앱 빌드의 아키텍처를 기반으로 합니다. HoloLens에 대한 앱 빌드(1세대)가 매장에서 ARM 아키텍처 패키지를 포함하도록 최신 UWP로 업데이트 되지 않은 경우 HoloLens 2 장치에서 사용할 수 없게 됩니다. 마찬가지로, HoloLens 2 앱에 x86 아키텍처 패키지가 포함되어 있지 않은 경우 HoloLens(1세대) 장치에는 사용할 수 없습니다. HoloLens 장치 아키텍처:
> - x86 = HoloLens (1세대)
> - ARM = HoloLens 2

> [!NOTE]
> 2021년 1월 12일에 다음 앱이 HoloLens 장치에 대한 지원 종료에 도달합니다. 장치의 다음 링크를 사용하여 앱의 웹 버전을 사용하는 것이 좋습니다.

| 앱        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint Mobile | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>앱 설치

앱을 다운로드 하려면 Microsoft 계정으로 로그인 해야 합니다. 일부 앱은 무료이며 바로 다운로드 할 수 있습니다. 유료 앱을 사용 하려면 Microsoft 계정으로 스토어에 로그인 해야 하며 유효한 결제 방법을 보유하고 있어야 합니다.
> [!NOTE]
> Microsoft Store에서 사용하는 계정은 로그인하는 계정과 같지 않아도 됩니다. HoloLens에 회사 또는 학교 계정을 사용하는 경우, Store 앱에서는 개인 계정으로 로그인하여 구입 해야 합니다.

> [!TIP]
> 결제 방법을 설정 하려면 [account.microsoft.com](https://account.microsoft.com/)으로 이동 하 고 **결제 및 대금 청구** > **결제 옵션** > **결제 옵션 추가**를 선택합니다.

1. [**시작** 메뉴](holographic-home.md)를 열려면 HoloLens 1(1세대)에서 [시작 제스처](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) 또는 [피어오르는](hololens1-basic-usage.md) 제스처를 수행합니다.
1. Microsoft Store 앱을 선택합니다. Store 앱이 열리면 다음을 수행합니다.
   1. 검색 바를 사용하여 응용 프로그램을 찾습니다. 
   1. 큐레이터 범주 중에서 HoloLens 용으로 특별히 만들어진 앱 또는 필수 앱을 선택 합니다.
   1. Store 앱의 우측 상단에 있는 **"..."** 단추를 선택한 다음 **내 라이브러리**를 선택하여 이전에 구입한 앱을 확인합니다.
1. 응용 프로그램의 페이지에서**가져오기** 또는 **설치**를 선택 합니다(구입이 필요할 수 있음).

## <a name="update-apps"></a>앱 업데이트
Microsoft Store에서 설치한 앱을 업데이트하려면 Microsoft Store 앱에서 앱을 업데이트할 수 있습니다. 비즈니스용 Microsoft Store에 대해 설치된 앱의 경우 비즈니스용 Microsoft Store에서 해당 앱을 업데이트할 수 있습니다. 
1. [**시작** 메뉴](holographic-home.md)를 열려면 HoloLens 1(1세대)에서 [시작 제스처](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) 또는 [피어오르는](hololens1-basic-usage.md) 제스처를 수행합니다.
1. Store 앱을 선택합니다.
1. Store 앱의 오른쪽 상단을 찾습니다. 
1. **"..."** 또는 “자세히 보기” 단추를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 앱 스크린샷.](images/store-update-1.png)

1. **다운로드 및 업데이트**를 선택합니다.
    1. 장치에서 이전 업데이트를 식별한 경우 아래쪽 화살표와 번호가 표시될 수 있으며 이는 보류 중인 업데이트를 나타냅니다.
1. **업데이트**를 선택합니다. 이제 장치에서 업데이트를 검색하고 다운로드 및 설치하도록 설정합니다. 
 
   > [!div class="mx-imgBorder"]
   > ![업데이트를 다운로드하는 Microsoft Store 앱 스크린샷.](images/store-update-2.png.jpg)

> [!NOTE]
> 장치에 있는 앱이 조직에서 분리되어 있는 경우 동일한 상업용 앱 관리 방법을 통해 업데이트할 수 있습니다. 이러한 상황에 해당될 경우 [상업용 앱 배포에 대한 개요를 자세히 읽어보세요.](app-deploy-overview.md)
>
> 사이드라인되거나 배포된 사용자 지정 앱을 업데이트하려면 업데이트된 버전의 앱과 동일한 방법을 사용해야 합니다. 사용자 지정 앱의 설치 및 실행 방법에 대한 자세한 내용은 [사용자 지정 홀로그램 앱](holographic-custom-apps.md)을 참조 하세요.

## <a name="uninstall-apps"></a>앱 설치 제거

앱을 제거하는 두 가지 방법입니다.  Microsoft Store 또는 시작 메뉴를 통해 응용 프로그램을 제거할 수 있습니다.

### <a name="uninstall-from-the-start-menu"></a>시작 메뉴에서 설치 제거

**시작** 메뉴를 열거나 **모든 앱** 목록에서 앱을 찾습니다. 메뉴가 나타날 때까지 선택하고 길게 탭하고 **제거**를 선택합니다.

### <a name="uninstall-from-the-microsoft-store"></a>Microsoft Store에서 설치 제거

**시작** 메뉴에서 Microsoft Store를 열고 제거할 앱을 찾습니다.  Store 페이지에서 설치된 각 응용 프로그램에 **설치 제거** 단추가 있습니다.
