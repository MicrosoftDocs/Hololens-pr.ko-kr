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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 52503c0e1ff8c937211500203b91a30806cd317d
ms.sourcegitcommit: 74f5b64c67026881c8ae46410f272b22862ff582
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "114696319"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens에 대한 참가자 미리 보기

HoloLens 위한 최신 Insider Preview 빌드를 시작합니다. HoloLens 대한 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 [간단하게 시작하고](hololens-insider.md#start-receiving-insider-builds) 제공할 수 있습니다.

## <a name="windows-insider-release-notes"></a>Windows 참가자 릴리스 정보

새 기능을 다시 Windows 위해 플라이팅을 시작하게 되어 기쁩니다. 새 빌드는 최신 업데이트를 위해 개발 및 베타 채널로 플라이팅됩니다. Windows Insider 빌드에 더 많은 기능 및 업데이트를 추가함에 따라 이 페이지를 계속 업데이트할 예정입니다. 이러한 업데이트를 현실에 혼합할 준비가 되어 있습니다.

| 기능                 | 설명                | 사용자 또는 시나리오 | 빌드 소개 |
|-------------------------|----------------------------|--------------|------------------|
| [HoloLens 세부 정보를 보고하기 위한 CSP 변경 내용](#csp-changes-for-reporting-hololens-details) | 데이터를 쿼리하기 위한 의 새 CSP | IT 관리자    | 20348.1403                 |
| [CSP에서 제어하는 자동 로그인 정책](#auto-login-policy-controlled-by-csp) | 자동으로 계정에 로그인하는 데 사용 | IT 관리자 | 20348.1405 |
| [인증서 관리자에 대한 PFX 파일 지원](#pfx-file-support-for-certificate-manager) | 설정 UI를 통해 PFX 인증서 추가 | 최종 사용자 | 20348.1405 |
| [HoloLens 설정 고급 진단 보고서 보기](#view-advanced-diagnostic-report-in-settings-on-hololens) | 디바이스에서 MDM 진단 로그 보기 | 문제 해결 | 20348.1405 |
| [오프라인 진단 알림](#offline-diagnostics-notifications) | 로그 수집에 대한 시청각 피드백 | 문제 해결 | 20348.1405 |
| [프라이빗 스토어 앱만 Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | 조직의 앱만 표시하도록 스토어 앱 구성 | IT 관리자 | 20348.1408 |
| [수정 및 개선](hololens-insider.md#fixes-and-improvements) | HoloLens 대한 수정 및 개선 | 모두 | 20348.1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>HoloLens 세부 정보를 보고하기 위한 CSP 변경 내용

- Windows Insider 빌드에 도입된 20348.1403

다음 CSP는 HoloLens 디바이스에서 정보를 보고하는 새로운 방법으로 업데이트되었습니다.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 무료 Storage

이제 DevDetail CSP는 HoloLens 디바이스에 사용 중인 스토리지 공간도 보고합니다. 이 값은 설정 앱의 Storage 페이지에 표시된 값과 거의 일치해야 합니다. 다음은 이 정보를 포함하는 특정 노드입니다.

- ./DevDetail/Ext/Microsoft/FreeStorage(GET 작업만 해당)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID 및 BSSID

이제 DeviceStatus CSP는 HoloLens 적극적으로 연결된 Wi-Fi 네트워크의 SSID 및 BSSID도 보고합니다. 다음은 이 정보를 포함하는 특정 노드입니다.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

NetworkIdentifiers를 쿼리하는 syncml Blob 예제(MDM 공급업체용)

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

### <a name="auto-login-policy-controlled-by-csp"></a>CSP에서 제어하는 자동 로그인 정책

이 새로운 AutoLogonUser 정책은 사용자가 자동으로 로그온되는지 여부를 제어합니다. 일부 고객은 ID에 연결되어 있지만 로그인 환경을 원하지 않는 디바이스를 설정하려고 합니다. 디바이스를 선택하고 원격 지원을 즉시 사용하는 Imagine. 또는 HoloLens 디바이스를 신속하게 배포하고 최종 사용자가 로그인을 신속하게 수행할 수 있다는 이점이 있습니다.

정책이 비어있지 않은 값으로 설정된 경우 자동 로그온 사용자의 이메일 주소를 지정합니다. 자동 로그온을 사용하려면 지정된 사용자가 디바이스에 한 번 이상 로그온해야 합니다.

새 정책 문자열 값의 OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 이메일 주소가 동일한 사용자는 자동 로그온을 사용하도록 설정됩니다.

이 정책이 구성된 디바이스에서 정책에 지정된 사용자는 한 번 이상 로그온해야 합니다. 첫 번째 로그온 후 디바이스를 다시 부팅하면 지정된 사용자가 자동으로 로그온됩니다. 단일 자동 로그온 사용자만 지원됩니다. 사용하도록 설정하면 자동으로 로그온된 사용자는 수동으로 로그아웃할 수 없습니다. 다른 사용자로 로그온하려면 먼저 정책을 사용하지 않도록 설정해야 합니다.

> [!NOTE]
> - 주요 OS 업데이트와 같은 일부 이벤트는 지정된 사용자가 디바이스에 다시 로그온하여 자동 로그온 동작을 다시 시작하도록 요구할 수 있습니다. 
> - 자동 로그온은 MSA 및 AAD 사용자에 대해서만 지원됩니다.

### <a name="pfx-file-support-for-certificate-manager"></a>인증서 관리자에 대한 PFX 파일 지원

Windows Insider 빌드 20348.1405에 도입되었습니다. 이제 .pfx 인증서를 사용할 수 있도록 [인증서 관리자에](certificate-manager.md) 대한 지원이 추가되었습니다. 사용자가 **설정** 업데이트 & 보안 인증서 로 이동하고  >    >   **인증서 설치를** 선택하면 이제 UI에서 .pfx 인증서 파일을 지원합니다.
사용자는 프라이빗 키가 있는 .pfx 인증서를 사용자 저장소 또는 컴퓨터 저장소로 가져올 수 있습니다.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens 설정 고급 진단 보고서 보기

동작 문제를 해결할 때 관리되는 디바이스의 경우 예상되는 정책 구성이 적용되는지 확인하는 것이 중요한 단계입니다. 이전에는 이 새로운 기능을 사용하려면 MDM을 통해 디바이스에서 또는 디바이스 근처에서 수행되어야 했습니다. **이** 작업은 설정 계정을 통해 수집된 MDM 진단 로그를 내보낸 후 작업 또는 학교 에  ->    >  **액세스하고** **관리 로그 내보내기를** 선택하여 주변 PC에서 볼 수 있었습니다.

이제 Edge 브라우저를 사용하여 디바이스에서 MDM 진단을 볼 수 있습니다. MDM 진단 보고서를 보다 쉽게 보려면 작업 또는 학교 액세스 페이지로 이동하고 **고급 진단 보고서 보기를** 선택합니다. 그러면 새 Edge 창에서 보고서가 생성되고 열립니다.

![설정 앱에서 고급 진단 보고서를 봅니다.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>오프라인 진단 알림

오프라인 진단이라는 기존 기능에 대한 [업데이트입니다.](hololens-diagnostic-logs.md#offline-diagnostics) 이전에는 사용자에게 진단 수집을 트리거했거나 완료되었다는 명확한 표시기가 없었습니다.
이제 Windows 참가자 빌드에 추가되었습니다. 오프라인 진단에 대한 두 가지 형태의 시청각 피드백이 있습니다. 첫 번째는 컬렉션이 시작되고 완료될 때 둘 다에 대해 표시되는 알림 메시지입니다. 사용자가 로그인하고 시각적 개체를 가지고 있을 때 표시됩니다.

![로그를 수집하기 위한 알림입니다.](./images/logcollection1.jpg)

![로그 수집이 완료되면 알림 메시지입니다.](./images/logcollection2.jpg)
 
사용자가 디스플레이에 액세스할 수 없거나 로그인할 수 없거나 여전히 OOBE에 있는 경우 오프라인 진단을 대체 로그 수집 메커니즘으로 사용하기 때문에 로그가 수집될 때 오디오 큐가 재생됩니다. 이 소리는 알림 메시지 외에도 재생됩니다.

이 새로운 기능은 디바이스가 업데이트될 때 사용하도록 설정되며 사용하도록 설정하거나 관리하지 않아도 됩니다. 이 새 피드백을 표시하거나 들어 볼 수 없는 경우에도 오프라인 진단이 계속 생성됩니다.

이 새로운 오디오시각 피드백 추가를 통해 진단 데이터를 더 쉽게 수집하고 문제를 보다 신속하게 해결할 수 있기를 바랍니다.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store 프라이빗 스토어 앱만 사용

RequirePrivateStoreOnly 정책이 HoloLens 사용하도록 설정되었습니다. 이 정책을 사용하면 Microsoft Store 앱이 조직에 대해 구성된 프라이빗 저장소만 표시하도록 구성할 수 있습니다. 사용 가능한 앱에 대 한 액세스만 제한 합니다.

[Applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) 에 대 한 자세한 정보

### <a name="fixes-and-improvements"></a>수정 사항 및 향상 된 기능

- [잠긴 파일 다운로드 프롬프트가 없는 장치 포털의 알려진 문제를 수정 했습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [파일 업로드 및 다운로드 시간 제한이 있는 장치 포털의 알려진 문제를 수정 했습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- HoloLens 장치에서 준수 속성을 보고 하는 문제를 해결 합니다. 올바른 보고가 Insider 빌드에서 트리거되도록 하려면 다시 부팅 해야 할 수 있습니다.  
- 새 깜박이에 설치 된 원격 지원의 기본 버전을 업데이트 했습니다.


## <a name="start-receiving-insider-builds"></a>Insider 빌드 수신을 시작 합니다.

> [!NOTE]
> 최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.
> - "장치 다시 부팅" 음성 명령은 제대로 작동 합니다. 
> - 설정/Windows Insider Program에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 사용자가 발생 시킨 백 엔드에 대 한 버그가 있었으며이로 인해 다시 추적할 수 있습니다.

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** 로 이동 하 고 **시작** 을 선택 합니다. Windows Insider로 등록 하는 데 사용한 계정을 연결 합니다.

이제 Windows insider가 채널로 이동 하 고 있습니다. **빠른** 링은 **Dev 채널이** 되 고, **저속** 링은 **베타 채널이** 되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이** 됩니다. 매핑은 다음과 같습니다.

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그의 [Windows Insider 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.
그런 다음 **Windows의 활성 개발** 을 선택 하 고 **개발 채널** 또는 **베타 채널** 빌드를 받을지 여부를 선택한 후 프로그램 용어를 검토 합니다.
확인을 선택 하 **> 지금 다시 시작** 하 여 완료 합니다. 장치를 다시 부팅 한 후 설정으로 이동 하 **> 업데이트 & 업데이트 > 업데이트를 확인** 하 여 최신 빌드를 가져옵니다.

### <a name="update-error-0x80070490-work-around"></a>업데이트 오류 0x80070490 문제 해결

Dev 또는 Beta 채널에서 업데이트할 때 0x80070490 업데이트 오류가 발생 하는 경우 다음 단기 작업을 수행해 보세요. 여기에는 insider channel을 이동 하 고, 업데이트를 선택한 다음, Insider channel을 다시 이동 하는 작업이 포함 됩니다.

#### <a name="stage-one---release-preview"></a>1 단계 릴리스 미리 보기

1.  설정, 업데이트 & 보안, Windows Insider Program, **Release preview 채널** 을 차례로 선택 합니다.

2.  설정, 업데이트 & 보안, Windows 업데이트 **업데이트를 확인** 합니다. 업데이트 후 2 단계를 계속 진행 합니다.

#### <a name="stage-two---dev-channel"></a>2 단계 개발자 채널

1. 설정, 업데이트 & 보안, Windows Insider Program에서 **Dev Channel** 을 선택 합니다.

2. 설정, 업데이트 & 보안, Windows 업데이트 **업데이트를 확인** 합니다.

## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 방향

비행 서명 된 ffu로 테스트 하려면 비행 서명 된 ffu를 깜박임 전에 먼저 장치 잠금을 해제 해야 합니다.

1. PC:
    1. 에서 PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.
    
    1. Microsoft Store에서 ARC (고급 복구 도우미)를 설치 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 합니다.
    
1. HoloLens 비행 잠금 해제: **설정**  >  **업데이트 & 보안**  >  **Windows Insider Program** 을 등록 하 고 장치를 다시 부팅 합니다.

1. 플래시 FFU-이제 호를 사용 하 여 비행 서명 된 FFU를 깜박일 수 있습니다.

### <a name="provide-feedback-and-report-issues"></a>사용자 의견을 제공 하 고 문제를 보고 합니다.

사용자 의견을 제공 하 고 문제를 보고 하려면 HoloLens [피드백 허브 앱](hololens-feedback.md) 을 사용 하세요. 피드백 허브를 사용 하면 엔지니어가 신속 하 게 디버그 하 고 문제를 해결 하는 데 필요한 모든 진단 정보가 포함 됩니다.  중국어 및 일본어 버전의 HoloLens 관련 된 문제는 동일한 방식으로 보고 해야 합니다.

> [!NOTE]
> 사용자 의견 허브에서 문서 폴더에 액세스할 지 여부를 묻는 메시지를 수락 해야 합니다 (메시지가 표시 되 면 **예** 선택).

## <a name="note-for-developers"></a>개발자를 위한 정보

HoloLens의 참가자 빌드를 사용 하 여 응용 프로그램을 개발 하는 것이 좋습니다.  [HoloLens 개발자 설명서](https://developer.microsoft.com/windows/mixed-reality/development) 를 확인 하 여 시작 하세요. 이와 동일한 지침은 HoloLens의 참가자 빌드와 함께 작동 합니다.  이미 HoloLens 개발에 사용 하 고 있는 것과 동일한 Unity 및 Visual Studio 빌드를 사용할 수 있습니다.

## <a name="stop-receiving-insider-builds"></a>Insider 빌드 수신을 중지 합니다.

Windows Holographic의 참가자 빌드를 더 이상 수신 하지 않으려는 경우, HoloLens 프로덕션 빌드를 실행 하 고 있을 때 옵트아웃 하거나, 고급 복구 도우미를 사용 하 여 장치를 [복구](hololens-recovery.md) 하 고 Windows Holographic의 비-insider 버전으로 장치를 복구할 수 있습니다.

> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치 하면 사용자에 게 Insider Preview 빌드에서 등록을 취소 하는 알려진 문제가 있습니다. 이후에는 장치를 수동으로 복구 해야 합니다. 영향을 받는 경우에 대 한 자세한 내용은이 [알려진 문제](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)에 대 한 자세한 내용을 확인 하세요.

HoloLens에서 프로덕션 빌드를 실행 하 고 있는지 확인 하려면 다음을 수행 합니다.

1. **설정 > System > 정보** 로 이동 하 여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.

참가자 빌드를 옵트아웃 (opt out) 하려면 다음을 수행 합니다.

1. 프로덕션 빌드를 실행 하는 HoloLens에서 **설정 > 업데이트 & 보안 > insider Program** 로 이동 하 여 insider build **중지** 를 선택 합니다.

1. 지침에 따라 장치를 옵트아웃 합니다.
