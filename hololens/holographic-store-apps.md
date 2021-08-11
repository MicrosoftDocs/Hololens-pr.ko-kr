---
title: 애플리케이션 찾기, 설치 및 제거
description: Microsoft Store는 HoloLens와 작동하는 앱과 게임의 소스입니다.  홀로그램 앱을 찾고, 설치하고, 제거하는 방법에 대해 자세히 알아봅니다.
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
ms.openlocfilehash: c26c3a236a1047e62d480c27ec1bbb09faa63630eb29e0e1103546842d6a76d3
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664794"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Microsoft Store에서 애플리케이션 찾기, 설치 및 제거

HoloLens와 작동하는 앱과 게임을 얻으려면 Microsoft Store를 방문하세요. HoloLens에서 스토어로 이동하면 표시되는 모든 앱이 스토어에서 실행됩니다.

HoloLens의 앱은 2D 보기 또는 홀로그램 보기를 사용합니다. 2D 보기를 사용하는 앱은 창처럼 보이고 사용자 주위의 모든 위치에 배치할 수 있습니다. 홀로그램 보기를 사용하는 앱은 사용자 주위에 있고 사용자가 볼 수 있는 유일한 앱이 됩니다.

HoloLens는 Microsoft Store의 많은 기존 애플리케이션과 HoloLens용으로 특별히 빌드된 새로운 앱을 지원합니다.  이 문서에서는 Microsoft Store의 홀로그램 애플리케이션에 중점을 둡니다.

사용자 지정 앱 설치 및 실행에 대한 자세한 내용은 [사용자 지정 홀로그램 애플리케이션](holographic-custom-apps.md)을 참조하세요.

## <a name="find-apps"></a>앱 찾기

**시작** 메뉴의 Microsoft Store를 엽니다. 그런 다음, 앱 및 게임을 찾습니다. [음성 명령](hololens-cortana.md)을 사용하여 "검색"이라고 말하면 검색할 수 있습니다. 검색 창이 열리면 "Start dictating"이라고 말한 다음, 메시지가 표시되면 검색어를 말합니다.

> [!NOTE]
> HoloLens 디바이스의 시스템 요구 사항은 앱 빌드의 아키텍처를 기반으로 합니다. HoloLens(1세대)용 앱 빌드가 ARM 아키텍처 패키지를 포함하도록 스토어의 최신 UWP로 업데이트되지 않은 경우 HoloLens 2 디바이스에서 사용할 수 없습니다. 마찬가지로, HoloLens 2 앱에 x86 아키텍처 패키지가 포함되어 있지 않은 경우 HoloLens(1세대) 디바이스에 사용할 수 없습니다. HoloLens 디바이스 아키텍처:
> - x86 = HoloLens(1세대)
> - ARM = HoloLens 2

> [!NOTE]
> 2021년 1월 12일에 다음 앱은 HoloLens 디바이스에서 지원이 종료됩니다. 디바이스의 다음 링크를 사용하여 앱의 웹 버전을 사용하는 것이 좋습니다.

| 앱        | 링크                                          |
|------------|-----------------------------------------------|
| Excel 모바일      | https://office.live.com/start/Excel.aspx      |
| Word 모바일       | https://office.live.com/start/Word.aspx       |
| PowerPoint 모바일 | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>앱 설치

앱을 다운로드하려면 Microsoft 계정으로 로그인해야 합니다. 일부 앱은 무료이며 바로 다운로드할 수 있습니다. 구매해야 하는 앱의 경우 Microsoft 계정으로 스토어에 로그인해야 하며 유효한 결제 방법을 보유하고 있어야 합니다.

> [!NOTE]
> Microsoft Store에서 사용하는 계정은 로그인하는 계정과 같지 않아도 됩니다. HoloLens에 회사 또는 학교 계정을 사용하는 경우, 스토어 앱에서 개인 계정으로 로그인하여 구입해야 합니다.

> [!TIP]
> 결제 수단을 설정하려면 [account.microsoft.com](https://account.microsoft.com/)으로 이동하여 **결제 및 청구** > **결제 옵션** > **결제 옵션 추가** 를 선택합니다.

1. [**시작** 메뉴](holographic-home.md)를 열려면 HoloLens(1세대)에서 [시작 제스처](/hololens/hololens2-basic-usage#start-gesture) 또는 [블룸](hololens1-basic-usage.md) 동작을 수행합니다.

1. Microsoft Store 앱을 선택합니다. 스토어 앱이 열리면 다음을 수행합니다.
   1. 검색 창을 사용하여 애플리케이션을 찾습니다. 
   1. 큐레이팅된 범주 중 하나에서 HoloLens용으로 특별히 제작된 필수 앱 또는 앱을 선택합니다.
   1. 스토어 앱의 오른쪽 위에서 **"..."** 단추를 선택한 다음, **내 라이브러리** 를 선택하여 이전에 구매한 앱을 봅니다.

1. 애플리케이션 페이지에서 **가져오기** 또는 **설치** 를 선택합니다(구매해야 할 수 있음).

## <a name="update-apps"></a>앱 업데이트

Microsoft Store에서 설치한 앱을 업데이트하려면 Microsoft Store 앱에서 앱을 업데이트할 수 있습니다. 비즈니스용 Microsoft Store에 설치된 앱의 경우 비즈니스용 Microsoft Store에서 해당 앱을 업데이트할 수 있습니다. 

1. [**시작** 메뉴](holographic-home.md)를 열려면 HoloLens(1세대)에서 [시작 제스처](/hololens/hololens2-basic-usage#start-gesture) 또는 [블룸](hololens1-basic-usage.md) 동작을 수행합니다.

1. 스토어 앱을 선택합니다.

1. 스토어 앱의 오른쪽 위를 살펴봅니다. 

1. **"..."** 또는 "자세히 보기" 단추를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 앱 스크린샷.](images/store-update-1.png)

1. **다운로드 및 업데이트** 를 선택합니다.
    1. 디바이스가 이전에 업데이트를 식별한 경우 아래쪽 화살표와 보류 중인 업데이트를 나타내는 번호가 있을 수 있습니다.

1. **업데이트 가져오기** 를 선택합니다. 이제 디바이스가 업데이트를 검색하고 다운로드 및 설치하도록 설정합니다. 
 
   > [!div class="mx-imgBorder"]
   > ![업데이트를 가져오는 Microsoft Store 앱 스크린샷..](images/store-update-2.png.jpg)

> [!NOTE]
> 디바이스의 앱이 조직에서 배포된 경우 동일한 상용 앱 관리 방법을 통해 업데이트할 수 있습니다. 이러한 상황에 해당하는 경우 [상업용 앱 배포 개요](app-deploy-overview.md)를 통해 자세히 알아보세요.
>
> 테스트용으로 로드되거나 배포된 사용자 지정 앱을 업데이트하려면 앱의 업데이트된 버전과 동일한 방법을 사용해야 합니다. 사용자 지정 앱 설치 및 실행에 대한 자세한 내용은 [사용자 지정 홀로그램 애플리케이션](holographic-custom-apps.md)을 참조하세요.

## <a name="uninstall-apps"></a>앱 제거

애플리케이션을 제거하는 세 가지 방법이 있습니다. Microsoft Store, 시작 메뉴 또는 설정을 통해 애플리케이션을 제거할 수 있습니다. 

> [!WARNING]
> 시스템 앱 또는 Microsoft Store 자체는 제거할 수 없습니다.

> [!IMPORTANT]
> HoloLens 2에 여러 사용자가 있는 경우 이를 제거하려면 앱을 설치한 사용자로 로그인해야 합니다. 

### <a name="uninstall-from-the-microsoft-store"></a>Microsoft Store에서 설치 제거

**시작** 메뉴에서 Microsoft Store를 열고 제거할 애플리케이션을 찾습니다.  스토어 페이지에서 설치된 각 애플리케이션에는 **제거** 단추가 있습니다.

### <a name="uninstall-from-the-start-menu"></a>시작 메뉴에서 제거

**시작** 메뉴 또는 **모든 앱** 목록에서 앱으로 이동합니다. 선택한 상태로 유지하여 메뉴가 나타나면 **제거** 를 선택합니다.

### <a name="uninstall-from-settings"></a>설정에서 제거
**시작** 메뉴에서 **설정 -> 앱** 을 선택합니다. 목록에서 앱을 찾아 선택한 다음, **제거** 를 클릭합니다.

앱을 제거할 수 없는 경우 피드백 허브를 사용하여 [피드백](/hololens/hololens-feedback)을 제출해주세요.
