---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 로드 하 고 설치 하는 방법
description: UI를 통해 앱 로드 및 설치
keywords: 앱 관리, 앱, hololens, 앱 설치 관리자
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027482"
---
# 앱 설치 관리자를 통해 HoloLens 2에 앱 설치

이제 개발자 모드를 사용 하도록 설정 하거나 Device Portal을 사용할 필요 없이 이제 Appx 번들을 통해 앱을 설치할 수 있습니다. 이 환경은 로컬 장치에 앱을 설치 하거나 HoloLens의 다른 앱 설치 방법에 익숙하지 않은 다른 사용자와 앱을 공유 하는 것을 간단 하 게 수행할 수 있습니다. 

> [!IMPORTANT]
> 이 기능은 현재 Windows 참가자 빌드 19041.1377 +에만 avalible 있습니다. [Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).

> [!NOTE]
> 앱 설치 관리자가 스토어의 종속성을 사용 하므로 앱의 솔루션 구성이 **Master** 또는 **Release** 여야 합니다. [앱 패키지 만들기](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 확인 하세요.

1.  HoloLens 2 디바이스의 전원이 켜져 있고 로그인 되어 있는지 확인 합니다.
1.  PC에서 사용자 지정 앱으로 이동 하 고 yourapp를 yourdevicename\Internal Storage\Downloads.에 복사 합니다. 
    파일 복사가 완료 되 면 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.
1.  HoloLens 2 장치에서 **시작 메뉴**를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 실행 합니다.
1.  다운로드 폴더로 이동 합니다. 앱의 왼쪽 창에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.
1.  Yourapp 파일을 선택 합니다. 
1.  앱 설치 관리자가 실행 됩니다. **설치** 단추를 선택 하 여 앱을 설치 합니다. 

설치가 완료 되 면 설치 된 앱이 자동으로 실행 됩니다. 

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

앱을 설치 하지 못한 경우 다음을 확인 합니다.
-   앱이 마스터 또는 릴리스 빌드입니다.
-   [인터넷에 연결](hololens-network.md)되어 있습니다.
-   [Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.  
