---
title: HoloLens 업데이트
description: HoloLens의 빌드 번호, 업데이트, 롤백 업데이트를 확인 합니다.
keywords: 방법, 업데이트, 롤백, HoloLens, 확인, 빌드 번호
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828593"
---
# HoloLens 업데이트

HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다. HoloLens는 전원이 켜져 있고 인터넷에 연결 될 때마다 시스템 업데이트가 자동으로 다운로드 되 고 설치 되며,이는 대기 상태에 있는 경우에도 마찬가지입니다.

이 문서에서는 다음에 대 한 HoloLens 도구를 안내 합니다.

- 현재 운영 체제 버전 보기 (빌드 번호)
- 업데이트 확인
- 수동으로 HoloLens 업데이트
- 이전 업데이트로 롤백

## 운영 체제 버전 확인 (빌드 번호)

설정 앱을 열고 **시스템**정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  **About**.

## 업데이트 확인 및 수동 업데이트

설정에서 언제 든 지 업데이트를 확인할 수 있습니다.  사용 가능한 업데이트를 보고 새 업데이트를 확인 하려면 다음을 수행 합니다.

1. **설정** 앱을 엽니다.
1. **업데이트 & 보안**  >  **Windows 업데이트**를 탐색 합니다.
1. **업데이트 확인을**선택 합니다.

업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다. 다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다. 장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.

HoloLens에서 업데이트를 설치 하는 동안에는 회전 하는 기어 및 진행 표시기가 표시 됩니다. 이번 시간에는 HoloLens를 끄지 마세요. 설치가 완료 되 면 자동으로 다시 시작 됩니다.

HoloLens는 한 번에 하나의 업데이트를 적용 합니다.  HoloLens가 최신 버전 뒤에 두 개 이상 있는 경우 업데이트 프로세스를 여러 번 실행 하 여 완전히 최신 상태가 되도록 해야 할 수 있습니다.

## 이전 버전으로 돌아가기-HoloLens 2

일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다. 고급 복구 도우미를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가면 개인 파일 및 설정이 삭제 됩니다.

이전 버전의 HoloLens 2로 돌아가려면 다음 단계를 따르세요.

1. PC에 전화 또는 Windows 장치가 연결 되어 있지 않은지 확인 합니다.
1. PC에서 Microsoft Store의 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 를 다운로드 합니다.
1. [최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.
1. 이러한 다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드**를 엽니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 추출** > **추출**을 선택하여 압축을 풉니다.
1. USB-A에서 USB-C 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다. (다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)
1. 고급 복구 도우미는 HoloLens를 자동으로 검색 합니다. **Microsoft HoloLens** 타일을 선택 합니다.
1. 다음 화면에서 **수동 패키지 선택을** 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다. (확장명을 가진 파일을 찾습니다.)
1. **소프트웨어 설치**를 선택 하 고 지침을 따릅니다.

## 이전 버전으로 돌아가기-HoloLens (첫번째 Gen)

일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다. Windows 장치 복구 도구를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가면 개인 파일 및 설정이 삭제 됩니다.

이전 버전의 HoloLens 1로 돌아가려면 다음 단계를 따르세요.

1. PC에 전화 또는 Windows 장치가 연결 되어 있지 않은지 확인 합니다.
1. PC에서 [WDRT (Windows 장치 복구) 도구](https://support.microsoft.com/help/12379)를 다운로드 합니다.
1. [HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.
1. 다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드**를 엽니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 고 압축 풀기 **모두 추출을**선택  >  **Extract** 하 여 압축을 풉니다.
1. 함께 제공 된 마이크로 USB 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다. (다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)
1. WDRT는 HoloLens를 자동으로 검색 합니다. **Microsoft HoloLens** 타일을 선택 합니다.
1. 다음 화면에서 **수동 패키지 선택을** 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다. (확장명을 가진 파일을 찾습니다.)
1. **소프트웨어 설치**를 선택 하 고 지침을 따릅니다.

> [!NOTE]
> WDRT가 HoloLens를 감지 하지 못하는 경우 PC를 다시 시작 해 보세요. 그래도 문제가 해결 **되지 않으면 내 장치를 찾을 수 없음을**선택 하 고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.

## HoloLens의 Windows 참가자 프로그램

HoloLens의 최신 기능을 확인 하 고 싶으신가요?  그렇다면 Windows 참가자 프로그램에 가입 하세요. 일반적인 일반 사용자가 사용할 수 있으려면 HoloLens 소프트웨어 업데이트의 preview 빌드에 대 한 액세스 권한을 얻을 수 있습니다.

[Microsoft HoloLens에 대 한 Windows 참가자 미리 보기를 다운로드](hololens-insider.md)하세요.
