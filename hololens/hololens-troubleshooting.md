---
title: HoloLens 디바이스 문제 해결
description: 디바이스 문제를 HoloLens 및 문제 해결 기술에 대한 가장 일반적인 솔루션을 최신 상태로 유지합니다.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 문제, 버그, 문제 해결, 수정, 도움말, 지원, HoloLens, 에뮬레이터
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635452"
---
# <a name="device-troubleshooting"></a>디바이스 문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결하는 방법을 설명합니다.

>[!IMPORTANT]
> 문제 해결 절차를 시작하기 전에 가능한 경우 디바이스에 배터리 용량의 **20~40%가** 청구되는지 확인합니다. 전원 단추 아래에 있는 [배터리 표시등은](hololens2-setup.md#lights-that-indicate-the-battery-level) 디바이스에 로그인하지 않고 배터리 용량을 확인하는 빠른 방법입니다.

<a id="list"></a>

**알려진 문제**
- [Remote Assist 비디오가 20분 후에 중지됩니다.](#remote-assist-video-freezes-after-20-minutes)
- [자동 로그인에서 로그인 요청](#auto-login-asks-for-log-in)
- [Microsoft Edge 시작하지 못함](#microsoft-edge-fails-to-launch)
- [키보드가 특수 문자로 전환되지 않습니다.](#keyboard-doesnt-switch-to-special-characters)
- [잠긴 파일을 다운로드해도 오류가 표시되지 않습니다.](#downloading-locked-files-doesnt-error)
- [파일 업로드/다운로드 시간 장치 포털](#device-portal-file-uploaddownload-times-out)
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

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist 비디오가 20분 후에 중지됩니다.

> [!NOTE]
> 이 문제에 대한 수정이 있는 최신 버전의 Remote Assist 있습니다. 이 문제를 방지하려면 Remote Assist 최신 버전으로 [업데이트하세요.](holographic-store-apps.md#update-apps)

> [!NOTE]
> 이 알려진 문제의 심각도로 인해 Windows Holographic 버전 21H1의 가용성을 일시적으로 일시 중지했습니다. 이제 21H1 빌드를 다시 사용할 수 있으므로 디바이스가 다시 최신 21H1 빌드로 업데이트될 수 있습니다.

[Windows Holographic 버전 21H1의](hololens-release-notes.md#windows-holographic-version-21h1)최신 릴리스에서는 Remote Assist 일부 사용자가 20분 넘게 통화하는 동안 비디오 중지를 경험했습니다. 이것은 **알려진 문제입니다.**

### <a name="workarounds"></a>해결 방법

최신 빌드로 Remote Assist 업데이트할 수 없는 경우 다음 해결 방법을 시도해 보세요.

#### <a name="restart-in-between-calls"></a>호출 간에 다시 시작

호출이 20분을 초과하고 이 문제가 발생하는 경우 디바이스를 다시 부팅해 보세요. Remote Assist 호출 사이에 디바이스를 다시 부팅하면 디바이스가 새로 고쳐지고 다시 양호한 상태가 됩니다.

Windows Holographic에서 디바이스를 신속하게 다시 시작하려면 [버전 21H1에서](hololens-release-notes.md#windows-holographic-version-21h1) 시작 메뉴를 열고 사용자 아이콘을 선택한 다음, **다시 시작을** 선택합니다.

[목록으로 돌아가기](#list)

## <a name="auto-login-asks-for-log-in"></a>자동 로그인에서 로그인 요청

설정 계정 로그인 옵션 **->** 및 필수에서 값을 안 됨으로 설정하여 자동으로  ->    ->   로그인하도록 HoloLens 2  디바이스를 구성할 수 **있습니다.** 일부 사용자는 기능 업데이트와 같이 상당히 큰 업데이트로 디바이스를 업데이트할 때 디바이스에 다시 로그인해야 할 수 있습니다. 이것은 **알려진 문제입니다.**

이 문제가 발생할 수 있는 경우의 예:

- Windows Holographic 버전 2004(빌드 19041.xxxx)에서 Windows Holographic 버전 21H1로 디바이스 업데이트(빌드 20346.xxxx)
- 동일한 주 빌드에서 대규모 업데이트를 사용하도록 디바이스 업데이트(예: Windows Holographic 버전 2004에서 Windows Holographic 버전 20H2로 업데이트)
- 공장 이미지에서 최신 이미지로 디바이스 업데이트

다음 중에는 이 문제가 발생하지 않습니다.

- 월간 서비스 업데이트를 받는 디바이스

메서드 해결:

- PIN, 암호, 아이리스, 웹 인증 또는 FIDO2 키와 같은 로그인 방법입니다.
- 디바이스 PIN을 기억할 수 없고 다른 인증 방법을 사용할 수 없는 경우 사용자는 [수동 리플래시 모드 를](hololens-recovery.md#manual-procedure)사용할 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge 시작하지 못함

> [!NOTE]
> 이 문제는 원래 Microsoft Edge 배송 버전을 염두에 두고 만들어졌습니다. 이 문제는 [새 Microsoft Edge](hololens-new-edge.md)해결될 수 있습니다. 그렇지 않은 경우 피드백을 제출하세요.

일부 고객은 Microsoft Edge 시작하지 못하는 문제를 보고했습니다. 이러한 고객의 경우 다시 부팅을 통해 문제가 지속되며 Windows 또는 애플리케이션 업데이트로 해결되지 않습니다. 이 문제가 발생하고 [Windows](hololens-updates.md#manually-check-for-updates)최신인지 확인한 경우 Windows 업데이트 다운로드, 설치 및 구성을 > 설치 및 업데이트 범주 및 하위 범주를 사용하여 피드백 허브 [앱에서](hololens-feedback.md) 버그를 제출하세요.

지금까지 문제의 근본 원인을 알 수 없으므로 알려진 해결 방법이 없습니다. 피드백 허브 통해 버그를 신고하면 조사에 도움이 됩니다. 이것은 **알려진 문제입니다.**

[목록으로 돌아가기](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>키보드가 특수 문자로 전환되지 않습니다.

OOBE 중에는 사용자가 직장 또는 학교 계정을 선택하고 암호를 입력한 후 &123 단추를 탭하여 키보드의 특수 문자로 전환하려고 하면 특수 문자로 변경되지 않는 문제가 있습니다. 이것은 **알려진 문제입니다.**

해결 작업:
-   키보드를 닫고 텍스트 필드를 탭하여 다시 엽니다.
-   암호를 잘못 입력합니다. 다음에 키보드가 다시 시작되면 예상대로 작동합니다.
- 웹 인증에서 키보드를 닫고 **다른 디바이스에서 로그인을** 선택합니다.
-   숫자만 입력하는 경우 사용자는 특정 키를 누르고 확장된 메뉴를 열 수 있습니다.
-   USB 키보드 사용.

이는 다음에 영향을 주지 않습니다.
- 개인 계정을 사용하도록 선택한 사용자입니다.

[목록으로 돌아가기](#list)

## <a name="downloading-locked-files-doesnt-error"></a>잠긴 파일을 다운로드해도 오류가 발생하지 않습니다.

> [!NOTE]
> 이는 Windows Insider 빌드 버전 20348.1403에서 해결된 **알려진 문제입니다.**

Windows Holographic의 이전 빌드에서 잠긴 파일을 다운로드하려고 할 때 결과는 HTTP 오류 페이지가 됩니다. Windows Holographic 버전 21H1 업데이트에서 잠긴 파일을 다운로드하려고 시도하면 아무 것도 표시되지 않습니다. 파일이 다운로드되지 않고 오류가 발생하지 않습니다.

[목록으로 돌아가기](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>파일 업로드/다운로드 시간 장치 포털
> [!NOTE]
> 이는 Windows Insider 빌드 버전 20348.1403에서 해결된 **알려진 문제입니다.** 이전에 해결 방법의 일부로 SSL 연결을 사용하지 않도록 설정한 경우 다시 사용하도록 설정하는 것이 좋습니다.


일부 고객은 파일을 업로드하거나 다운로드하려고 할 때 작업이 중단된 다음 시간 부족하거나 완료되지 않을 수 있음을 발견했습니다. 이는 알려진['파일 잠김' 문제와는](#downloading-locked-files-doesnt-error) 별개입니다. 이는 Holographic 버전 2004, 20H2 및 21H1 시장 내 빌드에 Windows 영향을 미칩니다. 이 문제는 장치 포털 특정 요청을 처리하는 버그로 인해 발생했으며, https를 사용할 때 가장 일관되게 발생합니다(기본값). 

### <a name="workaround"></a>해결 방법

Wi-Fi 및 UsbNcm에도 동일하게 적용되는 이 해결 방법은 "SSL 연결"에서 "필수" 옵션을 사용하지 않도록 설정하는 것입니다. 이렇게 하려면 장치 포털 **시스템** 으로 이동하여 **기본 설정** 페이지를 선택합니다. 디바이스 **보안** 섹션에서 **SSL 연결** 를 찾은 다음, **필수** 를 사용하지 않도록 설정하려면 선택을 취소합니다.

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
- 전원 단추를 누를 때 Led가 켜져 있지만 디스플레이에 아무것도 표시 되지 않으면 [장치의 하드 리셋을 수행](hololens-recovery.md#hard-reset-procedure)합니다.

HoloLens 고정 되거나 응답 하지 않는 경우:

- 5 개의 led가 모두 꺼질 때까지 전원 단추를 누르거나 led가 응답 하지 않는 경우 15 초 동안 HoloLens를 해제 합니다. HoloLens를 시작 하려면 전원 단추를 다시 누릅니다.

이러한 단계가 작동 하지 않는 경우 [HoloLens 2 장치](hololens-recovery.md) 또는 [HoloLens (첫 번째 gen) 장치](hololens1-recovery.md) 를 복구 해 볼 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="low-disk-space-error"></a>"디스크 공간 부족" 오류

다음 중 하나 이상을 수행 하 여 저장소 공간을 확보 해야 합니다.

- 사용 하지 않는 공간을 삭제 합니다. **설정** 시스템 공간으로 이동 하 여  >    >  더 이상 필요 하지 않은 공간을 선택 하 고 **제거** 를 선택 합니다.
- 배치한 holograms 중 일부를 제거 합니다.
- 사진 앱에서 일부 그림과 비디오를 삭제 합니다.
- HoloLens에서 일부 앱을 제거 합니다. **모든 앱** 목록에서 제거 하려는 앱을 탭 하 고 누른 다음 **제거** 를 선택 합니다.

[목록으로 돌아가기](#list)

## <a name="calibration-fails"></a>보정 실패

보정은 대부분의 사용자에 게 작동 하지만 보정에 실패 하는 경우가 있습니다.
  
몇 가지 잠재적인 보정 실패 이유는 다음과 같습니다.

- 보정 대상을 따르지 않고 무시 가져오기
- 더티 또는 긁힌 장치 센터 또는 장치 센터의 위치가 올바르게 지정 되지 않았습니다.
- 더티 또는 긁힌
- 특정 유형의 연락처 lenses 및 고 사양 (컬러 연락처 lenses, 일부 toric 연락처 lenses, IR 차단, 일부 높은 prescription, 선글라스 또는 비슷함)
- 더 많은 발음을 구성을 및 eyelash 확장
- 장치가 눈동자를 보지 못하도록 차단 하는 경우에는 머리카락 또는 두꺼운 eyeglass 프레임
- 좁은 눈동자, 긴 eyelashes, amblyopia, nystagmus, LASIK 또는 기타 아이 surgeries의 일부 사례와 같은 특정 눈동자 physiology, 아이 조건 또는 눈 수술

보정에 실패 한 경우 다음을 시도 합니다.

- 장치 센터 정리
- 고가를 청소 하는 중
- 최대한 눈에 가까운 장치 센터 푸시
- 방식으로 센터에서 개체 이동 (예: 헤어)
- 대화방에서 광원을 설정 하거나 직접 광선 이동

모든 지침을 따르고 보정에 여전히 오류가 발생 한 경우 설정에서 보정 프롬프트를 사용 하지 않도록 설정할 수 있습니다. [피드백 허브](hololens-feedback.md)에서 사용자 의견을 보내 알려주세요.

또한 [이미지 색 또는 밝기 문제 해결](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) 에 대 한 관련 정보를 참조 하세요.

IPD 설정은 시스템에서 눈 위치를 계산 하므로 HoloLens 2에는 적용 되지 않습니다. 

[목록으로 돌아가기](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>이전에 다른 사용자에 대해 HoloLens를 설정 했기 때문에 로그인 할 수 없습니다.

[장치를 **깜박임 모드로** 전환 하 고 고급 복구 도우미를 사용](hololens-recovery.md#clean-reflash-the-device) 하 여 장치를 복구할 수 있습니다.

[목록으로 돌아가기](#list)


## <a name="unity-isnt-working"></a>Unity가 작동 하지 않음

- HoloLens 개발에 권장 되는 최신 버전의 Unity 용 [도구 설치](/windows/mixed-reality/install-the-tools) 를 참조 하세요.
- unity HoloLens Technical Preview의 알려진 문제는 [HoloLens unity 포럼](https://forum.unity3d.com/threads/known-issues.394627/)에 설명 되어 있습니다.

[목록으로 돌아가기](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows 장치 포털이 제대로 작동 하지 않습니다.

- 혼합 현실 캡처의 실시간 미리 보기 기능은 몇 초 동안 대기 시간을 나타낼 수 있습니다.

- 가상 입력 페이지에서 가상 제스처 섹션 아래의 제스처 및 스크롤 컨트롤이 작동 하지 않습니다. 이를 사용 하면 아무런 영향을 주지 않습니다. 가상 입력 페이지의 가상 키보드가 제대로 작동 합니다.

- 설정에서 개발자 모드를 사용 하도록 설정한 후 장치 포털을 켜는 스위치를 사용 하도록 설정 하는 데 몇 초 정도 걸릴 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator 작동 하지 않습니다.

HoloLens 에뮬레이터에 대 한 정보는 개발자 설명서에 있습니다.  [HoloLens 에뮬레이터 문제 해결을](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)참조 하세요.


- Microsoft Store의 모든 앱은 에뮬레이터와 호환 되지 않습니다. 예를 들어, 에뮬레이터에서 젊은 Conker 및 조각은 재생할 수 없습니다.
- Emulator PC 웹캠을 사용할 수 없습니다.
- Windows 장치 포털의 실시간 미리 보기 기능은 에뮬레이터에서 작동 하지 않습니다. 여전히 혼합 현실 비디오 및 이미지를 캡처할 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="voice-commands-arent-working"></a>음성 명령이 작동 하지 않음

Cortana 음성 명령에 응답 하지 않는 경우 Cortana 켜져 있는지 확인 합니다. 모든 앱 목록에서 **Cortana**  >  **Menu**  >  **노트북**  >  **설정** 를 선택 하 여 변경 합니다. 말할 수 있는 내용에 대 한 자세한 내용은 [HoloLens에 음성 사용](hololens-cortana.md)을 참조 하세요.

HoloLens (첫 번째 gen)에서는 기본 제공 음성 인식을 구성할 수 없습니다. 항상 켜져 있습니다. HoloLens 2에서 장치를 설치 하는 동안 음성 인식 및 Cortana를 모두 켤 지 여부를 선택할 수 있습니다.

HoloLens 2 음성에 응답 하지 않는 경우 음성 인식이 설정 되어 있는지 확인 합니다. **시작**  >  **설정**  >  **개인 정보**  >  **음성** 으로 이동 하 여 **음성 인식을** 켭니다.

[목록으로 돌아가기](#list)

## <a name="hand-input-isnt-working"></a>손으로 입력이 작동 하지 않음

HoloLens 사용자의 손을 볼 수 있도록 하려면 제스처 프레임에 보관 해야 합니다.  혼합 현실 홈은 사용자가 손을 추적 하는 시기를 알 수 있는 피드백을 제공 합니다.  사용자 의견은 다양 한 버전의 HoloLens에서 다릅니다.
- HoloLens (첫 번째 gen)에서 응시 커서는 점에서 링으로 바뀝니다.
- HoloLens 2에서 손 모양이 슬레이트에 가까이 있을 때 fingertip 커서가 나타나고 슬레이트이 더 멀리 떨어져 있을 때 손 모양으로 나타납니다.

많은 모던 앱은 혼합 현실 집과 비슷한 입력 패턴을 따릅니다.  [HoloLens (첫 번째 gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) 및 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)에서 직접 입력을 사용 하는 방법에 대해 자세히 알아보세요.

글러브를 입고 있는 경우 일부 종류의 장갑은 수동 추적에서 작동 하지 않습니다.  일반적인 예로는 검정 고무 장갑이 있습니다 .이는 적외선을 흡수 하 고 깊이 카메라에 의해 선택 되지 않습니다.  작업에 고무 장갑이 포함 되어 있는 경우 파란색 또는 회색 등의 더 밝은 색을 사용해 보는 것이 좋습니다.  또 다른 예로는 긴 baggy 장갑이 있습니다 .이를 통해 손 모양에는 경향이 있습니다. 최상의 결과를 위해 가능한 한 폼 피팅으로 글러브를 사용 하는 것이 좋습니다.

센터에 지문 또는 얼룩이 있는 경우 HoloLens와 함께 제공 되는 마이크로 파이버 클리닝 천을 사용 하 여 센터를 천천히 정리 합니다.

[목록으로 돌아가기](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi에 연결할 수 없음

HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.

- Wi-Fi 설정 되어 있는지 확인 합니다. 확인 하려면 시작 제스처를 사용 하 **설정**  >  **네트워크 &amp; 인터넷**  >  **wi-fi** 를 선택 합니다. Wi-Fi 설정 되어 있으면 해제 한 후 다시 설정 하십시오.
- 라우터 또는 액세스 지점에 가깝게 이동 합니다.
- Wi-Fi 라우터를 다시 시작한 다음 [HoloLens를 다시 시작](hololens-recovery.md)합니다. 다시 연결해 보세요.
- 이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용 하 고 있는지 확인 합니다. 이 정보는 제조업체 웹 사이트에서 찾을 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth 장치가 페어링 하지 않음

[Bluetooth 장치를 페어링 하는](hololens-connect-devices.md)데 문제가 있는 경우 다음을 시도 하세요.

- **설정** 장치로 이동 하 여  >  Bluetooth 켜져 있는지 확인 합니다. 이 경우 다시 설정 하거나 해제 합니다.
- Bluetooth 장치가 완전히 충전 되어 있거나 새 배터리가 있는지 확인 합니다.
- 그래도 연결할 수 없으면 HoloLens를 [다시 시작](hololens-recovery.md)합니다.

[목록으로 돌아가기](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 마이크가 작동 하지 않음
일부 USB-C 마이크는 마이크 *와* 스피커로 잘못 보고 합니다. 이는 HoloLens 아닌 마이크의 문제입니다. 이러한 마이크 중 하나를 HoloLens에 연결 하는 경우 소리가 손실 될 수 있습니다. 다행히 간단한 해결 방법이 있습니다.  

**설정**  ->  **시스템**  ->  **소리** 에서 기본 제공 스피커 **(아날로그 기능 오디오 드라이버)** 를 **기본 장치로** 명시적으로 설정 합니다. 마이크가 제거 되 고 나중에 다시 연결 된 경우에도이 설정을 기억할 HoloLens.

![USB 문제 해결-C 마이크](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>설정에서 사용 가능으로 나열 된 장치가 작동 하지 않음

HoloLens (첫 번째 gen) Bluetooth 오디오 프로필을 지원 하지 않습니다. 스피커 및 헤드셋과 같은 Bluetooth 오디오 장치는 HoloLens 설정에서 사용할 수 있는 것 처럼 보일 수 있지만 지원 되지 않습니다.

HoloLens 2은 스테레오 재생을 위한 Bluetooth A2DP 오디오 프로필을 지원 합니다. Bluetooth 주변 장치에서 마이크 캡처가 가능 하도록 하는 Bluetooth 손 무료 프로필은 HoloLens 2에서 지원 되지 않습니다.

Bluetooth 장치를 사용 하는 데 문제가 있는 경우 지원 되는 장치 인지 확인 합니다. 지원 되는 장치는 다음과 같습니다.

- 영어 Bluetooth 키보드 (holographic 키보드를 사용 하는 모든 곳에서 사용할 수 있음)
- Bluetooth 마우스.
- [HoloLens clicker](hololens1-clicker.md)입니다.

다른 Bluetooth HID 및 GATT 장치를 HoloLens와 함께 연결할 수 있습니다. 그러나 실제로 장치를 사용 하려면 Microsoft Store에서 해당 하는 관련 앱을 설치 해야 할 수 있습니다.

[목록으로 돌아가기](#list)
