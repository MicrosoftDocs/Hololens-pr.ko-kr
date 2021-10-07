---
title: 여러 사용자와 HoloLens 공유
description: 여러 Azure Active Directory 계정 또는 단일 계정을 사용하는 여러 사용자가 공유하도록 HoloLens 구성할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600732"
---
# <a name="share-your-hololens-with-multiple-people"></a>여러 사용자와 HoloLens 공유

## <a name="overview"></a>개요

기업은 종종 여러 공유 HoloLens 디바이스에 투자합니다. HoloLens 사용하는 방법은 개별 요구 사항에 따라 전반적으로 유연합니다. 다음은 몇 가지 다중 사용자 환경의 예입니다.

- HoloLens 2 디바이스는 각 디바이스에서 일관된 회사 애플리케이션 포트폴리오를 통해 HoloLens 2 Windows Autopilot을 통해 설정됩니다. 다른 Azure AD 그룹을 대상으로 하는 몇 가지 다른 키오스크 프로필을 설정했습니다. 각 사용자는 FIDO2 키를 사용하여 HoloLens 로그인하고 자신의 Azure AD 계정에 로그인하며 맞춤형 환경을 제공합니다.
- ISV(독립 소프트웨어 공급업체)는 D365 Remote Assist 및 LOB(LOB) 애플리케이션이 있는 HoloLens 2 디바이스를 고객의 회사에 대여합니다. 이러한 디바이스는 LOB 앱 및 Remote Assist 포함하는 키오스크에 대해 구성되며 여러 최종 사용자 간에 공유됩니다. WDAC는 설정 앱 및 Microsoft Edge 시작하지 못하게 하는 데 사용됩니다. 임대에 포함된 USB-C 배터리 팩은 여러 교대 근무 동안 디바이스를 완전히 충전할 수 있도록 합니다.
- 엔터프라이즈의 최종 사용자가 새 디바이스를 연결할 수 있도록 디바이스에서 Bluetooth 조정하려고 하지만 페이지 설정 표시 유형 정책을 사용하여 디바이스 페이지를 볼 수 없도록 제한합니다. 동일한 HoloLens 여러 위치에서 Remote Assist 사용할 수 있도록 Wi-Fi 같은 다른 페이지에 대한 액세스가 여전히 허용됩니다.

## <a name="best-practices"></a>모범 사례

디바이스 공유를 계획할 때 비즈니스 요구 사항에 따라 디바이스 환경을 최적화하기 위한 몇 가지 고려 사항이 있습니다.

- [ID 및 인증](#identity-and-authentication)
- [디바이스 관리](#device-management)
- [고급 디바이스 관리 - 키오스크 및 WDAC](#advanced-device-management---kiosk-and-wdac)
- [물리적 관리](#physical-management)

### <a name="identity-and-authentication"></a>[ID 및 인증](hololens-identity.md)

디바이스에 여러 계정을 보유할 계획인 경우 모든 인증 모드의 Azure AD 계정을 갖게 됩니다. 이러한 인증 방법은 아이리스 및 FIDO2 키를 포함하여 [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)를 기반으로 합니다.

- FIDO 2 보안 키는 여러 디바이스, 많은 사용자가 있거나 지속적으로 새 디바이스를 사용하는 경우에 매우 좋습니다.
- 사용자가 10명 이하인 경우 Iris는 이전에 동일한 디바이스에 로그인한 사용자를 로그인하는 빠른 솔루션입니다.

### <a name="device-management"></a>[디바이스 관리](hololens-csp-policy-overview.md)

디바이스가 사용자 간에 공유되는 경우 디바이스 제한을 사용할 가능성이 높습니다. 디바이스 관리를 사용하면 사용자가 디바이스를 더 잘 사용하거나, 업데이트를 관리하거나, 디바이스가 수행할 수 있는 작업을 제한할 수 있도록 일부 정책을 설정할 수 있습니다. 일반적인 디바이스 제한 [사항을](hololens-common-device-restrictions.md)검토하고 이러한 권장 사항이 조직에 적합한지 확인하는 것이 좋습니다. 사용하려는 정책을 알고 있으면 [Microsoft의 MDM(Endpoint Manager)](hololens-mdm-configure.md) 또는 프로비저닝 패키지를 통해 정책을 적용할 수 있습니다.

### <a name="advanced-device-management---kiosk-and-wdac"></a>고급 디바이스 관리 - [키오스크](hololens-kiosk.md) 및 [WDAC](windows-defender-application-control-wdac.md)

경우에 따라 최종 사용자가 액세스할 수 있는 애플리케이션을 제한할 수 있습니다. [키오스크 모드](hololens-kiosk.md)를 사용하여 시작 메뉴에서 사용자에게 표시할 앱을 제한할 수 있습니다. 키오스크는 사용자, Azure 그룹 또는 특수 사용자 유형에 따라 다른 시작 메뉴를 표시하도록 구성할 수 있습니다. 이러한 방문자 또는 디바이스 소유자 제외 여러 앱을 선택하거나 단일 앱만 선택할 수 있습니다. 다중 앱 키오스크는 한 앱이 다른 앱을 시작하는 것을 중지하지 않으므로 스토어 또는 다른 앱을 사용할 수 있는 경우 사용자는 다른 앱을 계속 시작할 수 있습니다.

[또한 WDAC(Windows Defender Application Control)를](windows-defender-application-control-wdac.md) 사용하여 앱 또는 서비스의 시작을 완전히 중지하여 앱을 제한하는 것이 좋습니다. WDAC는 HoloLens UI를 변경하지 않고 차단된 앱을 시작할 수 없으므로 키오스크와 다릅니다.

[페이지 설정 표시 유형은](settings-uri-list.md) 디바이스에 제한을 추가하는 또 다른 방법입니다. 설정 앱의 일부 페이지에 대한 액세스 권한을 사용자에게 부여해야 하는 경우 페이지 설정 표시 유형만 사용하여 액세스를 제한할 수 있습니다. 예를 들어 사용자가 Wi-Fi를 변경해야 하지만 계정 페이지에 액세스하지 않으려는 경우에 유용합니다.

### <a name="physical-management"></a>물리적 관리

여러 사용자 간에 디바이스를 공유하는 경우 몇 가지 물리적 고려 사항이 있습니다.

- 디바이스가 교대 근무 간에 요금을 청구하는지 확인합니다.
- 교대 근무에 디바이스가 필요하고 여러 교대 근무를 지속해야 하는 경우 디바이스가 여전히 열 방향 관리에 따라 상당한 요금이 부과되는 동안 교대 근무 시작 시 외부 배터리를 사용하는 [것이 좋습니다.](hololens2-charging.md#managing-heat)
- 디바이스를 저장할 때 디바이스를 네트워크에 연결하고 연결합니다. 이는 OS 및 앱 업데이트를 보장하는 가장 좋은 방법입니다.
- 사용자 간에 [디바이스를 정리하는](hololens2-maintenance.md) 방법을 고려합니다.
- 단일 사용자에 대해 공유 PIN/암호를 사용하는 경우 단일 공유 사용자가 있는 디바이스의 경우 디바이스 쪽에 PIN/암호를 배치하지 마세요.
- 단일 공유 사용자가 있는 여러 디바이스의 경우 다양한 PIN/암호를 사용합니다.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>각각 자신의 계정을 사용하여 여러 사람과 공유

Azure AD(개별 Azure Active Directory) 계정은 HoloLens 2 사용자에게 선호되고 가장 안전한 ID 사용 사례입니다. 자신의 Azure AD 계정을 사용하는 경우 여러 사용자가 각각 자신의 사용자 설정 및 사용자 데이터를 디바이스에 유지할 수 있습니다. 한 번에 한 명의 사용자만 로그인할 수 있습니다. 사용자가 로그인하면 HoloLens 이전 사용자를 로그인합니다.

여러 사람이 HoloLens 자신의 계정을 사용할 수 있도록 하려면 다음 단계에 따라 구성합니다.

1. [디바이스를 설정할](hololens2-start.md)때 **내 직장 또는 학교 소유를** 선택하고 Azure AD 계정을 사용하여 로그인합니다.
1. 설정을 완료한 후 계정 설정(설정 > 계정)에 **다른 사용자가** 포함되어 있는지 확인합니다.

> [!NOTE]
> 디바이스가 Azure AD 계정으로 설정되지 않은 경우 [다시 설정하거나 다시](hololens-recovery.md) 설정하고 제대로 설정해야 합니다.

HoloLens 사용하려면 각 사용자가 다음 단계를 수행합니다.

1. 다른 사용자가 디바이스를 사용하고 있는 경우 다음 옵션 중 하나를 선택합니다.
   - 전원 단추를 한 번 눌러 대기 상태로 이동한 다음 전원 단추를 다시 눌러 잠금 화면으로 돌아갑니다.
   - **시작 메뉴** 사용자 타일을 선택하거나 **전원 메뉴에서** 로그아웃을 선택하여 현재 사용자를 로그아웃합니다.

1. Azure AD 계정 자격 증명을 사용하여 디바이스에 로그인합니다.  
    - 디바이스를 처음 사용하는 경우 HoloLens 자신의 눈에 [보정하라는](hololens-calibration.md) 메시지가 표시됩니다.
    - 이전에 디바이스를 사용한 경우:
        - [Holographic 버전 20H2, 빌드 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) 이상과 Windows 디스플레이는 품질 및 편안한 보기 환경을 위해 원활하게 조정됩니다.
        - 이전 빌드는 눈에 맞게 조정하기 위해 수동 보정이 필요합니다.

> [!TIP]
> 사용자가 디바이스에 로그인하지 않은 경우 더 빠른 로그인을 위해 다음 두 가지 방법 중 하나를 시도합니다.
>
> - **FIDO 2 보안 키:** FIDO2 보안 키가 자동으로 인식되며 사용자가 사용자 자격 증명을 입력하거나 MFA를 사용할 필요가 없습니다. 새 디바이스에서 로그인하는 가장 빠른 방법입니다.
> - **웹 인증:** 새 디바이스에 로그인할 때 **다른 디바이스에서 로그인** 링크를 선택하면 [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) 디바이스에서 사용자로 로그인하거나 편의를 위해 키보드를 사용하여 사용자 이름과 암호를 입력하는 데 사용할 수 있는 9자 코드가 생성됩니다.

디바이스 사용자 목록을 보거나 디바이스에서 사용자를 제거하려면 **설정**  >  **계정**  >  **기타 사용자** 로 이동합니다.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>동일한 계정을 사용하여 여러 사람과 공유

여러 사용자가 단일 사용자 계정을 사용하는 동안 HoloLens 디바이스를 공유할 수도 있습니다. HoloLens 사용자가 개별 ID(Azure AD 계정)를 사용하여 디바이스에 로그인하는 것이 좋지만 일부 조직에서는 이 옵션이 아닙니다.

다음 두 가지 공유 디바이스 메서드를 사용할 수 있습니다.

- **1개 디바이스를 공유하는 여러 최종 사용자** - 모든 직원이 디바이스를 사용할 수 있는 지정된 공간에 HoloLens 디바이스가 할당됩니다. 예를 들어 클린룸 또는 방이 있는 도구 모음이 있습니다.

- **여러 디바이스를 공유하는 여러 최종 사용자** - HoloLens 디바이스는 직원이 모든 디바이스를 사용할 수 있는 공유 스토리지 공간에 있습니다. 예를 들어 오일 장비 또는 자동차 대리점/창고가 있습니다.

새 사용자가 동일한 계정을 로그인 상태로 유지하면서 처음으로 디바이스를 켜면 디바이스는 사용자에게 보기 환경을 신속하게 보정하고 개인화하라는 메시지를 표시합니다. 디바이스는 보정 정보를 저장하여 각 사용자의 보기 환경의 품질과 편의성을 자동으로 최적화합니다. 사용자는 디바이스를 다시 보정할 필요가 없습니다.
