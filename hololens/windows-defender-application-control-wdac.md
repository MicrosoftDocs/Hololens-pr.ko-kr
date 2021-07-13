---
title: Windows Defender 애플리케이션 제어 - WDAC
description: 애플리케이션 제어의 Windows Defender 및 이를 사용하여 HoloLens 혼합 현실 디바이스를 관리하는 방법에 대한 개요입니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639933"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender 애플리케이션 제어 - WDAC

WDAC를 사용하면 IT 관리자가 디바이스에서 앱의 출시를 차단하도록 디바이스를 구성할 수 있습니다. 이는 키오스크 모드와 같이 디바이스에서 앱을 숨기는 UI가 사용자에게 표시되지만 여전히 시작될 수 있는 디바이스 제한 방법과 다릅니다. WDAC가 구현되는 동안 앱은 여전히 모든 앱 목록에 표시되지만 WDAC는 해당 앱 및 프로세스가 디바이스 사용자가 시작하지 못하게 합니다.

디바이스에 WDAC 정책이 두 개 이상 할당될 수 있습니다. 시스템에 여러 WDAC 정책이 설정된 경우 가장 제한적인 정책이 적용됩니다. 

> [!NOTE]
> 최종 사용자가 WDAC에 의해 차단된 앱을 시작하려고 하면 HoloLens 해당 앱을 시작할 수 없다는 알림이 수신되지 않습니다.

다음은 사용자가 [WDAC 및 Windows PowerShell 사용하여 Microsoft Intune HoloLens 2 디바이스에서 앱을 허용하거나 차단하는](/mem/intune/configuration/custom-profile-hololens)방법을 알아보는 가이드입니다.

사용자가 첫 번째 예제 단계를 사용하여 Windows 10 PC에 설치된 앱을 검색할 때 결과의 범위를 좁히기 위해 몇 가지 시도를 해야 할 수 있습니다.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

패키지의 전체 이름을 모르는 경우 'Get-AppxPackage -name \* YourBestGuess'를 몇 \* 번 실행하여 찾아야 할 수 있습니다. 그런 다음 이름이 '$package 1 = Get-AppxPackage -name Actual.PackageName'을 실행합니다.

예를 들어 Microsoft Edge 대해 다음을 실행하면 결과가 두 개 이상 반환되지만 해당 목록에서 필요한 전체 이름이 Microsoft.MicrosoftEdge임을 확인할 수 있습니다.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens 앱의 패키지 패밀리 이름

위에 링크된 가이드에서는 newPolicy.xml 수동으로 편집하고 패키지 패밀리 이름으로 HoloLens 설치되는 애플리케이션에 대한 규칙을 추가할 수 있습니다. 경우에 따라 정책에 추가하려는 데스크톱 PC에 없는 앱을 사용할 수 있습니다.

다음은 HoloLens 2 디바이스에 일반적으로 사용되고 In-Box 앱의 목록입니다.

| 앱 이름                   | 패키지 패밀리 이름                                |
|----------------------------|----------------------------------------------------|
| 3D 뷰어                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 앱 설치 관리자              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| 캘린더                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 카메라                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 피드백 허브               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 파일 탐색기              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 영화 & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 사진                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| 설정                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 팁                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - 앱 설치 관리자 차단하면 앱 설치 관리자 앱만 차단되고 Microsoft Store 같은 다른 원본 또는 MDM 솔루션에서 설치된 앱은 차단되지 않습니다.

### <a name="how-to-find-a-package-family-name"></a>패키지 패밀리 이름을 찾는 방법

앱이 이 목록에 없는 경우 사용자는 차단하려는 앱을 설치한 HoloLens 2 연결된 장치 포털 사용하여 PackageRelativeID를 확인하고 이 목록에서 PackageFamilyName을 얻을 수 있습니다.

1. HoloLens 2 디바이스에 앱을 설치합니다. 
1. 개발자용 설정 -> 업데이트 & 보안 -> 열고 **개발자 모드를** 사용하도록 설정한 다음, **디바이스 포털 을** 사용하도록 설정합니다. 
    1. 자세한 지침은 [여기에서 디바이스 포털 설정 및 사용에](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)대해 자세히 읽어보세요.
1. 장치 포털 연결되면 **보기,** **앱으로** 이동합니다. 
1. 설치된 앱 패널 내에서 드롭다운을 사용하여 설치된 앱을 선택합니다. 
1. PackageRelativeID를 찾습니다. 
1. !앞에 앱 문자를 복사합니다. 이러한 문자는 PackageFamilyName이 됩니다.


