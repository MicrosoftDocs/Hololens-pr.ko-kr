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
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "11268004"
---
# 원격 지원을 사용하여 외부 클라이언트에 HoloLens 2 배포

이 문서는 IT 사용자가 원격 지원에 중점을 두는 HoloLens 2 장치를 계획하고 배포하는 데 도움이 됩니다. [원격 지원에 대해 자세히 알아보시고.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

## 시나리오 설명

이 문서의 목적을 위해 Contoso Company는 단기 또는 장기 사용을 위해 HoloLens 2 장치를 외부 클라이언트의 공장에 발송하기를 원합니다. 클라이언트가 기계를 서비스하는 데 도움이 필요한 경우 클라이언트는 Contoso Company에서 제공하는 자격 증명을 사용하여 HoloLens 2 장치에 로그인하고 원격 지원을 사용하여 Contoso Company의 전문가에게 연락합니다.

### 이 시나리오에 대한 요구 사항

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. 모바일 장치 관리자 - [Intune 등의](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. 원격 지원 라이선스
    1. [원격 지원 구입](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [평가판 원격 지원](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## 일반적인 문제

- [외부 클라이언트가 서로 통신할 수 없는지 확인하는 방법](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [클라이언트가 회사 리소스에 액세스할 수 없는지 확인하는 방법](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [앱을 제한하는 방법](#how-to-restrict-apps)
- [암호를 관리하는 방법](#how-to-manage-passwords)
- [클라이언트가 채팅 기록에 액세스할 수 없는지 확인하는 방법](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### 외부 클라이언트가 서로 통신할 수 없는지 확인하는 방법

HoloLens에 대한 원격 지원 HoloLens 통화는 지원되지 않습니다. 클라이언트는 검색할 수 있지만 서로 통신할 수 없습니다. 클라이언트가 검색 및 통화를 할 수 있는 사용자에 대한 제한을 강화하기 위해  [정보](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 장벽은 클라이언트가 통신할 수 있는 사용자에 대해 제한할 수 있습니다. 고려해야 할 또 다른 옵션은 [범위가 지정한 디렉터리 검색을 사용하는 것입니다.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Single Sign-On이 사용하도록 설정되어 있는 경우 [**WDAC를**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다. 외부 클라이언트가 브라우저를 열고 Teams의 웹 버전을 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.

### 클라이언트가 회사 리소스에 액세스할 수 없는지 확인하는 방법

두 가지 옵션을 고려해야 합니다.

첫 번째 옵션은 다중 계층 접근 방식입니다.

1. 사용자에게 필요한 라이선스만 할당합니다. 사용자에게 OneDrive, Outlook, SharePoint, Yammer 등을 할당하지 않는 경우 해당 리소스에 액세스할 수 없습니다. 사용자에게 필요한 라이선스는 원격 지원, Intune 및 AAD 라이선스뿐입니다.
1. 클라이언트가 액세스하지 못하게 할 앱(예: 전자 메일)을 [차단합니다(앱](#how-to-restrict-apps)제한 방법 참조).
1. 사용자 이름이나 암호를 클라이언트와 공유하지 않습니다. HoloLens 2에 로그인하려면 전자 메일 및 숫자 PIN이 필요합니다.

두 번째 옵션은 클라이언트를 호스트하는 별도의 테넌트를 만드는 것입니다(이미지 1.1 참조).

**이미지 1.1**

![서비스 테넌트 이미지](./images/hololens-service-tenant-image.png)

### 앱을 제한하는 방법

[키오스크](https://docs.microsoft.com/hololens/hololens-kiosk) 모드 및/또는 [WDAC(Windows Defender 응용](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 프로그램 제어)는 응용 프로그램을 제한하는 옵션입니다.

### 암호를 관리하는 방법

1. 암호 만료를 제거합니다. 그러나 이렇게 하면 계정이 손상될 가능성이 높아집니다. NIST 암호 권장은 30-90일마다 암호를 변경하는 것입니다.
1. HoloLens 2 장치의 암호 만료를 90일을 초과할 수 있습니다.
1. 암호를 변경하기 위해 장치를 Contoso로 반환해야 합니다. 그러나 장치가 90일 이상 클라이언트의 공장에 있을 것으로 예상되는 경우 이로 인해 문제가 발생할 수 있습니다.  
1. 여러 클라이언트로 전송되는 장치의 경우 장치를 클라이언트에 전달하기 전에 암호를 다시 설정하십시오.

### 클라이언트가 채팅 기록에 액세스할 수 없는지 확인하는 방법

원격 지원은 각 세션 후 채팅 기록을 지우습니다. 그러나 Microsoft Teams 사용자가 채팅 기록을 사용할 수 있습니다.

> [!NOTE]
> Single Sign-On이 사용하도록 설정되어 있는 경우 [**WDAC를**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)사용하여 브라우저를 사용하지 않도록 설정하는 것이 중요합니다. 외부 클라이언트가 브라우저를 열고 Teams의 웹 버전을 사용하는 경우 클라이언트는 통화/채팅 기록에 액세스할 수 있습니다.

## 일반 배포 권장 사항 및 지침

HoloLens 2 배포 단계에는 다음이 권장됩니다.

1. 최신 [HoloLens OS](https://aka.ms/hololens2download) 릴리스를 기본 빌드로 사용
1. 사용자 기반 또는 장치 기반 라이선스를 할당합니다.
    1. 사용자 기반 라이선스와 장치 기반 라이선스는 모두 다음 단계를 따릅니다.
        1. [AAD에서 그룹을](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 만들고 HoloLens/RA 사용자에 대한 구성원을 추가합니다.
        1. [이 그룹에 장치 기반](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 또는 사용자 기반 라이선스를 할당합니다.
        1. (선택 사항) MDM 정책에 대한 그룹을 대상으로 할 수 있습니다.

1. 장치는 테넌트에 AAD에 [가입되고,](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)자동 등록되고, 자동 파일럿을 통해 [구성해야 합니다.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. 디바이스의 첫 번째 사용자는 장치 소유자가 됩니다.
    1. 장치가 AAD에 가입된 경우 조인을 수행한 사용자가 장치 소유자가 됩니다.
    1. 자세한 내용은 [장치 소유자를 참조하세요.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [테넌트는](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 테넌트에만 가입할 수 있도록 디바이스를 잠습니다.
    1. **추가 링크:** [테넌트 잠금 CSP.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. 여기에 대한 전역 할당 액세스를 사용하여 키오스크를 [구성합니다.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. 다음과 같은(선택 사항) 기능을 사용 안 하게 하는 것이 좋습니다.
    1. 여기에서 디바이스를 개발자 모드로 전환하는 [기능을 제공합니다.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. HOloLens를 PC에 연결하여 날짜를 복사하여 [USB를 사용하지 않도록 설정하는 기능을 제공합니다.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > USB를 사용하지 않도록 설정하고 USB를 사용하여 장치에 프로비저닝 패키지를 적용하려는 경우 여기에 나열된 지침을 [**따릅니다.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. [WDAC를 사용하여](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) HoloLens 2 장치에서 앱을 허용하거나 검은색 앱을 허용합니다.
1. 설치의 일부로 원격 지원을 최신 버전으로 업데이트합니다. 이 작업을 위한 두 가지 옵션이 있습니다.
    1. 이 수행은 Windows **Microsoft Store --> --> 앱 업데이트로 > 수 있습니다.**
    1. 또 다른 방법은 자동 업데이트를 위해 HoloLens 2를 밤에 플러그 인된 그대로 두는 것입니다.
1. [사용자가 클라이언트 사이트에서](https://docs.microsoft.com/hololens/settings-uri-list) 게스트 네트워크에 연결할 수 있도록 네트워크 설정을 제외한 모든 설정 페이지를 사용하지 않도록 설정합니다.
1. [HoloLens 업데이트 관리](https://docs.microsoft.com/hololens/hololens-updates)
    1. OS 업데이트를 [제어하거나](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 자유롭게 진행할 수 있는 옵션입니다.
1. [일반 장치 제한.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
