---
title: Microsoft HoloLens 참가자 미리 보기
description: 참가자 빌드를 시작 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 소중한 피드백을 제공 하는 것은 간단 합니다.
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
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 4f09a383f20c5c4f2d21ee9367a1b3c5afd62f9f
ms.sourcegitcommit: c0c8b57bb03a2fc724c051ad42ea5a3fb911ba71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894071"
---
# Microsoft HoloLens 참가자 미리 보기

HoloLens에 대 한 최신 참가자 Preview 빌드에 오신 것을 환영 합니다!  이 작업을 간단 하 게 시작 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 소중한 의견을 제공 하세요.

이제 Windows 참가자가 채널로 이동 하 고 있습니다. **빠른** 링이 **개발자 채널이**되 고, **느린** 고리는 **베타 채널이**되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이**됩니다. 매핑 결과는 다음과 같습니다.

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.

## Windows 참가자 릴리스 정보

더 이상 여기에 나열 되지 않는 기능을 찾고 있다면 이제 일반적으로 사용할 수 있습니다. 기대 하는 기능이 어떤 빌드에 있는지 확인 하려면 [릴리스 노트](hololens-release-notes.md) 를 검토 하세요. 최신 기능을 모두 얻으려면 [HoloLens를 업데이트](hololens-update-hololens.md) 해야 합니다.

Windows 참가자 빌드에이를 릴리스할 때 새 기능으로이 페이지를 다시 업데이트 합니다.

| 기능                                         | 설명                                                                                   | 참가자 빌드에서 사용 가능 |
|-------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| 자동 눈동자 위치 지원                       | 현재 위치를 찾고 정확한 홀로그램 포지셔닝을 가능 하 게 합니다.                       | 19041.1339 +                 |
| 전체 할당된 액세스                          | 시스템 수준에서 적용 되는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성 합니다.  | 19041.1346 +                 |
| 다중 앱 키오스크에서 앱 자동 실행           | 여러 앱 키오스크 모드로 로그인 할 때 응용 프로그램이 자동으로 실행 되도록 설정 합니다. | 19041.1346 +                 |
| Hololens 2에 대 한 새 전원 정책               | 전원 시간 제한 설정에 대해 새로 지원 되는 정책입니다.                                          | 19041.1349 +                 |
| 인증서 뷰어                              | 설정 앱에서 사용자 및 장치 인증서를 봅니다.                                        | 19041.1346 +                 |
| HoloLens 2에 대 한 새 장치 제한 정책  | 장치 관리 정책을 HoloLens 2에 대해 새로 사용 하도록 설정 했습니다.                              | 19041.1349 +                 |
| HoloLens 2에 대 한 사용 설정 페이지 표시 여부 | 설정 앱에 표시 되는 페이지를 선택 하는 정책입니다.                                          | 19041.1349 +                 |
| HoloLens 정책                               | 혼합 현실 장치에 대 한 새로운 정책.                                                       | 19041.1349 +                 |

### 자동 눈동자 위치 지원

HoloLens 2에서 눈 위치는 적절 한 홀로그램 위치 지정, 편안한 시청 경험 및 향상 된 디스플레이 품질을 가능 하 게 합니다. 눈동자 위치는 시각 추적 결과의 일부로 계산 됩니다. 그러나이를 위해서는 각 사용자가 눈 응시 입력이 필요 하지 않은 경우에도 시각 추적 보정을 거쳐야 합니다.

**자동 눈동자 (AEP)** 를 사용 하면 이러한 시나리오를 조작 없이 사용자에 대 한 눈 위치를 계산할 수 있습니다.  자동 눈동자 위치는 사용자가 장치를 전환 하는 순간부터 자동으로 백그라운드에서 작업을 시작 합니다. 사용자가 이전 시각 추적 보정을 보유 하 고 있지 않은 경우, 자동 눈동자 위치는 처리 시간이 적은 후 디스플레이 시스템에 대 한 사용자의 눈 위치를 제공 하기 시작 합니다. 일반적으로이 처리 시간은 20-60 초입니다. 사용자 데이터는 장치에 유지 되지 않으므로 사용자가 장치를 종료 하 고 다시 시작 하거나 절전 모드에서 부팅 또는 절전 모드를 전환 하는 경우이 프로세스가 반복 됩니다.  

Uncalibrated 사용자가 디바이스에 배치 하는 경우 자동 눈 위치 기능을 사용 하 여 몇 가지 시스템 동작 변화가 변경 되었습니다. Uncalibrated 사용자는 이전에 장치에서 눈 추적 보정 프로세스를 거치지 않은 사람을 참조 합니다.

|     활성 응용 프로그램                           |     현재 동작                                   |     Windows 참가자 빌드 19041.1339 +의 동작                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     비 응시 사용 앱 또는 홀로그램 셸    |     눈동자 추적 보정 프롬프트가 표시 됩니다.    |     메시지가 표시 되지 않습니다.                                                                                |
|     응시 사용 앱                             |     눈동자 추적 보정 프롬프트가 표시 됩니다.    |     응용 프로그램이 아이 응시 스트림에 액세스 하는 경우에만 눈동자 추적 보정 프롬프트가 표시 됩니다.     |

 사용자가 비 응시 사용 응용 프로그램에서 응시 데이터에 액세스 하는 앱으로 전환 하는 경우 보정 메시지가 표시 됩니다. 경험 치를 다 활용 해도 변경 되지 않습니다. 
 
아이 응시 데이터 나 매우 정밀한 홀로그램 위치가 필요한 환경에서는 사용자가 눈 추적 보정 프롬프트에서 눈 추적 보정을 실행 하거나 시작 메뉴에서 설정 앱을 시작한 다음 **시스템 > 보정 > 눈동자 보정 > 실행**을 선택 하는 것이 좋습니다.

**알려진 문제**
 - 이는 메모리가 과도 하 게 로드 되는 동안 아이 트래커 드라이버 호스트 프로세스가 충돌할 수 있는 문제를 조사 하는 중입니다. 아이 추적 드라이버 호스트 프로세스는 자동으로 복구 되어야 합니다.

### 전역 할당 액세스 – 키오스크 모드
이 새로운 기능을 사용 하면 IT 관리자가 시스템에서 사용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성 하 고 시스템의 모든 id와 관련 된 선호도가 없으며 장치에 로그인 하는 모든 사용자에 게 적용 됩니다. 이 새로운 기능에 대 한 자세한 내용은 [여기](hololens-global-assigned-access-kiosk.md)를 참조 하세요.

### 다중 앱 키오스크 모드에서 응용 프로그램 자동 실행 
이 속성은 여러 앱 키오스크 모드에만 적용 되며 지정 된 액세스 구성에서 아래의 강조 표시 되는 특성을 사용 하 여 자동 시작 하도록 지정할 수 있습니다. 

사용자가 로그인 하면 응용 프로그램이 자동으로 시작 됩니다. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Hololens 2에 대 한 새 전원 정책
관리자는 이러한 새로 추가 된 정책을 통해 유휴 시간 제한 등의 전원 상태를 제어할 수 있습니다. 각 개별 정책에 대 한 자세한 내용을 보려면 해당 정책의 링크를 클릭 하세요.

|     정책 설명서 링크                |     참고                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 구성 디자이너에서 사용할 예제 값입니다 (예: 100).                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예: 100).                                                                          |
|     [소모 되는 Bytimeout배터리](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### 인증서 뷰어

Windows 참가자 빌드 19041.1346 + HoloLens 2 설정 앱에서 인증서 뷰어를 추가 하는 중입니다. 이 기능은 디바이스에서 인증서를 확인 하는 간단 하 고 사용자에 게 친숙 한 방법을 제공 합니다. 특정 인증서를 빠르게 찾으려면 이름, 저장 또는 만료 날짜별로 정렬 하는 옵션이 있습니다. 사용자가 직접 인증서를 검색할 수도 있습니다. 새 인증서 뷰어를 통해 관리자와 사용자는 향상 된 감사, 진단 및 유효성 검사 도구를 사용 하 여 디바이스를 안전 하 고 준수 하도록 유지할 수 있습니다.  개별 인증서에 대 한 자세한 내용을 보려면 인증서를 선택 하 고 정보를 클릭 합니다.

> [!NOTE]
> 미국 이외의 언어 지역화에 대 한 알려진 제한 사항은 이후 Windows 참가자 릴리스에서 해결 하는 데 사용 됩니다.

-   **감사:** 인증서가 올바르게 배포 되었는지 확인 하거나 적절 하 게 제거 되었는지 확인 하는 기능. 
-   **진단:** 문제가 발생 하면 장치에 적절 한 인증서가 있는지 확인 하 여 시간을 절약 하 고 문제를 해결 하는 데 도움이 됩니다. 
-   **유효성 검사:** 인증서가 의도 한 목적을 제공 하 고 작동 하는지 확인 하는 것은 중요 한 기간으로 인증서를 배포 하기 전에 상업적 환경에서 시간을 절약할 수 있습니다.

인증서를 보려면 **& 보안 > 인증서를 업데이트 > 설정**으로 이동 합니다.

![설정 앱의 인증서 뷰어](images/hololens-certificate-viewer.png)

### HoloLens 2에 대 한 새 장치 제한 정책
HoloLens 2 장치의 추가 관리 옵션을 허용 하는 새로 사용할 수 있는 정책 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone) 

### HoloLens 2에 대 한 사용 설정 페이지 표시 여부
이제 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스할 수 없도록 하거나 지정 된 모든 페이지를 제외 하 고,이 정책을 사용 하도록 설정 했습니다. 이 기능을 완전히 사용자 지정 하는 방법에 대 한 자세한 내용을 보려면 아래 링크를 클릭 하세요.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![설정 앱에서 수정 되는 활성 시간 스크린샷](images/hololens-page-visibility-list.jpg)

### HoloLens 정책
빌드 19041.1349 +의 HoloLens 2 장치에 대 한 새 혼합 현실 정책이 생성 되었습니다. 제어 가능한 새 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음 사용 안 함, 진단 프로그램 수집 시 설정 등이 포함 됩니다.  

|     새 HoloLens 정책                   |     설명                                                                            |     참고                                                                |
|-------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
|     MixedReality\BrightnessButtonDisabled |     밝기 단추를 눌러도 밝기가 변경 되지 않도록 할 수 있습니다.    |     1 예, 0 아니요 (기본값)                                                |
|     MixedReality\VolumeButtonDisabled     |     볼륨 단추를 눌러도 볼륨이 변경 되지 않도록 할 수 있습니다.            |     1 예, 0 아니요 (기본값)                                                |
|     MixedReality\MicrophoneDisabled       |     HoloLens 2에서 오디오 녹음을 할 수 없도록 마이크를 사용 하지 않도록 설정 합니다.                   |     1 예, 0 아니요 (기본값)                                                |
|     MixedReality\FallbackDiagnostics      |     진단 로그를 수집할 수 있는 동작을 제어 합니다.                            |     0 사용 안 함, 장치 소유자에 대해 1 개 사용, 2에 모두 사용 (기본값) |
|     MixedReality\HeadTrackingMode         |     나중에 사용 하기 위해 예약 되어 있습니다.                                                               |                                                                          |

## 참가자 빌드 받기 시작

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동 하 고 **시작**을 선택 합니다. Windows 참가자로 등록 하는 데 사용한 계정을 연결 합니다.

그런 다음 **Windows의 활성 개발**을 선택 하 고 **개발자 채널** 및 **베타 채널** 빌드를 받을지 여부를 선택한 다음 프로그램 약관을 검토 합니다.

**확인 > 지금 다시 시작** 을 선택 하 여 완료 합니다. 장치를 다시 부팅 한 후 **설정 > 업데이트 & 보안** 으로 이동 하 여 최신 빌드를 다운로드 > 업데이트를 확인 합니다.

## FFU 다운로드 및 플래시 방향
비행 서명 된 ffu를 사용 하 여 테스트 하려면 먼저 디바이스의 잠금을 해제 한 후에는 비행 서명 된 ffu가 깜박입니다.
1. PC:

    1. PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.
    
    1. Microsoft Store에서 ARC (고급 복구 도우미) 설치:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. HoloLens 비행 잠금 해제: **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 을 열고, 장치를 다시 부팅 합니다.

1. 플래시 FFU-이제 호를 사용 하 여 비행에 서명 된 FFU를 깜박일 수 있습니다.

## 피드백 및 보고 문제 제공

HoloLens에서 [피드백 허브 앱](hololens-feedback.md) 을 사용 하 여 피드백을 제공 하 고 문제를 보고 해 주십시오. 피드백 허브를 사용 하면 엔지니어가 신속 하 게 디버그 하 여 문제를 해결할 수 있도록 필요한 모든 진단 정보가 포함 됩니다.  HoloLens와 중국어 (일본) 버전의 문제는 같은 방식으로 보고 되어야 합니다.

> [!NOTE]
> 문서 폴더에 대 한 피드백 허브가 있는지를 묻는 메시지를 수락 하세요 (메시지가 표시 되 면 **예** 를 선택).

## 개발자를 위한 참고 사항

HoloLens의 참가자 빌드를 사용 하 여 응용 프로그램 개발을 시도 하는 것이 좋습니다.  시작 하려면 [HoloLens 개발자 설명서](https://developer.microsoft.com/windows/mixed-reality/development) 를 참조 하세요. 이 동일한 명령은 HoloLens의 참가자 빌드와 작동 합니다.  HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio의 동일한 빌드를 사용할 수 있습니다.

## 참가자 빌드 수신 중지

Windows 홀로그램의 참가자 빌드를 더 이상 수신 하지 않으려는 경우 HoloLens에서 프로덕션 빌드를 실행 하 고 있는지 확인 하거나 고급 복구 도우미를 사용 하 여 디바이스를 [복구](hololens-recovery.md) 하 여 비 참가자 버전의 Windows 홀로그램에서 장치를 복구할 수 있습니다.

> [!CAUTION]
> 새 preview 빌드를 수동으로 다시 설치한 후에는 참가자 미리 보기 빌드에서 등록을 취소 하는 알려진 문제가 파란색 화면으로 나타날 수 있습니다. 나중에 장치를 수동으로 복구 해야 합니다. 이에 대 한 자세한 내용은이 [알려진 문제](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)를 참조 하세요.

HoloLens가 프로덕션 빌드를 실행 하 고 있는지 확인 하려면 다음을 수행 합니다.

1. **설정 > 시스템 >에 대 한 정보**로 이동 하 여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.

참가자 빌드를 옵트아웃 하려면 다음을 수행 합니다.

1. 프로덕션 빌드를 실행 하는 HoloLens에서 > 설정으로 이동 하 **& 보안 > Windows 참가자 프로그램을 업데이트**한 다음 **참가자 빌드 중지**를 선택 합니다.

1. 지침에 따라 장치를 옵트아웃 합니다.
