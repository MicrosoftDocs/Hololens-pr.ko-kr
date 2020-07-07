---
title: HoloLens 다시 시작, 초기화 또는 복구
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: 고급 복구 도우미를 사용하여 이미지를 HoloLens 2로 플래시하는 방법
keywords: 사용 방법, 다시 부팅, 초기화, 복구, 하드 초기화, 소프트 초기화, 전원 주기, HoloLens, 종료, acr, 고급 복구 도우미
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828598"
---
# HoloLens 2 초기화 및 복구

## 장치 충전

가능하다면 문제 해결 절차를 시작하기 전에 적어도 장치가 20%에서 40% 정도 충전이 되어있는지 확인합니다.

HoloLens 2 장치와 함께 제공되는 충전기와 USB 유형 C 케이블을 사용하고 있는지 확인하세요. 사용할 수 없는 경우에는 사용 가능한 충전기가 적어도 15W의 전력을 지원하는지 확인합니다.

> [!NOTE]
> USB를 사용해 PC로 장치를 충전하면 시간이 아주 오래 걸리므로 PC는 가능하다면 사용하지 마세요.

장치가 제대로 부팅되고 실행되고 있는 경우에는 세 가지 방법으로 배터리 충전을 확인할 수 있습니다.

1. HoloLens 장치 UI의 주 메뉴에서 확인
2. 전원 버튼 가까이 있는 LED를 사용해서 확인 (40%에서는 LED가 최소 2개 켜진 것을 볼 수 있습니다.)
3. 호스트 PC에서 파일 탐색기 창을 열고 ‘이 PC’ 아래의 왼쪽에서 HoloLens 2 장치를 찾아서 확인
    
      a. 장치의 이름을 마우스 오른쪽 단추로 클릭하고 속성을 선택합니다. 장치의 배터리 잔량이 표시된 대화 상자가 나타납니다.

![HoloLens 2 초기화복구](images/ResetRecovery2.png)

장치를 시작 메뉴로 부팅할 수 없는 경우 호스트 PC에 있는 LED와 열거를 기록해 두고 문제 해결 가이드를 따르세요(https://docs.microsoft.com/hololens/hololens-troubleshooting). 장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않는 경우 장치를 호스트 PC에 다시 연결하지 않고 **** 하드 초기화 절차**를 실행하되 대신 전원 공급 장치에 연결합니다.** 장치가 충전될 때까지 1시간 이상 기다립니다.

## 장치 초기화

특정 상황에서는 소프트웨어에서 SW UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다. 

### 표준 절차
1. 유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.

2. **전원 버튼**을 15초간 길게 누릅니다. 모든 LED가 꺼집니다.

3. 2-3초 후 **전원 버튼**을 짧게 누르면 전원 버튼 가까이 있는 LED가 켜진 후 불이 켜지고 장치가 부팅되기 시작합니다. 

4. 장치를 호스트 PC에 연결하고 장치 관리자(Windows 10에서는 ****‘Windows’ 키**를 누른 후 **‘x’ 키**를 누른 다음 ‘장치 관리자’를 클릭)를 열어 아래 그림과 같이 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.**

![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLensRecovery.png)

### 하드 초기화 절차

표준 초기화 절차로 문제가 해결되지 않는 경우에는 하드 초기화 절차를 사용할 수 있습니다.

1. 유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.

2. **볼륨 작게 + 전원 버튼**을 15초간 누릅니다.

3. 장치가 자동으로 재부팅됩니다. 

4. 장치를 호스트 PC에 연결하고 장치 관리자(Windows 10에서는 ****‘Windows’ 키**를 누른 후 **‘x’ 키**를 누른 다음 ‘장치 관리자’를 클릭)를 열어 아래 그림과 같이 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.**

![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

## 장치 클린 리플래시

드물게 일부 상황에서 장치를 클린 플래시해야 할 수 있습니다. HoloLens 2 장치를 리플래시하는 두 가지 방법이 있습니다. 모든 리플래시 절차를 수행하려면[](https://www.microsoft.com/store/productId/9P74Z35SFRS8)Windows 스토어에서 고급 복구 도우미 앱을 설치[해야 합니다.](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 장치를 초기화하면 TPM 초기화를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.

고급 복구 도우미는 현재 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004)에 대한 기능 릴리스 빌드를 다운로드하도록 설정되어 있습니다. 최신 HoloLens 2 FFU를 다운로드하여 고급 복구 도우미를 통해 장치를 플래시하려면[](https://aka.ms/hololens2download)여기[에서 다운로드할 수 있습니다.](https://aka.ms/hololens2download) 이 기능은 최신 상태로 유지되며 일반적으로 사용할 수 있는 최신 빌드와 일치합니다. 

플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 감지할 준비가 되었는지 확인합니다.

![HoloLens 2 클린 리플래시](images/ARC1.png)

### 일반 절차

1. HoloLens 장치가 실행 중일 때 고급 복구 도우미 앱을 미리 실행해 놓은 Windows 10 PC에 연결합니다.

2. 장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트됩니다.

![HoloLens 2 클린 리플래시](images/ARC2.png)

3. 고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 플래시를 완료합니다.

### 수동 절차

장치가 제대로 부팅되지 않는 경우에는 HoloLens 2 장치를 복구 모드로 전환해야 할 수 있습니다.

1. 유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다. 

2. **전원 버튼**을 15초간 길게 누릅니다. 모든 LED가 꺼집니다. 

3. **볼륨 크게 버튼**을 누른 상태에서 **전원 버튼**을 눌렀다가 놓아 장치를 부팅합니다. 15초 후 볼륨 크게 버튼을 놓습니다. 장치의 5개 LED 중에서 가운데 LED만 켜집니다.

4. 장치를 호스트 PC에 연결하고 장치 관리자(Windows 10에서는 ****‘Windows’ 키**를 누른 후 **‘x’ 키**를 누른 다음 ‘장치 관리자’를 클릭)를 열어 아래 이미지와 같이 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.**

![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLensRecovery.png)

5. 장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트됩니다.

![HoloLens 2 클린 리플래시](images/ARC2.png)

6. 고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 플래시를 완료합니다.

## 앱 스토어를 사용하지 않고 ARC 다운로드

IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자가 다른 '오프라인' 배포 경로를 통해 이 앱을 사용할 수 있도록 할 수 있습니다. 

- 이 프로세스는 2단계에 표시된 것처럼 다른 앱에서도 사용할 수 있습니다. 이 가이드에서는 고급 복구 도우미에 중점을 두며 다른 오프라인 앱에 대해서는 수정될 예정입니다.  

이 배포 경로는 다음 단계를 통해 사용하도록 설정할 수 있습니다.
1.  [비즈니스용 스토어 웹 사이트](https://businessstore.microsoft.com)로 이동하여 Azure AD ID로 로그인합니다.
1.  관리 – 설정으로 이동하여 https://businessstore.microsoft.com/manage/settings/shop에 설명된 대로 **쇼핑 환경**에서 **오프라인 앱 표시**를 켭니다.  
1.  **내 그룹샵**으로 이동하여 고급 복구 도우미 앱을 검색합니다.
1.  **라이선스 유형** 상자를 오프라인으로 변경하고 **관리**를 클릭합니다.
1.  오프라인으로 사용하기 위해 패키지 다운로드에서 두 번째 파란색 **‘다운로드’** 버튼을 클릭합니다. 파일 확장명이 .appxbundle인지 확인합니다.
1.  이 단계에서 데스크톱 PC에서 인터넷에 연결되어 있으면 두 번 클릭하여 설치하면 됩니다. 
1.  IT 관리자가 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.
1.  대상 PC가 인터넷에 연결되어 있지 않으면 몇 가지 추가 단계를 수행해야 합니다. 
    1.  인코딩되지 않은 라이선스를 선택하고 **‘라이선스 생성’** 을 클릭한 다음 **‘필수 프레임 워크’** 에서 **‘다운로드’** 를 클릭합니다. 
    1.  인터넷에 연결할 수 없는 PC는 DISM으로 종속성과 라이선스를 사용하여 패키지를 적용해야 합니다. 관리자 명령 프롬프트에서 다음을 입력합니다.

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> 이 코드 예제에 나와 있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다. 제공된 예제의 위치와 다른 다운로드 위치를 선택했을 수도 있습니다. 필요에 따라 변경하도록 합니다.

> [!TIP]
> 고급 복구 도우미를 사용하여 FFU(Full Flash Update)를 오프라인으로 설치하려는 경우 플래시 이미지를 사용할 수 있도록 다운로드하는 것이 유용할 수 있습니다. 여기 [](https://aka.ms/hololens2download)HoloLens 2의 현재 이미지[가 있습니다.](https://aka.ms/hololens2download) 

다른 리소스:
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


