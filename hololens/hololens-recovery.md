---
title: HoloLens 다시 시작, 초기화 또는 복구
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 8c028ed39cf0925ebff18ca69889de2d87f1e7eb
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996416"
---
# HoloLens 2 다시 시작, 초기화 또는 복구

## 장치 충전

문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 20~40%정도 충전되어 있는지 확인합니다. HoloLens 2 장치와 함께 제공되는 충전기와 USB 유형 C 케이블을 사용하세요. 디바이스와 함께 제공되는 전원 공급 장치와 USB-C-to-C 케이블이 HoloLens 2를 충전하는 가장 좋은 방법입니다. 충전기는 18W의 전력을 공급합니다(2A에서 9V). 해당 액세서리를 사용할 수 없는 경우 사용할 수 있는 충전기가 최소 15W의 전원을 지원할 수 있는지 확인하세요.

> [!NOTE]
> 가능하면 PC에 USB를 연결해 장치를 충전하지 마세요. 속도가 느립니다.

장치가 제대로 부팅되고 실행되고 있는 경우에는 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.

- HoloLens 장치 UI의 주 메뉴에서 확인
- 전원 버튼 가까이 있는 LED로 확인(40%에서는 LED가 최소 2개 켜진 것을 볼 수 있습니다.)
    - 디바이스가 충전 중일 때 배터리 표시등이 켜지면서 현재 충전 수준을 나타냅니다.  마지막 표시등은 활성 충전을 나타내기 위해 안 페이드 인/페이드 아웃합니다.
    - HoloLens가 켜져 있으면 배터리 표시등에 배터리 수준이 5단계로 표시됩니다.
    - 5개의 표시등 중 하나만 켜져 있으면 배터리 잔량이 20% 미만입니다.
    - 배터리 잔량이 매우 낮은 상태에서 장치를 켜려고 하면 한 개의 표시등이 잠깐 깜박인 다음 꺼집니다.
- 호스트 PC에서 **파일 탐색기**를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾습니다. 장치를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. 대화 상자에 배터리 충전 수준이 표시됩니다.

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됩니다.](images/ResetRecovery2.png)

장치가 시작 메뉴로 부팅할 수 없는 경우 호스트 PC에 LED 모양과 장치 열거형을 기록해 둡니다. 그런 다음 [문제 해결 가이드](https://docs.microsoft.com/hololens/hololens-troubleshooting)를 따릅니다. 장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않으면 장치를 호스트 PC가 아닌 전원 공급 장치에 연결하고 [하드 초기화 절차](hololens-recovery.md#hard-reset-procedure)를 실행합니다. 장치가 충전될 때까지 1시간 이상 기다립니다.

## 장치 초기화

특정 상황에서는 소프트웨어 UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다.

### 표준 절차
1. 유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.

2. **전원** 버튼을 15초간 길게 누릅니다. 모든 LED가 꺼집니다.

3. 2-3초 후 **전원** 버튼을 짧게 누릅니다. 전원 버튼 옆에 있는 LED가 켜지며 장치가 시작되기 시작합니다.

4. 호스트 PC에 장치를 연결한 다음 장치 관리자를 엽니다. (Windows 10에서는 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자**를 클릭) 아래 이미지에 표시된 것처럼 장치가 *Microsoft HoloLens*로 제대로 열거되는지 확인합니다.

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

### 하드 초기화 절차

표준 초기화 절차로 문제가 해결되지 않는 경우에는 하드 초기화 절차를 사용할 수 있습니다.

1. 유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.

2. **볼륨 작게** + **전원** 단추를 15초 동안 누릅니다. 장치가 자동으로 재부팅됩니다.

4. 장치를 호스트 PC에 연결합니다.
5. 장치 관리자를 엽니다.(Windows 10에서는 ** Windows** 키를 누른 다음 **X** 키를 누르고 **장치 관리자**를 선택) 아래 이미지에 표시된 것처럼 장치에서 *Microsoft HoloLens*로 제대로 열거 되는지 확인 합니다.

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLens_DeviceManager.png)

## 장치 클린 리플래시

드물게 일부 상황에서 HoloLens 2를 ‘클린 플래시’해야 할 수 있습니다. 클린 리플래시는 다음 문제에 영향을 주지 않을 것으로 예상됩니다.
- [색상 균일성 표시](hololens2-display.md)
- 부팅시 소리가 나지만 디스플레이 출력이 없음
- [1-3-5-LED 패턴](hololens2-setup.md#lights-to-indicate-problems)
- [과열](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- OS 충돌(응용 프로그램 충돌과는 다름)

장치를 리플래시하는 두 가지 방법이 있습니다. 두 가지 방법 모두 [Windows 스토어에서 고급 복구 도우미](https://www.microsoft.com/store/productId/9P74Z35SFRS8)를 먼저 설치해야 합니다. 

>[!WARNING]
>장치를 리플래시하면 TPM 초기화 정보를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.

현재 고급 복구 도우미는 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004)에 대한 기능 릴리스 빌드를 다운로드하도록 설정되어 있습니다. 최신 HoloLens 2 FFU(Full Flash Update) 패키지를 다운로드하여 고급 복구 도우미를 통해 장치를 리플래시하려면 [여기에서 패키지를 다운로드하세요](https://aka.ms/hololens2download). 이 버전은 일반적으로 사용할 수 있는 최신 빌드입니다.

리플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 감지할 준비가 되었는지 확인합니다.

![HoloLens 2 클린 리플래시 스크린샷](images/ARC1.png)

### 일반 절차

1. HoloLens 장치가 실행 중일 때 고급 복구 도우미 앱을 미리 열려 있는 Windows 10 PC에 연결합니다.
 
   장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.

   ![HoloLens 2 클린 리플래시 초기 화면](images/ARC2.png)

3. 고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.

### 수동 절차

장치가 제대로 시작되지 않는 경우에는 HoloLens 2 장치를 복구 모드로 전환해야 할 수 있습니다.

1. 유형 C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치를 분리합니다.

2. **전원** 버튼을 15초간 길게 누릅니다. 모든 LED가 꺼집니다.

3. **볼륨 크게 버튼**을 누른 상태에서 **전원 버튼**을 눌렀다가 놓아 장치를 시작합니다. 15초 후 **볼륨 크게** 버튼을 놓습니다. LED 5개 중 가운데 LED만 켜집니다.

4. 호스트 PC에 장치를 연결하고 장치 관리자를 엽니다. (Windows 10에서는 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자**를 클릭) 아래 이미지에 표시된 것처럼 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.

   ![HoloLens 2 MicrosoftHoloLens복구](images/MicrosoftHoloLensRecovery.png)

   장치가 자동으로 감지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.

   ![HoloLens 2 클린 리플래시 화면](images/ARC2.png)

6. 고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.

## 앱 스토어를 사용하지 않고 ARC 다운로드

IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자가 '오프라인' 배포 경로를 통해 이 앱을 사용할 수 있도록 할 수 있습니다.

 >[!NOTE] 
 > - IT 관리자가 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.
 > - 이 가이드는 고급 복구 도우미에 중점을 두지만 다른 ‘오프라인’ 앱에 대해서도 이 프로세스를 사용할 수 있습니다.

배포 경로를 설정하려면 다음 단계를 따릅니다.
1. [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com)로 이동하고 Azure Active Directory ID를 사용하여 로그인합니다.

1. **관리 – 설정**으로 이동합니다. **장바구니**에서 **오프라인 앱 표시**를 켭니다. 
1. **내 그룹샵**으로 이동하여 [***고급 복구 도우미***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)를 검색합니다.
1. **라이선스 유형**을 ***오프라인***으로 변경하고 **관리**를 클릭합니다.
1. **오프라인으로 사용하기 위해 패키지 다운로드**에서 두 번째 파란색 **다운로드** 버튼을 클릭합니다. 파일 확장명이 *.appxbundle*인지 확인합니다.

    - 이 단계에서 데스크톱 PC에서 인터넷에 액세스할 수 있으면 패키지를 두 번 클릭하여 앱을 설치합니다.


    - 대상 PC가 인터넷에 연결되어 있지 않으면 다음 단계를 따릅니다. 
       1. 인코딩되지 않은 라이선스를 선택한 다음 **라이선스 생성**을 선택합니다.
       2. **필수 프레임워크**에서 **다운로드**를 선택합니다.
       3. DISM을 통해 종속성과 라이선스를 사용하여 패키지를 적용합니다. 관리자 명령 프롬프트에서 다음 명령을 실행합니다.

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > 이 코드 예제에 나와있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다. 예제의 위치와 다른 다운로드 위치를 선택했을 수도 있습니다. 필요에 따라 명령을 변경합니다.

> [!TIP]
> 고급 복구 도우미를 사용하여 FFU를 오프라인으로 설치하려는 경우 플래시 이미지를 다운로드하면 유용할 수 있습니다. [**HoloLens 2의 현재 이미지를 다운로드합니다**](https://aka.ms/hololens2download). 

다른 리소스:
- [오프라인 앱 배포](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [DISM 앱 패키지 (.appx 또는 .appxbundle) 서비스 명령줄 옵션](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
