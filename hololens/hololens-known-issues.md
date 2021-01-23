---
title: HoloLens에 대해 알려진 문제
description: Unity 및 Windows Device Portal을 사용하여 HoloLens 고객 및 개발자에게 영향을 줄 수 있는 알려진 문제 및 해결 방법 목록을 최신으로 유지하세요.
keywords: 문제 해결, 알려진 문제, 도움말
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284079"
---
# HoloLens에 대해 알려진 문제

HoloLens 장치에 대한 알려진 문제의 현재 목록입니다. 이상한 동작이 표시하는 경우 먼저 여기에서 확인하세요. 이 목록은 새 문제가 발견되거나 보고될 때 또는 향후 HoloLens 소프트웨어 업데이트에서 문제가 해결될 때 계속 업데이트됩니다.

>[!NOTE]
> - 차단되지 않는 문제가 발견되는 경우 피드백 허브를 통해 HoloLens 장치에 [보고하세요.](hololens-feedback.md)
> - 문제가 사용자에 대해 차단하는 경우 피드백을 제출하는 것 외에도 지원 요청을 [제출하십시오.](https://aka.ms/hlsupport)

- [모든 HoloLens 세대에 대한 알려진 문제](#known-issues-for-all-hololens-generations)
- [HoloLens 2 장치에 대한 알려진 문제](#known-issues-for-hololens-2-devices)
- [HoloLens(1세대)에 대한 알려진 문제](#known-issues-for-hololens-1st-gen)
- [HoloLens 에뮬레이터에 대한 알려진 문제](#known-issues-for-hololens-emulator)

## 모든 HoloLens 세대에 대한 알려진 문제

### Unity

- HoloLens 개발에 권장되는 최신 버전의 Unity에 대한 도구 설치를 참조합니다. [](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)
- Unity HoloLens Technical Preview의 알려진 문제는 [HoloLens Unity 포럼에 문서화되어 있습니다.](https://forum.unity3d.com/threads/known-issues.394627/)

### Windows Device Portal

- Mixed Reality 캡처의 실시간 미리 보기 기능은 몇 초의 대기 시간을 표시될 수 있습니다.

- 가상 입력 페이지에서 가상 제스처 섹션의 제스처 및 스크롤 컨트롤이 작동되지 않습니다. 이러한 기능을 사용하는 경우 아무 영향도 없습니다. 같은 페이지의 가상 키보드가 제대로 작동합니다.

- 설정에서 개발자 모드를 사용하도록 설정한 후 디바이스 포털을 켜기 위해 전환하는 데 몇 초 정도 걸릴 수 있습니다.

### OneDrive 카메라 업로드

HoloLens용 OneDrive 앱은 직장 또는 학교 계정에 대해 자동 카메라 업로드를 지원하지 않습니다.

해결 해결 작업:

- 비즈니스에서 사용할 수 있는 경우 소비자 Microsoft 계정에서 자동 카메라 업로드가 지원됩니다. 직장 또는 학교 계정 외에 Microsoft 계정에 로그인할 수 있습니다(OneDrive 앱은 이중 로그인을 지원). OneDrive 내의 Microsoft 계정 프로필에서 백그라운드 카메라 롤 자동 업로드를 사용하도록 설정할 수 있습니다.

- 소비자 Microsoft 계정을 사용하여 사진을 자동으로 업로드할 수 없는 경우 OneDrive 앱에서 사진을 수동으로 직장 또는 학교 계정에 업로드할 수 있습니다. 이를 위해 OneDrive 앱에서 직장 또는 학교 계정에 로그인해야 합니다. 단추를 **+** 선택하고 **업로드를 선택합니다.** 카메라 롤을 통해 사진으로 > 업로드할 사진 또는 **비디오를 찾아 보세요.** 업로드할 사진 또는 비디오를 선택한 다음 열기 **단추를** 선택합니다.

## HoloLens 2 장치에 대한 알려진 문제

### Microsoft Edge를 실행하지 못했습니다.

일부 고객은 Microsoft Edge가 시작되지 못하는 문제를 보고했습니다. 이러한 고객의 경우 이 문제는 재부팅을 통해 지속되고 Windows 또는 응용 프로그램 업데이트로 해결되지 않습니다. If you're experiencing this issue and you've confirmed [Windows is up-up-date,](hololens-updates.md#manually-check-for-updates)please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.

지금까지 문제를 근본으로 일으킬 수 없는 알려진 해결 방안은 없습니다. 피드백 허브를 통해 버그를 보고하면 조사에 도움이 됩니다!

### 키보드가 특수 문자로 전환되지 않습니다.

OOBE 중에 사용자가 직장 또는 학교 계정을 선택한 후 암호를 입력하고 나면 &123 단추를 탭하여 키보드의 특수 문자로 전환하려고 하여 특수 문자로 변경되지 않는 문제가 있습니다. 

해결 작업:
-   키보드를 닫고 텍스트 필드를 탭하여 다시 니다.
-   암호를 잘못 입력합니다. 다음에 키보드가 다시 시작될 때 예상대로 작동됩니다.
- 웹 인증, 키보드를 닫고 다른 **장치에서 로그인을 선택합니다.** 
-   숫자만 입력하면 사용자가 특정 키를 누르고 확장된 메뉴를 열 수 있습니다.
-   USB 키보드 사용

이는 영향을 주지 않습니다.
- 개인 계정을 사용하기로 선택한 사용자입니다.

### Insider 빌드로 리플래시된 디바이스의 Insider Preview 빌드에서 잠금을 언인플로한 후 파란색 화면이 표시됩니다.

이는 Insider Preview 빌드에 있는 사용자에게 영향을 미치고, 새 Insider Preview 빌드로 HoloLens 2를 다시 래시한 다음, Insider 프로그램에서 다시 시작하지 않는 문제입니다. 

이는 영향을 주지 않습니다.
- Windows Insider에 등록되지 않은 사용자 
- Insiders:
    - Insider 빌드가 버전 18362.x 이후로 장치를 등록한 경우
    - Insider Signed 19041.x 빌드를 플래시하고 Insider 프로그램에 등록된 경우 

해결 작업: 
- 문제 방지 
    - 비구성자 빌드를 플래시합니다. 정기적인 월별 업데이트 중 하나. 
    - Insider Preview 계속 보기
- 장치 리플래시

    1. 연결되지 않은 동안 완전히 전원을 [다가 HoloLens 2를](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 깜박이는 모드로 수동으로 전환합니다. 그런 다음 볼륨을 누를 때 전원 단추를 탭합니다.
    
    1. PC에 연결하고 고급 복구 도우미를 여는 경우 
    
    1. HoloLens 2를 기본 빌드로 플래시합니다.   

## HoloLens(1세대)에 대한 알려진 문제

### 다음을 통해 HoloLens에 연결하고 배포할 수 Visual Studio

> [!NOTE]
> Last Update: 8/8 @5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue. 이 오류가 발생하지 않도록 이 최신 버전으로 업데이트하는 것이 좋습니다.

Visual Studio 이 문제를 해결하는 VS 2019 버전 16.2가 릴리스되었습니다. 이 오류가 발생하는 것을 방지하기 위해 이 최신 버전으로 업데이트하는 것이 좋습니다.

근본 원인 문제: Visual Studio 2015 또는 Visual Studio 2017의 초기 릴리스를 사용하여 HoloLens에서 응용 프로그램을 배포 및 디버그한 다음 동일한 HoloLens에서 최신 버전의 Visual Studio 2017 또는 Visual Studio 2019를 사용한 사용자에게 영향을 미치게 됩니다. 최신 버전의 Visual Studio 구성 요소의 새 버전을 배포하지만 이전 버전의 파일이 장치에 남아 새 버전이 실패하게 됩니다.  이로 인해 DEP0100: 대상 디바이스에 개발자 모드가 설정되어 있는지 확인하십시오. 오류 \<ip\> 80004005로 인해 개발자 라이선스를 얻을 수 없습니다.

#### 해결 방법

Our team is currently working on a fix. 그 동안 다음 단계를 사용하여 문제를 해결하고 배포 차단 해제 및 디버깅을 지원할 수 있습니다.  

1. Visual Studio를 엽니다.

1. 새 **프로젝트 파일**  >  ****  >  **선택**

1. **Visual C#**  >  **Windows 데스크톱 콘솔**  >  **앱(.NET Framework)을 선택합니다.**

1. 프로젝트에 이름(예: "HoloLensDeploymentFix")을 지정하고 프레임워크가 .NET Framework 4.5 이상으로 설정되어 있는지 확인을 **선택합니다.**

1. 솔루션 탐색기에서 **참조** 노드를 마우스 오른쪽 단추로 클릭하고 **** 다음 참조를 추가합니다(찾아보기 섹션을 선택하고 **찾아보기**선택).

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0이 설치되어 있지 않은 경우 가장 최근 버전을 사용 합니다. 

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **기존**항목  >  **추가를 선택합니다.**

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86으로 찾아 필터를 **모든 파일(\*.\*)로**변경합니다.

1. 선택과 SirepClient.dll SshClient.dll 추가를 **선택합니다.**

1. 솔루션 탐색기에서 두 파일을 모두 찾아 선택하고(파일 목록 맨 아래에 표시) 속성 **** 창에서 출력 **디렉터리로** 복사를 항상 복사로 **변경합니다.**

1. 파일 맨 위에 기존 문 목록에 다음을 `using` 추가합니다.

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 내부에서 `static void Main(...)` 다음 코드를 추가합니다.

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 빌드 **솔루션**  >  **빌드를 선택합니다.**

1. 명령 프롬프트 창과 cd를 컴파일된 .exe 파일이 포함된 폴더(예: C:\MyProjects\HoloLensDeploymentFix\bin\Debug)를 런타임으로 니다.

1. 실행을 실행하고 장치의 IP 주소를 명령줄 인수로 제공합니다. USB를 사용하여 연결된 경우 127.0.0.1을 사용할 수 있습니다. 그렇지 않으면 장치의 IP 주소를 Wi-Fi 있습니다.  예를 들면 "HoloLensDeploymentFix 127.0.0.1"입니다.

1. 메시지가 없는 도구가 종료된 후(몇 초만 걸립니다) 이제 Visual Studio 2017 이상에서 배포하고 디버그할 수 있습니다.  도구를 계속 사용할 필요는 없습니다.

이후 업데이트가 제공될 예정입니다.

### HoloLens에서 Microsoft Store 및 앱을 시작해야 하는 문제

> [!NOTE]
> Last Update: 4/2 @ 10 AM - Issue resolved. 

HoloLens에서 Microsoft Store 및 앱을 시작하려고 할 때 문제가 있을 수 있습니다. 백그라운드 앱 업데이트가 하나 이상의 종속 앱이 계속 실행되는 동안 특정 시퀀스에서 최신 버전의 프레임워크 패키지를 배포할 때 문제가 발생하도록 결정했습니다. 이 경우 자동 앱 업데이트는 새 버전의 .NET 네이티브 프레임워크(버전 10.0.25531 ~ 10.0.27413)를 제공하여 실행 중인 앱이 이전 버전의 프레임워크를 사용하는 모든 실행 중인 앱에 대해 올바르게 업데이트되지 못했습니다.  프레임워크 업데이트 흐름은 다음과 같습니다. 

1. 새 프레임워크 패키지가 스토어에서 다운로드하여 설치됩니다.

1. 이전 프레임워크를 사용하는 모든 앱은 최신 버전을 사용하기 위해 '업데이트'됩니다.

2단계가 완료되기 전에 중단된 경우 새 프레임워크가 등록되지 않은 앱은 시작 메뉴에서 시작되지 않습니다.  HoloLens의 모든 앱은 이 문제의 영향을 받을 수 있습니다.

일부 사용자는 헝가리 앱을 닫고 피드백 허브, 3D 뷰어 또는 사진 같은 다른 앱을 실행하면 해당 문제를 해결할 수 있는 것으로 보고했습니다. 그러나 이 문제는 &mdash; 시간의 100%에서 작동하지 않습니다.

이 문제가 업데이트 자체를 유발하지는 않지만 .NET 네이티브 프레임워크 업데이트가 잘못 처리되는 OS의 버그가 발생했습니다. We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.  

장치에서 업데이트를 사용할 수 있는지 확인하려면 다음을 참조하세요.

1. 설정 앱으로 이동하여 보안 및 업데이트 **& 를 습니다.**

1. 업데이트 **확인을 선택합니다.**

1. If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.

1. 이 OS 버전으로 업데이트하면 앱이 예상대로 작동해야 합니다.

또한 모든 HoloLens OS 릴리스와 함께 FFU 이미지를 Microsoft 다운로드 센터에 [게시했습니다.](https://aka.ms/hololensdownload/10.0.17763.380)

업데이트를 원하지 않을 경우 3/29에 Microsoft Store UWP 앱의 새 버전을 릴리스했습니다. 스토어의 업데이트된 버전이 있는 경우:

1. 스토어를 열고 로드하는지 확인할 수 있습니다.
1. 블룸 제스처를 사용하여 메뉴를 열 수 있습니다.
1. 이전에 손상된 앱을 열려고 시도합니다.
1. 아직 실행될 수 없는 경우 손상된 앱의 아이콘을 탭하고 누르고 제거를 선택합니다.
1. 스토어에서 이러한 앱을 다시 설치합니다.

디바이스에서 여전히 앱을 로드할 수 없는 경우 다음 단계에 따라 다운로드 센터를 통해 .NET 네이티브 프레임워크 및 런타임 버전을 사이드로드할 수 있습니다.

1. Microsoft 다운로드 [센터에서](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 이 zip 파일을 다운로드하십시오. 파일의 양을 풀면 두 개의 파일이 생성됩니다.  Microsoft.NET.Native.Runtime.1.7.appx 및 Microsoft.NET.Native.Framework.1.7.appx.

1. 디바이스가 잠금 해제된지 확인합니다.  아직 수행하지 않은 경우 Windows [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 사용 지침을 참조하세요.

1. 그런 다음 Windows Device Portal에 들어가고자 합니다. USB를 통해 이 작업을 하는 것이 좋습니다. 브라우저에 입력하여 이 http://127.0.0.1:10080 작업을 하는 것이 좋습니다.

1. Windows Device Portal을 설치한 후 다운로드한 두 파일을 "테스트에 로드"해야 합니다. 이를 위해 앱 섹션으로 이동하여 앱을 선택할 때까지 **** 왼쪽 사이드 바를 아래로 **이동해야 합니다.**

1. 그러면 아래와 비슷한 화면이 표시됩니다.  앱 설치를 설명하는 섹션으로 이동하여 두 APPX 파일의 매핑을 언핑한 위치로 이동하려는 경우 **** 한 번만 작업을 할 수 있으므로 첫 번째 작업을 선택한 후 배포 섹션에서 "이동"을 클릭합니다. 그런 다음 두 번째 APPX 파일에 대해 이 작업을 실행합니다.

   ![Windows Device Portal to Install Side-Loaded App](images/20190322-DevicePortal.png)
   
1. 이제 응용 프로그램이 다시 작동하기 시작해야 하고 스토어에도 도착할 수 있습니다.

1. 경우에 따라 영향을 받는 앱이 시작되기 전에 3D 뷰어 앱을 시작하기 위해 추가 단계를 실행해야 합니다. 

이 문제를 해결하기 위한 프로세스를 진행해 주셔서 감사합니다. 성공적인 Mixed Reality 환경을 만들기 위해 커뮤니티와 계속 협력하기를 기대합니다.

### 장치 업데이트

- 새 업데이트 후 30초 후에 셸이 한 번 사라질 수 있습니다. 블룸 **제스처를** 수행하여 세션을 다시 시작해 주세요.

### Visual Studio

- [HoloLens](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 개발에 권장되는 최신 버전의 Visual Studio 설치를 참조합니다.

- Visual Studio 앱을 HoloLens에 배포할 때 오류가 표시될 수 있습니다. 사용자가 매핑한 섹션이 열려 있는 파일에 대해 요청된 작업을 수행할 **수 없습니다. (HRESULT에서 예외: 0x800704C8)**. 이 경우 다시 시도하면 배포가 일반적으로 성공합니다.

### API

- 응용 프로그램이 사용자 [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 뒤에 포커스 지점을 설정하거나 일반을 camera.forward로 설정하면 혼합 현실 캡처 사진 또는 비디오에 홀로그램이 나타나지 않습니다. Windows에서 이 버그가 해결될 때까지 응용 [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 프로그램이 적극적으로 포커스 지점을 설정하는 경우 평면 일반이 반대 카메라 앞으로 설정되도록 해야 합니다(예: normal = -camera.forward).

### Xbox 무선 컨트롤러

- Xbox 무선 컨트롤러 S를 업데이트해야 HoloLens에서 사용할 수 있습니다. 컨트롤러를 [](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) HoloLens와 페어링하기 전에 최신 정보를 확인 합니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens를 다시 시작하면 컨트롤러가 HoloLens에 자동으로 다시 연결되지 않습니다. 3분 후에 컨트롤러가 꺼질 때까지 안내 단추 표시등이 느리게 깜박입니다. 컨트롤러를 즉시 다시 연결하기 위해 조명이 꺼질 때까지 가이드 단추를 눌러 컨트롤러를 끄십시오. 컨트롤러 전원을 다시 니다. 이 경우 HoloLens에 다시 연결됩니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens가 대기 모드로 들어오면 컨트롤러의 모든 입력이 HoloLens를 해제합니다. 컨트롤러 사용이 완료되면 컨트롤러를 꺼서 이를 방지할 수 있습니다.

## HoloLens 에뮬레이터에 대한 알려진 문제

- Microsoft Store의 일부 앱은 에뮬레이터와 호환되지 않습니다. 예를 들어, 에뮬레이터에서 유정 Conker 및 Fragments를 재생할 수 없습니다.
- 에뮬레이터에서는 PC 웹캠을 사용할 수 없습니다.
- Windows Device Portal의 실시간 미리 보기 기능은 에뮬레이터에서 작동하지 않습니다. 혼합 현실 비디오 및 이미지를 캡처할 수 있습니다.
