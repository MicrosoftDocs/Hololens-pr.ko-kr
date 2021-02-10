---
title: Microsoft HoloLens 참가자 미리 보기
description: Insider 빌드를 시작하는 방법을 알아보고 HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공합니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 4573f3b2e88af36c397fd1735ec9c6a96b4c52d6
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324801"
---
# Microsoft HoloLens 참가자 미리 보기

HoloLens용 최신 Insider Preview 빌드를 시작하세요! HoloLens의 [](hololens-insider.md#start-receiving-insider-builds) 다음 주요 운영 체제 업데이트에 대해 간단하게 시작하고 중요한 피드백을 제공할 수 있습니다.

## Windows Insider Release Notes

Windows Insiders에 새로운 기능의 플라이트를 다시 시작하게 됩니다. We will be flighting to the Dev Channel for the latest updates. Windows Insider 빌드에 추가 기능 및 업데이트를 추가하면 이 페이지가 계속 업데이트됩니다.  이러한 업데이트를 현실에 혼합할 수 있도록 기다렸다가 준비하세요.

> [!IMPORTANT]
> 이전에 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용 중이던 경우 이러한 앱을 다른 앱 ID를 사용하는 새 앱으로 대체했습니다. 아래 키오스크 모드에서 새 앱에 대한 새 [AUMID를 읽어보는 것이](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 좋습니다. 이렇게 하면 키오스크에 설정 앱이 계속 포함되거나 새 Microsoft Edge 앱이 포함됩니다.

<br>

| 기능 이름                                              | 간단한 설명                                                                      | 빌드에서 사용 가능 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [새 Microsoft Edge](#introducing-the-new-microsoft-edge) | 이제 HoloLens 2에서 새로운 Chromium 기반 Microsoft Edge를 사용할 수 있습니다.                         | 20279.1006 |
| [WebXR 및 360 Viewer](#webxr-and-360-viewer)             | 몰입형 웹 환경 및 360 비디오 재생 체험                                           | 20289.1000 |
| [새 설정 앱](#new-settings-app)                     | 레거시 설정 앱이 새로운 기능 및 설정으로 업데이트된 버전으로 대체되고 있습니다. | 20279.1006 |
| [기본 앱 선택기](#default-app-picker)                 | 각 파일 또는 링크 유형에 대해 시작해야 하는 앱 선택                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Office Web App 바로 가기가 이제 "모든 앱"에 나열됩니다.                                   | 20279.1006 |
| [스와이프하여 입력](#swipe-to-type)                           | 손가락 팁을 사용하여 홀로그램 키보드에서 단어 "스와이프"                        | 20279.1006 |
| [USB-C 외부 마이크 지원](#usb-c-external-microphone-support) | 앱 및/또는 원격 지원에 USB-C 마이크를 사용하세요.| 20279.1006 |
| [키오스크 모드의 새 앱용 새 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 새 설정 및 에지 앱용 AUMID | 20279.1006 |
| [개선된 키오스크 모드 오류 수리](#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드는 비어 있는 시작 메뉴 전에 전역 할당된 액세스를 선택합니다. | 20279.1006 |
| [Fallback Diagnostics 구성](#configuring-fallback-diagnostics-via-settings-app) | 설정 앱에서 Fallback Diagnostic Behavior 설정 | 20279.1006 |
| [주변 장치와 공유](#share-things-with-nearby-devices) | HoloLens에서 PC로 파일 또는 URL 공유 | 20279.1006 |
| [새 OS 업데이트 문제 해결사](#new-os-update-troubleshooter) | OS 업데이트 설정의 새로운 문제 해결사 | 20279.1006 |
| [업데이트의 개선 및 수정](#improvements-and-fixes-in-the-update) | 업데이트의 추가 수정입니다. | 20279.1006 |

### 새 Microsoft Edge 소개

![새 Microsoft Edge 로고에 대한 레거시 Microsoft Edge 로고 애니메이션](images/new-edge.gif)

새로운 Microsoft [Edge는 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 오픈 소스 프로젝트를 채택하여 고객에게 더 나은 호환성을 제공하고 웹 개발자를 위한 웹 조각화가 줄어 습니다.

이 Insider 미리 보기를 통해 HoloLens 2 고객은 새 Microsoft Edge를 처음으로 사용할 수 있습니다. 새 Microsoft Edge는 결국 HoloLens 2의 레거시 Microsoft Edge를 대체하는 반면, 현재 두 브라우저는 모두 Insiders에서 사용할 수 있습니다. 새 Microsoft Edge 또는 피드백 허브를 통해 피드백 보내기 기능을 통해 피드백 및 버그를 팀과 [공유해 주세요.](hololens-feedback.md) ****

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### 새 Microsoft Edge 시작

Insiders에 사용할 수 있는 두 가지 버전의 Microsoft Edge가 있습니다. 새 Microsoft Edge 새 Microsoft Edge 아이콘(파란색 및 녹색 소용구 아이콘으로 표시) 및 레거시 ![ Microsoft Edge(흰색 "e" 아이콘으로 ](images/new_edge_logo.png) 표시)가 있습니다. 새 Microsoft Edge가 시작 메뉴에 고정되고 웹 링크를 활성화하면 자동으로 시작됩니다. 레거시 Microsoft Edge를 기본 웹 브라우저로 다시 사용하겠는 경우 아래 지침을 참조하여 기본 앱을 [초기화하세요.](#default-app-picker)

> [!NOTE]
> HoloLens 2에서 새 Microsoft Edge를 처음 시작하면 레거시 Microsoft Edge에서 설정 및 데이터를 가져올 수 있습니다. 새 Microsoft Edge를 시작한 후 레거시 Microsoft Edge를 계속 사용하는 경우 해당 새 데이터는 레거시 Microsoft Edge에서 새 Microsoft Edge로 동기화되지 않습니다.

#### 새 Microsoft Edge에 대한 정책 설정 구성

새로운 Microsoft Edge는 IT 관리자에게 이전에 레거시 Microsoft Edge에서 사용할 수 있는 것보다 HoloLens 2의 훨씬 광범위한 브라우저 정책 집합을 제공합니다.

다음은 새 Microsoft Edge의 정책 설정 관리에 대한 자세한 정보를 알아보는 데 도움이 되는 몇 가지 리소스입니다.

- [Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 레거시에서 Microsoft Edge로 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome에서 Microsoft Edge로 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 전체 [Microsoft Edge Enterprise 설명서](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 새 Microsoft Edge에서 지원되는 브라우저 정책의 양 때문에 각 새 정책이 HoloLens 2에서 작동하는지 보장할 수 없습니다. 그러나 이전에 HoloLens 2에서 지원했던 각 레거시 Microsoft Edge 정책에 해당하는 새 Microsoft Edge가 예상대로 작동하고 확인했습니다. Microsoft [Edge 레거시와 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 정책 매핑을 참조하여 HoloLens 2에서 사용 중이던 각 레거시 Microsoft Edge 브라우저 정책에 해당하는 새 Microsoft Edge를 찾을 수 있습니다.
>
> HoloLens 2에서 작동하지 않는 ** 새로운 Microsoft Edge 정책이 두 개 이상 있습니다.
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### HoloLens 2의 새로운 Microsoft Edge에서 예상할 일

새 Microsoft Edge는 HoloLens 2와 같은 UWP 전용 장치에서 실행될 수 있도록 하는 새로운 UWP 어댑터 계층이 있는 네이티브 Win32 앱이기 때문에 일부 기능을 즉시 사용할 수 없는 경우도 있습니다. 앞으로 몇 개월 동안 새로운 시나리오 및 기능을 지원할 예정이니 이 공간에서 최신 정보를 확인하시기 바랍니다.

**작동해야 하는 시나리오 및 기능:**
- 첫 실행 환경, 프로필에 로그인 및 동기화
- 웹 사이트가 렌더링 및 예상대로 행동해야 합니다.
- 대부분의 브라우저 기능(즐겨찾기, 기록 등)이 예상대로 작동해야 합니다.
- 어두운 모드
- 장치에 웹앱 설치
- 확장 설치(HoloLens 2에서 제대로 작동하지 않는 확장을 사용하는 경우 알려주세요.
- PDF 보기 및 표시
- 단일 브라우저 창의 공간 소리
- 브라우저의 자동 및 수동 업데이트
- 인쇄 메뉴에서 PDF 저장("PDF로 저장" 옵션 사용)

**곧 제공될 시나리오 및 기능:**
- WebXR 및 360 뷰어 확장
- 환경에 배치된 여러 창을 탐색할 때 창을 수정하기 위한 콘텐츠 복원

**다음과 같은 시나리오 및 기능이 작동하지 않을 것으로 예상됩니다.**
- 동시 오디오 스트림이 있는 여러 창의 공간 사운드
- "참조, 말하기"
- 인쇄

**가장 알려진 브라우저 문제:**
- 장치를 초기화하면 새 Microsoft Edge가 제거됩니다.
- 홀로그램 키보드의 돋보기 미리 보기에 잘못된 콘텐츠가 표시됩니다.

#### Microsoft Edge 내부자 채널

Microsoft Edge 팀은 에지 참여자 커뮤니티에서 세 가지 미리 보기 채널인 Beta, Dev 및 Canary를 사용할 수 있도록 합니다. 미리 보기 채널을 설치해도 HoloLens 2에 릴리스된 Microsoft Edge 버전이 제거되지는 않습니다. 동시에 두 개 이상의 Microsoft Edge를 설치할 수 있습니다. 

Microsoft [Edge Insider 홈페이지를](https://www.microsoftedgeinsider.com) 방문하여 에지 내부자 커뮤니티에 대해 자세히 알아보십시오. 다양한 에지 Insider 채널에 대한 자세한 내용을 알아보고 시작하려면 [Edge Insider 다운로드 페이지를 방문하세요.](https://www.microsoftedgeinsider.com/download)

HoloLens 2에 Microsoft Edge Insider 채널을 설치하는 데 사용할 수 있는 몇 가지 방법이 있습니다.

**장치에 직접 설치(현재 관리되지 않는 디바이스에서만 사용 가능)**
  1. HoloLens 2에서 Edge [Insider 다운로드 페이지를 방문합니다.](https://www.microsoftedgeinsider.com/download)
  1. 설치하고자 하는 에지 내부자 채널에 대한 **HoloLens 2** 다운로드 단추를 선택합니다.
  1. Edge 다운로드 큐 또는 장치의 "다운로드" 폴더(파일 탐색기 사용)에서 다운로드된 .msix 파일을 실행합니다.
  1. [앱 설치 관리자를 실행합니다.](app-deploy-app-installer.md)
  1. 설치 **단추를** 선택합니다.
  1. 설치가 성공하면 시작 메뉴의 모든 앱 목록에서 Microsoft Edge **** Beta, Dev 또는 Canary를 별도의 항목으로 찾을 수 있습니다.

**Windows Device Portal을 사용하여 [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) PC를 통해 설치(HoloLens 2에서 개발자 모드를 사용하도록 설정해야 합니다.)**
  1. PC에서 [Edge Insider 다운로드 페이지를 방문합니다.](https://www.microsoftedgeinsider.com/download)
  1. 설치하고자 **** 하는 에지 Insider 채널의 "Windows 10용 다운로드" 단추 옆에 있는 드롭다운 화살표 단추를 선택합니다.
  1. 드롭다운 **메뉴에서 HoloLens 2를** 선택합니다.
  1. .msix 파일을 PC의 "다운로드" 폴더(또는 쉽게 찾을 수 있는 다른 폴더)에 저장합니다.
  1. PC에서 [Windows Device Portal을](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 사용하여 다운로드한 .msix 파일을 HoloLens 2에 설치합니다.
  1. 설치가 성공하면 시작 메뉴의 모든 앱 목록에서 Microsoft Edge **** Beta, Dev 또는 Canary를 별도의 항목으로 찾을 수 있습니다.

> [!NOTE]
> HoloLens 2에 대한 이 Windows Insider 미리 보기 동안 장치의 Microsoft Edge 버전이 일부 또는 전체 Microsoft Edge Insider 채널에서 사용할 수 있는 버전보다 클 수 있습니다. 이는 HoloLens 2의 웹 브라우저를 대상으로 하는 새로운 기능 및 수정이 가능한 한 빨리 Windows Insiders에 연결되도록 보장하기 위한 것입니다. 다음 Windows 업데이트가 공개된 직후 Microsoft Edge 내부자 채널 빌드는 능가하며 HoloLens 2의 Microsoft Edge 버전을 앞서 있습니다.

### WebXR 및 360 Viewer

*Windows Insider Build 20289.1000에 추가되었습니다.*

새로운 Microsoft Edge에는 몰입형 웹 환경을 만들기 위한 새로운 표준인 WebXR에 대한 지원이 포함되어 있습니다(WebVR 대체). 많은 몰입형 웹 환경은 VR을 염두에 두어 디자인했지만(시야를 가상 환경으로 대체) HoloLens 2에서도 지원됩니다. WebXR 표준을 사용하면 실제 환경을 활용하는 증강 및 혼합 현실 몰입형 웹 환경도 사용할 수 있습니다. 개발자가 WebXR에 더 많은 시간을 소비할수록 HoloLens 2 고객에게 새로운 증강 및 혼합 현실 몰입형 환경이 제공될 것으로 예상됩니다.

360 뷰어 확장은 WebXR을 통해 구축되며 HoloLens 2의 새로운 Microsoft Edge와 함께 자동으로 설치됩니다. 이 웹 확장은 360도 비디오에 자신을 들이는 기능을 제공합니다. YouTube에서는 360개 비디오의 최대 선택을 제공하게 있으므로 이 비디오에서 시작하는 것이 권장됩니다.

#### WebXR 사용 방법

1. WebXR 지원을 사용하여 웹 사이트로 이동합니다.
1. 웹 사이트에서 **VR** 입력 단추를 선택합니다. 이 단추의 위치 및 시각적 표현은 웹 사이트마다 다를 수 있지만 다음과 유사할 수 있습니다.

    ![VR 입력 단추 예제](images/75px-enter-vr.png)

1. 특정 도메인에서 WebXR 환경을 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하는 데 동의하도록 요청하고 허용을 **선택합니다.**
1. [HoloLens 2 제스처를 사용하여](hololens2-basic-usage.md#the-hand-tracking-frame) 환경을 조작합니다.
1. 환경의 종료 단추가 **** 없는 경우 시작 제스처를 [사용하여](hololens2-basic-usage.md#start-gesture) 홈으로 돌아오십시오.

**권장 WebXR 샘플**
- 360 뷰어(다음 섹션 참조)
- [XR 공룡](https://www.xrdinosaurs.com/)
- [바리타 Express](https://constructarca.de/game/barista-express/)
- [WebXR 그림판](https://threejs.org/examples/webxr_vr_paint.html)

#### 360 뷰어를 사용하는 방법

1. YouTube에서 360도 비디오로 이동합니다.
1. 비디오 프레임에서 혼합 현실 헤드셋 단추를 선택합니다.

    ![360 뷰어 활성화 단추](images/enter-360-viewer.jpg)

1. 특정 도메인에서 360 Viewer를 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하는 데 동의하도록 요청합니다. 허용을 **선택합니다.**
1. [에어 탭하여](hololens2-basic-usage.md#select-using-air-tap) 재생 컨트롤을 나타 습니다. 손 [광선](hololens2-basic-usage.md#select-using-air-tap) 및 에어 탭을 사용하여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 켜기/끄기 또는 경험을 중지합니다(몰입형 보기를 종료). 재생 컨트롤은 몇 초 동안 비활성 상태일 때 사라집니다.

#### 상위 WebXR 및 360 뷰어 알려진 문제
- WebXR 환경에서는 머리를 기울거나 환경 주위를 이동할 때 홀로그램이 이동하거나 기울어지게 될 수 있습니다.
- WebXR 환경의 복잡도에 따라 프레임 속도는 떨어뜨리거나 스터터될 수 있습니다.
- Articulated hand joints are not yet available in WebXR.
- WebXR 또는 360 뷰어 환경을 종료할 때 혼합 현실 홈의 홀로그램이 다시 나타남에 30초 이상 걸릴 수 있습니다.
- YouTube가 아닌 웹 사이트의 360 동영상이 예상대로 작동하지 않을 수 있습니다.
- 360 비디오가 몰입형 보기를 입력하지 않는 경우(또는 혼합 현실 헤드셋 단추가 나타나지 않는 경우) 페이지를 새로 고쳐 보세요.
- HoloLens 2의 360 뷰어에는 캡션이 아직 표시되지 않습니다.
- 360 뷰어에서 비디오를 일시 중지하면 비디오 렌더링이 중지되지만 재생 단추를 올바르게 선택하면 재생이 다시 시작됩니다.
- 360 뷰어의 "다음 비디오" 단추는 현재 작동하지 않습니다.
- 몰입형 "비디오" 모드에서 2D 비디오를 재생할 수 있지만 프레임 속도는 30ps 미만입니다.

#### WebXR 및 360 뷰어에 대한 피드백 제공

새 Microsoft Edge의 피드백 보내기 **** 기능을 통해 피드백 및 버그를 팀과 공유해 주세요.

### 새 설정 앱

이 릴리스에서는 새로운 버전의 설정 앱을 소개합니다. 새 설정 앱에는 소리, Power & 절전, 네트워크 & 인터넷, 앱, 계정, 접근성 등 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.

> [!NOTE]
> 새 설정 앱은 레거시 설정 앱과는 별개이기 때문에 이전에 환경에 배치한 설정 창은 업데이트 시 제거됩니다.

![새 설정 앱 홈페이지](images/new-settings-app.png)

**새로운 기능 및 설정**
- 설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈에서 설정을 검색합니다.
- 시스템 > 소리:
  - 입력 및 출력 오디오 장치: 입력 및 출력 오디오 장치를 독립적으로 선택하십시오(예: Bluetooth 헤드폰을 통해 오디오를 듣거나 오디오 입력에 USB-C 마이크를 사용). 
    > [!NOTE]
    > Bluetooth HoloLens 2에서 지원되지 않습니다.
  - 앱 볼륨: 각 앱의 볼륨을 독립적으로 조정합니다.
- 시스템 > 전원 & 절전: 장치가 비활성 기간 후 절전으로 이동해야 하는 시기를 선택하십시오.
- 시스템 > 배터리: 배터리 절약 모드를 수동으로 사용하도록 설정하거나 배터리 절약 모드가 자동으로 켜진 지점에 배터리 임계값을 설정합니다.
- USB > 장치: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.
- 네트워크 & 인터넷:
  - 이제 USB-C 이더넷 어댑터가 네트워크 & 표시됩니다.
  - 이제 해당 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.
  - 이제 HoloLens 2에서 비행기 모드를 사용하도록 설정할 수 있습니다.
- 앱: 파일 및 링크 형식에 사용되는 기본 앱을 다시 설정할 수 있습니다. 자세한 [내용은 기본 앱 선택을](#default-app-picker) 참조하세요.
- 다른 > 사용자에 대한 계정: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.
- 접근성: 텍스트 크기 및 일부 시각 효과를 변경합니다.

**알려진 문제**
- 이전에 배치한 설정 창이 제거됩니다(위의 참고 참조).
- 알림 페이지를 방문하면 설정 앱이 충돌할 수 있습니다(조사 중).
- 현재 이더넷 페이지가 표시되지 않습니다(곧 수정될 예정).
- 더 이상 설정 앱으로 디바이스 이름을 변경할 수 없습니다(IT 관리자는 프로비저닝 패키지 또는 MDM을 사용하여 장치 이름을 변경할 수 있습니다).
- UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램(곧 수정이 예상되지 않는 경우)으로 인해 새 Microsoft Edge의 배터리 사용량이 정확하지 않을 수 있습니다.

### 기본 앱 선택기

하이퍼링크를 활성화하거나 앱을 지원하는 설치된 앱이 두 개 이상 있는 파일 형식을 열면 파일 또는 링크 형식을 처리해야 하는 설치된 앱을 선택하라는 새 창이 열립니다. 이 창에서 선택한 앱이 파일 또는 링크 형식 "한 번" 또는 "항상"을 처리하게 선택할 수도 있습니다.

![앱 선택기 창](images/default-app-picker.png)

"항상"을 선택하지만 나중에 특정 파일 또는 링크 형식을 처리하는 앱을 변경하려면 앱의 설정에서 저장된 기본값을 **> 있습니다.** 페이지 아래쪽으로 스크롤하여 "파일 **** 형식에 대한 기본 앱" 및/또는 "링크 형식의 기본 앱"에서 지우기 단추를 선택합니다. 데스크톱 PC의 유사한 설정과 달리 개별 파일 형식 기본값은 다시 설정할 수 없습니다.

### Office Web App

시작 메뉴의 "모든 앱" 목록에 Office Web App이 추가되었습니다. 이 웹앱은 시작 또는 제거에 고정할 수도 있습니다. 웹앱이기 때문에 해당 기능은 방문하여 경험하는 기능과 정확히 https://www.office.com 일치합니다. Office Web App 기능은 HoloLens 2에 활성 인터넷 연결이 있는 경우만 사용할 수 있습니다.

### 스와이프하여 입력

일부 고객은 입력하려는 단어의 모양을 스와이프하여 가상 키보드에서 "입력"하는 것이 더 빠르며 홀로그램 키보드에 대해 이 기능을 미리 보고 있습니다. 홀로그램 키보드의 평면을 통해 손가락 팁을 전달하고 단어의 모양을 스와이프한 다음 키보드 평면에서 손가락 끝을 철회하여 한 단어씩 한 번씩 스와이프할 수 있습니다. 단어 사이에 있는 키보드에서 손가락을 제거하여 스페이스바를 누르지 않고도 후속 단어를 스와이프할 수 있습니다. 키보드에서 손가락을 움직일 때 뒤로 미는 내선이 표시될 경우 이 기능이 작동하고 있는 것을 알 수 있습니다.

휴대폰 디스플레이와 달리 손가락에 대한 저항이 느껴지지 않는 홀로그램 키보드의 특성 때문에 이 기능을 사용 및 마스터하기가 까다로울 수 있습니다. 이 기능은 공개 릴리스에서 평가 중이기 때문에 사용자 의견이 중요합니다. 이 기능이 유용하게 사용되거나 생성적 피드백이 있는지 여부에 따라 피드백 허브를 통해 [알려주세요.](hololens-feedback.md)

### USB-C 외부 마이크 지원

> [!IMPORTANT]
> USB 마이크를 연결하면 자동으로 입력 장치로 **설정되지 않습니다.** USB-C 헤드폰 집합을 연결할 때 사용자는 헤드폰의 오디오가 자동으로 헤드폰으로 리디렉션되는 것이 관찰되지만 HoloLens OS는 다른 입력 장치보다 내부 마이크 배열의 우선 순위를 지정합니다. **USB-C 마이크를 사용하려면 아래 단계를 따릅니다.**

사용자는 소리 설정 패널을 사용하여 USB-C 연결 외부 **마이크를 선택할** 수 있습니다. USB-C 마이크는 통화, 녹음 등에 사용할 수 있습니다.

설정 앱을 **열고** **시스템 소리를**  ->  **선택합니다.**

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 원격 도우미와 **** 함께 외부 마이크를 사용하려면 사용자가 "사운드 장치 관리" 하이퍼링크를 클릭해야 합니다.
>
> 그런 다음 드롭다운을 사용하여 외부 마이크를 **기본** 또는 통신 기본값으로 **설정합니다.** 기본값을 **선택하면** 외부 마이크가 모든 곳에서 사용됩니다.
>
> 통신 **기본값을** 선택하면 외부 마이크가 원격 지원 및 기타 통신 앱에서 사용되지만 HoloLens 마이크 배열을 다른 작업에 계속 사용할 수 있습니다.

![사운드 장치 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### 마이크 지원에 Bluetooth 어떻게 하나요?

안타깝게도 Bluetooth 마이크는 현재 HoloLens 2에서 지원되지 않습니다.

#### USB-C 마이크 문제 해결

일부 USB-C 마이크는 마이크와 스피커 모두로 ** 잘못 보고합니다. HoloLens가 아니라 마이크에 문제가 있습니다. 이러한 마이크 중 하나를 HoloLens에 연결할 때 소리가 손실될 수 있습니다. 다행히 간단한 수정이 있습니다.  

설정 **시스템**  ->  **소리에서**기본 제공 스피커(아날로그 기능 오디오 드라이버)를 명시적으로 기본  ->  **** **장치로 설정** **** HoloLens는 마이크를 제거하고 나중에 다시 연결한 경우에도 이 설정을 기억해야 합니다.

![USB-C 마이크 문제 해결](images/usbc-mic-4.png)

### 키오스크 모드에서 새 설정 및 에지 앱 사용

키오스크에 [](hololens-kiosk.md)앱을 포함하면 IT 관리자가 종종 앱을 키오스크에 추가하지만 AUMID(앱 사용자 모델 ID)를 사용하게 됩니다. 설정 앱과 Microsoft Edge 앱은 모두 새 앱으로 간주되어 해당 앱에 대해 AUMID를 사용하는 이전 앱 키오스크를 업데이트해야 새 AUMID를 사용할 수 있습니다.

새 앱을 포함하도록 키오스크를 수정할 때 새 AUMID를 추가하고 이전 앱을 남겨 두는 것이 좋습니다. 이렇게 하면 사용자가 OS를 업데이트할 때 쉽게 전환할 수 있으며 키오스크를 의도한 바에 따라 계속 사용하기 위한 새 정책을 받을 필요가 없습니다.

| 앱                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 이전 설정 앱       | HolographicSystemSettings_cw5n1h2txyewy! 앱            |
| 새 설정 앱       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 앱 |
| 이전 Microsoft Edge 앱 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 새 Microsoft Edge 앱 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### 오류 처리를 위한 키오스크 모드 동작 변경

이전 빌드에서는 장치에 전역 할당된 액세스와 AAD 그룹 구성원이 할당된 액세스가 모두 조합된 키오스크 구성이 있는 경우 AAD 그룹 구성원 자격 확인에 실패하면["시작"](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)메뉴에 아무 것도 표시되지 않습니다.

Windows Insider 릴리스부터는 AAD 그룹 키오스크 모드 중 오류가 발생하면 키오스크 환경이 전역 키오스크 구성(있는 경우)으로 변경됩니다.

### 설정 앱을 통해 Fallback Diagnostics 구성

이제 설정 앱에서 사용자가 [Fallback Diagnostics의 동작을 구성할 수 있습니다.](hololens-diagnostic-logs.md) 설정 앱에서 개인 **정보**문제 해결 페이지로 이동하여 이  ->  **** 설정을 구성합니다.

> [!NOTE]
> 장치에 대해 구성된 MDM 정책이 있는 경우 사용자는 해당 동작을 다시할 수 없습니다.  

### 주변 장치와 공유

HoloLens Insider 빌드 20279.1006+를 실행하는 PC 및 기타 HoloLens 2 장치를 포함하여 Windows 10 장치에서 거의 모든 것을 공유합니다. 설정 시스템 공유 **** 환경에서 시도해 보아  ->  ****  ->  **** HoloLens에서 PC로 파일 또는 URL을 공유할 수 있습니다. 자세한 내용은 Windows 10에서 주변 장치와 정보를 공유하는 [방법에 대해 자세히 읽어 읽습니다.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

이 기능은 [Connectivity/AllowConnectedDevices를 통해 관리할 수 있습니다.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### 새 OS 업데이트 문제 해결사

설정 앱 내의 이전 문제 해결사 외에도 OS 업데이트용 새 설정 앱이 추가되어 새로운 문제 해결사도 추가되었습니다. 설정 **업데이트**  ->  **보안 &amp; 문제**  ->  ****  ->  **해결 Windows 업데이트로 이동하고** 시작을 **선택합니다.** 이렇게 하면 IT 또는 지원 문제 해결에 도움이 될 수 있도록 OS 업데이트에서 문제를 재현하는 동안 추적을 수집할 수 있습니다.

### 업데이트의 개선 사항 및 수정 사항:

- [오프라인 진단에는](hololens-diagnostic-logs.md#offline-diagnostics) 일련 번호 및 OS 버전에 대한 추가 장치 정보도 포함됩니다.






## Insider 빌드 수신 시작

> [!NOTE]
> If you haven't updated recently, please reboot your device to update state and get the latest build.
> - "다시부팅 장치" 음성 명령이 잘 작동합니다. 
> - 설정/Windows Insider 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 백 엔드에서 발생할 수 있는 버그가 발생하여 다시 추적할 수 있습니다.

HoloLens 2 장치에서 보안 **** Windows & 설정 업데이트로 이동하고  >  ****  >  **** **시작을 선택합니다.** Windows Insider로 등록하는 데 사용한 계정을 연결합니다.

Windows 내부자는 이제 채널로 이동하고 있습니다. 빠른 **링은** 개발자 채널이 되고, **슬로우** 링은 **** 베타 채널이 **되고,** 릴리스 미리 보기 링은 릴리스 미리 보기 **** **채널이 됩니다.** 매핑의 모양은 다음과 같습니다.

![Windows Insider Channels 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에 [Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 소개를 참조하세요.

그런 다음 **Windows의 활성**개발을 선택하고 개발자 **** 채널 또는 **** 베타 채널 빌드를 받을지 여부를 선택하고 프로그램 용어를 검토합니다.

지금 **다시 > 확인을** 선택하여 완료합니다. 장치를 다시 시작한 후 설정 > 업데이트 & **보안** > 최신 빌드를 다운로드하는 업데이트를 확인합니다.

### 해결 0x80070490 오류 업데이트
개발자 또는 베타 0x80070490 업데이트할 때 업데이트 오류가 발생하는 경우 다음과 같은 단기적인 해결 방법을 시도해 보세요. 내부자 채널을 이동하고 업데이트를 선택하고 내부자 채널을 다시 이동하는 과정이 진행됩니다.

#### 1단계 - 릴리스 미리 보기
1.  설정, 업데이트 & 보안, Windows Insider Program, 릴리스 미리 보기 **채널을 선택합니다.**
2.  설정, 업데이트 & 보안, Windows 업데이트, **업데이트를 확인합니다.** 업데이트 후 2단계로 계속 진행합니다.

#### 2단계 - 개발자 채널
1. 설정, & 업데이트, Windows Insider Program, **개발자 채널을 선택합니다.**
2. 설정, 업데이트 & 보안, Windows 업데이트, **업데이트를 확인합니다.**

## FFU 다운로드 및 플래시 길
플라이트 서명된 ffu로 테스트하려면 플라이트 서명된 ffu를 깜박이기 전에 먼저 디바이스 잠금 해제를 플라이트해야 합니다.
1. PC에서:

    1. .에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.
    
    1. Microsoft Store에서 ARC(Advanced Recovery Companion)를 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 설치합니다.
    
1. HoloLens - 플라이트 **** 잠금 해제: 보안 Windows & 프로그램으로 설정 열기 업데이트 후 장치를 등록하고 장치를  >  ****  >  **** 다시 시작합니다.

1. 플래시 FFU - 이제 ARC를 사용하여 플라이트 서명된 FFU를 플래시할 수 있습니다.

## 피드백 제공 및 문제 보고

HoloLens에서 피드백 허브 앱을 사용하여 피드백을 제공하고 문제를 보고하세요. [](hololens-feedback.md) 피드백 허브를 사용하면 엔지니어가 문제를 빠르게 디버그하고 해결하는 데 도움이 되는 필요한 모든 진단 정보가 포함됩니다.  중국어 및 일본어 버전의 HoloLens 관련 문제는 동일한 방식으로 보고해야 합니다.

> [!NOTE]
> 피드백 허브가 문서 폴더에 액세스할지 묻는 메시지를 수락해야 합니다(메시지가 표시될 때 예 선택). ****

## 개발자 참고 사항

환영합니다. HoloLens의 Insider 빌드를 사용하여 응용 프로그램을 개발해 보시고 권장됩니다.  [HoloLens 개발자](https://developer.microsoft.com/windows/mixed-reality/development) 설명서를 확인하여 시작하세요. 이러한 지침은 HoloLens의 Insider 빌드에서 작동됩니다.  HoloLens 개발에 이미 사용 중이 Visual Studio Unity와 동일한 빌드를 사용할 수 있습니다.

## Insider 빌드 수신 중지

Windows Holographic의 Insider 빌드를 더 이상 받지 못하게 하려는 경우 HoloLens가 프로덕션 빌드를 [](hololens-recovery.md) 실행 중일 때 옵트아웃하거나 Advanced Recovery Companion를 사용하여 장치를 Windows Holographic의 비 Insider 버전으로 복구할 수 있습니다.

> [!CAUTION]
> Insider Preview 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 등록하지 않은 사용자가 파란색 화면을 경험하는 알려진 문제가 있습니다. 이후 장치를 수동으로 복구해야 합니다. 영향이 있을지 아니면 그렇지 않을지에 대한 자세한 내용은 이 알려진 문제에서 자세히 [확인하시기 바랍니다.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

HoloLens에서 프로덕션 빌드를 실행 중인지 확인:

1. Settings > **System > About로**이동하고 빌드 번호를 확인합니다.

1. [프로덕션 빌드 번호에 대한 릴리스 참고를 참조합니다.](hololens-release-notes.md)

Insider 빌드를 옵트아웃(opt out)하는 경우:

1. 프로덕션 빌드를 실행하는 HoloLens에서 **설정**> 업데이트 & Windows & 프로그램으로 이동한 다음 > 빌드 중지를 **선택합니다.**

1. 지침에 따라 디바이스를 옵트아웃합니다.
