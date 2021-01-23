---
title: HoloLens 업데이트
description: HoloLens 빌드 번호를 확인하고, 장치 업데이트를 최신으로 유지하며, Insiders 프로그램에 참여하고, 업데이트를 롤백하는 방법을 자세히 알아보는 방법을 확인합니다.
keywords: 방법, 업데이트, 롤백, HoloLens, 빌드 확인, 빌드 번호
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283939"
---
# HoloLens 업데이트

HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다. HoloLens는 전원에 연결되어 있으며 대기 중이어도 인터넷에 연결될 때마다 시스템 업데이트를 자동으로 다운로드하여 설치합니다.

이 문서에서는 다음에 대한 HoloLens 도구를 진행합니다.

- 현재 운영 체제 버전 보기(빌드 번호)
- 업데이트 확인
- HoloLens 수동 업데이트
- 이전 업데이트로 롤백

## 운영 체제 버전 확인(빌드 번호)

설정 앱을 열고 시스템 정보(시스템 정보)를 선택하여 시스템 버전 번호(빌드 번호)를 **확인할**  >  **수 있습니다.**

## 업데이트 확인 및 수동으로 업데이트

설정에서 업데이트를 확인할 수 있습니다.  사용 가능한 업데이트를 확인하고 새 업데이트를 확인:

1. 설정 **앱을 열** 수 있습니다.
1. 보안 **Windows &**  >  **업데이트로 이동합니다.**
1. Select **Check for updates**.

업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작됩니다. 다운로드가 완료되면 지금 다시 **** 시작 단추를 선택하여 설치를 트리거합니다. 장치가 40% 미만으로 연결되어 있지 않은 경우 업데이트를 다시 시작하지 않습니다.

HoloLens에서 업데이트를 설치하는 동안 회전 기어와 진행률 표시기가 표시됩니다. 이 시간 동안 HoloLens를 끄지 않습니다. 설치가 완료되면 자동으로 다시 시작됩니다.

HoloLens는 한 번의 업데이트를 적용합니다.  HoloLens가 최신 버전보다 두 개 이상 최신 버전인 경우 업데이트 프로세스를 여러 번 실행하여 완전히 최신 버전을 제공해야 할 수 있습니다.

## 이전 버전으로 돌아가기 - HoloLens 2

경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아갈 수도 있습니다. 이 작업을 위해 고급 복구 도우미를 사용하여 HoloLens를 이전 버전으로 다시 설정할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가면 개인 파일 및 설정이 삭제됩니다.

HoloLens 2의 이전 버전으로 돌아가려면 다음 단계를 따르세요.

1. PC에 연결된 휴대폰이나 Windows 장치가 없는지 확인
1. PC에서 Microsoft Store에서 [Advanced Recovery Companion를](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 다운로드합니다.
1. [최근 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.
1. 이러한 다운로드를 마쳤을 때 파일 **탐색기**  >  **다운로드를 열 수 있습니다.** 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 추출** > **추출**을 선택하여 압축을 풉니다.
1. USB-A와 USB-C 케이블을 사용하여 HoloLens를 PC에 연결합니다. (다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)
1. Advanced Recovery Companion가 HoloLens를 자동으로 검색합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 수동 **** 패키지 선택을 선택한 다음 4단계에서 제거한 폴더에 포함된 설치 파일을 선택합니다. 확장명은 .ffu인 파일을 찾아야 합니다.
1. 소프트웨어 **설치를**선택하고 지침을 따릅니다.

## 이전 버전으로 돌아가기 - HoloLens(1세대)

경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아갈 수도 있습니다. 이 작업을 위해 Windows Device Recovery Tool을 사용하여 HoloLens를 이전 버전으로 다시 설정할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가면 개인 파일 및 설정이 삭제됩니다.

이전 버전의 HoloLens 1로 돌아가서 다음 단계를 수행합니다.

1. PC에 연결된 휴대폰이나 Windows 장치가 없는지 확인
1. PC에서 [WDRT(Windows Device Recovery Tool)를 다운로드합니다.](https://support.microsoft.com/help/12379)
1. [HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.
1. 다운로드가 완료되면 파일 **탐색기**  >  **다운로드를 열어 니다.** 방금 다운로드한 압축된 폴더를 마우스 오른쪽 **** 단추로 클릭하고 압축을 풀려면 추출을  >  **** 선택합니다.
1. HoloLens를 함께 사용한 마이크로 USB 케이블을 사용하여 PC에 연결합니다. (다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)
1. WDRT는 HoloLens를 자동으로 검색합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 수동 **** 패키지 선택을 선택하고 4단계에서 제거한 폴더에 포함된 설치 파일을 선택합니다. 확장명은 .ffu인 파일을 찾아야 합니다.
1. 소프트웨어 **설치를**선택하고 지침을 따릅니다.

> [!NOTE]
> WDRT에서 HoloLens를 검색하지 못하면 PC를 다시 시작해 보아야 합니다. 그래도 문제가 해결 되지 않으면 **장치가 감지 되지 않음**을 선택하고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.

## HoloLens의 Windows Insider 프로그램

HoloLens의 최신 기능을 보고 싶나요?  그렇다면 Windows Insider 프로그램에 참여합니다. HoloLens 소프트웨어 업데이트의 미리 보기 빌드에 대한 액세스 권한을 얻게 되기 전에 일반인에게 제공됩니다.

[Microsoft HoloLens용 Windows Insider Preview를 다운로드합니다.](hololens-insider.md)
