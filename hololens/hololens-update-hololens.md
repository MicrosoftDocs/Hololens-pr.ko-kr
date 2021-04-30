---
title: HoloLens 업데이트
description: HoloLens 빌드 번호를 확인 하 고, 장치 업데이트를 최신 상태로 유지 하 고, 참가자 프로그램에 참여 하 고, 업데이트를 롤백하는 방법에 대해 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309512"
---
# <a name="update-hololens"></a>HoloLens 업데이트

HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다. HoloLens는 대기 중인 경우에도 전원에 연결 하 고 인터넷에 연결 될 때마다 자동으로 다운로드 하 여 시스템 업데이트를 설치 합니다.

이 문서에서는 다음에 대 한 HoloLens 도구를 안내 합니다.

- 현재 운영 체제 버전 보기 (빌드 번호)
- 업데이트 확인
- HoloLens 수동 업데이트
- 이전 업데이트로 롤백

## <a name="check-your-operating-system-version-build-number"></a>운영 체제 버전 확인 (빌드 번호)

설정 앱을 열고 **시스템** 정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  .

## <a name="check-for-updates-and-manually-update"></a>업데이트 확인 및 수동으로 업데이트

언제 든 지 설정에서 업데이트를 확인할 수 있습니다.  사용 가능한 업데이트를 확인 하 고 새 업데이트를 확인 하려면:

1. **설정** 앱을 엽니다.
1. **업데이트 & 보안**  >  **Windows 업데이트** 으로 이동 합니다.
1. **업데이트 확인** 을 선택합니다.

업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다. 다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다. 장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.

HoloLens는 업데이트를 설치 하는 동안 회전 하는 기어와 진행률 표시기를 표시 합니다. 이 시간 동안에는 HoloLens를 끄지 마세요. 설치가 완료 되 면 자동으로 다시 시작 됩니다.

HoloLens는 한 번에 하나의 업데이트를 적용 합니다.  HoloLens가 최신 버전 보다 최신 버전인 경우 업데이트 프로세스를 여러 번 실행 하 여 완전히 최신 상태로 만들어야 할 수 있습니다.

## <a name="go-back-to-a-previous-version---hololens-2"></a>이전 버전으로 돌아가기-HoloLens 2

일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다. 고급 복구 도우미를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.

이전 버전의 HoloLens 2로 돌아가려면 다음 단계를 수행 합니다.

1. 휴대폰 또는 Windows 장치가 PC에 연결 되지 않았는지 확인 합니다.
1. PC의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 를 다운로드 합니다.
1. [최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.
1. 이러한 다운로드를 마치면 **파일 탐색기**  >  **다운로드** 를 엽니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 **고 압축 풀기**  >   를 선택 하 여 압축을 풉니다.
1. USB-A USB-C 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다. (다른 케이블을 사용 하 여 HoloLens를 연결 하는 경우에도이 작업은 가장 효과적입니다.)
1. Advanced Recovery 도우미가 자동으로 HoloLens를 검색 합니다. **Microsoft HoloLens** 타일을 선택 합니다.
1. 다음 화면에서 **수동 패키지 선택** 을 선택한 다음 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다. (.Ffu 확장명을 가진 파일을 찾습니다.)
1. **소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>이전 버전으로 돌아가기-HoloLens (첫 번째 Gen)

일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다. Windows 장치 복구 도구를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.

이전 버전의 HoloLens 1로 돌아가려면 다음 단계를 수행 합니다.

1. 휴대폰 또는 Windows 장치가 PC에 연결 되지 않았는지 확인 합니다.
1. PC에서 [WDRT (Windows 장치 복구 도구)](https://support.microsoft.com/help/12379)를 다운로드 합니다.
1. [HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.
1. 다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드** 를 엽니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 고 **압축 풀기**  >  를 선택 하 여 압축을 **풉니다** .
1. 동봉 된 마이크로 USB 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다. (다른 케이블을 사용 하 여 HoloLens를 연결 하는 경우에도이 작업은 가장 효과적입니다.)
1. WDRT는 HoloLens를 자동으로 검색 합니다. **Microsoft HoloLens** 타일을 선택 합니다.
1. 다음 화면에서 **수동 패키지 선택** 을 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다. (.Ffu 확장명을 가진 파일을 찾습니다.)
1. **소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.

> [!NOTE]
> WDRT가 HoloLens를 검색 하지 않으면 PC를 다시 시작 합니다. 그래도 작동 하지 않으면 **내 장치를 찾을 수 없음** 을 선택 하 고 **Microsoft HoloLens** 를 선택한 후 지침을 따릅니다.

## <a name="windows-insider-program-on-hololens"></a>HoloLens의 Windows 참가자 프로그램

HoloLens의 최신 기능을 보 시겠습니까?  그렇다면 Windows 참가자 프로그램에 참여 하세요. 일반적으로 일반 사용자에 게 제공 되기 전에 HoloLens 소프트웨어 업데이트의 빌드 미리 보기에 액세스할 수 있습니다.

[Microsoft HoloLens 용 Windows Insider preview를 다운로드](hololens-insider.md)합니다.
