---
title: 애플리케이션 찾기, 설치 및 제거
description: Microsoft Store는 HoloLens와 작동하는 앱과 게임의 소스입니다.  홀로그램 앱을 찾고, 설치하고, 제거하는 방법에 대해 자세히 알아봅니다.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
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
ms.openlocfilehash: f7d4ddf41f02b083000c1e57f5140c38527826d7
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364414"
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
>
> - x86 = HoloLens(1세대)
> - ARM = HoloLens 2

> [!NOTE]
> 2021년 1월 12일에 다음 앱은 HoloLens 디바이스에서 지원이 종료됩니다. 디바이스의 다음 링크를 사용하여 앱의 웹 버전을 사용하는 것이 좋습니다.

| 앱        | 링크                                          |
|------------|-----------------------------------------------|
| Excel 모바일      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word 모바일       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint 모바일 | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> OneDrive 앱은 현재 HoloLens의 Azure AD 계정에 대해 지원되지 않습니다. Microsoft OneDrive PWA 앱을 다운로드하는 것이 좋습니다. [다음 단계에 따라 앱을 다운로드하세요.]

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

### <a name="install-microsoft-onedrive-pwa-app"></a>Microsoft OneDrive PWA 앱 설치

필수 조건: 사용자가 이미 HoloLens 2 디바이스를 작업 테넌트에 조인했습니다.

1. [시작] 메뉴를 열고, Edge 브라우저를 시작합니다.

    ![시작 메뉴](images/office-pwa-1.jpg)

1. HoloLens에서 [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin)으로 이동하여 회사 계정 자격 증명을 입력합니다.

    ![회사 로그인](images/office-pwa-2.jpg)

1. OneDrive 웹 포털에 성공적으로 로그인하면 PWA 다운로드 단추가 표시될 때까지 30~60초 동안 기다립니다.

    ![PWA 설치 단추](images/office-pwa-3.jpg)

1. PWA 다운로드 단추를 선택하고, 앱을 설치합니다.

    ![설치 프롬프트](images/office-pwa-4.jpg)

1. Edge 브라우저를 닫고, [시작] 메뉴에서 **모든 앱** 단추를 선택하고, **Microsoft OneDrive** 라고 레이블이 지정된 OneDrive PWA 앱을 시작합니다.

    ![두 앱을 모두 보여 주는 모든 앱](images/office-pwa-5.jpg)

    > [!NOTE]
    > "Microsoft OneDrive"는 "OneDrive"가 이전 UWP인 PWA 앱입니다.

1. 그러면 OneDrive 파일이 표시됩니다.

    ![OneDrive PWA](images/office-pwa-6.jpg)

참고 항목: [비즈니스용 OneDrive에 자동 업로드 사용](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>앱 업데이트

### <a name="manual-updates"></a>수동 업데이트

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

### <a name="automatic-app-updates"></a>자동 앱 업데이트

자동 업데이트는 Microsoft Store 또는 비즈니스용 Microsoft Store 앱에 적용되며, Store에서 직접 설치된 경우에만 자동으로 업데이트할 수 있습니다. Intune에서 설치한 경우 IT는 앱에 사용 가능한 최신 버전에 대해 비즈니스용 Microsoft Store와 동기화하여 MDM에서 업데이트를 푸시다운할 수 있습니다.

> [!NOTE]
> 비즈니스용 Microsoft Store에서 제공하는 앱의 경우 Store에 로그인하고 디바이스에서 사용되는 비즈니스용 Microsoft Store 카탈로그와 연결된 동일한 테넌트를 사용하여 인증해야 합니다.

#### <a name="how-automatic-updates-work"></a>자동 업데이트 방법

자동 앱 업데이트는 네트워크 가용성에 따라 매일(약 24시간마다) 수행하도록 예약되어 있습니다. 디바이스를 활성 상태로 유지하거나 AC에 연결하여 업데이트를 받습니다. 활성 일일 사용 중에 앱 업데이트를 다운로드하더라도 업데이트할 앱이 더 이상 사용되지 않는 경우에만 적용됩니다.

> [!TIP]
> 가능하면 디바이스를 회사 네트워크에 연결된 상태로 야간에 충전하세요. 업데이트를 야간에 다운로드하여 설치할 수 있으면 활성 디바이스의 사용을 중단할 가능성이 적습니다.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>IT 관리자가 자동 ​​업데이트를 제어하는 ​​방법

IT 관리자는 [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 정책을 통해 자동 앱 업데이트를 제어할 수 있습니다. 이 정책을 통해 자동 앱 업데이트를 완전히 사용하거나 사용하지 않도록 설정할 수 있지만 업데이트가 수행되는 시기를 제어하지는 않습니다.

[21H2](hololens-release-notes.md#windows-holographic-version-21h1)부터 IT 관리자는 [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) 정책을 사용하여 사용 중이었지만 이전 시도에서 업데이트할 수 없었던 앱을 강제로 다시 시작해야 하는 시기를 제어할 수도 있습니다.

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

**시작** 메뉴에서 **설정 > 앱** 을 차례로 선택합니다. 목록에서 앱을 찾아 선택한 다음, **제거** 를 클릭합니다.

앱을 제거할 수 없는 경우 피드백 허브를 사용하여 [피드백](/hololens/hololens-feedback)을 제출해주세요.
