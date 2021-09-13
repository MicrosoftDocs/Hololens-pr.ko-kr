---
title: HoloLens의 지역화 된 버전을 설치 합니다.
description: 중국어 및 일본어 버전을 포함 하 여 HoloLens (첫 번째 gen)의 지역화 된 버전을 설치 하는 방법에 대해 알아봅니다.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033672"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>HoloLens의 지역화 된 버전 설치 (첫 번째 gen)

중국어 또는 일본어 버전의 HoloLens로 전환 하려면 wdrt (Windows Device Recovery Tool)를 사용 하 여 PC에서 언어에 대 한 빌드를 다운로드 한 다음 HoloLens에 설치 해야 합니다.

> [!IMPORTANT]
> wdrt를 사용 하 여 HoloLens의 중국어 또는 일본어 빌드를 설치 하면 개인 파일 및 설정과 같은 기존 데이터가 HoloLens에서 삭제 됩니다. 

1. PC에서 [wdrt (Windows 장치 복구 도구)](https://support.microsoft.com/help/12379)를 다운로드 하 여 설치 합니다.
1. PC에 원하는 언어 (  [중국어 간체](https://aka.ms/hololensdownload-ch) 또는 [일본어](https://aka.ms/hololensdownload-jp))의 패키지를 다운로드 합니다.
1. 다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드** 를 선택 합니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 **고 압축 풀기**  >   를 선택 하 여 압축을 풉니다.
1. 제공 된 마이크로 USB 케이블을 사용 하 여 PC에 HoloLens를 커넥트 합니다. HoloLens 연결 하는 데 다른 케이블을 사용한 경우에도이 방법이 가장 잘 작동 합니다.
1. 도구가 HoloLens를 자동으로 검색 한 후 Microsoft HoloLens 타일을 선택 합니다.
1. 다음 화면에서 **수동 패키지 선택** 을 선택   하 고 4 단계에서 압축을 푼 폴더에 있는 설치 파일을 선택 합니다. 확장명이 ".ffu" 인 파일을 찾습니다. 
1.  **소프트웨어 설치** 를 선택 하 고 지침을 따릅니다. 
1. 빌드를 설치한 후 HoloLens 설치가 자동으로 시작 됩니다. 장치에를 추가 하 고 설치 지침을 따릅니다. 

설치가 완료 되 면 **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** 로 이동 하 여 최신 미리 보기 빌드를 받도록 구성 되어 있는지 확인 합니다. 영어 미리 보기 빌드와 마찬가지로 Windows Insider Program은 최신 미리 보기 빌드를 사용 하 여 중국어 및 일본어 버전의 HoloLens 최신 버전으로 유지 합니다.

> [!NOTE]
>  
> - 설정 앱을 사용 하 여 영어, 일본어 및 중국어로 시스템 언어를 변경할 수 없습니다. 깜박이는 새 빌드는 장치 시스템 언어를 변경 하는 데 유일 하 게 지원 되는 방법입니다.
> - 화면 병음 키보드를 사용 하 여 중국어 간체 또는 일본어 텍스트를 입력할 수 있지만이 경우에는 Bluetooth 하드웨어 키보드를 사용 하 여 중국어 간체 또는 일본어 텍스트를 입력 하는 것은 지원 되지 않습니다.  그러나 중국어 또는 일본어 HoloLens에서는 계속 해 서 Bluetooth 키보드를 사용 하 여 영어로 입력할 수 있습니다. 하드웨어 키보드를 영어로 전환 하려면 ~ 키를 누릅니다.
