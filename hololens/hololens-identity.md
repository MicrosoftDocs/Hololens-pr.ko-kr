---
title: HoloLens에 대한 사용자 ID 및 로그인 관리
description: HoloLens 디바이스에 대한 사용자 ID, 다중 사용자 지원, 보안, 엔터프라이즈 인증 및 로그인을 관리하는 방법을 자세히 알아보는 방법을 배워야 합니다.
keywords: HoloLens, 사용자, 계정, AAD, Azure AD, adfs, Microsoft 계정, msa, 자격 증명, 참조
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d9b7bebd9fd326def4ddfc2982bfecb09cb14186
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283279"
---
# HoloLens에 대한 사용자 ID 및 로그인 관리

> [!NOTE]
> 이 문서는 IT 프로 및 기술 매니아를 위한 기술 참조입니다. HoloLens 설정 지침을 찾고 있는 경우 "[HoloLens(1세대)](hololens1-start.md)설정" 또는["HoloLens 2"](hololens2-start.md)설정

다른 Windows 장치와 마찬가지로 HoloLens는 항상 사용자 컨텍스트에서 작동합니다. 항상 사용자 ID가 있습니다. HoloLens는 ID를 다른 Windows 10 디바이스와 거의 동일한 방식으로 처리합니다. 이 문서는 HoloLens의 ID에 대한 심층적인 참조로, HoloLens가 다른 Windows 10 디바이스와 어떻게 다른지 중점적으로 다를 수 있습니다.

HoloLens는 여러 종류의 사용자 ID를 지원합니다. 하나 이상의 사용자 계정을 사용하여 로그인할 수 있습니다. HoloLens의 ID 유형 및 인증 옵션에 대한 개요는 다음과 같습니다.

| ID 유형 | 장치당 계정 | 인증 옵션 |
| --- | --- | --- |
| [Azure AD(Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure 웹 자격 증명 공급자</li><li>Azure Authenticator 앱</li><li>생체 인식(홍채) &ndash; HoloLens 2만 <sup> 1</sup> </li><li>&ndash;HoloLens 2에 필요한 HoloLens(1세대)에 대한 PIN 선택 사항</li><li>암호</li></ul> |
| [MSA(Microsoft 계정)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>생체 인식(홍채) &ndash; HoloLens 2만 해당</li><li>&ndash;HoloLens 2에 필요한 HoloLens(1세대)에 대한 PIN 선택 사항</li><li>암호</li></ul> |
| [로컬 계정](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 암호 |

클라우드 연결 계정(Azure AD 및 MSA)은 Azure 서비스를 사용할 수 있기 때문에 더 많은 기능을 제공합니다.  

> [!NOTE]
> 1 - HoloLens 2 장치는 최대 64개 Azure AD 계정을 지원할 수 있는 반면 이러한 계정 중 10개만 홍채 인증에 등록할 수 있습니다. 이는 비즈니스용 Windows Hello에 대한 다른 생체 인식 인증 옵션과 [일치합니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## 사용자 설정

새 사용자를 설정하는 가장 일반적인 방법은 HoloLens 첫 사용 환경(OOBE) 중에입니다. 설치 중에 HoloLens는 장치에서 사용하려는 계정을 사용하여 로그인하라는 메시지를 사용자에게 제공합니다. 이 계정은 소비자 Microsoft 계정 또는 Azure에서 구성된 엔터프라이즈 계정일 수 있습니다. [HoloLens(1세대)](hololens1-start.md) 또는 [HoloLens 2 설정을 참조합니다.](hololens2-start.md)

다른 디바이스의 Windows와 마찬가지로 설치 중에 로그인하면 디바이스에 사용자 프로필이 생성됩니다. 사용자 프로필에는 앱과 데이터가 저장됩니다. 또한 동일한 계정은 Windows 계정 관리자 API를 사용하여 Edge 또는 Skype와 같은 앱에 대한 Single Sign-On을 제공합니다.  

엔터프라이즈 또는 조직 계정을 사용하여 HoloLens에 로그인하는 경우 HoloLens는 조직의 IT 인프라에 등록합니다. 이 등록을 통해 IT 관리자는 MDM(모바일 장치 관리)에서 HoloLens로 그룹 정책을 보내도록 구성할 수 있습니다.

기본적으로 다른 Windows 10 장치의 경우 HoloLens가 대기에서 다시 시작되거나 다시 시작될 때 다시 로그인해야 합니다. 설정 앱을 사용하여 이 동작을 변경하거나 그룹 정책에 의해 동작을 제어할 수 있습니다.

### 연결된 계정

데스크톱 버전의 Windows와 같은 경우 추가 웹 계정 자격 증명을 HoloLens 계정에 링크할 수 있습니다. 이러한 연결은 앱(예: 스토어)에서 리소스에 쉽게 액세스하거나 개인 및 작업 리소스에 대한 액세스를 결합할 수 있도록 합니다. 계정에 연결한 후 각 앱에 개별적으로 로그인할 필요 없이 앱에 디바이스를 사용할 수 있는 권한을 부여할 수 있습니다.

연결 계정은 이미지 또는 다운로드와 같이 장치에서 만든 사용자 데이터를 분리하지 않습니다.  

### 다중 사용자 지원 설정(Azure AD만 해당)

HoloLens는 동일한 Azure AD 테넌트의 여러 사용자를 지원합니다. 이 기능을 사용하려면 조직에 속한 계정을 사용하여 장치를 설정해야 합니다. 이후에는 동일한 테넌트의 다른 사용자가 로그인 화면에서 또는 시작 패널에서 사용자 타일을 탭하여 장치에 로그인할 수 있습니다. 한 번의 사용자만 로그인할 수 있습니다. 사용자가 로그인하면 HoloLens가 이전 사용자를 로그인합니다. Azure AD 조인의 경우를 제외하고 장치의 첫 번째 사용자는 장치 소유자로 [간주됩니다.](security-adminless-os.md#device-owner)

모든 사용자는 장치에 설치된 앱을 사용할 수 있습니다. 그러나 각 사용자에게는 자체 앱 데이터 및 기본 설정이 있습니다. 장치에서 앱을 제거하면 모든 사용자에 대해 제거됩니다.  

Azure AD 계정으로 설정된 장치는 Microsoft 계정으로 디바이스에 로그인할 수 없습니다. 사용되는 모든 후속 계정은 장치와 동일한 테넌트의 Azure AD 계정이 되어야 합니다. Microsoft 계정을 사용하여 해당 계정을 지원하는 앱(예: [Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) Store)에 계속 로그인할 수 있습니다. 장치에 로그인하기 위해 Azure AD 계정을 Microsoft 계정으로 변경하려면 장치를 [다시 래시해야 합니다.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens(1세대)는** 비즈니스용 Windows Holographic의 일부로 [Windows 10 2018년 4월](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 업데이트에서 여러 Azure AD 사용자를 [지원하기 시작했습니다.](hololens-upgrade-enterprise.md)

## 사용자 제거

설정 계정 다른 사용자로 이동하여 **** 장치에서 사용자를  >  ****  >  **제거할 수 있습니다.** 또한 이 작업은 장치에서 해당 사용자의 앱 데이터를 모두 제거하여 공간을 다시 차지합니다.  

## 앱 내에서 Single Sign-On 사용

앱 개발자는 다른 Windows 디바이스에서와 같은 [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)계정 관리자 API를 사용하여 HoloLens에서 연결된 ID를 활용할 수 있습니다. 이러한 API에 대한 일부 코드 예제는 GitHub: 웹 계정 관리 [샘플에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

계정 정보에 대한 사용자 동의 요청, 2단계 인증 등 발생할 수 있는 계정 인터럽트는 앱이 인증 토큰을 요청할 때 처리해야 합니다.

앱에 이전에 연결되지 않은 특정 계정 유형이 필요한 경우 앱에서 사용자에게 계정을 추가하라는 메시지를 표시하도록 시스템에 요청할 수 있습니다. 이 요청은 계정 설정 창이 앱의 모달 자식으로 시작될 수 있도록 트리거합니다. 2D 앱의 경우 이 창은 앱의 중앙 위에 직접 렌더링됩니다. Unity 앱의 경우 이 요청은 사용자가 홀로그램 앱에서 잠시 후 자식 창을 렌더링하도록 합니다. 이 창에서 명령 및 작업을 사용자 지정하는 데 대한 자세한 내용은 [WebAccountCommand 클래스를 참조하십시오.](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## 엔터프라이즈 및 기타 인증

앱에서 NTLM, 기본 또는 Kerberos와 같은 다른 유형의 인증을 사용하는 경우 Windows 자격 증명 [UI를](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 사용하여 사용자의 자격 증명을 수집, 처리 및 저장할 수 있습니다. 이러한 자격 증명을 수집하는 사용자 환경은 다른 클라우드 기반 계정 인터럽트와 매우 유사하며 2D 앱 위에 자식 앱으로 표시되거나 UI를 표시하기 위해 Unity 앱을 일시 중단합니다.

## 사용 불가능한 API

HoloLens용 개발이 데스크톱용 개발과 다른 한 가지 방법은 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API가 완전히 지원되지 않는다는 것입니다. API는 기본 계정이 양호한 경우 토큰을 반환합니다. 그러나 이 문서에 설명된 것 같은 인터럽트는 사용자의 UI를 표시하지 않고 계정을 올바르게 인증하지 못합니다.

## 질문과 대답

### 비즈니스용 Windows Hello는 HoloLens(1세대)에서 지원하나요?

비즈니스용 Windows Hello(로그인에 PIN 사용 지원)는 HoloLens(1세대)에 지원됩니다. HoloLens에서 비즈니스용 Windows Hello PIN 로그인을 허용합니다.

1. HoloLens 장치는 [MDM에서 관리해야 합니다.](hololens-enroll-mdm.md)
1. 디바이스에 대해 비즈니스용 Windows Hello를 사용하도록 설정해야 합니다. (Microsoft[Intune에 대한 지침을 참조하세요.)](https://docs.microsoft.com/intune/windows-hello)
1. HoloLens에서 사용자는 설정 로그인 **** 옵션 추가 PIN을 사용하여  >  ****  >  **PIN을** 설정할 수 있습니다.

> [!NOTE]
> Microsoft 계정을 사용하여 로그인하는 사용자는 설정 로그인 옵션 **** PIN 추가에서 PIN을  >  ****  >  **설정할 수 있습니다.** 이 PIN은 비즈니스용 [Windows Hello가](https://support.microsoft.com/help/17215/windows-10-what-is-hello)아니라 [Windows Hello와 연결됩니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### HoloLens 2에서 홍채 생체 인식 인증을 구현하는 방법

HoloLens 2는 홍채 인증을 지원합니다. 홍채는 Windows Hello 기술을 기반으로 하여 Azure Active Directory 및 Microsoft 계정 모두에서 사용할 수 있습니다. 홍채는 다른 Windows Hello 기술과 동일한 방식으로 구현되고 1/100K의 생체 인식 보안을 구현합니다.

자세한 내용은 [Windows Hello의](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) 생체 인식 요구 사항 및 사양을 참조하세요. Windows Hello 및 [비즈니스용](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) [Windows Hello에 대해 자세히 알아보습니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### 계정 유형이 로그인 동작에 어떤 영향을 미치나요?

로그인에 대한 정책을 적용하면 정책이 항상 준수됩니다. 로그인 정책이 적용되지 않았다면 각 계정 유형에 대한 기본 동작입니다.

- **Azure AD**: 기본적으로 인증을 요청하며 **** 설정에 따라 인증을 요청하지 않습니다.
- **Microsoft 계정:** 잠금 동작이 자동 잠금 해제를 허용하는 것은 다르지만 다시부팅할 때 로그인 인증은 계속 필요합니다.
- **로컬 계정:** 설정에서 구성할 수 없는 암호 형식의 **** 인증 요청

> [!NOTE]
> 비활성 Timers는 현재 지원되지 않습니다. 즉, **AllowIdleReturnWithoutPassword** 정책은 장치가 대기 중인 경우만 적용됩니다.

## 추가 리소스

Windows 10 보안 및 ID 설명서에서 사용자 ID 보호 및 인증에 대해 [자세히 읽어 읽습니다.](https://docs.microsoft.com/windows/security/identity-protection/)

Azure 하이브리드 ID 설명서에서 하이브리드 ID 인프라를 [철저하게 설정하는 방법을 자세히 설명합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/)
