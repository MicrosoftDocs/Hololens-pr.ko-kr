---
title: 업데이트 HoloLens 2
description: HoloLens 빌드 번호를 확인하고, 디바이스 업데이트를 최신 상태로 유지하고, 참가자 프로그램에 가입하고, 업데이트를 롤백하는 방법을 알아봅니다.
keywords: 방법, 업데이트, 롤백, HoloLens, 빌드 확인, 빌드 번호
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033816"
---
# <a name="update-hololens-2"></a>업데이트 HoloLens 2

## <a name="overview"></a>개요

항상 새로운 기능, 버그 수정 및 보안 업데이트에 대해 작업하고 있습니다. 이러한 업데이트가 준비되면 알림이 표시됩니다.

기본 설정에 따라 HoloLens 전원에 연결되고 인터넷에 연결되고 대기 상태일 때마다 시스템 업데이트를 자동으로 다운로드하고 설치합니다.

HoloLens 항상 업데이트되도록 하려면 HoloLens 함께 들어 있는 귀에 연결한 상태로 둡니다. 또한 HoloLens 인터넷에 연결하려고 합니다. 이러한 방식으로 시스템 업데이트를 자동으로 다운로드하고 설치합니다. 

Windows 업데이트 서비스를 사용하면 업데이트 프로세스의 여러 측면(예: 어떤 디바이스가 언제 어떤 업데이트를 받는지 등)을 제어할 수 있습니다. 이 컨트롤은 테스트를 위해 HoloLens 디바이스의 하위 집합에 업데이트를 롤아웃할 수 있기 때문에 유용합니다. 그런 다음, 나머지 업데이트에 대한 업데이트를 롤아웃합니다. 또는 다른 업데이트 유형에 대해 서로 다른 업데이트 일정을 정의할 수 있습니다.

## <a name="types-of-updates"></a>업데이트 유형

HoloLens 경우 두 가지 유형의 업데이트를 자동으로 관리할 수 있습니다. 

- 기능 업데이트: 1년 2회 릴리스됩니다.
- 품질 업데이트: 중요한 보안 업데이트를 포함합니다. 매월 또는 필요에 따라 릴리스합니다.

**업데이트** / **AllowAutoUpdate를** 사용하여 업데이트의 검사, 다운로드 및 설치를 관리합니다. 

## <a name="scheduling-updates"></a>업데이트 예약

업데이트 일정을 설정할 수도 있습니다. 특정 요일 또는 매일 특정 시간에 있을 수 있습니다. 예를 들어 오후 5시 또는 활성 시간 외입니다.

마지막으로, 업데이트 전략 계획에 대한 몇 가지 단어를 입력합니다. 업데이트 지연을 지원합니다. 따라서 Microsoft에서 업데이트를 릴리스하여 디바이스에 해당 업데이트를 설치한 후 대기하는 시간을 결정할 수 있습니다.

경우에 따라 회사에서 먼저 모든 새로운 기능을 시도하여 모든 기능이 작동하는지 확인하고 지원 팀이 준비되도록 새 업데이트에 익숙할 수 있습니다. 모두 양호한 것으로 확인되면 전체 회사에 업데이트를 롤아웃합니다. 디바이스의 하위 집합을 업데이트 링이라고 하는 다양한 지연 정책과 연결하면 조직의 업데이트 출시 전략을 조정할 수 있습니다.

## <a name="hololens-update-tools"></a>HoloLens 업데이트 도구

이 섹션에서는 다음을 위한 HoloLens 도구를 안내합니다.

- 업데이트 확인
- 수동으로 업데이트 HoloLens
- 현재 운영 체제 버전 보기(빌드 번호)
- 이전 업데이트로 롤백

### <a name="check-for-updates-and-manually-update"></a>업데이트 확인 및 수동으로 업데이트

설정에서 언제든지 업데이트를 확인할 수 있습니다.  사용 가능한 업데이트를 확인하고 새 업데이트를 확인하려면 다음을 수행합니다.

1. **설정** 앱을 엽니다.
1. 업데이트 **& 보안**  >  **Windows 업데이트로 이동합니다.**
1. **업데이트 확인** 을 선택합니다.

업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작됩니다. 다운로드가 완료되면 **지금 다시 시작** 단추를 선택하여 설치를 트리거합니다. 디바이스가 40% 미만이고 연결되지 않은 경우 다시 시작해도 업데이트 설치가 시작되지 않습니다.

HoloLens 업데이트를 설치하는 동안 회전 기어와 진행률 표시기가 표시됩니다. 이 시간 동안 HoloLens 해제하지 마십시오. 설치가 완료되면 자동으로 다시 시작됩니다.

HoloLens 한 번에 하나의 업데이트를 적용합니다.  HoloLens 최신 버전보다 버전이 두 개 이상인 경우 업데이트 프로세스를 여러 번 실행하여 완전히 최신 상태로 만들어야 할 수 있습니다.

### <a name="check-your-operating-system-version-build-number"></a>운영 체제 버전 확인(빌드 번호)

**설정** 열고 시스템 정보 를 **선택하여** 시스템 버전 번호(빌드 번호)를 확인할 수  >  있습니다.

### <a name="go-back-to-a-previous-version"></a>이전 버전으로 돌아가기

경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아가야 할 수 있습니다. 권장되는 단계는 다음과 같습니다.

1. 지원팀에 문의하여 문제를 해결할 수 있는지 확인합니다.
    1. **선택적** 또는 **전체** 원격 분석이 사용하도록 설정되어 있는지 확인합니다. 이렇게 하면 버그가 더 실행 가능하고 엔지니어가 쉽게 진단할 수 있습니다.
    1. [파일 피드백은](hololens-feedback.md) 최대한 설명적입니다. 제목을 기록해 두거나 공유 기능을 사용하여 지원과 버그를 공유할 수 있습니다.
    1. [지원 담당자에게 문의합니다.](https://aka.ms/hlsupport) 이전 버전으로 돌아가서 해결해야 하는 문제인 경우 디바이스를 플래시하는 FFU를 제공할 수 있습니다.

1. 작동하지 않는 경우 고급 복구 도우미 를 [HoloLens 2 다시 설정하거나 다시](hololens-recovery.md)설정합니다.
    1. PC의 Microsoft Store [Advanced Recovery Companion을](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 다운로드합니다.
    1. PC에 연결된 휴대폰 또는 Windows 디바이스가 없는지 확인합니다.
    1. 플래시할 버전을 선택합니다.
        1. 최신 HoloLens 2 [릴리스](https://aka.ms/hololens2download)를 다운로드할 수 있습니다.
        1. ARC에서 호스트하는 기본 빌드를 사용할 수 있습니다. (이 옵션을 선택하면 다음 단계를 건너뜁니다.)
        1. 제공된 빌드 지원을 사용할 수 있습니다.
    1. 이러한 다운로드를 완료했으면 **파일 탐색기**  >  **다운로드를** 엽니다. 다운로드한 압축된 폴더를 마우스 오른쪽 단추로 클릭하고 **압축을** 풀려면 모두  >  **추출을** 선택합니다.
    1. USB-A-USB-C 케이블을 사용하여 PC에 HoloLens 커넥트. (다른 케이블을 사용하여 HoloLens 연결한 경우에도 가장 효과적입니다.)
    1. 고급 복구 도우미는 HoloLens 자동으로 검색합니다. **Microsoft HoloLens** 타일을 선택합니다.
    1. 다음 화면에서 수동 **패키지 선택을** 선택한 다음, 4단계에서 압축을 풀 폴더에 포함된 설치 파일을 선택합니다. (확장이 있는 파일을 `.ffu` 찾습니다.)
    1. **소프트웨어 설치를** 선택하고 지침을 따릅니다.

> [!NOTE]
> 이전 버전으로 돌아가면 개인 파일 및 설정이 삭제됩니다.

또한 현재 설치된 릴리스를 계속 사용하려는 경우 업데이트를 수동으로 일시 [중지할](hololens-updates.md#pause-updates-via-device)수도 있습니다. 이렇게 하면 엔지니어링 팀이 문제를 해결할 수 있는 시간이 주게 됩니다.

## <a name="windows-insider-program-on-hololens"></a>Windows HoloLens 참가자 프로그램

HoloLens 최신 기능을 확인하시겠습니까?  그렇다면 Windows 참가자 프로그램 조인합니다. 일반 일반인에게 제공되기 전에 HoloLens 소프트웨어 업데이트의 미리 보기 빌드에 액세스할 수 있습니다.

[Microsoft HoloLens Windows 참가자 미리 보기를 받으세요.](hololens-insider.md)