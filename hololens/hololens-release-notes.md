---
title: HoloLens 2 릴리스 정보
description: 새로운 HoloLens 릴리스의 업데이트에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829043"
---
# HoloLens 2 릴리스 정보

HoloLens 장치를 능숙 하 게 사용할 수 있도록 기능, 버그, 보안 업데이트를 계속 릴리스 합니다. 이 페이지에서는 매달 HoloLens의 새로운 기능에 대해 알아볼 수 있습니다. 최신 HoloLens 2 FFU를 다운로드 하 여 [고급 복구 도우미](hololens-recovery.md#clean-reflash-the-device) 를 통해 장치를 플래시 하려면 [여기](https://aka.ms/hololens2download)에서 다운로드할 수 있습니다. 이는 최신 상태로 유지 되며 일반적으로 사용할 수 있는 최신 빌드와 일치 하 게 됩니다. 

HoloLens 에뮬레이터 릴리스 정보는 [여기](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)에서 찾을 수 있습니다.

## Windows 홀로그램 버전 2004-2020 업데이트
- 빌드 19041.1106

업데이트의 개선 사항 및 수정 사항:

- 사용자 지정 MRC 레코더는 특정 속성을 지정 하지 않은 경우 새 기본값을 사용 합니다.
  - MRC 비디오 효과:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (HoloLens (0.9) 1.0 (모던 헤드셋))
  - MRC 오디오 효과:
    - LoopbackGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "앱 오디오 게인" 값
    - MicrophoneGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "Mic 오디오 게인" 값
- 이 업데이트에는 혼합 현실 캡처 시나리오에서 오디오 품질을 개선 하는 버그 수정이 포함 되어 있습니다. 특히 시작 메뉴가 표시 되 면 기록의 오디오 결함 제거 해야 합니다.
- 녹화 된 비디오의 홀로그램 안정성이 개선 되었습니다.
- 장치가 여러 일 동안 대기 상태로 남아 있는 경우 mixed reality 캡처가 비디오를 녹화할 수 없는 문제를 해결 합니다.
- HolographicSpace는 일반적으로 Unity에서 실행 하는 설정을 사용 하는 경우에도 센터를 대칭 이동할 때 일부 앱이 일시 중지 되도록 하는 문제를 방지 하기 위해 Unity 응용 프로그램에서 사용 되지 않습니다. 이제 API를 Unity 버전 2018.4.18 이상, 2019.3.4 이상에서 사용할 수 있습니다.
- WiFi 연결을 통해 디바이스 포털에 액세스 하는 경우 웹 브라우저가 유효 하지 않은 인증서로 인해 액세스가 차단 되어 장치 인증서가 이전에 신뢰 된 경우에도 "ERR_SSL_PROTOCOL_ERROR"와 같은 오류를 보고할 수 있습니다.  이 경우 보안 경고를 무시 하는 옵션을 사용할 수 없기 때문에 장치 포털로 진행 될 수 없습니다.  이 업데이트는 문제를 해결 합니다.  장치 인증서가 이전에 PC에서 다운로드 되 고 신뢰 하 여 브라우저 보안 경고가 표시 되 고 SSL 오류가 발생 한 경우 새 인증서를 다운로드 하 여 브라우저 보안 경고에 신뢰 해야 합니다.
- MSIX 패키지를 사용 하 여 앱을 설치할 수 있는 런타임 프로비저닝 패키지를 만드는 기능을 사용 하도록 설정 합니다.
- 사용자가 장치를 종료할 때 혼합 현실 집에서 모든 홀로그램을 자동으로 제거할 수 있도록 하는 시스템 > 홀로그램 > 설정에서 찾을 수 있는 새로운 설정입니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경 하는 HoloLens 앱이 검정색을 렌더링 하는 문제를 해결 했습니다.
- Iri 로그인 중에 충돌을 일으킨 해결 된 버그입니다.
- 이미 존재 하는 앱에 대 한 반복 스토어 다운로드 관련 문제를 해결 합니다.
- 몰입 형 앱이 Edge를 여러 번 실행 하지 못하도록 버그를 해결 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부츠에서 사진 앱이 시작 되는 문제를 해결 합니다.
- 성능 및 안정성이 개선 되었습니다.

## Windows 홀로그램 버전 1903-2020 업데이트
- 빌드 18362.1064

업데이트의 개선 사항 및 수정 사항:

- 사용자 지정 MRC 레코더는 특정 속성을 지정 하지 않은 경우 새 기본값을 사용 합니다.
  - MRC 비디오 효과:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (HoloLens (0.9) 1.0 (모던 헤드셋))
  - MRC 오디오 효과:
    - LoopbackGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "앱 오디오 게인" 값
    - MicrophoneGain (Windows Device Portal의 혼합 현실 캡처 페이지)의 현재 "Mic 오디오 게인" 값
- HolographicSpace는 일반적으로 Unity에서 실행 하는 설정을 사용 하는 경우에도 센터를 대칭 이동할 때 일부 앱이 일시 중지 되도록 하는 문제를 방지 하기 위해 Unity 응용 프로그램에서 사용 되지 않습니다. 이제 API를 Unity 버전 2018.4.18 이상, 2019.3.4 이상에서 사용할 수 있습니다.
- HoloLens 에뮬레이터에서 픽셀 형식을 변경 하는 HoloLens 앱이 검정색을 렌더링 하는 문제를 해결 했습니다.
- 1903 릴리스에서 업데이트 한 후 초기 부츠에서 사진 앱이 시작 되는 문제를 해결 합니다.

## Windows 홀로그램 버전 2004  
빌드-19041.1103

HoloLens 2, **Windows 홀로그램, 버전 2004**에 대 한 2020 주요 소프트웨어 업데이트를 발표 하 고 있습니다. 이 릴리스에는 Windows Autopilot의 지원, 앱 어둡게 모드, 5G/LTE 핫스팟에 대 한 USB 이더넷 지원 등 흥미로운 새 기능 호스트가 포함 되어 있습니다. 최신 릴리스로 업데이트 하려면 **설정 앱**을 열고 **업데이트 & 보안**으로 이동한 다음 **업데이트 확인**   단추를 선택 합니다. 

|             기능                              |          설명                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot을 사용 하 여 새 제작 장치를 미리 구성 하 고 완벽 하 게 설정                 |
|       FIDO 2 지원                             |          공유 디바이스에 대해 빠른 및 보안 인증을 사용 하도록 FIDO2 보안 키 지원            |
|       향상 된 프로비저닝                      |          USB 드라이브에서 HoloLens에 프로비저닝 패키지를 원활 하 게 적용                              |
|       응용 프로그램 설치 상태                 |          설정 앱에서 MDM을 통해 앱의 설치 상태를 HoloLens 2로 푸시 했는지 확인              |
|       Csp (구성 서비스 공급자)   |          새로운 Csp (구성 서비스 공급자)가 관리 제어 기능을 개선 했습니다.                 |
|       USB 5G/LTE 지원                       |          확장 USB 이더넷 기능을 통해 5G/LTE를 지원 합니다.                                    |
|       어둡게 앱 모드                              |          어둡게 모드와 가벼운 모드를 모두 지 원하는 앱에 대 한 어둡게 앱 모드, 보기 환경 개선        |
|       음성 명령                             |          추가 시스템 음성 명령으로 HoloLens를 제어 하기 위한 지원, 핸 즈 프리                           |
|       향상 된 수동 추적                 |          향상 된 기능 추적 단추와 2D 슬레이트의 더욱 정확한 상호 작용                        |
|       품질 개선 및 수정                 |          플랫폼 전체의 다양 한 시스템 성능 및 안정성 향상                            |

### Windows Autopilot에 대 한 지원 

HoloLens 2 용 Windows Autopilot에서는 device sales 채널의 HoloLens를 Intune 테 넌 트에 미리 등록할 수 있습니다.  장치가 도착 하면 테 넌 트에서 공유 장치로 자체 배포할 준비가 된 것입니다. 자체 배포를 활용 하기 위해 디바이스는 USB-C ~ 이더넷 동글 또는 USB-C에서 LTE 동글을 사용 하 여 설치 프로그램의 첫 번째 화면에서 네트워크에 연결 해야 합니다. 

사용자가 Autopilot 자체 배포 프로세스를 시작하면 프로세스에서 다음 단계를 완료합니다. 

1. 장치를 Azure AD(Azure Active Directory)에 가입시킵니다. 
1. Azure AD를 사용하여 Microsoft Intune(또는 다른 MDM 서비스)에 장치를 등록합니다. 
1. 장치 대상 정책, 인증서, 네트워킹 프로필을 다운로드합니다. 
1. 장치를 프로비전합니다. 
1. 사용자에게 로그인 화면을 표시합니다. 

[Windows Autopilot HoloLens에 대해 자세히 알아보세요 2 평가 가이드를 참조](https://docs.microsoft.com/hololens/hololens2-autopilot)하세요.

**지금 AutoPilot preview에 참가 하려면 계정 관리자에 게 문의 하세요. Autopilot 준비는 곧 시작 됩니다.**

### FIDO2 보안 키 지원 

대부분 회사 또는 학교 환경에서 많은 사람들과 HoloLens 장치를 공유 합니다. 디바이스는 교실에서 학생 들 간에 공유 되는지, 아니면 장치 락커에서 체크 아웃 되었는지 여부는 긴 사용자 이름 및 암호를 입력 하지 않고 빠르고 쉽게 변경할 수 있는 것이 중요 합니다. 

FIDO를 사용 하면 조직 (AAD 테 넌 트)의 모든 사용자가 사용자 이름 또는 암호를 입력 하지 않고도 HoloLens에 쉽게 로그인 할 수 있습니다. 

FIDO2 보안 키는 모든 폼 요소에 사용할 수 있는 unphishable 표준 기반 passwordless 인증 방법입니다. FIDO (빠른 Id 온라인)는 passwordless 인증을 위한 개방형 표준입니다. FIDO에서는 사용자와 조직이 표준 보안 키 또는 장치에 기본 제공 된 플랫폼 키를 사용 하 여 사용자 이름 또는 암호 없이 해당 리소스에 로그인 할 수 있습니다. 

시작 하려면 [암호를 더 적게 하는 보안 문서](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) 를 읽어 보세요. 

### 프로 비전 패키지를 통한 MDM 등록 개선 

배포 패키지를 통해 HoloLens 사용 경험 치를 거치지 않고 구성 파일을 통해 HoloLens 구성을 설정할 수 있습니다. 이전에는 프로 비전 패키지를 HoloLens의 내부 메모리에 복사 해야 했으며, 이제 여러 HoloLens에 다시 사용 하기 쉽도록 USB 드라이브에 추가 하 고 더 많은 사용자가 HoloLens를 병렬로 구축할 수 있습니다.  또한 프로 비전 패키지는 장치 관리에서 등록할 새 필드를 지원 하므로 수동 설정 후 구축을 할 수 없습니다. 

1. 다시 시도 하려면 Windows 스토어에서 최신 버전의 Windows 구성 디자이너를 PC로 다운로드 하세요. 
1. **Hololens 장치 프로 비전** > 선택 하 여 **Hololens 2 장치 프로 비전** 을 선택 합니다. 
1. 구성 프로필을 작성 하 고 완료 되 면 생성 된 모든 파일을 USB-C 저장소 장치에 복사 합니다. 
1. 새로 플래시 HoloLens에 연결 하 고 **볼륨 작게 + 전원을** 눌러 프로비저닝 패키지를 적용 합니다. 

### Lob (기간 업무) 응용 프로그램 설치 상태 

LOB (기간 업무) 앱에 대 한 MDM 앱 배포 및 관리는 고객에 게 매우 중요 합니다. 관리자와 사용자는 감사 및 진단 목적으로 앱 설치 상태를 볼 수 있어야 합니다. 이 릴리스에서는 **설정 > 계정에 대 한 세부 정보를 추가 하 고 > 회사 또는 학교에 액세스 > 계정 > 정보를 클릭 합니다.**

### 추가 Csp 및 정책 

[CSP (구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 는 디바이스에서 구성 설정을 읽고, 설정 하 고, 수정 하 고, 삭제 하는 인터페이스입니다. 이번 릴리스에서는 더 많은 정책에 대 한 지원을 추가 하 여 관리자가 배포 된 HoloLens 장치를 사용 하는 컨트롤을 늘립니다. HoloLens에서 지원 되는 Csp 목록은이 [링크](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)를 방문 하세요. 이번 릴리스의 새로운 내용:

**Policy CSP** 

정책 구성 서비스 공급자는 엔터프라이즈에서 Windows 디바이스에 대 한 정책을 구성할 수 있도록 합니다. 이번 릴리스에서는 아래에 나열 된 HoloLens에 대 한 새로운 정책을 추가 하 고 있습니다. 지원 되는 정책에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)를 참조 하세요.  

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

**Networkqospolicy CSP** NetworkQoSPolicy 구성 서비스 공급자는 네트워크 QoS (서비스 품질) 정책을 만듭니다. QoS 정책은 일치하는 조건 집합에 따라 네트워크 트래픽에 대한 작업을 수행합니다. 이 정책에 대해 자세히 알아볼 수 [있습니다.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 

### 5G/LTE tethered 장치에 대 한 확장 된 USB 이더넷 지원

USB를 통해 HoloLens 2를 tethered 때 5G/LTE 전화기와 WiFi hotpots 같은 특정 모바일 광대역 장치를 사용할 수 있도록 지 원하는 지원이 추가 되었습니다. 이러한 디바이스는 네트워크 설정에서 다른 이더넷 연결로 표시 됩니다. 외부 드라이버를 필요로 하는 모바일 광대역 장치는 지원 되지 않습니다. WiFi를 사용할 수 없는 시나리오에서 높은 대역폭 연결을 가능 하 게 하 고 WiFi 테더 링이 충분 하지 않습니다. 지원 되는 USB 장치에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/hololens/hololens-connect-devices)를 참조 하세요.  

### 향상 된 수동 추적

이 릴리스에서는 여러 가지 개선 된 기능을 받고 있습니다. 

- **방향 포즈 안정성:** 이제 시스템은 palm에 의해 occluded 될 때 색인 손가락을 벤딩 하는 것을 거부 합니다.  이렇게 하면 단추를 누름, 입력, 스크롤 하는 등의 기능을 사용할 때 정확성이 향상 됩니다. 
- **실수로가는 탭 감소:** 이제는 번 탭 제스처의 향상 된 감지 기능을 제공 합니다.  이제 사용자의 손을 끌어 놓는 등 몇 가지 일반적인 경우에 발생 하는 우발적 정품 인증이 적습니다. 
- **사용자 전환 안정성:** 이제 시스템은 장치를 앞뒤로 공유할 때 손 크기를 업데이트 하는 것이 더 빠르고 안정적입니다. 
- **핸드 절도 감소:** 센서에 대 한 두 개 이상의 손을가지고 있는 경우를 처리 하는 것이 개선 되었습니다.  여러 사용자가 함께 작업 하는 경우 추적 된 손으로 사용자가 장면의 다른 사람을 손으로 이동할 확률이 훨씬 낮습니다. 
- **시스템 안정성:** 장치에 높은 부하가 발생 하는 경우 핸드 추적이 기간 동안 작업을 중지 하는 문제를 해결 했습니다. 

### 어둡게 모드

이제 많은 Windows 앱이 어둡게 및 라이트 모드를 모두 지원 하 고 HoloLens 2 고객은 두 가지를 모두 지 원하는 앱의 기본 모드를 선택할 수 있습니다. 업데이트 된 기본 앱 모드는 "어둡게"가 되지만 쉽게 변경할 수 있습니다. 시스템 > 색 > 설정으로 이동 하 여 "기본 앱 모드 선택"을 찾습니다. 어둡게 모드를 지 원하는 현재 앱의 일부는 다음과 같습니다. 

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

이제 장치에서 앱을 사용 하 여 음성으로 명령을 빠르게 액세스 하 고 사용할 수 있습니다. 다른 언어로 시스템을 실행 중인 경우 해당 언어로 적절 한 명령을 시도해 보세요. 명령에 대 한 자세한 내용과 사용 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/hololens/hololens-cortana)의 설명서를 참조 하세요.  

### Cortana 업데이트 

업데이트 된 앱이 Microsoft 365 (현재 영어 (미국)로 통합 되어 있으므로 장치에서 더 많은 작업을 수행할 수 있도록 도와 드립니다. HoloLens 2에서는 Cortana가 볼륨 조정과 같은 특정 디바이스 특정 명령을 더 이상 지원 하지 않으며, 이제 앞에서 설명한 새 시스템 음성 명령으로 지원 됩니다. 새로운 Cortana 앱 및 해당 블로그의 방향에 대 한 자세한 내용은 [여기](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)를 참고 하세요. 

### 품질 개선 및 수정 

업데이트에도 향상 된 기능과 수정 사항이 있습니다.  
- 이 업데이트는 활성 디스플레이 보정 시스템을 소개 합니다. 이렇게 하면 홀로그램의 안정성과 맞춤이 향상 되며,이를 통해 머리를 나란히 이동할 때 유지 됩니다. 
- 정기적으로 HoloLens에 Wi-fi 스트리밍이 주기적으로 중단 되는 버그가 해결 되었습니다. 응용 프로그램이 짧은 대기 시간 스트리밍을 필요로 하는 것으로 표시 되는 경우이 수정은이 [함수](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)를 호출 하 여 수행할 수 있습니다. 
- 리서치 모드로 스트리밍 중에 장치가 중단 될 수 있는 문제를 해결 했습니다. 
- 일부 경우에는 세션을 다시 시작할 때 올바른 사용자가 로그인 화면에 표시 되지 않는 문제가 해결 된 버그입니다. 
- 사용자가 설정을 통해 MDM 로그를 내보낼 수 없는 문제를 해결 했습니다. 
- 실행 중이 아닌 즉시 눈 추적의 정확성이 사양 보다 낮을 수 있는 문제를 해결 했습니다. 
- 특정 조건에서 아이 추적 하위 시스템이 초기화 및/또는 보정을 수행 하지 못하는 문제를 해결 했습니다. 
- 이미 보정 된 사용자에 대 한 눈 보정에 대 한 메시지가 표시 되는 문제를 해결 했습니다. 
- 눈 보정 중 드라이버의 작동이 중단 되는 문제를 해결 했습니다. 
- 반복 되는 power button enter로 인해 60 두번째 시스템 시간 초과 및 셸 충돌이 발생할 수 있는 문제를 해결 했습니다. 
- 깊이 버퍼의 안정성을 개선 했습니다. 
- 사용자 의견을 더욱 쉽게 공유할 수 있도록 피드백 허브에 ' 공유 ' 단추가 추가 되었습니다. 
- RoboRaid 올바르게 설치 되지 않은 버그가 해결 되었습니다. 

### 알려진 문제

- Microsoft는 혼합 현실 캡처 또는 장치 IP 주소 표시에 대 한 음성 명령이 작동 하지 않도록 하는 zh-cn 시스템 언어 사용에 대 한 문제를 조사 중입니다.
- "안녕 코타 나" 음성 정품 인증을 사용 하기 위해 디바이스를 부팅 한 후 Cortana 앱을 시작 해야 하는 문제를 조사 중 이며, 18362 빌드에서 업데이트 한 경우에는 더 이상 작동 하지 않는 이전 버전의 Cortana 앱에 대 한 두 번째 앱 타일이 표시 될 수 있습니다. 

## Windows 홀로그램 버전 1903-2020 업데이트를 할 수 있습니다. 
- 빌드 18362.1061

이 월 품질 업데이트에는 현재 Windows 홀로그램에서 제공 되는 최고 품질 기능 업데이트를 제공 하는 데 중점을 두기 때문에 메모의 변경 내용이 포함 되어 있지 않습니다. 위의 세부 정보는 버전 2004에서 업데이트 될 수 있습니다. 이 기회를 최신 기능 업데이트로 이동 하 여 새로운 변경 사항을 적용 해 보세요.

## Windows 홀로그램 버전 1903-2020 업데이트 4 월
- 빌드 18362.1059

**지원 되는 앱의 어둡게 모드** 

대부분의 Windows 앱은 어둡게 및 라이트 모드를 모두 지원 하며 곧 HoloLens 2 고객은 두 색 구성표를 모두 지 원하는 앱의 기본 모드를 선택할 수 있습니다. 이 업데이트를 통해 overwhelmingly 긍정적인 고객 의견을 기반으로 기본 앱 모드를 "어둡게"로 설정 하 고 있지만 언제 든 지이 설정을 쉽게 변경할 수 있습니다.
**시스템 > 색 > 설정** 으로 이동 하 여 **"기본 앱 모드 선택"** 을 찾습니다.

어둡게 모드를 지 원하는 현재 앱의 일부는 다음과 같습니다.
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
- 셸 오버레이가 mixed reality 캡처에 포함 되어 있는지 확인 합니다.
- 실제 개발자는 이제 Device Portal의 3D 보기 페이지를 사용 하 여 해당 응용 프로그램을 테스트 하 고 디버그할 수 있습니다.
- HolographicDepthReprojectionMethod DepthReprojection 알고리즘이 사용 되는 경우 mixed reality 캡처에서 홀로그램 안정성을 개선 합니다.
- 32 비트 ARM 앱에 대 한 해결 되지 않은 WinRT IStreamSocketListener API 클래스 등록 오류.

## Windows 홀로그램 버전 1903-2020 업데이트 3 월 
- 빌드 18362.1056

업데이트의 개선 사항 및 수정 사항:

- HolographicDepthReprojectionMethod AutoPlanar 알고리즘을 사용 하는 경우 mixed reality 캡처에서 홀로그램 안정성을 개선 합니다.
- 깊이 MF 샘플에 연결 된 좌표계가 공용 문서와 일관성을 유지 하도록 보장 합니다.
- 장치 포털을 통해 많은 양의 텍스트를 붙여 넣을 수 있도록 하 여 개발자 생산성 향상

## Windows 홀로그램 버전 1903-2020 업데이트 
- 빌드 18362.1053

업데이트의 개선 사항 및 수정 사항:

- 백그라운드에서 실행 하는 설정을 사용 하는 경우에도, 센터를 대칭 이동할 때 일부 앱이 일시 중지 되는 문제를 방지 하기 위해 Unity 응용 프로그램의 HolographicSpace 현재 상태 API를 일시적으로 비활성화 했습니다.
- 수동 추적을 사용 하 여 대/소문자를 수정한 후 몇 초 후에 UI가 셸로 다시 재생 되는 것을 볼 수 있습니다.
- Poking는 인덱스 손가락을 사용 하는 동안에는 해당 손가락의 위쪽 부분이 예기치 않게 넘기기 때문에 직접 추적 하는 것이 개선 되었습니다.
- 헤드 추적, 공간 매핑 및 기타 런타임 개선의 신뢰성.

## Windows 홀로그램, 버전 1903-2020 업데이트 
- 빌드 18362.1043

업데이트 개선:

- HoloLens 2 에뮬레이터 작업을 할 때 전용 앱에 대 한 안정성 개선.

## Windows 홀로그램 버전 1903-2019 업데이트-12 월 
- 빌드 18362.1042

업데이트의 개선 사항 및 수정 사항:

- LSR (마지막 단계 복제) 수정 사항에 대해 설명 합니다. 홀로그램의 시각적 렌더링이 향상 되어 깊이에 대 한 더 정확 하 게 회계 되므로 더욱 안정적이 고 선명 하 게 표시 됩니다. 이 업데이트 후 앱에서 홀로그램의 깊이를 올바르게 설정 하지 않으면 더욱 눈에 띄게 됩니다.
- 독점 앱의 안정성을 해결 합니다.
- 장치가 여러 일 동안 대기 상태로 남아 있는 경우 Mixed Reality 캡처가 비디오를 녹화할 수 없는 문제를 해결 합니다.
- 홀로그램 안정성이 개선 되었습니다.

## Windows 홀로그램 버전 1903-2019 업데이트-11 월 
- 빌드 18362.1039

업데이트의 개선 사항 및 수정 사항:

- En-us 및 en-AU에 대해 초기 설정 중에 **"선택"** 음성 명령을 수정 합니다.
- 최신 Unity 및 MRTK 버전에서 멀리 떨어진 개체의 시각적 품질이 개선 되었습니다.
- 시작 시 핀 패널이 홀로그램 다시 해제 될 때까지 응용 프로그램이 일시 중지 된 상태로 눌려 있는 문제 해결을 해결 합니다.
- HoloLens 2 및 에뮬레이터에 대 한 OpenXR 런타임 준수 수정 및 개선 사항.


