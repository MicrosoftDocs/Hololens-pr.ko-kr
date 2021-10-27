---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: Insider 빌드를 시작 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 귀중 한 피드백을 제공 하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351658"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens에 대한 참가자 미리 보기

HoloLens에 대 한 최신 Insider Preview 빌드를 시작 합니다. 간단 하 게 [시작](hololens-insider.md#start-receiving-insider-builds) 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 유용한 피드백을 제공할 수 있습니다.

## <a name="windows-insider-release-notes"></a>Windows 참가자 릴리스 정보

HoloLens에 대 한 새로운 기능 및 수평은 무엇 인가요? HoloLens에 제공 되는 새로운 업데이트를 확인 하세요.

### <a name="colorblind-mode"></a>Colorblind 모드

Insider build 20348.1463에 추가 됨

colorblind 모드는 HoloLens 더 쉽게 액세스할 수 있도록 하는 유용한 기능입니다. 새 색맹인 모드는 설정 앱에서 **설정**  ->  **접근성**  ->  **색 필터** 를 사용 하 여 찾을 수 있습니다. 여러 가지 새 필터를 사용할 수 있습니다. 다음은 사용 가능한 필터 중 일부에 대 한 시각적 예제입니다.

| 끄기 | 회색조로 변환 | Tritanopia |
|-----|-----------|------------|
| ![색 필터 해제](images/colorblind-off.png)   | ![색 필터 회색조로 변환](images/colorblind-greyscale.png)         | ![색 필터 tritanopia](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>수정 사항 및 향상 된 기능

- [전원이 18%로 이동 될 때마다 장치가 갑자기 자동으로 종료](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)되는 알려진 문제를 수정 했습니다.
- 다운 방향을 검색할 때 플랫폼 전환의 향상 된 기능
- 업데이트 대화 상자에 대 한 문제를 해결 했습니다.
- 수신함 Microsoft Edge 브라우저 버전으로 업데이트 되었습니다.
- 다시 부팅 한 후 선택적 진단 데이터를 설정/해제 해도 원격 분석 설정 페이지에서 선택한 설정이 유지 되지 않는 문제가 해결 되었습니다.
- 장치에 상대적인 45 각도 각도에서 회전 된 경우 QR 코드가 인식 되지 않는 문제를 해결 하 고 문제를 해결 합니다.

## <a name="start-receiving-insider-builds"></a>Insider 빌드 수신을 시작 합니다.

> [!NOTE]
> 최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.
>
> - "장치 다시 부팅" 음성 명령은 제대로 작동 합니다.
> - 설정/Windows Insider Program에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 사용자가 발생 시킨 백 엔드에 대 한 버그가 있었으며이로 인해 다시 추적할 수 있습니다.

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** 로 이동 하 고 **시작** 을 선택 합니다. Windows Insider로 등록 하는 데 사용한 계정을 연결 합니다.

> [!NOTE]
> 참가자 빌드에 장치를 등록 하려면 선택적 원격 분석을 사용 하도록 설정 해야 합니다. 아직 수행 하지 않은 경우 설정 앱을 열고 **개인 정보**  ->  **진단 & 피드백** 을 선택한 후 **선택적 진단 데이터** 를 선택 합니다.

이제 Windows insider가 채널로 이동 하 고 있습니다. **빠른** 링은 **Dev 채널이** 되 고, **저속** 링은 **베타 채널이** 되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이** 됩니다. 매핑은 다음과 같습니다.

![Windows 참가자 채널 설명입니다.](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그의 [Windows Insider 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.
그런 다음 **Windows의 활성 개발** 을 선택 하 고 **개발 채널** 또는 **베타 채널** 빌드를 받을지 여부를 선택한 후 프로그램 용어를 검토 합니다.
확인을 선택 하 **> 지금 다시 시작** 하 여 완료 합니다. 장치를 다시 부팅 한 후 설정으로 이동 하 **> 업데이트 & 업데이트 > 업데이트를 확인** 하 여 최신 빌드를 가져옵니다.

### <a name="update-error-0x80070490-work-around"></a>업데이트 오류 0x80070490 문제 해결

Dev 또는 Beta 채널에서 업데이트할 때 0x80070490 업데이트 오류가 발생 하는 경우 다음과 같은 단기 해결 방법을 시도해 보세요. 여기에는 insider channel을 이동 하 고, 업데이트를 선택한 다음, Insider channel을 다시 이동 하는 작업이 포함 됩니다.

#### <a name="stage-one---release-preview"></a>1 단계 릴리스 미리 보기

1. 설정, 업데이트 & 보안, Windows Insider Program, **Release preview 채널** 을 차례로 선택 합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트 **업데이트를 확인** 합니다. 업데이트 후 2 단계를 계속 진행 합니다.

#### <a name="stage-two---dev-channel"></a>2 단계 개발자 채널

1. 설정, 업데이트 & 보안, Windows Insider Program에서 **Dev Channel** 을 선택 합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트 **업데이트를 확인** 합니다.

## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 방향

비행 서명 된 ffu로 테스트 하려면 비행 서명 된 ffu를 깜박임 전에 먼저 장치 잠금을 해제 해야 합니다.

1. PC:
    1. 에서 PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.

    1. Microsoft Store에서 ARC (고급 복구 도우미)를 설치 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 합니다.

1. HoloLens 비행 잠금 해제: **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** 을 등록 하 고 장치를 다시 부팅 합니다.

1. 플래시 FFU-이제 호를 사용 하 여 비행 서명 된 FFU를 깜박일 수 있습니다.

### <a name="provide-feedback-and-report-issues"></a>사용자 의견을 제공 하 고 문제를 보고 합니다.

사용자 의견을 제공 하 고 문제를 보고 하려면 HoloLens [피드백 허브 앱](hololens-feedback.md) 을 사용 하세요. 피드백 허브를 사용 하면 엔지니어가 신속 하 게 디버그 하 고 문제를 해결 하는 데 필요한 모든 진단 정보가 포함 됩니다.  중국어 및 일본어 버전의 HoloLens 관련 된 문제는 동일한 방식으로 보고 해야 합니다.

> [!NOTE]
> 사용자 의견 허브에서 문서 폴더에 액세스할 지 여부를 묻는 메시지를 수락 해야 합니다 (메시지가 표시 되 면 **예** 선택).

## <a name="note-for-developers"></a>개발자를 위한 정보

HoloLens의 참가자 빌드를 사용 하 여 응용 프로그램을 개발 하는 것이 좋습니다.  [HoloLens 개발자 설명서](https://developer.microsoft.com/windows/mixed-reality/development) 를 확인 하 여 시작 하세요. 이와 동일한 지침은 HoloLens의 참가자 빌드와 함께 작동 합니다.  이미 HoloLens 개발에 사용 하 고 있는 것과 동일한 Unity 및 Visual Studio 빌드를 사용할 수 있습니다.

## <a name="stop-receiving-insider-builds"></a>Insider 빌드 수신을 중지 합니다.

Windows Holographic의 참가자 빌드를 더 이상 수신 하지 않으려는 경우, HoloLens 프로덕션 빌드를 실행 하 고 있을 때 옵트아웃 하거나, 고급 복구 도우미를 사용 하 여 장치를 [복구](hololens-recovery.md) 하 고 Windows Holographic의 비-insider 버전으로 장치를 복구할 수 있습니다.

> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치 하면 사용자에 게 Insider Preview 빌드에서 등록을 취소 하는 알려진 문제가 있습니다. 이후에는 장치를 수동으로 복구 해야 합니다. 영향을 받는 경우에 대 한 자세한 내용은이 [알려진 문제](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)에 대 한 자세한 내용을 확인 하세요.

HoloLens에서 프로덕션 빌드를 실행 하 고 있는지 확인 하려면 다음을 수행 합니다.

1. **설정 > System > 정보** 로 이동 하 여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.

참가자 빌드를 옵트아웃 (opt out) 하려면 다음을 수행 합니다.

1. 프로덕션 빌드를 실행 하는 HoloLens에서 **설정 > 업데이트 & 보안 > insider Program** 로 이동 하 여 insider build **중지** 를 선택 합니다.

1. 지침에 따라 장치를 옵트아웃 합니다.
