---
title: HoloLens 디바이스 문제 해결
description: 디바이스 문제를 HoloLens 및 문제 해결 기술에 대한 가장 일반적인 솔루션을 최신 상태로 유지합니다.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 문제, 버그, 문제 해결, 수정, 도움말, 지원, HoloLens, 에뮬레이터
ms.openlocfilehash: deed0d14b2567ae0a1fb2cde8ad1fbe3dbb20bb3
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351768"
---
# <a name="device-troubleshooting"></a>디바이스 문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결하는 방법을 설명합니다.

>[!IMPORTANT]
> 문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다. 전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.

<a id="list"></a>

**알려진 문제**
- [참가자 수정 - 전원이 18%가 될 때마다 디바이스가 갑자기 자동으로 종료됩니다.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Azure AD 사용자에 대해 UWP 앱이 작동하지 않습니다.](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Autopilot 중에 0x80180014가 표시되는 이유는 무엇인가요?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store 오류 코드 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge 마이크를 시작하지 못함](#microsoft-edge-fails-to-start-the-microphone)
- [**수정됨** - Remote Assist 비디오가 20분 후에 중지됨](#remote-assist-video-freezes-after-20-minutes)
- [자동 로그인에서 로그인 요청](#auto-login-asks-for-log-in)
- [Microsoft Edge 시작하지 못함](#microsoft-edge-fails-to-launch)
- [키보드가 특수 문자로 전환되지 않습니다.](#keyboard-doesnt-switch-to-special-characters)
- [**수정됨** - 잠긴 파일 다운로드에 오류가 표시되지 않습니다.](#downloading-locked-files-doesnt-error)
- [**수정됨** - 파일 업로드/다운로드 시간 장치 포털](#device-portal-file-uploaddownload-times-out)
- [Insider 빌드로 깜박이는 디바이스의 Insider 미리 보기에서 등록을 취소한 후의 파란색 화면](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive 사진을 자동으로 업로드하지 않습니다.](#onedrive-doesnt-automatically-upload-pictures)

**일반**
- [HoloLens 응답하지 않거나 시작되지 않습니다.](#hololens-is-unresponsive-or-wont-start)
- ["디스크 공간 부족" 오류](#low-disk-space-error)
- [보정 실패](#calibration-fails)
- [내 HoloLens 이전에 다른 사람을 위해 설정되었으므로 로그인할 수 없습니다.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity가 작동하지 않습니다.](#unity-isnt-working)
- [Windows 장치 포털 제대로 작동하지 않습니다.](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator 작동하지 않습니다.](#the-hololens-emulator-isnt-working)

**입력**
- [음성 명령이 작동하지 않습니다.](#voice-commands-arent-working)
- [손 입력이 작동하지 않습니다.](#hand-input-isnt-working)

**연결**
- [Wi-Fi에 연결할 수 없습니다.](#cant-connect-to-wi-fi)

**외부 디바이스** 
- [Bluetooth 디바이스가 페어링되지 않습니다.](#bluetooth-devices-arent-pairing)
- [USB-C 마이크가 작동하지 않습니다.](#usb-c-microphone-isnt-working)
- [설정 사용할 수 있는 것으로 나열된 디바이스가 작동하지 않습니다.](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>전원이 18%가 될 때마다 디바이스가 갑자기 자동으로 종료됩니다.

> [!NOTE]
> [Windows 참가자에서](hololens-insider.md) 사용할 수 있는 이 문제에 대한 수정이 있습니다.

디바이스가 18% 배터리에 도달하면 예기치 않게 종료되는 알려진 문제가 있습니다. 이는 하드웨어 또는 배터리 문제가 아닌 소프트웨어 문제이므로 이를 위해 디바이스를 교환하지 마십시오. 문제가 이 버그와 일치하는지 확실하지 않은 경우 다음을 수행하세요.

1. 선택적 진단이 디바이스에서 사용하도록 설정되어 있는지 확인합니다.
1. 문제 재현
1. [피드백 허브](hololens-feedback.md) 문제 제출
1. 피드백 문제 URL 공유
1. [고객 지원 문의](https://aka.ms/hololenssupport)

[목록으로 돌아가기](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Azure AD 사용자에 대해 UWP 앱이 작동하지 않습니다.

Azure AD 계정을 사용하여 OneDrive For Business를 사용하는 경우 받은 편지함 OneDrive 앱에 로그인할 때 오류가 발생할 수 있습니다. OneDrive 앱에 로그인할 수 없는 경우 카메라 앱에서 캡처한 이미지 및 비디오의 자동 업로드에는 영향을 미치지 않습니다. 비즈니스용 OneDrive 클라우드 스토리지에서 파일을 저장하고 액세스할 수 있습니다. OneDrive 및 HoloLens 팀이 이 문제에 대해 작업하고 있습니다.

### <a name="workarounds"></a>해결 방법

필수 조건: 고객은 Microsoft Edge 사용할 수 있으며 디바이스 OS는 Windows Holographic, 21H1 빌드 이상으로 업데이트됩니다.

이 문제가 발생하는 경우 다음 중 하나를 시도합니다.

- 사용자는 Microsoft Edge OneDrive 직접 액세스하고 브라우저에서 웹 사이트 파일과 상호 작용할 수 있습니다.
- 사용자는 OneDrive PWA 앱을 Microsoft Edge 다운로드하여 HoloLens 설치할 수 있습니다. 이렇게 하면 사용자가 디바이스에서 파일을 다시 보고 관리할 수 있습니다. HoloLens OneDrive PWA [앱을 설치하려면](holographic-store-apps.md#install-microsoft-onedrive-pwa-app) 다음 지침을 읽고 따릅니다.

[목록으로 돌아가기](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot 중에 0x80180014가 표시되는 이유는 무엇인가요?

이 오류는 일반적으로 HoloLens 디바이스가 Autopilot을 한 번 이상 통과한 경우 디바이스를 재설정하고 흐름을 다시 사용하는 동안 발생합니다. 이 문제를 해결하려면 [Microsoft Intune 디바이스를 삭제하고](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) 다시 설정하여 Autopilot 흐름을 완료하세요.

자세한 내용은 [Autopilot 페이지에서 문제 해결 단계를 참조하세요.](hololens2-autopilot.md#issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store 오류 코드 0x80131500

일부 사용자는 Microsoft Store 예상대로 작동하지 않을 수 있으며 오류 코드가 0x80131500. HoloLens Microsoft Store 앱에서 사용할 수 없는 HoloLens 설정된 지역으로 인해 발생하는 문제입니다. 오류 코드 0x80131500 발생하는 경우 해결하려면 다음을 수행하세요.

1. 설정 > Time & Language > Region > Country 또는 Region을 다음 중 하나로 설정합니다.
    - 미국, 일본, 중국, 독일, 캐나다, 영국, 아일랜드, 프랑스, 오스트레일리아, 뉴질랜드.
1. 스토어 앱을 다시 시작합니다.
1. 전체 디바이스가 변경된 것을 반영하려면 디바이스를 다시 시작해야 합니다.

HoloLens 팀은 더 많은 지역에 대한 지원을 추가하기 위해 노력하고 있습니다.

HoloLens 2 구입하는 국가에 대한 자세한 내용은 [여기를 참조하세요.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge 마이크를 시작하지 못함

Microsoft Edge 사용하는 사용자가 마이크를 시작하지 못하여 HoloLens Edge와 상호 작용하는 데 사용할 수 없습니다. 이 알려진 문제는 Microsoft Edge 앱의 버전과 관련이 있습니다. 이 문제는 해결되지 않기 때문에 디바이스를 이전 버전으로 되감지 마십시오.

### <a name="who-is-affected"></a>Who 영향을 받나요?

Microsoft Edge 버전 93, 94 또는 95가 있는 사용자입니다.
Microsoft Store 앱을 사용하여 Microsoft Edge 버전을 확인한 다음, **...로** 표시된 "자세히 보기" 단추를 선택한 **다음, 다운로드 및 업데이트를** 선택합니다.

### <a name="work-around"></a>해결

현재 수정은 Microsoft Edge 참가자에 등록한 사용자가 사용할 수 있는 버전 96입니다. 디바이스를 Windows 참가자로 등록하는 것과는 다릅니다. [Edge의 참가자 프로그램에 등록하는 방법에](hololens-new-edge.md#microsoft-edge-insider-channels) 대한 자세한 내용은 다음 지침을 읽어보십시오.

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist 비디오가 20분 후에 중지됩니다.

> [!NOTE]
> 이 문제에 대한 수정이 있는 최신 버전의 Remote Assist 있습니다. 이 문제를 방지하려면 Remote Assist 최신 버전으로 [업데이트하세요.](holographic-store-apps.md#update-apps)

> [!NOTE]
> 이 알려진 문제의 심각도로 인해 Windows Holographic 버전 21H1의 가용성을 일시적으로 일시 중지했습니다. 이제 21H1 빌드를 다시 사용할 수 있으므로 디바이스가 다시 최신 21H1 빌드로 업데이트될 수 있습니다.

[Windows Holographic 버전 21H1의](hololens-release-notes.md#windows-holographic-version-21h1)최신 릴리스에서는 Remote Assist 일부 사용자가 20분 넘게 통화하는 동안 비디오 중지를 경험했습니다. 이것은 **알려진 문제입니다.**

### <a name="workarounds"></a>해결 방법

최신 빌드로 Remote Assist 업데이트할 수 없는 경우 다음 해결 방법을 시도해 보세요.

#### <a name="restart-in-between-calls"></a>호출 간에 다시 시작

호출이 20분을 초과하고 이 문제가 발생하는 경우 디바이스를 다시 부팅해 보세요. Remote Assist 호출 사이에 디바이스를 다시 부팅하면 디바이스가 새로 고쳐지고 다시 양호한 상태로 전환됩니다.

Windows Holographic에서 디바이스를 신속하게 다시 시작하려면 [버전 21H1에서](hololens-release-notes.md#windows-holographic-version-21h1) 시작 메뉴를 열고 사용자 아이콘을 선택한 다음, **다시 시작을** 선택합니다.

[목록으로 돌아가기](#list)

## <a name="auto-login-asks-for-log-in"></a>로그인에 대 한 자동 로그인 요청

**설정** 계정 로그인 옵션을 통해 HoloLens 2 장치를 자동으로 로그인 하도록 구성할 수 있습니다  ->    ->   . > 하 고 **필요한** 경우 값을 **없음** 으로 설정 합니다. 기능 업데이트와 같이 상당히 큰 업데이트를 사용 하 여 장치를 업데이트할 때 일부 사용자가 장치에 다시 로그인 해야 할 수 있습니다. 이것은 **알려진 문제** 입니다.

이 문제가 발생할 수 있는 경우의 예는 다음과 같습니다.

- Windows Holographic, 버전 2004 (build 19041)에서 Windows Holographic, 버전 21h1 (build 20346)로 장치 업데이트
- 장치를 업데이트 하 여 동일한 주요 빌드 (예: Windows Holographic, 버전 2004 Windows Holographic, 버전 20h2에 대 한 큰 업데이트를 수행 합니다.
- 공장 이미지에서 최신 이미지로 장치 업데이트

다음 작업 중에는 발생 하지 않아야 합니다.

- 월별 서비스 업데이트를 수행 하는 장치

해결 방법:

- PIN, 암호, Iri, 웹 인증 또는 FIDO2 키와 같은 로그인 방법입니다.
- 장치 PIN을 기억할 수 없고 다른 인증 방법을 사용할 수 없는 경우 사용자가 [수동 reflashing 모드](hololens-recovery.md#manual-flashing-mode-procedure)를 사용할 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge 시작 실패

> [!NOTE]
> 이 문제는 원래 Microsoft Edge의 배송 버전을 사용 하 여 만들어졌습니다. 이 문제는 [새 Microsoft Edge](hololens-new-edge.md)에서 해결할 수 있습니다. 그렇지 않으면 파일 피드백을 보내 주세요.

몇 명의 고객이 Microsoft Edge를 시작 하지 못하는 문제를 보고 했습니다. 이러한 고객의 경우에는 다시 부팅을 통해 문제가 지속 되며 Windows 또는 응용 프로그램 업데이트로 해결 되지 않습니다. 이 문제가 발생 하 고 [Windows 최신 상태 인지](hololens-updates.md#manually-check-for-updates)확인 한 경우 [피드백 허브 앱](hololens-feedback.md) 에서 다음 범주 및 하위 범주를 사용 하 여 버그를 파일에 입력 하세요. 설치 및 업데이트 > Windows 업데이트 다운로드, 설치 및 구성 하는 중입니다.

지금까지 문제를 발생 시킬 수 없기 때문에 알려진 해결 방법이 없습니다. 피드백 허브를 통해 버그를 제출 하면 조사에 도움이 됩니다. 이것은 **알려진 문제** 입니다.

[목록으로 돌아가기](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>키보드에서 특수 문자로 전환 하지 않음

사용자가 회사 또는 학교 계정을 선택 하 고 암호를 입력 하는 경우 OOBE 중에 문제가 발생 합니다. &123 단추를 탭 하 여 키보드의 특수 문자로 전환 하려는 시도는 특수 문자로 변경 되지 않습니다. 이것은 **알려진 문제** 입니다.

해결 방법:

- 키보드를 닫고 텍스트 필드를 탭 하 여 다시 엽니다.
- 암호를 잘못 입력 했습니다. 다음 번에 키보드를 고 하면 예상 대로 작동 합니다.
- 웹 인증, 키보드를 닫고 **다른 장치에서 로그인** 을 선택 합니다.
- 숫자만 입력 하는 경우 사용자는 특정 키를 길게 눌러 확장 된 메뉴를 열 수 있습니다.
- USB 키보드 사용.

이는 다음에 영향을 주지 않습니다.

- 개인 계정을 사용 하도록 선택 하는 사용자입니다.

[목록으로 돌아가기](#list)

## <a name="downloading-locked-files-doesnt-error"></a>잠긴 파일 다운로드 오류

> [!NOTE]
> 이 문제는 [Windows Holographic, 버전 21h1-7 월 2021 업데이트](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)에서 해결 된 **알려진 문제** 입니다.

Windows Holographic의 이전 빌드에서 잠긴 파일을 다운로드 하려고 하면 결과는 HTTP 오류 페이지가 됩니다. Windows Holographic, 버전 21h1 업데이트에서 잠긴 파일을 다운로드 하려고 하면 파일이 다운로드 되지 않으며 오류가 발생 하지 않습니다.

[목록으로 돌아가기](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>장치 포털 파일 업로드/다운로드 제한 시간
> [!NOTE]
> 이 문제는 [Windows Holographic, 버전 21h1-7 월 2021 업데이트](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)에서 해결 된 **알려진 문제** 입니다. 이전에 해결 방법의 일부로 SSL 연결을 사용 하지 않도록 설정한 경우 다시 사용 하도록 설정 하는 것이 좋습니다.

일부 고객은 파일을 업로드 하거나 다운로드 하려고 할 때 작업이 중단 된 것 처럼 표시 되 고 시간이 초과 되거나 완료 되지 않을 수 있습니다. 이는 '[파일 잠김 ' 알려진 문제와](#downloading-locked-files-doesnt-error) 는 별개입니다 .이는 Windows Holographic, 버전 2004, 20h2 및 21h1 시장 빌드에 영향을 줍니다. 이 문제는 장치 포털의 특정 요청 처리에서 버그로 인해 발생 했으며, https를 사용 하는 경우 (기본값) 가장 일관 되 게 적중 됩니다.

### <a name="workaround"></a>해결 방법

Wi-Fi 및 a n Cm에 동일 하 게 적용 되는이 해결 방법은 "SSL 연결"에서 "필수" 옵션을 사용 하지 않도록 설정 하는 것입니다. 이렇게 하려면 장치 포털, **시스템** 으로 이동 하 여 **기본 설정** 페이지를 선택 합니다. **장치 보안** 섹션에서 **SSL 연결** 을 찾아 선택 취소 하 여 **필수** 를 해제 합니다.

그런 다음 사용자는 https://(IP 주소)가 아닌 http://로 이동 하 고 파일 업로드 및 다운로드와 같은 기능이 작동 합니다.

[목록으로 돌아가기](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider build를 사용 하 여 제공 된 장치에서 Insider preview 등록 취소 이후 파란색 화면

이 문제는 insider preview 빌드에 있었던 사용자에 게 영향을 주는 문제 이며, 새 insider preview 빌드를 사용 하 여 HoloLens 2를 reflashed 다음, 참가자 프로그램에서 등록 취소 합니다. 이것은 **알려진 문제** 입니다.

이는 다음에 영향을 주지 않습니다.

- Windows Insider에 등록 되지 않은 사용자
- 참가자
    - Insider 빌드된 버전이 18362 이므로 장치가 등록 된 경우
    - Insider 19041 빌드 되었으며 Insider program에 등록 된 상태를 유지 하는 경우

해결 방법:

- 문제 방지
    - 비-insider build를 플래시 합니다. 정기 매월 업데이트 중 하나입니다.
    - Insider Preview 유지
- 장치 경감 하기 위해

    1. 연결 되지 않은 상태에서 전원을 끄고 수동으로 [HoloLens 2를 깜박임 모드로](hololens-recovery.md) 전환 합니다. 그런 다음 볼륨을 유지 하는 동안 전원 단추를 누릅니다.

    1. PC에 커넥트 하 고 고급 복구 도우미를 엽니다.

    1. HoloLens 2를 기본 빌드로 깜박입니다.

[목록으로 돌아가기](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>자동으로 그림을 업로드 하지 OneDrive

HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다. 이것은 **알려진 문제** 입니다.

해결 방법:

- 비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다. 회사 또는 학교 계정 외에도 Microsoft 계정에 로그인 할 수 있습니다. OneDrive 앱은 이중 로그인을 지원 합니다. OneDrive 내의 Microsoft 계정 프로필에서 자동, 배경 카메라 롤 업로드를 사용 하도록 설정할 수 있습니다.

- 회사를 자동으로 업로드 하는 데 소비자 Microsoft 계정를 안전 하 게 사용할 수 없는 경우 OneDrive 앱에서 회사 또는 학교 계정에 사진을 수동으로 업로드할 수 있습니다. 이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 했는지 확인 합니다. 단추를 선택 **+** 하 고 **업로드** 를 선택 합니다. **사진 > 카메라 롤** 로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다. 업로드 하려는 사진 또는 비디오를 선택 하 고 **열기** 단추를 선택 합니다.

[목록으로 돌아가기](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens 응답 하지 않거나 시작 되지 않음

HoloLens 시작 되지 않는 경우:

- 전원 단추 옆의 Led가 켜지 지 않거나 LED가 잠시 깜박일 경우 [HoloLens 요금을 청구](hololens2-charging.md#charging-the-device) 해야 할 수 있습니다.
- 전원 단추를 누를 때 Led가 켜져 있지만 디스플레이에 아무것도 표시 되지 않으면 [장치의 하드 리셋을 수행](hololens-recovery.md#hard-restart-procedure)합니다.

HoloLens 고정 되거나 응답 하지 않는 경우:

- 5 개의 led가 모두 꺼질 때까지 전원 단추를 누르거나 led가 응답 하지 않는 경우 15 초 동안 HoloLens를 해제 합니다. HoloLens를 시작 하려면 전원 단추를 다시 누릅니다.

이러한 단계가 작동 하지 않는 경우 [HoloLens 2 장치](hololens-recovery.md) 또는 [HoloLens (첫 번째 gen) 장치](hololens1-recovery.md) 를 복구 해 볼 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="low-disk-space-error"></a>"디스크 공간 부족" 오류

다음 중 하나 이상을 수행 하 여 저장소 공간을 확보 해야 합니다.

- 사용 하지 않는 공간을 삭제 합니다. **설정** 시스템 공간으로 이동 하 여  >    >  더 이상 필요 하지 않은 공간을 선택 하 고 **제거** 를 선택 합니다.
- 배치한 홀로그램 중 일부를 제거합니다.
- 사진 앱에서 일부 사진 및 비디오를 삭제합니다.
- HoloLens 일부 앱을 제거합니다. **모든 앱** 목록에서 제거하려는 앱을 길게 누른 다음, **제거를** 선택합니다.

[목록으로 돌아가기](#list)

## <a name="calibration-fails"></a>보정 실패

보정은 대부분의 사람들에게 작동해야 하지만 보정이 실패하는 경우가 있습니다.
  
보정 실패의 몇 가지 잠재적 원인은 다음과 같습니다.

- 보정 대상을 따르지 않고 주의가 분산됩니다.
- 더티 또는 스크래치된 디바이스 바이저 또는 디바이스 바이저가 제대로 배치되지 않음
- 더티 또는 스크래치된 안경
- 특정 유형의 연락처 렌즈 및 안경(색이 있는 연락처 렌즈, 일부 의약형 연락처 렌즈, IR 차단 안경, 일부 고가용성 안경, 눈금 등)
- 더 뚜렷한 눈금과 일부 눈금 확장
- 디바이스에서 눈의 표시를 차단하는 경우 머리 또는 굵은 안경 프레임
- 좁은 눈, 긴 속눈눈, amblyopia, nystagmus, LASIK 또는 기타 시선 시선의 일부 사례와 같은 특정 시선 안과, 시선 상태 또는 안과

보정에 실패한 경우 다음을 시도합니다.

- 디바이스 바이저 정리
- 안경 정리
- 가능한 한 눈에 가까운 디바이스 바이저 푸시
- 바이저의 개체를 방해하지 않습니다(예: 머리).
- 실내에서 조명 켜기 또는 직접 세로 바깥으로 이동

모든 지침을 따르고 보정이 여전히 실패하는 경우 설정 보정 프롬프트를 사용하지 않도록 설정할 수 있습니다. 또한 [피드백 허브](hololens-feedback.md)피드백을 제출하여 알려주세요.

[이미지 색 또는 밝기 문제 해결에](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) 대한 관련 정보도 참조하세요.

시스템에서 시선 위치를 계산하기 때문에 IPD 설정은 HoloLens 2 적용할 수 없습니다. 

[목록으로 돌아가기](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>내 HoloLens 이전에 다른 사람을 위해 설정되었으므로 로그인할 수 없습니다.

[디바이스를 **플래시 모드로** 전환하고 고급 복구 도우미를 사용하여](hololens-recovery.md#clean-reflash-the-device) 디바이스를 복구할 수 있습니다.

[목록으로 돌아가기](#list)


## <a name="unity-isnt-working"></a>Unity가 작동하지 않습니다.

- HoloLens 개발에 권장되는 최신 버전의 Unity용 [도구 설치를](/windows/mixed-reality/install-the-tools) 참조하세요.
- Unity HoloLens Technical Preview의 알려진 문제는 HoloLens Unity 포럼 에 [설명되어 있습니다.](https://forum.unity3d.com/threads/known-issues.394627/)

[목록으로 돌아가기](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows 장치 포털 제대로 작동하지 않습니다.

- Mixed Reality 캡처의 라이브 미리 보기 기능은 몇 초의 대기 시간을 나타낼 수 있습니다.

- 가상 입력 페이지의 가상 제스처 섹션 아래에 있는 제스처 및 스크롤 컨트롤이 작동하지 않습니다. 이를 사용하면 아무런 영향을 미치지 않습니다. 가상 입력 페이지의 가상 키보드가 제대로 작동합니다.

- 설정 개발자 모드를 사용하도록 설정한 후 스위치가 장치 포털 켜기까지 몇 초 정도 걸릴 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator 작동하지 않습니다.

HoloLens 에뮬레이터에 대한 정보는 개발자 설명서에 있습니다.  [HoloLens 에뮬레이터 문제 해결에](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)대해 자세히 읽어보십시오.


- Microsoft Store 있는 모든 앱이 에뮬레이터와 호환되는 것은 아닙니다. 예를 들어 Young Conker 및 Fragments는 에뮬레이터에서 재생할 수 없습니다.
- Emulator PC 웹캠을 사용할 수 없습니다.
- Windows 장치 포털 라이브 미리 보기 기능은 에뮬레이터에서 작동하지 않습니다. Mixed Reality 비디오 및 이미지를 캡처할 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="voice-commands-arent-working"></a>음성 명령이 작동하지 않습니다.

Cortana 음성 명령에 응답하지 않는 경우 Cortana 켜져 있는지 확인합니다. 모든 앱 목록에서 **Cortana** 메뉴 Notebook 설정 선택하여  >    >    >   변경합니다. 할 수 있는 내용에 대한 자세한 내용은 [HoloLens 함께 음성 사용을 참조하세요.](hololens-cortana.md)

HoloLens(1세대)에서는 기본 제공 음성 인식을 구성할 수 없습니다. 항상 켜져 있습니다. HoloLens 2 디바이스를 설정하는 동안 음성 인식과 Cortana 둘 다 설정할지 여부를 선택할 수 있습니다.

HoloLens 2 음성에 응답하지 않는 경우 음성 인식이 켜져 있는지 확인합니다. 개인 정보 설정 시작으로 이동하여  >    >    >  **음성** **인식을** 켭니다.

[목록으로 돌아가기](#list)

## <a name="hand-input-isnt-working"></a>손 입력이 작동하지 않습니다.

HoloLens 손을 볼 수 있도록 제스처 프레임에 유지해야 합니다.  Mixed Reality 홈은 손을 추적하는 시기를 알려주는 피드백을 제공합니다.  피드백은 HoloLens 버전에 따라 다릅니다.

- HoloLens(1세대)에서 응시 커서가 점에서 링으로 변경됩니다.
- HoloLens 2 손을 슬레이트 가까이에 놓으면 손끝 커서가 나타나고 슬레이트가 더 멀리 있을 때 손 광선이 나타납니다.

많은 몰입형 앱은 Mixed Reality Home과 유사한 입력 패턴을 따릅니다.  [HoloLens(1세대)](hololens1-basic-usage.md#use-hololens-with-your-hands) [및](hololens2-basic-usage.md#the-hand-tracking-frame)HoloLens 2 손 입력을 사용하는 방법에 대해 자세히 알아봅니다.

글러브를 신고 있는 경우 일부 유형의 글러브가 손 추적에서 작동하지 않습니다.  일반적인 예로는 검정색 무중단 글러브가 있습니다. 이 블래스는 광원을 흡수하는 경향이 있으며 깊이 카메라에 의해 선택되지 않습니다.  작업에 글러브가 포함된 경우 파란색 또는 회색과 같은 밝은 색을 사용해보는 것이 좋습니다.  또 다른 예로는 손 모양이 가려지는 경향이 있는 큰 글러브가 있습니다. 최상의 결과를 위해 가능한 한 폼 맞춤인 글러브를 사용하는 것이 좋습니다.

visor에 지문 또는 스미지가 있는 경우 HoloLens 함께 제공되는 마이크로Fiber 청소 의류를 사용하여 visor를 깔끔하게 정리합니다.

[목록으로 돌아가기](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi 연결할 수 없습니다.

HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 작업을 시도해 볼 수 있습니다.

- Wi-Fi가 켜져 있는지 확인하세요. 확인하려면 시작 제스처를 사용한 다음, **설정**  >  **네트워크 &amp; 인터넷**  >  **Wi-Fi를** 선택합니다. Wi-Fi가 켜져 있으면 끈 다음 다시 켜보세요.
- 라우터 또는 액세스 지점에 좀 더 가깝게 이동하세요.
- Wi-Fi 라우터를 다시 시작한 다음 [HoloLens 다시 시작합니다.](hololens-recovery.md) 다시 연결해 보세요.
- 이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용하고 있는지 확인합니다. 제조업체 웹 사이트에서 이 정보를 찾을 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth 디바이스가 페어링되지 않습니다.

[Bluetooth 디바이스를 페어링하는 데](hololens-connect-devices.md)문제가 있는 경우 다음을 시도합니다.

- **설정** 디바이스 로 이동하여 Bluetooth 켜져 있는지  >  **확인합니다.** 이 경우 해제했다가 다시 켭니다.
- Bluetooth 디바이스에 완전히 요금이 부과되거나 배터리가 새로 설치되어 있는지 확인합니다.
- 여전히 연결할 수 없는 경우 [HoloLens 다시 시작합니다.](hololens-recovery.md)

[목록으로 돌아가기](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 마이크가 작동하지 않습니다.

일부 USB-C 마이크는 자신을 *마이크와* 스피커로 잘못 보고합니다. 이는 마이크에 문제가 있고 HoloLens 문제가 아닙니다. 이러한 마이크 중 하나를 HoloLens 연결하면 소리가 손실될 수 있습니다. 다행히 간단한 수정이 있습니다.  

**설정** 시스템 소리 에서  ->    ->  기본 제공 **스피커(아날로그 기능 오디오 드라이버)를** **기본 디바이스** 로 명시적으로 설정합니다. HoloLens 마이크가 제거되고 나중에 다시 연결되더라도 이 설정을 기억해야 합니다.

![USB-C 마이크 문제 해결](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>설정에서 사용 가능으로 나열 된 장치가 작동 하지 않음

HoloLens (첫 번째 gen) Bluetooth 오디오 프로필을 지원 하지 않습니다. 스피커 및 헤드셋과 같은 Bluetooth 오디오 장치는 HoloLens 설정에서 사용할 수 있는 것 처럼 보일 수 있지만 지원 되지 않습니다.

HoloLens 2은 스테레오 재생을 위한 Bluetooth A2DP 오디오 프로필을 지원 합니다. Bluetooth 주변 장치에서 마이크 캡처가 가능 하도록 하는 Bluetooth 손 무료 프로필은 HoloLens 2에서 지원 되지 않습니다.

Bluetooth 장치를 사용 하는 데 문제가 있는 경우 지원 되는 장치 인지 확인 합니다. 지원 되는 장치는 다음과 같습니다.

- 영어 Bluetooth 키보드 (holographic 키보드를 사용 하는 모든 곳에서 사용할 수 있음)
- Bluetooth 마우스.
- [HoloLens clicker](hololens1-clicker.md)입니다.

다른 Bluetooth HID 및 GATT 장치를 HoloLens와 함께 연결할 수 있습니다. 그러나 실제로 장치를 사용 하려면 Microsoft Store에서 해당 하는 관련 앱을 설치 해야 할 수 있습니다.

[목록으로 돌아가기](#list)
