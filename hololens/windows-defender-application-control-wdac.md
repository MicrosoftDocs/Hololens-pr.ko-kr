---
title: Windows Defender 응용 프로그램 제어-WDAC
description: Windows Defender 응용 프로그램 컨트롤의 정의 및이를 사용 하 여 HoloLens 혼합 현실 장치를 관리 하는 방법에 대 한 개요입니다.
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309405"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender 응용 프로그램 제어-WDAC

WDAC를 사용 하면 IT 관리자가 장치의 앱 시작을 차단 하도록 장치를 구성할 수 있습니다. 키오스크 모드와 같은 장치 제한의 방법과는 다릅니다. 사용자는 장치에서 앱을 숨기는 UI를 제공 하지만 여전히 시작할 수 있습니다. WDAC가 구현 되는 동안 앱은 모든 앱 목록에 계속 표시 되지만, WDAC는 장치 사용자가 해당 앱 및 프로세스를 시작할 수 없게 됩니다.

장치에 둘 이상의 WDAC 정책이 할당 될 수 있습니다. 시스템에 여러 개의 WDAC 정책이 설정 되어 있으면 대부분의 제한 사항이 적용 됩니다. 

> [!NOTE]
> 최종 사용자가 WDAC에 의해 차단 된 앱을 시작 하려고 하면 HoloLens에서 해당 앱을 시작할 수 없다는 알림이 수신 되지 않습니다.

다음은 사용자가 Microsoft Intune를 사용 하 [여 HoloLens 2 장치에서 앱을 허용 하거나 차단 하는 데 WDAC 및 Windows PowerShell을 사용](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법에 대 한 지침입니다.

사용자가 첫 번째 예제 단계를 사용 하 여 Windows 10 PC에 설치 된 앱을 검색 하는 경우 결과 범위를 좁히기 위해 몇 번의 시도를 해야 할 수 있습니다.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

패키지의 전체 이름을 모르는 경우 ' Add-appxpackage-name \* YourBestGuess '를 몇 번 실행 하 여 찾아야 할 수 있습니다 \* . 그런 다음 이름이 ' $package 1 = Get-AppxPackage-name Actual. PackageName '로 실행 됩니다.

예를 들어 Microsoft Edge에 대해 다음을 실행 하면 둘 이상의 결과가 반환 되지만 해당 목록에서 필요한 전체 이름이 MicrosoftEdge 인지 확인할 수 있습니다.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens 앱에 대 한 패키지 패밀리 이름

위에 연결 된 가이드에서 newPolicy.xml를 수동으로 편집 하 고 패키지 제품군 이름으로 HoloLens에 설치 된 응용 프로그램에 대 한 규칙을 추가할 수 있습니다. 사용자가 사용 하는 데 사용할 수 있는 앱이 있는 경우에는 정책에 추가 하려는 데스크톱 PC가 없는 경우가 있습니다.

다음은 HoloLens 2 장치에 일반적으로 사용 되는 앱과 In-Box 앱의 목록입니다.

| 앱 이름                   | 패키지 패밀리 이름                                |
|----------------------------|----------------------------------------------------|
| 3D 뷰어                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 앱 설치 관리자              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| 일정                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 카메라                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 피드백 허브               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 파일 탐색기              | c5e2524a-ea46-4f67 6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| TV & 영상                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 사진                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| 설정                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 팁                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-앱 설치 관리자를 차단 하면 Microsoft Store 또는 MDM 솔루션과 같은 다른 원본에서 설치 된 앱이 아닌 앱 설치 관리자 앱만 차단 됩니다.

### <a name="how-to-find-a-package-family-name"></a>패키지 제품군 이름을 찾는 방법

앱이이 목록에 없는 경우 사용자가 장치 포털을 사용할 수 있습니다 .이 경우 앱이 차단 될 것으로 표시 된 HoloLens 2에 연결 된 PackageRelativeID를 확인 하 고 PackageFamilyName을 받게 됩니다.

1. HoloLens 2 장치에 앱을 설치 합니다. 
1. 개발자를 위한 설정-업데이트 > & > 업데이트를 열고 **개발자 모드** 를 사용 하도록 설정한 다음 **장치 포털** 을 사용 하도록 설정 합니다. 
    1. 자세한 내용은 [장치 포털의 설정 및 사용](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)에 대 한 자세한 내용을 참조 하세요.
1. 장치 포털이 연결 되 면 **보기** , **앱** 으로 이동 합니다. 
1. 설치 된 앱 패널 내에서 드롭다운을 사용 하 여 설치 된 앱을 선택 합니다. 
1. PackageRelativeID를 찾습니다. 
1. 전에 앱 문자를 복사 합니다. 이러한 문자는 PackageFamilyName 됩니다.


