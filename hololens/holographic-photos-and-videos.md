---
title: 혼합 현실 사진 및 비디오 캡처, 기록 및 공유
description: HoloLens 혼합 현실 디바이스를 사용하여 혼합 현실 사진 및 비디오를 캡처, 녹화 및 보는 방법을 알아봅니다. Miracast 또는 수집된 파일을 통해 공유하는 방법을 알아봅니다.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635962"
---
# <a name="create-mixed-reality-photos-and-videos"></a>혼합 현실 사진 및 비디오 만들기

HoloLens 통해 사용자는 실제 세계와 디지털 세계를 혼합할 수 있습니다.  MRC(혼합 현실 캡처)를 사용하면 해당 환경을 사진 또는 비디오로 캡처하거나 다른 사람과 실시간으로 볼 수 있는 내용을 공유할 수 있습니다.

혼합 현실 캡처는 1인칭 시점을 사용하므로 다른 사람이 볼 때 홀로그램을 볼 수 있습니다. 3인칭 시점의 경우 [을](/windows/mixed-reality/spectator-view)사용합니다. 데모에는 특히 유용한 보기가 있습니다.

친구 및 동료 간에 비디오를 공유하는 것은 재미있지만 비디오는 다른 사람들이 앱을 사용하거나 앱 및 환경과 문제를 전달하도록 교육하는 데 도움이 될 수 있습니다.

> [!NOTE]
> 혼합 현실 캡처 환경을 시작할 수 없고 HoloLens 작업 디바이스인 경우 시스템 관리자에게 문의하세요. 카메라 액세스는 회사 정책을 통해 제한할 수 있습니다.

## <a name="capture-a-mixed-reality-photo"></a>혼합 현실 사진 캡처

HoloLens 혼합 현실 사진을 찍는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴 사용할 수 있습니다.

### <a name="hardware-buttons-to-take-photos"></a>사진을 찍는 하드웨어 단추

현재 보기의 빠른 사진을 찍려면 볼륨을 위로 누르고 볼륨 다운 단추를 동시에 누릅니다.  이는 스크린샷 또는 인쇄 화면의 HoloLens 버전과 비슷합니다.

- [HoloLens 2 단추 위치](hololens2-hardware.md)
- [HoloLens 단추 위치(1세대)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> **볼륨을 위로** 누르고 3초 동안 **볼륨을 낮추면** 사진을 찍는 대신 비디오 녹화가 시작됩니다. 기록을 중지하려면 **볼륨 위로** 및 **볼륨 다운** 단추를 동시에 탭합니다.

### <a name="voice-commands-to-take-photos"></a>사진을 찍는 음성 명령

HoloLens 2 버전 2004 이상에서는 "Take a picture"이라고 말합니다.

HoloLens(1세대) 또는 HoloLens 2 버전 1903에서는 "Hey Cortana, take a picture."라고 말합니다.

### <a name="start-menu-to-take-photos"></a>사진을 찍는 시작 메뉴

시작 제스처를 사용하여 **시작으로** 이동한 **다음, 카메라** 아이콘을 선택합니다.

캡처하려는 방향을 머리로 가리킨 [다음, 에어 탭하여](hololens2-basic-usage.md#touch-holograms-near-you) 사진을 찍습니다. 계속 에어 탭하고 추가 사진을 캡처할 수 있습니다. 캡처한 모든 사진이 디바이스에 저장됩니다.

시작 제스처를 다시 사용하여 사진 캡처를 종료합니다.  

## <a name="capture-a-mixed-reality-video"></a>혼합 현실 비디오 캡처

HoloLens 혼합 현실 비디오를 녹화하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴 사용할 수 있습니다.

### <a name="hardware-buttons-to-record-videos"></a>비디오를 녹화하는 하드웨어 단추

비디오를 녹화하는 가장 빠른 방법은 3초 카운트다운이 시작될 때까지 **볼륨을 길게** 누르고 볼륨 **다운** 단추를 동시에 누르는 것입니다. 기록을 중지하려면 두 단추를 동시에 탭합니다.

> [!NOTE]
> **볼륨을** 빠르게 누르고 동시에 **볼륨을 줄이면** 비디오를 녹화하는 대신 사진을 찍습니다.

### <a name="voice-to-record-videos"></a>비디오를 녹음하는 음성

HoloLens 2 버전 2004 이상에서는 "기록 시작"이라고 말합니다. 기록을 중지하려면 "Stop recording"라고 말합니다.

HoloLens(1세대) 또는 HoloLens 2 버전 1903에서는 "Hey Cortana, start recording"이라고 말합니다. 기록을 중지하려면 "Hey Cortana, 기록 중지"라고 말합니다.

### <a name="start-menu-to-record-videos"></a>비디오를 녹화하는 시작 메뉴

시작 제스처를 사용하여 **시작으로** 이동한 **다음, 비디오** 아이콘을 선택합니다. 캡처하려는 방향을 머리로 가리킨 [다음, 에어 탭하여](hololens2-basic-usage.md#touch-holograms-near-you) 기록을 시작합니다. 3초 카운트다운이 있고 녹음이 시작됩니다.

기록을 중지하려면 시작 제스처를 사용하고 강조 표시된 **비디오** 아이콘을 선택합니다. 비디오는 디바이스에 저장됩니다.

> [!NOTE]
> **HoloLens(1세대)에만 적용됩니다.**  
> [Windows 10 2018년 10월 업데이트](/windows/mixed-reality/release-notes-october-2018) 시작 제스처 및 Windows 단추가 HoloLens(1세대)에서 동작하는 방식을 변경합니다. 업데이트하기 전에 시작 제스처 또는 Windows 단추는 비디오 녹화를 중지합니다. 그러나 업데이트 후에 시작 제스처 또는 Windows 단추는 **시작** 메뉴(또는 몰입형 앱에 있는 경우 **빠른 작업 메뉴)를** 엽니다. 이 메뉴에서 강조 표시된 **비디오** 아이콘을 선택하여 녹화를 중지할 수 있습니다.

## <a name="share-what-you-see-in-real-time"></a>실시간으로 표시되는 내용 공유

HoloLens 보는 내용을 실시간으로 친구 및 동료와 공유할 수 있습니다. 다음과 같은 몇 가지 방법을 사용할 수 있습니다.

1. MIRACAST 지원 디바이스 또는 어댑터에 연결하여 TV에서 시청합니다.
1. [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal) 사용하여 PC에서 시청
1. Microsoft HoloLens [도우미 앱을](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 사용하여 PC에서 시청합니다.
1. [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱을 배포하면 일선 작업자가 원격 전문가에게 표시되는 내용을 스트리밍할 수 있습니다. 그런 다음 원격 전문가는 자신의 세계에 주석을 추가하거나 언어적으로 일선 작업자를 안내할 수 있습니다.

> [!NOTE]
> Windows 장치 포털 또는 Microsoft HoloLens 도우미 앱을 통해 표시되는 내용을 공유하려면 HoloLens [개발자 모드여야](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)합니다.

### <a name="stream-video-with-miracast"></a>Miracast 비디오 스트리밍

시작 제스처를 사용하여 **시작으로** 이동한 **다음, 커넥트** 아이콘을 선택합니다. 표시되는 선택기에서 연결하려는 Miracast 사용 가능한 디바이스 또는 어댑터를 선택합니다.

공유를 중지하려면 시작 제스처를 사용하고 강조 표시된 **커넥트** 아이콘을 선택합니다. 스트리밍 중이므로 아무 것도 디바이스에 저장되지 않습니다.

> [!NOTE]
> Miracast 지원은 Windows 10 2018년 10월 업데이트 HoloLens(1세대)에서 사용하도록 [설정되었습니다.](/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>Windows 장치 포털 실시간 비디오

Windows 장치 포털 통해 공유하려면 HoloLens 개발자 모드를 사용하도록 설정해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정하고 Windows 장치 포털 탐색합니다.](/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens 도우미 앱

Microsoft HoloLens 도우미 앱을 통해 공유하려면 HoloLens 개발자 모드를 사용하도록 설정해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정합니다.](/windows/mixed-reality/using-the-windows-device-portal) 그런 [다음, Microsoft HoloLens 도우미 앱을](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 다운로드하고 앱 내의 지침에 따라 HoloLens 연결합니다.

앱이 HoloLens 설정되면 앱의 주 메뉴에서 **라이브 스트림** 옵션을 선택합니다.

## <a name="view-your-mixed-reality-photos-and-videos"></a>혼합 현실 사진 및 비디오 보기

혼합 현실 사진 및 비디오는 디바이스의 "카메라 롤"에 저장됩니다. 파일 탐색기 앱을 사용하여 HoloLens 이 폴더의 내용을 찾아볼 수 있습니다(사진 **> 카메라 롤로** 이동).

HoloLens 미리 설치된 사진 앱에서 혼합 현실 사진 및 비디오를 볼 수도 있습니다. 세계에 사진을 고정하려면 사진 앱에서 선택하고 **혼합 세계 에 배치를** 선택합니다. 사진을 배치한 후 전 세계로 이동할 수 있습니다.

HoloLens 연결된 PC에서 혼합 현실 사진 및 비디오를 보거나/또는 저장하려면 [MTP를 통해](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens) [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 PC의 파일 탐색기 사용할 수 있습니다.

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>파일 탐색기 사용하여 사진, 비디오 및 파일 다운로드

다른 모바일 디바이스와 마찬가지로 HoloLens PC에 연결하여 쉽게 전송할 수 있도록 HoloLens 라이브러리(사진, 비디오, 문서)에 액세스하는 파일 탐색기 불러올 수 있습니다. 이 방법은 사용하기 쉽고 디바이스 포털 또는 Wi-Fi를 사용할 필요가 없습니다.

1. 디바이스 잠금을 해제합니다.
1. USB를 통해 디바이스를 PC에 커넥트.
1. 파일 탐색기 PC에서 열립니다.
1. 다음으로 이동합니다. 이 PC \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll
1. PC에 필요한 파일을 복사합니다.

팁:
- 파일이 표시되지 않으면 HoloLens 로그인하여 데이터에 액세스할 수 있도록 합니다.
- Documents 폴더에서 진단 파일과 같은 다른 [폴더의](hololens-diagnostic-logs.md#offline-diagnostics) 다른 파일을 얻을 수 있습니다.
- PC의 파일 탐색기 디바이스 속성을 선택하여 Windows Holographic OS 버전 번호(펌웨어 버전), 디바이스 일련 번호 및 배터리 백분율을 확인할 수 있습니다.
- 조직에서 MDM을 사용하여 [연결/AllowUSBConnection을](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 사용하지 않도록 설정하면 디바이스에 연결할 수 없습니다.

## <a name="share-your-mixed-reality-photos-and-videos"></a>혼합 현실 사진 및 비디오 공유

[Holographic 버전 21H1을 Windows](hololens-release-notes.md#windows-holographic-version-21h1)전에 혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시됩니다. 미리 보기 위의 **공유** 아이콘을 선택하여 공유 도우미를 표시합니다. 이 위치에서 해당 사진 또는 비디오를 공유하려는 끝점을 선택할 수 있습니다.

Windows Holographic 버전 21H1에서는 혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시됩니다. 미리 보기 위의 **공유** 아이콘을 선택하여 공유 도우미를 표시합니다. 이 위치에서 해당 사진 또는 비디오를 공유하려는 끝점(메일, OneDrive 등)을 선택할 수 있습니다. **설정 > 시스템 > 공유 환경** 으로 이동 하 여 HoloLens 주변 장치와 공유할 수도 있습니다. 자세한 내용은 [Windows 10에서 주변 장치와 공유 항목](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)을 참조 하세요.

> [!TIP] 
> 혼합 현실 사진과 비디오를 자동으로 업로드 하 여 OneDrive에서 혼합 된 현실 사진과 비디오를 공유할 수도 있습니다. HoloLens에서 OneDrive 앱을 열고 **개인 [Microsoft 계정](https://account.microsoft.com)**(아직 없는 경우)로 로그인 합니다. **설정** 아이콘을 선택 하 고 **카메라 업로드** 를 선택 합니다. 카메라 업로드를 켭니다. 이제 HoloLens에서 앱을 시작할 때마다 혼합 현실 사진과 비디오가 OneDrive 업로드 됩니다.

> [!NOTE]
> 개인 Microsoft 계정를 사용 하 여 OneDrive에 로그인 한 경우에만 OneDrive에서 카메라 업로드를 사용 하도록 설정할 수 있습니다. 회사 또는 학교 계정을 사용 하 여 HoloLens를 설정 하는 경우 OneDrive 앱에 개인 Microsoft 계정를 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다.

## <a name="limitations-of-mixed-reality-capture"></a>혼합 현실 캡처의 제한 사항

- 혼합 현실 캡처를 사용 하는 동안 HoloLens의 프레임 비율은 30 Hz로 반 됩니다.
- 사진/비디오 카메라가 다른 응용 프로그램에서 이미 사용 중이거나 라이브 스트리밍 또는 시스템 리소스가 부족 한 경우 사진 및 비디오의 해상도가 줄어들 수 있습니다.

### <a name="maximum-recording-length"></a>최대 기록 길이

Windows Holographic, 버전 20h2 이전의 HoloLens 2 장치에서는 장치에 기록 된 비디오가 최대 5 분 길이로 제한 되었습니다.

고객의 의견 때문에 [혼합 현실 캡처](holographic-photos-and-videos.md)의 기록 길이가 증가 했습니다. 혼합 현실 캡처는 기본적으로 더 이상 5 분으로 제한 되지 않으며, 대신 사용 가능한 디스크 공간을 기준으로 최대 기록 길이를 계산 합니다. 장치는 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 예상 하며 총 디스크 공간의 80%까지 예상 합니다.

> [!NOTE]
> 다음 중 하나가 발생 하는 경우 HoloLens는 기본 비디오 녹화 길이 (5 분)를 사용 합니다.
> - 예상 최대 기록 기간은 기본값 5 분 보다 작습니다.
> - 사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.

## <a name="default-file-format-and-resolution"></a>기본 파일 형식 및 해상도

### <a name="default-photo-format-and-resolution"></a>기본 사진 형식 및 해상도

|  디바이스  |  서식  |  확장명  |  해결 방법  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens(1세대) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>녹화 된 비디오 형식 및 해상도

| 디바이스 | 서식 | 확장명 | 해결 방법 | 속도 | 오디오 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 스테레오 |
| HoloLens(1세대) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 스테레오 |
