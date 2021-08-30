---
title: HoloLens(1세대)의 알려진 문제
description: Unity 및 Windows 장치 포털 사용하여 HoloLens 고객과 개발자에게 영향을 줄 수 있는 알려진 문제 및 해결 방법 목록을 최신 상태로 유지하세요.
keywords: 문제 해결, 알려진 문제, 도움말
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189293"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens(1세대)의 알려진 문제

다음은 HoloLens 디바이스에 대한 알려진 문제의 현재 목록입니다. 홀수 동작이 표시되는 경우 먼저 여기를 확인하세요. 이 목록은 새 문제가 검색되거나 보고되거나 향후 소프트웨어 업데이트 HoloLens 문제가 해결될 때 업데이트됩니다.

>[!NOTE]
> - 차단되지 않는 문제가 발견되면 [피드백 허브](hololens-feedback.md)통해 HoloLens 디바이스에 보고하세요.
> - 사용자 의견을 제출하는 것 외에도 문제가 차단되는 경우 [지원 요청을 제출하세요.](https://aka.ms/hlsupport)


- [모든 HoloLens 세대의 알려진 문제](#known-issues-for-all-hololens-generations)
- [HoloLens 알려진 문제(1세대)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>모든 HoloLens 세대의 알려진 문제

### <a name="unity"></a>Unity

- HoloLens 개발에 권장되는 최신 버전의 Unity용 [도구 설치를](/windows/mixed-reality/install-the-tools) 참조하세요.
- Unity HoloLens Technical Preview의 알려진 문제는 HoloLens Unity 포럼 에 [설명되어 있습니다.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows 장치 포털

- Mixed Reality 캡처의 라이브 미리 보기 기능은 몇 초의 대기 시간을 나타낼 수 있습니다.

- 가상 입력 페이지의 가상 제스처 섹션 아래에 있는 제스처 및 스크롤 컨트롤이 작동하지 않습니다. 이를 사용하면 아무런 영향을 미치지 않습니다. 가상 입력 페이지의 가상 키보드가 제대로 작동합니다.

- 설정 개발자 모드를 사용하도록 설정한 후 스위치가 장치 포털 켜기까지 몇 초 정도 걸릴 수 있습니다.

### <a name="onedrive-camera-upload"></a>카메라 업로드 OneDrive

HoloLens OneDrive 앱은 직장 또는 학교 계정에 대한 자동 카메라 업로드를 지원하지 않습니다.

해결 방법:

- 비즈니스에 적합한 경우 소비자 Microsoft 계정에서 자동 카메라 업로드가 지원됩니다. 직장 또는 학교 계정 외에도 Microsoft 계정 로그인할 수 있습니다(OneDrive 앱은 이중 로그인을 지원함). OneDrive 내의 Microsoft 계정 프로필에서 자동 백그라운드 카메라 롤 업로드를 사용하도록 설정할 수 있습니다.

- 소비자 Microsoft 계정 사용하여 사진을 자동으로 업로드할 수 없는 경우 OneDrive 앱에서 수동으로 사진을 직장 또는 학교 계정에 업로드할 수 있습니다. 이렇게 하려면 OneDrive 앱에서 직장 또는 학교 계정에 로그인했는지 확인합니다. 단추를 선택하고 **+** **업로드** 선택합니다. **사진 > 카메라 롤로** 이동하여 업로드하려는 사진 또는 비디오를 찾습니다. 업로드하려는 사진 또는 비디오를 선택한 다음, **열기** 단추를 선택합니다.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens(1세대)의 알려진 문제

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Visual Studio 통해 HoloLens 연결하고 배포할 수 없음

> [!NOTE]
> 마지막 업데이트: 8/8 @ 5:11PM - Visual Studio VS 2019 버전 16.2를 릴리스했습니다. 여기에는 이 문제에 대한 수정이 포함됩니다. 이 오류가 발생하지 않도록 이 최신 버전으로 업데이트하는 것이 좋습니다.

Visual Studio VS 2019 버전 16.2를 릴리스했습니다. 여기에는 이 문제에 대한 수정이 포함됩니다. 이 오류가 발생하지 않도록 이 최신 버전으로 업데이트하는 것이 좋습니다.

근본 원인 문제: Visual Studio 2017의 Visual Studio 2015 또는 초기 릴리스를 사용하여 HoloLens 애플리케이션을 배포 및 디버그한 다음, 동일한 HoloLens Visual Studio 2017 또는 Visual Studio 2019의 최신 버전을 사용한 사용자는 영향을 받습니다. 최신 버전의 Visual Studio 새 버전의 구성 요소를 배포하지만 이전 버전의 파일이 디바이스에 남아 있어 최신 버전이 실패합니다.  그러면 다음 오류 메시지가 발생합니다. DEP0100: 대상 디바이스에 개발자 모드가 사용하도록 설정되어 있는지 확인합니다. 오류 80004005 인해 에서 개발자 라이선스를 가져올 수 \<ip\> 없습니다.

#### <a name="workaround"></a>해결 방법

우리 팀은 현재 수정 작업을 진행 중입니다. 그동안 다음 단계를 사용하여 문제를 해결할 수 있으며 배포 및 디버깅을 차단 해제할 수 있습니다.  

1. Visual Studio를 엽니다.

1. **File** > **New** > **Project** 를 선택합니다.

1. **Visual C#**  >  **Windows 데스크톱** 콘솔  >  **앱(.NET Framework)** 을 선택합니다.

1. 프로젝트에 이름(예: "HoloLensDeploymentFix")을 지정하고 프레임워크가 .NET Framework 4.5 이상으로 설정되어 있는지 확인한 다음 확인을 **선택합니다.**

1. 솔루션 탐색기 참조 **노드를** 마우스 오른쪽 단추로 클릭하고 다음 참조를 추가합니다(찾아보기 섹션에 선택하고 **찾아보기를 선택).** 

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0이 설치되어 있지 않은 경우 최신 버전을 사용합니다.

1. 솔루션 탐색기 프로젝트를 마우스 오른쪽 단추로 클릭하고   >  **기존 항목 추가를** 선택합니다.

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86으로 이동한 후 필터를 **모든 파일( . \* \* )** 로 변경합니다.

1. SirepClient.dll 및 SshClient.dll 모두 선택하고 **추가를** 선택합니다.

1. 솔루션 탐색기 두 파일을 찾아서 선택하고(파일 목록의 맨 아래에 있어야 합니다) **속성** 창에서 **출력 디렉터리로 복사를** **항상 복사로** 변경합니다.

1. 파일 맨 위에 있는 기존 문 목록에 다음을 `using` 추가합니다.

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 내부에 `static void Main(...)` 다음 코드를 추가합니다.

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. **빌드** > **솔루션 빌드** 를 선택합니다.

1. 명령 프롬프트 창을 열고 컴파일된 .exe 파일이 포함된 폴더로 cd합니다(예: C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. 실행 파일을 실행하고 디바이스의 IP 주소를 명령줄 인수로 제공합니다. USB를 사용하여 연결된 경우 127.0.0.1을 사용할 수 있고, 그렇지 않으면 디바이스의 Wi-Fi IP 주소를 사용할 수 있습니다.  예를 들어 "HoloLensDeploymentFix 127.0.0.1"입니다.

1. 도구가 메시지 없이 종료된 후(몇 초만 소요) 이제 Visual Studio 2017 이상에서 배포하고 디버그할 수 있습니다.  도구를 계속 사용할 필요는 없습니다.

추가 업데이트가 제공될 예정입니다.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens Microsoft Store 및 앱을 시작하는 문제

> [!NOTE]
> 마지막 업데이트: 오전 4/2 @ 10 - 문제가 해결되었습니다.

HoloLens Microsoft Store 및 앱을 시작하려고 할 때 문제가 발생할 수 있습니다. 하나 이상의 종속 앱이 계속 실행되는 동안 백그라운드 앱 업데이트가 특정 시퀀스로 최신 버전의 프레임워크 패키지를 배포할 때 문제가 발생한다는 것을 확인했습니다. 이 경우 자동 앱 업데이트가 새 버전의 .NET 네이티브 Framework(버전 10.0.25531~ 10.0.27413)를 제공했기 때문에 이전 버전의 프레임워크를 사용하는 실행 중인 모든 앱에 대해 실행 중인 앱이 올바르게 업데이트되지 않습니다.  프레임워크 업데이트 흐름은 다음과 같습니다.

1. 새 프레임워크 패키지는 저장소에서 다운로드되어 설치됩니다.

1. 이전 프레임워크를 사용하는 모든 앱 최신 버전을 사용하도록 '업데이트'되어 있습니다.

완료하기 전에 2단계가 중단되면 최신 프레임워크가 등록되지 않은 앱은 시작 메뉴에서 시작되지 않습니다.  HoloLens 모든 앱이 이 문제의 영향을 받을 수 있다고 생각합니다.

일부 사용자는 중단된 앱을 닫고 피드백 허브, 3D 뷰어 또는 사진 같은 다른 앱을 시작하면 문제가 해결되었다고 보고했습니다. 그러나 이 문제는 100% 작동하지 않습니다.

근본 원인으로 인해 이 문제가 업데이트 자체의 원인이 아니라 OS에서 버그가 발생하여 .NET 네이티브 프레임워크 업데이트가 잘못 처리되었습니다. 수정 사항을 확인하고 수정이 포함된 업데이트(OS 버전 17763.380)를 릴리스했다는 것을 알려드리게 되어 기쁘게 생각합니다.  

디바이스가 업데이트를 수행할 수 있는지 확인하려면 다음을 수행합니다.

1. 설정 앱으로 이동하여 **& 보안 업데이트를** 엽니다.

1. **업데이트 확인을 선택합니다.**

1. 17763.380으로 업데이트를 사용할 수 있는 경우 이 빌드로 업데이트하여 앱 중단 버그에 대한 수정 사항을 받으세요.

1. 이 버전의 OS로 업데이트하면 앱이 예상대로 작동합니다.

또한 모든 HoloLens OS 릴리스와 마찬가지로 Microsoft [다운로드 센터에](https://aka.ms/hololensdownload/10.0.17763.380)FFU 이미지를 게시했습니다.

업데이트를 사용하려는 경우 3월 29일 현재 Microsoft Store UWP 앱의 새 버전을 릴리스했습니다. 스토어의 업데이트된 버전이 있으면 다음을 수행합니다.

1. 저장소를 열고 로드를 확인합니다.
1. 꽃 제스처를 사용하여 메뉴를 엽니다.
1. 이전에 끊어진 앱을 열려고 시도합니다.
1. 계속 시작될 수 없는 경우 끊어진 앱의 아이콘을 길게 누르고 제거를 선택합니다.
1. 스토어에서 이러한 앱을 다시 설치합니다.

디바이스가 여전히 앱을 로드할 수 없는 경우 다음 단계에 따라 다운로드 센터를 통해 .NET 네이티브 Framework 및 런타임 버전을 테스트용으로 로드할 수 있습니다.

1. Microsoft 다운로드 센터에서 [이 zip 파일을](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 다운로드하세요. 압축을 풀면 두 개의 파일이 생성됩니다.  Microsoft .NET.Native.Runtime.1.7.appx 및 Microsoft .NET.Native.Framework.1.7.appx.

1. 디바이스의 잠금이 해제되었는지 확인하세요.  이전에 수행하지 않은 경우 [지침은 Windows 장치 포털 사용을](/windows/mixed-reality/using-the-windows-device-portal) 참조하세요.

1. 그런 다음 Windows 장치 포털. USB를 통해 이 작업을 수행하는 것이 좋습니다. 브라우저에 를 입력하면 http://127.0.0.1:10080 됩니다.

1. Windows 장치 포털 후 다운로드한 두 파일을 "사이드로드"해야 합니다. 이렇게 하려면 **앱** 섹션으로 이동하고 **앱을** 선택할 때까지 왼쪽 사이드바로 이동해야 합니다.

1. 그러면 아래와 유사한 화면이 표시됩니다.  **앱 설치** 섹션으로 이동하여 두 APPX 파일의 압축을 풀 위치를 찾습니다. 한 번에 하나씩만 수행할 수 있으므로 첫 번째 항목을 선택한 후 배포 섹션에서 "이동"을 클릭합니다. 그런 다음 두 번째 APPX 파일에 대해 이 작업을 수행합니다.

   ![Windows Side-Loaded 앱 설치를 장치 포털.](images/20190322-DevicePortal.png)

1. 이 시점에서 애플리케이션이 다시 작동하기 시작해야 하며 스토어에 도달할 수도 있다고 생각합니다.

1. 경우에 따라 영향을 받는 앱이 시작되기 전에 3D 뷰어 앱을 시작하는 추가 단계를 실행해야 합니다.

이 문제를 해결하는 과정을 진행하면서 기다려 주셔서 감사합니다. 성공적인 Mixed Reality 환경을 만들기 위해 커뮤니티와 지속적으로 협력하기를 기대합니다.

### <a name="device-update"></a>디바이스 업데이트

- 새 업데이트 후 30초 후에 셸이 한 번 사라질 수 있습니다. 세션을 다시 시작하려면 **개 제스처를** 수행하세요.

### <a name="visual-studio"></a>Visual Studio

- HoloLens 개발에 권장되는 최신 버전의 Visual Studio 도구 [설치를](/windows/mixed-reality/install-the-tools) 참조하세요.

- Visual Studio HoloLens 앱을 배포할 때 다음과 같은 오류가 **표시될 수 있습니다. 사용자 매핑된 섹션이 열려 있는 파일에서 요청된 작업을 수행할 수 없습니다. (HRESULT에서 예외: 0x800704C8)**. 이 경우 다시 시도하면 배포가 일반적으로 성공합니다.

### <a name="api"></a>API

- 애플리케이션이 사용자 뒤의 [포커스 지점](/windows/mixed-reality/focus-point-in-unity) 또는 camera.forward로 보통을 설정하는 경우 홀로그램은 혼합 현실 캡처 사진이나 비디오에 표시되지 않습니다. Windows 이 버그가 수정될 때까지 애플리케이션에서 [포커스 지점을](/windows/mixed-reality/focus-point-in-unity) 적극적으로 설정하는 경우 평면 보통이 카메라 앞으로 반대 방향으로 설정되도록 해야 합니다(예: normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Xbox 무선 컨트롤러

- Xbox 무선 컨트롤러 S는 HoloLens 함께 사용하려면 먼저 업데이트해야 합니다. 컨트롤러를 HoloLens 페어링하기 전에 [최신](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 상태로 유지합니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens 다시 부팅하면 컨트롤러가 HoloLens 자동으로 다시 연결되지 않습니다. 3분 후에 컨트롤러가 꺼질 때까지 가이드 단추 조명이 느리게 깜박입니다. 컨트롤러를 즉시 다시 연결하려면 조명이 꺼질 때까지 가이드 단추를 누른 채 컨트롤러의 전원을 끕니다. 컨트롤러의 전원을 다시 켜면 HoloLens 다시 연결됩니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens 대기로 들어가면 컨트롤러의 모든 입력이 HoloLens 절전 모드를 깨우게 됩니다. 사용이 완료되면 컨트롤러의 전원을 꺼서 이를 방지할 수 있습니다.

