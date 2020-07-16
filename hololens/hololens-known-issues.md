---
title: HoloLens에 대해 알려진 문제
description: HoloLens 개발자에 게 영향을 줄 수 있는 알려진 문제의 목록입니다.
keywords: 문제 해결, 알려진 문제, 도움말
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: db95edfbadb271b7fc47cf5798e80d9b2cad3c90
ms.sourcegitcommit: 708da7b390fed1fd3aea1a2b2e50461851052683
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881331"
---
# HoloLens에 대해 알려진 문제

이는 HoloLens 디바이스의 현재 알려진 문제 목록입니다. 이상한 동작이 표시 되는 경우 먼저 다음을 확인 하세요. 이 목록은 새로운 문제가 발견 또는 보고 되거나 향후 HoloLens 소프트웨어 업데이트에서 문제가 해결 됨에 따라 업데이트 됩니다.

>[!NOTE]
> - 차단 하지 않는 문제를 발견 한 경우 [피드백 허브](hololens-feedback.md)를 통해 HoloLens 장치에서 보고 하세요.
> - 직면 하는 문제로 인해 사용자가 차단 하는 경우 피드백을 제공 하는 addtion에서 [지원 요청](https://aka.ms/hlsupport)을 확인 하세요.

- [모든 HoloLens 생성에 대해 알려진 문제](#known-issues-for-all-hololens-generations)
- [HoloLens 2 장치에 대 한 알려진 문제점](#known-issues-for-hololens-2-devices)
- [HoloLens에 대 한 알려진 문제 (첫번째 Gen)](#known-issues-for-hololens-1st-gen)
- [HoloLens 에뮬레이터에 대 한 알려진 문제](#known-issues-for-hololens-emulator)

## 모든 HoloLens 생성에 대해 알려진 문제

### Unity

- HoloLens 개발에 권장 되는 최신 버전의 Unity에 대 한 [도구 설치](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 를 참조 하세요.
- Unity HoloLens 기술 미리 보기의 알려진 문제점은 [HoloLens Unity 포럼](https://forum.unity3d.com/threads/known-issues.394627/)에 설명 되어 있습니다.

### Windows Device Portal

- Mixed Reality 캡처의 실시간 미리 보기 기능에 몇 초의 대기 시간이 발생할 수 있습니다.
- 가상 제스처 섹션 아래의 제스처 및 스크롤 컨트롤이 작동 하지 않습니다. 이 기능을 사용 해도 아무 효과가 없습니다. 같은 페이지의 가상 키보드가 올바르게 작동 합니다.
- 설정에서 개발자 모드를 사용 하도록 설정한 후 디바이스 포털을 켜기 위한 스위치가 활성화 되기까지 몇 초 정도 걸릴 수 있습니다.

### OneDrive 카메라 업로드

HoloLens 용 OneDrive 앱은 회사 또는 학교 계정에 대 한 자동 카메라 업로드를 지원 하지 않습니다.

방법
- 비즈니스에 적합 한 경우 자동 카메라 업로드가 소비자 Microsoft 계정에서 지원 됩니다. 회사 또는 학교 계정 외에 Microsoft 계정에 로그인 할 수 있습니다 (OneDrive 앱이 이중 로그인을 지원 합니다). OneDrive 내 Microsoft 계정 프로필에서 자동, 백그라운드 카메라 앨범 업로드를 사용 하도록 설정할 수 있습니다.
- 자동으로 사진을 업로드 하는 데 소비자 Microsoft 계정을 안전 하 게 사용할 수 없는 경우에는 OneDrive 앱에서 회사 또는 학교 계정에 수동으로 사진을 업로드할 수 있습니다. 이렇게 하려면 OneDrive 앱에서 회사 또는 학교 계정에 로그인 되어 있는지 확인 하세요. 단추를 선택 **+** 하 고 **업로드**를 선택 합니다. **사진 > 카메라 앨범**으로 이동 하 여 업로드 하려는 사진 또는 비디오를 찾습니다. 업로드할 사진이 나 비디오를 선택 하 고 **열기** 단추를 선택 합니다.

## HoloLens 2 장치에 대 한 알려진 문제점

### 참가자 빌드를 사용 하 여 디바이스 reflashed에서 참가자 미리 보기 빌드의 unenrolling 후 파란색 화면이 표시 됨

이 문제는 참가자 미리 보기 빌드에 참여 한 사용자에 게 영향을 미치며, 새 참가자 preview 빌드를 사용 하 여 HoloLens 2를 reflashed, 참가자 프로그램에서 unenrolled 하는 경우 발생 합니다. 

이는 영향을 받지 않습니다.
- Windows 참가자에 등록 되지 않은 사용자 
- 참가자
    - 참가자 빌드가 버전 18362 때문에 디바이스가 등록 된 경우
    - 참가자가 19041를 생성 하 고 참가자 프로그램에 등록 된 상태를 유지 하는 경우 

해결 방법: 
- 문제 방지 
    - 비 참가자 빌드를 깜박입니다. 정기 월간 업데이트 중 하나입니다. 
    - Insider Preview 유지
- 장치 Reflash
    1. 연결 하지 않는 동안 완전히 종료 하 여 [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 를 수동으로 깜박이는 모드로 전환 합니다. 그런 다음 볼륨을 들고 전원 단추를 탭 합니다.
    1. PC에 연결 하 고 고급 복구 도우미를 엽니다. 
    1. HoloLens 2를 기본 빌드로 깜박입니다.   

## HoloLens에 대 한 알려진 문제 (첫번째 Gen)

### Visual Studio를 통해 HoloLens에 연결 하 고 배포할 수 없음

> [!NOTE]
> 마지막 업데이트: 8/8 @ 5:11PM-Visual Studio에서이 문제에 대 한 수정 사항이 포함 된 VS 2019 버전 16.2을 해제 했습니다. 이 오류가 발생 하지 않도록 하려면이 최신 버전으로 업데이트 하는 것이 좋습니다.

Visual Studio에는이 문제에 대 한 수정 사항이 포함 된 VS 2019 버전 16.2이 릴리스 되었습니다. 이 오류가 발생 하지 않도록 하려면이 최신 버전으로 업데이트 하는 것이 좋습니다.

문제 근본 원인: visual studio 2015 또는 초기 릴리스의 Visual Studio 2017를 사용 하 여 HoloLens에 응용 프로그램을 배포 하 고 디버그 한 다음 나중에 동일한 HoloLens로 Visual studio 2017 또는 Visual Studio 2019의 최신 버전을 사용 하는 것이 영향을 받습니다. Visual Studio의 최신 릴리스에서는 새 버전의 구성 요소를 배포 하지만 이전 버전의 파일은 장치에서 남아 있으므로 최신 버전이 작동 하지 않습니다.  이로 인해 DEP0100: 대상 디바이스에서 개발자 모드를 사용 하도록 설정 되어 있는지 확인 하세요. 오류 80004005 때문에 개발자 라이선스를 가져올 수 없습니다 \<ip\> .

#### 해결 방법

현재 팀에서 수정 작업을 진행 하 고 있습니다. 그 동안에는 다음 단계를 사용 하 여 문제를 해결 하 고 배포 및 디버깅을 차단 해제할 수 있습니다.  

1. Visual Studio 열기
1. **파일**  >  **새**  >  **프로젝트**를 선택 합니다.
1. **Visual c #**  >  **Windows 데스크톱**  >  **콘솔 앱 (.net Framework)** 을 선택 합니다.
1. 프로젝트 이름 (예: "HoloLensDeploymentFix")을 지정 하 고 프레임 워크가 최소 .NET Framework 4.5로 설정 되어 있는지 확인 한 다음 **확인**을 선택 합니다.
1. 솔루션 탐색기에서 **참조** 노드를 마우스 오른쪽 단추로 클릭 하 고 다음 참조를 추가 합니다 ( **찾아보기** 섹션을 선택 하 고 **찾아보기**선택).

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0가 설치 되어 있지 않은 경우에는 최신 버전을 사용 합니다. 

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **Add**  >  **기존 항목**추가를 선택 합니다.
1. C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86로 이동 하 여 필터를 **모든 파일 (\ *. \ *)** 로 변경 합니다.
1. SirepClient.dll 및 SshClient.dll을 모두 선택 하 고 **추가**를 선택 합니다.
1. 솔루션 탐색기에서 두 파일을 찾아 선택 하 고 (파일 목록의 맨 아래에 있어야 함) **속성** 창에서 **출력 디렉터리로 복사** 를 **항상 복사**로 변경 합니다.
1. 파일의 맨 위에 있는 기존 문 목록에 다음을 추가 합니다 `using` .

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 내부 `static void Main(...)` 에 다음 코드를 추가 합니다.

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 빌드 **Build**  >  **빌드 솔루션**을 선택 합니다.
1. 명령 프롬프트 창과 cd를 컴파일된 .exe 파일이 포함 된 폴더에 엽니다 (예: C:\MyProjects\HoloLensDeploymentFix\bin\Debug).
1. 실행 파일을 실행 하 고 디바이스의 IP 주소를 명령줄 인수로 제공 합니다. (USB를 사용 하 여 연결 된 경우 127.0.0.1을 사용 하 고, 그렇지 않으면 디바이스의 Wi-fi IP 주소를 사용할 수 있습니다.)  예를 들어 "HoloLensDeploymentFix 127.0.0.1"

1. 메시지 없이 도구를 종료 한 후 (몇 초 정도 소요 되는 경우), 이제 Visual Studio 2017 이상에서 배포 및 디버그할 수 있게 됩니다.  계속 해 서 도구를 사용할 필요는 없습니다.

사용할 수 있게 되 면 추가 업데이트를 제공 합니다.

### HoloLens에서 Microsoft 스토어 및 앱을 시작 하는 문제

> [!NOTE]
> 마지막 업데이트: 4/2 @ 10 AM-문제가 해결 되었습니다. 

HoloLens에서 Microsoft 스토어 및 앱을 시작 하려고 하면 문제가 발생할 수 있습니다. 백그라운드 앱 업데이트가 특정 시퀀스에 최신 버전의 프레임 워크 패키지를 배포 하는 경우 해당 종속 앱이 계속 실행 되 고 있는 경우이 문제가 발생 하는 것으로 확인 되었습니다. 이 경우 자동 앱 업데이트는 이전 버전의 프레임 워크를 사용 하는 실행 중인 모든 앱에 대해 실행 중인 앱이 새 버전의 .NET 네이티브 프레임 워크 (버전 10.0.25531를 10.0.27413)를 올바르게 업데이트 하지 않은 것으로 발생 했습니다.  프레임 워크 업데이트 흐름은 다음과 같습니다. 

1. 새 프레임 워크 패키지가 스토어에서 다운로드 되 고 설치 됨
1. 최신 버전을 사용 하기 위해 이전 프레임 워크를 사용 하는 모든 앱은 ' 업데이트 됨 '입니다.

2 단계가 완료 되기 전에 중단 되 면 최신 프레임 워크가 등록 되지 않은 모든 앱이 시작 메뉴에서 실행 되지 않습니다.  이 문제로 인해 HoloLens의 모든 앱이 영향을 받을 수 있다고 생각 합니다.

일부 사용자가 중단 된 앱을 종료 하 고 피드백 허브, 3D 뷰어 또는 사진 등의 다른 앱을 실행 하 여 문제를 해결 했다고 보고 한 경우 &mdash; ,이는 해당 시간의 100%로 작동 하지 않습니다.

이 문제가 발생 하 여 업데이트 자체는 발생 되지 않았지만 .NET 네이티브 프레임 워크 업데이트를 잘못 처리 하는 OS의 버그로 인해 근본 했습니다. 픽스를 확인 하 고 수정 프로그램을 포함 하는 업데이트 (OS 버전 17763.380)를 릴리스 했습니다.  

장치에서 업데이트를 받을 수 있는지 확인 하려면 다음을 수행 하세요.

1. 설정 앱으로 이동 하 여 **업데이트 & 보안**을 엽니다.
1. **업데이트 확인을**선택 합니다.
1. 17763.380에 대 한 업데이트를 사용할 수 있는 경우이 빌드로 업데이트 하 여 앱 중지 버그 수정을 수신 하세요.
1. 이 버전의 OS를 업데이트 하면 앱이 예상 대로 작동 하 게 됩니다.

또한 모든 HoloLens OS 릴리스부터는 [Microsoft 다운로드 센터](https://aka.ms/hololensdownload/10.0.17763.380)에 ffu 이미지를 게시 했습니다.

업데이트를 수행 하지 않으려면 3/29에서 Microsoft Store UWP 앱의 새 버전을 출시 했습니다. 스토어의 업데이트 된 버전을 설치한 후 다음을 수행 합니다.

1. 스토어를 열고 로드 되는지 확인 합니다.
1. 블 룸 제스처를 사용 하 여 메뉴를 엽니다.
1. 이전에 중단 된 앱을 열어 봅니다.
1. 여전히 실행할 수 없는 경우 손상 된 앱의 아이콘을 길게 탭 하 고 제거를 선택 합니다.
1. 스토어에서 이러한 앱을 설치 합니다.

장치가 여전히 앱을 로드할 수 없는 경우 다음 단계에 따라 다운로드 센터를 통해 .NET 네이티브 프레임 워크 및 런타임 버전을 테스트용으로 로드 수 있습니다.

1. Microsoft 다운로드 센터에서 [이 zip 파일](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 을 다운로드 하세요. 압축을 푸는 경우 두 가지 파일이 생성 됩니다.  Microsoft NET.TCP. e. t e t. e t e. t e t. e 프레임 워크
1. 디바이스의 개발이 해제 되었는지 확인 하세요.  [이 작업](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 수행 하기 위한 지침 이전에 완료 하지 않은 경우
1. 그런 다음 Windows 디바이스 포털에 액세스 합니다. 이는 USB를 통해이 작업을 수행 하 고 브라우저에 입력 하 여 수행 하는 것이 좋습니다 http://127.0.0.1:10080 .
1. Windows Device Portal을 설치한 후에는 다운로드 한 두 개의 파일을 "로드" 하는 것이 필요 합니다. 이를 위해서는 **apps** 섹션으로 이동 하 고 **앱**을 선택할 때까지 왼쪽 막대를 아래로 이동해 야 합니다.
1. 그러면 아래와 비슷한 화면이 표시 됩니다.  **앱 설치** 의 섹션으로 이동 하 여 해당 두 APPX 파일의 압축을 푼 위치를 탐색 합니다. 한 번에 한 번만 수행할 수 있으므로 첫 번째 항목을 선택한 후 배포 섹션에서 "이동"을 클릭 합니다. 그런 다음 두 번째 APPX 파일에 대해이 작업을 수행 합니다.

   ![로드 된 앱을 설치 하는 Windows 디바이스 포털](images/20190322-DevicePortal.png)
1. 이 시점에는 응용 프로그램이 다시 작동 하 고 스토어에도 액세스할 수 있다고 생각 합니다.
1. 일부 경우에는 영향을 받는 앱이 시작 되기 전에 3D 뷰어 앱을 시작 하는 추가 단계를 실행 해야 합니다. 

이 문제를 해결 하기 위해 프로세스를 진행 하는 과정을 완료 한 후에는 저희 커뮤니티를 계속 사용 하 여 성공적으로 혼합 된 현실 환경을 만드는 것으로 감사 합니다.

### 장치 업데이트

- 새 업데이트 후 30 초가 지난 후 셸이 한 번 사라질 수 있습니다. **블 룸** 제스처를 수행 하 여 세션을 다시 시작 하십시오.

### Visual Studio

- HoloLens 개발에 권장 되는 최신 버전의 Visual Studio에 대 한 [도구 설치](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 를 참조 하세요.
- Visual Studio에서 HoloLens에 앱을 배포 하는 경우 오류가 표시 될 수 있습니다. **사용자 매핑 섹션이 열려 있는 파일에서 요청 된 작업을 수행할 수 없습니다. (HRESULT: 0x800704C8의 예외.)** 이 문제가 발생 하면 다시 시도 하 고 배포에는 일반적으로 성공 합니다.

### API

- 응용 프로그램이 [포커스 지점을](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 사용자에 게 설정 하거나 기본으로 카메라로 전환 하는 경우, 홀로그램는 혼합 현실에 사진이 나 비디오를 캡처하는 것으로 표시 되지 않습니다. Windows에서이 버그가 해결 될 때까지 응용 프로그램이 [포커스 지점을](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 능동적으로 설정한 경우 비행기의 수직이 반대 방향 (예: 보통 =-camera)으로 설정 되어 있는지 확인 해야 합니다.

### Xbox 무선 컨트롤러

- Xbox 무선 컨트롤러 S를 HoloLens에 사용 하려면 먼저 업데이트 해야 합니다. 컨트롤러를 HoloLens와 연결 하기 전에 최신 [상태](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 를 유지 하세요.
- Xbox 무선 컨트롤러에 연결 된 상태에서 HoloLens를 재부팅 하면 컨트롤러가 HoloLens에 자동으로 다시 연결 되지 않습니다. 가이드 단추 조명은 3 분 후에도 컨트롤러가 꺼질 때까지 느리게 깜박입니다. 컨트롤러를 즉시 다시 연결 하려면 표시등이 꺼질 때까지 가이드 단추를 눌러 컨트롤러 전원을 끄십시오. 컨트롤러를 다시 켠 후에는 HoloLens에 다시 연결 됩니다.
- Xbox 무선 컨트롤러에 연결 된 상태에서 HoloLens가 대기 모드로 전환 되 면 컨트롤러의 모든 입력에 대 한 HoloLens의 절전 모드가 해제 됩니다. 이 작업을 사용 하는 동안 컨트롤러의 전원을 끄면이 문제가 발생 하지 않도록 할 수 있습니다.

## HoloLens 에뮬레이터에 대 한 알려진 문제

- Microsoft Store의 모든 앱은 에뮬레이터와 호환 되지 않습니다. 예를 들어, 젊은 Conker 및 조각은 에뮬레이터에서 재생할 수 없습니다.
- 에뮬레이터에서 PC 웹캠 사용을 사용할 수 없습니다.
- Windows Device Portal의 실시간 미리 보기 기능은 에뮬레이터에서 작동 하지 않습니다. 혼합 현실 비디오 및 이미지를 계속 캡처할 수 있습니다.
