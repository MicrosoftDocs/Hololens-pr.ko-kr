---
title: HoloLens 업데이트 관리
description: 관리자가 모바일 장치 관리를 사용하여 HoloLens 장치 업데이트를 관리하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427358"
---
# <a name="manage-hololens-updates"></a>HoloLens 업데이트 관리

HoloLens는 다른 Windows 10 장치와 같은 방식으로 Windows 업데이트를 사용합니다. 업데이트를 사용할 수 있게 되면 자동으로 다운로드되고 장치가 충전되고 인터넷에 연결되면 설치됩니다. 이 문서에서는 엔터프라이즈 또는 기타 관리되는 환경에서 업데이트를 관리하는 방법을 설명합니다. 개별 HoloLens 장치에 대한 업데이트를 관리하는 방법에 대한 자세한 내용은 [HoloLens 업데이트](hololens-update-hololens.md)를 참조하세요.

## <a name="manage-updates-automatically"></a>자동으로 업데이트 관리

### <a name="managing-updates-by-using-windows-update-for-business"></a>비즈니스용 Windows 업데이트를 사용하여 업데이트 관리

Windows Holographic for Business는 [비즈니스용 Windows 업데이트](/windows/deployment/update/waas-manage-updates-wufb)를 사용하여 업데이트를 관리할 수 있습니다. 모든 HoloLens 2 장치에서 Windows Holographic for Business를 사용할 수 있습니다. Windows Holographic for Business 빌드 10.0.18362.1042 이상을 사용하고 있는지 확인합니다. HoloLens(1세대) 장치가 있는 경우 업데이트를 관리하려면 [해당 장치를 Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 합니다.

비즈니스용 Windows 업데이트는 HoloLens 장치를 Windows 업데이트 서비스에 직접 연결합니다. 비즈니스용 Windows 업데이트를 사용하여 업데이트 프로세스의 여러 측면을 제어할 수 있습니다.&mdash;즉, 어떤 장치가 어떤 시간에 업데이트되는지 관리할 수 있습니다. 예를 들어 테스트를 위해 장치 하위 집합에 대한 업데이트를 하고 나중에 나머지 장치에 대한 업데이트를 시작할 수 있습니다. 또는 다른 업데이트 유형에 대해 서로 다른 업데이트 일정을 정의할 수 있습니다.

> [!NOTE]  
> HoloLens 장치의 경우 기능 업데이트(1년에 2번 릴리스) 및 품질 업데이트 (긴급 보안 업데이트를 포함하여 월간 또는 필요에 따라 릴리스)를 자동으로 관리할 수 있습니다. 업데이트 유형에 대한 자세한 내용은 [비즈니스용 Windows 업데이트에서 관리하는 업데이트 유형](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)을 참조하세요.

Microsoft Intune과 같은 MDM(모바일 장치 관리) 솔루션에서 정책을 사용하여 HoloLens에 대한 Windows 업데이트를 구성할 수 있습니다.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트 관리

Intune을 사용하여 비즈니스용 Windows 업데이트를 구성하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 소프트웨어 업데이트 관리](/intune/protect/windows-update-for-business-configure)를 참조하세요. HoloLens에서 지원하는 특정 Intune 기능에 대한 자세한 내용은 [HoloLens에서 지원하는 Intune 업데이트 관리 기능](#intune-update-management-functions-that-hololens-supports)을 참조하세요.

> [!IMPORTANT]  
> Intune은 두 가지 업데이트 관리 정책 유형인 *Windows 10 업데이트 링* 과 *Windows 10 기능 업데이트* 를 제공합니다. Windows 10 기능 업데이트 정책 유형은 현재 공개 미리 보기에 있으며, HoloLens에 대해서는 지원되지 않습니다.
>  
> Windows 10 업데이트 링 정책을 사용하여 HoloLens 2 업데이트를 관리할 수 있습니다.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 또는 HoloLens(1세대)에 대한 업데이트 정책 구성

이 섹션에서는 HoloLens 2 또는 HoloLens(1세대) 업데이트를 관리하는 데 사용할 수 있는 정책에 대해 설명합니다. HoloLens 2 사용 가능한 기능에 대한 자세한 내용은 [HoloLens 2에 대한 업데이트 롤아웃 계획 및 구성](#plan-and-configure-update-rollouts-for-hololens-2)을 참조하세요.

[정책 CSP-업데이트](/windows/client-management/mdm/policy-csp-update)는 비즈니스용 Windows 업데이트를 구성하는 정책을 정의합니다.

> [!NOTE]  
> 특정 버전의 HoloLens에서 지원하는 특정 정책 CSP(구성 서비스 공급자) 목록은 [HoloLens 장치에서 지원하는 정책 CSP](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)를 참조하세요.

#### <a name="configure-automatic-checks-for-updates"></a>업데이트 자동 확인 구성

**Update/AllowAutoUpdate** 정책을 사용하여 업데이트 검색, 다운로드 및 설치와 같은 자동 업데이트 동작을 관리할 수 있습니다. 이 정책에 사용할 수 있는 설정에 대한 자세한 내용은 [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)를 참조하세요.

> [!NOTE]  
> Microsoft Intune에서 **자동 업데이트 동작** 을 사용하여 이 정책을 변경할 수 있습니다. 자세한 내용은 [Intune에서 Windows 10 소프트웨어 업데이트 관리](/intune/windows-update-for-business-configure)를 참조하세요.

#### <a name="configure-an-update-schedule"></a>업데이트 일정 구성

업데이트를 적용하는 방법과 시기를 구성하려면 다음 정책을 사용합니다.

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - 값: **0**~**7**(0 = 매일, 1 = 일요일, 7 = 토요일)
  - 기본값: **0**(매일)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - 값: 0~23(0 = 자정, 23 = 오후 11시)
  - 기본값: 오전 3시

#### <a name="configure-active-hours"></a>사용 시간 구성
[Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)부터 IT 관리자는 HoloLens 2 장치에 대해 활성 시간 범위를 지정할 수 있습니다.

사용 시간은 장치가 사용 중일 것으로 예상하는 시간을 나타냅니다. 업데이트 후 자동 다시 시작은 사용 시간이 아닐 때 수행됩니다. 지정된 범위는 사용 시간 시작 시간부터 계산됩니다. [MDM을 사용하여 사용 시간 구성](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm)에서 설명된 것처럼 MDM을 사용할 수 있습니다. MDM은 정책 CSP의 Update/ActiveHoursStart, Update/ActiveHoursEnd 및 Update/ActiveHoursMaxRange 설정을 사용하여 사용 시간을 구성합니다.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - 이 값은 종료 시간을 설정합니다. 시작 시간으로부터 최대 12시간까지 설정할 수 있습니다.
    -   0~23의 값이 지원되며 여기서 0은 오전 12시, 1은 오전 1시를 의미합니다.
    -   기본값은 17(오후 5시)입니다.
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - 이 값은 시작 시간으로부터 최대 사용 시간을 설정합니다.
    -   지원되는 값은 8~18입니다.
    -   기본값은 18(시간)입니다.
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) -이 값은 시작 시간을 설정합니다. 종료 시간으로부터 최대 12시간입니다.
    -   0~23의 값이 지원되며 여기서 0은 오전 12시, 1은 오전 1시를 의미합니다.
    -   기본값은 8(오전 8시)입니다.

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Windows 10 버전 1607만 실행하는 장치의 경우

다음 업데이트 정책을 사용하여 Windows 업데이트 대신 WSUS(Windows Server Update Service)에서 업데이트를 받을 장치를 구성할 수 있습니다.

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>HoloLens 2에 대한 업데이트 실행 계획 및 구성

HoloLens 2는 HoloLens(1세대)보다 더 많은 업데이트 자동화 기능을 지원합니다. Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트를 관리하는 경우에는 더 많이 적용받습니다. 이러한 기능을 사용하면 조직 전체에서 간편하게 업데이트 시행을 계획하고 구현할 수 있습니다.

#### <a name="plan-the-update-strategy"></a>업데이트 전략 계획

비즈니스용 Windows 업데이트는 지연 정책을 지원합니다. Microsoft에서 업데이트가 릴리스된 후 지연 정책을 사용하여 장치에 업데이트를 설치하기 전에 대기 기간을 정의할 수 있습니다. 다양한 지연 정책을 통해 장치의 하위 집합(*업데이트 링* 이라고도 함)을 연결하여 조직의 업데이트 시행 전략을 조정할 수 있습니다.

1,000개의 장치를 보유하고 있고 5가지 웨이브로 업데이트를 해야 하는 조직을 예로 들어보겠습니다. 조직은 다음 표에 표시된 대로 5개의 업데이트 링을 만들 수 있습니다.

|그룹 |디바이스 수 |지연(일) |
| ---| :---: | :---: |
|Grp 1(IT 직원) |5 |0 |
|Grp 2(얼리어답터) |50 |60 |
|Grp 3(기본 1) |250 |120 |
|Grp 4(기본 2) |300 |150 |
|Grp 5(기본 3) |395 |180 |

다음은 시간에 따라 전체 조직에서 출시가 진행되는 방식입니다.

![업데이트를 배포하기 위한 타임라인.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>업데이트 지연 정책 구성

지연 정책은 업데이트를 사용할 수 있게 된 날부터 해당 업데이트가 장치에 제공되는 날 사이의 일 수를 지정합니다.

기능 업데이트 및 품질 업데이트에 대해 서로 다른 지연을 구성할 수 있습니다. 다음 표에서는 각 유형에 사용할 특정 정책과 각 유형에 대한 최대 지연 기간을 보여줍니다.

|범주 |정책 |최대 지연 |
| --- | --- | --- |
|기능 업데이트 |DeferFeatureUpdatesPeriodInDays |365일 |
|품질 업데이트 |DeferQualityUpdatesPeriodInDays |30일 |

#### <a name="pause-updates-via-device"></a>장치를 통한 업데이트 일시 중지

사용자가 MDM에 액세스할 수 없는 경우 빌드 [Windows Holographic, 버전 2004](hololens-release-notes.md#windows-holographic-version-2004) 이상의 HoloLens 2 장치에서는 최대 35일 동안 수동으로 업데이트를 각각 일시 중지할 수 있습니다. 사용자는 **설정 > 업데이트 및 보안 > 고급 옵션** 으로 이동하여 이 설정에 도달한 후 **업데이트 일시 중지** 까지 아래로 스크롤하여 언제까지 업데이트를 일시 중지할지 날짜를 선택합니다. 사용자가 일시 중지 제한에 도달하면 장치에 새 업데이트를 설치해야 다시 일시 중지할 수 있습니다. 

[Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)부터 HoloLens 2 장치에 대해 이 일시 중지 업데이트 기능을 관리할 수 있습니다. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0(기본값) – 사용
    - 1 - 사용 안 함

#### <a name="intune-update-management-functions-that-hololens-supports"></a>HoloLens에서 지원하는 Intune 업데이트 관리 기능

다음 Intune 업데이트 관리 기능을 사용하여 HoloLens에 대한 업데이트를 관리할 수 있습니다.

- **만들기** 및 **할당**: 이 기능은 업데이트 링 목록에 Windows 10 업데이트 링을 추가합니다. 자세한 내용은 [업데이트 링 만들기 및 할당](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)을 참조하세요.

- **일시 중지**: 기능 또는 품질 업데이트를 배포할 때 문제가 발생하는 경우 업데이트를 35일(지정된 날짜부터 시작) 동안 일시 중지할 수 있습니다. 이 일시 중지를 수행하면 문제가 해결되거나 완화될 때까지 다른 장치에서 업데이트를 설치할 수 없습니다. 기능 업데이트를 일시 중지해도 장치 품질 업데이트는 계속 제공되기 때문에 계속해서 보안을 유지할 수 있습니다. 업데이트 형식이 일시 중지되면 해당 링의 [개요] 창에는 해당 업데이트 형식이 다시 시작되기 전에 남은 기간(일)이 표시됩니다. 지정된 시간이 경과되면 일시 중지가 자동으로 만료되고 업데이트 프로세스가 다시 시작됩니다.

  업데이트 링이 일시 중지된 상태에서 다음 옵션 중 하나를 선택할 수 있습니다.

  - **연장**: 업데이트 유형에 대해 35일간의 일시 중지 기간을 연장합니다.
  - **다시 시작**: 해당 링에 대한 업데이트를 활성 작업으로 복원합니다. 필요한 경우 업데이트 링을 다시 일시 중지할 수 있습니다.

  > [!NOTE]  
  > HoloLens 2 장치에서는 업데이트 링에 대한 **제거** 작업이 지원되지 않습니다.

### <a name="delivery-optimization-preview"></a>배달 최적화 미리 보기

[Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1)은 여러 HoloLens 장치에서 다운로드할 때 대역폭 사용량을 줄이기 위해 배달 최적화 설정에 대한 초기 미리 보기를 사용하도록 설정되어 있습니다. 이 기능과 권장되는 네트워크 구성에 대한 자세한 설명은 [Windows 10 업데이트에 대한 배달 최적화](/windows/deployment/update/waas-delivery-optimization)에서 제공됩니다.

다음 설정은 관리 화면의 일부로 사용하도록 설정되어 있으며 [Intune에서 구성할 수 있습니다](/mem/intune/configuration/delivery-optimization-settings).

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

이 미리 보기 제공에 대한 몇 가지 주의 사항:

- 이 미리 보기에서 HoloLens 지원은 OS 업데이트만으로 제한됩니다.
- Windows Holographic for Business는 HTTP 다운로드 모드 및 [Microsoft 연결된 캐시 엔드포인트](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)의 다운로드만 지원합니다. 현재 HoloLens 장치에서는 피어 투 피어 다운로드 모드 및 그룹 할당이 지원되지 않습니다.
- HoloLens는 Windows Server Update Services 엔드포인트에 대한 배포 또는 배달 최적화를 지원하지 않습니다.
- 문제를 해결하려면 연결된 캐시 서버에 대한 진단을 수행하거나 **설정** > **업데이트 및 보안** >  **문제 해결** >  **Windows 업데이트** 를 통해 HoloLens에서 HoloLens에 대한 추적을 수집해야 합니다.

## <a name="manually-check-for-updates"></a>수동으로 업데이트 확인

HoloLens가 정기적으로 시스템 업데이트를 확인하기 때문에 사용자가 수동으로 확인하고자 할 때도 있을 것입니다.

업데이트를 수동으로 확인하려면 **설정** > **업데이트 및 보안** > **업데이트 확인** 으로 이동합니다. 설정 앱에서 장치가 최신 상태로 나타나면 현재 사용 가능한 모든 업데이트를 사용 중인 것입니다.

## <a name="manually-roll-back-an-update"></a>수동으로 업데이트 롤백

경우에 따라 이전 버전의 HoloLens 소프트웨어로 되돌릴 수도 있습니다. HoloLens 2를 사용하는지 또는 HoloLens(1세대)를 사용하는지에 따라 해당 과정이 달라집니다.

### <a name="revert-to-a-previous-version-hololens-2"></a>이전 버전으로 되돌리기(HoloLens 2)

[고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)를 사용하여 HoloLens 2를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens 2로 돌아갈 수 있습니다.

> [!NOTE]
> 이전 버전으로 되돌리면 개인 파일과 설정이 삭제됩니다.

HoloLens 2의 이전 버전으로 되돌리려면 다음 단계를 따르세요.

1. 컴퓨터에 연결된 휴대폰 또는 Windows 장치가 없는지 확인합니다.
1. 컴퓨터의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)를 다운로드합니다.
1. [최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드합니다.
1. 이러한 다운로드가 완료되면 **파일 탐색기** > **다운로드** 를 열고 방금 다운로드한 압축(.zip) 폴더를 마우스 오른쪽 단추로 클릭한 다음 **Extract all** > **Extract** 를 선택하여 파일을 확장합니다.
1. USB-A나 USB-C 케이블을 사용하여 컴퓨터에 HoloLens 장치를 연결합니다. 그동안 다른 케이블을 사용하여 HoloLens를 연결했더라도 이 케이블이 가장 적합합니다.
1. 고급 복구 도우미는 HoloLens 장치를 자동으로 감지합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 **Manual package selection** 을 선택하고 이전에 확장한 폴더를 엽니다.
1. 설치(.ffu) 파일을 선택합니다.
1. **소프트웨어 설치** 를 선택한 다음 지침을 따릅니다.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>이전 버전으로 되돌리기(HoloLens(1세대))

[WDRT(Windows Device Recovery Tool)](https://support.microsoft.com/help/12379)를 사용하여 HoloLens(1세대)를 이전 버전으로 다시 설정하여 업데이트를 롤백하고 이전 버전의 HoloLens로 돌아갈 수 있습니다.

> [!NOTE]
> 이전 버전의 HoloLens로 되돌리면 개인 파일과 설정이 삭제됩니다.

HoloLens(1세대)의 이전 버전으로 되돌리려면 다음 단계를 따르세요.

1. 컴퓨터에 연결된 휴대폰 또는 Windows 장치가 없는지 확인합니다.
1. 컴퓨터에서 [WDRT(Windows Device Recovery Tool)](https://support.microsoft.com/help/12379)를 다운로드합니다.
1. [HoloLens 1주년 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드합니다.
1. 다운로드가 완료되면 **파일 탐색기** > **다운로드** 를 열고 방금 다운로드한 압축(.zip) 폴더를 마우스 오른쪽 단추로 클릭한 다음 **Extract all** > **Extract** 를 선택하여 파일을 확장합니다.
1. Hololens 장치와 함께 제공된 마이크로 USB 케이블을 사용하여 HoloLens 장치를 컴퓨터에 연결합니다. 그동안 다른 케이블을 사용하여 HoloLens를 연결했더라도 이 케이블이 가장 적합합니다.
1. WDRT는 HoloLens 장치를 자동으로 감지합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 **Manual package selection** 을 선택하고 이전에 확장한 폴더를 엽니다.
1. 설치(.ffu) 파일을 선택합니다.
1. **소프트웨어 설치** 를 선택한 다음 지침을 따릅니다.

**WDRT에서 장치를 감지하지 않는 경우**

WDRT에서 HoloLens 장치를 자동으로 감지하지 않으면 컴퓨터를 다시 시작해보세요. 그래도 작동하지 않으면 **My device was not detected** 를 선택하고 **Microsoft HoloLens** 를 선택한 후 지침을 따릅니다.

## <a name="related-articles"></a>관련 문서

- [HoloLens 2 릴리스 정보](hololens-release-notes.md)
- [비즈니스용 Windows 업데이트란 무엇인가요?](/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 업데이트용 서비스 채널에 장치 할당](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune에서 Windows 10 소프트웨어 업데이트 관리](/mem/intune/protect/windows-update-for-business-configure)
