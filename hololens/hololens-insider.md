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
ms.date: 3/4/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 33e16d75a95d62e2c8b881f298acdf692874ef94
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400708"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens 참가자 미리 보기

HoloLens용 최신 Insider Preview 빌드를 시작하세요! HoloLens에 [](hololens-insider.md#start-receiving-insider-builds) 대한 다음 주요 운영 체제 업데이트를 시작하고 중요한 피드백을 제공하는 것이 간단합니다.

## <a name="windows-insider-release-notes"></a>Windows Insider Release Notes

Windows Insiders에 새로운 기능의 플라이트를 다시 시작하게 됐습니다. 새 빌드는 최신 업데이트를 위해 개발자 채널로 플라이트됩니다. Windows Insider 빌드에 추가 기능 및 업데이트를 추가하면 이 페이지가 계속 업데이트됩니다.  이러한 업데이트를 현실에 혼동하고 혼합할 준비를 합니다.

이 기능 업데이트에는 두 대상 대상에 대한 기능이 포함되어 있습니다. 최종 사용자가 디바이스의 모든 사용자가 사용할 수 있는 기능 및 IT 관리자가 구성할 수 있는 새로운 장치 관리 옵션 아래 기능 표에는 각 새 기능을 사용할 수 있는 대상이 구체적으로 설명됩니다. IT 관리자인 경우 IT 관리자 - 업데이트 검사 [목록을 살펴보아 주세요.](#it-admin---update-checklist)

> [!IMPORTANT]
> 이전에 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용 중이던 경우 이러한 앱을 다른 앱 ID를 사용하는 새 앱으로 대체했습니다. 아래 키오스크 모드에서 새 앱에 대한 새 [AUMID를](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 읽는 것이 좋습니다. 이렇게 하면 키오스크에 설정 앱이 계속 포함되거나 새 Microsoft Edge 앱이 포함됩니다.

<br>

| 기능 이름                                              | 간단한 설명                                                                      | 대상 | 빌드에서 사용 가능 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [새 Microsoft Edge](#introducing-the-new-microsoft-edge) | HoloLens 2에서 새로운 Chromium 기반 Microsoft Edge를 사용할 수 있습니다.                         | 최종 사용자 | 20279.1006 |
| [WebXR 및 360 뷰어](#webxr-and-360-viewer)             | 몰입형 웹 환경 및 360 비디오 재생 체험                                           | 최종 사용자 | 20289.1000 |
| [새 설정 앱](#new-settings-app)                     | 레거시 설정 앱이 새로운 기능 및 설정으로 업데이트된 버전으로 대체되고 있습니다. | 최종 사용자 | 20279.1006 |
| [색 보정 표시](#display-color-calibration)   | HoloLens 2 디스플레이에 대한 대체 색 프로필 선택                                | 최종 사용자 | 20293.1000 |
| [기본 앱 선택기](#default-app-picker)                 | 각 파일 또는 링크 유형에 대해 시작해야 하는 앱 선택                                      | 최종 사용자 | 20279.1006 |
| [앱 볼륨 컨트롤당](#per-app-volume-control) |  시스템 볼륨과 독립적으로 앱 수준 볼륨 제어 | 최종 사용자 | 20293.1000 |
| [Office Web App](#office-web-app)                         | 이제 Office Web App 바로 가기가 "모든 앱"에 나열됩니다.                                   | 최종 사용자 | 20279.1006 |
| [스와이프하여 입력](#swipe-to-type)                           | 손가락 팁을 사용하여 홀로그램 키보드에서 단어 "스와이프"                        | 최종 사용자 | 20279.1006 |
| [시작 메뉴의 전원 메뉴](#power-menu-from-start) | 시작 메뉴에서 HoloLens 장치를 다시 시작하고 종료합니다. | 최종 사용자 | 20293.1000 |
| [로그인 화면에 나열된 여러 사용자](#multiple-users-listed-on-sign-in-screen) | 로그인 화면에 여러 사용자 계정 표시 | 최종 사용자 | 20293.1000 |
| [USB-C 외부 마이크 지원](#usb-c-external-microphone-support) | 앱 및/또는 Remote Assist에 USB-C 마이크를 사용하세요.| 최종 사용자 | 20279.1006 |
| [키오스크에 대한 방문자 자동 로그온](#visitor-auto-logon-for-kiosks)                          | 방문자 계정의 자동 로그온을 키오스크 모드에 사용할 수 있습니다.                         | IT 관리자 | 20279.1006                 |
| [키오스크 모드의 새 앱용 새 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 새 설정 및 에지 앱용 AUMID | IT 관리자 | 20279.1006 |
| [키오스크 모드 오류 수리 개선](#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드는 비어 있는 시작 메뉴 전에 전역 할당된 액세스를 선택합니다. | IT 관리자 | 20279.1006 |
| [페이지 설정 표시 여부에 대한 새 설정 URIS](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 설정/PageVisibilityList 정책에 대한 20개 이상의 새 설정URIS | IT 관리자 | 20289.1000 |
| [Fallback Diagnostics 구성](#configuring-fallback-diagnostics-via-settings-app) | 설정 앱에서 Fallback Diagnostic Behavior 설정 | IT 관리자 | 20279.1006 |
| [주변 장치와 공유](#share-things-with-nearby-devices) | HoloLens에서 PC로 파일 또는 URL 공유 | 모두 | 20279.1006 |
| [새 OS 업데이트 문제 해결사](#new-os-update-troubleshooter) | OS 업데이트 설정의 새로운 문제 해결사 | IT 관리자 | 20279.1006 |
| [배달 최적화 미리 보기](#delivery-optimization-preview) | 여러 HoloLens 장치에서 다운로드에 대한 대역폭 소비 감소 | IT 관리자 | 20301.1000 |
| [업데이트의 개선 및 수정](#improvements-and-fixes-in-the-update) | 업데이트의 추가 수정입니다. | 모두 | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 관리자 - 업데이트 검사 목록

이 검사 목록은 현재 장치 관리 구성에 영향을 줄 수 있는 이 기능 업데이트에 추가되는 새 항목 또는 사용을 시작할 수 있는 새 기능을 아는 데 도움이 됩니다.

#### <a name="updates-to-kiosk-mode"></a>키오스크 모드 업데이트

[**키오스크 모드의 새 앱용 새 AUMID**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

이전에 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용 중이던 경우 이러한 앱을 다른 앱 ID를 사용하는 새 앱으로 대체했습니다. 아래 키오스크 모드에서 새 앱에 대한 새 [AUMID를](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 읽는 것이 좋습니다. 이렇게 하면 키오스크에 설정 앱이 계속 포함되거나 새 Microsoft Edge 앱이 포함됩니다.

이제 이러한 변경을 수행하고 모든 디바이스에 배포할 수 있으며 업데이트 시 더 원활한 전환이 가능합니다.

[**키오스크에 대한 방문자 자동 로그온**](#visitor-auto-logon-for-kiosks)

이제 방문자가 자동으로 키오스크에 로그인할 수 있습니다. 이 동작은 기본적으로 설정되어 있지만 관리 및 비활성화할 수 있습니다.

[**키오스크 모드 오류 수리 개선**](#kiosk-mode-behavior-changes-for-handling-of-failures)

이제 이 업데이트는 디바이스를 키오스크 모드로 더 잘 제어하므로 단순히 빈 키오스크를 발표하기 전에 다양한 유형의 키오스크로 돌아갑니다. 이 방법은 관리할 수 없는 경우 구성에 적용될 수 있는 방식으로 키오스크를 사용하는 경우 지원 부서에 알리기 위한 것일 수 있습니다.

#### <a name="updates-to-page-settings-visibility"></a>페이지 설정 표시 여부 업데이트

[**페이지 설정 표시 여부에 대한 새 설정 URIS**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

현재 페이지 설정 [](settings-uri-list.md) 표시를 사용하고 있는 경우 허용되거나 차단된 기존 URIS를 조정할 수 있습니다.

#### <a name="updates-for-your-wdac-policy"></a>WDAC 정책 업데이트

이전에 WDAC를 통해 Microsoft Edge를 차단한 경우 WDAC 정책을 업데이트할 수 있습니다. 다음을 [검토하고](#using-wdac-to-block-new-microsoft-edge) 제공된 샘플 코드를 사용하시기 바랍니다.

#### <a name="enable-new-endpoints-for-edge"></a>Edge에 대한 새 끝점 사용

프록시 또는 방화벽과 같은 네트워크 끝점을 구성하는 인프라가 있는 경우 새 Microsoft Ege 앱에 대해 이러한 새 끝점을 사용하도록 [설정하세요.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>새로 구성 가능한 항목

- [Fallback Diagnostics 구성](#configuring-fallback-diagnostics-via-settings-app)
  - Fallback Diagnostics를 수집할 수 있는지와 수집할 수 있는지를 구성할 수 있습니다.
- [주변 장치와 공유](#share-things-with-nearby-devices)
  - 새 근처 공유 기능을 사용하지 않도록 설정할 수 있습니다.
- [새 Microsoft Edge에 대한 정책 설정 구성](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Microsoft Edge에 사용할 수 있는 새로 구성을 검토합니다.

#### <a name="new-diagnostic-tool"></a>새 진단 도구

- [새 OS 업데이트 문제 해결사](#new-os-update-troubleshooter)
  - OS 업데이트와 관련된 로그 수집

### <a name="introducing-the-new-microsoft-edge"></a>새 Microsoft Edge 소개

![새 Microsoft Edge 로고에 대한 레거시 Microsoft Edge 로고 애니메이션](images/new-edge.gif)

새 Microsoft [Edge는 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 오픈 소스 프로젝트를 채택하여 고객에게 더 나은 호환성을 제공하고 웹 개발자를 위한 웹 조각화가 줄어 습니다.

이 Insider Preview를 통해 HoloLens 2 고객은 새 Microsoft Edge를 처음으로 사용할 수 있습니다. 새 Microsoft Edge는 결국 HoloLens 2의 레거시 Microsoft Edge를 대체하는 반면, 현재 두 브라우저는 모두 Insiders에서 사용할 수 있습니다. 새 Microsoft Edge의 피드백 보내기 **** 기능을 통해 또는 피드백 허브를 통해 피드백 및 버그를 팀과 [공유해 주세요.](hololens-feedback.md)

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>새 Microsoft Edge 시작

내부자는 두 가지 버전의 Microsoft Edge를 사용할 수 있습니다. 새로운 Microsoft Edge 새 Microsoft Edge 아이콘(파란색 및 녹색 소용구 아이콘으로 표시)과 레거시 ![ Microsoft Edge(흰색 "e" 아이콘으로 ](images/new_edge_logo.png) 표시)가 있습니다. 새 Microsoft Edge가 시작 메뉴에 고정되며 웹 링크를 활성화하면 자동으로 시작됩니다. 레거시 Microsoft Edge를 기본 웹 브라우저로 사용으로 되 되전하고자 하는 경우 기본 앱 초기화에 대한 지침은 아래 [지침을 참조하세요.](#default-app-picker)

> [!NOTE]
> HoloLens 2에서 새 Microsoft Edge를 처음 시작하면 레거시 Microsoft Edge에서 설정 및 데이터를 가져올 수 있습니다. 새 Microsoft Edge를 시작한 후 레거시 Microsoft Edge를 계속 사용하는 경우 해당 새 데이터는 레거시 Microsoft Edge에서 새 Microsoft Edge로 동기화되지 않습니다.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>새 Microsoft Edge에 대한 정책 설정 구성

새로운 Microsoft Edge는 IT 관리자에게 이전에 레거시 Microsoft Edge에서 사용할 수 있는 것보다 HoloLens 2의 훨씬 광범위한 브라우저 정책 집합을 제공합니다.

다음은 새 Microsoft Edge의 정책 설정 관리에 대한 자세한 정보를 학습하는 데 도움이 되는 몇 가지 리소스입니다.

- [Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 레거시에서 Microsoft Edge로 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome에서 Microsoft Edge로 정책 매핑](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 전체 [Microsoft Edge 엔터프라이즈 설명서](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 새 Microsoft Edge에서 지원되는 브라우저 정책의 양 때문에 팀에서는 각 새 정책이 HoloLens 2에서 작동하는지 보장할 수 없습니다. 그러나 이전에 HoloLens 2에서 지원했던 각 레거시 Microsoft Edge 정책에 해당하는 새 Microsoft Edge보다 테스트하고 확인했습니다. HoloLens 2에서 사용 중이던 각 레거시 Microsoft Edge 브라우저 정책에 해당하는 새 Microsoft Edge를 찾으십시오. [](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
>
> HoloLens 2에서는 두 개 ** 이상의 새로운 Microsoft Edge 정책이 작동하지 않을 것으로 알고 있습니다.
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2의 새로운 Microsoft Edge에서 예상할 일

새 Microsoft Edge는 HoloLens 2와 같은 UWP 전용 장치에서 실행할 수 있도록 하는 새로운 UWP 어댑터 계층이 있는 네이티브 Win32 앱이기 때문에 일부 기능은 즉시 사용할 수 없습니다. 앞으로 몇 개월 동안 새로운 시나리오 및 기능을 지원할 예정이기 때문에 이 공간에서 최신 정보를 확인할 수 있습니다.

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
- 인쇄 메뉴에서 PDF 저장("PDF에 저장" 옵션 사용)
- WebXR 및 360 뷰어 확장
- 환경에 배치된 여러 창을 탐색할 때 올바른 창으로 콘텐츠 복원

**다음과 같은 시나리오 및 기능이 작동하지 않을 것으로 예상됩니다.**
- 동시 오디오 스트림이 있는 여러 창의 공간 소리
- "보고 말하기"
- 인쇄

**가장 알려진 브라우저 문제:**
- 장치를 초기화하면 새 Microsoft Edge가 제거됩니다.
- 홀로그램 키보드의 돋보기 미리 보기에 잘못된 콘텐츠가 표시됩니다.
- 스크롤 시 스터터가 표시될 수 있습니다.
- Microsoft Store 앱의 웹 링크가 브라우저를 시작하지 않을 수 있습니다.
- 이전에 다른 브라우저 창에서 오디오를 재생한 경우 오디오가 잘못된 브라우저 창에서 재생될 수 있습니다.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge 내부자 채널

Microsoft Edge 팀은 에지 참여자 커뮤니티에서 베타, 개발자 및 카나리아의 세 가지 미리 보기 채널을 사용할 수 있도록 합니다. 미리 보기 채널을 설치해도 HoloLens 2에 릴리스된 버전의 Microsoft Edge가 제거되지는 않습니다. 동시에 두 개 이상의 Microsoft Edge를 설치할 수 있습니다. 

Microsoft [Edge Insider 홈페이지를](https://www.microsoftedgeinsider.com) 방문하여 Edge 내부자 커뮤니티에 대해 자세히 알아보십시오. 다양한 에지 내부자 채널에 대한 자세한 내용을 알아보고 시작하려면 [Edge Insider 다운로드 페이지를 방문하세요.](https://www.microsoftedgeinsider.com/download)

HoloLens 2에 Microsoft Edge Insider 채널을 설치하는 데 사용할 수 있는 몇 가지 방법이 있습니다.

**장치에 직접 설치(현재 관리되지 않는 디바이스에서만 사용 가능)**
  1. HoloLens 2에서 Edge [Insider 다운로드 페이지를 방문합니다.](https://www.microsoftedgeinsider.com/download)
  1. 설치하고자 하는 에지 내부자 채널의 **HoloLens 2** 다운로드 단추를 선택합니다.
  1. Edge 다운로드 큐 또는 장치의 "다운로드" 폴더(파일 탐색기 사용)에서 다운로드한 .msix 파일을 실행합니다.
  1. [앱 설치 관리자가](app-deploy-app-installer.md) 실행됩니다.
  1. 설치 **단추를** 선택합니다.
  1. 설치가 성공하면 시작 메뉴의 모든 앱 목록에서 Microsoft Edge Beta, Dev 또는 Canary를 별도의 항목으로 찾을 수 있습니다. ****

**Windows Device Portal을 사용하여 [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) PC를 통해 설치(HoloLens 2에서 개발자 모드를 사용하도록 설정해야 합니다.**
  1. PC에서 [Edge Insider 다운로드 페이지 를 방문합니다.](https://www.microsoftedgeinsider.com/download)
  1. 설치하고자 **** 하는 Edge Insider 채널의 "Windows 10용 다운로드" 단추 옆에 있는 드롭다운 화살표 단추를 선택합니다.
  1. 드롭다운 **메뉴에서 HoloLens 2를** 선택합니다.
  1. .msix 파일을 PC의 "다운로드" 폴더 또는 쉽게 찾을 수 있는 다른 폴더에 저장합니다.
  1. PC에서 [Windows Device Portal을](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 사용하여 다운로드한 .msix 파일을 HoloLens 2에 설치합니다.
  1. 설치가 성공하면 시작 메뉴의 모든 앱 목록에서 Microsoft Edge Beta, Dev 또는 Canary를 별도의 항목으로 찾을 수 있습니다. ****

> [!NOTE]
> HoloLens 2에 대한 이 Windows Insider 미리 보기 동안 장치의 Microsoft Edge 버전이 일부 또는 전체 Microsoft Edge Insider 채널에서 사용 가능한 버전보다 클 수 있습니다. 이는 HoloLens 2에서 웹 브라우저를 대상으로 하는 새로운 기능 및 수정이 최대한 빨리 Windows Insiders에 연결되도록 보장하기 위한 것입니다. 다음 Windows 업데이트가 공개된 직후에 Microsoft Edge Insider 채널 빌드가 HoloLens 2의 Microsoft Edge 버전을 능가하고 계속 이전 버전으로 유지될 것입니다.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC를 사용하여 새 Microsoft Edge 차단

새 Microsoft Edge 앱을 차단하기 위해 [WDAC](windows-defender-application-control-wdac.md) 정책을 업데이트하려면 정책에 다음을 추가해야 합니다.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>새 Microsoft Edge의 끝점 관리

일부 환경에는 네트워크 제한이 고려 사항으로 고려될 수 있습니다. 새 Edge를 원활하게 사용하려면 이러한 Microsoft 끝점을 사용하도록 [설정하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

HoloLens에 대해 현재 사용 가능한 끝점에 대해 자세히 [읽어보아야 합니다.](hololens-offline.md)

### <a name="webxr-and-360-viewer"></a>WebXR 및 360 뷰어

*Windows Insider 빌드 20289.1000에서 추가되었습니다.*

새 Microsoft Edge에는 몰입형 웹 환경을 만들기 위한 새로운 표준인 WebXR에 대한 지원이 포함되어 있습니다(WebVR 대체). 많은 몰입형 웹 환경은 VR을 염두에 두어 설계되었습니다(시야를 가상 환경으로 대체). 이러한 환경은 HoloLens 2에서도 지원됩니다. 또한 WebXR 표준은 실제 환경을 사용하는 증강 및 혼합 현실 몰입형 웹 환경을 가능하게 합니다. 개발자가 WebXR에 더 많은 시간을 소비할수록 HoloLens 2 고객에게 새로운 증강 및 혼합 현실 몰입형 환경이 제공될 것으로 예상됩니다.

360 뷰어 확장은 WebXR을 통해 구축되며 HoloLens 2의 새 Microsoft Edge와 함께 자동으로 설치됩니다. 이 웹 확장은 360도 비디오에 자신을 들이는 기능을 제공합니다. YouTube는 360개 비디오를 가장 많이 선택하기 때문에 이 비디오에서 시작하는 것이 권장됩니다.

#### <a name="how-to-use-webxr"></a>WebXR 사용 방법

1. WebXR 지원으로 웹 사이트로 이동합니다.
1. 웹 **사이트에서 VR 입력** 단추를 선택합니다. 이 단추의 위치 및 시각적 표현은 웹 사이트마다 다를 수 있지만 다음과 유사할 수 있습니다.

    ![VR 단추 입력 예제](images/75px-enter-vr.png)

1. 특정 도메인에서 WebXR 환경을 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하는 데 동의하도록 요청하고 허용을 **선택합니다.**
1. [HoloLens 2 제스처를 사용하여](hololens2-basic-usage.md#the-hand-tracking-frame) 환경을 조작합니다.
1. 환경의 종료 단추가 **** 없는 경우 시작 [제스처를](hololens2-basic-usage.md#start-gesture) 사용하여 홈으로 돌아오십시오.

**권장 WebXR 샘플**
- 360 뷰어(다음 섹션 참조)
- [XR 공룡](https://www.xrdinosaurs.com/)
- [바리타 Express](https://constructarca.de/game/barista-express/)
- [WebXR 그림판](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 뷰어를 사용하는 방법

1. YouTube에서 360도 비디오로 이동합니다.
1. 비디오 프레임에서 혼합 현실 헤드셋 단추를 선택합니다.

    ![360 뷰어를 활성화하는 단추](images/enter-360-viewer.jpg)

1. 특정 도메인에서 360 뷰어를 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하는 데 동의하도록 요청합니다. 허용을 **선택합니다.**
1. [에어 탭하여](hololens2-basic-usage.md#select-using-air-tap) 재생 컨트롤을 업합니다. 손 [광선](hololens2-basic-usage.md#select-using-air-tap) 및 에어 탭을 사용하여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 켜기/끄기 또는 환경을 중지(몰입형 보기를 종료)합니다. 재생 컨트롤은 몇 초 동안 비활성 상태일 때 사라집니다.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>상위 WebXR 및 360 뷰어 알려진 문제
- WebXR 환경에서는 머리를 기울거나 환경 주위를 이동할 때 홀로그램이 이동하거나 기울어지게 될 수 있습니다.
- WebXR 환경의 복잡도에 따라 프레임 속도는 떨어뜨리거나 스터터될 수 있습니다.
- WebXR에서는 아직 손 조인트가 제공되지 않습니다.
- WebXR 또는 360 뷰어 환경을 종료할 때 혼합 현실 홈의 홀로그램이 다시 시작될 때 30초 이상이 걸릴 수 있습니다.
- YouTube가 아닌 웹 사이트의 360 비디오가 예상대로 작동하지 않을 수 있습니다.
- 360 비디오가 몰입형 보기를 입력하지 않는 경우(또는 혼합 현실 헤드셋 단추가 나타나지 않는 경우) 페이지를 새로 고쳐 보세요.
- HoloLens 2의 360 뷰어에는 캡션이 아직 표시되지 않습니다.
- 360 뷰어에서 비디오를 일시 중지하면 비디오 렌더링이 중지되지만 재생 단추를 올바르게 선택하면 재생이 다시 시작됩니다.
- 360 뷰어의 "다음 비디오" 단추는 현재 작동하지 않습니다.
- 몰입형 "페더러" 모드에서 2D 비디오를 재생할 수 있지만 프레임 속도는 30ps 미만입니다.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR 및 360 뷰어에 대한 피드백 제공

새 Microsoft Edge의 피드백 보내기 **** 기능을 통해 피드백 및 버그를 팀과 공유해 주세요.

### <a name="new-settings-app"></a>새 설정 앱

이 릴리스에서는 새로운 버전의 설정 앱을 소개합니다. 새 설정 앱에는 소리, Power & 절전, 네트워크 &, 앱, 계정, 접근성 등 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.

> [!NOTE]
> 새 설정 앱은 레거시 설정 앱과는 별개이기 때문에 이전에 환경에 배치한 설정 창은 업데이트 시 제거됩니다.

![새 설정 앱 홈페이지](images/new-settings-app.png)

**새로운 기능 및 설정**
- 설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈페이지에서 설정을 검색합니다.
- 시스템 > 소리:
  - 입력 및 출력 오디오 장치: 입력 및 출력 오디오 장치를 독립적으로 선택하십시오(예: Bluetooth 헤드폰을 통해 오디오를 듣거나 오디오 입력을 위해 USB-C 마이크 사용).
    > [!NOTE]
    > Bluetooth 마이크는 HoloLens 2에서 지원되지 않습니다.
  - 앱 볼륨: 각 앱의 볼륨을 독립적으로 조정합니다. 앱 [볼륨 제어당을 참조하세요.](#per-app-volume-control)
- 시스템 > 전원 & 절전: 장치가 비활성 기간 후 절전으로 이동해야 하는 시기를 선택하세요.
- 시스템 > 배터리: 배터리 절약 모드를 수동으로 사용하도록 설정하거나 배터리 절약 모드가 자동으로 켜진 지점에 배터리 임계값을 설정합니다.
- USB > 장치: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.
- 네트워크 & 인터넷:
  - 이제 USB-C 이더넷 어댑터가 네트워크 인터넷에 & 표시됩니다.
  - 이제 해당 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.
  - 이제 HoloLens 2에서 비행기 모드를 사용하도록 설정할 수 있습니다.
- 앱: 파일 및 링크 형식에 사용되는 기본 앱을 다시 설정할 수 있습니다. 자세한 내용은 기본 앱 [선택을 참조하세요.](#default-app-picker)
- 계정 > 사용자: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.
- 접근성: 텍스트 크기 및 일부 시각 효과를 변경합니다.

**알려진 문제**
- 이전에 배치된 설정 창이 제거됩니다(위의 참고 참조).
- 더 이상 설정 앱을 사용하여 디바이스 이름을 변경할 수 없습니다. IT 관리자는 [HoloLens 2용 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 장치 이름 템플릿 또는 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 노드를 사용하여 디바이스 이름을 바킬 수 있습니다.
- 이더넷 페이지에는 모든 가상 이더넷 장치("UsbNcm")가 표시됩니다.
- UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램(곧 수정이 예상되지 않을 예정)으로 인해 새 Microsoft Edge의 배터리 사용량이 정확하지 않을 수 있습니다.

### <a name="display-color-calibration"></a>색 보정 표시

*Windows Insider 빌드 20293.1000에 추가되었습니다.*

이 새 설정을 사용하여 HoloLens 2 디스플레이에 대한 대체 색 프로필을 선택할 수 있습니다. 특히 디스플레이 밝기 수준이 낮은 경우 색이 더 정확하게 표시될 수 있습니다. 디스플레이 색 보정은 설정 앱의 시스템 보정 페이지에서 > 있습니다.

> [!NOTE]
> 이 설정은 디스플레이 펌웨어에 새 색 프로필을 저장하기 때문에 장치별로 설정됩니다(각 사용자 계정마다 고유하지는 않습니다).

#### <a name="how-to-use-display-color-calibration"></a>디스플레이 색 보정을 사용하는 방법

1. 설정 **앱을 시작하고** 시스템 및 > **이동합니다.**
1. 색 **보정 표시에서**색 보정 **실행 단추를** 선택합니다.
1. 디스플레이 색 보정 환경이 시작될 것이고 바이서가 올바른 위치에 있는지 확인하도록 장려합니다.
1. 명령 대화 상자를 진행하면 디스플레이가 자동으로 30% 밝기로 희미해집니다.
    > [!TIP]
    > 환경에서 희미해진 장면을 보는 데 문제가 있는 경우 장치의 왼쪽에 있는 밝기 단추를 사용하여 HoloLens 2의 밝기 수준을 수동으로 조정할 수 있습니다.
1. 단추 1-6을 선택하여 즉시 각 색 프로필을 시도하고 눈에 가장 잘 보이는 프로필을 찾으십시오(일반적으로 장면이 가장 중립적으로 표시될 수 있도록 하는 프로필, 회색조 패턴 및 스킨 톤이 예상대로 표시)

    ![색 보정 장면 표시](images/color-cal-ui.png)
    
1. 선택한 프로필이 만족스러우면 Save **& Exit 단추를** 선택합니다.
1. 변경하지 않을 경우 취소 & **** 취소 단추를 선택하면 변경 내용이 되전됩니다.

> [!TIP]
> 디스플레이 색 보정 설정을 사용하는 동안 유의해야 할 몇 가지 유용한 팁은 다음과 같습니다.
> - 원하는 경우 설정에서 디스플레이 색 보정을 다시 실행할 수 있습니다.
> - 장치의 모든 사용자가 이전에 설정을 사용하여 색상 프로필을 변경한 경우 가장 최근 변경 날짜/시간이 설정 페이지에 반영됩니다.
> - 디스플레이 색 보정을 다시 실행하면 이전에 저장한 색 프로필이 강조 표시되고 프로필 0이 표시되지 않습니다(프로필 0은 디스플레이의 원래 색 프로필을 나타내기).
> - 디스플레이의 원래 색 프로필로 되감기하려면 설정 페이지에서 이 작업을 할 수 있습니다(색 프로필 다시 설정 [방법 참조).](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>색 프로필을 다시 설정하는 방법

HoloLens 2에 저장된 사용자 지정 색 프로필에 불만이 있는 경우 장치의 원래 색 프로필을 복원할 수 있습니다.
1. 설정 **앱을 시작하고** 시스템 및 > **이동합니다.**
1. 색 **보정 표시에서**기본 색 프로필로 다시 **설정 단추를** 선택합니다.
1. 대화 상자가 열리면 **** HoloLens 2를 다시 시작하고 변경 내용을 적용할 준비가 된 경우 다시 시작을 선택합니다.

#### <a name="top-display-color-calibration-known-issues"></a>상위 디스플레이 색 보정 알려진 문제

- 설정 페이지에서 색 프로필이 마지막으로 변경된 날짜를 표시하는 상태 문자열은 설정 페이지를 다시 로드할 때까지 최신 상태가 됩니다. 
    - 해결 작업: 다른 설정 페이지를 선택한 다음 보정 페이지를 다시 선택합니다.
- 디스플레이 색 보정을 실행하는 동안 HoloLens 2가 절전된 경우 나중에 혼합 현실 홈으로 다시 시작되고 디스플레이 밝기 수준은 여전히 희미해지게 됩니다.
- 장치 왼쪽에 있는 밝기 단추를 예상대로 작동하기 전에 몇 번 아래로 누르는 것을 시도해야 할 수 있습니다.
- 지역화가 모든 지역화에 완료되지는 않습니다.

### <a name="default-app-picker"></a>기본 앱 선택기

하이퍼링크를 활성화하거나 설치된 앱이 두 개 이상 있는 파일 형식을 열면 파일 또는 링크 형식을 처리해야 하는 설치된 앱을 선택하라는 새 창이 열립니다. 이 창에서 선택한 앱이 파일 또는 링크 유형 "한 번" 또는 "항상"을 처리하게 선택할 수도 있습니다.

![앱 선택기 창](images/default-app-picker.png)

"항상"을 선택했지만 나중에 특정 파일 또는 링크 형식을 처리하는 앱을 변경하려는 경우 설정 > 앱 에서 저장된 **기본값을 다시 설정할 수 있습니다.** 페이지 아래쪽으로 스크롤하고 "파일 **** 형식에 대한 기본 앱" 및/또는 "링크 형식용 기본 앱"에서 지우기 단추를 선택합니다. 데스크톱 PC의 유사한 설정과 달리 개별 파일 형식 기본값은 다시 설정할 수 없습니다.

### <a name="per-app-volume-control"></a>앱 볼륨 컨트롤당

이제 이 Windows Insider 빌드 사용자는 각 앱의 볼륨 수준을 수동으로 조정할 수 있습니다. 이를 통해 사용자는 필요한 앱에 더 잘 집중하거나 여러 앱을 사용할 때 더 잘 들을 수 있습니다. 원격 지원을 위해 다른 사람을 호출하는 동안 한 앱의 볼륨을 끄는 등의 경우

개별 앱의 볼륨을 설정 **** 시스템 소리로 이동하고 고급 소리 옵션에서 앱 볼륨 및 장치 기본 설정을  ->  ****  ->  **** **선택합니다.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web App

Office Web App이 시작 메뉴의 "모든 앱" 목록에 추가되었습니다. 이 웹앱을 시작 또는 제거에 고정할 수도 있습니다. 이 기능은 웹 앱이기 때문에 를 방문하여 경험하는 기능과 정확히 https://www.office.com 일치합니다. Office Web App 기능은 HoloLens 2에 활성 인터넷 연결이 있는 경우만 사용할 수 있습니다.

**알려진 문제**
- 장치를 초기화하면 Office 웹앱이 제거됩니다.

### <a name="swipe-to-type"></a>스와이프하여 입력

일부 고객은 입력하려는 단어의 모양을 스와이프하여 가상 키보드에서 "입력"하는 것이 더 빠르며 홀로그램 키보드에 대해 이 기능을 미리 보고 있습니다. 홀로그램 키보드의 평면을 통해 손가락의 팁을 전달하고 단어의 모양을 스와이프한 다음 키보드 평면에서 손가락 끝을 철회하여 한 번씩 한 단어를 스와이프할 수 있습니다. 단어 사이에 있는 키보드에서 손가락을 제거하여 스페이스바를 누르지 않고도 단어를 뒤이어 볼 수 있습니다. 키보드에서 손가락의 움직임을 따라 스와이프 후 뒤로 이동이 표시될 경우 이 기능이 작동하고 있는 것을 알 수 있습니다.

휴대폰 디스플레이와 달리 손가락에 대한 저항이 느끼지 않는 홀로그램 키보드의 특성 때문에 이 기능을 사용 및 마스터하기가 까다로울 수 있습니다. 이 기능은 공개 릴리스에 대해 평가 중이기 때문에 사용자 의견이 중요합니다. 기능을 유용하게 찾거나 생성적인 피드백이 있는지 여부에 따라 피드백 허브를 통해 [알려주세요.](hololens-feedback.md)

### <a name="power-menu-from-start"></a>시작 메뉴의 전원 메뉴

사용자가 디바이스를 종료하고 다시 시작할 수 있도록 하는 새 메뉴입니다. 시스템 업데이트를 사용할 수 있는 경우를 표시하는 HoloLens 시작 화면의 표시기입니다.

#### <a name="how-to-use"></a>사용하는 방법

1. 시작 제스처를 사용하여 HoloLens 시작 화면을 열거나 "시작으로 이동"이라고 말하면 됩니다. [](hololens2-basic-usage.md#start-gesture)

2. 사용자 프로필 사진 옆에 있는 타원 아이콘(...)이 표시됩니다.

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 손을 사용하여 사용자 프로필 사진을 선택하거나 음성 명령 "전원"을 선택합니다.

4. 디바이스를 종료, 다시 시작 또는 종료하는 옵션이 있는 메뉴가 나타납니다.

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. HoloLens를 로그인, 다시 시작 또는 종료하려면 메뉴 옵션을 선택합니다. 디바이스가 [단일 Microsoft 계정(MSA)](hololens-identity.md)또는 로컬 계정에 대해 설정된 경우 로그인 옵션을 사용할 수 없습니다.

6. 다른 곳을 터치하거나 시작 제스처로 시작 메뉴를 닫아 메뉴를 닫습니다.

#### <a name="update-indicator"></a>업데이트 표시기

업데이트를 사용할 수 있는 경우 타원 아이콘이 켜지며 업데이트가 다시 시작될 것임이 표시되어 업데이트의 현재 상태도 반영하도록 메뉴 옵션이 변경됩니다.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>로그인 화면에 나열된 여러 사용자

이전에는 로그인 화면에 가장 최근에 로그인한 사용자뿐 아니라 '기타 사용자' 진입점만 표시했습니다. 여러 사용자가 장치에 로그인한 경우 이로 충분하지 않다는 고객 피드백을 수신했습니다. 여전히 사용자 이름을 다시 입력해야 합니다.

이 Windows Insider 빌드에 도입된 **** 경우 PIN 항목 필드 오른쪽에 있는 다른 사용자를 선택하면 로그인 화면에 이전에 장치에 로그인한 여러 사용자가 표시됩니다. 이렇게 하면 사용자가 자신의 사용자 프로필을 선택한 다음 Windows Hello 자격 증명을 사용하여 로그인할 수 있습니다. 계정 추가 단추를 통해 이 다른 사용자 페이지에서 새 사용자를 디바이스에 **추가할 수도** 있습니다.

기타 사용자 메뉴에서 기타 사용자 단추에는 장치에 마지막으로 로그인한 사용자가 표시됩니다. 이 사용자의 로그인 화면으로 돌아가면 이 단추를 선택합니다.

![로그인 화면 기본값](./images/multiusers1.jpg)

<br>

![로그인 화면 다른 사용자](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 외부 마이크 지원

> [!IMPORTANT]
> USB 마이크를 연결하면 입력 장치로 자동으로 **설정되지 않습니다.** USB-C 헤드폰 집합을 연결할 때 사용자는 헤드폰의 오디오가 자동으로 헤드폰으로 리디렉션되는 것이 관찰되지만 HoloLens OS는 다른 입력 장치보다 내부 마이크 배열의 우선 순위를 지정합니다. **USB-C 마이크를 사용하려면 아래 단계를 따릅니다.**

사용자는 소리 설정 패널을 사용하여 USB-C 연결 외부 **마이크를 선택할** 수 있습니다. USB-C 마이크는 통화, 녹음 등에 사용할 수 있습니다.

설정 **앱을** 열고 **시스템 소리를**  >  **선택합니다.**

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 원격 지원과 함께 외부 마이크를 사용하려면 **사용자가**"소리 장치 관리" 하이퍼링크를 클릭해야 합니다.
>
> 그런 다음 드롭다운을 사용하여 외부 마이크를 기본 또는 통신 **기본값으로** **설정합니다.** 기본값을 **선택하면** 외부 마이크가 모든 곳에서 사용됩니다.
>
> 통신 **기본값을** 선택하면 원격 지원 및 기타 통신 앱에서 외부 마이크가 사용되지만 HoloLens 마이크 배열이 다른 작업에 계속 사용될 수 있습니다.

![사운드 장치 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>마이크 Bluetooth 지원은 어떻게 하나요?

안타깝게도 Bluetooth 마이크는 현재 HoloLens 2에서 지원되지 않습니다.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C 마이크 문제 해결

일부 USB-C 마이크는 마이크와 스피커 모두로 ** 잘못 보고합니다. HoloLens가 아니라 마이크에 문제가 있습니다. 이러한 마이크 중 하나를 HoloLens에 연결하면 소리가 손실될 수 있습니다. 다행히 간단한 수정이 있습니다.  

설정 **시스템**소리에서 기본 제공 스피커(아날로그 기능 오디오 드라이버)를 기본 장치로  ->  ****  ->  **** **명시적으로 설정합니다.** **** HoloLens는 마이크를 제거하고 나중에 다시 연결한 경우에도 이 설정을 기억해야 합니다.

![USB-C 마이크 문제 해결](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>키오스크에 대한 방문자 자동 로그온

이 새로운 기능을 사용하면 방문자 계정의 자동 로그온을 키오스크 모드에 사용할 수 있습니다.

AAD가 아닌 구성의 경우 방문자 자동 로그온을 위해 장치를 구성하려면 다음을 실행합니다.

1. 다음을 위한 프로비저닝 패키지를 생성합니다.
    1. 방문자 계정을 **허용하도록 런타임 설정/AssignedAccess를** 구성합니다.
    1. 선택적으로 나중에 관리할 수 있도록 MDM(런타임 **설정/Workplace/Enrollments)에** 장치를 등록합니다.
    1. 로컬 계정을 만들지 않습니다.
1. [프로비저닝 패키지를 적용합니다.](hololens-provisioning.md)

AAD 구성의 경우 사용자는 이러한 변경 없이 현재와 비슷한 결과를 얻을 수 있습니다. 키오스크 모드로 구성된 AAD 가입 장치는 로그인 화면에서 단일 단추 탭으로 방문자 계정에 로그인할 수 있습니다. 방문자 계정에 로그인한 후 시작 메뉴에서 방문자가 명시적으로 서명되거나 장치가 다시 시작될 때까지 장치가 다시 로그인하라는 메시지를 표시하지 않습니다.

사용자 지정 [OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 정책을 통해 방문자 자동 로그온을 관리할 수 있습니다.

- URI 값: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 정책  | 설명   | 구성  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 방문자가 키오스크에 자동 로그온할 수 있습니다.   | 1(예), 0(아니요, 기본값)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>키오스크 모드에서 새 설정 및 에지 앱 사용

키오스크에 [](hololens-kiosk.md)앱을 포함하면 IT 관리자가 종종 앱을 키오스크에 추가하지만 AUMID(앱 사용자 모델 ID)를 사용하게 됩니다. 설정 앱과 Microsoft Edge 앱은 모두 새 앱으로 간주되어 해당 앱에 AUMID를 사용하는 이전 앱 키오스크와 다르기 때문에 새 AUMID를 사용하려면 업데이트해야 합니다.

새 앱을 포함하도록 Kiosk를 수정할 때 새 AUMID를 추가하고 이전 앱을 남겨 두는 것이 좋습니다. 이렇게 하면 사용자가 OS를 업데이트할 때 쉽게 전환할 수 있으며, 키오스크를 의도한 경우 계속 사용하기 위한 새 정책을 받을 필요가 없습니다.

| 앱                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 이전 설정 앱       | HolographicSystemSettings_cw5n1h2txyewy! 앱            |
| 새 설정 앱       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 앱 |
| 이전 Microsoft Edge 앱 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 새 Microsoft Edge 앱 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리를 위한 키오스크 모드 동작 변경

이전 빌드에서 장치에 전역 할당된 액세스와 AAD 그룹 구성원이 할당된 액세스의 조합인 키오스크 구성이 있는 경우 AAD 그룹 구성원 자격 확인에 실패하면 사용자에게[시작](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" 메뉴에 " 아무 것도 표시되지 않습니다.

Windows Insider 릴리스부터 키오스크 환경은 AAD 그룹 키오스크 모드 중 오류가 발생하면 전역 키오스크 구성(있는 경우)으로 변경됩니다.

### <a name="new-settingsuris-for-page-settings-visibility"></a>페이지 설정 표시 여부에 대한 새 설정 URIS

[Windows Holographic 버전 20H2에서는](hololens-release-notes.md#windows-holographic-version-20h2) 설정 앱에 있는 페이지를 제한하기 위해 [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 정책을 추가했습니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스 하지 못하도록 방지 하거나 지정 된 페이지를 제외한 모든 페이지에 대한 작업을 수행하는 데 사용 하는 정책입니다.

페이지 설정 [표시](settings-uri-list.md)여부 를 방문하는 경우 이 CSP를 사용하는 지침과 이전 릴리스에서 사용할 수 있는 URIS 목록을 찾을 수 있습니다.

Windows Insider 빌드에서는 IT 관리자가 관리할 수 있는 사용 가능한 설정 URIS 목록을 확장하고 있습니다. 이러한 UR의 일부는 새 설정 앱 내에서 새로 사용할 수 있는 영역에 대한 것입니다. 설정/PageVisibilityList 정책을 사용하는 경우 다음 목록을 검토하고 필요한 경우 허용되거나 차단된 페이지를 조정합니다.

> [!NOTE]
> **사용 안 례: ms-settings:network-proxy**
>
> 이러한 새 빌드에서 한 설정 페이지는 더 이상 사용하지 않습니다. 이전 네트워크 **& 인터넷**프록시 페이지를 전역  >  **** 설정으로 더 이상 사용할 수 없습니다. 새로운 연결당 프록시 설정은 Network **& Internet**  >  **Wi-Fi**  >  **Properties** 또는 Network & 인터넷 이더넷 **속성에서**찾을  >  **수**  >  **있습니다.**

<br>

| 설정 페이지                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 앱 > 앱 & 기능                               | `ms-settings:appsfeatures`                         |
| 앱 > 앱 & 고급 > 기능          | `ms-settings:appsfeatures-app`                     |
| 오프라인 > 앱                                  | `ms-settings:maps`                                 |
| 오프라인 > 앱 > 지도 다운로드                  | `ms-settings:maps-downloadmaps`                    |
| 디바이스 > 마우스                                      | `ms-settings:mouse`                                |
| 장치 > USB                                        | `ms-settings:usb`                                  |
| 네트워크 & 인터넷 > 비행기 모드                   | `ms-settings:network-airplanemode`                 |
| 개인 > 일반                                    | `ms-settings:privacy-general`                      |
| 개인 > 입력하는 & 개인 정보 보호             | `ms-settings:privacy-speechtyping`                 |
| 개인 > 동작                                     | `ms-settings:privacy-motion`                       |
| 개인 > 스크린샷 테두리                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 개인 > 스크린샷 및 앱                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 시스템 > 배터리                                     | `ms-settings:batterysaver`                         |
| 시스템 > 배터리                                     | `ms-settings:batterysaver-settings`                |
| 시스템 > 소리                                       | `ms-settings:sound`                                |
| 시스템 > 소리 > 볼륨 및 장치 기본 설정 | `ms-settings:apps-volume`                          |
| 시스템 > 소리 > 장치 관리              | `ms-settings:sound-devices`                        |
| 시스템 > 저장소 > 센스 구성         | `ms-settings:storagepolicies`                      |
| 시간 & 언어 > 날짜 & 시간                        | `ms-settings:dateandtime`                          |
| 키보드 & 언어 > 시간                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| 보안 & 업데이트 > 복구 & 다시 설정               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>업데이트된 URIS

이전에는 다음 두 개의 URIS는 사용자가 표시된 페이지로 직접 이동하지 않고 기본 업데이트 페이지만 차단했습니다. 다음 항목이 해당 페이지로 연결될 수 있도록 업데이트되었습니다.

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>설정 앱을 통해 Fallback Diagnostics 구성

이제 설정 앱에서 사용자는 [Fallback Diagnostics의 동작을 구성할 수 있습니다.](hololens-diagnostic-logs.md) 설정 앱에서 개인 정보 **문제**해결 페이지로 이동하여  ->  **** 이 설정을 구성합니다.

> [!NOTE]
> 장치에 대해 구성된 MDM 정책이 있는 경우 사용자는 해당 동작을 다시 구성할 수 없습니다.  

### <a name="share-things-with-nearby-devices"></a>주변 장치와 공유

HoloLens Insider 빌드 20279.1006+를 실행하는 PC 및 기타 HoloLens 2 장치를 포함하여 Windows 10 장치에서 거의 모든 것을 공유합니다. 설정 시스템 공유 **** 환경에서 시도해 보아  ->  ****  ->  **** HoloLens에서 PC로 파일 또는 URL을 공유할 수 있습니다. 자세한 내용은 Windows 10에서 주변 장치와 정보를 공유하는 [방법에 대해 자세히 읽어보아야 합니다.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

이 기능은 [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)를 통해 관리할 수 있습니다.

### <a name="new-os-update-troubleshooter"></a>새 OS 업데이트 문제 해결사

설정 앱 내의 이전 문제 해결사 외에도 OS 업데이트용 새 설정 앱이 추가되어 새로운 문제 해결사도 추가되었습니다. 설정 **업데이트**  ->  **보안 &amp; 문제 해결**Windows  >  ****  >  **업데이트로 이동하고** 시작 을 **선택합니다.** 이렇게 하면 IT 또는 지원과의 문제 해결을 보다 잘 지원하기 위해 OS 업데이트에서 문제를 재현하는 동안 추적을 수집할 수 있습니다.

### <a name="delivery-optimization-preview"></a>배달 최적화 미리 보기

이 HoloLens Insider 업데이트를 통해 비즈니스용 Windows Holographic은 배달 최적화 설정에 대한 초기 미리 보기를 통해 여러 HoloLens 장치에서 다운로드에 대한 대역폭 소비를 줄일 수 있습니다. 권장 네트워크 구성과 함께 이 기능에 대한 자세한 설명은 [Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)업데이트에 대한 배달 최적화 에서 사용할 수 있습니다.

다음 설정은 관리 화면의 일부로 사용하도록 설정되어 있으며 [Intune에서 구성할 수 있습니다.](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

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

이 미리 보기 제공에 대한 몇 가지 주의 사항:

- HoloLens 지원은 OS 업데이트에 대한 이 미리 보기에서만 제한됩니다.
- 비즈니스용 Windows Holographic은 Microsoft 연결된 캐시 끝점에서 HTTP 다운로드 모드 및 다운로드만 [지원됩니다.](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) 현재 HoloLens 장치에 대해 피어 투 피어 다운로드 모드 및 그룹 할당이 지원되지 않습니다.
- HoloLens는 Windows Server Update Services 끝점에 대한 배포 또는 배달 최적화를 지원하지 않습니다.
- 문제 해결에는 연결된 캐시 서버에서 진단을 요구하거나 설정 업데이트 및 보안 문제 해결 **** Windows 업데이트를 통해 HoloLens의 HoloLens에  >  **&**  >   ****  >   **수집해야 합니다.**

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 개선 사항 및 수정 사항:

- [오프라인 진단에는](hololens-diagnostic-logs.md#offline-diagnostics) 일련 번호 및 OS 버전에 대한 추가 장치 정보도 포함됩니다.






## <a name="start-receiving-insider-builds"></a>Insider 빌드 수신 시작

> [!NOTE]
> 최근에 업데이트하지 않은 경우 장치를 다시 시작하여 상태를 업데이트하고 최신 빌드를 얻습니다.
> - "다시부팅 장치" 음성 명령은 잘 작동합니다. 
> - 설정/Windows Insider 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> We have a bug on the back-end that you may encountered and this will get you back on track.

HoloLens 2 장치에서 설정 **** 업데이트 &  >  ****  >  **Windows Insider Program으로 이동하고** **시작을 선택합니다.** Windows Insider로 등록하는 데 사용한 계정을 연결합니다.

Windows 내부자는 이제 채널로 이동하고 있습니다. 빠른 **링은** 개발자 채널이 **되고,** **슬로우** 링은 베타 채널이 **되고,** **릴리스** 미리 보기 링은 릴리스 미리 보기 **채널이 됩니다.** 매핑의 모양은 다음과 같습니다.

![Windows Insider Channels 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에 [Windows Insider 채널](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 소개를 참조하세요.

그런 다음 **Windows의 활성**개발을 선택하고 개발자 **** 채널 또는 **** 베타 채널 빌드를 받을지 여부를 선택하고 프로그램 용어를 검토합니다.

지금 **다시 > 확인을 선택하여** 완료합니다. 장치를 다시 시작한 후 설정 > 업데이트 & 보안 > **업데이트** 확인으로 이동하여 최신 빌드를 다운로드합니다.

### <a name="update-error-0x80070490-work-around"></a>해결 0x80070490 오류 업데이트
개발자 또는 베타 0x80070490 업데이트할 때 업데이트 오류가 발생하는 경우 다음과 같은 단기적인 해결 방법을 시도해 보세요. 내부자 채널을 이동하고 업데이트를 선택하고 내부자 채널을 다시 이동하는 과정이 진행됩니다.

#### <a name="stage-one---release-preview"></a>1단계 - 릴리스 미리 보기
1.  설정, 보안 & 업데이트, Windows Insider Program, 릴리스 미리 보기 **채널을 선택합니다.**
2.  설정, 업데이트 & 보안, Windows 업데이트, **업데이트 확인**. 업데이트 후 2단계로 계속 진행합니다.

#### <a name="stage-two---dev-channel"></a>2단계 - 개발자 채널
1. 설정, & 업데이트, Windows Insider Program, **개발자 채널을 선택합니다.**
2. 설정, 업데이트 & 보안, Windows 업데이트, **업데이트 확인**.

## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 길
플라이트 서명된 ffu로 테스트하려면 플라이트 서명된 ffu를 깜박이기 전에 먼저 플라이트 잠금 해제를 실행해야 합니다.
1. PC에서:

    1. 에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.
    
    1. Microsoft Store에서 ARC(고급 복구 도우미)를 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 설치합니다. .
    
1. HoloLens - 플라이트 **** 잠금 해제: 보안 Windows & 프로그램으로 설정 업데이트 열기 후 장치를 다시  >  ****  >  **** 시작합니다.

1. Flash FFU - 이제 ARC를 사용하여 플라이트 서명된 FFU를 플래시할 수 있습니다.

## <a name="provide-feedback-and-report-issues"></a>피드백 제공 및 문제 보고

HoloLens에서 피드백 허브 앱을 사용하여 피드백을 제공하고 문제를 보고하세요. [](hololens-feedback.md) 피드백 허브를 사용하면 엔지니어가 문제를 빠르게 디버그하고 해결하는 데 도움이 되는 필요한 모든 진단 정보가 포함되어 있습니다.  중국어 및 일본어 버전의 HoloLens 관련 문제는 동일한 방식으로 보고해야 합니다.

> [!NOTE]
> 피드백 허브가 문서 폴더에 액세스할지 묻는 메시지를 수락해야 합니다(메시지가 표시될 때 예 선택). ****

## <a name="note-for-developers"></a>개발자용 참고 사항

HoloLens의 Insider 빌드를 사용하여 응용 프로그램을 개발할 것을 환영합니다.  [HoloLens 개발자 설명서를 확인하여](https://developer.microsoft.com/windows/mixed-reality/development) 시작하세요. 이러한 지침은 HoloLens의 Insider 빌드에서 작동됩니다.  HoloLens 개발에 이미 사용 중이면 Visual Studio 빌드와 동일한 빌드를 사용할 수 있습니다.

## <a name="stop-receiving-insider-builds"></a>Insider 빌드 수신 중지

Windows Holographic의 Insider 빌드를 더 이상 받지 않는 경우 HoloLens가 프로덕션 빌드를 실행 중일 때 옵트아웃하거나 고급 복구 도우미를 사용하여 장치를 Windows Holographic의 비 Insider 버전으로 복구할 수 있습니다. [](hololens-recovery.md)

> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 등록하지 않은 사용자가 파란색 화면을 경험하는 알려진 문제가 있습니다. 이후 장치를 수동으로 복구해야 합니다. 영향이 있을지 아니면 그렇지 않을지에 대한 자세한 내용은 이 알려진 문제 에서 자세히 [참조하시기 바랍니다.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

HoloLens에서 프로덕션 빌드를 실행 중인지 확인:

1. 설정 > 시스템 > **정보로**이동하여 빌드 번호를 확인합니다.

1. [프로덕션 빌드 번호에 대한 릴리스 노트를 참조합니다.](hololens-release-notes.md)

Insider 빌드를 옵트아웃(opt out)하는 경우:

1. 프로덕션 빌드를 실행하는 HoloLens에서 설정 > 업데이트 & Windows > 프로그램으로 이동한 다음 **Insider 빌드**중지를 **선택합니다.**

1. 지침에 따라 장치를 옵트아웃합니다.
