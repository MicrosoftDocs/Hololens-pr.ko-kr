---
title: HoloLens에서 파일 찾기 및 저장
description: HoloLens의 파일 탐색기를 사용하여 혼합 현실 장치에서 파일을 열고, 보고, 관리하는 방법을 배워야 합니다.
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283529"
---
# HoloLens에서 파일 찾기, 열기 및 저장

사진 및 비디오를 포함하여 HoloLens에서 만든 파일은 HoloLens 장치에 직접 저장됩니다. Windows 10에서 파일을 관리하는 방법과 동일한 방식으로 보고 관리합니다.

- 파일 탐색기 앱을 사용하여 로컬 폴더에 액세스
- 앱의 저장소 내에 있습니다.
- 특수 폴더(예: 비디오 또는 음악 라이브러리)에 있습니다.
- 앱 및 파일 선택기(예: OneDrive)를 포함하는 저장소 서비스 사용.
- MTP(미디어 전송 프로토콜) 지원을 사용하여 USB 케이블을 사용하여 HoloLens에 연결된 데스크톱 PC를 사용합니다.

## 파일 탐색기를 사용하여 HoloLens에서 파일 보기

> HoloLens용 [Windows 10 2018년 4월 업데이트(RS4)부터](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)모든 HoloLens 2 장치 및 HoloLens(1세대)에 적용됩니다.

HoloLens의 파일 탐색기를 사용하여 3D 개체, 문서 및 그림을 비롯한 장치의 파일을 보고 관리합니다. 시작하려면 **모든**앱   >  **파일**   >  **탐색기** 시작으로 이동하세요.

> [!TIP]
> 파일 탐색기에서 나열된 파일이 **** 없는 경우 왼쪽 위 창에서 이 장치를 선택합니다.

파일 탐색기에서 파일이 없는 경우 "최근" 필터가 활성화될 수 있습니다(시계 아이콘이 왼쪽 창에 강조 표시). 이 문제를 해결하려면 **** 왼쪽 창(시계 아이콘 아래)에서 이 장치 문서 아이콘을 선택하거나 메뉴를 열고 **이 장치를 선택합니다.**

## 사진 및 비디오 찾기 및 보기

[혼합 현실 캡처를](holographic-photos-and-videos.md) 사용하면 HoloLens에서 혼합 현실 사진 및 비디오를 촬영할 수 있습니다.  이러한 사진 및 비디오는 장치의 카메라 롤 폴더에 저장됩니다.

다음을 통해 HoloLens로 찍은 사진 및 비디오에 액세스할 수 있습니다.

- 사진 통해 카메라 [롤에 직접 액세스합니다.](holographic-photos-and-videos.md)
- OneDrive에 사진 및 비디오를 동기화하여 사진 및 비디오를 클라우드 저장소에 업로드합니다.
- [Windows Device Portal의](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)혼합 현실 캡처 페이지를 사용합니다.

### 사진 앱

앱 사진 시작 메뉴의 기본 앱 중 **** 하나에 HoloLens가 기본 제공됩니다. 앱 앱을 사용하여 [사진 보는 방법을 자세히 알아보겠습니다.](holographic-photos-and-videos.md)

Microsoft Store에서 [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 앱을 설치하여 사진을 다른 장치와 동기화할 수도 있습니다.

### OneDrive 앱

[OneDrive를](https://onedrive.live.com/) 사용하면 모든 장치 및 사용자와 사진 및 비디오를 액세스, 관리 및 공유할 수 있습니다. HoloLens에서 캡처한 사진 및 비디오에 액세스하려면 HoloLens의 Microsoft Store에서 [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 앱을 다운로드합니다. 다운로드한 후 OneDrive 앱을 열고 설정 카메라 업로드를 **선택하고**  >  **** 카메라 업로드를 **켜면 됩니다.**

### PC에 연결

HoloLens에서 [Windows 10 2018년 4월](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 업데이트 이상을 실행하는 경우 USB 케이블을 사용하여 MTP(미디어 전송 프로토콜)를 사용하여 디바이스의 사진 및 비디오를 찾아보는 방법을 통해 HoloLens를 Windows 10 PC에 연결할 수 있습니다. 디바이스에 PIN 또는 암호가 설정된 경우 파일을 찾아보기 위해 장치가 잠금 해제되어 있는지 확인해야 합니다.  

[Windows Device Portal을](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)사용하도록 설정한 경우 이를 사용하여 디바이스에 저장된 사진 및 비디오를 찾아보고 검색하고 관리할 수 있습니다.

## 앱 내의 파일에 액세스

응용 프로그램에서 장치에 파일을 저장하는 경우 해당 응용 프로그램을 사용하여 파일에 액세스할 수 있습니다.

### 다른 앱에서 파일 요청

응용 프로그램은 파일 선택기에서 파일을 저장하거나 다른 앱에서 파일을 열지 [요청할 수 있습니다.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### 알려진 폴더

HoloLens는 앱에서 액세스 [](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) 권한을 요청할 수 있는 여러 알려진 폴더를 지원합니다.

## PC에서 HoloLens 파일 보기

다른 모바일 장치와 마찬가지로 MTP(미디어 전송 프로토콜)를 사용하여 HoloLens를 데스크톱 PC에 연결하고 PC에서 파일 탐색기를 열어 쉽게 전송할 수 있도록 HoloLens 라이브러리에 액세스합니다.

PC의 파일 탐색기에서 HoloLens 파일을 확인하려면

1. HoloLens에 로그인한 다음 HoloLens와 함께 사용된 USB 케이블을 사용하여 PC에 연결합니다.

1. 파일 탐색기를 사용하여 파일을 **보거나**PC에서 파일 탐색기를 열고 디바이스로 이동합니다.

HoloLens에 대한 정보를 보려면 PC의 파일 탐색기에서 장치 이름을 마우스 오른쪽 단추로 클릭한 다음 속성을 **선택합니다.**

> [!NOTE]
> HoloLens(1세대)는 외부 하드 드라이브 또는 SD 카드에 연결할 수 없습니다.

## 클라우드에 동기화

HoloLens에서 사진 및 기타 파일을 클라우드로 동기화하려면 HoloLens에 OneDrive를 설치하고 설치합니다. OneDrive를 다운로드하기 위해 HoloLens의 Microsoft Store에서 검색합니다.

HoloLens는 앱 파일 및 데이터를 백업하지 않습니다. 따라서 중요한 정보를 OneDrive에 저장하는 것이 좋습니다. 이렇게 하면 장치를 초기화하거나 앱을 제거하면 정보가 백업됩니다.
