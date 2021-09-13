---
title: HoloLens 디바이스에서 진단 정보 수집 및 사용
description: HoloLens 디바이스에서 진단 정보를 수집, 사용 및 유지하는 방법을 알아봅니다.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 082a263bdd7eba694c13124abf40763644c83dfa
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032949"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens 디바이스에서 진단 정보 수집 및 사용

HoloLens 사용자와 관리자는 다음 네 가지 방법 중에서 선택하여 HoloLens 진단 정보를 수집할 수 있습니다.

- 앱 피드백 허브
- DiagnosticLog CSP
- 앱 설정
- 오프라인 진단

> [!IMPORTANT]  
> 디바이스 진단 로그에는 일반적인 작업 중에 사용자가 시작하는 프로세스 또는 애플리케이션과 같은 PII(개인 식별 정보)가 포함됩니다. 여러 사용자가 HoloLens 디바이스를 공유하는 경우(예: 사용자가 다른 Microsoft Azure Active Directory(Azure AD) 계정을 사용하여 동일한 디바이스에 로그인) 진단 로그에 여러 사용자에게 적용되는 PII 정보가 포함될 수 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침을 참조하세요.](https://privacy.microsoft.com/privacystatement)

다음 표에서는 다양한 컬렉션 메서드를 비교합니다. 메서드 이름은 표 다음에 있는 섹션의 자세한 정보에 연결됩니다.

|방법 |사전 요구 사항 |데이터 위치 |데이터 액세스 및 사용 |데이터 보존 |
| --- | --- | --- | --- | --- |
|[피드백 허브](#feedback-hub) |네트워크 및 인터넷 연결<br /><br />앱 피드백 허브<br /><br />Microsoft 클라우드에 파일을 업로드할 수 있는 권한 |Microsoft 클라우드<br /><br />HoloLens 디바이스(선택 사항) |사용자가 지원을 요청하고, 사용 약관에 동의하고, 데이터를 업로드합니다.<br /><br />Microsoft 직원은 사용 약관에 따라 데이터를 봅니다. |클라우드의 데이터는 NGP(차세대 개인 정보)에 정의된 기간 동안 보존됩니다. 그러면 데이터가 자동으로 삭제됩니다.<br /><br />디바이스 소유자 또는 **관리자** 권한이 있는 사용자는 언제든지 **디바이스의** 데이터를 삭제할 수 있습니다. |
|[설정 문제 해결사](#settings-troubleshooter) |앱 설정 |HoloLens 디바이스<br /><br />연결된 컴퓨터(선택 사항) |사용자는 데이터를 저장하고 사용자만 데이터에 액세스합니다(사용자가 다른 사용자와 데이터를 구체적으로 공유하지 않는 한). |데이터는 사용자가 삭제할 때까지 디바이스에 유지됩니다.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |네트워크 연결<br /><br />DiagnosticLog CSP를 지원하는 MDM 환경 |관리자가 스토리지 위치를 구성합니다. |관리되는 환경에서 사용자는 데이터에 대한 관리자 액세스에 암시적으로 동의합니다.<br /><br />관리자는 액세스 역할 및 권한을 구성합니다. | 데이터는 클라우드 스토리지에 보존되며 관리자는 보존 정책을 구성합니다. |
|[오프라인 진단](#offline-diagnostics) |디바이스 구성:<ul><li>전원이 켜지고 컴퓨터에 연결됨</li><li>전원 및 볼륨 단추 작동</li></ul> |HoloLens 디바이스<br /><br />연결된 컴퓨터 |사용자는 데이터를 저장하고 사용자만 데이터에 액세스합니다(사용자가 다른 사용자와 데이터를 구체적으로 공유하지 않는 한). |데이터는 사용자가 삭제할 때까지 디바이스에 유지됩니다. |

* 최종 사용자는 다른 사용자와 로그를 책임 있게 공유할 책임이 있습니다. 이러한 파일은 고객 서비스 및 지원에 문의할 때 주로 유용합니다.  

## <a name="feedback-hub"></a>피드백 허브

HoloLens 사용자는 Microsoft 피드백 허브 데스크톱 앱을 사용하여 진단 정보를 Microsoft 지원 보낼 수 있습니다. 자세한 내용 및 전체 지침은 [피드백 제공을 참조하세요.](hololens-feedback.md)  

> [!NOTE]  
> **상용 또는 엔터프라이즈 사용자:** 피드백 허브 앱을 사용하여 MDM, 프로비전 또는 기타 디바이스 관리 측면과 관련된 문제를 보고하는 경우 앱 범주를 **Enterprise 관리**  >  **디바이스 범주로** 변경합니다.

>[!IMPORTANT]
> 문제를 해결하기 위한 최상의 데이터를 제공하려면 디바이스 원격 분석을 **선택 사항으로** 설정하는 것이 좋습니다. OOBE(첫 경험) 중에 또는 **설정** 앱을 사용하여 이 값을 설정할 수 있습니다. 설정 사용하여 이 작업을 수행하려면 개인 **정보 > 설정 > 시작 > 앱 진단 > 켜기를** 선택합니다.
### <a name="prerequisites"></a>사전 요구 사항

- 디바이스가 네트워크에 연결되어 있습니다.
- 피드백 허브 앱은 사용자의 데스크톱 컴퓨터에서 사용할 수 있으며 사용자는 Microsoft 클라우드에 파일을 업로드할 수 있습니다.

### <a name="data-locations-access-and-retention"></a>데이터 위치, 액세스 및 보존

사용자는 피드백 허브 사용 약관에 동의하여 해당 계약에서 정의한 대로 데이터의 스토리지 및 사용에 명시적으로 동의합니다.

피드백 허브 사용자가 진단 정보를 저장할 수 있는 두 위치를 제공합니다.

- **Microsoft 클라우드 입니다.** 사용자가 피드백 허브 앱을 사용하여 업로드하는 데이터는 NGP(차세대 개인 정보 보호) 요구 사항과 일치하는 일 수 동안 저장됩니다. Microsoft 직원은 NGP 규격 뷰어를 사용하여 이 기간 동안 정보에 액세스할 수 있습니다.

   > [!NOTE]  
   > 이러한 요구 사항은 모든 피드백 허브 범주의 데이터에 적용됩니다.

- **HoloLens 디바이스 입니다.** 피드백 허브 보고서를 제출하는 동안 사용자는 피드백을 **제공할 때 만든 진단 및 첨부 파일의 로컬 복사본 저장을** 선택할 수 있습니다. 사용자가 이 옵션을 선택하면 피드백 허브 HoloLens 디바이스에 진단 정보의 복사본을 저장합니다. 이 정보는 사용자(또는 해당 계정을 사용하여 HoloLens 로그인하는 모든 사용자)가 계속 액세스할 수 있습니다. 이 정보를 삭제하려면 사용자에게 **디바이스에** 대한 디바이스 소유자 또는 **관리자** 권한이 있어야 합니다. 적절한 권한이 있는 사용자는 피드백 허브 로그인하고, **설정** 진단 로그 보기를 선택하고, 정보를 삭제할 수  >  **있습니다.**

## <a name="settings-troubleshooter"></a>설정 문제 해결사

HoloLens 사용자는 디바이스에서 **설정** 앱을 사용하여 문제를 해결하고 진단 정보를 수집할 수 있습니다. 이렇게 하려면 다음 단계를 따르십시오.

1. 설정 앱을 열고 **업데이트 & 보안** 문제  >  **해결** 페이지를 선택합니다.
1. 적절한 영역을 선택하고 **시작을** 선택합니다.
1. 이슈를 재현합니다.
1. 문제를 재현한 후 설정 돌아가서 **중지를** 선택합니다.

사용자는 **설정** 앱에서 대체 진단의 동작을 구성할 수도 있습니다. 개인 **정보 -> 문제 해결** 페이지로 이동하여 이 설정을 구성합니다.
> [!NOTE]
> 디바이스에 대해 구성된 MDM 정책이 있는 경우 사용자는 해당 동작을 재정의할 수 없습니다.

### <a name="os-update-troubleshooter"></a>OS 업데이트 문제 해결사
빌드 Windows [Holographic 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 이상:
- 설정 앱 내의 이전 문제 해결사 외에도 OS 업데이트용 새 설정 앱을 추가하여 새 문제 해결사를 추가했습니다. 설정 **-> 업데이트 & 보안 -> 문제 해결 -> Windows 업데이트로** 이동하고 **시작을** 선택합니다. 이렇게 하면 OS 업데이트와 관련된 문제를 재현하는 동안 추적을 수집하여 IT 또는 지원 문제를 더 잘 해결할 수 있습니다.
### <a name="prerequisites"></a>사전 요구 사항

- **설정** 앱은 디바이스에 설치되며 사용자가 사용할 수 있습니다.

### <a name="data-locations-access-and-retention"></a>데이터 위치, 액세스 및 보존

사용자가 데이터 수집을 시작하므로 사용자는 진단 정보의 스토리지에 암시적으로 동의합니다. 사용자 또는 사용자가 데이터를 공유하는 사용자만 데이터에 액세스할 수 있습니다.

진단 정보는 디바이스에 저장됩니다. 디바이스가 사용자의 컴퓨터에 연결된 경우 정보는 다음 파일의 컴퓨터에도 있습니다.

> 이 PC \\ \<*HoloLens device name*> \\ 내부 Storage 문서 \\ 추적 \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> 이 파일 경로 및 이름에서 \<*HoloLens device name*> 는 HoloLens 디바이스의 이름을 \<*ddmmyyhhmmss*> 나타내고 파일이 만들어진 날짜와 시간을 나타냅니다.

진단 정보는 사용자가 삭제할 때까지 이러한 위치에 유지됩니다.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

MDM(모바일 장치 관리) 환경에서 IT 관리자는 [CSP(DiagnosticLog 구성 서비스 공급자)를](/windows/client-management/mdm/diagnosticlog-csp) 사용하여 등록된 HoloLens 디바이스에서 진단 설정을 구성할 수 있습니다. IT 관리자는 등록된 디바이스에서 로그를 수집하도록 이러한 설정을 구성할 수 있습니다.

자세한 내용은 다음을 참조하세요.
- [Windows 디바이스에서 진단 수집](/mem/intune/remote-actions/collect-diagnostics)
- [Intune 공개 미리 보기 - Windows 10 디바이스 진단](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>사전 요구 사항

- 디바이스가 네트워크에 연결되어 있습니다.
- 디바이스가 DiagnosticLog CSP를 지원하는 MDM 환경에 등록됩니다.

### <a name="data-locations-access-and-retention"></a>데이터 위치, 액세스 및 보존

디바이스는 관리되는 환경의 일부이므로 사용자는 진단 정보에 대한 관리 액세스에 암시적으로 동의합니다.

IT 관리자는 DiagnosticLog CSP를 사용하여 다음을 제어하는 정책을 포함하여 데이터 스토리지, 보존 및 액세스 정책을 구성합니다.

- 진단 정보를 저장하는 클라우드 인프라입니다.
- 진단 정보의 보존 기간입니다.
- 진단 정보에 대한 액세스를 제어하는 권한입니다.

## <a name="offline-diagnostics"></a>오프라인 진단
디바이스가 피드백 허브 또는 설정 문제 해결사를 통해 진단을 수집할 수 없는 경우 수동으로 진단을 수집할 수 있습니다. 이 시나리오가 필요한 한 가지 시나리오는 디바이스가 Wi-Fi 연결할 수 없거나 위에서 언급한 다른 메서드에 액세스할 수 없는 경우입니다. 진단은 Microsoft 지원 엔지니어가 문제를 격리하는 데 도움이 되는 디바이스에서 크래시 덤프 및 로그를 수집합니다.

USB 케이블을 통해 PC에 연결한 후 디바이스가 파일 탐색기 표시되면 작동합니다.

> [!NOTE]
> 오프라인 진단 생성 및 관리는 OS 버전에 따라 다르게 제어됩니다. 이전에는 원격 분석 설정에 의해 제어되었지만 이제 MDM 정책을 통해 직접 제어됩니다. 설정 또는 MDM 정책을 통해 사용하지 않도록 설정하면 이 메커니즘을 사용하여 진단 로그를 수집할 수 없습니다.

[Holographic 버전 20H2를 Windows](hololens-release-notes.md#windows-holographic-version-20h2)이전의 동작:
 - 오프라인 진단은 사용자가 OOBE를 거치거나 [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 정책 값이 Full로 설정된 경우에만 사용할 수 있습니다(기본값은 HoloLens 기본값임). 
- 오프라인 진단을 사용하지 않도록 설정하려면 **앱 > 개인 정보 설정** 페이지로 이동하고 진단 **데이터에서** **기본을** 선택합니다. 오프라인 진단이 원격 분석 설정에 따라 달라지는 빌드에서는 로그가 수집되는지 여부만 영향을 받습니다. 수집되는 파일에는 영향을 주지 않습니다.
- 디바이스가 잠겨 있으면 로그가 표시되지 않습니다.

빌드 Windows [Holographic 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상:
- 대체 진단을 사용하는 경우 해당 설정 [MixedReality/FallbackDiagnostics를](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) 사용하여 특정 MDM 정책에 의해 제어됩니다.
- 디바이스가 잠겨 있으면 로그가 표시되지 않습니다.

이 비디오를 시청하여 자세히 알아보세요.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

진단을 수집하려면 다음 단계를 수행합니다.
1.  USB 케이블을 사용하여 디바이스를 PC에 커넥트.
2.  PC의 파일 탐색기 **'This PC \<hololens-device> \Internal Storage'로** 이동합니다.
3.  내부 **Storage** 폴더가 표시되지 않으면 디바이스가 사용자가 로그인할 때까지 기다리고 있습니다. 전원 단추를 10초 동안 눌러서 디바이스에 로그인하거나 전원을 순환합니다.
4.  **Power + 볼륨 다운** 단추를 눌러 즉시 함께 놓습니다.
5.  디바이스가 zip 보관 파일을 준비할 때까지 잠시 기다립니다. (디바이스에서 zip 보관 파일을 생성하는 동안 HololensDiagnostics.temp라는 임시 파일이 표시될 수 있습니다. 해당 파일에 액세스하거나 저장하지 않습니다. 프로세스가 완료되면 zip 보관 파일로 대체됩니다.)
6.  파일 탐색기를 새로 고치고 **'\Documents'** 폴더로 이동합니다.
7.  진단 ZIP 파일을 복사하고 Microsoft 지원 팀과 공유합니다.

> [!NOTE]
> 진단 ZIP 파일 중 일부는 PII를 포함할 수 있습니다.
