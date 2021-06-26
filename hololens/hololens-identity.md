---
title: HoloLens에 대한 사용자 ID 및 로그인 관리
description: HoloLens 디바이스에 대한 사용자 ID, 다중 사용자 지원, 보안, 엔터프라이즈 인증 및 로그인을 관리하는 방법을 알아봅니다.
keywords: HoloLens, 사용자, 계정, AAD, Azure AD, adfs, microsoft 계정, msa, 자격 증명, 참조
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
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924420"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens에 대한 사용자 ID 및 로그인 관리

> [!NOTE]
> 이 문서는 IT 전문가 및 기술 전문가를 위한 기술 참조입니다. HoloLens 설정 지침을 찾고 있는 경우 "[HoloLens(1세대) 설정"](hololens1-start.md)또는 "[HoloLens 2 설정"을](hololens2-start.md)읽어보세요.

다른 Windows 디바이스와 마찬가지로 HoloLens는 항상 사용자 컨텍스트에서 작동합니다. 항상 사용자 ID가 있습니다. HoloLens는 다른 Windows 10 디바이스와 거의 동일한 방식으로 ID를 처리합니다. 이 문서는 HoloLens의 ID에 대한 심층적인 참조이며 HoloLens가 다른 Windows 10 디바이스와 어떻게 다른지에 중점을 둡니다.

HoloLens는 여러 종류의 사용자 ID를 지원합니다. 하나 이상의 사용자 계정을 사용하여 로그인할 수 있습니다. HoloLens의 ID 유형 및 인증 옵션에 대한 개요는 다음과 같습니다.

| ID 형식 | 디바이스당 계정 수 | 인증 옵션 |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure 웹 자격 증명 공급자</li><li>Azure Authenticator 앱</li><li>생체 인식(아이리스) &ndash; HoloLens 2<sup>2만</sup> </li><li>&ndash;holoLens(1세대)의 PIN 선택 사항으로, HoloLens 2</li><li>암호</li></ul> |
| [Microsoft 계정(MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>생체 인식(아이리스) &ndash; HoloLens 2</li><li>&ndash;holoLens(1세대)의 PIN 선택 사항으로, HoloLens 2</li><li>암호</li></ul> |
| [로컬 계정](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 암호 |

클라우드 연결 계정(Azure AD 및 MSA)은 Azure 서비스를 사용할 수 있으므로 더 많은 기능을 제공합니다.  
> [!IMPORTANT]
> 1 - Azure AD Premium 디바이스에 로그인할 필요가 없습니다. 그러나 자동 등록 및 Autopilot과 같은 낮은 터치 클라우드 기반 배포의 다른 기능에 필요합니다.

> [!NOTE]
> 2 - HoloLens 2 디바이스는 최대 64개의 Azure AD 계정을 지원할 수 있지만 이러한 계정 중 10개만 아이리스 인증에 등록할 수 있습니다. 이는 비즈니스용 Windows Hello 다른 [생체 인식 인증 옵션과](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)일치합니다.

## <a name="setting-up-users"></a>사용자 설정

새 사용자를 설정하는 가장 일반적인 방법은 HoloLens OOBE(첫 번째 경험)를 수행하는 것입니다. 설치하는 동안 HoloLens는 사용자가 디바이스에서 사용하려는 계정을 사용하여 로그인하라는 메시지를 표시합니다. 이 계정은 소비자 Microsoft 계정 또는 Azure에서 구성된 엔터프라이즈 계정일 수 있습니다. [HoloLens(1세대)](hololens1-start.md) 설정 또는 [HoloLens 2](hololens2-start.md)참조하세요.

다른 디바이스의 Windows와 마찬가지로 설치 중에 로그인하면 디바이스에 사용자 프로필이 생성됩니다. 사용자 프로필은 앱과 데이터를 저장합니다. 또한 동일한 계정은 Windows 계정 관리자 API를 사용하여 Edge 또는 Microsoft Store 같은 앱에 Single Sign-on을 제공합니다.  

엔터프라이즈 또는 조직 계정을 사용하여 HoloLens에 로그인하는 경우 HoloLens는 조직의 IT 인프라에 등록됩니다. 이 등록을 통해 IT 관리자는 그룹 정책을 HoloLens에 보내도록 MDM(모바일 장치 관리)을 구성할 수 있습니다.

기본적으로 다른 Windows 10 디바이스의 경우 HoloLens가 다시 시작되거나 대기에서 다시 시작될 때 다시 로그인해야 합니다. 설정 앱을 사용하여 이 동작을 변경하거나 그룹 정책을 통해 동작을 제어할 수 있습니다.

### <a name="linked-accounts"></a>연결된 계정

데스크톱 버전의 Windows와 마찬가지로 추가 웹 계정 자격 증명을 HoloLens 계정에 연결할 수 있습니다. 이러한 연결을 사용하면 앱 간 또는 앱 내에서(예: 스토어) 리소스에 쉽게 액세스하거나 개인 및 업무용 리소스에 대한 액세스를 결합할 수 있습니다. 계정을 디바이스에 연결한 후에는 각 앱에 개별적으로 로그인할 필요가 없도록 디바이스를 앱에 사용할 수 있는 권한을 부여할 수 있습니다.

연결 계정은 이미지 또는 다운로드와 같이 디바이스에서 만든 사용자 데이터를 분리하지 않습니다.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>다중 사용자 지원 설정(Azure AD에만 해당)

HoloLens는 동일한 Azure AD 테넌트에서 여러 사용자를 지원합니다. 이 기능을 사용하려면 조직에 속한 계정을 사용하여 디바이스를 설정해야 합니다. 이후에 동일한 테넌트에서 다른 사용자가 로그인 화면에서 또는 시작 패널에서 사용자 타일을 탭하여 디바이스에 로그인할 수 있습니다. 한 번에 한 명의 사용자만 로그인할 수 있습니다. 사용자가 로그인하면 HoloLens는 이전 사용자를 로그인합니다. Azure AD 조인의 경우를 제외하고 디바이스의 첫 번째 사용자는 디바이스 소유자로 간주됩니다. [디바이스 소유자에 대해 자세히 알아보세요.](security-adminless-os.md#device-owner)

모든 사용자는 디바이스에 설치된 앱을 사용할 수 있습니다. 그러나 각 사용자에게는 고유한 앱 데이터와 기본 설정이 있습니다. 디바이스에서 앱을 제거하면 모든 사용자에 대해 제거됩니다.  

Azure AD 계정으로 설정된 디바이스는 Microsoft 계정으로 디바이스에 로그인할 수 없습니다. 사용되는 모든 후속 계정은 디바이스와 동일한 테넌트에서 Azure AD 계정이어야 합니다. Microsoft 계정을 지원하는 [앱(예: Microsoft Store)에](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) 여전히 로그인할 수 있습니다. 디바이스에 로그인하기 위해 Azure AD 계정 사용에서 Microsoft 계정으로 변경하려면 [디바이스를 다시 사용해야](hololens-recovery.md#clean-reflash-the-device)합니다.

> [!NOTE]
> **HoloLens(1세대)는** Windows Holographic for Business [의](hololens-upgrade-enterprise.md)일부로 [Windows 10 2018년 4월 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 여러 Azure AD 사용자를 지원하기 시작했습니다.

### <a name="multiple-users-listed-on-sign-in-screen"></a>로그인 화면에 나열된 여러 사용자

이전에는 로그인 화면에 가장 최근에 로그인한 사용자와 '다른 사용자' 진입점만 표시했습니다. 여러 사용자가 디바이스에 로그인한 경우 충분하지 않다는 고객의 피드백을 받았습니다. 사용자 이름 등을 다시 입력해야 했습니다.

[Windows Holographic 버전 21H1에](hololens-release-notes.md#windows-holographic-version-21h1)도입된 PIN 항목 필드의 오른쪽에 있는 **다른 사용자를** 선택하면 로그인 화면에 이전에 디바이스에 로그인한 사용자가 여러 명 표시됩니다. 이렇게 하면 사용자가 자신의 사용자 프로필을 선택한 다음 Windows Hello 자격 증명을 사용하여 로그인할 수 있습니다. **계정 추가** 단추를 통해 이 다른 사용자 페이지에서 새 사용자를 디바이스에 추가할 수도 있습니다.

다른 사용자 메뉴에서 다른 사용자 단추가 디바이스에 마지막으로 로그인한 사용자를 표시합니다. 이 사용자의 로그인 화면으로 돌아가려면 이 단추를 선택합니다.

![로그인 화면 기본값](./images/multiusers1.jpg)

<br>

![로그인 화면 다른 사용자](./images/multiusers2.jpg)

## <a name="removing-users"></a>사용자 제거

**설정** 계정 기타 사용자 로 가서 디바이스에서 사용자를 제거할 수  >  **있습니다.**  >   또한 이 작업은 디바이스에서 해당 사용자의 앱 데이터를 모두 제거하여 공간을 회수합니다.  

## <a name="using-single-sign-on-within-an-app"></a>앱 내에서 Single Sign-on 사용

앱 개발자는 다른 Windows 디바이스에서와 마찬가지로 Windows 계정 관리자 [API를](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)사용하여 HoloLens에서 연결된 ID를 활용할 수 있습니다. 이러한 API에 대한 일부 코드 샘플은 GitHub: [웹 계정 관리 샘플](https://go.microsoft.com/fwlink/p/?LinkId=620621)에서 사용할 수 있습니다.

계정 정보에 대한 사용자 동의 요청, 2단계 인증 등 발생할 수 있는 모든 계정 인터럽트는 앱이 인증 토큰을 요청할 때 처리되어야 합니다.

앱에 이전에 연결되지 않은 특정 계정 유형이 필요한 경우 앱에서 사용자에게 계정을 추가하라는 메시지를 시스템에 요청할 수 있습니다. 이 요청은 계정 설정 창을 트리거하여 앱의 모달 자식으로 시작합니다. 2D 앱의 경우 이 창은 앱의 가운데에 직접 렌더링됩니다. Unity 앱의 경우 이 요청은 사용자를 홀로그램 앱에서 잠시 벗어나 자식 창을 렌더링합니다. 이 창에서 명령 및 작업을 사용자 지정하는 자세한 내용은 [WebAccountCommand 클래스 를 참조하세요.](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>엔터프라이즈 및 기타 인증

앱에서 NTLM, Basic 또는 Kerberos와 같은 다른 유형의 인증을 사용하는 경우 [Windows 자격 증명 UI를](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 사용하여 사용자의 자격 증명을 수집, 처리 및 저장할 수 있습니다. 이러한 자격 증명을 수집하기 위한 사용자 환경은 다른 클라우드 기반 계정 인터럽트와 매우 유사하며, 2D 앱 위에 자식 앱으로 표시되거나 UI를 표시하기 위해 Unity 앱을 잠시 일시 중단합니다.

## <a name="deprecated-apis"></a>사용되지 않는 API

HoloLens용 개발이 Desktop용 개발과 다른 한 가지 방법은 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API가 완전히 지원되지 않는다는 것입니다. 기본 계정이 양호한 경우 API가 토큰을 반환하지만 이 문서에 설명된 것과 같은 인터럽트는 사용자에 대한 UI를 표시하지 않으며 계정을 올바르게 인증하지 못합니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>비즈니스용 Windows Hello HoloLens(1세대)에서 지원하나요?

비즈니스용 Windows Hello(로그인에 PIN 사용을 지원함)는 HoloLens(1세대)에 대해 지원됩니다. HoloLens에서 비즈니스용 Windows Hello PIN 로그인을 허용 하려면:

1. HoloLens 장치는 [MDM에서 관리](hololens-enroll-mdm.md)되어야 합니다.
1. 장치에 비즈니스용 Windows Hello를 사용 하도록 설정 해야 합니다. [Microsoft Intune에 대 한 지침을 참조 하세요.](https://docs.microsoft.com/intune/windows-hello)
1. HoloLens에서 사용자는 **설정**  >  **로그인 옵션**  >  **pin 추가** 를 사용 하 여 pin을 설정할 수 있습니다.

> [!NOTE]
> Microsoft 계정를 사용 하 여 로그인 하는 사용자는 **설정**  >  **로그인 옵션**  >  **pin 추가** 에서 pin을 설정할 수도 있습니다. 이 PIN은 [비즈니스용 Windows hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)가 아닌 [windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)와 연결 되어 있습니다.

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>HoloLens에서 Iri 생체 인식 인증을 구현 하는 방법 2?

HoloLens 2는 Iri 인증을 지원 합니다. Iri는 Windows Hello 기술을 기반으로 하며 Azure Active Directory 및 Microsoft 계정 모두에서 사용 하도록 지원 됩니다. Iri는 다른 Windows Hello 기술과 동일한 방식으로 구현 되며 1/10만의 생체 인식 보안을 달성 합니다.

자세한 내용은 [Windows Hello에 대 한 생체 인식 요구 사항 및 사양](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) 을 참조 하세요. 비즈니스용 [windows hello 및](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) [windows hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)에 대해 자세히 알아보세요. 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>계정 유형은 로그인 동작에 어떤 영향을 미칩니까?

로그인에 정책을 적용 하면 정책이 항상 적용 됩니다. 로그인에 대 한 정책이 적용 되지 않은 경우 각 계정 유형에 대 한 기본 동작은 다음과 같습니다.

- **AZURE AD**: 기본적으로 인증을 요청 하 고, 더 이상 인증을 요구 하지 않도록 **설정** 으로 구성할 수 있습니다.
- **Microsoft 계정**: 잠금 동작은 자동 잠금 해제를 허용 하는 것과 다르지만 다시 부팅 하려면 로그인 인증이 필요 합니다.
- **로컬 계정**: 항상 암호 형식으로 인증을 요청 하며 **설정** 에서 구성할 수 없습니다.

> [!NOTE]
> 비활성 타이머는 현재 지원 되지 않습니다. 즉, 장치가 대기 모드로 전환 될 때만 **AllowIdleReturnWithoutPassword** 정책이 적용 됩니다.

## <a name="additional-resources"></a>추가 리소스

사용자 id 보호 및 인증에 대 한 자세한 내용은 [Windows 10 보안 및 id 설명서](https://docs.microsoft.com/windows/security/identity-protection/)를 참조 하세요.

하이브리드 id 인프라를 설정 하는 방법에 대 한 자세한 내용은 [Azure 하이브리드 id 설명서](https://docs.microsoft.com/azure/active-directory/hybrid/)를 참조 하세요.
