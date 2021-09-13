---
title: HoloLens에 대 한 알려진 문제 (첫 번째 Gen)
description: Unity 및 Windows Device Portal을 사용 하 여 고객과 개발자 HoloLens에 영향을 줄 수 있는 알려진 문제 및 해결 방법 목록을 최신 상태로 유지 합니다.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033090"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens에 대 한 알려진 문제 (첫 번째 Gen)

다음은 HoloLens 장치에 대 한 알려진 문제의 현재 목록입니다. 이상한 동작이 표시 되는 경우 먼저 여기를 확인 하세요. 이 목록은 새로운 문제가 검색 되거나 보고 되거나 향후 HoloLens 소프트웨어 업데이트에서 문제가 해결 될 때 업데이트 됩니다.

>[!NOTE]
> - 차단 되지 않는 문제를 발견 한 경우 [피드백 허브](hololens-feedback.md)를 통해 HoloLens 장치에 보고 하세요.
> - 문제가 발생 하는 경우 피드백을 작성 하는 것 외에도 [지원 요청](https://aka.ms/hlsupport)을 제출 하세요.


- [모든 HoloLens 세대에 대 한 알려진 문제](#known-issues-for-all-hololens-generations)
- [HoloLens에 대 한 알려진 문제 (첫 번째 Gen)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>모든 HoloLens 세대에 대 한 알려진 문제

### <a name="unity"></a>Unity

- HoloLens 개발에 권장 되는 최신 버전의 Unity 용 [도구 설치](/windows/mixed-reality/install-the-tools) 를 참조 하세요.
- unity HoloLens Technical Preview의 알려진 문제는 [HoloLens unity 포럼](https://forum.unity3d.com/threads/known-issues.394627/)에 설명 되어 있습니다.

### <a name="windows-device-portal"></a>Windows 장치 포털

- 혼합 현실 캡처의 실시간 미리 보기 기능은 몇 초 동안 대기 시간을 나타낼 수 있습니다.

- 가상 입력 페이지에서 가상 제스처 섹션 아래의 제스처 및 스크롤 컨트롤이 작동 하지 않습니다. 이를 사용 하면 아무런 영향을 주지 않습니다. 가상 입력 페이지의 가상 키보드가 제대로 작동 합니다.

- 설정에서 개발자 모드를 사용 하도록 설정한 후 장치 포털을 켜는 스위치를 사용 하도록 설정 하는 데 몇 초 정도 걸릴 수 있습니다.

### <a name="onedrive-camera-upload"></a>OneDrive 카메라 업로드

HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다.

해결 방법:

- 비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다. 회사 또는 학교 계정 외에도 Microsoft 계정에 로그인 할 수 있습니다. OneDrive 앱은 이중 로그인을 지원 합니다. OneDrive 내의 Microsoft 계정 프로필에서 자동, 배경 카메라 롤 업로드를 사용 하도록 설정할 수 있습니다.

- 회사를 자동으로 업로드 하는 데 소비자 Microsoft 계정를 안전 하 게 사용할 수 없는 경우 OneDrive 앱에서 회사 또는 학교 계정에 사진을 수동으로 업로드할 수 있습니다. 이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 했는지 확인 합니다. 단추를 선택 **+** 하 고 **업로드** 를 선택 합니다. **사진 > 카메라 롤** 로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다. 업로드 하려는 사진 또는 비디오를 선택 하 고 **열기** 단추를 선택 합니다.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens에 대 한 알려진 문제 (첫 번째 Gen)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Visual Studio를 통해 HoloLens에 연결 하 고 배포할 수 없습니다.

> [!NOTE]
> 마지막 업데이트: 8/8 @ 5:11pm-Visual Studio에이 문제에 대 한 수정 사항이 포함 된 VS 2019 버전 16.2이 릴리스 되었습니다. 이 오류가 발생 하지 않도록 최신 버전으로 업데이트 하는 것이 좋습니다.

Visual Studio에는이 문제에 대 한 수정 사항이 포함 된 VS 2019 버전 16.2이 릴리스 되었습니다. 이 오류가 발생 하지 않도록 최신 버전으로 업데이트 하는 것이 좋습니다.

문제 근본 원인: 2015 또는 조기 Visual Studio 2017 릴리스를 Visual Studio 사용 하 여 HoloLens에 응용 프로그램을 배포 하 고 디버그 한 다음 Visual Studio 2017 또는 Visual Studio 2019의 최신 버전을 사용 하는 사용자가 영향을 받게 됩니다. 최신 버전의 Visual Studio는 새 버전의 구성 요소를 배포 하지만 이전 버전의 파일은 장치에 남아 있으므로 최신 버전이 실패 합니다.  이렇게 하면 다음 오류 메시지가 발생 합니다. DEP0100: 대상 장치에서 개발자 모드를 사용 하도록 설정 했는지 확인 합니다. 80004005 오류로 인해에서 개발자 라이선스를 가져올 수 없습니다 \<ip\> .

#### <a name="workaround"></a>해결 방법

팀이 현재 수정 작업을 진행 중입니다. 그 동안에는 다음 단계를 사용 하 여 문제를 해결 하 고 배포 및 디버깅을 차단 해제 하는 데 도움이 될 수 있습니다.  

1. Visual Studio를 엽니다.

1. **File** > **New** > **Project** 를 선택합니다.

1. **Visual c #**  >  **Windows 데스크톱**  >  **콘솔 앱 (.NET Framework)** 을 선택 합니다.

1. 프로젝트에 이름 (예: "HoloLensDeploymentFix")을 지정 하 고 프레임 워크가 .NET Framework 4.5 이상으로 설정 되었는지 확인 한 다음 **확인** 을 선택 합니다.

1. 솔루션 탐색기에서 **참조** 노드를 마우스 오른쪽 단추로 클릭 하 고 다음 참조를 추가 합니다. **찾아보기** 섹션으로 선택 하 고 **찾아보기** 를 선택 합니다.

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0가 설치 되어 있지 않은 경우에는 최신 버전을 사용 합니다.

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고   >  **기존 항목** 추가를 선택 합니다.

1. C:\Program files (x86) \ Windows Kits\10\bin\10.0.18362.0\x86로 이동 하 고 필터를 **모든 파일 ( \* . \* )** 로 변경 합니다.

1. SirepClient.dll와 SshClient.dll를 모두 선택 하 고 **추가** 를 선택 합니다.

1. 솔루션 탐색기 (파일 목록의 맨 아래에 있어야 함)에서 두 파일을 찾아서 선택 하 고 **속성** 창에서 **출력 디렉터리로 복사를** **항상 복사** 로 변경 합니다.

1. 파일의 맨 위에서 기존 문 목록에 다음을 추가 합니다 `using` .

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 내 `static void Main(...)` 에서 다음 코드를 추가 합니다.

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

1. 명령 프롬프트 창을 열고 컴파일된 .exe 파일을 포함 하는 폴더 (예: C:\MyProjects\HoloLensDeploymentFix\bin\Debug)로 cd를 엽니다.

1. 실행 파일을 실행 하 고 장치의 IP 주소를 명령줄 인수로 제공 합니다. (USB를 사용 하 여 연결한 경우 127.0.0.1을 사용할 수 있습니다. 그렇지 않으면 장치의 Wi-Fi IP 주소를 사용 합니다.)  예를 들면 "HoloLensDeploymentFix 127.0.0.1"입니다.

1. 도구가 메시지 없이 종료 된 후 (몇 초 정도 소요 됨) 이제 Visual Studio 2017 이상에서 배포 하 고 디버그할 수 있습니다.  계속 해 서 도구를 사용 해야 하는 것은 아닙니다.

사용할 수 있게 되 면 추가 업데이트를 제공 합니다.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens에서 Microsoft Store 및 앱을 시작 하는 문제

> [!NOTE]
> 마지막 업데이트: 4/2 @ 10 AM-문제가 해결 되었습니다.

HoloLens에서 Microsoft Store 및 앱을 시작 하려고 하면 문제가 발생할 수 있습니다. 백그라운드 앱 업데이트가 특정 시퀀스에서 최신 버전의 프레임 워크 패키지를 배포 하는 동안 해당 종속 앱 중 하나 이상이 실행 중일 때 문제가 발생 함을 확인 했습니다. 이 경우 자동 앱 업데이트는 이전 버전의 프레임 워크를 사용 하는 실행 중인 모든 앱에 대해 올바르게 업데이트 되지 않는 .NET 네이티브 framework (version 10.0.25531 to 10.0.27413)의 새 버전을 제공 했습니다.  프레임 워크 업데이트에 대 한 흐름은 다음과 같습니다.

1. 새 프레임 워크 패키지가 저장소에서 다운로드 되 고 설치 됩니다.

1. 이전 프레임 워크를 사용 하는 모든 앱은 최신 버전을 사용 하도록 ' 업데이트 ' 됩니다.

2 단계가 완료 되기 전에 중단 되 면 최신 프레임 워크가 등록 되지 않은 모든 앱이 시작 메뉴에서 시작 되지 않습니다.  HoloLens의 모든 앱이이 문제의 영향을 받을 수 있다고 생각 합니다.

일부 사용자가 중지 된 앱을 닫고 피드백 허브, 3D 뷰어 또는 사진 같은 기타 앱을 시작 하 여 문제를 해결 하는 것을 보고 했습니다. 그러나이 문제는 100%의 시간 동안 작동 하지 않습니다.

이 문제로 인해 업데이트 자체가 발생 하지 않았지만, .NET 네이티브 framework 업데이트를 잘못 처리 하는 OS의 버그가 발생 하 여 근본 원인이 되었습니다. 수정 사항을 확인 하 고 픽스를 포함 하는 업데이트 (OS 버전 17763.380)를 릴리스 했습니다.  

장치에서 업데이트를 사용할 수 있는지 확인 하려면 다음을 수행 합니다.

1. 설정 앱으로 이동 하 고 **업데이트 & 보안** 을 엽니다.

1. **업데이트 확인을** 선택 합니다.

1. 17763.380에 대 한 업데이트를 사용할 수 있는 경우이 빌드로 업데이트 하 여 앱 중단 버그에 대 한 픽스를 수신 하세요.

1. 이 버전의 OS를 업데이트할 때 앱이 예상 대로 작동 해야 합니다.

또한 모든 HoloLens OS 릴리스와 마찬가지로 [Microsoft 다운로드 센터](https://aka.ms/hololensdownload/10.0.17763.380)에 ffu 이미지를 게시 했습니다.

업데이트를 수행 하지 않으려는 경우 3/29 Microsoft Store UWP 앱의 새 버전을 릴리스 했습니다. 업데이트 된 버전의 스토어를 만든 후에는 다음을 수행 합니다.

1. 저장소를 열고 로드 되는지 확인 합니다.
1. 블 룸 제스처를 사용 하 여 메뉴를 엽니다.
1. 이전에 중단 된 앱을 열려고 시도 합니다.
1. 여전히 시작할 수 없는 경우 손상 된 앱의 아이콘을 탭 하 고 누른 채 제거를 선택 합니다.
1. 스토어에서 이러한 앱을 다시 설치 합니다.

장치에서 여전히 앱을 로드할 수 없는 경우 다음 단계를 수행 하 여 다운로드 센터를 통해 .NET 네이티브 Framework 및 런타임 버전을 테스트용으로 로드 수 있습니다.

1. Microsoft 다운로드 센터에서 [이 zip 파일](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 을 다운로드 하세요. 압축을 푸는 경우 두 개의 파일이 생성 됩니다.  Microsoft.. m a. m. i n t. 1.7.

1. 장치가 dev의 잠금 해제 상태 인지 확인 하세요.  이전에 수행 하지 않은 경우 지침에 [Windows 장치 포털 사용](/windows/mixed-reality/using-the-windows-device-portal) 을 참조 하세요.

1. 그런 다음 Windows 장치 포털로 이동할 수 있습니다. USB를 통해이 작업을 수행 하 고 브라우저에를 입력 하 여이 작업을 수행 하는 것이 좋습니다 http://127.0.0.1:10080 .

1. Windows 장치 포털을 설치한 후 다운로드 한 두 파일을 "로드" 해야 합니다. 이렇게 하려면 **앱** 섹션에 도달할 때까지 왼쪽 막대를 아래로 이동 하 여 **앱** 을 선택 해야 합니다.

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

- 애플리케이션이 사용자 뒤의 [포커스 지점](/windows/mixed-reality/focus-point-in-unity) 또는 camera.forward로 보통을 설정하는 경우 홀로그램은 혼합 현실 캡처 사진이나 비디오에 표시되지 않습니다. Windows 이 버그가 수정될 때까지 애플리케이션에서 [포커스 지점을](/windows/mixed-reality/focus-point-in-unity) 적극적으로 설정하는 경우 평면 보통이 카메라 앞으로 반대 방향으로 설정되었는지 확인해야 합니다(예: normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Xbox 무선 컨트롤러

- Xbox 무선 컨트롤러 S는 HoloLens 함께 사용하려면 먼저 업데이트해야 합니다. 컨트롤러를 HoloLens 페어링하기 전에 [최신](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 상태로 유지합니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens 다시 부팅하면 컨트롤러가 HoloLens 자동으로 다시 연결되지 않습니다. 3분 후에 컨트롤러가 꺼질 때까지 가이드 단추 조명이 느리게 깜박입니다. 컨트롤러를 즉시 다시 연결하려면 조명이 꺼질 때까지 가이드 단추를 누른 채 컨트롤러의 전원을 끕니다. 컨트롤러의 전원을 다시 켜면 HoloLens 다시 연결됩니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens 대기로 들어가면 컨트롤러의 모든 입력이 HoloLens 절전 모드를 깨우게 됩니다. 사용이 완료되면 컨트롤러의 전원을 꺼서 이를 방지할 수 있습니다.

