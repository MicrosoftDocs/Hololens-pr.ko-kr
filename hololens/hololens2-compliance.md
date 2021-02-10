---
title: HoloLens 2 규정 준수 및 GDPR
description: GDPR 설명서
keywords: HoloLens, GDPR, 개인 정보, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324878"
---
# HoloLens 2 개인정보처리방침

GDPR의 핵심 요소 중 하나는 '디자인에 따라 데이터 보호'입니다. 이 개념은 이식성, 무제한 인터넷 연결 및 개방형 통신 채널 때문에 HoloLens 2와 같은 모바일 장치에 특히 적용됩니다. 그 결과, HoloLens 2의 보안은 Microsoft의 개인 정보 보호 및 [GDPR](https://privacy.microsoft.com/)규정에 대한 Microsoft의 접근 방식을 통합하여 혁신적인 고급 보안 및 개인 정보 보호 기능을 종단으로 제공하기 위해 다시 디자인되어 있습니다. [](https://docs.microsoft.com/hololens/security-architecture)

 >[!NOTE]
> 이 문서는 HoloLens(1세대)에는 적용되지 않습니다.

## 개인 정보 개요

HoloLens 2는 몰입형 혼합 현실 환경에서 앱 및 솔루션을 실행하는 Windows Holographic을 실행하는 자체 포함된 Windows 컴퓨터입니다. 보안 오프라인 장치로 사용되거나 조직 내에서 관리되는 장치로 [배포할](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) 수 있습니다. HoloLens 2 및 Microsoft에서 데이터를 사용 및 보호하는 방법을 이해하기 위해 다음 링크를 참조하세요.
1. Microsoft 개인 정보 취급 [방침 - HoloLens](https://privacy.microsoft.com/privacystatement) – 왼쪽 탐색 메뉴에서 **엔터프라이즈** 및 개발자 섹션을 확장하고 Enterprise 및 개발자 소프트웨어 및 어플라이언스를 **선택합니다.** **HoloLens 섹션으로** 이동하세요.
2.  [Windows 10 및 온라인 서비스](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 및 개인 정보 취급 방침 준수 가이드](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Intune의 개인 정보 및 개인 데이터](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## 네트워크 보안
HoloLens 2 [일반](https://docs.microsoft.com/hololens/common-scenarios)배포 시나리오에 따라 데이터는 법적/규정 표준 통합과 함께 [Azure의](https://docs.microsoft.com/azure/compliance/) 세계적 규정 준수로 보호됩니다. Azure AD 및 Dynamics 365 Remote Assist를 신규로 하는 경우 GDPR에 대한 Azure 및 [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)책임 준비 검사 목록을 참조하세요.

또한 Windows Defender 방화벽은 장치 연결을 보호하는 중요한 기능을 제공합니다. HoloLens 2를 사용하면 방화벽이 항상 사용되고 있으며 이것을 프로그래밍 방식으로 또는 UI를 통해 사용하지 않도록 설정할 방법이 없습니다. [Intune을](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)사용하여 HoloLens 2를 관리되는 장치로 배포할 때 더 많은 준수 기능을 Mobile Threat Defense 솔루션으로 [Microsoft Intune과](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) 통합하여 더 많은 준수 기능을 사용할 수 있습니다. 

HoloLens 2 보안 및 [아키텍처에 대해 자세히 알아보세요.](https://docs.microsoft.com/hololens/security-architecture)

## OS 보안
업데이트는 자동으로(기본적으로) 수행되며, HoloLens 2는 Windows Holographic의 최신 릴리스 및 설치된 앱을 사용하여 항상 최신으로 업데이트됩니다. OS를 안전하게 디자인하는 방법에 대한 자세한 내용은 다음을 참조합니다.
1. [상태 구분 및 격리](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [관리자가 없는 운영 체제](https://docs.microsoft.com/hololens/security-adminless-os)
1. [암호 사용 제한](https://docs.microsoft.com/hololens/security-limiting-password-use)

## 물리적 보안
HoloLens 2에는 BitLocker 암호화로 보호되는 플래시 [메모리가 있습니다.](https://docs.microsoft.com/hololens/security-encryption-data-protection) 고급 복구 도우미를 사용하여 디바이스 및 [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) 해당 로컬 데이터를 오프라인으로 플래시하거나 관리되는 장치로 배포된 경우 MDM을 통해 원격으로 지워야 합니다.

## 데이터 보호
Windows 업데이트는 자동으로 실행되며(기본적으로) [Azure 통합은](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) 자체와 클라우드 간에 이동하는 데이터를 보호합니다. 

HoloLens 2를 외부 클라이언트에 배포할 때 [Dynamics 365 Remote Assist는](https://docs.microsoft.com/hololens/hololens2-deployment-guide) 중요한 회사 데이터와 리소스를 분리하여 안전하게 보호합니다. 

OOBE 중에 MDM 또는 사용자가 Microsoft와 진단 데이터 공유를 수동으로 구성할 수 있습니다. 선택적 진단 데이터와 필수 진단 데이터의 두 가지 선택이 있습니다. 문제 해결을 위해 나중에 원래 진단 설정을 변경해야 하는 경우 사용자가 설정 **->** 개인 정보 -> 진단 & 피드백 또는 관리되는 장치인 경우 IT 관리자(MDM)에서 변경할 수 있습니다. [Windows 10의 진단, 피드백 및 개인 정보](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)보호에 대해 더 많은 정보를 참조합니다.

> [!Important]
> 장치 진단 로그에는 사용자가 일반적인 작업 중에 시작하는 프로세스 또는 응용 프로그램과 같은 PII(개인 식별이 가능한 정보)가 포함됩니다. 여러 사용자가 HoloLens 장치를 공유하는 경우(예: 사용자가 다른 Microsoft Azure AD(Azure Active Directory) 계정을 사용하여 동일한 장치에 로그인)진단 로그에 여러 사용자에게 적용되는 PII 정보가 포함될 수 있습니다.

 

HoloLens 2에서 진단 데이터를 수집하기 위한 몇 가지 수집 방법 및 데이터 보존 정책이 있습니다. [](https://docs.microsoft.com/hololens/hololens-diagnostic-logs)  Microsoft에서 진단 데이터를 수집하고 사용하는 방법에 대한 자세한 내용은 Microsoft 개인 정보 취급 방침 [- 진단 -](https://privacy.microsoft.com/privacystatement) 왼쪽 탐색 메뉴에서 **Windows를** 확장하고 **진단을 선택합니다.** 진단 **섹션으로** 이동하세요.
