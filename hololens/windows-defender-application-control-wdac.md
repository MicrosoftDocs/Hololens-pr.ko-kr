---
title: Windows Defender 응용 프로그램 제어 - WDAC
description: WDAC가 무엇일지와 HoloLens 장치를 관리하는 데 사용하는 방법에 대한 개요입니다.
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
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252649"
---
# Windows Defender 응용 프로그램 제어 - WDAC

WDAC를 사용하면 IT 관리자가 디바이스에서 앱 실행을 차단하도록 장치를 구성할 수 있습니다. 이는 사용자가 디바이스에서 앱을 숨기지만 계속 실행될 수 있는 UI를 표시하는 키오스크 모드와 같은 장치 제한 메서드와 다릅니다. WDAC가 구현되는 동안 앱은 여전히 모든 앱 목록에 표시되지만 WDAC는 해당 앱 및 프로세스가 장치 사용자가 시작하지 못하도록 합니다.

디바이스에 두 개 이상의 WDAC 정책이 할당될 수 있습니다. 시스템에서 여러 WDAC 정책이 설정되어 있는 경우 가장 제한적인 정책이 적용됩니다. 

> [!NOTE]
> 최종 사용자가 WDAC에 의해 차단된 앱을 시작하려고 하면 HoloLens에서 해당 앱을 시작하지 못했다는 알림이 수신되지 않습니다.

다음은 [Microsoft Intune에서 HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)장치에서 앱을 허용하거나 차단하기 위해 WDAC 및 Windows PowerShell 방법을 알아보는 사용자를 위한 가이드입니다.

사용자가 첫 번째 예제 단계를 사용하여 Windows 10 PC에 설치된 앱을 검색할 때 결과를 좁히기 위해 몇 가지 시도를 해야 할 수 있습니다.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

패키지의 전체 이름을 모르는 경우 'Get-AppxPackage -name \*YourBestGuess\*'를 몇 번 실행하여 패키지를 찾아야 할 수 있습니다. 그런 다음 이름이 '$package 1 = Get-AppxPackage -name Actual.PackageName'으로 실행됩니다.

예를 들어 Microsoft Edge에 대해 다음을 실행하면 결과가 두 개 이상 반환되지만 해당 목록에서 필요한 전체 이름이 Microsoft.MicrosoftEdge임이 식별될 수 있습니다.

```powershell
Get-AppxPackage -name *edge*
``` 

## HoloLens의 앱에 대한 패키지 패밀리 이름

위에 연결된 가이드에서 수동으로 패키지를 편집하고 newPolicy.xml 패밀리 이름으로 HoloLens에만 설치된 응용 프로그램에 대한 규칙을 추가할 수 있습니다. 경우에 따라 정책에 추가하고자 하는 데스크톱 PC에 없는 앱을 사용할 수 있습니다.

다음은 HoloLens 2 장치에 대해 일반적으로 In-Box 앱의 목록입니다.

| 앱 이름                   | 패키지 패밀리 이름                                |
|----------------------------|----------------------------------------------------|
| 3D 뷰어                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 앱 설치 관리자              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendar                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 카메라                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 피드백 허브               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 파일 탐색기              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 영화 및 TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 사진                     | Microsoft.Windows.사진_8wekyb3d8bbwe             |
| 설정                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 팁                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - 앱 설치 관리자를 차단하면 앱 설치 관리자 앱만 차단하고 Microsoft Store 또는 MDM 솔루션과 같은 다른 소스에서 설치된 앱은 차단하지 않습니다.

### 패키지 패밀리 이름을 찾는 방법

앱이 목록에 없는 경우 사용자는 차단하고자 하는 앱을 설치한 HoloLens 2에 연결된 Device Portal을 사용하여 PackageRelativeID를 확인한 다음 해당 장치에서 PackageFamilyName을 얻을 수 있습니다.

1. HoloLens 2 장치에 앱을 설치합니다. 
1. Open Settings -> Updates & Security ->, and enable **Developer mode** and then **Device portal.** 
    1. 자세한 내용은 여기에서 디바이스 포털의 설정 및 사용에 대해 [자세히 읽어 읽습니다.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. 디바이스 포털이 연결되면 **Views로** 이동한 다음 **앱으로 이동합니다.** 
1. 설치된 앱 패널 내에서 드롭다운을 사용하여 설치된 앱을 선택합니다. 
1. PackageRelativeID를 찾습니다. 
1. !, 이러한 문자는 PackageFamilyName 앞에 앱 문자를 복사합니다.


