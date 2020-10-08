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
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102327"
---
# MDM에 HoloLens 등록

[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)과 같은 솔루션을 사용 하 여 여러 Microsoft HoloLens 장치를 동시에 관리할 수 있습니다. 설정을 관리하고 앱을 선택해서 설치하며 조직의 요구에 부합하는 보안 구성을 설정할 수 있습니다. [Microsoft Intune와 Windows Holographic을 실행하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [Windows Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 및 [Windows Holographic for Business에서 지원되는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조하세요.

> [!NOTE]
> VPN, Bitlocker, 및 키오스크 모드 기능을 포함하여 모바일 디바이스 관리(MDM)는 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 사용할 수 있습니다.

## 요구 사항

 조직에서는 HoloLens 장치를 관리 하기 위해 MDM (모바일 디바이스 관리)을 설정 해야 합니다. MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.
 
## 다양 한 등록 방법

OOBE 또는 post 로그인 중에 선택한 id 유형에 따라 다양 한 등록 방법이 있습니다. HoloLens의 각 Id 유형에 대 한 자세한 내용을 보려면 [이 페이지](hololens-identity.md)를 방문 하세요.

- Id가 AAD 이면 OOBE 또는 **설정 앱**  ->  **액세스 작업 또는 학교**  ->  **연결** 단추 중 하나입니다.
    - AAD의 경우 자동 MDM 등록은 AAD가 등록 Url로 구성 된 경우에만 발생 합니다.
- Id가 AAD이 고 장치가 지정 된 특정 구성 프로필이 있는 Intune MDM 서버에 미리 등록 된 경우 OOBE 중에 AAD 조인과 등록이 자동으로 수행 됩니다.
    - [19041.1103 + 빌드에서](hololens-release-notes.md#windows-holographic-version-2004)사용할 수 있는 [Autopilot 흐름이](hololens2-autopilot.md) 라고도 합니다.
- Id가 MSA 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **연결** 단추를 사용 합니다.
    - AWA (작업 계정 추가) 흐름이 라고도 합니다.
- Id가 로컬 사용자 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **등록을 장치 관리 링크 에서만** 사용 합니다.
    - 순수한 MDM 등록 흐름이 라고도 합니다.

디바이스를 MDM 서버에 등록 한 후에는 설정 앱이 장치 관리에 디바이스를 등록 했음을 반영 합니다.

## MDM에 자동 등록

조직이 Azure AD(Azure Active Directory) 및 인증을 위해 AAD 토큰을 허용하는 MDM 솔루션(현재 Microsoft Intune 및 AirWatch에서만 지원됨)을 사용하는 경우, IT 관리자는 Azure AD를 구성하여 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록이 자동으로 진행되도록 할 수 있습니다. [Azure AD 등록을 구성하는 방법을 알아봅니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

자동 등록을 활성화하는 경우 수동 등록이 추가로 필요하지 않습니다. 사용자가 Azure AD 계정으로 로그인하면 장치는 첫 실행 경험이 완료된 후 MDM에 등록됩니다.

디바이스가 AAD에 연결 되 면 [장치 소유자](security-adminless-os.md#device-owner)에 게 영향을 줄 수 있습니다.

## Intune의 HoloLens 등록 해제

장치 unenrolling에 대해 자세히 알아보려면 [이 페이지](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)를 방문 하세요. 
