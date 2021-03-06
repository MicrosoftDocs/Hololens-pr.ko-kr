---
title: MDM에 HoloLens 등록
description: 여러 장치를 보다 쉽게 관리하기 위해 MDM(모바일 장치 관리)에 HoloLens를 등록하는 방법을 학습합니다.
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
ms.openlocfilehash: 5613c69bda8bbf70722a050ac5ce4ebeab95d332
ms.sourcegitcommit: 771e53feefbcc6bce18577515ad7d3f6a7f33840
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399386"
---
# <a name="enroll-hololens-in-mdm"></a>MDM에 HoloLens 등록

Microsoft [Intune과](https://docs.microsoft.com/intune/windows-holographic-for-business)같은 솔루션을 사용하여 동시에 여러 Microsoft HoloLens 장치를 관리할 수 있습니다. 설정을 관리하고 앱을 선택해서 설치하며 조직의 요구에 부합하는 보안 구성을 설정할 수 있습니다. [Microsoft Intune와 Windows Holographic을 실행하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [Windows Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 및 [Windows Holographic for Business에서 지원되는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조하세요.

> [!NOTE]
> VPN, Bitlocker, 및 키오스크 모드 기능을 포함하여 모바일 디바이스 관리(MDM)는 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

 조직에서 HoloLens 장치를 관리하려면 MDM(모바일 장치 관리)을 설정해야 합니다. MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.
 
## <a name="different-ways-to-enroll"></a>다양한 등록 방법

OOBE 또는 로그인 후 중에 선택한 ID 유형에 따라 다양한 등록 방법이 있습니다. HoloLens의 각 ID 유형에 대한 자세한 내용은 이 페이지를 [방문하세요.](hololens-identity.md)

- Id가 Azure AD인 경우 OOBE **** 또는 설정 앱 액세스 작업 또는 학교 연결 단추  ->  ****  ->  **중** 하나입니다.
    - Azure AD의 경우 자동 MDM 등록은 Azure AD가 등록 URL로 구성된 경우만 발생합니다.
- Id가 Azure AD인 경우 디바이스가 특정 구성 프로필이 할당된 Intune MDM 서버에 사전 등록된 경우 Azure AD-Join 등록이 OOBE 중에 자동으로 수행됩니다.
    - [Autopilot 흐름이라고도](hololens2-autopilot.md) [합니다. 19041.1103+ 빌드에서 사용할 수 있습니다.](hololens-release-notes.md#windows-holographic-version-2004)
- Identity가 MSA인 경우 설정 **앱**액세스 작업 또는 학교 연결  ->  ****  ->  **단추를** 사용합니다.
    - AWA(작업 계정 추가) 흐름이라고도 합니다.
- ID가 로컬 사용자인 경우 장치 관리 링크에서만 설정 **앱**액세스 작업 또는  ->  **학교**  ->  **등록을 사용합니다.**
    - 순수 MDM 등록 흐름이라고도 합니다.

장치가 MDM 서버에 등록된 후 설정 앱은 이제 장치가 장치 관리에 등록된 것을 반영합니다.

## <a name="auto-enrollment-in-mdm"></a>MDM에 자동 등록

조직에서 인증을 위해 Azure AD 토큰을 수락하는 Azure AD(Azure Active Directory) 및 MDM 솔루션을 사용하는 경우(현재 Microsoft Intune 및 AirWatch에서만 지원) IT 관리자는 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록을 자동으로 허용하도록 Azure AD를 구성할 수 있습니다. [Azure AD 등록을 구성하는 방법을 알아봅니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

자동 등록을 활성화하는 경우 수동 등록이 추가로 필요하지 않습니다. 사용자가 Azure AD 계정으로 로그인하면 장치는 첫 실행 경험이 완료된 후 MDM에 등록됩니다.

장치가 Azure AD에 가입된 경우 장치 소유자로 간주하는 사람에 영향을 [줄 수 있습니다.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Intune에서 HoloLens의Enroll Unenroll

HoloLens 2는 Windows 10 장치지만 Intune에서 간단히 사용이이면 안 됩니다. Azure AD에서 HoloLens에 조인을 언하거나 Azure AD 테넌트에 다시 [](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 연결하려면 디바이스를 초기화/리플래시해야 합니다.