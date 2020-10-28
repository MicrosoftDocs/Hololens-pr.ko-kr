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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135576"
---
# Windows Defender Application Control

WDAC는 IT 관리자가 장치에서 앱의 실행을 차단 하도록 장치를 구성할 수 있도록 합니다. 이 방법은 사용자에 게 장치에서 앱을 숨기는 UI가 표시 되지만 계속 실행할 수 있는 키오스크 모드와 같은 장치 제한의 방법과는 다릅니다. WDAC가 구현 되는 동안에도 모든 앱 목록에 앱이 표시 되지만, WDAC는 해당 앱과 프로세스를 디바이스 사용자가 시작할 수 없도록 합니다.

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
1. > 설정-개발자를 위해 업데이트 & Securtiy-> 하 고 **개발자 모드** 와 **장치 포털**을 차례로 사용 하도록 설정 합니다. 
    1. 자세한 내용은 [여기에 디바이스 포털의 설정 및 사용](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)에 대 한 자세한 내용을 참조 하세요.
1. 디바이스 포털이 연결 되 면 **보기로** 이동한 다음 **앱**으로 이동 합니다. 
1. 설치 된 앱 패널 내에서 드롭다운을 사용 하 여 설치 된 앱을 선택 합니다. 
1. PackageRelativeID를 찾습니다. 
1. ! 앞에 앱 문자를 복사 하면 여러분의 PackageFamilyName 됩니다.

## 샘플 차단 앱 설치 관리자

예를 들어 [App Installer](app-deploy-app-installer.md) 앱을 차단 하 고 싶을 수 있습니다. 이 예제에 대 한 샘플 코드도 몇 가지 포함 되어 있습니다. [이 예제에 대 한 이러한 코드 샘플을](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)다운로드 하세요. Zip 파일에서 다음을 확인할 수 있습니다.

| 파일 | 사용 |
|-|-|
| compiledPolicy | [9 단계에서 생성 되며 마지막 10 단계에 사용 됩니다.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| mergedPolicy.xml | [6 단계에서 생성 됩니다.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| WDAC_Set syncml | WDAC에는 사용 되지 않지만 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 에 대해 사용할 수 있습니다. |

앱을 즉시 차단 하려면이 경우 앱 설치 관리자 앱에서 compiledPolicy 파일을 사용 하 고 위의 링크에서 10 단계로 건너뛰십시오. 이렇게 하면 사용자 지정 정책을 테스트 하 고 그룹 할당과 정책 구성이 올바른지 확인할 수 있습니다. 

앱 설치 관리자를 위 목록의 다른 앱 이나 다른 앱과 차단 하기 위해 WDAC 정책을 결합 하려는 경우 mergedPolicy.xml 파일을 사용 하 고 새 정책을 계속 병합할 수 있습니다. 위에 명시 된 것 처럼 WDAC 정책은 추가 되지 않으므로이는 필요 하지 않습니다. 

파일을 열려고 할 때 앱 설치 관리자 앱이 시작 되기 때문에 메시지가 표시 됩니다. WDAC에 의해 차단 된 앱 위에 설명 된 바와 같이, 사용자가 장치에서 파일을 열려고 하면 파일을 열 때 오류가 표시 되는 것을 확인 하는 메시지가 표시 되지 않습니다. 

![WDAC에서 앱 설치가 차단 됨](images\wdac-app-installer-no-launch.jpg)

WDAC를 사용 하지 않으려는 경우에는 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 를 사용 하 여 앱이 모두 실행 되는 응용 프로그램 설치 관리자 UX를 제거할 수 있습니다. 그 결과, 앱 설치 관리자 앱이 장치에서 제거 됩니다. .appx,. m 6,. a x번들 및 기타 파일 확장명과 함께 웹-앱 실행을 위한 프로토콜은 앱 설치 관리자 앱에서 더 이상 처리 되지 않습니다. 사용자는 스토어의 파일 확장명/프로토콜에 대 한 처리기를 검색 하 라는 메시지를 받게 되며 앱이 나열 되어 있지 않기 때문에 찾을 수 없게 됩니다.