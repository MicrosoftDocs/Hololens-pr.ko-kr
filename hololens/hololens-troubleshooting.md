---
title: HoloLens 장치 문제 해결
description: 가장 일반적인 솔루션을 최신 상태로 유지 하 여 장치 문제 및 문제 해결 기법을 HoloLens 하세요.
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
ms.openlocfilehash: 5501e036b5852833b7ff26445a98c3378ae6963c96114e26bf588eb33a56f6f0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662879"
---
# <a name="device-troubleshooting"></a>장치 문제 해결

이 문서에서는 몇 가지 일반적인 HoloLens 문제를 해결 하는 방법을 설명 합니다.

>[!IMPORTANT]
> 문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다. 전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.

<a id="list"></a>

**알려진 문제**
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

**Input**
- [음성 명령이 작동 하지 않음](#voice-commands-arent-working)
- [손으로 입력이 작동 하지 않음](#hand-input-isnt-working)

**연결**
- [Wi-fi에 연결할 수 없음](#cant-connect-to-wi-fi)

**외부 장치** 
- [Bluetooth 장치가 페어링 하지 않음](#bluetooth-devices-arent-pairing)
- [USB-C 마이크가 작동 하지 않음](#usb-c-microphone-isnt-working)
- [설정에서 사용 가능으로 나열 된 장치가 작동 하지 않음](#devices-listed-as-available-in-settings-dont-work)

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

지금까지 문제를 발생 시킬 수 없기 때문에 알려진 해결 방법이 없습니다. 피드백 허브를 통해 버그를 제출 하면 조사에 도움이 됩니다. 이것은 **알려진 문제** 입니다.

[목록으로 돌아가기](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>키보드에서 특수 문자로 전환 하지 않음

사용자가 회사 또는 학교 계정을 선택 하 고 암호를 입력 하는 경우 OOBE 중에 문제가 발생 합니다. &123 단추를 탭 하 여 키보드의 특수 문자로 전환 하려는 시도는 특수 문자로 변경 되지 않습니다. 이것은 **알려진 문제** 입니다.

해결 방법:
-   키보드를 닫고 텍스트 필드를 탭 하 여 다시 엽니다.
-   암호를 잘못 입력 했습니다. 다음 번에 키보드를 고 하면 예상 대로 작동 합니다.
- 웹 인증, 키보드를 닫고 **다른 장치에서 로그인** 을 선택 합니다.
-   숫자만 입력 하는 경우 사용자는 특정 키를 길게 눌러 확장 된 메뉴를 열 수 있습니다.
-   USB 키보드 사용.

이는 다음에 영향을 주지 않습니다.
- 개인 계정을 사용 하도록 선택 하는 사용자입니다.

[목록으로 돌아가기](#list)

## <a name="downloading-locked-files-doesnt-error"></a>잠긴 파일 다운로드 오류

> [!NOTE]
> 이 문제는 Windows Insider build 버전 20348.1403에서 해결 된 **알려진 문제** 입니다.

Windows Holographic의 이전 빌드에서 잠긴 파일을 다운로드 하려고 하면 결과는 HTTP 오류 페이지가 됩니다. Windows Holographic, 버전 21h1 업데이트에서 잠긴 파일을 다운로드 하려고 하면 파일이 다운로드 되지 않으며 오류가 발생 하지 않습니다.

[목록으로 돌아가기](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>장치 포털 파일 업로드/다운로드 제한 시간
> [!NOTE]
> 이 문제는 Windows Insider build 버전 20348.1403에서 해결 된 **알려진 문제** 입니다. 이전에 해결 방법의 일부로 SSL 연결을 사용 하지 않도록 설정한 경우 다시 사용 하도록 설정 하는 것이 좋습니다.


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

HoloLens(1세대)에서는 기본 제공 음성 인식을 구성할 수 없습니다. 항상 켜져 있습니다. HoloLens 2 디바이스를 설정하는 동안 음성 인식과 Cortana 둘 다 설정할지 여부를 선택할 수 있습니다.

HoloLens 2 음성에 응답하지 않는 경우 음성 인식이 켜져 있는지 확인합니다. 개인 정보 음성 설정 **시작으로** 이동하여  >    >    >  **음성** **인식을** 켭니다.

[목록으로 돌아가기](#list)

## <a name="hand-input-isnt-working"></a>손 입력이 작동하지 않습니다.

HoloLens 손을 볼 수 있도록 제스처 프레임에 유지해야 합니다.  Mixed Reality 홈은 손을 추적하는 시기를 알려주는 피드백을 제공합니다.  피드백은 HoloLens 버전에 따라 다릅니다.
- HoloLens(1세대)에서 응시 커서가 점에서 링으로 변경됩니다.
- HoloLens 2 손을 슬레이트 가까이에 놓으면 손끝 커서가 나타나고 슬레이트가 더 멀리 있을 때 손 광선이 나타납니다.

많은 몰입형 앱은 Mixed Reality Home과 유사한 입력 패턴을 따릅니다.  [HoloLens(1세대)](hololens1-basic-usage.md#use-hololens-with-your-hands) [및](hololens2-basic-usage.md#the-hand-tracking-frame)HoloLens 2 손 입력을 사용하는 방법에 대해 자세히 알아봅니다.

글러브를 신고 있는 경우 일부 유형의 글러브가 손 추적에서 작동하지 않습니다.  일반적인 예로는 검정색 무중단 글러브가 있습니다. 이 블래스는 광원을 흡수하는 경향이 있으며 깊이 카메라에 의해 선택되지 않습니다.  작업에 글러브가 포함된 경우 파란색 또는 회색과 같은 밝은 색을 사용해보는 것이 좋습니다.  또 다른 예로는 손 모양이 가려지는 경향이 있는 큰 글러브가 있습니다. 최상의 결과를 위해 가능한 한 폼 맞춤인 글러브를 사용하는 것이 좋습니다.

visor에 지문 또는 스미지가 있는 경우 HoloLens 함께 제공되는 마이크로Fiber 청소 의류를 사용하여 바이저를 깔끔하게 정리합니다.

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
일부 USB-C 마이크는 자신을 *마이크와* 스피커로 잘못 보고합니다. HoloLens 아닌 마이크에 문제가 있습니다. 이러한 마이크 중 하나를 HoloLens 연결하면 소리가 손실될 수 있습니다. 다행히 간단한 수정이 있습니다.  

**설정** 시스템 소리 에서  ->    ->  기본 제공 **스피커(아날로그 기능 오디오 드라이버)를** **기본 디바이스** 로 명시적으로 설정합니다. HoloLens 마이크가 제거되고 나중에 다시 연결되더라도 이 설정을 기억해야 합니다.

![USB-C 마이크 문제 해결](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>설정 사용할 수 있는 것으로 나열된 디바이스가 작동하지 않습니다.

HoloLens(1세대)는 Bluetooth 오디오 프로필을 지원하지 않습니다. 스피커 및 헤드셋과 같은 Bluetooth 오디오 디바이스는 HoloLens 설정에서 사용할 수 있는 것으로 나타날 수 있지만 지원되지 않습니다.

HoloLens 2 스테레오 재생을 위해 Bluetooth A2DP 오디오 프로필을 지원합니다. Bluetooth 주변 장치에서 마이크 캡처를 사용하도록 설정하는 Bluetooth Hands Free 프로필은 HoloLens 2 지원되지 않습니다.

Bluetooth 디바이스를 사용하는 데 문제가 있는 경우 지원되는 디바이스인지 확인합니다. 지원되는 디바이스는 다음과 같습니다.

- 영어 QWERTY Bluetooth 키보드(홀로그램 키보드를 사용하는 모든 곳에서 사용할 수 있습니다.)
- 마우스를 Bluetooth.
- [HoloLens 클릭하여 을 클릭합니다.](hololens1-clicker.md)

다른 Bluetooth HID 및 GATT 디바이스를 HoloLens 함께 페어링할 수 있습니다. 그러나 실제로 디바이스를 사용하려면 Microsoft Store 해당 도우미 앱을 설치해야 할 수 있습니다.

[목록으로 돌아가기](#list)
