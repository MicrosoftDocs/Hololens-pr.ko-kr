---
title: 페이지 설정 표시 여부
description: PageVisibilityList에 대해 지원되는 HoloLens 목록 및 가이드입니다.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: Holollens, Holollens 2, 액세스 할당, 키오스크, 설정 페이지입니다.
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8cd336ce64cf7d4549b031a7977f592ca82dd6e4
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163146"
---
# 페이지 설정 표시 여부

HoloLens 디바이스의 관리 가능한 기능 중 하나는 [Settings/PageVisibilityList 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)을(를) 사용하여 설정 앱에 표시되는 페이지를 제한합니다. PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스 하지 못하도록 방지 하거나 지정 된 페이지를 제외한 모든 페이지에 대한 작업을 수행하는 데 사용 하는 정책입니다. 

> [!NOTE]
> 이 기능은 HoloLens 2 장치용 [Windows 홀로그램, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에서만 사용 가능합니다. 사용하려는 장치가 업데이트되었는지 확인하세요.

다음 예제에서는 URI "ms-설정: network-wifi" 및 "ms-설정: Bluetooth"를 각각 포함 하는 정보 및 블루투스 페이지에만 액세스를 허용하는 정책을 보여줍니다.
- showonly:network-wifi;network-proxy;bluetooth

프로비저닝 패키지를 통해 설정 하려면: 
1. Windows 구성 디자이너에서 패키지를 만드는 동안 **정책 > 설정 > PageVisibilityList**로 이동합니다.
1. 문자열 입력: **showonly:network-wifi;network-proxy;bluetooth**
1. 프로비저닝 패키지를 내보냅니다.
1. 장치에 패키지를 적용합니다. 프로비저닝 패키지를 만들고 적용 하는 방법에 대한 자세한 내용은 [이 페이지](hololens-provisioning.md)를 방문하세요. 

이 작업은 OMA-URI를 사용하여 Intune을 통해 수행할 수 있습니다.
1. **사용자 지정 정책**을 사용합니다.
1. OMA-URI이 문자열을 사용하도록 설정: **./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. 데이터 선택을 선택할 때: **문자열**
1. 값을 입력 할 때 사용: **showonly:network-wifi;network-proxy;bluetooth**
1. 장치가 있는 그룹에 사용자 지정 장치 구성을 할당 해야 합니다.
Intune 그룹과 장치 구성에 대 한 자세한 내용은 [여기를 참조 하세요](hololens-mdm-configure.md).

장치가 선택한 방법에 상관 없이 이제 변경을 수신 받을 것이고 사용자에게는 다음 설정 앱이 표시됩니다. 

![설정 앱에서 수정 중인 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

사용자가 선택한 페이지를 표시 하거나 숨기도록 설정 앱 페이지를 구성 하려면 HoloLens에서 사용 가능한 설정 URI를 확인하세요. 

## URI 설정

HoloLens 장치와 Windows 10 장치는 설정 앱 내에서 서로 다른 페이지 선택을 합니다. 이 페이지에서는 HoloLens에 존재하는 설정만 볼 수 있습니다. 

### 계정
| 설정 페이지           | URI                                            |
|-------------------------|------------------------------------------------|
| 로그인 옵션         | ms-settings:signinoptions                      |
| Iris 등록       | ms-settings:signinoptions-launchirisenrollment |
| 회사 또는 학교 계정에 액세스 | ms-settings:workplace                          |

### 장치
| 설정 페이지 | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### 개인 정보
| 설정 페이지            | URI                                             |
|--------------------------|-------------------------------------------------|
| 계정 정보             | ms-settings:privacy-accountinfo                 |
| 앱 진단        | ms-settings:privacy-appdiagnostics              |
| 배경 앱        | ms-settings:privacy-backgroundapps              |
| 사용자 이동           | ms-settings:privacy-backgroundspatialperception |
| 파일 시스템              | ms-settings:privacy-broadfilesystemaccess       |
| Calendar                 | ms-settings:privacy-calendar                    |
| 통화 기록             | ms-settings:privacy-callhistory                 |
| 연락처                 | ms-settings:privacy-contacts                    |
| 기타 장치            | ms-settings:privacy-customdevices               |
| 문서                | ms-settings:privacy-documents                   |
| 이메일                    | ms-settings:privacy-email                       |
| 피드백 및 진단 | ms-settings:privacy-feedback                    |
| 위치                 | ms-settings:privacy-location                    |
| 메시지                | ms-settings:privacy-messaging                   |
| 마이크               | ms-settings:privacy-microphone                  |
| 알림            | ms-settings:privacy-notifications               |
| 사진                 | ms-settings:privacy-pictures                    |
| 무선                   | ms-settings:privacy-radios                      |
| 음성 명령                   | ms-settings:privacy-speech                      |
| 작업                    | ms-settings:privacy-tasks                       |
| 비디오                   | ms-settings:privacy-videos                      |
| 음성 활성화       | ms-settings:privacy-voiceactivation             |
| 카메라                   | ms-settings:privacy-webcam                      |

### 네트워크 및 인터넷
| 설정 페이지 | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy (프록시) | ms-settings:network-proxy        |

### System
| 설정 페이지      | URI                                |
|--------------------|------------------------------------|
| 공유 환경 | ms-settings:crossdevice            |
| 색             | ms-settings:colors<br>ms-settings:personalization-colors |
| 알림 및 동작  | ms-settings:notifications          |
| 저장 공간            | ms-settings:storagesense           |

### 시간 및 언어
| 설정 페이지 | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| 외국어      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### 업데이트 및 보안
| 설정 페이지                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows 참가자 프로그램               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows 업데이트                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows 업데이트-업데이트 확인 | ms-settings:windowsupdate-action          |
| 고급 옵션                    | ms-settings:windowsupdate-options         |

>  <sup>1</sup> 다음 두 URI는 실제로 **고급 옵션** 또는 **옵션** 페이지로 이동하지 않고 기본 Windows Update 페이지만 차단 또는 표시합니다. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Windows 10 설정 URI의 전체 목록을 보려면 [여기](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)를 방문해 주세요. 
