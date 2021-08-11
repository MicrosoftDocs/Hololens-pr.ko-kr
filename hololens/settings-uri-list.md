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
ms.openlocfilehash: d2747da37ae198f7a2c051593da3ffd4cb4476dfaa7a3078a7749fa1fc912ba2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665627"
---
# <a name="page-settings-visibility"></a>페이지 설정 표시

HoloLens 장치에 대한 관리 가능한 기능 중 하나는 [설정/PageVisibilityList 정책](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)을 사용하여 설정 앱 내에 표시되는 페이지를 제한하는 것입니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지가 표시 또는 액세스되지 않도록 방지하거나 지정된 페이지를 제외한 모든 페이지에 대해서도 표시 또는 액세스를 방지할 수 있도록 하는 정책입니다.

> [!NOTE]
> 이 기능은 HoloLens 2 장치의 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상에서만 사용할 수 있습니다. 이 기능을 사용하려는 장치가 업데이트되었는지 확인하세요.


## <a name="examples"></a>예
페이지는 URI에서 "ms-settings:" 접두사를 뺀 게시된 URI의 단축 버전으로 식별됩니다.

다음 예는 각각 URI "network-wifi" 및 "bluetooth"가 있는 about 및 bluetooth 페이지에만 액세스를 허용하는 정책을 보여줍니다.
- `showonly:network-wifi;network-proxy;bluetooth`

다음 예는 OS 재설정 페이지를 숨기는 정책을 보여줍니다.
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Intune을 통해 이 정책 배포

다음은 Intune에 제공될 구성 값입니다.

- **이름:** 관리자가 선호하는 프로필 표시 이름.
- **OMA-URI:** [범위](/windows/client-management/mdm/policy-configuration-service-provider)를 포함한 설정 페이지의 정규화된 URI. 이 페이지의 이 예에서는 `./Device` 범위를 사용하고 있습니다.
- **값:** 지정된 *페이지만* 숨길지 또는 표시할지 여부를 나타내는 문자열 값. 가능한 값은 `hide:<pagename>` 및 `showonly:<pagename>`입니다. 
 
여러 페이지를 세미콜론으로 구분하여 지정할 수 있으며 공통 페이지 목록은 아래에서 확인할 수 있습니다.

1. **사용자 지정 정책** 을 만듭니다.
1. **OMA-URI** 를 설정할 때 전체 범위의 URI를 입력합니다. 예: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 데이터 선택을 선택할 때 다음을 선택합니다. **문자열**
1. **값** 을 지정할 때 위의 지침을 사용합니다. 예: **`showonly:network-wifi;network-proxy;bluetooth`** 또는 **`hide:reset`** 
> [!IMPORTANT]
> 장치를 포함시킬 그룹에 사용자 지정 장치 구성을 할당해야 합니다. 이 단계를 수행하지 않으면 정책이 푸시되지만 적용되지 않습니다.

Intune 그룹 및 장치 구성에 대한 자세한 내용은 [HoloLens MDM 구성](hololens-mdm-configure.md)을 참조하세요.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>프로비전 패키지를 통해 이 정책 배포

다음은 Windows 구성 디자이너에서 지정될 구성 값입니다.

**값:** 지정된 *페이지만* 숨길지 또는 표시할지 여부를 나타내는 문자열 값. 가능한 값은 `hide:<pagename>` 및 `showonly:<pagename>`입니다. 여러 페이지를 세미콜론으로 구분하여 지정할 수 있으며 공통 페이지 목록은 아래에서 확인할 수 있습니다.


1. Windows 구성 디자이너에서 패키지를 만드는 동안 **정책> 설정 > PageVisibilityList** 로 이동합니다.
1. 다음 문자열을 입력합니다. **`showonly:network-wifi;network-proxy;bluetooth`**
1. 프로비전 패키지를 내보냅니다.
1. 패키지를 장치에 적용합니다.
프로비전 패키지를 만들고 적용하는 방법에 대한 자세한 내용은 [HoloLens 프로비전 페이지](hololens-provisioning.md)를 참조하세요.


선택한 방법에 관계없이 이제 장치가 변경 내용을 수신해야 하고 사용자에게 다음과 같은 설정 앱이 표시됩니다.

![설정 앱에서 수정되는 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

사용자가 선택한 페이지를 표시하거나 숨기도록 설정 앱 페이지를 구성하려면 HoloLens에서 사용 가능한 설정 URI를 확인합니다.

## <a name="settings-uris"></a>URI 설정

HoloLens 장치와 Windows 10 장치는 설정 앱 내에서 선택할 수 있는 페이지가 서로 다릅니다. 이 페이지에서는 HoloLens에 있는 설정만 볼 수 있습니다.

### <a name="accounts"></a>계정
| 설정 페이지           | URI                                            |
|-------------------------|------------------------------------------------|
| 회사 또는 학교 액세스 | `workplace`                         |
| 홍채 등록       | `signinoptions-launchirisenrollment` |
| 로그인 옵션         | ` signinoptions `                   |

### <a name="apps"></a>앱
| 설정 페이지 | URI                          |
|---------------|------------------------------|
| 앱 및 기능 <sup>2</sup>     | `appsfeatures` <br> |
| 앱 및 기능 > 고급 옵션 <sup>2</sup>     | `appsfeatures-app` <br> |
| 앱 및 기능 > 오프라인 지도 <sup>2</sup>     | `maps-maps` <br> |
| 앱 및 기능 > 오프라인 지도 > 지도 다운로드 <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>디바이스
| 설정 페이지 | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| 마우스 <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>개인 정보 취급 방침
| 설정 페이지            | URI                                             |
|--------------------------|-------------------------------------------------|
| 계정 정보             | `privacy-accountinfo`              |
| 앱 진단        | `privacy-appdiagnostics`              |
| 배경 앱        | `privacy-backgroundapps`              |
| 달력                 | `privacy-calendar`                    |
| 통화 기록             | `privacy-callhistory`                 |
| 카메라                   | `privacy-webcam`                      |
| 연락처                 | `privacy-contacts`                    |
| 피드백 및 진단 | `privacy-feedback`                    |
| 문서                | `privacy-documents`                   |
| 메일                    | `privacy-email`                       |
| 파일 시스템              | `privacy-broadfilesystemaccess`       |
| 일반 <sup>2</sup>             | `privacy-general`       |
| 수동 입력 및 키 입력 개인 설정 <sup>2</sup>             | `privacy-speechtyping`       |
| 위치                 | `privacy-location`                    |
| 메시징                | `privacy-messaging`                   |
| 마이크               | `privacy-microphone`                  |
| Motion <sup>2</sup>               | `privacy-motion`                  |
| 알림            | `privacy-notifications`               |
| 기타 디바이스            | `privacy-customdevices`               |
| 사진                 | `privacy-pictures`                    |
| 무선                   | `privacy-radios`                      |
| 스크린샷 테두리 <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| 스크린샷 및 앱 <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `privacy-speech`                      |
| 작업                    | `privacy-tasks`                       |
| 사용자 이동           | `privacy-backgroundspatialperception` |
| 동영상                   | `privacy-videos`                      |
| 음성 활성화       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>네트워크 및 인터넷
| 설정 페이지 | URI                              |
|---------------|----------------------------------|
| 비행기 모드 <sup>2</sup> | `network-airplanemode`        |
| 프록시 | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>시스템
| 설정 페이지      | URI                                |
|--------------------|------------------------------------|
| 배터리 <sup>2</sup>           | `batterysaver`<br>|
| 배터리 <sup>2</sup>           | `batterysaver-settings`<br>|
| 색             | `colors`<br>`personalization-colors` |
| 홀로그램 <sup>2</sup>  |  `holograms`  |
| 보정 <sup>2</sup> |  `calibration` |
| 알림 및 작업  | `notifications`          |
| Shared Experiences | `crossdevice` 
| 소리 <sup>2</sup>           | `sound`<br>|
| 소리 > 앱 볼륨 및 장치 기본 설정 <sup>2</sup>           | `apps-volume`<br>|
| 소리 > 사운드 장치 관리 <sup>2</sup>           | `sound-devices`<br>|
| 스토리지            | `storagesense`           |
| 저장소 > 저장소 센스 구성 <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>시간 및 언어
| 설정 페이지 | URI                                           |
|---------------|-----------------------------------------------|
| 날짜 및 시간 <sup>2</sup> | `dateandtime`                  |
| 키보드 <sup>2</sup> | `keyboard`                  |
| 언어 <sup>2</sup> | `language`                  |
| 언어 <sup>2</sup> | `regionlanguage-languageoptions`                  |
| 언어      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| 지역        | `regionformatting`                  |

### <a name="update--security"></a>업데이트 및 보안
| 설정 페이지                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 고급 옵션                    | `windowsupdate-options`         |
| 초기화 및 복구 <sup>2</sup>      | `reset`         |
|  Windows 참가자 프로그램               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows 업데이트                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows 업데이트 - 업데이트 확인 | `windowsupdate-action`          |


- <sup>1</sup> -Windows Holographic 버전 21H1 이전 버전의 경우, 다음 두 URI는 실제로 **고급 옵션** 또는 **옵션** 페이지로 이동하지 않습니다. 기본 Windows Update 페이지를 차단하거나 표시할 뿐입니다.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> -Windows Holographic 21H1 이상에서 사용 가능합니다.


Windows 10 설정 URI의 전체 목록은 [시작 설정](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 설명서를 참조하세요.
