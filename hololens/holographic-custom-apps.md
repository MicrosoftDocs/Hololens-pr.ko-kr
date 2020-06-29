---
title: HoloLens에 대한 사용자 지정 앱 관리
description: HoloLens에서 사용자 지정 앱을 로드 합니다. 홀로그램 앱 설치 및 제거에 대해 자세히 알아보세요.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens, 테스트용으로 로드, 사이드 부하, 측면 부하, 스토어, uwp, 앱, 설치
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828863"
---
# HoloLens에 대한 사용자 지정 앱 관리

HoloLens는 Microsoft Store에서 제공 하는 다양 한 기존 응용 프로그램과 HoloLens 용으로 고안 된 새 앱을 모두 지원 합니다. 이 문서에서는 사용자 지정 홀로그램 응용 프로그램에 대해 중점적으로 설명 합니다.  

스토어 앱에 대 한 자세한 내용은 [스토어를 사용 하 여 앱 관리](holographic-store-apps.md)를 참조 하세요.

## 사용자 지정 앱 설치

디바이스 포털을 사용 하거나 Visual Studio에서 앱을 배포 하 여 HoloLens에 자신만의 응용 프로그램을 설치할 수 있습니다.

### 장치 포털을 사용 하 여 응용 프로그램 패키지 설치

1. [장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 에서 대상 HoloLens로의 연결을 설정 합니다.
1. 왼쪽 탐색 창에서 **Apps** 페이지로 이동 합니다.
1. **앱 패키지** 에서 응용 프로그램과 연결 된 .appx 파일을 찾습니다.
   > [!IMPORTANT]
   > 연결 된 종속성 및 인증서 파일을 참조 해야 합니다.

1. **이동을**선택 합니다.
   ![Microsoft HoloLens의 Windows Device Portal에서 앱 양식 설치](images/deviceportal-appmanager.jpg)

### Microsoft Visual Studio 2015에서 배포

1. 앱의 Visual Studio 솔루션 (.sln 파일)을 엽니다.
1. 프로젝트의 **속성**을 엽니다.
1. **Master/x86/원격 컴퓨터**빌드 구성을 선택 합니다.
1. **원격 컴퓨터**를 선택 하는 경우:
   - 주소가 HoloLens의 Wi-fi IP 주소를 가리키는지 확인 하세요.
   - 인증을 **유니버설 (암호화 되지 않은 프로토콜)** 로 설정 합니다.
1. 솔루션을 빌드합니다.
1. 개발 PC에서 HoloLens에 앱을 배포 하려면 **원격 컴퓨터**를 선택 합니다. HoloLens에 이미 기존 빌드가 있는 경우 **예** 를 선택 하 여이 최신 버전을 설치 합니다.  

   ![Visual Studio에서 Microsoft HoloLens 용 앱에 대 한 원격 컴퓨터 배포](images/vs2015-remotedeployment.jpg)  
1. 응용 프로그램이 HoloLens에 설치 되 고 자동으로 실행 됩니다.

앱을 설치한 후에는 **모든** 앱 목록 (**Start**  >  **모든 앱**시작)에서 찾을 수 있습니다.
