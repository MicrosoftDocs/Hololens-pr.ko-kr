---
title: Microsoft HoloLens 용 Insider preview
description: Insider 빌드를 시작 하 고 다음 주요 HoloLens 운영 체제 업데이트에 대 한 귀중 한 피드백을 제공 하는 방법에 대해 알아봅니다.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309605"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens 용 Insider preview

HoloLens의 최신 Insider Preview 빌드를 시작 합니다. 간단 하 게 [시작](hololens-insider.md#start-receiving-insider-builds) 하 고 HoloLens의 다음 주요 운영 체제 업데이트에 대 한 유용한 피드백을 제공할 수 있습니다.

## <a name="windows-insider-release-notes"></a>Windows 참가자 릴리스 정보

Windows 참가자에 게 새 기능을 다시 시작 하는 것이 좋습니다. 새 빌드는 최신 업데이트에 대 한 개발 채널에 대 한 플 라이팅 됩니다. Windows 참가자 빌드에 더 많은 기능과 업데이트를 추가 하는 경우이 페이지를 계속 업데이트 합니다.  이러한 업데이트를 현실에 맞게 혼합할 수 있습니다.

이 기능 업데이트에는 두 대상 대상에 대 한 기능이 포함 되어 있습니다. 최종 사용자가 장치의 모든 사용자가 사용할 수 있는 기능 및 IT 관리자가 구성할 수 있는 새로운 장치 관리 옵션입니다. 아래 기능 테이블은 각 새 기능을 사용할 수 있는 사용자를 대상으로 합니다. IT 관리자 인 경우 [It 관리자-업데이트 검사 목록](#it-admin---update-checklist) 을 확인 하세요.

> [!IMPORTANT]
> 이전에 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용 하는 경우 이러한 앱을 다른 앱 ID를 사용 하는 새 앱으로 대체 했습니다. 아래의 [키오스크 모드에서 새 앱에 대 한 새 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 를 읽을 것을 적극 권장 합니다. 그러면 키오스크에서 설정 앱을 계속 유지 하거나 새 Microsoft Edge 앱을 포함할 수 있습니다.

<br>

| 기능 이름                                              | 간단한 설명                                                                      | 대상 사용자 | 빌드에서 사용 가능 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [새 Microsoft Edge](#introducing-the-new-microsoft-edge) | 새 Chromium 기반 Microsoft Edge는 이제 HoloLens 2에서 사용할 수 있습니다.                         | 최종 사용자 | 20279.1006 |
| [WebXR 및 360 뷰어](#webxr-and-360-viewer)             | 몰입 형 웹 환경 및 360 비디오 재생 사용해 보기                                           | 최종 사용자 | 20289.1000 |
| [새 설정 앱](#new-settings-app)                     | 레거시 설정 앱이 새 기능 및 설정으로 업데이트 된 버전으로 대체 되 고 있습니다. | 최종 사용자 | 20279.1006 |
| [디스플레이 색 보정](#display-color-calibration)   | HoloLens 2 디스플레이에 대 한 대체 색 프로필을 선택 합니다.                                | 최종 사용자 | 20293.1000 |
| [기본 앱 선택기](#default-app-picker)                 | 각 파일 또는 링크 형식에 대해 시작할 앱 선택                                      | 최종 사용자 | 20279.1006 |
| [앱 당 볼륨 컨트롤](#per-app-volume-control) |  시스템 볼륨과 독립적으로 앱 수준 볼륨 제어 | 최종 사용자 | 20293.1000 |
| [Office 웹 앱](#office-web-app)                         | 이제 Office 웹 앱에 대 한 바로 가기가 "모든 앱"에 나열 됩니다.                                   | 최종 사용자 | 20279.1006 |
| [형식으로 살짝 밀기](#swipe-to-type)                           | 손가락의 팁을 사용 하 여 holographic 키보드의 "살짝 밀기" 단어를 사용 합니다.                        | 최종 사용자 | 20279.1006 |
| [시작 메뉴의 전원 메뉴](#power-menu-from-start) | 시작 메뉴에서 HoloLens 장치를 다시 시작 하 고 종료 합니다. | 최종 사용자 | 20293.1000 |
| [로그인 화면에 나열 된 여러 사용자](#multiple-users-listed-on-sign-in-screen) | 로그인 화면에 여러 사용자 계정 표시 | 최종 사용자 | 20293.1000 |
| [USB-C 외부 마이크 지원](#usb-c-external-microphone-support) | 앱 및/또는 원격 지원에는 USB-C 마이크를 사용 합니다.| 최종 사용자 | 20279.1006 |
| [키오스크를 위한 방문자 자동 로그온](#visitor-auto-logon-for-kiosks)                          | 방문자 계정에 대해 키오스크 모드에 대 한 자동 로그온을 사용 하도록 설정 합니다.                         | IT 관리자 | 20279.1006                 |
| [키오스크 모드의 새 앱에 대 한 새 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 새 설정 및에 지 앱의 AUMIDs | IT 관리자 | 20279.1006 |
| [향상 된 키오스크 모드 오류 처리](#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드는 빈 시작 메뉴 전에 전역 할당 된 액세스를 찾습니다. | IT 관리자 | 20279.1006 |
| [페이지 설정 표시에 대 한 새 SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20 + 설정/PageVisibilityList 정책에 대 한 새 SettingsURIs | IT 관리자 | 20289.1000 |
| [대체 진단 구성](#configuring-fallback-diagnostics-via-settings-app) | 설정 앱에서 대체 진단 동작 설정 | IT 관리자 | 20279.1006 |
| [주변 장치와 항목 공유](#share-things-with-nearby-devices) | HoloLens에서 PC로 파일 또는 Url 공유 | 모두 | 20279.1006 |
| [새 OS 업데이트 문제 해결사](#new-os-update-troubleshooter) | OS 업데이트 설정의 새 문제 해결사 | IT 관리자 | 20279.1006 |
| [배달 최적화 미리 보기](#delivery-optimization-preview) | 여러 HoloLens 장치에서 다운로드에 대 한 대역폭 사용량 감소 | IT 관리자 | 20301.1000 |
| [업데이트의 향상 된 기능 및 수정 사항](#improvements-and-fixes-in-the-update) | 업데이트의 추가 수정 사항입니다. | 모두 | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 관리자-업데이트 검사 목록

이 검사 목록은 현재 장치 관리 구성에 영향을 줄 수 있는이 기능 업데이트에 추가 되는 기능 또는 사용을 시작 하려는 새로운 기능을 알려 주는 데 도움이 됩니다.

#### <a name="updates-to-kiosk-mode"></a>키오스크 모드 업데이트

[**키오스크 모드의 새 앱에 대 한 새 AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

이전에 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용 하는 경우 이러한 앱을 다른 앱 ID를 사용 하는 새 앱으로 대체 했습니다. 아래의 [키오스크 모드에서 새 앱에 대 한 새 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 를 읽을 것을 적극 권장 합니다. 그러면 키오스크에서 설정 앱을 계속 유지 하거나 새 Microsoft Edge 앱을 포함할 수 있습니다.

이러한 변경 내용을 지금 수행 하 고 모든 장치에 배포 하 고 업데이트를 더욱 원활 하 게 전환할 수 있습니다.

[**키오스크를 위한 방문자 자동 로그온**](#visitor-auto-logon-for-kiosks)

이제 방문자가 자동으로 키오스크에 로그인 할 수 있습니다. 이 동작은 기본적으로 설정 되어 있지만 관리 하거나 사용 하지 않도록 설정할 수 있습니다.

[**향상 된 키오스크 모드 오류 처리**](#kiosk-mode-behavior-changes-for-handling-of-failures)

로그인 된 AAD 사용자의 AAD 그룹 멤버 자격이 성공적으로 확인 되지 않으면 시작 메뉴에 전역 키오스크 구성 (있는 경우)이 사용 되 고 그렇지 않으면 사용자에 게 빈 시작 메뉴가 표시 됩니다. 빈 시작 메뉴는 직접 설정할 수 있는 구성이 아니라, 키오스크를 사용 하는 경우, 사용자의 구성에 적용 될 수 있거나 할당 된 액세스 구성에 대 한 새로운 조정을 수행 하는 경우에 대 한 지원 부서에이 새로운 처리를 알릴 수 있습니다.

#### <a name="updates-to-page-settings-visibility"></a>페이지 설정 표시에 대 한 업데이트

[**페이지 설정 표시에 대 한 새 SettingsURIs**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

현재 [페이지 설정 표시 유형을](settings-uri-list.md) 사용 하는 경우 허용 또는 차단 된 기존 uri를 조정 하는 것이 좋습니다.

#### <a name="updates-for-your-wdac-policy"></a>WDAC 정책에 대 한 업데이트

이전에 WDAC를 통해 Microsoft Edge를 차단한 경우에는 WDAC 정책을 업데이트 해야 합니다. [다음을 검토](#using-wdac-to-block-new-microsoft-edge) 하 고 제공 된 샘플 코드를 사용 하세요.

#### <a name="enable-new-endpoints-for-edge"></a>Edge에 대 한 새 끝점 사용

프록시 또는 방화벽과 같은 네트워크 끝점 구성을 포함 하는 인프라가 있는 경우 [새 Microsoft Edge 앱에 대해 이러한 새 끝점을 사용 하도록 설정 하세요.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>새로 구성 가능한 항목

- [대체 진단 구성](#configuring-fallback-diagnostics-via-settings-app)
  - 대체 진단을 수집할 수 있는 경우 및 사용자를 구성할 수 있습니다.
- [주변 장치와 항목 공유](#share-things-with-nearby-devices)
  - 가까운 새 공유 기능을 사용 하지 않도록 설정할 수 있습니다.
- [새 Microsoft Edge에 대 한 정책 설정 구성](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Microsoft Edge에 대해 새로 제공 되는 구성을 검토 합니다.

#### <a name="new-diagnostic-tool"></a>새 진단 도구

- [새 OS 업데이트 문제 해결사](#new-os-update-troubleshooter)
  - OS 업데이트와 관련 된 로그 수집

### <a name="introducing-the-new-microsoft-edge"></a>새 Microsoft Edge 소개

![새 Microsoft Edge 로고에 대 한 레거시 Microsoft Edge 로고의 애니메이션](images/new-edge.gif)

새 Microsoft Edge는 [Chromium 오픈 소스 프로젝트를 채택](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 하 여 고객에 게 더 나은 호환성을 만들고 웹 개발자를 위한 웹의 조각화를 줄일 수 있습니다.

이 Insider preview를 사용 하는 경우 처음에는 새 Microsoft Edge를 HoloLens 2 명의 고객에 게 제공할 수 있습니다. 새 Microsoft Edge는 결국 HoloLens 2에서 레거시 Microsoft Edge를 대체 하지만 두 브라우저를 모두 현재 참가자에 게 제공 합니다. 새 Microsoft Edge 또는 [피드백 허브](hololens-feedback.md)를 통해 사용자 의견 **보내기** 기능을 통해 팀과 의견 및 버그를 공유 하세요.

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>새 Microsoft Edge 시작

Microsoft Edge에는 두 가지 버전의 Microsoft edge 새 microsoft edge ![ 새 microsoft edge 아이콘 ](images/new_edge_logo.png) (파란색 및 녹색 소용돌이 아이콘으로 표시) 및 레거시 microsoft edge (흰색 "e" 아이콘으로 표시)가 있습니다. 새 Microsoft Edge가 시작 메뉴에 고정 되 고 웹 링크를 활성화할 때 자동으로 시작 됩니다. 레거시 Microsoft Edge를 기본 웹 브라우저로 되돌리려면 [기본 앱을 다시 설정](#default-app-picker)하는 방법에 대 한 지침을 참조 하세요.

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
> 두 개 이상의 새로운 Microsoft Edge 정책이 HoloLens 2에서 작동 *하지* 않습니다.
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens의 새 Microsoft Edge 2에서 제공 되는 것은 무엇 인가요?

새 Microsoft Edge는 HoloLens 2와 같은 UWP 전용 장치에서 실행 되도록 허용 하는 새 UWP 어댑터 계층을 포함 하는 네이티브 Win32 앱 이기 때문에 일부 기능을 즉시 사용할 수 없습니다. 향후 몇 개월 동안 새로운 시나리오와 기능을 지원할 예정 이므로 최신 정보는이 공간을 확인 하세요.

**작동 해야 하는 시나리오 및 기능은 다음과 같습니다.**
- 첫 실행 경험, 프로필에 로그인 및 동기화
- 웹 사이트가 예상 대로 렌더링 및 작동 해야 함
- 대부분의 브라우저 기능 (즐겨찾기, 기록 등)은 예상 대로 작동 합니다.
- 어둡게 모드
- 장치에 웹 앱 설치
- 확장 설치 (HoloLens 2에서 제대로 작동 하지 않는 확장을 사용 하는 경우 알려 주세요.)
- PDF 보기 및 표시
- 단일 브라우저 창의 공간 소리
- 자동 및 수동 브라우저 업데이트
- "PDF에 저장" 옵션을 사용 하 여 인쇄 메뉴에서 PDF 저장
- WebXR 및 360 뷰어 확장
- 환경에 배치 되는 여러 창에서 검색할 때 올바른 창으로 콘텐츠 복원

**작동 하지 않는 시나리오 및 기능은 다음과 같습니다.**
- 동시 오디오 스트림을 사용 하는 여러 창의 공간 소리
- "이 항목을 참조 하세요."
- 인쇄

**주요 브라우저의 알려진 문제:**
- 개별 Wi-Fi 연결을 대상으로 하는 프록시 정책 인 Wi-Fi 프록시 구성은 현재 새 Microsoft Edge에서 작동 하지 않습니다. OS 업데이트의 공개 릴리스 전에이 문제를 차단 해제 하기 위해 적극적으로 노력 하 고 있습니다.
- Holographic 키보드의 돋보기 미리 보기가 새 Microsoft Edge에 대해 사용 하지 않도록 설정 되었습니다. 확대를 올바르게 수행 하 고 나면 향후 업데이트에서이 기능을 다시 사용 하는 것이 좋습니다.
- 일본어 키보드의 두 문자는 새 Microsoft Edge에서 예상 대로 작동 하지 않습니다. 이 문제는 근본 원인이 되었으며 곧 수정 해야 합니다.
- Microsoft Store 앱의 웹 링크가 브라우저를 시작할 수 없습니다.
- 다른 브라우저 창이 열려 있고 활성 상태인 경우 잘못 된 브라우저 창에서 오디오를 재생할 수 있습니다. 오디오를 재생할 수 없는 다른 활성 창을 닫으면이 문제를 해결할 수 있습니다.
- "사용자가 [팔 로우" 모드](hololens2-basic-usage.md#follow-me-stop-following)의 브라우저 창에서 오디오를 재생 하는 경우 "사용자 팔 로우" 모드를 사용 하지 않도록 설정 하면 오디오가 계속 재생 됩니다. "나 팔 로우" 모드를 사용 하지 않도록 설정 하기 전에 오디오 재생을 중지 하거나 **X** 단추를 사용 하 여 창을 닫으면이 문제를 해결할 수 있습니다.
- 활성 Microsoft Edge 창과의 상호 작용으로 인해 다른 2D 앱 창이 예기치 않게 비활성화 될 수 있습니다. 이러한 창은 다시 상호 작용 하 여 다시 활성화할 수 있습니다.
- 다른 앱에서 웹 링크를 열거나 Pdf와 같은 특정 유형의 문서를 열면 웹 링크 또는 파일 링크의 콘텐츠로 만든 새 탭 외에도 두 번째 빈 탭이 브라우저에서 열립니다. 추가 빈 탭을 닫아이 문제를 해결할 수 있습니다.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider 채널

Microsoft Edge 팀은 Edge Insider community에서 사용할 수 있는 세 가지 미리 보기 채널 (베타, 개발 및 카나리아)을 만듭니다. 미리 보기 채널을 설치 하면 HoloLens 2에서 릴리스된 버전의 Microsoft Edge가 제거 되지 않으며, 동시에 둘 이상을 설치할 수 있습니다. 

[Microsoft Edge insider 홈 페이지](https://www.microsoftedgeinsider.com) 를 방문 하 여 edge insider community에 대해 자세히 알아보세요. 다른 Edge Insider 채널에 대 한 자세한 내용을 알아보고 시작 하려면 [Edge 참가자 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문 하세요.

HoloLens 2에 Microsoft Edge Insider 채널을 설치 하는 데 사용할 수 있는 몇 가지 방법이 있습니다.

**장치에 직접 설치 (현재는 관리 되지 않는 장치 에서만 사용 가능)**
  1. HoloLens 2에서 [Edge 참가자 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문 합니다.
  1. 설치 하려는 Edge Insider channel에 대해 **HoloLens 다운로드 2** 단추를 선택 합니다.
  1. Edge 다운로드 큐 또는 장치의 "다운로드" 폴더 (파일 탐색기 사용)에서 다운로드 한 msix 파일을 시작 합니다.
  1. [앱 설치 관리자](app-deploy-app-installer.md) 가 시작 됩니다.
  1. **설치** 단추를 선택합니다.
  1. 설치가 완료 되 면 시작 메뉴의 **모든 앱** 목록에서 Microsoft Edge Beta, Dev 또는 카나리아를 별도의 항목으로 찾을 수 있습니다.

**Windows Device Portal을 사용 하 여 PC를 통해 설치 (HoloLens 2에서 [개발자 모드](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 를 사용 하도록 설정 해야 함)**
  1. PC에서 [Edge 참가자 다운로드 페이지](https://www.microsoftedgeinsider.com/download)를 방문 합니다.
  1. 설치할 Edge Insider channel에 대해 "Windows 10 다운로드" 단추 옆에 있는 **드롭다운 화살표 단추** 를 선택 합니다.
  1. 드롭다운 메뉴에서 **HoloLens 2** 를 선택 합니다.
  1. PC의 "다운로드" 폴더 (또는 쉽게 찾을 수 있는 다른 폴더)에. msix 파일을 저장 합니다.
  1. PC에서 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 을 사용 하 여 HoloLens 2에서 다운로드 한 msix 파일을 설치 합니다.
  1. 설치가 완료 되 면 시작 메뉴의 **모든 앱** 목록에서 Microsoft Edge Beta, Dev 또는 카나리아를 별도의 항목으로 찾을 수 있습니다.

> [!NOTE]
> HoloLens 2 용 Windows Insider preview를 실행 하는 동안 장치의 Microsoft Edge 버전이 Microsoft Edge Insider 채널의 일부 (또는 모두)에서 사용할 수 있는 것 보다 높을 수 있습니다. 이는 HoloLens 2에서 웹 브라우저를 대상으로 하는 새로운 기능 및 수정 사항을 최대한 빨리 Windows 참가자에 게 제공 하는 것입니다. 다음 Windows 업데이트의 공용 릴리스 직후에 Microsoft Edge Insider channel 빌드는 HoloLens 2의 Microsoft Edge 버전을 초과할 하 고 앞으로 유지 됩니다.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>새 Microsoft Edge를 차단 하기 위해 WDAC 사용

새 Microsoft Edge 앱을 차단 하도록 해당 [WDAC 정책을](windows-defender-application-control-wdac.md) 업데이트 하려는 IT 관리자의 경우 정책에 다음을 추가 해야 합니다.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>새 Microsoft Edge에 대 한 끝점 관리

일부 환경에는 고려 사항으로 고려할 네트워크 제한이 있을 수 있습니다. 새에 지에 부드러운 환경을 보장 하려면 [이러한 Microsoft 끝점을 사용 하도록 설정 하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

[HoloLens에 대해](hololens-offline.md)현재 사용할 수 있는 끝점에 대해 자세히 알아보세요.

### <a name="webxr-and-360-viewer"></a>WebXR 및 360 뷰어

*Windows 참가자 빌드 20289.1000에 추가 됨*

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
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [익스프레스](https://constructarca.de/game/barista-express/)
- [WebXR 그리기](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 뷰어를 사용 하는 방법

1. YouTube의 360 수준 비디오로 이동 합니다.
1. 비디오 프레임에서 혼합 현실 헤드셋 단추를 선택 합니다.

    ![360 뷰어를 활성화 하는 단추](images/enter-360-viewer.jpg)

1. 특정 도메인에서 처음 360 Viewer를 시작 하려고 하면 브라우저에서 몰입 형 보기에 대 한 동의를 요청 합니다. **허용** 을 선택 합니다.
1. [공기 탭](hololens2-basic-usage.md#select-using-air-tap) 하 여 재생 컨트롤을 표시 합니다. [손 광선 및 air 탭](hololens2-basic-usage.md#select-using-air-tap) 을 사용 하 여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 설정/해제, 환경 중지 (몰입 형 보기 종료)를 사용 합니다. 몇 초 동안 활동이 없으면 재생 컨트롤이 사라집니다.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR 및 360 Viewer의 알려진 문제
- WebXR 환경의 복잡도에 따라 프레임 속도는 삭제 또는 끊길 수 있습니다.
- WebXR에서의 트레일러 식에 대 한 지원은 기본적으로 사용 하도록 설정 되어 있지 않습니다. 개발자는 `edge://flags` "WebXR 손을 입력"을 설정 하 여을 통해 지원을 사용할 수 있습니다.
- WebXR 또는 360 뷰어 환경을 종료할 때 혼합 현실 홈의 holograms에 30 초 이상 걸릴 수 있습니다.
- 360 YouTube 이외의 웹 사이트의 비디오는 예상 대로 작동 하지 않을 수 있습니다.
- 현재 HoloLens 2의 360 뷰어에서 캡션을 사용할 수 없습니다. 향후 업데이트에서이 기능을 사용 하도록 계획 합니다.
- 360 Viewer에서 비디오를 일시 중지 하면 비디오가 렌더링 되지 않지만 재생 단추를 선택 하면 재생이 올바르게 다시 시작 됩니다.
- 360 Viewer의 "다음 비디오" 단추는 현재 작동 하지 않습니다.
- 2D 비디오를 몰입 형 "극장" 모드로 재생할 수 있지만 프레임 속도가 30fps 미만일 수 있습니다.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR 및 360 뷰어에 대 한 피드백 제공

새 Microsoft Edge의 **사용자 의견 보내기** 기능을 통해 팀과 의견 및 버그를 공유 하세요.

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
- 다른 사용자 > 계정: 장치 소유자는 사용자를 추가 하 고, 표준 사용자를 장치 소유자로 업그레이드 하 고, 장치 소유자를 표준 사용자로 다운 그레이드 하 고, 사용자를 제거할 수 있습니다.
- 편리한 액세스: 텍스트 크기와 일부 시각적 효과를 변경 합니다.

**알려진 문제**
- 이전에 배치한 설정 창이 제거 됩니다 (위의 참고 사항 참조).
- 더 이상 설정 앱을 사용 하 여 장치 이름을 바꿀 수 없습니다. IT 관리자는 [Windows Autopilot For HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) 장치 이름 템플릿 또는 MDM [devdetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername 노드를 사용 하 여 장치 이름을 바꿀 수 있습니다.
- 이더넷 페이지에는 항상 가상 이더넷 장치 ("UsbNcm")가 표시 됩니다.
- 새 Microsoft Edge에 대 한 배터리 사용량은 UWP 어댑터 계층에서 지원 되는 Win32 데스크톱 응용 프로그램의 특성으로 인해 정확 하지 않을 수 있습니다 (곧 해결 되지 않음).

### <a name="display-color-calibration"></a>디스플레이 색 보정

*Windows 참가자 빌드 20293.1000에 추가 됨*

이 새로운 설정을 사용 하 여 HoloLens 2 디스플레이에 대 한 대체 색 프로필을 선택할 수 있습니다. 이렇게 하면 색이 더 정확 하 게 표시 될 수 있습니다. 특히 디스플레이 밝기 수준이 낮습니다. 디스플레이 색 보정은 시스템 > 보정 페이지의 설정 앱에서 찾을 수 있습니다.

> [!NOTE]
> 이 설정은 새 색 프로필을 표시 펌웨어에 저장 하므로 각 사용자 계정에 고유 하지 않은 장치 단위 설정입니다.

#### <a name="how-to-use-display-color-calibration"></a>표시 색 보정을 사용 하는 방법

1. **설정** 앱을 시작 하 고 **시스템 > 보정** 으로 이동 합니다.
1. **디스플레이 색 보정** 에서 **디스플레이 색 보정 실행** 단추를 선택 합니다.
1. 디스플레이 색 보정 환경이 시작 되 고 센터의 위치가 올바른지 확인 하는 것이 좋습니다.
1. 명령 대화 상자를 진행 한 후에는 디스플레이가 자동으로 30% 밝기까지 흐리게 표시 됩니다.
    > [!TIP]
    > 사용자 환경에서 흐리게 표시 되는 장면을 표시 하는 데 문제가 있는 경우 장치의 왼쪽에 있는 밝기 단추를 사용 하 여 HoloLens 2의 밝기 수준을 수동으로 조정할 수 있습니다.
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

#### <a name="how-to-reset-color-profile"></a>색 프로필을 다시 설정 하는 방법

HoloLens 2에 저장 된 사용자 지정 색 프로필을 만족 하지 않는 경우 장치의 원래 색 프로필을 복원할 수 있습니다.
1. **설정** 앱을 시작 하 고 **시스템 > 보정** 으로 이동 합니다.
1. **디스플레이 색 보정** 에서 **기본 색 프로필로 다시 설정** 단추를 선택 합니다.
1. 대화 상자가 열리면 HoloLens 2를 다시 시작 하 고 변경 내용을 적용할 준비가 되 면 **다시 시작** 을 선택 합니다.

#### <a name="top-display-color-calibration-known-issues"></a>위쪽 디스플레이 색 보정 알려진 문제

- 설정 페이지에서 색 프로필이 마지막으로 변경 된 시기를 알려 주는 상태 문자열은 설정의 해당 페이지를 다시 로드할 때까지 만료 됩니다.
    - 해결 방법: 다른 설정 페이지를 선택한 다음 보정 페이지를 다시 선택 합니다.

### <a name="default-app-picker"></a>기본 앱 선택기

하이퍼링크를 활성화 하거나 둘 이상의 설치 된 앱이 있는 파일 형식을 열 때이를 지 원하는 경우, 파일 또는 링크 형식을 처리 해야 하는 설치 된 앱을 선택 하 라는 새 창이 표시 됩니다. 이 창에서 선택한 앱이 파일 또는 링크 형식 "Once" 또는 "Always"를 처리 하도록 선택할 수도 있습니다.

![앱 선택기 창](images/default-app-picker.png)

"항상"을 선택 했지만 나중에 특정 파일 또는 링크 형식을 처리 하는 앱을 변경 하려는 경우 **설정 > 앱** 에서 저장 된 기본값을 다시 설정할 수 있습니다. 페이지 아래쪽으로 스크롤하여 "파일 형식에 대 한 기본 앱" 및/또는 "링크 형식에 대 한 기본 앱" 아래에서 **지우기** 단추를 선택 합니다. 데스크톱 Pc의 비슷한 설정과 달리 개별 파일 유형 기본값은 다시 설정할 수 없습니다.

### <a name="per-app-volume-control"></a>앱 당 볼륨 컨트롤

이제이 Windows 참가자 빌드 사용자는 각 앱의 볼륨 수준을 수동으로 조정할 수 있습니다. 이렇게 하면 사용자가 필요한 앱에 더 잘 집중 하거나 여러 앱을 사용 하는 경우 더 잘 듣지 못합니다. 다른 사용자가 다른 사용자의 원격 지원을 위해 다른 사용자를 호출 하는 동안 한 앱의 볼륨을 해제 해야 합니다.

개별 앱의 볼륨을 설정 하려면 **설정**  ->  **시스템**  ->  **소리** 로 이동 하 고 고급 소리 옵션에서 **앱 볼륨 및 장치 기본 설정** 을 선택 합니다.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office 웹 앱

>[!NOTE]
>Windows 참가자 빌드 20325.1000을 기반으로 Office 웹 앱은 더 이상 미리 설치 되지 않으며 OS 업데이트의 예정 된 공개 릴리스에 대해 미리 설치 되지 않습니다. Office 웹 앱을 설치 하려면를 방문 하 여 https://www.office.com 주소 표시줄에서 **사용할 수 있는 앱** 또는 **Office 설치** 단추를 선택 합니다. **설치** 를 선택 하 여 확인 합니다.

Office 웹 앱이 시작 메뉴의 "모든 앱" 목록에 추가 되었습니다. 이 웹 앱은 시작 또는 제거에 고정 될 수도 있습니다. 웹 앱 이기 때문에 해당 기능은 방문 하 여 발생 하는 것과 정확히 일치 https://www.office.com 합니다. Office 웹 앱 기능은 HoloLens 2에 활성 인터넷 연결이 있는 경우에만 사용할 수 있습니다.

**알려진 문제**
- 장치를 다시 설정 하면 Office 웹 앱이 제거 됩니다.

### <a name="swipe-to-type"></a>형식으로 살짝 밀기

일부 고객은 입력 하려는 단어의 셰이프를 살짝 밀어 holographic 키보드에 대해이 기능을 미리 보는 방법으로 가상 키보드에서 "유형"을 빠르게 찾을 수 있습니다. Holographic 키보드 평면을 통해 손가락의 팁을 전달 하 여 한 번에 한 단어씩 이동 하 고, 해당 단어의 형태를 살짝 민 다음 키보드 평면에서 손가락의 팁을 입출금 계좌 수 있습니다. 단어 사이에서 키보드에서 손가락을 제거 하 여 스페이스바를 누르지 않고도 후속 단어를 살짝 밀기 할 수 있습니다. 키보드에서 손가락의 움직임에 따라 살짝 밀기 내역이 표시 되 면 기능이 작동 하는 것을 알 수 있습니다.

이 기능을 사용 하는 것은 holographic 키보드의 특성으로 인해 손가락에 대해 저항 하지 않는 (휴대폰 디스플레이와 달리) 사용 하기 어려울 수 있습니다. 공개 릴리스를 위해이 기능을 평가 하 고 있으므로 사용자 의견은 중요 합니다. 기능이 유용 하거나 건설적인 피드백이 있는 경우 [피드백 허브](hololens-feedback.md)를 통해 알려 주세요.

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

이 Windows 참가자 빌드에서 도입 된 PIN 입력 필드의 오른쪽에 있는 **다른 사용자** 를 선택할 때 로그인 화면에는 이전에 장치에 로그인 한 사용자가 있는 여러 사용자가 표시 됩니다. 그러면 사용자가 자신의 사용자 프로필을 선택 하 고 해당 Windows Hello 자격 증명을 사용 하 여 로그인 할 수 있습니다. **계정 추가** 단추를 통해 다른 사용자 페이지에서 장치에 새 사용자를 추가할 수도 있습니다.

다른 사용자 메뉴의 다른 사용자 단추에는 장치에 마지막으로 로그인 한 사용자가 표시 됩니다. 이 사용자에 대 한 로그인 화면으로 돌아가려면이 단추를 선택 합니다.

![로그인 화면 기본값](./images/multiusers1.jpg)

<br>

![로그인 화면 기타 사용자](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 외부 마이크 지원

> [!IMPORTANT]
> **USB mic를 꽂으면 입력 장치로 자동 설정 되지** 않습니다. USB-C 헤드폰 사용자를 연결 하는 경우 헤드폰의 오디오가 헤드폰으로 자동으로 리디렉션되고 HoloLens OS는 다른 입력 장치 위의 내부 마이크 배열에 우선 순위를 두고 있습니다. **USB-C 마이크를 사용 하려면 다음 단계를 수행 합니다.**

사용자는 **사운드** 설정 패널을 사용 하 여 USB C 연결 외부 마이크를 선택할 수 있습니다. USB-C 마이크는 호출, 기록 등에 사용할 수 있습니다.

**설정** 앱을 열고 **시스템**  >  **소리** 를 선택 합니다.

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> **원격 지원** 에서 외부 마이크를 사용 하려면 사용자가 "사운드 장치 관리" 하이퍼링크를 클릭 해야 합니다.
>
> 그런 다음 드롭다운을 사용 하 여 외부 마이크를 **기본값** 또는 **통신 기본값으로 설정 합니다.** **기본값** 을 선택 하면 외부 마이크가 어디에서 나 사용 됩니다.
>
> **통신 기본값** 을 선택 하면 외부 마이크가 원격 지원 및 기타 통신 앱에서 사용 되지만 다른 작업에는 HoloLens mic 배열을 계속 사용할 수 있습니다.

![사운드 장치 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth 마이크 지원 이란?

아쉽게도 현재 Bluetooth 마이크는 HoloLens 2에서 아직 지원 되지 않습니다.

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

- URI 값:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 정책  | 설명   | 구성  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 방문자가 키오스크에 자동으로 로그온 하도록 허용 합니다.   | 1 (예), 0 (아니요, 기본값)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>키오스크 모드에서 새 설정 및 Edge 앱 사용

[키오스크](hololens-kiosk.md)에 앱을 포함 하는 경우 it 관리자는 앱을 키오스크에 추가 하지만 앱 사용자 모델 ID (AUMID)를 사용 하는 경우가 많습니다. 설정 앱과 Microsoft Edge 앱은 모두 새로운 앱으로 간주 되며, 해당 앱에 대해 AUMIDs를 사용 하는 이전 앱 키오스크와는 새로운 AUMID를 사용 하도록 업데이트 해야 합니다.

새 앱을 포함 하도록 키오스크를 수정할 때 새로운 AUMID를 추가 하는 것은 물론 기존 항목을 그대로 두는 것이 좋습니다. 이렇게 하면 사용자가 OS를 업데이트할 때 쉽게 전환할 수 있으며, 원하는 대로 키오스크를 계속 사용 하기 위해 새 정책을 받을 필요가 없습니다.

| 앱                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 이전 설정 앱       | HolographicSystemSettings_cw5n1h2txyewy! 다운로드            |
| 새 설정 앱       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 다운로드 |
| 이전 Microsoft Edge 앱 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| 새 Microsoft Edge 앱 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리에 대 한 키오스크 모드 동작 변경 내용

이전 빌드에서 장치에 할당 된 전역 액세스 권한 및 AAD 그룹 구성원 모두의 조합 인 키오스크 구성이 있는 경우 AAD 그룹 멤버 자격을 확인 하지 못한 경우 사용자에 게 "[시작에 표시 되지 않음](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" 메뉴가 표시 됩니다.

Windows 참가자 릴리스부터 키오스크 환경에서 AAD 그룹 키오스크 모드 중 오류가 발생 하는 경우 전역 키오스크 구성 (있는 경우)으로 대체 됩니다.

### <a name="new-settingsuris-for-page-settings-visibility"></a>페이지 설정 표시에 대 한 새 SettingsURIs

[Windows Holographic 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 에서는 설정 앱 내에 표시 되는 페이지를 제한 하는 [settings/PageVisibilityList 정책을](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 추가 했습니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스할 수 없도록 하거나 지정 된 페이지를 제외한 모든 페이지에 대해이 작업을 수행 하는 데 사용할 수 있는 정책입니다.

[페이지 설정 표시 유형을](settings-uri-list.md)방문 하는 경우이 CSP와 이전 버전에서 사용할 수 있는 uri 목록을 사용할 수 있는 지침을 찾을 수 있습니다.

Windows 참가자 빌드에서 사용 가능한 설정 Uri 목록으로 확장 하 고, IT 관리자가 관리할 수 있습니다. 이러한 Uri 중 일부는 새 설정 앱 내에서 새로 사용할 수 있는 영역에 대 한 것입니다. Settings/PageVisibilityList policy를 사용 하는 경우 다음 목록을 검토 하 고 필요에 따라 허용 또는 차단 된 페이지를 조정 합니다.

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
| 개인 설정 > 잉크 & 개인 설정             | `ms-settings:privacy-speechtyping`                 |
| 개인 정보 > 동작                                     | `ms-settings:privacy-motion`                       |
| 개인 정보 > 스크린샷 테두리                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 개인 정보 > 스크린샷 및 앱                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 시스템 > 배터리                                     | `ms-settings:batterysaver`                         |
| 시스템 > 배터리                                     | `ms-settings:batterysaver-settings`                |
| 시스템 > 소리                                       | `ms-settings:sound`                                |
| 시스템 > 소리 > 앱 볼륨 및 장치 기본 설정 | `ms-settings:apps-volume`                          |
| 시스템 > 소리 > 사운드 장치 관리              | `ms-settings:sound-devices`                        |
| 저장소 구성 > 시스템 > 저장소         | `ms-settings:storagepolicies`                      |
| 시간 & 언어 > 날짜 & 시간                        | `ms-settings:dateandtime`                          |
| 시간 & 언어 > 키보드                           | `ms-settings:keyboard`                             |
| 시간 & 언어 > 언어                           | `ms-settings:language`                             |
| 시간 & 언어 > 언어                           | `ms-settings:regionlanguage-languageoptions`       |
| 업데이트 & 보안 > 다시 설정 & 복구               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>업데이트 된 Uri

이전에는 다음 두 개의 Uri가 표시 된 페이지에 직접 사용자를 가져오지 않고 주 업데이트 페이지만 차단 했습니다. 다음 항목은 해당 페이지에 직접 전달 되도록 업데이트 되었습니다.

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>설정 앱을 통해 대체 진단 구성

이제 설정 앱에서 사용자는 [대체 진단](hololens-diagnostic-logs.md)의 동작을 구성할 수 있습니다. 설정 앱에서 **개인 정보**  ->  **문제 해결** 페이지로 이동 하 여이 설정을 구성 합니다.

> [!NOTE]
> 장치에 대해 구성 된 MDM 정책이 있으면 사용자가 해당 동작을 재정의할 수 없습니다.  

### <a name="share-things-with-nearby-devices"></a>주변 장치와 항목 공유

HoloLens Insider Preview 20279.1006 +를 실행 하는 Pc 및 기타 HoloLens 2 장치를 모두 포함 하 여 Windows 10 장치에 있는 항목을 공유 합니다. **설정** 시스템 공유 환경에서 사용해 볼 수 있으며  ->    ->   HoloLens의 파일 또는 url을 PC로 공유할 수 있습니다. 자세한 내용은 [Windows 10에서 주변 장치와 항목을 공유](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)하는 방법을 참조 하세요.

이 기능은 [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)를 통해 관리할 수 있습니다.

### <a name="new-os-update-troubleshooter"></a>새 OS 업데이트 문제 해결사

설정 앱 내에서 이전 문제 해결사 외에도 새 설정 앱이 OS 업데이트용 새 설정 앱과 함께 추가 되었습니다. **설정**  ->  **업데이트 &amp; 보안**  >  **문제 해결**  >  **Windows 업데이트** 로 이동 하 고 **시작** 을 선택 합니다. 이렇게 하면 OS 업데이트에 대 한 문제를 재현 하는 동안 추적을 수집 하 여 IT 또는 지원과 관련 된 문제 해결에 더 효과적으로 지원할 수 있습니다.

### <a name="delivery-optimization-preview"></a>배달 최적화 미리 보기

이 HoloLens Insider update를 사용 하 여 Windows Holographic for Business는 여러 HoloLens 장치에서 다운로드에 대 한 대역폭 소비를 줄이기 위해 배달 최적화 설정에 대 한 초기 미리 보기를 설정 합니다. 권장 되는 네트워크 구성과 함께이 기능에 대 [한 자세한 설명은 Windows 10 업데이트에 대 한 배달 최적화](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)에서 제공 됩니다.

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

이 미리 보기 제품에 대 한 몇 가지 주의 사항:

- HoloLens 지원은이 미리 보기에서 OS 업데이트로 제한 됩니다.
- Windows Holographic for Business는 HTTP 다운로드 모드 및 [Microsoft 연결 된 캐시 끝점](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)의 다운로드만 지원 합니다. 지금은 HoloLens 장치에 대해 피어 투 피어 다운로드 모드 및 그룹 할당이 지원 되지 않습니다.
- HoloLens는 Windows Server Update Services 끝점에 대 한 배포 또는 배달 최적화를 지원 하지 않습니다.
- 문제를 해결 하려면 연결 된 캐시 서버에 대 한 진단을 수행 하거나 **설정**  >  **업데이트 & 보안**  >   **문제 해결**  >   **Windows 업데이트** 를 통해 hololens의 hololens에서 추적을 수집 해야 합니다.

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 향상 된 기능 및 수정 사항:

- 또한 [오프 라인 진단](hololens-diagnostic-logs.md#offline-diagnostics) 에는 일련 번호 및 OS 버전에 대 한 추가 장치 정보가 포함 됩니다.

### <a name="known-issues-and-work-around"></a>알려진 문제 및 해결 방법

#### <a name="pairing-hololens-to-pc"></a>HoloLens를 PC에 페어링

Windows 참가자 빌드 20325.1000 이전에는 사용자가 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 또는 [windows Holographic, 버전 2004](hololens-release-notes.md#windows-holographic-version-2004) 에 대 한 연결 자격 증명을 설정 하 고 windows 참가자 빌드로 업데이트 한 경우 Visual Studio를 사용 하는 것과 같은 앱을 배포 하 고 디버깅 하기 위해 HoloLens를 PC와 연결 하기 위한 이전에 설정한 자격 증명이 더 이상 작동 하지 않습니다. Windows Insider build 20325.1000은이 문제를 해결 하 고 장치 포털을 사용 하 여 다시 시작할 추가 작업은 필요 하지 않습니다.

이제 [참가자 빌드를 사용 하 여 장치](#ffu-download-and-flash-directions) 를 업데이트 한 사용자가 장치를 PC와 연결 하기 위해 장치 (20325.1000 + 또는 GA 빌드)를 경감 하기 위해 해야 합니다.

Windows 참가자에 등록 하지 않은 사용자는 일반적으로 사용할 수 있는 경우 기능 업데이트를 수행 합니다.


## <a name="start-receiving-insider-builds"></a>Insider 빌드 수신을 시작 합니다.

> [!NOTE]
> 최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.
> - "장치 다시 부팅" 음성 명령은 제대로 작동 합니다. 
> - 설정/Windows 참가자 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 사용자가 발생 시킨 백 엔드에 대 한 버그가 있었으며이로 인해 다시 추적할 수 있습니다.

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동 하 고 **시작** 을 선택 합니다. Windows 참가자로 등록 하는 데 사용한 계정을 연결 합니다.

이제 Windows 참가자가 채널로 이동 하 고 있습니다. **빠른** 링은 **Dev 채널이** 되 고, **저속** 링은 **베타 채널이** 되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이** 됩니다. 매핑은 다음과 같습니다.

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.

그런 다음 **Windows의 활성 개발** 을 선택 하 고 **개발 채널** 또는 **베타 채널** 빌드를 받을지 여부를 선택한 후 프로그램 용어를 검토 합니다.

확인을 선택 하 **> 지금 다시 시작** 하 여 완료 합니다. 장치를 다시 부팅 한 후에는 **설정 > 업데이트 & 보안 > 업데이트 확인** 으로 이동 하 여 최신 빌드를 가져옵니다.

### <a name="update-error-0x80070490-work-around"></a>업데이트 오류 0x80070490 문제 해결
Dev 또는 Beta 채널에서 업데이트할 때 0x80070490 업데이트 오류가 발생 하는 경우 다음 단기 작업을 수행해 보세요. 여기에는 insider channel을 이동 하 고, 업데이트를 선택한 다음, Insider channel을 다시 이동 하는 작업이 포함 됩니다.

#### <a name="stage-one---release-preview"></a>1 단계 릴리스 미리 보기
1.  설정, 업데이트 & 보안, Windows Insider Program, **Release Preview 채널** 을 선택 합니다.
2.  설정, 업데이트 & 보안, Windows 업데이트 **업데이트 확인**. 업데이트 후 2 단계를 계속 진행 합니다.

#### <a name="stage-two---dev-channel"></a>2 단계 개발자 채널
1. 설정, 업데이트 & 보안, Windows 참가자 프로그램, **개발 채널** 을 선택 합니다.
2. 설정, 업데이트 & 보안, Windows 업데이트 **업데이트 확인**.

## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 방향
비행 서명 된 ffu로 테스트 하려면 비행 서명 된 ffu를 깜박임 전에 먼저 장치 잠금을 해제 해야 합니다.
1. PC:

    1. 에서 PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.
    
    1. Microsoft Store에서 ARC (고급 복구 도우미)를 설치 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 합니다.
    
1. HoloLens 비행 잠금 해제: **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** , 등록, 다시 부팅 장치를 엽니다.

1. 플래시 FFU-이제 호를 사용 하 여 비행 서명 된 FFU를 깜박일 수 있습니다.

## <a name="provide-feedback-and-report-issues"></a>사용자 의견을 제공 하 고 문제를 보고 합니다.

사용자 의견을 제공 하 고 문제를 보고 하려면 HoloLens의 [피드백 허브 앱](hololens-feedback.md) 을 사용 하세요. 피드백 허브를 사용 하면 엔지니어가 신속 하 게 디버그 하 고 문제를 해결 하는 데 필요한 모든 진단 정보가 포함 됩니다.  HoloLens의 중국어 및 일본어 버전 문제는 동일한 방식으로 보고 되어야 합니다.

> [!NOTE]
> 사용자 의견 허브에서 문서 폴더에 액세스할 지 여부를 묻는 메시지를 수락 해야 합니다 (메시지가 표시 되 면 **예** 선택).

## <a name="note-for-developers"></a>개발자를 위한 정보

HoloLens의 Insider 빌드를 사용 하 여 응용 프로그램을 개발 하는 것이 좋습니다.  시작 하려면 [HoloLens 개발자 설명서](https://developer.microsoft.com/windows/mixed-reality/development) 를 확인 하세요. 이러한 동일한 지침은 HoloLens의 Insider 빌드에서만 작동 합니다.  HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio의 동일한 빌드를 사용할 수 있습니다.

## <a name="stop-receiving-insider-builds"></a>Insider 빌드 수신을 중지 합니다.

더 이상 Windows Holographic의 참가자 빌드를 수신 하지 않으려는 경우 HoloLens가 프로덕션 빌드를 실행 하 고 있을 때 옵트아웃 하거나 고급 복구 도우미를 사용 하 여 장치를 [복구](hololens-recovery.md) 하 여 비-windows Holographic 버전으로 장치를 복구할 수 있습니다.

> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치 하면 사용자에 게 Insider Preview 빌드에서 등록을 취소 하는 알려진 문제가 있습니다. 이후에는 장치를 수동으로 복구 해야 합니다. 영향을 받는 경우에 대 한 자세한 내용은이 [알려진 문제](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)에 대 한 자세한 내용을 확인 하세요.

HoloLens가 프로덕션 빌드를 실행 하 고 있는지 확인 하려면 다음을 수행 합니다.

1. **설정 > 시스템 > 정보** 로 이동 하 여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.

참가자 빌드를 옵트아웃 (opt out) 하려면 다음을 수행 합니다.

1. 프로덕션 빌드를 실행 하는 HoloLens에서 **설정 > 업데이트 & 보안 > Windows Insider Program** 로 이동 하 여 **insider build 중지** 를 선택 합니다.

1. 지침에 따라 장치를 옵트아웃 합니다.
