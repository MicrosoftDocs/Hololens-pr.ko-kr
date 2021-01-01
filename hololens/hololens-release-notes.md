---
title: HoloLens 2 릴리스 정보
description: 각 새로운 HoloLens 2 릴리스의 업데이트에 대해 자세히 알아보습니다.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: e1bdc6292dc016dde78c781db79505e2b64b0d6d
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253065"
---
# HoloLens 2 릴리스 정보

HoloLens 장치에 대한 생산성을 보장하기 위해 계속해서 기능, 버그 및 보안 업데이트를 릴리스합니다. 이 페이지에서 매월 HoloLens의 새로운 것을 볼 수 있습니다. To get the latest HoloLens 2 update, you can either [check for updates and manually update](hololens-update-hololens.md#check-for-updates-and-manually-update) or get the Full Flash Update (FFU) to flash your device via Advanced Recovery [Companion,](hololens-recovery.md#clean-reflash-the-device) [download it here.](https://aka.ms/hololens2download) 다운로드는 최신으로 유지하며 일반적으로 사용할 수 있는 최신 빌드를 제공합니다.

>[!NOTE]
> HoloLens 에뮬레이터 릴리스 정보를 읽으시고 보관 [파일을 방문합니다.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)


## Windows Holographic, 버전 20H2 – 2020년 12월 업데이트
- 빌드 19041.1131

### 앱 설치 관리자를 통해 HoloLens 2에 앱 설치

**HoloLens** 2 장치에 응용 프로그램을 보다 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)을 추가하고 있습니다. 이 기능은 관리되지 않는 장치에 대해 기본적으로 **설정됩니다.** 엔터프라이즈 중단을 방지하기 위해 현재 관리되는 디바이스에서는 앱 설치 관리자를 사용할 **수** 없습니다.  

다음 중 한 가지가 **** 참이면 디바이스가 "관리"되는 것으로 간주됩니다.
- MDM [등록](hololens-enroll-mdm.md)
- 프로비저닝 [패키지로 구성](hololens-provisioning.md)
- 사용자 [ID가](hololens-identity.md) Azure AD입니다.

이제 개발자 모드를 사용하도록 설정하거나 디바이스 포털을 사용하지 않고도 앱을 설치할 수 있습니다.  USB를 통해 또는 Edge를 통해 Appx 번들을 장치에 다운로드하고 파일 탐색기에서 Appx 번들로 이동하여 설치를 시작하라는 메시지가 표시됩니다.  또는 웹 [페이지에서 설치를 시작하십시오.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Microsoft Store에서 설치하거나 MDM의 LOB 앱 배포 기능을 사용하여 사이드로드하는 앱과 마찬가지로 앱은 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 서명 도구를 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 사용하여 디지털 서명해야 합니다. 서명에 사용되는 인증서를 HoloLens 장치에서 신뢰해야 앱을 배포할 수 있습니다.

**응용 프로그램 설치 지침.**

1.  디바이스가 관리되지 않는지 확인
1.  HoloLens 2 장치가 전원을 들이고 PC에 연결되어 있는지 확인
1.  HoloLens 2 장치에 로그인해야 합니다.
1.  PC에서 사용자 지정 앱으로 이동하고app.appxbundle을devicename\Internal Storage\Downloads에 복사합니다.   파일 복사를 마친 후 장치 연결을 끊을 수 있습니다.
1.  HoloLens 2 장치에서 시작 메뉴를 열고 모든 앱을 선택하고 파일 탐색기 앱을 실행합니다.
1.  다운로드 폴더로 이동합니다. 앱의 왼쪽 패널에서 이 디바이스를 먼저 선택한 다음 다운로드로 이동해야 할 수 있습니다.
1.  yourapp.appxbundle 파일을 선택합니다.
1.  앱 설치 관리자가 실행됩니다. 설치 단추를 선택하여 앱을 설치합니다.
설치가 완료되면 설치된 앱이 자동으로 시작됩니다.

Windows 유니버설 샘플 [GitHub에서](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 샘플 앱을 찾아 이 흐름을 테스트할 수 있습니다.

앱 설치 관리자를 사용하여 [HoloLens 2에](app-deploy-app-installer.md)앱을 설치하는 전체 프로세스를 읽어 읽습니다.  

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### 업데이트의 개선 사항 및 수정 사항:

- 손 추적은 이제 이전에 손을 잃은 많은 새로운 경우 추적을 유지 관리합니다.  이러한 새로운 경우 일부에서는 사용자의 실제 손바목에 따라 손바라지 위치만 업데이트되고 다른 조인트는 이전 포즈에 따라 유추됩니다.  이 변경은 슬래시, 던지기, 스푸핑 및 박수와 같은 동작의 추적 일관성을 향상시키는 데 도움이 됩니다.  손이 표면에 가깝거나 개체를 잡고 있는 경우도 도움이 됩니다.  손 조인트가 유추되는 경우 [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 조인트당 정확도 값은 "High" 대신 "Approximate"로 설정됩니다.
- Azure AD 계정의 PIN 재설정 시 "문제가 발생했습니다.
- 사용자는 ET, 설정 앱의 홍채, 새 사용자 또는 알림 알림을 시작하면 부팅 후 OOBE 크래시가 훨씬 더 적게 표시됩니다.
- 사용자에게 올바른 표준 시간대가 OOBE에서 나오야 합니다.

## Windows Holographic, 버전 1903 – 2020년 12월 업데이트
- 빌드 18362.1088

이 월별 품질 업데이트에는 중요 한 변경 내용이 포함되어 있지 않습니다, 최신 Windows Holographic, 버전 20H2 – 2020년 12월 업데이트 및 빌드에 추가된 새로운 앱 설치 관리자 기능을 사용해 보아야 합니다.


## Windows Holographic, 버전 20H2
- 빌드 19041.1128

Windows Holographic, 버전 20H2를 이제 사용할 수 있으며 HoloLens 2 사용자 및 IT 전문가에게 새로운 기능 집합을 제공합니다. 자동 눈 위치 설정에서 설정의 인증서 관리자에, 향상된 키오스크 모드 기능 및 새로운 Autopilot 설정 기능까지. 이 새로운 업데이트를 통해 IT 팀은 HoloLens 장치를 구성 및 관리하는 데 더 세부적인 제어를 할 수 있으며 사용자에게 훨씬 원활한 홀로그램 환경을 제공합니다. 

이 최신 릴리스는 버전 2004에 대한 월별 업데이트이지만 이번에는 새로운 기능을 포함하게 됩니다. 주 빌드 번호는 동일하게 유지될 것이고 Windows 업데이트는 버전 2004(빌드 19041)에 대한 월별 릴리스를 나타냅니다. You can look at your Build Number in your Settings > About screen to confirm you are on the latest available build 19041.1128+. 최신 릴리스로 업데이트하려면 설정 앱을 열고 업데이트 & 보안으로 이동한 다음 업데이트 확인을 탭합니다. HoloLens 업데이트를 관리하는 방법에 대한 자세한 내용은 이 [페이지를 방문하세요.](https://docs.microsoft.com/hololens/hololens-updates)

### Windows Holographic 버전 20H2의 새로운  

| 기능                                              | 설명                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [자동 눈 위치 지원](hololens-release-notes.md#auto-eye-position-support) | 사용자가 눈 추적 보정을 거치지 않고 눈 위치를 적극적으로 계산합니다.   |
| [인증서 관리자](hololens-release-notes.md#certificate-manager)   | 설정 앱에서 인증서를 설치 및 제거할 수 있는 새로운 방법을 사용할 수 있습니다.     |
| [USB에서 자동 시작 프로비전](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 드라이브의 프로비저닝 패키지는 OOBE의 프로비저닝 페이지를 자동으로 묻습니다.                                                         |
| [OOBE에서 프로비저닝 패키지 자동 확인](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 프로비저닝 패키지는 프로비저닝 페이지에서 OOBE 중에 자동으로 적용됩니다.                                                         |
| [UI를 사용하지 않고 자동 프로비전](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 프로비저닝 자동 실행과 자동 확인을 함께 결합하는 방법 |
| [Autopilot과 Wi-Fi 연결 사용](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 이더넷 어댑터 없이 Wi-Fi 장치에서 autopilot을 사용합니다. |
| [Tenantlockdown CSP 및 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 테넌트 등록 및 정책이 적용된 후 장치를 다시 설정하거나 다시 플래시할 때만 해당 테넌트에 장치를 등록할 수 있습니다. |
| [전체 할당된 액세스](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 시스템 수준에서 키오스크를 적용하여 모든 앱에 적용할 수 있는 여러 앱 키오스크 모드에 대한 새 구성 방법입니다.                  |
| [다중 앱 키오스크에서 앱 자동 실행](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 다중 앱 키오스크 모드에 로그인할 때 응용 프로그램이 자동으로 실행됩니다.                                                        |
| [오류 처리를 위한 키오스크 모드 동작 변경](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 이제 키오스크 모드 오류에 제한적인 폴백이 있습니다.                                                                                                |
| [HoloLens 정책](hololens-release-notes.md#hololens-policies)                                    | HoloLens에 대한 새로운 정책입니다.     |
| [오프라인 Kiosk에 대한 Azure AD 그룹 구성원 캐시](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 새 정책을 사용하면 사용자가 그룹 구성원 자격 캐시를 사용하여 설정된 일 수 동안 키오스크 모드를 오프라인으로 사용할 수 있습니다.                                        |
| [HoloLens 2에 대한 새로운 장치 제한 정책](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2에 대해 새로 사용하도록 설정된 장치 관리 정책                                                                                |
| [HoloLens 2에 대한 새로운 전원 정책](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 전원 시간 제한 설정에 대해 새로 지원되는 정책입니다.  |
| [업데이트 정책](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 업데이트 제어를 허용하는 새로 사용하도록 설정된 정책입니다.           |
| [HoloLens 2에 대한 설정 페이지 표시](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 설정 앱에 표시되는 페이지를 선택하기 위해 정책입니다.             |
| [리서치 모드](hololens-release-notes.md#research-mode) | HoloLens 2에서 리서치 모드 사용. |
| [기록 길이 증가](hololens-release-notes.md#recording-length-increased) | MRC 녹음/녹화가 더 이상 5분으로 증가하지 않습니다. |
| [업데이트의 개선 및 수정](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 업데이트의 추가 수정입니다.   |

### 자동 눈 위치 지원

HoloLens 2에서는 눈 위치를 통해 정확한 홀로그램 위치, 편안한 시야 확보, 디스플레이 품질 개선 등이 가능하게 합니다. 눈 위치는 시선 추적 계산의 일부로 내부적으로 계산됩니다. 그러나, 이를 위해서는 각 사용자가 시선 입력이 필요하지 않은 경우에도 시선 추적 보정을 거쳐야 합니다.

**AEP(자동 눈 위치)** 를 사용하면 상호작용 없이도 사용자의 눈 위치를 계산할 수 있습니다. 자동 눈 위치 기능은 사용자가 장치를 사용하는 순간부터 백그라운드에서 자동으로 작동하기 시작합니다. 사용자에게 사전 시선 추적 보정이 없는 경우, 자동 눈 위치는 20~30초의 처리 시간이 지난 후 디스플레이 시스템에 사용자의 눈 위치를 제공하기 시작합니다. 사용자 데이터는 장치에 유지되지 않으므로 사용자가 장치를 껐다가 다시 켜거나 장치가 재부팅되거나 절전 모드에서 깨어난 경우 이 프로세스가 반복됩니다.

보정되지 않은 사용자가 장치를 사용할 때 자동 눈 위치 기능을 통해 몇 가지 시스템 동작이 변경됩니다. 이 컨텍스트에서 보정되지 않은 사용자는 이전에 장치에서 시선 추적 보정 프로세스를 거치지 않은 사용자를 말합니다.

| 활성 응용 프로그램 | 이전 동작 | Windows Holographic, 버전 20H2 업데이트의 동작 |
|:-------------------|:-----------------|:-----------------------------------|
| 비응시 사용 앱 또는 홀로그램 셸 |시선 추적 보정 프롬프트 대화 상자가 표시됩니다. | 프롬프트가 표시되지 않습니다. |
| 응시를 사용하는 앱 | 시선 추적 보정 프롬프트 대화 상자가 표시됩니다. | 시선 응시 스트림에 액세스하는 경우에만 시선 추적 보정 프롬프트가 표시됩니다. |

사용자가 비응시를 사용하는 응용 프로그램에서 응시 데이터에 액세스하는 앱으로 전환하는 경우 보정 프롬프트가 표시됩니다. 

다른 모든 시스템 동작은 현재 사용자에게 활성 시선 추적 보정이 없는 경우와 유사합니다. 예를 들어, 일회성 시작 제스처는 사용할 수 없습니다. 초기 설정에 대한 OOBE(첫 실행 경험)는 변경되지 않습니다.

시선 응시 데이터 또는 정밀한 홀로그램 위치가 필요한 환경에서는 보정되지 않은 사용자가 시선 추적 보정을 실행하도록 권장합니다. 시선 추적 보정 프롬프트에서 액세스하거나 시작 메뉴에서 설정 앱을 실행한 다음 **시스템 > 보정 > 눈 보정 > 눈 보정 실행**을 선택합니다.

이 정보는 나중에 다른 보정 정보와 [함께 찾을 수 있습니다.](hololens-calibration.md#auto-eye-position-support) 

### 인증서 관리자

- 새 인증서 관리자를 통해 장치 보안 및 규정 준수를 위한 감사, 진단 및 유효성 검사 도구가 개선됩니다. 이 기능을 사용하면 상업적 환경에서 인증서를 대규모로 배포, 문제 해결 및 유효성 검사를 할 수 있습니다.

Windows Holographic 버전 20H2에서는 HoloLens 2 설정 앱에 인증서 관리자를 추가하고 있습니다. Go to **Settings > Update & Security > Certificates.** 이 기능은 장치에서 인증서를 보고 설치하고 제거하는 간단하고 친숙한 방법을 제공합니다. 이제 관리자와 사용자는 새로운 인증서 관리자를 통해 감사, 진단 및 유효성 검사 도구를 개선하여 장치가 안전하고 규정을 준수하는지 확인했습니다. 

-   **감사:** 인증서가 올바르게 배포되어 있는지 확인하거나 인증서가 적절히 제거된지 확인하는 기능을 제공합니다. 
-   **진단:** 문제가 발생하면 장치에 적절한 인증서가 존재하는지 확인하면 시간이 절약되어 문제 해결에 도움이 됩니다. 
-   **유효성 검사:** 인증서가 의도된 용도에 작동하고 있는지 확인하면 특히 대규모로 인증서를 배포하기 전에 상업적 환경에서 상당한 시간을 절약할 수 있습니다.

목록에서 특정 인증서를 빠르게 찾기 위해 이름, 저장소 또는 만료 날짜별로 정렬할 수 있는 옵션이 있습니다. 사용자는 인증서를 직접 검색할 수도 있습니다. 개별 인증서 속성을 보려면 인증서를 선택하고 정보를 **클릭합니다.** 

인증서 설치는 현재 .cer 및 .crt 파일을 지원하고 있습니다. 장치 소유자는 로컬 컴퓨터 및 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자에만 설치할 수 있습니다. 사용자는 설정 UI에서 직접 설치된 인증서만 제거할 수 있습니다. 다른 수단을 통해 인증서를 설치한 경우 동일한 메커니즘을 통해 인증서도 제거해야 합니다.

#### 인증서를 설치하려면 

1.  HoloLens 2를 PC에 연결합니다.
1.  설치하려는 인증서 파일을 HoloLens 2의 위치에 저장합니다.
1.  Settings **App > Update & Security > 인증서로**이동한 다음 인증서 설치를 선택합니다.
1.  파일 **가져오기를** 클릭하고 인증서를 저장한 위치로 이동합니다.
1.  스토어 **위치를 선택합니다.**
1.  인증서 **저장소를 선택합니다.**
1.  **설치**를 클릭합니다.

이제 인증서가 장치에 설치됩니다.

#### 인증서를 제거하려면 
1. 설정 앱 업데이트 및 > 및 보안 > **이동합니다.**
1. 검색 상자에서 이름으로 인증서를 검색합니다.
1. 인증서를 선택합니다.
1. 제거를 **클릭합니다.**
1. 확인 **메시지가** 표시될 때 예를 선택합니다.

![설정 앱의 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용하여 인증서를 설치하는 방법을 보여주는 그림](images/certificate-device-install.jpg)

이 정보는 나중에 새 인증서 관리자 페이지에서 찾을 [수 있습니다.](certificate-manager.md)

### USB에서 자동 시작 프로비전

- OOBE 중에 프로비저닝 패키지가 있는 USB 드라이브를 사용하는 경우 사용자 조작을 덜 허용하는 자동화된 프로세스입니다.

이 릴리스 전에 사용자는 단추 조합을 사용하여 프로비전하기 위해 OOBE 중에 프로비저닝 화면을 수동으로 시작해야 했습니다. 이제 사용자가 USB 저장소 드라이브에서 프로비저닝 패키지를 사용하여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE가 처음으로 조작 가능한 순간에 프로비저닝 패키지로 USB 드라이브에 연결
1. 장치를 프로비전할 준비가 되면 프로비전 페이지가 있는 프롬프트가 자동으로 열립니다. 

참고: 장치가 부팅되는 동안 USB 드라이브가 연결되어 있는 경우 OOBE는 기존 USB 저장 장치를 열00개하고 연결되는 추가 장치를 확인합니다.

OOBE 중에 프로비저닝 패키지를 적용하는 데 대한 자세한 내용은 여기에서 계속 읽어 [주세요.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

이 정보는 나중에 여기에서 찾을 수 [있습니다.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### OOBE에서 프로비저닝 패키지 자동 확인
- 사용자 조작을 덜 허용하는 자동화된 프로세스로 프로비저닝 패키지 페이지가 표시되면 나열된 모든 패키지가 자동으로 적용됩니다.

프로비저닝 주 화면이 시작될 때 OOBE는 모든 프로비저닝 패키지 적용을 자동으로 시작하기 전에 10초 아래로 계산됩니다. 사용자는 예상한 패키지를 확인한 후 10초 이내에 계속 확인하거나 취소할 수 있습니다.

이 정보는 나중에 여기에서 찾을 수 [있습니다.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### UI를 사용하지 않고 자동 프로비전
- 프로비저닝을 위한 축소된 장치 조작을 위한 결합된 자동 프로세스. 

USB 장치에서 프로비저닝 자동 시작과 프로비저닝 패키지의 자동 확인을 결합하면 사용자는 장치의 UI를 사용하지 않고 또는 장치를 착용하지 않고도 HoloLens 2 장치를 자동으로 프로비전할 수 있습니다. 여러 장치에 동일한 USB 드라이브 및 프로비저닝 패키지를 계속 사용할 수 있습니다. 이 기능은 동일한 영역에 여러 장치를 동시에 배포하는 데 유용합니다. 

1. Windows [구성 디자이너를 사용하여](hololens-provisioning.md) 프로비저닝 [패키지를 만드시다.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. USB 저장소 드라이브에 패키지를 복사합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ~ [19041.1361 이상 빌드를 플래시합니다.](https://aka.ms/hololens2previewdownload) 
1. Advanced [Recovery Companion가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 디바이스 깜박이기 작업을 완료하면 USB-C 케이블을 언플러그합니다. 
1. USB 드라이브를 장치에 연결합니다.
1. HoloLens 2 장치가 OOBE로 부팅되면 USB 드라이브에서 프로비저닝 패키지를 자동으로 검색하고 프로비저닝 페이지를 실행합니다.
1. 10초 후 장치는 프로비저닝 패키지를 자동으로 적용합니다. 

이제 장치가 구성되어 프로비전 성공 화면이 표시됩니다.

이 정보는 나중에 여기에서 찾을 수 [있습니다.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Autopilot과 Wi-Fi 연결 사용
- Autopilot이 연결된 디바이스에서 작동할 수 있도록 하여 이더넷에 대한 USB-C 어댑터의 Wi-Fi 제거되었습니다.

이제 OOBE 중에 HoloLens 2를 Wifi에 연결하면 OOBE에서 장치에 대한 Autopilot 프로필을 확인합니다. 이 중 하나를 찾은 경우 AAD 가입 및 등록 흐름의 나머지를 완료하는 데 사용됩니다. 즉, USB-C 또는 Wi-Fi USB-C 어댑터에 이더넷을 사용하는 것은 더 이상 요구 사항이 아닙니다. 그러나 OOBE 시작 시에 제공된 경우 계속 사용할 수 있습니다. [HoloLens 2 디바이스용 Autopilot에 대해 자세히 알아보시고.](hololens2-autopilot.md)

### Tenantlockdown CSP 및 Autopilot
- 장치 재설정이나 reflash를 통해 장치를 테넌트로 잠가 조직의 테넌트에 디바이스를 유지합니다. 프로비저닝을 통해 계정 생성을 허용하지 않도록 하여 추가 보안을 사용합니다. 

HoloLens 2 장치는 이제 [Windows Holographic 버전 20H2부터](hololens-release-notes.md#windows-holographic-version-20h2)TenantLockdown CSP를 지원합니다. 

[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP는 Autopilot만 사용하여 HoloLens 2를 MDM 등록에 연결할 수 있습니다. TenantLockdown CSP의 RequireNetworkInOOBE 노드는 HoloLens 2에서 true 또는 false (초기 설정) 값으로 설정되고, 다시 깜박이는 경우, OS 업데이트 등의 장치에도 해당 값이 남아 있습니다. 

HoloLens 2에서 TenantLockdown Csp의 RequireNetworkInOOBE 노드가 true로 설정되면, OOBE는 네트워크 연결 후에 Autopilot 프로필이 성공적으로 다운로드되고 적용될 때까지 무기한 대기합니다. 

RequireNetworkInOOBE는 HoloLens 2에서 TenantLockdown Csp의 a 노드가 true로 설정되 면 OOBE에서 다음 작업을 허용하지 않습니다. 
- 런타임 프로비저닝을 사용하여 로컬 사용자 만들기 
- 런타임 프로비전을 통해 Azure AD 조인 작업 수행 
- OOBE 환경에서 장치를 소유하는 사용자 선택 

#### Intune을 사용하여 설정하는 방법은 무엇인가요? 
1. 사용자 지정 OMA URI 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE 노드에 true를 지정합니다.
OMA URI 값은/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE이어야 합니다.

   > [!div class="mx-imgBorder"]
   > ![OMA-URI를 통해 tennant 잠금 설정](images/hololens-tenant-lockdown.png)

1. 그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작합니다.  

장치 구성이 성공적으로 적용되었는지 Intune 포털에서 확인합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 활성화됩니다.

#### Intune을 사용하여 HoloLens 2에서 TenantLockdown RequireNetworkInOOBE 설정 해제하는 방법 
1. 위에서 만든 장치 구성이 이전에 할당된 장치 그룹에서 HoloLens 2를 제거합니다. 

1. 사용자 지정 OMA URI 기반 장치 구성 프로필을 만들고 아래와 같이 RequireNetworkInOOBE에 대해 false를 지정합니다. OMA URI 값은 /Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE이어야 합니다.

   > [!div class="mx-imgBorder"]
   > ![Intune에서 OMA URI를 통해 RequireNetworkInOOBE를 false로 설정하는 스크린샷](images/hololens-tenant-lockdown-false.png)

1. 그룹을 만들고 장치 구성 프로필을 해당 장치 그룹에 할당합니다. 

1. 이전 단계에서 만든 그룹의 HoloLens 2 장치 구성원을 만들고 동기화를 시작합니다.

장치 구성이 성공적으로 적용되었는지 Intune 포털에서 확인합니다. 이 장치 구성이 HoloLens 2 장치에 성공적으로 적용되면 TenantLockdown 효과가 비활성화 됩니다. 

#### TenantLockdown true로 설정된 후 HoloLens에서 Autopilot 프로필이 할당되지 않은 경우 OOBE 중에 무슨 문제가 발생하나요? 
OOBE는 Autopilot 프로필이 다운로드될 때까지 무기한 대기하고 대화 상자가 표시됩니다. TenantLockdown 효과를 제거하려면 장치를 원래 테넌트만 사용하여 먼저 등록해야 하며, 이전 단계에서 설명한 대로 Autopilot를 설정하지 않아야 합니다. TenantLockdown CSP에서 도입된 제한이 제거됩니다. 

![장치에서 정책이 시행될 때의 장치 내 보기입니다.](images/hololens-autopilot-lockdown.png)

이 정보는 이제 [Tenantlockdown CSP 및 Autopilot에서 Autopilot의](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)나머지와 함께 찾을 수 있습니다.

### 전역 할당된 액세스 - 키오스크 모드
- 시스템 수준에서 키오스크 모드를 적용하는 새로운 Kiosk 메서드를 사용하도록 설정하여 키오스크의 ID 관리를 줄입니다.

이 새로운 기능을 통해 IT 관리자는 시스템 수준에서 적용할 수 있는 여러 앱 키오스크 모드에 대해 HoloLens 2 장치를 구성할 수 있으며, 시스템의 ID와 관련이 없습니다. 이 디바이스에 로그인하는 모든 사용자에 적용할 수 있습니다. 여기에서 이 새로운 기능에 대해 자세히 [읽어 읽습니다.](hololens-global-assigned-access-kiosk.md)

### 다중 앱 키오스크 모드에서 응용 프로그램 자동 실행 
- 자동 앱 실행에 집중된 환경으로, 키오스크 모드 환경을 위해 선택된 UI 및 앱 선택을 추가로 늘려야 합니다.

다중 앱 키오스크 모드에만 적용하며 할당된 액세스 구성에서 아래의 강조 표시된 특성을 사용하여 1개 앱만 자동 실행으로 지정될 수 있습니다. 

사용자가 로그인하면 응용 프로그램이 자동으로 시작됩니다. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 오류 처리를 위한 키오스크 모드 동작 변경
- 키오스크 모드 오류 시 사용 가능한 앱을 제거하여 보다 안전한 키오스크 모드를 사용할 수 있습니다. 

키오스크 모드 적용에 오류가 발생하기 전에 HoloLens는 시작 메뉴에 모든 응용 프로그램을 표시하는 데 사용되었습니다. 이제 Windows Holographic 버전 20H2에서 오류가 발생하면 아래와 같이 시작 메뉴에 앱이 표시되지 않습니다. 

![오류가 발생하면 키오스크 모드가 어떻게 보이는지의 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

### HoloLens 정책
- 장치를 관리하기 위해 만들어진 HoloLens 전용 장치 관리 옵션입니다. 

Windows Holographic 버전 20H2의 HoloLens 2 장치에 대한 새로운 혼합 현실 정책이 만들어졌습니다. 새로운 제어 가능한 설정에는 밝기 설정, 볼륨 설정, 혼합 현실 캡처에서 오디오 녹음을 사용할 수 없습니다. 진단을 수집할 수 있는 시간 설정 및 AAD 그룹 구성원 캐시가 포함됩니다.  

| 새 HoloLens 정책                                | 설명                                                                               | 참고                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 밝기 단추를 사용하지 않도록 설정하여 밝기를 변경하지 않도록 합니다.       | 1 예, 0 아니요(기본값)                                                |
| MixedReality\VolumeButtonDisabled                  | 볼륨을 누를 경우 볼륨이 변경되지 않도록 볼륨 단추를 사용하지 않도록 설정할 수 있습니다.               | 1 예, 0 아니요(기본값)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2에서 오디오 녹음이 가능하지 않도록 마이크를 비활성화합니다.                      | 1 예, 0 아니요(기본값)                                                |
| MixedReality\FallbackDiagnostics                   | 진단 로그를 수집할 수 있는 경우의 동작을 제어합니다.                               | 0 사용 안 됩니다. 1 장치 소유자에 대 한 사용, 2 모두에 대 한 사용(기본값) |
| MixedReality\HeadTrackingMode                      | 향후 사용을 위해 예약되어 있습니다.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD 그룹을 대상으로 하는 Kiosk에 Azure AD 그룹 구성원 자격 캐시가 사용되는 일 수를 제어합니다. | 아래를 참조하세요.                                                           |

### 오프라인 Kiosk에 대한 Azure AD 그룹 구성원 캐시
- 오프라인 키오스크를 최대 60일 동안 AAD 그룹과 함께 사용할 수 있습니다.

이 정책은 로그인한 사용자의 Azure AD 그룹을 대상으로 하는 할당된 액세스 구성에 Azure AD 그룹 구성원 캐시를 사용할 수 있는 일 수를 제어합니다. 이 정책 값을 0보다 큰 값으로 설정하면 캐시가 사용되지 않습니다.  

이름: AADGroupMembershipCacheValidityInDays URI 값: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

최소 - 0일  
최대 - 60일 

이 정책을 올바르게 사용하는 단계: 
1. Azure AD 그룹을 대상으로 하는 키오스크에 대한 장치 구성 프로필을 만들고 HoloLens 디바이스에 할당합니다. 
1. 이 정책 값을 원하는 일 수(> 0)로 설정하고 HoloLens 장치에 할당하는 사용자 지정 OMA URI 기반 장치 구성을 생성합니다. 
    1. URI 값은 OMA-URI 텍스트 상자에 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays로 입력해야 합니다.
    1. 값은 최소/최대값 사이일 수 있습니다.
1. HoloLens 장치를 등록하고 두 구성이 장치에 적용되는지 확인합니다. 
1. 사용자가 로그인하고 Azure AD 그룹 구성원 자격이 확인되면 인터넷을 사용할 수 있는 경우 Azure AD 사용자 1에 로그인하도록 합니다. 캐시가 생성됩니다. 
1. 이제 Azure AD 사용자 1은 HoloLens를 오프라인으로 전환하고 정책 값이 X일 수에 한해 키오스크 모드에 사용할 수 있습니다. 
1. 다른 Azure AD 사용자 N에 대해 4단계와 5단계를 반복할 수 있습니다. 여기서 핵심은 Azure AD 사용자가 적어도 키오스크 구성이 대상으로 지정되는 Azure AD 그룹의 구성원인지 확인할 수 있도록 인터넷을 사용하여 장치에 로그인해야 하다는 것입니다. 
 
> [!NOTE]
> Azure AD 사용자에 대해 4단계를 수행할 때까지 "연결이 끊어진" 환경에 언급된 오류 동작이 발생합니다. 

### HoloLens 2에 대한 새로운 장치 제한 정책
- 사용자가 프로비저닝 패키지 추가 또는 제거 차단과 같은 특정 장치 관리 정책을 관리할 수 있습니다.

HoloLens 2 장치의 추가 관리 옵션을 허용하는 새로 설정된 정책입니다. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 및 AllowRemoveProvisioningPackage에 대한 이러한 두 가지 새 경찰이 일반 장치 제한에 [추가됩니다.](hololens-common-device-restrictions.md)

> [!NOTE]
> [RemoteLock과](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)관련하여 HoloLens는 ./Vendor/MSFT/RemoteLock/Lock 구성만 지원합니다. 초기화 및 복구와 같은 PIN을 다루는 구성은 지원되지 않습니다.

### HoloLens 2에 대한 새로운 전원 정책
- HoloLens가 전원 정책을 통해 절전 또는 잠겨 있는 경우를 위한 추가 옵션입니다. 

새로 추가된 정책은 관리자가 유휴 시간 제한과 같은 전원 상태 제어를 허용합니다. 각 개별 정책에 대한 자세한 내용을 보려면 해당 정책에 대한 링크를 클릭하세요.

|     정책 설명서 링크                |     참고                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 구성 디자이너에서 사용할 예제 값( 예:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 구성 디자이너에서 사용할 예제 값( 예:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 구성 디자이너에서 사용할 예제 값(예: 100)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 구성 디자이너에서 사용할 예제 값(예: 100)                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 구성 디자이너에서 사용할 예제 값( 예:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 구성 디자이너에서 사용할 예제 값( 예:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery 및 DisplayOffTimeoutPluggedIn에 대한 이러한 두 가지 새로운 규정이 일반 장치 제한에 [추가됩니다.](hololens-common-device-restrictions.md)

> [!NOTE]
> HoloLens 2에서 일관된 환경을 제공하도록 DisplayOffTimeoutOnBattery 및 StandbyTimeoutOnBattery의 값이 동일한 값으로 설정되어 있도록 하십시오. DisplayOffTimeoutPluggedIn 및 StandbyTimeoutPluggedIn에도 동일하게 적용됩니다. 최신 [대기에 대한](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 자세한 내용은 표시, 절전 및 최대 절전형 유휴 시간을 참조하세요.

### HoloLens에 대해 새로 사용하도록 설정된 업데이트 정책
- 업데이트를 설치하거나 업데이트 확인을 위해 업데이트 일시 중지 단추를 사용할 수 없습니다.

이제 HoloLens 2 장치에서 이러한 업데이트 정책을 사용할 수 있습니다.
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

이 업데이트 정책 및 HoloLens 장치에 사용하는 방법에 대한 자세한 내용은 [HoloLens](hololens-updates.md)업데이트 관리에서 여기에서 읽을 수 있습니다.

### HoloLens 2에 대한 설정 페이지 표시
- 설정 앱에서 제한된 페이지 선택을 표시하기 위해 혼동될 수 있는 설정 앱의 UI 컨트롤이 증가했습니다.

이제 IT 관리자가 시스템 설정 앱의 특정 페이지가 표시되거나 액세스되지 않도록 차단하거나 지정된 페이지를 제외한 모든 페이지에 대해 이 작업을 허용하는 정책을 사용하도록 설정했습니다. 이 기능을 완전히 사용자 지정하는 방법을 알아보려면 아래 링크를 클릭하세요.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2에서 사용자 지정할 수 있는 페이지 설정을 확인하려면 설정 [URIS 페이지를 방문하세요.](settings-uri-list.md) 
 
![설정 앱에서 수정 중인 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

### 리서치 모드
연구 모드에서 HoloLens 2는 컴퓨터 비전 연구를 위한 강력한 도구가 됩니다. HoloLens 2의 리서치 모드는 이전 버전과 비교할 때 다음과 같은 이점이 있습니다.
-   HoloLens(1세대) 리서치 모드에 노출된 센서 외에도 이제 가속도계, 자이로스코프 및 자력계를 비롯한 IMU 센서 액세스를 제공합니다.
-   HoloLens 2는 리서치 모드와 함께 사용할 수 있는 새로운 기능을 제공합니다. 특히 풍부한 실험 집합을 제공할 수 있는 풍부한 손 추적 및 눈 추적 API에 액세스할 수 있습니다.

이제 연구원들이 HoloLens 장치에서 연구 모드를 사용하도록 설정하여 이러한 모든 외부 연결 원시 이미지 센서 스트림에 액세스할 수 있습니다. HoloLens 2의 리서치 모드는 가속도계, 자이로스코프 및 자력계 판독값에 대한 액세스도 제공합니다. 사용자의 개인 정보를 보호하기 위해 리서치 모드를 통해 원시 눈 추적 카메라 이미지를 사용할 수 없지만 기존 API를 통해 시선 방향을 사용할 수 있습니다.

자세한 기술 [정보는 리서치](https://docs.microsoft.com/windows/mixed-reality/research-mode) 모드 설명서를 참조하세요.

### 기록 길이 증가
고객 피드백으로 인해 혼합 현실 캡처의 기록 [길이가 증가했습니다.](holographic-photos-and-videos.md) 혼합 현실 캡처는 더 이상 기본적으로 5분으로 제한되지 않고 사용 가능한 디스크 공간에 따라 최대 녹음/녹화 길이를 계산합니다. 장치는 사용 가능한 디스크 공간에 따라 최대 비디오 녹화 시간을 총 디스크 공간의 80%까지 예측합니다.

> [!NOTE]
> HoloLens는 다음 중 하나에 해당하면 기본 비디오 녹화 길이(5분)를 사용하게 됩니다.
> - 예상 최대 녹음/녹화 기간이 기본값인 5분보다 작습니다.
> - 사용 가능한 디스크 공간이 총 디스크 공간의 20% 미만입니다.

이 정보는 여기에서 다시 찾을 수 [있습니다.](holographic-photos-and-videos.md#maximum-recording-length) 

### 업데이트의 개선 사항 및 수정 사항:
- 이제 OOBE의 더 많은 화면이 어두운 모드에 있습니다.
- 자세한 내용은 온라인에서 최신 개인 정보 취급 방침을 설정해야 합니다.
- 사용자가 프로비저닝 패키지를 통해 VPN 프로필을 프로비전할 수 없는 문제를 해결했습니다.
- VPN 연결에 대한 프록시 구성 문제가 수정되었습니다.
- AllowUsbConnection에 대한 NCM에 대해 MDM을 통해 USB 기능 열0을 사용하지 않도록 정책이 업데이트되었습니다.
- 장치가 단일 앱 키오스크로 설정될 때 HOloLens 장치가 MTP(Media Transfer Protocol)를 통해 파일 탐색기에서 표시하지 못하게 하는 문제를 [해결했습니다.](hololens-kiosk.md) [ALLOWUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 정책을 사용하여 MTP(및 일반적으로 USB 연결)를 사용하지 않도록 설정할 수 있습니다.
- 시작 메뉴의 아이콘이 키오스크 모드에서 올바르게 조정되는 문제를 해결했습니다.
- Azure AD 그룹을 대상으로 하는 키오스크 모드와의 HTTP 캐싱으로 인한 문제가 해결되었습니다.
- 개발자 모드를 사용하지 않도록 설정하고 다시 활성화하지 않으면 사용자가 프로비저닝 패키지에서 개발자 모드를 사용하도록 설정한 후 페어링 단추를 사용할 수 없는 문제를 해결했습니다.

## Windows Holographic, 버전 1903 - 2020년 11월 업데이트
- 빌드 18362.1085

이 월별 품질 업데이트에는 중요 한 변경 내용이 포함되어 있지 않습니다, 최신 기능 릴리스 빌드 Windows Holographic 버전 20H2를 사용해 보아야 합니다.

## Windows Holographic, 버전 2004 - 2020년 10월 업데이트
- 빌드 19041.1124
 
업데이트의 개선 사항 및 수정 사항:

- 런타임 시스템 오류의 원인이 된 불필요한 검사를 제거했습니다.

## Windows Holographic, 버전 1903 - 2020년 10월 업데이트
- 빌드 18362.1081

이 월별 품질 업데이트에는 중요 한 변경 내용이 포함 되지 않습니다, Windows Holographic, 버전 2004에 대 한 최신 빌드를 시도 하는 것이 권장 합니다.

## Windows Holographic, 버전 2004 - 2020년 9월 업데이트
- 빌드 19041.1117

업데이트의 개선 사항 및 수정 사항:

- supportsMultipleInstances="true"가 appxmanifest에 있는 Visual Studio 응용 프로그램을 디버깅하지 못하게 하는 문제를 해결합니다.
- 이 릴리스에는 네트워크 프록시를 통해 실패한 인터넷 검색을 해결하기 위해 NCSI 프록시 검색 수정이 포함되어 있습니다. NCSI는 인터넷 연결 검색에 컴퓨터 프록시 및 프로필당 프록시를 사용할 수 있습니다. 사용자당 프록시는 향후 릴리스에서 NCSI에서 지원됩니다.
- 대부분의 Windows Mixed Reality 장치에서 전진 방향 벡터는 사용자의 머리가 앞으로를 보고 있는 중립 위치에 있는 경우 지면과 평행합니다. 그러나 이전 버전의 HoloLens 2에서는 벡터를 디스플레이 패널에 대한 직각으로 정렬했습니다. 이 벡터는 이상적인 방향을 상대로 몇 도 아래로 밀려 나타났습니다. 최신 버전의 HoloLens 2에서는 폼 팩터에서 시맨틱 일관성을 보장하기 위해 이를 수정했습니다.
- 특정 시나리오에서 추적 손실이 줄어듭니다.
- 이 릴리스에는 비디오 캡처 문제에 기여할 수 있는 오디오 타임스탬프 품질을 개선하는 수정이 포함되어 있습니다.

## Windows Holographic, 버전 1903 - 2020년 9월 업데이트
- 빌드 18362.1079

업데이트의 개선 사항 및 수정 사항:

- 대부분의 Windows Mixed Reality 장치에서 전진 방향 벡터는 사용자의 머리가 앞으로를 보고 있는 중립 위치에 있는 경우 지면과 평행합니다. 그러나 이전 버전의 HoloLens 2에서는 벡터를 디스플레이 패널에 대한 직각으로 정렬했습니다. 이 벡터는 이상적인 방향을 상대로 몇 도 아래로 밀려 나타났습니다. 최신 버전의 HoloLens 2에서는 폼 팩터에서 시맨틱 일관성을 보장하기 위해 이를 수정했습니다.
- 특정 시나리오에서 추적 손실이 줄어듭니다.

## Windows Holographic, 버전 2004 - 2020년 8월 업데이트
- 빌드 19041.1113

업데이트의 개선 사항 및 수정 사항:

- 설정 앱은 더 이상 사용자를 홍채 등록 또는 눈 추적 보정 환경으로 따르지 않습니다.
- OOBE 중에 장치 이름을 변경하고 다른 작업(예: 네트워크에 연결)을 수행하는 프로비저닝 패키지를 적용하면 이름 변경으로 인해 장치가 다시 시작된 후 다른 작업을 수행하지 못하는 버그가 수정되었습니다.
- 시각적 품질을 향상하기 위해 초기 장치 설정 흐름의 색 구성표가 수정되었습니다.

## Windows Holographic, 버전 1903 - 2020년 8월 업데이트
- 빌드 18362.1074

이 월별 품질 업데이트에는 중요 한 변경 내용이 포함 되지 않습니다, Windows Holographic, 버전 2004에 대 한 최신 빌드를 시도 하는 것이 권장 합니다.

## Windows Holographic, 버전 2004 - 2020년 7월 업데이트
- 빌드 19041.1109

업데이트의 개선 사항 및 수정 사항:

- 이제 개발자는 Device Portal을 사용하도록 설정하거나 사용 안 하는 경우 보안 연결이 필요한지 선택할 수 있습니다.
- OS 업데이트 후 응용 프로그램을 시작하기 위해 안정성이 향상되었습니다.
- 기본 받은 편지함 밝기를 100%로 변경했습니다.
- HoloLens 2의 Windows Device Portal에 대한 HTTPS 전달 문제를 해결했습니다.

## Windows Holographic, 버전 1903 - 2020년 7월 업데이트
- 빌드 18362.1071

업데이트의 개선 사항 및 수정 사항:

- 추적을 잃거나 다시 사용할 때 Unity 응용 프로그램에서 홀로그램이 사라지는 문제를 해결했습니다.
- 특정 장치에서 하드웨어 가속과 함께 HoloLens 에뮬레이터를 사용하는 동안 단독 HoloLens 앱이 셸로 다시 충돌하는 문제를 해결했습니다.
- HoloLens 2의 Windows Device Portal에 대한 HTTPS 전달과 관련한 문제를 해결했습니다.

## Windows Holographic, 버전 2004 - 2020년 6월 업데이트
- 빌드 19041.1106

업데이트의 개선 사항 및 수정 사항:

- 사용자 지정 MRC 레코더가 지정되지 않은 경우 특정 속성에 대한 새 기본값이 설정됩니다.
  - *MRC 비디오 효과:*
    - PreferredHologramPerspective(1 PhotoVideoCamera)
    - GlobalOpacityCoefficient(0.9(HoloLens) 1.0(몰입형 헤드셋))
  - *MRC 오디오 효과:*
    - LoopbackGain(Windows Device Portal의 Mixed Reality 캡처 페이지의 현재 "앱 오디오 게인" 값)
    - MicrophoneGain(Windows Device Portal의 Mixed Reality 캡처 페이지의 현재 "마이크 오디오 게인" 값)
- 혼합 현실 캡처 시나리오에서 오디오 품질을 향상시키는 버그를 수정했습니다. 특히 이 수정은 시작 메뉴가 표시될 때 녹음에서 오디오 오류를 **제거해야** 합니다.
- 녹화된 비디오에서 홀로그램 안정성이 향상되었습니다.
- 디바이스가 여러 일 동안 대기 상태로 남아 있는 후 혼합 현실 캡처가 비디오를 녹화할 수 없는 문제를 해결했습니다.
- HolographicSpace.UserPresence API는 일반적으로 Unity 응용 프로그램에 대해 사용하지 않도록 설정됩니다. 이 동작은 "백그라운드에서 실행" 설정을 사용하도록 설정한 경우에도 바이너리가 대칭 이동될 때 일부 앱이 일시 중지하는 문제를 방지합니다. 이제는 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 API를 사용할 수 있습니다.
- 장치 포털에 액세스하는 경우 Wi-Fi 인증서로 인해 웹 브라우저에서 액세스를 차단할 수 있습니다. 이전에 장치 인증서를 신뢰할 수 있는 경우에도 브라우저에서 "ERR_SSL_PROTOCOL_ERROR" 등의 오류를 보고할 수 있습니다. 이 경우 보안 경고를 무시하는 옵션이 아니기 때문에 Device Portal로 진행할 수 없습니다. 이 업데이트로 문제가 해결되었습니다. 이전에 브라우저 보안 경고를 제거하기 위해 PC에서 장치 인증서를 다운로드하고 신뢰할 수 있는 경우 SSL 오류가 발생하는 경우 브라우저 보안 경고를 해결하려면 새 인증서를 다운로드하고 신뢰할 수 있는 인증서를 다운로드해야 합니다.
- MSIX 패키지를 사용하여 앱을 설치할 수 있는 런타임 프로비저닝 패키지를 만드는 기능을 사용하도록 설정했습니다.
- 사용자가 디바이스가 **** 종료될 때 Mixed Reality 홈에서 모든 홀로그램을 자동으로 제거할 수 있도록 하는 설정 시스템 홀로그램에  >  ****  >  **** 설정이 추가되었습니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경하는 HoloLens 앱이 검은색을 렌더링하는 문제를 해결했습니다.
- 홍채 로그인 중 충돌을 일으키는 버그를 수정했습니다.
- 이미 최신 앱에 대해 반복된 스토어 다운로드에 대한 문제를 해결했습니다.
- 몰입형 앱이 Microsoft Edge를 반복적으로 열지 못하게 하는 버그가 수정되었습니다.
- 1903 릴리스에서 업데이트한 후 초기 부팅 시 사진 앱의 실행 문제를 해결했습니다.
- 성능 및 안정성이 향상되었습니다.

## Windows Holographic, 버전 1903 - 2020년 6월 업데이트
- 빌드 18362.1064

업데이트의 개선 사항 및 수정 사항:

- 사용자 지정 MRC 레코더가 지정되지 않은 경우 특정 속성에 대한 새 기본값이 있습니다.
  - *MRC 비디오 효과:*
    - PreferredHologramPerspective(1 PhotoVideoCamera)
    - GlobalOpacityCoefficient(0.9(HoloLens) 1.0(몰입형 헤드셋))
  - *MRC 오디오 효과:*
    - LoopbackGain(Windows Device Portal의 Mixed Reality 캡처 페이지의 현재 "앱 오디오 게인" 값)
    - MicrophoneGain(Windows Device Portal의 Mixed Reality 캡처 페이지의 현재 "마이크 오디오 게인" 값)
- HolographicSpace.UserPresence API는 일반적으로 Unity 응용 프로그램에 대해 사용하지 않도록 설정됩니다. 이 동작은 백그라운드에서 실행할 설정을 사용하도록 설정한 경우에도 바이너리가 대칭 이동되면 일부 앱이 일시 중지하는 문제를 방지합니다. 이제는 Unity 버전 2018.4.18 이상 및 2019.3.4 이상에서 API를 사용할 수 있습니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경하는 HoloLens 앱이 검은색을 렌더링하는 문제를 해결했습니다.
- 1903 릴리스에서 업데이트한 후 초기 부팅 시 사진 앱의 실행에 대한 문제를 해결했습니다.

## Windows Holographic, 버전 2004  
- 빌드 - 19041.1103

HoloLens 2, *Windows Holographic, 버전 2004의 2020년* 5월 주요 소프트웨어 업데이트에는 Windows Autopilot에 대한 지원, 앱 어두운 모드, 5G/LTE 핫스팟에 대한 USB 이더넷 지원 등의 흥미로운 새 기능이 포함되어 있습니다. To update to the latest release, open the **Settings**   app, go to Update & **Security,** and select the **Check for Updates**   button. 

|             기능                              |          설명                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot을 사용하여 프로덕션용 새 디바이스 사전 구성 및 원활한 설정                 |
|       FIDO 2 지원                             |          공유 장치에 대해 빠르고 안전한 인증을 사용하도록 설정하기 위한 FIDO2 보안 키 지원            |
|       향상된 프로비전                      |          USB 드라이브의 프로비저닝 패키지를 HoloLens에 원활하게 적용                              |
|       응용 프로그램 설치 상태                 |          MDM을 통해 앱의 설정 앱에서 설치 상태 확인이 HoloLens 2로 푸시된 경우               |
|       CSP(구성 서비스 공급자)   |          관리 제어 기능을 향상하기 위해 새로운 구성 서비스 공급자가 추가되었습니다.                 |
|       USB 5G/LTE 지원                       |          확장된 USB 이더넷 기능을 사용하면 5G/LTE를 지원할 수 있습니다.                                    |
|       어두운 앱 모드                              |          어둡게 모드와 밝은 모드를 모두 지원하는 앱에 사용할 수 있는 어두운 앱 모드로 보기 환경 개선        |
|       음성 명령                             |          HoloLens 핸즈 프리 제어를 위한 추가 시스템 음성 명령 지원                           |
|       손 추적 개선                 |          손 추적이 개선되어 단추 및 2D 슬레이트 조작의 정확도가 향상됩니다.                        |
|       품질 개선 및 수정                 |          플랫폼 전체의 다양한 시스템 성능 및 안정성 향상                            |

### Windows Autopilot 지원

HoloLens 2용 Windows Autopilot을 사용하면 장치 판매 채널에서 HoloLens를 Intune 테넌트에 미리 등록할 수 있습니다. 장치가 도착하면 테넌트에서 공유 장치로 자체 배포할 준비가 됩니다. 자체 배포를 활용하려면 장치가 USB-C-이더넷을 사용하여 설치 시 첫 번째 화면 중에 네트워크에 연결해야 합니다.

사용자가 Autopilot 자체 배포 프로세스를 시작하면 프로세스가 다음 단계를 완료합니다.

1. 장치를 Azure Active Directory(Azure AD)에 가입시킵니다.
1. Azure AD를 사용하여 Microsoft Intune(또는 다른 MDM 서비스)에 장치를 등록합니다.
1. 장치 대상 정책, 인증서, 네트워킹 프로필을 다운로드합니다.
1. 장치를 프로비전합니다.
1. 로그인 화면을 사용자에게 제시합니다.

[HoloLens 2용 Windows Autopilot 평가 가이드에서 자세히 알아보세요.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*지금 계정 관리자에게 문의하여 AutoPilot 미리 보기에 참여하세요. Autopilot-ready 장치는 곧 배송을 시작할 예정입니다.*

### FIDO2 보안 키 지원

일부 사용자는 직장 또는 학교 환경의 다른 사용자와 HoloLens 장치를 공유합니다. 따라서 긴 사용자 이름과 암호를 입력하지 않고도 사용자가 쉽게 사용할 수 있는 것이 중요합니다. FIDO(Fast Identity Online)를 사용하면 조직의 모든 사용자(Azure AD 테넌트)가 사용자 이름이나 암호를 입력하지 않고 HoloLens에 원활하게 로그인할 수 있습니다.

FIDO2 보안 키는 모든 폼 팩터에서 사용할 수 있는 "코드할 수 없는" 표준 기반 암호 없는 인증 방법입니다. FIDO는 암호 없는 인증을 위한 개방형 표준입니다. 이를 통해 사용자 및 조직이 사용자 이름이나 암호 없이 리소스에 로그인할 수 있습니다. 대신 외부 보안 키 또는 장치에 기본 제공되는 플랫폼 키를 사용합니다.

시작하려면 암호 없는 보안 키 로그인 [사용을 참조하세요.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### 프로비저닝 패키지를 통해 MDM 등록 개선

프로비저닝 패키지를 사용하면 HoloLens 첫 제공 환경이 아닌 구성 파일을 통해 HoloLens 구성을 설정할 수 있습니다. 이전에는 프로비저닝 패키지를 HoloLens 내부 메모리에 복사해야 합니다. 이제 USB 드라이브에 있을 수 있으므로 여러 HoloLens 장치에서 재사용하기 쉬우며 디바이스를 병렬로 프로비전할 수 있습니다. 프로비저닝 패키지는 이제 장치 관리에 등록할 필드도 지원하기 때문에 프로비전 후 수동 설정이 없습니다.

사용해 보기:

1. 최신 버전의 Windows 구성 디자이너를 Windows 스토어에서 PC로 다운로드합니다.
1. **HoloLens 장치**  >  **프로비전 HoloLens 2 장치를 선택합니다.**
2. 구성 프로필을 빌드합니다. 그런 다음 생성된 모든 파일을 USB-C 저장 장치에 복사합니다.
3. USB-C 장치를 신선하게 깜박이는 HoloLens에 연결합니다. 그런 다음 볼륨 **다운 전원**단추를 눌러 프로비저닝  +  **** 패키지를 적용합니다.

### 업무용 응용 프로그램 설치 상태

HoloLens에는 업무용 앱에 대한 MDM 앱 배포 및 관리가 중요합니다. 관리자와 사용자는 감사 및 진단을 위해 앱 설치 상태를 볼 수 있습니다. 이 릴리스에서는 설정 계정 액세스 **** 직장 또는 학교에서 계정 정보 클릭에 더 많은 세부  >  ****  >  ****  >  **정보를**  >  **추가했습니다.**

### 추가 CSP 및 정책

[CSP(구성](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 서비스 공급자)는 장치에서 구성 설정을 읽고, 설정하고, 수정하거나, 삭제할 수 있는 인터페이스입니다. 이 릴리스에서는 배포된 HoloLens 장치를 통해 관리자가 제어 기능을 강화하는 추가 정책에 대한 지원을 추가합니다. HoloLens에서 지원하는 CSP 목록은 [NetworkQoSPolicy CSP를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

이 릴리스의 새로운 버전:

**Policy CSP** 

정책 구성 서비스 공급자를 사용하면 엔터프라이즈에서 Windows 장치에서 정책을 구성할 수 있습니다. 이 릴리스에서는 여기에 나열된 HoloLens에 대한 새 정책을 추가했습니다. 자세한 내용은 [HoloLens 2에서 지원하는 정책 CSP를 참조합니다.](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

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

NetworkQoSPolicy 구성 서비스 공급자는 네트워크 QoS(서비스 품질) 정책을 만듭니다. QoS 정책은 일치하는 조건 집합에 따라 네트워크 트래픽에 대한 작업을 수행합니다. 자세한 내용은 [NetworkQoSPolicy CSP를 참조합니다.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### 5G/LTE 테더링 장치에 대한 확장된 USB 이더넷 지원

USB를 통해 HoloLens 2에 테더링될 때 5G/LTE 휴대폰 및 Wi-Fi 핫팟과 같은 특정 모바일 광대역 장치를 사용하도록 지원이 추가되었습니다. 이러한 장치는 이제 네트워크 설정에 다른 이더넷 **연결로** 표시됩니다. (외부 드라이버가 필요한 모바일 광대역 장치는 지원되지 않습니다.) 이 기능을 사용하면 데이터를 사용할 수 Wi-Fi 수 없는 경우 Wi-Fi 테더링이 충분하지 않은 경우 대역폭이 높은 연결을 사용할 수 있습니다. 지원되는 USB 장치에 대한 자세한 내용은 다음을 참조하고 Bluetooth [USB-C 장치에 연결합니다.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### 손 추적 개선

이 릴리스에는 몇 가지 손 추적 개선이 포함되어 있습니다.

- **포인트 안정성:** 이제 시스템은 손바운드에 의해 오목할 때 인덱스 손가락을 구부리지 않습니다. 이렇게 변경하면 단추를 누르고, 입력하고, 콘텐츠를 스크롤하는 등 정확도가 향상됩니다! 
- **우발적인 에어 탭 감소:** 에어 탭 제스처의 감지 기능이 개선했습니다. 이제 손을 측면에 놓을 때와 같은 몇 가지 일반적인 시나리오에서 실수로 활성화하는 횟수가 줄어듭니다.
- **사용자 전환 안정성:** 이제 장치를 공유할 때 손 크기를 업데이트할 때 시스템이 더 빠르고 안정적입니다.
- **손 도용 감소:** 센서 보기에 두 개 이상의 손이 있는 경우의 처리가 개선됩니다. 여러 사람이 함께 작업하는 경우 이제 추적된 손이 장면의 다른 사람의 손으로 "이동"할 가능성이 훨씬 낮습니다.
- **시스템 안정성:** 디바이스가 높은 부하에 있는 경우 손 추적이 작동하지 못하게 하는 문제를 해결했습니다.

### 어두운 모드

이제 많은 Windows 앱이 어둡게 모드와 밝은 모드를 모두 지원하고 있습니다. HoloLens 2 사용자는 둘 다 지원하는 앱의 기본 모드를 선택할 수 있습니다. 업데이트 후 기본 앱 모드는 "어둡게"이지만 설정 시스템 **** 색으로 이동하여 기본 앱 모드를 선택합니다.  >  ****  >  ****  >  **** 

이러한 "인박스" 앱은 어두운 모드를 지원합니다. 

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

![바둑판식 어두운 모드 창](images/DarkMode.jpg)

### 시스템 음성 명령

이제 디바이스의 모든 앱에서 음성 명령을 사용할 수 있습니다. 자세한 내용은 [음성을 사용하여 HoloLens를 작동할 수 있습니다.](https://docs.microsoft.com/hololens/hololens-cortana) [HoloLens 2에 대한 지원되는 언어도 참조합니다.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### Cortana 업데이트

업데이트된 앱은 Microsoft 365와 통합되어 장치 전체에서 더 많은 것을 완료할 수 있도록 합니다(현재는 US-English 있습니다. HoloLens 2에서 Cortana는 더 이상 볼륨 조정 또는 다시 시작과 같은 특정 장치별 명령을 지원하지 않습니다. 이러한 옵션은 이제 새 시스템 음성 명령에서 지원됩니다. 블로그에서 새 Cortana 앱에 대해 자세히 [알아보하세요.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### 품질 개선 및 수정

업데이트의 향상된 기능 및 수정 사항:  
- 활성 디스플레이 보정 시스템이 도입됩니다. 이 기능은 홀로그램의 안정성과 맞춤을 향상시킵니다. 이제 머리를 왼쪽으로 이동할 때 해당 자리에 있습니다.
- HoloLens로의 Wi-Fi 주기적으로 중단되는 버그를 해결했습니다. 응용 프로그램에서 짧은 대기 시간 스트리밍이 필요하다고 표시되면 [SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)함수를 호출하여 수정 프로그램을 구현합니다.
- 리서치 모드에서 스트리밍하는 동안 발생한 장치 중단을 수정했습니다.
- 경우에 따라 세션을 다시 시작하면 로그인 화면에 올바른 사용자가 표시되지 않는 버그가 수정되었습니다.
- 사용자가 설정을 통해 MDM 로그를 내보낼 수 없는 문제를 **해결했습니다.**
- 첫 실행 설치 후 바로 눈 추적의 정확도가 예상보다 낮을 수 있는 문제를 해결했습니다.
- 눈 추적 하위 시스템으로 특정 조건에서 보정을 초기화하거나 수행하지 못한 문제를 해결했습니다.
- 이미 보정된 사용자에게 눈 보정 메시지가 표시되는 문제를 해결했습니다.
- 시선 보정 중에 드라이버가 충돌하는 문제를 해결했습니다.
- 전원 단추를 반복해서 누르면 60초 시스템 시간 제한 및 셸 충돌이 발생할 수 있는 문제를 해결했습니다.
- 깊이 버퍼의 안정성이 향상되었습니다.
- 사용자가 **보다** 쉽게 피드백을 공유할 수 있도록 피드백 허브에 공유 단추가 추가되었습니다.
- RoboRaid wan이 올바르게 설치되지 않는 버그를 수정했습니다.

### 알려진 문제

- zh-CN 시스템 언어의 문제는 음성 명령이 혼합 현실 캡처를 취하거나 장치 IP 주소를 표시하지 못하게 합니다.
- 이 문제를 해결하려면 디바이스를 시작한 후 Cortana 앱을 실행하여 "안보이는 Cortana" 음성 활성화를 사용해야 합니다. 18362 빌드에서 업데이트한 경우 이전 버전의 Cortana 앱에 대한 두 번째 앱 타일이 시작에서 더 이상 작동하지 않을 수도 **있습니다.**

## Windows Holographic, 버전 1903 - 2020년 5월 업데이트 
- 빌드 18362.1061

이 월별 품질 업데이트에는 앞에서 설명한 대로 팀이 Windows Holographic 버전 2004 5월 업데이트에서 작업했기 때문에 중요 변경 내용이 포함되지 않습니다.

## Windows Holographic, 버전 1903 - 2020년 4월 업데이트
- 빌드 18362.1059

**지원되는 앱의 어두운 모드** 

대부분의 Windows 앱은 어둡게 모드와 밝은 모드를 모두 지원합니다. HoloLens 2 고객은 이제 두 색 구성표를 모두 지원하는 앱의 기본 모드를 선택할 수 있습니다. 고객 피드백에 따라 기본 앱 모드를 "어둡게"로 설정했지만, 이 설정은 설정 > **시스템** > 색으로 이동하여 **"기본** 앱 모드 선택"을 찾을 수 있습니다.

이러한 "인박스" 앱은 어두운 모드를 지원합니다.
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

**업데이트의 향상된 기능 및 수정 사항:** 
- 혼합 현실 캡처에 셸 오버레이가 포함되도록 합니다.
- 이제 Unreal 개발자는 Device Portal의 3D 보기 페이지를 사용하여 응용 프로그램을 테스트하고 디버그할 수 있습니다.
- *HolographicDepthReprojectionMethod DepthReprojection* 알고리즘을 사용할 때 혼합 현실 캡처의 홀로그램 안정성이 개선되었습니다.
- 32비트 앱의 32비트에서 "WinRT IStreamSocketListener API 클래스가 등록되지 ARM 수정했습니다.

## Windows Holographic, 버전 1903 - 2020년 3월 업데이트 
- 빌드 18362.1056

업데이트의 개선 사항 및 수정 사항:

- *HolographicDepthReprojectionMethod AutoPlanar* 알고리즘을 사용할 때 혼합 현실 캡처의 홀로그램 안정성이 개선되었습니다.
- 깊이 MF 샘플에 연결된 좌표계가 공개 설명서와 일치해야 합니다.
- 고객이 디바이스 포털을 통해 많은 양의 텍스트를 붙여넣을 수 있도록 하여 개발자 생산성이 향상되었습니다.

## Windows Holographic, 버전 1903 - 2020년 2월 업데이트 
- 빌드 18362.1053

업데이트의 개선 사항 및 수정 사항:

- Unity 응용 프로그램에 대해 HolographicSpace.UserPresence API를 일시적으로 사용하지 않도록 설정했습니다. 이 변경은 "백그라운드에서 실행" 설정을 사용하도록 설정한 경우에도 바이너리가 대칭 이동될 때 일부 앱이 일시 중지하는 문제를 방지합니다.
- 사용자가 UI가 고정된 후 몇 초 후에 다시 셸로 고정되는 손 추적으로 인한 임의 HUP 충돌을 해결했습니다.
- 손가락으로 장하면 손가락 위쪽 부분이 예기치 않게 컬링될 가능성이 낮아지기 때문에 손 추적이 개선됩니다.
- 헤드 추적, 공간 매핑 및 기타 런타임의 안정성이 향상되었습니다.

## Windows Holographic, 버전 1903 - 2020년 1월 업데이트 
- 빌드 18362.1043
 
업데이트의 개선 사항 및 수정 사항:

- HoloLens 2 에뮬레이터로 작업할 때 배타적 앱의 안정성이 향상되었습니다.

## Windows Holographic, 버전 1903 - 2019년 12월 업데이트 
- 빌드 18362.1042

업데이트의 개선 사항 및 수정 사항:

- 마지막 단계 재생(LSR) 픽스를 도입했습니다. 홀로그램의 시각적 렌더링이 향상되어 깊이를 보다 정확하게 고려하여 더욱 안정적이고 선명하게 표시됩니다. 앱이 홀로그램의 깊이를 올바르게 설정하지 않으면 이 업데이트 후 이 증상이 더 두드러지게 됩니다.
- 단독 앱과 단독 앱 간의 탐색 안정성이 고정되었습니다.
- 디바이스가 며칠 동안 대기 상태일 때 혼합 현실 캡처가 비디오를 녹화할 수 없는 문제를 해결했습니다.
- 홀로그램 안정성이 향상되었습니다.

## Windows Holographic, 버전 1903 - 2019년 11월 업데이트 
- 빌드 18362.1039

업데이트의 개선 사항 및 수정 사항:

- en-CA **** 및 en-AU에 대한 초기 설정 중에 음성 명령 선택 기능이 수정되었습니다.
- 최신 Unity 및 MRTK(Mixed Reality Toolkit) 버전에서 멀리 배치된 개체의 시각적 품질이 개선되었습니다.
- 시작 메뉴를 열고 닫을 때까지 시작 시 일시 중지된 상태로 Holographic 응용 프로그램의 문제를 해결했습니다.
- HoloLens 2 및 에뮬레이터에 대한 OpenXR 런타임 준수 수정 및 개선
