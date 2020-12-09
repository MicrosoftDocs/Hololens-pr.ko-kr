---
title: Microsoft HoloLens 참가자 미리 보기
description: 간단하게 Insider 빌드를 시작하고 HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공할 수 있습니다.
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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 260b195a18ecb7fe05d819fcd3e86d56fc2022bf
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201342"
---
# Microsoft HoloLens 참가자 미리 보기

HoloLens용 최신 Insider Preview 빌드를 시작하세요! HoloLens의 [get started](hololens-insider.md#start-receiving-insider-builds) 다음 주요 운영 체제 업데이트에 대해 간단하게 시작하고 중요한 피드백을 제공할 수 있습니다.

## Windows Insider Release Notes

최근에 모든 Windows Insider 기능을 출시했습니다. 이러한 모든 기능이 이제 일반적으로 사용 가능해지기 때문에 모든 최신 기능을 볼 수 있도록 릴리스 정보를 읽어 보시고자 합니다. [release notes](hololens-release-notes.md) 새로운 흥미로운 기능의 플라이트를 시작하여 사용해 볼 수 있는 곳을 계속 확인하세요!

## Insider 빌드 수신 시작

> [!NOTE]
> If you haven't updated recently, please reboot your device to update state and get the latest build.
> - "다시부팅 장치" 음성 명령이 잘 작동합니다. 
> - 설정/Windows Insider 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 백 엔드에서 발생할 수 있는 버그가 발생하여 다시 추적할 수 있습니다.

HoloLens 2 장치에서 보안 **Settings**Windows & 업데이트로 이동하고  >  **Update & Security**  >  **Windows Insider Program** **시작을 선택합니다.** Windows Insider로 등록하는 데 사용한 계정을 연결합니다.

Windows 내부자는 이제 채널로 이동하고 있습니다. 빠른 **링은** 개발자 채널이 **되고,** **슬로우** 링은 베타 채널이 **되고,** **릴리스** 미리 보기 링은 릴리스 미리 보기 **채널이 됩니다.** 매핑의 모양은 다음과 같습니다.

![Windows Insider Channels 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에 [Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 소개를 참조하세요.

그런 다음 **Windows의 활성**개발을 선택하고 개발자 **Dev Channel** 채널 또는 **Beta Channel** 베타 채널 빌드를 받을지 여부를 선택하고 프로그램 용어를 검토합니다.

지금 **다시 > 확인을** 선택하여 완료합니다. 장치를 다시 시작한 후 설정 > 업데이트 & **보안** > 최신 빌드를 다운로드하는 업데이트를 확인합니다.

## FFU 다운로드 및 플래시 길
플라이트 서명된 ffu로 테스트하려면 플라이트 서명된 ffu를 깜박이기 전에 먼저 디바이스 잠금 해제를 플라이트해야 합니다.
1. PC에서:

    1. .에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.
    
    1. Microsoft Store에서 ARC(고급 복구 도우미)를 설치합니다. [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. HoloLens - 플라이트 **Settings**잠금 해제: 보안 Windows & 프로그램으로 설정 열기 업데이트 후 등록하고 장치를 다시  >  **Update & Security**  >  **Windows Insider Program** 시작하십시오.

1. 플래시 FFU - 이제 ARC를 사용하여 플라이트 서명된 FFU를 플래시할 수 있습니다.

## 피드백 제공 및 문제 보고

HoloLens에서 피드백 허브 앱을 사용하여 피드백을 제공하고 문제를 보고하세요. [the Feedback Hub app](hololens-feedback.md) 피드백 허브를 사용하면 엔지니어가 문제를 빠르게 디버그하고 해결하는 데 도움이 되는 필요한 모든 진단 정보가 포함됩니다.  중국어 및 일본어 버전의 HoloLens 관련 문제는 동일한 방식으로 보고해야 합니다.

> [!NOTE]
> 피드백 허브가 문서 폴더에 액세스할지 묻는 메시지를 수락해야 합니다(메시지가 표시될 때 예 선택). **Yes**

## 개발자 참고 사항

환영합니다. HoloLens의 Insider 빌드를 사용하여 응용 프로그램을 개발해 보시고 권장됩니다.  [HoloLens 개발자](https://developer.microsoft.com/windows/mixed-reality/development) 설명서를 확인하여 시작하세요. 이러한 지침은 HoloLens의 Insider 빌드에서 작동됩니다.  HoloLens 개발에 이미 사용 중이 Visual Studio Unity와 동일한 빌드를 사용할 수 있습니다.

## Insider 빌드 수신 중지

Windows Holographic의 Insider 빌드를 더 이상 받지 못하게 하려는 경우 HoloLens가 프로덕션 빌드를 [recover your device](hololens-recovery.md) 실행 중일 때 옵트아웃하거나 고급 복구 도우미를 사용하여 장치를 비 Insider 버전의 Windows Holographic으로 복구할 수 있습니다.

> [!CAUTION]
> Insider Preview 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 등록하지 않은 사용자가 파란색 화면을 경험하는 알려진 문제가 있습니다. 그런 다음 장치를 수동으로 복구해야 합니다. 영향이 있을지 아니면 그렇지 않을지에 대한 자세한 내용은 이 알려진 문제에서 자세히 [확인하시기 바랍니다.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

HoloLens에서 프로덕션 빌드를 실행 중인지 확인:

1. Settings > **System > About로**이동하고 빌드 번호를 확인합니다.

1. [프로덕션 빌드 번호에 대한 릴리스 참고를 참조합니다.](hololens-release-notes.md)

Insider 빌드를 옵트아웃(opt out)하는 경우:

1. 프로덕션 빌드를 실행하는 HoloLens에서 **설정**> 업데이트 & Windows & 프로그램으로 이동한 다음 > 빌드 중지를 **선택합니다.**

1. 지침에 따라 디바이스를 옵트아웃합니다.
