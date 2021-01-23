---
title: HoloLens 장치에서 진단 정보 수집 및 사용
description: HoloLens 장치에서 진단 정보를 수집, 사용 및 보존하는 방법에 대해 자세히 알아보습니다.
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
ms.openlocfilehash: 206a31476820e8722b1b72fbd501345a089379b1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283229"
---
# HoloLens 장치에서 진단 정보 수집 및 사용

HoloLens 사용자 및 관리자는 HoloLens에서 진단 정보를 수집하는 네 가지 방법 중에서 선택할 수 있습니다.

- 피드백 허브 앱
- DiagnosticLog CSP
- 설정 앱

> [!IMPORTANT]  
> 장치 진단 로그에는 사용자가 일반적인 작업 중에 시작하는 프로세스 또는 응용 프로그램과 같은 PII(개인 식별이 가능한 정보)가 포함됩니다. 여러 사용자가 HoloLens 장치를 공유하는 경우(예: 사용자가 다른 Microsoft Azure AD(Azure Active Directory) 계정을 사용하여 동일한 장치에 로그인)진단 로그에 여러 사용자에게 적용되는 PII 정보가 포함될 수 있습니다. 자세한 내용은 Microsoft 개인 정보 [취급 방침을 참조하세요.](https://privacy.microsoft.com/privacystatement)

다음 표에서는 세 가지 컬렉션 메서드를 비교합니다. 메서드 이름은 표 다음에 있는 섹션의 자세한 정보에 연결됩니다.

|메서드 |필수 구성 요소 |데이터 위치 |데이터 액세스 및 사용 |데이터 보존 |
| --- | --- | --- | --- | --- |
|[피드백 허브](#feedback-hub) |네트워크 및 인터넷 연결<br /><br />피드백 허브 앱<br /><br />Microsoft 클라우드에 파일 업로드 권한 |Microsoft 클라우드<br /><br />HoloLens 장치(선택 사항) |사용자가 지원을 요청하고, 사용 약관에 동의하고, 데이터를 업로드합니다.<br /><br />Microsoft 직원은 사용 약관과 일관된 데이터 보기 |클라우드의 데이터는 NGP(차세대 개인 정보)에 정의된 기간 동안 보존됩니다. 그런 다음 데이터가 자동으로 삭제됩니다.<br /><br />디바이스 소유자 또는 관리자 권한이 있는 사용자가 디바이스의 **** 데이터를 삭제할 **수** 있습니다. |
|[설정 문제 해결사](#settings-troubleshooter) |설정 앱 |HoloLens 디바이스<br /><br />연결된 컴퓨터(선택 사항) |사용자는 데이터를 저장하고, 사용자가 특별히 다른 사용자와 데이터를 공유하지 않는 한 해당 사용자만 데이터에 액세스합니다. |데이터는 사용자가 삭제할 때까지 보존됩니다.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |네트워크 연결<br /><br />DiagnosticLog CSP를 지원하는 MDM 환경 |관리자가 저장소 위치를 구성합니다. |관리 환경에서 사용자는 데이터에 대한 관리자 액세스에 암시적으로 동의합니다.<br /><br />관리자가 액세스 역할 및 사용 권한을 구성합니다. | 관리자가 보존 정책을 구성합니다. |
|[오프라인 진단](#offline-diagnostics) |장치 구성:<ul><li>전원이 설정되고 컴퓨터에 연결됩니다.</li><li>전원 및 볼륨 단추 작동</li></ul> |HoloLens 디바이스<br /><br />연결된 컴퓨터 |사용자는 데이터를 저장하고, 사용자가 특별히 다른 사용자와 데이터를 공유하지 않는 한 해당 사용자만 데이터에 액세스합니다. |데이터는 사용자가 삭제할 때까지 보존됩니다. | 


-   최종 사용자는 다른 사용자와 책임감 있는 로그 공유를 담당합니다. 이러한 파일은 주로 고객 서비스 및 지원에 문의할 때 유용합니다.  

## 피드백 허브

HoloLens 사용자는 Microsoft 피드백 허브 데스크톱 앱을 사용하여 Microsoft 지원에 진단 정보를 보낼 수 있습니다. 자세한 내용과 전체 지침은 피드백 [보내기(Give us)를 참조하세요.](hololens-feedback.md)  

> [!NOTE]  
> **상업용 또는 엔터프라이즈 사용자:** 피드백 허브 앱을 사용하여 MDM, 프로비저닝 또는 기타 장치 관리 측면과 관련된 문제를 보고하는 경우 앱 범주를 **엔터프라이즈**관리 장치 범주로  >  **변경합니다.**

### 필수 구성 요소

- 장치가 네트워크에 연결되어 있습니다.
- 피드백 허브 앱은 사용자의 데스크톱 컴퓨터에서 사용할 수 있으며 사용자는 Microsoft 클라우드에 파일을 업로드할 수 있습니다.

### 데이터 위치, 액세스 및 보존

피드백 허브의 사용 약관에 동의하면 사용자는 해당 계약에 따라 정의된 데이터 저장 및 사용에 명시적으로 동의합니다.

피드백 허브는 사용자가 진단 정보를 저장할 수 있는 두 개의 장소를 제공합니다.

- **Microsoft 클라우드.** 피드백 허브 앱을 사용하여 사용자가 업로드하는 데이터는 NGP(차세대 개인 정보) 요구 사항과 일치하는 일 수 동안 저장됩니다. Microsoft 직원은 이 기간 동안 NGP 규격 뷰어를 사용하여 정보에 액세스할 수 있습니다.
   > [!NOTE]  
   > 이러한 요구 사항은 모든 피드백 허브 범주의 데이터에 적용됩니다.

- **HoloLens 장치.** 피드백 허브에 보고서를 작성하는 동안 사용자는 피드백을 제공하면 만들어진 진단 및 첨부 파일 로컬 복사본 저장을 **선택할 수 있습니다.** 사용자가 이 옵션을 선택하면 피드백 허브는 HoloLens 장치에 진단 정보의 복사본을 저장합니다. 이 정보는 사용자(또는 해당 계정을 사용하여 HoloLens에 로그인하는 데 사용하는 모든 사용자)에게 계속 액세스할 수 있습니다. 이 정보를 삭제하려면 사용자에게 장치에 대한 **** **장치 소유자** 또는 관리자 권한이 있어야 합니다. 적절한 권한이 있는 사용자는 피드백 허브에 로그인하고 설정 **** 보기 진단 로그를 선택한 다음 정보를  >  **** 삭제할 수 있습니다.

## 설정 문제 해결사

HoloLens 사용자는 장치의 설정 앱을 사용하여 문제를 해결하고 진단 정보를 수집할 수 있습니다. 이렇게 하려면 다음 단계를 따르세요.

1. 설정 앱을 열고 보안 **문제 &**  >  **업데이트를** 선택합니다.
1. 적절한 영역을 선택하고 시작을 **선택합니다.**
1. 문제를 재현합니다.
1. 문제를 재현한 후 설정으로 돌아가서 중지를 **선택합니다.**

### 필수 구성 요소

- 설정 앱은 장치에 설치되어 있으며 사용자가 사용할 수 있습니다.

### 데이터 위치, 액세스 및 보존

사용자가 데이터 수집을 시작하기 때문에 사용자는 진단 정보의 저장에 암시적으로 동의합니다. 사용자 또는 사용자가 데이터를 공유하는 사람만 데이터에 액세스할 수 있습니다.

진단 정보는 장치에 저장됩니다. 장치가 사용자 컴퓨터에 연결되어 있는 경우 정보는 다음 파일의 컴퓨터에도 있습니다.

> 이 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> 이 파일 경로와 이름에서 HoloLens 장치의 이름을 나타내고 파일을 만든 날짜와 \<*HoloLens device name*> \<*ddmmyyhhmmss*> 시간을 지정합니다.

진단 정보는 사용자가 삭제할 때까지 이러한 위치에 남아 있습니다.

## DiagnosticLog CSP

MDM(모바일 장치 관리) 환경에서 IT 관리자는 [DiagnosticLog CSP(구성](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 서비스 공급자)를 사용하여 등록된 HoloLens 장치에서 진단 설정을 구성할 수 있습니다. IT 관리자는 등록된 장치에서 로그를 수집하도록 이러한 설정을 구성할 수 있습니다.

### 필수 구성 요소

- 장치가 네트워크에 연결되어 있습니다.
- 장치가 DiagnosticLog CSP를 지원하는 MDM 환경에 등록됩니다.

### 데이터 위치, 액세스 및 보존

장치가 관리되는 환경의 일부이기 때문에 사용자는 진단 정보에 대한 관리 액세스에 암시적으로 동의합니다.

IT 관리자는 DiagnosticLog CSP를 사용하여 다음을 제어하는 정책을 포함하여 데이터 저장소, 보존 및 액세스 정책을 구성합니다.

- 진단 정보를 저장하는 클라우드 인프라입니다.
- 진단 정보에 대한 보존 기간입니다.
- 진단 정보에 대한 액세스를 제어하는 권한입니다.

## 오프라인 진단
디바이스가 피드백 허브 또는 설정 문제 해결사로 진단을 수집할 수 없는 경우 진단을 수동으로 수집할 수 있습니다. 이 시나리오가 필요한 한 가지 시나리오는 장치가 Wi-Fi에 연결할 수 없는 경우입니다. 진단은 Microsoft 지원 엔지니어가 문제를 격리하는 데 도움이 되는 장치에서 크래시 덤프 및 로그를 수집합니다.

USB 케이블을 통해 PC에 연결한 후 파일 탐색기에서 장치가 표시될 때 작동합니다. 

> [!NOTE]
> 오프라인 진단 생성 및 관리는 OS 버전에 따라 다르게 제어됩니다. 이전에는 원격 분석 설정에 의해 제어했지만 이제 정책을 통해 직접 제어됩니다. 

[Windows Holographic, Verison 20H2 이전 동작:](hololens-release-notes.md#windows-holographic-version-20h2)
 - 오프라인 진단은 사용자가 OOBE 또는 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 정책 값을 Full(HoloLens의 기본값)로 설정한 경우만 사용할 수 있습니다. 
- 오프라인 진단을 사용하지 않도록 **** 설정하려면 설정 앱 > 개인 정보 페이지로 이동하고 진단 **데이터에서 기본을** **선택합니다.** 오프라인 진단이 원격 분석 설정에 따라 달라지는 빌드에서는 로그 수집 여부에만 영향을 미치게 됩니다. 수집된 파일에는 영향을 주지 않습니다.
- 장치가 잠겨 있는 경우 로그가 나타나지 않습니다.

Windows [Holographic, Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상 빌드:
- Fallback Diagnostics가 사용하도록 설정된 경우 해당 설정 [MixedReality/FallbackDiagnostics를](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) 사용하여 특정 MDM 정책에 의해 제어됩니다.
- 장치가 잠겨 있는 경우 로그가 나타나지 않습니다.


자세한 내용은 이 비디오를 시청합니다. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

다음 단계에 따라 진단을 수집합니다.
1.  USB 케이블로 디바이스를 PC에 연결합니다.
2.  PC의 파일 탐색기에서 **'이 PC \<hololens-device> \내부 저장소'로 이동합니다.**
3.  내부 **저장소** 폴더가 표시되지 않는 경우 장치가 사용자가 로그인할 때까지 대기하고 있습니다. 10초 동안 전원 단추를 누를 경우 디바이스에 로그인하거나 전원을 다.
4.  POWER + VOLUME DOWN 단추를 함께 **누르고** 즉시 해제합니다.
5.  디바이스가 zip 보관 파일을 준비할 때까지 1분 정도 기다릴 수 있습니다. (장치가 zip 보관 파일을 생성하는 동안 HololensDiagnostics.temp라는 임시 파일이 표시될 수 있습니다. 해당 파일에 액세스하거나 저장하지 않습니다. 프로세스가 완료되면 zip 보관 파일로 대체됩니다.
6.  파일 탐색기를 새로 고치고 **'\문서' 폴더로** 이동합니다.
7.  진단 ZIP 파일을 복사하여 Microsoft 지원 팀과 공유합니다.

> [!NOTE]
> 일부 진단 ZIP 파일에는 개인 식별 가능 정보가 포함될 수 있습니다.



