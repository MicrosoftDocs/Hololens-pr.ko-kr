---
title: 지역화된 버전의 HoloLens 설치
description: 중국어 및 일본어 버전을 포함하여 지역화된 버전의 HoloLens(1세대)를 설치하는 방법을 알아봅니다.
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
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661815"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>지역화된 버전의 HoloLens(1세대) 설치

중국어 또는 일본어 버전의 HoloLens 전환하려면 WDRT(Windows Device Recovery Tool)를 사용하여 PC에서 언어에 대한 빌드를 다운로드한 다음 HoloLens 설치해야 합니다.

> [!IMPORTANT]
> WDRT를 사용하여 HoloLens 중국어 또는 일본어 빌드를 설치하면 HoloLens 개인 파일 및 설정과 같은 기존 데이터가 삭제됩니다. 

1. PC에서 [WDRT(Windows Device Recovery Tool)](https://support.microsoft.com/help/12379)를 다운로드하여 설치합니다.
1. PC에 원하는  [언어(중국어 간체](https://aka.ms/hololensdownload-ch) 또는 [일본어)에](https://aka.ms/hololensdownload-jp)대한 패키지를 다운로드합니다.
1. 다운로드가 완료되면 다운로드 **파일 탐색기**  >  선택합니다. 방금 다운로드한 압축된 폴더를 마우스 오른쪽 단추로 클릭하고 **압축을** 풀려면 모두  >  **추출을** 선택합니다.
1. 제공된 마이크로 USB 케이블을 사용하여 PC에 HoloLens 커넥트. (다른 케이블을 사용하여 HoloLens 연결한 경우에도 가장 잘 작동합니다.)
1. 도구에서 HoloLens 자동으로 검색한 후 Microsoft HoloLens 타일을 선택합니다.
1. 다음 화면에서 수동 **패키지 선택을**   선택하고 4단계에서 압축을 풀 폴더에 있는 설치 파일을 선택합니다. (확장명 ".ffu"가 있는 파일을 찾습니다.) 
1.  **소프트웨어 설치를** 선택하고 지침을 따릅니다. 
1. 빌드가 설치된 후 HoloLens 설치가 자동으로 시작됩니다. 디바이스를 켜고 설정 지침을 따릅니다. 

설치가 완료되면 **설정** 업데이트 & 보안 Windows 참가자 프로그램 로 이동하여 최신 미리 보기  >    >  빌드를 받도록 구성되었는지 확인합니다. 영어 미리 보기 빌드와 마찬가지로 Windows 참가자 프로그램 최신 미리 보기 빌드를 사용하여 HoloLens 중국어 및 일본어 버전을 최신 상태로 유지합니다.

> [!NOTE]
>  
> - 설정 앱을 사용하여 영어, 일본어 및 중국어 간의 시스템 언어를 변경할 수 없습니다. 디바이스 시스템 언어를 변경하는 유일한 방법은 새 빌드를 플래시하는 것입니다.
> - 화면의 Pinyin 키보드를 사용하여 중국어 간체 또는 일본어 텍스트를 입력할 수 있지만, Bluetooth 하드웨어 키보드를 사용하여 중국어 간체 또는 일본어 텍스트를 입력하는 것은 현재 지원되지 않습니다.  그러나 중국어 또는 일본어 HoloLens 계속해서 Bluetooth 키보드를 사용하여 영어로 입력할 수 있습니다(하드웨어 키보드를 영어로 입력하도록 토글하려면 ~ 키를 누를 수 있습니다).
