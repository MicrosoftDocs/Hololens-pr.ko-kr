---
title: HoloLens 다시 시작, 초기화 또는 복구
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: 고급 복구 도우미를 사용하여 이미지를 HoloLens 2로 플래시하는 방법.
keywords: 사용 방법, 다시 부팅, 초기화, 복구, 하드 리셋, 소프트 리셋, 전원 주기, HoloLens, 종료, acr, 고급 복구 도우미
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: e9aad32891bb093cbce18671b76549788b19afcb
ms.sourcegitcommit: c4fe077e9e19a3b0a9fad8defa4b51547c5ae3c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2021
ms.locfileid: "123261926"
---
# <a name="restart-reset-or-recover-hololens-2"></a>HoloLens 2 다시 시작, 초기화 또는 복구

>[!IMPORTANT]
> 문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다. 전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.

HoloLens 2와 함께 제공된 [충전기와 USB Type-C 케이블](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)을 사용하는 것이 장치를 충전하는 가장 좋은 방법입니다. 충전기는 18W의 전력을 공급합니다(9V/2A). HoloLens 2 장치는 제공된 벽면 충전기를 사용하여 장치가 대기 중일 때 65분 이내에 배터리를 완전 충전할 수 있습니다. 해당 액세서리를 사용할 수 없는 경우 사용 가능한 충전기가 최소 15W의 전력을 지원할 수 있는지 확인하세요.

> [!NOTE]
> 가능하면 PC에 연결하여 USB를 통해 장치를 충전하지 마세요. 속도가 느립니다.

장치가 제대로 부팅되고 실행되고 있으면 다음과 같은 세 가지 방법으로 배터리 충전 수준을 확인할 수 있습니다.

- HoloLens 장치 UI의 주 메뉴에서 확인합니다.
- 전원 단추 가까이에 있는 LED로 확인합니다(40% 충전의 경우 LED가 최소 2개 켜진 것을 볼 수 있어야 함).
    - 장치가 충전 중일 때는 배터리 표시등이 켜져 있고 현재 충전 수준을 나타냅니다.  마지막 표시등은 페이드 인/페이드 아웃하여 활성 충전을 나타냅니다.
    - HoloLens가 켜져 있으면 배터리 표시등이 배터리 잔량을 5단계로 표시합니다.
    - 5개의 표시등 중 하나만 켜져 있으면 배터리 잔량이 20% 미만입니다.
    - 배터리 잔량이 매우 낮은 상태에서 장치를 켜려고 하면 표시등 1개가 잠깐 깜박인 다음 꺼집니다.
- 호스트 PC에서 **파일 탐색기** 를 열고 **이 PC** 아래의 왼쪽에서 HoloLens 2 장치를 찾습니다. 장치를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다. 대화 상자에 배터리 충전 잔량이 표시됩니다.

   ![HoloLens 2 속성 화면에 배터리 충전 수준이 표시됩니다.](images/ResetRecovery2.png)

장치가 시작 메뉴로 부팅할 수 없는 경우 호스트 PC의 LED 모양과 장치 열거형을 기록해 둡니다. 그런 다음, [문제 해결 가이드](hololens-troubleshooting.md)를 따릅니다. 장치 상태가 문제 해결 가이드에 나열된 상태에 해당하지 않으면 장치를 호스트 PC가 아닌 전원 공급 장치에 연결하고 [하드 리셋 절차](hololens-recovery.md#hard-reset-procedure)를 수행합니다. 장치가 충전될 때까지 1시간 이상 기다립니다.

## <a name="reset-the-device"></a>디바이스 재설정

특정 상황에서는 소프트웨어 UI를 사용하지 않고 수동으로 장치를 초기화해야 할 수 있습니다.

### <a name="standard-procedure"></a>표준 절차

1. Type-C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치 연결을 해제합니다.

2. **전원** 단추를 15초간 길게 누릅니다. 모든 LED가 꺼져야 합니다.

3. 2~3초 후 **전원** 단추를 짧게 누릅니다. 전원 단추 옆에 있는 LED가 켜지고 장치가 시작됩니다.

4. 호스트 PC에 장치를 연결한 다음 장치 관리자를 엽니다. (Windows 10의 경우 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자** 를 선택합니다.) 아래 이미지에 표시된 것처럼 장치가 *Microsoft HoloLens* 로 제대로 열거되는지 확인합니다.

   ![HoloLens 2 MicrosoftHoloLensRecovery 디바이스 관리자.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>하드 리셋 절차

표준 초기화 절차가 작동하지 않는 경우에는 하드 리셋 절차를 사용합니다.

1. Type-C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치 연결을 해제합니다.

1. **Volume down** + **전원** 단추를 15초 동안 길게 누릅니다. 장치가 자동으로 다시 시작합니다.

1. 호스트 PC에 장치를 연결합니다.

1. 장치 관리자를 엽니다(Windows 10의 경우 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자** 를 선택). 아래 이미지에 표시된 것처럼 장치에서 *Microsoft HoloLens* 로 제대로 열거되는지 확인합니다.

   ![HoloLens 2 MicrosoftHoloLensRecovery 디바이스 관리자 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>장치 클린 리플래시

드문 상황에서 HoloLens 2를 "클린 플래시"해야 할 수 있습니다. 클린 리플래시는 다음 문제에 영향을 주지 않을 것으로 예상됩니다.

- [색 균일성 표시](hololens2-display.md)
- 부팅 시 소리가 나지만 디스플레이 출력이 없음
- [1-3-5-LED 패턴](hololens2-setup.md#lights-to-indicate-problems)
- [과열](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- OS 충돌(응용 프로그램 충돌과 다름)

장치를 리플래시하는 방법은 두 가지입니다. 두 경우 모두 먼저 [Windows 스토어에서 고급 복구 도우미를 설치](https://www.microsoft.com/store/productId/9P74Z35SFRS8)해야 합니다.

>[!WARNING]
>장치를 리플래시하면 TPM 초기화 정보를 포함하여 모든 개인 데이터, 앱 및 설정 내용이 지워집니다.

기본적으로 고급 복구 도우미는 최신 기능 릴리스 빌드를 다운로드하도록 설정되어 있습니다. 최신 기능 릴리스에 대해 알아보려면 [HoloLens 2 릴리스 정보](hololens-release-notes.md)를 참조하세요. 최신 HoloLens 2 FFU(Full Flash Update) 패키지를 다운로드하여 고급 복구 도우미를 통해 디바이스를 리플래시하려면 최신 월별 HoloLens 2 이미지를 다운로드합니다[https://aka.ms/hololens2download](https://aka.ms/hololens2download). 이 버전은 일반적으로 사용 가능한 최신 빌드입니다.

리플래시 절차를 시작하기 전에 앱이 Windows 10 PC에 설치되어 실행 중인지 확인하고 장치를 탐지할 준비가 되었는지 확인합니다. 또한 HoloLens가 최소 40%까지 충전되는지 확인합니다.

![HoloLens 2 클린 리플래시 스크린샷.](images/ARC1.png)

### <a name="normal-procedure"></a>일반 절차

1. HoloLens 장치가 실행 중일 때 이전에 고급 복구 도우미 앱을 열었던 Windows 10 PC에 연결합니다.

   장치가 자동으로 탐지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.

   ![HoloLens 2 클린 리플래시 초기 화면.](images/ARC2.png)

1. 고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.

### <a name="manual-procedure"></a>수동 절차

다음과 같은 경우 디바이스를 복구 모드로 전환해야 할 수 있습니다.

- HoloLens 2 올바르게 시작되지 않는 경우
- 고급 복구 도우미가 디바이스를 검색할 수 없는 경우
- 사용자가 한 명뿐인 디바이스의 암호/PIN을 더 이상 알지 못하는 경우

1. Type-C 케이블을 뽑아 전원 공급 장치 또는 호스트 PC에서 장치 연결을 해제합니다.

2. **전원** 단추를 15초간 길게 누릅니다. 모든 LED가 꺼져야 합니다.

3. **Volume up** 단추를 누른 상태에서 **전원** 단추를 놓아서 장치를 시작합니다. 15초 동안 기다린 다음 **Volume up** 단추를 놓습니다. 5개 LED 중 가운데 LED만 켜집니다.

4. 장치를 호스트 PC에 연결하고 장치 관리자를 엽니다. (Windows 10의 경우 **Windows** 키를 누른 후 **X** 키를 누른 다음 **장치 관리자** 선택합니다.) 아래 이미지에 표시된 것처럼 장치가 Microsoft HoloLens로 제대로 열거되는지 확인합니다.

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   장치가 자동으로 탐지되고 고급 복구 도우미 앱 UI가 다음과 같이 업데이트 프로세스를 시작합니다.

   ![HoloLens 2 클린 리플래시 화면.](images/ARC2.png)

6. 고급 복구 도우미 앱 UI에서 HoloLens 2 장치를 선택하고 지침에 따라 리플래시를 완료합니다.

## <a name="troubleshoot-advanced-recovery-companion"></a>고급 복구 도우미 문제 해결

1. 플래시를 시도하기 전에 장치가 40% 이상 충전되었는지 확인합니다.

1. 디바이스가 잠금 해제되어 있는지 확인합니다.

1. 디바이스가 허브가 아닌 호스트 PC에 직접 연결되어 있는지 확인합니다.

1. 디바이스가 범용 직렬 버스 드라이버에서 HoloLens/HoloLens 복구 디바이스로 표시되지 않는 경우 다음을 확인합니다.
    1. Qualcomm HS-USB 디바이스로서의 **포트**
    1. QUSB_BULK 디바이스로서의 **기타 디바이스** - 호스트 PC에 HoloLens를 감지하는 데 필요한 드라이버가 없습니다. 마우스 오른쪽 단추를 클릭하고 드라이버 업데이트를 선택하여 온라인으로 드라이버를 검색하거나 [Windows 업데이트 설정에서 선택적 업데이트를 확인합니다](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). 드라이버가 다운로드되면 ARC가 이를 검색할 수 있어야 합니다.

1. ARC가 장치를 탐지하지 못하는 경우 PC의 파일 탐색기를 통해 장치에 연결할 수 있는지 확인합니다. 연결할 수 없는 경우, 다음과 같이 합니다.

    1. 장치에 해당 연결을 사용하지 않도록 설정하는 USB 정책이 있을 수 있습니다. 이 경우 [수동 플래싱 모드](hololens-recovery.md#manual-procedure)를 사용해 보세요.
    2. 정책이 없으면 다른 USB 케이블을 사용해 보세요.

1. 장치가 [1-3-5-LED 패턴](hololens2-setup.md#lights-to-indicate-problems)을 표시하지 않는지 확인합니다.

## <a name="download-arc-without-using-the-app-store"></a>앱 스토어를 사용하지 않고 ARC 다운로드

IT 환경에서 Windows 스토어 앱을 사용하지 못하도록 하거나 소매점에 대한 액세스를 제한하는 경우 IT 관리자는 "오프라인" 배포 경로를 통해 이 앱을 사용 가능하게 만들 수 있습니다.

 >[!NOTE]
 > - IT 관리자는 SCCM(System Center Configuration Manager) 또는 Intune을 통해 이 앱을 배포할 수도 있습니다.
 > - 이 가이드는 고급 복구 도우미에 중점을 두지만 다른 "오프라인" 앱에 대해서도 이 프로세스를 사용할 수 있습니다.

배포 경로를 사용하도록 설정하려면 다음 단계를 따릅니다.

1. [비즈니스용 Microsoft Store](https://businessstore.microsoft.com)로 이동하여 Azure Active Directory ID를 사용하여 로그인합니다.

1. **관리 - 설정** 으로 이동합니다. **Shopping experience** 에서 **Show offline apps** 를 켭니다.

1. **shop for my group** 으로 이동하고 [**_고급 복구 도우미_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)를 검색합니다.

1. **라이선스 형식** 을 **_오프라인_*으로 변경하고* 관리** 를 선택합니다.

1. **Download the package for offline use** 에서 두 번째 파란색 **다운로드** 단추를 선택합니다. 파일 확장명이 *.appxbundle* 인지 확인합니다.

    - 이 단계에서 데스크톱 PC에 인터넷이 연결되어 있으면 패키지를 두 번 클릭하여 앱을 설치합니다.

    - 대상 PC에 인터넷이 연결되어 있지 않으면 다음 단계를 따릅니다.
       1. 인코딩되지 않은 라이선스를 선택하고 **Generate license** 를 선택합니다.
       2. **Required Frameworks** 에서 **다운로드** 를 선택합니다.
       3. DISM을 사용하여 종속성과 라이선스로 패키지를 적용합니다. 관리자 명령 프롬프트에서 다음 명령을 실행합니다.

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > 이 코드 예제에 나와 있는 버전 번호는 현재 사용 가능한 버전과 다를 수 있습니다. 예제와 다른 다운로드 위치를 선택했을 수도 있습니다. 필요에 따라 명령을 변경합니다.

> [!TIP]
> 고급 복구 도우미를 사용하여 오프라인으로 FFU를 설치하려는 경우 플래시 이미지를 다운로드하면 유용할 수 있습니다. [**HoloLens 2에 대한 현재 이미지를 다운로드합니다**](https://aka.ms/hololens2download).

기타 리소스:

- [오프라인 앱 배포](/microsoft-store/distribute-offline-apps) 
- [DISM 앱 패키지(.appx 또는 .appxbundle) 서비스 명령줄 옵션](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
