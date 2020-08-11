---
title: HoloLens에서 파일 찾기 및 저장
description: HoloLens의 파일 탐색기를 사용 하 여 장치에서 파일 보기 및 관리
keywords: 방법, 파일 선택기, 파일, 사진, 비디오, 사진, OneDrive, 저장소, 파일 탐색기, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fb3287f0a074eddeac0c7ee2871e289b93eafcac
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919129"
---
# HoloLens에서 파일 찾기, 열기 및 저장

HoloLens에서 만든 사진 및 비디오 등의 파일은 HoloLens 장치에 직접 저장 됩니다. Windows 10에서 파일을 관리 하는 것과 동일한 방법으로 보기 및 관리:

- 파일 탐색기 앱을 사용 하 여 로컬 폴더에 액세스
- 앱 저장소 내
- 비디오 또는 음악 라이브러리와 같은 특수 폴더
- 앱과 파일 선택 (예: OneDrive)이 포함 된 저장소 서비스를 사용 합니다.
- MTP (미디어 전송 프로토콜) 지원을 사용 하 여 HoloLens에 연결 된 데스크톱 PC를 USB 케이블로 사용 합니다.

## 파일 탐색기를 사용 하 여 HoloLens에서 파일 보기

> [Hololens에 대 한 Windows 10 4 월 2018 업데이트 (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)의 모든 HoloLens 2 장치 및 HoloLens (1 회 gen)에 적용 됩니다.

HoloLens의 파일 탐색기를 사용 하 여 3D 개체, 문서, 그림을 비롯 한 장치에서 파일을 보고 관리할 수 있습니다. **Start**   >  시작 하려면**모든 앱**   >  **파일 탐색기** 시작으로 이동 합니다.

> [!TIP]
> 파일 탐색기에 파일이 나열 되어 있지 않으면 왼쪽 위 창에서 **이 장치** 를 선택 합니다.

파일 탐색기에 파일이 표시 되지 않는 경우 "최근" 필터가 활성 상태일 수 있습니다 (시계 아이콘이 왼쪽 창에서 강조 표시 됨). 이 문제를 해결 하려면 왼쪽 창에서 **이 장치** 문서 아이콘 (시계 아이콘 아래)을 선택 하거나 메뉴를 열고 **이 장치**를 선택 합니다.

## 사진 및 동영상 찾기 및 보기

[Mixed reality 캡처](holographic-photos-and-videos.md) 를 사용 하 여 HoloLens에서 실제로 사용할 수 있는 사진 및 동영상을 혼합할 수 있습니다.  이러한 사진과 비디오는 장치의 카메라 앨범 폴더에 저장 됩니다.

아래와 같은 방법으로 HoloLens를 사용 하 여 찍은 사진과 비디오에 액세스할 수 있습니다.

- [사진 앱](holographic-photos-and-videos.md)을 통해 카메라 롤에 직접 액세스 합니다.
- 사진과 비디오를 OneDrive에 동기화 하 여 클라우드 저장소에 사진 및 비디오를 업로드 합니다.
- [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)의 Mixed Reality 캡처 페이지를 사용 합니다.

### 사진 앱

사진 앱은 **시작** 메뉴의 기본 앱 중 하나 이며, HoloLens를 사용 하 여 기본적으로 제공 됩니다. [사진 앱을 사용 하 여 콘텐츠를 보는](holographic-photos-and-videos.md)방법에 대해 자세히 알아보세요.

Microsoft Store에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 설치 하 여 사진을 다른 장치에 동기화 할 수도 있습니다.

### OneDrive 앱

[OneDrive](https://onedrive.live.com/) 를 사용 하면 모든 장치 및 사용자와 함께 사진과 비디오에 액세스 하 고, 관리 하 고, 공유할 수 있습니다. HoloLens에서 캡처한 사진과 비디오에 액세스 하려면 HoloLens의 Microsoft 스토어에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 다운로드 하세요. 다운로드 되 면 OneDrive 앱을 열고 **설정**  >  **카메라 업로드**를 선택 하 고 **카메라 업로드**를 켭니다.

### PC에 연결

HoloLens에서 [windows 10 4 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 이상을 실행 하는 경우 USB 케이블을 사용 하 여 WINDOWS 10 PC에 hololens를 연결 하 고 MTP (미디어 전송 프로토콜)를 사용 하 여 디바이스의 사진 및 비디오를 찾아볼 수 있습니다. 장치에 PIN 또는 암호가 설정 되어 있는 경우 장치를 잠금 해제 하 여 파일을 검색 해야 합니다.  

[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용 하도록 설정한 경우 장치에 저장 된 사진과 비디오를 찾아보고 검색 하 고 관리 하는 데 사용할 수 있습니다.

## 앱 내에서 파일에 액세스

응용 프로그램이 장치에 파일을 저장 하는 경우 해당 응용 프로그램을 사용 하 여 액세스할 수 있습니다.

### 다른 앱에서 파일 요청

파일 [선택기](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)를 사용 하 여 응용 프로그램에서 파일을 저장 하거나 다른 앱에서 파일을 열 수 있습니다.

### 알려진 폴더

HoloLens는 앱이 액세스 권한을 요청할 수 있는 여러 개의 [알려진 폴더](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) 를 지원 합니다.

## PC에서 HoloLens 파일 보기

다른 모바일 장치와 유사 하 게, MTP (미디어 전송 프로토콜)를 사용 하 여 HoloLens를 데스크톱 PC에 연결 하 고 PC의 파일 탐색기를 열어 사용자 환경 전송을 위해 HoloLens 라이브러리에 액세스 합니다.

PC의 파일 탐색기에서 HoloLens 파일을 보려면 다음을 수행 합니다.

1. HoloLens에 로그인 한 다음 HoloLens와 함께 제공 되는 USB 케이블을 사용 하 여 PC에 연결 합니다.

1. **장치 열기를 선택 하 여 파일 탐색기를 사용 하 여 파일을 보거나**PC의 파일 탐색기를 열고 장치로 이동 합니다.

HoloLens에 대 한 정보를 보려면 PC의 파일 탐색기에서 장치 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 선택 합니다.

> [!NOTE]
> HoloLens (첫번째 gen)는 외부 하드 드라이브 또는 SD 카드에 대 한 연결을 지원 하지 않습니다.

## 클라우드와 동기화

HoloLens의 사진 및 기타 파일을 클라우드와 동기화 하려면 HoloLens에 OneDrive를 설치 하 고 설정 합니다. OneDrive를 다운로드 하려면 HoloLens의 Microsoft Store에서 검색 하세요.

HoloLens는 앱 파일 및 데이터를 백업 하지 않으므로 중요 한 내용을 OneDrive에 저장 하는 것이 좋습니다. 이렇게 하면 장치를 다시 설정 하거나 앱을 제거 하면 정보가 백업 됩니다.
