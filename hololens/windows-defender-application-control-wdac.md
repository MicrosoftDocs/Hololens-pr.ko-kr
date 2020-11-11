---
title: Windows Defender Application Control
description: WDAC에 대 한 개요와 HoloLens 장치를 관리 하는 데 사용 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163121"
---
# Windows Defender Application Control

WDAC는 IT 관리자가 장치에서 앱의 실행을 차단 하도록 장치를 구성할 수 있도록 합니다. 이 방법은 사용자에 게 장치에서 앱을 숨기는 UI가 표시 되지만 계속 실행할 수 있는 키오스크 모드와 같은 장치 제한의 방법과는 다릅니다. WDAC가 구현 되는 동안에도 모든 앱 목록에 앱이 표시 되지만, WDAC는 해당 앱과 프로세스를 디바이스 사용자가 시작할 수 없도록 합니다.

장치에 하나 이상의 WDAC 정책이 할당 될 수 있습니다. 시스템에 여러 WDAC 정책이 설정 된 경우 대부분의 제한 사항이 적용 됩니다. 

> [!NOTE]
> 최종 사용자가 WDAC에 의해 차단 된 앱을 시작 하려고 하면 HoloLens에서 해당 앱을 시작할 수 없다는 알림을 받지 않게 됩니다.

다음은 [Windows Intune을 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단 하는 데 WDAC 및 Windows PowerShell을 사용](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법을 배우는 사용자를 위한 지침입니다.

사용자가 첫 번째 예제 단계를 사용 하 여 Windows 10 PC에 설치 된 앱을 검색 하는 경우 결과 범위를 좁히는 몇 가지 시도를 수행 해야 할 수 있습니다.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

패키지의 전체 이름을 모르는 경우 검색 하려면 ' Add-appxpackage-name \ * YourBestGuess \ * '을 몇 번 실행 해야 할 수 있습니다. 그런 다음 이름 실행 ' $package 1 = Get-AppxPackage-name PackageName '

예를 들어 Edge에 대해 다음을 실행 하면 두 개 이상의 결과가 반환 되지만 해당 목록에서 필요한 전체 이름은 Microsoft MicrosoftEdge입니다. 

```powershell
Get-AppxPackage -name *edge*
``` 

## HoloLens에서 앱에 대 한 패키지 패밀리 이름

위에 링크 된 가이드에서 newPolicy.xml 수동으로 편집 하 고 패키지 패밀리 이름을 사용 하 여 HoloLens에 설치 된 응용 프로그램에 대 한 규칙을 추가할 수 있습니다. 경우에 따라 정책에 추가 하려는 데스크톱 PC에서 사용 하지 않는 앱이 있을 수 있습니다. 

다음은 HoloLens 2 장치용으로 자주 사용 되는 앱과 In-Box 하는 목록입니다.

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
| 사진                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| 설정                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 팁                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-차단 앱 설치 관리자는 앱 설치 관리자 앱만 차단 하 고 Microsoft Store 또는 MDM 솔루션 등의 다른 원본에서 설치 된 앱은 제외 합니다.

### 패키지 패밀리 이름을 찾는 방법

앱이이 목록에 없는 경우 사용자는 디바이스 포털을 사용 하 여 앱을 차단 하기 위해 설치 된 HoloLens 2에 연결 하 고 PackageRelativeID를 확인 하 고 PackageFamilyName를 받을 수 있습니다.

1. HoloLens 2 장치에 앱을 설치 합니다. 
1. 열기 설정-> & 보안 > 개발자 용으로 업데이트 하 고 **개발자 모드** 와 **Device portal**을 차례로 사용 하도록 설정 합니다. 
    1. 자세한 내용은 [여기에 디바이스 포털의 설정 및 사용](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)에 대 한 자세한 내용을 참조 하세요.
1. 디바이스 포털이 연결 되 면 **보기로** 이동한 다음 **앱**으로 이동 합니다. 
1. 설치 된 앱 패널 내에서 드롭다운을 사용 하 여 설치 된 앱을 선택 합니다. 
1. PackageRelativeID를 찾습니다. 
1. ! 앞에 앱 문자를 복사 하면 여러분의 PackageFamilyName 됩니다.


