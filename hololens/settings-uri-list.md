---
title: URI 설정
description: PageVisibilityList에 대해 지원되는 HoloLens 목록입니다.
author: evmill
ms.author: v-evmill
ms.date: 8/1/2020
ms.topic: article
keywords: Holollens, Holollens 2, 액세스 할당, 키오스크, 설정 페이지입니다.
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6b506b36915c8f34b90c455410db67e55a2cca09
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963720"
---
# URI 설정

HoloLens 디바이스의 관리 가능한 기능 중 하나는 [Settings/PageVisibilityList 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)을(를) 사용하여 설정 앱에 표시되는 페이지를 제한합니다. HoloLens 장치와 Windows 10 장치는 설정 앱 내에서 서로 다른 페이지 선택을 합니다. 이 페이지에서는 HoloLens에 존재하는 설정만 볼 수 있습니다. 

## 계정
| 설정 페이지           | URI                                            |
|-------------------------|------------------------------------------------|
| 로그인 옵션         | ms-settings:signinoptions                      |
| Iris 등록       | ms-settings:signinoptions-launchirisenrollment |
| 회사 또는 학교 계정에 액세스 | ms-settings:workplace                          |

## 장치
| 설정 페이지 | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

## 개인 정보
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

## 네트워크 및 인터넷
| 설정 페이지 | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy (프록시) | ms-settings:network-proxy        |

## System
| 설정 페이지      | URI                                |
|--------------------|------------------------------------|
| 공유 환경 | ms-settings:crossdevice            |
| 색             | ms-settings:colors<br>ms-settings:personalization-colors |
| 알림 및 동작  | ms-settings:notifications          |
| 저장 공간            | ms-settings:storagesense           |

## 시간 및 언어
| 설정 페이지 | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| 외국어      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

## 업데이트 및 보안
| 설정 페이지                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows 참가자 프로그램               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows 업데이트                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows 업데이트-업데이트 확인 | ms-settings:windowsupdate-action          |
| 고급 옵션                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 다음 두 URI는 실제로 고급 옵션 또는 옵션 페이지로 이동하지 않고 기본 Windows Update 페이지만 차단/표시합니다. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Windows 10 설정 URI의 전체 목록을 보려면 [여기](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)를 방문해 주세요. 
