---
title: Microsoft HoloLens 참가자 미리 보기
description: 참가자 빌드를 시작하고 HoloLens에 대한 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공하는 것은 간단합니다.
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
ms.openlocfilehash: 1e6b8fcfad1dab49823f38c722de33654b361f58
ms.sourcegitcommit: 16d61083a1da8007278aed7e11eb6d44f7a90952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941689"
---
# Microsoft HoloLens 참가자 미리 보기

HoloLens용 최신 Insider Preview 빌드를 소개합니다. 간단히 시작하고 [get started](hololens-insider.md#start-receiving-insider-builds) HoloLens에 대한 다음 주요 운영 체제 업데이트에 대한 가치 있는 피드백을 제공해 드리겠습니다.

## Windows 참가자 릴리스 정보

다음은 Windows 참가자 빌드에서 오늘 출시할 수 있는 예정된 기능 목록입니다.

| 기능                                                | 설명                                                                                    | 참가자 빌드 사용 가능 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [자동 완화 기능](hololens-insider.md#auto-eye-position-support)                              | 적시중하게 위치를 찾아 정확한 하으로그래머 위치를 정확하게 설정합니다.                        | 19041.1339 이상                 |
| [인증서 뷰어](hololens-insider.md#certificate-viewer)                                     | 설정 앱에서 사용자 및 장치 인증서를 볼 수 있습니다.                                         | 19041.1346+                 |
| [인증서 설치 및 제거](hololens-insider.md#install-and-remove-certificates)                        | 사용자는 인증서 뷰어를 사용하여 인증서를 설치하고 제거할 수 있습니다.                        | 19041.1361 이상                 |
| [USB에서 자동 시작 프로비전](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE는 USB 드라이브에 패키지 프로비전 패키지를 자동으로 감지합니다.                                | 19041.1361 이상                 |
| [OOBE의 자동 프로비저닝 패키지 프로비저닝 확인](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | OOBE에 는 프로비전 패키지를 자동으로 적용할 수 있습니다.                                             | 19041.1361 이상                 |
| [Wi-Fi 연결을 사용한 Autopilot 사용](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | 이더넷 어터가 필요 없이 장치 Wi-Fi에서 자동 픽피트를 사용합니다.                             | 19041.1364+                 |
|[테넌트 잠금 CSP 및 Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | 테넌트 등록 및 정책이 적용된 후에는 장치가 재설정되거나 플래시될 때마다 해당 테넌트에만 장치를 등록할 수 있습니다. | 19041.1366+|
| [전체 할당된 액세스](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | 시스템 수준에 적용되는 여러 앱 시작 모드에 대해 HoloLens 2 장치를 구성합니다. | 19041.1356+                 |
| [다중 앱 키 오스크에서 앱 자동 실행](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 다중 앱을 수개 개수 모드에 로그인할 때 응용 프로그램이 자동으로 시작하도록 설정합니다.     | 19041.1346+                 |
| [Kiosks의 자동 로그온 방문](hololens-insider.md#visitor-auto-logon-for-kiosks)                          | 키오스크 모드에 대해 방문자 계정의 자동 로그온을 사용할 수 있습니다.                         | 19041.1361 이상                 |
| [오류를 숨겨야 하는 Kiosk 모드 동작 변경](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 선택 모드 오류가 어떻게 해결됩니다.                                              | 19041.1356+                 |
| [HoloLens 정책](hololens-insider.md#hololens-policies)                                      | 혼합 현실 장치에 대한 새로운 정책.                                                        | 19041.1349+                 |
| [오프라인 Kiosk의 캐시 AAD 그룹 멤버 자격](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | AAD 그룹 멤버 자격 캐시를 키오스크 모드에 사용할 수 있는 일수에 대한 정책입니다.    | 19041.1356+                 |
| [HoloLens 2에 대한 새 장치 제한 정책](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | 장치 관리 정책을 사용하여 HoloLens 2에 새로 활성화할 수 있습니다.                               | 19041.1349+                 |
| [HoloLens 2에 대한 새로운 전원 정책](hololens-insider.md#new-power-policies-for-hololens-2)                      | 새로 지원되는 전원 시간 초과 설정에 대한 새로 지원됩니다.                                           | 19041.1349+                 |
| [정책 업데이트](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 새로 사용되는 정책이 업데이트 제어를 허용합니다.                                            | 19041.1352 이상                 |
| [HoloLens 2에 대한 활성화된 설정 페이지 표시 여부](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 설정 앱에 표시할 페이지를 선택하는 정책입니다.                                           | 19041.1349+                 |
| [업데이트의 개선 사항 및 해결](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 업데이트에 대한 추가 수정 사항                                                                | 19041.1361 이상                 |

### 자동 완화 기능

HoloLens 2에서 시멘트 기능을 사용하면 정확한 하로그로그로 위치를 정확히 감정해 보고 환경을 조성하고 디스플레이 품질이 향상되었습니다. 시각적 위치는 시각적 추적 결과의 일부로 컴파일됩니다. 하지만 경험하기 위해서는 인기 입력을 선택할 필요가 없더라도 사용자가 인기 추적 설정을 진행해야 합니다.

**AEP(자동 중문 기능)를** 사용하여 이러한 시나리오를 사용자의 눈이 편리한 통합 방법으로 컴퓨팅할 수 있습니다.  자동 연결 위치는 사용자가 잠시 장치를 설정할 때 자동으로 백그라운드에서 작업을 시작합니다. 사용자가 이전 눈에 일주일 안의 눈을 추적하는 보험이 없는 경우 자동 차원 위치를 설정하면 소규모 처리 시간이 지나면서 표시 시스템의 눈이 표시됩니다. 일반적으로 처리 시간은 20초에서 60초입니다. 사용자 데이터는 장치에서 지워지지 않으며 사용자가 장치를 해제하고 장치를 다시 부각하거나 장치가 다시 부기를 마무리하는 경우 이 프로세스가 반복됩니다.  

기간이 없는 사용자가 장치에 표시하는 경우 자동 Eye 위치 기능을 사용하여 몇 가지 시스템 동작이 적용되었습니다. 명시되지 않은 사용자는 이전에 장치에서 눈이 조금 별 모를 때 변경 내용을 추적하는 사람을 지칭합니다.

|     활성 응용 프로그램                           |     현재 동작                                   |     Windows 참가자 빌드 19041.1339 이상                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     비G가 활성화된 앱 또는 HolographicShell    |     일단 추적 하이라는 메시지가 표시됩니다.    |     표시되는 메시지가 표시되지 않습니다.                                                                                |
|     Gaze 사용 앱                             |     일단 추적 하이라는 메시지가 표시됩니다.    |     응용 프로그램이 눈의 스트림에 액세스하는 행간에 한정적으로 추적 프롬프트가 표시됩니다.     |

 사용자가 부가금이 아닌 응용 프로그램에서 데이터에 액세스하는 응용 프로그램으로 전환하면 자동 차세프 프롬프트가 표시됩니다. 기본 경험 흐름은 변경되지 않습니다. 
 
눈이 데이터를 주로 화이하거나 정밀 한개의 집중 치열 사지 기능이 필요한 환경을 위해 계열 추적 프롬프트에서 보기 전달의 토글을 실행하거나 시작 메뉴에서 설정 앱을 시작한 다음 시스템 > 보일 게이브 **레이블리 >션> 실행**

**알려진 문제**
 - 메모리 로드 시 Eye Tracker 드라이버 호스트 프로세스가 충돌할 수 있는 문제를 조사 중입니다. 과보기 추적 드라이버 호스트 프로세스는 자동 복구해야 합니다.

### 인증서 뷰어

Windows 참가자 빌드 19041.1346 이상에서 HoloLens 2 설정 앱에 인증서 뷰어가 추가됩니다. 인증서 설치는 현재 .cer 및 .crt 파일을 지원합니다. 장치 소유자는 로컬 컴퓨터및 현재 사용자에서 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자에게만 설치할 수 있습니다. 사용자는 설정 UI에서 직접 설치된 인증서만 제거할 수 있습니다. 인증서가 다른 방법을 통해 설치된 경우 동일한 메이크패까지도 제거해야 합니다.

-   **감사:** 인증서가 제대로 배포되었는지 확인하거나 인증서가 제대로 제거되었는지 확인하는 기능 
-   **진단:** 문제가 발생하면 장치에 적절한 인증서가 존재한다는 점을 검사하고 문제 해결에 도움이 됩니다. 
-   **유효성 검사:** 인증서가 그의 용도를 이용하고 작동하는지 확인하면 더 큰 규모로 인증서를 배포하기 전에 상업적인 환경에서 상세한 시간을 절약할 수 있습니다.

인증서를 보 >려면 업데이트 & **인증서를 > 탭으로 이동합니다.**

![설정 앱의 인증서 뷰어](images/certificate-viewer-device.jpg)

### 인증서 설치 및 제거
Windows 참가자 릴리스 19041.1361+ 시작하면 설정 앱을 통해 HoloLens 2에서 직접 인증서를 설치하고 제거할 수 있습니다. 인증서 설치는 현재 .cer 및 .crt 파일을 지원합니다. 장치 소유자는 로컬 컴퓨터및 현재 사용자에서 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자에게만 설치할 수 있습니다. 사용자는 설정 UI에서 직접 설치된 인증서만 제거할 수 있습니다. 인증서가 다른 방법을 통해 설치된 경우 동일한 메이크패까지도 제거해야 합니다.

#### 인증서 뷰어를 사용하여 인증서를 설치하려면 
1. 설정 **앱 업데이트**및  ->  **보안**  ->  **인증서로**이동하고 **인증서 설치를 선택합니다.** 
1. 파일 선택기 환경에서 .cer 파일을 선택합니다.
1. 로컬 컴퓨터(또는 인증서가 있는 곳)를 선택합니다.)
1. **인증서** 저장소로 루트(또는 인증서를 배치할 스토어)를 선택합니다. 
1. **설치**를 클릭합니다.

이제 인증서가 장치에 설치되어 있어야 합니다.

#### 인증서 뷰어를 사용하여 인증서를 제거하려면 
1. 설정 **앱 업데이트**  ->  **및 보안**  ->  **인증서로 이동합니다.**
1. 검색 상자에서 이름으로 인증서를 검색합니다.
1. 인증서를 선택합니다.
1. **제거클릭**
1. 메시지가 표시되면 예를 선택하고 확인 메시지가 표시되면

![인증서 UI를 사용하여 인증서를 설치하는 방법을 보여주는 그림](images/certificate-device-install.jpg)

#### 알려진 문제 
파일 선택기에서 인증서를 선택한 후 설치 중에 선택된 인증서 파일이 표시되지 않는다는 것에 대해 조사하고 있습니다. 파일을 선택한 후에는 대화 상자에 파일이 나타나지 않다하더라도 설치를 진행할 수 있습니다. 

### USB에서 자동 시작 프로비전
OOBE에서 단추 조합을 사용해 프로비전하는 과정을 시작하기 전에 이 빌드 사용자가 프로비전 화면을 시작해야 했습니다. 이제 사용자는 USB 저장소 드라이브에서 프로비전 패키지를 사용하여 버튼 조합을 건너뛸 수 있습니다. 

1. OOBE의 첫 번째 인터페이스 이동에 프로비전 패키지를 사용하여 USB 드라이브에 연결
1. 장치를 프로비전할 준비가 되면 프로비전 페이지가 있는 프롬프트를 자동으로 엽니다. 

참고: USB 드라이브가 연결되어 있을 때 장치가 부족하는 동안 동안 동안 연결되어 있으면 기존 USB 저장장치 디바이스가 열거되고 플러그 인될 추가 장치가 있는지 관시를 확인합니다.

OOBE 에서 프로비전 패키지를 적용하는 방법에 대한 자세한 내용을 보려면 여기를 계속 [하세요.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### OOBE의 자동 프로비저닝 패키지 프로비저닝 확인
프로비전 기본 화면이 생성되면, OOBE는 모든 프로비전 패키지를 자동으로 적용하기 시작하기 전에 10초 간소화됩니다. 사용자는 예상한 패키지를 확인한 후 이 10초 내에 참여하거나 취소할 수 있습니다.

### UI를 사용하지 않고 자동 구매
USB 장치에서 프로비전 및 디바이스 자동 확인을 결합하면 사용자는 장치의 UI를 사용하거나 장치를 사용하지 않고도 HoloLens 2장치를 자동으로 프로비전할 수 있습니다. 여러 장치에서 동일한 USB 드라이브를 계속 사용하고 패키지를 프로비전할 수 있습니다. 이 기능은 같은 영역에 여러 장치를 한 번에 배제하는 경우 유용합니다. 

1. Windows [구성 디자이너를 사용하여 프로비전](hololens-provisioning.md) [패키지를 만듭니다.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. 패키지를 USB 저장소 드라이브로 복사합니다.
1. [HoloLens 2에서](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361 이상 빌드를 플래시합니다.](https://aka.ms/hololens2previewdownload) 
1. USB-C [cable을 플래그](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 를 플래그 를 플래그 를 플래그 를 플래그 사용하지 않기 시작했습니다. 
1. USB 드라이브를 장치에 연결합니다.
1. HoloLens 2 장치가 OOBE에 부스위로 부여될 경우 USB 드라이브에서 프로비전 패키지를 자동으로 감지하고 프로비전 페이지를 시작합니다.
1. 10초 후 디바이스는 프로비전 패키지를 자동으로 적용합니다. 

이제 장치가 구성되어 프로비전 성공 화면이 표시됩니다.

### Wi-Fi 연결을 사용한 Autopilot 사용
이제 OOBE에서 HoloLens 2를 Wifi에 연결하면 OOBE에서 장치에 대한 Autopilot 프로필을 확인합니다. 일을 발용할 경우 AAD 조인 및 등록 흐름의 나중에 완료하는 용도로 사용됩니다. 즉, 이더넷을 USB C 또는 USB C 어터터에 더 이상 사용하고 있는 경우 아니지만 OOBE의 시작 부분에 제공된 경우 계속 작동합니다. [HoloLens 2 장치용 Autopilot에 대해 자세히 알아봅니다.](hololens2-autopilot.md)

### 테넌트 잠금 CSP 및 Autopilot
HoloLens 2 장치는 이제 Windows 참가자 빌드 19041.1366 이상의 TenantLockdown CSP를 지원합니다. 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP를 사용하면 HoloLens 2를 Autopilot을 사용하여 MDM 등록에 연결할 수 있습니다. TenantLockdown CSP의 RequireNetworkInOBE 노드가 true 또는 False(초기 설정) 값으로 설정되면 값이 장치에 다시 플래시 작동, OS 업데이트 등에 유지됩니다. 

TenantLockdown CSPs'RequireNetworkInOBE 노드가 HoloLens 2에서 true로 설정되면, OOBE는 네트워크 연결 후 Autopilot 프로필이 성공적으로 다운로드되어 적용되도록 무기한으로 기다립니다. 

TenantLockdown CSPs'RequireNetworkInOBE 노드가 True로 설정되면 OOBE에서 다음 작업을 할 수 없습니다. 
- 런타임 프로비전을 사용하여 로컬 사용자 만들기 
- 런타임 프로비저닝을 통해 AAD 조인 작업 수행 
- OOBE 환경에서 장치를 소유하고 있는 사용자 선택 

#### Intune을 사용하여 이를 설정하려면 어떻게 해야 합니다. 
1. 사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래 표시된 대로 RequireNetworkInOBE 노드에 대해 true를 지정합니다.
OMA-URI 값은 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOBE ![ 설정 테넌트 잠금을 설정해야 합니다. OMA-URI를 iia-URI를 기한다리는 것을 볼 수 있습니다.](images/hololens-tenant-lockdown.png)
1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다. 
1. HoloLens 2 장치 멤버를 이전 단계에서 생성하고 동기화를 트리거합니다.  

Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다. 이 장치 구성이 Hololens 2 장치에 성공적으로 적용되면 TenantLockdown의 영향이 활성화됩니다.

#### Intune을 사용하여 HoloLens 2의 테넌트Lockdown의 RequireNetworkInOBE의 필수 인을 설정 해제하는 방법은 무엇인가요? 
1. 위에서 만든 장치 구성이 지정된 장치 그룹에서 HoloLens 2를 제거합니다. 
1. 사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래 표시된 대로 RequireNetworkInOOBE의 false를 지정합니다. OMA-URI 값은 ![ Intune에서 OMA URI를 False로 설정하는 데 필요한 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOBE 스크린샷이어야 합니다.](images/hololens-tenant-lockdown-false.png)
1. 그룹을 만들고 해당 장치 그룹에 장치 구성 프로필을 할당합니다. 
1. HoloLens 2 장치 멤버를 이전 단계에서 생성하고 동기화를 트리거합니다.

Intune 포털에서 장치 구성이 성공적으로 적용되었는지 확인합니다. 이 장치 구성이 Hololens 2 장치에 성공적으로 적용되면 TenantLockdown을 적용한다는 메시지는 비활성화됩니다. 

#### OOBE에서 TenantLockdown이 true로 설정된 후 HoloLens에 Autopilot 프로필이 할당되지 않으면 어떻게 되나요? 
Autopilot 프로필을 다운로드하고 팔로우할 수 있는 대화 상자가 무기다간 OOBE가 표시될 것입니다. TenantLockdown 효과를 제거하려면 먼저 Autopilot을 사용하여 원래 테넌트에 등록되어 있어야 하며 테넌트 Lock CSP에 의해 소개되기 전에 이전 단계에서 설명한 것과 마련된 것과 완전히 원래 테넌트에 설명되어야 합니다. 

![정책이 장치에 적용되는 경우의 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

### 글로블 할당된 액세스 – 키오스크 모드
이 새로운 기능을 통해 IT 관리자는 시스템 수준에서 적용되는 여러 앱 시작 모드에 맞게 HoloLens 2 장치를 구성할 수 있으며 시스템의 ID는 마음에 들지 않고 장치에 로그인한 모든 사용자에게 적용됩니다. 이 새 기능에 대한 자세한 내용은 [여기를 참조하세요.](hololens-global-assigned-access-kiosk.md)

### 여러 앱 시작 모드에서 응용 프로그램 자동 실행 
적용 하는 앱의 경우 지정된 Access 구성에서 아래의 강조 표시된 특성을 사용하여 자동 시작으로 지정할 수 있습니다. 

사용자가 로그인하면 자동으로 응용 프로그램이 시작됩니다. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Kiosks용 자동 로그온 방문
이 새로운 기능을 사용하면 키오스크 모드에 대해 자동 로그온을 사용할 수 있습니다. 

AAD 비보안 구성의 경우 방문자 자동 로그온을 위한 장치를 구성하려면 다음을 실행합니다.
1.  다음과 해당하는 프로비전 패키지를 만듭니다.
    1.  방수 **계정을 허용하도록 런타임 설정/AssignedAccess를** 구성합니다.
    1.  필요에 따라 나중에 관리할 수 있도록 **MDM(런타임 설정/작업 공간/등록)에** 장치를 등록합니다.
    1.  로컬 계정을 만들지 마세요.
1.  [프로비전 패키지를 적용합니다.](hololens-provisioning.md)

AAD 구성에서, 사용자는 이러한 변경 없이 현재와 비사하여 수행할 수 있습니다. 키오스크 모드에 대해 연결된 AAD가 키오는 장치는 로그인 화면에서 단일 단추를 탭하여 방문자 계정에 로그인할 수 있습니다. 방문자 계정에 로그인하면 방문자가 시작 메뉴 또는 장치를 다시 시작할 때까지 장치에서 다시 로그인하라는 메시지가 표시되지 않습니다.

### 오류를 숨겨야 하는 Kiosk 모드 동작 변경

키오스크 모드 적용시처 실패가 발생하더라도 HoloLens는 시작 메뉴에 모든 응용 프로그램을 표시하는 것을 사용했습니다. 오류가 발생할 경우 시작 메뉴에 앱이 없으면 다음과 같은 앱이 시작 메뉴에 표시됩니다. 

![선택 모드가 실패할 때 어떻게 보이는지를 이미지로 보이는 이미지](images/hololens-kiosk-failure-behavior.png )

### HoloLens 정책
빌드 19041.1349+를 사용하는 HoloLens 2 장치가 새로운 혼합 현실 정책이 생성되었습니다. 새로운 컨트롤 사용 가능한 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음 비순위 지정, 진단이 수집될 때 설정 및 AAD 그룹 멤버 자격 캐시 등이 있습니다.  

| New HoloLens 정책                                | 설명                                                                               | 참고                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 밝기 단추를 사용하지 않도록 설정하여 밝기를 변경하지 않도록 합니다.       | 1/Yes, 0 No(기본값)                                                |
| MixedReality\VolumeButtonDisabled                  | 볼륨 단추를 사용하지 않도록 설정하여 볼륨을 변경하지 않도록 할 수 있습니다.               | 1/Yes, 0 No(기본값)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2에서 오디오 녹음/녹화가 가능하도록 마이크를 비활성화합니다.                      | 1/Yes, 0 No(기본값)                                                |
| MixedReality\FallbackDiagnostics                   | 진단 로그를 수집할 때의 컨트롤 동작입니다.                               | 0 사용 안 함, 1 장치 소유자에 대해 사용, 2는 모든에 대해 사용 가능(기본값) |
| MixedReality\HeadTrackingMode                      | 향후 사용을 위한 예정되어 있습니다.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | AAD 그룹을 대상으로 하는 Kiosk kiosk에 사용되는 AAD 그룹 멤버 자격 캐시의 수를 제어합니다. | 아래를 참조하세요.                                                           |

### 오프라인 Kiosk의 캐시 AAD 그룹 멤버 자격

이 정책은 로그인된 사용자를 대상으로 AAD 그룹을 대상으로 하는 할당된 액세스 구성에 사용할 수 있는 일 수를 제어합니다. 이 정책 값이 0보다 크게 값으로 설정된 다음 그렇지 않게 단락이 사용되지 않습니다.  

이름: AADGroupMembershipCacheValidityInDays URI 값: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

최소 - 0일  
최대 - 60일 

이 정책을 올바르게 사용하는 단계: 
1. AAD 그룹을 대상으로 하는 잉크 주간 장치 구성 프로필을 만들고 HoloLens 장치에 할당합니다. 
1. 이 정책 값을 원하는 일 수(> 0)로 설정하고 HoloLens 장치에 할당하는 사용자 지정 OMA URI 기반 장치 구성을 만드세요. 
    1. URI 값은 OMA-URI 텍스트 상자에 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays로 입력해야 합니다.
    1. 값이 최소/최대 허용일 수 있습니다.
1. Holll HoloLens 장치를 등록하고 두 구성이 모두 장치에 적용되는지 확인합니다. 
1. 인터넷을 사용할 수 있는 경우 AAD 사용자 1 로그인과 AAD 그룹 멤버 자격이 확인되면 캐시가 만들어집니다. 
1. 이제 AAD 사용자 1에서 HoloLens를 오프라인으로 사용하고 정책 값이 X일수를 허용하는 경우 키오스크 모드에 사용하면 됩니다. 
1. 4단계와 5단계는 다른 모든 AAD 사용자 N에 대해 반복할 수 있음을 확인합니다. 키를 사용할 경우 최소한 한 번은 인터넷을 사용하여 장치에 로그인해야 하므로 한 번 이상은 어떤 Kiosk 구성의 구성원인지 확인할 수 있음을 확인할 수 있다는 것입니다. 
 
> [!NOTE]
> AAD 사용자에 대해 4단계를 수행할 때까지는 아래 "연결되지 않은" 환경에서 아래에 나오는 실패 동작을 경험합니다. 

### HoloLens 2에 대한 새 장치 제한 정책
HoloLens 2 장치의 추가 관리 옵션을 사용할 수 있는 새로 지원되는 정책입니다. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

### Hololens 2에 대한 새로운 전원 정책
새로 추가된 정책을 통해 관리자는 유출 시간 제한과 같은 전원 상태를 제어할 수 있습니다. 각 개별 정책에 대한 자세한 내용을 읽어보려면 해당 정책의 링크를 클릭하세요.

|     정책 설명서 링크                |     참고                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 구성 디자이너에서 사용해야 하는 예제 값(예:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 구성 디자이너에서 사용해야 하는 예제 값(예:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 구성 디자이너에서 사용해야 하는 예제 값( 예: 1000000)                                                                             |
|     [EnergySaverBatteryThresholdPlugedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 구성 디자이너에서 사용해야 하는 예제 값( 예: 1000000)                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 구성 디자이너에서 사용해야 하는 예제 값(예:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPlugedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 구성 디자이너에서 사용해야 하는 예제 값(예:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### 새로 지원되는 HoloLens용 업데이트 정책
이제 HoloLens 2 장치에서 이러한 업데이트 정책을 사용할 수 있습니다.
-   [업데이트/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [업데이트/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### HoloLens 2에 대한 활성화된 설정 페이지 표시 여부
이제 IT 관리자가 시스템 설정 앱의 특정 페이지가 표시되거나 액세스할 수 없습니다. 또는 지정한 페이지를 제외한 모든 페이지에서 이 작업을 수행할 수 없습니다. 이 기능을 완전히 사용자 지정하는 방법을 알아보려면 아래 링크를 클릭하세요.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![설정 앱에 수정되는 활성 시간 스크린샷](images/hololens-page-visibility-list.jpg)

### 업데이트의 개선 사항 및 해결:
- AllowUsbConnection에서 NCM을 통해 USB 함수의 열거를 비활성화하기 위한 정책이 업데이트되었습니다.
- OOBE의 더 많은 화면이 어두운 모드로 있습니다.
- 더 많은 콘텐츠는 온라인으로 최신 개인 정보 취급 방침을 가리키어야 합니다.
- 사용자가 프로비전 패키지를 통해 VPN 프로필을 프로비전할 수 없는 문제와 문제를 해결했습니다.

## Insider 빌드 받기 시작

> [!NOTE]
> 최근에 업데이트하지 않은 경우 장치를 다시 부적절하게 업데이트하고 최신 빌드를 받습니다.
> - "장치 다시 부우트 장치" 음성 명령이 작동합니다. 
> - 설정/Windows 참가자 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 발생할 수 있는 백 엔드에 버그가 있어 원인이 되돌아가게 됩니다.

HoloLens 2 장치에서는 **Settings**설정 업데이트 옵션에  >  **& 보안**Windows 참가자  >  **프로그램으로 이동하고** **시작을 선택합니다.** Windows 참가자로 등록하는 에 사용한 계정을 연결합니다.

이제 Windows 참가자가 채널로 이동합니다. 초기 **고리는** 개발 채널이 **됩니다.** **이후** 신용 여부는 **Beta 채널이**되며, 릴리스 **미리** 보기 신여가 **릴리스 Preview 채널이 됩니다.** 매핑의 모양은 다음과 같습니다.

![Windows 참가자 채널에 대한 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows [블로그의 Windows 참가자 채널 소개를](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 참조하세요.

그런 다음 **Windows의 활성 개발을**선택하고 개발자 채널 빌드 또는 Beta **채널** 빌드를 **받을지** 여부를 선택한 다음 프로그램 용어를 검토합니다.

**요금제를 선택하고 > 다시 시작해 마세요.** 디바이스가 다시 부크로 나면 설정 **업데이트 >에서 사용할 & 업데이트를 >** 최신 빌드를 가져오세요.

## FFU 다운로드 및 플래시 길 제안
플라이트 서명된 플래그와 테스트하려면 플라이트 서명된 플래그를 플래그하기 전에 플라이트 장치의 잠금을 해제해야 합니다.
1. PC에서:

    1. PC에 프레앱을 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.
    
    1. Microsoft Store에서 ARC(고급 복구 도우미)를 설치합니다. [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. HoloLens - 플라이트 잠금 **Settings**해제: Windows  >  **&**  >  **프로그램에 대한 설정 업데이트 열기** 후 다시 부호 장치에 등록하세요.

1. FFU - 이제 ARC를 사용하여 플라이트 서명된 FFU를 플래시할 수 있습니다.

## 피드백을 제공하고 문제 보고

HoloLens에서 [피드백 Hub](hololens-feedback.md) 앱을 사용하여 피드백을 제공하고 문제를 보고하세요. 피드백 하이브를 사용하면 엔지니어가 빠르게 디버그를 디버그하고 해결할 수 있게 필요한 모든 진단 정보가 포함됩니다.  중국어 및 일본어 버전의 HoloLens와 관련된 문제는 동일한 방법으로 보고되어야 합니다.

> [!NOTE]
> 사용자의 문서 폴더에 액세스하려면 피드백 Hub를 사용할지(메시지가 표시되면 예 선택 선택)할지 **여부를** 선택하는 메시지를 수락해야 합니다.

## 개발자를 위한 참고 사항

HoloLens의 참가자 빌드를 사용하여 응용 프로그램을 개발해 보는 것을 선려한 사용자만의 시도해 보세요.  [HoloLens 개발자 설명서를](https://developer.microsoft.com/windows/mixed-reality/development) 확인하여 시작하세요. 이러한 지침은 HoloLens의 참가자 빌드에서도 함께 사용됩니다.  이미 HoloLens 개발에 사용 중인 Visual Studio 유니티티 및 유니티티 빌드를 사용할 수 있습니다.

## Insider 빌드 수신 중지

Windows Holographic에 대한 참가자 빌드를 더 이상 받지 않으려는 경우 HoloLens가 프로로세션 빌드를 [recover your device](hololens-recovery.md) 실행할 때 Optout을 받거나 고급 복구 도우미로 디바이스를 복구하고 이외 버전의 Windows Holographic에 디바이스를 복구할 수 있습니다.

> [!CAUTION]
> 새로 워드 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 취소하는 사용자에게 파란색 화면이 되는 알려진 문제가 있습니다. 나중에는 장치를 수동으로 복구해야 합니다. 영향을 주거나 영향을 주지 않는 경우 자세한 내용은 이 알려진 문제에 대해 [자세히 알려주세요.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

HoloLens가 프로파일션 빌드를 실행하고 있는지 확인하려면

1. 설정 > **시스템 설정으로 > 정보에서**빌드 번호를 찾습니다.

1. [프로로제이션 빌드 번호에 대한 릴리스 정보를 확인하세요.](hololens-release-notes.md)

참가자 빌드를 사용하지 않아웃하려면

1. 프로세션 빌드를 실행하는 HoloLens에서 **> 업데이트& 보안 > Windows 참가자 프로그램으로**이동하고 **참가자 빌드를 선택합니다.**

1. 장치를 선택하려면 지침을 따릅니다.
