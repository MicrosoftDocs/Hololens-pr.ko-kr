---
title: 암호 사용 제한
description: HoloLens에 대한 암호 사용 제한
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, HoloLens, 암호 사용 제한, 암호, HoloLens 암호, 로그인, 로그인, Windows Hello, Hello, Windows 계정 관리자, FIDO2 로그인, FIDO2, WEBAUTHN, 로컬 계정, HoloLens 보안
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d9527c9fee2818dfe8aa1f88a2f193415323bb1
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280667"
---
# 암호 사용 제한

현재 대부분의 컴퓨터 시스템에서는 재사용 가능한, 사용자가 만든 암호에 의존하게 하는 보안의 기본으로 사용자 자격 증명을 사용하고 있습니다. 이로 인해 암호는 계정 손상 및 데이터 위반에 대한 가장 일반적인 원인이 되었습니다. 이에 대한 예시로 암호는 전송 중에 노출되거나 서버에서 도난(피싱 또는 암호 스프레이 공격)당할 수 있으며 사용자 계정에 액세스하기 위해 손상될 수 있습니다.

보안 및 계정 보호를 개선하기 위해 HoloLens2는 장치 로그인에 대해 강력하고 하드웨어에서 지원하는 "암호 없는” 자격 증명(Windows Hello 포함) 기능을 보유하고 있으며 이를 통해 Microsoft 클라우드에 원활한 액세스를 제공하고 있습니다. 

## 다른 장치에서 로그인

HoloLens2는 초기 장치 설정 및 사용자 로그인 도중 Azure Active Directory 작업 계정에 대한 원격 장치 로그인 옵션을 제공하여 복잡하게 암호를 입력해야 할 필요성을 줄이고 자격 증명으로 암호의 필요성을 최소화합니다. 스마트 카드를 사용하여 인증하는 사용자와 조직에서는 HoloLens2와 같은 장치에서 이러한 자격 증명을 사용하는 데 어려움이 있으며 종종 기관들은 해당 문제를 해결하기 위해 복잡한 시스템과 비용이 많이 드는 프로세스를 개발합니다. 이 문제를 해결하기 위해 Azure AD에서는 HoloLens2에서 암호 없는 로그인에 대한 두 가지 옵션을 제공합니다. 

첫 번째 인증 방법은 Microsoft Authenticator 앱의 새로운 기능을 사용하여 장치에 연결된 사용자 자격 증명을 설정하는 키 기반 인증을 제공합니다. 관리자가 테넌트에서 활성화되면 HoloLens 장치 설정 중에 사용자에게 앱에서 숫자를 탭하라는 메시지가 표시됩니다. 그런 다음 해당 사용자가 인증자 앱에 있는 번호와 일치해야 합니다. 승인을 선택하고 PIN 또는 생체 인식을 제공하고 HoloLens 설정에 대한 인증을 완료하여 진행합니다. 자세한 내용은 [암호 없는 로그인](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)을 참조하세요.

두 번째 인증 방법은 사용자에게 직관적인 장치 코드 흐름이며 여기에는 추가 인프라가 필요하지 않습니다.  이 원격 로그인 동작은 조직에서 선호하는 인증 메커니즘을 지 원하고 신뢰할 수 있는 다른 장치에 사용되며 완료 후 해당 토큰은 HoloLens로 다시 발급되어 로그인 또는 장치 설정을 완료합니다. 이 흐름의 단계는 다음과 같습니다.

  1.    OOBE의 초기 장치 설정 또는 로그인 흐름을 진행하는 사용자에게 "다른 장치에서 로그인" 링크가 표시되며 그 위에 탭이 표시됩니다. 이는 원격 로그인 세션을 시작합니다.
  2.    그런 다음 사용자에게 Azure AD STS(보안 토큰 서비스)의 장치 인증 끝점을 가리키는 짧은 URI([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin))가 포함된 폴링 페이지가 표시됩니다. 또한 사용자에게 클라우드에 안전하게 생성되고 최대 수명이 15분인 일회성 코드도 표시됩니다. 코드 생성과 함께 Azure AD는 이전 단계에서 원격 로그인 요청 시작 시 암호화된 세션을 생성하고 URI 및 코드는 원격 로그인 요청을 승인하는 데 사용됩니다. 
  3.    그런 다음 사용자는 다른 장치에서 URI로 이동하며 사용자에게 해당 HoloLens2 장치에 표시된 코드를 입력하라는 메시지가 표시됩니다. 
  4.    사용자가 코드를 입력하면 Azure AD STS는 원격 로그인 요청을 트리거하고 코드 생성을 요청하는 사용자의 HoloLens2 장치를 나타내는 페이지를 표시합니다. 그런 다음 사용자에게 피싱 공격을 방지하기 위해 확인하라는 메시지가 표시됩니다. 
  5.    사용자가 표시된 '응용 프로그램'에 계속 로그인하도록 선택하는 경우 Azure AD STS는 사용자에게 자격 증명을 입력하라는 메시지를 표시합니다. 인증 성공 시 Azure AD STS는 캐시된 원격 세션을 인증 코드와 함께 '승인됨'으로 업데이트합니다.
  6.    마지막으로 사용자의 HoloLens2 장치의 폴링 페이지에서 Azure AD로부터 '권한 있음' 응답을 받고 사용자 코드 및 이와 연결되어 저장된 인증 코드의 유효성 검사를 진행하며 요청대로 OAuth 토큰을 생성하여 장치 설정을 완료합니다. 생성된 인증 토큰은 1시간 동안 유효하며 새로 고침 토큰의 수명은 90일입니다. 

이 흐름에 사용되는 코드 생성 및 암호화 알고리즘은 둘 다 FIPS를 준수합니다. HoloLens2 장치는 TPM을 활용하여 장치 키를 보호하고 하드웨어 보호 키를 사용하여 사용자 인증 후에 생성된 토큰을 암호화합니다. HoloLens2의 토큰 보안에 대한 자세한 내용은 [PRT(주 새로 고침 토큰)란?](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)에서 공유됩니다.

## Windows Hello를 사용하여 장치 로그인

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)에서는 사용자가 Iris 또는 PIN을 사용하여 장치에 로그인하는 것을 허용하는 운영 체제에 직접 빌드된 암호를 사용하지 않는 옵션을 제공합니다. PIN은 언제든지 자격 증명으로 사용할 수 있고 장치 설정이 필요하지만 Iris는 선택 사항이며 건너뛸 수 있습니다. 사용자는 [암호를 *입력하지 않고* 개인 Microsoft 계정 또는 Azure Active Directory 작업 계정](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)을 사용하여 HoloLens 장치에 로그인할 수 있습니다. 사용자는 이와 같은 옵션을 사용하여 전체 Windows 환경, 앱, 데이터, 웹 사이트 및 서비스에 빠르고 안전하게 액세스할 수 있습니다. 암호 없는 환경에 대한 Microsoft의 전략은 아래에 자세히 설명되어 있습니다.

Windows Hello 자격 증명을 만들면 ID 공급자와 신뢰 관계를 설정하고 인증에 사용되는 비대칭 키 쌍을 만듭니다. Windows Hello 제스처(예: iris 또는 PIN)는 장치에서 TPM(신뢰할 수 있는 플랫폼 모듈) 칩에 의해 지원되는 개인 키를 암호화하는 엔트로피를 제공합니다. 그런 다음 해당 개인 키는 인증 서버로 전송되는 요청에 서명하는 데 사용되며 인증 성공 시, 사용자에게 메일, 사진 및 기타 계정 설정에 대한 액세스 권한이 부여됩니다. 

자세한 내용은 다음의 인포그래픽을 참조하세요.

  ![Windows Hello 로그인](images/security-hello-sign-in.png)
  
위에 표시된 그래픽에서 Nonce는 "Number Once"를 의미하며 임의 또는 부분적인 임의로 생성된 번호입니다. Windows Hello 생체 인식 또는 PIN 자격 증명이 설정되면 프로비전된 장치를 벗어날 수 없습니다. 사용자의 Windows Hello PIN이 피싱 공격 등을 통해 도난당한 경우에도 [사용자의 물리적 장치가 없으면 아무 쓸모가 없게 됩니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password) 

추가 보안을 위해 Windows Hello 자격 증명은 TPM(신뢰할 수 있는 플랫폼 모듈)에서 보호되어 자격 증명 변조가 방지되고 여러 잘못된 항목에 대한 해머 방지 보호 기능과 노출을 방지하기 위한 악성 소프트웨어 보호 기능으로 보완됩니다. SSO(Single Sign-on)에 대한 자세한 내용은 [SSO 방법 개요](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)를 참조하세요.

Iris 인증이 PIN으로 대체됩니다. 장치에서 새 PIN(강력한 인증자)을 설정하려면 사용자가 최근 [MFA(다단계 인증)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)을 사용하여 프로세스를 완료해야 합니다.

## 웹 계정 관리자를 사용한 Single sign-on 

SSO(Single sign-on)를 통해 암호를 사용하지 않는 사용자는 사용자의 개인 계정이나 회사 또는 학교 계정을 활용하여 장치에 로그인할 수 있습니다. 사용자는 [웹 계정 관리자 API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)를 통해 모든 통합 앱 및 서비스에서 SSO를 사용하여 자동으로 인증됩니다.

하나의 응용 프로그램을 통해 ID가 추가되면 사용자 동의를 사용하여 시스템 수준 통합을 사용하는 모든 앱과 서비스에서 ID를 사용할 수 있게 됩니다. 이를 통해 앱 로그인 부담을 크게 줄이고 사용자에게 원활한 ID 환경을 제공할 수 있습니다.

웹 계정 관리자 API를 구현하는 방법에 대한 자세한 내용은 [웹 계정 관리자 API 구현](https://docs.microsoft.com/windows/uwp/security/web-account-manager)을 참조하세요.

  ![보안 API](images/security-api-img.png)
  
특수 인증 요구 사항을 포함하는 앱 제품군의 경우 WAM(웹 계정 관리자) 프레임 워크는 사용자 지정 ID 공급자로 확장될 수 있습니다. 사용자는 Microsoft 스토어에서 UWP(유니버설 Windows 플랫폼) 앱으로 패키지화된 사용자 지정 ID 공급자를 다운로드하여 해당 ID 공급자와 통합된 다른 앱에서 SSO를 사용할 수 있습니다. 

사용자 지정 WAM ID 공급자 구현에 대한 자세한 내용은 [사용자 지정 WAM ID 공급자 API 참조](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)를 참조하세요.

## WebAuthn을 사용하여 Windows Hello 및 FIDO2로 로그인

HoloLens2에서 암호를 사용하지 않는 사용자 자격 증명(예: Windows Hello 또는 FIDO2 보안 키)을 사용하여 Microsoft Edge를 통해 웹과 WebAuthn을 지원하는 웹 사이트에 안전하게 로그인할 수 있습니다. FIDO2를 통해 사용자 자격 증명으로 표준 기반 장치를 활용하여 온라인 서비스에 대해 인증할 수 있습니다.

> [!Note] 
> [WebAuthn](https://www.w3.org/TR/webauthn/) 및 FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) 사양은 서비스에 구현됩니다. WebAuthn 및 FIDO2에서 지정되고 서명된 메타 데이터는 사용자가 현재 있는지 여부와 로컬 제스처를 통해 인증을 확인하는 등의 정보를 제공합니다.

Windows Hello와 마찬가지로 사용자가 FIDO2 자격 증명을 생성하고 등록하면 장치(HoloLens2 또는 FIDO2 보안 키)가 장치에서 개인 및 공개 키를 생성합니다. 개인 키는 장치에 안전하게 저장되며 생체 인식 또는 PIN과 같은 로컬 제스처를 사용하여 잠금을 해제한 후에만 사용될 수 있습니다. 개인 키가 저장되면 공개 키는 클라우드에서 Microsoft 계정 시스템으로 전송되고 연결된 사용자 계정에 등록됩니다.

MSA 및 Azure AD 계정을 사용하여 로그인한 후 시스템은 생성된 번호 또는 데이터 변수를 HoloLens2 또는 FIDO2 장치로 전송합니다. HoloLens2 또는 장치는 개인 키를 사용하여 식별 정보에 서명합니다. 서명된 ID와 메타 데이터는 Microsoft 계정 시스템으로 다시 전송되고 공개 키를 사용하여 확인됩니다.

Windows Hello 및 FIDO2 장치는 HoloLens 장치, 특히 기본 제공되는 신뢰할 수 있는 플랫폼 모듈 보안 엔클레이브 기반의 자격 증명을 구현합니다. TPM 엔클레이브는 개인 키를 저장하며 이에 대해 잠금을 해제하려면 생체 인식 또는 PIN이 필요합니다. 이와 유사하게 FIDO2 보안 키는 개인 키를 저장하는 기본 제공된 보안 엔클레이브가 있는 작은 외부 장치 이며 이에 대해 잠금을 해제하려면 생체 인식 또는 PIN이 필요합니다.

두 옵션 모두 한 단계에서 2단계 인증을 제공합니다. 이 경우 성공적인 로그인을 위해 등록된 장치와 생체 인식 또는 PIN이 모두 필요합니다. 자세한 내용은 다음의 사항을 준수하는 FIDO2 보안 키 그래픽이 포함된 강력한 인증을 참조하세요.

  ![FIDO img](images/security-fido2-whfb.png)

MSA 및 Azure AD는 WebAuthn을 구현하여 암호 없는 인증을 지원하는 첫 신뢰 당사자 중 하나입니다. 

응용 프로그램 및/또는 SDK에서 WebAuthn를 사용하는 방법에 대한 자세한 내용은 [Windows 10에서 암호 없는 인증을 위한 WebAuthn API](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis)를 참조하세요.

## 로컬 계정

단일 로컬 계정을 오프라인 모드 배포용으로 구성할 수 있습니다. 로컬 계정은 기본적으로 사용하도록 설정되어 있지 않으며 장치 프로비전 중에 구성해야 합니다. 암호로 로그인해야 하며 대체 인증 방법(예: [비즈니스용 Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) 또는 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello))을 지원하지 않습니다. 

HoloLens 사용자 계정에 대한 자세한 내용은 [HoloLens ID](https://docs.microsoft.com/hololens/hololens-identity)를 참조하세요. 

IT 관리자는 [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)을 통해 사용자가 전자 메일 이외의 관련 연결 인증 및 서비스에 MSA 계정을 사용할 수 있는지 여부를 조정할 수 있습니다. 암호 구성 정책, 유휴 정책 및 잠금 화면 정책은 [장치 잠금](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)을 참조하세요. 
