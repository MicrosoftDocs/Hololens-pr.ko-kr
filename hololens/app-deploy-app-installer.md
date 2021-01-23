---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 테스트용 로드 및 설치하는 방법
description: 앱 설치 관리자를 사용하여 앱을 설치하고 문제를 해결하는 방법을 알아보고 UI를 통해 앱을 테스트용 로드 및 설치합니다.
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: af4e222a4f83ab82466a383099897986ddf6b8c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297293"
---
# 앱 설치 관리자를 통해 HoloLens 2에 앱 설치

> [!NOTE]
> 이 기능은 Windows [Holographic 버전 20H2 – 2020년 12월 업데이트에서 사용할 수 있습니다.](hololens-release-notes.md) 이 기능을 [사용하기 위해](hololens-update-hololens.md) 장치가 업데이트되어 있는지 확인합니다.

**HoloLens** 2 디바이스에 응용 프로그램을 보다 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)이 추가되었습니다. 이 기능은 관리되지 않는 장치에 대해 기본적으로 **설정됩니다.** 엔터프라이즈 중단을 방지하기 위해 현재 관리되는 디바이스에서는 앱 설치 관리자를 사용할 **수** 없습니다.  

다음 중 한 가지가 **** 참이면 디바이스가 "관리"되는 것으로 간주됩니다.

- MDM [등록](hololens-enroll-mdm.md)
- 프로비저닝 [패키지로 구성](hololens-provisioning.md)
- 사용자 [ID가](hololens-identity.md) Azure AD입니다.

이제 개발자 모드를 사용하도록 설정하거나 디바이스 포털을 사용하지 않고도 앱을 설치할 수 있습니다.  USB를 통해 또는 Microsoft Edge를 통해 Appx 번들을 장치에 다운로드하고 파일 탐색기에서 Appx 번들로 이동하여 설치를 시작하라는 메시지가 표시됩니다.  또는 웹 [페이지에서 설치를 시작하십시오.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Microsoft Store에서 설치하거나 MDM의 LOB 앱 배포 기능을 사용하여 사이드로드하는 앱과 마찬가지로 앱은 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 서명 도구를 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 사용하여 디지털 서명해야 합니다. 서명에 사용되는 인증서를 HoloLens 장치에서 신뢰해야 앱을 배포할 수 있습니다.

## 요구 사항

### 디바이스의 경우:

이 기능은 현재 HoloLens 2 디바이스용 Windows Holographic 20H2 빌드에서 사용할 수 있습니다. 이 메서드를 사용하는 모든 장치가 [업데이트되도록 합니다.](hololens-update-hololens.md)

### 앱의 경우:

앱 설치 관리자에서 스토어의 **** 종속성에 따라 앱의 솔루션 구성이 마스터 또는 릴리스가 되어야 합니다. **** 앱 패키지 만들기에 [대한 자세한 정보를 참조하세요.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

이 방법을 통해 설치된 앱은 디지털 서명을 해야 합니다. 인증서를 사용하여 앱에 서명해야 합니다. MS 신뢰할 수 있는 [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)목록에서 인증서를 얻을 수 있습니다. 이 경우 추가 작업을 수행하지 필요가 없습니다. 또는 인증서를 장치에 푸시해야 하는 자체 인증서에 서명할 수 있습니다.

- 서명 도구를 사용하여 [앱에 서명하는 방법](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**인증서 옵션:**

- [MS 신뢰할 수 있는 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**인증서 배포 방법을 선택하십시오.**

- [프로비저닝 패키지는](hololens-provisioning.md) 로컬 장치에 적용할 수 있습니다.
- MDM을 사용하여 장치 구성을 사용하여 [인증서를 적용할 수 있습니다.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- 디바이스 인증서 [관리자를 사용합니다.](certificate-manager.md)

## 설치 방법

1. 디바이스가 관리되는 것으로 간주되지 않는지 확인합니다.
1. HoloLens 2 디바이스가 전원이 설정 및 로그인된지 확인합니다.
1. PC에서 사용자 지정 앱으로 이동하고app.appxbundle을devicename\Internal Storage\Downloads에 복사합니다.
    파일 복사를 마친 후 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.
1. HoloLens 2 장치에서 시작 메뉴를 열고 **모든**앱을 **선택하고** 파일 탐색기 **앱을 실행합니다.**
1. 다운로드 폴더로 이동합니다. 앱의 왼쪽 패널에서 이 디바이스를 **** 먼저 선택한 다음 다운로드로 이동해야 할 수 있습니다.
1. yourapp.appxbundle 파일을 선택합니다.
1. 앱 설치 관리자가 실행됩니다. 설치 **단추를** 선택하여 앱을 설치합니다.

설치가 완료되면 설치된 앱이 자동으로 시작됩니다.

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### 설치 문제 해결

앱을 설치하지 못한 경우 다음을 확인하여 문제를 해결합니다.

- 앱은 마스터 또는 릴리스 빌드입니다.
- 디바이스가 이 기능을 사용할 수 있는 빌드로 업데이트됩니다.
- 인터넷에 [연결되어 있습니다.](hololens-network.md)
- [Microsoft Store의 끝점이](hololens-offline.md) 올바르게 구성되었습니다.  

## 웹 설치 관리자

사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다. 이 흐름은 간편한 다운로드 및 설치 배포 방법과 결합된 앱 설치 관리자를 사용합니다.

### 웹 설치를 설정하는 방법:

1. 앱이 설치되도록 올바르게 구성되어 있는지 확인합니다.
1. 웹 페이지에서 [설치를 사용하도록 설정하려면 다음 단계를 수행합니다.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### 최종 사용자 환경:

1. 사용자가 위에서 선택한 방법을 사용하여 인증서를 받아 장치에 설치합니다.
1. 사용자가 위의 단계에서 만든 URL을 방문합니다.

이제 앱이 장치에 설치됩니다. 앱을 찾으하려면 시작 **** 메뉴를 열고 **** 모든 앱 단추를 선택하여 앱을 찾습니다.

- 앱 설치 관리자 설치 방법 문제 해결에 대한 자세한 도움말은 앱 설치 관리자 [문제 해결을 방문하세요.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> 업데이트 프로세스 중 UI는 지원되지 않습니다. 따라서 이 페이지의 ShowPrompt 옵션 및 관련 옵션은 지원되지 않습니다. [](https://docs.microsoft.com/windows/msix/app-installer/update-settings)

## 샘플 앱

일부 샘플 앱에서 앱 설치 관리자를 시도하려면 사용 가능한 샘플 중 일부를 확인하세요.

- [MRTK 예제 허브](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [표면](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [테스트에 사용할 수 있는 UWP 샘플 앱](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
