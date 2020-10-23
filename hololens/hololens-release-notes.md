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
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 85bba3c955c26bcfdb7e80a24be0befa1e06289e
ms.sourcegitcommit: 8fb914cf6512c67444e0ead2050cf1c82bd5decc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134427"
---
# HoloLens 2 릴리스 정보

HoloLens 장치를 능숙 하 게 사용할 수 있도록 기능, 버그, 보안 업데이트를 계속 릴리스 합니다. 이 페이지에서는 매달 HoloLens에 대 한 새로운 기능을 확인할 수 있습니다. [고급 복구 도우미를 통해 장치를 플래시](hololens-recovery.md#clean-reflash-the-device)하기 위해 최신 HoloLens 2 Full Flash 업데이트 (ffu)를 얻으려면 [여기서 다운로드](https://aka.ms/hololens2download)하세요. 다운로드는 최신 상태로 유지 되며 일반적으로 사용할 수 있는 최신 빌드를 제공 합니다.

>[!NOTE]
> HoloLens 에뮬레이터 릴리스 노트를 읽으려면 [보관 파일을 방문](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)하세요.

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
