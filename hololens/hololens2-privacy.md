---
title: HoloLens 2 개인 정보 및 데이터 보호
description: 개인 정보 설명서
keywords: HoloLens, GDPR, 개인 정보 보호, PII, 데이터 보호
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033298"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 개인 정보 및 데이터 보호

GDPR의 핵심 요소 중 하나는 '의도적으로 데이터 보호'입니다. 이 개념은 이식성, 무제한 인터넷 연결 및 공개 통신 채널로 인해 HoloLens 2 같은 모바일 디바이스에 특히 적용됩니다. 결과적으로 HoloLens 2 [보안은](/hololens/security-architecture) Microsoft의 개인 정보 보호 및 [GDPR 규정](https://privacy.microsoft.com/)접근 방식을 통합하여 엔드투엔드에 고급의 혁신적인 보안 및 개인 정보 보호를 제공하도록 다시 디자인되었습니다.

 >[!NOTE]
> 이 문서는 HoloLens(1세대)에는 적용되지 않습니다.

## <a name="privacy-overview"></a>개인 정보 개요

HoloLens 2 몰입형 혼합 현실 환경에서 앱과 솔루션을 실행하는 Windows Holographic을 실행하는 자체 포함된 Windows 컴퓨터입니다. 보안 오프라인 디바이스로 사용하거나 조직 내에서 [관리](/mem/intune/fundamentals/windows-holographic-for-business) 디바이스로 배포할 수 있습니다. HoloLens 2 및 Microsoft에서 데이터를 사용하고 보호하는 방법을 이해하려면 다음 링크를 참조하세요.

1. [Microsoft 개인정보처리방침 - HoloLens](https://privacy.microsoft.com/privacystatement) – 왼쪽 탐색 메뉴에서 **Enterprise 및 개발자** 섹션을 확장하고 Enterprise 및 개발자 소프트웨어 및 **어플라이언스를** 선택합니다. **HoloLens** 섹션으로 이동합니다.
2. [Windows 10 및 온라인 서비스](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & 개인 정보 보호 규정 준수 가이드](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune의 개인 정보 및 개인 데이터](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>네트워크 보안
HoloLens 2 일반적인 배포 [시나리오에](/hololens/common-scenarios)따라 데이터는 법률/규정 표준 통합과 함께 [Azure의 세계적 규정 준수로](/azure/compliance/) 보호됩니다. Azure AD 및 Dynamics 365 Remote Assist 경우 [GDPR에 대한 Azure 및 Dynamics 365 책임 준비 검사 목록을](/compliance/regulatory/gdpr-arc-azure-dynamics)참조하세요.

또한 Windows Defender 방화벽은 디바이스 연결을 보호하는 중요한 기능을 제공합니다. HoloLens 2를 사용하면 방화벽이 항상 사용되고 있으며 이것을 프로그래밍 방식으로 또는 UI를 통해 사용하지 않도록 설정할 방법이 없습니다. HoloLens 2 [Intune을](/mem/intune/protect/device-compliance-get-started)사용하여 관리 디바이스로 배포되는 경우 Mobile Threat Defense 솔루션으로 [Microsoft Intune 엔드포인트에](/mem/intune/protect/advanced-threat-protection) 대한 통합을 통해 더 많은 규정 준수 기능을 사용할 수 있습니다.

HoloLens 2 [보안 및 아키텍처에](/hololens/security-architecture)대해 자세히 알아봅니다.

## <a name="os-security"></a>OS 보안
업데이트는 자동으로 수행되므로(기본적으로) HoloLens 2 항상 최신 릴리스의 Windows Holographic 및 설치된 앱을 사용하여 최신 상태로 업데이트됩니다. OS를 안전하게 디자인하는 방법에 대한 자세한 내용은 다음을 참조하세요.

1. [상태 구분 및 격리](/hololens/security-state-separation-isolation)
1. [관리자가 없는 운영 체제](/hololens/security-adminless-os)
1. [암호 사용 제한](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>물리적 보안
HoloLens 2 [BitLocker 암호화로](/hololens/security-encryption-data-protection)보호되는 플래시 메모리가 있습니다. 디바이스 및 해당 로컬 데이터는 [고급 복구 도우미를](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) 사용하여 오프라인으로 플래시하거나 관리 디바이스로 배포된 경우 MDM을 통해 원격으로 초기화할 수 있습니다.

## <a name="data-protection"></a>데이터 보호
Windows 업데이트는 기본적으로 자동으로 실행되며 [Azure 통합은](/hololens/security-encryption-data-protection#Azure-integration) 자체와 클라우드 간에 이동하는 데이터를 보호합니다.

외부 클라이언트에 HoloLens 2 배포할 때 [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) 중요한 회사 데이터와 리소스가 분리되고 안전하도록 합니다.

Microsoft와의 진단 데이터 공유는 OOBE 중에 MDM 또는 사용자가 수동으로 구성할 수 있습니다. 선택적 진단 데이터와 필수 진단 데이터의 두 가지 선택 항목이 있습니다. 문제 해결을 위해 나중에 원래 진단 설정을 변경해야 하는 경우 관리 디바이스인 경우 **설정 -> Privacy -> Diagnostics & Feedback** 또는 IT 관리자(MDM)의 사용자가 변경할 수 있습니다. [Windows 10 진단, 피드백 및 개인 정보 보호에](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)대해 자세히 참조하세요.

> [!Important]
> 디바이스 진단 로그에는 일반적인 작업 중에 사용자가 시작하는 프로세스 또는 애플리케이션과 같은 PII(개인 식별 정보)가 포함됩니다. 여러 사용자가 HoloLens 디바이스를 공유하는 경우(예: 사용자가 다른 azure AD(Microsoft Azure Active Directory) 계정을 사용하여 동일한 디바이스에 로그인) 진단 로그에는 여러 사용자에게 적용되는 PII 정보가 포함될 수 있습니다.

HoloLens 2 진단 데이터를 수집하기 위한 [몇 가지 수집 방법 및](/hololens/hololens-diagnostic-logs) 데이터 보존 정책이 있습니다.  Microsoft에서 진단 데이터를 수집하고 사용하는 방법에 대한 자세한 내용은 [Microsoft 개인정보처리방침 - 진단 -](https://privacy.microsoft.com/privacystatement) 왼쪽 탐색 메뉴에서 **Windows** 확장하고 **진단을** 선택합니다. **진단 섹션으로** 이동합니다.
