---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: 참가자 빌드를 시작하고 HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977233"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens에 대한 참가자 미리 보기

HoloLens에 대한 최신 Insider Preview 빌드를 시작합니다. HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 [간단하게 시작하고](hololens-insider.md#start-receiving-insider-builds) 제공할 수 있습니다.

## <a name="windows-insider-release-notes"></a>Windows 참가자 릴리스 정보

새로운 기능을 Windows 참가자로 다시 플라이팅하기 시작하게 되어 기쁘게요. 새 빌드는 최신 업데이트를 위해 개발 및 베타 채널로 플라이팅됩니다. Windows 참가자 빌드에 더 많은 기능과 업데이트를 추가함에 따라 이 페이지를 계속 업데이트할 예정입니다. 이러한 업데이트를 현실에 혼합할 준비가 되어 있습니다.

| 기능                 | Description                | 대상 사용자 | 빌드 소개 |
|-------------------------|----------------------------|--------------|------------------|
| HoloLens의 CSP 변경 내용 | 데이터를 쿼리하는 에 대한 새 CSP | IT 관리자    | 20348.1403                 |

### <a name="csp-changes-on-hololens"></a>HoloLens의 CSP 변경 내용

- Windows 참가자 빌드에 도입된 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP는 이제 HoloLens 디바이스에 사용 중인 스토리지 공간도 보고합니다. 이 값은 설정 앱의 스토리지 페이지에 표시된 값과 거의 일치해야 합니다. 다음은 이 정보를 포함하는 특정 노드입니다.

- ./DevDetail/Ext/Microsoft/FreeStorage(GET 작업만 해당)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP는 이제 HoloLens가 적극적으로 연결된 Wifi 네트워크의 SSID 및 BSSID도 보고합니다. 다음은 이 정보를 포함하는 특정 노드입니다.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

NetworkIdentifiers를 쿼리하는 syncml Blob 예제(MDM 공급업체용)

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>수정 및 개선 사항:

- 잠긴 [파일을 다운로드하라는 프롬프트가 없는 장치 포털 대해 알려진 문제가 해결되었습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 파일 [업로드 및 다운로드 시간 장치 포털 대한 알려진 문제를 해결했습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>참가자 빌드 수신 시작
> [!NOTE]
> 최근에 업데이트하지 않은 경우 디바이스를 다시 부팅하여 상태를 업데이트하고 최신 빌드를 받으세요.
> - "디바이스 다시 부팅" 음성 명령이 제대로 작동합니다. 
> - 설정/Windows 참가자 프로그램 다시 시작 단추를 선택할 수도 있습니다.
>
> 발생한 백 엔드에 버그가 있으므로 다시 추적할 수 있습니다.

HoloLens 2 디바이스에서 설정 업데이트   >  **& 보안** Windows 참가자 프로그램 이동하여  >   **시작을** 선택합니다. Windows 참가자 등록하는 데 사용한 계정을 연결합니다.
이제 Windows 참가자가 채널로 전환됩니다. **빠른** 링이 **개발 채널이** **되고, 느린** 링이 **베타 채널** 되고, 릴리스 **미리 보기** 링이 릴리스 미리 **보기 채널** 이 됩니다. 매핑은 다음과 ![ 같습니다. Windows 참가자 채널 ](images/WindowsInsiderChannels.png) 설명에 대한 자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개를](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 참조하세요.
그런 **다음, Windows의 활성 개발을** **선택하고, 개발 채널** 또는 **베타 채널** 빌드를 받을지 선택하고, 프로그램 용어를 검토합니다.
확인을 > **지금 다시 시작을** 선택하여 완료합니다. 디바이스가 다시 부팅된 후 설정 > 업데이트 & 보안 > 업데이트 확인으로 이동하여 최신 빌드를 **확인합니다.**
### <a name="update-error-0x80070490-work-around"></a>업데이트 오류 0x80070490 해결
Dev 또는 Beta 채널에서 업데이트할 때 업데이트 오류 0x80070490 발생하는 경우 다음과 같은 단기 해결을 시도합니다. 여기에는 참가자 채널을 이동하고, 업데이트를 선택하고, 참가자 채널을 다시 이동하는 작업이 포함됩니다.
#### <a name="stage-one---release-preview"></a>1단계 - 릴리스 미리 보기
1.  설정, & 보안 업데이트 Windows 참가자 프로그램 릴리스 미리 **보기 채널을** 선택합니다.
2.  설정, 업데이트 & 보안, **Windows 업데이트, 업데이트 확인.** 업데이트 후 2단계로 계속 진행합니다.
#### <a name="stage-two---dev-channel"></a>2단계 - 개발 채널
1. 설정, & 보안 업데이트, Windows 참가자 프로그램 개발 **채널을** 선택합니다.
2. 설정, 업데이트 & 보안, **Windows 업데이트, 업데이트 확인.**
## <a name="ffu-download-and-flash-directions"></a>FFU 다운로드 및 플래시 방향
비행 서명 ffu를 사용하여 테스트하려면 먼저 항공편 서명 ffu를 플래시하기 전에 디바이스의 잠금을 해제해야 합니다.
1. On PC:
    1. 에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.
    
    1. Microsoft Store ARC(고급 복구 도우미)를 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 설치합니다.
    
1. HoloLens - 플라이트 잠금 해제: **설정** 업데이트 & 보안 Windows 참가자 프로그램 열고  >    >   등록한 후 디바이스를 다시 부팅합니다.
1. Flash FFU - 이제 ARC를 사용하여 비행 서명된 FFU를 플래시할 수 있습니다.
### <a name="provide-feedback-and-report-issues"></a>피드백 제공 및 문제 보고
HoloLens에서 [피드백 허브 앱을](hololens-feedback.md) 사용하여 피드백을 제공하고 문제를 보고하세요. 피드백 허브 사용하면 엔지니어가 문제를 신속하게 디버그하고 해결할 수 있도록 필요한 진단 정보가 모두 포함됩니다.  중국어 및 일본어 버전의 HoloLens와 관련된 문제는 동일한 방식으로 보고되어야 합니다.
> [!NOTE]
> Documents 폴더에 액세스하도록 피드백 허브 여부를 묻는 프롬프트를 수락해야 합니다(메시지가 표시되면 **예** 선택).
## <a name="note-for-developers"></a>개발자를 위한 참고 사항
HoloLens의 참가자 빌드를 사용하여 애플리케이션을 개발하는 것이 좋습니다.  시작하려면 [HoloLens 개발자 설명서를](https://developer.microsoft.com/windows/mixed-reality/development) 확인하세요. 이러한 동일한 지침은 HoloLens의 참가자 빌드에서 작동합니다.  HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio 동일한 빌드를 사용할 수 있습니다.
## <a name="stop-receiving-insider-builds"></a>참가자 빌드 수신 중지
Windows Holographic의 참가자 빌드를 더 이상 수신하지 않으려는 경우 HoloLens에서 프로덕션 빌드를 실행할 때 옵트아웃하거나 고급 복구 도우미를 사용하여 [디바이스를](hololens-recovery.md) Windows Holographic의 비 참가자 버전으로 복구할 수 있습니다.
> [!CAUTION]
> 새 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 취소하는 사용자에게 파란색 화면이 발생하는 알려진 문제가 있습니다. 그런 다음 디바이스를 수동으로 복구해야 합니다. 영향을 받을지 여부에 대한 자세한 내용은 이 [알려진 문제에](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)대한 자세한 내용을 확인하세요.
HoloLens에서 프로덕션 빌드를 실행하고 있는지 확인하려면 다음을 수행합니다.
1. 설정 **> 시스템 > 정보로** 이동하여 빌드 번호를 찾습니다.
1. [프로덕션 빌드 번호는 릴리스 정보 를 참조하세요.](hololens-release-notes.md)
참가자 빌드를 옵트아웃하려면 다음을 수행합니다.
1. 프로덕션 빌드를 실행하는 HoloLens에서 **설정 > 업데이트 & 보안 > Windows 참가자 프로그램** 로 이동하고 참가자 **빌드 중지를** 선택합니다.
1. 지침에 따라 디바이스를 옵트아웃합니다.
