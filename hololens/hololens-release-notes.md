---
title: HoloLens 2 릴리스 정보
description: 각 새 HoloLens 2 릴리스의 모든 업데이트를 최신 상태로 유지합니다.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397344"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 릴리스 정보

HoloLens 디바이스를 사용하여 생산성을 높일 수 있도록 기능, 버그 및 보안 업데이트를 계속 릴리스합니다. 이 페이지에서는 매월 HoloLens의 새로운 내용을 확인할 수 있습니다. 최신 HoloLens 2 업데이트를 얻으려면 [업데이트를 확인하고 수동으로 업데이트하거나](hololens-update-hololens.md#check-for-updates-and-manually-update) FFU(전체 플래시 업데이트)를 다운로드하여 고급 복구 도우미 를 [통해 디바이스를 플래시할 수 있습니다.](hololens-recovery.md#clean-reflash-the-device) [다운로드는](https://aka.ms/hololens2download) 최신 상태로 유지되며 일반적으로 사용 가능한 최신 빌드를 제공합니다.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic 버전 21H1
- 빌드 20346.1002

이 업데이트에는 두 대상에 대한 기능이 포함되어 있습니다. 최종 사용자가 디바이스의 모든 사용자가 사용할 수 있는 기능 및 IT 관리자가 구성할 수 있는 새 디바이스 관리 옵션입니다. 아래 표에서는 각 대상과 관련된 기능을 지정합니다. IT 관리자인 경우 IT 관리자 - [업데이트 검사 목록](#it-admin---update-checklist)을 살펴보세요.
>[!IMPORTANT]
>이 빌드로 업데이트하려면 HoloLens 2 디바이스가 현재 2021년 2월 업데이트(빌드 19041.1136) 이상에서 실행되고 있어야 합니다. 사용 가능한 이 기능 업데이트가 표시되지 않으면 먼저 디바이스를 업데이트하고 다시 시도하세요.

>[!NOTE]
>현재 Microsoft HoloLens 2는 다음 릴리스에 대한 월별 서비스 업데이트(버그 및 보안 수정)를 지원합니다.
>- Windows Holographic 버전 20H2(빌드 19041.1128 이상)
>- Windows Holographic 버전 2004(빌드 19041.1103 이상)
>- Windows Holographic 버전 1903(빌드 18362 이상) 
>
> Windows Holographic 버전 21H1이 도입되면서 **Windows Holographic 버전 1903에 대한 월간 서비스 업데이트가 중단됩니다.** 이를 통해 최신 릴리스에 집중하고 계속해서 중요한 향상된 기능을 제공할 수 있습니다. 


| 기능 이름                                              | 간단한 설명                                                                      | 대상 사용자 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [새 Microsoft Edge](#introducing-the-new-microsoft-edge)  | 이제 새로운 Chromium 기반 Microsoft Edge를 HoloLens 2에서 사용할 수 있습니다. | 최종 사용자 | 
[WebXR 및 360 뷰어](#webxr-and-360-viewer) | 몰입 형 웹 경험과 360 비디오 재생을 사용해 보세요. | 최종 사용자 | 
[새 설정 앱](#new-settings-app) | 레거시 설정 앱은 새로운 기능 및 설정으로 업데이트 된 버전으로 대체 됩니다. | 최종 사용자 |
[디스플레이 색 보정](#display-color-calibration) | HoloLens 2 디스플레이에 대 한 대체 색 프로필을 선택 합니다. | 최종 사용자 |
[기본 앱 선택기](#default-app-picker) | 각 파일 또는 링크 형식에 대해 시작할 앱을 선택 합니다. | 최종 사용자 |
[앱 당 볼륨 컨트롤](#per-app-volume-control) | 시스템 볼륨과 독립적으로 앱 수준 볼륨을 제어 합니다. | 최종 사용자 |
[웹 앱 설치](#install-web-apps) | 새 Microsoft Edge 브라우저를 사용 하 여 Microsoft Office와 같이 HoloLens 2에 웹 앱을 설치 합니다. | 최종 사용자 |
[형식으로 살짝 밀기](#swipe-to-type) | 손가락의 팁을 사용 하 여 holographic 키보드의 "살짝 밀기" 단어를 사용 합니다. | 최종 사용자 |
[시작 메뉴의 전원 메뉴](#power-menu-from-start) | 시작 메뉴에서 HoloLens 장치를 다시 시작 하 고 종료 합니다. | 최종 사용자 |
[로그인 화면에 나열 된 여러 사용자](#multiple-users-listed-on-sign-in-screen) | 로그인 화면에 여러 사용자 계정을 표시 합니다. | 최종 사용자 |
[USB-C 외부 마이크 지원](#usb-c-external-microphone-support) | 앱 및/또는 Remote Assist USB-C 마이크를 사용합니다. | 최종 사용자 |
[키오스크에 대한 방문자 자동 로그온](#visitor-auto-logon-for-kiosks) | 방문자 계정의 자동 로그온을 키오스크 모드에 사용할 수 있도록 합니다. | IT 관리자 |
[키오스크 모드의 새 앱에 대한 새 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 새 설정 및 Edge 앱에 대한 AUMID입니다. | IT 관리자 |
[키오스크 모드 오류 전달 개선](#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드는 빈 시작 메뉴 전에 전역 할당 액세스를 찾습니다. | IT 관리자 |
[페이지 설정 표시 유형에 대한 새 설정 URL](#new-settings-uris-for-page-settings-visibility) | 설정/PageVisibilityList 정책에 대한 20개 이상의 새 설정 UR입니다. | IT 관리자 |
[대체 진단 구성](#configuring-fallback-diagnostics-via-settings-app) | 설정 앱에서 대체 진단 동작 설정 | IT 관리자 |
[주변 디바이스와 사물 공유](#share-things-with-nearby-devices) | HoloLens에서 PC로 파일 또는 URL을 공유합니다. | 모두 |
[새 OS 진단 추적](#new-os-diagnostic-traces) | OS 업데이트에 대한 설정의 새 문제 해결사입니다. | IT 관리자 |
[배달 최적화 미리 보기](#delivery-optimization-preview) | 여러 HoloLens 디바이스에서 다운로드할 때 대역폭 사용량을 줄입니다. | IT 관리자 |

관련 릴리스 정보 확인:

- [HoloLens 에뮬레이터 아카이브 방문](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>새 Microsoft Edge 소개

![새 Microsoft Edge 로고에 대 한 레거시 Microsoft Edge 로고의 애니메이션](images/new-edge.gif)

새 Microsoft Edge는 [Chromium 오픈 소스 프로젝트를 채택](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 하 여 고객에 게 더 나은 호환성을 만들고 웹 개발자를 위한 웹의 조각화를 줄일 수 있습니다.

> [!IMPORTANT]
> 이 새로운 Microsoft Edge는 새 릴리스에서 [더 이상 지원 되지](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) 않는 레거시 microsoft edge를 자동으로 대체 합니다.

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>새 Microsoft Edge 시작

새로운 Microsoft Edge ![새 Microsoft Edge 아이콘](images/new_edge_logo.png) (파란색 및 녹색 소용돌이 아이콘으로 표시 됨)은 시작 메뉴에 고정 되며 웹 링크를 활성화할 때 자동으로 시작 됩니다.

> [!NOTE]
> HoloLens 2에서 처음으로 새 Microsoft Edge를 시작할 때 레거시 Microsoft Edge에서 설정 및 데이터를 가져옵니다. 새 Microsoft Edge를 시작한 후 레거시 Microsoft Edge를 계속 사용 하는 경우 새 데이터는 레거시 Microsoft Edge에서 새로운 Microsoft Edge로 동기화 되지 않습니다.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>새 Microsoft Edge에 대 한 정책 설정 구성

새 Microsoft Edge는 이전에 레거시 Microsoft Edge에서 사용할 수 있었던 것 보다 더 광범위 한 브라우저 정책 집합을 HoloLens 2에 제공 합니다.

새 Microsoft Edge의 정책 설정을 관리 하는 방법에 대 한 자세한 내용은 다음 리소스를 참조 하세요.

- [Microsoft Intune를 사용 하 여 Microsoft Edge 정책 설정 구성](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft edge 레거시에서 Microsoft Edge 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome에서 Microsoft Edge 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 전체 [Microsoft Edge Enterprise 설명서](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 새 Microsoft Edge에서 지원 되는 브라우저 정책의 양에 따라 팀은 각 새 정책이 HoloLens 2에서 작동 하도록 보장할 수 없습니다. 그러나 이전에는 HoloLens 2에서 지원 되는 각 레거시 Microsoft Edge 정책에 해당 하는 새 Microsoft edge 정책이 예상 대로 작동 하는지 테스트 하 고 확인 했습니다. HoloLens 2에서 사용 하는 각 레거시 Microsoft Edge 브라우저 정책에 해당 하는 새 Microsoft edge를 찾으려면 microsoft [Edge Legacy To Microsoft edge 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 을 참조 하세요.
>
> HoloLens 2 작동하지 *않을 것으로* 알고 있는 두 개 이상의 새 Microsoft Edge 정책이 있습니다.
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 새 Microsoft Edge 예상되는 내용

새 Microsoft Edge HoloLens 2 같은 UWP 전용 디바이스에서 실행할 수 있는 새 UWP 어댑터 계층이 있는 네이티브 Win32 앱이므로 일부 기능을 즉시 사용할 수 없습니다. 앞으로 몇 개월 동안 새로운 시나리오와 기능을 지원할 예정이므로 이 공간에서 최신 정보를 확인하세요.

**작동할 것으로 예상되는 시나리오 및 기능:**
- 첫 실행 환경, 프로필에 로그인 및 동기화
- 웹 사이트는 예상대로 렌더링되고 동작해야 합니다.
- 대부분의 브라우저 기능(즐겨찾기, 기록 등)은 예상대로 작동해야 합니다.
- 어둡게 모드
- 디바이스에 웹앱 설치
- 확장 설치(HoloLens 2 제대로 작동하지 않는 확장을 사용하는 경우 알려주세요.)
- PDF 보기 및 표시
- 단일 브라우저 창의 공간 소리
- 브라우저 자동 및 수동 업데이트
- 인쇄 메뉴에서 PDF 저장("PDF에 저장" 옵션 사용)
- WebXR 및 360 뷰어 확장
- 환경에 배치된 여러 창을 탐색할 때 올바른 창으로 콘텐츠 복원

**시나리오 및 기능이 작동하지 않을 것으로 예상됩니다.**
- 동시 오디오 스트림이 있는 여러 창의 공간 소리
- "이 항목을 참조 하세요."
- 인쇄

**주요 브라우저의 알려진 문제:**

- Holographic 키보드의 돋보기 미리 보기가 새 Microsoft Edge에 대해 사용 하지 않도록 설정 되었습니다. 확대를 올바르게 수행 하 고 나면 향후 업데이트에서이 기능을 다시 사용 하는 것이 좋습니다.
- 다른 브라우저 창이 열려 있고 활성 상태인 경우 잘못 된 브라우저 창에서 오디오를 재생할 수 있습니다. 오디오를 재생할 수 없는 다른 활성 창을 닫으면이 문제를 해결할 수 있습니다.
- "사용자가 [팔 로우" 모드](hololens2-basic-usage.md#follow-me-stop-following)의 브라우저 창에서 오디오를 재생 하는 경우 "사용자 팔 로우" 모드를 사용 하지 않도록 설정 하면 오디오가 계속 재생 됩니다. "나 팔 로우" 모드를 사용 하지 않도록 설정 하기 전에 오디오 재생을 중지 하거나 **X** 단추를 사용 하 여 창을 닫으면이 문제를 해결할 수 있습니다.
- 활성 Microsoft Edge 창과의 상호 작용으로 인해 다른 2D 앱 창이 예기치 않게 비활성화 될 수 있습니다. 이러한 창은 다시 상호 작용 하 여 다시 활성화할 수 있습니다.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider 채널

Microsoft Edge 팀은 Edge Insider community에서 사용할 수 있는 세 가지 미리 보기 채널 (베타, 개발 및 카나리아)을 만듭니다. 미리 보기 채널을 설치 하면 HoloLens 2에서 릴리스된 버전의 Microsoft Edge가 제거 되지 않으며, 동시에 둘 이상을 설치할 수 있습니다. 

[Microsoft Edge insider 홈 페이지](https://www.microsoftedgeinsider.com) 를 방문 하 여 edge insider community에 대해 자세히 알아보세요. 다른 Edge Insider 채널에 대 한 자세한 내용을 알아보고 시작 하려면 [Edge 참가자 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문 하세요.

HoloLens 2에 Microsoft Edge Insider 채널을 설치 하는 데 사용할 수 있는 몇 가지 방법이 있습니다.

**장치에 직접 설치 (현재는 관리 되지 않는 장치 에서만 사용 가능)**
  1. HoloLens 2에서 [Edge 참가자 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문 합니다.
  1. 설치 하려는 Edge Insider channel에 대해 **HoloLens 다운로드 2** 단추를 선택 합니다.
  1. Edge 다운로드 큐 또는 장치의 "다운로드" 폴더 (파일 탐색기 사용)에서 다운로드 한 msix 파일을 시작 합니다.
  1. [앱 설치 관리자가](app-deploy-app-installer.md) 시작됩니다.
  1. **설치** 단추를 선택합니다.
  1. 설치에 성공하면 시작 메뉴 모든 앱 **목록에서** Microsoft Edge Beta, Dev 또는 카나리아를 별도의 항목으로 찾을 수 있습니다.

**Windows 장치 포털 PC를 통해 설치(HoloLens 2 [개발자 모드를](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 사용하도록 설정해야 합니다.)**
  1. PC에서 [Edge 참가자 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문합니다.
  1. 설치하려는 Edge 참가자 채널의 "Windows 10 다운로드" 단추 옆에 있는 **드롭다운 화살표 단추를** 선택합니다.
  1. 드롭다운 메뉴에서 **HoloLens 2** 선택합니다.
  1. .msix 파일을 PC의 "다운로드" 폴더(또는 쉽게 찾을 수 있는 다른 폴더)에 저장합니다.
  1. PC에서 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 사용하여 다운로드한 .msix 파일을 HoloLens 2 설치합니다.
  1. 설치에 성공하면 시작 메뉴 모든 앱 **목록에서** Microsoft Edge Beta, Dev 또는 카나리아를 별도의 항목으로 찾을 수 있습니다.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC를 사용하여 새 Microsoft Edge 차단

새 Microsoft Edge 앱을 차단하도록 [WDAC 정책을](windows-defender-application-control-wdac.md) 업데이트하려는 IT 관리자의 경우 정책에 다음을 추가해야 합니다.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>새 Microsoft Edge 대한 엔드포인트 관리

일부 환경에서는 고려해야 할 네트워크 제한이 있을 수 있습니다. 새 Edge를 사용하여 원활한 환경을 보장하려면 [이러한 Microsoft 엔드포인트를 사용하도록 설정하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

HoloLens에 대해 현재 사용 가능한 [엔드포인트에 대해 자세히 읽어보십시오.](hololens-offline.md)

### <a name="install-web-apps"></a>웹앱 설치
 > [!Note]
>Windows [Holographic 버전 21H1에서는](hololens-release-notes.md#windows-holographic-version-21h1)Office 웹앱이 더 이상 사전 설치되지 않습니다.

새 Edge를 사용하여 Microsoft Store 앱과 함께 웹앱을 설치할 수 있습니다. 예를 들어 Microsoft Office 웹앱을 설치하여 SharePoint 또는 OneDrive에서 호스트되는 파일을 보고 편집할 수 있습니다. Office 웹앱을 설치하려면 를 방문하여 https://www.office.com 주소 표시줄에서 **사용 가능한 앱** 또는 Office **설치** 단추를 선택합니다. **설치** 를 선택 하 여 확인 합니다.

> [!IMPORTANT]
> Office 웹 앱 기능은 HoloLens 2에 활성 인터넷 연결이 있는 경우에만 사용할 수 있습니다.

### <a name="webxr-and-360-viewer"></a>WebXR 및 360 뷰어

새 Microsoft Edge에는 몰입 형 웹 환경을 만들기 위한 새로운 표준 인 WebXR에 대 한 지원이 포함 되어 있습니다 (WebVR 대체). 대부분의 몰입 형 웹 환경은 VR를 염두에 두어야 설계 되었지만 (이는 보기의 필드를 가상 환경으로 대체), 이러한 환경은 HoloLens 2 에서도 지원 됩니다. WebXR standard를 사용 하면 물리적 환경을 사용 하는 확장 및 혼합 현실 몰입 형 웹 환경을 사용할 수도 있습니다. 개발자가 WebXR를 사용 하 여 더 많은 시간을 투자 하 게 되 면 새로운 확장 및 혼합 현실 경험을 위해 HoloLens 2 고객에 게 제공 될 것으로 예상 됩니다!

360 뷰어 확장은 WebXR를 기반으로 하며, HoloLens 2의 새로운 Microsoft Edge와 함께 자동으로 설치 됩니다. 이 웹 확장은 360 수준 비디오에서 직접 컨퍼런스 수 있는 기능을 제공 합니다. YouTube는 가장 광범위 한 360 비디오를 제공 하므로 시작 하는 것이 좋습니다.

#### <a name="how-to-use-webxr"></a>WebXR 사용 방법

1. WebXR가 지원 되는 웹 사이트로 이동 합니다.
1. 웹 사이트에서 **VR 입력** 단추를 선택 합니다. 이 단추의 위치 및 시각적 표현은 웹 사이트별로 다를 수 있지만 다음과 유사할 수 있습니다.

    ![VR 단추 입력 예](images/75px-enter-vr.png)

1. 특정 도메인에서 WebXR 환경을 처음 시작 하는 경우 브라우저는 몰입 형 보기 입력에 대 한 동의를 요청 하 고 **허용** 을 선택 합니다.
1. [HoloLens 2 제스처](hololens2-basic-usage.md#the-hand-tracking-frame) 를 사용 하 여 환경을 조작할 수 있습니다.
1. 환경에 **종료** 단추가 없으면 [시작 제스처](hololens2-basic-usage.md#start-gesture) 를 사용 하 여 home을 반환 합니다.

**권장 WebXR 샘플**
- 360 뷰어 (다음 섹션 참조)
- [XR 공룡](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 그리기](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 뷰어를 사용하는 방법

1. YouTube에서 360도 비디오로 이동합니다.
1. 비디오 프레임에서 혼합 현실 헤드셋 단추를 선택합니다.

    ![360 뷰어를 활성화하는 단추](images/enter-360-viewer.jpg)

1. 특정 도메인에서 360 뷰어를 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하기 위한 동의를 요청합니다. **허용을** 선택합니다.
1. [재생](hololens2-basic-usage.md#select-using-air-tap) 컨트롤을 불러 오도록 에어 탭합니다. [손 광선 및 에어 탭을](hololens2-basic-usage.md#select-using-air-tap) 사용하여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 켜기/끄기 또는 몰입형 보기를 종료하는 환경을 중지합니다. 재생 컨트롤은 몇 초 동안 비활성 후에 사라집니다.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>상위 WebXR 및 360 뷰어 알려진 문제
- WebXR 환경의 복잡성에 따라 프레임 속도는 떨어지거나 끊어질 수 있습니다.
- WebXR에서 연속된 손 조인트 지원은 기본적으로 사용하도록 설정되지 않습니다. 개발자는 `edge://flags` "WebXR 손 입력"을 켜면 을 통해 지원을 사용하도록 설정할 수 있습니다.
- YouTube 이외의 웹 사이트의 비디오 360개는 예상대로 작동하지 않을 수 있습니다.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR 및 360 뷰어에 대한 피드백 제공

새 Microsoft Edge 피드백 **보내기** 기능을 통해 피드백 및 버그를 팀과 공유하세요.

### <a name="new-settings-app"></a>새 설정 앱

이 릴리스에서는 새 버전의 설정 앱을 소개 합니다. 새 설정 앱에는 사운드, 전원 & 절전, 네트워크 & 인터넷, 앱, 계정, 액세스 편의성 등의 영역에서 HoloLens 2에 대 한 새로운 기능 및 확장 된 설정이 포함 되어 있습니다.

> [!NOTE]
> 새 설정 앱은 레거시 설정 앱과 다르기 때문에 이전에 환경 주위에 배치한 모든 설정 창은 업데이트 시 제거 됩니다.

![새 설정 앱 홈페이지](images/new-settings-app.png)

**새 기능 및 설정**
- 설정 검색: 키워드 또는 설정 이름을 사용 하 여 설정 홈페이지에서 설정을 검색 합니다.
- 시스템 > 소리:
  - 입력 및 출력 오디오 장치: 입력 및 출력 오디오 장치를 독립적으로 선택 합니다. 예를 들어 Bluetooth 헤드폰을 통해 오디오를 수신 하거나 오디오 입력에 USB-C 마이크를 사용 합니다.
    > [!NOTE]
    > Bluetooth 마이크는 HoloLens 2에서 지원 되지 않습니다.
  - 앱 볼륨: 각 앱의 볼륨을 독립적으로 조정 합니다. [앱 당 볼륨 제어](#per-app-volume-control)를 참조 하세요.
- 시스템 > 전원 & 절전 모드: 비활성 기간 후 장치가 절전 모드로 전환 해야 하는 경우를 선택 합니다.
- 시스템 > 배터리: 배터리 절약 모드를 수동으로 사용 하도록 설정 하거나 배터리 절약 모드가 자동으로 설정 되는 배터리 임계값을 설정 합니다.
- 장치 > USB: 기본적으로 USB 연결을 사용 하지 않도록 설정할 수 있습니다.
- 네트워크 & 인터넷:
  - 이제 USB-C 이더넷 어댑터가 네트워크 & 인터넷에 표시 됩니다.
  - 이제 IP 주소를 포함 하 여 USB C 이더넷 어댑터 설정을 사용할 수 있습니다.
  - 이제 HoloLens 2에서 비행기 모드를 사용 하도록 설정할 수 있습니다.
- 앱: 파일 및 링크 형식에 사용 되는 기본 앱을 다시 설정할 수 있습니다. 자세한 내용은 [기본 앱 선택](#default-app-picker)을 참조 하세요.
- 계정 > 기타 사용자: 디바이스 소유자는 사용자를 추가하고, 표준 사용자를 디바이스 소유자로 업그레이드하고, 디바이스 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.
- 접근성: 텍스트 크기 및 일부 시각적 효과를 변경합니다.

**알려진 문제**
- 이전에 배치된 설정 창이 제거됩니다(위의 참고 참조).
- 설정 앱을 사용하면 더 이상 디바이스 이름을 바꿀 수 없습니다. IT 관리자는 HoloLens 2 디바이스 이름 [템플릿에 대한 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 또는 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 노드를 사용하여 디바이스 이름을 바꿀 수 있습니다.
- 이더넷 페이지에는 항상 가상 이더넷 디바이스("UsbNcm")가 표시됩니다.
- UWP 어댑터 계층에서 지원하는 Win32 데스크톱 애플리케이션의 특성으로 인해 새 Microsoft Edge 배터리 사용이 정확하지 않을 수 있습니다(곧 수정될 예정임).

#### <a name="display-color-calibration"></a>색 보정 표시



이 새 설정을 사용하면 HoloLens 2 표시할 대체 색 프로필을 선택할 수 있습니다. 이렇게 하면 특히 낮은 디스플레이 밝기 수준에서 색이 더 정확하게 표시되는 데 도움이 될 수 있습니다. 디스플레이 색 보정은 설정 앱의 시스템 > 보정 페이지에서 찾을 수 있습니다.

> [!NOTE]
> 이 설정은 디스플레이 펌웨어에 새 색 프로필을 저장하기 때문에 디바이스별 설정이며 각 사용자 계정에 고유하지 않습니다.

##### <a name="how-to-use-display-color-calibration"></a>디스플레이 색 보정을 사용하는 방법

1. **설정** 앱을 시작하고 **시스템 > 보정으로** 이동합니다.
1. **색 보정 표시** 아래에서 디스플레이 색 **보정 실행** 단추를 선택합니다.
1. 디스플레이 색 보정 환경이 시작되고 바이저가 올바른 위치에 있는지 확인하는 것이 좋습니다.
1. 명령 대화 상자를 진행하면 디스플레이가 자동으로 30% 밝기로 흐리게 표시됩니다.
    > [!TIP]
    > 환경에서 흐리게 표시된 장면을 보는 데 문제가 있는 경우 디바이스 왼쪽에 있는 밝기 단추를 사용하여 HoloLens 2 밝기 수준을 수동으로 조정할 수 있습니다.
1. 단추 1-6을 선택 하 여 각 색 프로필을 즉시 사용해 보고, 눈에 잘 맞는를 찾습니다 .이는 일반적으로 장면을 가장 많이 사용 하는 프로필을 의미 하 고 회색조 패턴 및 스킨 톤을 예상 대로 표시 합니다.

    ![색 보정 장면 표시](images/color-cal-ui.png)
    
1. 선택한 프로필에 만족 하는 경우 **저장 & 끝내기** 단추를 선택 합니다.
1. 변경 하지 않으려는 경우 **취소 & 끝내기** 단추를 선택 하면 변경 내용이 되돌려집니다.

> [!TIP]
> 다음은 디스플레이 색 보정 설정을 사용 하는 동안 염두에 두어야 하는 몇 가지 유용한 팁입니다.
> - 원하는 경우 언제 든 지 설정에서 표시 색 보정을 다시 실행할 수 있습니다.
> - 장치의 모든 사용자가 이전에이 설정을 사용 하 여 색 프로필을 변경한 경우 가장 최근의 변경 내용에 대 한 날짜/시간이 설정 페이지에 반영 됩니다.
> - 표시 색 보정을 다시 실행 하면 이전에 저장 된 색 프로필이 강조 표시 되 고 프로필 0은 표시 되지 않습니다 (프로필 0은 표시의 원래 색 프로필을 나타냄).
> - 디스플레이의 원래 색 프로필로 되돌리려면 설정 페이지에서이 작업을 수행할 수 있습니다 ( [색 프로필을 다시 설정 하는 방법](#how-to-reset-color-profile)참조).

##### <a name="how-to-reset-color-profile"></a>색 프로필을 다시 설정 하는 방법 

HoloLens 2에 저장 된 사용자 지정 색 프로필을 만족 하지 않는 경우 장치의 원래 색 프로필을 복원할 수 있습니다.
1. **설정** 앱을 시작 하 고 **시스템 > 보정** 으로 이동 합니다.
1. **디스플레이 색 보정** 에서 **기본 색 프로필로 다시 설정** 단추를 선택 합니다.
1. 대화 상자가 열리면 HoloLens 2를 다시 시작 하 고 변경 내용을 적용할 준비가 되 면 **다시 시작** 을 선택 합니다.

#### <a name="top-display-color-calibration-known-issues"></a>위쪽 디스플레이 색 보정 알려진 문제

- 설정 페이지에서 색 프로필이 마지막으로 변경 된 시기를 알려 주는 상태 문자열은 설정의 해당 페이지를 다시 로드할 때까지 만료 됩니다.
    - 해결 방법: 다른 설정 페이지를 선택한 다음 보정 페이지를 다시 선택 합니다.

#### <a name="default-app-picker"></a>기본 앱 선택기

하이퍼링크를 활성화하거나 앱을 지원하는 앱을 두 개 이상 설치한 파일 형식을 열면 파일 또는 링크 형식을 처리할 설치된 앱을 선택하라는 새 창이 열립니다. 이 창에서 선택한 앱이 파일을 처리하도록 선택하거나 "Once" 또는 "Always" 링크 형식을 선택할 수도 있습니다.

"항상"을 선택하지만 나중에 특정 파일 또는 링크 형식을 처리하는 앱을 변경하려는 경우 **설정 > 앱에서** 저장된 기본값을 다시 설정할 수 있습니다. 페이지 아래쪽으로 스크롤하여 "파일 형식에 대한 기본 앱" 및/또는 "링크 형식의 기본 앱" 아래에서 **지우기** 단추를 선택합니다. 데스크톱 PC에서 유사한 설정과 달리 개별 파일 형식 기본값을 다시 설정할 수 없습니다.

#### <a name="per-app-volume-control"></a>앱별 볼륨 제어

이제 이 Windows 빌드에서 사용자는 각 앱의 볼륨 수준을 수동으로 조정할 수 있습니다. 이렇게 하면 사용자가 필요한 앱에 더 잘 집중하거나 여러 앱을 사용할 때 더 잘 듣고 있을 수 있습니다. 예를 들어 다른 사람에게 원격 지원을 요청하는 동안 한 앱의 볼륨을 낮추어야 합니다.

개별 앱의 볼륨을 설정하려면 **설정** 시스템 소리 로 이동하고  ->    ->  고급 소리 옵션에서 앱 볼륨 및 디바이스 **기본 설정을** 선택합니다.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>형식으로 살짝 밀기

일부 고객은 입력하려는 단어의 모양을 살짝 밀어 가상 키보드에서 "입력"하는 것이 더 빠르며 홀로그램 키보드에 대해 이 기능을 미리 봅니다. 홀로그램 키보드의 평면을 통해 손가락 끝을 전달하고 단어 모양을 살짝 밀고 키보드 평면에서 손가락 끝을 빼서 한 번에 한 단어를 살짝 밀 수 있습니다. 단어 사이에 있는 키보드에서 손가락을 제거하여 스페이스바를 누르지 않고도 후속 단어를 살짝 밀 수 있습니다. 키보드에서 손가락의 움직임을 따라 살짝 밀기 내역이 표시되면 기능이 작동하는 것을 알 수 있습니다.

이 기능을 사용 하는 것은 holographic 키보드의 특성으로 인해 손가락에 대해 저항 하지 않는 (휴대폰 디스플레이와 달리) 사용 하기 어려울 수 있습니다. 

### <a name="power-menu-from-start"></a>시작 메뉴의 전원 메뉴

사용자가 로그 아웃 하 고 장치를 종료 하 고 다시 시작할 수 있도록 하는 새 메뉴입니다. 시스템 업데이트를 사용할 수 있는 시기를 표시 하는 HoloLens 시작 화면에 표시 되는 표시기입니다.

#### <a name="how-to-use"></a>사용 방법

1. [시작 제스처](hololens2-basic-usage.md#start-gesture) 를 사용 하 여 HoloLens 시작 화면을 열거나 "시작으로 이동"을 말합니다.

2. 사용자 프로필 그림 옆에 있는 줄임표 아이콘 (...)을 확인 합니다.

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 손으로 나 음성 명령 "Power"를 사용 하 여 사용자 프로필 그림을 선택 합니다.

4. 로그 아웃 하 고 장치를 다시 시작 하거나 종료 하는 옵션이 포함 된 메뉴가 나타납니다.

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 메뉴 옵션을 선택 하 여 로그 아웃 하 고 HoloLens를 다시 시작 하거나 종료 합니다. 장치가 [단일 Microsoft 계정 (MSA) 또는 로컬 계정](hololens-identity.md)에 대해 설정 된 경우 로그 아웃 옵션을 사용 하지 못할 수 있습니다.

6. 다른 위치에 접촉 하거나 시작 제스처를 사용 하 여 시작 메뉴를 닫아 메뉴를 닫습니다.

#### <a name="update-indicator"></a>업데이트 표시기

업데이트를 사용할 수 있는 경우 줄임표 아이콘이 표시 됩니다. 그러면 다시 시작 시 업데이트를 설치 하면 업데이트의 존재 여부를 반영 하도록 메뉴 옵션도 변경 됩니다.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>로그인 화면에 나열 된 여러 사용자

이전에는 로그인 화면에는 가장 최근에 로그인 한 사용자와 ' 기타 사용자 ' 진입점이 표시 되었습니다. 여러 사용자가 장치에 로그인 한 경우 충분 하지 않은 고객 의견을 받았습니다. 사용자 이름을 다시 입력 해야 합니다.

이 Windows 빌드에서 도입 된 PIN 입력 필드의 오른쪽에 있는 **다른 사용자** 를 선택할 때 로그인 화면에는 이전에 장치에 로그인 한 여러 사용자가 표시 됩니다. 그러면 사용자가 자신의 사용자 프로필을 선택 하 고 해당 Windows Hello 자격 증명을 사용 하 여 로그인 할 수 있습니다. **계정 추가** 단추를 통해 다른 사용자 페이지에서 장치에 새 사용자를 추가할 수도 있습니다.

다른 사용자 메뉴에서 다른 사용자 단추가 디바이스에 마지막으로 로그인한 사용자를 표시합니다. 이 사용자의 로그인 화면으로 돌아가려면 이 단추를 선택합니다.

![로그인 화면 기본값](./images/multiusers1.jpg)

<br>

![로그인 화면 다른 사용자](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 외부 마이크 지원

> [!IMPORTANT]
> **USB 마이크에 연결해도 입력 디바이스 로 자동 설정되지는 않습니다.** USB-C 레그 세트를 연결할 때 사용자는 액세서리의 오디오가 자동으로 나머지로 리디렉션되지만 HoloLens OS는 다른 입력 디바이스보다 내부 마이크 배열의 우선 순위를 지정합니다. **USB-C 마이크를 사용하려면 다음 단계를 수행합니다.**

사용자는 **소리** 설정 패널을 사용하여 USB-C 연결된 외부 마이크를 선택할 수 있습니다. USB-C 마이크는 통화, 녹음 등에 사용할 수 있습니다.

**설정** 앱을 열고 **시스템**  >  **소리** 를 선택합니다.

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> **Remote Assist** 외부 마이크를 사용하려면 사용자가 "사운드 디바이스 관리" 하이퍼링크를 클릭해야 합니다.
>
> 그런 다음, 드롭다운을 사용하여 외부 마이크를 기본값 또는 통신 **기본값으로** **설정합니다.** **기본값을** 선택하면 외부 마이크가 어디서나 사용됩니다.
>
> 통신 **기본값을** 선택하면 외부 마이크가 Remote Assist 및 기타 통신 앱에서 사용되지만 HoloLens 마이크 배열을 다른 작업에 계속 사용할 수 있습니다.

![사운드 디바이스 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth 마이크 지원은 어떤가요?

아쉽게도 Bluetooth 마이크는 현재 HoloLens 2 지원되지 않습니다.

#### <a name="troubleshooting-usb-c-microphones"></a>USB 문제 해결-C 마이크

일부 USB-C 마이크는 마이크 *와* 스피커로 잘못 보고 합니다. 이는 마이크와 관련 된 문제 이며 HoloLens와는 관련 되지 않습니다. 이러한 마이크 중 하나를 HoloLens에 꽂으면 소리가 손실 될 수 있습니다. 다행히 간단한 해결 방법이 있습니다.  

**설정**  ->  **시스템**  ->  **소리** 에서 기본 제공 스피커 **(아날로그 기능 오디오 드라이버)** 를 **기본 장치로** 명시적으로 설정 합니다. HoloLens는 마이크가 제거 되 고 나중에 다시 연결 된 경우에도이 설정을 명심 해야 합니다.

![USB 문제 해결-C 마이크](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>키오스크에 대 한 방문자 자동 로그온

이 새로운 기능을 통해 방문자 계정에 대 한 자동 로그온을 키오스크 모드에 사용할 수 있습니다.

AAD가 아닌 구성의 경우 방문자 자동 로그온을 위해 장치를 구성 하려면 다음을 수행 합니다.

1. 다음을 수행 하는 프로 비전 패키지를 만듭니다.
    1. 방문자 계정을 허용 하도록 **런타임 설정/AssignedAccess** 를 구성 합니다.
    1. 필요에 따라 MDM **(런타임 설정/작업 공간/등록)** 에 장치를 등록 하 여 나중에 관리할 수 있도록 합니다.
    1. 로컬 계정 만들기 안 함
1. [프로 비전 패키지를 적용](hololens-provisioning.md)합니다.

AAD 구성의 경우 사용자가이 변경 없이 현재 이와 유사한 항목을 달성할 수 있습니다. 키오스크 모드에 대해 구성 된 AAD 조인 장치는 로그인 화면에서 단일 단추 탭을 사용 하 여 방문자 계정에 로그인 할 수 있습니다. 방문자 계정에 로그인 한 후에는 방문자가 시작 메뉴에서 명시적으로 로그 아웃 하거나 장치를 다시 시작할 때까지 장치에서 다시 로그인 하 라는 메시지를 표시 하지 않습니다.

방문자 자동 로그온은 [사용자 지정 OMA URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 정책을 통해 관리할 수 있습니다.

- URI 값: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 정책  | 설명   | 구성  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 방문자가 키오스크에 자동으로 로그온하도록 허용   | 1(예), 0(아니요, 기본값)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>키오스크 모드에서 새 설정 및 Edge 앱 사용

[키오스크에](hololens-kiosk.md)앱을 포함하는 경우 IT 관리자는 종종 앱을 키오스크에 추가하지만 AUMID(앱 사용자 모델 ID)를 사용하는 경우가 많습니다. 설정 앱과 Microsoft Edge 앱은 모두 새 앱으로 간주되고 해당 앱에 AUMID를 사용하는 이전 앱 키오스크와 다르기 때문에 새 AUMID를 사용하도록 업데이트해야 합니다.

새 앱을 포함하도록 키오스크를 수정하는 경우 새 AUMID에 추가하고 이전 앱을 그대로 두는 것이 좋습니다. 이렇게 하면 사용자가 OS를 업데이트할 때 쉽게 전환할 수 있으며, 의도한 대로 키오스크를 계속 사용하기 위해 새 정책을 받을 필요가 없습니다.

| 앱                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 이전 설정 앱       | HolographicSystemSettings_cw5n1h2txyewy! 앱            |
| 새 설정 앱       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 앱 |
| 이전 Microsoft Edge 앱 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| 새 Microsoft Edge 앱 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리를 위한 키오스크 모드 동작 변경

이전 빌드에서 디바이스에 전역 할당 액세스 및 AAD 그룹 구성원 할당 액세스의 조합인 키오스크 구성이 있는 경우 AAD 그룹 멤버 자격을 결정하지 못한 경우 사용자에게 시작 "[메뉴에 "아무 것도 표시되지 않습니다."](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)가 표시됩니다.

이 Windows 릴리스부터는 AAD 그룹 키오스크 모드에서 오류가 발생 하는 경우 키오스크 환경이 전역 키오스크 구성 (있는 경우)으로 대체 됩니다.

### <a name="new-settings-uris-for-page-settings-visibility"></a>페이지 설정 표시 유형에 대 한 새 설정 Uri

[Windows Holographic 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 에서는 설정 앱 내에 표시 되는 페이지를 제한 하는 [settings/PageVisibilityList 정책을](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 추가 했습니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스할 수 없도록 하거나 지정 된 페이지를 제외한 모든 페이지에 대해이 작업을 수행 하는 데 사용할 수 있는 정책입니다.

[페이지 설정 표시 유형을](settings-uri-list.md)방문 하는 경우이 CSP와 이전 버전에서 사용할 수 있는 uri 목록을 사용할 수 있는 지침을 찾을 수 있습니다.

IT 관리자가 관리할 수 있는 사용 가능한 설정 Uri 목록으로 확장 하 고 있습니다. 이러한 Uri 중 일부는 새 설정 앱 내에서 새로 사용할 수 있는 영역에 대 한 것입니다. Settings/PageVisibilityList policy를 사용 하는 경우 다음 목록을 검토 하 고 필요에 따라 허용 또는 차단 된 페이지를 조정 합니다.

> [!NOTE]
> **사용 되지 않음: ms 설정: 네트워크-프록시**
>
> 이러한 최신 빌드에서는 한 설정 페이지가 더 이상 사용 되지 않습니다. 이전 **네트워크 & 인터넷**  >  **프록시** 페이지는 더 이상 전역 설정으로 사용할 수 없습니다. 새 연결 당 프록시 설정은 **네트워크 & internet**  >  **wi-fi**  >  **속성** 또는 **네트워크 & 인터넷**  >  **이더넷**  >  **속성** 에서 찾을 수 있습니다.

<br>

| 설정 페이지                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 앱 > 앱 & 기능                               | `ms-settings:appsfeatures`                         |
| 앱 > 앱 & 기능 > 고급 옵션          | `ms-settings:appsfeatures-app`                     |
| 앱 > 오프 라인 맵                                  | `ms-settings:maps`                                 |
| 앱 > 오프 라인 maps > 지도 다운로드                  | `ms-settings:maps-downloadmaps`                    |
| 마우스 > 장치                                      | `ms-settings:mouse`                                |
| USB > 장치                                        | `ms-settings:usb`                                  |
| 네트워크 & 인터넷 > 비행기 모드                   | `ms-settings:network-airplanemode`                 |
| 개인 정보 > 일반                                    | `ms-settings:privacy-general`                      |
| 개인 설정 입력 & 개인 정보 > 잉크             | `ms-settings:privacy-speechtyping`                 |
| 개인 정보 보호 > 동작                                     | `ms-settings:privacy-motion`                       |
| 개인 정보 > 스크린샷 테두리                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 개인 정보 > 스크린샷 및 앱                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 시스템 > 배터리                                     | `ms-settings:batterysaver`                         |
| 시스템 > 배터리                                     | `ms-settings:batterysaver-settings`                |
| 시스템 > 소리                                       | `ms-settings:sound`                                |
| 시스템 > 소리 > 앱 볼륨 및 디바이스 기본 설정 | `ms-settings:apps-volume`                          |
| 시스템 > 소리 > 사운드 디바이스 관리              | `ms-settings:sound-devices`                        |
| System > Storage > 구성 저장 공간 센스         | `ms-settings:storagepolicies`                      |
| 시간 & 언어 > 날짜 & 시간                        | `ms-settings:dateandtime`                          |
| 시간 & 언어 > 키보드                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| 업데이트 & 보안 > 다시 설정 & 복구               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>업데이트된 URI

이전에는 다음 두 URI가 사용자를 표시된 페이지로 직접 가져가지 않고 주 업데이트 페이지만 차단했습니다. 다음 항목이 해당 페이지로 직접 업데이트되었습니다.

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>설정 앱을 통해 대체 진단 구성

이제 설정 앱에서 사용자가 대체 진단 의 동작을 구성할 수 [있습니다.](hololens-diagnostic-logs.md) 설정 앱에서 **개인 정보**  ->  **문제 해결** 페이지로 이동 하 여이 설정을 구성 합니다.

> [!NOTE]
> 장치에 대해 구성 된 MDM 정책이 있으면 사용자가 해당 동작을 재정의할 수 없습니다.  

### <a name="share-things-with-nearby-devices"></a>주변 장치와 항목 공유

Pc와 기타 HoloLens 2 장치를 포함 하 여 Windows 10 장치 근처와 사물을 공유 합니다. **설정** 시스템 공유 환경에서 사용해 볼 수 있으며  ->    ->   HoloLens의 파일 또는 url을 PC로 공유할 수 있습니다. 자세한 내용은 [Windows 10에서 주변 장치와 항목을 공유](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)하는 방법을 참조 하세요.

이 기능은 [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)를 통해 관리할 수 있습니다.

### <a name="new-os-diagnostic-traces"></a>새 OS 진단 추적

설정 앱 내에서 이전 문제 해결사 외에도 새 설정 앱이 OS 업데이트용 새 설정 앱과 함께 추가 되었습니다. **설정**  ->  **업데이트 &amp; 보안**  >  **문제 해결**  >  **Windows 업데이트** 로 이동 하 고 **시작** 을 선택 합니다. 이렇게 하면 OS 업데이트에 대 한 문제를 재현 하는 동안 추적을 수집 하 여 IT 또는 지원과 관련 된 문제 해결에 더 효과적으로 지원할 수 있습니다.

### <a name="delivery-optimization-preview"></a>배달 최적화 미리 보기

이 HoloLens 업데이트를 사용 하면 Windows Holographic for Business에서 배달 최적화 설정을 사용 하 여 여러 HoloLens 장치에서 다운로드에 대 한 대역폭 사용량을 줄일 수 있습니다. 권장 되는 네트워크 구성과 함께이 기능에 대 [한 자세한 설명은 Windows 10 업데이트에 대 한 배달 최적화](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)에서 제공 됩니다.

다음 설정은 관리 화면의 일부로 사용 하도록 설정 되며 [Intune에서 구성할 수 있습니다](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings).

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

이 미리 보기 제품에 대한 몇 가지 주의 사항은 다음과 같습니다.

- HoloLens 지원은 이 미리 보기에서 OS 업데이트로만 제한됩니다.
- Windows Holographic for Business [Microsoft 연결된 캐시 엔드포인트에서](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)HTTP 다운로드 모드 및 다운로드만 지원합니다. 피어 투 피어 다운로드 모드 및 그룹 할당은 현재 HoloLens 디바이스에 대해 지원되지 않습니다.
- HoloLens는 Windows Server Update Services 엔드포인트에 대한 배포 또는 배달 최적화를 지원하지 않습니다.
- 문제 해결에는 연결된 캐시 서버에서 진단하거나 **설정** 업데이트 & 보안 문제 해결 Windows 업데이트 통해 HoloLens의 HoloLens에서 추적을 수집해야  >    >     >   합니다.

### <a name="it-admin---update-checklist"></a>IT 관리자 - 업데이트 검사 목록

이 검사 목록은 현재 디바이스 관리 구성에 영향을 줄 수 있는 이 기능 업데이트에 추가되는 기능 또는 사용하려는 새 기능을 파악하는 데 도움이 됩니다.

#### <a name="updates-to-kiosk-mode"></a>키오스크 모드 업데이트

[**키오스크 모드에서 새 앱에 대한 새 AUMID를**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️.

이전에 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용한 경우 이러한 앱을 다른 앱 ID를 사용하는 새 앱으로 대체했습니다. 아래 [키오스크 모드에서 새 앱에 대한 새 AUMID를](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 읽어보는 것이 좋습니다. 이렇게 하면 키오스크에 설정 앱을 계속 포함하거나 새 Microsoft Edge 앱을 포함할 수 있습니다. 이러한 변경은 지금 수행할 수 있으며 모든 디바이스에 배포할 수 있으며 업데이트 시 더 원활한 전환을 허용합니다.

[**키오스크에 대한 ✔️ Visitor 자동 로그온:**](#visitor-auto-logon-for-kiosks) 

이제 방문자가 자동으로 키오스크에 로그인 할 수 있습니다. 이 동작은 기본적으로 설정 되어 있지만 관리 하거나 사용 하지 않도록 설정할 수 있습니다.

✔️ [**개선 된 키오스크 모드 오류**](#kiosk-mode-behavior-changes-for-handling-of-failures)처리:

로그인 된 AAD 사용자의 AAD 그룹 멤버 자격이 성공적으로 확인 되지 않으면 시작 메뉴에 전역 키오스크 구성 (있는 경우)이 사용 되 고 그렇지 않으면 사용자에 게 빈 시작 메뉴가 표시 됩니다. 빈 시작 메뉴는 직접 설정할 수 있는 구성이 아니라, 키오스크를 사용 하는 경우, 사용자의 구성에 적용 될 수 있거나 할당 된 액세스 구성에 대 한 새로운 조정을 수행 하는 경우에 대 한 지원 부서에이 새로운 처리를 알릴 수 있습니다.

#### <a name="updates-to-page-settings-visibility"></a>페이지 설정 표시에 대 한 업데이트

[**페이지 설정 표시 유형에 대 한 새 설정 uri** ✔️](#new-settings-uris-for-page-settings-visibility)

현재 [페이지 설정 표시 유형을](settings-uri-list.md) 사용 하는 경우 허용 또는 차단 된 기존 uri를 조정 하는 것이 좋습니다.

#### <a name="updates-for-your-wdac-policy"></a>WDAC 정책에 대 한 업데이트
✔️ 이전에 WDAC를 통해 Microsoft Edge를 차단한 경우에는 WDAC 정책을 업데이트 해야 합니다. 다음을 검토 하 고 제공 된 샘플 코드를 사용 하세요.
#### <a name="enable-new-endpoints-for-edge"></a>Edge에 대 한 새 끝점 사용
✔️ 프록시 또는 방화벽과 같은 네트워크 끝점 구성을 포함 하는 인프라가 있는 경우 새 Microsoft Edge 앱에 대해 이러한 새 끝점을 사용 하도록 설정 하세요.

#### <a name="newly-configurable-items"></a>새로 구성 가능한 항목

[대체 진단 구성](#configuring-fallback-diagnostics-via-settings-app)✔️: 대체 진단을 수집할 수 있는 경우 및 사용자를 구성할 수 있습니다.

[주변 장치와 항목을 공유](#share-things-with-nearby-devices)하는 ✔️: 가까운 새 공유 기능을 사용 하지 않도록 설정할 수 있습니다.

[새 Microsoft edge에 대 한 정책 설정을 구성](#configuring-policy-settings-for-the-new-microsoft-edge)하는 ✔️: microsoft edge에 대해 새로 제공 되는 구성을 검토 합니다.

#### <a name="new-diagnostic-tool"></a>새 진단 도구

[새 os 진단 추적](#new-os-diagnostic-traces)✔️: os 업데이트와 관련 된 로그를 수집 합니다.

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 향상 된 기능 및 수정 사항:

- [오프라인 진단에는](hololens-diagnostic-logs.md#offline-diagnostics) 일련 번호 및 OS 버전에 대한 추가 디바이스 정보도 포함됩니다.
- 런타임 프로비전 패키지를 통해 사업체 애플리케이션의 배포와 관련된 문제를 해결합니다.
- 사업체 애플리케이션 설치 상태 보고와 관련된 문제를 해결합니다.
- 디바이스 재설정에서 새 앱 패키지의 지속성에 대한 문제를 해결합니다.
- 일본 고객을 위해 Edge에 잘못된 기호가 입력될 수 있는 문제를 해결합니다.
- Edge와 같이 사전 설치된 앱에 대한 OS 업데이트의 복원력을 향상시킵니다. 
- Microsoft Edge 설치에 영향을 미치는 업데이트 안정성을 해결합니다. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic 버전 20H2 – 2021년 5월 업데이트
- 빌드 19041.1146

업데이트의 개선 사항 및 수정 사항:
- 이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다. 최신 빌드인 Windows Holographic 버전 21H1을 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic 버전 1903 - 2021년 5월 업데이트
- 빌드 18362.1110

업데이트의 개선 사항 및 수정 사항:
- 이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다. **이 빌드는 더 이상 월별 서비스 업데이트를 받지 않습니다.** 최신 빌드인 Windows Holographic 버전 21H1을 사용해보는 것이 좋습니다.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic 버전 20H2 - 2021년 4월 업데이트
- 빌드 19041.1144

업데이트의 개선 사항 및 수정 사항:

- Lob (기간 업무) 응용 프로그램 설치 상태 보고와 관련 된 문제를 해결 합니다.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic 버전 1903-4 월 2021 업데이트
- 빌드 18362.1108

업데이트의 향상 된 기능 및 수정 사항:

- 로컬 계정에 대 한 암호를 변경 하려고 할 때 설정 앱이 충돌 하는 문제를 해결 합니다.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic 버전 20H2-3 월 2021 일 업데이트
- 빌드 19041.1140

업데이트의 향상 된 기능 및 수정 사항:

- AdvancedPhotoCapture 또는 Lowlagphoto 캡처를 사용 하 여 HoloLens 2로 사진을 캡처하는 고객은 이제 사진을 캡처한 후 최대 3 초간 카메라를 검색할 수 있습니다.
- 장치 포털 서비스의 메모리 누수를 수정 합니다 .이 문제로 인해 다른 응용 프로그램에서 메모리 할당에 실패 하는 서비스의 메모리 사용량이 증가 했습니다.
- 스테이징 된 롤아웃에 등록 된 사용자가 장치에 로그인 할 수 없는 문제를 해결 했습니다.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic 버전 1903-3 월 2021 업데이트
- 빌드 18362.1102

업데이트의 향상 된 기능 및 수정 사항:

- 장치 포털 서비스의 메모리 누수를 수정 합니다 .이 문제로 인해 다른 응용 프로그램에서 메모리 할당에 실패 하는 서비스의 메모리 사용량이 증가 했습니다.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, 버전 20H2-2 월 2021 일 업데이트
- 빌드 19041.1136

업데이트의 향상 된 기능 및 수정 사항:

- 초기 장치 설정 및 스토어 앱 업데이트와 관련 된 문제를 해결 합니다.
- 이후 HoloLens 릴리스를 위한 업그레이드와 항공편에 대 한 문제를 해결 합니다.
- HoloLens 디바이스에서 eSIM 루트 저장소에서 사용되지 않는 미리 설치된 인증서가 제거되었습니다.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic 버전 1903 - 2021년 2월 업데이트
- 빌드 18362.1098

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되어 있지 않습니다. Windows Holographic 버전 2004용 최신 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic 버전 20H2 - 2021년 1월 업데이트
- 빌드 19041.1134

업데이트의 개선 사항 및 수정 사항:

- 디바이스에 사용자가 많은 경우 시작, 다시 시작 및 사용자 전환 중에 성능이 향상되었습니다.
- 연구 모드 에 대한 arm32 지원이 [추가되었습니다.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic 버전 1903 - 2021년 1월 업데이트
- 빌드 18362.1091

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다. Windows Holographic 버전 2004용 최신 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic 버전 20H2 – 2020년 12월 업데이트
- 빌드 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>앱 설치 관리자 통해 HoloLens 2 앱 설치

HoloLens 2 **디바이스에 애플리케이션을 더 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)을 추가하고** 있습니다. 이 기능은 **관리되지 않는 디바이스 에 대해 기본적으로 설정됩니다.** 엔터프라이즈의 중단을 방지하기 위해 현재 관리 디바이스에 앱 설치 **관리자를 사용할 수 없습니다.**  

다음 **중** 한 가지가 true인 경우 디바이스는 "관리"로 간주됩니다.
- MDM [등록](hololens-enroll-mdm.md)
- [프로 비전 패키지](hololens-provisioning.md) 를 사용 하 여 구성
- 사용자 [id](hololens-identity.md) 는 Azure AD입니다.

이제 개발자 모드를 사용 하도록 설정 하거나 장치 포털을 사용 하지 않고도 앱을 설치할 수 있습니다.  (USB를 통해 또는 Edge를 통해) Appx 번들을 장치에 다운로드 하 고 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지를 표시 합니다.  또는 [웹 페이지에서 설치를 시작](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)합니다.  MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 서명 [도구](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 를 사용 하 여 앱을 디지털 서명 해야 하며, [서명 하는 데 사용 되는 인증서](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 는 앱을 배포 하기 전에 HoloLens 장치에서 신뢰할 수 있어야 합니다.

**응용 프로그램 설치 지침**

1.  장치가 관리 되는 것으로 간주 되지 않는지 확인 합니다.
1.  HoloLens 2 장치가 켜져 있고 PC에 연결 되어 있는지 확인 합니다.
1.  HoloLens 2 장치에 로그인 했는지 확인 합니다.
1.  PC에서 사용자 지정 앱으로 이동 하 고 yourapp을 yourdevicename\Internal Storage\downloadss에 복사 합니다.   파일 복사를 완료 한 후 장치 연결을 끊을 수 있습니다.
1.  HoloLens 2 장치에서 시작 메뉴를 열고 모든 앱을 선택 하 고 파일 탐색기 앱을 시작 합니다.
1.  다운로드 폴더로 이동 합니다. 앱의 왼쪽 패널에서이 장치를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.
1.  Yourapp 파일을 선택 합니다.
1.  앱 설치 관리자가 시작 됩니다. 설치 단추를 선택 하 여 앱을 설치 합니다.
설치 완료 시 설치 된 앱이 자동으로 시작 됩니다.

이 흐름을 테스트 하려면 [Windows 유니버설 샘플 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 에서 샘플 앱을 찾을 수 있습니다.

앱 설치 관리자 HoloLens 2 [앱을 설치하는](app-deploy-app-installer.md)전체 프로세스를 읽어 보십시오.  

![앱 설치 관리자 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 개선 사항 및 수정 사항:

- 이제 손 추적은 이전에 손을 잃을 수 있었던 많은 새로운 경우에 추적을 유지 관리합니다.  이러한 새로운 경우 중 일부에서는 손만 위치만 사용자의 실제 손을 기반으로 계속 업데이트되고 다른 공동은 이전 자세를 기반으로 유추됩니다.  이 변경은 이동에서 추적 일관성을 개선하는 데 도움이 됩니다(예: 트래핑, throw, 힌팅 및 힌팅).  또한 손은 표면에 가깝거나 개체를 보유하는 경우에도 도움이 됩니다.  손 조인을 유추하는 경우 [공동 정확도당](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 값은 "높음" 대신 "근사값"으로 설정됩니다.
- Azure AD 계정에 대한 PIN 재설정에 "문제가 발생했습니다.
- ET, 설정 앱의 아이리스, 새 사용자 또는 알림 알림을 시작할 때 부팅 후 OOBE 충돌이 훨씬 적게 표시됩니다.
- 사용자에게 OOBE에서 나오는 올바른 표준 시간대가 있어야 합니다.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic 버전 1903 – 2020년 12월 업데이트
- 빌드 18362.1088

이 월별 품질 업데이트는 주목할 만한 변경 내용을 포함하지 않습니다. 최신 Windows Holographic 버전 20H2 – 2020년 12월 업데이트 및 빌드에 추가된 새로운 앱 설치 관리자 기능을 사용해보는 것이 좋습니다.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic 버전 20H2
- 빌드 19041.1128

이제 Windows Holographic 버전 20H2를 사용할 수 있으며 HoloLens 2 사용자 및 IT 전문가에게 훌륭한 새로운 기능 집합을 제공합니다. 자동 눈 위치 지정에서 설정의 인증서 관리자, 향상된 키오스크 모드 기능 및 새로운 Autopilot 설정 기능까지. 이 새로운 업데이트를 통해 IT 팀은 HoloLens 디바이스를 구성하고 관리하는 데 보다 세부적인 제어를 사용할 수 있으며 사용자에게 훨씬 더 원활한 홀로그램 환경을 제공합니다. 

이 최신 릴리스는 버전 2004에 대한 월별 업데이트이지만 이번에는 새로운 기능을 포함하고 있습니다. 주 빌드 번호는 동일 하 게 유지 되 고 Windows 업데이트 버전 2004 (빌드 19041)에 대 한 월간 릴리스를 표시 합니다. 설정 > 화면에서 빌드 번호를 확인 하 여 사용 가능한 최신 빌드 19041.1128 +에 있는지 확인할 수 있습니다. 최신 릴리스로 업데이트 하려면 설정 앱을 열고 업데이트 & 보안으로 이동한 후 업데이트 확인을 탭 합니다. HoloLens 업데이트를 관리 하는 방법에 대 한 자세한 내용은 [이 페이지](https://docs.microsoft.com/hololens/hololens-updates)를 참조 하세요.

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic 버전 20H2의 새로운 기능  

| 기능                                              | 설명                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [자동 눈 위치 지원](hololens-release-notes.md#auto-eye-position-support) | 사용자가 눈 추적 보정을 거치지 않고 눈 위치를 적극적으로 계산 합니다.   |
| [인증서 관리자](hololens-release-notes.md#certificate-manager)   | 설정 앱에서 새로운 간단한 방법으로 인증서를 설치 하 고 제거할 수 있습니다.     |
| [USB에서 프로 비전 자동 시작](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 드라이브에서 패키지를 프로 비전 하면 자동으로 OOBE의 프로 비전 페이지에 표시 됩니다.                                                         |
| [OOBE에서 프로 비전 패키지 자동 확인](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 프로 비전 패키지는 OOBE 중 프로 비전 페이지에서 자동으로 적용 됩니다.                                                         |
| [UI를 사용 하지 않고 자동 프로 비전](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 프로 비전 자동 시작 및 자동 확인을 함께 결합 하는 방법입니다. |
| [Wi-Fi 연결에서 Autopilot 사용](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 이더넷 어댑터 없이 장치 Wi-Fi에서 autopilot를 사용 합니다. |
| [Tenantlockdown CSP 및 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 테 넌 트를 등록 하 고 정책을 적용 한 후에는 장치를 다시 설정 하거나 다시 보낼 때마다 장치를 해당 테 넌 트에만 등록할 수 있습니다. |
| [전역 할당 액세스](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 시스템 수준에서 키오스크를 적용하여 모든 사용자에 적용할 수 있도록 하는 여러 앱 키오스크 모드에 대한 새로운 구성 방법입니다.                  |
| [다중 앱 키오스크에서 앱 자동 시작](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 다중 앱 키오스크 모드에 로그인할 때 자동으로 시작하도록 애플리케이션을 설정합니다.                                                        |
| [오류 처리를 위한 키오스크 모드 동작 변경](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 이제 키오스크 모드 오류가 제한적으로 대체됩니다.                                                                                                |
| [HoloLens 정책](hololens-release-notes.md#hololens-policies)                                    | HoloLens에 대한 새 정책.     |
| [오프라인 키오스크에 대한 Azure AD 그룹 멤버 자격 캐시](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 새 정책을 사용하면 사용자가 그룹 멤버 자격 캐시를 사용하여 설정된 일 수 동안 오프라인으로 키오스크 모드를 사용할 수 있습니다.                                        |
| [HoloLens 2 대한 새 디바이스 제한 정책](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 대해 디바이스 관리 정책을 새로 사용하도록 설정했습니다.                                                                                |
| [HoloLens 2 대한 새 전원 정책](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 전원 제한 시간 설정에 대해 새로 지원되는 정책입니다.  |
| [정책 업데이트](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 업데이트를 제어할 수 있는 새로 사용하도록 설정된 정책입니다.           |
| [HoloLens 2 설정 페이지 표시 유형 사용](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 설정 앱에 표시할 페이지를 선택하는 정책입니다.             |
| [연구 모드](hololens-release-notes.md#research-mode) | HoloLens 2 연구 모드 사용. |
| [기록 길이가 증가했습니다.](hololens-release-notes.md#recording-length-increased) | MRC 기록은 더 이상 5 분으로 제한 되지 않습니다. |
| [업데이트의 향상 된 기능 및 수정 사항](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 업데이트의 추가 수정 사항입니다.   |

### <a name="auto-eye-position-support"></a>자동 눈 위치 지원

HoloLens 2에서는 눈에 맞춰 정확한 홀로그램 위치 지정, 편안 하 게 보기 경험 및 향상 된 디스플레이 품질을 사용할 수 있습니다. 눈 위치는 내부적으로 눈 추적 계산의 일부로 계산 됩니다. 그러나이를 위해서는 각 사용자가 눈에 눈길을 요하는 입력이 필요 하지 않은 경우에도 눈 추적 보정을 거쳐야 합니다.

**자동 눈 위치 (AEP)** 를 사용 하면 이러한 시나리오에서 사용자의 눈 위치를 계산 하는 데 사용할 수 있습니다. 자동 눈 위치는 사용자가 장치를 배치 하는 순간부터 백그라운드에서 자동으로 작업을 시작 합니다. 사용자에 게 이전 눈 추적 보정이 없으면 자동 눈 위치가 20-30 초 후에 표시 시스템에 사용자의 눈 위치를 제공 하기 시작 합니다. 사용자 데이터는 장치에서 지속 되지 않으므로 사용자가 장치를 사용 하지 않도록 설정 하 고 장치를 다시 부팅 하거나 절전 모드에서 해제 하는 경우이 프로세스가 반복 됩니다.

Uncalibrated 사용자가 장치에 배치 하는 경우 자동 눈 위치 기능을 사용 하는 몇 가지 시스템 동작 변경 내용이 있습니다. 이 컨텍스트에서 uncalibrated 사용자는 이전에 장치에서 눈 추적 보정 프로세스를 거치지 않은 사용자를 가리킵니다.

| 활성 응용 프로그램 | 이전 동작 | Windows Holographic 버전 20H2 업데이트의 동작 |
|:-------------------|:-----------------|:-----------------------------------|
| 비-응시 가능 앱 또는 Holographic Shell |눈 추적 보정 프롬프트 대화 상자가 표시 됩니다. | 프롬프트가 표시 되지 않습니다. |
| 응시 앱 사용 | 시선 추적 보정 프롬프트 대화 상자가 표시됩니다. | 시선 추적 보정 프롬프트는 애플리케이션이 시선 응시 스트림에 액세스할 때만 표시됩니다. |

사용자가 응시를 사용하지 않는 애플리케이션에서 응시 데이터에 액세스하는 애플리케이션으로 전환하면 보정 프롬프트가 표시됩니다. 

다른 모든 시스템 동작은 현재 사용자에게 활성 시선 추적 보정이 없는 경우와 유사합니다. 예를 들어 한 손 시작 제스처는 사용하도록 설정되지 않습니다. 초기 설치를 위한 첫 실행 환경은 변경되지 않습니다.

시선 응시 데이터 또는 매우 정확한 홀로그램 위치가 필요한 환경의 경우 눈 추적 보정을 실행하려면 비정형 사용자를 권장합니다. 시선 추적 보정 프롬프트에서 또는 시작 메뉴에서 설정 앱을 시작한 다음 **시스템 > 보정 > 눈 보정 > 눈 보정 실행을** 선택하여 액세스할 수 있습니다.

이 정보는 나중에 [다른 보정 정보](hololens-calibration.md#auto-eye-position-support)를 통해 찾을 수 있습니다. 

### <a name="certificate-manager"></a>인증서 관리자

- 새 인증서 관리자를 통해 디바이스 보안 및 규정 준수를 위한 감사, 진단 및 유효성 검사 도구가 향상되었습니다. 이 기능을 사용하면 상용 환경에서 대규모로 인증서를 배포, 문제 해결 및 유효성을 검사할 수 있습니다.

Windows Holographic 버전 20H2에서는 HoloLens 2 설정 앱에 인증서 관리자를 추가합니다. 설정 **> 업데이트 & 보안 > 인증서로 이동합니다.** 이 기능은 디바이스에서 인증서를 보고, 설치하고, 제거하는 간단하고 사용자에게 친숙한 방법을 제공합니다. 이제 새 인증서 관리자를 통해 관리자와 사용자가 감사, 진단 및 유효성 검사 도구를 개선하여 디바이스가 안전하고 규정을 준수하는지 확인합니다. 

-   **감사:** 인증서가 올바르게 배포되었는지 유효성을 검사하거나 인증서가 적절하게 제거되었는지 확인하는 기능입니다. 
-   **진단:** 문제가 발생하면 디바이스에 적절한 인증서가 있는지 확인하면 시간이 절약되고 문제 해결에 도움이 됩니다. 
-   **유효성 검사:** 인증서가 의도 된 용도를 제공 하 고 작동 하는지 확인 하면, 특히 상업적 환경에서 더 큰 규모로 인증서를 배포 하기 전에 상당한 시간을 절약할 수 있습니다.

목록에서 특정 인증서를 빠르게 찾기 위해 이름, 매장 또는 만료 날짜별로 정렬 하는 옵션이 있습니다. 사용자가 직접 인증서를 검색할 수도 있습니다. 개별 인증서 속성을 보려면 인증서를 선택 하 고 **정보** 를 클릭 합니다. 

인증서 설치는 현재 .cer 및 .crt 파일을 지원 합니다. 장치 소유자는 로컬 컴퓨터 및 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자 에게만 설치할 수 있습니다. 사용자는 설정 UI에서 직접 설치 된 인증서만 제거할 수 있습니다. 인증서가 다른 방법으로 설치 된 경우에도 동일한 메커니즘을 사용 하 여 인증서를 제거 해야 합니다.

#### <a name="to-install-a-certificate"></a>인증서를 설치 하려면: 

1.  HoloLens 2를 PC에 연결 합니다.
1.  설치 하려는 인증서 파일을 HoloLens 2의 한 위치에 배치 합니다.
1.  **설정 앱 > 업데이트 & 보안 > 인증서** 로 이동 하 고 인증서 설치를 선택 합니다.
1.  **파일 가져오기** 를 클릭 하 고 인증서를 저장 한 위치로 이동 합니다.
1.  **저장소 위치** 를 선택 합니다.
1.  **인증서 저장소** 를 선택 합니다.
1.  **설치** 를 클릭합니다.

이제 인증서가 장치에 설치 됩니다.

#### <a name="to-remove-a-certificate"></a>인증서를 제거 하려면: 
1. **설정 앱 > 업데이트 및 보안 > 인증서** 로 이동 합니다.
1. 검색 상자에서 이름으로 인증서를 검색 합니다.
1. 인증서를 선택합니다.
1. **제거** 클릭
1. 확인하라는 메시지가 표시되면 **예** 를 선택합니다.

![설정 앱의 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용하여 인증서를 설치하는 방법을 보여주는 그림](images/certificate-device-install.jpg)

이 정보는 나중에 [새 인증서 관리자 페이지 에서](certificate-manager.md)찾을 수 있습니다.

### <a name="auto-launch-provisioning-from-usb"></a>USB에서 자동 시작 프로비저닝

- OOBE 중에 프로비전 패키지가 있는 USB 드라이브가 사용되는 경우 사용자 상호 작용을 줄이는 자동화된 프로세스입니다.

이 릴리스 전에 사용자는 OOBE 중에 수동으로 프로비전 화면을 시작하여 단추 조합을 사용하여 프로비전해야 했습니다. 이제 사용자는 USB 스토리지 드라이브에서 프로비전 패키지를 사용하여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE의 첫 번째 상호 작용 가능한 순간 동안 USB 드라이브를 프로비저닝 패키지에 연결합니다.
1. 디바이스를 프로비전할 준비가 되면 프로비전 페이지가 있는 프롬프트가 자동으로 열립니다. 

참고: 디바이스가 부팅되는 동안 USB 드라이브가 연결된 경우 OOBE는 기존 USB 스토리지 디바이스를 열거하고 추가 USB 스토리지 디바이스가 연결되어 있는지 감시합니다.

OOBE 중에 프로비전 패키지를 적용하는 데 대한 자세한 내용은 [HoloLens 프로비저닝](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 설명서를 참조하세요.

[USB의 자동 시작 프로비저닝에](hololens-provisioning.md#auto-launch-provisioning-from-usb) 대한 추가 정보는 HoloLens 프로비저닝 설명서에서 확인할 수 있습니다.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE에서 프로비저닝 패키지 자동 확인
- 사용자 상호 작용을 줄이는 자동화된 프로세스로, 프로비전 패키지 페이지가 표시되면 나열된 모든 패키지가 자동으로 적용됩니다.

프로비전 기본 화면이 표시되면 OOBE는 모든 프로비전 패키지 적용을 자동으로 시작하기 전에 10초 동안 카운트다운됩니다. 사용자는 예상한 패키지를 확인한 후 이 10초 이내에 [확인하거나 취소할](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 수 있습니다.

### <a name="automatic-provisioning-without-using-ui"></a>UI를 사용하지 않고 자동 프로비전
- 프로비저닝을 위해 디바이스 상호 작용을 줄이기 위한 자동 프로세스를 결합했습니다. 

USB 디바이스에서 프로비전의 자동 시작과 패키지 프로비저닝 자동 확인을 결합하여 사용자는 디바이스의 UI를 사용하거나 디바이스를 사용하지 않고도 HoloLens 2 디바이스를 자동으로 프로비전할 수 있습니다. 여러 장치에 대해 동일한 USB 드라이브 및 프로 비전 패키지를 계속 사용할 수 있습니다. 이는 동일한 영역에서 한 번에 여러 장치를 배포 하는 데 유용 합니다. 

1. [Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22)를 사용 하 여 [프로 비전 패키지를 만듭니다](hololens-provisioning.md) . 
1. 패키지를 USB 저장소 드라이브에 복사 합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ~ [19041.1361 이상 빌드](https://aka.ms/hololens2previewdownload)를 깜박입니다. 
1. [Advanced Recovery 도우미가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 성공적으로 깜박이는 경우 장치가 USB-C 케이블을 분리 합니다. 
1. 장치에 USB 드라이브를 연결 합니다.
1. HoloLens 2 장치가 OOBE로 부팅 되 면 USB 드라이브에서 프로 비전 패키지를 자동으로 검색 하 고 프로 비전 페이지를 시작 합니다.
1. 10 초 후에 장치가 프로 비전 패키지를 자동으로 적용 합니다. 

이제 장치가 구성 되어 [프로 비전 성공 화면이 표시](hololens-provisioning.md#automatic-provisioning-without-using-ui)됩니다.

### <a name="using-autopilot-with-wi-fi-connection"></a>Wi-Fi 연결에서 Autopilot 사용
- Autopilot가 연결 된 장치 Wi-Fi 기능을 사용할 수 있도록 하 여 하드웨어 요구 사항을 줄이는 USB C 어댑터의 필요를 제거 했습니다.

이제 OOBE를 진행 하는 동안 Autopilot를 사용 하 여 HoloLens 2를 연결 하면 OOBE는 장치에 대 한 프로필을 확인 합니다. 하나를 찾은 경우 AAD 조인 및 등록 흐름의 나머지를 완료 하는 데 사용 됩니다. 즉, usb-C에 대 한 이더넷 또는 USB C 어댑터에 Wi-Fi를 사용 하는 것은 더 이상 요구 사항이 아니지만 OOBE 시작 시 제공 되는 경우 계속 작동 합니다. [HoloLens 2 장치에 대 한 Autopilot](hololens2-autopilot.md)에 대해 자세히 알아보세요.

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 및 Autopilot
- 장치를 다시 설정 하거나 경감 하기 위해 하는 경우에도 테 넌 트에 장치를 잠가 조직의 테 넌 트에 장치를 보관 합니다. 프로 비전을 통해 계정 생성을 허용 하지 않는 추가 보안. 

HoloLens 2 장치는 이제 [Windows Holographic 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에서 TENANTLOCKDOWN CSP를 지원 합니다. 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP를 사용하면 HoloLens 2 Autopilot만 사용하여 MDM 등록에 연결될 수 있습니다. TenantLockdown CSP의 RequireNetworkInOOBE 노드가 HoloLens 2 true 또는 false(처음에 설정) 값으로 설정되면 해당 값은 다시 플래시, OS 업데이트 등에도 불구하고 디바이스에 유지됩니다. 

HoloLens 2 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면 OOBE는 네트워크 연결 후 Autopilot 프로필이 성공적으로 다운로드 및 적용될 때까지 무기한 대기합니다. 

HoloLens 2 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면 OOBE에서 다음 작업이 허용되지 않습니다. 
- 런타임 프로비저닝을 사용하여 로컬 사용자 만들기 
- 런타임 프로비저닝을 통해 Azure AD 조인 작업 수행 
- OOBE 환경의 디바이스를 소유하는 사람 선택 

#### <a name="how-to-set-this-using-intune"></a>Intune을 사용하여 설정하는 방법 
1. 사용자 지정 OMA URI 디바이스 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.
OMA-URI 값은 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 테넌트 잠금 설정](images/hololens-tenant-lockdown.png)

1. 그룹을 만들고 해당 디바이스 그룹에 디바이스 구성 프로필을 할당합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 디바이스 구성원으로 만들고 동기화를 트리거합니다.  

Intune 포털에서 디바이스 구성이 성공적으로 적용되었는지 확인합니다. 이 디바이스 구성이 HoloLens 2 디바이스에 성공적으로 적용되면 TenantLockdown의 효과가 활성화됩니다.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune을 사용하여 HoloLens 2 TenantLockdown의 RequireNetworkInOOBE를 설정 해제하는 방법 
1. 위에서 만든 디바이스 구성이 이전에 할당된 디바이스 그룹에서 HoloLens 2 제거합니다. 

1. 사용자 지정 OMA URI 기반 디바이스 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE에 false를 지정합니다. OMA-URI 값은 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당 합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 트리거합니다.

Intune 포털에서 장치 구성이 성공적으로 적용 되었는지 확인 합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용 되 면 TenantLockdown 효과는 비활성화 됩니다. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true로 설정 된 후 Autopilot 프로필이 HoloLens에서 할당 해제 된 경우 OOBE 중에 수행 되는 작업 
OOBE는 Autopilot 프로필이 다운로드 될 때까지 무기한 대기 하 고 다음 대화 상자가 표시 됩니다. TenantLockdown 효과를 제거 하려면 먼저 Autopilot only를 사용 하 여 장치를 원래 테 넌 트에 등록 해야 하며, TenantLockdown CSP에 의해 도입 된 제한이 제거 되기 전에 이전 단계에서 설명한 대로 RequireNetworkInOOBE 설정 되지 않아야 합니다. 

![장치에서 정책이 적용 되는 경우에 대 한 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

이 정보는 이제 [Tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)아래 Autopilot의 나머지 부분과 함께 찾을 수 있습니다.

### <a name="global-assigned-access--kiosk-mode"></a>전역 할당 액세스-키오스크 모드
- 시스템 수준에서 키오스크 모드를 적용 하는 새 키오스크 방법을 사용 하도록 설정 하 여 키오스크에 대 한 Id 관리를 줄였습니다.

이 새로운 기능을 통해 IT 관리자는 시스템 수준에서 적용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성할 수 있으며, 시스템의 id를 사용 하는 선호도는 없으며 장치에 로그인 하는 모든 사용자에 게 적용 됩니다. [HoloLens 전역 할당 된 액세스 키오스크](hololens-global-assigned-access-kiosk.md)에서이 새로운 기능에 대해 자세히 알아보세요.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>다중 앱 키오스크 모드에서 응용 프로그램 자동 시작 
- 자동 앱 시작에 초점을 맞춘 경험을 통해 키오스크 모드 환경에 대해 선택한 UI 및 앱 선택 항목을 더 늘립니다.

다중 앱 키오스크 모드에만 적용 되며 할당 된 액세스 구성에서 아래 강조 표시 된 특성을 사용 하 여 자동으로 실행 되도록 1 개의 앱만 지정할 수 있습니다. 

사용자가 로그인 하면 응용 프로그램이 자동으로 시작 됩니다. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리에 대 한 키오스크 모드 동작 변경 내용
- 키오스크 모드 오류 시 사용 가능한 앱을 제거하여 키오스크 모드를 더욱 안전하게 보호합니다. 

이전에 키오스크 모드 적용에서 오류가 발생했을 때 HoloLens는 시작 메뉴에 모든 애플리케이션을 표시하는 데 사용했습니다. 이제 Windows Holographic 버전 20H2에서 오류가 발생한 경우 아래와 같이 시작 메뉴에 앱이 표시되지 않습니다. 

![이제 키오스크 모드가 실패할 때 어떻게 보이는지 이미지.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens 정책
- 디바이스를 관리하기 위해 만든 HoloLens에 대한 디바이스 관리 옵션입니다. 

Windows Holographic 버전 20H2에서 HoloLens 2 디바이스에 대한 새로운 혼합 현실 정책이 만들어졌습니다. 새로운 제어 가능한 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음 사용 안함, 진단을 수집할 수 있는 시기 설정 및 AAD 그룹 멤버 자격 캐시가 포함됩니다.  

| 새 HoloLens 정책                                | 설명                                                                               | 메모                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 밝기 단추를 사용하지 않도록 설정하여 키를 누르면 밝기도 변경되지 않습니다.       | 1 예, 0 아니요(기본값)                                                |
| MixedReality\VolumeButtonDisabled                  | 볼륨 단추를 사용하지 않도록 설정하여 키를 누르면 볼륨이 변경되지 않습니다.               | 1 예, 0 아니요(기본값)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 오디오 녹음이 가능하지 않도록 마이크를 사용하지 않도록 설정합니다.                      | 1 예, 0 아니요(기본값)                                                |
| MixedReality\FallbackDiagnostics                   | 진단 로그를 수집할 수 있는 경우의 동작을 제어합니다.                               | 0 사용 안 함, 1 장치 소유자에 대해 1 사용, 2 모두 사용 (기본값) |
| MixedReality\HeadTrackingMode                      | 다음에 사용하도록 예약됩니다.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure ad 그룹을 대상으로 하는 키오스크에 Azure AD 그룹 멤버 자격 캐시가 사용 되는 기간 (일 수)을 제어 합니다. | 아래 내용을 참조하세요.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>오프 라인 키오스크를 위한 Azure AD 그룹 멤버 자격 캐시
- 최대 60 일 동안 AAD 그룹과 함께 오프 라인 키오스크를 사용할 수 있습니다.

이 정책은 로그인 한 사용자에 대해 Azure AD 그룹을 대상으로 하는 할당 된 액세스 구성에 사용할 수 있는 Azure AD 그룹 멤버 자격 캐시의 일 수를 제어 합니다. 이 정책 값이 0 보다 큰 값으로 설정 된 경우에만 캐시가 사용 됩니다.  

이름: AADGroupMembershipCacheValidityInDays URI 값:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

최소-0 일  
최대-60 일 

이 정책을 올바르게 사용 하는 단계: 
1. 키오스크를 대상으로 하는 Azure AD 그룹을 대상으로 하는 장치 구성 프로필을 만들고 HoloLens 장치에 할당 합니다. 
1. 이 정책 값을 원하는 일 수 (> 0)로 설정 하 고 HoloLens 장치에 할당 하는 사용자 지정 OMA URI 기반 장치 구성을 만듭니다. 
    1. URI 값은 OMA-URI 텍스트 상자에./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays로 입력 해야 합니다.
    1. 허용 되는 최소값/최대값 사이에 값을 지정할 수 있습니다.
1. HoloLens 장치를 등록 하 고 두 구성이 장치에 적용 되는지 확인 합니다. 
1. 인터넷을 사용할 수 있을 때 Azure AD 사용자 1 로그인 허용, 사용자 로그인 및 Azure AD 그룹 멤버 자격이 성공적으로 확인 되 면 캐시가 생성 됩니다. 
1. 이제 Azure AD 사용자 1은 HoloLens 오프 라인으로 전환 하 고, 정책 값이 X 일 수를 허용 하는 경우 키오스크 모드에 사용할 수 있습니다. 
1. 다른 모든 Azure AD 사용자에 대해 4 단계와 5 단계를 반복할 수 있습니다. 중요 한 점은 Azure AD 사용자가 인터넷을 사용 하 여 장치에 로그인 해야 하는 것입니다 .이는 적어도 한 번은 키오스크 구성이 대상으로 하는 Azure AD 그룹의 구성원 인지 확인할 수 있습니다. 
 
> [!NOTE]
> Azure AD 사용자에 대해 4단계가 수행될 때까지 "연결이 끊긴" 환경에서 언급된 오류 동작이 발생합니다. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 대한 새 디바이스 제한 정책
- 사용자가 프로비전 패키지 추가 또는 제거 차단과 같은 특정 디바이스 관리 정책을 관리할 수 있습니다.

HoloLens 2 디바이스의 추가 관리 옵션을 허용하는 새로 사용하도록 설정된 정책입니다. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 및 AllowRemoveProvisioningPackage에 대한 이러한 두 가지 새로운 보호가 일반적인 디바이스 제한 에 추가되고 [있습니다.](hololens-common-device-restrictions.md)

> [!NOTE]
> [RemoteLock과](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)관련하여 HoloLens는 ./Vendor/MSFT/RemoteLock/Lock 구성만 지원합니다. 재설정 및 복구와 같은 PIN을 처리하는 구성은 지원되지 않습니다.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 대한 새 전원 정책
- HoloLens가 전원 정책을 통해 절전 모드 또는 잠금을 하는 경우에 대한 추가 옵션입니다. 

새로 추가된 정책을 통해 관리자는 유휴 시간 제한과 같은 전원 상태를 제어할 수 있습니다. 각 개별 정책에 대해 자세히 알아보려면 해당 정책에 대한 링크를 클릭하세요.

|     정책 설명서 링크                |     메모                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 구성 디자이너에서 사용할 예제 값(예:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 구성 디자이너에서 사용할 예제 값(예:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 구성 디자이너에서 사용할 예제 값 (예: 100)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 구성 디자이너에서 사용할 예제 값 (예: 100)                                                                          |
|     [Bytimeouton배터리](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 구성 디자이너에서 사용할 예제 값 (예:)   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 구성 디자이너에서 사용할 예제 값 (예:)  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

이러한 두 가지 새 정책 DisplayOffTimeoutOnBattery 및 DisplayOffTimeoutPluggedIn는 [일반적인 장치 제한](hololens-common-device-restrictions.md)에 추가 됩니다.

> [!NOTE]
> HoloLens 2에 대 한 일관 된 경험을 위해 DisplayOffTimeoutOnBattery 및 필요한 Bytimeouton배터리의 값이 동일한 값으로 설정 되어 있는지 확인 하세요. DisplayOffTimeoutPluggedIn 및 StandbyTimeoutPluggedIn에도 동일 하 게 적용 됩니다. 최신 대기 상태에 대 한 자세한 내용은 [디스플레이, 절전 및 최대 절전 모드 타이머](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 를 참조 하세요.

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens에 대해 새로 설정 된 업데이트 정책
- 업데이트를 설치 하거나 업데이트를 위해 업데이트 일시 중지 단추를 사용 하지 않도록 설정 하는 추가 옵션이 있습니다.

이러한 업데이트 정책은 이제 HoloLens 2 장치에서 사용 하도록 설정 됩니다.
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [업데이트/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

이러한 업데이트 정책에 대 한 자세한 내용 및 HoloLens 장치에 사용 하는 방법은 [hololens 업데이트 관리](hololens-updates.md)에서 확인할 수 있습니다.

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2에 대 한 설정 페이지 표시 여부 설정
- 설정 앱에서 UI 컨트롤이 증가 하 여 제한 된 페이지 선택을 표시 하는 것과 혼동 될 수 있습니다.

이제 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스할 수 없도록 하거나 지정 된 페이지를 제외한 모든 페이지에 대해이 작업을 수행 하도록 허용 하는 정책을 사용 하도록 설정 했습니다. 이 기능을 완전히 사용자 지정하는 방법을 알아보려면 아래 링크를 클릭합니다.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 사용자 지정할 수 있는 페이지 설정을 알아보려면 [설정 URIS 페이지 를](settings-uri-list.md)방문하세요. 
 
![설정 앱에서 수정되는 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>연구 모드
연구 모드에서 HoloLens 2 컴퓨터 비전 연구를 위한 훌륭한 도구가 됩니다. 이전 버전에 비해 HoloLens 2 연구 모드에는 다음과 같은 이점이 있습니다.
-   HoloLens(1세대) 연구 모드에 노출된 센서 외에도 이제 가속도계, 자이록 범위 및 지자기계를 포함한 IMU 센서 액세스를 제공합니다.
-   HoloLens 2 연구 모드와 함께 사용할 수 있는 새로운 기능을 제공합니다. 특히 보다 다양한 실험을 제공할 수 있는 명확한 손 추적 및 시선 추적 API에 액세스할 수 있습니다.

이제 연구원이 HoloLens 디바이스에서 연구 모드를 사용하도록 설정하여 이러한 모든 외부에 연결된 원시 이미지 센서 스트림에 액세스할 수 있습니다. 또한 HoloLens 2 연구 모드에서는 가속도계, 자이록 범위 및 지자기계 판독값에 액세스할 수 있습니다. 사용자의 개인 정보를 보호하기 위해 원시 시선 추적 카메라 이미지는 연구 모드를 통해 사용할 수 없지만 기존 API를 통해 시선 응시 방향을 사용할 수 있습니다.

자세한 기술 정보는 [연구 모드 설명서를 참조하세요.](https://docs.microsoft.com/windows/mixed-reality/research-mode)

### <a name="recording-length-increased"></a>기록 길이가 증가했습니다.
고객 피드백으로 인해 혼합 현실 캡처의 기록 [길이가 증가했습니다.](holographic-photos-and-videos.md) 혼합 현실 캡처는 더 이상 기본적으로 5분으로 제한되지 않지만 대신 사용 가능한 디스크 공간에 따라 최대 기록 길이를 계산합니다. 디바이스는 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 총 디스크 공간의 80%까지 예측합니다.

> [!NOTE]
> HoloLens는 다음 중 하나가 발생하는 경우 기본 비디오 녹화 길이(5분)를 사용합니다.
> - 예상 최대 기록 기간은 기본값인 5분보다 작습니다.
> - 사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.

전체 요구 사항은 [holographic 사진 및 비디오](holographic-photos-and-videos.md#maximum-recording-length) 설명서에서 확인할 수 있습니다. 

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 향상 된 기능 및 수정 사항:
- 이제 OOBE의 더 많은 화면이 진한 모드입니다.
- 자세한 내용은 온라인 개인 정보 취급 방침을 온라인으로 가리켜야 합니다.
- 사용자가 프로 비전 패키지를 통해 VPN 프로필을 프로 비전 할 수 없는 문제를 해결 했습니다.
- VPN 연결에 대 한 프록시 구성 문제를 수정 했습니다.
- NCM에 대 한 NCM 연결에 대 한 MDM을 통한 USB 기능 열거를 사용 하지 않도록 정책을 업데이트 했습니다.
- 장치가 [단일 앱 키오스크](hololens-kiosk.md)로 설정 된 경우 MTP (미디어 전송 프로토콜)를 통해 HoloLens 장치를 파일 탐색기에 표시 하지 못하는 문제를 해결 했습니다. [Allowa 연결](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 정책을 사용 하 여 MTP (일반적으로 USB 연결)를 사용 하지 않도록 설정할 수 있습니다.
- 시작 메뉴의 아이콘이 키오스크 모드에서 올바르게 확장 된 문제를 해결 했습니다.
- Azure AD 그룹을 대상으로 하는 키오스크 모드를 방해 하는 HTTP 캐싱이 발생 하는 문제를 해결 했습니다.
- 개발자 모드를 사용 하지 않도록 설정 했다가 다시 사용 하도록 설정한 경우를 제외 하 고 개발자 모드를 프로 비전 하 여 사용 하도록 설정한 후 사용자가 쌍 단추를 사용할 수 없는 문제를 해결 했습니다.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic 버전 1903-11 월 2020 업데이트
- 빌드 18362.1085

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않습니다. 최신 기능 릴리스 빌드 Windows Holographic, 버전 20H2를 사용해 보는 것이 좋습니다.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic 버전 2004-10 월 2020 업데이트
- 빌드 19041.1124
 
업데이트의 향상 된 기능 및 수정 사항:

- 런타임 시스템 오류를 일으킨 불필요 한 검사를 제거 했습니다.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic 버전 1903 - 2020년 10월 업데이트
- 빌드 18362.1081

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다. Windows Holographic 버전 2004용 최신 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic 버전 2004 - 2020년 9월 업데이트
- 빌드 19041.1117

업데이트의 개선 사항 및 수정 사항:

- supportsMultipleInstances="true"가 appxmanifest에 있는 경우 Visual Studio 애플리케이션을 디버깅하지 못하게 하는 문제를 해결합니다.
- 이 릴리스에는 네트워크 프록시를 통해 실패한 인터넷 검색을 해결하기 위한 NCSI 프록시 검색 수정이 포함되어 있습니다. NCSI는 인터넷 연결 검색에 컴퓨터 프록시 및 프로필별 프록시를 사용할 수 있습니다. 사용자별 프록시는 향후 릴리스에서 NCSI에서 지원됩니다.
- 대부분의 Windows Mixed Reality 디바이스에서 사용자의 머리가 중립 위치에 있을 때 정방향 벡터는 지면과 병렬로 진행됩니다. 그러나 이전 버전의 HoloLens 2 벡터를 디스플레이 패널에 수직으로 맞추었으며, 이상적인 방향을 기준으로 몇 도 아래로 기울어져 있습니다. 최신 버전의 HoloLens 2 폼 팩터 간에 의미 체계 일관성을 보장하기 위해 이를 수정했습니다.
- 특정 시나리오에서 손 추적 견고성이 향상되어 추적 손실이 줄어듭니다.
- 이 릴리스에는 비디오 캡처 문제에 기여했을 수 있는 오디오 타임스탬프 품질을 개선하기 위한 수정이 포함되어 있습니다.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic 버전 1903 - 2020년 9월 업데이트
- 빌드 18362.1079

업데이트의 개선 사항 및 수정 사항:

- 대부분의 Windows Mixed Reality 디바이스에서 사용자의 머리가 중립 위치에 있을 때 정방향 벡터는 지면과 병렬로 진행됩니다. 그러나 이전 버전의 HoloLens 2 벡터를 디스플레이 패널에 수직으로 맞추었으며, 이상적인 방향을 기준으로 몇 도 아래로 기울어져 있습니다. 최신 버전의 HoloLens 2는 폼 팩터 간에 의미 체계 일관성을 유지 하기 위해이를 수정 했습니다.
- 특정 시나리오에서 추적 손실을 줄이는 향상 된 수동 추적 견고성

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic 버전 2004-8 월 2020 업데이트
- 빌드 19041.1113

업데이트의 향상 된 기능 및 수정 사항:

- 설정 앱은 더 이상 사용자를 조리개 등록 또는 눈 추적 보정 환경에 팔 로우 하지 않습니다.
- 장치 이름을 바꾸고 다른 작업 (예: 네트워크에 연결)을 수행 하는 OOBE 중에 프로 비전 패키지를 적용 하는 버그가 수정 되었습니다. 이름을 바꾸면 장치를 다시 부팅 한 후에 다른 작업을 수행 하지 못할 수 있습니다.
- 시각적 품질을 향상 시키기 위해 초기 장치 설정 흐름의 수정 된 색 구성표입니다.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic 버전 1903-8 월 2020 업데이트
- 빌드 18362.1074

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않으므로 Windows Holographic 버전 2004에 대 한 최신 빌드를 사용해 보는 것이 좋습니다.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic 버전 2004-7 월 2020 업데이트
- 빌드 19041.1109

업데이트의 향상 된 기능 및 수정 사항:

- 이제 개발자는 장치 포털에 보안 연결이 필요 하도록 설정 하거나 해제 하는 중에서 선택할 수 있습니다.
- OS 업데이트 후 응용 프로그램 시작에 대 한 안정성이 향상 되었습니다.
- 기본 수신함 밝기를 100%로 변경 했습니다.
- HoloLens 2에서 Windows 장치 포털에 대 한 HTTPS 전달 문제를 해결 했습니다.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic 버전 1903-7 월 2020 업데이트
- 빌드 18362.1071

업데이트의 개선 사항 및 수정 사항:

- 추적을 손실하거나 다시 복원할 때 Unity 애플리케이션에서 홀로그램이 사라지는 문제를 해결했습니다.
- 특정 디바이스에서 하드웨어 가속과 함께 HoloLens 에뮬레이터를 사용하는 동안 배타적 HoloLens 앱이 셸에 크래시되는 문제를 해결했습니다.
- HoloLens 2 Windows 장치 포털 대한 HTTPS 전달과 관련된 문제를 해결했습니다.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic 버전 2004 - 2020년 6월 업데이트
- 빌드 19041.1106

업데이트의 개선 사항 및 수정 사항:

- 이제 사용자 지정 MRC 레코더가 지정되지 않은 경우 특정 속성에 대한 새 기본값을 갖습니다.
  - *MRC 비디오 효과:*
    - PreferredHologramPerspective(1 PhotoVideoCamera)
    - GlobalOpacityCoefficient(0.9(HoloLens) 1.0(몰입형 헤드셋))
  - *MRC 오디오 효과:*
    - LoopbackGain(Windows 장치 포털 혼합 현실 캡처 페이지의 현재 "앱 오디오 게인" 값)
    - MicrophoneGain(Windows 장치 포털 혼합 현실 캡처 페이지의 현재 "마이크 오디오 게인" 값)
- 혼합 현실 캡처 시나리오에서 오디오 품질을 개선하기 위한 버그가 수정되었습니다. 특히 이 수정 사항은 **시작** 메뉴가 표시될 때 녹음에서 오디오 결함을 제거해야 합니다.
- 녹화된 비디오에서 홀로그램 안정성이 향상되었습니다.
- 디바이스가 며칠 동안 대기 상태로 남아 있는 후 혼합 현실 캡처가 비디오를 녹화할 수 없는 문제를 해결했습니다.
- HolographicSpace.UserPresence API는 일반적으로 Unity 애플리케이션에 대해 사용하지 않도록 설정됩니다. 이 동작은 "백그라운드에서 실행" 설정이 설정된 경우에도 바이저가 대칭 이동되었을 때 일부 앱이 일시 중지되는 문제를 방지합니다. API는 이제 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 사용할 수 있습니다.
- Wi-Fi 연결을 통해 장치 포털에 액세스 하는 경우 웹 브라우저에서 잘못 된 인증서로 인해에 액세스 하지 못할 수 있습니다. 장치 인증서가 이전에 신뢰 된 경우에도 브라우저에서 "ERR_SSL_PROTOCOL_ERROR"와 같은 오류를 보고할 수 있습니다. 이 경우에는 보안 경고를 무시 하는 옵션이 없으므로 장치 포털을 진행할 수 없습니다. 이 업데이트는 문제를 해결 했습니다. 이전에 장치 인증서를 다운로드 하 여 PC에서 다운로드 하 여 브라우저 보안 경고를 제거 하 고 SSL 오류가 발생 한 경우 새 인증서를 다운로드 하 고 신뢰 하 여 브라우저 보안 경고를 해결 해야 합니다.
- MSIX 패키지를 사용 하 여 앱을 설치할 수 있는 런타임 프로 비전 패키지를 만드는 기능이 사용 하도록 설정 되었습니다.
-   >    >  사용자가 장치를 종료할 때 Mixed Reality 홈의 모든 Holograms을 자동으로 제거할 수 있도록 설정 시스템 **Holograms** 에 설정이 추가 되었습니다.
- Hololens 에뮬레이터에서 검정색을 렌더링 하도록 픽셀 형식을 변경 하는 HoloLens 앱이 발생 하는 문제를 해결 했습니다.
- Iri 로그인 중에 충돌을 일으킨 버그를 수정 했습니다.
- 이미 존재 하는 앱에 대 한 반복적인 스토어 다운로드 문제를 수정 했습니다.
- 몰입 형 앱에서 Microsoft Edge를 반복적으로 열지 못하게 하는 버그를 수정 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부팅에서 사진 앱을 시작할 때 발생 하는 문제를 해결 했습니다.
- 성능 및 안정성이 향상 되었습니다.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic 버전 1903-6 월 2020 업데이트
- 빌드 18362.1064

업데이트의 향상 된 기능 및 수정 사항:

- 사용자 지정 MRC 레코더는 지정 되지 않은 경우 특정 속성에 대 한 새 기본값을 포함 합니다.
  - *Mrc 비디오 효과*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient(0.9(HoloLens) 1.0(몰입형 헤드셋))
  - *MRC 오디오 효과:*
    - LoopbackGain(Windows 장치 포털 혼합 현실 캡처 페이지의 현재 "앱 오디오 게인" 값)
    - MicrophoneGain(Windows 장치 포털 혼합 현실 캡처 페이지의 현재 "마이크 오디오 게인" 값)
- HolographicSpace.UserPresence API는 일반적으로 Unity 애플리케이션에 대해 사용하지 않도록 설정됩니다. 이 동작은 백그라운드에서 실행되도록 설정이 설정된 경우에도 바이저가 대칭 이동될 때 일부 앱이 일시 중지되는 문제를 방지합니다. 이제 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 API를 사용할 수 있습니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경하여 검은색으로 렌더링하는 HoloLens 앱의 문제를 해결했습니다.
- 1903 릴리스에서 업데이트한 후 초기 부팅에서 Photos 앱의 시작에 대한 문제를 해결했습니다.

## <a name="windows-holographic-version-2004"></a>Windows Holographic 버전 2004  
- 빌드 - 19041.1103

HoloLens 2, *Windows Holographic 버전 2004에 대한 2020년 5월* 주요 소프트웨어 업데이트에는 Windows Autopilot 지원, 앱 어둡게 모드, 5G/LTE 핫스팟에 대한 USB 이더넷 지원 등과 같은 흥미로운 새로운 기능이 포함되어 있습니다. 최신 릴리스로 업데이트하려면 **설정** 앱을 열고   업데이트 & **보안으로** 이동한 다음  **업데이트 확인 단추를**   선택합니다. 

|             기능                              |          설명                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot을 사용하여 프로덕션을 위한 새 디바이스를 미리 구성하고 원활하게 설정                 |
|       FIDO 2 지원                             |          공유 디바이스에 대해 빠르고 안전한 인증을 사용하도록 FIDO2 보안 키 지원            |
|       향상된 프로비저닝                      |          USB 드라이브에서 HoloLens에 프로비전 패키지를 원활하게 적용                              |
|       애플리케이션 설치 상태                 |          MDM을 통해 HoloLens 2 푸시된 앱에 대한 설정 앱의 설치 상태 확인               |
|       Csp (구성 서비스 공급자)   |          관리 제어 기능을 향상 시키기 위해 새 구성 서비스 공급자를 추가 했습니다.                 |
|       USB 5G/LTE 지원                       |          확장 된 USB 이더넷 기능을 통해 5G/LTE를 지원할 수 있습니다.                                    |
|       어두운 앱 모드                              |          어두운 모드 및 밝은 모드를 모두 지 원하는 앱에 대해 사용 가능한 어두운 앱 모드, 보기 환경 향상        |
|       음성 명령                             |          HoloLens 실습을 제어 하는 추가 시스템 음성 명령을 지원 합니다.                           |
|       향상 된 기능 추적                 |          향상 된 기능 추적 기능을 통해 단추와 2D 슬레이트 상호 작용을 보다 정확 하 게                        |
|       품질 향상 및 수정                 |          플랫폼 전체의 다양 한 시스템 성능 및 안정성 향상                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot 지원

HoloLens 용 Windows Autopilot 2에서는 장치 판매 채널에서 HoloLens를 Intune 테 넌 트에 미리 등록할 수 있습니다. 장치가 도착 하면 테 넌 트에서 공유 장치로 자체 배포할 준비가 된 것입니다. 자동 배포를 활용 하려면 USB-C-이더넷을 사용 하 여 설치 프로그램의 첫 번째 화면에서 장치를 네트워크에 연결 해야 합니다.

사용자가 Autopilot 자동 배포 프로세스를 시작 하면 프로세스는 다음 단계를 완료 합니다.

1. 장치를 Azure Active Directory (Azure AD)에 가입 합니다.
1. Azure AD를 사용 하 여 Microsoft Intune 또는 다른 MDM 서비스에 장치를 등록 합니다.
1. 장치 대상 정책, 인증서 및 네트워킹 프로필을 다운로드 합니다.
1. 디바이스를 프로비전합니다.
1. 사용자에게 로그인 화면을 표시합니다.

HoloLens 2 평가 [가이드에 대한 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)자세히 알아보세요.

*지금 AutoPilot 미리 보기에 가입하려면 계정 관리자에게 문의하세요. Autopilot 준비 디바이스는 곧 출시될 예정입니다.*

### <a name="fido2-security-key-support"></a>FIDO2 보안 키 지원

일부 사용자는 작업 또는 학교 환경에서 HoloLens 디바이스를 다른 사용자와 공유합니다. 따라서 사용자가 긴 사용자 이름과 암호를 입력하지 않고도 쉽게 할 수 있는 것이 중요합니다. FIDO(Fast Identity Online)를 사용하면 조직(Azure AD 테넌트)의 모든 사용자가 사용자 이름이나 암호를 입력하지 않고도 HoloLens에 원활하게 로그인할 수 있습니다.

FIDO2 보안 키는 폼 팩터에서 사용할 수 있는 "암호화할 수 없는" 표준 기반 암호 없는 인증 방법입니다. FIDO는 암호 없는 인증을 위한 개방형 표준입니다. 이를 통해 사용자와 조직은 사용자 이름이나 암호 없이 리소스에 로그인할 수 있습니다. 대신 디바이스에 기본 제공되는 외부 보안 키 또는 플랫폼 키를 사용합니다.

시작하려면 [암호 없는 보안 키 로그인 사용을 참조하세요.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>프로비전 패키지를 통한 MDM 등록 개선

패키지를 프로비전하면 HoloLens의 첫 번째 환경이 아닌 구성 파일을 통해 HoloLens 구성을 설정할 수 있습니다. 이전에는 프로비전 패키지를 HoloLens 내부 메모리에 복사해야 했습니다. 이제 여러 HoloLens 디바이스에서 다시 사용할 수 있도록 USB 드라이브에 있을 수 있으며, 동시에 디바이스를 프로비전할 수 있습니다. 이제 프로비전 패키지는 디바이스 관리에 등록하는 필드도 지원하므로 프로비전 후 수동 설정이 없습니다.

기능 사용해 보기:

1. Windows 스토어에서 PC로 최신 버전의 Windows 구성 디자이너를 다운로드합니다.
1. **HoloLens 디바이스**  >  **프로비전 HoloLens 2 디바이스 프로비저닝을** 선택합니다.
2. 구성 프로필을 작성 합니다. 그런 다음 생성 된 모든 파일을 USB-C 저장소 장치에 복사 합니다.
3. USB C 장치를 새롭게 플래시 HoloLens에 연결 합니다. 그런 다음 **볼륨 아래쪽**  +  **전원** 단추를 눌러 프로 비전 패키지를 적용 합니다.

### <a name="line-of-business-application-install-status"></a>Lob (기간 업무) 응용 프로그램 설치 상태

Lob (기간 업무) 앱에 대 한 MDM 앱 배포 및 관리는 HoloLens에 매우 중요 합니다. 관리자와 사용자는 감사 및 진단에 대 한 앱 설치 상태를 확인 해야 합니다. 이 릴리스에서는   >    >  계정 정보를 클릭 하 여 **회사 또는 학교 액세스**  >    >  에서 설정 계정에 추가 세부 정보를 추가 했습니다.

### <a name="additional-csps-and-policies"></a>추가 Csp 및 정책

[CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 는 장치에서 구성 설정을 읽고, 설정 하거나, 수정 하거나, 삭제 하는 인터페이스입니다. 이 릴리스에서는 추가 정책에 대 한 지원을 추가 하 여 관리자가 배포 된 HoloLens 장치에 대해 갖는 제어를 향상 시킵니다. HoloLens에서 지원 되는 Csp 목록은 [Networkqospolicy csp](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)를 참조 하세요.

이 버전의 새 항목:

**Policy CSP**: 

엔터프라이즈는 정책 구성 서비스 공급자를 사용 하 여 Windows 장치에서 정책을 구성할 수 있습니다. 이 릴리스에는 여기에 나열 된 HoloLens에 대 한 새 정책이 추가 되었습니다. 자세히 알아보려면 [HoloLens 2에서 지원 되는 정책 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)를 참조 하세요.  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy 구성 서비스 공급자는 네트워크 QoS(서비스 품질) 정책을 만듭니다. QoS 정책은 일련의 일치 조건에 따라 네트워크 트래픽에 대해 일련의 작업을 수행합니다. 자세한 내용은 [NetworkQoSPolicy CSP를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE 테더링된 디바이스에 대한 확장된 USB 이더넷 지원

USB를 통해 HoloLens 2 테더링될 때 5G/LTE 휴대폰 및 Wi-Fi 핫스팟과 같은 특정 모바일 광대역 디바이스를 사용할 수 있도록 지원이 추가되었습니다. 이러한 디바이스는 이제 **네트워크 설정에** 다른 이더넷 연결로 표시됩니다. (외부 드라이버가 필요한 모바일 광대역 디바이스는 지원되지 않습니다.) 이 기능은 Wi-Fi 사용할 수 없고 Wi-Fi 테더링 성능이 충분하지 않은 경우 고대역폭 연결을 사용하도록 설정합니다. 지원되는 USB 디바이스에 대한 자세한 내용은 [Bluetooth 및 USB-C 디바이스에 연결을 참조하세요.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>손 추적 개선 사항

이 릴리스에는 다음과 같은 몇 가지 손 추적 기능이 포함되어 있습니다.

- **포인팅 자세 안정성:** 이제 시스템은 손끝에 의해 가려질 때 인덱스 손가락의 압정을 거부합니다. 이 변경으로 단추를 누르고, 입력하고, 콘텐츠를 스크롤하는 등의 경우 정확도가 향상됩니다. 
- **실수로 에어 탭 감소:** 에어 탭 제스처의 감지가 향상되었습니다. 이제 사용자에 게 손을 놓는 경우와 같이 몇 가지 일반적인 시나리오에서 실수로 인 한 정품 인증이 줄어듭니다.
- **사용자 전환 안정성:** 이제 시스템은 장치를 공유할 때 수동 크기를 업데이트 하는 것 보다 빠르고 안정적입니다.
- **줄어든 가로채기:** 센서 보기가 세 개 이상 있는 경우의 처리 기능이 개선 되었습니다. 여러 사용자가 서로 긴밀 하 게 작업 하는 경우 추적 된 손을 사용자에서 장면의 다른 사람에 게 "이동" 할 가능성이 훨씬 낮습니다.
- **시스템 안정성:** 장치의 부하가 높을 때 수동 추적의 작동이 중지 되는 문제를 해결 했습니다.

### <a name="dark-mode"></a>어둡게 모드

이제 많은 Windows 앱에서 어두운 모드와 밝은 모드를 모두 지원 합니다. HoloLens 2 사용자는 둘 다를 지 원하는 앱에 대 한 기본 모드를 선택할 수 있습니다. 업데이트 후 기본 앱 모드는 "어둡게" 이지만 **설정**  >  **시스템**  >  **색** 으로 이동  >  **기본 앱 모드를 선택** 하 여이 설정을 쉽게 변경할 수 있습니다. 

이러한 "기본 제공" 앱은 어두운 모드를 지원 합니다. 

- 설정 
- Microsoft Store 
- Mail 
- 달력 
- 파일 탐색기 
- 피드백 허브 
- OneDrive 
- 사진 
- 3D 뷰어 
- TV & 영상 

![진한 모드 windows 바둑판식 배열](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>시스템 음성 명령

이제 장치의 모든 앱에서 음성 명령을 사용할 수 있습니다. 자세한 내용은 [voice를 사용 하 여 HoloLens 운영을](https://docs.microsoft.com/hololens/hololens-cortana)참조 하세요. 또한 [HoloLens 2에 대해 지원 되는 언어를](https://docs.microsoft.com/hololens/hololens2-language-support)참조 하세요.  

### <a name="cortana-updates"></a>Cortana 업데이트

업데이트 된 앱은 Microsoft 365와 통합 되어 장치에서 더 많은 작업을 수행할 수 있도록 지원 합니다 (현재 US-English에만 해당). HoloLens 2에서 Cortana는 볼륨 조정 또는 다시 시작과 같은 특정 장치 특정 명령을 더 이상 지원 하지 않습니다. 이러한 옵션은 이제 새 시스템 음성 명령에서 지원 됩니다. [블로그](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)에서 새 Cortana 앱에 대해 자세히 알아보세요.

### <a name="quality-improvements-and-fixes"></a>품질 향상 및 수정

업데이트의 개선 사항 및 수정 사항:  
- 활성 디스플레이 보정 시스템을 도입했습니다. 이 기능은 홀로그램의 안정성과 맞춤을 향상시킵니다. 이제 헤드를 좌우로 이동할 때 그대로 유지합니다.
- HoloLens로의 Wi-Fi 스트리밍이 정기적으로 중단되는 버그가 수정되었습니다. 애플리케이션에서 짧은 대기 시간 스트리밍이 필요하다고 표시되면 [SetSocketMediaStreamingMode 함수](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)를 호출하여 수정 사항을 구현합니다.
- 연구 모드에서 스트리밍하는 동안 발생한 디바이스 중단 문제가 해결되었습니다.
- 세션을 다시 시작해도 로그인 화면에 올바른 사용자가 표시되지 않는 버그가 수정되었습니다.
- 사용자가 **설정** 을 통해 MDM 로그를 내보낼 수 없는 문제를 해결했습니다.
- 즉시 설치 후 시선 추적의 정확도가 예상보다 낮을 수 있는 문제를 해결했습니다.
- 시선 추적 하위 시스템이 특정 조건에서 보정을 초기화하거나 수행하지 못하는 문제를 해결했습니다.
- 이미 보정된 사용자에게 눈 보정 메시지가 표시되는 문제를 해결했습니다.
- 시선 보정 중에 드라이버가 충돌하는 문제를 해결했습니다.
- 반복되는 전원 단추 누를 때 60초 시스템 시간 제한 및 셸 크래시 문제가 해결되었습니다.
- 깊이 버퍼의 안정성이 향상되었습니다.
- 사용자가 피드백을 보다 쉽게 공유할 수 있도록 피드백 허브 **공유** 단추가 추가되었습니다.
- RoboRaid wan이 올바르게 설치되지 않은 버그가 수정되었습니다.

### <a name="known-issues"></a>알려진 문제

- zh-CN 시스템 언어 관련 문제는 음성 명령이 혼합 현실 캡처를 취하거나 디바이스 IP 주소를 표시하지 못하도록 차단합니다.
- 문제를 해결 하려면 "안녕 코타 나 음성 활성화"를 사용 하도록 장치를 시작한 후 Cortana 앱을 시작 해야 합니다. 18362 빌드에서 업데이트 한 경우 **시작** 시 더 이상 작동 하지 않는 이전 버전의 Cortana 앱에 대 한 두 번째 앱 타일이 표시 될 수도 있습니다.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic 버전 1903-2020 업데이트 
- 빌드 18362.1061

이전에 설명한 대로 팀에서 Windows Holographic 버전 2004를 업데이트할 수 있기 때문에이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않습니다.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic 버전 1903-4 월 2020 업데이트
- 빌드 18362.1059

**지원 되는 앱에 대 한 어두운 모드** 

많은 Windows 앱은 어두운 모드와 밝은 모드를 모두 지원 합니다. HoloLens 2 고객은 이제 두 색 구성표를 모두 지 원하는 앱에 대 한 기본 모드를 선택할 수 있습니다. 사용자 의견에 따라 기본 앱 모드를 "어둡게"로 설정 하지만 언제 든 지이 설정을 쉽게 변경할 수 있습니다. [ **설정 > 시스템 > 색** 으로 이동 하 여 **"기본 앱 모드 선택"** 을 찾습니다.

이러한 "기본 제공" 앱은 어두운 모드를 지원 합니다.
- 설정
- Microsoft Store
- Mail
- 달력
- 파일 탐색기
- 피드백 허브
- OneDrive
- 사진
- 3D 뷰어
- TV & 영상

**업데이트의 향상 된 기능 및 수정 사항:** 
- 셸 중첩이 혼합 현실 캡처에 포함 되었는지 확인 합니다.
- Unreal 개발자는 이제 장치 포털의 3D 보기 페이지를 사용 하 여 응용 프로그램을 테스트 하 고 디버그할 수 있습니다.
- *HolographicDepthReprojectionMethod DepthReprojection* 알고리즘을 사용 하는 경우 혼합 현실 캡처의 홀로그램 안정성이 향상 되었습니다.
- 32 비트 ARM 앱에서 "WinRT IStreamSocketListener API 클래스가 등록 되지 않았습니다." 오류가 수정 되었습니다.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic 버전 1903-3 월 2020 업데이트 
- 빌드 18362.1056

업데이트의 개선 사항 및 수정 사항:

- *HolographicDepthReprojectionMethod AutoPlanar* 알고리즘을 사용할 때 혼합 현실 캡처의 홀로그램 안정성이 향상되었습니다.
- 깊이 MF 샘플에 연결된 좌표계가 공용 설명서와 일치하는지 확인했습니다.
- 고객이 디바이스 포털을 통해 많은 양의 텍스트를 붙여넣을 수 있도록 하여 개발자 생산성을 개선했습니다.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic 버전 1903 - 2020년 2월 업데이트 
- 빌드 18362.1053

업데이트의 개선 사항 및 수정 사항:

- Unity 애플리케이션용 HolographicSpace.UserPresence API를 일시적으로 사용하지 않도록 설정했습니다. 이 변경으로 인해 "백그라운드에서 실행" 설정이 설정된 경우에도 바이저가 대칭 이동되었을 때 일부 앱이 일시 중지되는 문제가 방지됩니다.
- 손 추적으로 인한 임의 HUP 크래시를 수정했습니다. 이 경우 사용자는 몇 초 후에 UI가 중지된 후 다시 셸로 고정되었습니다.
- 손 추적이 향상되어, 인덱스 손가락으로 를 익히면 해당 손가락의 위쪽 부분이 예기치 않게 말릴 가능성이 줄어듭니다.
- 헤드 추적, 공간 매핑 및 기타 런타임의 안정성이 향상되었습니다.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic 버전 1903 - 2020년 1월 업데이트 
- 빌드 18362.1043
 
업데이트의 개선 사항 및 수정 사항:

- HoloLens 2 에뮬레이터로 작업할 때 배타적 앱의 안정성이 향상되었습니다.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic 버전 1903 - 2019년 12월 업데이트 
- 빌드 18362.1042

업데이트의 개선 사항 및 수정 사항:

- 는 LSR (마지막 단계 복제) 픽스를 도입 했습니다. 깊이를 보다 정확 하 게 고려 하 여 보다 안정적이 고 선명 하 게 보이도록 holograms의 시각적 렌더링이 개선 되었습니다. 앱에서 holograms의 깊이를 올바르게 설정 하지 않은 경우이 업데이트 후에이 증상이 더욱 두드러지게 나타납니다.
- 전용 앱 및 전용 앱 간의 탐색의 안정성을 수정 했습니다.
- 장치가 몇 일 동안 대기 상태 였던 혼합 현실 캡처가 비디오를 녹화 하지 못하는 문제를 해결 했습니다.
- 홀로그램의 안정성이 향상 되었습니다.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic 버전 1903-11 월 2019 업데이트 
- 빌드 18362.1039

업데이트의 향상 된 기능 및 수정 사항:

- En-us 및 en-us에 대 한 초기 설정 중에 음성 명령의 **선택** 기능을 수정 했습니다.
- 최신 Unity 및 MRTK (Mixed Reality Toolkit) 버전에서 멀리 떨어진 개체의 시각적 품질이 향상 되었습니다.
- 시작 메뉴를 열고 닫을 때까지 시작 시 일시 중지 됨 상태가 holographic 응용 프로그램의 문제 해결이 수정 되었습니다.
- HoloLens 2 및 에뮬레이터에 대 한 OpenXR 런타임 규칙 수정 및 개선 사항
