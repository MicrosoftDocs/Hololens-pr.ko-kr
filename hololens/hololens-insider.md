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
ms.openlocfilehash: d51616f23a63c1f45fe5ed7da88be4b5429c36eb
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956774"
---
# Microsoft HoloLens 참가자 미리 보기

HoloLens에 대 한 최신 참가자 Preview 빌드에 오신 것을 환영 합니다! 이 작업을 간단 하 게 [시작](hololens-insider.md#start-receiving-insider-builds) 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 소중한 의견을 제공 하세요.

## Windows 참가자 릴리스 정보

다음은 Windows 참가자 빌드에서 오늘 사용해 볼 수 있는 예정 된 기능 목록입니다.

| 기능                                                | 설명                                                                                    | 참가자 빌드에서 사용 가능 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [자동 눈동자 위치 지원](hololens-insider.md#auto-eye-position-support)                              | 현재 위치를 찾고 정확한 홀로그램 포지셔닝을 가능 하 게 합니다.                        | 19041.1339 +                 |
| [인증서 관리자](hololens-insider.md#certificate-manager)                                     | 사용자는 설정 앱에서 인증서를 보고, 설치 및 제거 하 고, 현재 사용자 및 로컬 컴퓨터 인증서를 제거할 수 있습니다.                                         | 19041.1361 +                 |
| [USB에서 자동 시작 프로 비전](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE는 USB 드라이브에서 프로 비전 패키지를 자동으로 검색 합니다.                                | 19041.1361 +                 |
| [OOBE에서 프로 비전 패키지 자동 확인](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | OOBE에서 자동으로 프로비저닝 패키지를 적용 합니다.                                             | 19041.1361 +                 |
| [Wi-fi 연결에 Autopilot 사용](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | 이더넷 어댑터가 필요 없이 device Wi-fi의 autopilot를 사용 합니다.                             | 19041.1364 +                 |
|[Tenantlockdown CSP 및 Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | 테 넌 트 등록 및 policiy 적용 된 후 장치를 다시 설정 하거나 다시 사용할 때 해당 테 넌 트에만 장치를 등록할 수 있습니다. | 19041.1366 +|
| [전체 할당된 액세스](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | 시스템 수준에서 적용 되는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성 합니다. | 19041.1356 +                 |
| [다중 앱 키오스크에서 앱 자동 실행](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 여러 앱 키오스크 모드에 로그인 할 때 응용 프로그램이 자동으로 실행 되도록 설정 합니다.     | 19041.1346 +                 |
| [키오스크 용 방문자 자동 로그온](hololens-insider.md#visitor-auto-logon-for-kiosks)                          | 키오스크 모드에 사용할 방문자 계정에 대 한 자동 로그온을 사용 하도록 설정 합니다.                         | 19041.1361 +                 |
| [오류 처리에 대 한 키오스크 모드 동작 변경](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 키오스크 모드 오류가 이제 처리 되는 방식에 대 한 변경                                              | 19041.1356 +                 |
| [HoloLens 정책](hololens-insider.md#hololens-policies)                                      | 혼합 현실 장치에 대 한 새로운 정책.                                                        | 19041.1349 +                 |
| [오프 라인 키오스크에 대 한 AAD 그룹 구성원 캐시](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | 키오스크 모드에 사용할 수 있는 기간 (일) AAD 그룹 구성원 캐시에 대 한 정책입니다.    | 19041.1356 +                 |
| [HoloLens 2에 대 한 새 장치 제한 정책](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | 장치 관리 정책을 HoloLens 2에 대해 새로 사용 하도록 설정 했습니다.                               | 19041.1349 +                 |
| [HoloLens 2에 대 한 새 전원 정책](hololens-insider.md#new-power-policies-for-hololens-2)                      | 전원 시간 제한 설정에 대해 새로 지원 되는 정책입니다.                                           | 19041.1349 +                 |
| [업데이트 정책](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 업데이트 제어를 허용 하는 새로 사용할 수 있는 정책                                            | 19041.1352 +                 |
| [HoloLens 2에 대 한 사용 설정 페이지 표시 여부](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 설정 앱에 표시 되는 페이지를 선택 하는 정책입니다.                                           | 19041.1349 +                 |
| [업데이트의 개선 사항 및 수정](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 업데이트의 추가 수정 사항.                                                                | 19041.1361 +                 |

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

### 인증서 관리자

Windows 참가자 빌드 19041.1361 + HoloLens 2 설정 앱에서 인증서 관리자를 추가 하는 중입니다. **& 보안 > 인증서를 업데이트 > 설정**으로 이동 합니다. 이 기능을 사용 하면 간단 하 고 사용자에 게 장치에서 인증서를 보고, 설치 하 고, 제거할 수 있습니다. 새 인증서 관리자를 통해 관리자와 사용자는 향상 된 감사, 진단 및 유효성 검사 도구를 사용 하 여 디바이스를 안전 하 고 준수 하도록 유지할 수 있습니다. 

-   **감사:** 인증서가 올바르게 배포 되었는지 확인 하거나 적절 하 게 제거 되었는지 확인 하는 기능. 
-   **진단:** 문제가 발생 하면 장치에 적절 한 인증서가 있는지 확인 하 여 시간을 절약 하 고 문제를 해결 하는 데 도움이 됩니다. 
-   **유효성 검사:** 인증서가 의도 한 목적을 제공 하 고 작동 하는지 확인 하는 것은 중요 한 시간을 크게 절약할 수 있습니다.

목록에서 특정 인증서를 빠르게 찾으려면 이름, 저장 또는 만료 날짜별로 정렬 하는 옵션이 있습니다. 사용자가 직접 인증서를 검색할 수도 있습니다. 개별 인증서 속성을 보려면 인증서를 선택 하 고 **정보**를 클릭 합니다. 

인증서 설치는 현재 .cer 및 .crt 파일을 지원 합니다. 장치 소유자는 로컬 컴퓨터와 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자 에게만 설치할 수 있습니다. 사용자는 설정 UI에서 직접 설치한 인증서만 제거할 수 있습니다. 다른 수단을 통해 인증서를 설치한 경우 같은 메커니즘을 통해서도이를 제거 해야 합니다.

#### 인증서를 설치 하려면 다음을 수행 합니다. 

1.  HoloLens 2를 PC에 연결 합니다.
1.  설치할 인증서 파일을 HoloLens 2의 위치에 배치 합니다.
1.  설정 앱으로 이동 하 여 **& 보안 > 인증서를 업데이트 >** 하 고 인증서 설치를 선택 합니다.
1.  **파일 가져오기를** 클릭 하 고 인증서를 저장 한 위치로 이동 합니다.
1.  **스토어 위치**를 선택 합니다.
1.  **인증서 저장소**를 선택 합니다.
1.  **설치**를 클릭합니다.

이제 인증서가 장치에 설치 되어 있어야 합니다.

#### 인증서를 제거 하려면 다음을 수행 합니다. 
1. **설정 앱 > 업데이트 및 보안 > 인증서**로 이동 합니다.
1. 검색 상자에서 이름으로 인증서를 검색 합니다.
1. 인증서를 선택 합니다.
1. **제거** 클릭
1. 확인 메시지가 표시 되 면 **예** 를 선택 합니다.

![설정 앱의 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용 하 여 인증서를 설치 하는 방법을 보여 주는 그림](images/certificate-device-install.jpg)

### USB에서 자동 시작 프로 비전
이 빌드 사용자는 OOBE 중에 단추 조합을 사용 하 여 프로 비전 할 때 수동으로 프로비저닝 화면을 실행 해야 합니다. 이제 사용자는 USB 저장소 드라이브의 프로비저닝 패키지를 사용 하 여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE의 첫 번째 감 순간에 프로비저닝 패키지와 함께 USB 드라이브 연결
1. 디바이스를 프로 비전 할 준비가 되 면 프로 비전 페이지로 메시지가 자동으로 열립니다. 

참고: 장치를 부팅 하는 동안 USB 드라이브가 연결 된 상태에서, OOBE는 기존 USB 저장 디바이스를 열거 하 고 추가 연결을 감시할 수도 있습니다.

OOBE 중에는 프로비저닝 패키지를 적용 하는 방법에 대 한 자세한 내용은 [여기](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)를 계속 읽으십시오.

### OOBE에서 프로 비전 패키지 자동 확인
프로 비전 주 화면이 나타나면 OOBE는 자동으로 모든 프로 비전 패키지 적용을 시작 하기 전에 10 초 동안 횟수를 계산 합니다. 사용자는 예상 되는 패키지를 확인 한 후 10 초 내에 계속 확인 하거나 취소할 수 있습니다.

### UI를 사용 하지 않고 자동 프로 비전
USB 장치에서 프로 비전의 자동 실행을 결합 하 고 프로 비전 패키지의 자동 확인을 통해 디바이스의 UI를 사용 하지 않거나 장치를 착용 하지 않고 HoloLens 2 장치를 자동으로 프로 비전 할 수 있습니다. 동일한 USB 드라이브와 여러 장치에 대 한 프로비저닝 패키지를 계속 사용할 수 있습니다. 이 기능은 같은 영역에 여러 장치를 동시에 배포 하는 데 유용 합니다. 

1. [Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22)를 사용 하 여 [프로비저닝 패키지를 만듭니다](hololens-provisioning.md) . 
1. 패키지를 USB 저장소 드라이브에 복사 합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) 에서 [19041.1361 이상 빌드](https://aka.ms/hololens2previewdownload)를 플래시 합니다. 
1. [고급 복구 도우미가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 장치를 깜박이는 경우 USB-C 케이블을 뽑습니다. 
1. USB 드라이브를 장치에 연결 합니다.
1. HoloLens 2 장치가 OOBE로 부팅 되 면 USB 드라이브에서 자동으로 프로비저닝 패키지를 감지 하 고 프로비저닝 페이지를 실행 합니다.
1. 10 초 후에 장치가 프로비저닝 패키지를 자동으로 적용 합니다. 

디바이스가 이제 구성 되 고 프로 비전 성공 화면이 표시 됩니다.

### Wi-fi 연결에 Autopilot 사용
현재 OOBE 중에 HoloLens 2를 Wifi에 연결 하면 OOBE에서 디바이스에 대 한 autopilot 프로필을 확인 합니다. 하나가 발견 되 면 나머지 AAD 조인과 등록 흐름을 완료 하는 데 사용 됩니다. 즉, 이더넷을 USB C 또는 USB C 어댑터에 사용 하는 것은 필요 하지 않지만, OOBE 시작 부분에 제공 되는 경우 계속 작동 합니다. [HoloLens 2 장치에 대 한 Autopilot](hololens2-autopilot.md)에 대해 자세히 알아보세요.

### Tenantlockdown CSP 및 Autopilot
HoloLens 2 장치는 이제 Windows 참가자 빌드 19041.1366 +로 TenantLockdown CSP를 지원 합니다. 

[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용 하 여 HoloLens 2를 MDM 등록에 연결할 수 있습니다. TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false (초기 설정) 값으로 설정 되 고, 다시 깜박이는 경우, OS 업데이트 등의 장치에도 해당 값이 남아 있습니다. 

HoloLens 2에서 TenantLockdown Csp의 RequireNetworkInOOBE 노드가 true로 설정 되 면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드 되 고 적용 될 때까지 무기한 대기 합니다. 

RequireNetworkInOOBE는 HoloLens 2에서 TenantLockdown Csp의 a 노드가 true로 설정 되 면 OOBE에서 다음 작업을 허용 하지 않습니다. 
- 런타임 프로 비전을 사용 하 여 로컬 사용자 만들기 
- 런타임 프로 비전을 통해 AAD 조인 작업 수행 
- OOBE 환경에서 장치를 소유 하는 사용자 선택 

#### Intune을 사용 하 여 설정 하는 방법은 무엇 인가요? 
1. 사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정 합니다.
OMA-URI 값은/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE 설정 해야 합니다. ![ oma-uri를 통해 tennant 잠금](images/hololens-tenant-lockdown.png)
1. 그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당 합니다. 
1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작 합니다.  

장치 구성이 성공적으로 적용 되었는지 Intune 포털에서 확인 합니다. 이 장치 구성이 Hololens 2 장치에 성공적으로 적용 되 면 TenantLockdown 효과가 활성화 됩니다.

#### Intune을 사용 하 여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제 하는 방법 
1. 위에서 만든 장치 구성이 이전에 할당 된 장치 그룹에서 HoloLens 2를 제거 합니다. 
1. 사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE에 대해 false를 지정 합니다. OMA URI 값은 ![ Intune에서 OMA uri를 통해 RequireNetworkInOOBE를 false로 설정 하는/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE 스크린샷](images/hololens-tenant-lockdown-false.png)
1. 그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당 합니다. 
1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작 합니다.

장치 구성이 성공적으로 적용 되었는지 Intune 포털에서 확인 합니다. 이 장치 구성이 Hololens 2 장치에 성공적으로 적용 되 면 TenantLockdown 효과가 비활성화 됩니다. 

#### TenantLockdown true로 설정 된 후 HoloLens에서 Autopilot 프로필이 할당 되지 않은 경우 OOBE 중에 발생 하는 작업은 무엇 인가요? 
OOBE는 Autopilot 프로필이 다운로드 될 때까지 무기한 대기 하 고 대화 상자가 표시 됩니다. TenantLockdown 효과를 제거 하려면 장치를 원래 테 넌 트만 사용 하 여 먼저 등록 해야 하며, 이전 단계에서 설명한 대로 Autopilot를 설정 하지 않아야 합니다. TenantLockdown CSP에서 도입 된 제한이 제거 됩니다. 

![장치에서 정책이 적용 되는 시기에 대 한 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

### 전역 할당 액세스 – 키오스크 모드
이 새로운 기능을 사용 하면 IT 관리자가 시스템에서 사용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성 하 고 시스템의 모든 id와 관련 된 선호도가 없으며 장치에 로그인 하는 모든 사용자에 게 적용 됩니다. 이 새로운 기능에 대 한 자세한 내용은 [여기](hololens-global-assigned-access-kiosk.md)를 참조 하세요.

### 다중 앱 키오스크 모드에서 응용 프로그램 자동 실행 
이 속성은 여러 앱 키오스크 모드에만 적용 되며 지정 된 액세스 구성에서 아래의 강조 표시 되는 특성을 사용 하 여 자동 시작 하도록 지정할 수 있습니다. 

사용자가 로그인 하면 응용 프로그램이 자동으로 시작 됩니다. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 키오스크 용 방문자 자동 로그온
이 새로운 기능을 통해 방문자 계정에 대 한 자동 로그온을 키오스크 모드에 사용할 수 있습니다. 

비 AAD 구성의 경우 방문자 자동 로그온에 맞게 장치를 구성 하려면 다음을 수행 합니다.
1.  다음과 같은 프로비저닝 패키지를 만듭니다.
    1.  방문자 계정을 허용 하도록 **런타임 설정/AssignedAccess** 를 구성 합니다.
    1.  필요에 따라 MDM **(런타임 설정/작업 공간/Enrollments)** 에 디바이스를 등록 하 여 나중에 관리할 수 있도록 합니다.
    1.  로컬 계정 만들기 안 함
1.  [배포 패키지를 적용](hololens-provisioning.md)합니다.

AAD 구성의 경우 사용자는이 변경 없이 오늘 이와 비슷한 내용을 얻을 수 있습니다. 키오스크 모드용으로 구성 된 AAD 연결 디바이스는 로그인 화면에서 단추를 한 번 탭 하 여 방문자 계정에 로그인 할 수 있습니다. 방문자 계정에 로그인 한 후에는 방문자가 시작 메뉴에서 명시적으로 로그 아웃 되거나 장치가 다시 시작 될 때까지 장치에서 다시 로그인 하 라는 메시지가 표시 되지 않습니다.

### 오류 처리에 대 한 키오스크 모드 동작 변경

이전에는 키오스크 모드 적용 중 오류가 발생 하 여 시작 메뉴의 모든 응용 프로그램을 표시 하는 데 사용 되는 HoloLens가 있습니다. 이 Windows 참가자 빌드부터 오류가 발생 하는 경우 다음과 같이 시작 메뉴에 앱이 표시 되지 않습니다. 

![오류가 발생 했을 때 표시 되는 키오스크 모드의 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

### HoloLens 정책
빌드 19041.1349 +의 HoloLens 2 장치에 대 한 새 혼합 현실 정책이 생성 되었습니다. 제어 가능한 새 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음 사용 안 함, 진단 프로그램 수집 시 설정, AAD 그룹 구성원 캐시 등이 포함 됩니다.  

| 새 HoloLens 정책                                | 설명                                                                               | 참고                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 밝기 단추를 눌러도 밝기가 변경 되지 않도록 할 수 있습니다.       | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\VolumeButtonDisabled                  | 볼륨 단추를 눌러도 볼륨이 변경 되지 않도록 할 수 있습니다.               | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2에서 오디오 녹음을 할 수 없도록 마이크를 사용 하지 않도록 설정 합니다.                      | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\FallbackDiagnostics                   | 진단 로그를 수집할 수 있는 동작을 제어 합니다.                               | 0 사용 안 함, 장치 소유자에 대해 1 개 사용, 2에 모두 사용 (기본값) |
| MixedReality\HeadTrackingMode                      | 나중에 사용 하기 위해 예약 되어 있습니다.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 키오스크 대상 AAD 그룹에 AAD 그룹 구성원 캐시를 사용 하는 기간 (일 수)을 제어 합니다. | 아래를 참조 하세요.                                                           |

### 오프 라인 키오스크에 대 한 AAD 그룹 구성원 캐시

이 정책은 로그인 한 사용자에 대해 AAD 그룹을 대상으로 하는 할당 된 액세스 구성에 사용할 수 있는 시간 (일 수)에 대 한 AAD 그룹 구성원 캐시를 제어 합니다. 이 정책 값을 0 보다 큰 값으로 설정한 후에는 캐시를 사용 하지 않을 수 있습니다.  

Name: AADGroupMembershipCacheValidityInDays URI 값:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

최소-0 일  
최대 60 일 

이 정책을 올바르게 사용 하는 단계: 
1. 키오스크 대상 AAD 그룹에 대 한 장치 구성 프로필을 만들어 HoloLens 장치에 할당 합니다. 
1. 이 정책 값을 원하는 일 수 (> 0)로 설정 하 고 HoloLens 장치에 할당 하는 사용자 지정 OMA URI 기반 장치 구성을 만듭니다. 
    1. URI 값은/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays로 OMA URI 텍스트 상자에 입력 해야 합니다.
    1. 값은 허용 되는 최소값/최대값 일 수 있습니다.
1. HoloLens 디바이스를 등록 하 고 두 구성이 장치에 적용 되었는지 확인 합니다. 
1. AAD 사용자 1 로그인 허용 인터넷을 사용할 수 있게 되 면 사용자 로그인 및 AAD 그룹 구성원 자격이 성공적으로 확인 되 면 캐시를 만듭니다. 
1. 정책 값이 X 일 수를 허용 하는 경우, 이제 AAD 사용자 1이 오프 라인 상태에서 사용할 수 있으며 키오스크 모드에 사용 됩니다. 
1. 다른 AAD 사용자 N에 대해 4-5 단계를 반복할 수 있습니다. 주요 요점 여기서는 모든 AAD 사용자가 키오스크 구성을 대상으로 하는 AAD 그룹의 구성원 인지 확인할 수 있도록 먼저 인터넷을 사용 하 여 디바이스에 로그인 해야 합니다. 
 
> [!NOTE]
> AAD 사용자에 대해 4 단계를 수행할 때까지 "연결이 끊긴" 환경에서 아래 언급 된 오류 동작이 발생 합니다. 

### HoloLens 2에 대 한 새 장치 제한 정책
HoloLens 2 장치의 추가 관리 옵션을 허용 하는 새로 사용할 수 있는 정책 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

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

### HoloLens에 대해 새로 설정 된 업데이트 정책
이 업데이트 정책은 이제 HoloLens 2 장치에서 사용할 수 있습니다.
-   [업데이트/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [업데이트/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [업데이트/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [업데이트/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### HoloLens 2에 대 한 사용 설정 페이지 표시 여부
이제 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스할 수 없도록 하거나 지정 된 모든 페이지를 제외 하 고,이 정책을 사용 하도록 설정 했습니다. 이 기능을 완전히 사용자 지정 하는 방법에 대 한 자세한 내용을 보려면 아래 링크를 클릭 하세요.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![설정 앱에서 수정 되는 활성 시간 스크린샷](images/hololens-page-visibility-list.jpg)

### 업데이트의 개선 사항 및 수정 사항:
- Allow: NCM 연결에 대 한 MDM을 통해 USB 기능 열거를 사용 하지 않도록 정책을 업데이트 했습니다.
- 현재 OOBE의 다른 화면은 어둡게 모드입니다.
- 자세한 내용은 온라인의 최신 개인 정보 취급 방침을 참고 하세요.
- 사용자가 프로 비전 패키지를 통해 VPN 프로필을 프로 비전 할 수 없는 문제를 해결 했습니다.

## 참가자 빌드 받기 시작

> [!NOTE]
> 최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.
> - "장치 재부팅" 음성 명령은 제대로 작동 합니다. 
> - 설정/Windows 참가자 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 백 엔드에 버그가 있는데,이는 사용자가 직면 했을 때 다시 추적 하 게 됩니다.

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동 하 고 **시작**을 선택 합니다. Windows 참가자로 등록 하는 데 사용한 계정을 연결 합니다.

이제 Windows 참가자가 채널로 이동 하 고 있습니다. **빠른** 링이 **개발자 채널이**되 고, **느린** 고리는 **베타 채널이**되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이**됩니다. 매핑 결과는 다음과 같습니다.

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.

그런 다음 **Windows의 활성 개발**을 선택 하 고 **개발자 채널** 및 **베타 채널** 빌드를 받을지 여부를 선택한 다음 프로그램 약관을 검토 합니다.

**확인 > 지금 다시 시작** 을 선택 하 여 완료 합니다. 장치를 다시 부팅 한 후 **설정 > 업데이트 & 보안** 으로 이동 하 여 최신 빌드를 다운로드 > 업데이트를 확인 합니다.

## FFU 다운로드 및 플래시 방향
비행 서명 된 ffu를 사용 하 여 테스트 하려면 먼저 디바이스의 잠금을 해제 한 후에는 비행 서명 된 ffu가 깜박입니다.
1. PC:

    1. PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.
    
    1. Microsoft Store에서 ARC (고급 복구 도우미) 설치: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
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
