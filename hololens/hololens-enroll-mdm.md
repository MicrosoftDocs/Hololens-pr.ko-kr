---
title: MDM에 HoloLens 등록
description: 여러 장치를 쉽게 관리 하기 위해 MDM (모바일 장치 관리)에 HoloLens를 등록 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309715"
---
# <a name="enroll-hololens-in-mdm"></a>MDM에 HoloLens 등록

[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)같은 솔루션을 사용 하 여 여러 Microsoft HoloLens 장치를 동시에 관리할 수 있습니다. 설정을 관리 하 고, 설치할 앱을 선택 하 고, 조직의 요구에 맞게 조정 된 보안 구성을 설정할 수 있습니다. [Holographic를 사용 하 Microsoft Intune 여 Windows를 실행 하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [windows Holographic에서 지원 되는 csp (구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), windows [Holographic for Business에서 지 원하는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조 하세요.

> [!NOTE]
> VPN, Bitlocker 및 키오스크 모드 기능을 비롯 한 MDM (모바일 장치 관리)은 [비즈니스용 Windows Holographic로 업그레이드](hololens1-upgrade-enterprise.md)하는 경우에만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

 조직에서는 HoloLens 장치를 관리 하기 위해 MDM (모바일 장치 관리)을 설정 해야 합니다. MDM 공급자를 Microsoft Intune 하거나 Microsoft MDM Api를 사용 하는 타사 공급자를 사용할 수 있습니다.
 
## <a name="different-ways-to-enroll"></a>다양 한 등록 방법

OOBE 또는 사후 로그인 중에 선택 된 [id](hololens-identity.md) 유형에 따라 다양 한 등록 방법이 있습니다.

- Id가 Azure AD 인 경우 OOBE 또는 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **연결** 단추 중 하나입니다.
    - Azure AD의 경우 [자동 MDM 등록](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 은 azure ad가 등록 url로 구성 된 경우에만 발생 합니다.
     
- Id가 Azure AD이 고 장치가 특정 구성 프로필이 할당 된 Intune MDM 서버에 미리 등록 된 경우 Azure AD-Join 및 [자동 MDM 등록](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 은 OOBE 중에 발생 합니다.
    - [19041.1103 + 빌드에서](hololens-release-notes.md#windows-holographic-version-2004)사용할 수 있는 [Autopilot flow](hololens2-autopilot.md) 라고도 합니다.
    

- Id가 MSA 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **연결** 단추를 사용 합니다.
    - AWA (회사 계정 추가) 흐름이 라고도 합니다.
- Id가 로컬 사용자 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **에서 장치 관리 링크만 등록** 을 사용 합니다.
    - 순수한 MDM 등록 흐름이 라고도 합니다.

장치가 MDM 서버에 등록 되 면 장치 관리에 장치가 등록 된 것으로 설정 앱이 반영 됩니다.

## <a name="auto-enrollment-in-mdm"></a>MDM에서 자동 등록

조직에서 [Azure Premium 구독](https://azure.microsoft.com/overview/)을 사용 하는 경우, 인증을 위해 azure ad 토큰을 허용 하는 mdm 솔루션 (Microsoft Intune 현재 Azure Active Directory (azure ad) 및 azure ad 토큰을 사용 하는 경우, IT 관리자는 사용자가 azure ad 계정으로 로그인 한 후 mdm 등록을 자동으로 허용 하도록 azure ad를 구성할 수 있습니다. [Azure AD 등록을 구성 하는 방법을 알아봅니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

자동 등록을 사용 하도록 설정 하면 추가 수동 등록이 필요 하지 않습니다. 사용자가 Azure AD 계정으로 로그인 하면 첫 실행 환경을 완료 한 후 장치가 MDM에 등록 됩니다.

장치가 Azure AD에 가입 된 경우 [장치 소유자](security-adminless-os.md#device-owner)를 고려 하는 사용자에 게 영향을 줄 수 있습니다.

## <a name="unenroll-hololens-from-intune"></a>Intune에서 HoloLens 등록 취소

등록 방법에 따라 장치를 등록 취소 수 없습니다.

Azure AD 계정 또는 Autopilot를 사용 하 여 장치를 등록 한 경우 Intune에서 등록 취소 수 없습니다. Azure AD에서 HoloLens를 가입 해제 하거나 다른 Azure AD 테 넌 트에 다시 참여 시키려면 장치를 [다시 설정/경감 하기 위해](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 해야 합니다.

장치가 회사 계정을 추가 하는 MSA 계정이 나 장치 관리에만 등록 된 로컬 계정에서 등록 된 경우 장치 등록을 취소할 수 있습니다. 시작 메뉴를 열고 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  *계정*  ->  **연결 끊기** 단추를 선택 합니다.