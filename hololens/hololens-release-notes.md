---
title: HoloLens 2 릴리스 정보
description: 각각의 새 HoloLens 2 릴리스의 업데이트에 대해 알아봅니다.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 0825e3fd2d0a4e6328eaa617e4233639f481e8cb
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163153"
---
# HoloLens 2 릴리스 정보

HoloLens 장치를 능숙 하 게 사용할 수 있도록 기능, 버그, 보안 업데이트를 계속 릴리스 합니다. 이 페이지에서는 매달 HoloLens에 대 한 새로운 기능을 확인할 수 있습니다. [고급 복구 도우미를 통해 장치를 플래시](hololens-recovery.md#clean-reflash-the-device)하기 위해 최신 HoloLens 2 Full Flash 업데이트 (ffu)를 얻으려면 [여기서 다운로드](https://aka.ms/hololens2download)하세요. 다운로드는 최신 상태로 유지 되며 일반적으로 사용할 수 있는 최신 빌드를 제공 합니다.

>[!NOTE]
> HoloLens 에뮬레이터 릴리스 노트를 읽으려면 [보관 파일을 방문](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)하세요.

## Windows 홀로그램, version 20H2
- 빌드 19041.1128

이제 Windows 홀로그램, 버전 20H2를 사용할 수 있으며, HoloLens 2 사용자 및 IT 전문가를 위한 훌륭한 새로운 기능 집합을 제공 합니다. 자동 눈동자 위치, 설정의 인증서 관리자에서 키오스크 모드 기능 향상, 새로운 Autopilot 설정 기능을 제공 합니다. 이 새로운 업데이트를 통해 IT 팀이 HoloLens 장치를 구성 하 고 관리 하는 것이 보다 세밀 하 게 제어 하 고 사용자에 게 더욱 원활한 홀로그램 환경을 제공할 수 있습니다. 

이 최신 릴리스는 버전 2004에 대 한 월간 업데이트로, 이번에는 새로운 기능을 포함 하 고 있습니다. 주 빌드 번호는 동일 하 게 유지 되며 Windows 업데이트는 버전 2004 (빌드 19041)에 대 한 월간 릴리스를 나타냅니다. 설정에서 빌드 번호 > 화면에 대 한 정보를 확인 하 여 사용 가능한 최신 빌드 19041.1128 +를 확인할 수 있습니다. 최신 릴리스로 업데이트 하려면 설정 앱을 열고 업데이트 & 보안으로 이동한 다음 업데이트 확인을 탭 합니다. HoloLens 업데이트를 관리 하는 방법에 대 한 자세한 내용은 [이 페이지](https://docs.microsoft.com/hololens/hololens-updates)를 참조 하세요.

### Windows 홀로그램의 새로운 기능, 버전 20H2  

| 기능                                              | 설명                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [자동 눈동자 위치 지원](hololens-release-notes.md#auto-eye-position-support) | 사용자가 활성 보정을 진행 하지 않고 눈 위치를 적극적으로 계산 합니다.   |
| [인증서 관리자](hololens-release-notes.md#certificate-manager)   | 더 간단한 새 방법으로 설정 앱에서 인증서를 설치 및 제거할 수 있습니다.     |
| [USB에서 자동 시작 프로 비전](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 드라이브의 제공 패키지는 자동으로 OOBE의 프로 비전 페이지에 표시 됩니다.                                                         |
| [OOBE에서 프로 비전 패키지 자동 확인](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 프로 비전 패키지는 제공 페이지에서 OOBE 중에 자동으로 적용 됩니다.                                                         |
| [UI를 사용 하지 않고 자동 프로 비전](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 프로비저닝 자동 실행을 결합 하 고 함께 자동 확인 하는 방법 |
| [Wi-Fi 연결에 Autopilot 사용](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Wi-Fi 장치에서 이더넷 어댑터가 필요 없이 autopilot를 사용 합니다. |
| [Tenantlockdown CSP 및 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 테 넌 트 등록 및 정책이 적용 된 후 장치를 다시 설정 하거나 다시 사용할 때 해당 테 넌 트에만 장치를 등록할 수 있습니다. |
| [전체 할당된 액세스](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 시스템 수준에서 키오스크를 적용 하는 여러 앱 키오스크 모드에 대 한 새로운 구성 방법으로,이 방법을 모두에 게 적용할 수 있습니다.                  |
| [다중 앱 키오스크에서 앱 자동 실행](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 여러 앱 키오스크 모드에 로그인 할 때 응용 프로그램이 자동으로 실행 되도록 설정 합니다.                                                        |
| [오류 처리에 대 한 키오스크 모드 동작 변경](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 이제 키오스크 모드 오류는 제한 된 fallback을 갖습니다.                                                                                                |
| [HoloLens 정책](hololens-release-notes.md#hololens-policies)                                    | HoloLens에 대 한 새로운 정책.     |
| [오프 라인 키오스크에 대 한 AAD 그룹 구성원 캐시](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | 새 정책을 통해 사용자는 그룹 구성원 캐시를 사용 하 여 오프 라인 모드를 설정 된 일 수로 사용할 수 있습니다.                                        |
| [HoloLens 2에 대 한 새 장치 제한 정책](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 장치 관리 정책을 HoloLens 2에 대해 새로 사용 하도록 설정 했습니다.                                                                                |
| [HoloLens 2에 대 한 새 전원 정책](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 전원 시간 제한 설정에 대해 새로 지원 되는 정책입니다.  |
| [업데이트 정책](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 업데이트 제어를 허용 하는 새로 사용할 수 있는 정책           |
| [HoloLens 2에 대 한 사용 설정 페이지 표시 여부](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 설정 앱에 표시 되는 페이지를 선택 하는 정책입니다.             |
| [리서치 모드](hololens-release-notes.md#research-mode) | HoloLens 2에서 리서치 모드를 사용 합니다. |
| [기록 길이 증가](hololens-release-notes.md#recording-length-increased) | MRC 기록은 5 분 이상으로 중단 되지 않습니다. |
| [업데이트의 개선 사항 및 수정](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 업데이트의 추가 수정 사항.   |

### 자동 눈동자 위치 지원

- 이제 향상 된 편안 하 게 시청 하 고 디스플레이 품질을 향상 시키기 위해 자동 눈 위치 지원을 통해 홀로그램을 더 정확 하 게 배치할 수 있습니다. 

HoloLens 2에서 눈 위치는 적절 한 홀로그램 위치 지정, 편안한 시청 경험 및 향상 된 디스플레이 품질을 가능 하 게 합니다. 눈동자 위치는 시각 추적 결과의 일부로 계산 됩니다. 그러나이를 위해서는 각 사용자가 눈 응시 입력이 필요 하지 않은 경우에도 시각 추적 보정을 거쳐야 합니다.

**자동 눈동자 (AEP)** 를 사용 하면 이러한 시나리오를 조작 없이 사용자에 대 한 눈 위치를 계산할 수 있습니다.  자동 눈동자 위치는 사용자가 장치를 전환 하는 순간부터 자동으로 백그라운드에서 작업을 시작 합니다. 사용자가 이전 시각 추적 보정을 보유 하 고 있지 않은 경우, 자동 눈동자 위치는 처리 시간이 적은 후 디스플레이 시스템에 대 한 사용자의 눈 위치를 제공 하기 시작 합니다. 일반적으로이 처리 시간은 20-60 초입니다. 사용자 데이터는 장치에 유지 되지 않으므로 사용자가 장치를 종료 하 고 다시 시작 하거나 절전 모드에서 부팅 또는 절전 모드를 전환 하는 경우이 프로세스가 반복 됩니다.  

Uncalibrated 사용자가 디바이스에 배치 하는 경우 자동 눈 위치 기능을 사용 하 여 몇 가지 시스템 동작 변화가 변경 되었습니다. Uncalibrated 사용자는 이전에 장치에서 눈 추적 보정 프로세스를 거치지 않은 사람을 참조 합니다.

|     활성 응용 프로그램                           |     이전 동작                                   |     Windows 홀로그램 버전 20H2의 동작                                                     |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     비 응시 사용 앱 또는 홀로그램 셸    |     눈동자 추적 보정 프롬프트가 표시 됩니다.    |     메시지가 표시 되지 않습니다.                                                                                |
|     응시 사용 앱                             |     눈동자 추적 보정 프롬프트가 표시 됩니다.    |     응용 프로그램이 아이 응시 스트림에 액세스 하는 경우에만 눈동자 추적 보정 프롬프트가 표시 됩니다.     |

 사용자가 비 응시 사용 응용 프로그램에서 응시 데이터에 액세스 하는 앱으로 전환 하는 경우 보정 메시지가 표시 됩니다. 경험 치를 다 활용 해도 변경 되지 않습니다. 
 
아이 응시 데이터 나 매우 정밀한 홀로그램 위치가 필요한 환경에서는 사용자가 눈 추적 보정 프롬프트에서 눈 추적 보정을 실행 하거나 시작 메뉴에서 설정 앱을 시작한 다음 **시스템 > 보정 > 눈동자 보정 > 실행**을 선택 하는 것이 좋습니다.

이 정보는 나중에 [다른 보정 정보](hololens-calibration.md#auto-eye-position-support)를 사용 하 여 찾을 수 있습니다. 

### 인증서 관리자

- 새로운 인증서 관리자를 통해 장치 보안 및 준수에 대 한 감사, 진단, 유효성 검사 도구를 개선 했습니다. 이 접근 권한 값을 통해 상업용 환경에서 규모의 인증서를 배포 하 고, 문제를 해결 하 고, 유효성을 검사할 수 있습니다.

Windows 홀로그램 버전 20H2에서는 HoloLens 2 설정 앱에서 인증서 관리자를 추가 합니다. **& 보안 > 인증서를 업데이트 > 설정**으로 이동 합니다. 이 기능을 사용 하면 간단 하 고 사용자에 게 장치에서 인증서를 보고, 설치 하 고, 제거할 수 있습니다. 새 인증서 관리자를 통해 관리자와 사용자는 향상 된 감사, 진단 및 유효성 검사 도구를 사용 하 여 디바이스를 안전 하 고 준수 하도록 유지할 수 있습니다. 

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

이 정보는 나중 [에 새 인증서 관리자 페이지에서](certificate-manager.md)찾을 수 있습니다.

### USB에서 자동 시작 프로 비전

- OOBE 중에 제공 되는 프로비저닝 패키지가 있는 USB 드라이브를 사용 하는 경우 더 적은 사용자 조작을 허용 하는 자동화 된 프로세스

이 릴리스 사용자는 OOBE가 단추 조합을 사용 하 여 프로 비전 할 때 수동으로 프로비저닝 화면을 실행 해야 합니다. 이제 사용자는 USB 저장소 드라이브의 프로비저닝 패키지를 사용 하 여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE의 첫 번째 감 순간에 프로비저닝 패키지와 함께 USB 드라이브 연결
1. 디바이스를 프로 비전 할 준비가 되 면 프로 비전 페이지로 메시지가 자동으로 열립니다. 

참고: 장치를 부팅 하는 동안 USB 드라이브가 연결 된 상태에서, OOBE는 기존 USB 저장 디바이스를 열거 하 고 추가 연결을 감시할 수도 있습니다.

OOBE 중에는 프로비저닝 패키지를 적용 하는 방법에 대 한 자세한 내용은 [여기](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)를 계속 읽으십시오.

이 정보는 나중에 볼 수 있습니다 [.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### OOBE에서 프로 비전 패키지 자동 확인
- 자동화 프로세스를 통해 사용자 조작을 덜 수행할 수 있으며, 프로비저닝 패키지 페이지가 표시 되 면 나열 된 모든 패키지가 자동으로 적용 됩니다.

프로 비전 주 화면이 나타나면 OOBE는 자동으로 모든 프로 비전 패키지 적용을 시작 하기 전에 10 초 동안 횟수를 계산 합니다. 사용자는 예상 되는 패키지를 확인 한 후 10 초 내에 계속 확인 하거나 취소할 수 있습니다.

이 정보는 나중에 볼 수 있습니다 [.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### UI를 사용 하지 않고 자동 프로 비전
- 프로 비전을 위한 감소 된 장치 조작에 대 한 자동 프로세스가 결합 되었습니다. 

USB 장치에서 프로 비전의 자동 실행을 결합 하 고 프로 비전 패키지의 자동 확인을 통해 디바이스의 UI를 사용 하지 않거나 장치를 착용 하지 않고 HoloLens 2 장치를 자동으로 프로 비전 할 수 있습니다. 동일한 USB 드라이브와 여러 장치에 대 한 프로비저닝 패키지를 계속 사용할 수 있습니다. 이 기능은 같은 영역에 여러 장치를 동시에 배포 하는 데 유용 합니다. 

1. [Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22)를 사용 하 여 [프로비저닝 패키지를 만듭니다](hololens-provisioning.md) . 
1. 패키지를 USB 저장소 드라이브에 복사 합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) 에서 [19041.1361 이상 빌드](https://aka.ms/hololens2previewdownload)를 플래시 합니다. 
1. [고급 복구 도우미가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 장치를 깜박이는 경우 USB-C 케이블을 뽑습니다. 
1. USB 드라이브를 장치에 연결 합니다.
1. HoloLens 2 장치가 OOBE로 부팅 되 면 USB 드라이브에서 자동으로 프로비저닝 패키지를 감지 하 고 프로비저닝 페이지를 실행 합니다.
1. 10 초 후에 장치가 프로비저닝 패키지를 자동으로 적용 합니다. 

디바이스가 이제 구성 되 고 프로 비전 성공 화면이 표시 됩니다.

이 정보는 나중에 볼 수 있습니다 [.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Wi-Fi 연결에 Autopilot 사용
- USB-C 어댑터는 Wi-Fi 연결 된 장치에서 Autopilot 기능을 사용 하도록 설정 하 여 이더넷에서 하드웨어 요구 사항을 줄이는 것이 필요 했습니다.

현재 OOBE 중에 HoloLens 2를 Wifi에 연결 하면 OOBE에서 디바이스에 대 한 Autopilot 프로필을 확인 합니다. 하나가 발견 되 면 나머지 AAD 조인과 등록 흐름을 완료 하는 데 사용 됩니다. 즉, 이더넷을 USB-C에 사용 하거나 USB-C 어댑터에 Wi-Fi 하는 것은 요구 사항이 더 이상 필요 하지 않지만, OOBE 시작 부분에 제공 되는 경우 계속 작동 합니다. [HoloLens 2 장치에 대 한 Autopilot](hololens2-autopilot.md)에 대해 자세히 알아보세요.

### Tenantlockdown CSP 및 Autopilot
- 장치 재설정이 나 reflash를 통해 장치를 테 넌 트로 잠가서 조직의 테 넌 트에 디바이스를 유지 합니다. 프로 비전을 통해 계정 생성을 허용 하지 않도록 하 여 추가 보안을 사용 합니다. 

HoloLens 2 장치는 이제 [Windows 홀로그램 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)로 TENANTLOCKDOWN CSP를 지원 합니다. 

[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용 하 여 HoloLens 2를 MDM 등록에 연결할 수 있습니다. TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false (초기 설정) 값으로 설정 되 고, 다시 깜박이는 경우, OS 업데이트 등의 장치에도 해당 값이 남아 있습니다. 

HoloLens 2에서 TenantLockdown Csp의 RequireNetworkInOOBE 노드가 true로 설정 되 면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드 되 고 적용 될 때까지 무기한 대기 합니다. 

RequireNetworkInOOBE는 HoloLens 2에서 TenantLockdown Csp의 a 노드가 true로 설정 되 면 OOBE에서 다음 작업을 허용 하지 않습니다. 
- 런타임 프로 비전을 사용 하 여 로컬 사용자 만들기 
- 런타임 프로 비전을 통해 AAD 조인 작업 수행 
- OOBE 환경에서 장치를 소유 하는 사용자 선택 

#### Intune을 사용 하 여 설정 하는 방법은 무엇 인가요? 
1. 사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정 합니다.
OMA URI 값은/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE 이어야 합니다.

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 tennant 잠금 설정](images/hololens-tenant-lockdown.png)

1. 그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당 합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작 합니다.  

장치 구성이 성공적으로 적용 되었는지 Intune 포털에서 확인 합니다. 이 장치 구성이 Hololens 2 장치에 성공적으로 적용 되 면 TenantLockdown 효과가 활성화 됩니다.

#### Intune을 사용 하 여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제 하는 방법 
1. 위에서 만든 장치 구성이 이전에 할당 된 장치 그룹에서 HoloLens 2를 제거 합니다. 

1. 사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE에 대해 false를 지정 합니다. OMA URI 값은/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE 이어야 합니다.

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정 하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. 그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당 합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작 합니다.

장치 구성이 성공적으로 적용 되었는지 Intune 포털에서 확인 합니다. 이 장치 구성이 Hololens 2 장치에 성공적으로 적용 되 면 TenantLockdown 효과가 비활성화 됩니다. 

#### TenantLockdown true로 설정 된 후 HoloLens에서 Autopilot 프로필이 할당 되지 않은 경우 OOBE 중에 발생 하는 작업은 무엇 인가요? 
OOBE는 Autopilot 프로필이 다운로드 될 때까지 무기한 대기 하 고 대화 상자가 표시 됩니다. TenantLockdown 효과를 제거 하려면 장치를 원래 테 넌 트만 사용 하 여 먼저 등록 해야 하며, 이전 단계에서 설명한 대로 Autopilot를 설정 하지 않아야 합니다. TenantLockdown CSP에서 도입 된 제한이 제거 됩니다. 

![장치에서 정책이 적용 되는 시기에 대 한 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

이 정보는 이제 [Tenantlockdown CSP 및 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)에 있는 Autopilot의 나머지와 함께 찾을 수 있습니다.

### 전역 할당 액세스 – 키오스크 모드
- 시스템 수준에서 키오스크 모드를 적용 하는 새 키오스크 방법을 활성화 하 여 키오스크에 대 한 Id 관리를 줄입니다.

이 새로운 기능을 사용 하면 IT 관리자가 시스템에서 사용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성 하 고 시스템의 모든 id와 관련 된 선호도가 없으며 장치에 로그인 하는 모든 사용자에 게 적용 됩니다. 이 새로운 기능에 대 한 자세한 내용은 [여기](hololens-global-assigned-access-kiosk.md)를 참조 하세요.

### 다중 앱 키오스크 모드에서 응용 프로그램 자동 실행 
- 자동 앱 시작 기능을 통해 키오스크 모드 환경에 맞게 선택한 UI 및 앱 선택이 더욱 향상 되었습니다.

이 속성은 여러 앱 키오스크 모드에만 적용 되며 지정 된 액세스 구성에서 아래의 강조 표시 되는 특성을 사용 하 여 자동 시작 하도록 지정할 수 있습니다. 

사용자가 로그인 하면 응용 프로그램이 자동으로 시작 됩니다. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 오류 처리에 대 한 키오스크 모드 동작 변경
- 키오스크 모드 오류에서 사용 가능한 앱을 제거 하 여 더욱 안전한 키오스크 모드. 

이전에는 키오스크 모드 적용 중 오류가 발생 하 여 시작 메뉴의 모든 응용 프로그램을 표시 하는 데 사용 되는 HoloLens가 있습니다. 이제 Windows 홀로그램 버전 20H2에서 실패가 발생 하는 경우 시작 메뉴에 아래와 같이 앱이 표시 되지 않습니다. 

![오류가 발생 했을 때 표시 되는 키오스크 모드의 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

### HoloLens 정책
- 장치 관리용으로 만든 HoloLens 용 장치 관리 옵션 

Windows 홀로그램 버전 20H2의 HoloLens 2 장치에 대 한 새로운 혼합 현실 정책이 생성 되었습니다. 제어 가능한 새 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음 사용 안 함, 진단 프로그램 수집 시 설정, AAD 그룹 구성원 캐시 등이 포함 됩니다.  

| 새 HoloLens 정책                                | 설명                                                                               | 참고                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 밝기 단추를 눌러도 밝기가 변경 되지 않도록 할 수 있습니다.       | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\VolumeButtonDisabled                  | 볼륨 단추를 눌러도 볼륨이 변경 되지 않도록 할 수 있습니다.               | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2에서 오디오 녹음을 할 수 없도록 마이크를 사용 하지 않도록 설정 합니다.                      | 1 예, 0 아니요 (기본값)                                                |
| MixedReality\FallbackDiagnostics                   | 진단 로그를 수집할 수 있는 동작을 제어 합니다.                               | 0 사용 안 함, 장치 소유자에 대해 1 개 사용, 2에 모두 사용 (기본값) |
| MixedReality\HeadTrackingMode                      | 나중에 사용 하기 위해 예약 되어 있습니다.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 키오스크 대상 AAD 그룹에 AAD 그룹 구성원 캐시를 사용 하는 기간 (일 수)을 제어 합니다. | 아래를 참조 하세요.                                                           |

### 오프 라인 키오스크에 대 한 AAD 그룹 구성원 캐시
- 최대 60 일간 AAD 그룹과 사용할 오프 라인 키오스크를 사용할 수 있습니다.

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
> AAD 사용자에 대해 4 단계를 수행할 때까지 "연결이 끊긴" 환경에서 발생 하는 실패 동작이 발생 합니다. 

### HoloLens 2에 대 한 새 장치 제한 정책
- 사용자가 프로비저닝 패키지 추가 또는 제거 차단 등의 특정 장치 관리 정책을 관리할 수 있도록 합니다.

HoloLens 2 장치의 추가 관리 옵션을 허용 하는 새로 사용할 수 있는 정책 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 및 AllowRemoveProvisioningPackage에 대 한 이러한 두 가지 새로운 정책은 [일반적인 디바이스 제한](hololens-common-device-restrictions.md)에 추가 됩니다.

### Hololens 2에 대 한 새 전원 정책
- HoloLens 절전 또는 전원 정책으로 잠금에 대 한 추가 옵션 

관리자는 이러한 새로 추가 된 정책을 통해 유휴 시간 제한 등의 전원 상태를 제어할 수 있습니다. 각 개별 정책에 대 한 자세한 내용을 보려면 해당 정책의 링크를 클릭 하세요.

|     정책 설명서 링크                |     참고                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 구성 디자이너에서 사용할 예제 값입니다 (예: 100).                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예: 100).                                                                          |
|     [소모 되는 Bytimeout배터리](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 구성 디자이너에서 사용할 예제 값입니다 (예:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

이 두 가지 DisplayOffTimeoutOnBattery 및 DisplayOffTimeoutPluggedIn에 대 한 새로운 정책은 [일반적인 디바이스 제한](hololens-common-device-restrictions.md)에 추가 됩니다.

> [!NOTE]
> HoloLens 2에서 일관 된 환경을 유지 하기 위해 DisplayOffTimeoutOnBattery와 a Bytimeouton배터리 모두의 값이 동일한 값으로 설정 되어 있는지 확인 하세요. DisplayOffTimeoutPluggedIn 및 StandbyTimeoutPluggedIn에도 마찬가지입니다. 최신 대기 상태에 대 한 자세한 내용은 [표시, 절전 및 최대 절전 모드 유휴 타이머](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 를 참조 하세요.

### HoloLens에 대해 새로 설정 된 업데이트 정책
- 업데이트를 설치 하는 경우와 업데이트를 위해 업데이트 일시 중지 단추를 사용 하지 않도록 설정 하는 추가 옵션

이 업데이트 정책은 이제 HoloLens 2 장치에서 사용할 수 있습니다.
-   [업데이트/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [업데이트/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [업데이트/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [업데이트/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ise 업데이트 정책 및 HoloLens 장치에 사용 하는 방법에 대 한 자세한 내용은 [hololens 업데이트 관리](hololens-updates.md)에서 볼 수 있습니다.

### HoloLens 2에 대 한 사용 설정 페이지 표시 여부
- 설정 앱의 향상 된 UI 컨트롤-제한 된 페이지 선택을 표시 하는 것을 혼동할 수 있습니다.

이제 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스할 수 없도록 하거나 지정 된 모든 페이지를 제외 하 고,이 정책을 사용 하도록 설정 했습니다. 이 기능을 완전히 사용자 지정 하는 방법에 대 한 자세한 내용을 보려면 아래 링크를 클릭 하세요.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2에서 사용자 지정할 수 있는 페이지 설정을 알아보려면 [설정 uri 페이지](settings-uri-list.md)를 방문 하세요. 
 
![설정 앱에서 수정 중인 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

### 리서치 모드
리서치 모드에서 HoloLens 2는 컴퓨터 비전 조사에 대 한 potent 도구가 됩니다. 이전 버전에 비해 HoloLens 2의 연구 모드에는 다음과 같은 이점이 있습니다.
-   HoloLens (첫번째 gen) 연구 모드에서 제공 되는 센서 외에도 이제가 속도계, gyroscope, 자력 계 등의 IMU 센서 액세스를 제공 합니다.
-   HoloLens 2는 연구 모드와 함께 사용할 수 있는 새로운 기능을 제공 합니다. 특히, 다양 한 실험을 제공할 수 있는 트레일러 추적 및 아이 추적 Api에 액세스 합니다.

현재 연구원은 이러한 모든 외부의 raw 이미지 센서 스트림에 액세스할 수 있도록 HoloLens 장치에서 리서치 모드를 사용 하도록 설정 하는 옵션을 사용할 수 있습니다. HoloLens 2에 대 한 연구 모드는가 속도계, gyroscope 및 자력 계 판독값에 대 한 액세스도 제공 합니다. 사용자의 개인 정보를 보호 하기 위해 원시 아이 추적 카메라 이미지는 리서치 모드를 통해 사용할 수 없지만 기존 Api를 통해 눈 응시 방향을 사용할 수 있습니다.

자세한 기술 정보는 [리서치 모드 설명서](https://docs.microsoft.com/windows/mixed-reality/research-mode) 를 확인 하세요.

### 기록 길이 증가
고객 의견 때문에 [혼합 현실 캡처](holographic-photos-and-videos.md)의 기록 길이를 높였습니다. 혼합 현실 캡처는 기본적으로 5 분으로 제한 되지 않으며, 대신 사용 가능한 디스크 공간을 기준으로 최대 기록 길이를 계산 하 게 됩니다. 장치는 총 디스크 공간에 대 한 최대 80% 까지의 사용 가능한 디스크 공간을 기준으로 최대 비디오 녹화 기간을 계산 합니다.

> [!NOTE]
> 다음 중 하나가 발생 하는 경우 HoloLens에서 기본 비디오 녹화 길이 (5 분)를 사용 합니다.
> - 예상 최대 기록 기간이 기본 5 분 보다 작습니다.
> - 사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.

이 정보는 [여기](holographic-photos-and-videos.md#maximum-recording-length)에 다시 나와 있습니다. 

### 업데이트의 개선 사항 및 수정 사항:
- 현재 OOBE의 다른 화면은 어둡게 모드입니다.
- 자세한 내용은 온라인의 최신 개인 정보 취급 방침을 참고 하세요.
- 사용자가 프로 비전 패키지를 통해 VPN 프로필을 프로 비전 할 수 없는 문제를 해결 했습니다.
- VPN 연결에 대 한 프록시 구성 문제가 해결 되었습니다.
- Allow: NCM 연결에 대 한 MDM을 통해 USB 기능 열거를 사용 하지 않도록 정책을 업데이트 했습니다.
- 장치를 [단일 앱 키오스크](hololens-kiosk.md)로 설정 하는 경우 MTP (미디어 전송 프로토콜)를 통해 HoloLens 장치가 파일 탐색기에 표시 되지 않도록 하는 문제를 해결 했습니다. MTP (일반의 경우 USB 연결)는 [Allowe 연결](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 정책을 사용 하 여 계속 사용할 수 있습니다.
- 키오스크 모드에서 시작 메뉴의 아이콘이 올바르게 확장 된 문제가 해결 되었습니다.
- AAD 그룹을 대상으로 하는 키오스크 모드를 방해 하는 HTTP 캐싱으로 인해 문제가 해결 되었습니다.
- 개발자 모드를 비활성화 하 고 다시 사용할 수 있도록 설정 하지 않은 경우 개발자 모드를 사용 하도록 설정한 후 사용자가 쌍 단추를 사용할 수 없는 문제가 해결 되었습니다.

## Windows 홀로그램 버전 1903-2020 업데이트-11 월
- 빌드 18362.1085

이 월 품질 업데이트에는 중요 한 변경 사항이 포함 되어 있지 않으므로 최신 기능 릴리스 빌드 Windows 홀로그램, 버전 20H2를 사용해 보세요.

## Windows 홀로그램 버전 2004 ~ 10 월 2020 업데이트
- 빌드 19041.1124
 
업데이트의 개선 사항 및 수정 사항:

- 런타임 시스템 오류를 일으킨 불필요 한 검사를 제거 했습니다.

## Windows 홀로그램 버전 1903 ~ 10 월 2020 업데이트
- 빌드 18362.1081

이 월 품질 업데이트에는 중요 한 변경 사항이 포함 되어 있지 않으므로 Windows 홀로그램 버전 2004에 대 한 최신 빌드를 사용 하는 것이 좋습니다.

## Windows 홀로그램 버전 2004-2020 업데이트-09 월
- 빌드 19041.1117

업데이트의 개선 사항 및 수정 사항:

- SupportsMultipleInstances = "true"가 appxmanifest에 있을 때 Visual Studio에서 응용 프로그램을 디버그할 수 없도록 하는 문제를 해결 합니다.
- 이 릴리스에는 네트워크 프록시를 통해 실패 한 인터넷 검색을 처리 하는 NCSI 프록시 검색 수정 사항이 포함 되어 있습니다. NCSI는 인터넷 연결 검색을 위해 컴퓨터 프록시와 프로필 단위 프록시를 사용할 수 있습니다. 사용자 당 프록시는 향후 릴리스에서 NCSI를 통해 지원 됩니다.
- 대부분의 Windows Mixed Reality 장치에서 전방 방향 벡터는 사용자의 헤드가 중립 위치에 있을 때 지상에 평행한 것입니다. 그러나 이전 버전의 HoloLens 2에서는 벡터를 디스플레이 패널과 수직이 되도록 맞춥니다 (가장 적합 한 방향을 기준으로 몇도 아래로 기울어짐). 최신 버전의 HoloLens 2는 폼 팩터 간의 의미 일관성을 보장 하기 위해이를 수정 했습니다.
- 특정 시나리오에서 추적 손실의 감소를 초래 하는 향상 된 수동 추적 견고성.
- 이 릴리스에는 비디오 캡처 문제에 참가 한 오디오 타임 스탬프 품질을 개선 하는 수정 사항이 포함 되어 있습니다.

## Windows 홀로그램 버전 1903-2020 업데이트-09 월
- 빌드 18362.1079

업데이트의 개선 사항 및 수정 사항:

- 대부분의 Windows Mixed Reality 장치에서 전방 방향 벡터는 사용자의 헤드가 중립 위치에 있을 때 지상에 평행한 것입니다. 그러나 이전 버전의 HoloLens 2에서는 벡터를 디스플레이 패널과 수직이 되도록 맞춥니다 (가장 적합 한 방향을 기준으로 몇도 아래로 기울어짐). 최신 버전의 HoloLens 2는 폼 팩터 간의 의미 일관성을 보장 하기 위해이를 수정 했습니다.
- 특정 시나리오에서 추적 손실의 감소를 초래 하는 향상 된 수동 추적 견고성.

## Windows 홀로그램 버전 2004-2020 업데이트 8 월
- 빌드 19041.1113

업데이트의 개선 사항 및 수정 사항:

- 설정 앱은 더 이상 사용자를 팔 로우 하는 조리개 등록 또는 눈동자 추적 보정 환경을 제공 하지 않습니다.
- OOBE 중에 프로비저닝 패키지를 적용 하 여 디바이스 이름을 바꾸고 다른 작업 (예: 네트워크 연결)을 수행 하는 버그가 해결 되 면 장치를 다시 부팅 한 후 다른 작업을 수행할 수 없습니다.
- 시각적 품질을 향상 시키기 위해 초기 디바이스 설정 흐름의 수정 된 색 구성표입니다.

## Windows 홀로그램 버전 1903-2020 업데이트 8 월
- 빌드 18362.1074

이 월 품질 업데이트에는 중요 한 변경 사항이 포함 되어 있지 않으므로 Windows 홀로그램 버전 2004에 대 한 최신 빌드를 사용 하는 것이 좋습니다.

## Windows 홀로그램 버전 2004-2020 업데이트
- 빌드 19041.1109

업데이트의 개선 사항 및 수정 사항:

- 이제 개발자는 Device Portal에서 보안 연결을 요구 하는 것을 선택 하거나 사용 하지 않도록 설정할 수 있습니다.
- OS 업데이트 후 응용 프로그램 시작 안정성이 향상 되었습니다.
- 기본 받은 편지함 밝기를 100 퍼센트로 변경 했습니다.
- HoloLens 2에서 Windows 디바이스 포털에 대 한 HTTPS 전달에 대 한 문제를 해결 했습니다.

## Windows 홀로그램 버전 1903-2020 업데이트
- 빌드 18362.1071

업데이트의 개선 사항 및 수정 사항:

- 추적을 잃거나 regaining 하는 경우 Unity 응용 프로그램에서 홀로그램가 사라질 수 있는 문제를 해결 했습니다.
- 특정 장치에서 하드웨어 가속으로 HoloLens 에뮬레이터를 사용 하는 동안 독점 HoloLens 앱이 셸로 다시 작동 하는 문제를 해결 했습니다.
- HoloLens 2의 Windows Device Portal에 대 한 HTTPS 전달과 관련 된 문제를 해결 했습니다.

## Windows 홀로그램 버전 2004-2020 업데이트
- 빌드 19041.1106

업데이트의 개선 사항 및 수정 사항:

- 지정 되지 않은 경우 사용자 지정 MRC 레코더에는 특정 속성에 대 한 새로운 기본값이 적용 됩니다.
  - *Mrc 비디오 효과*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (HoloLens (0.9) 1.0 (모던 헤드셋))
  - *Mrc 오디오 효과*:
    - LoopbackGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "앱 오디오 게인" 값
    - MicrophoneGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "Mic 오디오 게인" 값
- 혼합 현실 캡처 시나리오에서 오디오 품질을 개선 하기 위해 버그가 수정 되었습니다. 특히이 수정은 **시작** 메뉴가 표시 되 면 기록에서 오디오 결함를 제거 합니다.
- 녹화 된 비디오의 홀로그램 안정성이 개선 되었습니다.
- 장치가 여러 일 동안 대기 상태로 남겨진 경우 mixed reality 캡처가 비디오를 녹화할 수 없는 문제를 해결 했습니다.
- 일반적으로 Unity 응용 프로그램에서는 HolographicSpace 현재 상태 API를 사용할 수 없습니다. 이 동작은 "백그라운드에서 실행" 설정을 사용 하는 경우에도, 센터를 대칭 이동 했을 때 일부 앱이 일시 중지 되는 문제를 방지 합니다. 이제 API를 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 사용할 수 있습니다.
- Wi-Fi 연결을 통해 디바이스 포털에 액세스 하면 웹 브라우저가 유효 하지 않은 인증서로 인해 액세스 하지 못할 수 있습니다. 브라우저는 장치 인증서가 이전에 신뢰 된 경우에도 "ERR_SSL_PROTOCOL_ERROR"와 같은 오류를 보고할 수 있습니다. 이 경우에는 보안 경고를 무시 하는 옵션이 없기 때문에 Device Portal로 진행할 수 없습니다. 이 업데이트로 문제를 해결 했습니다. 장치 인증서가 이전에 PC에서 다운로드 되 고 신뢰 되어 브라우저 보안 경고가 표시 되는 경우 SSL 오류가 발생 하는 경우 새 인증서를 다운로드 하 여 브라우저 보안 경고가 표시 되도록 신뢰 해야 합니다.
- MSIX 패키지를 사용 하 여 앱을 설치할 수 있는 런타임 프로비저닝 패키지를 만드는 기능을 사용 하도록 설정 했습니다.
- **Settings**  >  **System**  >  장치를 종료할 때 사용자가 혼합 현실 집에서 모든 홀로그램을 자동으로 제거할 수 있도록 설정 시스템**홀로그램** 에 설정이 추가 되었습니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경 하는 HoloLens 앱이 검정색을 렌더링 하는 문제를 해결 했습니다.
- Iri 로그인 중에 충돌을 일으킨 버그를 해결 했습니다.
- 이미 존재 하는 앱에 대 한 반복 스토어 다운로드 문제가 해결 되었습니다.
- 몰입 형 앱이 반복적으로 Microsoft Edge를 열지 못하도록 버그를 수정 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부팅에서 사진 앱이 시작 되는 문제를 해결 했습니다.
- 성능 및 안정성이 개선 되었습니다.

## Windows 홀로그램 버전 1903-2020 업데이트
- 빌드 18362.1064

업데이트의 개선 사항 및 수정 사항:

- 사용자 지정 MRC 레코더는 특정 속성을 지정 하지 않은 경우 새 기본값을 사용 합니다.
  - *Mrc 비디오 효과*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (HoloLens (0.9) 1.0 (모던 헤드셋))
  - *Mrc 오디오 효과*:
    - LoopbackGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "앱 오디오 게인" 값
    - MicrophoneGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "Mic 오디오 게인" 값
- 일반적으로 Unity 응용 프로그램에서는 HolographicSpace 현재 상태 API를 사용할 수 없습니다. 이 동작을 사용 하면 작업을 수행 하는 데 문제가 발생 하는 것을 방지 하는데,이는 백그라운드에서 실행 되는 설정이 활성화 된 경우에도 일부 앱이 일시 중단 되는 경우 이제 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에 API를 사용할 수 있습니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경 하는 HoloLens 앱이 검정색을 렌더링 하는 문제를 해결 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부츠에서 사진 앱을 시작 하는 방법에 대 한 문제가 수정 되었습니다.

## Windows 홀로그램 버전 2004  
- 빌드-19041.1103

2020, *Windows 홀로그램, 버전 2004* 에 대 한 주요 소프트웨어 업데이트에는 windows Autopilot에 대 한 지원, 앱 어둡게 모드, 5g/LTE 핫스팟에 대 한 USB 이더넷 지원 등 흥미로운 새로운 기능 호스트가 포함 되어 있습니다. 최신 릴리스로 업데이트 하려면 **설정**   앱을 열고 **업데이트 & 보안**으로 이동한 다음 **업데이트 확인**   단추를 선택 합니다. 

|             기능                              |          설명                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot를 사용 하 여 제작에 대 한 새 장치를 미리 구성 하 고 완벽 하 게 설정                 |
|       FIDO 2 지원                             |          공유 디바이스에 대해 빠른 및 보안 인증을 사용 하도록 FIDO2 보안 키 지원            |
|       향상 된 프로비저닝                      |          USB 드라이브에서 HoloLens에 프로비저닝 패키지를 원활 하 게 적용                              |
|       응용 프로그램 설치 상태                 |          앱에 대 한 설정 앱이 MDM을 통해 HoloLens 2로 푸시 된 경우 설치 상태 확인               |
|       Csp (구성 서비스 공급자)   |          관리 제어 기능을 향상 시키기 위해 새로운 구성 서비스 공급자가 추가 됨                 |
|       USB 5G/LTE 지원                       |          확장 USB 이더넷 기능을 통해 5G/LTE를 지원 합니다.                                    |
|       어둡게 앱 모드                              |          어둡게 모드와 가벼운 모드를 모두 지 원하는 앱에 사용할 수 있는 어두운 앱 모드, 보기 환경 개선        |
|       음성 명령                             |          HoloLens 핸 즈 프리를 제어 하기 위한 추가 시스템 음성 명령 지원                           |
|       향상 된 수동 추적                 |          향상 된 기능 추적 단추와 2D 슬레이트의 더욱 정확한 상호 작용                        |
|       품질 개선 및 수정                 |          플랫폼 전체의 다양 한 시스템 성능 및 안정성 향상                            |

### Windows Autopilot에 대 한 지원

HoloLens 2 용 Windows Autopilot에서는 device sales 채널의 HoloLens를 Intune 테 넌 트에 미리 등록할 수 있습니다. 장치가 도착 하면 테 넌 트에서 공유 장치로 자체 배포할 준비가 된 것입니다. 자체 배포를 활용 하려면 USB-C ~ 이더넷을 사용 하 여 설치 프로그램의 첫 화면에서 장치가 네트워크에 연결 되어야 합니다.

사용자가 Autopilot 자동 배포 프로세스를 시작 하면 프로세스는 다음 단계를 완료 합니다.

1. 장치를 Azure AD(Azure Active Directory)에 가입시킵니다.
1. Azure AD를 사용하여 Microsoft Intune(또는 다른 MDM 서비스)에 장치를 등록합니다.
1. 장치 대상 정책, 인증서, 네트워킹 프로필을 다운로드합니다.
1. 장치를 프로비전합니다.
1. 사용자에게 로그인 화면을 표시합니다.

[Windows Autopilot HoloLens에 대해 자세히 알아보세요 2 평가 가이드를 참조](https://docs.microsoft.com/hololens/hololens2-autopilot)하세요.

*지금 AutoPilot preview에 참가 하려면 계정 관리자에 게 문의 하세요. Autopilot 준비는 곧 시작 됩니다.*

### FIDO2 보안 키 지원

일부 사용자는 회사 또는 학교 환경에서 다른 사람과 HoloLens 장치를 공유 합니다. 따라서 사용자가 긴 사용자 이름 및 암호를 입력 하지 않아도 쉽게 사용할 수 있도록 하는 것이 중요 합니다. 빠른 Id 온라인 (FIDO)은 사용자 이름 또는 암호를 입력 하지 않고 조직 (Azure AD 테 넌 트)의 모든 사용자가 HoloLens에 간편 하 게 로그인 할 수 있도록 합니다.

FIDO2 보안 키는 모든 폼 요소에 사용할 수 있는 "unphishable" 표준 기반 암호 보다 덜 인증 방법입니다. FIDO는 passwordless 인증을 위한 개방형 표준입니다. 이를 통해 사용자와 조직이 사용자 이름 또는 암호 없이 해당 리소스에 로그인 할 수 있습니다. 대신 외부 보안 키 또는 장치에 기본 제공 되는 플랫폼 키를 사용 합니다.

시작 하려면 [passwordless 키 로그인 사용](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)을 참조 하세요.

### 프로 비전 패키지를 통한 MDM 등록 개선

배포 패키지를 사용 하 여 hololens 이용 경험이 아닌 구성 파일을 통해 HoloLens 구성을 설정할 수 있습니다. 이전에는 프로비저닝 패키지를 HoloLens 내부 메모리에 복사 해야 했습니다. 이제 USB 드라이브를 사용 하 여 여러 HoloLens 장치에서 더 쉽게 재사용할 수 있으며 디바이스를 병렬로 제공할 수 있습니다. 이제 프로 비전 패키지는 디바이스 관리에서 등록할 필드도 지원 하므로 프로 비전 후 수동 설치가 필요 하지 않습니다.

사용해 보기:

1. Windows 스토어에서 최신 버전의 Windows 구성 디자이너를 PC로 다운로드 합니다.
1. **Hololens 디바이스**프로  >  **비전 hololens 2 장치**를 선택 합니다.
2. 구성 프로필을 작성 합니다. 그런 다음 생성 된 모든 파일을 USB-C 저장소 장치에 복사 합니다.
3. USB-C 장치를 새로 플래시 HoloLens에 연결 합니다. 그런 다음 **볼륨 아래로 이동**  +  **power** 단추를 눌러 프로비저닝 패키지를 적용 합니다.

### Lob (기간 업무) 응용 프로그램 설치 상태

비즈니스 업무용 앱에 대 한 MDM 앱 배포 및 관리는 HoloLens에 중요 합니다. 관리자와 사용자는 감사 및 진단에 대 한 앱 설치 상태를 확인 해야 합니다. 이 릴리스에서는 **Settings**  >  계정 정보를 클릭 하 여 설정**계정**,  >  **회사 또는 학교에 대**  >  **Click on your account**  >  **Info**한 세부 정보를 추가 했습니다.

### 추가 Csp 및 정책

[CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 는 디바이스에서 구성 설정을 읽고, 설정 하 고, 수정 하 고, 삭제 하는 인터페이스입니다. 이번 릴리스에서는 관리자가 배포 된 HoloLens 장치를 사용 하는 컨트롤을 늘리기 위한 추가 정책에 대 한 지원이 추가 되었습니다. HoloLens에서 지원 되는 Csp 목록은 [Networkqospolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)를 참조 하세요.

이번 릴리스의 새로운 내용:

**Policy CSP** 

정책 구성 서비스 공급자는 엔터프라이즈에서 Windows 디바이스에 대 한 정책을 구성할 수 있도록 합니다. 이번 릴리스에서는 아래에 나열 된 HoloLens에 대 한 새 정책을 추가 했습니다. 자세히 알아보려면 [HoloLens 2에서 지 원하는 정책 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)를 참조 하세요.  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy 구성 서비스 공급자는 네트워크 QoS (서비스 품질) 정책을 만듭니다. QoS 정책은 일치하는 조건 집합에 따라 네트워크 트래픽에 대한 작업을 수행합니다. 자세히 알아보려면 [Networkqospolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)를 참조 하세요.

### 5G/LTE tethered 장치에 대 한 확장 된 USB 이더넷 지원

USB를 통해 HoloLens 2 tethered 하는 경우 5G/LTE 전화기와 Wi-Fi hotpots 같은 특정 모바일 광대역 장치를 사용 하기 위한 지원이 추가 되었습니다. 이러한 디바이스는 이제 다른 이더넷 연결로 **네트워크 설정** 에 표시 됩니다. 외부 드라이버를 필요로 하는 모바일 광대역 장치는 지원 되지 않습니다. 이 기능은 Wi-Fi을 사용할 수 없고 Wi-Fi 테더 링이 충분 하지 않은 경우 고대역폭 연결을 가능 하 게 합니다. 지원 되는 USB 장치에 대 한 자세한 내용은 [Bluetooth 및 USB-C 장치에 연결](https://docs.microsoft.com/hololens/hololens-connect-devices)을 참조 하세요.  

### 향상 된 수동 추적

이 릴리스에는 다음과 같은 다양 한 추적 개선 사항이 포함 되어 있습니다.

- **방향 포즈 안정성:** 이제 시스템은 palm을 occluded 때 인덱스 손가락을 resists. 이 변경으로 단추를 누르고, 입력 하거나, 콘텐츠를 스크롤 하는 등의 정확성을 높일 수 있습니다. 
- **우발적인 공기 탭 감소:** Air 탭 제스처 감지 기능이 향상 되었습니다. 이제 사용자가 손을 끌어 놓는 등의 몇 가지 일반적인 시나리오에서 발생 하는 우발적 정품 인증이 감소 합니다.
- **사용자 전환 안정성:** 이제 시스템은 장치를 공유할 때 손 크기를 업데이트 하는 것이 더 빠르고 안정적입니다.
- **핸드 절도 감소:** 센서를 두 번 이상 볼 수 있는 경우를 처리 하는 것이 개선 되었습니다. 여러 사용자가 함께 작업 하는 경우에는 손으로 사용자가 장면에 있는 다른 사람에 게 "이동" 할 확률이 훨씬 낮습니다.
- **시스템 안정성:** 장치 로드가 높을 때 핸드 추적이 작동을 중지 하는 문제를 해결 했습니다.

### 어둡게 모드

이제 대부분의 Windows 앱에서 어둡게 모드와 빛이 모두 지원 됩니다. HoloLens 2 사용자는 둘 다 지 원하는 앱의 기본 모드를 선택할 수 있습니다. 업데이트 후에 기본 앱 모드는 "어둡게" 이지만이 설정을 쉽게 변경할 수 있습니다. **설정**  >  **시스템**  >  **색**으로 이동  >  **기본 앱 모드를 선택**합니다. 

이러한 "in box" 앱은 어둡게 모드를 지원 합니다. 

- 설정 
- Microsoft Store 
- Mail 
- Calendar 
- 파일 탐색기 
- 피드백 허브 
- OneDrive 
- 사진 
- 3D 뷰어 
- 영화 및 TV 

![어둡게 모드 창 바둑판식](images/DarkMode.jpg)

### 시스템 음성 명령

이제 디바이스의 모든 앱에서 음성 명령을 사용할 수 있습니다. 자세한 내용은 [voice를 사용 하 여 HoloLens 작동](https://docs.microsoft.com/hololens/hololens-cortana)을 참조 하세요. 또한 [HoloLens 2에 대해 지원 되는 언어를](https://docs.microsoft.com/hololens/hololens2-language-support)참조 하세요.  

### Cortana 업데이트

업데이트 된 앱이 Microsoft 365와 통합 되어 장치에서 더 많은 작업을 수행할 수 있습니다 (현재 US-English에만 해당). HoloLens 2에서 Cortana는 더 이상 볼륨 조정과 같은 특정 디바이스 특정 명령을 지원 하지 않습니다. 이러한 옵션은 이제 새 시스템 음성 명령으로 지원 됩니다. [블로그의](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)새 Cortana 앱에 대해 자세히 알아보세요.

### 품질 개선 및 수정

업데이트에도 향상 된 기능과 수정 사항이 있습니다.  
- 활성 디스플레이 보정 시스템을 도입 했습니다. 이 기능은 홀로그램의 안정성과 맞춤을 개선 합니다. 이제 머리를 나란히 이동할 때 해당 위치가 그대로 유지 됩니다.
- HoloLens로 스트리밍할 Wi-Fi 주기적으로 중단 되는 버그가 해결 되었습니다. 응용 프로그램에서 대기 시간이 짧은 스트리밍이 필요 하다 고 표시 되는 경우 [SetSocketMediaStreamingMode 함수](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)를 호출 하 여 수정을 구현 합니다.
- 리서치 모드에서 스트리밍 중에 발생 한 디바이스 중단 문제를 해결 했습니다.
- 세션을 다시 시작할 때 올바른 사용자가 로그인 화면에 표시 되지 않는 경우에는 버그가 해결 되었습니다.
- 사용자가 **설정을**통해 MDM 로그를 내보낼 수 없는 문제를 해결 했습니다.
- 바로 이전 설치 다음에 나오는 눈 고의 정확성이 예상 보다 낮을 수 있는 문제를 해결 했습니다.
- 특정 조건에서 아이 추적 하위 시스템을 초기화 하거나 보정을 수행 하지 못한 문제가 해결 되었습니다.
- 이미 보정 된 사용자에 대 한 시각 보정에 대 한 메시지가 표시 되는 문제를 해결 했습니다.
- 눈 보정 중 드라이버의 작동이 중단 되는 문제를 해결 했습니다.
- 반복 되는 power button enter로 인해 60 초 시스템 시간 초과 및 셸 작동이 중단 되는 문제가 해결 되었습니다.
- 깊이 버퍼의 안정성을 개선 했습니다.
- 피드백 허브에 **공유** 단추가 추가 되어 사용자가 피드백을 더욱 쉽게 공유할 수 있습니다.
- RoboRaid wan't 올바르게 설치 된 버그를 해결 했습니다.

### 알려진 문제

- Zh-cn 시스템 언어의 문제는 음성 명령으로 인해 혼합 현실 캡처 또는 장치 IP 주소 표시를 방지 하는 데 문제가 있습니다.
- 문제를 해결 하려면 "안녕 코타 나" 음성 정품 인증을 사용 하기 위해 디바이스를 시작한 후 Cortana 앱을 시작 해야 합니다. 18362 빌드에서 업데이트 한 경우에는 더 이상 **시작**에서 작동 하지 않는 이전 버전의 Cortana 앱에 대 한 두 번째 앱 타일이 표시 될 수도 있습니다.

## Windows 홀로그램 버전 1903-2020 업데이트를 할 수 있습니다. 
- 빌드 18362.1061

이 월 품질 업데이트에는 앞에서 설명한 대로 Windows 홀로그램 버전 2004이 업데이트 될 수 있기 때문에 팀이 중요 한 변경 사항이 포함 되어 있지 않습니다.

## Windows 홀로그램 버전 1903-2020 업데이트 4 월
- 빌드 18362.1059

**지원 되는 앱의 어둡게 모드** 

대부분의 Windows 앱은 어둡거나 밝은 모드를 모두 지원 합니다. HoloLens 2 고객은 이제 두 색 구성표를 모두 지 원하는 앱의 기본 모드를 선택할 수 있습니다. 고객 의견을 기반으로 기본 앱 모드를 "어둡게"로 설정 하면 언제 든 지이 설정을 쉽게 변경할 수 있습니다. **설정 > 시스템 > 색** 으로 이동 하 여 **"기본 앱 모드 선택"** 을 찾습니다.

이러한 "in box" 앱은 어둡게 모드를 지원 합니다.
- 설정
- Microsoft Store
- Mail
- Calendar
- 파일 탐색기
- 피드백 허브
- OneDrive
- 사진
- 3D 뷰어
- 영화 및 TV

**업데이트에도 향상 된 기능과 수정 사항이 있습니다.** 
- 셸 오버레이가 mixed reality 캡처에 포함 되었는지 확인 했습니다.
- 이제 실제 개발자가 장치 포털의 3D 보기 페이지를 사용 하 여 응용 프로그램을 테스트 하 고 디버그할 수 있습니다.
- *HolographicDepthReprojectionMethod DepthReprojection* 알고리즘을 사용 하는 경우 혼합 현실 캡처의 홀로그램 안정성이 향상 되었습니다.
- 32 비트 ARM 앱에서 "WinRT IStreamSocketListener API 클래스가 등록 되지 않았습니다." 오류가 수정 되었습니다.

## Windows 홀로그램 버전 1903-2020 업데이트 3 월 
- 빌드 18362.1056

업데이트의 개선 사항 및 수정 사항:

- *HolographicDepthReprojectionMethod AutoPlanar* 알고리즘이 사용 되는 경우 혼합 현실 캡처의 홀로그램 안정성이 개선 되었습니다.
- 깊이 MF 샘플에 연결 된 좌표계가 공용 문서와 일관성을 유지 합니다.
- 고객이 장치 포털을 통해 많은 양의 텍스트를 붙여 넣을 수 있도록 하 여 개발자 생산성 향상

## Windows 홀로그램 버전 1903-2020 업데이트 
- 빌드 18362.1053

업데이트의 개선 사항 및 수정 사항:

- Unity 응용 프로그램의 HolographicSpace 현재 상태 API를 일시적으로 사용 하지 않도록 설정 했습니다. 이 변경으로 인해 "백그라운드에서 실행" 설정이 사용 되는 경우에도, 센터를 대칭 이동 했을 때 일부 앱이 일시 중지 되는 문제를 방지할 수 있습니다.
- 수동 추적으로 인 한 임의 HUP 충돌을 해결 했습니다 .이는 사용자가 몇 초 후에 UI 고정을 다시 셸로 인식 하는 것입니다.
- 색인 손가락을 사용 하 여 poke 때 손가락의 위쪽 부분이 갑자기 말아 넘기기 때문에 직접 추적 기능이 향상 되었습니다.
- 헤드 추적, 공간 매핑 및 기타 런타임 개선의 신뢰성.

## Windows 홀로그램, 버전 1903-2020 업데이트 
- 빌드 18362.1043
 
업데이트의 개선 사항 및 수정 사항:

- HoloLens 2 에뮬레이터 작업을 할 때 전용 앱의 안정성을 개선 했습니다.

## Windows 홀로그램 버전 1903-2019 업데이트-12 월 
- 빌드 18362.1042

업데이트의 개선 사항 및 수정 사항:

- LSR (마지막 단계 생성) 수정 사항을 도입 했습니다. 홀로그램의 시각적 렌더링이 향상 되어 깊이에 대 한 더 정확 하 게 계정으로 더욱 안정적이 고 선명 하 게 표시 됩니다. 이 문제는 앱의 깊이가 올바르게 설정 되지 않은 경우이 업데이트 후에 더 잘 홀로그램 수 있습니다.
- 전용 앱의 고정 안정성 및 단독 앱 간 탐색
- 장치가 며칠 동안 대기 상태에 있는 경우 mixed reality 캡처가 비디오를 녹화할 수 없는 문제를 해결 했습니다.
- 홀로그램 안정성이 개선 되었습니다.

## Windows 홀로그램 버전 1903-2019 업데이트-11 월 
- 빌드 18362.1039

업데이트의 개선 사항 및 수정 사항:

- 첫 번째-CA 및 반각 AU에 대 한 초기 설정의 음성 명령 **선택** 기능을 해결 했습니다.
- 최신 Unity 및 MRTK (혼합 현실 도구 키트) 버전에서 멀리 떨어진 개체의 시각적 품질이 향상 되었습니다.
- 시작 메뉴가 열리고 닫힐 때까지 시작 시 일시 중지 됨 상태가 홀로그램 응용 프로그램과 관련 된 문제 해결 문제가 해결 되었습니다.
- HoloLens 2 및 에뮬레이터에 대 한 OpenXR 런타임 준수 수정 및 개선 사항.
