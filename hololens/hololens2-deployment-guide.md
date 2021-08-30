---
title: 외부 클라이언트에 클라우드 연결 HoloLens 2 배포
description: 외부 클라이언트에 대 한 HoloLens 2 배포 가이드 (원격 지원을 예제로 사용)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190330"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>외부 클라이언트에 클라우드 연결 HoloLens 2 배포

이 가이드는 [클라우드 연결 배포 가이드](hololens2-cloud-connected-overview.md)에 대 한 추가 자료입니다. 조직에서 단기 또는 장기 사용을 위해 외부 클라이언트의 시설에 HoloLens 2 장치를 배송 하려는 경우에 사용 됩니다. 외부 클라이언트는 조직에서 제공 하는 자격 증명을 사용 하 여 HoloLens 2 장치에 로그인 하 고, [원격 지원을](/dynamics365/mixed-reality/remote-assist/ra-overview) 사용 하 여 전문가에 게 연락 합니다. 이 가이드에서는 대부분의 외부 HoloLens 2 배포 시나리오에 적용 되는 [일반적인 HoloLens 2 배포 권장 사항과](#general-deployment-recommendations) 외부 사용을 위한 원격 지원을 배포할 때 고객이 보유 하는 [일반적인 문제](#common-external-client-deployment-concerns) 에 대해 설명 합니다. 

## <a name="prerequisites"></a>사전 요구 사항

HoloLens 2를 외부적으로 배포 하기 위한 [클라우드 연결 배포 가이드](hololens2-cloud-connected-overview.md) 에 따라 다음과 같은 인프라가 준비 되어야 합니다.

- MDM 자동 등록을 사용 하는 Azure AD 조인-MDM 관리 (Intune)
- 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
    - 장치당 단일 또는 여러 사용자가 지원 됩니다.

### <a name="remote-assist-licensing-and-requirements"></a>원격 지원 라이선스 및 요구 사항

- Azure AD 계정(구독을 구매하고 라이선스를 할당하는 데 필요)
- [Remote Assist 구독](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)(또는 [Remote Assist 평가판](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

[원격 지원에 대 한 자세한](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)정보를 참조 하세요.

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 사용자

- Remote Assist 라이선스
- 네트워크 연결

### <a name="microsoft-teams-user"></a>Microsoft Teams 사용자

- Microsoft Teams 또는 [Teams Freemium](https://products.office.com/microsoft-teams/free)
- 네트워크 연결

## <a name="general-deployment-recommendations"></a>일반 배포 권장 사항

외부 HoloLens 2 배포에 대해 다음 단계를 수행 하는 것이 좋습니다.

1. [최신 HoloLens OS 릴리스](https://aka.ms/hololens2download) 를 기준 빌드로 사용 합니다.
1. 다음 단계를 수행 하 여 사용자 기반 라이선스 또는 장치 기반 라이선스를 할당 합니다.
    1. [AAD에서 그룹을 만들고](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 사용자에 대 한 멤버를 추가 합니다.
    1. [장치 기반 또는 사용자 기반 라이선스](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 를이 그룹에 할당 합니다.
    1. 필드 [MDM (모바일 장치 관리)](hololens-enroll-mdm.md) 정책에 대 한 대상 그룹입니다.

1. AAD 장치를 테 넌 트에 연결 하 고, [자동으로 등록](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)하 고, [Autopilot](/hololens/hololens2-autopilot)를 통해 구성 합니다. 자세한 내용은 [장치 소유자](/hololens/security-adminless-os#device-owner)를 참조 하세요.
    1. 장치의 첫 번째 사용자는 장치 소유자가 됩니다.
    1. 장치가 AAD에 연결 된 경우에는 조인을 수행한 사용자가 장치 소유자가 됩니다.
    
1. [테](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 넌 트가 테 넌 트에서만 참가할 수 있도록 장치를 잠급니다.
    1. 또한 [테 넌 트 잠금 CSP](/windows/client-management/mdm/tenantlockdown-csp)를 참조 하세요.

1. [전역 할당 액세스를 사용 하 여 키오스크 모드를 구성](/hololens/hololens-global-assigned-access-kiosk)합니다.

1. 다음 (옵션) 기능을 사용 하지 않도록 설정 합니다.
    1. [여기](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)에서 장치를 개발자 모드로 전환 하는 기능.
    1. HoloLens를 PC에 연결 하 여 복사 하는 기능 [USB를 사용 하지 않도록 설정](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)합니다.
       > [!NOTE]
        > Usb를 사용 하지 않도록 설정 하 고 USB를 사용 하 여 장치에 프로 비전 패키지를 적용 하는 기능이 필요 하지 않은 경우 [프로 비전 패키지 설치를 허용 하는 방법에 대 한 지침](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)을 따르세요.

1. [WDAC (Windows Defender 응용 프로그램 제어)](/hololens/windows-defender-application-control-wdac) 를 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단 합니다.
1. 원격 지원을 설치의 일부로 최신 버전으로 업데이트 합니다. 다음 두 가지 옵션을 고려 합니다.
    1. Windows **Microsoft Store--> 원격 지원--> 및 앱 업데이트** 로 이동 합니다.
    1. 자동 앱 업데이트를 허용 하는 [Applicationmanagement/Allowapp자동](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 업데이트-기본적으로 사용 하도록 설정 되어 있습니다. 장치를 연결 된 상태로 유지 하 여 업데이트를 수신 합니다.
1. 사용자가 클라이언트 사이트에서 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 [모든 설정 페이지를 사용 하지 않도록](/hololens/settings-uri-list) 설정 합니다.
1. [HoloLens 업데이트 관리](/hololens/hololens-updates)
    1. [OS 업데이트를 제어](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 하거나 자유롭게 이동 하도록 허용 하는 옵션입니다.
1. [일반적인 장치 제한을](/hololens/hololens-common-device-restrictions)설정 합니다.

이제 외부 클라이언트는 HoloLens 2을 사용할 준비가 되었습니다.

## <a name="common-external-client-deployment-concerns"></a>일반적인 외부 클라이언트 배포 문제

- [클라이언트가 서로 통신할 수 없도록 보장](#ensure-that-external-clients-cant-communicate-with-one-another)
- [클라이언트에서 회사 리소스에 액세스할 수 없는지 확인](#ensure-that-clients-wont-have-access-to-company-resources)
- [앱 숨기기 또는 제한](#hidden-or-restricted-apps)
- [클라이언트에 대 한 암호 관리](#password-management-for-your-clients) 
- [클라이언트에서 채팅 기록에 액세스할 수 없는지 확인](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>외부 클라이언트가 서로 통신할 수 없는지 확인

HoloLens 호출에 대 한 원격 지원 HoloLens 지원 되지 않습니다. 클라이언트는 검색할 수 있지만 서로 통신할 수는 없습니다. [Microsoft 365의 정보 장애물](/microsoft-365/compliance/information-barriers) 은 클라이언트에서 검색 하 고 호출할 수 있는를 추가로 제한할 수 있습니다. 또 다른 옵션은 [Microsoft Teams 범위 디렉터리 검색](/MicrosoftTeams/teams-scoped-directory-search)을 사용 하는 것입니다.

 > [!NOTE]
> single sign on을 사용 하도록 설정 했으므로 [Windows Defender 응용 프로그램 제어 (WDAC)](/hololens/windows-defender-application-control-wdac)를 사용 하 여 브라우저를 사용 하지 않도록 설정 하는 것이 중요 합니다. 외부 클라이언트가 브라우저를 열고 웹 버전의 Teams 사용 하는 경우 클라이언트는 채팅 기록에 액세스할 수 있습니다.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>클라이언트에서 회사 리소스에 액세스할 수 없는지 확인

두 가지 옵션을 고려해 야 합니다.

첫 번째 옵션은 다중 계층 접근 방식입니다.

1. 사용자에 게 필요한 라이선스만 할당 합니다. OneDrive, Outlook, SharePoint, Yammer 등을 할당 하지 않으면 해당 리소스에 대 한 액세스 권한이 사용자에 게 표시 되지 않습니다. 사용자에 게 필요한 라이선스는 원격 지원, Intune 및 AAD 라이선스를 시작 하는 것입니다.
1. 클라이언트에서 액세스 하지 않으려는 앱 (예: 전자 메일)을 차단 합니다 ( [앱이 숨겨지거나 제한 됨](#apps are hidden or restricted)참조).
1. 사용자 이름 및 암호를 클라이언트와 공유 하지 않습니다. HoloLens 2에 로그인 하려면 전자 메일과 숫자 PIN이 필요 합니다.

두 번째 옵션은 클라이언트를 호스트 하는 별도의 테 넌 트를 만드는 것입니다 (이미지 1.1 참조).

**이미지 1.1**

![서비스 테 넌 트 이미지입니다.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>숨겨진 앱 또는 제한 된 앱

[키오스크 모드](/hololens/hololens-kiosk) 및/또는 [WDAC (Windows Defender 응용 프로그램 컨트롤)](/hololens/windows-efender-application-control-wdac) 는 응용 프로그램을 숨기 거 나 제한 하는 옵션입니다.

### <a name="password-management-for-your-clients"></a>클라이언트에 대 한 암호 관리

1. 암호 만료를 제거 합니다. 그러나이 옵션을 선택 하면 계정이 손상 될 가능성이 높아질 수 있습니다. NIST 암호 권장 사항은 30-90 일 마다 암호를 변경 하는 것입니다.
1. 90 일을 초과 하 HoloLens 2 장치에 대 한 암호 만료를 연장 합니다.
1. 암호를 변경 하려면 장치를 조직에 반환 해야 합니다. 그러나이 옵션을 선택 하면 장치가 클라이언트의 공장 90 일 동안 발생 한 경우 문제가 발생할 수 있습니다.  
1. 여러 클라이언트에 전송 되는 장치의 경우 장치를 클라이언트에 배달 하기 전에 암호를 다시 설정 합니다.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>클라이언트에서 채팅 기록에 액세스할 수 없도록 합니다.

원격 지원에서는 각 세션 후에 채팅 기록을 지웁니다. 그러나 Microsoft Teams 사용자는 채팅 기록을 사용할 수 있습니다.

> [!NOTE]
> single sign on을 사용 하도록 설정 했으므로 [Windows Defender 응용 프로그램 제어 (WDAC)](/hololens/windows-defender-application-control-wdac)를 사용 하 여 브라우저를 사용 하지 않도록 설정 하는 것이 중요 합니다.  외부 클라이언트가 브라우저를 열고 웹 버전의 Teams을 사용 하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.
