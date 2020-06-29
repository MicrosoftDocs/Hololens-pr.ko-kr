---
title: MDM에 HoloLens 등록
description: 여러 장치를 더 쉽게 관리하기 위해 MDM(모바일 장치 관리)에 HoloLens를 등록합니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828693"
---
# MDM에 HoloLens 등록

[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)과 같은 솔루션을 사용 하 여 여러 Microsoft HoloLens 장치를 동시에 관리할 수 있습니다. 설정을 관리하고 앱을 선택해서 설치하며 조직의 요구에 부합하는 보안 구성을 설정할 수 있습니다. [Microsoft Intune와 Windows Holographic을 실행하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [Windows Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 및 [Windows Holographic for Business에서 지원되는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조하세요.

> [!NOTE]
> VPN, Bitlocker, 및 키오스크 모드 기능을 포함하여 모바일 디바이스 관리(MDM)는 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 사용할 수 있습니다.

## 요구 사항

 조직에서는 HoloLens 장치를 관리 하기 위해 MDM (모바일 디바이스 관리)을 설정 해야 합니다. MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.

## MDM에 자동 등록

조직이 Azure AD(Azure Active Directory) 및 인증을 위해 AAD 토큰을 허용하는 MDM 솔루션(현재 Microsoft Intune 및 AirWatch에서만 지원됨)을 사용하는 경우, IT 관리자는 Azure AD를 구성하여 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록이 자동으로 진행되도록 할 수 있습니다. [Azure AD 등록을 구성하는 방법을 알아봅니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

자동 등록을 활성화하는 경우 수동 등록이 추가로 필요하지 않습니다. 사용자가 Azure AD 계정으로 로그인하면 장치는 첫 실행 경험이 완료된 후 MDM에 등록됩니다.

## 설정 앱을 통해 등록

 첫 실행 경험 동안 장치가 MDM에 등록되지 않는 경우 사용자는 설정 앱을 사용하여 조직의 MDM 서버를 통해 장치를 수동으로 등록할 수 있습니다.

1. **설정** > **계정** > **회사 액세스**로 이동합니다.
1. **장치 관리에 등록**을 선택하고 조직 계정을 입력합니다. 조직의 로그인 페이지로 다시 이동하게 됩니다.
1. MDM 서버에 대한 인증이 성공하면 성공 메시지가 표시됩니다.

이제 장치가 MDM 서버에 등록되었습니다. 이제 설정 앱에서 장치 관리에 장치가 등록되었음을 확인할 수 있습니다.

## Intune의 HoloLens 등록 해제

Intune에서 원격으로 HoloLens를 [등록 해제](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows)할 수 없습니다. 관리자가 MDM을 사용하여 장치 등록을 해제할 경우 장치는 Intune 대시보드에서 삭제됩니다.
