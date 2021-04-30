---
title: HoloLens의 사용자 id 및 로그인 관리
description: 사용자 id, 다중 사용자 지원, 보안, 엔터프라이즈 인증 및 HoloLens 장치에 대 한 로그인을 관리 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309885"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens의 사용자 id 및 로그인 관리

> [!NOTE]
> 이 문서는 IT 전문가 및 기술 매니아를 위한 기술 참조입니다. HoloLens를 설정 하는 방법에 대 한 자세한 내용은 "[Hololens 설정 (첫 번째 gen)](hololens1-start.md)" 또는 "[hololens 설정 2](hololens2-start.md)" (영문)를 참조 하세요.

다른 Windows 장치와 마찬가지로 HoloLens는 항상 사용자 컨텍스트에서 작동 합니다. 항상 사용자 id가 있습니다. HoloLens는 다른 Windows 10 장치에서 수행 하는 것과 거의 동일한 방식으로 id를 처리 합니다. 이 문서는 HoloLens에서 id에 대 한 심층 참조 이며, HoloLens가 다른 Windows 10 장치와 어떻게 다른 지에 대해 집중적으로 설명 합니다.

HoloLens는 여러 종류의 사용자 id를 지원 합니다. 하나 이상의 사용자 계정을 사용 하 여 로그인 할 수 있습니다. 다음은 HoloLens의 id 유형 및 인증 옵션에 대 한 개요입니다.

| ID 형식 | 장치당 계정 | 인증 옵션 |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD Premium 필요) | 64 | <ul><li>Azure 웹 자격 증명 공급자</li><li>Azure Authenticator 앱</li><li>생체 인식 (Iri) &ndash; HoloLens 2만 해당<sup>1</sup> </li><li>Hololens &ndash; (첫 번째 gen)의 고정 옵션 (hololens 2에 필요)</li><li>암호</li></ul> |
| [Microsoft 계정 (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>생체 인식 (Iri) &ndash; HoloLens 2만 해당</li><li>Hololens &ndash; (첫 번째 gen)의 고정 옵션 (hololens 2에 필요)</li><li>암호</li></ul> |
| [로컬 계정](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 암호 |

클라우드 연결 계정 (Azure AD 및 MSA)은 Azure 서비스를 사용할 수 있기 때문에 더 많은 기능을 제공 합니다.  

> [!NOTE]
> 1-HoloLens 2 장치는 최대 64 개의 Azure AD 계정을 지원할 수 있지만 이러한 계정 중 10 개만 Iri 인증에 등록할 수 있습니다. 이는 [비즈니스용 Windows Hello에 대 한 다른 생체 인식 인증 옵션과](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)맞춰져 있습니다.

## <a name="setting-up-users"></a>사용자 설정

새 사용자를 설정 하는 가장 일반적인 방법은 HoloLens OOBE (첫 실행 경험)를 사용 하는 것입니다. 설치 하는 동안 장치에서 사용할 계정을 사용 하 여 사용자에 게 로그인 하 라는 메시지가 표시 됩니다. 이 계정은 Azure에서 구성 된 소비자 Microsoft 계정 또는 엔터프라이즈 계정일 수 있습니다. [Hololens 설정 (첫 번째 gen)](hololens1-start.md) 또는 [hololens 2](hololens2-start.md)를 참조 하세요.

다른 장치의 Windows와 마찬가지로 설치 중에 로그인 하면 장치에 사용자 프로필이 생성 됩니다. 사용자 프로필은 앱과 데이터를 저장 합니다. 또한 동일한 계정은 Windows 계정 관리자 Api를 사용 하 여 Edge 또는 Skype와 같은 앱에 대 한 Single Sign-on을 제공 합니다.  

엔터프라이즈 또는 조직 계정을 사용 하 여 HoloLens에 로그인 하는 경우 HoloLens는 조직의 IT 인프라에 등록 합니다. 이 등록을 통해 IT 관리자는 MDM (모바일 장치 관리)을 구성 하 여 그룹 정책을 HoloLens로 보낼 수 있습니다.

기본적으로 다른 Windows 10 장치에 대해, HoloLens를 다시 시작 하거나 대기에서 다시 시작할 때 다시 로그인 해야 합니다. 설정 앱을 사용 하 여이 동작을 변경 하거나 그룹 정책에 따라 동작을 제어할 수 있습니다.

### <a name="linked-accounts"></a>연결된 계정

Windows 데스크톱 버전에서와 같이 추가 웹 계정 자격 증명을 HoloLens 계정에 연결할 수 있습니다. 이러한 연결을 통해 스토어와 같은 앱 또는 앱 내에서 리소스에 보다 쉽게 액세스 하거나 개인 및 회사 리소스에 대 한 액세스를 결합할 수 있습니다. 계정을 장치에 연결한 후에는 각 앱에 개별적으로 로그인 할 필요가 없도록 장치를 앱에 사용할 수 있는 권한을 부여할 수 있습니다.

계정을 연결 해도 장치에서 만든 사용자 데이터 (예: 이미지 또는 다운로드)는 분리 되지 않습니다.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>다중 사용자 지원 설정 (Azure AD에만 해당)

HoloLens는 동일한 Azure AD 테 넌 트의 여러 사용자를 지원 합니다. 이 기능을 사용 하려면 장치를 설정 하기 위해 조직에 속해 있는 계정을 사용 해야 합니다. 이후에는 동일한 테 넌 트의 다른 사용자가 로그인 화면에서 또는 시작 패널에서 사용자 타일을 눌러 장치에 로그인 할 수 있습니다. 한 번에 한 명의 사용자만 로그인 할 수 있습니다. 사용자가 로그인 하면 HoloLens에서 이전 사용자를 로그 아웃 합니다. 장치의 첫 번째 사용자는 Azure AD 조인의 경우를 제외 하 고 장치 소유자에 게는 장치 소유자 [에 대 한 자세한](security-adminless-os.md#device-owner)정보를 알려 주는 것으로 간주 됩니다.

모든 사용자는 장치에 설치 된 앱을 사용할 수 있습니다. 그러나 각 사용자에 게는 고유한 앱 데이터 및 기본 설정이 있습니다. 장치에서 앱을 제거 하면 모든 사용자가 해당 앱을 제거 합니다.  

Azure AD 계정으로 설정 된 장치는 Microsoft 계정을 사용 하 여 장치에 로그인 할 수 없습니다. 사용 되는 모든 후속 계정은 장치와 동일한 테 넌 트의 Azure AD 계정 이어야 합니다. Microsoft 계정을 지 원하는 앱 (예: Microsoft Store) [으로 Microsoft 계정을 사용 하 여 계속 로그인](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) 할 수 있습니다. 장치에 로그인 하기 위해 Azure AD 계정을 사용 하 여 Microsoft 계정으로 변경 하려면 [장치를 경감 하기 위해](hololens-recovery.md#clean-reflash-the-device)해야 합니다.

> [!NOTE]
> **HoloLens (첫 번째 gen)** 는 windows [Holographic for Business](hololens-upgrade-enterprise.md)의 일부로 [Windows 10 4 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 에서 여러 Azure AD 사용자를 지원 하기 시작 했습니다.

## <a name="removing-users"></a>사용자 제거

**설정**  >  **계정**  >  **다른 사람** 으로 이동 하 여 장치에서 사용자를 제거할 수 있습니다. 또한이 작업은 장치에서 해당 사용자의 앱 데이터를 모두 제거 하 여 공간을 회수 합니다.  

## <a name="using-single-sign-on-within-an-app"></a>앱 내에서 Single Sign-On 사용

앱 개발자는 다른 Windows 장치와 마찬가지로 [Windows 계정 관리자 api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)를 사용 하 여 HoloLens에서 연결 된 id를 활용할 수 있습니다. 이러한 Api에 대 한 일부 코드 샘플은 GitHub: [웹 계정 관리 샘플](https://go.microsoft.com/fwlink/p/?LinkId=620621)에서 사용할 수 있습니다.

계정 정보, 2 단계 인증 등에 대 한 사용자 동의를 요청 하는 등 발생할 수 있는 모든 계정 인터럽트는 앱이 인증 토큰을 요청할 때 처리 되어야 합니다.

앱에 이전에 연결 되지 않은 특정 계정 유형이 필요한 경우 앱에서 사용자에 게 사용자에 게 메시지를 추가 하 라는 메시지를 표시 하도록 요청할 수 있습니다. 이 요청은 계정 설정 창이 앱의 모달 자식으로 시작 되도록 트리거합니다. 2D 앱의 경우이 창은 앱의 중앙에서 직접 렌더링 됩니다. Unity 앱의 경우이 요청은 자식 창을 렌더링 하기 위해 사용자를 holographic 앱에서 간략하게 가져옵니다. 이 창에서 명령 및 동작을 사용자 지정 하는 방법에 대 한 자세한 내용은 [WebAccountCommand 클래스](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)를 참조 하세요.

## <a name="enterprise-and-other-authentication"></a>엔터프라이즈 및 기타 인증

앱에서 NTLM, 기본 또는 Kerberos와 같은 다른 인증 유형을 사용 하는 경우 [Windows 자격 증명 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 를 사용 하 여 사용자의 자격 증명을 수집, 처리 및 저장할 수 있습니다. 이러한 자격 증명을 수집 하는 사용자 환경은 다른 클라우드 기반 계정 인터럽트와 매우 비슷하며, 2D 앱 위에 자식 앱으로 표시 되거나, UI를 표시 하기 위해 Unity 앱을 잠깐 일시 중단 합니다.

## <a name="deprecated-apis"></a>사용되지 않는 API

HoloLens를 개발 하는 방법 중 하나는 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API가 완전히 지원 되지 않는다는 점입니다. 기본 계정이 양호 하면 API는 토큰을 반환 하지만이 문서에 설명 된 것과 같은 인터럽트는 사용자에 대 한 UI를 표시 하지 않고 계정을 올바르게 인증 하지 못합니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens (첫 번째 Gen)에서 비즈니스용 Windows Hello가 지원 되나요?

비즈니스용 Windows Hello (로그인을 위한 PIN 사용 지원)는 HoloLens (첫 번째 Gen)에서 지원 됩니다. HoloLens에서 비즈니스용 Windows Hello PIN 로그인을 허용 하려면:

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
