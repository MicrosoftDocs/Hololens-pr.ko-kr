---
title: 암호 사용 제한
description: HoloLens에 대한 암호 사용 제한
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, 암호 사용 제한, 암호, hololens 암호, 로그인, 로그인, windows hello, hello, windows 계정 관리자, FIDO2 로그인, FIDO 2, WEBAUTHN, 로컬 계정, hololens 보안
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034714"
---
# <a name="limiting-password-use"></a>암호 사용 제한

오늘날 대부분의 컴퓨터 시스템은 사용자 자격 증명을 보안 기반으로 활용하여 사용자가 만든 재사용 가능한 암호에 의존합니다. 이로 인해 암호는 계정 손상 및 데이터 위반에 대한 가장 일반적인 원인이 되었습니다. 예를 들어 전송 시 암호를 가로채거나 서버에서 피싱 또는 암호 스프레이 공격으로 인해 암호가 도난당하게 되어 사용자 계정에 액세스하는 데 악용될 수 있습니다.

보안 및 계정 보호를 개선하기 위해 HoloLens 2에는 디바이스 로그인을 위한 강력한 하드웨어 지원 "암호 없는" 자격 증명(Windows Hello 포함)을 사용하여 Microsoft 클라우드에 원활하게 액세스할 수 있는 기능이 있습니다.

## <a name="signing-in-from-another-device"></a>다른 디바이스에서 로그인

HoloLens 2는 초기 디바이스 설정 및 사용자 로그인 중에 Azure Active Directory 작업 계정에 원격 디바이스 로그인 옵션을 제공하여 복잡한 암호를 입력할 필요성을 줄이고 자격 증명으로 암호의 필요성을 최소화합니다. 스마트 카드를 사용하여 인증하는 사용자와 조직에서는 HoloLens 2와 같은 디바이스에서 이러한 자격 증명을 사용하는 데 어려움이 있으며 종종 기관들은 해당 문제를 해결하기 위해 복잡한 시스템과 비용이 많이 드는 프로세스를 개발합니다. 이 문제를 해결하기 위해 Azure AD에서는 HoloLens 2에서 암호 없는 로그인에 대한 두 가지 옵션을 제공합니다.

첫 번째 인증 방법은 Microsoft Authenticator 앱의 새로운 기능을 사용하여 디바이스에 연결된 사용자 자격 증명을 설정하는 키 기반 인증을 제공합니다. 관리자가 테넌트에서 활성화되면 HoloLens 디바이스 설정 중에 사용자에게 앱에서 숫자를 탭하라는 메시지가 표시됩니다. 그런 다음, 해당 사용자가 인증자 앱에 있는 번호와 일치해야 합니다. 승인을 선택하고 PIN 또는 생체 인식을 제공하고 HoloLens 설정에 대한 인증을 완료하여 진행합니다. 이 내용은 [암호 없는 로그인](/azure/active-directory/authentication/howto-authentication-passwordless-phone)에 자세히 설명되어 있습니다.

두 번째 인증 방법은 사용자에게 직관적이고 추가 인프라가 필요하지 않은 디바이스 코드 흐름입니다.  이 원격 로그인 동작은 조직의 기본 인증 메커니즘을 지원하는 신뢰할 수 있는 다른 디바이스에 의존하며, 완료되면 로그인 또는 디바이스 설정을 완료하기 위해 토큰이 HoloLens에 다시 발급됩니다. 이 흐름의 단계는 다음과 같습니다.

  1. OOBE에서 초기 디바이스 설정 또는 로그인 흐름을 진행하는 사용자에게 "다른 디바이스에서 로그인" 링크가 표시되고 탭합니다. 그러면 원격 로그인 세션이 시작됩니다.
  1. 그런 다음, 사용자에게 Azure AD STS(보안 토큰 서비스)의 디바이스 인증 엔드포인트를 가리키는 짧은 URI([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin))가 포함된 폴링 페이지가 표시됩니다. 또한 사용자에게는 클라우드에서 안전하게 생성되고 최대 수명이 15분인 일회성 코드가 제공됩니다. 코드 생성과 함께 Azure AD는 이전 단계에서 원격 로그인 요청을 시작할 때 암호화된 세션을 만들고, URI와 코드를 함께 사용하여 원격 로그인 요청을 승인합니다.
  1. 그런 다음, 사용자는 다른 디바이스에서 URI로 이동하고 HoloLens 2 디바이스에 표시된 코드를 입력하라는 메시지가 표시됩니다.
  1. 사용자가 코드를 입력하면 Azure AD STS는 원격 로그인 요청을 트리거하고 코드 생성을 요청한 사용자의 HoloLens 2 디바이스를 나타내는 페이지를 표시합니다. 그러면 피싱 공격을 방지하기 위한 확인 메시지가 사용자에게 표시됩니다.
  1. 사용자가 표시된 '애플리케이션'에 계속 로그인하도록 선택하면 Azure AD STS는 사용자에게 자격 증명을 묻는 메시지를 표시합니다. 인증이 성공적이면 Azure AD STS는 캐시된 원격 세션을 인증 코드와 함께 '승인'으로 업데이트합니다.
  1. 마지막으로, 사용자의 HoloLens 2 디바이스에 대한 폴링 페이지는 Azure AD에서 '권한 부여' 응답을 받고 사용자 코드, 연결된 저장된 권한 부여 코드의 유효성을 검사하고 요청된 대로 OAuth 토큰을 생성하여 디바이스 설정을 완료합니다. 만든 인증 토큰은 1시간 동안 유효하며 새로 고침 토큰의 수명은 90일입니다.

이 흐름에서 사용되는 코드 생성 및 암호화 알고리즘은 모두 FIPS 규격입니다. HoloLens 2 디바이스는 TPM을 활용하여 디바이스 키를 보호하고 하드웨어로 보호된 키를 사용하여 사용자 인증 후에 생성된 토큰을 암호화합니다. HoloLens 2 토큰 보안에 대한 자세한 내용은 [PRT(주 새로 고침 토큰)란?](/azure/active-directory/devices/concept-primary-refresh-token)에서 공유됩니다.

## <a name="device-sign-in-with-windows-hello"></a>Windows Hello를 사용하여 디바이스 로그인

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)는 사용자가 홍채 또는 PIN을 사용하여 디바이스에 로그인할 수 있도록 운영 체제에 직접 기본 제공되는 암호 없는 옵션을 제공합니다. PIN은 항상 자격 증명으로 사용할 수 있으며 디바이스 설정에 필요한 반면 홍채는 선택 사항이며 건너뛸 수 있습니다. 사용자는 개인 Microsoft 계정을 사용하거나 [암호를 입력하지 *않고* Azure Active Directory 작업 계정](/azure/active-directory/authentication/concept-authentication-passwordless)을 사용하여 HoloLens 디바이스에 로그인할 수 있습니다. 이러한 옵션은 사용자에게 전체 Windows 환경, 앱, 데이터, 웹 사이트 및 서비스에 대한 빠르고 안전한 액세스를 제공합니다. 암호 없는 환경을 위한 Microsoft의 전략은 여기에 자세히 설명되어 있습니다.

Windows Hello 자격 증명이 만들어지면 ID 공급자와 신뢰할 수 있는 관계를 설정하고 인증을 위한 비대칭 키 쌍을 만듭니다. Windows Hello 제스처(예: 홍채 또는 PIN)는 디바이스의 TPM(신뢰할 수 있는 플랫폼 모듈) 칩에서 백업하는 프라이빗 키를 해독하는 엔트로피를 제공합니다. 이 프라이빗 키는 인증 서버에 전송된 요청에 서명하는 데 사용되며 인증에 성공하면 사용자에게 메일, 사진 및 기타 계정 설정에 대한 액세스 권한이 부여됩니다.

자세한 내용은 다음 인포그래픽을 참조하세요.

  ![Windows Hello 로그인.](images/security-hello-sign-in.png)
  
위에 제공된 그래픽에서 nonce는 "number once"를 의미하며 임의 또는 반 임의 생성 숫자입니다. Windows Hello 생체 인식 또는 PIN 자격 증명이 설정되면 프로비전된 디바이스를 벗어나지 않습니다. 피싱 공격을 통해 사용자의 Windows Hello PIN을 도난당한 경우에도 [사용자의 물리적 디바이스가 없으면](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password) 소용이 없습니다.

보안 강화를 위해 Windows Hello 자격 증명은 TPM(신뢰할 수 있는 플랫폼 모듈)에 의해 보호되어 자격 증명이 변조되지 않도록 하고 여러 잘못된 항목에 대한 해머링 방지 보호와 노출을 방지하는 악성 소프트웨어 보호로 보완됩니다. SSO(Single Sign-On)에 대한 자세한 내용은 이 [SSO 메서드 개요](/azure/active-directory/manage-apps/what-is-single-sign-on)를 참조하세요.

홍채 인증은 PIN으로 돌아갑니다. 디바이스에서 새 PIN(강력한 인증자)을 설정하려면 사용자가 최근에 [MFA(다단계 인증)](/azure/active-directory/authentication/concept-mfa-howitworks)를 통과해야 프로세스를 완료할 수 있습니다.

## <a name="single-sign-on-with-web-account-manager"></a>웹 계정 관리자를 사용하는 Single Sign-On

SSO(Single Sign-On)를 사용하면 암호 없는 사용자가 사용자의 개인 계정이나 직장 또는 학교 계정을 활용하여 디바이스에 로그인할 수 있습니다. 사용자는 [웹 계정 관리자 API](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)를 통해 모든 통합 앱 및 서비스에서 SSO로 자동 승인됩니다.

하나의 애플리케이션을 통해 ID가 추가되면 사용자 동의 하에 시스템 수준 통합을 사용하여 모든 앱과 서비스에서 ID를 사용할 수 있습니다. 이렇게 하면 앱 로그인 부담을 크게 줄이고 사용자에게 원활한 ID 경험을 제공합니다.

웹 계정 관리자 API 구현에 대한 자세한 내용은 [웹 계정 관리자 API 구현](/windows/uwp/security/web-account-manager)을 참조하세요.

  ![보안 API.](images/security-api-img.png)
  
특수 인증 요구 사항이 있는 앱 제품군의 경우 WAM(Web Account Manager) 프레임워크를 사용자 지정 ID 공급자로 확장할 수 있습니다. 사용자는 Microsoft Store에서 UWP(유니버설 Windows 플랫폼) 앱으로 패키지된 사용자 지정 ID 공급자를 다운로드하여 해당 ID 공급자와 통합된 다른 앱에서 SSO를 활성화할 수 있습니다.

사용자 지정 WAM ID 공급자 구현에 대한 자세한 내용은 [사용자 지정 WAM ID 공급자 API 참조](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)를 참조하세요.

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>WebAuthn을 사용하여 Windows Hello 및 FIDO2로 로그인

HoloLens 2는 암호 없는 사용자 자격 증명(예: Windows Hello 또는 FIDO2 보안 키)을 사용하여 Microsoft Edge를 통해 웹 및 WebAuthn을 지원하는 웹 사이트에 안전하게 로그인할 수 있습니다. FIDO2를 사용하면 사용자 자격 증명이 표준 기반 디바이스를 활용하여 온라인 서비스에 인증할 수 있습니다.

> [!Note]
> [WebAuthn](https://www.w3.org/TR/webauthn/) 및 FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) 사양은 서비스로 구현됩니다. WebAuthn 및 FIDO2에서 지정한 서명된 메타데이터는 사용자의 존재 여부와 같은 정보를 제공하고 로컬 제스처를 통해 인증을 확인합니다.

Windows Hello와 마찬가지로 사용자가 FIDO2 자격 증명을 만들고 등록하면 디바이스(HoloLens 2 또는 FIDO2 보안 키)가 디바이스에 프라이빗 및 공개 키를 생성합니다. 프라이빗 키는 디바이스에 안전하게 저장되며, 생체 인식 또는 PIN과 같은 로컬 제스처를 사용하여 잠금 해제된 후에만 사용할 수 있습니다. 프라이빗 키가 저장되면 공개 키가 클라우드의 Microsoft 계정 시스템으로 전송되고 연결된 사용자 계정에 등록됩니다.

MSA 및 Azure AD 계정으로 로그인한 후 시스템은 생성된 숫자 또는 데이터 변수를 HoloLens 2 또는 FIDO2 디바이스로 보냅니다. HoloLens 2 또는 디바이스는 프라이빗 키를 사용하여 ID에 서명합니다. 서명된 ID와 메타데이터는 Microsoft 계정 시스템으로 다시 전송되고 공개 키를 사용하여 확인됩니다.

Windows Hello 및 FIDO2 디바이스는 HoloLens 디바이스, 특히 기본 제공 신뢰할 수 있는 플랫폼 모듈 보안 enclave를 기반으로 자격 증명을 구현합니다. TPM enclave는 프라이빗 키를 저장하고 잠금을 해제하려면 생체 인식 또는 PIN이 필요합니다. 마찬가지로 FIDO2 보안 키는 프라이빗 키를 저장하고 잠금을 해제하려면 생체 인식 또는 PIN이 필요한 기본 제공 보안 enclave가 있는 작은 외부 디바이스입니다.

두 옵션 모두 2단계 인증을 한 단계로 제공하며, 등록된 디바이스와 생체 인식 또는 PIN이 모두 성공적으로 로그인해야 합니다. 자세한 내용은 FIDO2 보안 키 그래픽 및 프로세스를 사용하는 강력한 인증을 참조하세요.

### <a name="strong-authentication-with-fido2-security-key"></a>FIDO2 보안 키를 사용하는 강력한 인증

  ![FIDO img.](images/security-fido2-whfb-smaller.png)

1. 사용자가 FIDO2 보안 키를 HoloLens 2에 연결합니다.
1. Windows가 FIDO2 보안 키를 감지합니다.
1. HoloLens가 인증 요청을 보냅니다.
1. Azure AD가 nonce를 다시 보냅니다.
1. 사용자가 보안 키의 보안 enclave에서 프라이빗 키 저장소의 잠금을 해제하는 제스처를 완료합니다.
1. FIDO2 보안 키가 프라이빗 키를 사용하여 nonce를 서명합니다.
1. 서명된 nonce를 포함하는 PRT 토큰 요청이 Azure AD로 전송됩니다.
1. Azure AD가 FIDO 키를 확인합니다.
1. Azure AD는 PRT 및 TGT를 반환하여 리소스에 액세스할 수 있도록 합니다.

MSA 및 Azure AD는 WebAuthn을 구현하여 암호 없는 인증을 지원하는 첫 번째 신뢰 당사자 중 하나입니다.

애플리케이션 및/또는 SDK에서 WebAuthn을 사용하는 자세한 내용은 [Windows 10에서 암호 없는 인증을 위한 WebAuthn API](/windows/security/identity-protection/hello-for-business/webauthnapis)로 이동하세요.

HoloLens 2는 [Azure Active Directory 암호 없는 로그인 - FIDO2 보안 키](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys)에 나열된 요구 사항을 충족하고 사양에 맞게 구현된 FIDO2 보안 디바이스를 지원해야 합니다.

## <a name="local-accounts"></a>로컬 계정

오프라인 모드 배포를 위해 단일 로컬 계정을 구성할 수 있습니다. 로컬 계정은 기본적으로 사용하도록 설정되지 않으며 디바이스를 프로비전하는 동안 구성해야 합니다. 암호를 사용하여 로그인해야 하며 대체 인증 방법(예: [비즈니스용 Windows Hello](/windows/security/identity-protection/hello-for-business/hello-overview) 또는 [Windows Hello](/windows-hardware/design/device-experiences/windows-hello))을 지원하지 않습니다.

HoloLens 사용자 계정에 대한 자세한 내용은 [HoloLens ID](hololens-identity.md)에서 찾을 수 있습니다.

IT 관리자는 사용자가 [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)을 통해 메일 이외의 관련 연결 인증 및 서비스에 MSA 계정을 사용할 수 있는지 여부를 조정합니다. 암호 구성 정책, 유휴 정책 및 잠금 화면 정책은 [디바이스 잠금](/windows/client-management/mdm/policy-csp-devicelock)을 참조하세요.
