---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: 참가자 빌드를 시작하고 HoloLens 대한 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공하는 방법을 알아봅니다.
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
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b865f9f9a9a734ef6a6c6419fc523049e925d5f8
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189480"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens에 대한 참가자 미리 보기

HoloLens 위한 최신 Insider Preview 빌드를 시작합니다. HoloLens 대한 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 [간단하게 시작하고](hololens-insider.md#start-receiving-insider-builds) 제공할 수 있습니다.

## <a name="windows-insider-release-notes"></a>Windows 참가자 릴리스 정보

새로운 기능을 Windows 참가자에게 다시 플라이팅을 시작하게 되어 기쁩니다. 새 빌드는 최신 업데이트를 위해 개발 및 베타 채널로 플라이팅됩니다. Windows 참가자 빌드에 더 많은 기능 및 업데이트를 추가함에 따라 이 페이지를 계속 업데이트할 예정입니다. 이러한 업데이트를 현실에 혼합할 준비가 되어 있습니다.

향상된 문제 해결 및 디바이스 보고서, 키오스크 모드 및 인증서 뷰어의 일부 수정된 버그, 확장된 관리 기능 표면 및 향상된 업데이트 안정성에 대한 것입니다. HoloLens 출시될 이 기능 업데이트의 새로운 주력 기능은 이동 플랫폼 모드입니다. HoloLens 2 위한 새로운 훌륭한 기능을 모두 확인하세요.

| 기능                 | 설명                | 사용자 또는 시나리오 | 빌드 소개 |
|-------------------------|----------------------------|--------------|------------------|
| [플랫폼 모드 이동](#moving-platform-mode) | 구성된 경우 동적이 낮은 동작이 발생하는 대형 배선에서 HoloLens 2 사용할 수 있도록 하는 이동 플랫폼 모드 베타가 도입되었습니다. | 모두 | 20348.1411 |
| [인증서 관리자에 대한 PFX 파일 지원](#pfx-file-support-for-certificate-manager) | 설정 UI를 통해 PFX 인증서 추가 | 최종 사용자 | 20348.1405 |
| [HoloLens 설정 고급 진단 보고서 보기](#view-advanced-diagnostic-report-in-settings-on-hololens) | 디바이스에서 MDM 진단 로그 보기 | 문제 해결 | 20348.1405 |
| [오프라인 진단 알림](#offline-diagnostics-notifications) | 로그 수집에 대한 시청각 피드백 | 문제 해결 | 20348.1405 |
| [낮은 스토리지 로그 수집 개선](#low-storage-log-collection-improvements) | 스토리지 부족 상황에서 로그 수집 시나리오가 개선되었습니다. | 문제 해결 | 20348.1412 |
| [HoloLens 세부 정보를 보고하기 위한 CSP 변경 내용](#csp-changes-for-reporting-hololens-details) | 데이터를 쿼리하는 에 대한 새 CSP | IT 관리자    | 20348.1403                 |
| [CSP에서 제어하는 자동 로그인 정책](#auto-login-policy-controlled-by-csp) | 자동으로 계정에 로그인하는 데 사용 | IT 관리자 | 20348.1405 |
| [향상된 업데이트 다시 시작 검색 및 알림](#improved-update-restart-detection-and-notifications) | 업데이트에 사용할 수 있는 새 정책 및 UX입니다. | IT 관리자 | 20348.1405 |
| [앱 업데이트에 대한 스마트 다시 시도](#smart-retry-for-app-updates) | IT 관리자가 앱을 업데이트하도록 예약된 재시도를 허용합니다. | IT 관리자 | 20348.1405 |
| [프라이빗 스토어 앱만 Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 조직의 앱만 표시하도록 스토어 앱 구성 | IT 관리자 | 20348.1408 |
| [WDAC 및 LOB 앱 사용](#use-wdac-and-lob-apps) | IT 관리자가 자신의 앱을 사용하고 WDAC를 사용하여 다른 앱을 차단할 수 있습니다. | IT 관리자 | 20348.1405 |
| [수정 및 개선](#fixes-and-improvements) | HoloLens 대한 수정 및 개선 | 모두 | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT 관리자 참가자 기능 검사 목록

✔️ 자동으로 로그인하도록 단일 Azure AD 계정을 설정하려면 [이 새 CSP를 구성합니다.](#auto-login-policy-controlled-by-csp) <br>
✔️ 업데이트에 실패한 후 자동으로 업데이트를 시도하도록 앱을 구성하려면 [스마트 재시도를 위해 이 새 CSP를 설정합니다.](#smart-retry-for-app-updates) <br>
✔️ OS 업데이트를 보다 세밀하게 제어하려면 새로 사용하도록 설정된 [업데이트 정책을 확인하세요.](#improved-update-restart-detection-and-notifications) <br>
✔️ Microsoft Store 통해 회사 스토어에서 조직의 앱을 사용할 수 있도록 해야 하지만 전체 저장소가 아닌 조직의 앱에 대한 액세스만 허용하려면 [이 정책을 설정합니다.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ HoloLens 디바이스의 사용 가능 스토리지 공간, SSID 또는 BSSID를 확인하려면 이러한 [보고 CSP를 확인하세요.](#csp-changes-for-reporting-hololens-details) <br>
✔️ WDAC를 사용하여 앱 또는 프로세스의 시작을 차단하지만 고유한 앱을 사용해야 하는 경우 이제 [WDAC 정책 에서 LOB를 허용할](#use-wdac-and-lob-apps)수 있습니다.

### <a name="moving-platform-mode"></a>플랫폼 모드 이동

참가자 **빌드 20348.1411을** 기준으로 HoloLens 2 저동적 동작 이동 플랫폼을 추적하기 위한 베타 지원이 추가되었습니다. 빌드를 설치하고 플랫폼 모드 이동을 사용하도록 설정하면 대형 배 및 대형 배선과 같이 이전에 액세스할 수 없었던 환경에서 HoloLens 2 사용할 수 있습니다. 현재 이 기능은 이러한 특정 이동 플랫폼만 사용하는 것을 목표로 합니다. 다른 환경에서 기능을 사용해도 무방하지만, 이 기능은 우선 이러한 환경에 대한 지원을 추가하는 데 중점을 둡니다.

지원되는 기능 및 이 새로운 기능을 사용하도록 설정하는 방법에 대한 자세한 내용은 [이동 플랫폼 페이지를 방문하세요.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>인증서 관리자에 대한 PFX 파일 지원

Windows Insider 빌드 20348.1405에 도입되었습니다. 이제 .pfx 인증서를 사용할 수 있도록 [인증서 관리자에](certificate-manager.md) 대한 지원이 추가되었습니다. 사용자가 **설정** 업데이트 & 보안 인증서 로 이동하고  >    >   **인증서 설치를** 선택하면 이제 UI에서 .pfx 인증서 파일을 지원합니다.
사용자는 프라이빗 키가 있는 .pfx 인증서를 사용자 저장소 또는 컴퓨터 저장소로 가져올 수 있습니다.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens 설정 고급 진단 보고서 보기

동작 문제를 해결할 때 관리되는 디바이스의 경우 예상되는 정책 구성이 적용되는지 확인하는 것이 중요한 단계입니다. 이전에는 이 새로운 기능을 사용하려면 MDM을 통해 디바이스에서 또는 디바이스 근처에 있는 계정 액세스 설정 통해 수집된 MDM 진단 로그를 내보낸 후 디바이스에서 이 정보를 확인하고  ->    >  관리 **로그 내보내기를** 선택하여 주변 PC에서 볼 수 있었습니다.

이제 Edge 브라우저를 사용하여 디바이스에서 MDM 진단을 볼 수 있습니다. MDM 진단 보고서를 보다 쉽게 보려면 작업 또는 학교 액세스 페이지로 이동하고 **고급 진단 보고서 보기를** 선택합니다. 그러면 새 Edge 창에서 보고서가 생성되고 열립니다.

![설정 앱에서 고급 진단 보고서를 봅니다.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>오프라인 진단 알림

오프라인 진단이라는 기존 기능에 대한 [업데이트입니다.](hololens-diagnostic-logs.md#offline-diagnostics) 이전에는 사용자에게 진단 수집을 트리거했거나 완료되었다는 명확한 표시기가 없었습니다.
이제 Windows 참가자 빌드에 추가되었습니다. 오프라인 진단에 대한 두 가지 형태의 시청각 피드백이 있습니다. 첫 번째는 컬렉션이 시작되고 완료될 때 둘 다에 대해 표시되는 알림 메시지입니다. 사용자가 로그인하고 시각적 개체를 가지고 있을 때 표시됩니다.

![로그를 수집하기 위한 알림입니다.](./images/logcollection1.jpg)

![로그 수집이 완료되면 알림 메시지입니다.](./images/logcollection2.jpg)

사용자가 디스플레이에 액세스할 수 없거나 로그인할 수 없거나 여전히 OOBE에 있는 경우 오프라인 진단을 대체 로그 수집 메커니즘으로 사용하기 때문에 로그가 수집될 때 오디오 큐가 재생됩니다. 이 소리는 알림 메시지 외에도 재생됩니다.

이 새로운 기능은 장치를 업데이트할 때 사용할 수 있으며, 사용 하거나 관리 하지 않아도 됩니다. 이 새로운 피드백을 표시 하거나 듣지 못할 경우 오프 라인 진단이 계속 생성 됩니다.

이 새로운 고급 시각적 피드백 추가를 사용 하 여 진단 데이터를 수집 하는 것이 더 쉽고 신속 하 게 문제를 해결할 수 있습니다.

### <a name="low-storage-log-collection-improvements"></a>저장소 로그 수집 기능이 향상 되었습니다.

진단 로그가 수집 될 때 장치의 디스크 공간이 부족 한 경우에는 **StorageDiagnostics.zip** 이라는 추가 보고서가 만들어집니다. 저장소의 임계값은 [저장소 센스](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)Windows 의해 자동으로 결정 됩니다.

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
- [업데이트/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>앱 업데이트에 대 한 스마트 재시도

현재 HoloLens에 대해 사용 하도록 설정 된 새 정책을 사용 하면 IT 관리자가 앱을 사용 하 여 업데이트를 적용 하 여 업데이트를 적용할 수 있는 앱을 다시 시작 하도록 되풀이 또는 한 시간 날짜를 설정할 수 있습니다. 예약 된 시간 또는 로그인과 같은 몇 가지 다른 트리거를 기반으로 설정할 수 있습니다. 이 정책을 사용 하는 방법에 대 한 자세한 내용은 [Applicationmanagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)를 참조 하세요.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store에 대 한 개인 저장소 앱만 사용

HoloLens에 대해 RequirePrivateStoreOnly 정책을 사용 하도록 설정 했습니다. 이 정책을 사용 하면 조직에 대해 구성 된 개인 저장소만 표시 하도록 Microsoft Store 앱을 구성할 수 있습니다. 사용 가능한 앱에 대 한 액세스만 제한 합니다.

[Applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) 에 대 한 자세한 정보

### <a name="use-wdac-and-lob-apps"></a>WDAC 및 LOB 앱 사용

이제 WDAC를 사용 하 여 앱 또는 프로세스가 시작 되지 않도록 차단 하 고 계속 해 서 bushiness 앱의 줄을 사용할 수 있습니다. 이제 WDAC 정책에서 허용할 수 있습니다. 이 정책을 사용 하려면 WDAC 정책을 만들 때 PowerShell에서 추가 코드 줄을 실행 해야 합니다. [여기에서 단계를 검토 합니다.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>수정 사항 및 향상 된 기능

- [잠긴 파일 다운로드 프롬프트가 없는 장치 포털의 알려진 문제를 수정 했습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [파일 업로드 및 다운로드 시간 제한이 있는 장치 포털의 알려진 문제를 수정 했습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- HoloLens 장치에서 준수 속성을 보고 하는 문제를 해결 합니다. 올바른 보고가 Insider 빌드에서 트리거되도록 하려면 다시 부팅 해야 할 수 있습니다.  
- 앱이 HoloLens에 로그인 한 사용자에 대해 키오스크 모드에서 HoloLens 실행 되 고 있는지 확인할 수 있도록 [할당 된 액세스 API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) 를 사용 하도록 설정 되었습니다.
- 새 깜박이에 설치 된 원격 지원의 기본 버전을 업데이트 했습니다.

## <a name="start-receiving-insider-builds"></a>Insider 빌드 수신을 시작 합니다.

> [!NOTE]
> 최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.
>
> - "장치 다시 부팅" 음성 명령은 제대로 작동 합니다.
> - 설정/Windows Insider Program에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 사용자가 발생 시킨 백 엔드에 대 한 버그가 있었으며이로 인해 다시 추적할 수 있습니다.

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** 로 이동 하 고 **시작** 을 선택 합니다. Windows Insider로 등록 하는 데 사용한 계정을 연결 합니다.

이제 Windows insider가 채널로 이동 하 고 있습니다. **빠른** 링은 **Dev 채널이** 되 고, **저속** 링은 **베타 채널이** 되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이** 됩니다. 매핑은 다음과 같습니다.

![Windows 참가자 채널 설명입니다.](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그의 [Windows Insider 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.
그런 다음 **Windows의 활성 개발** 을 선택 하 고 **개발 채널** 또는 **베타 채널** 빌드를 받을지 여부를 선택한 후 프로그램 용어를 검토 합니다.
확인을 선택 하 **> 지금 다시 시작** 하 여 완료 합니다. 장치를 다시 부팅 한 후 설정으로 이동 하 **> 업데이트 & 업데이트 > 업데이트를 확인** 하 여 최신 빌드를 가져옵니다.

### <a name="update-error-0x80070490-work-around"></a>업데이트 오류 0x80070490 문제 해결

Dev 또는 Beta 채널에서 업데이트할 때 0x80070490 업데이트 오류가 발생 하는 경우 다음과 같은 단기 해결 방법을 시도해 보세요. 여기에는 insider channel을 이동 하 고, 업데이트를 선택한 다음, Insider channel을 다시 이동 하는 작업이 포함 됩니다.

#### <a name="stage-one---release-preview"></a>1 단계 릴리스 미리 보기

1. 설정, 업데이트 & 보안, Windows Insider Program, **Release preview 채널** 을 차례로 선택 합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트 **업데이트를 확인** 합니다. 업데이트 후 2 단계를 계속 진행 합니다.

#### <a name="stage-two---dev-channel"></a>2 단계 개발자 채널

1. 설정, 업데이트 & 보안, Windows Insider Program에서 **Dev Channel** 을 선택 합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트 **업데이트를 확인** 합니다.

## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 방향

비행 서명 된 ffu로 테스트 하려면 비행 서명 된 ffu를 깜박임 전에 먼저 장치 잠금을 해제 해야 합니다.

1. PC:
    1. 에서 PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.

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

더 이상 Windows Holographic의 참가자 빌드를 수신하지 않으려는 경우 HoloLens 프로덕션 빌드를 실행할 때 옵트아웃하거나 고급 복구 도우미를 사용하여 [디바이스를](hololens-recovery.md) Windows Holographic의 참가자가 아닌 버전으로 복구할 수 있습니다.

> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 취소하는 사용자에게 파란색 화면이 발생하는 알려진 문제가 있습니다. 그런 다음 디바이스를 수동으로 복구해야 합니다. 영향을 받을지 여부에 대한 자세한 내용은 이 [알려진 문제에](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)대한 자세한 내용을 확인하세요.

HoloLens 프로덕션 빌드를 실행하고 있는지 확인하려면 다음을 수행합니다.

1. 설정 > **시스템 > 정보로** 이동하여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호는 릴리스 정보 를 참조하세요.](hololens-release-notes.md)

참가자 빌드를 옵트아웃하려면 다음을 수행합니다.

1. 프로덕션 빌드를 실행하는 HoloLens 설정 > 업데이트 **& 보안 > Windows 참가자 프로그램** 로 이동하고 **참가자 빌드 중지를** 선택합니다.

1. 지침에 따라 디바이스를 옵트아웃합니다.
