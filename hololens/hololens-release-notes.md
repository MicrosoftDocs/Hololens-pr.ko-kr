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
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 1de9687174bf9c1de2e2b15ee03aa841254b0b82
ms.sourcegitcommit: 2988afb1d7792c9e4bae15485cd52d6eff7e27c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2021
ms.locfileid: "113685051"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 릴리스 정보

HoloLens 디바이스에서 생산성을 높일 수 있도록 기능, 버그 및 보안 업데이트를 계속 릴리스합니다. 이 페이지에서 매월 HoloLens 새로운 내용을 확인할 수 있습니다. 최신 HoloLens 2 업데이트를 얻으려면 [업데이트를 확인하고 수동으로 업데이트하거나](hololens-update-hololens.md#check-for-updates-and-manually-update) FFU(전체 플래시 업데이트)를 다운로드하여 고급 복구 도우미 를 [통해 디바이스를 플래시할 수 있습니다.](hololens-recovery.md#clean-reflash-the-device) [다운로드는](https://aka.ms/hololens2download) 최신 상태로 유지되며 일반적으로 사용 가능한 최신 빌드를 제공합니다.

> [!NOTE]
> 최근 Windows 11 공지 내용은 PC 버전의 Windows에 집중되었습니다. Microsoft는 최근 2021년 5월에 HoloLens 2의 [주요 OS 업데이트](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)를 시작했으며, 이번 여름 고객의 피드백에 따라 예정된 릴리스에 대해 작업할 예정입니다.

> [!IMPORTANT]
> 이제 Remote Assist 사용자에게 [영향을 주는 21H1 빌드에서 알려진 문제가 해결되어](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)Windows Holographic 버전 21H1 업데이트 제공을 일시 중지했습니다. 또한 기본 ARC(Advanced Recovery Companion) 빌드를 [Windows Holographic 버전 20H2 – 2021년 6월 업데이트로](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)변경했습니다. ARC 빌드는 이제 21H1 빌드를 대상으로 다시 시작됩니다.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows 홀로그램 버전 21H1 - 2021년 7월 업데이트
- 빌드 20348.1010

업데이트의 개선 사항 및 수정 사항:

- 장치 포털 잠긴 파일을 여는 데 문제가 파일 탐색기 고객에게 알리는 향상된 방법을 제공합니다.
- 통합된 그래픽 어댑터와 불연속 그래픽 어댑터를 모두 사용하는 PC에서 HoloLens 2 Emulator 사용하는 경우 에뮬레이터는 이제 덜 강력한 통합 어댑터를 사용할 수 있지만 대부분의 경우 하드웨어 그래픽 가속을 사용하도록 설정할 수 있습니다.  이전에는 하드웨어 가속을 사용하도록 설정할 수 없었습니다. 코드 43에서 그래픽 오류를 보고하는 경우가 많습니다.  경우에 따라 에뮬레이터가 성공적으로 부팅되지 않지만 이제는 부팅됩니다.
- 이제 지원되는 모든 브라우저에서 https를 사용할 때 파일 업로드, 다운로드, 이름 바꾸기 및 삭제가 수정되었습니다.
- Wi-Fi 속성 UI가 설정 -> Network & **Internet -> 상태 -> 속성** 에서 시작될 때 Wi-Fi 프록시를 저장할 수 없는 문제가 해결되었습니다.
- OS 업데이트에서 eSIM 인증서 제거와 관련된 문제를 해결했습니다. 이 수정은 21H1 릴리스로 업데이트할 때 eSIM 인증서 및 관련 구성 요소가 제거되도록 합니다.
- OS 재설정에서 미리 설치된 앱에 영향을 미치는 문제를 수정했습니다. 
- CPU 로드가 증가하면서 충전 시 런타임을 늘리도록 배터리 충전 성능이 조정되었습니다.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows 홀로그램 버전 20H2 – 2021년 7월 업데이트
- 빌드 19041.1157

업데이트의 개선 사항 및 수정 사항:
- 장치 포털 잠긴 파일을 여는 데 문제가 파일 탐색기 고객에게 알리는 향상된 방법을 제공합니다. 
- 통합된 그래픽 어댑터와 불연속 그래픽 어댑터를 모두 사용하는 PC에서 HoloLens 2 Emulator 사용하는 경우 에뮬레이터는 이제 덜 강력한 통합 어댑터를 사용할 수 있지만 대부분의 경우 하드웨어 그래픽 가속을 사용하도록 설정할 수 있습니다.  이전에는 하드웨어 가속을 사용하도록 설정할 수 없었습니다. 코드 43에서 그래픽 오류를 보고하는 경우가 많습니다.  경우에 따라 에뮬레이터가 성공적으로 부팅되지 않지만 이제는 부팅됩니다.
- 이제 지원되는 모든 브라우저에서 https를 사용할 때 파일 업로드, 다운로드, 이름 바꾸기 및 삭제가 수정되었습니다.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows 홀로그램 버전 21H1 - 2021년 6월 업데이트
- 빌드 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>직장 또는 학교 카메라 롤 업로드를 위한 OneDrive

고객이 디바이스의 사진 > Camera Roll 폴더에서 해당 OneDrive 직장 또는 학교 폴더에 혼합 현실 사진 및 비디오를 자동으로 업로드할 수 있는 새로운 기능을 HoloLens 2 설정 앱에 추가했습니다. 이 기능은 [HoloLens 2 OneDrive 앱 내에서 기능 차이를](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) 해결합니다. 이 앱은 고객의 개인 Microsoft 계정 자동 카메라 롤 업로드만 지원합니다(직장 또는 학교 계정이 아닌).

**작동 방법**

- **설정 > System > 혼합 현실 카메라** 방문하여 "카메라 업로드"를 사용하도록 설정합니다.
- 이 기능을 **켜기** 위치로 설정하면 디바이스에 캡처된 혼합 현실 사진 또는 비디오가 자동으로 큐에 대기되어 직장 또는 학교 계정용 OneDrive Pictures > Camera Roll 폴더에 업로드됩니다.
    >[!NOTE]
    >이 기능을 사용하도록 설정하기 전에 캡처된 사진 및 비디오는 업로드를 위해 큐에 *대기되지 않으며* 수동으로 업로드해야 합니다.
- 설정 페이지의 상태 메시지에 업로드 보류 중인 파일 수가 표시됩니다(또는 보류 중인 모든 파일이 업로드된 경우 "OneDrive 최신 상태").
- 대역폭이 걱정되거나 어떤 이유로든 업로드를 "일시 중지"하려는 경우 기능을 **끄기** 위치로 전환할 수 있습니다. 기능을 일시적으로 사용하지 않도록 설정하면 Camera Roll 폴더에 새 파일을 추가할 때 업로드 큐가 계속 증가하지만 기능을 다시 사용하도록 설정할 때까지 파일이 업로드되지 않습니다.
- 최신 파일이 먼저 업로드됩니다(마지막, 첫 번째 파일).
- OneDrive 계정에 문제가 있는 경우(예: 암호 변경 후) **지금 수정** 단추가 설정 페이지에 표시됩니다.
- 최대 파일 크기는 없지만 큰 파일은 업로드하는 데 시간이 더 오래 소요됩니다(특히 업로드 대역폭이 제한된 경우). 큰 파일을 업로드하는 동안 업로드를 "일시 중지"하거나 해제하면 부분 업로드가 유지됩니다. 업로드가 "일시 중지"된 후 몇 시간 이내에 다시 활성화되거나 해제된 경우 업로드는 중단된 위치에서 계속됩니다. 그러나 몇 시간 후에 업로드를 다시 사용하도록 설정하면 대용량 파일의 업로드가 처음부터 다시 시작됩니다.

**알려진 문제 및 주의 사항**

- 이 설정에는 현재 대역폭 사용량을 기반으로 하는 기본 제공 제한 기능이 없습니다. 다른 시나리오에 대한 대역폭을 최대화해야 하는 경우 설정을 수동으로 끕니다. 업로드 일시 중지되지만 이 기능은 카메라 롤에 새로 추가된 파일을 계속 모니터링합니다. 업로드를 계속할 준비가 되면 다시 활성화합니다.
- 이 기능은 디바이스의 각 사용자 계정에 대해 사용하도록 설정해야 하며, 현재 디바이스에 로그인한 사용자에 대한 파일만 적극적으로 업로드할 수 있습니다.
- 설정 페이지의 업로드 횟수를 실시간으로 보는 동안 사진이나 비디오를 만드는 경우 현재 파일 업로드가 완료될 때까지 보류 중인 파일 수가 변경되지 않을 수 있습니다.
- 디바이스가 절전 상태이거나 전원이 꺼지면 업로드 일시 중지됩니다. 보류 중인 업로드가 완료되었는지 확인하려면 설정 페이지에 "OneDrive 최신 상태"가 표시될 때까지 디바이스를 적극적으로 사용하거나 **Power & 절전 모드** 설정을 조정합니다.
### <a name="added-support-for-some-telemetry-policies"></a>일부 원격 분석 정책에 대한 지원이 추가되었습니다.

이제 HoloLens 2 다음 원격 분석 정책이 지원됩니다.
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 및 System\ConfigureTelemetryOptInSettingsUx는 모두 함께 사용하여 설정 앱의 원격 분석 및 동작을 완전히 제어해야 합니다.

업데이트의 개선 사항 및 수정 사항:
- 색 보정을 통해 주요 비디오 손상 문제를 해결합니다.
- 전원 메뉴에서 텍스트가 잘릴 수 있는 문제를 해결합니다.
- RequirePrivateStoreOnly 정책에 대한 지원을 사용하도록 설정합니다.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows 홀로그램 버전 20H2 – 2021년 6월 업데이트
- 빌드 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>일부 원격 분석 정책에 대한 지원이 추가되었습니다.

이제 HoloLens 2 다음 원격 분석 정책이 지원됩니다.
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 및 System\ConfigureTelemetryOptInSettingsUx는 모두 함께 사용하여 설정 앱의 원격 분석 및 동작을 완전히 제어해야 합니다.

Holographic 버전 21H1을 Windows 최신 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows 홀로그램 버전 1903 - 2021년 6월 업데이트
- 빌드 18362.1116

업데이트의 개선 사항 및 수정 사항:
- 이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되어 있지 않으므로 Holographic 버전 21H1을 Windows 최신 빌드를 사용해보는 것이 좋습니다.

>[!IMPORTANT]
> 이 빌드는 더 이상 서비스되지 않습니다.

## <a name="windows-holographic-version-21h1"></a>Windows 홀로그램 버전 21H1
- 빌드 20346.1002

이 업데이트에는 두 대상에 대한 기능이 포함되어 있습니다. 최종 사용자가 디바이스의 모든 사용자가 사용할 수 있는 기능 및 IT 관리자가 구성할 수 있는 새 디바이스 관리 옵션입니다. 아래 표에서는 각 대상과 관련된 기능을 지정합니다. IT 관리자인 경우 IT 관리자 - [업데이트 검사 목록](#it-admin---update-checklist)을 살펴보세요.
>[!IMPORTANT]
>이 빌드로 업데이트하려면 HoloLens 2 디바이스가 현재 2021년 2월 업데이트(빌드 19041.1136) 이상에서 실행되고 있어야 합니다. 사용 가능한 이 기능 업데이트가 표시되지 않으면 먼저 디바이스를 업데이트하고 다시 시도하세요.

>[!NOTE]
>현재 Microsoft HoloLens 2는 다음 릴리스에 대한 월별 서비스 업데이트(버그 및 보안 수정)를 지원합니다.
>- Windows 홀로그램 버전 20H2(빌드 19041.1128 이상)
>- Windows 홀로그램 버전 2004(빌드 19041.1103 이상)
>- Windows 홀로그램 버전 1903(빌드 18362 이상) 
>
> Windows Holographic 버전 21H1이 도입되면서 **Windows Holographic 버전 1903에 대한 월간 서비스 업데이트가 중단됩니다.** 이를 통해 최신 릴리스에 집중하고 계속해서 중요한 향상된 기능을 제공할 수 있습니다. 


| 기능 이름                                              | 간단한 설명                                                                      | 대상 사용자 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [새 Microsoft Edge](#introducing-the-new-microsoft-edge)  | 이제 새로운 Chromium 기반 Microsoft Edge HoloLens 2 사용할 수 있습니다. | 최종 사용자 | 
[WebXR 및 360 뷰어](#webxr-and-360-viewer) | 몰입형 웹 환경 및 360 비디오 재생을 사용해 보세요. | 최종 사용자 | 
[새 설정 앱](#new-settings-app) | 레거시 설정 앱은 새로운 기능과 설정으로 업데이트된 버전으로 대체됩니다. | 최종 사용자 |
[색 보정 표시](#display-color-calibration) | HoloLens 2 디스플레이의 대체 색 프로필을 선택합니다. | 최종 사용자 |
[기본 앱 선택기](#default-app-picker) | 각 파일 또는 링크 형식에 대해 시작할 앱을 선택합니다. | 최종 사용자 |
[앱당 볼륨 조절](#per-app-volume-control) | 시스템 볼륨과 독립적으로 앱 수준 볼륨을 제어합니다. | 최종 사용자 |
[웹 앱 설치](#install-web-apps) | 새 Microsoft Edge 브라우저를 Microsoft Office 같은 HoloLens 2 웹앱을 설치합니다. | 최종 사용자 |
[입력으로 살짝 밀기](#swipe-to-type) | 손가락 끝을 사용하여 홀로그램 키보드에서 단어를 "살짝 밀기"합니다. | 최종 사용자 |
[시작의 전원 메뉴](#power-menu-from-start) | 시작 메뉴에서 디바이스를 다시 시작하고 HoloLens 종료합니다. | 최종 사용자 |
[로그인 화면에 나열된 여러 사용자](#multiple-users-listed-on-sign-in-screen) | 로그인 화면에 여러 사용자 계정을 표시합니다. | 최종 사용자 |
[USB-C 외부 마이크 지원](#usb-c-external-microphone-support) | 앱 및/또는 Remote Assist USB-C 마이크를 사용합니다. | 최종 사용자 |
[키오스크에 대한 방문자 자동 로그온](#visitor-auto-logon-for-kiosks) | 방문자 계정의 자동 로그온을 키오스크 모드에 사용할 수 있도록 합니다. | IT 관리자 |
[키오스크 모드의 새 앱에 대한 새 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 새 설정 및 Edge 앱에 대한 AUMID입니다. | IT 관리자 |
[키오스크 모드 오류 전달 개선](#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드는 빈 시작 메뉴 전에 전역 할당 액세스를 찾습니다. | IT 관리자 |
[페이지 설정 표시 유형에 대한 새 설정 URI](#new-settings-uris-for-page-settings-visibility) | 설정/PageVisibilityList 정책에 대한 20개 이상의 새 설정 UR입니다. | IT 관리자 |
[대체 진단 구성](#configuring-fallback-diagnostics-via-settings-app) | 설정 앱에서 대체 진단 동작 설정 | IT 관리자 |
[주변 디바이스와 사물 공유](#share-things-with-nearby-devices) | HoloLens PC로 파일 또는 URL을 공유합니다. | 모두 |
[새 OS 진단 추적](#new-os-diagnostic-traces) | OS 업데이트에 대한 설정 새로운 문제 해결사입니다. | IT 관리자 |
[배달 최적화 미리 보기](#delivery-optimization-preview) | 여러 HoloLens 디바이스에서 다운로드할 때 대역폭 사용량을 줄입니다. | IT 관리자 |

관련 릴리스 정보 확인:

- [HoloLens Emulator 보관을 방문합니다.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>새 Microsoft Edge 소개

![레거시 Microsoft Edge 로고를 새 Microsoft Edge 로고로 애니메이션](images/new-edge.gif)

새 Microsoft Edge는 [Chromium 오픈 소스 프로젝트를 채택](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)하여 고객을 위해 호환성을 높이고 웹 개발자를 위해 웹의 조각화를 줄입니다.

> [!IMPORTANT]
> 이 새 Microsoft Edge는 새 릴리스에서 [더 이상 지원되지 않는](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) 레거시 Microsoft Edge를 자동으로 대체합니다.

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>새 Microsoft Edge 시작

새로운 Microsoft Edge ![새 Microsoft Edge 아이콘](images/new_edge_logo.png) (파란색 및 녹색 소용돌이 아이콘으로 표시됨)은 시작 메뉴에 고정되어 있으며 웹 링크를 활성화할 때 자동으로 시작됩니다.

> [!NOTE]
> HoloLens 2에서 새 Microsoft Edge를 처음 시작하면 기존 Microsoft Edge에서 설정 및 데이터를 가져옵니다. 새 Microsoft Edge 시작한 후 레거시 Microsoft Edge 계속 사용하는 경우 해당 새 데이터는 레거시 Microsoft Edge 새 Microsoft Edge 동기화되지 않습니다.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>새 Microsoft Edge에 대한 정책 설정 구성

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

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2의 새 Microsoft Edge에서 예측할 수 있는 사항

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

**브라우저의 알려진 주요 문제:**

- 홀로그램 키보드의 돋보기 미리 보기가 새 Microsoft Edge에서 사용하지 않도록 설정되었습니다. 확대가 제대로 작동되면 향후 업데이트에서 이 기능을 다시 사용하도록 설정하는 것이 좋습니다.
- 다른 브라우저 창이 열려 있고 활성 상태인 경우 잘못된 브라우저 창에서 오디오를 재생할 수 있습니다. 오디오를 재생할 필요가 없는 다른 활성 창을 닫으면 이 문제를 해결할 수 있습니다.
- 브라우저 창에서 ["Follow me" 모드로](hololens2-basic-usage.md#follow-me-stop-following)오디오를 재생할 때 "Follow me" 모드를 사용하지 않도록 설정하면 오디오가 계속 재생됩니다. "Follow me" 모드를 사용하지 않도록 설정하기 전에 오디오 재생을 중지하거나 **X** 단추로 창을 닫아 이 문제를 해결할 수 있습니다.
- 활성 Microsoft Edge 창과 상호 작용하면 다른 2D 앱 창이 갑자기 비활성 상태가 될 수 있습니다. 이러한 창은 다시 상호 작용하여 다시 활성화할 수 있습니다.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

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

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC를 사용하여 새 Microsoft Edge 차단

[WDAC 정책](windows-defender-application-control-wdac.md)을 업데이트하여 새 Microsoft Edge 앱을 차단하려는 IT 관리자의 경우 정책에 다음을 추가해야 합니다.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>새 Microsoft Edge의 엔드포인트 관리

일부 환경에는 고려 사항으로 확인해야 할 네트워크 제한이 있을 수 있습니다. 새 Edge의 원활한 환경을 보장하려면 [이러한 Microsoft 엔드포인트를 사용하도록 설정](/deployedge/microsoft-edge-security-endpoints)하세요.

현재 사용할 수 있는 [HoloLens의 엔드포인트](hololens-offline.md)에 대해 자세히 읽어보세요.

### <a name="install-web-apps"></a>웹 앱 설치
 > [!Note]
>[Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1)에서는 더 이상 Office 웹 앱이 미리 설치되지 않습니다.

새 Edge를 사용하여 Microsoft Store 앱과 함께 웹 앱을 설치할 수 있습니다. 예를 들어 Microsoft Office 웹 앱을 설치하여 SharePoint 또는 OneDrive에서 호스트되는 파일을 보고 편집할 수 있습니다. Office 웹 앱을 설치하려면 https://www.office.com 에 방문하여 주소 표시줄에서 **App Available** 또는 **Install Office** 단추를 선택합니다. **설치** 를 선택하여 확인합니다.

> [!IMPORTANT]
> Office 웹 앱 기능은 HoloLens 2 활성 인터넷 연결이 있는 경우에만 사용할 수 있습니다.

### <a name="webxr-and-360-viewer"></a>WebXR 및 360 뷰어

새 Microsoft Edge에는 몰입형 웹 환경을 만들기 위한 새로운 표준인 WebXR에 대한 지원이 포함되어 있습니다(WebVR 대체). 대부분의 몰입형 웹 환경은 VR을 염두에 두고 설계되었지만(이는 보기의 필드를 가상 환경으로 대체), 이러한 환경은 HoloLens 2에서도 지원됩니다. WebXR 표준을 사용하면 물리적 환경을 사용하는 증강 현실 및 혼합 현실 몰입형 웹 환경을 사용할 수도 있습니다. 개발자가 WebXR에 더 많은 시간을 쏟고 있으므로, HoloLens 2 고객이 시험해 볼 수 있는 새로운 증강 현실 및 혼합 현실 환경이 도래할 것을 기대합니다!

360 뷰어 확장은 WebXR을 기반으로 하며 HoloLens 2에 새 Microsoft Edge와 함께 자동으로 설치됩니다. 이 웹 확장은 360도 비디오에 직접 몰입할 수 있는 기능을 제공합니다. YouTube는 가장 광범위하게 선택할 수 있는 360 비디오를 제공하므로 YouTube에서 시작해 보세요.

#### <a name="how-to-use-webxr"></a>WebXR 사용 방법

1. WebXR가 지원되는 웹 사이트로 이동합니다.
1. 웹 사이트에서 **Enter VR** 단추를 선택합니다. 이 단추의 위치와 표시되는 모양은 웹 사이트별로 다를 수 있지만 다음과 유사할 것입니다.

    ![Enter VR 입력 예제](images/75px-enter-vr.png)

1. 특정 도메인에서 WebXR 환경을 처음 시작하는 경우 브라우저에서 몰입형 보기 입력에 대한 동의를 요청하므로 **허용** 을 선택합니다.
1. 환경을 조작하려면 [HoloLens 2 제스처](hololens2-basic-usage.md#the-hand-tracking-frame)를 사용합니다.
1. 환경에 **끝내기** 단추가 없으면 [시작 제스처](hololens2-basic-usage.md#start-gesture)를 사용하여 홈으로 돌아갑니다.

**권장되는 WebXR 샘플**
- 360 뷰어(다음 섹션 참조)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 그림판](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 뷰어를 사용하는 방법

1. YouTube에서 360도 비디오로 이동합니다.
1. 비디오 프레임에서 혼합 현실 헤드셋 단추를 선택합니다.

    ![360 뷰어를 활성화하는 단추](images/enter-360-viewer.jpg)

1. 특정 도메인에서 처음 360 뷰어를 시작하려고 하면 브라우저에서 몰입형 보기에 대한 동의를 요청합니다. **허용** 을 선택합니다.
1. [에어 탭](hololens2-basic-usage.md#select-using-air-tap)하여 재생 컨트롤을 표시합니다. [손 광선 및 에어 탭](hololens2-basic-usage.md#select-using-air-tap)을 사용하여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 설정/해제, 경험 중지(몰입형 보기 끝내기)를 사용합니다. 몇 초 동안 활동이 없으면 재생 컨트롤이 사라집니다.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR 및 360 뷰어의 알려진 문제
- WebXR 환경의 복잡도에 따라 프레임 속도가 떨어지거나 끊길 수 있습니다.
- WebXR의 손 관절에 대한 지원은 기본적으로 사용되지 않습니다. 개발자는 `edge://flags` "WebXR 손 입력"을 켜서 을 통해 지원을 사용하도록 설정할 수 있습니다.
- YouTube 이외의 웹 사이트에서 360 비디오가 예상대로 작동하지 않을 수 있습니다.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR 및 360 뷰어에 대한 피드백 제공

새 Microsoft Edge에서 **피드백 보내기** 기능을 통해 피드백과 버그를 팀과 공유하세요.

### <a name="new-settings-app"></a>새 설정 앱

이 릴리스에서는 새 버전의 설정 앱을 소개합니다. 새 설정 앱에는 소리, 전원 및 절전 모드, 네트워크 및 인터넷, 앱, 계정, 접근성 등의 영역에서 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.

> [!NOTE]
> 새 설정 앱은 레거시 설정 앱과 구별되므로 이전에 사용 환경에 있었던 모든 설정 창은 업데이트 시 제거됩니다.

![새 설정 앱 홈페이지](images/new-settings-app.png)

**새로운 기능 및 설정**
- 설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈페이지에서 설정을 검색합니다.
- 시스템 > 소리:
  - 입력 및 출력 오디오 장치: 입력 오디오 장치와 출력 오디오 장치(예: Bluetooth 헤드폰을 통한 오디오 수신 또는 오디오 입력용 USB-C 마이크 사용)를 따로 선택합니다.
    > [!NOTE]
    > Bluetooth 마이크는 HoloLens 2에서 지원하지 않습니다.
  - 앱 볼륨: 각 앱의 볼륨을 따로 조정합니다. [앱당 볼륨 조절](#per-app-volume-control)을 참조하세요.
- 시스템 > 전원 및 절전: 비활성 기간 후에 장치가 절전 모드로 바뀌어야 하는 시기를 선택합니다.
- 시스템 > 배터리: 수동으로 배터리 절약 모드 모드를 사용하도록 설정하거나 배터리 절약 모드 모드가 자동으로 켜지는 배터리 임계값을 설정합니다.
- 장치 > USB: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.
- 네트워크 및 인터넷:
  - 이제 USB-C 이더넷 어댑터가 네트워크 및 인터넷에 표시됩니다.
  - 이제 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.
  - 이제 HoloLens 2 비행기 모드를 사용하도록 설정할 수 있습니다.
- 앱: 파일 형식과 링크 유형에 사용되는 기본 앱을 다시 설정할 수 있습니다. 자세한 내용은 [기본 앱 선택기](#default-app-picker)를 참조하세요.
- 계정 > 다른 사용자: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.
- 접근성: 텍스트 크기와 일부 시각적 효과를 변경합니다.

**알려진 문제**
- 이전에 배치된 설정 창이 제거됩니다(위 참고 사항 참조).
- 더 이상 설정 앱을 통해 장치 이름을 바꿀 수 없습니다. IT 관리자는 [HoloLens 2용 Windows Autopilot](hololens2-autopilot.md) 장치 이름 템플릿 또는 MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 노드를 사용하여 장치 이름을 바꿀 수 있습니다.
- 이더넷 페이지에는 항상 가상 이더넷 장치("UsbNcm")가 표시됩니다.
- UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램의 특성 때문에 새 Microsoft Edge 대한 배터리 사용량이 정확하지 않을 수 있습니다(곧 수정될 예정 없음).

#### <a name="display-color-calibration"></a>색 보정 표시



이 새 설정을 사용하면 HoloLens 2 표시할 대체 색 프로필을 선택할 수 있습니다. 그러면 특히 낮은 디스플레이 밝기 수준에서 색을 더 정확하게 표시하는 데 도움이 될 수 있습니다. 디스플레이 색 보정은 설정 앱의 시스템 > 보정 페이지에서 찾을 수 있습니다.

> [!NOTE]
> 이 설정은 디스플레이 펌웨어에 새 색 프로필을 저장하기 때문에 장치별 설정입니다(각 사용자 계정에 고유하지 않음).

##### <a name="how-to-use-display-color-calibration"></a>디스플레이 색 보정 사용 방법

1. **설정** 앱을 시작하고 **시스템 > 보정** 으로 이동합니다.
1. **디스플레이 색 보정** 아래에서 **Run display color calibration** 단추를 선택합니다.
1. 디스플레이 색 보정 환경이 시작되고 바이저가 올바른 위치에 있는지 확인하라는 메시지가 표시됩니다.
1. 지침 대화 상자를 진행하면 디스플레이가 자동으로 30% 밝기로 어둡게 표시됩니다.
    > [!TIP]
    > 환경에서 어둡게 표시된 장면을 보는 데 문제가 있는 경우 장치 왼쪽의 밝기 단추를 사용하여 HoloLens 2 밝기 수준을 수동으로 조정할 수 있습니다.
1. 단추 1~6을 선택하여 각 색 프로필을 즉시 사용해 보고 눈에 가장 잘 맞는 프로필을 찾습니다(이는 일반적으로 장면이 가장 중립적으로 표시되고 회색조 패턴과 피부색은 예상대로 표시된다는 의미임).

    ![디스플레이 색 보정 장면](images/color-cal-ui.png)
    
1. 선택한 프로필에 만족하면 **Save & Exit** 단추 선택
1. 변경하지 않으려면 **Cancel & Exit** 단추를 선택하여 변경 내용 되돌리기

> [!TIP]
> 디스플레이 색 보정 설정을 사용하는 동안 몇 가지 유용한 팁은 다음과 같습니다.
> - 원할 때마다 설정 디스플레이 색 보정을 다시 실행할 수 있습니다.
> - 장치의 누군가가 이전에 설정을 사용하여 색 프로필을 변경한 경우 가장 최근 변경 사항의 날짜/시간이 설정 페이지에 반영됩니다.
> - 디스플레이 색 보정을 다시 실행하면 이전에 저장된 색 프로필이 강조 표시되고 프로필 0이 표시되지 않습니다(프로필 0은 디스플레이의 원래 색 프로필을 나타냄).
> - 디스플레이의 원래 색 프로필로 되돌리려면 설정 페이지에서 수행할 수 있습니다([색 프로필 다시 설정 방법](#how-to-reset-color-profile) 참조).

##### <a name="how-to-reset-color-profile"></a>색 프로필 다시 설정 방법 

HoloLens 2에 저장된 사용자 지정 색 프로필이 만족스럽지 않으면 장치의 원래 색 프로필을 복원할 수 있습니다.
1. **설정** 앱을 시작하고 **시스템 > 보정** 으로 이동합니다.
1. **디스플레이 색 보정** 아래에서 **Reset to default color profile** 단추를 선택합니다.
1. 대화 상자가 열리면 HoloLens 2를 다시 시작하고 변경 내용을 적용할 준비가 되면 **Restart** 를 선택합니다.

#### <a name="top-display-color-calibration-known-issues"></a>알려진 주요 디스플레이 색 보정 문제

- 설정 페이지에서 색 프로필이 마지막으로 변경된 시기를 알려주는 상태 문자열은 설정 해당 페이지를 다시 로드할 때까지 만료됩니다.
    - 해결 방법: 다른 설정 페이지를 선택한 다음 보정 페이지를 다시 선택합니다.

#### <a name="default-app-picker"></a>기본 앱 선택기

하이퍼링크를 활성화하거나 앱을 지원하는 앱을 두 개 이상 설치한 파일 형식을 열면 파일 또는 링크 형식을 처리할 설치된 앱을 선택하라는 새 창이 열립니다. 이 창에서 선택한 앱이 해당 파일 또는 링크 유형을 "한 번" 또는 "항상" 처리하도록 선택할 수도 있습니다.

"항상"을 선택했지만 나중에 특정 파일 또는 링크 유형을 처리하는 앱을 변경하려면 **설정 > 앱** 에서 저장된 기본값을 다시 설정할 수 있습니다. 페이지 아래쪽으로 스크롤하여 "Default apps for file types" 및/또는 "Default apps for link types" 아래에서 **지우기** 단추를 선택합니다. 데스크톱 PC의 비슷한 설정과 달리 개별 파일 형식 기본값은 다시 설정할 수 없습니다.

#### <a name="per-app-volume-control"></a>앱당 볼륨 조절

이제 이 Windows 빌드에서 사용자는 각 앱의 볼륨 수준을 수동으로 조정할 수 있습니다. 따라서 사용자는 집중해야 하는 앱에 더 잘 집중하거나 여러 앱을 사용할 때 더 잘 들을 수 있습니다. 예를 들어 다른 사용자의 원격 지원을 위해 또 다른 사용자를 호출하는 동안 한 앱의 볼륨을 줄여야 하는 경우가 있을 수 있습니다.

개별 앱의 볼륨을 설정하려면 **설정** -> **시스템** -> **소리** 로 이동하고 고급 소리 옵션에서 **앱 볼륨 및 장치 기본 설정** 을 선택합니다.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>입력으로 살짝 밀기

일부 고객은 입력하려는 단어의 모양을 살짝 밀어 가상 키보드에서 "입력"하는 것이 더 빠르며 홀로그램 키보드에 대해 이 기능을 미리 봅니다. 홀로그램 키보드의 평면을 통해 손가락 끝을 전달하고 단어 모양을 살짝 밀고 키보드 평면에서 손가락 끝을 빼서 한 번에 한 단어를 살짝 밀 수 있습니다. 단어 사이에 있는 키보드에서 손가락을 치워서 스페이스바를 누르지 않고도 후속 단어를 살짝 밀 수 있습니다. 키보드에서 손가락의 움직임을 따라 살짝 밀기 흔적이 표시되면 기능이 작동한다는 것을 알 수 있습니다.

휴대폰 디스플레이와 달리 손가락에 저항이 느껴지지 않는 홀로그램 키보드의 특성 때문에 이 기능을 사용하고 숙달하는 것이 어려울 수 있습니다. 

### <a name="power-menu-from-start"></a>시작의 전원 메뉴

사용자가 장치를 로그아웃, 종료 및 다시 시작할 수 있는 새 메뉴입니다. 시스템 업데이트가 사용 가능한 때를 보여 주는 HoloLens 시작 화면의 표시기입니다.

#### <a name="how-to-use"></a>사용 방법

1. [시작 제스처](hololens2-basic-usage.md#start-gesture)를 사용하거나 "Go to Start"라고 말하여 HoloLens 시작 화면을 엽니다.

2. 사용자 프로필 사진 옆에 있는 말줄임표 아이콘(...)이 있습니다.<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 손 또는 음성 명령 "Power"을 사용하여 사용자 프로필 사진을 선택합니다.

4. 장치 로그아웃, 다시 시작 또는 종료 옵션이 있는 메뉴가 나타납니다.<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 메뉴 옵션을 선택하여 HoloLens를 로그아웃, 다시 시작 또는 종료합니다. 장치가 [단일 MSA(Microsoft 계정) 또는 로컬 계정](hololens-identity.md)에 대해 설정된 경우 로그아웃 옵션을 사용할 수 없습니다.

6. 다른 곳을 아무 데나 터치하거나 시작 제스처로 시작 메뉴를 닫아 메뉴를 해제합니다.

#### <a name="update-indicator"></a>업데이트 표시기

업데이트를 사용할 수 있는 경우 줄임표 아이콘이 켜지면 다시 시작 시 업데이트가 설치된다는 것을 나타냅니다. 메뉴 옵션도 업데이트의 존재를 반영하도록 변경됩니다.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>로그인 화면에 나열된 여러 사용자

이전에는 로그인 화면에 가장 최근에 로그인한 사용자와 '다른 사용자' 진입점만 표시했습니다. 여러 사용자가 디바이스에 로그인한 경우 충분하지 않다는 고객의 피드백을 받았습니다. 사용자 이름 등을 다시 입력해야 했습니다.

이 Windows 빌드에 도입된 PIN 항목 필드의 오른쪽에 있는 **다른 사용자를** 선택하면 로그인 화면에 이전에 디바이스에 로그인한 사용자가 여러 명 표시됩니다. 이렇게 하면 사용자가 자신의 사용자 프로필을 선택한 다음 Windows Hello 자격 증명을 사용하여 로그인할 수 있습니다. **계정 추가** 단추를 통해 이 다른 사용자 페이지에서 새 사용자를 디바이스에 추가할 수도 있습니다.

다른 사용자 메뉴에서 다른 사용자 단추가 디바이스에 마지막으로 로그인한 사용자를 표시합니다. 이 사용자의 로그인 화면으로 돌아가려면 이 단추를 선택합니다.

![로그인 화면 기본값](./images/multiusers1.jpg)

<br>

![로그인 화면 다른 사용자](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 외부 마이크 지원

> [!IMPORTANT]
> **USB 마이크를 꽂으면 입력 장치로 자동으로 설정되지 않습니다**. USB-C 플러그 집합에 연결하는 경우 사용자는 마이크의 오디오가 자동으로 나머지로 리디렉션되지만 HoloLens OS는 다른 입력 디바이스보다 내부 마이크 배열의 우선 순위를 지정하는 것을 관찰합니다. **USB-C 마이크를 사용하려면 다음 단계를 수행합니다.**

사용자는 **소리** 설정 패널을 사용하여 USB C 연결 외부 마이크를 선택할 수 있습니다. USB-C 마이크는 호출, 기록 등에 사용할 수 있습니다.

**설정** 앱을 열고 **시스템** > **소리** 를 선택합니다.

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> **Remote Assist** 에서 외부 마이크를 사용하려면 사용자가 “소리 장치 관리” 하이퍼링크를 클릭해야 합니다.
>
> 그런 다음 드롭다운을 사용하여 외부 마이크를 **기본값** 또는 **Communications Default** 로 설정합니다. **기본값** 을 선택하면 외부 마이크가 어디에서나 사용됩니다.
>
> **Communications Default** 를 선택하면 외부 마이크가 Remote Assist 및 기타 통신 앱에서 사용되지만 다른 작업에는 여전히 HoloLens 마이크 배열이 사용될 수 있습니다.

![소리 장치 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth 마이크 지원이란?

아쉽게도 Bluetooth 마이크는 현재 HoloLens 2 지원되지 않습니다.

#### <a name="troubleshooting-usb-c-microphones"></a>USB 문제 해결-C 마이크

일부 USB-C 마이크는 마이크 *와* 스피커로 잘못 보고 합니다. 이는 HoloLens 아닌 마이크의 문제입니다. 이러한 마이크 중 하나를 HoloLens에 연결 하는 경우 소리가 손실 될 수 있습니다. 다행히 간단한 해결 방법이 있습니다.  

**설정**  ->  **시스템**  ->  **소리** 에서 기본 제공 스피커 **(아날로그 기능 오디오 드라이버)** 를 **기본 장치로** 명시적으로 설정 합니다. 마이크가 제거 되 고 나중에 다시 연결 된 경우에도이 설정을 기억할 HoloLens.

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

방문자 자동 로그온은 [사용자 지정 OMA URI](/mem/intune/configuration/custom-settings-windows-10) 정책을 통해 관리할 수 있습니다.

- URI 값:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 정책  | 설명   | 구성  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 방문자가 키오스크에 자동으로 로그온 하도록 허용 합니다.   | 1 (예), 0 (아니요, 기본값)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>키오스크 모드에서 새로운 설정 및 Edge 앱 사용

[키오스크](hololens-kiosk.md)에 앱을 포함 하는 경우 it 관리자는 앱을 키오스크에 추가 하지만 앱 사용자 모델 ID (AUMID)를 사용 하는 경우가 많습니다. 설정 앱과 Microsoft Edge 앱은 모두 새로운 앱으로 간주 되며, 해당 앱에 대해 aumids를 사용 하는 이전 앱 키오스크와는 새 AUMID를 사용 하도록 업데이트 해야 합니다.

새 앱을 포함 하도록 키오스크를 수정할 때 새로운 AUMID를 추가 하는 것은 물론 기존 항목을 그대로 두는 것이 좋습니다. 이렇게 하면 사용자가 OS를 업데이트할 때 쉽게 전환할 수 있으며, 원하는 대로 키오스크를 계속 사용 하기 위해 새 정책을 받을 필요가 없습니다.

| 앱                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 이전 설정 앱       | HolographicSystemSettings_cw5n1h2txyewy! 다운로드            |
| 새 설정 앱       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 다운로드 |
| 이전 Microsoft Edge 앱 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| 새 Microsoft Edge 앱 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리에 대 한 키오스크 모드 동작 변경 내용

이전 빌드에서 장치에 할당 된 전역 액세스 권한 및 AAD 그룹 구성원 모두의 조합 인 키오스크 구성이 있는 경우 AAD 그룹 멤버 자격을 확인 하지 못한 경우 사용자에 게 "[시작에 표시 되지 않음](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)" 메뉴가 표시 됩니다.

이 Windows 릴리스부터는 AAD 그룹 키오스크 모드에서 오류가 발생 하는 경우 키오스크 환경이 전역 키오스크 구성 (있는 경우)으로 대체 됩니다.

### <a name="new-settings-uris-for-page-settings-visibility"></a>페이지 설정 표시 유형에 대 한 새 설정 uri

[Windows Holographic, 버전 20h2](hololens-release-notes.md#windows-holographic-version-20h2) 에서 설정 앱 내에 표시 되는 페이지를 제한 하는 [설정/PageVisibilityList 정책을](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 추가 했습니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지가 표시 또는 액세스되지 않도록 방지하거나 지정된 페이지를 제외한 모든 페이지에 대해서도 표시 또는 액세스를 방지할 수 있도록 하는 정책입니다.

[페이지 설정 표시 여부](settings-uri-list.md)를 방문 하는 경우이 CSP와 이전 릴리스에서 사용할 수 있는 uri 목록을 사용할 수 있는 지침을 찾을 수 있습니다.

IT 관리자가 관리할 수 있는 사용 가능한 설정 uri 목록으로 확장 하 고 있습니다. 이러한 Uri 중 일부는 새 설정 앱 내에서 새로 사용할 수 있는 영역에 대 한 것입니다. 설정/PageVisibilityList 정책을 사용 하는 경우 다음 목록을 검토 하 고 필요에 따라 허용 되거나 차단 된 페이지를 조정 합니다.

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
| 시스템 > Storage > Storage 구성         | `ms-settings:storagepolicies`                      |
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

pc와 기타 HoloLens 2 장치를 포함 하 여 Windows 10 장치 근처와 사물을 공유 합니다.   ->    ->  HoloLens의 파일 또는 url을 PC로 공유 하기 위해 설정 시스템 **공유 환경** 에서 사용해 볼 수 있습니다. 자세한 내용은 [Windows 10에서 주변 장치와 항목을 공유](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)하는 방법을 참조 하세요.

이 기능은 [Connectivity/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)를 통해 관리할 수 있습니다.

### <a name="new-os-diagnostic-traces"></a>새 OS 진단 추적

설정 앱 내에서 이전 문제 해결사 외에도 새로운 OS 업데이트를 위한 새 설정 앱이 추가 되어 새 문제 해결사가 추가 되었습니다. **설정**  ->  **업데이트 &amp; 보안**  >  **문제 해결**  >  **Windows 업데이트** 로 이동 하 고 **시작** 을 선택 합니다. 이렇게 하면 OS 업데이트에 대 한 문제를 재현 하는 동안 추적을 수집 하 여 IT 또는 지원과 관련 된 문제 해결에 더 효과적으로 지원할 수 있습니다.

### <a name="delivery-optimization-preview"></a>배달 최적화 미리 보기

이 HoloLens 업데이트를 사용 하면 Windows Holographic for Business HoloLens 장치에서 다운로드 하기 위해 배달 최적화 설정을 사용 하 여 대역폭 사용량을 줄일 수 있습니다. 이 기능과 권장되는 네트워크 구성에 대한 자세한 설명은 [Windows 10 업데이트에 대한 배달 최적화](/windows/deployment/update/waas-delivery-optimization)에서 제공됩니다.

다음 설정은 관리 화면의 일부로 사용하도록 설정되어 있으며 [Intune에서 구성할 수 있습니다](/mem/intune/configuration/delivery-optimization-settings).

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

이 미리 보기 제공에 대한 몇 가지 주의 사항:

- 이 미리 보기에서 HoloLens 지원은 OS 업데이트만으로 제한됩니다.
- Windows Holographic for Business는 HTTP 다운로드 모드 및 [Microsoft 연결된 캐시 엔드포인트](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)의 다운로드만 지원합니다. 현재 HoloLens 장치에서는 피어 투 피어 다운로드 모드 및 그룹 할당이 지원되지 않습니다.
- HoloLens는 Windows Server Update Services 엔드포인트에 대한 배포 또는 배달 최적화를 지원하지 않습니다.
- 문제를 해결하려면 연결된 캐시 서버에 대한 진단을 수행하거나 **설정** > **업데이트 및 보안** >  **문제 해결** >  **Windows 업데이트** 를 통해 HoloLens에서 HoloLens에 대한 추적을 수집해야 합니다.

### <a name="it-admin---update-checklist"></a>IT 관리자-업데이트 검사 목록

이 검사 목록은 현재 장치 관리 구성에 영향을 줄 수 있는이 기능 업데이트에 추가 되는 기능 또는 사용을 시작 하려는 새로운 기능을 알려 주는 데 도움이 됩니다.

#### <a name="updates-to-kiosk-mode"></a>키오스크 모드 업데이트

[**키오스크 모드에서 새 앱에 대 한 새 AUMIDs를 ✔️ 합니다**](#use-the-new-settings-and-edge-apps-in-kiosk-modes).

이전에는 키오스크에서 설정 앱 또는 Microsoft Edge 앱을 사용 하는 경우 이러한 앱을 다른 앱 ID를 사용 하는 새 앱으로 대체 했습니다. 아래의 [키오스크 모드에서 새 앱에 대 한 새 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 를 읽을 것을 적극 권장 합니다. 그러면 키오스크에서 설정 앱을 계속 유지 하거나 새 Microsoft Edge 앱을 포함할 수 있습니다. 이러한 변경 내용을 지금 수행 하 고 모든 장치에 배포 하 고 업데이트를 더욱 원활 하 게 전환할 수 있습니다.

[**키오스크를 위한 방문자 자동 로그온**](#visitor-auto-logon-for-kiosks)✔️: 

이제 방문자가 자동으로 키오스크에 로그인 할 수 있습니다. 이 동작은 기본적으로 설정 되어 있지만 관리 하거나 사용 하지 않도록 설정할 수 있습니다.

✔️ [**개선 된 키오스크 모드 오류**](#kiosk-mode-behavior-changes-for-handling-of-failures)처리:

로그인 된 AAD 사용자의 AAD 그룹 멤버 자격이 성공적으로 확인 되지 않으면 시작 메뉴에 전역 키오스크 구성 (있는 경우)이 사용 되 고 그렇지 않으면 사용자에 게 빈 시작 메뉴가 표시 됩니다. 빈 시작 메뉴는 직접 설정할 수 있는 구성이 아니라, 키오스크를 사용 하는 경우, 사용자의 구성에 적용 될 수 있거나 할당 된 액세스 구성에 대 한 새로운 조정을 수행 하는 경우에 대 한 지원 부서에이 새로운 처리를 알릴 수 있습니다.

#### <a name="updates-to-page-settings-visibility"></a>페이지 설정 표시 유형 업데이트

[**페이지 설정 표시 유형에 대 한 새 설정 uri** ✔️](#new-settings-uris-for-page-settings-visibility)

현재 [페이지 설정 표시 유형을](settings-uri-list.md) 사용 하는 경우 허용 또는 차단 된 기존 uri를 조정 하는 것이 좋습니다.

#### <a name="updates-for-your-wdac-policy"></a>WDAC 정책에 대 한 업데이트
✔️ 이전에 wdac를 통해 Microsoft Edge 차단 된 경우에는 wdac 정책을 업데이트 해야 합니다. 다음을 검토 하 고 제공 된 샘플 코드를 사용 하세요.
#### <a name="enable-new-endpoints-for-edge"></a>Edge에 대 한 새 끝점 사용
✔️ 프록시 또는 방화벽과 같은 네트워크 끝점 구성을 포함 하는 인프라가 있는 경우 새 Microsoft Edge 앱에 대해 이러한 새 끝점을 사용 하도록 설정 하세요.

#### <a name="newly-configurable-items"></a>새로 구성 가능한 항목

[대체 진단 구성](#configuring-fallback-diagnostics-via-settings-app)✔️: 대체 진단을 수집할 수 있는 경우 및 사용자를 구성할 수 있습니다.

[주변 장치와 항목을 공유](#share-things-with-nearby-devices)하는 ✔️: 가까운 새 공유 기능을 사용 하지 않도록 설정할 수 있습니다.

[새 Microsoft Edge에 대 한 정책 설정을 구성](#configuring-policy-settings-for-the-new-microsoft-edge)하는 ✔️: Microsoft Edge에 사용할 수 있는 새로 구성을 검토 합니다.

#### <a name="new-diagnostic-tool"></a>새 진단 도구

[새 os 진단 추적](#new-os-diagnostic-traces)✔️: os 업데이트와 관련 된 로그를 수집 합니다.

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 향상 된 기능 및 수정 사항:

- 또한 [오프 라인 진단](hololens-diagnostic-logs.md#offline-diagnostics) 에는 일련 번호 및 OS 버전에 대 한 추가 장치 정보가 포함 됩니다.
- 런타임 프로 비전 패키지를 통해 lob (기간 업무) 응용 프로그램 배포와 관련 된 문제를 해결 합니다.
- Lob (기간 업무) 응용 프로그램 설치 상태 보고와 관련 된 문제를 해결 합니다.
- 장치를 다시 설정 하는 동안 새 앱 패키지의 지 속성 문제를 해결 합니다.
- 일본어 고객에 대 한 Edge에서 잘못 된 기호가 입력 될 수 있는 문제를 해결 합니다.
- Edge와 같은 사전 설치 된 앱에 대 한 OS 업데이트의 복원 력을 향상 시킵니다. 
- Microsoft Edge 설치에 영향을 주는 업데이트 안정성을 해결 합니다. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, 버전 20H2-2021-5 월 업데이트
- 빌드 19041.1146

업데이트의 향상 된 기능 및 수정 사항:
- 이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않으므로 최신 빌드 Windows Holographic, 버전 21h1을 사용해 보는 것이 좋습니다.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, 버전 1903-2021 업데이트
- 빌드 18362.1110

업데이트의 향상 된 기능 및 수정 사항:
- 이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않습니다. **이 빌드는 더 이상 월별 서비스 업데이트를 받지** 않습니다. 최신 빌드 Windows Holographic, 버전 21h1을 사용해 보는 것이 좋습니다.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, 버전 20H2-4 월 2021 일 업데이트
- 빌드 19041.1144

업데이트의 향상 된 기능 및 수정 사항:

- Lob (기간 업무) 응용 프로그램 설치 상태 보고와 관련 된 문제를 해결 합니다.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, 버전 1903-4 월 2021 업데이트
- 빌드 18362.1108

업데이트의 향상 된 기능 및 수정 사항:

- 로컬 계정에 대 한 암호를 변경 하려고 할 때 설정 앱이 충돌 하는 문제를 해결 합니다.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, 버전 20H2-3 월 2021 일 업데이트
- 빌드 19041.1140

업데이트의 향상 된 기능 및 수정 사항:

- AdvancedPhotoCapture 또는 lowlagphoto 캡처를 사용 하 여 HoloLens 2 사진을 캡처하는 고객은 이제 카메라를 검색할 수 있습니다 사진을 캡처한 후 최대 3 초가 발생 합니다.
- 장치 포털 서비스의 메모리 누수를 수정 합니다 .이 문제로 인해 다른 응용 프로그램에서 메모리 할당에 실패 하는 서비스의 메모리 사용량이 증가 했습니다.
- 스테이징 된 롤아웃에 등록 된 사용자가 장치에 로그인 할 수 없는 문제를 해결 했습니다.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, 버전 1903-3 월 2021 업데이트
- 빌드 18362.1102

업데이트의 향상 된 기능 및 수정 사항:

- 장치 포털 서비스의 메모리 누수를 수정 합니다 .이 문제로 인해 다른 응용 프로그램에서 메모리 할당에 실패 하는 서비스의 메모리 사용량이 증가 했습니다.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, 버전 20H2-2 월 2021 일 업데이트
- 빌드 19041.1136

업데이트의 향상 된 기능 및 수정 사항:

- 초기 장치 설정 및 스토어 앱 업데이트와 관련 된 문제를 해결 합니다.
- 이후 HoloLens 릴리스에 대 한 업그레이드 및 항공편 문제를 해결 합니다.
- HoloLens 장치에서 eSIM 루트 저장소에서 사용 하지 않는 사전 설치 된 인증서를 제거 했습니다.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, 버전 1903-2 월 2021 업데이트
- 빌드 18362.1098

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않으므로 Windows Holographic 버전 2004에 대 한 최신 빌드를 사용해 보는 것이 좋습니다.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, 버전 20H2-1 월 2021 일 업데이트
- 빌드 19041.1134

업데이트의 향상 된 기능 및 수정 사항:

- 장치에 많은 사용자가 있는 경우 시작, 다시 시작 및 사용자 전환 중 성능이 향상 됩니다.
- [연구 모드](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)에 대 한 arm32 지원이 추가 되었습니다.

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, 버전 1903-1 월 2021 업데이트
- 빌드 18362.1091

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않으므로 Windows Holographic 버전 2004에 대 한 최신 빌드를 사용해 보는 것이 좋습니다.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, 버전 20H2 – 12 월 2020 업데이트
- 빌드 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>앱 설치 관리자를 통해 HoloLens 2에 앱 설치

HoloLens 2 장치에 **더욱 원활 하 게 응용 프로그램을 설치할 수 있도록 새 기능 (앱 설치 관리자)을 추가 하** 고 있습니다. 이 기능은 **기본적으로 관리 되지 않는 장치에 대해 설정** 됩니다. 엔터프라이즈 중단을 방지 하기 위해 지금은 **관리 되는 장치에 대해** 앱 설치 관리자를 사용할 수 없습니다.  

다음 조건 중 **하나** 에 해당 하는 경우 장치는 "관리" 된 것으로 간주 됩니다.
- MDM [등록](hololens-enroll-mdm.md) 됨
- [프로 비전 패키지](hololens-provisioning.md) 를 사용 하 여 구성
- 사용자 [id](hololens-identity.md) 는 Azure AD입니다.

이제 개발자 모드를 사용 하도록 설정 하거나 장치 포털을 사용 하지 않고도 앱을 설치할 수 있습니다.  (USB를 통해 또는 Edge를 통해) Appx 번들을 장치에 다운로드 하 고 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지를 표시 합니다.  또는 [웹 페이지에서 설치를 시작](/windows/msix/app-installer/installing-windows10-apps-web)합니다.  MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 서명 [도구](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 를 사용 하 여 앱을 디지털 서명 해야 하며, [서명 하는 데 사용 된 인증서](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 를 HoloLens 장치에서 신뢰할 수 있어야 앱을 배포할 수 있습니다.

**응용 프로그램 설치 지침**

1.  장치가 관리 되는 것으로 간주 되지 않는지 확인 합니다.
1.  HoloLens 2 장치가 켜져 있고 PC에 연결 되어 있는지 확인 합니다.
1.  HoloLens 2 장치에 로그인 했는지 확인 합니다.
1.  pc에서 사용자 지정 앱으로 이동 하 고 yourapp을 yourdevicename\Internal Storage \downloads.에 복사 합니다.   파일 복사를 완료 한 후 장치 연결을 끊을 수 있습니다.
1.  HoloLens 2 장치에서 시작 메뉴를 열고 모든 앱을 선택 하 고 파일 탐색기 앱을 시작 합니다.
1.  다운로드 폴더로 이동 합니다. 앱의 왼쪽 패널에서이 장치를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.
1.  Yourapp 파일을 선택 합니다.
1.  앱 설치 관리자가 시작 됩니다. 설치 단추를 선택 하 여 앱을 설치 합니다.
설치 완료 시 설치 된 앱이 자동으로 시작 됩니다.

이 흐름을 테스트 하기 위해 [Windows 범용 샘플 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 에서 샘플 앱을 찾을 수 있습니다.

[앱 설치 관리자를 사용 하 여 HoloLens 2에 앱을 설치 하](app-deploy-app-installer.md)는 전체 프로세스를 참조 하세요.  

![App Installer를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 향상 된 기능 및 수정 사항:

- 이제 수동 추적은 이전에 손실 된 많은 새 사례에서 추적을 유지 관리 합니다.  이러한 새로운 경우 중 일부는 사용자의 실제 손에 따라 팜 위치만 계속 업데이트 되는 반면 다른 조인트는 이전 포즈를 기반으로 유추 됩니다.  이러한 변경으로 slapping, throw, scooping 및 박수와 같은 이동의 추적 일관성을 향상 시킬 수 있습니다.  또한 손을 표면에 가까이 있거나 개체를 보유 하는 경우에도 유용 합니다.  직접 조인트를 유추 하는 경우에는 [조인트 당 정확도](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 값이 "High" 대신 "근사치"로 설정 됩니다.
- Azure AD 계정에 대 한 PIN을 다시 설정 하는 동안 오류가 발생 하는 문제가 해결 되었습니다.
- 사용자에 게는 설정 앱에서 Iri, 새 사용자 또는 알림 알림을 시작할 때 부팅 후 OOBE 크래시가 훨씬 줄어듭니다.
- 사용자는 OOBE에서 들어오는 올바른 표준 시간대가 있어야 합니다.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, 버전 1903 – 12 월 2020 업데이트
- 빌드 18362.1088

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함 되어 있지 않습니다. 최신 Windows Holographic, 버전 20h2 – 12 월 2020 업데이트 및 빌드에 추가 된 새 앱 설치 관리자 기능을 사용해 보는 것이 좋습니다.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, 버전 20H2
- 빌드 19041.1128

Windows Holographic, 이제 버전 20h2를 사용할 수 있으며, 사용자와 IT 전문가에 게 HoloLens 2 다양 한 새로운 기능을 제공 합니다. 자동 눈 위치 지정, 설정의 인증서 관리자, 향상 된 키오스크 모드 기능 및 새로운 Autopilot 설치 기능을 제공 합니다. 이 새로운 업데이트를 통해 IT 팀은 HoloLens 장치를 구성 하 고 관리 하는 보다 세부적인 제어를 수행할 수 있으며 사용자에 게 보다 원활한 holographic 환경을 제공 합니다. 

이 최신 릴리스는 버전 2004에 대 한 월별 업데이트 이지만 이번에는 새로운 기능을 포함 하 고 있습니다. 주 빌드 번호는 동일 하 게 유지 되 고 Windows 업데이트 버전 2004 (빌드 19041)에 대 한 월간 릴리스를 표시 합니다. 설정 > 정보 화면에서 빌드 번호를 확인 하 여 사용 가능한 최신 빌드 19041.1128 +에 있는지 확인할 수 있습니다. 최신 릴리스로 업데이트 하려면 설정 앱을 열고 업데이트 & 보안으로 이동한 후 업데이트 확인을 탭 합니다. HoloLens 업데이트를 관리 하는 방법에 대 한 자세한 내용은 [HoloLens 업데이트 관리](hololens-updates.md)를 참조 하세요.

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic, 버전 20h2의 새로운 기능  

| 기능                                              | 설명                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [자동 눈 위치 지원](hololens-release-notes.md#auto-eye-position-support) | 사용자가 눈 추적 보정을 거치지 않고 눈 위치를 적극적으로 계산 합니다.   |
| [인증서 관리자](hololens-release-notes.md#certificate-manager)   | 설정 앱에서 더 간단한 방법으로 인증서를 설치 하 고 제거할 수 있습니다.     |
| [USB에서 프로 비전 자동 시작](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 드라이브에서 패키지를 프로 비전 하면 자동으로 OOBE의 프로 비전 페이지에 표시 됩니다.                                                         |
| [OOBE에서 프로 비전 패키지 자동 확인](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 프로 비전 패키지는 OOBE 중 프로 비전 페이지에서 자동으로 적용 됩니다.                                                         |
| [UI를 사용 하지 않고 자동 프로 비전](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 프로 비전 자동 시작 및 자동 확인을 함께 결합 하는 방법입니다. |
| [Wi-Fi 연결에서 Autopilot 사용](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 이더넷 어댑터 없이 장치 Wi-Fi에서 autopilot를 사용 합니다. |
| [Tenantlockdown CSP 및 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 테 넌 트를 등록 하 고 정책을 적용 한 후에는 장치를 다시 설정 하거나 다시 보낼 때마다 장치를 해당 테 넌 트에만 등록할 수 있습니다. |
| [전역 할당 액세스](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 시스템 수준에서 키오스크를 적용 하 여 모든 앱에 적용할 수 있도록 하는 여러 앱 키오스크 모드에 대 한 새 구성 방법입니다.                  |
| [다중 앱 키오스크에서 앱 자동 시작](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 다중 앱 키오스크 모드에 로그인 할 때 자동으로 시작 되도록 응용 프로그램을 설정 합니다.                                                        |
| [오류 처리에 대 한 키오스크 모드 동작 변경 내용](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드 오류는 이제 제한적 대체를 포함 합니다.                                                                                                |
| [HoloLens 방침](hololens-release-notes.md#hololens-policies)                                    | HoloLens에 대 한 새 정책입니다.     |
| [오프 라인 키오스크를 위한 Azure AD 그룹 멤버 자격 캐시](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 새 정책을 통해 사용자는 그룹 멤버 자격 캐시를 사용 하 여 설정 된 일 수 동안 오프 라인 상태에서 키오스크 모드를 사용할 수 있습니다.                                        |
| [HoloLens 2에 대 한 새 장치 제한 정책](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 장치 관리 정책을 사용 하도록 설정 된 HoloLens 2 새로 사용 하도록 설정 되었습니다.                                                                                |
| [HoloLens 2에 대 한 새 전원 정책](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 전원 제한 시간 설정에 대해 새로 지원 되는 정책입니다.  |
| [정책 업데이트](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 업데이트 제어를 허용 하는 새로 설정 된 정책           |
| [HoloLens 2에 대 한 설정 페이지 표시 유형 사용](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 설정 앱에 표시 되는 페이지를 선택 하는 정책입니다.             |
| [연구 모드](hololens-release-notes.md#research-mode) | HoloLens 2에서 연구 모드를 사용 합니다. |
| [기록 길이가 증가 함](hololens-release-notes.md#recording-length-increased) | MRC 기록은 더 이상 5 분으로 제한 되지 않습니다. |
| [업데이트의 향상 된 기능 및 수정 사항](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 업데이트의 추가 수정 사항입니다.   |

### <a name="auto-eye-position-support"></a>자동 눈 위치 지원

HoloLens 2에서 눈 위치는 홀로그램 위치 지정, 편안 하 게 보기 경험 및 향상 된 디스플레이 품질을 제공 합니다. 눈 위치는 시선 추적 계산의 일부로 내부적으로 계산됩니다. 그러나, 이를 위해서는 각 사용자가 환경에 눈 응시 입력이 필요하지 않은 경우에도 시선 추적 보정을 거쳐야 합니다.

**AEP(자동 눈 위치)** 를 사용하면 이러한 시나리오에서 상호 작용 없이 사용자의 눈 위치를 계산할 수 있습니다. 자동 눈 위치는 사용자가 장치를 배치 하는 순간부터 백그라운드에서 자동으로 작업을 시작 합니다. 사용자에 게 이전 눈 추적 보정이 없으면 자동 눈 위치가 20-30 초 후에 표시 시스템에 사용자의 눈 위치를 제공 하기 시작 합니다. 사용자 데이터는 장치에서 지속 되지 않으므로 사용자가 장치를 사용 하지 않도록 설정 하 고 장치를 다시 부팅 하거나 절전 모드에서 해제 하는 경우이 프로세스가 반복 됩니다.

보정되지 않은 사용자가 장치를 착용하면 자동 눈 위치 기능을 통해 몇 가지 시스템 동작이 변경됩니다. 이 컨텍스트에서 uncalibrated 사용자는 이전에 장치에서 눈 추적 보정 프로세스를 거치지 않은 사용자를 가리킵니다.

| 활성 응용 프로그램 | 이전 동작 | Windows Holographic, 버전 20H2 업데이트의 동작 |
|:-------------------|:-----------------|:-----------------------------------|
| 비응시 사용 앱 또는 홀로그램 셸 |시선 추적 보정 프롬프트 대화 상자가 표시됩니다. | 프롬프트가 표시되지 않습니다. |
| 응시 사용 앱 | 시선 추적 보정 프롬프트 대화 상자가 표시됩니다. | 시선 추적 보정 프롬프트는 응용 프로그램이 시선 응시 스트림에 액세스하는 경우에만 표시됩니다. |

사용자가 비응시 사용 응용 프로그램에서 응시 데이터에 액세스하는 응용 프로그램으로 전환하는 경우 보정 프롬프트가 표시됩니다. 

현재 사용자에 게 활성 눈 추적 보정이 없는 경우 다른 모든 시스템 동작은와 유사 합니다. 예를 들어 단방향 시작 제스처는 사용할 수 없습니다. 초기 설정에 대한 OOBE는 변경되지 않습니다.

아이 응시 데이터 나 매우 정확한 홀로그램 위치가 필요한 환경의 경우 uncalibrated 사용자에 게 눈 추적 보정을 실행 하는 것이 좋습니다. 이 파일은 눈 추적 보정 프롬프트에서 액세스 하거나, 시작 메뉴에서 설정 앱을 시작한 다음, 눈동자 보정을 **> >는 시스템 > 보정** 을 선택 하 여 눈동자 보정을 실행할 수 있습니다.

이 정보는 나중에 [다른 보정 정보](hololens-calibration.md#auto-eye-position-support)를 사용 하 여 찾을 수 있습니다. 

### <a name="certificate-manager"></a>인증서 관리자

- 새 인증서 관리자를 통해 장치 보안 및 규정 준수에 대 한 감사, 진단 및 유효성 검사 도구가 개선 되었습니다. 이 기능을 사용 하면 상업적 환경에서 대규모로 인증서를 배포 하 고, 문제를 해결 하 고, 유효성을 검사할 수 있습니다.

Windows Holographic 버전 20h2에서 HoloLens 2 설정 앱에 인증서 관리자를 추가 합니다. **설정 > 업데이트 & 보안 > 인증서** 로 이동 합니다. 이 기능은 장치에서 인증서를 보고 설치 하 고 제거 하는 간단 하 고 사용자에 게 친숙 한 방법을 제공 합니다. 새 인증서 관리자를 사용 하면 관리자와 사용자가 향상 된 감사, 진단 및 유효성 검사 도구를 사용 하 여 장치가 안전 하 고 규정을 준수 하도록 할 수 있습니다. 

-   **감사:** 인증서가 올바르게 배포 되었는지 확인 하거나 적절 하 게 제거 되었는지 확인 하는 기능입니다. 
-   **진단:** 문제가 발생 하는 경우 장치에 적절 한 인증서가 있는지 확인 하면 시간이 절약 되 고 문제 해결에 도움이 됩니다. 
-   **유효성 검사:** 인증서가 의도 된 용도를 제공 하 고 작동 하는지 확인 하면, 특히 상업적 환경에서 더 큰 규모로 인증서를 배포 하기 전에 상당한 시간을 절약할 수 있습니다.

목록에서 특정 인증서를 빠르게 찾기 위해 이름, 매장 또는 만료 날짜별로 정렬 하는 옵션이 있습니다. 사용자가 직접 인증서를 검색할 수도 있습니다. 개별 인증서 속성을 보려면 인증서를 선택 하 고 **정보** 를 클릭 합니다. 

인증서 설치는 현재 .cer 및 .crt 파일을 지원 합니다. 장치 소유자는 로컬 컴퓨터 및 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자 에게만 설치할 수 있습니다. 사용자는 설정 UI에서 직접 설치 된 인증서만 제거할 수 있습니다. 인증서가 다른 방법으로 설치 된 경우에도 동일한 메커니즘을 사용 하 여 인증서를 제거 해야 합니다.

#### <a name="to-install-a-certificate"></a>인증서를 설치 하려면: 

1.  pc에 HoloLens 2를 커넥트 합니다.
1.  설치 하려는 인증서 파일을 HoloLens 2 위치에 배치 합니다.
1.  설정 App으로 이동 하 **> & 보안 > 인증서를 업데이트** 하 고 인증서 설치를 선택 합니다.
1.  **파일 가져오기** 를 클릭 하 고 인증서를 저장 한 위치로 이동 합니다.
1.  **저장소 위치** 를 선택 합니다.
1.  **인증서 저장소** 를 선택 합니다.
1.  **설치** 를 클릭합니다.

이제 인증서가 장치에 설치 됩니다.

#### <a name="to-remove-a-certificate"></a>인증서를 제거 하려면: 
1. **설정 App > Update 및 Security > 인증서** 로 이동 합니다.
1. 검색 상자에서 이름으로 인증서를 검색 합니다.
1. 인증서를 선택합니다.
1. **제거** 클릭
1. 확인하라는 메시지가 표시되면 **예** 를 선택합니다.

![설정 앱의 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용 하 여 인증서를 설치 하는 방법을 보여 주는 그림](images/certificate-device-install.jpg)

이 정보는 나중에 [새 인증서 관리자 페이지에서](certificate-manager.md)찾을 수 있습니다.

### <a name="auto-launch-provisioning-from-usb"></a>USB에서 프로 비전 자동 시작

- 프로 비전 패키지를 사용 하는 USB 드라이브가 OOBE 중에 사용 되는 경우 사용자 상호 작용을 줄일 수 있는 자동화 된 프로세스입니다.

이 릴리스는 사용자가 단추 조합을 사용 하 여 프로 비전 하는 동안 수동으로 프로 비전 화면을 시작 해야 합니다. 이제 사용자가 USB 저장소 드라이브에서 프로 비전 패키지를 사용 하 여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE의 첫 번째 interactable 순간에 프로 비전 패키지를 사용 하 여 USB 드라이브에 연결
1. 장치를 프로 비전 할 준비가 되 면 프로 비전 페이지를 사용 하 여 프롬프트가 자동으로 열립니다. 

참고: 장치가 부팅 되는 동안 USB 드라이브가 연결 된 상태를 유지 하는 경우 OOBE는 기존 USB 저장 장치를 열거 하 고 연결 되는 추가 항목을 감시 합니다.

OOBE 중에 프로 비전 패키지를 적용 하는 방법에 대 한 자세한 내용은 [HoloLens 프로 비전](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 설명서를 참조 하세요.

[USB에서 자동 시작을 프로 비전](hololens-provisioning.md#auto-launch-provisioning-from-usb) 하는 방법에 대 한 자세한 내용은 HoloLens 프로 비전 설명서를 참조 하세요.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE에서 프로 비전 패키지 자동 확인
- 사용자 상호 작용을 줄일 수 있는 자동화 된 프로세스, 프로 비전 패키지 페이지가 표시 되 면 나열 된 모든 패키지가 자동으로 적용 됩니다.

프로 비전 주 화면이 나타나면 OOBE는 모든 프로 비전 패키지 적용을 자동으로 시작 하기 전에 10 초 후에 계산 됩니다. 사용자는 예상 되는 패키지를 확인 한 후이 10 초 내에 계속 [확인 하거나 취소할](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 수 있습니다.

### <a name="automatic-provisioning-without-using-ui"></a>UI를 사용 하지 않고 자동 프로 비전
- 프로 비전을 위해 장치 상호 작용을 줄이는 자동 프로세스를 결합 했습니다. 

USB 장치에서 프로 비전의 자동 시작과 프로 비전 패키지의 자동 확인을 결합 하 여 사용자는 장치 UI를 사용 하거나 장치를 출시 하지 않고 자동으로 HoloLens 2 장치를 프로 비전 할 수 있습니다. 여러 장치에 대해 동일한 USB 드라이브 및 프로 비전 패키지를 계속 사용할 수 있습니다. 이는 동일한 영역에서 한 번에 여러 장치를 배포 하는 데 유용 합니다. 

1. [Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22)를 사용 하 여 [프로 비전 패키지를 만듭니다](hololens-provisioning.md) . 
1. 패키지를 USB 저장소 드라이브에 복사 합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) 를 [19041.1361 이상 빌드로](https://aka.ms/hololens2previewdownload)깜박입니다. 
1. [Advanced Recovery 도우미가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 성공적으로 깜박이는 경우 장치가 USB-C 케이블을 분리 합니다. 
1. 장치에 USB 드라이브를 연결 합니다.
1. HoloLens 2 장치가 OOBE로 부팅 되 면 USB 드라이브에서 프로 비전 패키지를 자동으로 검색 하 고 프로 비전 페이지를 시작 합니다.
1. 10 초 후에 장치가 프로 비전 패키지를 자동으로 적용 합니다. 

이제 장치가 구성 되어 [프로 비전 성공 화면이 표시](hololens-provisioning.md#automatic-provisioning-without-using-ui)됩니다.

### <a name="using-autopilot-with-wi-fi-connection"></a>Wi-Fi 연결에서 Autopilot 사용
- Autopilot가 연결 된 장치 Wi-Fi 기능을 사용할 수 있도록 하 여 하드웨어 요구 사항을 줄이는 USB C 어댑터의 필요를 제거 했습니다.

이제 oobe 중에 wi-fi를 사용 하 여 HoloLens 2 연결 하면 oobe가 해당 장치에 대 한 Autopilot 프로필을 확인 합니다. 하나를 찾은 경우 AAD 조인 및 등록 흐름의 나머지를 완료 하는 데 사용 됩니다. 즉, usb-C에 대 한 이더넷 또는 USB C 어댑터에 Wi-Fi를 사용 하는 것은 더 이상 요구 사항이 아니지만 OOBE 시작 시 제공 되는 경우 계속 작동 합니다. [HoloLens 2 장치에 대 한 Autopilot](hololens2-autopilot.md)에 대해 자세히 알아보세요.

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 및 Autopilot
- 장치를 다시 설정 하거나 경감 하기 위해 하는 경우에도 테 넌 트에 장치를 잠가 조직의 테 넌 트에 장치를 보관 합니다. 프로 비전을 통해 계정 생성을 허용 하지 않는 추가 보안. 

HoloLens 2 장치는 이제 [Windows Holographic 버전 20h2](hololens-release-notes.md#windows-holographic-version-20h2)에서 tenantlockdown CSP를 지원 합니다. 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용하여 HoloLens 2를 MDM 등록에 연결할 수 있습니다. TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false(초기 설정) 값으로 설정되면 리플래시, OS 업데이트 등을 수행해도 해당 값이 장치에 그대로 유지됩니다. 

HoloLens 2에서 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드되고 적용될 때까지 무기한 대기합니다. 

HoloLens 2에서 TenantLockdown CSP의 RequireNetworkInOOBE 노드가 true로 설정되면 OOBE에서 다음 작업을 수행할 수 없습니다. 
- 런타임 프로비전을 사용하여 로컬 사용자 만들기 
- 런타임 프로비전을 통해 Azure AD 조인 작업 수행 
- OOBE 환경에서 장치를 소유하는 사용자 선택 

#### <a name="how-to-set-this-using-intune"></a>Intune을 사용하여 설정하는 방법은 무엇인가요? 
1. 사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.
OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 테넌트 잠금 설정](images/hololens-tenant-lockdown.png)

1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 시작합니다.  

Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 활성화됩니다.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune을 사용하여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제하는 방법은 무엇인가요? 
1. 위에서 만든 장치 구성이 이전에 할당되었던 장치 그룹에서 HoloLens 2를 제거합니다. 

1. 사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE를 false로 지정합니다. OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE여야 합니다.

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 멤버를 만들고 동기화를 시작합니다.

Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 비활성화됩니다. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true로 설정된 후 HoloLens에서 Autopilot 프로필이 할당되지 않은 경우 OOBE 중에 무슨 문제가 발생하나요? 
Autopilot 프로필이 다운로드될 때까지 OOBE가 무기한 대기하고 다음 대화 상자가 표시됩니다. TenantLockdown 효과를 제거하려면 먼저 Autopilot만 사용하여 장치를 원래 테넌트에 등록해야 하며, TenantLockdown CSP에서 도입한 제한 사항이 제거되기 전에 이전 단계에서 설명한 대로 RequireNetworkInOOBE를 설정 해제해야 합니다. 

![장치에서 정책이 시행될 때의 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

이 정보는 이제 [Tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)아래 Autopilot의 나머지 부분과 함께 찾을 수 있습니다.

### <a name="global-assigned-access--kiosk-mode"></a>전역 할당 액세스-키오스크 모드
- 시스템 수준에서 키오스크 모드를 적용 하는 새 키오스크 방법을 사용 하도록 설정 하 여 키오스크에 대 한 Id 관리를 줄였습니다.

이 새로운 기능을 사용 하면 IT 관리자가 시스템 수준에서 적용할 수 있는 여러 앱 키오스크 모드에 대 한 HoloLens 2 장치를 구성 하 고, 시스템의 id로 선호도를 적용 하지 않으며, 장치에 로그인 하는 모든 사용자에 게 적용할 수 있습니다. 이 새로운 기능에 대 한 자세한 내용은 [HoloLens global 할당 된 액세스 키오스크](hololens-global-assigned-access-kiosk.md)를 참조 하세요.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>다중 앱 키오스크 모드에서 응용 프로그램 자동 시작 
- 자동 앱 시작에 초점을 맞춘 경험을 통해 키오스크 모드 환경에 대해 선택한 UI 및 앱 선택 항목을 더 늘립니다.

다중 앱 키오스크 모드에만 적용 되며 할당 된 액세스 구성에서 아래 강조 표시 된 특성을 사용 하 여 자동으로 실행 되도록 1 개의 앱만 지정할 수 있습니다. 

사용자가 로그인 하면 응용 프로그램이 자동으로 시작 됩니다. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>오류 처리에 대 한 키오스크 모드 동작 변경 내용
- 키오스크 모드 오류 시 사용 가능한 앱을 제거 하 여 더 안전한 키오스크 모드. 

키오스크 모드를 적용 하는 동안 오류가 발생 하는 경우 시작 메뉴에 모든 응용 프로그램을 표시 하는 데 사용 HoloLens. 현재 Windows Holographic 버전 20h2의 경우 시작 메뉴에 아래와 같이 앱이 표시 되지 않습니다. 

![이제 실패할 때 표시 되는 키오스크 모드 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens 방침
- 장치 관리를 위해 생성 된 HoloLens에 대 한 장치 관리 옵션입니다. 

Windows Holographic 버전 20h2의 HoloLens 2 장치에 대해 새로운 혼합 현실 정책이 생성 되었습니다. 제어 가능한 새 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음 사용 안 함, 진단을 수집할 수 있는 경우 설정 및 AAD 그룹 멤버 자격 캐시가 포함 됩니다.  

| 새 HoloLens 정책                                | 설명                                                                               | 메모                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 밝기 단추를 사용 하지 않도록 설정 하 여 밝기를 변경 하지 않도록 합니다.       | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\VolumeButtonDisabled                  | 볼륨 단추를 사용 하지 않도록 설정할 수 있으므로 볼륨을 변경 하지 않습니다.               | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2에서 오디오 기록을 사용할 수 없도록 마이크를 사용 하지 않도록 설정 합니다.                      | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\FallbackDiagnostics                   | 진단 로그를 수집할 수 있는 경우의 동작을 제어 합니다.                               | 0 사용 안 함, 1 장치 소유자에 대해 1 사용, 2 모두 사용 (기본값) |
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
1. 이제 Azure AD 사용자 1이 오프 라인에서 HoloLens 하 고, 정책 값에서 X 일 수를 허용 하는 한 키오스크 모드에 사용할 수 있습니다. 
1. 다른 모든 Azure AD 사용자에 대해 4 단계와 5 단계를 반복할 수 있습니다. 중요 한 점은 Azure AD 사용자가 인터넷을 사용 하 여 장치에 로그인 해야 하는 것입니다 .이는 적어도 한 번은 키오스크 구성이 대상으로 하는 Azure AD 그룹의 구성원 인지 확인할 수 있습니다. 
 
> [!NOTE]
> Azure AD 사용자에 대해 4 단계를 수행 하기 전에는 "연결이 끊어진" 환경에서 언급 한 오류 동작이 발생 합니다. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2에 대 한 새 장치 제한 정책
- 사용자가 프로 비전 패키지 추가 또는 제거 차단과 같은 특정 장치 관리 정책을 관리할 수 있습니다.

HoloLens 2 장치의 추가 관리 옵션을 허용 하는 새로 설정 된 정책입니다. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 및 AllowRemoveProvisioningPackage에 대 한 두 가지 새로운 정책은 [일반적인 장치 제한](hololens-common-device-restrictions.md)에 추가 됩니다.

> [!NOTE]
> [remotelock](/windows/client-management/mdm/remotelock-csp)과 관련 하 여 HoloLens는/Vendor/MSFT/RemoteLock/Lock 구성만 지원 합니다. 재설정 및 복구와 같은 PIN을 처리 하는 구성은 지원 되지 않습니다.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2에 대 한 새 전원 정책
- 전원 정책을 통해 HoloLens를 대기 또는 잠금 하는 경우에 대 한 추가 옵션입니다. 

이러한 새로 추가 된 정책을 통해 관리자는 유휴 시간 제한 등의 전원 상태를 제어할 수 있습니다. 각 개별 정책에 대 한 자세한 내용을 보려면 해당 정책에 대 한 링크를 클릭 하세요.

|     정책 설명서 링크                |     메모                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 구성 디자이너에서 사용할 예제 값 (예:)`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 구성 디자이너에서 사용할 예제 값 (예:)`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 구성 디자이너에서 사용할 예제 값 (예: 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 구성 디자이너에서 사용할 예제 값 (예: 100                                                                          |
|     [Bytimeouton배터리](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 구성 디자이너에서 사용할 예제 값 (예:)`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 구성 디자이너에서 사용할 예제 값 (예:)`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

이러한 두 가지 새 정책 DisplayOffTimeoutOnBattery 및 DisplayOffTimeoutPluggedIn는 [일반적인 장치 제한](hololens-common-device-restrictions.md)에 추가 됩니다.

> [!NOTE]
> HoloLens 2 일관된 환경을 위해 DisplayOffTimeoutOnBattery 및 StandbyTimeoutOnBattery의 값이 동일한 값으로 설정되어 있는지 확인하세요. DisplayOffTimeoutPluggedIn 및 StandbyTimeoutPluggedIn에도 동일하게 적용됩니다. 최신 대기에 대한 자세한 내용은 [표시, 절전 모드 및 최대 절전 모드 유휴 타이머를](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 참조하세요.

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens 대해 새로 사용하도록 설정된 업데이트 정책
- 업데이트를 설치하거나 업데이트 일시 중지 단추를 사용하지 않도록 설정한 경우에 대한 추가 옵션입니다.

이러한 업데이트 정책은 이제 HoloLens 2 디바이스에서 사용하도록 설정됩니다.
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

이러한 업데이트 정책 및 HoloLens 디바이스에 사용하는 방법에 대한 자세한 내용은 HoloLens [업데이트 관리에서](hololens-updates.md)확인할 수 있습니다.

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 대해 설정 페이지 표시 유형 사용
- 설정 앱에서 UI 컨트롤이 향상되었습니다. 제한된 페이지 선택 항목을 표시하면 혼동될 수 있습니다.

이제 IT 관리자가 System 설정 앱의 특정 페이지를 보거나 액세스할 수 없도록 하거나 지정된 페이지를 제외한 모든 페이지에 대해 이 작업을 수행할 수 있는 정책을 사용하도록 설정했습니다. 이 기능을 완전히 사용자 지정하는 방법을 알아보려면 아래 링크를 클릭합니다.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 사용자 지정할 수 있는 페이지 설정을 알아보려면 [설정 URIS 페이지를](settings-uri-list.md)방문하세요. 
 
![설정 앱에서 수정되는 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>연구 모드
연구 모드에서는 HoloLens 2 컴퓨터 비전 연구를 위한 도구가 됩니다. 이전 버전에 비해 HoloLens 2 연구 모드에는 다음과 같은 이점이 있습니다.
-   HoloLens(1세대) 연구 모드에 노출된 센서 외에도 이제 가속도계, 자이록 범위 및 지자기계를 포함한 IMU 센서 액세스를 제공합니다.
-   HoloLens 2 연구 모드와 함께 사용할 수 있는 새로운 기능을 제공합니다. 특히 풍부한 실험 세트를 제공할 수 있는 명확한 손 추적 및 시선 추적 API에 액세스할 수 있습니다.

이제 연구원이 HoloLens 디바이스에서 연구 모드를 사용하도록 설정하여 이러한 모든 외부에 연결된 원시 이미지 센서 스트림에 액세스할 수 있습니다. 또한 HoloLens 2 연구 모드에서는 가속도계, 자이록 범위 및 지자기계 판독값에 액세스할 수 있습니다. 사용자의 개인 정보를 보호하기 위해 원시 시선 추적 카메라 이미지는 연구 모드를 통해 사용할 수 없지만 기존 API를 통해 시선 응시 방향을 사용할 수 있습니다.

자세한 기술 정보는 [연구 모드 설명서를 참조하세요.](/windows/mixed-reality/research-mode)

### <a name="recording-length-increased"></a>기록 길이가 증가했습니다.
고객 피드백으로 인해 혼합 현실 캡처의 기록 [길이가 증가했습니다.](holographic-photos-and-videos.md) 혼합 현실 캡처는 더 이상 기본적으로 5분으로 제한되지 않지만 대신 사용 가능한 디스크 공간에 따라 최대 기록 길이를 계산합니다. 디바이스는 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 총 디스크 공간의 80%까지 예측합니다.

> [!NOTE]
> HoloLens 다음 중 하나가 발생하는 경우 기본 비디오 녹화 길이(5분)를 사용합니다.
> - 예상 최대 기록 기간은 기본값인 5분보다 작습니다.
> - 사용 가능한 디스크 공간이 전체 디스크 공간의 20% 미만입니다.

[홀로그램 사진 및 비디오](holographic-photos-and-videos.md#maximum-recording-length) 설명서에서 전체 요구 사항을 찾을 수 있습니다. 

### <a name="improvements-and-fixes-in-the-update"></a>업데이트의 개선 사항 및 수정 사항:
- 이제 OOBE의 더 많은 화면이 어두운 모드에 있습니다.
- 최신 개인정보처리방침 온라인을 가리킨 콘텐츠에 대해 자세히 알아보세요.
- 사용자가 프로비전 패키지를 통해 VPN 프로필을 프로비전할 수 없는 문제를 해결했습니다.
- VPN 연결에 대한 프록시 구성 문제가 해결되었습니다.
- AllowUsbConnection에 대한 NCM용 MDM을 통해 USB 함수의 열거를 사용하지 않도록 설정하는 정책이 업데이트되었습니다.
- 디바이스가 [단일 앱 키오스크로](hololens-kiosk.md)설정된 경우 HoloLens 디바이스가 MTP(미디어 전송 프로토콜)를 통해 파일 탐색기 표시되지 않도록 하는 문제를 해결했습니다. MTP(및 일반적으로 USB 연결)는 [AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 정책을 사용하여 계속 사용하지 않도록 설정될 수 있습니다.
- 키오스크 모드에서 시작 메뉴 아이콘의 크기가 올바르게 조정되는 문제를 해결했습니다.
- Azure AD 그룹을 대상으로 하는 키오스크 모드를 방해하는 HTTP 캐싱으로 인한 문제가 해결되었습니다.
- 사용자가 개발자 모드를 사용하지 않도록 설정했다가 다시 사용하도록 설정하지 않는 한 프로비저닝 패키지에서 개발자 모드를 사용하도록 설정한 후 페어링 단추를 사용할 수 없는 문제를 해결했습니다.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 11월 업데이트
- 빌드 18362.1085

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되어 있지 않으므로 Holographic 버전 20H2를 Windows 최신 기능 릴리스 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows 홀로그램 버전 2004 - 2020년 10월 업데이트
- 빌드 19041.1124
 
업데이트의 개선 사항 및 수정 사항:

- 런타임 시스템 오류를 발생시킨 불필요한 검사가 제거되었습니다.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 10월 업데이트
- 빌드 18362.1081

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다. Windows Holographic 버전 2004에 대한 최신 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows 홀로그램 버전 2004 - 2020년 9월 업데이트
- 빌드 19041.1117

업데이트의 개선 사항 및 수정 사항:

- supportsMultipleInstances="true"가 appxmanifest에 있는 경우 Visual Studio 애플리케이션을 디버깅하지 못하게 하는 문제를 해결합니다.
- 이 릴리스에는 네트워크 프록시를 통해 실패한 인터넷 검색을 해결하기 위한 NCSI 프록시 검색 수정이 포함되어 있습니다. NCSI는 인터넷 연결 검색에 컴퓨터 프록시 및 프로필별 프록시를 사용할 수 있습니다. 사용자별 프록시는 향후 릴리스에서 NCSI에서 지원됩니다.
- 대부분의 Windows Mixed Reality 디바이스에서 사용자의 머리가 중립 위치에 있을 때 정방향 벡터는 지면과 병렬로 진행됩니다. 그러나 이전 버전의 HoloLens 2 벡터를 디스플레이 패널에 수직으로 정렬했습니다. 이 벡터는 이상적인 방향을 기준으로 몇 도 아래로 기울어져 있습니다. 최신 버전의 HoloLens 2 폼 팩터 간에 의미 체계 일관성을 보장하기 위해 이를 수정했습니다.
- 특정 시나리오에서 손 추적 견고성이 향상되어 추적 손실이 줄어듭니다.
- 이 릴리스에는 비디오 캡처 문제에 기여했을 수 있는 오디오 타임스탬프 품질을 개선하기 위한 수정이 포함되어 있습니다.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 9월 업데이트
- 빌드 18362.1079

업데이트의 개선 사항 및 수정 사항:

- 대부분의 Windows Mixed Reality 디바이스에서 사용자의 머리가 중립 위치에 있을 때 정방향 벡터는 지면과 병렬로 진행됩니다. 그러나 이전 버전의 HoloLens 2 벡터를 디스플레이 패널에 수직으로 정렬했습니다. 이 벡터는 이상적인 방향을 기준으로 몇 도 아래로 기울어져 있습니다. 최신 버전의 HoloLens 2 폼 팩터 간에 의미 체계 일관성을 보장하기 위해 이를 수정했습니다.
- 특정 시나리오에서 손 추적 견고성이 향상되어 추적 손실이 줄어듭니다.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows 홀로그램 버전 2004 - 2020년 8월 업데이트
- 빌드 19041.1113

업데이트의 개선 사항 및 수정 사항:

- 설정 앱은 더 이상 사용자를 따라 아이리스 등록 또는 시선 추적 보정 환경을 이용하지 않습니다.
- OOBE 중에 디바이스 이름을 바꾸고 다른 작업(예: 네트워크에 연결)을 수행하는 프로비전 패키지를 적용하면 이름 바꾸기로 인해 디바이스를 다시 부팅한 후 다른 작업을 수행하지 못하는 버그가 수정되었습니다.
- 시각적 품질을 향상시키기 위해 초기 디바이스 설정 흐름의 색 구성표가 수정되었습니다.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 8월 업데이트
- 빌드 18362.1074

이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다. Windows Holographic 버전 2004에 대한 최신 빌드를 사용해보는 것이 좋습니다.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows 홀로그램 버전 2004 - 2020년 7월 업데이트
- 빌드 19041.1109

업데이트의 개선 사항 및 수정 사항:

- 이제 개발자는 보안 연결이 필요한 장치 포털 설정 또는 비활성화 중에서 선택할 수 있습니다.
- OS 업데이트 후 애플리케이션 시작에 대한 안정성이 향상되었습니다.
- 기본 받은 편지함 밝기를 100%로 변경했습니다.
- HoloLens 2 Windows 장치 포털 대한 HTTPS 전달 관련 문제를 해결했습니다.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 7월 업데이트
- 빌드 18362.1071

업데이트의 개선 사항 및 수정 사항:

- 추적을 손실하거나 다시 복원할 때 Unity 애플리케이션에서 홀로그램이 사라지는 문제를 해결했습니다.
- 특정 디바이스에서 하드웨어 가속과 함께 HoloLens Emulator 사용하는 동안 배타적 HoloLens 앱이 셸에 크래시되는 문제를 해결했습니다.
- HoloLens 2 Windows 장치 포털 대한 HTTPS 전달과 관련된 문제를 해결했습니다.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows 홀로그램 버전 2004 - 2020년 6월 업데이트
- 빌드 19041.1106

업데이트의 향상 된 기능 및 수정 사항:

- 이제 사용자 지정 MRC 레코더는 지정 되지 않은 경우 특정 속성에 대 한 새 기본값을 포함 합니다.
  - *Mrc 비디오 효과*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (모던 헤드셋))
  - *Mrc 오디오 효과*:
    - LoopbackGain (Windows 장치 포털의 혼합 현실 캡처 페이지에서 현재 "앱 오디오 게인" 값)
    - MicrophoneGain (Windows 장치 포털의 혼합 현실 캡처 페이지에서 현재 "Mic 오디오 게인" 값)
- 혼합 현실 캡처 시나리오에서 오디오 품질을 개선 하는 버그를 수정 했습니다. 특히이 픽스는 **시작** 메뉴가 표시 될 때 기록에서 오디오 glitching을 제거 해야 합니다.
- 기록 된 비디오에서 홀로그램 안정성이 개선 되었습니다.
- 장치가 며칠 동안 대기 상태로 유지 된 후 혼합 현실 캡처가 비디오를 녹화 하지 못하는 문제를 해결 했습니다.
- HolographicSpace API는 일반적으로 Unity 응용 프로그램에서 사용할 수 없습니다. 이 동작은 "백그라운드에서 실행" 설정을 사용 하는 경우에도 일부 앱이 시작 될 때 일부 앱을 일시 중지 하는 문제를 방지 합니다. API는 이제 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 사용할 수 있습니다.
- Wi-Fi 연결을 통해 장치 포털에 액세스 하는 경우 웹 브라우저에서 잘못 된 인증서로 인해에 액세스 하지 못할 수 있습니다. 장치 인증서가 이전에 신뢰 된 경우에도 브라우저에서 "ERR_SSL_PROTOCOL_ERROR"와 같은 오류를 보고할 수 있습니다. 이 경우에는 보안 경고를 무시 하는 옵션이 없으므로 장치 포털을 진행할 수 없습니다. 이 업데이트는 문제를 해결 했습니다. 이전에 장치 인증서를 다운로드 하 여 PC에서 다운로드 하 여 브라우저 보안 경고를 제거 하 고 SSL 오류가 발생 한 경우 새 인증서를 다운로드 하 고 신뢰 하 여 브라우저 보안 경고를 해결 해야 합니다.
- MSIX 패키지를 사용 하 여 앱을 설치할 수 있는 런타임 프로 비전 패키지를 만드는 기능이 사용 하도록 설정 되었습니다.
-   >    >  장치가 종료 될 때 사용자가 혼합 현실 홈에서 모든 Holograms을 자동으로 제거할 수 있도록 하는 설정 시스템 **홀로그램스** 의 설정이 추가 되었습니다.
- HoloLens 에뮬레이터에서 검정색을 렌더링 하도록 픽셀 형식을 변경 하는 앱 HoloLens 발생 하는 문제를 해결 했습니다.
- Iri 로그인 중에 충돌을 일으킨 버그를 수정 했습니다.
- 이미 존재 하는 앱에 대 한 반복적인 스토어 다운로드 문제를 수정 했습니다.
- 몰입 형 앱에서 Microsoft Edge를 반복적으로 열지 못하게 하는 버그를 수정 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부팅에서 사진 앱이 시작 될 때 발생 하는 문제를 해결 했습니다.
- 성능 및 안정성이 향상 되었습니다.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, 버전 1903-6 월 2020 업데이트
- 빌드 18362.1064

업데이트의 향상 된 기능 및 수정 사항:

- 사용자 지정 MRC 레코더는 지정 되지 않은 경우 특정 속성에 대 한 새 기본값을 포함 합니다.
  - *Mrc 비디오 효과*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (모던 헤드셋))
  - *Mrc 오디오 효과*:
    - LoopbackGain (Windows 장치 포털의 혼합 현실 캡처 페이지에서 현재 "앱 오디오 게인" 값)
    - MicrophoneGain (Windows 장치 포털의 혼합 현실 캡처 페이지에서 현재 "Mic 오디오 게인" 값)
- HolographicSpace API는 일반적으로 Unity 응용 프로그램에서 사용할 수 없습니다. 이 동작은 배경에서 실행 되는 설정이 사용 되는 경우에도 일부 앱이 실행 될 때 일부 앱을 일시 중지 하는 문제를 방지 합니다. API는 이제 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 사용할 수 있습니다.
- HoloLens Emulator에서 검정색을 렌더링 하도록 픽셀 형식을 변경 하는 HoloLens 앱이 발생 하는 문제를 해결 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부팅에서 사진 앱의 시작에 대 한 문제를 해결 했습니다.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, 버전 2004  
- 빌드-19041.1103

2020 년 5 월 주 소프트웨어 업데이트 HoloLens 2 *Windows Holographic, 버전 2004* 에는 Autopilot Windows에 대 한 지원, 앱 어둡게 모드, 5g/LTE 핫스팟의 USB 이더넷 지원 등과 같은 흥미로운 새 기능의 호스트가 포함 되어 있습니다. 최신 릴리스로 업데이트 하려면 **설정**   앱을 열고  **업데이트 & 보안** 으로 이동한 후  **업데이트 확인** 단추를 선택 합니다   . 

|             기능                              |          설명                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot를 사용 하 여 프로덕션을 위한 새 장치를 미리 구성 하 고 원활 하 게 설정 합니다.                 |
|       FIDO 2 지원                             |          공유 장치에 대해 빠르고 안전한 인증을 사용할 수 있도록 FIDO2 보안 키 지원            |
|       향상 된 프로 비전                      |          프로 비전 패키지를 USB 드라이브에서 HoloLens로 원활 하 게 적용                              |
|       응용 프로그램 설치 상태                 |          앱 용 설정 앱의 설치 상태 확인이 MDM을 통해 HoloLens 2에 푸시 됨               |
|       Csp (구성 서비스 공급자)   |          관리 제어 기능을 향상 시키기 위해 새 구성 서비스 공급자를 추가 했습니다.                 |
|       USB 5G/LTE 지원                       |          확장 된 USB 이더넷 기능을 통해 5G/LTE를 지원할 수 있습니다.                                    |
|       어두운 앱 모드                              |          어두운 모드 및 밝은 모드를 모두 지 원하는 앱에 대해 사용 가능한 어두운 앱 모드, 보기 환경 향상        |
|       음성 명령                             |          HoloLens 실습을 제어 하는 추가 시스템 음성 명령을 지원 합니다.                           |
|       향상 된 기능 추적                 |          향상 된 기능 추적 기능을 통해 단추와 2D 슬레이트 상호 작용을 보다 정확 하 게                        |
|       품질 향상 및 수정                 |          플랫폼 전체의 다양 한 시스템 성능 및 안정성 향상                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot 지원

Windows HoloLens 2 Autopilot를 사용 하면 장치 판매 채널에서 Intune 테 넌 트에 HoloLens 사전 등록할 수 있습니다. 장치가 도착 하면 테 넌 트에서 공유 장치로 자체 배포할 준비가 된 것입니다. 자동 배포를 활용 하려면 USB-C-이더넷을 사용 하 여 설치 프로그램의 첫 번째 화면에서 장치를 네트워크에 연결 해야 합니다.

사용자가 Autopilot 자동 배포 프로세스를 시작 하면 프로세스는 다음 단계를 완료 합니다.

1. 장치를 Azure AD(Azure Active Directory)에 조인합니다.
1. Azure AD를 사용 하 여 Microsoft Intune 또는 다른 MDM 서비스에 장치를 등록 합니다.
1. 장치 대상 정책, 인증서 및 네트워킹 프로필을 다운로드 합니다.
1. 장치를 프로비전합니다.
1. 사용자에게 로그인 화면을 표시합니다.

자세한 내용은 [Windows Autopilot for HoloLens 2 evaluation guide를 참조](hololens2-autopilot.md)하세요.

*지금 AutoPilot 미리 보기에 참여 하려면 계정 관리자에 게 문의 하세요. Autopilot ready 장치는 곧 배송 되기 시작 합니다.*

### <a name="fido2-security-key-support"></a>FIDO2 보안 키 지원

일부 사용자는 회사 또는 학교 환경에서 다른 사용자와 HoloLens 장치를 공유 합니다. 따라서 긴 사용자 이름 및 암호를 입력 하지 않고도 사용자가 쉽게 사용할 수 있는 것이 중요 합니다. FIDO (Fast Identity Online)를 사용 하면 조직 (Azure AD 테 넌 트)의 모든 사용자가 사용자 이름 또는 암호를 입력 하지 않고 HoloLens에 원활 하 게 로그인 할 수 있습니다.

FIDO2 보안 키는 모든 폼 팩터로 제공 될 수 있는 "unphishable" 표준 기반 암호 없는 인증 방법입니다. FIDO는 암호 없는 인증을 위한 개방형 표준입니다. 사용자와 조직이 사용자 이름 또는 암호 없이 해당 리소스에 로그인 할 수 있습니다. 대신 장치에 기본 제공 되는 외부 보안 키 또는 플랫폼 키를 사용 합니다.

시작 하려면 [암호 없는 보안 키 로그인 사용](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)을 참조 하세요.

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>프로 비전 패키지를 통해 MDM 등록 개선

프로 비전 패키지를 사용 하면 HoloLens 기본 환경이 아닌 구성 파일을 통해 HoloLens 구성을 설정할 수 있습니다. 이전에는 프로 비전 패키지를 HoloLens 내부 메모리에 복사 해야 했습니다. 이제는 USB 드라이브에 있을 수 있으므로 여러 HoloLens 장치에서 다시 사용 하기 쉬우며 장치를 병렬로 프로 비전 할 수 있습니다. 프로 비전 패키지는 이제 장치 관리에 등록할 필드도 지원 하므로 프로 비전 후 수동 설정이 없습니다.

기능 사용해 보기:

1. Windows 스토어에서 Windows Configuration Designer의 최신 버전을 PC로 다운로드 합니다.
1. **프로 비전 HoloLens 장치**  >  **프로 비전 HoloLens 2 장치** 를 선택 합니다.
2. 구성 프로필을 작성 합니다. 그런 다음 생성 된 모든 파일을 USB-C 저장소 장치에 복사 합니다.
3. USB-C 디바이스를 새로 플래시된 HoloLens 연결합니다. 그런 다음 **볼륨 다운** 전원 단추를 눌러  +   프로비전 패키지를 적용합니다.

### <a name="line-of-business-application-install-status"></a>사업장 애플리케이션 설치 상태

업무용 앱에 대한 MDM 앱 배포 및 관리는 HoloLens 데 중요합니다. 관리자와 사용자는 감사 및 진단에 대한 앱 설치 상태를 확인해야 합니다. 이 릴리스에서는 **설정**  >  계정회사 또는 학교 **액세스사용자**  >    >  계정 정보 **클릭에서**  >  자세한 내용을 추가했습니다.

### <a name="additional-csps-and-policies"></a>추가 CSP 및 정책

[CSP(구성 서비스 공급자)는](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 디바이스에서 구성 설정을 읽고, 설정하고, 수정하거나, 삭제하는 인터페이스입니다. 이 릴리스에서는 관리자가 배포된 HoloLens 디바이스에 대한 제어 권한을 높이기 위해 더 많은 정책에 대한 지원을 추가했습니다. HoloLens 지원하는 CSP 목록은 [NetworkQoSPolicy CSP를 참조하세요.](/windows/client-management/mdm/networkqospolicy-csp)

이 버전의 새 항목:

**Policy CSP**: 

정책 구성 서비스 공급자를 사용하면 엔터프라이즈에서 Windows 디바이스에서 정책을 구성할 수 있습니다. 이 릴리스에서는 여기에 나열된 HoloLens 대한 새 정책을 추가했습니다. 자세한 내용은 [HoloLens 2 에서 지원하는 정책 CSP를](/windows/client-management/mdm/policies-supported-by-hololens2)참조하세요.  

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

NetworkQoSPolicy 구성 서비스 공급자는 네트워크 QoS(서비스 품질) 정책을 만듭니다. QoS 정책은 일련의 일치 조건에 따라 네트워크 트래픽에 대해 일련의 작업을 수행합니다. 자세한 내용은 [NetworkQoSPolicy CSP를 참조하세요.](/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE 테더링된 디바이스에 대한 확장된 USB 이더넷 지원

USB를 통해 HoloLens 2 테더링될 때 5G/LTE 휴대폰 및 Wi-Fi 핫스팟과 같은 특정 모바일 광대역 디바이스를 사용할 수 있도록 지원이 추가되었습니다. 이러한 디바이스는 이제 **네트워크 설정에** 다른 이더넷 연결로 표시됩니다. (외부 드라이버가 필요한 모바일 광대역 디바이스는 지원되지 않습니다.) 이 기능은 Wi-Fi 사용할 수 없고 Wi-Fi 테더링 성능이 충분하지 않은 경우 고대역폭 연결을 사용하도록 설정합니다. 지원되는 USB 디바이스에 대한 자세한 내용은 [Bluetooth 및 USB-C 디바이스에 대한 커넥트 참조하세요.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>손 추적 개선 사항

이 릴리스에는 다음과 같은 몇 가지 손 추적 기능이 포함되어 있습니다.

- **포인팅 자세 안정성:** 이제 시스템은 손끝에 의해 가려질 때 인덱스 손가락의 압정을 거부합니다. 이 변경으로 단추를 누르고, 입력하고, 콘텐츠를 스크롤하는 등의 경우 정확도가 향상됩니다. 
- **실수로 에어 탭 감소:** 에어 탭 제스처의 감지가 향상되었습니다. 이제 손을 측면에 놓는 경우와 같은 몇 가지 일반적인 시나리오에서 실수로 활성화되는 횟수가 줄어듭니다.
- **사용자 스위치 안정성:** 이제 디바이스를 공유할 때 손 크기를 업데이트할 때 시스템이 더 빠르고 안정적입니다.
- **손 도용 감소:** 센서를 볼 수 있는 사례가 두 개 이상 있는 경우의 처리를 개선했습니다. 여러 사람이 함께 작업하는 경우 추적된 손은 사용자에서 장면에 있는 다른 사람의 손으로 "점프"할 가능성이 훨씬 낮아질 수 있습니다.
- **시스템 안정성:** 디바이스의 부하가 높을 때 손 추적이 작동을 중지하는 문제가 해결되었습니다.

### <a name="dark-mode"></a>어둡게 모드

이제 많은 Windows 앱에서 어둡게 모드와 밝은 모드를 모두 지원합니다. HoloLens 2 사용자는 둘 다 지원하는 앱의 기본 모드를 선택할 수 있습니다. 업데이트 후 기본 앱 모드는 "어둡게"이지만 이 설정을 쉽게 변경할 수 있습니다. **설정**  >  **시스템**  >  **색으로** 이동  >  **기본 앱 모드를 선택합니다.** 

이러한 "입력" 앱은 어둡게 모드를 지원합니다. 

- 설정 
- Microsoft Store 
- Mail 
- 달력 
- 파일 탐색기 
- 피드백 허브 
- OneDrive 
- 사진 
- 3D 뷰어 
- 영화 및 TV 

![어둡게 모드 창 타일식](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>시스템 음성 명령

이제 디바이스의 모든 앱에서 음성 명령을 사용할 수 있습니다. 자세한 내용은 [음성을 사용하여 HoloLens 작동을 참조하세요.](hololens-cortana.md) HoloLens 2 [지원되는 언어도](hololens2-language-support.md)참조하세요.  

### <a name="cortana-updates"></a>업데이트 Cortana

업데이트된 앱은 디바이스 전체에서 더 많은 작업을 수행할 수 있도록 Microsoft 365 통합됩니다(현재 US-English만 해당). HoloLens 2 Cortana 볼륨 조정 또는 다시 시작과 같은 특정 디바이스 관련 명령을 더 이상 지원하지 않습니다. 이러한 옵션은 이제 새 시스템 음성 명령에서 지원됩니다. [블로그에서](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)새 Cortana 앱에 대해 자세히 알아보세요.

### <a name="quality-improvements-and-fixes"></a>품질 향상 및 수정

업데이트의 개선 사항 및 수정 사항:  
- 활성 디스플레이 보정 시스템을 도입했습니다. 이 기능은 홀로그램의 안정성과 맞춤을 향상시킵니다. 이제 헤드를 좌우로 이동할 때 그대로 유지합니다.
- HoloLens Wi-Fi 스트리밍이 정기적으로 중단되는 버그가 수정되었습니다. 애플리케이션에서 짧은 대기 시간 스트리밍이 필요하다고 표시되면 [SetSocketMediaStreamingMode 함수](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)를 호출하여 수정 사항을 구현합니다.
- 연구 모드에서 스트리밍하는 동안 발생한 디바이스 중단 문제가 해결되었습니다.
- 세션을 다시 시작해도 로그인 화면에 올바른 사용자가 표시되지 않는 버그가 수정되었습니다.
- 사용자가 **설정** 통해 MDM 로그를 내보낼 수 없는 문제를 해결했습니다.
- 즉시 설치 후 시선 추적의 정확도가 예상보다 낮을 수 있는 문제를 해결했습니다.
- 시선 추적 하위 시스템이 특정 조건에서 보정을 초기화하거나 수행하지 못하는 문제를 해결했습니다.
- 이미 보정된 사용자에게 눈 보정 메시지가 표시되는 문제를 해결했습니다.
- 시선 보정 중에 드라이버가 충돌하는 문제를 해결했습니다.
- 반복되는 전원 단추 누를 때 60초 시스템 시간 제한 및 셸 충돌이 발생할 수 있는 문제를 해결했습니다.
- 깊이 버퍼의 안정성이 향상되었습니다.
- 사용자가 피드백을 보다 쉽게 공유할 수 있도록 피드백 허브 **공유** 단추가 추가되었습니다.
- RoboRaid wan이 올바르게 설치되지 않은 버그가 수정되었습니다.

### <a name="known-issues"></a>알려진 문제

- zh-CN 시스템 언어 관련 문제는 음성 명령이 혼합 현실 캡처를 취하거나 디바이스 IP 주소를 표시하지 못하도록 합니다.
- "Hey Cortana" 음성 활성화를 사용하려면 디바이스를 시작한 후 Cortana 앱을 시작해야 합니다. 18362 빌드에서 업데이트한 경우 더 이상 **시작** 에서 작동하지 않는 이전 버전의 Cortana 앱에 대한 두 번째 앱 타일이 표시되었을 수도 있습니다.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 5월 업데이트 
- 빌드 18362.1061

팀이 앞서 설명한 대로 Windows Holographic 버전 2004 5월 업데이트에서 작업 중이므로 이 월별 품질 업데이트에는 주목할 만한 변경 내용이 포함되지 않습니다.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows 홀로그램 버전 1903 - 2020년 4월 업데이트
- 빌드 18362.1059

**지원되는 앱에 대한 어둡게 모드** 

많은 Windows 앱은 어둡게 및 밝은 모드를 모두 지원합니다. HoloLens 2 고객은 이제 두 색 구성표를 모두 지원하는 앱의 기본 모드를 선택할 수 있습니다. 사용자 의견에 따라 기본 앱 모드를 "어둡게"로 설정 하지만 언제 든 지이 설정을 쉽게 변경할 수 있습니다. **설정 > 시스템 > 색** 으로 이동 하 여 **"기본 앱 모드 선택"** 을 찾습니다.

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
- 영화 및 TV

**업데이트의 향상 된 기능 및 수정 사항:** 
- 셸 중첩이 혼합 현실 캡처에 포함 되었는지 확인 합니다.
- Unreal 개발자는 이제 장치 포털의 3D 보기 페이지를 사용 하 여 응용 프로그램을 테스트 하 고 디버그할 수 있습니다.
- *HolographicDepthReprojectionMethod DepthReprojection* 알고리즘을 사용 하는 경우 혼합 현실 캡처의 홀로그램 안정성이 향상 되었습니다.
- 32 비트 ARM 앱에서 "WinRT IStreamSocketListener API 클래스가 등록 되지 않았습니다." 오류가 수정 되었습니다.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, 버전 1903-3 월 2020 업데이트 
- 빌드 18362.1056

업데이트의 향상 된 기능 및 수정 사항:

- *HolographicDepthReprojectionMethod AutoPlanar* 알고리즘이 사용 되는 경우 혼합 현실 캡처의 홀로그램 안정성이 향상 되었습니다.
- 깊이 MF 샘플에 연결 된 좌표계가 공개 문서와 일치 하는지 확인 했습니다.
- 고객이 장치 포털을 통해 많은 양의 텍스트를 붙여넣을 수 있도록 하 여 개발자의 생산성을 향상 시켰습니다.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, 버전 1903-2 월 2020 업데이트 
- 빌드 18362.1053

업데이트의 향상 된 기능 및 수정 사항:

- Unity 응용 프로그램의 HolographicSpace API를 일시적으로 사용 하지 않도록 설정 했습니다. 이렇게 변경 하면 "백그라운드에서 실행" 설정을 사용 하는 경우에도 일부 앱이 시작 될 때 일부 앱을 일시 중지 하는 문제가 발생 하지 않습니다.
- 사용자가 UI 고정을 인식 하 고 몇 초 후에 다시 셸로 전달 되는 직접 추적으로 인해 발생 하는 임의 HUP 충돌 문제를 수정 했습니다.
- 인덱스 손가락으로 poke 때 해당 손가락의 위쪽 부분이 예기치 않게 중단 될 가능성이 낮은 수동 추적 기능이 향상 되었습니다.
- 헤드 추적, 공간 매핑 및 기타 런타임의 안정성이 향상 되었습니다.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, 버전 1903-1 월 2020 업데이트 
- 빌드 18362.1043
 
업데이트의 향상 된 기능 및 수정 사항:

- HoloLens 2 에뮬레이터를 사용할 때 전용 앱의 안정성이 향상 되었습니다.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, 버전 1903-12 월 2019 업데이트 
- 빌드 18362.1042

업데이트의 향상 된 기능 및 수정 사항:

- 는 LSR (마지막 단계 복제) 픽스를 도입 했습니다. 깊이를 보다 정확 하 게 고려 하 여 보다 안정적이 고 선명 하 게 보이도록 holograms의 시각적 렌더링이 개선 되었습니다. 앱에서 holograms의 깊이를 올바르게 설정 하지 않은 경우이 업데이트 후에이 증상이 더욱 두드러지게 나타납니다.
- 전용 앱 및 전용 앱 간의 탐색의 안정성을 수정 했습니다.
- 장치가 몇 일 동안 대기 상태 였던 혼합 현실 캡처가 비디오를 녹화 하지 못하는 문제를 해결 했습니다.
- 홀로그램의 안정성이 향상 되었습니다.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, 버전 1903-11 월 2019 업데이트 
- 빌드 18362.1039

업데이트의 향상 된 기능 및 수정 사항:

- En-us 및 en-us에 대 한 초기 설정 중에 음성 명령의 **선택** 기능을 수정 했습니다.
- 최신 Unity 및 mrtk (Mixed Reality Toolkit) 버전에서 멀리 떨어진 개체의 시각적 품질이 향상 되었습니다.
- 시작 메뉴를 열고 닫을 때까지 시작 시 일시 중지 됨 상태가 holographic 응용 프로그램의 문제 해결이 수정 되었습니다.
- HoloLens 2 및 에뮬레이터에 대 한 OpenXR 런타임 규칙 수정 및 개선 사항
