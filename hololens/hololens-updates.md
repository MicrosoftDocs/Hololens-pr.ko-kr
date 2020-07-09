---
title: HoloLens 업데이트 관리
description: 관리자는 모바일 장치 관리를 사용하여 HoloLens 장치에 대한 업데이트를 관리할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: f8d0c788756b0a24ac8a26b8258b267483f1a890
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857756"
---
# HoloLens 업데이트 관리

HoloLens는 다른 Windows 10 장치와 같은 방식으로 Windows 업데이트를 사용합니다. 업데이트가 사용 가능하게 되면 자동으로 다운로드 되고 장치가 충전되고 인터넷에 연결 되면 설치합니다. 이 문서에서는 엔터프라이즈 또는 기타 관리되는 환경에서 업데이트를 관리하는 방법을 설명합니다. 개별 HoloLens 장치에 대한 업데이트를 관리하는 방법에 대한 자세한 내용은 [HoloLens 업데이트](hololens-update-hololens.md)를 참조하세요.

## 자동으로 업데이트 관리

비즈니스용 Windows Holographic은 [비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)를 사용하여 업데이트를 관리할 수 있습니다. 모든 HoloLens 2 장치에서 비즈니스용 Windows Holographic을 사용할 수 있습니다. 비즈니스용 Windows Holographic 빌드 10.0.18362.1042 이상을 사용하고 있는지 확인합니다. HoloLens(1세대) 장치를 보유하고 있는 경우에는 [비즈니스용 Windows Holographic로 업그레이드](hololens1-upgrade-enterprise.md) 해야 업데이트를 관리할 수 있습니다.

비즈니스용 Windows 업데이트는 HoloLens 장치를 Windows Update 서비스에 직접 연결 합니다. 비즈니스용 Windows Update를 사용하여 업데이트 프로세스&mdash;의 여러 측면을 제어할 수 있습니다. 즉, 어떤 장치가 어떤 시간에 업데이트 되는지 관리할 수 있습니다. 예를 들어 테스트를 위해 장치 하위 집합에 대한 업데이트를 하고 나중에 나머지 장치에 대한 업데이트를 시작할 수 있습니다. 또는 다른 업데이트 유형에 대해 서로 다른 업데이트 일정을 정의할 수 있습니다.

> [!NOTE]  
> HoloLens 장치의 경우 기능 업데이트(1년에 2번 릴리스) 및 품질 업데이트 (긴급 보안 업데이트를 포함하여 월간 또는 필요에 따라 릴리스)를 자동으로 관리할 수 있습니다. 업데이트 유형에 대한 자세한 내용은 [비즈니스용 Windows Updated에서 관리되는 업데이트 유형](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)을 참조하세요.

Microsoft Intune과 같은 MDM (모바일 장치 관리) 솔루션에서 정책을 사용하여 HoloLens에 대한 Windows 업데이트를 구성할 수 있습니다.

Intune을 사용하여 비즈니스용 Windows 업데이트를 구성 하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)를 참조하세요.

> [!IMPORTANT]  
> Intune에서는 업데이트를 관리하기 위한 두 가지 정책 유형 (*Windows 10 업데이트 링* 및 *Windows 10 기능 업데이트*)을 제공합니다. Windows 10 기능 업데이트 정책 유형은 현재 공개 미리 보기에 있습니다. 이는 HoloLens에서 지원 되지 않습니다.
>  
> Windows 10 업데이트 링 정책을 사용하여 HoloLens 2 업데이트를 관리할 수 있습니다.

### HoloLens 2 또는 HoloLens(1세대)에 대한 업데이트 정책 구성

이 섹션에서는 HoloLens 2 또는 HoloLens (1 세대) 업데이트를 관리 하는데 사용할 수 있는 정책에 대해 설명합니다. HoloLens 2에서 사용할 수 있는 추가 기능에 대한 자세한 내용은 [HoloLens 2에 대한 업데이트 실시 계획 및 구성](#plan-and-configure-update-rollouts-for-hololens-2)을 참조하세요.

[정책 CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)는 비즈니스용 Windows 업데이트를 구성하는 정책을 정의합니다.

> [!NOTE]  
> 특정 버전의 HoloLens에서 지원되는 특별 정책에 대한 자세한 내용은 [HoloLens 장치에서 지원 되는 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)을 참조 하세요.

#### 업데이트 자동 검사 구성

**Update/AllowAutoUpdate** 정책을 사용하여 업데이트 검색, 다운로드 및 설치와 같은 자동 업데이트 동작을 관리할 수 있습니다.

이 정책은 다음의 값을 지원합니다.

- **0**-장치에 적용 되는 업데이트를 다운로드 할 준비가 되면 사용자에게 알립니다.
- **1** - 자동으로 업데이트를 설치한 다음 장치 다시 시작 예약을 사용자에게 알립니다.  
- **2** - 업데이트를 자동으로 설치하고 장치를 다시 시작합니다. 이 값은 권장 값이며 이 정책의 기본 값입니다.  

- **3** - 업데이트를 자동으로 설치하고 특정 시간에 장치를 다시 시작합니다. 설치 일과 시간을 지정합니다. 날짜와 시간을 지정하지 않으면 매일 오전 3시가 기본값입니다.  

- **4** - 업데이트를 자동으로 설치하고 장치를 다시 시작합니다. 이 옵션을 선택 하면 설정 페이지는 읽기 전용으로 설정됩니다.

- **5** - 자동 업데이트를 해제합니다.

이 정책에서 사용 가능한 설정에 대한 자세한 내용은 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)를 참조하세요.

> [!NOTE]  
> Microsoft Intune에서 **자동 업데이트 동작**을 사용하여 이 정책을 변경할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/windows-update-for-business-configure)를 참조하십시오.

#### 업데이트 일정 구성

업데이트를 적용하는 방법과 시기를 구성 하려면 다음 정책을 사용합니다.

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).  
   - 값: **0**-**7** (0 = 매일, 1 = 일요일, 7 = 토요일)
   - 기본값: **0** (매일)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).
   - 값: 0-23 (0 = 자정, 23 = 오후 11시)
   - 기본값: 오후 3시

#### Windows 10에서 실행되는 장치에는 버전 1607만 해당

다음 업데이트 정책을 사용하여 Windows 업데이트 대신 WSUS(Windows Server Update Service)에서 업데이트를 받을 장치를 구성할 수 있습니다.

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### HoloLens 2에 대한 업데이트 실행 계획 및 구성

HoloLens 2는 HoloLens (1세대) 보다 더 많은 업데이트 자동화 기능을 지원합니다. Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트를 관리하는 경우에는 더 많이 적용 받습니다. 이러한 기능을 사용하면 조직 전체에서 간편하게 업데이트 시행을 계획하고 구현할 수 있습니다.

#### 업데이트 전략 계획

비즈니스용 Windows 업데이트는 지연 정책을 지원 합니다. Microsoft에서 업데이트기 릴리스 된 후 지연 정책을 사용하여 장치에 업데이트를 설치하기 전에 대기 기간을 정의할 수 있습니다. 다양한 지연 정책을 통해 장치의 하위 집합 (*업데이트 링*)을 연결하여 조직의 업데이트 시행 전략을 조정할 수 있습니다.

1,000개의 장치를 보유하고 있고 5 가지 방법으로 업데이트를 해야하는 조직을 예로 들어보겠습니다. 조직은 다음 표에 표시 된 대로 5개의 업데이트 링을 만들 수 있습니다.

|그룹 |장치 수 |지연 (일) |
| ---| :---: | :---: |
|Grp 1 (IT 담당자) |5 |0 |
|Grp 2 (이른 도입자) |50 |60 |
|Grp 3 (정 1) |250 |120 |
|Grp 4 (정 2) |300 |150 |
|Grp 5 (정 3) |395 |180 |

시간에 따라 전체 조직에 시행되는 과정입니다.

![업데이트를 배포하기 위한 타임라인](./images/hololens-updates-timeline.png)

#### 업데이트 지연 정책 구성

지연 정책은 업데이트를 사용 할 수 있게 된 날부터 해당 업데이트가 장치에 제공 되는 날 사이의 일 수를 지정합니다.

기능 업데이트 및 품질 업데이트에 대해 서로 다른 지연을 구성할 수 있습니다. 다음 표에서는 각 유형에 사용할 특정 정책과 각 유형에 대한 최대 지연 기간을 보여줍니다.

|범주 |정책 |최대 지연 |
| --- | --- | --- |
|기능 업데이트 |DeferFeatureUpdatesPeriodInDays |365일 |
|품질 업데이트 |DeferQualityUpdatesPeriodInDays |30일 |

####  예: Intune을 사용하여 업데이트 관리

**예1: 업데이트 링 만들기 및 할당**

이 예제에 대한 자세한 내용은 [업데이트 링 만들기 및 할당](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)을 참조하세요.

1. [Microsoft 끝점 관리자 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인하여 Intune 프로필로 이동 합니다.
1. **소프트웨어 업데이트** > **Windows 10 업데이트 링** > **만들기**를 선택합니다.
1. **기초**에서 이름과 설명을 지정(선택 사항)하고 **다음**을 선택합니다.
1. **업데이트 링 설정**의 **서비스 채널**에서 **반기 채널**을 선택한 다음 **기능 업데이트 지연 기간**을 **120**으로 변경 합니다. **다음**을 선택합니다.
1. **과제**에서 **+ 그룹을 선택하여 포함**을 선택하고 업데이트 링을 하나 이상의 그룹에 할당합니다. **+ 그룹을 선택하여 제외**를 사용하여 과제를 세부조정 할 수 있습니다. **다음**을 선택합니다.
1. **검토 + 만들기**에서 설정을 검토합니다. 업데이트 링 구성을 저장할 준비가 되면 **만들기**를 선택합니다.

이제 업데이트 링 목록에 새 Windows 10 업데이트 링이 포함됩니다.

**예2: 업데이트 링 일시 중지**

기능 또는 품질 업데이트를 배포할 때 문제가 발생하는 경우 업데이트를 35일(지정 된 날짜부터 시작)간 일시 중지할 수 있습니다. 이 일시 중지를 수행하면 문제가 해결 되거나 완화 될 때까지 다른 장치에서 업데이트를 설치 하지 못 합니다. 기능 업데이트를 일시 중지해도 장치 품질 업데이트는 계속 제공되기 때문에 계속해서 보안을 유지할 수 있습니다. 지정 된 시간이 경과되면 일시 중지가 자동으로 만료됩니다. 해당 시점에 업데이트 프로세스가 다시 시작됩니다.

Intune에서 업데이트 링을 일시 중지 하려면 다음 단계를 따릅니다.

1. 업데이트 링 개요 페이지에서 **일시 중지**를 선택합니다.
1. 업데이트 유형(**기능** 또는 **품질**)을 선택하여 일시 중지 한 다음 **확인**을 선택합니다.

업데이트 유형 하나를 일시 중지 하면 해당 링의 개요 창에 해당 업데이트 유형을 다시 시작 하기까지 남은 일수가 표시됩니다.

업데이트 링이 일시 중지 된 상태에서 다음 옵션 중 하나를 선택할 수 있습니다.

- 해당 업데이트 유형에 대해 35일간의 일시 중지 기간을 연장 하려면 **확장**을 선택합니다.
- 해당 링에 대한 업데이트를 활성 작업으로 복원하려면 **다시 시작**을 선택합니다. 필요한 경우 업데이트 링을 다시 일시 중지할 수 있습니다.

> [!NOTE]  
> HoloLens 2 장치에서는 업데이트 링에 대한 **제거** 작업이 지원 되지 않습니다.

## 업데이트 수동으로 확인

HoloLens가 정기적으로 시스템 업데이트를 확인하기 때문에 사용자가 하지 않아도 되지만 사용자가 수동으로 확인하고자 할 때도 있을 것입니다.

수동으로 업데이트를 확인하려면 **설정** > **업데이트 및 보안** > **으로 이동하여 업데이트를 확인하세요**. 설정 앱에서 장치가 최신 상태로 나타나면 현재 사용 가능한 모든 업데이트를 사용 중인 것입니다.

## 수동으로 업데이트 되돌리기

경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아갈 수도 있습니다. HoloLens 2 또는 HoloLens (1세대)를 사용 여부에 따라 해당 과정이 달라집니다.

### 이전 버전으로 돌아가기 (HoloLens 2)

고급 복구 도우미를 사용하여 HoloLens 2를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens 2로 돌아갈 수 있습니다.

> [!NOTE]
> 이전 버전으로 되돌리면 개인 파일과 설정이 삭제됩니다.

HoloLens 2의 이전 버전으로 돌아가려면 다음 단계를 따르세요.

1. 컴퓨터에 연결 된 휴대폰 또는 Windows 장치가 없는지 확인합니다.
1. 컴퓨터의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)를 다운로드 합니다.
1. [최근 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.
1. 다운로드가 끝나면 **파일 탐색기** > **다운로드**를 열고 방금 다운로드 받은 압축된(zip) 폴더를 오른쪽 클릭한 후 **모두 압축 풀기** > **압축풀기**를 선택하여 파일을 확장합니다.
1. USB-A나 USB-C 케이블을 사용하여 컴퓨터에 HoloLens 장치를 연결합니다. 그동안 다른 케이블을 사용하여 HoloLens를 연결 했더라도 이 케이블이 가장 적합합니다.
1. 고급 복구 도우미는 HoloLens 장치를 자동으로 감지합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 **수동 패키지 선택**을 선택한 다음 이전에 확장 한 폴더를 엽니다. 
1. 설치 파일을 선택 합니다(.ffu 확장명을 가진 파일).
1. **소프트웨어 설치**를 선택하고 지침을 따릅니다.

### 이전 버전으로 돌아가기 (HoloLens(1세대))

고급 복구 도우미를 사용하여 HoloLens(1세대)를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens로 돌아갈 수 있습니다.

> [!NOTE]
> 이전 버전으로 되돌리면 개인 파일과 설정이 삭제됩니다.

HoloLens(1세대)의 이전 버전으로 돌아가려면 다음 단계를 따르세요.

1. 컴퓨터에 연결 된 휴대폰 또는 Windows 장치가 없는지 확인합니다.
1. 컴퓨터에서 [(WDRT) Windows 장치 복구 도구](https://support.microsoft.com/help/12379)를 다운로드 합니다.
1. [HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.
1. 다운로드가 끝나면 **파일 탐색기** > **다운로드**를 열고 방금 다운로드 받은 압축된(zip) 폴더를 오른쪽 클릭한 후 **모두 압축 풀기** > **압축풀기**를 선택하여 파일을 확장합니다.
1. Hololens 장치와 함께 제공 된 마이크로 USB 케이블을 사용하여 HoloLens 장치를 컴퓨터에 연결합니다. 그동안 다른 케이블을 사용하여 HoloLens를 연결 했더라도 이 케이블이 가장 적합합니다.
1. WDRT는 HoloLens 장치를 자동으로 감지합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 **수동 패키지 선택**을 선택한 다음 이전에 확장 한 폴더를 엽니다. 
1. 설치 파일을 선택 합니다(.ffu 확장명을 가진 파일).
1. **소프트웨어 설치**를 선택하고 지침을 따릅니다.

> [!NOTE]
> WDRT에서 HoloLens 장치가 자동으로 감지되지 않으면 컴퓨터를 다시 시작 해 보세요. 그래도 문제가 해결 되지 않으면 **장치가 감지 되지 않음**을 선택하고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.

## 관련 문서

- [비즈니스용 Windows 업데이트를 사용하여 업데이트 배포](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 업데이트용 서비스 채널에 장치 할당](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
