---
title: 혼합 현실 사진 및 동영상 캡처 및 관리
description: HoloLens를 사용 하 여 혼합 현실 사진과 비디오를 캡처, 보기 및 공유 하는 방법에 대해 알아봅니다.
keywords: hololens, 사진, 비디오, 캡처, mrc, 혼합 현실 캡처, 사진, 카메라, 스트림, livestream, 데모
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
ms.openlocfilehash: 1be4e80c040d5b8e451c07fb931c7c7fb8d5ab48
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829108"
---
# 혼합 현실 사진 및 비디오 만들기

HoloLens를 통해 사용자는 디지털 세계와 실제 세계를 함께 활용할 수 있습니다.  MRC (혼합 현실 캡처)를 사용 하 여 해당 환경을 사진 또는 비디오로 캡처 하거나 다른 사용자와 실시간으로 공유할 수 있습니다.

Mixed reality 캡처는 첫 번째 사용자의 보기를 사용 하 여 다른 사용자가 홀로그램 볼 수 있습니다. 세 번째 사용자의 관점에서는 [spectator 보기](https://docs.microsoft.com/windows/mixed-reality/spectator-view)를 사용 합니다. Spectator view는 데모에 특히 유용 합니다.

친구와 동료 간에 비디오를 공유 하는 것은 재미 있지만, 비디오를 통해 다른 사용자가 앱을 사용 하거나 앱과 환경에 문제를 교환할 수 있습니다.

> [!NOTE]
> Mixed reality 캡처 환경을 시작할 수 없고 HoloLens가 작업 장치인 경우에는 시스템 관리자에 게 문의 하세요. 카메라에 대 한 액세스는 회사 정책을 통해 제한할 수 있습니다.

## Mixed reality 사진 캡처

HoloLens에서 혼합 현실 사진을 촬영 하는 방법에는 여러 가지가 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.

### 사진을 촬영 하는 하드웨어 단추

현재 보기의 빠른 사진을 찍으려면 볼륨을 위로 길게 누르고 볼륨을 아래로 단추를 누릅니다.  이는 HoloLens 버전의 스크린샷 또는 인쇄 화면 처럼 비트입니다.

- [HoloLens 2의 단추 위치](hololens2-hardware.md)
- [HoloLens의 단추 위치 (첫번째 gen)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> **볼륨** 을 길게 누르고 3 초간 **볼륨 작게** 단추를 누르면 사진을 촬영 하는 대신 비디오 녹화가 시작 됩니다. 녹화를 중지 하려면 볼륨을 **위로** 또는 **볼륨 아래로** 단추를 동시에 탭 합니다.

### 사진을 촬영 하는 음성 명령

HoloLens 2, 버전 2004 (이상)에서 "사진 찍기" 라고 말합니다.

HoloLens (첫번째 gen) 또는 HoloLens 2, 버전 1903, "안녕 코타 나, 사진 찍기" 라고 말합니다.

### 사진을 찍을 시작 메뉴

시작 제스처를 사용 하 여 **시작**으로 이동한 다음 **카메라** 아이콘을 선택 합니다.

캡처하려는 방향으로 원하는 위치를 가리킨 다음 [air을 탭](hololens2-basic-usage.md#touch-holograms-near-you) 하 여 사진을 찍습니다. 계속 해 서 air을 탭 하 여 추가 사진을 캡처할 수 있습니다. 캡처한 사진은 모두 장치에 저장 됩니다.

시작 제스처를 다시 사용 하 여 사진 캡처를 종료 합니다.  

## 혼합 현실 비디오 캡처

여러 가지 방법으로 HoloLens에 혼합 현실 비디오를 녹화할 수 있습니다. 하드웨어 단추, 음성 또는 시작 메뉴를 사용할 수 있습니다.

### 비디오 녹화를 위한 하드웨어 단추

비디오를 녹화 하는 가장 빠른 방법은 3 초 카운트다운이 시작 될 때까지 **볼륨** 을 길게 누르고 **볼륨 다운** 단추를 동시에 누르고 있는 것입니다. 녹화를 중지 하려면 두 단추를 동시에 탭 합니다.

> [!NOTE]
> 동시에 **볼륨** 을 길게 누르고 **볼륨 아래로** 단추를 누르면 비디오가 녹화 되는 것이 아니라 사진이 찍습니다.

### 음성에서 비디오 녹화

HoloLens 2, 버전 2004 (이상)에서 "기록 시작" 이라고 말합니다. 녹음을 중지 하려면 "기록 중지" 라고 말합니다.

HoloLens (첫번째 gen) 또는 HoloLens 2, 버전 1903, "안녕 코타 나 기록 시작" 이라고 말합니다. 녹음을 중지 하려면 "안녕 코타 나 기록 중지" 라고 말합니다.

### 비디오 녹화를 위한 시작 메뉴

시작 제스처를 사용 하 여 **시작**으로 이동한 다음 **비디오** 아이콘을 선택 합니다. 캡처하려는 방향으로 원하는 위치를 가리킨 다음 [air을 탭](hololens2-basic-usage.md#touch-holograms-near-you) 하 여 녹화를 시작 합니다. 3 초 동안 기록이 시작 됩니다.

녹화를 중지 하려면 시작 제스처를 사용 하 여 강조 표시 된 **비디오** 아이콘을 선택 합니다. 비디오가 장치에 저장 됩니다.

> [!NOTE]
> **HoloLens에 적용 (첫번째 gen)**  
> [Windows 10 10 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 는 HoloLens (1 회 gen)에서 시작 제스처 및 Windows 단추가 작동 하는 방법을 변경 합니다. 업데이트 하기 전에 시작 제스처 또는 Windows 단추를 클릭 하면 비디오 녹화가 중지 됩니다. 그러나 업데이트 후 시작 제스처 또는 Windows 단추는 **시작** 메뉴 (또는 몰입 형 앱을 사용할 경우 **빠른 작업 메뉴** )를 열고 강조 표시 된 **비디오** 아이콘을 선택 하 여 녹화를 중지할 수 있습니다.

## 실시간으로 표시 되는 내용 공유

친구 및 동료와 동시에 볼 수 있습니다. 사용할 수 있는 몇 가지 방법이 있습니다.

1. TV를 시청 하기 위해 Miracast 지원 장치나 어댑터에 연결 합니다.
1. [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 을 사용 하 여 PC에서 시청
1. [Microsoft HoloLens 도우미 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 사용 하 여 PC 시청
1. 사용자가 원격 전문가에 게 표시 되는 내용을 스트리밍할 수 있도록 하는 [Microsoft Dynamics 365 원격 지원](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 앱을 배포 합니다. 그런 다음 원격 전문가는 프런트 라인의 작업자 구두로를 안내 하거나, 전세계에 주석을 달아 지 게 할 수 있습니다.

> [!NOTE]
> Windows Device Portal 또는 Microsoft HoloLens 도우미 앱을 통해 표시 되는 내용을 공유 하려면 HoloLens [가 개발자 모드](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)여야 합니다.

### Miracast를 사용 하 여 비디오 스트리밍

시작 제스처를 사용 하 여 **시작**으로 이동한 다음 **연결** 아이콘을 선택 합니다. 표시 되는 선택기에서 연결 하려는 Miracast 사용 장치 또는 어댑터를 선택 합니다.

공유를 중지 하려면 시작 제스처를 사용 하 여 강조 표시 된 **연결** 아이콘을 선택 합니다. 스트리밍 중이기 때문에 장치에 아무 것도 저장 되지 않습니다.

> [!NOTE]
> Miracast 지원은 [Windows 10 10 월 2018 업데이트로](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)시작 되는 HoloLens (1 회 gen)에서 사용 하도록 설정 되었습니다.

### Windows Device Portal을 사용한 실시간 비디오

Windows 디바이스 포털을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정 하 고 Windows Device Portal을 탐색](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다.

### Microsoft HoloLens 도우미 앱

Microsoft HoloLens 도우미 앱을 통해 공유 하려면 HoloLens에서 개발자 모드를 사용 하도록 설정 해야 하므로 개발자 설명서의 지침에 따라 [개발자 모드를 설정](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)합니다. 그런 다음 [Microsoft hololens 도우미 앱](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 을 다운로드 하 고 앱 내의 지침에 따라 HoloLens에 연결 합니다.

HoloLens를 사용 하 여 앱을 설정한 후에는 앱의 주 메뉴에서 **라이브 스트림** 옵션을 선택 합니다.

## 혼합 현실 사진 및 동영상 보기

혼합 현실 사진과 비디오는 장치의 "카메라 롤"에 저장 됩니다. 파일 탐색기 앱을 사용 하 여 HoloLens에서이 폴더의 콘텐츠를 탐색할 수 있습니다 (그림 > 카메라 앨범으로 이동).

또한 HoloLens에 사전 설치 되어 있는 사진 앱에서 혼합 현실 사진과 비디오를 볼 수 있습니다. 세상에서 사진을 고정 하려면 사진 앱에서 선택 하 고 **혼합 세계에서 배치**를 선택 합니다. 사진을 배치한 후에는 전세계에 이동할 수 있습니다.

HoloLens에 연결 된 PC에서 혼합 현실 사진과 비디오를 보고/또는 저장 하려면 MTP를 통해 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 또는 [PC의 파일 탐색기](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)를 사용할 수 있습니다.

## 혼합 현실 사진 및 동영상 공유

혼합 현실 사진 또는 비디오를 캡처한 후 미리 보기가 표시 됩니다. 미리 보기 위의 **공유** 아이콘을 선택 하 여 공유 도우미를 가져옵니다. 여기서 해당 사진이 나 비디오를 공유할 끝점을 선택할 수 있습니다.

혼합 현실 사진과 비디오를 자동으로 업로드 하 여 OneDrive에서 혼합 현실 사진과 비디오를 공유할 수도 있습니다. HoloLens에서 OneDrive 앱을 열고 아직 계정이 없는 경우 개인 [Microsoft 계정](https://account.microsoft.com) 으로 로그인 합니다. **설정** 아이콘을 선택 하 고 **카메라 업로드**를 선택 합니다. 카메라 업로드를 켭니다. 이제 HoloLens에서 앱을 시작할 때마다 혼합 현실 사진과 비디오가 OneDrive에 업로드 됩니다.

> [!NOTE]
> 개인 Microsoft 계정으로 OneDrive에 로그인 한 경우 OneDrive 에서만 카메라를 업로드 하도록 설정할 수 있습니다. 회사 또는 학교 계정을 사용 하 여 HoloLens를 설정 하는 경우 OneDrive 앱에 개인 Microsoft 계정을 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다.

## Mixed reality 캡처의 제한 사항

- Mixed reality 캡처를 사용 하는 동안 HoloLens의 프레임 속도는 halved로 최대 30hz입니다.
- 비디오의 최대 길이는 5 분입니다.
- 사진/비디오 카메라가 이미 다른 응용 프로그램에서 사용 중이거나 라이브 스트리밍 중 이거나 시스템 리소스가 부족 한 경우 사진 및 비디오의 해상도를 줄일 수 있습니다.

## 기본 파일 형식 및 해상도

### 기본 사진 형식 및 해상도

|  장치  |  형식  |  확장  |  해상도  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (첫번째 gen) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### 녹화 된 비디오 형식 및 해상도

| 장치 | 형식 | 확장 | 해상도 | 속력과 | Audio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 스테레오 |
| HoloLens (첫번째 gen) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 스테레오 |
