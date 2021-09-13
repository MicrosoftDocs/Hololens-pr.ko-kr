---
title: 새 Microsoft Edge 소개
description: 새 Edge 앱에 대해 알아보기
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, 에지, 인터넷, 브라우저
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034663"
---
# <a name="introducing-the-new-microsoft-edge"></a>새 Microsoft Edge 소개

![레거시 Microsoft Edge 로고를 새 Microsoft Edge 로고로 애니메이션.](images/new-edge.gif)

새 Microsoft Edge는 [Chromium 오픈 소스 프로젝트를 채택](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)하여 고객을 위해 호환성을 높이고 웹 개발자를 위해 웹의 조각화를 줄입니다.

[Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1)을 사용할 경우 HoloLens 2 고객은 최초로 새 Microsoft Edge를 사용할 수 있습니다! 새 Microsoft Edge의 **피드백 보내기** 기능을 통해 또는 [피드백 허브](hololens-feedback.md)를 통해 팀과 의견 및 버그를 공유하세요.

> [!IMPORTANT]
> 이 새 Microsoft Edge는 새 릴리스에서 [더 이상 지원되지 않는](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) 레거시 Microsoft Edge를 자동으로 대체합니다.

![새 Microsoft Edge 스크린샷.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>새 Microsoft Edge 시작

새로운 Microsoft Edge ![새 Microsoft Edge 아이콘.](images/new_edge_logo.png) (파란색 및 녹색 소용돌이 아이콘으로 표시됨)은 시작 메뉴에 고정되어 있으며 웹 링크를 활성화할 때 자동으로 시작됩니다.

> [!NOTE]
> HoloLens 2에서 새 Microsoft Edge를 처음 시작하면 기존 Microsoft Edge에서 설정 및 데이터를 가져옵니다.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>새 Microsoft Edge에 대한 정책 설정 구성

새 Microsoft Edge는 IT 관리자에게 이전에 레거시 Microsoft Edge HoloLens 2에서 사용 가능했던 것보다 훨씬 더 광범위한 브라우저 정책 집합을 제공합니다.

새 Microsoft Edge의 정책 설정을 관리하는 방법에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성](/deployedge/configure-edge-with-intune)
- [Microsoft Edge 레거시와 Microsoft Edge 정책 매핑](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome과 Microsoft Edge 정책 매핑](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 전체 [Microsoft Edge Enterprise 설명서](/deployedge/)

> [!IMPORTANT]
> 새 Microsoft Edge에서 지원되는 브라우저 정책의 양 때문에 저희 팀은 각 새 정책이 HoloLens 2에서 작동한다고 보장할 수 없습니다. 그러나 이전에 HoloLens 2에서 지원했던 각 레거시 Microsoft Edge 정책에 해당하는 새로운 Microsoft Edge 정책이 예상대로 작동하는지 테스트하고 확인했습니다. HoloLens 2에서 사용했던 각 레거시 Microsoft Edge 브라우저 정책에 해당하는 새 Microsoft Edge 정책을 찾으려면 [Microsoft Edge 레거시와 Microsoft Edge 정책 매핑](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)을 참조하세요.
>
> HoloLens 2에서 작동하지 *않는* 것으로 알고 있는 새로운 Microsoft Edge 정책이 두 개 이상 있습니다.
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2의 새 Microsoft Edge에서 예측할 수 있는 사항

새 Microsoft Edge는 HoloLens 2와 같은 UWP 전용 장치에서 실행할 수 있도록 하는 새 UWP 어댑터 레이어가 포함된 네이티브 Win32 앱이기 때문에 일부 기능은 즉시 사용할 수 없습니다. 향후 몇 개월 동안 새로운 시나리오와 기능을 지원할 예정이므로 이 공간에서 최신 정보를 확인하세요.

**작동할 것으로 예상되는 시나리오 및 기능은 다음과 같습니다.**
- 첫 실행 경험, 프로필에 로그인 및 동기화
- 웹 사이트가 예상대로 렌더링 및 작동해야 함
- 대부분의 브라우저 기능(즐겨찾기, 기록 등)이 예상대로 작동해야 함
- 어둡게 모드
- 장치에 웹 앱 설치
- 확장 설치(HoloLens 2에서 제대로 작동하지 않는 확장을 사용하는 경우 알려주십시오.)
- PDF 보기 및 표시
- 단일 브라우저 창의 공간 음향
- 브라우저 자동 및 수동 업데이트
- 인쇄 메뉴에서 PDF 저장("PDF에 저장" 옵션 사용)
- WebXR 및 360 뷰어 확장
- 환경에 배치되는 여러 창에서 검색할 때 올바른 창으로 콘텐츠 복원

**작동하지 않을 것으로 예상되는 시나리오 및 기능은 다음과 같습니다.**
- 동시 오디오 스트림을 사용하는 여러 창의 공간 음향
- "See it, say it"
- 인쇄

**가장 많이 알려진 브라우저 문제:**
- 홀로그램 키보드의 돋보기 미리 보기가 새 Microsoft Edge에서 사용하지 않도록 설정되었습니다. 확대가 제대로 작동되면 향후 업데이트에서 이 기능을 다시 사용하도록 설정하는 것이 좋습니다.
- 다른 브라우저 창이 열려 있고 활성 상태인 경우 잘못된 브라우저 창에서 오디오를 재생할 수 있습니다. 오디오를 재생할 필요가 없는 다른 활성 창을 닫으면 이 문제를 해결할 수 있습니다.
- "Follow me" 모드의 브라우저 창에서 오디오를 재생하는 경우 "Follow me" 모드를 사용하지 않도록 설정하면 오디오가 계속 재생됩니다. "Follow me" 모드를 사용하지 않도록 설정하기 전에 오디오 재생을 중지하거나 X 단추를 사용하여 창을 닫으면 이 문제를 해결할 수 있습니다.
- 활성 Microsoft Edge 창과 상호 작용하면 다른 2D 앱 창이 갑자기 비활성 상태가 될 수 있습니다. 이러한 창은 다시 상호 작용하여 다시 활성화할 수 있습니다.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

Microsoft Edge 팀은 Edge Insider 커뮤니티에서 사용할 수 있는 세 가지 미리 보기 채널(Beta, Dev 및 Canary)을 만듭니다. 미리 보기 채널을 설치하면 HoloLens 2에서 릴리스된 버전의 Microsoft Edge가 제거되지 않으며 동시에 두 개 이상 설치할 수 있습니다. 

Edge insider 커뮤니티에 대해 자세히 알아보려면 [Microsoft Edge Insider 홈 페이지](https://www.microsoftedgeinsider.com)를 참조하세요. 다른 Edge Insider Channels에 대한 자세한 내용을 알아보고 시작하려면 [Edge Insider 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문하세요.

HoloLens 2에 Microsoft Edge Insider Channels를 설치하는 데 사용할 수 있는 다음 몇 가지 방법이 있습니다.

**장치에 직접 설치(현재는 관리되지 않는 장치에서만 사용 가능)**
  1. HoloLens 2에서 [Edge Insider 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문합니다.
  1. 설치할 Edge Insider Channel의 **Download for HoloLens 2** 단추를 선택합니다.
  1. Edge 다운로드 큐 또는 장치의 "다운로드" 폴더(파일 탐색기 사용)에서 다운로드한 .msix 파일을 실행합니다.
  1. [앱 설치 관리자](app-deploy-app-installer.md)가 시작됩니다.
  1. **설치** 단추를 선택합니다.
  1. 설치가 완료되면 시작 메뉴의 **모든 앱** 목록에 Microsoft Edge Beta, Dev 또는 Canary가 별도의 항목으로 나타납니다.

**Windows 장치 포털을 사용하여 PC를 통해 설치(HoloLens 2에서 [개발자 모드](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)를 사용해야 함)**
  1. PC에서 [Edge Insider 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문합니다.
  1. 설치할 Edge Insider Channel의 "Windows 10 다운로드" 단추 옆에 있는 **드롭다운 화살표 단추** 를 선택합니다.
  1. 드롭다운 메뉴에서 **HoloLens 2** 를 선택합니다.
  1. PC의 "다운로드" 폴더(또는 쉽게 찾을 수 있는 다른 폴더)에 .msix 파일을 저장합니다.
  1. PC에서 [Windows 장치 포털](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)을 사용하여 다운로드한 .msix 파일을 HoloLens 2에 설치합니다.
  1. 설치가 완료되면 시작 메뉴의 **모든 앱** 목록에 Microsoft Edge Beta, Dev 또는 Canary가 별도의 항목으로 나타납니다.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC를 사용하여 새 Microsoft Edge 차단

[WDAC 정책](windows-defender-application-control-wdac.md)을 업데이트하여 새 Microsoft Edge 앱을 차단하려는 IT 관리자의 경우 정책에 다음을 추가해야 합니다.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>새 Microsoft Edge의 엔드포인트 관리

일부 환경에는 고려 사항으로 확인해야 할 네트워크 제한이 있을 수 있습니다. 새 Edge의 원활한 환경을 보장하려면 [이러한 Microsoft 엔드포인트를 사용하도록 설정](/deployedge/microsoft-edge-security-endpoints)하세요.

현재 사용할 수 있는 [HoloLens의 엔드포인트](hololens-offline.md)에 대해 자세히 읽어보세요.

## <a name="install-web-apps"></a>웹 앱 설치
 > [!Note]
> [Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1)에서는 더 이상 Office 웹 앱이 미리 설치되지 않습니다. 

새 Edge를 사용하여 Microsoft Store 앱과 함께 웹 앱을 설치할 수 있습니다. 예를 들어 Microsoft Office 웹 앱을 설치하여 SharePoint 또는 OneDrive에서 호스트되는 파일을 보고 편집할 수 있습니다. Office 웹 앱을 설치하려면 https://www.office.com 에 방문하여 주소 표시줄에서 **App Available** 또는 **Install Office** 단추를 선택합니다. **설치** 를 선택하여 확인합니다.
> [!IMPORTANT]
> Office 웹 앱 기능은 HoloLens 2 활성 인터넷 연결이 있는 경우에만 사용할 수 있습니다.

## <a name="webxr-and-360-viewer"></a>WebXR 및 360 뷰어


새 Microsoft Edge에는 몰입형 웹 환경을 만들기 위한 새로운 표준인 WebXR에 대한 지원이 포함되어 있습니다(WebVR 대체). 대부분의 몰입형 웹 환경은 VR을 염두에 두고 설계되었지만(이는 보기의 필드를 가상 환경으로 대체), 이러한 환경은 HoloLens 2에서도 지원됩니다. WebXR 표준을 사용하면 물리적 환경을 사용하는 증강 현실 및 혼합 현실 몰입형 웹 환경을 사용할 수도 있습니다. 개발자가 WebXR에 더 많은 시간을 쏟고 있으므로, HoloLens 2 고객이 시험해 볼 수 있는 새로운 증강 현실 및 혼합 현실 환경이 도래할 것을 기대합니다!

360 뷰어 확장은 WebXR을 기반으로 하며 HoloLens 2에 새 Microsoft Edge와 함께 자동으로 설치됩니다. 이 웹 확장은 360도 비디오에 직접 몰입할 수 있는 기능을 제공합니다. YouTube는 가장 광범위하게 선택할 수 있는 360 비디오를 제공하므로 YouTube에서 시작해 보세요.

### <a name="how-to-use-webxr"></a>WebXR 사용 방법

1. WebXR가 지원되는 웹 사이트로 이동합니다.
1. 웹 사이트에서 **Enter VR** 단추를 선택합니다. 이 단추의 위치와 표시되는 모양은 웹 사이트별로 다를 수 있지만 다음과 유사할 것입니다.

    ![VR 단추 입력 예.](images/75px-enter-vr.png)

1. 특정 도메인에서 WebXR 환경을 처음 시작하는 경우 브라우저에서 몰입형 보기 입력에 대한 동의를 요청하므로 **허용** 을 선택합니다.
1. 환경을 조작하려면 [HoloLens 2 제스처](hololens2-basic-usage.md#the-hand-tracking-frame)를 사용합니다.
1. 환경에 **끝내기** 단추가 없으면 [시작 제스처](hololens2-basic-usage.md#start-gesture)를 사용하여 홈으로 돌아갑니다.

**권장되는 WebXR 샘플**
- 360 뷰어(다음 섹션 참조)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 그림판](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>360 뷰어를 사용하는 방법

1. YouTube에서 360도 비디오로 이동합니다.
1. 비디오 프레임에서 혼합 현실 헤드셋 단추를 선택합니다.

    ![360 뷰어를 활성화하는 단추.](images/enter-360-viewer.jpg)

1. 특정 도메인에서 처음 360 뷰어를 시작하려고 하면 브라우저에서 몰입형 보기에 대한 동의를 요청합니다. **허용** 을 선택합니다.
1. [에어 탭](hololens2-basic-usage.md#select-using-air-tap)하여 재생 컨트롤을 표시합니다. [손 광선 및 에어 탭](hololens2-basic-usage.md#select-using-air-tap)을 사용하여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 설정/해제, 경험 중지(몰입형 보기 끝내기)를 사용합니다. 몇 초 동안 활동이 없으면 재생 컨트롤이 사라집니다.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR 및 360 뷰어의 알려진 문제
- WebXR 환경의 복잡도에 따라 프레임 속도가 떨어지거나 끊길 수 있습니다.
- WebXR의 손 관절에 대한 지원은 기본적으로 사용되지 않습니다. 개발자는 "WebXR Hand Input"을 설정하여 edge://flags를 통해 지원을 사용하도록 설정할 수 있습니다.
- YouTube 이외의 웹 사이트에서 360 비디오가 예상대로 작동하지 않을 수 있습니다.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR 및 360 뷰어에 대한 피드백 제공

새 Microsoft Edge에서 **피드백 보내기** 기능을 통해 피드백과 버그를 팀과 공유하세요.
