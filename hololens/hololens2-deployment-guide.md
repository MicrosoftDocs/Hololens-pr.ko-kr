---
title: 외부 클라이언트 배포 가이드
description: 외부 클라이언트용 HoloLens 2에 대 한 배포 가이드 (예제로 원격 지원 포함)
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309336"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>원격 지원을 통해 외부 클라이언트에 HoloLens 2 배포

이 가이드를 통해 IT 전문가는 조직에 Microsoft HoloLens 2 장치를 배포할 수 있습니다.

1. 클라우드 연결 HoloLens 2 장치
1. 사용 하기 위해 외부 클라이언트에 대 한 HoloLens 2 개 장치
1. 안전한 loaned 장치

이 가이드에서는 대부분의 HoloLens 2 배포 시나리오와 외부 사용을 위한 원격 지원을 배포할 때 고객이 보유 하는 [일반적인 문제](#common-concerns) 에 적용 되는 [일반적인 hololens 2 배포 권장 사항을](#general-deployment-recommendations-and-instructions) 제공 합니다.

## <a name="scenario-description"></a>시나리오 설명

이 문서에서는 Contoso 회사에서 단기 또는 장기 사용을 위해 외부 클라이언트의 공장에 HoloLens 2 장치를 배송 하려고 합니다. 클라이언트에서 지원 서비스를 제공 해야 하는 경우 클라이언트는 Contoso 회사에서 제공 하는 자격 증명을 사용 하 여 HoloLens 2 장치에 로그인 하 고 원격 지원을 사용 하 여 Contoso 회사의 전문가에 게 연락 합니다.

[여기](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)에서 원격 지원에 대해 자세히 알아보세요.

### <a name="requirements-for-this-scenario"></a>이 시나리오에 대 한 요구 사항

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. 모바일 장치 관리자 (예: [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up) )
1. 원격 지원 라이선스
    1. [원격 지원 구입](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [평가판 원격 지원](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>일반적인 문제

- [외부 클라이언트에 서로 통신할 수 있는 권한이 없는지 확인 하는 방법](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [클라이언트에 회사 리소스에 대 한 액세스 권한이 없도록 하는 방법](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [앱을 제한 하는 방법](#how-to-restrict-apps)
- [암호를 관리 하는 방법](#how-to-manage-passwords)
- [클라이언트에서 채팅 기록에 액세스할 수 없도록 하는 방법](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>외부 클라이언트에 서로 통신할 수 있는 권한이 없는지 확인 하는 방법

HoloLens에 대 한 원격 지원 HoloLens 호출이 지원 되지 않으므로 클라이언트는 검색할 수 있지만 서로 통신할 수는 없습니다. 클라이언트에서 검색 하 고 호출할 수 있는 사용자를 제한 하기 위해  [정보 장벽을](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 통해 클라이언트가 통신할 수 있는 사용자를 제한할 수 있습니다. 고려할 또 다른 옵션은 [범위 지정 디렉터리 검색](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search) 을 사용 하는 것입니다.

 > [!NOTE]
> Single sign-on이 사용 하도록 설정 되어 있으므로 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)를 사용 하 여 브라우저를 사용 하지 않도록 설정 하는 것이 중요 합니다. 외부 클라이언트가 브라우저를 열고 웹 버전의 팀을 사용 하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>클라이언트에 회사 리소스에 대 한 액세스 권한이 없도록 하는 방법

두 가지 옵션을 고려해 야 합니다.

첫 번째 옵션은 다중 계층 접근 방식입니다.

1. 사용자에 게 필요한 라이선스만 할당 합니다. 사용자에 게 OneDrive, Outlook, SharePoint, Yammer 등을 할당 하지 않으면 해당 리소스에 대 한 액세스 권한이 없습니다. 사용자에 게 필요한 라이선스는 원격 지원, Intune 및 AAD 라이선스를 시작 하는 것입니다.
1. 클라이언트에서 액세스 하지 않으려는 앱 (예: 전자 메일)을 차단 합니다 ( [앱을 제한 하는 방법](#how-to-restrict-apps)참조).
1. 사용자 이름 및 암호를 클라이언트와 공유 하지 않습니다. HoloLens 2에 로그인 하려면 전자 메일 및 숫자 PIN이 필요 합니다.

두 번째 옵션은 클라이언트를 호스트 하는 별도의 테 넌 트를 만드는 것입니다 (이미지 1.1 참조).

**이미지 1.1**

![서비스 테 넌 트 이미지](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>앱을 제한 하는 방법

[키오스크 모드](https://docs.microsoft.com/hololens/hololens-kiosk) 및/또는 [WDAC (Windows Defender 응용 프로그램 제어)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 는 응용 프로그램을 제한 하는 옵션입니다.

### <a name="how-to-manage-passwords"></a>암호를 관리 하는 방법

1. 암호 만료를 제거 합니다. 그러나 이렇게 하면 계정이 손상 될 가능성이 높아집니다. NIST 암호 권장 사항은 30-90 일 마다 암호를 변경 하는 것입니다.
1. 90 일을 초과 하는 HoloLens 2 장치에 대 한 암호 만료를 연장 합니다.
1. 암호를 변경 하려면 장치를 Contoso로 반환 해야 합니다. 그러나이로 인해 장치가 클라이언트의 공장에 90 일 동안 예상 되는 경우 문제가 발생할 수 있습니다.  
1. 여러 클라이언트에 전송 되는 장치의 경우 장치를 클라이언트에 배달 하기 전에 암호를 다시 설정 합니다.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>클라이언트에서 채팅 기록에 액세스할 수 없도록 하는 방법

원격 지원에서는 각 세션 후에 채팅 기록을 지웁니다. 그러나 Microsoft 팀 사용자에 게 채팅 기록을 사용할 수 있습니다.

> [!NOTE]
> Single sign-on이 사용 하도록 설정 되어 있으므로 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)를 사용 하 여 브라우저를 사용 하지 않도록 설정 하는 것이 중요 합니다. 외부 클라이언트가 브라우저를 열고 웹 버전의 팀을 사용 하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.

## <a name="general-deployment-recommendations-and-instructions"></a>일반 배포 권장 사항 및 지침

HoloLens 2 배포 단계에서는 다음을 수행 하는 것이 좋습니다.

1. [최신 HOLOLENS OS 릴리스](https://aka.ms/hololens2download) 를 기준 빌드로 사용 합니다.
1. 사용자 기반 또는 장치 기반 라이선스 할당:
    1. 사용자 기반 라이선스와 장치 기반 라이선스는 모두 다음 단계를 따릅니다.
        1. [AAD에서 그룹을 만들고](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HOLOLENS/RA 사용자에 대 한 멤버를 추가 합니다.
        1. [장치 기반 또는 사용자 기반 라이선스](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 를이 그룹에 할당 합니다.
        1. 필드 MDM 정책의 그룹을 대상으로 지정할 수 있습니다.

1. 장치는 자동 [파일럿](https://docs.microsoft.com/hololens/hololens2-autopilot)을 통해 테 넌 트에 연결 되 고 [자동으로 등록](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)되 고 구성 되어야 합니다.
    1. 장치의 첫 번째 사용자는 장치 소유자가 됩니다.
    1. 장치가 AAD에 연결 된 경우에는 조인을 수행한 사용자가 장치 소유자가 됩니다.
    1. 자세한 내용은 [장치 소유자](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)를 참조 하세요.
1. 테 넌 트는 테 넌 트에만 참가할 수 있도록 장치를 [잠급니다](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) .
    1. **추가 링크:** [테 넌 트 잠금 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. [여기](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)에 대 한 전역 할당 액세스를 사용 하 여 키오스크를 구성 합니다.
1. 다음 (옵션) 기능을 사용 하지 않도록 설정 하는 것이 좋습니다.
    1. [여기](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)에서 장치를 개발자 모드로 전환 하는 기능.
    1. Hpc를 PC에 연결 하 여 복사 날짜에 [USB를 사용 하지 않도록 설정할](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)수 있습니다.
       > [!NOTE]
        > Usb를 사용 하지 않도록 설정 하 고 USB를 사용 하 여 장치에 프로 비전 패키지를 적용 하는 기능을 사용 하려면 [**여기**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)에 나열 된 지침을 따르세요.

1. [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 를 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단 합니다.
1. 원격 지원을 설치의 일부로 최신 버전으로 업데이트 합니다. 이 작업을 수행 하는 두 가지 옵션이 있습니다.
    1. Windows **Microsoft Store--> 원격 지원--> 및 업데이트 앱** 으로 이동 하 여이 작업을 수행할 수 있습니다.
    1. 자동 앱 업데이트를 허용 하는 [Applicationmanagement/Allowapp자동](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 업데이트-기본적으로 사용 하도록 설정 되어 있습니다. 장치를 연결 된 상태로 유지 하 여 업데이트를 수신 합니다.
1. 사용자가 클라이언트 사이트에서 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 [모든 설정 페이지를 사용 하지 않도록](https://docs.microsoft.com/hololens/settings-uri-list) 설정 합니다.
1. [HoloLens 업데이트 관리](https://docs.microsoft.com/hololens/hololens-updates)
    1. [OS 업데이트를 제어](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 하거나 자유롭게 이동 하도록 허용 하는 옵션입니다.
1. [일반적인 장치 제한 사항](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
