---
title: HoloLens 장치 문제 해결
description: 가장 일반적인 솔루션을 최신 상태로 유지 하 여 장치 문제 및 문제 해결 기법을 HoloLens 하세요.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 문제, 버그, 문제 해결, 수정, 도움말, 지원, HoloLens, 에뮬레이터
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924368"
---
# <a name="device-troubleshooting"></a>장치 문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결 하는 방법을 설명 합니다.

>[!IMPORTANT]
> 문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다. 전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.

<a id="list"></a>

**알려진 문제**
- [전원이 18%로 이동 될 때마다 장치는 갑자기 자동으로 종료 됩니다.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive UWP 앱이 Azure AD 사용자에 대해 작동 하지 않음](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Autopilot 중 0x80180014가 표시 되는 이유는 무엇 인가요?](#why-do-i-see-0x80180014-during-autopilot)
- [20 분 후에 원격 지원 비디오가 정지 됨](#remote-assist-video-freezes-after-20-minutes)
- [로그인에 대 한 자동 로그인 요청](#auto-login-asks-for-log-in)
- [Microsoft Edge 시작 실패](#microsoft-edge-fails-to-launch)
- [키보드에서 특수 문자로 전환 하지 않음](#keyboard-doesnt-switch-to-special-characters)
- [잠긴 파일을 다운로드 해도 오류가 표시 되지 않음](#downloading-locked-files-doesnt-error)
- [장치 포털 파일 업로드/다운로드 제한 시간](#device-portal-file-uploaddownload-times-out)
- [Insider build를 사용 하 여 제공 된 장치에서 Insider preview 등록 취소 이후 파란색 화면](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [자동으로 그림을 업로드 하지 OneDrive](#onedrive-doesnt-automatically-upload-pictures)

**일반**
- [HoloLens 응답 하지 않거나 시작 되지 않음](#hololens-is-unresponsive-or-wont-start)
- ["디스크 공간 부족" 오류](#low-disk-space-error)
- [보정 실패](#calibration-fails)
- [이전에 다른 사용자에 대해 HoloLens를 설정 했기 때문에 로그인 할 수 없습니다.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity가 작동 하지 않음](#unity-isnt-working)
- [Windows 장치 포털이 제대로 작동 하지 않습니다.](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator 작동 하지 않습니다.](#the-hololens-emulator-isnt-working)

**입력**
- [음성 명령이 작동 하지 않음](#voice-commands-arent-working)
- [손으로 입력이 작동 하지 않음](#hand-input-isnt-working)

**연결**
- [Wi-fi에 연결할 수 없음](#cant-connect-to-wi-fi)

**외부 장치** 
- [Bluetooth 장치가 페어링 하지 않음](#bluetooth-devices-arent-pairing)
- [USB-C 마이크가 작동 하지 않음](#usb-c-microphone-isnt-working)
- [설정에서 사용 가능으로 나열 된 장치가 작동 하지 않음](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>전원이 18%로 이동 될 때마다 장치는 갑자기 자동으로 종료 됩니다.

장치가 18% 배터리에 도달 하면 예기치 않게 종료 되는 알려진 알려진 문제가 있습니다. 하드웨어 또는 배터리 문제가 아닌 소프트웨어 문제 이므로이에 대 한 장치를 교환 하지 마세요. 문제가이 버그와 일치 하는지 잘 모르겠으면 다음을 수행 하십시오.

1. 장치에서 선택적 진단을 사용 하도록 설정 했는지 확인 합니다.
1. 문제 재현
1. [피드백 허브](hololens-feedback.md) 문제 제출
1. 피드백 발행 URL 공유
1. [고객 지원 문의](https://aka.ms/hololenssupport)

[목록으로 돌아가기](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP 앱이 Azure AD 사용자에 대해 작동 하지 않음

Azure AD 계정을 사용 하 여 비즈니스용 OneDrive를 사용 하는 경우 수신함 OneDrive 앱에 로그인 할 때 오류가 발생 했을 수 있습니다. OneDrive 앱에 로그인 할 수 없는 경우 카메라 앱에서 캡처한 이미지 및 비디오의 자동 업로드에 영향을 주지 않습니다. 비즈니스용 OneDrive 클라우드 저장소에서 파일을 저장 하 고 액세스할 수 있습니다. OneDrive 및 HoloLens 팀이 문제에 대해 작업 하 고 있습니다.

### <a name="workarounds"></a>해결 방법

필수 구성 요소: 고객이 Microsoft Edge를 사용 하 고 장치 OS를 Windows Holographic, 21h1 빌드 이상으로 업데이트할 수 있습니다.

이 문제가 발생 하는 경우 다음 중 하나를 수행 합니다.

- 사용자는 Microsoft Edge에서 비즈니스 OneDrive에 직접 액세스 하 고 브라우저에서 해당 웹 사이트와 상호 작용할 수 있습니다.
- 사용자는 Microsoft Edge에서 다운로드 하 여 HoloLens에 OneDrive PWA 앱을 설치할 수 있습니다. 이렇게 하면 사용자가 장치에서 파일을 다시 보고 관리할 수 있습니다. [HoloLens에서 OneDrive PWA 앱을 설치 하는 방법에 대 한 다음 지침](holographic-store-apps.md#install-microsoft-onedrive-pwa-app) 을 읽고 따르세요.

[목록으로 돌아가기](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot 중 0x80180014가 표시 되는 이유는 무엇 인가요?

이 오류는 일반적으로 장치를 다시 설정 하는 동안 발생 하며, HoloLens 장치가 Autopilot를 한 번 이상 사용 하는 흐름을 다시 사용 하는 경우에 발생 합니다. 이 문제를 해결 하려면 [Microsoft Intune에서 장치를 삭제](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) 하 고 다시 설정 하 여 Autopilot flow를 완료 하세요.

자세한 내용은 [autopilot 페이지의 문제 해결 단계](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot) 를 참조 하세요.

## <a name="remote-assist-video-freezes-after-20-minutes"></a>20 분 후에 원격 지원 비디오가 정지 됨

> [!NOTE]
> 이 문제에 대 한 해결 방법이 있는 최신 버전의 원격 지원이 있습니다. 이 문제를 방지 하려면 [원격 지원을](holographic-store-apps.md#update-apps) 최신 버전으로 업데이트 하세요.

> [!NOTE]
> 이 알려진 문제의 심각도로 인해 Windows Holographic 버전 21h1의 가용성을 일시적으로 중지 했습니다. 이제 21H1 빌드를 다시 사용할 수 있으므로 장치가 다시 한 번 최신 21H1 빌드로 업데이트 될 수 있습니다.

[Windows Holographic 버전 21h1](hololens-release-notes.md#windows-holographic-version-21h1)의 최신 릴리스에서는 원격 지원의 일부 사용자가 20 분 동안 전화를 걸 때 비디오가 동결 되었습니다. 이것은 **알려진 문제** 입니다.

### <a name="workarounds"></a>해결 방법

원격 지원을 최신 빌드로 업데이트할 수 없는 경우 다음 해결 방법을 시도해 보세요.

#### <a name="restart-in-between-calls"></a>호출 사이에 다시 시작

호출이 20 분 동안 발생 하 여이 문제가 발생 하는 경우 장치를 다시 부팅 해 보세요. 원격 지원 호출 사이에서 장치를 다시 부팅 하면 장치가 새로 고쳐 정상 상태로 전환 됩니다.

Windows Holographic에서 장치를 신속 하 게 다시 시작 하려면 [21h1 버전](hololens-release-notes.md#windows-holographic-version-21h1) 의 시작 메뉴를 열고 사용자 아이콘을 선택한 다음 **다시 시작** 을 선택 합니다.

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
- 장치 PIN을 기억할 수 없고 다른 인증 방법을 사용할 수 없는 경우 사용자가 [수동 reflashing 모드](hololens-recovery.md#manual-procedure)를 사용할 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge 시작 실패

> [!NOTE]
> 이 문제는 원래 Microsoft Edge의 배송 버전을 사용 하 여 만들어졌습니다. 이 문제는 [새 Microsoft Edge](hololens-new-edge.md)에서 해결할 수 있습니다. 그렇지 않으면 파일 피드백을 보내 주세요.

몇 명의 고객이 Microsoft Edge를 시작 하지 못하는 문제를 보고 했습니다. 이러한 고객의 경우에는 다시 부팅을 통해 문제가 지속 되며 Windows 또는 응용 프로그램 업데이트로 해결 되지 않습니다. 이 문제가 발생 하 고 [Windows 최신 상태 인지](hololens-updates.md#manually-check-for-updates)확인 한 경우 [피드백 허브 앱](hololens-feedback.md) 에서 다음 범주 및 하위 범주를 사용 하 여 버그를 파일에 입력 하세요. 설치 및 업데이트 > Windows 업데이트 다운로드, 설치 및 구성 하는 중입니다.

지금까지 문제를 발생 시킬 수 없기 때문에 알려진 해결 방법이 없습니다. 피드백 허브를 통해 버그를 제출 하면 조사에 도움이 됩니다. 이것은 **알려진 문제입니다.**

[목록으로 돌아가기](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>키보드가 특수 문자로 전환되지 않습니다.

OOBE 중에는 사용자가 직장 또는 학교 계정을 선택하고 암호를 입력한 후 &123 단추를 탭하여 키보드의 특수 문자로 전환하려고 하면 특수 문자로 변경되지 않는 문제가 있습니다. 이것은 **알려진 문제입니다.**

해결 작업:

- 키보드를 닫고 텍스트 필드를 탭하여 다시 엽니다.
- 암호를 잘못 입력합니다. 다음에 키보드가 다시 시작되면 예상대로 작동합니다.
- 웹 인증에서 키보드를 닫고 **다른 디바이스에서 로그인을** 선택합니다.
- 숫자만 입력하는 경우 사용자는 특정 키를 누르고 확장된 메뉴를 열 수 있습니다.
- USB 키보드 사용.

이는 다음에 영향을 주지 않습니다.

- 개인 계정을 사용하도록 선택한 사용자입니다.

[목록으로 돌아가기](#list)

## <a name="downloading-locked-files-doesnt-error"></a>잠긴 파일을 다운로드해도 오류가 발생하지 않습니다.

> [!NOTE]
> 이는 [Windows Holographic 버전 21H1 - 2021년 7월 업데이트에서](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)해결된 **알려진 문제입니다.**

Windows Holographic의 이전 빌드에서 잠긴 파일을 다운로드하려고 할 때 결과는 HTTP 오류 페이지가 됩니다. Windows Holographic 버전 21H1 업데이트에서 잠긴 파일을 다운로드하려고 시도하면 아무 것도 표시되지 않습니다. 파일이 다운로드되지 않고 오류가 발생하지 않습니다.

[목록으로 돌아가기](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>파일 업로드/다운로드 시간 장치 포털
> [!NOTE]
> 이는 [Windows Holographic 버전 21H1 - 2021년 7월 업데이트에서](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)해결된 **알려진 문제입니다.** 이전에 해결 방법의 일부로 SSL 연결을 사용하지 않도록 설정한 경우 다시 사용하도록 설정하는 것이 좋습니다.

일부 고객은 파일을 업로드하거나 다운로드하려고 할 때 작업이 중단된 다음 시간 부족하거나 완료되지 않을 수 있음을 발견했습니다. 이는 알려진['파일 잠금' 문제와는](#downloading-locked-files-doesnt-error) 별개입니다. 이는 Holographic 버전 2004, 20H2 및 21H1 시장 내 빌드에 Windows 영향을 미칩니다. 이 문제는 장치 포털 특정 요청을 처리하는 버그로 인해 발생했으며, https를 사용할 때 가장 일관되게 발생합니다(기본값).

### <a name="workaround"></a>해결 방법

Wi-Fi 및 UsbNcm에도 동일하게 적용되는 이 해결 방법은 "SSL 연결"에서 "필수" 옵션을 사용하지 않도록 설정하는 것입니다. 이렇게 하려면 장치 포털 **시스템** 으로 이동하고 기본 **설정** 페이지를 선택합니다. 디바이스 **보안** 섹션에서 **SSL 연결** 을 찾은 다음, **필수** 를 사용하지 않도록 설정하려면 선택을 취소합니다.

그런 다음 사용자는 https://(IP 주소)가 아닌 http:// 이동해야 하며 파일 업로드 및 다운로드와 같은 기능이 작동합니다.

[목록으로 돌아가기](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider 빌드로 깜박이는 디바이스의 Insider Preview에서 등록을 취소한 후의 파란색 화면

이는 참가자 미리 보기 빌드에 있던 사용자에게 영향을 미치는 문제이며, 새 참가자 미리 보기 빌드를 통해 HoloLens 2 다시 적용한 다음 참가자 프로그램에서 등록을 취소합니다. 이것은 **알려진 문제입니다.**

이는 다음에 영향을 주지 않습니다.

- Windows 참가자에 등록되지 않은 사용자
- 내부:
    - 참가자 빌드 이후 디바이스가 등록된 경우 버전 18362.x
    - 참가자 서명 19041.x 빌드를 플래시한 경우 참가자 프로그램에 등록 상태를 유지합니다.

해결:

- 문제 방지
    - 비 참가자 빌드를 플래시합니다. 정기적인 월별 업데이트 중 하나입니다.
    - Insider Preview에 유지
- 디바이스 리플래시

    1. 연결되지 않은 상태에서 전원을 완전히 낮추어 HoloLens 2 수동 [플래시 모드로](hololens-recovery.md) 전환합니다. 그런 다음, Volume up 누를 때 전원 단추를 누릅니다.

    1. PC로 커넥트 고급 복구 도우미를 엽니다.

    1. HoloLens 2 기본 빌드로 플래시합니다.

[목록으로 돌아가기](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive 사진을 자동으로 업로드하지 않습니다.

HoloLens OneDrive 앱은 직장 또는 학교 계정에 대한 자동 카메라 업로드를 지원하지 않습니다. 이것은 **알려진 문제입니다.**

해결 방법:

- 비즈니스에 적합한 경우 소비자 Microsoft 계정에서 자동 카메라 업로드가 지원됩니다. 직장 또는 학교 계정 외에도 Microsoft 계정 로그인할 수 있습니다(OneDrive 앱은 이중 로그인을 지원함). OneDrive 내의 Microsoft 계정 프로필에서 자동 백그라운드 카메라 롤 업로드를 사용하도록 설정할 수 있습니다.

- 사진을 자동으로 업로드하는 데 소비자 Microsoft 계정 안전하게 사용할 수 없는 경우 OneDrive 앱에서 수동으로 사진을 직장 또는 학교 계정에 업로드할 수 있습니다. 이렇게 하려면 OneDrive 앱에서 직장 또는 학교 계정에 로그인했는지 확인합니다. 단추를 선택하고 **+** **업로드** 선택합니다. **사진 > 카메라 롤로** 이동하여 업로드하려는 사진 또는 비디오를 찾습니다. 업로드하려는 사진 또는 비디오를 선택한 다음, **열기** 단추를 선택합니다.

[목록으로 돌아가기](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens 응답하지 않거나 시작되지 않습니다.

HoloLens 시작되지 않는 경우:

- 전원 단추 옆의 LED가 켜지지 않거나 LED가 하나만 잠깐 깜박이면 [HoloLens 요금을 청구해야](hololens2-charging.md#charging-the-device) 할 수 있습니다.
- 전원 단추를 누를 때 LED가 켜지지만 디스플레이에 아무것도 표시되지 않는 경우 [디바이스의 하드 재설정을 수행합니다.](hololens-recovery.md#hard-reset-procedure)

HoloLens 고정되거나 응답하지 않는 경우:

- LED 5개가 모두 꺼질 때까지 전원 단추를 누르거나 LED가 응답하지 않는 경우 15초 동안 전원 단추를 눌러 HoloLens 끕니다. HoloLens 시작하려면 전원 단추를 다시 누릅니다.

이러한 단계가 작동하지 않으면 HoloLens 2 디바이스 또는 [HoloLens(1세대) 디바이스를](hololens1-recovery.md) [복구해](hololens-recovery.md) 볼 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="low-disk-space-error"></a>"디스크 공간 부족" 오류

다음 중 하나 이상을 수행하여 일부 스토리지 공간을 확보해야 합니다.

- 사용되지 않는 일부 공백을 삭제합니다. 시스템 **공간 설정** 이동하여  >    >  더 이상 필요하지 않은 공간을 선택한 다음, **제거를** 선택합니다.
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
- 특정 유형의 연락처 렌즈 및 안경(색이 있는 연락처 렌즈, 일부 상한 연락처 렌즈, IR 차단 안경, 일부 고가용성 안경, 눈금 등)
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

HoloLens 2 음성에 응답하지 않는 경우 음성 인식이 켜져 있는지 확인합니다. **개인** 정보 설정 시작으로 이동하여  >    >    >  **음성** **인식을** 켭니다.

[목록으로 돌아가기](#list)

## <a name="hand-input-isnt-working"></a>손 입력이 작동하지 않습니다.

HoloLens 손을 볼 수 있도록 제스처 프레임에 유지해야 합니다.  Mixed Reality 홈은 손을 추적하는 시기를 알려주는 피드백을 제공합니다.  피드백은 HoloLens 버전에 따라 다릅니다.

- HoloLens(1세대)에서 응시 커서가 점에서 링으로 변경됩니다.
- HoloLens 2 손을 슬레이트 가까이에 놓으면 손끝 커서가 나타나고 슬레이트가 더 멀리 있을 때 손 광선이 나타납니다.

많은 몰입형 앱은 Mixed Reality Home과 유사한 입력 패턴을 따릅니다.  [HoloLens(1세대)](hololens1-basic-usage.md#use-hololens-with-your-hands) [및](hololens2-basic-usage.md#the-hand-tracking-frame)HoloLens 2 손 입력을 사용하는 방법에 대해 자세히 알아봅니다.

글러브를 신고 있는 경우 일부 유형의 글러브가 손 추적에서 작동하지 않습니다.  일반적인 예로는 검정색 무중단 글러브가 있습니다. 이 블래스는 광원을 흡수하는 경향이 있으며 깊이 카메라에 의해 선택되지 않습니다.  작업에 글러브가 포함된 경우 파란색 또는 회색과 같은 밝은 색을 사용해보는 것이 좋습니다.  또 다른 예로는 손 모양이 가려지는 경향이 있는 큰 글러브가 있습니다. 최상의 결과를 위해 가능한 한 폼 맞춤인 글러브를 사용하는 것이 좋습니다.

visor에 지문 또는 번짐이 있는 경우 HoloLens 함께 제공되는 마이크로Fiber 청소 의류를 사용하여 visor를 깔끔하게 정리합니다.

[목록으로 돌아가기](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi 연결할 수 없습니다.

HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 작업을 시도해 볼 수 있습니다.

- Wi-Fi가 켜져 있는지 확인하세요. 확인하려면 시작 제스처를 사용한 다음, **설정**  >  **네트워크 &amp; 인터넷**  >  **Wi-Fi를** 선택합니다. Wi-Fi가 켜져 있으면 끈 다음 다시 켜보세요.
- 라우터 또는 액세스 지점에 좀 더 가깝게 이동하세요.
- Wi-Fi 라우터를 다시 시작한 다음 HoloLens [다시 시작합니다.](hololens-recovery.md) 다시 연결해 보세요.
- 이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용하고 있는지 확인합니다. 제조업체 웹 사이트에서 이 정보를 찾을 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth 디바이스가 페어링되지 않습니다.

[Bluetooth 디바이스를 페어링하는 데](hololens-connect-devices.md)문제가 있는 경우 다음을 시도합니다.

- **설정** 디바이스 로 이동하여 Bluetooth 켜져 있는지  >  **확인합니다.** 이 경우 해제했다가 다시 켭니다.
- Bluetooth 디바이스에 완전히 요금이 부과되거나 배터리가 새로 고워지는지 확인합니다.
- 여전히 연결할 수 없는 경우 [HoloLens 다시 시작합니다.](hololens-recovery.md)

[목록으로 돌아가기](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 마이크가 작동하지 않습니다.

일부 USB-C 마이크는 자신을 *마이크와* 스피커로 잘못 보고합니다. 이는 마이크에 문제가 있으며 HoloLens 문제가 아닙니다. 이러한 마이크 중 하나를 HoloLens 연결하면 소리가 손실될 수 있습니다. 다행히 간단한 수정이 있습니다.  

**설정** 시스템 소리 에서  ->    ->  기본 제공 **스피커(아날로그 기능 오디오 드라이버)를** **기본 디바이스** 로 명시적으로 설정합니다. HoloLens 마이크가 제거되고 나중에 다시 연결되더라도 이 설정을 기억해야 합니다.

![USB-C 마이크 문제 해결](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>설정 사용할 수 있는 것으로 나열된 디바이스가 작동하지 않습니다.

HoloLens(1세대)는 Bluetooth 오디오 프로필을 지원하지 않습니다. 스피커 및 헤드셋과 같은 Bluetooth 오디오 디바이스는 HoloLens 설정에서 사용할 수 있는 것으로 나타날 수 있지만 지원되지 않습니다.

HoloLens 2 스테레오 재생을 위해 Bluetooth A2DP 오디오 프로필을 지원합니다. Bluetooth 주변 장치에서 마이크 캡처를 사용하도록 설정하는 Bluetooth Hands Free 프로필은 HoloLens 2 지원되지 않습니다.

Bluetooth 디바이스를 사용하는 데 문제가 있는 경우 지원되는 디바이스인지 확인합니다. 지원되는 디바이스는 다음과 같습니다.

- 영어 QWERTY Bluetooth 키보드(홀로그램 키보드를 사용하는 모든 곳에서 사용할 수 있습니다).
- 마우스를 Bluetooth.
- [HoloLens 클릭하여 을 클릭합니다.](hololens1-clicker.md)

다른 Bluetooth HID 및 GATT 디바이스를 HoloLens 함께 페어링할 수 있습니다. 그러나 실제로 디바이스를 사용하려면 Microsoft Store 해당 도우미 앱을 설치해야 할 수 있습니다.

[목록으로 돌아가기](#list)
