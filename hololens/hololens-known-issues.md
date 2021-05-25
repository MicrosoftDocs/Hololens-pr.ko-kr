---
title: HoloLens의 알려진 문제
description: Unity 및 Windows 장치 포털 사용하여 HoloLens 고객 및 개발자에게 영향을 줄 수 있는 알려진 문제 및 해결 방법 목록을 최신 상태로 유지합니다.
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
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397784"
---
# <a name="known-issues-for-hololens"></a>HoloLens의 알려진 문제

HoloLens 디바이스에 대한 알려진 문제의 현재 목록은 다음과 같습니다. 홀수 동작이 표시되는 경우 먼저 여기를 확인하세요. 이 목록은 새 문제가 검색되거나 보고되거나 향후 HoloLens 소프트웨어 업데이트에서 문제가 해결될 때 업데이트됩니다.

>[!NOTE]
> - 차단되지 않는 문제가 발견되면 [피드백 허브](hololens-feedback.md)통해 HoloLens 디바이스에 보고하세요.
> - 사용자 의견을 제출하는 것 외에도 문제가 차단되는 경우 [지원 요청을 제출하세요.](https://aka.ms/hlsupport)

- [모든 HoloLens 세대에 대한 알려진 문제](#known-issues-for-all-hololens-generations)
- [HoloLens 2 디바이스의 알려진 문제](#known-issues-for-hololens-2-devices)
- [HoloLens(1세대)의 알려진 문제](#known-issues-for-hololens-1st-gen)
- [HoloLens 에뮬레이터의 알려진 문제](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>모든 HoloLens 세대에 대한 알려진 문제

### <a name="unity"></a>Unity

- HoloLens 개발에 권장되는 최신 버전의 Unity용 [도구 설치를](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 참조하세요.
- Unity HoloLens Technical Preview의 알려진 문제는 [HoloLens Unity 포럼 에 설명되어 있습니다.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Device Portal

- Mixed Reality 캡처의 라이브 미리 보기 기능은 몇 초의 대기 시간을 나타낼 수 있습니다.

- 가상 입력 페이지의 가상 제스처 섹션 아래에 있는 제스처 및 스크롤 컨트롤이 작동하지 않습니다. 이를 사용하면 아무런 영향을 미치지 않습니다. 가상 입력 페이지의 가상 키보드가 제대로 작동합니다.

- 설정에서 개발자 모드를 사용 하도록 설정한 후 장치 포털을 켜는 스위치를 사용 하도록 설정 하는 데 몇 초 정도 걸릴 수 있습니다.

### <a name="onedrive-camera-upload"></a>OneDrive 카메라 업로드

HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다.

해결 방법:

- 비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다. 회사 또는 학교 계정 외에도 Microsoft 계정에 로그인 할 수 있습니다. OneDrive 앱은 이중 로그인을 지원 합니다. OneDrive 내의 Microsoft 계정 프로필에서 자동, 배경 카메라 롤 업로드를 사용 하도록 설정할 수 있습니다.

- 회사를 자동으로 업로드 하는 데 소비자 Microsoft 계정를 안전 하 게 사용할 수 없는 경우 OneDrive 앱에서 회사 또는 학교 계정에 사진을 수동으로 업로드할 수 있습니다. 이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 했는지 확인 합니다. 단추를 선택 **+** 하 고 **업로드** 를 선택 합니다. **사진 > 카메라 롤** 로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다. 업로드 하려는 사진 또는 비디오를 선택 하 고 **열기** 단추를 선택 합니다.

## <a name="known-issues-for-hololens-2-devices"></a>HoloLens 2 장치에 대 한 알려진 문제

### <a name="device-using-auto-login-asks-for-log-in"></a>자동 로그인을 사용 하는 장치에서 로그인을 요청 합니다.

HoloLens 2 장치는 **설정** 계정 로그인 옵션을 통해 자동 로그인 하도록 구성할 수 있습니다  ->    ->   . > 하 고 **필요한** 경우 값을 **없음** 으로 설정 합니다. 기능 업데이트와 같이 상당히 큰 업데이트를 사용 하 여 장치를 업데이트할 때 일부 사용자가 장치에 다시 로그인 해야 할 수 있습니다.

이 문제가 발생할 수 있는 경우의 예는 다음과 같습니다.

- Windows Holographic 버전 2004 (Build 19041)에서 Windows Holographic, 버전 21H1 (Build 20346)로 장치 업데이트
- 동일한 주요 빌드에 대 한 큰 업데이트를 수행 하도록 장치 업데이트 (예: Windows Holographic, 버전 2004-Windows Holographic, 버전 20H2)
- 공장 이미지에서 최신 이미지로 장치 업데이트

다음 작업 중에는 발생 하지 않아야 합니다.

- 월간 서비스 업데이트를 받는 디바이스

메서드 해결:

- PIN, 암호, 아이리스, 웹 인증 또는 FIDO2 키와 같은 로그인 방법입니다.
- 디바이스 PIN을 기억할 수 없고 다른 인증 방법을 사용할 수 없는 경우 사용자는 [수동 리플래시 모드 를](hololens-recovery.md#manual-procedure)사용할 수 있습니다.

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge 시작하지 못함

> [!NOTE]
> 이 문제는 원래 Microsoft Edge 배송 버전을 염두에 두고 만들어졌습니다. 이 문제는 [새 Microsoft Edge](hololens-new-edge.md)해결될 수 있습니다. 그렇지 않은 경우 피드백을 제출하세요.

일부 고객은 Microsoft Edge 시작에 실패하는 문제를 보고했습니다. 이러한 고객의 경우 문제는 다시 부팅을 통해 지속되며 Windows 또는 애플리케이션 업데이트로 해결되지 않습니다. 이 문제가 발생하고 [Windows가 최신인지](hololens-updates.md#manually-check-for-updates)확인한 경우 [피드백 허브 앱에서](hololens-feedback.md) 다음 범주 및 하위 범주인 설치 및 업데이트 > Windows 업데이트 다운로드, 설치 및 구성으로 버그를 제출하세요.

지금까지 문제의 근본 원인을 알 수 없으므로 알려진 해결 방법이 없습니다. 피드백 허브 통해 버그를 신고하면 조사에 도움이 됩니다.

### <a name="keyboard-does-not-switch-to-special-characters"></a>키보드가 특수 문자로 전환되지 않음

OOBE 중에는 사용자가 직장 또는 학교 계정을 선택하고 암호를 입력한 후 &123 단추를 탭하여 키보드의 특수 문자로 전환하려고 하면 특수 문자로 변경되지 않는 문제가 있습니다.

해결 작업:
-   키보드를 닫고 텍스트 필드를 탭하여 다시 엽니다.
-   암호를 잘못 입력합니다. 다음에 키보드를 다시 시작하면 예상대로 작동합니다.
- 웹 인증에서 키보드를 닫고 **다른 디바이스에서 로그인을** 선택합니다.
-   숫자만 입력 하는 경우 사용자는 특정 키를 길게 눌러 확장 된 메뉴를 열 수 있습니다.
-   USB 키보드 사용.

이는 다음에 영향을 주지 않습니다.
- 개인 계정을 사용 하도록 선택 하는 사용자입니다.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>참가자 빌드를 사용 하 여 장치 reflashed에서 Insider preview 빌드를 등록 취소 후 파란색 화면이 표시 됨

이 문제는 Insider preview 빌드에 있었던 사용자에 게 영향을 주는 문제 이며, HoloLens 2를 새 insider preview 빌드로 reflashed 다음, 참가자 프로그램에서 등록 취소 합니다.

이는 다음에 영향을 주지 않습니다.
- Windows 참가자에 등록 되지 않은 사용자 
- 참가자
    - Insider 빌드된 버전이 18362 이므로 장치가 등록 된 경우
    - Insider 19041 빌드 되었으며 Insider program에 등록 된 상태를 유지 하는 경우

해결 방법: 
- 문제 방지 
    - 비-insider build를 플래시 합니다. 정기 매월 업데이트 중 하나입니다.
    - Insider Preview 유지
- 장치 경감 하기 위해

    1. 연결 되지 않은 상태에서 전원을 끄고, [HoloLens 2를 수동으로 플래시 모드로](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 전환 합니다. 그런 다음 볼륨을 유지 하는 동안 전원 단추를 누릅니다.
    
    1. PC에 연결 하 고 고급 복구 도우미를 엽니다.
    
    1. HoloLens 2 기본 빌드로 플래시합니다.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens(1세대)의 알려진 문제

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Visual Studio 통해 HoloLens에 연결하고 배포할 수 없음

> [!NOTE]
> 마지막 업데이트: 오후 8시 8분 @ 5:11 - Visual Studio 이 문제에 대한 수정이 포함된 VS 2019 버전 16.2를 릴리스했습니다. 이 오류가 발생하지 않도록 이 최신 버전으로 업데이트하는 것이 좋습니다.

Visual Studio VS 2019 버전 16.2를 릴리스했습니다. 여기에는 이 문제에 대한 수정이 포함됩니다. 이 오류가 발생하지 않도록 이 최신 버전으로 업데이트하는 것이 좋습니다.

근본 원인 문제: Visual Studio 2017의 Visual Studio 2015 또는 초기 릴리스를 사용하여 HoloLens에 애플리케이션을 배포하고 디버그한 다음, 이후 동일한 HoloLens로 최신 버전의 Visual Studio 2017 또는 Visual Studio 2019를 사용한 사용자는 영향을 받습니다. 최신 버전의 Visual Studio 새 버전의 구성 요소를 배포하지만 이전 버전의 파일이 디바이스에 남아 있어 최신 버전이 실패합니다.  그러면 다음 오류 메시지가 발생합니다. DEP0100: 대상 디바이스에 개발자 모드가 사용하도록 설정되어 있는지 확인합니다. \<ip\>오류 80004005로 인해 에서 개발자 라이선스를 가져올 수 없습니다.

#### <a name="workaround"></a>해결 방법

우리 팀은 현재 수정 작업을 진행 중입니다. 그 동안 다음 단계를 사용하여 문제를 해결할 수 있으며 배포 및 디버깅을 차단 해제할 수 있습니다.  

1. Visual Studio를 엽니다.

1. **File** > **New** > **Project** 를 선택합니다.

1. **Visual C#**  >  **Windows 데스크톱** 콘솔  >  **앱(.NET Framework)** 을 선택합니다.

1. 프로젝트에 이름(예: "HoloLensDeploymentFix")을 지정하고 프레임워크가 .NET Framework 4.5 이상으로 설정되어 있는지 확인한 다음 확인을 **선택합니다.**

1. 솔루션 탐색기 참조 **노드를** 마우스 오른쪽 단추로 클릭하고 다음 참조를 추가합니다(찾아보기 섹션에 선택하고 **찾아보기** 선택). 

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0이 설치되어 있지 않은 경우 최신 버전을 사용합니다. 

1. 솔루션 탐색기 프로젝트를 마우스 오른쪽 단추로 클릭하고   >  **기존 항목 추가를** 선택합니다.

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86으로 이동한 후 필터를 **모든 파일( . \* \* )** 로 변경합니다.

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

1. 명령 프롬프트 창을 열고 컴파일된 .exe 파일 (예: C:\MyProjects\HoloLensDeploymentFix\bin\Debug)을 포함 하는 폴더로 cd를 이동 합니다.

1. 실행 파일을 실행 하 고 장치의 IP 주소를 명령줄 인수로 제공 합니다. (USB를 사용 하 여 연결한 경우 127.0.0.1을 사용할 수 있습니다. 그렇지 않으면 장치의 Wi-Fi IP 주소를 사용 합니다.)  예를 들면 "HoloLensDeploymentFix 127.0.0.1"입니다.

1. 도구가 메시지 없이 종료 된 후 (몇 초만 소요 됨) 이제 Visual Studio 2017 이상에서 배포 하 고 디버그할 수 있습니다.  계속 해 서 도구를 사용 해야 하는 것은 아닙니다.

사용할 수 있게 되 면 추가 업데이트를 제공 합니다.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens에서 Microsoft Store 및 앱을 시작 하는 문제

> [!NOTE]
> 마지막 업데이트: 4/2 @ 10 AM-문제가 해결 되었습니다.

HoloLens에서 Microsoft Store 및 앱을 시작 하려고 하면 문제가 발생할 수 있습니다. 백그라운드 앱 업데이트가 특정 시퀀스에서 최신 버전의 프레임 워크 패키지를 배포 하는 동안 해당 종속 앱 중 하나 이상이 실행 중일 때 문제가 발생 함을 확인 했습니다. 이 경우 자동 앱 업데이트는 이전 버전의 프레임 워크를 사용 하는 실행 중인 모든 앱에 대해 올바르게 업데이트 되지 않는 .NET 네이티브 Framework (version 10.0.25531 to 10.0.27413)의 새 버전을 제공 했습니다.  프레임 워크 업데이트에 대 한 흐름은 다음과 같습니다.

1. 새 프레임 워크 패키지가 저장소에서 다운로드 되 고 설치 됩니다.

1. 이전 프레임 워크를 사용 하는 모든 앱은 최신 버전을 사용 하도록 ' 업데이트 ' 됩니다.

2 단계가 완료 되기 전에 중단 되 면 최신 프레임 워크가 등록 되지 않은 모든 앱이 시작 메뉴에서 시작 되지 않습니다.  HoloLens의 모든 앱이 이 문제의 영향을 받을 수 있다고 생각합니다.

일부 사용자는 중단된 앱을 닫고 피드백 허브, 3D 뷰어 또는 사진과 같은 다른 앱을 시작하면 문제가 해결되었다고 보고했습니다. 그러나 이 문제는 100% 작동하지 않습니다.

근본 원인으로 인해 이 문제가 업데이트 자체의 원인이 아니라 OS에서 버그가 발생하여 .NET 네이티브 프레임워크 업데이트가 잘못 처리되었습니다. 수정 사항을 확인하고 수정이 포함된 업데이트(OS 버전 17763.380)를 릴리스했다는 것을 알려드리게 되어 기쁘게 생각합니다.  

디바이스가 업데이트를 수행할 수 있는지 확인하려면 다음을 수행합니다.

1. 설정 앱으로 이동하여 **업데이트 & 보안을** 엽니다.

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

1. Microsoft 다운로드 센터에서 [이 zip 파일을](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 다운로드하세요. 압축을 풀면 두 개의 파일이 생성됩니다.  Microsoft.. m a. m. i n t. 1.7.

1. 장치가 dev의 잠금 해제 상태 인지 확인 하세요.  이전에 수행 하지 않은 경우 지침에 대 한 자세한 내용은 [Windows 장치 포털 사용](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 을 참조 하세요.

1. 그런 다음 Windows 장치 포털로 이동 하려고 합니다. USB를 통해이 작업을 수행 하 고 브라우저에를 입력 하 여이 작업을 수행 하는 것이 좋습니다 http://127.0.0.1:10080 .

1. Windows 장치 포털을 설치한 후 다운로드 한 두 파일을 "로드" 해야 합니다. 이렇게 하려면 **앱** 섹션에 도달할 때까지 왼쪽 막대를 아래로 이동 하 여 **앱** 을 선택 해야 합니다.

1. 그러면 아래와 비슷한 화면이 표시 됩니다.  **앱 설치** 섹션으로 이동 하 여 해당 두 APPX 파일의 압축을 푼 위치를 찾습니다. 한 번에 하나씩만 수행할 수 있으므로 첫 번째 항목을 선택한 후 배포 섹션에서 "이동"을 클릭 합니다. 그런 다음 두 번째 APPX 파일에 대해이 작업을 수행 합니다.

   ![Side-Loaded 앱을 설치 하는 Windows 장치 포털](images/20190322-DevicePortal.png)
   
1. 이 시점에서 응용 프로그램이 다시 작업을 시작 하 고 스토어에도 액세스할 수 있다고 생각 합니다.

1. 일부 경우에는 영향을 받는 앱이 시작 되기 전에 3D 뷰어 앱을 시작 하는 추가 단계를 실행 해야 합니다. 

이 문제를 해결 하기 위해 프로세스를 완료 한 후에 감사 드립니다. 그러면 커뮤니티와 함께 계속 작업 하 여 성공적인 혼합 현실 환경을 만들 수 있습니다.

### <a name="device-update"></a>디바이스 업데이트

- 새 업데이트 후 30 초 후 셸이 한 번 사라질 수 있습니다. **블 룸** 제스처를 수행 하 여 세션을 다시 시작 하세요.

### <a name="visual-studio"></a>Visual Studio

- HoloLens 개발에 권장 되는 최신 버전의 Visual Studio 용 [도구 설치](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 를 참조 하세요.

- Visual Studio에서 HoloLens에 앱을 배포할 때 다음 오류가 표시 될 수 있습니다. **사용자 매핑 섹션이 열려 있는 파일에 대해 요청 된 작업을 수행할 수 없습니다. (HRESULT의 예외: 0x800704C8)**. 이 문제가 발생 하는 경우 다시 시도 하면 배포가 일반적으로 성공 합니다.

### <a name="api"></a>API

- 애플리케이션이 사용자 뒤의 포커스 지점 또는 camera.forward로 [보통을](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 설정하는 경우 홀로그램은 혼합 현실 캡처 사진이나 비디오에 표시되지 않습니다. Windows에서 이 버그가 수정될 때까지 애플리케이션에서 [포커스 지점을](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 적극적으로 설정하는 경우 평면 보통이 카메라 앞으로 반대 방향으로 설정되도록 해야 합니다(예: normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Xbox 무선 컨트롤러

- Xbox 무선 컨트롤러 S는 HoloLens와 함께 사용하려면 먼저 업데이트해야 합니다. 컨트롤러를 HoloLens와 페어링하기 전에 [최신](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 상태로 유지합니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens를 다시 부팅하면 컨트롤러가 HoloLens에 자동으로 다시 연결되지 않습니다. 3분 후에 컨트롤러가 꺼질 때까지 가이드 단추 조명이 느리게 깜박입니다. 컨트롤러를 즉시 다시 연결하려면 조명이 꺼질 때까지 가이드 단추를 누른 채 컨트롤러의 전원을 끕니다. 컨트롤러의 전원을 다시 켜면 HoloLens에 다시 연결됩니다.

- Xbox 무선 컨트롤러가 연결된 동안 HoloLens가 대기로 들어가면 컨트롤러의 모든 입력이 HoloLens의 절전 모드를 깨우게 됩니다. 사용이 완료되면 컨트롤러의 전원을 꺼서 이를 방지할 수 있습니다.

## <a name="known-issues-for-hololens-emulator"></a>HoloLens 에뮬레이터의 알려진 문제

- Microsoft Store 있는 모든 앱이 에뮬레이터와 호환되는 것은 아닙니다. 예를 들어 Young Conker 및 Fragments는 에뮬레이터에서 재생할 수 없습니다.
- 에뮬레이터에서는 PC 웹캠을 사용할 수 없습니다.
- Windows 장치 포털 라이브 미리 보기 기능은 에뮬레이터에서 작동하지 않습니다. Mixed Reality 비디오 및 이미지를 캡처할 수 있습니다.
