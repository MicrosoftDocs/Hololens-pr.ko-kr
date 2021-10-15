---
title: MDM에 HoloLens 등록
description: 여러 장치를 쉽게 관리 하기 위해 MDM (모바일 장치 관리)에 HoloLens를 등록 하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fa114633afe70a11a180c67fedbd40eb423ece99
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034181"
---
# <a name="enroll-hololens-in-mdm"></a>MDM에 HoloLens 등록

[Microsoft Intune](/intune/windows-holographic-for-business)와 같은 솔루션을 사용 하 여 동시에 여러 Microsoft HoloLens 장치를 관리할 수 있습니다. 설정을 관리 하 고, 설치할 앱을 선택 하 고, 조직의 요구에 맞게 조정 된 보안 구성을 설정할 수 있습니다. [Windows Holographic에서 지원 되는 csp (구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)및 [Windows Holographic for Business에서 지 원하는 정책은](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies) [Microsoft Intune를 사용 하 여 Windows Holographic를 실행 하는 장치 관리](/intune/windows-holographic-for-business)를 참조 하세요.

> [!NOTE]
> VPN, Bitlocker 및 키오스크 모드 기능을 비롯 한 MDM (모바일 장치 관리)은 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)하는 경우에만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

 조직에서는 HoloLens 장치를 관리 하기 위해 MDM (모바일 장치 관리)을 설정 해야 합니다. mdm 공급자를 Microsoft Intune 하거나 Microsoft mdm api를 사용 하는 타사 공급자를 사용할 수 있습니다.

## <a name="different-ways-to-enroll"></a>다양 한 등록 방법

OOBE 또는 사후 로그인 중에 선택 된 [id](hololens-identity.md) 유형에 따라 다양 한 등록 방법이 있습니다.

- Identity가 Azure AD 인 경우 OOBE 또는 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **커넥트** 단추 중 하나입니다.
    - Azure AD의 경우 [자동 MDM 등록](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 은 azure ad가 등록 url로 구성 된 경우에만 발생 합니다.

- Id가 Azure AD이 고 장치가 특정 구성 프로필이 할당 된 Intune MDM 서버에 미리 등록 된 경우 Azure AD-Join 및 [자동 MDM 등록](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 은 OOBE 중에 발생 합니다.
    - [19041.1103 + 빌드에서](hololens-release-notes.md#windows-holographic-version-2004)사용할 수 있는 [Autopilot flow](hololens2-autopilot.md) 라고도 합니다.


- id가 MSA 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **커넥트** 단추를 사용 합니다.
    - AWA (회사 계정 추가) 흐름이 라고도 합니다.
- id가 로컬 사용자 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **에서 장치 관리 링크에만 등록** 을 사용 합니다.
    - 순수한 MDM 등록 흐름이 라고도 합니다.

장치가 MDM 서버에 등록 되 면 장치 관리에 장치를 등록 하는 설정 앱이 반영 됩니다.

## <a name="auto-enrollment-in-mdm"></a>MDM에서 자동 등록

조직에서 [azure Premium 구독](https://azure.microsoft.com/overview/)을 보유 하 고 있고 인증을 위해 azure ad 토큰을 허용 하는 MDM 솔루션을 사용 Azure Active Directory 하 고 있는 경우 (현재는 Microsoft Intune 및 진행 중에만 지원 됨), IT 관리자는 사용자가 azure ad를 사용 하 여 로그인 한 후 mdm 등록을 자동으로 허용 하도록 azure ad를 구성할 수 있습니다. 계정일. [Azure AD 등록을 구성 하는 방법을 알아봅니다.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

자동 등록을 사용 하도록 설정 하면 추가 수동 등록이 필요 하지 않습니다. 사용자가 Azure AD 계정으로 로그인 하면 첫 실행 환경을 완료 한 후 장치가 MDM에 등록 됩니다.

장치가 Azure AD에 가입 된 경우 [장치 소유자](security-adminless-os.md#device-owner)를 고려 하는 사용자에 게 영향을 줄 수 있습니다.

## <a name="unenroll-hololens-from-intune"></a>Intune에서 HoloLens 등록 취소

등록 방법에 따라 장치를 등록 취소 수 없습니다.

Azure AD 계정 또는 Autopilot를 사용 하 여 장치를 등록 한 경우 Intune에서 등록 취소 수 없습니다. azure ad에서 HoloLens 가입 해제 하거나 다른 azure ad 테 넌 트에 다시 참여 시키려면 장치를 [다시 설정/경감 하기 위해](hololens-recovery.md#restart-the-device) 해야 합니다.

장치가 회사 계정을 추가 하는 MSA 계정이 나 장치 관리에만 등록 된 로컬 계정에서 등록 된 경우 장치 등록을 취소할 수 있습니다. 시작 메뉴를 열고 **설정 App**  ->  **Access 회사 또는 학교**  ->  *계정*  ->  **연결 끊기** 단추를 선택 합니다.

## <a name="enrollment-troubleshooting"></a>등록 문제 해결

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>사용자에 게 유효한 라이선스가 할당 되었는지 확인

[장치 유형 제한을 확인](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) 하 고 [사용자에 게 유효한 라이선스를 할당](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user) 하는 경우에는 특히 다음 섹션 [Microsoft Intune에서 장치 등록 문제 Windows 문제 해결](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) 을 참조 하세요.

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Windows 장치에서 MDM 등록이 차단 되지 않았는지 확인 합니다.

등록에 성공 하려면 HoloLens 장치를 등록할 수 있는지 확인 해야 합니다. HoloLens는 Windows 디바이스로 간주되므로 배포를 차단할 수 있는 등록 제한이 없어야 합니다. [이 제한 목록을 검토](/mem/intune/enrollment/enrollment-restrictions-set)하고 디바이스를 등록할 수 있는지 확인하세요.