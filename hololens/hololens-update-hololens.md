---
title: 업데이트 HoloLens 2
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
- HoloLens 2
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662841"
---
# <a name="update-hololens-2"></a>업데이트 HoloLens 2

HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다. HoloLens은 전원에 연결 되어 있고 인터넷에 연결 되어 있는 경우에도 시스템 업데이트를 자동으로 다운로드 하 여 설치 합니다 (대기 중인 경우에도).

이 문서에서는 다음에 대 한 HoloLens 도구를 안내 합니다.

- 현재 운영 체제 버전 보기 (빌드 번호)
- 업데이트 확인
- 수동으로 HoloLens 업데이트
- 이전 업데이트로 롤백

## <a name="check-your-operating-system-version-build-number"></a>운영 체제 버전 확인 (빌드 번호)

설정 앱을 열고 **시스템** 정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  .

## <a name="check-for-updates-and-manually-update"></a>업데이트 확인 및 수동으로 업데이트

언제 든 지 설정에서 업데이트를 확인할 수 있습니다.  사용 가능한 업데이트를 확인 하 고 새 업데이트를 확인 하려면:

1. **설정** 앱을 엽니다.
1. **업데이트 & 보안**  >  **Windows 업데이트** 으로 이동 합니다.
1. **업데이트 확인** 을 선택합니다.

업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다. 다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다. 장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.

HoloLens 업데이트를 설치 하는 동안 회전 하는 기어 및 진행률 표시기가 표시 됩니다. 이 시간 동안 HoloLens 해제 하지 마십시오. 설치가 완료 되 면 자동으로 다시 시작 됩니다.

HoloLens은 한 번에 하나의 업데이트를 적용 합니다.  최신 버전 보다 두 버전 이상의 HoloLens 경우 업데이트 프로세스를 여러 번 실행 하 여 최신 상태로 유지 해야 할 수 있습니다.

## <a name="go-back-to-a-previous-version"></a>이전 버전으로 돌아가기

경우에 따라 HoloLens 소프트웨어의 이전 버전으로 돌아갈 수 있습니다. 권장 단계는 다음과 같습니다.

1. 지원 서비스에 문의 하 여 문제를 해결할 수 있는지 확인 합니다.
    1. **선택적** 또는 **전체** 원격 분석이 사용 하도록 설정 되어 있는지 확인 합니다. 이렇게 하면 엔지니어가 더 쉽게 실행할 수 있고 엔지니어가 진단할 수 있습니다.
    1. [파일 피드백](hololens-feedback.md) 을 가능한 한 설명적으로 설명 합니다. 버그를 지원과 공유할 수 있도록 제목을 적어 두고 공유 기능을 사용 합니다.
    1. [지원](https://aka.ms/hlsupport)담당자에 게 문의 하세요. 이전 버전으로 돌아가서 문제를 해결 해야 하는 경우에는 장치를 플래시 하기 위해 FFU를 제공할 수 있습니다.

1. 그래도 작동 하지 않으면 [고급 복구 도우미를 사용 하 여 HoloLens 2를 다시 설정 하거나 경감 하기 위해](hololens-recovery.md).
    1. PC의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 를 다운로드 합니다.
    1. 휴대폰 또는 Windows 장치가 PC에 연결 되어 있지 않은지 확인 합니다.
    1. 플래시 하려는 버전 선택:
        1. [최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드할 수 있습니다.
        1. ARC가 호스트 하는 기본 빌드를 사용할 수 있습니다. (이 옵션을 선택 하는 경우 다음 단계를 건너뜁니다.)
        1. 에서 제공 하는 빌드 지원을 사용할 수 있습니다.
    1. 이러한 다운로드를 마치면 **파일 탐색기**  >  **다운로드** 를 엽니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 **고 압축 풀기**  >   를 선택 하 여 압축을 풉니다.
    1. usb-a usb-C 케이블을 사용 하 여 PC에 HoloLens를 커넥트 합니다. HoloLens 연결 하는 데 다른 케이블을 사용한 경우에도이 방법이 가장 잘 작동 합니다.
    1. Advanced Recovery 도우미가 자동으로 HoloLens를 검색 합니다. **Microsoft HoloLens** 타일을 선택합니다.
    1. 다음 화면에서 **수동 패키지 선택** 을 선택한 다음 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다. (.Ffu 확장명을 가진 파일을 찾습니다.)
    1. **소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.

> [!NOTE]
> 이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.

또한 현재 설치 된 릴리스를 유지 하려는 경우 업데이트를 수동으로 [일시 중지할](hololens-updates.md#pause-updates-via-device)수도 있습니다. 그러면 엔지니어링 팀이 문제를 해결할 수 있습니다.

## <a name="windows-insider-program-on-hololens"></a>Windows HoloLens의 참가자 프로그램

HoloLens에서 최신 기능을 확인 하 고 싶으세요?  그렇다면 Windows Insider Program에 참여 하세요. 일반 사용자가 사용할 수 있게 되기 전에 HoloLens 소프트웨어 업데이트의 빌드 미리 보기에 액세스할 수 있습니다.

[Microsoft HoloLens에 대 한 Windows Insider preview를 가져옵니다](hololens-insider.md).
