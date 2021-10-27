---
title: HoloLens를 키오스크로 설정
description: HoloLens 장치에서 앱을 잠그기 위해 키오스크 구성을 설정 하 고 사용 하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e8f269a3793a5e61eb3eb4b88084a5e4af375ffa
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351722"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens를 키오스크로 설정

## <a name="what-is-kiosk-mode"></a>키오스크 모드는 무엇입니까?

키오스크 모드는 사용자가 HoloLens에 로그인 할 때 시작 메뉴에 표시 되는 응용 프로그램을 제어할 수 있는 기능입니다. 지원 되는 시나리오는 다음 두 가지입니다.

1. **단일 앱 키오스크 모드** – 시작 메뉴가 표시 되지 않으며 사용자가 로그인 할 때 단일 앱이 자동으로 시작 됩니다. <br> *예제 사용*: Dynamics 365 Guides 앱만 실행 하는 장치입니다.
2. **여러 앱 키오스크 모드** – 시작 메뉴 사용자가 로그인 할 때 키오스크 구성에서 지정 된 응용 프로그램만 표시 됩니다. 원하는 경우 앱을 자동으로 시작 하도록 선택할 수 있습니다. <br> *예제 사용*: 시작 메뉴에 스토어 앱, 피드백 허브 및 설정 앱만 표시 하는 장치입니다.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>사용자가 로그인 할 때 키오스크 모드 환경 설명

다음 표에서는 다양 한 키오스크 모드의 기능 기능을 보여 줍니다.

| &nbsp; |시작 메뉴 |빠른 작업 메뉴 |카메라 및 비디오 |Miracast |Cortana |기본 제공 음성 명령 |
| --- | --- | --- | --- | --- | --- | --- |
|단일 앱 키오스크 |사용 안 함 |사용 안 함 |사용 안 함 |사용 안 함   |사용 안 함 |사용 |
|다중 앱 키오스크 |사용 |사용  |있게  |있게 |있게   |사용  |

\*비활성화 된 기능을 사용 하도록 설정 하는 방법 또는 음성 명령이 사용 하지 않도록 설정 된 기능과 상호 작용 하는 방법에 대 한 자세한 내용은 [앱의 aumids HoloLens](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)를 참조 Cortana.

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>키오스크 모드를 구성 하기 전의 주요 주요 고려 사항

1. 환경에서 HoloLens에 로그인 하는 사용자 계정 종류를 결정 합니다.-HoloLens Azure Active Directory (AAD) 계정, MSA (Microsoft 계정) 및 로컬 계정을 지원 합니다. 또한 게스트/방문자 라고 하는 임시로 만든 계정도 지원 됩니다 (AAD 연결 장치에만 해당). 자세한 내용은 [사용자 Id 관리 및 HoloLens에 대 한 로그인을](hololens-identity.md)확인 하세요.
2. 모든 사람, 단일 사용자, 특정 사용자 또는 AAD 그룹의 멤버인 사용자 인지 여부에 관계 없이 키오스크 모드 환경의 대상을 결정 합니다.
3. 여러 앱 키오스크 모드의 경우 시작 메뉴에 표시할 응용 프로그램을 결정 합니다. 각 응용 프로그램에 대해 해당 [응용 프로그램 사용자 모델 ID (AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) 가 필요 합니다.
4. 런타임 프로 비전 패키지나 MDM (모바일 장치 관리) 서버를 통해 HoloLens에 키오스크 모드가 적용 되는지 확인 합니다.

## <a name="security-considerations"></a>보안 고려 사항

키오스크 모드는 보안 방법으로 간주 해서는 안 되며 사용자 로그인에 대 한 시작 환경을 제어 하는 수단으로 사용 해야 합니다. 특정 보안 관련 요구 사항이 있는 경우 아래에 설명 된 옵션과 함께 키오스크 모드 환경을 결합할 수 있습니다.

- 설정 앱이 키오스크 모드로 표시 되도록 구성 되 고 설정 앱에 표시 되는 페이지를 제어 하려면 [페이지 설정 표시 유형](settings-uri-list.md) 을 참조 하세요.
- 특정 응용 프로그램 등에 대 한 특정 하드웨어 기능 (예: 카메라, Bluetooth 등)에 대 한 액세스를 제어 하려는 경우 [HoloLens 2-Windows 클라이언트 관리에서 지 원하는 정책 CSP의](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)정책을 참조 하세요. [일반적인 장치 제한 사항을](hololens-common-device-restrictions.md) 검토 하 여 아이디어를 확인할 수 있습니다.
- 키오스크 모드는 다른 앱을 시작 하는 앱 (키오스크 환경의 일부로 구성 됨)을 차단 하지 않습니다. HoloLens에서 특정 앱/프로세스의 시작을 완전히 차단 하려면 [Microsoft Intune의 HoloLens 2 장치에서 응용 프로그램 제어 사용 Windows Defender](/mem/intune/configuration/custom-profile-hololens) 을 참조 하세요.

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>HoloLens 키오스크 모드에 대 한 주요 기술 고려 사항

런타임 프로 비전 패키지를 사용 하거나 수동으로 키오스크 구성을 만들 계획인 경우에만 적용 됩니다. 키오스크 모드 구성은 XML을 기반으로 하는 계층 구조를 사용 합니다.

- 할당 된 액세스 프로필은 키오스크 모드의 시작 메뉴에 표시 되는 응용 프로그램을 정의 합니다. 나중에 참조할 수 있는 동일한 XML 구조에서 여러 프로필을 정의할 수 있습니다.
- 할당 된 액세스 구성은 해당 프로필의 프로필 및 대상 사용자 (예: 특정 사용자 또는 AAD 그룹 또는 방문자 등)를 참조 합니다. 사용 시나리오의 복잡성에 따라 동일한 XML 구조로 여러 구성을 정의할 수 있습니다 (지원 되는 시나리오 섹션 참조).
- 자세한 내용은 [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp)를 참조 하세요.

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Id 유형을 기반으로 하는 키오스크 모드에 대해 지원 되는 시나리오

시나리오를 기반으로 하는 예제에 대 한 [참조 링크](hololens-kiosk-reference.md#kiosk-xml-code-samples) 를 참조 하 고 복사 하 여 붙여넣기 전에 필요에 따라 업데이트 합니다.

> [!NOTE]
> Intune UI를 사용 하지 않는 경우에만 XML을 사용 하 여 키오스크 구성을 만듭니다.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>로컬 계정 또는 MSA로 로그인 하는 사용자의 경우

| **원하는 키오스크 환경** | **권장 키오스크 구성** | **구성 방법**  | **주의** |
| --- | --- | --- | --- |
| 에 로그인 하는 모든 사용자는 키오스크 환경을 가져옵니다. | [여러 앱 전역 할당 된 액세스 프로필 구성](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [사용자 지정 템플릿 Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [런타임 프로 비전-다중 앱](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 전역 할당 액세스에는 [20H2 이상 빌드가](hololens-release-notes.md#windows-holographic-version-20h2) 필요 합니다. |
| 에 로그인 하는 특정 사용자는 키오스크 환경을 가져옵니다.  | [특정 사용자의 이름을 지정 하는 단일 또는 여러 앱 할당 액세스 프로필을 구성 합니다 (필요한 경우).](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [아래 지원 되는 옵션을 참조 하세요.](#steps-in-configuring-kiosk-mode-for-hololens) | 단일 앱 키오스크 모드의 경우에는 HoloLens에서 로컬 사용자 계정 또는 MSA 계정만 지원 됩니다. <br> 여러 앱 키오스크 모드의 경우 HoloLens에서 MSA 계정 또는 AAD 계정만 지원 됩니다. |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD 계정으로 로그인 하는 사용자의 경우

| **원하는 키오스크 환경** | **권장 키오스크 구성** | **구성 방법** | **주의** |
| --- | --- | --- | --- |
| 에 로그인 하는 모든 사용자는 키오스크 환경을 가져옵니다. | [여러 앱 전역 할당 된 액세스 프로필 구성](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [사용자 지정 템플릿 Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [런타임 프로 비전-다중 앱](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 전역 할당 액세스에는 [20H2 이상 빌드가](hololens-release-notes.md#windows-holographic-version-20h2) 필요 합니다. |
| 에 로그인 하는 모든 사용자는 특정 사용자를 제외 하 고 키오스크 경험을 얻습니다. | [특정 사용자 (장치 소유자 여야 함)를 제외 하 여 여러 앱 전역 할당 액세스 프로필을 구성](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)합니다. | • [사용자 지정 템플릿 Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [런타임 프로 비전-다중 앱](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 전역 할당 액세스에는 [20H2 이상 빌드가](hololens-release-notes.md#windows-holographic-version-20h2) 필요 합니다. |
| 모든 AAD 사용자는 해당 사용자에 대 한 별도의 키오스크 환경을 얻습니다. | [AAD 계정 이름을 지정 하는 각 사용자에 게 할당 된 액세스 구성을 구성 합니다.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [사용자 지정 템플릿 Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [런타임 프로 비전-다중 앱](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| 다른 AAD 그룹의 사용자는 해당 그룹에 대 한 키오스크 모드를 경험 합니다. | [원하는 각 AAD 그룹에 대해 할당 된 액세스 구성을 구성 합니다.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [사용자 지정 템플릿 Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [런타임 프로 비전-다중 앱](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • 사용자가 로그인 하 고 HoloLens 인터넷에 연결 된 경우 해당 사용자가 키오스크 구성이 존재 하는 AAD 그룹의 구성원이 면 해당 AAD 그룹에 대해 키오스크를 사용 하 게 됩니다. <br> • [사용자가 로그인 할 때 인터넷을 사용할 수 없는 경우 사용자에 게 HoloLens 오류 모드 동작이 발생할 수 있습니다.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • 사용자 로그인 및 AAD 그룹 기반 키오스크를 사용 해야 하는 경우 인터넷 가용성이 보장 되지 않는 경우 AADGroupMembershipCacheValidityInDayspolicy을 [사용 하는 것이 좋습니다](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). <br> • 로그인 중에 AAD 그룹에 대 한 최적의 환경을 얻으려면 [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) 를 사용 하는 것이 좋습니다. |
| 임시 용도로 HoloLens를 사용 해야 하는 사용자는 키오스크 환경을 이용 합니다. | [방문자에 대 한 할당 된 액세스 구성 구성](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [사용자 지정 템플릿 Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [런타임 프로 비전-단일 앱](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • 임시 사용자 계정은 로그인 시 HoloLens에 의해 자동으로 생성 되며 임시 사용자가 로그 아웃 하면 제거 됩니다. <br> • [방문자 자동 로그인 정책을](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)사용 하도록 설정 하는 것이 좋습니다. |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>HoloLens에 대 한 키오스크 모드를 구성 하는 단계

키오스크 구성은 다음과 같은 방법으로 만들고 적용할 수 있습니다.

1. MDM 서버 UI (예: Intune의 키오스크 템플릿 또는 it 사용자 지정 OMA-URI 구성)를 사용 하 여 HoloLens에 원격으로 적용 합니다.
2. 런타임 프로 비전 패키지를 사용 하 여 HoloLens에 직접 적용 됩니다.

다음은를 구성 하는 방법입니다. 사용 하려는 프로세스와 일치 하는 탭을 선택 합니다.

1. [Microsoft Intune 단일 앱 키오스크 템플릿](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune 다중 앱 키오스크 템플릿](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune 사용자 지정 템플릿](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [런타임 프로비저닝 - 다중 앱](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [런타임 프로비저닝 - 단일 앱](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>방문자 계정이 키오스크 환경에 자동으로 로그온 하는 방법

빌드 [Windows Holographic, 버전 21h1](hololens-release-notes.md#windows-holographic-version-21h1) 및 그 이후:

- AAD 및 추가 이외의 구성은 모두 키오스크 모드에서 자동 로그온이 사용 하도록 설정 되는 방문자 계정을 지원 합니다.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>HoloLens (첫 번째 gen)에서 키오스크 환경이 지원 되나요?

키오스크 모드는 장치가 Windows Holographic for Business 경우에만 사용할 수 있습니다. 모든 HoloLens 2 장치에는 Windows Holographic for Business 제공 되며 다른 버전은 없습니다. 모든 HoloLens 2 장치에서 키오스크 모드를 즉시 실행할 수 있습니다.

os 빌드 및 os 버전에 따라 HoloLens (첫 번째 gen) 장치를 모두 업그레이드 해야 합니다. HoloLens (첫 번째 gen)을 [Windows Holographic for Business](hololens1-upgrade-enterprise.md) 버전으로 업데이트 하는 방법에 대 한 자세한 내용은 다음과 같습니다. 키오스크 모드를 사용 하도록 HoloLens (첫 번째 gen) 장치를 업데이트 하려면 먼저 장치가 Windows 10 버전 1803 이상 버전을 실행 하는지 확인 해야 합니다. Windows 장치 복구 도구를 사용 하 여 HoloLens (첫 번째 gen) 장치를 기본 빌드로 복구 하거나 최신 업데이트를 설치한 경우 장치를 구성할 준비가 된 것입니다.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>비-프로덕션 환경에서 장치 포털을 사용 하 여 키오스크를 구성 하는 방법

[Windows 장치 포털을 사용 하도록 HoloLens 장치를](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)설정 합니다. Device Portal은 PC의 웹 브라우저에서 연결 가능한 HoloLens에 있는 웹 서버입니다.

 > [!CAUTION]
 > 장치 포털을 사용 하도록 HoloLens를 설정 하는 경우 장치에서 개발자 모드를 사용 하도록 설정 해야 합니다. Windows Holographic for Business 있는 장치에서 개발자 모드를 사용 하면 앱을 테스트용으로 로드할 수 있습니다. 그러나이 설정은 사용자가 Microsoft Store에 의해 인증 되지 않은 앱을 설치할 수 있는 위험을 만듭니다. 관리자는 [정책 CSP](/windows/client-management/mdm/policy-configuration-service-provider)의 **Applicationmanagement/Allowdeveloper 잠금 해제** 설정을 사용 하 여 개발자 모드를 사용 하도록 설정 하는 기능을 차단할 수 있습니다. [개발자 모드에 대해 자세히 알아보세요.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

"True" 또는 "false" 값을 가진 필수 쿼리 문자열 매개 변수 ("kioskModeEnabled")와 하나의 선택적 매개 변수 (패키지 이름 값이 있는 "startupApp")를 사용 하 여/api/holographic/kioskmode/settings에 대 한 POST를 수행 하 여 장치 포털의 REST API을 통해 키오스크 모드를 설정할 수 있습니다. 장치 포털은 개발자만을 위한 것 이며 개발자가 아닌 장치에서는 사용할 수 없습니다. REST API 향후 업데이트/릴리스에서 변경 될 수 있습니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>문제-키오스크 모드의 시작 메뉴에 앱이 표시 되지 않습니다.

**증상**

키오스크 모드를 적용 하는 동안 오류가 발생할 경우 다음과 같은 동작이 나타납니다.

- Windows Holographic 이전 버전 20h2-HoloLens는 시작 메뉴의 모든 응용 프로그램을 표시 합니다.
- Windows Holographic, 버전 20h2-장치에 할당 된 전역 액세스 및 AAD 그룹 구성원에 대 한 액세스 권한이 모두 조합 된 키오스크 구성이 있는 경우 AAD 그룹 멤버 자격을 확인 하면 "시작에 표시 되지 않음" 메뉴가 표시 됩니다.

    ![이제 실패할 때 표시 되는 키오스크 모드 이미지입니다.](images/hololens-kiosk-failure-behavior.png )

- [Windows Holographic, 버전 21h1](hololens-release-notes.md#windows-holographic-version-21h1)부터 키오스크 모드는 빈 시작 메뉴를 표시 하기 전에 전역 할당 된 액세스를 찾습니다. 키오스크 환경은 AAD 그룹 키오스크 모드 중에 오류가 발생 하는 경우 전역 키오스크 구성 (있는 경우)으로 대체 됩니다.

**문제 해결 단계**

- 앱의 AUMID가 올바르게 지정 되어 있고 버전을 포함 하지 않는지 확인 합니다. 예는 수신함 앱에 대 한 [HoloLens aumids](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) 를 참조 하세요.
- 해당 사용자의 장치에 응용 프로그램이 설치 되어 있는지 확인 합니다.
- 키오스크 구성이 AAD 그룹을 기반으로 하는 경우 AAD 사용자가 로그인 할 때 인터넷 연결이 있는지 확인 하십시오. 필요한 경우 [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) 정책을 구성 하면 인터넷이 없어도 작동할 수 있습니다.

XML을 사용 하 여 할당 된 액세스 구성 (런타임 프로 비전 또는 Intune 사용자 지정 OMA URI를 통해)을 만든 경우에는 모든 웹 브라우저 또는 XML 편집기에서 XML을 열어서 XML의 형식이 올바른지 확인 하십시오. 잘 구성 된 템플릿과 유효한 템플릿은 [키오스크 XML 코드 샘플](hololens-kiosk-reference.md#kiosk-xml-code-samples) 을 참조 하세요.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>문제-키오스크 모드를 사용 하 여 패키지를 빌드하지 못했습니다.

**증상**

아래와 같은 대화 상자가 표시 됩니다.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**문제 해결 단계**

1. 위의 대화 상자에 표시 된 하이퍼 링크를 클릭 합니다.
1. 텍스트 편집기에서 ICD을 열고 해당 내용이 오류를 표시 해야 합니다.

> [!NOTE]
> 여러 번 시도 했으면 로그의 타임 스탬프를 확인 합니다. 이렇게 하면 현재 문제만 확인 하는 데 도움이 됩니다.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>문제 – 프로 비전 패키지를 성공적으로 빌드 했지만 적용 하지 못했습니다.

**증상**

Hololens에서 프로 비전 패키지를 적용 하는 동안 오류가 표시 됨

**문제 해결 단계**

1. 런타임 프로 비전 패키지에 대 한 Windows 구성 디자이너 프로젝트가 있는 폴더로 이동 합니다.
1. ICD를 열고 프로 비전 패키지를 빌드하는 동안 로그에 오류가 없는지 확인 합니다. 일부 오류는 빌드 중에 표시 되지 않지만 여전히 ICD에 기록 됩니다.

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>문제 – AAD 그룹에 할당 된 여러 앱이 작동 하지 않음

**증상**

AAD 사용자 로그인 시 장치가 예상 키오스크 모드로 전환 되지 않습니다.

**문제 해결 단계**

- 할당 된 액세스 구성 XML에서 로그인 한 사용자가 구성원 인 AAD 그룹의 guid가 사용 되 고 AAD 사용자의 guid가 사용 되지 않는지 확인 합니다.
- Intune 포털에서 AAD 사용자가 실제로 대상 AAD 그룹의 구성원으로 표시 되는지 확인 합니다.
- Intune에만 해당 장치가 규격으로 표시 되는지 확인 합니다. 자세한 내용은 [장치 준수 참조](/mem/intune/protect/device-compliance-get-started) 를 참조 하세요.
