---
title: MDM에 HoloLens 등록
description: 여러 디바이스를 보다 쉽게 관리하기 위해 MDM(모바일 디바이스 관리)에 HoloLens 등록하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640409"
---
# <a name="enroll-hololens-in-mdm"></a>MDM에 HoloLens 등록

Microsoft Intune 같은 솔루션을 사용하여 여러 [Microsoft HoloLens](/intune/windows-holographic-for-business)디바이스를 동시에 관리할 수 있습니다. 설정을 관리하고, 앱을 선택하여 조직의 요구에 맞는 보안 구성을 설치하고 설정할 수 있습니다. Microsoft Intune, Windows [Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)및 Windows Holographic for Business [에서 지원하는 정책을](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)Windows [Holographic을 실행하는 디바이스 관리를](/intune/windows-holographic-for-business)참조하세요.

> [!NOTE]
> VPN, Bitlocker 및 키오스크 모드 기능을 포함한 MDM(모바일 디바이스 관리)은 [Windows Holographic for Business 로 업그레이드할](hololens1-upgrade-enterprise.md)때만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

 조직에서는 HoloLens 디바이스를 관리하기 위해 MDM(모바일 장치 관리)을 설정해야 합니다. MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.
 
## <a name="different-ways-to-enroll"></a>등록하는 다양한 방법

OOBE 또는 로그인 후 선택한 [ID](hololens-identity.md) 유형에 따라 다양한 등록 방법이 있습니다.

- ID가 Azure AD인 경우 OOBE 또는 **설정 앱** 액세스 작업 또는 학교 커넥트 단추 중  ->    ->   하나입니다.
    - Azure AD의 경우 [자동 MDM 등록은](hololens-enroll-mdm.md#auto-enrollment-in-mdm) Azure AD가 등록 URL로 구성된 경우에만 발생합니다.
     
- ID가 Azure AD이고 디바이스가 할당된 특정 구성 프로필이 있는 Intune MDM 서버에 미리 등록된 경우 OOBE 중에 Azure AD-Join [및 자동 MDM 등록이](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 발생합니다.
    - [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+(19041.1103 이상에서](hololens-release-notes.md#windows-holographic-version-2004)사용 가능)이라고도 합니다.
    

- ID가 MSA인 경우 **설정 앱**  ->  **액세스 작업 또는 학교**  ->  **커넥트** 단추를 사용하세요.
    - AWA(작업 계정 추가) 흐름이라고도 합니다.
- ID가 로컬 사용자인 경우 디바이스 관리 링크에서만 **설정 앱** 액세스  ->  **작업 또는 학교**  ->  **등록을** 사용하세요.
    - 순수 MDM 등록 흐름이라고도 합니다.

디바이스가 MDM 서버에 등록되면 이제 디바이스가 디바이스 관리에 등록되었다는 설정 앱이 반영됩니다.

## <a name="auto-enrollment-in-mdm"></a>MDM의 자동 등록

조직에 [Azure Premium 구독이](https://azure.microsoft.com/overview/)있는 경우 는 인증을 위해 Azure AD 토큰을 수락하는 Azure Active Directory(Azure AD) 및 MDM 솔루션을 사용하고 있습니다(현재 Microsoft Intune 및 AirWatch에서만 지원됨). IT 관리자는 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록을 자동으로 허용하도록 Azure AD를 구성할 수 있습니다. [Azure AD 등록을 구성하는 방법을 알아봅니다.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

자동 등록을 사용하도록 설정하면 추가 수동 등록이 필요하지 않습니다. 사용자가 Azure AD 계정으로 로그인하면 첫 번째 실행 환경을 완료한 후 디바이스가 MDM에 등록됩니다.

디바이스가 Azure AD 조인된 경우 디바이스 [소유자](security-adminless-os.md#device-owner)를 고려한 사람에게 영향을 줄 수 있습니다.

## <a name="unenroll-hololens-from-intune"></a>Intune에서 HoloLens 등록 취소

등록 방법에 따라 디바이스 등록 취소를 사용할 수 없습니다.

디바이스가 Azure AD 계정 또는 Autopilot에 등록된 경우 Intune에서 등록을 취소할 수 없습니다. Azure AD에서 HoloLens 조인을 해제하거나 Azure AD 테넌트에서 다른 테넌트로 다시 조인하려면 디바이스를 [다시 설정/리플래시해야](hololens-recovery.md#reset-the-device) 합니다.

디바이스가 작업 계정을 추가한 MSA 계정 또는 디바이스 관리에만 등록된 로컬 계정에서 등록된 경우 디바이스 등록을 취소할 수 있습니다. 시작 메뉴 열고 앱 액세스   ->  **작업 또는 학교**  ->  *사용자계정*  ->  **연결 끊기** 단추를 설정 선택합니다.