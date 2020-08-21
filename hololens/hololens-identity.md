---
title: HoloLens에 대한 사용자 ID 및 로그인 관리
description: HoloLens에 대한 사용자 ID, 보안 및 로그인을 관리합니다.
keywords: HoloLens, 사용자, 계정, adfs, microsoft 계정, msa, 자격 증명, 참조
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 1/6/2020
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
ms.openlocfilehash: 17d55d8cd5540c9beaf4b7348688c362b079f5da
ms.sourcegitcommit: ab9e70e68d546cc6965e1569e5d914995fa508da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "10955450"
---
# HoloLens에 대한 사용자 ID 및 로그인 관리

> [!NOTE]
> 이 문서는 IT 전문가 및 기술 지원에 대한 기술 참조입니다. HoloLens가 설정 지침을 찾고 있는 경우 "[HoloLens(1세대)](hololens1-start.md)" 설정을 보거나[HoloLens 2 "설정"을 설정하세요.](hololens2-start.md)

다른 Windows 디바이스와 마치 HoloLens는 항상 사용자 상황에서 운영합니다. 항상 사용자 ID가 있습니다. HoloLens는 다른 Windows 10 디바이스와 거의 동일한 방법으로 ID를 인정합니다. 이 문서는 HoloLens의 ID에 대한 대략적인 참조이며 HoloLens가 다른 Windows 10 디바이스와 어떻게 다른지 에집중합니다.

HoloLens는 여러 종종 사용자 ID를 지원합니다. 하나 이상의 사용자 계정을 사용하여 로그인할 수 있습니다. 다음은 HoloLens에서 ID 유형과 인증 옵션의 개요입니다.

| ID 유형 | 장치당 계정 | 인증 옵션 |
| --- | --- | --- |
| [AAD(Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure 웹 자격 증명 공급자</li><li>Azure Authenticator 앱</li><li>생자 메트릭(아르드) &ndash; HoloLens 2에만 해당</li><li>&ndash;HoloLens의 PIN 선택 사항(1세대), HoloLens 2가 필요</li><li>암호</li></ul> |
| [Microsoft 계정(MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>생자 메트릭(아르드) &ndash; HoloLens 2에만 해당</li><li>&ndash;HoloLens의 PIN 선택 사항(1세대), HoloLens 2가 필요</li><li>암호</li></ul> |
| [로컬 계정](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 암호 |

AAD 및 MSA(클라우드 연결 계정)에서는 Azure 서비스를 사용할 수 있기 때문에 더 많은 기능을 제공합니다.  

## 사용자 설정

새 사용자를 설정하는 가장 일반적인 방법은 OOBE(제대로 실행되지 않은 경험) 중에 발생합니다. 설정하는 동안 HoloLens는 장치에서 사용할 계정을 사용하여 로그인하라는 메시지를 표시합니다. 이 계정은 Microsoft 계정이나 Azure에서 구성한 기업 계정일 수 있습니다. [HoloLens(1세대) 또는](hololens1-start.md) [HoloLens 2 설정을 참조하세요.](hololens2-start.md)

설정하는 동안 다른 장치의 Windows와 마음에 로그인하는 동안 장치에 사용자 프로필이 만들어집니다. 사용자 프로필에 앱과 데이터를 저장합니다. 또한 동일한 계정에서 Windows 계정 관리자 A5를 사용하여 Edge 또는 Skype 등의 앱에 대해 Single Sign-On을 제공합니다.  

회사 또는 조직 계정을 사용하여 HoloLens에 로그인하는 경우 HoloLens는 조직의 IT 인프라에 등록합니다. 이 등록을 통해 IT 관리자는 MDM(모바일 장치 관리)을 구성하여 그룹 정책을 HoloLens에 보낼 수 있습니다.

기본적으로 다른 Windows 10 장치에서는 HoloLens가 대기 모드를 다시 시작하거나 다시 시작할 때 다시 로그인해야 합니다. 설정 앱을 사용하여 이 동작을 변경할 수도 있고, 그룹 정책에 의해 제어될 수 있습니다.

### 연결된 계정

데스크톱 버전의 Windows에서와 마치 면서 추가 웹 계정 자격 증명을 HoloLens 계정에 연결할 수 있습니다. 이러한 연결을 사용하면 전부 또는 앱(예: 스토어)에 있는 리소스에 손쉽게 액세스하거나 개인 및 작업 리소스에 액세스할 수 있습니다. 디바이스에 계정을 연결한 후 각 앱에 개별적으로 로그인할 필요가 없도록 앱에서 디바이스를 사용할 권한을 부여할 수 있습니다.

계정을 연결해도 이미지, 다운로드 등 장치에서 만든 사용자 데이터는 별도로 구분되지 않습니다.  

### 다중 사용자 지원 설정(AAD에만 해당)

HoloLens는 동일한 AAD 테넌트에서 여러 사용자를 지원합니다. 이 기능을 사용하려면 조직에 속한 계정을 사용하여 장치를 설정해야 합니다. 이후에 다른 테넌트의 다른 사용자는 로그인 화면에서 장치에 로그인하거나 시작 패널에 있는 사용자 타일을 탭하여 장치에 로그인할 수 있습니다. 한 번에 한 사용자만 로그인할 수 있습니다. 사용자가 로그인하면 HoloLens가 이전 사용자에서 로그아웃합니다.  

모든 사용자가 장치에 설치된 앱을 사용할 수 있습니다. 그러나 각 사용자에게는 고유한 앱 데이터와 기본 설정이 있습니다. 장치에서 앱을 제거하면 모든 사용자에 대한 앱이 제거됩니다.  

AAD 계정으로 설정된 디바이스는 Microsoft 계정을 사용하여 디바이스에 로그인할 수 없습니다. 사용되는 이후 모든 계정은 장치와 동일한 테넌트의 AAD 계정이어야 합니다. 아직 Microsoft [계정을 사용하여 이를 지원하는](hololens-identity.md#setting-up-multi-user-support-aad-only) 앱(예: Microsoft 스토어)에 로그인할 수 있습니다. AAD 계정을 사용하여 디바이스에 로그인하는 것으로 변경하려면 장치를 [재배치해야 합니다.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> 비즈니스용 Windows **Holographic의 일부로** [Windows 10 2018년](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 4월 업데이트에서 여러 AAD [사용자를 지원하고 있습니다.](hololens-upgrade-enterprise.md)

## 사용자 제거

다른 사용자의 설정으로 이동하여 **사용자를 장치에서**  >  **제거할**  >  **수 있습니다.** 또한 이 작업을 수행하면 장치에서 해당 사용자의 앱 데이터를 모두 제거하여 공간이 소모됩니다.  

## 앱 내에서 Single Sign-On 사용

앱 개발자는 다른 Windows 장치에서와 마찬가지로 Windows 계정 [관리자 AP를 사용하여](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)HoloLens에서 연결된 ID를 활용할 수 있습니다. 이러한 AD에 대한 일부 코드 샘플은 GitHub: 웹 계정 [관리 샘플에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

계정 정보에 대한 사용자 동의 요청, 2단계 인증 등과 같은 발생할 수 있는 모든 계정 중단은 앱에서 인증 토큰을 요청할 때 수행되어야 합니다.

앱에서 이전에 연결되지 않은 특정 계정 유형을 요구하는 경우, 앱에서 사용자에게 계정을 추가하라는 메시지를 표시할지 를 앱에서 사용자에게 요청할 수 있습니다. 이 요청을 요청하면 계정 설정 창이 앱의 모듈 자식으로 실행됩니다. 2D 앱의 경우 이 창은 앱 중간에 직접 렌더링됩니다. Unity 앱의 경우 이 요청은 매우 사용자가 간단하게 자식 창을 렌더링해 드립니다. 이 창에서 명령과 작업을 사용자 지정하는 방법에 대한 자세한 내용은 [WebAccountCommand 클래스를 참조하세요.](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## 엔터프라이즈 및 기타 인증

앱에서 NTLM, Basic 또는 Kerberos와 같은 다른 유형의 인증을 사용하는 경우 Windows 자격 증명 [UI를](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 사용하여 사용자 자격 증명을 수집, 처리 및 저장할 수 있습니다. 이러한 자격 증명을 수집하는 사용자 환경은 다른 클라우드 기반 계정 중단과 매우 유사하며, 2D 앱의 맨 위에서 자식 앱으로 표시하거나 UI를 표시하는 Unity 앱을 일시 중단합니다.

## 사용되지 않습니다 AIS

HoloLens를 개발할 때 는 데스크톱용 개발과는 다르게 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API를 완전히 지원하지 않다는 것입니다. 기본 계정이 적절한 상태이지만 이 문서에 설명된 것과 같은 중단은 사용자가 계정을 제대로 인증하지 않으며 계정을 제대로 인증하지 않습니다.

## 질문과 대답

### Is Windows Hello for Business is Supported on HoloLens (1st en)?

비즈니스용 Windows Hello(로그인하는 PIN을 사용하여 지원하는 기능)가 HoloLens(1세대)에 지원됩니다. HoloLens에서 비즈니스용 Windows Hello PIN 로그인을 허용하려면:

1. HoloLens 장치는 [MDM에서 관리해야 합니다.](hololens-enroll-mdm.md)
1. 장치에 대해 비즈니스용 Windows Hello를 사용하도록 설정해야 합니다. (Microsoft[Intune에 대한 지침을 참조하세요.)](https://docs.microsoft.com/intune/windows-hello)
1. 그런 다음 사용자가 설정 로그인 옵션 **Settings**  >  **Sign-in Options**  >  **추가 PIN을 사용하여 PIN을** 설정할 수 있습니다.

> [!NOTE]
> Microsoft 계정을 사용하여 로그인한 사용자는 설정 로그인 옵션 **Settings**추가 PIN을  >  **설정할**  >  **수도 있습니다.** 이 PIN은 비즈니스용 [Windows Hello가](https://support.microsoft.com/help/17215/windows-10-what-is-hello)아닌 [Windows Hello와 연결됩니다.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### HoloLens 2에서 생기게 구현하기 위한 생류상 인증은 어떻게 나요?

HoloLens 2는 Iris 인증을 지원합니다. Iris는 Windows Hello 기술을 기반으로 하며 Azure Active Directory 및 Microsoft 계정 모두에서 사용할 수 있습니다. Iris는 다른 Windows Hello 기술과 동일한 방식으로 구현되며, 200K의 생체 인해 생체 인원을 1/100K의 가져오는 방식으로 구현됩니다.

여기에서 Windows Hello의 생체 인기 요구 사항 [here](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)및 사양에 대해 자세히 알아보세요. [Windows Hello 및 비즈니스용 Windows Hello에](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) [대한 자세한 정보](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### 계정 유형이 로그인 동작에 미는 영향

로그인에 대한 정책을 적용하면 정책이 항상 준수됩니다. 로그인에 대한 정책이 적용되지 않을 경우 각 계정 유형에 대한 기본 동작입니다.

- **Azure AD:** 기본적으로 인증을 요청하며 설정으로 구성 가능한 경우 인증 **Settings** 요청이 더 이상 인증을 요청하지 않습니다.
- **Microsoft 계정:** 잠금 해제는 자동 잠금 해제를 허용하지만 다시 부격 시 로그인이 계속 필요합니다.
- **로컬**계정: 항상 설정에서 구성할 수 없고 암호 형식으로 인증하도록 **요청합니다.**

> [!NOTE]
> 비존 타이더는 현재 지원되지 않습니다. 즉, **AllowIdleReturnWithoutPassword** 정책은 장치가 StandBy로 이동할 때만 적용됩니다.

## 추가 리소스

Windows 10 보안 및 ID 문서의 사용자 ID 보호 및 인증에 [대한 자세한 내용을 읽어보세요.](https://docs.microsoft.com/windows/security/identity-protection/)

Azure 하이브리드 ID 문서만 보정하고 하이브리드 ID 인프라를 [설정하는 방법에 대해 자세히 알아보세요.](https://docs.microsoft.com/azure/active-directory/hybrid/)
