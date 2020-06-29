---
title: HoloLens 인프라 가이드라인
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 65403589fa3d612290fdd59a4843da27c12a956c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830152"
---
# HoloLens 네트워크 구성

문서의 이 부분에는 다음과 같은 사용자가 필요합니다.

1. Proxy/방화벽을 변경할 수 있는 권한이 있는 네트워크 관리자
2. Azure Active Directory 관리자
3. 모바일 장치 관리자

## 인프라 요구 사항

HoloLens는 핵심적으로 Azure와 통합된 Windows 모바일 장치입니다.  무선 네트워크 가용성(wi-fi) 및 Microsoft 서비스에 액세스할 수 있는 상업적 환경에 가장 적합합니다.

중요한 클라우드 서비스에는 다음이 포함됩니다.

- Azure Active Directory(AAD)
- Windows 업데이트(WU)

상업적 고객이 HoloLens 장치를 대규모로 관리하려면 엔터프라이즈 이동성 관리(EMM) 또는 모바일 장치 관리(MDM) 인프라가 필요합니다.  이 가이드에서는 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune)을 예제로 사용하지만 Microsoft 정책을 완벽하게 지원하는 모든 공급자는 HoloLens를 지원할 수 있습니다.  모바일 장치 관리 공급자에게 HoloLens 2를 지원하는지 문의하세요.

HoloLens는 제한된 클라우드 연결 해제 환경을 지원합니다.

### 무선 네트워크 EAP 지원

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### HoloLens 관련 네트워크 요구 사항

이 끝점 [목록](hololens-offline.md)이 네트워크 방화벽에서 허용되는지 확인합니다. 그러면 HoloLens가 제대로 작동하게 됩니다.

### 원격 지원 특정 네트워크 요구 사항

1. 원격 지원에서 최적의 성능을 내도록 권장되는 대역폭은 1.5 Mbps입니다. 자세한 네트워크 요구 사항과 추가 정보는 [여기](https://docs.microsoft.com/MicrosoftTeams/prepare-network)에서 볼 수 있습니다.
**(네트워크 속도가 1.5Mbps 이상인 네트워크가 아닌 경우에도 Remote Assist는 계속 작동합니다. 그러나 품질이 저하될 수 있습니다.)**
1. 이러한 포트와 URL이 네트워크 방화벽에서 허용되는지 확인합니다. 이를 통해 Microsoft Teams가 실행하게 됩니다. 최신 목록은[여기](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)에서 볼 수 있습니다.

### 특정 네트워크 요구 사항 가이드

가이드는 앱을 다운로드하고 사용하기 위해 네트워크 액세스만을 필요로 합니다.

## Azure Active Directory 지침

> [!NOTE]
> 이 단계는 회사에서 HoloLens 관리를 계획하는 경우에만 필요합니다.

1. Azure AD 라이선스가 있는지 확인합니다.
자세한 내용은 [HoloLens 라이선스 요구 사항](hololens-licenses-requirements.md)을 참조하세요.

1. 자동 등록을 사용하려는 경우 [Azure AD 등록을 구성](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)해야 합니다.

1. 회사의 사용자가 Azure Active Directory (Azure AD)에 있는지 확인합니다.
사용자 추가 지침은 [여기](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)에서 확인할 수 있습니다.

1. 유사한 라이선스가 필요한 사용자를 같은 그룹에 추가하는 것이 좋습니다.
    1. [그룹 만들기](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [그룹에 사용자 추가](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 회사의 사용자(또는 사용자 그룹)에게 필수 라이선스가 할당되어 있는지 확인합니다.
라이선스 할당에 대한 지시사항은 [여기](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)에서 찾을 수 있습니다.

1. 사용자가 HoloLens/모바일 장치를 사용자에게 등록해야 하는 경우에만이 단계를 수행하세요(세 가지 옵션이 있음). 이 단계는 회사의 사용자(또는 사용자 그룹)가 장치를 추가할 수 있도록 합니다.
    1. **옵션 1:** 모든 사용자에 게 Azure AD에 장치를 연결할 수 있는 권한을 부여합니다.
**관리자로 Azure Portal에 로그인** > **Azure Active Directory ** > **장치** > **장치 설정** >
**설정된 사용자는 다음을 위해 장치를 Azure AD에 연결할 수 있음*모두***

    1. **옵션 2 :** 선택한 사용자/그룹에게 장치를 Azure AD에 연결할 수 있는 권한 부여 **관리자로 Azure Portal에 로그인** > **Azure Active Directory** > **장치** > **장치 설정** >
**설정된 사용자는 다음을 위해 장치를 Azure AD에 연결할 수 있음*선택한***
![Azure AD 연결 장치의 구성을 보여주는 이미지](images/azure-ad-image.png)

    1. **옵션 3:** 모든 사용자가 자신의 장치를 도메인에 연결하지 못하도록 차단할 수 있습니다. 즉, 모든 장치를 수동으로 등록해야 합니다.

## 모바일 장치 관리자 지침

### 지속적인 디바이스 관리

> [!NOTE]
> 이 단계는 회사에서 HoloLens 관리를 계획하는 경우에만 필요합니다.

지속적인 디바이스 관리는 모바일 디바이스 관리 인프라에 따라 다릅니다.  일반적인 기능은 거의 같지만 사용자 인터페이스는 크게 다를 수 있습니다.

1. [CSP(구성 서비스 공급자)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)를 사용하면 네트워크의 디바이스에 대한 관리 설정을 만들고 배포할 수 있습니다. HoloLens 에 대한 CSP 목록은 [여기](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)에서 찾을 수 있습니다.

1. [준수 정책](https://docs.microsoft.com/intune/device-compliance-get-started)은 디바이스가 회사 인프라에서 준수를 위해 충족해야 하는 규칙 및 설정입니다. 이 정책을 조건부 액세스와 함께 사용하여 비준수 장치의 회사 리소스에 대한 액세스를 차단할 수 있습니다. 예를 들어, Bitlocker를 사용하도록 설정해야 하는 정책을 만들 수 있습니다.

1. [준수 정책 생성](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).

1. 조건부 액세스는 모바일 장치 및 모바일 애플리케이션이 회사 리소스에 액세스하는 것을 허용/거부합니다. 도움이 될 만한 두 가지 문서는 [CA 배포 계획 ](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 및 [모범 사례](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)입니다.

1. [이 문서](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)에서는 HoloLens용 Intune 관리 도구에 대해 설명합니다.

1. [장치 프로필 만들기](https://docs.microsoft.com/intune/configuration/device-profile-create)

### 업데이트 관리

Intune에는 HoloLens 2 및 HoloLens v1(Holographic for Business 포함)을 포함하여 Windows 10 장치용 업데이트 링이라는 기능이 포함되어 있습니다. 업데이트 링에는 업데이트 설치 방법 및 시기를 결정하는 설정 그룹이 포함되어 있습니다.

예를 들어 업데이트를 설치하는 유지 관리 창을 만들거나 업데이트를 설치한 후 다시 시작 하도록 선택할 수 있습니다.  업데이트할 준비가 될 때까지 업데이트를 무기한 일시 중지하도록 선택할 수도 있습니다.

[Intune으로 업데이트 링 구성](https://docs.microsoft.com/intune/windows-update-for-business-configure)에 대해 자세히 알아보세요.

### 응용 프로그램 관리

다음을 통해 HoloLens 응용 프로그램을 관리합니다.

1. Microsoft Store  
  Microsoft 스토어는 HoloLens에서 응용 프로그램을 배포하고 사용하는 가장 좋은 방법입니다.  주요 HoloLens 응용 프로그램이 이미 상점에서 사용 가능하고, 사용자가 [직접 게시](https://docs.microsoft.com/windows/uwp/publish/)할 수도 있습니다.  
  상점의 모든 응용 프로그램은 모든 사람이 공개적으로 사용할 수 있지만, 허용되지 않는 경우 비즈니스용 Microsoft Store를 확인하세요.  

1. [비즈니스용 Microsoft Store](https://docs.microsoft.com/microsoft-store/)  
  비즈니스 및 교육용 Microsoft Store는 기업 환경을 위한 사용자 지정 스토어입니다.  Windows 10 및 HoloLens에 내장된 Microsoft Store를 사용하여 조직을 위한 앱을 찾고 수집하고 배포하고 관리할 수 있습니다.  또한 전 세계가 아닌 사용자의 상업적 환경에만 앱을 배포할 수도 있습니다.

1. Intune 또는 다른 모바일 장치 관리 솔루션을 통한 응용 프로그램 배포 및 관리  
  Intune을 비롯한 대부분의 모바일 장치 관리 솔루션은 일련의 비즈니스 응용 프로그램을 등록된 장치 집합에 직접 배포할 수 있는 방법을 제공합니다.  [Intune 앱 설치](https://docs.microsoft.com/intune/apps-deploy)에 대한 이 문서를 참조하세요.

1. _권장되지 않는_ 장치 포털  
  Windows 장치 포털을 사용하여 HoloLens에 직접 응용 프로그램을 설치할 수도 있습니다.  장치 포털을 사용하려면 개발자 모드를 활성화해야 하므로 권장하지 않습니다.

[HoloLens에 앱을 설치하는 방법](https://docs.microsoft.com/hololens/hololens-install-apps)에 대해 자세히 알아보세요.

### 인증서

MDM 공급자를 통해 인증서를 배포할 수 있습니다. 회사에 인증서가 필요한 경우 Intune에서 PKCS, PFX 및 SCEP를 지원합니다. 어떤 인증서가 회사에 적합한지를 이해하는 것이 중요합니다. 사용자에게 가장 적합한 인증서를 확인하려면 [여기](https://docs.microsoft.com/intune/protect/certificates-configure)를 방문하세요. HoloLens 인증에 인증서를 사용하려는 경우 PFX 또는 SCEP가 적합할 수 있습니다.

SCEP 단계는 [여기](https://docs.microsoft.com/intune/protect/certificates-profile-scep)에서 찾을 수 있습니다.

### Holographics for Business Commercial 제품군으로 업그레이드 하는 방법

> [!NOTE]
> Windows Holographics for Business(상업용 제품군)는 HoloLens 1세대 장치에만 사용 가능합니다. HoloLens 2 장치에는 프로필이 적용되지 않습니다.

상업용 제품군으로 업그레이드하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/intune/configuration/holographic-upgrade)를 참조하세요.

### Microsoft Intune을 사용하여 키오스크 모드를 구성하는 방법

1. Microsoft Store와 Intune 동기화([여기](https://docs.microsoft.com/intune/apps/windows-store-for-business)).

1. 앱 설정 확인
    1. Microsoft Store Business 계정에 로그인
    1. **관리 > 제품 및 서비스 > 앱 및 소프트웨어 > 동기화하려는 앱 선택 > 개인 저장소 가용성 > "모두" 또는 "특정 그룹" 선택**
        >[!NOTE]
        >원하는 앱이 표시되지 않을 경우 스토어에서 앱을 검색하여 앱을 "가져와야" 합니다. **오른쪽 상단에서 "검색" 막대를 클릭하고 앱 이름을 입력한 다음 해당 앱을 클릭하고 "가져오기"를 선택하십시오.**
    1. **Intune > 클라이언트 앱 > 앱**에 앱이 표시되지 않는다면 다시 [앱을 동기화](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)해야 할 수 있습니다.

1. [키오스크 모드용 디바이스 프로필 만들기](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> "Azure AD"를 "사용자 로그온 유형"으로 사용하여 다른 사용자가 다른 키오스크 모드 환경을 갖도록 구성할 수 있습니다. 그러나 이 옵션은 다중 앱 키오스크 모드에서만 사용할 수 있습니다. 다중 앱 키오스크 모드는 여러 앱뿐만 아니라 하나의 앱에서만 작동합니다.

![Intune에서 키오스크 모드 구성을 보여주는 이미지](images/aad-kioskmode.png)

다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. MDM 서비스에서 키오스크를 설정하기 위해 사용자 지정 설정 및 전체 XML 구성을 사용해야 하는 경우 [여기](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)에서 추가 지침을 찾을 수 있습니다.

## 인증서 및 인증

MDM을 통해 인증서를 배포할 수 있습니다([MDM 섹션](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)의 "인증서" 참조). 패키지 프로비저닝을 통해 HoloLens에 인증서를 배포할 수도 있습니다. 추가 정보는 [HoloLens 프로비저닝](hololens-provisioning.md)을 참조하십시오.

### 추가 Intune 빠른 링크

1. [프로필 생성:](https://docs.microsoft.com/intune/configuration/device-profile-create) 프로필을 사용하면 조직의 기기에 푸시될 설정을 추가하고 구성할 수 있습니다.

