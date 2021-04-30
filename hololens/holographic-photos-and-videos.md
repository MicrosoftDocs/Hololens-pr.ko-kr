---
title: 혼합 현실 사진 및 비디오 캡처, 기록 및 공유
description: HoloLens mixed reality 장치를 사용 하 여 현실 사진과 비디오를 캡처, 기록 및 확인 하는 방법을 알아봅니다. Miracast 또는 수집 된 파일을 통해 공유 하는 방법에 대해 알아봅니다.
keywords: hololens, 사진, 비디오, 캡처, mrc, 혼합 현실 캡처, 사진, 카메라, miracast, 스트림, 라이브 스트림, 데모, 레코드
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
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309181"
---
# <a name="create-mixed-reality-photos-and-videos"></a>혼합 현실 사진 및 비디오 만들기

HoloLens는 사용자에 게 실제 세계와 세계를 혼합 하는 환경을 제공 합니다.  혼합 현실 캡처 (MRC)를 사용 하면 해당 환경을 사진 또는 비디오로 캡처하거나 다른 사용자와 실시간으로 볼 수 있습니다.

혼합 현실 캡처는 첫 번째 사람의 관점을 사용 하 여 다른 사람들이 볼 때 holograms를 볼 수 있도록 합니다. 세 번째 사용자 관점은 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)를 사용 합니다. Spectator view는 데모에 특히 유용 합니다.

친구나 동료 간에 비디오를 공유 하는 것은 재미 있지만 비디오를 사용 하면 다른 사용자가 앱을 사용 하거나 앱과 환경에 문제를 전달 하는 데 도움이 될 수도 있습니다.

> [!NOTE]
> 혼합 현실 캡처 환경을 시작할 수 없고 HoloLens가 작업 장치인 경우 시스템 관리자에 게 문의 하세요. 회사 정책을 통해 카메라에 대 한 액세스를 제한할 수 있습니다.

## <a name="capture-a-mixed-reality-photo"></a>혼합 현실 사진 캡처

HoloLens에서 혼합 현실 사진을 사용 하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.

### <a name="hardware-buttons-to-take-photos"></a>사진을 찍을 하드웨어 단추

현재 보기에 대 한 빠른 사진을 만들려면 볼륨 위로 및 볼륨 아래로 단추를 동시에 누릅니다.  이는 스크린샷 또는 인쇄 화면의 HoloLens 버전과 약간 유사 합니다.

- [HoloLens 2의 단추 위치](hololens2-hardware.md)
- [HoloLens의 단추 위치 (첫 번째 gen)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> **볼륨 위로** 및 **볼륨 작게** 단추를 세 초 동안 보관 하면 사진을 촬영 하는 대신 비디오 기록을 시작 합니다. 기록을 중지 하려면 **볼륨 위로** 및 **볼륨 아래로** 단추를 동시에 누릅니다.

### <a name="voice-commands-to-take-photos"></a>사진을 찍을 음성 명령

HoloLens 2, 버전 2004 (이상)에서 "그림을 찍습니다." 라고 말합니다.

HoloLens (첫 번째 gen) 또는 HoloLens 2, 버전 1903, 예: "Cortana, 사진 찍기"

### <a name="start-menu-to-take-photos"></a>사진을 가져오는 시작 메뉴

시작 제스처를 사용 하 여 **시작** 으로 이동한 다음 **카메라** 아이콘을 선택 합니다.

캡처 하려는 방향으로 헤드를 가리킨 다음, [공중 탭](hololens2-basic-usage.md#touch-holograms-near-you) 을 클릭 하 여 사진을 촬영 합니다. 계속 해 서 더 많은 사진을 길게 탭 하 고 캡처할 수 있습니다. 캡처한 사진은 모두 장치에 저장 됩니다.

시작 제스처를 다시 사용 하 여 사진 캡처를 종료 합니다.  

## <a name="capture-a-mixed-reality-video"></a>혼합 현실 비디오 캡처

HoloLens에서 혼합 현실 비디오를 기록 하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.

### <a name="hardware-buttons-to-record-videos"></a>비디오를 기록 하는 하드웨어 단추

비디오를 기록 하는 가장 빠른 방법은 3 초 카운트다운이 시작 될 때까지 **볼륨** 을 동시에 누르고 **볼륨을 아래로 이동** 하는 것입니다. 기록을 중지 하려면 두 단추를 동시에 누릅니다.

> [!NOTE]
> **볼륨 위로** 및 **볼륨 아래로** 단추를 동시에 빠르게 누르면 비디오를 기록 하는 대신 사진이 사용 됩니다.

### <a name="voice-to-record-videos"></a>음성 녹음 비디오

HoloLens 2, 버전 2004 (이상)에서 "기록 시작"을 말합니다. 기록을 중지 하려면 "기록 중지" 라고 표시 합니다.

HoloLens (첫 번째 gen) 또는 HoloLens 2 버전 1903, 예: "안녕하세요 Cortana, 녹화 시작" 기록을 중지 하려면 "안녕 코타 나 녹음 중지" 라고 표시 합니다.

### <a name="start-menu-to-record-videos"></a>비디오를 기록 하는 시작 메뉴

시작 제스처를 사용 하 여 **시작** 으로 이동한 다음 **비디오** 아이콘을 선택 합니다. 캡처 하려는 방향으로 헤드를 가리킨 다음, [공중 탭](hololens2-basic-usage.md#touch-holograms-near-you) 하 여 기록을 시작 합니다. 세 초 카운트다운이 발생 하 고 기록이 시작 됩니다.

기록을 중지 하려면 시작 제스처를 사용 하 고 강조 표시 된 **비디오** 아이콘을 선택 합니다. 비디오는 장치에 저장 됩니다.

> [!NOTE]
> **HoloLens (첫 번째 gen)에만 적용 됩니다.**  
> [Windows 10 10 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 는 HoloLens (첫 번째 gen)에서 시작 제스처와 Windows 단추가 동작 하는 방식을 변경 합니다. 업데이트 하기 전에 시작 제스처 또는 Windows 단추가 비디오 녹화를 중지 합니다. 그러나 업데이트 후 시작 제스처 또는 Windows 단추를 클릭 하 여 **시작** 메뉴 (또는 몰입 형 앱에 있는 경우 **빠른 작업 메뉴** )를 열면 강조 표시 된 **비디오** 아이콘을 선택 하 여 기록을 중지할 수 있습니다.

## <a name="share-what-you-see-in-real-time"></a>실시간으로 표시 되는 항목 공유

HoloLens에 표시 되는 내용을 실시간으로 친구와 동료와 공유할 수 있습니다. 사용할 수 있는 몇 가지 방법이 있습니다.

1. TV를 시청 하려면 Miracast 사용 장치 또는 어댑터에 연결 합니다.
1. [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 을 사용 하 여 PC 시청
1. [Microsoft HoloLens 부록 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 사용 하 여 PC를 시청 하세요.
1. [Microsoft Dynamics 365 원격 지원](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱 배포 .이 앱을 통해 프런트 라인 작업자는 원격 전문가에 게 표시 되는 내용을 스트리밍할 수 있습니다. 그러면 원격 전문가는 전 세계에 주석을 추가 하 여 프런트 라인 작업자 구두로을 안내할 수 있습니다.

> [!NOTE]
> Windows 장치 포털 또는 Microsoft HoloLens 부록 앱을 통해 표시 되는 내용을 공유 하려면 HoloLens [가 개발자 모드](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)여야 합니다.

### <a name="stream-video-with-miracast"></a>Miracast를 사용 하 여 비디오 스트리밍

시작 제스처를 사용 하 여 **시작** 으로 이동한 다음 **연결** 아이콘을 선택 합니다. 표시 되는 선택에서 연결 하려는 Miracast 사용 장치 또는 어댑터를 선택 합니다.

공유를 중지 하려면 시작 제스처를 사용 하 고 강조 표시 된 **연결** 아이콘을 선택 합니다. 스트리밍 중이기 때문에 장치에 아무 것도 저장 되지 않습니다.

> [!NOTE]
> Miracast 지원은 [Windows 10 10 월 2018 업데이트로](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)시작 하는 HoloLens (1 세대)에서 사용 하도록 설정 되었습니다.

### <a name="real-time-video-with-windows-device-portal"></a>Windows 장치 포털을 사용한 실시간 비디오

Windows 장치 포털을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정 하 고 Windows Device Portal로 이동](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다.

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens 부록 앱

Microsoft HoloLens 부록 앱을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다. 그런 다음 [Microsoft hololens 부록 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 다운로드 하 고 앱 내의 지침에 따라 HoloLens에 연결 합니다.

앱이 HoloLens로 설정 되 면 앱의 주 메뉴에서 **라이브 스트림** 옵션을 선택 합니다.

## <a name="view-your-mixed-reality-photos-and-videos"></a>혼합 현실 사진 및 비디오 보기

혼합 현실 사진과 비디오는 장치의 "카메라 롤"에 저장 됩니다. 파일 탐색기 앱 (사진 > 카메라 롤로 이동)을 사용 하 여 HoloLens에서이 폴더의 내용을 찾아볼 수 있습니다.

또한 HoloLens에 미리 설치 되어 있는 사진 앱에서 혼합 현실 사진과 비디오를 볼 수 있습니다. 전 세계에 사진을 고정 하려면 사진 앱에서 해당 사진을 선택 하 고 **혼합 세계에 있는 장소** 를 선택 합니다. 배치 된 후 전 세계에 사진을 이동할 수 있습니다.

HoloLens에 연결 된 PC에서 혼합 현실 사진과 비디오를 보거나 저장 하려면 MTP를 통해 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 [Pc의 파일 탐색기](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)를 사용할 수 있습니다.

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>파일 탐색기를 사용 하 여 사진, 동영상 및 파일 가져오기

다른 모바일 장치와 마찬가지로 HoloLens를 PC에 연결 하 여 파일 탐색기에서 HoloLens 라이브러리 (사진, 동영상, 문서)에 액세스 하 여 쉽게 전송할 수 있습니다. 이 방법은 사용 하기 쉬우며 장치 포털 또는 Wi-fi를 사용할 필요가 없습니다.

1. 장치를 잠금 해제 합니다.
1. USB를 통해 PC에 장치를 연결 합니다.
1. PC에서 파일 탐색기가 열립니다.
1. 이동:이 PC \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll
1. 필요한 모든 파일을 PC에 복사 합니다.

팁:
- 파일이 표시 되지 않는 경우 HoloLens에 로그인 하 여 데이터에 액세스할 수 있는지 확인 하세요.
- 문서 폴더에서 [진단 파일](hololens-diagnostic-logs.md#offline-diagnostics) 같은 다른 폴더의 다른 파일을 가져올 수 있습니다.
- PC의 파일 탐색기에서 장치 속성을 선택 하 여 Windows Holographic OS 버전 번호 (펌웨어 버전), 장치 일련 번호 및 배터리 비율을 확인할 수 있습니다.
- 조직에서 MDM을 사용 하 여 [연결/](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) a c c 연결을 사용 하지 않도록 설정한 경우 장치에 연결할 수 없게 됩니다.

## <a name="share-your-mixed-reality-photos-and-videos"></a>혼합 현실 사진과 비디오 공유

혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시 됩니다. 미리 보기 위에 있는 **공유** 아이콘을 선택 하 여 공유 길잡이를 엽니다. 여기에서 해당 사진 또는 비디오를 공유할 끝점을 선택할 수 있습니다.

혼합 현실 사진과 비디오를 자동으로 업로드 하 여 OneDrive에서 혼합 된 현실 사진과 비디오를 공유할 수도 있습니다. HoloLens에서 OneDrive 앱을 열고 아직 개인 [Microsoft 계정](https://account.microsoft.com) 로그인 합니다. **설정** 아이콘을 선택 하 고 **카메라 업로드** 를 선택 합니다. 카메라 업로드를 켭니다. 이제 HoloLens에서 앱을 시작할 때마다 혼합 현실 사진과 비디오가 OneDrive에 업로드 됩니다.

> [!NOTE]
> Onedrive에 개인 Microsoft 계정 로그인 하는 경우에만 OneDrive에서 카메라 업로드를 사용 하도록 설정할 수 있습니다. 회사 또는 학교 계정을 사용 하 여 HoloLens를 설정 하는 경우 OneDrive 앱에서 개인 Microsoft 계정을 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다.

## <a name="limitations-of-mixed-reality-capture"></a>혼합 현실 캡처의 제한 사항

- 혼합 현실 캡처를 사용 하는 동안 HoloLens의 프레임 속도가 30 Hz로 반 됩니다.
- 사진/비디오 카메라가 다른 응용 프로그램에서 이미 사용 중이거나 라이브 스트리밍 또는 시스템 리소스가 부족 한 경우 사진 및 비디오의 해상도가 줄어들 수 있습니다.

### <a name="maximum-recording-length"></a>최대 기록 길이

Windows Holographic 이전에 HoloLens 2 장치에서 장치에 기록 된 버전 20H2 비디오는 5 분의 최대 길이로 제한 되었습니다.

고객의 의견 때문에 [혼합 현실 캡처](holographic-photos-and-videos.md)의 녹화 길이가 증가 했습니다. 혼합 현실 캡처는 기본적으로 더 이상 5 분으로 제한 되지 않으며, 대신 사용 가능한 디스크 공간을 기준으로 최대 기록 길이를 계산 합니다. 장치는 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 예상 하며 총 디스크 공간의 80%까지 예상 합니다.

> [!NOTE]
> 다음 중 하나가 발생 하는 경우 HoloLens는 기본 비디오 녹화 길이 (5 분)를 사용 합니다.
> - 예상 최대 기록 기간은 기본값 5 분 보다 작습니다.
> - 사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.

## <a name="default-file-format-and-resolution"></a>기본 파일 형식 및 해상도

### <a name="default-photo-format-and-resolution"></a>기본 사진 형식 및 해상도

|  디바이스  |  서식  |  내선 번호  |  해결 방법  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens(1세대) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>녹화 된 비디오 형식 및 해상도

| 디바이스 | 서식 | 내선 번호 | 해결 방법 | 속도 | 오디오 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 스테레오 |
| HoloLens(1세대) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 스테레오 |
