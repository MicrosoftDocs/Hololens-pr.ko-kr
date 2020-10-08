---
title: HoloLens에 대한 사용자 ID 및 로그인 관리
description: HoloLens에 대 한 사용자 id, 보안 및 로그인을 관리 합니다.
keywords: HoloLens, 사용자, 계정, aad, adfs, microsoft 계정, msa, 자격 증명, 참조
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
ms.openlocfilehash: 5963e71bd6fdd084ca442995b02d99fc40da9d43
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102337"
---
# HoloLens에 대한 사용자 ID 및 로그인 관리

> [!NOTE]
> 이 문서는 IT 전문가와 기술 매니아에 대 한 기술 자료입니다. HoloLens를 설정 하려면 "[Hololens 설정 (첫번째 gen)](hololens1-start.md)" 또는 "[hololens 2 설정](hololens2-start.md)"을 참조 하세요.

다른 Windows 디바이스와 마찬가지로 HoloLens는 항상 사용자 컨텍스트에서 작동 합니다. 항상 사용자 id가 있습니다. HoloLens는 다른 Windows 10 장치와 거의 동일한 방식으로 id를 처리 합니다. 이 문서는 HoloLens의 id에 대 한 자세한 내용 참조와 다른 Windows 10 디바이스와의 HoloLens의 차이에 대해 중점적으로 설명 합니다.

HoloLens는 여러 종류의 사용자 id를 지원 합니다. 하나 이상의 사용자 계정을 사용 하 여 로그인 할 수 있습니다. 다음은 HoloLens의 id 유형과 인증 옵션에 대 한 개요입니다.

| Id 유형 | 장치 당 계정 수 | 인증 옵션 |
| --- | --- | --- |
| [AAD (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure 웹 자격 증명 공급자</li><li>Azure Authenticator 앱</li><li>생체 인식 (Iri) &ndash; HoloLens 2에만 해당</li><li>Hololens &ndash; 2 (1 번 gen)의 고정 옵션</li><li>암호</li></ul> |
| [Microsoft 계정 (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | raid-1 | <ul><li>생체 인식 (Iri) &ndash; HoloLens 2에만 해당</li><li>Hololens &ndash; 2 (1 번 gen)의 고정 옵션</li><li>암호</li></ul> |
| [로컬 계정](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | raid-1 | 암호 |

클라우드 연결 계정 (AAD 및 MSA)은 Azure 서비스를 사용할 수 있기 때문에 더 많은 기능을 제공 합니다.  

## 사용자 설정

새 사용자를 설정 하는 가장 일반적인 방법은 HoloLens OOBE (사용자 환경)를 사용 하는 것입니다. 설치 하는 동안 HoloLens에서 사용자에 게 장치에서 사용할 계정을 사용 하 여 로그인 하 라는 메시지를 표시할 수 있습니다. 이 계정은 소비자 Microsoft 계정 이거나 Azure에서 구성 된 엔터프라이즈 계정일 수 있습니다. [Hololens (첫번째 gen)](hololens1-start.md) 또는 [hololens 2](hololens2-start.md)설정을 참조 하세요.

다른 디바이스의 Windows와 마찬가지로, 설치 중에 로그인 하면 장치에 사용자 프로필이 만들어집니다. 사용자 프로필은 앱과 데이터를 저장 합니다. 또한 동일한 계정에서 Windows 계정 관리자 Api를 사용 하 여 Edge 또는 Skype와 같은 앱에 대 한 Single Sign-on을 제공 합니다.  

엔터프라이즈 또는 조직 계정을 사용 하 여 HoloLens에 로그인 하는 경우, HoloLens는 조직의 IT 인프라에 로그온 합니다. IT 관리자는이 등록을 통해 MDM (모바일 디바이스 관리)을 설정 하 여 HoloLens에 그룹 정책을 보낼 수 있습니다.

다른 Windows 10 디바이스의 경우에는 기본적으로 HoloLens를 다시 시작 하거나 대기 모드에서 다시 시작 하면 로그인 해야 합니다. 설정 앱을 사용 하 여이 동작을 변경 하거나 그룹 정책에 따라 동작을 제어할 수 있습니다.

### 연결 된 계정

데스크톱 버전의 Windows에서와 마찬가지로, 추가 웹 계정 자격 증명을 HoloLens 계정에 연결할 수 있습니다. 이러한 연결을 사용 하면 앱 (예: 스토어)에서 리소스에 액세스 하거나 개인 및 작업 리소스에 대 한 액세스를 결합할 수 있습니다. 장치에 계정을 연결한 후에는 각 앱에 개별적으로 로그인 할 필요가 없도록 디바이스를 앱에 사용할 수 있는 권한을 부여할 수 있습니다.

계정을 연결 해도 이미지 또는 다운로드와 같이 장치에서 만든 사용자 데이터는 분리 되지 않습니다.  

### 다중 사용자 지원 설정 (AAD에만 해당)

HoloLens는 같은 AAD 테 넌 트의 여러 사용자를 지원 합니다. 이 기능을 사용 하려면 장치를 설정 하는 데 조직에 속한 계정을 사용 해야 합니다. 나중에 같은 테 넌 트의 다른 사용자가 로그인 화면에서 장치에 로그인 하거나 시작 패널의 사용자 타일을 탭 할 수 있습니다. 한 번에 한 명의 사용자만 로그인 할 수 있습니다. 사용자가 로그인 하면 HoloLens가 이전 사용자를 로그 아웃 합니다. 장치에서 첫 번째 사용자는 AAD 조인의 경우와 장치 소유자 [에 대 한 자세한](security-adminless-os.md#device-owner)정보를 제외 하 고는 장치 소유자로 간주 됩니다.

모든 사용자가 장치에 설치 된 앱을 사용할 수 있습니다. 그러나 각 사용자에 게는 고유한 앱 데이터와 기본 설정이 있습니다. 장치에서 앱을 제거 하면 모든 사용자가 제거 됩니다.  

AAD 계정으로 설정 된 장치는 Microsoft 계정으로 장치에 로그인 할 수 없습니다. 사용 된 모든 후속 계정은 장치와 동일한 테 넌 트의 AAD 계정 이어야 합니다. Microsoft Store와 같이 지원 되는 [앱에 Microsoft 계정을 사용 하 여 계속 로그인](hololens-identity.md#setting-up-multi-user-support-aad-only) 할 수 있습니다. 장치에 로그인 하기 위해 AAD 계정을 사용 하 여 Microsoft 계정에서 변경 하려면 [장치를 reflash](hololens-recovery.md#clean-reflash-the-device)해야 합니다.

> [!NOTE]
> **HoloLens (첫 번째 gen)** Windows [10 년 4 월 2018 업데이트](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 에서 [비즈니스에 홀로그램](hololens-upgrade-enterprise.md)의 일부로 여러 AAD 사용자를 지원 하기 시작 했습니다.

## 사용자 제거

다른 사용자의 **설정**계정으로 이동해 장치에서 사용자를 제거할 수 있습니다  >  **Accounts**  >  **Other people**. 이 작업은 또한 장치에서 해당 사용자의 앱 데이터를 모두 제거 하 여 공간을 확보 합니다.  

## 앱 내에서 single sign-on 사용

앱 개발자는 다른 Windows 장치에서와 마찬가지로 [Windows 계정 관리자 api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)를 사용 하 여 HoloLens에 연결 된 id를 활용할 수 있습니다. 이러한 Api에 대 한 일부 코드 샘플은 GitHub: [웹 계정 관리 샘플](https://go.microsoft.com/fwlink/p/?LinkId=620621)에서 사용할 수 있습니다.

계정 정보, 2 단계 인증 등의 사용자 동의 요청 등 발생할 수 있는 계정 인터럽트는 앱이 인증 토큰을 요청할 때 처리 되어야 합니다.

앱이 이전에 연결 되지 않은 특정 계정 유형을 필요로 하는 경우 앱은 사용자에 게 추가 여부를 묻는 메시지를 표시 하도록 시스템에 요청할 수 있습니다. 이 요청은 계정 설정 창을 앱의 모달 자식으로 실행 하도록 트리거합니다. 2D 앱의 경우이 창은 앱의 중앙을 따라 직접 렌더링 됩니다. Unity 앱의 경우이 요청은 사용자가 홀로그램 앱에서 자식 창을 렌더링 하는 것을 간략하게 가져옵니다. 이 창에서 명령 및 작업을 사용자 지정 하는 방법에 대 한 자세한 내용은 [WebAccountCommand 클래스](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)를 참조 하세요.

## 엔터프라이즈 및 기타 인증

앱에서 NTLM, 기본 또는 Kerberos와 같은 다른 유형의 인증을 사용 하는 경우 [Windows 자격 증명 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 를 사용 하 여 사용자의 자격 증명을 수집, 처리, 저장할 수 있습니다. 이러한 자격 증명을 수집 하는 사용자 환경은 다른 클라우드 기반 계정 인터럽트와 매우 유사 하며, 2D 앱 위에 하위 앱으로 표시 되거나, UI를 표시 하기 위해 Unity 앱을 잠시 일시 중단 합니다.

## 사용 되지 않는 Api

HoloLens 개발이 데스크톱 개발과는 다른 한 가지 방법은 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API가 완벽 하 게 지원 되지 않는다는 것입니다. 기본 계정이 적절 한 경우 API는 토큰을 반환 하지만이 문서에 설명 된 것과 같은 인터럽트는 사용자에 대 한 UI를 표시 하지 않으며 계정을 올바르게 인증 하지 못합니다.

## 질문과 대답

### HoloLens에서 비즈니스용 Windows Hello가 지원 되나요 (첫번째 Gen)?

HoloLens (1 번 Gen)에 대해 PIN을 사용 하 여 로그인 하는 것을 지 원하는 비즈니스용 Windows Hello가 지원 됩니다. HoloLens에서 비즈니스용 Windows Hello PIN 로그인을 허용 하려면 다음을 수행 합니다.

1. HoloLens 장치는 MDM을 [통해 관리](hololens-enroll-mdm.md)해야 합니다.
1. 장치에 대해 비즈니스용 Windows Hello를 사용 하도록 설정 해야 합니다. ([Microsoft Intune에 대 한 지침을 참조 하세요.](https://docs.microsoft.com/intune/windows-hello))
1. HoloLens에서는 사용자가 **설정**  >  **로그인 옵션**  >  을 사용 하 여 pin을 설정 하는**pin을 추가할** 수 있습니다.

> [!NOTE]
> Microsoft 계정을 사용 하 여 로그인 하는 사용자도 **설정**로그인 옵션에서 pin을 설정할 수 있습니다  >  **Sign-in Options**  >  .**pin 추가**를 선택 합니다. 이 PIN은 [비즈니스용 Windows hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)가 아니라 [windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)와 연결 되어 있습니다.

### HoloLens 2에서 Iri 생체 인식 인증을 구현 하는 방법은 무엇 인가요?

HoloLens 2는 조리개 인증을 지원 합니다. Iri는 Windows Hello 기술을 기반으로 하며 Azure Active Directory와 Microsoft 계정 모두에서 사용할 수 있습니다. Iri는 다른 Windows Hello 기술과 같은 방식으로 구현 되며 1/10만 개의 생체 인식 보안을 달성 합니다.

Windows Hello에 대 한 생체 인식 요구 사항 및 사양에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)를 참고 하세요. [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 및 [비즈니스용 windows hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)에 대해 자세히 알아보세요. 

### 계정 유형이 로그인 동작에 미치는 영향

로그인에 대한 정책을 적용하면 정책이 항상 준수됩니다. 로그인에 대 한 정책이 적용 되지 않은 경우 각 계정 유형의 기본 동작은 다음과 같습니다.

- **AZURE AD**: 기본적으로 인증을 요청 하 고 **설정** 에서 더 이상 인증을 요청 하지 않도록 구성할 수 있습니다.
- **Microsoft 계정**: 잠금 동작은 자동 잠금을 해제할 수 있지만, 다시 부팅 하려면 로그인 인증이 여전히 필요 합니다.
- **로컬 계정**: 항상 암호 형식으로 인증을 요청 하며 **설정** 에서 구성할 수 없습니다.

> [!NOTE]
> 비활성 타이머는 현재 지원 되지 않으며, 이것은 장치가 대기 모드로 전환 될 때만 **AllowIdleReturnWithoutPassword** 정책이 적용 됨을 의미 합니다.

## 추가 리소스

자세한 내용은 [Windows 10 보안 및 id 설명서](https://docs.microsoft.com/windows/security/identity-protection/)의 사용자 id 보호 및 인증에 대해 자세히 읽어 보세요.

하이브리드 id 인프라 설정에 대 한 자세한 내용은 [Azure 하이브리드 id 설명서](https://docs.microsoft.com/azure/active-directory/hybrid/)를 참조 하세요.
