---
title: HoloLens를 위한 인프라 지침
description: 무선 네트워크 지원, 원격 지원 및 모바일 장치 관리를 포함하여 HoloLens 디바이스를 위한 인프라 지침에 대해 자세히 알아봅니다.
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639287"
---
# <a name="configure-your-network-for-hololens"></a>HoloLens용 네트워크 구성

문서의 이 부분에는 다음 사람이 필요합니다.

1. 프록시/방화벽을 변경할 수 있는 권한이 있는 네트워크 관리자
2. Azure Active Directory 관리자
3. 모바일 장치 관리자

## <a name="infrastructure-requirements"></a>인프라 요구 사항

HoloLens는 핵심적으로 Azure와 통합된 Windows 모바일 장치입니다.  무선 네트워크 가용성(Wi-Fi)과 Microsoft 서비스 액세스가 있는 상업 환경에서 가장 잘 작동합니다.

중요한 클라우드 서비스에는 다음이 포함됩니다.

- Azure AD(Azure Active Directory)
- WU(Windows 업데이트)

상업용 고객은 HoloLens 디바이스를 대규모로 관리하기 위해 EMM(Enterprise Mobility Management) 또는 MDM(모바일 장치 관리) 인프라가 필요합니다.  이 가이드에서는 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune)을 예로 사용하지만 Microsoft 정책을 완벽하게 지원하는 모든 공급자는 HoloLens를 지원할 수 있습니다.  모바일 장치 관리 공급자에게 HoloLens 2를 지원하는지 문의하세요.

HoloLens는 제한된 클라우드 연결 해제 환경 집합을 지원합니다.

### <a name="wireless-network-eap-support"></a>무선 네트워크 EAP 지원

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens 특정 네트워크 요구 사항

엔드포인트의 [이 목록](hololens-offline.md)이 네트워크 방화벽에서 허용되는지 확인합니다. 그래야 HoloLens가 제대로 작동할 수 있습니다.

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist 특정 네트워크 요구 사항

1. Remote Assist의 최적 성능을 위한 권장 대역폭은 1.5 Mbps입니다. 자세한 내용은 [자세한 네트워크 요구 사항](/MicrosoftTeams/prepare-network)을 참조하세요.
**(네트워크 속도가 1.5Mbps 이상인 경우 Remote Assist는 계속 작동하지만 품질이 저하될 수 있습니다.)**
1. Microsoft Teams가 작동할 수 있도록 네트워크 방화벽에서 이러한 포트와 URL이 허용되는지 확인합니다. [최신 포트 목록](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)을 최신 상태로 유지합니다.

- 특정 [Remote Assist의 네트워크 요구 사항](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)에 대해 자세히 알아보세요. 
- [Microsoft Teams를 위해 조직의 네트워크를 준비](/MicrosoftTeams/prepare-network)하는 방법에 대해 자세히 알아보세요.

### <a name="guides-specific-network-requirements"></a>특정 네트워크 요구 사항 안내

가이드는 앱을 다운로드하고 사용하기 위해 네트워크 액세스만 필요합니다.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory 지침

> [!NOTE]
> 이 단계는 회사가 HoloLens를 관리할 계획인 경우에만 필요합니다.

1. Azure AD 라이선스가 있는지 확인합니다.
자세한 내용은 [HoloLens 라이선스 요구 사항](hololens-licenses-requirements.md)을 참조하세요.

1. 자동 등록을 사용하려는 경우 [Azure AD 등록을 구성](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)해야 합니다.

1. 회사의 사용자가 Azure AD(Azure Active Directory)에 있는지 확인합니다.
사용자를 추가하는 경우 다음 [지침](/azure/active-directory/fundamentals/add-users-azure-active-directory)을 참조하세요.

1. 유사한 라이선스가 필요한 사용자는 동일한 그룹에 추가하는 것이 좋습니다.
    1. [그룹 만들기](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [그룹에 사용자 추가](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 회사의 사용자(또는 사용자 그룹)에게 필수 라이선스가 할당되어 있는지 확인합니다.
라이선스를 할당해야 하는 경우 이 [지침](/azure/active-directory/fundamentals/license-users-groups)을 따릅니다.

1. 사용자가 HoloLens/모바일 장치를 등록할 것으로 예상되는 경우에만 이 단계를 수행합니다(세 가지 옵션이 있음). 이 단계를 수행하면 회사의 사용자(또는 사용자 그룹)가 디바이스를 추가할 수 있습니다.
    1. **옵션 1:** 모든 사용자에게 디바이스를 Azure AD에 조인할 수 있는 권한을 부여합니다.
**Azure Portal에 관리자로 로그인** > **Azure Active Directory** > **디바이스** > **디바이스 설정** >
 **'사용자가 디바이스를 Azure AD에 조인할 수 있습니다.'를 *모두* 로 설정**

    1. **옵션 2:** 선택한 사용자/그룹에 디바이스를 Azure AD에 조인할 수 있는 권한 부여 **Azure Portal에 관리자로 로그인** > **Azure Active Directory** > **디바이스** > **디바이스 설정** >
 **'사용자가 디바이스를 Azure AD에 조인할 수 있습니다.'를 *선택됨* 으로 설정**
![Azure AD 조인 디바이스의 구성을 보여주는 이미지](images/azure-ad-image.png)

    1. **옵션 3:** 모든 사용자가 자신의 디바이스를 도메인에 조인하지 못하도록 차단할 수 있습니다. 즉, 모든 디바이스를 수동으로 등록해야 합니다.

## <a name="mobile-device-manager-guidance"></a>모바일 장치 관리자 지침

### <a name="ongoing-device-management"></a>지속적인 디바이스 관리

> [!NOTE]
> 이 단계는 회사가 HoloLens를 관리할 계획인 경우에만 필요합니다.

지속적인 디바이스 관리는 모바일 장치 관리 인프라에 따라 달라집니다.  일반적인 기능은 거의 같지만 사용자 인터페이스는 크게 다를 수 있습니다.

1. [CSP(구성 서비스 공급자)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)를 사용하면 네트워크의 디바이스에 대한 관리 설정을 만들고 배포할 수 있습니다. [HoloLens CSP 목록](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)을 참조하세요.

1. [규정 준수 정책](/intune/device-compliance-get-started)은 디바이스가 회사 인프라에서 규정을 준수하기 위해 충족해야 하는 규칙 및 설정입니다. 이러한 정책을 조건부 액세스와 함께 사용하여 규정을 준수하지 않는 디바이스가 회사 리소스에 액세스하는 것을 차단합니다. 예를 들어 Bitlocker를 사용하도록 설정할 것을 요구하는 정책을 만들 수 있습니다.

1. [규정 준수 정책 만들기](/intune/protect/compliance-policy-create-windows).

1. 조건부 액세스는 모바일 장치 및 모바일 애플리케이션이 회사 리소스에 액세스하는 것을 허용/거부합니다. 도움이 될 만한 두 문서는 [CA 배포 계획](/azure/active-directory/conditional-access/plan-conditional-access) 및 [모범 사례](/azure/active-directory/conditional-access/best-practices)입니다.

1. [이 문서](/intune/fundamentals/windows-holographic-for-business)에서는 HoloLens용 Intune 관리 도구에 대해 설명합니다.

1. [디바이스 프로필 만들기](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>업데이트 관리

Intune에는 HoloLens 2 및 HoloLens v1(Holographic for Business 포함)을 포함한 Windows 10 디바이스용 업데이트 링이라는 기능이 포함되어 있습니다. 업데이트 링에는 업데이트 설치 방법과 시기를 결정하는 설정 그룹이 포함되어 있습니다.

예를 들어 업데이트를 설치하기 위한 유지 관리 기간을 만들거나 업데이트가 설치된 후 다시 시작을 선택할 수 있습니다.  업데이트할 준비가 될 때까지 업데이트를 무기한 일시 중지하도록 선택할 수도 있습니다.

[Intune을 사용하여 업데이트 링 구성](/intune/windows-update-for-business-configure)에 대해 자세히 알아보세요.

### <a name="application-management"></a>애플리케이션 관리

다음을 통해 HoloLens 애플리케이션을 관리합니다.

1. Microsoft Store  
  Microsoft Store는 HoloLens에서 애플리케이션을 배포하고 사용하는 가장 좋은 방법입니다.  스토어에는 이미 사용 가능한 코어 HoloLens 애플리케이션 집합이 있으며, [자신의 애플리케이션을 게시](/windows/uwp/publish/)할 수도 있습니다.  
  스토어의 모든 애플리케이션은 모든 사람이 공개적으로 사용할 수 있지만 허용되지 않는 경우 비즈니스용 Microsoft Store를 확인하세요.  

1. [비즈니스용 Microsoft Store](/microsoft-store/)  
  비즈니스 및 교육용 Microsoft Store는 기업 환경을 위한 사용자 지정 스토어입니다.  Windows 10 및 HoloLens에 내장된 Microsoft Store를 사용하여 조직을 위한 앱을 찾고 수집하고 배포하고 관리할 수 있습니다.  또한 자신의 상용 환경에만 적용되지만 전 세계에는 적용되지 않는 앱을 배포할 수 있습니다.

1. Intune 또는 다른 모바일 장치 관리 솔루션을 통한 애플리케이션 배포 및 관리  
  Intune을 비롯한 대부분의 모바일 장치 관리 솔루션은 일련의 비즈니스 애플리케이션을 등록된 디바이스 집합에 직접 배포할 수 있는 방법을 제공합니다.  [Intune 앱 설치](/intune/apps-deploy)에 대해서는 이 문서를 참조하세요.

1. _권장되지 않는_ 장치 포털  
  Windows 장치 포털을 사용하여 HoloLens에 직접 애플리케이션을 설치할 수도 있습니다.  장치 포털을 사용하려면 개발자 모드를 활성화해야 하므로 권장하지 않습니다.

[HoloLens에 앱 설치](hololens-install-apps.md)에 대해 자세히 알아보세요.

### <a name="certificates"></a>인증서

MDM 공급자를 통해 인증서를 배포할 수 있습니다. 회사에 인증서가 필요한 경우 Intune은 PKCS, PFX 및 SCEP를 지원합니다. 어떤 인증서가 회사에 적합한지를 이해하는 것이 중요합니다. 가장 적합한 인증서를 확인하려면 [인증서 구성](/intune/protect/certificates-configure) 문서를 참조하세요. HoloLens 인증에 인증서를 사용하려는 경우 PFX 또는 SCEP가 적합할 수 있습니다.

[SCEP](/intune/protect/certificates-profile-scep)를 사용하려면 다음 단계를 참조하세요.

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Holographics for Business Commercial Suite로 업그레이드 하는 방법

> [!NOTE]
> Windows Holographics for Business(상업용 제품군)는 HoloLens 1세대 디바이스에만 사용 가능합니다. HoloLens 2 디바이스에는 프로필이 적용되지 않습니다.

[홀로그램 업그레이드](/intune/configuration/holographic-upgrade) 문서에서 상용 제품군으로 업그레이드하는 방법을 찾을 수 있습니다.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Microsoft Intune을 사용하여 키오스크 모드를 구성하는 방법

1. Microsoft Store를 Intune에 동기화합니다(다음 [지침](/intune/apps/windows-store-for-business) 참고).

1. 앱 설정 확인
    1. Microsoft Store Business 계정에 로그인
    1. **관리 > 제품 및 서비스 > 앱 및 소프트웨어 > 동기화할 앱 선택 > 개인 저장소 가용성 > "모든 사용자" 또는 "특정 그룹" 선택**
        >[!NOTE]
        >원하는 앱이 표시되지 않을 경우 스토어에서 앱을 검색하여 앱을 "가져와야" 합니다. **오른쪽 상단의 "검색" 표시줄 클릭 > 앱 이름 입력 > 앱 클릭 > "가져오기" 선택**.
    1. **Intune > 클라이언트 앱 > 앱** 에 앱이 표시되지 않는 경우 다시 [앱을 동기화](/intune/apps/windows-store-for-business#synchronize-apps)해야 할 수 있습니다.

1. [키오스크 모드용 디바이스 프로필 만들기](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> "Azure AD"를 "사용자 로그온 유형"으로 사용하여 다른 사용자가 다른 키오스크 모드 환경을 갖도록 구성할 수 있습니다. 그러나 이 옵션은 다중 앱 키오스크 모드에서만 사용할 수 있습니다. 다중 앱 키오스크 모드는 여러 앱뿐만 아니라 단 하나의 앱에서도 작동합니다.

![Intune에서 키오스크 모드 구성을 보여주는 이미지](images/aad-kioskmode.png)

다른 MDM 서비스의 경우 공급자의 설명서에서 지침을 확인하세요. 사용자 지정 설정 및 전체 XML 구성을 사용하여 MDM 서비스에서 키오스크를 설정해야 하는 경우 [HoloLens 키오스크](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 지침을 참조하세요.

## <a name="certificates-and-authentication"></a>인증서 및 인증

MDM을 통해 인증서를 배포할 수 있습니다([MDM 섹션](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)의 "인증서" 참조). 패키지 프로비전을 통해 HoloLens에 인증서를 배포할 수도 있습니다. 자세한 내용은 [HoloLens 프로비전](hololens-provisioning.md)을 참조하세요.

### <a name="additional-intune-quick-links"></a>추가 Intune 빠른 링크

1. [프로필 만들기:](/intune/configuration/device-profile-create) 프로필을 사용하면 조직의 디바이스에 푸시될 설정을 추가하고 구성할 수 있습니다.

