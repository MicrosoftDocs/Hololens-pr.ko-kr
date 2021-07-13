---
title: 페이지 설정 표시
description: PageVisibilityList에 대해 지원되는 URI 목록과 HoloLens 혼합 현실 장치에 대한 지침의 최신 정보를 확인하세요.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 할당된 액세스, 키오스크, 설정 페이지
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924335"
---
# <a name="page-settings-visibility"></a>페이지 설정 표시

HoloLens 장치에 대한 관리 가능한 기능 중 하나는 [설정/PageVisibilityList 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)을 사용하여 설정 앱 내에 표시되는 페이지를 제한하는 것입니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지가 표시 또는 액세스되지 않도록 방지하거나 지정된 페이지를 제외한 모든 페이지에 대해서도 표시 또는 액세스를 방지할 수 있도록 하는 정책입니다.

> [!NOTE]
> 이 기능은 HoloLens 2 장치의 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상에서만 사용할 수 있습니다. 이 기능을 사용하려는 장치가 업데이트되었는지 확인하세요.

다음 예제에서는 각각 URI "ms-settings:network-wifi" 및 "ms-settings:bluetooth"를 포함하는 정보 및 Bluetooth 페이지에만 액세스를 허용하는 정책을 보여줍니다.
- `showonly:network-wifi;network-proxy;bluetooth`

프로비전 패키지를 통해 설정하려면:

1. Windows 구성 디자이너에서 패키지를 만드는 동안 **정책> 설정 > PageVisibilityList** 로 이동합니다.
1. 다음 문자열을 입력합니다. **`showonly:network-wifi;network-proxy;bluetooth`**
1. 프로비전 패키지를 내보냅니다.
1. 패키지를 장치에 적용합니다.
프로비전 패키지를 만들고 적용하는 방법에 대한 자세한 내용은 [이 페이지](hololens-provisioning.md)를 방문하세요.

이 작업은 OMA-URI를 사용하여 Intune을 통해 수행할 수 있습니다.

1. **사용자 지정 정책** 을 만듭니다.
1. OMA-URI를 설정할 때 다음 문자열을 사용합니다. **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 데이터 선택을 선택할 때 다음을 선택합니다. **문자열**
1. 값을 입력할 때 다음을 사용합니다. **`showonly:network-wifi;network-proxy;bluetooth`**
1. 장치를 포함시킬 그룹에 사용자 지정 장치 구성을 할당해야 합니다.

Intune 그룹 및 장치 구성에 대한 자세한 내용은 [HoloLens MDM 구성](hololens-mdm-configure.md)을 참조하세요.

선택한 방법에 관계없이 이제 장치가 변경 내용을 수신해야 하고 사용자에게 다음과 같은 설정 앱이 표시됩니다.

![설정 앱에서 수정되는 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

사용자가 선택한 페이지를 표시하거나 숨기도록 설정 앱 페이지를 구성하려면 HoloLens에서 사용 가능한 설정 URI를 확인합니다.

## <a name="settings-uris"></a>URI 설정

HoloLens 장치와 Windows 10 장치는 설정 앱 내에서 선택할 수 있는 페이지가 서로 다릅니다. 이 페이지에서는 HoloLens에 있는 설정만 볼 수 있습니다.

### <a name="accounts"></a>계정
| 설정 페이지           | URI                                            |
|-------------------------|------------------------------------------------|
| 회사 또는 학교 액세스 | `ms-settings:workplace`                         |
| 아이리스 등록       | `ms-settings:signinoptions-launchirisenrollment` |
| 로그인 옵션         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>앱
| 설정 페이지 | URI                          |
|---------------|------------------------------|
| 앱 및 기능<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| 앱 및 기능 > 고급 옵션 <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| 앱 및 기능 > 오프라인 지도 <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| 앱 및 기능 > 오프라인 지도 > 지도 다운로드 <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>디바이스
| 설정 페이지 | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| 마우스 <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>개인 정보 취급 방침
| 설정 페이지            | URI                                             |
|--------------------------|-------------------------------------------------|
| 계정 정보             | `ms-settings:privacy-accountinfo`              |
| 앱 진단        | `ms-settings:privacy-appdiagnostics`              |
| 배경 앱        | `ms-settings:privacy-backgroundapps`              |
| 달력                 | `ms-settings:privacy-calendar`                    |
| 통화 기록             | `ms-settings:privacy-callhistory`                 |
| 카메라                   | `ms-settings:privacy-webcam`                      |
| 연락처                 | `ms-settings:privacy-contacts`                    |
| 피드백 및 진단 | `ms-settings:privacy-feedback`                    |
| 문서                | `ms-settings:privacy-documents`                   |
| 메일                    | `ms-settings:privacy-email`                       |
| 파일 시스템              | `ms-settings:privacy-broadfilesystemaccess`       |
| 일반 <sup>2</sup>             | `ms-settings:privacy-general`       |
| 수동 입력 및 키 입력 개인 설정 <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| 위치                 | `ms-settings:privacy-location`                    |
| 메시징                | `ms-settings:privacy-messaging`                   |
| 마이크               | `ms-settings:privacy-microphone`                  |
| Motion <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| 알림            | `ms-settings:privacy-notifications`               |
| 기타 디바이스            | `ms-settings:privacy-customdevices`               |
| 사진                 | `ms-settings:privacy-pictures`                    |
| 무선                   | `ms-settings:privacy-radios`                      |
| 스크린샷 테두리 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| 스크린샷 및 앱 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `ms-settings:privacy-speech`                      |
| 작업                    | `ms-settings:privacy-tasks`                       |
| 사용자 이동           | `ms-settings:privacy-backgroundspatialperception` |
| 동영상                   | `ms-settings:privacy-videos`                      |
| 음성 활성화       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>네트워크 및 인터넷
| 설정 페이지 | URI                              |
|---------------|----------------------------------|
| 비행기 모드 <sup>2</sup> | `ms-settings:network-airplanemode`        |
| 프록시 | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>시스템
| 설정 페이지      | URI                                |
|--------------------|------------------------------------|
| 배터리 <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| 배터리 <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| 색             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| 홀로그램 <sup>2</sup>  |  `ms-settings:holograms`  |
| 보정 <sup>2</sup> |  `ms-settings:calibration` |
| 알림 및 작업  | `ms-settings:notifications`          |
| Shared Experiences | `ms-settings:crossdevice` 
| 소리 <sup>2</sup>           | `ms-settings:sound`<br>|
| 소리 > 앱 볼륨 및 장치 기본 설정 <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| 소리 > 사운드 장치 관리 <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| 스토리지            | `ms-settings:storagesense`           |
| 저장소 > 저장소 센스 구성 <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>시간 및 언어
| 설정 페이지 | URI                                           |
|---------------|-----------------------------------------------|
| 날짜 및 시간 <sup>2</sup> | `ms-settings:dateandtime`                  |
| 키보드 <sup>2</sup> | `ms-settings:keyboard`                  |
| 언어 <sup>2</sup> | `ms-settings:language`                  |
| 언어 <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| 언어      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| 지역        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>업데이트 및 보안
| 설정 페이지                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 고급 옵션                    | `ms-settings:windowsupdate-options`         |
| 초기화 및 복구 <sup>2</sup>      | `ms-settings:reset`         |
|  Windows 참가자 프로그램               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows 업데이트                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows 업데이트 - 업데이트 확인 | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> -Windows Holographic 버전 21H1 이전 버전의 경우, 다음 두 URI는 실제로 **고급 옵션** 또는 **옵션** 페이지로 이동하지 않습니다. 기본 Windows Update 페이지를 차단하거나 표시할 뿐입니다.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> -Windows Holographic 21H1 이상에서 사용 가능합니다.


Windows 10 설정 URI의 전체 목록은 [시작 설정](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 설명서를 참조하세요.
