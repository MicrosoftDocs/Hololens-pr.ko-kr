---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 로드 하 고 설치 하는 방법
description: UI를 통해 앱 로드 및 설치
keywords: 앱 관리, 앱, hololens, 앱 설치 관리자
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eba1fd00215ef197f9e32949e958bdbded089d6d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162893"
---
# 앱 설치 관리자를 통해 HoloLens 2에 앱 설치


Windows 홀로그램, 버전 20H2 업데이트 직후에 앱 설치 관리자 기능을 제공 합니다. HoloLens 2 장치에 **응용 프로그램을 더욱 원활 하 게 설치할 수 있도록 새 접근 권한 (앱 설치 관리자)을 추가** 합니다. **관리 되지 않는 장치에 대 한 기능은 기본적으로 설정**됩니다. 엔터프라이즈에 대 한 혼란을 방지 하기 위해 지금은 **관리 장치에** 앱 설치 관리자를 사용할 수 없게 됩니다.  

> [!IMPORTANT]
> 이 기능은 현재 Windows 참가자 빌드에서만 사용할 수 있습니다. [Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).

Windows 참가자 릴리스에서 HoloLens 2 장치에 **응용 프로그램을 더욱 원활 하 게 설치할 수 있도록 새 기능 (앱 설치 관리자)을 추가** 합니다. **관리 되지 않는 장치에 대 한 기능은 기본적으로 설정**됩니다. 엔터프라이즈에 대 한 혼란을 방지 하기 위해 지금은 **관리 장치에** 앱 설치 관리자를 사용할 수 없게 됩니다.  

다음과 **같은 경우에** 는 장치가 "관리"로 간주 됩니다.
- MDM [등록](hololens-enroll-mdm.md) 됨
- [배포 패키지](hololens-provisioning.md) 를 사용 하 여 구성
- 사용자 [id](hololens-identity.md) 가 AAD입니다.

이제 개발자 모드를 사용 하거나 디바이스 포털을 사용할 필요 없이 앱을 설치할 수 있습니다.  장치에 Appx 번들을 다운로드 하 고 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지가 표시 되도록 합니다.  또는 [웹 페이지에서 설치를 시작](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)합니다.  MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 앱을 배포 하려면 [서명 도구로](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 디지털 서명 하 고 [서명에 사용 되는 인증서](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 를 HoloLens 장치에서 신뢰 해야 합니다.   

## 요구 사항

### 장치: 
현재이는 HoloLens 2 장치에 대 한 [Windows 참가자 빌드](hololens-insider.md) 에 avalible입니다. 이 방법을 사용 하는 모든 장치가 [업데이트](hololens-update-hololens.md)되었는지 확인 하세요. 

### 앱: 
앱 설치 관리자가 스토어의 종속성을 사용 하므로 앱의 솔루션 구성이 **Master** 또는 **Release** 여야 합니다. [앱 패키지 만들기](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 확인 하세요.

이 방법을 통해 설치 된 앱은 디지털 서명 해야 합니다. 앱에 서명 하는 데 인증서를 사용 해야 합니다. [MS 신뢰 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)에서 인증서를 가져올 수 있으며,이 경우 추가 작업을 수행할 필요가 없습니다. 또는 인증서를 장치에 푸시 해야 하지만 본인의 인증서에 서명할 수도 있습니다. 
- [서명 도구를 사용 하 여](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 앱에 서명 하는 방법

**인증서 옵션:** 
- [MS 신뢰할 수 있는 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**인증서 배포 방법을 선택 합니다.** 
- [배포 패키지](hololens-provisioning.md) 는 로컬 장치에 적용 될 수 있습니다.
- [장치 구성으로 인증서를 적용](https://docs.microsoft.com/mem/intune/protect/certificates-configure)하는 데 MDM을 사용할 수 있습니다.
- 장치 [인증서 관리자](certificate-manager.md)를 사용 합니다. 

## 설치 방법

1.  장치가 관리 되는 것으로 간주 되지 않는지 확인 합니다.
1.  HoloLens 2 디바이스의 전원이 켜져 있고 로그인 되어 있는지 확인 합니다.
1.  PC에서 사용자 지정 앱으로 이동 하 고 yourapp를 yourdevicename\Internal Storage\Downloads.에 복사 합니다. 
    파일 복사가 완료 되 면 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.
1.  HoloLens 2 장치에서 **시작 메뉴**를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 실행 합니다.
1.  다운로드 폴더로 이동 합니다. 앱의 왼쪽 창에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.
1.  Yourapp 파일을 선택 합니다. 
1.  앱 설치 관리자가 실행 됩니다. **설치** 단추를 선택 하 여 앱을 설치 합니다. 

설치가 완료 되 면 설치 된 앱이 자동으로 실행 됩니다. 

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### 설치 문제 해결
앱을 설치 하지 못한 경우 다음을 확인 합니다.
-   앱이 마스터 또는 릴리스 빌드입니다.
- 장치가이 기능을 사용할 수 있는 빌드로 업데이트 됩니다. 
-   [인터넷에 연결](hololens-network.md)되어 있습니다.
-   [Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.  

## 웹 설치 관리자

사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다. 이를 통해 간편 하 게 다운로드 하 고 설치할 수 있는 앱 설치 관리자가 결합 됩니다. 

### 웹 설치를 설정 하는 방법:
1.  앱이 설치 되도록 올바르게 구성 되어 있는지 확인 합니다.
1.  [웹 페이지에서이 기능을 사용 하도록 설정 하려면 다음 단계를](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)따르세요. 

### 최종 사용자 환경:
1. 사용자가 이전에 위에서 선택한 방법을 사용 하 여 디바이스에 인증서를 받아서 설치 합니다. 
1. 사용자가 위의 단계에서 만든 URL을 방문 합니다.

이제 앱이 디바이스에 설치 됩니다. 앱을 찾으려면 **시작 메뉴** 를 열고 **모든 앱** 단추를 선택 하 여 앱을 찾습니다. 

-   이 설치 방법 문제 해결에 대 한 도움말은 [앱 설치 관리자 문제 해결](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)을 참조 하세요. 

> [!NOTE]
> 업데이트 프로세스가 진행 되는 동안 UI가 지원 되지 않습니다. 따라서 [이 페이지](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 및 관련 옵션의 showprompt 옵션은 지원 되지 않습니다.

## 샘플 앱

샘플 앱을 사용 하 여이 작업을 수행해 보려면 사용 가능한 샘플 중 일부를 확인 하세요.
- [MRTK 예제 허브](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [평면](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [테스트에 사용할 수 있는 UWP 샘플 앱](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
