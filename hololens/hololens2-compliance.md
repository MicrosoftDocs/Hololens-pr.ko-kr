---
title: HoloLens 2 준수 및 GDPR
description: GDPR 설명서
keywords: HoloLens, gdpr, 개인 정보, PII
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
ms.openlocfilehash: 684a97a4fcdc3aaf830f164c54fb3079e296c78c
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637118"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 개인정보처리방침

GDPR의 핵심 요소 중 하나는 ' 설계상의 데이터 보호 '입니다. 이 개념은 이식성, 무제한 인터넷 연결 및 오픈 통신 채널 때문에 HoloLens 2와 같은 모바일 장치에 특히 적용 됩니다. Resultingly에 HoloLens 2는 Microsoft의 [개인 정보 보호 및 gdpr 규정](https://privacy.microsoft.com/)준수에 대 한 고급, 혁신적인 보안 및 개인 정보 보호를 제공 [하도록 설계 되었습니다](/hololens/security-architecture) .

 >[!NOTE]
> 이 문서는 HoloLens (첫 번째 gen)에는 적용 되지 않습니다.

## <a name="privacy-overview"></a>개인 정보 개요

HoloLens 2는 몰입 형 혼합 현실 환경에서 앱 및 솔루션을 실행 하는 자체 포함 된 Windows 컴퓨터로, Windows Holographic를 실행 합니다. 안전한 오프 라인 장치로 사용 하거나 조직 내에서 [관리 되는 장치로](/mem/intune/fundamentals/windows-holographic-for-business) 배포할 수 있습니다. HoloLens 2 및 Microsoft에서 데이터를 사용 하 고 보호 하는 방법을 이해 하려면 다음 링크를 참조 하세요.

1. [Microsoft 개인 정보 취급 방침-HoloLens](https://privacy.microsoft.com/privacystatement) – 왼쪽 탐색 메뉴에서 **Enterprise 및 개발자** 섹션을 확장 하 고 **Enterprise 및 개발자 소프트웨어 및 어플라이언스** 를 선택 합니다. **HoloLens** 섹션으로 이동 합니다.
2. [Windows 10 및 온라인 서비스](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & 개인 정보 규정 준수 가이드](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune의 개인 정보 및 개인 데이터](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>네트워크 보안
HoloLens 2 [일반적인 배포 시나리오](/hololens/common-scenarios)를 수행 하 여 데이터는 법적/규제 표준 통합과 함께 [Azure의 세계적인 규정 준수](/azure/compliance/) 에 의해 보호 됩니다. azure AD 및 Dynamics 365 Remote Assist를 처음 접하는 경우 [gdpr에 대 한 azure 및 Dynamics 365 책임 준비 검사 목록을](/compliance/regulatory/gdpr-arc-azure-dynamics)참조 하세요.

또한 Windows Defender 방화벽은 장치 연결을 보호 하기 위한 중요 한 기능을 제공 합니다. HoloLens 2 사용 하는 경우 방화벽은 항상 사용 하도록 설정 되며 프로그래밍 방식으로 또는 UI를 통해 사용 하지 않도록 설정할 수 있는 방법이 없습니다. HoloLens 2 [Intune](/mem/intune/protect/device-compliance-get-started)을 사용 하 여 관리 되는 장치로 배포 되는 경우 모바일 위협 방어 솔루션으로 [Microsoft Intune를 사용](/mem/intune/protect/advanced-threat-protection) 하는 끝점에 대 한 통합에서 더 많은 준수 기능을 사용할 수 있습니다.

HoloLens 2 [보안 및 아키텍처](/hololens/security-architecture)에 대해 자세히 알아보세요.

## <a name="os-security"></a>OS 보안
업데이트는 자동으로 수행 되므로 (기본적으로) 최신 버전의 Windows Holographic 및 설치 된 앱을 사용 하 여 HoloLens 2 항상 최신 상태가 됩니다. OS를 안전 하 게 디자인 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

1. [상태 구분 및 격리](/hololens/security-state-separation-isolation)
1. [관리 수준이 낮은 운영 체제](/hololens/security-adminless-os)
1. [암호 사용 제한](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>물리적 보안
HoloLens 2에는 [BitLocker 암호화](/hololens/security-encryption-data-protection)로 보호 되는 플래시 메모리가 있습니다. 장치 및 해당 로컬 데이터는 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) 를 사용 하 여 오프 라인으로 또는 관리 되는 장치로 배포 된 경우 MDM을 통해 원격으로 초기화 될 수 있습니다.

## <a name="data-protection"></a>데이터 보호
Windows 업데이트는 자동으로 실행 되 고 (기본적으로) [Azure 통합](/hololens/security-encryption-data-protection#Azure-integration) 은 자신과 클라우드 간에 이동 하는 데이터를 보호 합니다.

HoloLens 2를 외부 클라이언트에 배포 하는 경우 중요 한 회사 데이터와 리소스를 모두 분리 하 고 안전 하 게 유지할 [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) .

Microsoft와 진단 데이터를 공유 하려면 MDM을 사용 하 여 수동으로 구성 하거나 OOBE를 실행 하는 사용자가 수동으로 구성할 수 있습니다. 선택 사항인 진단 데이터와 필수 진단 데이터의 두 가지 옵션이 있습니다. 문제 해결을 위해 나중에 원래 진단 설정을 변경 해야 하는 경우 **설정 > 개인 정보-> 진단 & 피드백** 또는 it 관리자 (MDM)가 관리 되는 장치인 경우 사용자가 변경할 수 있습니다. [Windows 10의 진단, 피드백 및 개인 정보](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)에 대해 자세히 알아봅니다.

> [!Important]
> 장치 진단 로그에는 일반 작업 중 사용자가 시작 하는 프로세스 또는 응용 프로그램과 같은 PII (개인 식별이 가능한 정보)가 포함 됩니다. 여러 사용자가 HoloLens 장치를 공유 하는 경우 (예: 사용자가 다른 Microsoft Azure Active Directory (Azure AD) 계정을 사용 하 여 동일한 장치에 로그인 하는 경우) 진단 로그에는 여러 사용자에 게 적용 되는 PII 정보가 포함 될 수 있습니다.

HoloLens 2에서 진단 데이터를 수집 하는 데 사용할 수 있는 [몇 가지 컬렉션 메서드와 데이터 보존 정책이](/hololens/hololens-diagnostic-logs) 있습니다.  microsoft에서 진단 데이터를 수집 하 고 사용 하는 방법에 대 한 자세한 내용은 [microsoft 개인 정보 취급 방침-진단](https://privacy.microsoft.com/privacystatement) -왼쪽 탐색 메뉴에서 **Windows** 확장을 참조 하 고 **진단** 을 선택 합니다. **진단** 섹션으로 이동 합니다.
