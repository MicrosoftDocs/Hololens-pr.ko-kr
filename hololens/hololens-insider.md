---
title: Microsoft HoloLens 참가자 미리 보기
description: 참가자 빌드를 시작 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 소중한 피드백을 제공 하는 것은 간단 합니다.
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
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162955"
---
# Microsoft HoloLens 참가자 미리 보기

HoloLens에 대 한 최신 참가자 Preview 빌드에 오신 것을 환영 합니다! 이 작업을 간단 하 게 [시작](hololens-insider.md#start-receiving-insider-builds) 하 고 HoloLens에 대 한 다음 주요 운영 체제 업데이트에 대 한 소중한 의견을 제공 하세요.

## Windows 참가자 릴리스 정보

### 앱 설치 관리자를 통해 HoloLens 2에 앱 설치
Windows 홀로그램, 버전 20H2 업데이트 직후에 앱 설치 관리자 기능을 제공 합니다. HoloLens 2 장치에 **응용 프로그램을 더욱 원활 하 게 설치할 수 있도록 새 접근 권한 (앱 설치 관리자)을 추가** 합니다. **관리 되지 않는 장치에 대 한 기능은 기본적으로 설정**됩니다. 엔터프라이즈에 대 한 혼란을 방지 하기 위해 지금은 **관리 장치에** 앱 설치 관리자를 사용할 수 없게 됩니다.  

다음과 **같은 경우에** 는 장치가 "관리"로 간주 됩니다.
- MDM [등록](hololens-enroll-mdm.md) 됨
- [배포 패키지](hololens-provisioning.md) 를 사용 하 여 구성
- 사용자 [id](hololens-identity.md) 가 AAD입니다.

이제 개발자 모드를 사용 하거나 디바이스 포털을 사용할 필요 없이 앱을 설치할 수 있습니다.  장치에 Appx 번들을 다운로드 하 고 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지가 표시 되도록 합니다.  또는 [웹 페이지에서 설치를 시작](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)합니다.  MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 앱을 배포 하려면 [서명 도구로](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 디지털 서명 하 고 [서명에 사용 되는 인증서](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 를 HoloLens 장치에서 신뢰 해야 합니다.

**응용 프로그램 설치 지침**

1.  장치가 관리 되는 것으로 간주 되지 않는지 확인
1.  HoloLens 2 디바이스의 전원이 켜져 있고 PC에 연결 되어 있는지 확인
1.  HoloLens 2 장치에 로그인 되어 있는지 확인
1.  PC에서 사용자 지정 앱으로 이동 하 고 yourapp를 yourdevicename\Internal Storage\Downloads.에 복사 합니다.   파일 복사가 완료 되 면 장치 연결을 끊을 수 있습니다.
1.  HoloLens 2 장치에서 시작 메뉴를 열고 모든 앱을 선택 하 고 파일 탐색기 앱을 실행 합니다.
1.  다운로드 폴더로 이동 합니다. 앱의 왼쪽 창에서이 장치를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.
1.  Yourapp 파일을 선택 합니다.
1.  앱 설치 관리자가 실행 됩니다. 설치 단추를 선택 하 여 앱을 설치 합니다.
설치가 완료 되 면 설치 된 앱이 자동으로 시작 됩니다.

이 흐름을 테스트 하기 위해 [Windows 유니버설 샘플 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 에 대 한 샘플 앱을 찾을 수 있습니다.

[앱 설치 관리자를 사용 하 여 HoloLens 2에 앱을 설치 하](app-deploy-app-installer.md)는 전체 프로세스에 대해 알아봅니다.  

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

## 참가자 빌드 받기 시작

> [!NOTE]
> 최근에 업데이트 하지 않은 경우 장치를 다시 부팅 하 여 상태를 업데이트 하 고 최신 빌드를 다운로드 하세요.
> - "장치 재부팅" 음성 명령은 제대로 작동 합니다. 
> - 설정/Windows 참가자 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.
>
> 백 엔드에 버그가 있는데,이는 사용자가 직면 했을 때 다시 추적 하 게 됩니다.

HoloLens 2 장치에서 **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동 하 고 **시작**을 선택 합니다. Windows 참가자로 등록 하는 데 사용한 계정을 연결 합니다.

이제 Windows 참가자가 채널로 이동 하 고 있습니다. **빠른** 링이 **개발자 채널이**되 고, **느린** 고리는 **베타 채널이**되며, **릴리스 미리 보기** 링은 **릴리스 미리 보기 채널이**됩니다. 매핑 결과는 다음과 같습니다.

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 를 참조 하세요.

그런 다음 **Windows의 활성 개발**을 선택 하 고 **개발자 채널** 및 **베타 채널** 빌드를 받을지 여부를 선택한 다음 프로그램 약관을 검토 합니다.

**확인 > 지금 다시 시작** 을 선택 하 여 완료 합니다. 장치를 다시 부팅 한 후 **설정 > 업데이트 & 보안** 으로 이동 하 여 최신 빌드를 다운로드 > 업데이트를 확인 합니다.

## FFU 다운로드 및 플래시 방향
비행 서명 된 ffu를 사용 하 여 테스트 하려면 먼저 디바이스의 잠금을 해제 한 후에는 비행 서명 된 ffu가 깜박입니다.
1. PC:

    1. PC에 ffu를 다운로드 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 합니다.
    
    1. Microsoft Store에서 ARC (고급 복구 도우미) 설치: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. HoloLens 비행 잠금 해제: **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 을 열고, 장치를 다시 부팅 합니다.

1. 플래시 FFU-이제 호를 사용 하 여 비행에 서명 된 FFU를 깜박일 수 있습니다.

## 피드백 및 보고 문제 제공

HoloLens에서 [피드백 허브 앱](hololens-feedback.md) 을 사용 하 여 피드백을 제공 하 고 문제를 보고 해 주십시오. 피드백 허브를 사용 하면 엔지니어가 신속 하 게 디버그 하 여 문제를 해결할 수 있도록 필요한 모든 진단 정보가 포함 됩니다.  HoloLens와 중국어 (일본) 버전의 문제는 같은 방식으로 보고 되어야 합니다.

> [!NOTE]
> 문서 폴더에 대 한 피드백 허브가 있는지를 묻는 메시지를 수락 하세요 (메시지가 표시 되 면 **예** 를 선택).

## 개발자를 위한 참고 사항

HoloLens의 참가자 빌드를 사용 하 여 응용 프로그램 개발을 시도 하는 것이 좋습니다.  시작 하려면 [HoloLens 개발자 설명서](https://developer.microsoft.com/windows/mixed-reality/development) 를 참조 하세요. 이 동일한 명령은 HoloLens의 참가자 빌드와 작동 합니다.  HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio의 동일한 빌드를 사용할 수 있습니다.

## 참가자 빌드 수신 중지

Windows 홀로그램의 참가자 빌드를 더 이상 수신 하지 않으려는 경우 HoloLens에서 프로덕션 빌드를 실행 하 고 있는지 확인 하거나 고급 복구 도우미를 사용 하 여 디바이스를 [복구](hololens-recovery.md) 하 여 비 참가자 버전의 Windows 홀로그램에서 장치를 복구할 수 있습니다.

> [!CAUTION]
> 새 preview 빌드를 수동으로 다시 설치한 후에는 참가자 미리 보기 빌드에서 등록을 취소 하는 알려진 문제가 파란색 화면으로 나타날 수 있습니다. 나중에 장치를 수동으로 복구 해야 합니다. 이에 대 한 자세한 내용은이 [알려진 문제](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)를 참조 하세요.

HoloLens가 프로덕션 빌드를 실행 하 고 있는지 확인 하려면 다음을 수행 합니다.

1. **설정 > 시스템 >에 대 한 정보**로 이동 하 여 빌드 번호를 찾습니다.

1. [프로덕션 빌드 번호에 대 한 릴리스 정보를 참조](hololens-release-notes.md)하세요.

참가자 빌드를 옵트아웃 하려면 다음을 수행 합니다.

1. 프로덕션 빌드를 실행 하는 HoloLens에서 > 설정으로 이동 하 **& 보안 > Windows 참가자 프로그램을 업데이트**한 다음 **참가자 빌드 중지**를 선택 합니다.

1. 지침에 따라 장치를 옵트아웃 합니다.
