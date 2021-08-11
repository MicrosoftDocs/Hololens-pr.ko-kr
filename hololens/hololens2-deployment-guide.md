---
title: 외부 클라이언트 배포 가이드
description: '외부 클라이언트용 HoloLens 2 배포 가이드(예: 원격 지원 사용)'
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659902"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Remote Assist 사용하여 외부 클라이언트에 HoloLens 2 배포

이 가이드는 다음 목표를 가진 IT 전문가가 조직에 Microsoft HoloLens 2개 디바이스를 배포하는 데 도움이 됩니다.

1. 클라우드 연결 HoloLens 2 디바이스
1. 사용할 외부 클라이언트에 대한 대출 HoloLens 2 디바이스
1. 대출 디바이스 보호

이 가이드에서는 대부분의 HoloLens 2 배포 시나리오에 적용되는 일반적인 HoloLens 2 배포 [권장 사항](#general-deployment-recommendations-and-instructions) 및 고객이 외부 사용을 위해 Remote Assist 배포할 때 발생하는 일반적인 [문제를](#common-concerns) 제공합니다.

## <a name="scenario-description"></a>시나리오 설명

이 문서의 목적을 위해 Contoso Company는 단기 또는 장기 사용을 위해 외부 클라이언트 공장에 HoloLens 2 디바이스를 제공하려고 합니다. 클라이언트에 서비스 기계 지원이 필요한 경우 클라이언트는 Contoso Company에서 제공한 자격 증명을 사용하여 HoloLens 2 디바이스에 로그인하고 Remote Assist 사용하여 Contoso 회사 전문가에게 문의합니다.

[여기에서](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)Remote Assist 대해 자세히 알아보세요.

### <a name="requirements-for-this-scenario"></a>이 시나리오에 대한 요구 사항

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. 모바일 디바이스 관리자 - 예: [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist 라이선스
    1. [구매 Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [평가판 Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>일반적인 문제

- [외부 클라이언트가 서로 통신할 수 없도록 하는 방법](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [클라이언트가 회사 리소스에 액세스할 수 없도록 하는 방법](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [앱을 제한하는 방법](#how-to-restrict-apps)
- [암호를 관리하는 방법](#how-to-manage-passwords)
- [클라이언트가 채팅 기록에 액세스할 수 없도록 하는 방법](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>외부 클라이언트가 서로 통신할 수 없도록 하는 방법

HoloLens 호출에 대한 Remote Assist HoloLens 지원되지 않기 때문에 클라이언트는 서로 검색할 수 있지만 서로 통신할 수는 없습니다. 클라이언트가 검색하고 호출할 수 있는 사람을 추가로 제한하기 위해  [정보 장벽은](/microsoft-365/compliance/information-barriers) 클라이언트가 통신할 수 있는 사람을 제한할 수 있습니다. 고려해야 할 또 다른 옵션은 [범위가 있는 디렉터리 검색을](/MicrosoftTeams/teams-scoped-directory-search) 사용하는 것입니다.

 > [!NOTE]
> Single Sign On을 사용하도록 설정되므로 [**WDAC**](/hololens/windows-defender-application-control-wdac)를 사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다. 외부 클라이언트가 브라우저를 열고 웹 버전의 Teams 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>클라이언트가 회사 리소스에 액세스할 수 없도록 하는 방법

고려해야 할 두 가지 옵션이 있습니다.

첫 번째 옵션은 다중 계층 접근 방식입니다.

1. 사용자에게 필요한 라이선스만 할당합니다. 사용자에게 OneDrive, Outlook, SharePoint, Yammer 등을 할당하지 않으면 해당 리소스에 액세스할 수 없습니다. 사용자에게 필요한 유일한 라이선스는 Remote Assist, Intune 및 AAD 라이선스를 시작하는 것입니다.
1. 클라이언트가 액세스하지 않으려는 앱(예: 메일)을 [차단합니다(앱을 제한하는 방법](#how-to-restrict-apps)참조).
1. 사용자 이름이나 암호를 클라이언트와 공유하지 마십시오. HoloLens 2 로그인하려면 이메일 및 숫자 PIN이 필요합니다.

두 번째 옵션은 클라이언트를 호스트하는 별도의 테넌트(이미지 1.1 참조)를 만드는 것입니다.

**이미지 1.1**

![서비스 테넌트 이미지](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>앱을 제한하는 방법

[키오스크 모드](/hololens/hololens-kiosk) 및/또는 [WDAC(Windows Defender 애플리케이션 제어)는](/hololens/windows-defender-application-control-wdac) 애플리케이션을 제한하는 옵션입니다.

### <a name="how-to-manage-passwords"></a>암호를 관리하는 방법

1. 암호 만료를 제거합니다. 그러나 이렇게 하면 계정이 손상될 가능성이 높아질 수 있습니다. NIST 암호 권장 사항은 30-90일마다 암호를 변경하는 것입니다.
1. HoloLens 2 디바이스의 암호 만료 기간을 90일을 초과하도록 연장합니다.
1. 암호를 변경하려면 디바이스를 Contoso로 반환해야 합니다. 그러나 이로 인해 디바이스가 90일 이상 클라이언트 공장에 있어야 하는 경우 문제가 발생할 수 있습니다.  
1. 여러 클라이언트로 전송되는 디바이스의 경우 클라이언트에 디바이스를 전달하기 전에 암호를 재설정합니다.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>클라이언트가 채팅 기록에 액세스할 수 없도록 하는 방법

Remote Assist 각 세션 후에 채팅 기록을 지웁니다. 그러나 채팅 기록은 Microsoft Teams 사용자가 사용할 수 있습니다.

> [!NOTE]
> Single Sign On을 사용하도록 설정되므로 [**WDAC**](/hololens/windows-defender-application-control-wdac)를 사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다. 외부 클라이언트가 브라우저를 열고 웹 버전의 Teams 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.

## <a name="general-deployment-recommendations-and-instructions"></a>일반 배포 권장 사항 및 지침

HoloLens 2 배포 단계에는 다음을 권장합니다.

1. 최신 [HoloLens OS 릴리스를](https://aka.ms/hololens2download) 기준 빌드로 사용합니다.
1. 사용자 기반 또는 디바이스 기반 라이선스 할당:
    1. 사용자 기반 및 디바이스 기반 라이선스는 모두 다음 단계를 따릅니다.
        1. [AAD에서 그룹을 만들고](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 사용자에 대한 멤버를 추가합니다.
        1. 이 그룹에 [디바이스 기반 또는 사용자 기반 라이선스를 할당합니다.](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them)
        1. (선택 사항) MDM 정책의 대상 그룹을 지정할 수 있습니다.

1. 디바이스는 AAD를 테넌트인 자동 등록 에 조인하고 [자동 파일럿](/hololens/hololens2-autopilot) [을](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)통해 구성해야 합니다.
    1. 디바이스의 첫 번째 사용자는 디바이스 소유자가 됩니다.
    1. 디바이스가 AAD에 조인된 경우 조인을 수행한 사용자가 디바이스 소유자로 만들어집니다.
    1. 자세한 내용은 [디바이스 소유자](/hololens/security-adminless-os#device-owner)를 참조하세요.
1. [테넌트는 테넌트만](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 조인할 수 있도록 디바이스를 잠급합니다.
    1. **추가 링크:** [테넌트 잠금 CSP](/windows/client-management/mdm/tenantlockdown-csp).
1. 여기에 대한 전역 할당 액세스를 사용하여 키오스크를 [구성합니다.](/hololens/hololens-global-assigned-access-kiosk)
1. 다음(선택 사항) 기능을 사용하지 않도록 설정 하는 것이 좋습니다.
    1. 여기에서 디바이스를 개발자 모드로 전환할 수 [있습니다.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. HOLOLENS PC에 연결하여 날짜를 복사하는 기능은 [USB를 사용하지 않도록 설정합니다.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > USB를 사용하지 않도록 설정하지 않고 USB를 사용하여 디바이스에 프로비저닝 패키지를 적용하는 기능을 원하는 경우 [**여기에**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)나열된 지침을 따르세요.

1. [WDAC를](/hololens/windows-defender-application-control-wdac) 사용하여 HoloLens 2 디바이스에서 앱을 허용하거나 차단합니다.
1. 설치의 일부로 Remote Assist 최신 버전으로 업데이트합니다. 이 작업을 수행하는 두 가지 옵션이 있습니다.
    1. --> Remote Assist **--> 및 앱 업데이트 Microsoft Store Windows** 이 작업을 수행할 수 있습니다.
    1. 자동 앱 업데이트를 허용하는 [ApplicationManagement/AllowAppStoreAutoUpdate는](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 기본적으로 사용하도록 설정됩니다. 디바이스를 연결된 상태로 유지하여 업데이트를 받습니다.
1. 사용자가 클라이언트 사이트의 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 [모든 설정 페이지를 사용하지 않도록 설정합니다.](/hololens/settings-uri-list)
1. [HoloLens 업데이트 관리](/hololens/hololens-updates)
    1. OS [업데이트를 제어하거나](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 자유롭게 흐르도록 허용하는 옵션입니다.
1. [일반적인 디바이스 제한 사항.](/hololens/hololens-common-device-restrictions)
