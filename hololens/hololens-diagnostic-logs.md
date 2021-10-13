---
title: HoloLens 디바이스에서 진단 정보 수집 및 사용
description: HoloLens 장치에서 진단 정보를 수집, 사용 및 유지 하는 방법에 대해 알아봅니다.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
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
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924406"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens 디바이스에서 진단 정보 수집 및 사용

HoloLens 사용자와 관리자는 HoloLens에서 진단 정보를 수집 하는 네 가지 방법 중에서 선택할 수 있습니다.

- 피드백 허브 앱
- DiagnosticLog CSP
- 설정 앱
- 오프 라인 진단

> [!IMPORTANT]  
> 장치 진단 로그에는 일반 작업 중 사용자가 시작 하는 프로세스 또는 응용 프로그램과 같은 PII (개인 식별이 가능한 정보)가 포함 됩니다. 여러 사용자가 HoloLens 장치를 공유 하는 경우 (예: 사용자가 다른 Microsoft Azure Active Directory (Azure AD) 계정을 사용 하 여 동일한 장치에 로그인 하는 경우) 진단 로그에는 여러 사용자에 게 적용 되는 PII 정보가 포함 될 수 있습니다. 자세한 내용은 [Microsoft 개인 정보 취급 방침](https://privacy.microsoft.com/privacystatement)을 참조 하세요.

다음 표에서는 서로 다른 컬렉션 메서드를 비교 합니다. 메서드 이름은 표 다음에 나오는 섹션의 자세한 정보에 연결 됩니다.

|메서드 |필수 구성 요소 |데이터 위치 |데이터 액세스 및 사용 |데이터 보존 |
| --- | --- | --- | --- | --- |
|[피드백 허브](#feedback-hub) |네트워크 및 인터넷 연결<br /><br />피드백 허브 앱<br /><br />Microsoft 클라우드에 파일을 업로드할 수 있는 권한 |Microsoft 클라우드<br /><br />HoloLens 장치 (선택 사항) |사용자가 지원을 요청 하 고, 사용 약관에 동의 하 고, 데이터를 업로드 합니다.<br /><br />Microsoft 직원은 사용 약관과 일치 하는 데이터를 봅니다. |클라우드의 데이터는 NGP (차세대 개인 정보)로 정의 된 기간 동안 보존 됩니다. 그러면 데이터가 자동으로 삭제 됩니다.<br /><br />장치에 있는 데이터는 **장치 소유자** 또는 **관리자** 권한이 있는 사용자가 언제 든 지 삭제할 수 있습니다. |
|[설정 문제 해결사](#settings-troubleshooter) |설정 앱 |HoloLens 디바이스<br /><br />연결 된 컴퓨터 (선택 사항) |사용자는 데이터를 저장 하 고 사용자가 데이터에 액세스 하는 경우 (구체적으로 다른 사용자와 데이터를 공유 하지 않는 경우)에만 사용자가 데이터에 액세스 합니다. |데이터는 사용자가 삭제할 때까지 장치에 보존 됩니다. * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |네트워크 연결<br /><br />DiagnosticLog CSP를 지 원하는 MDM 환경 |관리자가 저장소 위치 구성 |관리 환경에서 사용자는 데이터에 대 한 관리자 액세스 권한을 암시적으로 동의 합니다.<br /><br />관리자가 액세스 역할 및 사용 권한을 구성 합니다. | 데이터는 클라우드 저장소에 유지 되 고 관리자는 보존 정책을 구성 합니다. |
|[오프 라인 진단](#offline-diagnostics) |장치 구성:<ul><li>전원이 켜져 있고 컴퓨터에 연결 됨</li><li>전원 및 볼륨 단추 작동</li></ul> |HoloLens 디바이스<br /><br />연결 된 컴퓨터 |사용자는 데이터를 저장 하 고 사용자가 데이터에 액세스 하는 경우 (구체적으로 다른 사용자와 데이터를 공유 하지 않는 경우)에만 사용자가 데이터에 액세스 합니다. |데이터는 사용자가 삭제할 때까지 장치에 보존 됩니다. |

* 최종 사용자는 로그를 다른 사용자와 함께 공유할 책임이 있습니다. 이러한 파일은 고객 서비스 및 지원 센터에 문의할 때 주로 유용 합니다.  

## <a name="feedback-hub"></a>피드백 허브

HoloLens 사용자는 Microsoft 피드백 허브 데스크톱 앱을 사용 하 여 Microsoft 지원에 진단 정보를 보낼 수 있습니다. 세부 정보 및 전체 지침은 [의견 보내기](hololens-feedback.md)를 참조 하세요.  

> [!NOTE]  
> **상용 또는 엔터프라이즈 사용자:** 피드백 허브 앱을 사용 하 여 MDM, 프로 비전 또는 기타 장치 관리 측면과 관련 된 문제를 보고 하는 경우 앱 범주를 **Enterprise 관리**  >  **장치 범주** 로 변경 합니다.

>[!IMPORTANT]
> 문제를 해결 하는 데 가장 적합 한 데이터를 제공 하려면 장치 원격 분석을 **선택적** 으로 설정 하는 것이 좋습니다. OOBE (기본 제공 환경) 중에 또는 **설정** 앱을 사용 하 여이 값을 설정할 수 있습니다. 설정를 사용 하 여이 작업을 수행 하려면 **시작 > 설정 > 개인 정보 보호 > 앱 진단 >을** 선택 합니다.

### <a name="prerequisites"></a>필수 구성 요소

- 장치가 네트워크에 연결 되어 있습니다.
- 피드백 허브 앱은 사용자의 데스크톱 컴퓨터에서 사용할 수 있으며 사용자는 Microsoft 클라우드에 파일을 업로드할 수 있습니다.

### <a name="data-locations-access-and-retention"></a>데이터 위치, 액세스 및 보존

사용자는 피드백 허브의 사용 약관에 동의 하 여 해당 계약에 정의 된 대로 데이터의 저장 및 사용을 명시적으로 동의 합니다.

피드백 허브는 사용자가 진단 정보를 저장할 수 있는 두 가지 위치를 제공 합니다.

- **Microsoft 클라우드**. 피드백 허브 앱을 사용 하 여 사용자가 업로드 하는 데이터는 NGP (차세대 개인 정보) 요구 사항과 일치 하는 일 수 동안 저장 됩니다. Microsoft 직원은 이러한 기간 동안 NGP 규격 뷰어를 사용 하 여 정보에 액세스할 수 있습니다.

   > [!NOTE]  
   > 이러한 요구 사항은 모든 피드백 허브 범주의 데이터에 적용 됩니다.

- **HoloLens 장치** 입니다. 피드백 허브에서 보고서를 작성 하는 동안 사용자가 **피드백을 제공할 때 사용자는 진단의 로컬 복사본과 첨부 파일을 저장** 하도록 선택할 수 있습니다. 사용자가이 옵션을 선택 하는 경우 피드백 허브는 HoloLens 장치에 진단 정보의 복사본을 저장 합니다. 이 정보는 사용자 (또는 해당 계정을 사용 하 여 HoloLens에 로그인 하는 모든 사용자)에 게 계속 액세스할 수 있습니다. 이 정보를 삭제 하려면 사용자에 게 장치에 대 한 **장치 소유자** 또는 **관리자** 권한이 있어야 합니다. 적절 한 권한이 있는 사용자는 피드백 허브에 로그인 하 고 **설정**  >  **진단 로그 보기** 를 선택한 후 정보를 삭제할 수 있습니다.

## <a name="settings-troubleshooter"></a>설정 문제 해결사

HoloLens 사용자는 장치의 **설정** 앱을 사용 하 여 문제를 해결 하 고 진단 정보를 수집할 수 있습니다. 이렇게 하려면 다음 단계를 따르십시오.

1. 설정 앱을 열고 **업데이트 & 보안**  >  **문제 해결** 페이지를 선택 합니다.
1. 적절 한 영역을 선택 하 고 **시작** 을 선택 합니다.
1. 문제를 재현합니다.
1. 문제를 재현 한 후 설정로 돌아간 다음 **중지** 를 선택 합니다.

또한 사용자는 **설정** 앱에서 대체 진단의 동작을 구성할 수 있습니다. **개인 정보-> 문제 해결** 페이지로 이동 하 여이 설정을 구성 합니다.
> [!NOTE]
> 장치에 대해 구성 된 MDM 정책이 있으면 사용자가 해당 동작을 재정의할 수 없습니다.

### <a name="os-update-troubleshooter"></a>OS 업데이트 문제 해결사

빌드 [Windows Holographic, 버전 21h1](hololens-release-notes.md#windows-holographic-version-21h1) 및 그 이후:
- 설정 앱 내에서 이전 문제 해결사 외에도 새로운 OS 업데이트를 위한 새 설정 앱이 추가 되어 새 문제 해결사가 추가 되었습니다. **설정-> 업데이트 & 보안-> 문제 해결-> Windows 업데이트** 으로 이동 하 고 **시작** 을 선택 합니다. 이렇게 하면 OS 업데이트에 대 한 문제를 재현 하는 동안 추적을 수집 하 여 IT 또는 지원과 관련 된 문제 해결에 더 효과적으로 지원할 수 있습니다.

### <a name="prerequisites"></a>필수 구성 요소

- **설정** 앱은 장치에 설치 되며 사용자가 사용할 수 있습니다.

### <a name="data-locations-access-and-retention"></a>데이터 위치, 액세스 및 보존

사용자가 데이터 컬렉션을 시작 하기 때문에 사용자는 암시적으로 진단 정보 저장소로 동의 합니다. 사용자 또는 사용자가 데이터를 공유 하는 모든 사용자만 데이터에 액세스할 수 있습니다.

진단 정보는 장치에 저장 됩니다. 장치가 사용자의 컴퓨터에 연결 되어 있는 경우에도이 정보는 컴퓨터의 다음 파일에 있습니다.

> 이 PC \\ \<*HoloLens device name*> \\ 내부 Storage \\ 문서 \\ 추적 \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> 이 파일 경로와 이름에서는 \<*HoloLens device name*> HoloLens 장치의 이름을 나타내며 \<*ddmmyyhhmmss*> 파일을 만든 날짜와 시간을 나타냅니다.

사용자가 삭제할 때까지 진단 정보는 이러한 위치에 유지 됩니다.

### <a name="view-diagnostic-report"></a>진단 보고서 보기

HoloLens 2에서 MDM 진단을 보려면 WiFi 아이콘을 선택한 다음 **설정**  ->  **계정**  >  **회사 또는 학교 액세스** 로 이동 하 고 **관리 로그 내보내기** 를 선택 합니다. HoloLens 로그 파일을 계정으로 보내고 데스크톱 PC에서 해당 위치를 표시 합니다.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

MDM (모바일 장치 관리) 환경에서 IT 관리자는 [DiagnosticLog CSP (구성 서비스 공급자)](/windows/client-management/mdm/diagnosticlog-csp) 를 사용 하 여 등록 된 HoloLens 장치에서 진단 설정을 구성할 수 있습니다. IT 관리자는 등록 된 장치에서 로그를 수집 하도록 이러한 설정을 구성할 수 있습니다.

자세히 보기:
- [Windows 디바이스에서 진단 수집](/mem/intune/remote-actions/collect-diagnostics)
- [Intune 공개 미리 보기-Windows 10 장치 진단](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>필수 구성 요소

- 장치가 네트워크에 연결 되어 있습니다.
- 장치가 DiagnosticLog CSP를 지 원하는 MDM 환경에 등록 되어 있습니다.

### <a name="data-locations-access-and-retention"></a>데이터 위치, 액세스 및 보존

장치가 관리 되는 환경의 일부 이기 때문에 사용자가 암시적으로 진단 정보에 대 한 관리 액세스를 동의 합니다.

IT 관리자는 DiagnosticLog CSP를 사용 하 여 다음을 제어 하는 정책을 포함 하 여 데이터 저장소, 보존 및 액세스 정책을 구성 합니다.

- 진단 정보를 저장 하는 클라우드 인프라입니다.
- 진단 정보의 보존 기간입니다.
- 진단 정보에 대 한 액세스를 제어 하는 권한입니다.

## <a name="offline-diagnostics"></a>오프 라인 진단

장치에서 피드백 허브 또는 설정 문제 해결사를 통해 진단을 수집할 수 없는 경우 진단을 수동으로 수집할 수 있습니다. 장치가 Wi-Fi에 연결할 수 없거나 위에서 언급 한 다른 방법에 액세스할 수 없는 경우를 예로 들 수 있습니다. 진단에서 Microsoft 지원 엔지니어가 문제를 격리 하는 데 도움이 되는 크래시 덤프 및 로그를 장치에서 수집 합니다.

이는 장치가 USB 케이블을 통해 PC에 연결한 후 파일 탐색기에 표시 되는 경우 작동 합니다.

> [!NOTE]
> 오프 라인 진단 생성 및 관리는 OS 버전에 따라 다르게 제어 됩니다. 이전에는 원격 분석 설정에 의해 제어 되었지만 이제는 MDM 정책을 통해 직접 제어 됩니다. 설정이 나 MDM 정책을 통해 사용 하지 않도록 설정 된 경우이 메커니즘을 사용 하 여 진단 로그를 수집할 수 없습니다.

[Windows Holographic 전의 동작, 20h2 버전](hololens-release-notes.md#windows-holographic-version-20h2):
 - 오프 라인 진단은 사용자가 OOBE를 통과 하거나 [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 정책 값이 Full로 설정 된 경우에만 사용할 수 있습니다 (기본 기본값은 HoloLens). 
- 오프 라인 진단을 사용 하지 않도록 설정 하려면 **설정 App > 개인 정보** 페이지로 이동 하 여 **진단 데이터** 에서 **기본** 을 선택 합니다. 오프 라인 진단이 원격 분석 설정에 의존 하는 빌드에서는 로그가 수집 되는지 여부에만 영향을 줍니다. 수집 되는 파일에는 영향을 주지 않습니다.
- 장치가 잠겨 있으면 로그가 표시 되지 않습니다.

빌드 [Windows Holographic, 버전 20h2](hololens-release-notes.md#windows-holographic-version-20h2) 이상:
- 대체 진단이 사용 하도록 설정 된 경우 해당 설정이 [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) 인 특정 MDM 정책에 의해 제어 됩니다.
- 장치가 잠겨 있으면 로그가 표시 되지 않습니다.

이 비디오를 시청하여 자세히 알아보세요.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

진단을 수집 하려면 다음 단계를 수행 합니다.

1.  USB 케이블을 사용 하 여 장치를 PC에 커넥트 합니다.

2.  PC의 파일 탐색기에서 **' THIS pc \<hololens-device> \internal Storage '** 로 이동 합니다.

3.  **내부 Storage** 폴더가 표시 되지 않으면 사용자가 로그인 할 때까지 장치가 대기 하 고 있는 것입니다. 전원 단추를 10 초 동안 눌러 장치를 로그인 하거나 전원을 껐다가 켭니다.

4.  **전원 + 볼륨 아래로** 단추를 함께 눌렀다가 즉시 해제 합니다.

5.  장치에서 zip 보관 파일을 준비 하는 데 몇 분 정도 기다립니다. HololensDiagnostics 라는 임시 파일은 장치에서 zip 보관 파일을 생성 하는 동안 표시 될 수 있습니다. 해당 파일에 액세스 하거나 저장 하지 마십시오. 프로세스가 완료 되 면 zip 보관 파일로 대체 됩니다.

6.  파일 탐색기를 새로 고치고 **' \Documents '** 폴더로 이동 합니다.

7.  진단 ZIP 파일을 복사 하 여 Microsoft 지원 팀과 공유 합니다.

> [!NOTE]
> 일부 진단 ZIP 파일에는 PII가 포함 될 수 있습니다.

### <a name="offline-diagnostics-notifications"></a>오프 라인 진단 알림

- [Windows Holographic, 버전 21h2](hololens-release-notes.md#windows-holographic-version-21h2)에 도입 되었습니다.

이는 [오프 라인 진단](hololens-diagnostic-logs.md#offline-diagnostics)이라는 기존 기능에 대 한 업데이트입니다. 이전에는 진단 수집을 트리거하거나 완료 했을 때 사용자에 게 명확한 표시기가 없었습니다.
이제 Windows Insider 빌드에 추가 되었습니다. 오프 라인 진단에 대 한 두 가지 형식의 오디오 시각적 피드백이 있습니다. 수집을 시작 하 고 완료할 때 알림을 알림이 표시 되는 첫 번째입니다. 사용자가 로그인 되어 있고 시각적 개체가 있는 경우 표시 됩니다.

![로그 수집에 대 한 알림입니다.](./images/logcollection1.jpg)

![로그 수집이 완료 된 경우의 알림입니다.](./images/logcollection2.jpg)

사용자가 표시에 대 한 액세스 권한이 없는 경우에 대 한 대체 로그 수집 메커니즘으로 오프 라인 진단을 사용 하는 경우가 많기 때문에 로그인 할 수 없거나 아직 OOBE에 있지 않기 때문에 로그가 수집 될 때 오디오 큐도 재생 됩니다. 이 소리는 알림 메시지 외에도 재생 됩니다.

이 새로운 기능은 장치를 업데이트할 때 사용할 수 있으며, 사용 하거나 관리 하지 않아도 됩니다. 이 새로운 피드백을 표시 하거나 듣지 못할 경우 오프 라인 진단이 계속 생성 됩니다.

이 새로운 고급 시각적 피드백 추가를 사용 하 여 진단 데이터를 수집 하는 것이 더 쉽고 신속 하 게 문제를 해결할 수 있습니다.

### <a name="low-storage-log-collection-improvements"></a>저장소 로그 수집 기능이 향상 되었습니다.

- [Windows Holographic, 버전 21h2](hololens-release-notes.md#windows-holographic-version-21h2)에 도입 되었습니다.

진단 로그가 수집 될 때 장치의 디스크 공간이 부족 한 경우에는 **StorageDiagnostics.zip** 이라는 추가 보고서가 만들어집니다. 저장소의 임계값은 [저장소 센스](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)Windows 의해 자동으로 결정 됩니다.

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens에서 설정 고급 진단 보고서 보기

- [Windows Holographic, 버전 21h2](hololens-release-notes.md#windows-holographic-version-21h2)에 도입 되었습니다.

동작 문제를 해결할 때 관리 되는 장치의 경우 예상 되는 정책 구성이 적용 되는지 확인 하는 것은 중요 한 단계입니다. 이전에는이 새로운 기능으로, **설정** 계정을 통해 수집 된 mdm 진단 로그를 내보내고 회사 또는 학교에 액세스 한 후 mdm을 통해 장치를 끄거나 장치 근처에서이를 수행 해야 했습니다  ->    >  . 그리고 **관리 로그 내보내기** 및 주변 PC에서 보기를 선택 합니다.

이제 Edge 브라우저를 사용 하 여 장치에서 MDM 진단을 볼 수 있습니다. MDM 진단 보고서를 더 쉽게 보려면 회사 또는 학교 액세스 페이지로 이동 하 고 **고급 진단 보고서 보기** 를 선택 합니다. 그러면 보고서가 생성 되어 새에 지 창에 열립니다.

![설정 앱에서 고급 진단 보고서를 봅니다.](./images/view-advanced-diagnostic-report.jpg)
