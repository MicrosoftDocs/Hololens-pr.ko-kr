---
title: 지역화된 버전의 HoloLens 설치
description: 중국어 및 일본어 버전을 포함하여 현지화된 버전의 홀로렌즈(1세대)를 설치하는 방법에 대해 알아보세요.
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
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439014"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>지역화된 버전의 HoloLens(1세대) 설치

HoloLens의 중국어 또는 일본어 버전으로 전환하려면 Windows Device Recovery Tool(WDRT)를 사용하여 PC에서 해당 언어의 빌드를 다운로드한 다음 HoloLens에 설치해야 합니다.

> [!IMPORTANT]
> WDRT를 사용하여 HoloLens의 중국어 또는 일본어 빌드를 설치하면 HoloLens에서 개인 파일 및 설정과 같은 기존 데이터가 삭제됩니다. 

1. PC에서 [Windows Device Recovery Tool(WDRT)](https://support.microsoft.com/help/12379)를 다운로드하여 설치합니다.
1. PC에 사용할 언어의 패키지([중국어 간체](https://aka.ms/hololensdownload-ch) 또는 [일본어](https://aka.ms/hololensdownload-jp))를 다운로드합니다.
1. 다운로드가 완료되면 **파일 탐색기** > **다운로드**를 선택합니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 추출** > **추출**을 선택하여 압축을 풉니다.
1. 함께 제공된 마이크로 USB 케이블을 사용하여 HoloLens를 PC에 연결합니다. (다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)
1. 도구에서 HoloLens를 자동으로 검색한 후 Microsoft HoloLens 타일을 선택합니다.
1. 다음 화면에서 **수동 패키지 선택** 을 선택하고 4단계에서 압축을 푼 폴더에 있는 설치 파일을 선택합니다. ". ,ffu"라는 확장명을 가진 파일을 찾습니다. 
1.  **소프트웨어 설치**를 선택하고 지침을 따릅니다. 
1. 빌드 설치가 완료되면 HoloLens 설치가 자동으로 시작됩니다. 장치에 배치하고 설치 지침을 따릅니다. 

설치를 완료한 경우 **설정** > **업데이트 및 보안** > **Windows 참가자 프로그램**으로 이동하여 최신 미리 보기 빌드를 받도록 구성되어 있는지 확인합니다. 영어 미리 보기 빌드와 마찬가지로 Windows 참가자 프로그램은 최신 미리 보기 빌드를 사용하여 중국어 및 일본어 버전의 HoloLens를 항상 최신 상태로 유지합니다.

> [!NOTE]
>  
> - 설정 앱을 사용하여 영어, 일본어, 중국어 간의 시스템 언어를 변경할 수 없습니다. 새 빌드를 플래시하는 것이 장치 시스템 언어를 변경하는 유일한 지원되는 방법입니다.
> - 화상 Pinyin 키보드를 사용하여 중국어 간체 또는 일본어 텍스트를 입력할 수 있지만 이번에는 Bluetooth 하드웨어 키보드를 사용하여 중국어 간체 또는 일본어 텍스트를 입력하는 것이 지원되지 않습니다.  그러나 중국어 또는 일본어 HoloLens에서는 Bluetooth 키보드를 사용하여 영어로 입력할 수 있습니다(영어를 입력하도록 하드웨어 키보드를 전환하려면 ~ 키를 누릅니다).
