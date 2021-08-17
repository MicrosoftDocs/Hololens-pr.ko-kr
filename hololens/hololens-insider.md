---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: Insider 빌드를 시작 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 귀중 한 피드백을 제공 하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 86a763adb233b45242182d069a56692aeddc2e59
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858576"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens에 대한 참가자 미리 보기

HoloLens에 대 한 최신 Insider Preview 빌드를 시작 합니다. 간단 하 게 [시작](hololens-insider.md#start-receiving-insider-builds) 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 유용한 피드백을 제공할 수 있습니다.

## <a name="windows-insider-release-notes"></a>Windows 참가자 릴리스 정보

새 기능을 시작 하 여 참가자를 다시 Windows 하 고 있습니다. 새 빌드는 최신 업데이트에 대 한 개발 및 베타 채널에 대 한 플 라이팅 받게 됩니다. Windows Insider 빌드에 더 많은 기능과 업데이트를 추가 하므로이 페이지를 계속 업데이트할 예정입니다. 이러한 업데이트를 현실에 맞게 혼합할 수 있습니다.

| 기능                 | 설명                | 사용자 또는 시나리오 | 빌드 도입 |
|-------------------------|----------------------------|--------------|------------------|
| [보고 HoloLens 세부 정보에 대 한 CSP 변경 내용](#csp-changes-for-reporting-hololens-details) | 에서 데이터를 쿼리 하는 새 Csp | IT 관리자    | 20348.1403                 |
| [CSP에서 자동 로그인 정책을 제어 합니다.](#auto-login-policy-controlled-by-csp) | 계정에 자동으로 로그인 하는 데 사용 됩니다. | IT 관리자 | 20348.1405 |
| [향상 된 업데이트 다시 시작 검색 및 알림](#improved-update-restart-detection-and-notifications) | 업데이트에 대 한 새로운 사용 정책 및 UX. | IT 관리자 | 20348.1405 |
| [인증서 관리자에 대 한 PFX 파일 지원](#pfx-file-support-for-certificate-manager) | 설정 UI를 통해 PFX 인증서 추가 | 최종 사용자 | 20348.1405 |
| [앱 업데이트에 대 한 스마트 재시도](#smart-retry-for-app-updates) | IT 관리자가 앱을 업데이트 하기 위해 예약 된 다시 시도를 허용 합니다. | IT 관리자 | 20348.1405 |
| [HoloLens에서 설정 고급 진단 보고서 보기](#view-advanced-diagnostic-report-in-settings-on-hololens) | 장치에서 MDM 진단 로그 보기 | 문제 해결 | 20348.1405 |
| [오프 라인 진단 알림](#offline-diagnostics-notifications) | 로그 수집에 대 한 오디오 시각적 피드백 | 문제 해결 | 20348.1405 |
| [Microsoft Store에 대해서만 개인 저장소 앱 사용](#use-only-private-store-apps-for-microsoft-store) | 조직의 앱만 표시 하도록 스토어 앱 구성 | IT 관리자 | 20348.1408 |
| [저장소 로그 수집 기능이 향상 되었습니다.](#low-storage-log-collection-improvements) | 낮은 저장소 상황에서 로그 수집 시나리오에 대 한 향상 된 기능 | IT 관리자 | 20348.1412 |
| [플랫폼 모드 이동](#moving-platform-mode) | 는 구성 된 경우 동적 이동이 발생 하는 대량 해병대 용기에 HoloLens 2를 사용할 수 있도록 하는 플랫폼 모드 베타 이동 기능을 도입 했습니다. | 모두 | 20348.1411 |
| [수정 사항 및 향상 된 기능](#fixes-and-improvements) | HoloLens에 대 한 수정 및 개선 사항 | 모두 | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>보고 HoloLens 세부 정보에 대 한 CSP 변경 내용

- Windows Insider build, 20348.1403에 도입 되었습니다.

다음 csp는 HoloLens 장치에서 정보를 보고 하는 새로운 방법으로 업데이트 되었습니다.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP-무료 Storage

이제 devdetail CSP는 HoloLens 장치에서 사용 가능한 저장소 공간을 보고 합니다. 이는 설정 앱의 Storage 페이지에 표시 된 값과 거의 일치 해야 합니다. 다음은이 정보를 포함 하는 특정 노드입니다.

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 작업에만 해당)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP-SSID 및 BSSID

DeviceStatus CSP는 HoloLens 현재 연결 되어 있는 Wi-Fi 네트워크의 SSID 및 BSSID도 보고 합니다. 다음은이 정보를 포함 하는 특정 노드입니다.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi 어댑터의 mac 주소 (*/ssid)
- Wi-Fi 어댑터/Bssid의./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac 주소*

NetworkIdentifiers (MDM 공급 업체) 예제를 통해 NetworkIdentifiers 쿼리

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>CSP에서 자동 로그인 정책을 제어 합니다.

이 새 AutoLogonUser 정책은 사용자가 자동으로 로그인 되는지 여부를 제어 합니다. 일부 고객은 id에 연결 되었지만 로그인 환경을 원하지 않는 장치를 설정 하려고 합니다. 장치를 선택 하 고 원격 지원을 즉시 사용할 Imagine. 또는 HoloLens 장치를 신속 하 게 배포 하 고 최종 사용자가 신속 하 게 로그인 할 수 있도록 하는 이점을 누릴 수 있습니다.

정책이 비어 있지 않은 값으로 설정 된 경우 자동 로그온 사용자의 전자 메일 주소를 지정 합니다. 자동 로그온을 사용 하려면 지정 된 사용자가 한 번 이상 장치에 로그온 해야 합니다.

새 정책 문자열 값의 OMA-URI입니다. `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 동일한 전자 메일 주소를 가진 사용자는 자동 로그온을 사용 하도록 설정 합니다.

이 정책이 구성 된 장치에서 정책에 지정 된 사용자가 한 번 이상 로그온 해야 합니다. 첫 번째 로그온 후 장치를 다시 부팅 하면 지정 된 사용자가 자동으로 로그온 됩니다. 단일 자동 로그온 사용자만 지원 됩니다. 사용 하도록 설정 되 면 자동으로 로그온 한 사용자는 수동으로 로그 아웃할 수 없습니다. 다른 사용자로 로그온 하려면 먼저 정책을 사용 하지 않도록 설정 해야 합니다.

> [!NOTE]
>
> - 주 OS 업데이트와 같은 일부 이벤트의 경우에는 지정 된 사용자가 자동 로그온 동작을 다시 시작 하기 위해 장치에 다시 로그온 해야 할 수 있습니다.
> - 자동 로그온은 MSA 및 AAD 사용자에 대해서만 지원 됩니다.

### <a name="improved-update-restart-detection-and-notifications"></a>향상 된 업데이트 다시 시작 검색 및 알림

활성 시간과 설치 시간 정책 사이에 사용 중일 때 HoloLens 장치가 다시 부팅 되는 것을 방지할 수 있습니다. 그러나 필요한 업데이트의 설치를 완료 하기 위해 다시 부팅이 발생 하지 않는 경우 업데이트 채택을 지연 시킬 수도 있습니다. 이제 최종 기한을 적용 하 고 다시 부팅 하는 데 사용할 수 있는 정책을 추가 하 고 업데이트 설치가 적시에 완료 되도록 합니다. 다시 부팅을 시작 하기 전에 사용자에 게 알릴 수 있으며 IT 정책에 따라 다시 부팅을 연기할 수 있습니다.

다음 업데이트 정책이 추가 되었습니다.

- [업데이트/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [업데이트/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [업데이트/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [업데이트/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [업데이트/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="pfx-file-support-for-certificate-manager"></a>인증서 관리자에 대한 PFX 파일 지원

Windows Insider 빌드 20348.1405에 도입되었습니다. 이제 .pfx 인증서를 사용할 수 있도록 [인증서 관리자에](certificate-manager.md) 대한 지원이 추가되었습니다. 사용자가 **설정** 업데이트 & 보안 인증서 로 이동하고  >    >   **인증서 설치를** 선택하면 이제 UI에서 .pfx 인증서 파일을 지원합니다.
사용자는 프라이빗 키가 있는 .pfx 인증서를 사용자 저장소 또는 컴퓨터 저장소로 가져올 수 있습니다.

### <a name="smart-retry-for-app-updates"></a>앱 업데이트에 대한 스마트 다시 시도

이제 HoloLens 사용하도록 설정된 것은 IT 관리자가 업데이트를 적용할 수 있는 앱 사용 중으로 인해 업데이트가 실패한 앱을 다시 시작하기 위해 되풀이 또는 한 번 날짜를 설정할 수 있도록 하는 새로운 정책입니다. 예약된 시간 또는 로그인과 같은 몇 가지 다른 트리거에 따라 설정할 수 있습니다. 이 정책을 사용하는 방법에 대한 자세한 내용은 [ApplicationManagement/ScheduleForceRestartForUpdateFailures 를 확인하세요.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens 설정 고급 진단 보고서 보기

동작 문제를 해결할 때 관리되는 디바이스의 경우 예상되는 정책 구성이 적용되는지 확인하는 것이 중요한 단계입니다. 이전에는 이 새로운 기능을 사용하려면 MDM을 통해 디바이스에서 또는 디바이스 근처에서 수행되어야 했습니다. **이** 작업은 설정 계정을 통해 수집된 MDM 진단 로그를 내보낸 후 작업 또는 학교 에  ->    >  **액세스하고** **관리 로그 내보내기를** 선택하여 주변 PC에서 볼 수 있었습니다.

이제 Edge 브라우저를 사용하여 디바이스에서 MDM 진단을 볼 수 있습니다. MDM 진단 보고서를 더 쉽게 보려면 작업 또는 학교 액세스 페이지로 이동하고 **고급 진단 보고서 보기를** 선택합니다. 그러면 새 Edge 창에서 보고서가 생성되고 열립니다.

![설정 앱에서 고급 진단 보고서를 봅니다.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>오프라인 진단 알림

오프라인 진단이라는 기존 기능에 대한 [업데이트입니다.](hololens-diagnostic-logs.md#offline-diagnostics) 이전에는 사용자에게 진단 수집을 트리거했거나 완료되었다는 명확한 표시기가 없었습니다.
이제 Windows Insider 빌드에 추가되었습니다. 오프라인 진단에 대한 두 가지 형태의 시청각 피드백이 있습니다. 첫 번째는 컬렉션이 시작되고 완료될 때 둘 다에 대해 표시되는 알림 메시지입니다. 사용자가 로그인하고 시각적 개체를 가지고 있을 때 표시됩니다.

![로그를 수집하기 위한 알림입니다.](./images/logcollection1.jpg)

![로그 수집이 완료되면 알림 메시지입니다.](./images/logcollection2.jpg)

사용자가 디스플레이에 액세스할 수 없거나 로그인할 수 없거나 여전히 OOBE에 있는 경우 오프라인 진단을 대체 로그 수집 메커니즘으로 사용하기 때문에 로그가 수집될 때 오디오 큐가 재생됩니다. 이 소리는 알림 메시지 외에도 재생됩니다.

이 새로운 기능은 디바이스가 업데이트될 때 사용하도록 설정되며 사용하도록 설정하거나 관리하지 않아도 됩니다. 이 새 피드백을 표시하거나 들어 볼 수 없는 경우에도 오프라인 진단이 계속 생성됩니다.

이 새로운 오디오 피드백 추가를 통해 진단 데이터를 더 쉽게 수집하고 문제를 보다 신속하게 해결할 수 있기를 바랍니다.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store 프라이빗 스토어 앱만 사용

RequirePrivateStoreOnly 정책이 HoloLens 사용하도록 설정되었습니다. 이 정책을 사용하면 Microsoft Store 앱이 조직에 대해 구성된 프라이빗 저장소만 표시하도록 구성할 수 있습니다. 사용 가능하게 만든 앱에 대한 액세스만 제한합니다.

[ApplicationManagement/RequirePrivateStoreOnly에](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) 대해 자세히 알아보기

### <a name="low-storage-log-collection-improvements"></a>낮은 스토리지 로그 수집 개선

진단 로그를 수집할 때 디바이스의 디스크 공간이 부족한 것으로 보이는 시나리오에서는 **StorageDiagnostics.zip** 라는 추가 보고서가 만들어집니다. 낮은 스토리지의 임계값은 Windows 스토리지에 의해 자동으로 [결정됩니다.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>플랫폼 모드 이동

참가자 **빌드 20348.1411을** 기준으로 HoloLens 2 저동적 동작 이동 플랫폼을 추적하기 위한 베타 지원이 추가되었습니다. 빌드를 설치하고 플랫폼 모드 이동을 사용하도록 설정하면 대형 배 및 대형 배선과 같이 이전에 액세스할 수 없었던 환경에서 HoloLens 2 사용할 수 있습니다. 현재 이 기능은 이러한 특정 이동 플랫폼만 사용하도록 설정하는 것을 목표로 합니다. 다른 환경에서 이 기능을 사용할 수 있는 것은 없지만, 이 기능은 먼저 이러한 환경에 대한 지원을 추가하는 데 중점을 두고 있습니다.

지원되는 기능 및 이 새로운 기능을 사용하도록 설정하는 방법에 대한 자세한 내용은 [이동 플랫폼 페이지를 방문하세요.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>수정 및 개선

- 잠긴 [파일을 다운로드하라는 프롬프트가 없는 장치 포털 대해 알려진 문제를 해결했습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 파일 [업로드 및 다운로드 시간 장치 포털 알려진 문제가 해결되었습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- HoloLens 디바이스의 준수 속성 보고와 관련된 문제를 해결합니다. 참가자 빌드에서 올바른 보고를 트리거하려면 다시 부팅해야 할 수 있습니다.  
- 앱이 HoloLens 로그인한 사용자의 키오스크 모드에서 HoloLens 실행 중인지 확인할 수 있도록 [할당된 액세스 API를](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) 사용하도록 설정했습니다.
- 새 플래시에 설치된 Remote Assist 첫 번째 버전이 업데이트되었습니다.

## <a name="start-receiving-insider-builds"></a>참가자 빌드 수신 시작

> [!NOTE]
> 최근에 업데이트하지 않은 경우 디바이스를 다시 부팅하여 상태를 업데이트하고 최신 빌드를 받으세요.
>
> - "디바이스 다시 부팅" 음성 명령이 제대로 작동합니다.
> - 설정/Windows 참가자 프로그램 다시 시작 단추를 선택할 수도 있습니다.
>
> 발생한 백 엔드에 버그가 있으므로 다시 추적할 수 있습니다.

HoloLens 2 디바이스에서 설정 업데이트   >  **& 보안** Windows 참가자 프로그램 이동하여  >   **시작을** 선택합니다. Windows 참가자로 등록하는 데 사용한 계정을 연결합니다.

Windows 참가자는 이제 채널로 이동하고 있습니다. **빠른** 링이 **개발 채널이** **되고, 느린** 링이 **베타 채널** 되고, 릴리스 **미리 보기** 링이 릴리스 미리 **보기 채널** 이 됩니다. 매핑은 다음과 같습니다.

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개를](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 참조하세요.
그런 다음, **Windows 활성 개발을** **선택하고, 개발 채널** 또는 **베타 채널** 빌드를 받을지 선택하고, 프로그램 용어를 검토합니다.
**확인을 > 지금 다시 시작을** 선택하여 완료합니다. 디바이스가 다시 부팅된 후 설정 > 업데이트 & 보안 > 업데이트 확인으로 이동하여 최신 빌드를 **확인합니다.**

### <a name="update-error-0x80070490-work-around"></a>업데이트 오류 0x80070490 해결

Dev 또는 Beta 채널에서 업데이트할 때 업데이트 오류 0x80070490 발생하는 경우 다음과 같은 단기 해결을 시도합니다. 여기에는 참가자 채널을 이동하고, 업데이트를 선택하고, 참가자 채널을 다시 이동하는 작업이 포함됩니다.

#### <a name="stage-one---release-preview"></a>1단계 - 릴리스 미리 보기

1. 설정 & 보안을 업데이트하고 Windows 참가자 프로그램 **릴리스 미리 보기 채널을** 선택합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트, **업데이트 확인.** 업데이트 후 2단계로 계속 진행합니다.

#### <a name="stage-two---dev-channel"></a>2단계 - 개발 채널

1. 설정 & 보안을 업데이트하고 Windows 참가자 프로그램 **개발 채널을** 선택합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트, **업데이트 확인.**

## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 방향

비행 서명 ffu를 사용하여 테스트하려면 먼저 항공편 서명 ffu를 플래시하기 전에 디바이스의 잠금을 해제해야 합니다.

1. On PC:
    1. 에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.

    1. Microsoft Store ARC(고급 복구 도우미)를 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 설치합니다.

1. HoloLens - 플라이트 잠금 해제: **설정** 업데이트 & 보안 Windows 참가자 프로그램 연  >    >   다음 등록하고 디바이스를 다시 부팅합니다.

1. Flash FFU - 이제 ARC를 사용하여 비행 서명된 FFU를 플래시할 수 있습니다.

### <a name="provide-feedback-and-report-issues"></a>피드백 제공 및 문제 보고

HoloLens [피드백 허브 앱을](hololens-feedback.md) 사용하여 피드백을 제공하고 문제를 보고하세요. 피드백 허브 사용하면 엔지니어가 문제를 신속하게 디버그하고 해결할 수 있도록 필요한 진단 정보가 모두 포함됩니다.  중국어 및 일본어 버전의 HoloLens 문제는 동일한 방식으로 보고되어야 합니다.

> [!NOTE]
> Documents 폴더에 액세스하도록 피드백 허브 여부를 묻는 프롬프트를 수락해야 합니다(메시지가 표시되면 **예** 선택).

## <a name="note-for-developers"></a>개발자를 위한 참고 사항

HoloLens 참가자 빌드를 사용하여 애플리케이션을 개발하는 것이 좋습니다.  [HoloLens 개발자 설명서를](https://developer.microsoft.com/windows/mixed-reality/development) 확인하여 시작하세요. 이러한 동일한 지침은 HoloLens 참가자 빌드에서 작동합니다.  HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio 동일한 빌드를 사용할 수 있습니다.

## <a name="stop-receiving-insider-builds"></a>참가자 빌드 수신 중지

더 이상 Windows Holographic의 참가자 빌드를 수신하지 않으려는 경우 HoloLens 프로덕션 빌드를 실행할 때 옵트아웃하거나 고급 복구 도우미를 사용하여 [디바이스를](hololens-recovery.md) 비인더 버전의 Windows Holographic으로 복구할 수 있습니다.

> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 취소하는 사용자에게 파란색 화면이 발생하는 알려진 문제가 있습니다. 그런 다음 디바이스를 수동으로 복구해야 합니다. 영향을 받을지 여부에 대한 자세한 내용은 이 [알려진 문제](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)에 대한 자세한 내용을 확인하세요.

HoloLens 프로덕션 빌드를 실행하고 있는지 확인하려면 다음을 수행합니다.

1. **설정 > System > 정보** 로 이동 하 여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.

참가자 빌드를 옵트아웃 (opt out) 하려면 다음을 수행 합니다.

1. 프로덕션 빌드를 실행 하는 HoloLens에서 **설정 > 업데이트 & 보안 > insider Program** 로 이동 하 여 insider build **중지** 를 선택 합니다.

1. 지침에 따라 장치를 옵트아웃 합니다.
