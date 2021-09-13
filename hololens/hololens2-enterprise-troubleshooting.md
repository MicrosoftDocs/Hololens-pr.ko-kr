---
title: HoloLens 2 구현 및 관리되는 장치 문제 해결
description: 엔터프라이즈 환경에서 HoloLens 2 장치 문제 해결
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: 문제 해결
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034600"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>구현 및 관리되는 장치 문제 해결 

이 문서에서는 HoloLens 2의 구현 및 관리와 관련하여 몇 가지 문제를 해결하거나 질문에 답변하는 방법을 설명합니다.

>[!IMPORTANT]
> 문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다. 전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.


<a id="list"></a>
- [EAP 문제 해결](#eap-troubleshooting)
- [Wi-Fi 문제 해결](#wi-fi-troubleshooting)
- [네트워크 문제 해결](#network-troubleshooting)
- [이전에 설정된 HoloLens 장치에 로그인할 수 없음](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Windows Holographic 21H1로 업데이트한 후 로그인할 수 없음](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot 문제 해결](#autopilot-troubleshooting)
- [관리되는 HoloLens 장치 FAQ](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP 문제 해결
1. Wi-Fi 프로필이 올바르게 설정되었는지 다시 확인합니다.
    - EAP 유형이 올바르게 구성되어 있습니다. 일반 EAP 유형은 EAP-TLS(13), EAP-TTLS(21), PEAP(25)입니다.
    - Wi-Fi SSID 이름이 올바르고 HEX 문자열과 일치합니다.
    - EAP-TLS의 경우 TrustedRootCA에는 서버의 신뢰할 수 있는 루트 CA 인증서의 SHA-1 해시가 포함되어 있습니다. Windows PC에서 "certutil.exe -dump cert_file_name" 명령이 인증서의 SHA-1 해시 문자열을 표시합니다.
2. 액세스 지점 또는 컨트롤러 또는 AAA 서버 로그의 네트워크 패킷 캡처를 수집하여 EAP 세션이 실패하는 위치를 확인합니다.
    - HoloLens에서 제공하는 EAP ID가 필요하지 않을 경우 Wi-Fi 프로필이나 클라이언트 인증서를 통해 ID가 올바르게 프로비전되었는지 확인합니다.
    - 서버가 HoloLens 클라이언트 인증서를 거부하는 경우 필요한 클라이언트 인증서가 장치에 프로비전되었는지 확인합니다.
    - HoloLens가 서버 인증서를 거부하는 경우, 서버 루트 CA 인증서가 HoloLens에 프로비전되었는지 확인합니다.
3. 엔터프라이즈 프로필이 Wi-Fi 프로비전 패키지를 통해 프로비전된 경우 Windows 10 PC에서 프로비전 패키지를 적용하는 것이 좋습니다. Windows 10 PC에서도 실패할 경우 Windows 클라이언트 802.1X 인증 문제 해결 가이드를 따르세요.
4. 피드백 허브를 통해 피드백을 보내 주세요.

[목록으로 돌아가기](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi 문제 해결

HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 작업을 시도해 볼 수 있습니다.

1. Wi-Fi가 켜져 있는지 확인하세요. 확인하려면 시작 제스처를 사용하고 설정 > 네트워크 및 인터넷 > Wi-Fi를 선택하세요. Wi-Fi가 켜져 있으면 끈 다음 다시 켜보세요.
2. 라우터 또는 액세스 지점에 좀 더 가깝게 이동하세요.
3. Wi-Fi 라우터를 다시 시작한 다음 HoloLens를 다시 시작하세요. 다시 연결해 보세요.
4. 이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용하고 있는지 확인합니다. 제조업체 웹 사이트에서 이 정보를 찾을 수 있습니다.

장치에서 엔터프라이즈 또는 조직 계정에 로그인하면 IT 관리자가 정책을 구성하는 경우 MDM(모바일 장치 관리) 정책을 적용할 수도 있습니다.

[목록으로 돌아가기](#list)

## <a name="network-troubleshooting"></a>네트워크 문제 해결
네트워크 문제가 조직에서 HoloLens 2를 성공적으로 배포하고 사용하는 데 방해가 되는 경우 HTTP/HTTPS 트래픽을 캡처하고 분석하도록 Fiddler 및/또는 Wireshark를 구성합니다. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>HTTP 트래픽을 캡처하도록 Fiddler 구성
Fiddler는 웹 디버깅 프록시이며 HTTP(S) 문제를 해결하는 데 사용됩니다. 컴퓨터가 만드는 모든 HTTP 요청을 캡처하고 이와 관련된 모든 것을 기록합니다. HTTPS 앱에 대한 최종 사용자 인증 문제를 발견하면 대상 HoloLens 2 사용 사례의 생산성과 효율성이 향상됩니다. 

#### <a name="prerequisites"></a>필수 조건
 
- HoloLens 2 디바이스와 PC가 동일한 네트워크에 있어야 합니다.
- PC의 IP 주소를 기록합니다.

#### <a name="install-and-configure-fiddler"></a>Fiddler 설치 및 구성

1. PC에서 - Fiddler를 [설치](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure)하고 시작합니다.  
1. PC에서 - 원격 컴퓨터가 연결할 수 있도록 Fiddler를 구성합니다.
    1. Fiddler 설정 -> 연결로 이동합니다.
    1. Fiddler의 수신 포트를 기록합니다(기본값은 8866).
    1. 원격 컴퓨터 연결 허용을 선택합니다.
    1. 저장을 클릭합니다.
3. HoloLens 2에서 - Fiddler를 프록시 서버<sup>1</sup>로 구성합니다.
    1. 시작 메뉴를 열고 설정을 선택합니다.
    1. 네트워크 및 인터넷을 선택한 다음, 왼쪽 메뉴에서 프록시를 선택합니다.
    1. 수동 프록시 설정까지 아래로 스크롤하고 프록시 서버 사용을 켜기로 전환합니다.
    1. Fiddler가 설치된 PC의 IP 주소를 입력합니다.
    1. 위에서 기록해둔 포트 번호를 입력합니다(기본값은 8866).
    1. 저장을 클릭합니다.

<sup>1</sup> 빌드 20279.1006+(참가자 및 향후 릴리스)의 경우 다음 단계에 따라 프록시를 구성합니다.
1. 시작 메뉴를 열고 Wi-Fi 네트워크의 속성 페이지로 이동합니다. 
1. 프록시까지 아래로 스크롤합니다.
1. 수동 설정으로 변경
1. Fiddler가 설치된 PC의 IP 주소를 입력합니다.
1. 위에서 기록해둔 포트 번호를 입력합니다. (기본값은 8866)
1. 적용을 클릭합니다.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>HoloLens 2에서 HTTPS 트래픽 암호 해독

1. PC에서 - Fiddler 인증서를 내보냅니다.
    1. Fiddler 설정 -> HTTPS로 이동하여 고급 설정 확장합니다.
    2. Fiddler 인증서 내보내기를 클릭합니다. 데스크톱에 저장됩니다.
    3. 인증서를 HoloLens 2의 다운로드 폴더로 이동합니다.

2.  HoloLens 2에서 - Fiddler 인증서를 가져옵니다.
    1. 설정 -> 업데이트 및 보안 -> 인증서로 이동합니다.
    2. 인증서 설치를 클릭하고, 다운로드 폴더로 이동한 다음, Fiddler 인증서를 선택합니다.
    3. 저장소 위치를 로컬 컴퓨터로 변경합니다.
    4. 인증서 저장소를 루트로 변경합니다.
    5. 설치를 선택합니다.
    6. 인증서가 인증서 목록에 표시되는지 확인합니다. 그렇지 않으면 위 단계를 반복합니다.

#### <a name="inspect-https-sessions"></a>HTTP(S) 세션 검사

PC에서 Fiddler는 HoloLens 2 라이브 HTTP(S) 세션을 표시합니다. Fiddler의 검사기 패널은 다른 보기에서 HTTP(S) 요청/응답을 표시할 수 있습니다. 예를 들어 "원시" 보기는 원시 요청 또는 응답을 일반 텍스트로 표시합니다. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>네트워크 트래픽을 캡처하도록 Wireshark 구성
Wireshark는 네트워크 프로토콜 분석기이며 HoloLens 2 디바이스를 드나드는 TCP/UDP 트래픽을 검사하는 데 사용됩니다. 이렇게 하면 네트워크를 통해 HoloLens 2로 이동하는 트래픽, 트래픽의 양, 빈도, 특정 홉 사이의 대기 시간 등을 쉽게 식별할 수 있습니다.

#### <a name="prerequisites"></a>필수 조건:
- PC는 인터넷에 액세스할 수 있어야 하며 Wi-Fi를 통해 인터넷 공유를 지원해야 합니다.

#### <a name="install-and-configure-wireshark"></a>Wireshark 설치 및 구성
1. PC에서 - [Wireshark](https://www.wireshark.org/#download)를 설치합니다. 
1. PC에서 - 모바일 핫스팟을 사용하여 Wi-Fi에서 인터넷 연결을 공유합니다.
1. PC에서 - Wireshark를 시작하고 모바일 핫스팟 인터페이스에서 트래픽을 캡처합니다. 
1. HoloLens 2에서 – Wi-Fi 네트워크를 PC의 모바일 핫스팟으로 변경합니다. HoloLens 2 IP 트래픽은 Wireshark에 표시됩니다.

#### <a name="analyze-wireshark-logs"></a>Wireshark 로그 분석
Wireshark 필터는 관심 패킷을 필터링하는 데 도움이 될 수 있습니다. 

원본 [블로그](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)를 확인하세요.

[목록으로 돌아가기](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>이전에 설정된 HoloLens 장치에 로그인할 수 없음

이전에 다른 사람 즉, 클라이언트나 이전 직원에 대해 장치를 설정했고 장치의 잠금을 해제하는 암호가 없는 경우 Intune을 사용하여 원격으로 장치를 [초기화](/intune/remote-actions/devices-wipe)할 수 있습니다. 그러면 장치가 자체 리플래시됩니다.  
> [!IMPORTANT]
> 장치를 초기화하는 경우 **Retain enrollment state and user account** 선택이 취소되어 있는지 확인합니다.

[목록으로 돌아가기](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Windows Holographic 21H1로 업데이트한 후 로그인할 수 없음

### <a name="symptoms"></a>증상
- 올바른 PIN을 입력한 후 PIN을 사용한 로그온이 실패합니다.
- 웹 페이지에서 성공적으로 로그인한 후 웹 로그온 방법이 실패합니다.
- 장치가 [Azure Portal](https://portal.azure.com/) -> Azure Active Directory ->장치에서 “Azure AD 조인됨”으로 표시되지 않습니다.

### <a name="cause"></a>원인
영향을 받는 장치가 Azure AD 테넌트에서 삭제되었을 수 있습니다. 예를 들어, 다음과 같은 경우가 발생할 수 있습니다.

- 관리자나 사용자가 Azure Portal에서 또는 PowerShell을 사용하여 장치를 삭제했습니다.
- 비활성으로 인해 Azure AD 테넌트에서 장치를 제거했습니다. 효율적인 관리 환경을 위해 일반적으로 IT 관리자는 [Azure AD 테넌트에서 오래된 비활성 장치를 제거](/azure/active-directory/devices/manage-stale-devices)하는 것이 좋습니다.

Azure AD 테넌트가 삭제된 후에 영향을 받는 장치가 Azure AD 테넌트에 다시 연결하려고 하면 Azure AD로 인증되지 않습니다. PIN을 통한 캐시된 로그온으로 사용자가 계속 로그온할 수 있으므로 이 효과가 장치 사용자에게 표시되지 않는 경우가 많습니다.

### <a name="mitigation"></a>완화 방법
삭제된 HoloLens 장치를 Azure AD에 다시 추가할 수 있는 방법은 현재 없습니다. 영향을 받는 장치는 [장치 리플래시](hololens-recovery.md#clean-reflash-the-device)에 대한 지침에 따라 클린 리플래시해야 합니다.

[목록으로 돌아가기](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot 문제 해결

다음 문서는 자세한 정보를 알아보고 Autopilot 문제를 해결하는 데 유용한 리소스가 될 수 있지만, 이러한 문서가 Windows 10 데스크톱을 기반으로 하며 모든 정보가 HoloLens에 적용되는 것은 아니라는 점에 유의하세요.

- [Windows Autopilot - 알려진 문제](/mem/autopilot/known-issues)
- [Microsoft Intune에서 iOS 디바이스 등록 문제 해결](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - 정책 충돌](/mem/autopilot/policy-conflicts)

[목록으로 돌아가기](#list)

## <a name="managed-hololens-devices-faqs"></a>관리되는 HoloLens 장치 FAQ

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>SCCM(System Center Configuration Manager)을 사용하여 HoloLens 장치를 관리할 수 있나요?

아니요. HoloLens 장치를 관리하려면 MDM 시스템을 사용해야 합니다.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>AD DS(Active Directory Domain Services)를 사용하여 HoloLens 사용자 계정을 관리할 수 있나요?

아니요. HoloLens 장치에 대한 사용자 계정을 관리하려면 Azure AD(Azure Active Directory)를 사용해야 합니다.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens는 ADCS(자동화된 데이터 캡처 시스템) 자동 등록이 가능한가요?

아니요.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens는 통합 Windows 인증에 참여할 수 있나요?

아니요.

### <a name="does-hololens-support-branding"></a>HoloLens는 브랜딩을 지원하나요?

아니요. 하지만 다음 접근 방식 중 하나를 사용하여 이 문제를 해결할 수 있습니다.

- 사용자 지정 앱을 만든 다음 [키오스크 모드를 사용하도록 설정](hololens-kiosk.md)합니다. 사용자 지정 앱은 브랜딩이 있을 수 있고 다른 앱(예: Remote Assist)을 시작할 수 있습니다.  
- Azure AD의 모든 사용자 프로필 사진을 회사 로고로 변경합니다. 그러나 이 방법은 모든 시나리오에 적합하지 않을 수 있습니다.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>HoloLens 2가 제공하는 로깅 기능은 무엇인가요?

로깅은 개발 또는 문제 해결 시나리오에서 캡처할 수 있는 추적 또는 장치가 Microsoft 서버로 전송하는 원격 분석으로 제한됩니다.

## <a name="questions-about-securing-hololens-devices"></a>HoloLens 장치 보안에 대한 질문

[HoloLens 2 보안 정보](security-overview.md)를 참조하세요.
HoloLens 1세대 장치에 대해서는 [이 FAQ](hololens1-faq-security.yml)를 검토하세요.

[목록으로 돌아가기](#list)
