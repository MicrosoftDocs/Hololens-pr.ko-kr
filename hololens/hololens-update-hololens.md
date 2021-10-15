---
title: 업데이트 HoloLens 2
description: HoloLens 빌드 번호를 확인 하 고, 장치 업데이트를 최신 상태로 유지 하 고, 참가자 프로그램에 참여 하 고, 업데이트를 롤백하는 방법에 대해 알아봅니다.
keywords: 방법, 업데이트, 롤백, HoloLens, 빌드 확인, 빌드 번호
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034266"
---
# <a name="update-hololens-2"></a>업데이트 HoloLens 2

## <a name="overview"></a>개요

새 기능, 버그 수정 및 보안 업데이트에 대해 항상 노력 하 고 있습니다. 이러한 업데이트가 준비 되 면 알림이 표시 됩니다.

사용자의 기본 설정에 따라 전원에 연결 되어 있고 인터넷에 연결 되어 있고 대기 중인 경우에도 HoloLens 자동으로 다운로드 하 여 시스템 업데이트를 설치 합니다.

HoloLens 항상 업데이트 되도록 하려면 함께 제공 된 충전기와 연결 된 상태를 유지 합니다. 또한 HoloLens 인터넷에 연결 하려고 합니다. 이러한 방식으로 시스템 업데이트를 자동으로 다운로드 하 여 설치 합니다. 

Windows 업데이트 서비스를 사용 하면 업데이트 프로세스의 여러 측면을 제어할 수 있습니다. 예를 들어 장치에서 어떤 시간에 업데이트를 가져올 수 있습니다. 이 컨트롤은 테스트를 위해 HoloLens 장치의 하위 집합에 대 한 업데이트를 롤아웃할 수 있으므로 유용 합니다. 그런 다음 나머지 업데이트에 업데이트를 배포 합니다. 또는 다른 업데이트 유형에 대해 서로 다른 업데이트 일정을 정의할 수 있습니다.

## <a name="types-of-updates"></a>업데이트 유형

HoloLens의 경우 두 가지 유형의 업데이트를 자동으로 관리할 수 있습니다.

- 기능 업데이트: 1 년에 두 번 릴리스 되었습니다.
- 품질 업데이트: 중요 한 보안 업데이트를 포함 합니다. 매월 또는 필요에 따라 릴리스됩니다.

**업데이트** / **allowautoupdate** 업데이트를 사용 하 여 업데이트의 검색, 다운로드 및 설치를 관리 합니다. 

## <a name="scheduling-updates"></a>업데이트 예약

업데이트 일정을 설정할 수도 있습니다. 특정 날짜 또는 매일 특정 시간에 있을 수 있습니다. 예를 들어 오후 5 시 또는 근무 외 시간에입니다.

마지막으로, 업데이트 전략 계획에 대 한 몇 가지 단어입니다. 업데이트 지연과을 지원 하므로 Microsoft에서 업데이트를 출시 하 여 장치에 해당 업데이트를 설치 하는 동안 대기할 기간을 결정할 수 있습니다.

회사에서 모든 새로운 기능을 먼저 사용해 보고 모든 것이 제대로 작동 하는지 확인 하 고 새 업데이트를 파악 하 여 지원 팀이 준비 하는 경우가 있습니다. 모두 양호 하다 고 확인 한 후에는 전체 회사에 대 한 업데이트를 배포 합니다. 장치 하위 집합을 업데이트 링 이라고 하는 서로 다른 지연 정책에 연결 하면 조직의 업데이트 출시 전략을 조정할 수 있습니다.

## <a name="hololens-update-tools"></a>HoloLens 업데이트 도구

이 섹션에서는 다음에 대 한 HoloLens 도구를 안내 합니다.

- 업데이트 확인
- 수동으로 HoloLens 업데이트
- 현재 운영 체제 버전 보기 (빌드 번호)
- 이전 업데이트로 롤백

### <a name="check-for-updates-and-manually-update"></a>업데이트 확인 및 수동으로 업데이트

언제 든 지 설정에서 업데이트를 확인할 수 있습니다.  사용 가능한 업데이트를 확인 하 고 새 업데이트를 확인 하려면:

1. **설정** 앱을 엽니다.
1. **업데이트 & 보안**  >  **Windows 업데이트** 으로 이동 합니다.
1. **업데이트 확인** 을 선택합니다.

업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다. 다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다. 장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.

HoloLens 업데이트를 설치 하는 동안 회전 하는 기어 및 진행률 표시기가 표시 됩니다. 이 시간 동안 HoloLens 해제 하지 마십시오. 설치가 완료 되 면 자동으로 다시 시작 됩니다.

HoloLens은 한 번에 하나의 업데이트를 적용 합니다.  최신 버전 보다 두 버전 이상의 HoloLens 경우 업데이트 프로세스를 여러 번 실행 하 여 완전히 최신 상태로 만들어야 할 수 있습니다.

### <a name="check-your-operating-system-version-build-number"></a>운영 체제 버전 확인 (빌드 번호)

**설정** 를 열고 **시스템** 정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  .

### <a name="go-back-to-a-previous-version"></a>이전 버전으로 돌아가기

경우에 따라 HoloLens 소프트웨어의 이전 버전으로 돌아갈 수 있습니다. 권장 단계는 다음과 같습니다.

1. 지원 서비스에 문의 하 여 문제를 해결할 수 있는지 확인 합니다.
    1. **선택적** 또는 **전체** 원격 분석이 사용 하도록 설정 되어 있는지 확인 합니다. 이렇게 하면 엔지니어가 더 쉽게 실행할 수 있고 엔지니어가 진단할 수 있습니다.
    1. [파일 피드백](hololens-feedback.md) 에는 가능한 한 설명으로 포함 됩니다. 제목을 기록 하거나 공유 기능을 사용 하 여 버그를 지원과 공유할 수 있습니다.
    1. [지원](https://aka.ms/hlsupport)담당자에 게 문의 하세요. 이전 버전으로 돌아가서 문제를 해결 해야 하는 경우에는 장치를 플래시 하기 위해 FFU를 제공할 수 있습니다.

1. 이 문제가 해결 되지 않으면 [고급 복구 도우미를 사용 하 여 HoloLens 2 경감 하기 위해](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> 이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.

또한 현재 설치 된 릴리스를 유지 하려는 경우 업데이트를 수동으로 [일시 중지할](hololens-updates.md#pause-updates-via-device)수도 있습니다. 그러면 엔지니어링 팀이 문제를 해결할 수 있습니다.

## <a name="windows-insider-program-on-hololens"></a>Windows HoloLens의 참가자 프로그램

HoloLens에서 최신 기능을 확인 하 고 싶으세요?  그렇다면 Windows Insider Program에 참여 하세요. 일반 사용자가 사용할 수 있게 되기 전에 HoloLens 소프트웨어 업데이트의 빌드 미리 보기에 액세스할 수 있습니다.

[Microsoft HoloLens에 대 한 Windows Insider preview를 가져옵니다](hololens-insider.md).