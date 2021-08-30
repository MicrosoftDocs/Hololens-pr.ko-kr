---
title: HoloLens 2 App Installer를 통해 앱을 로드 하 고 설치 하는 방법
description: 앱 설치 관리자를 사용 하 여 앱을 설치 하 고 문제를 해결 하 고 UI를 통해 앱을 로드 하 고 설치 하는 방법을 알아봅니다
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188919"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>앱 설치 관리자를 통해 HoloLens 2에 앱 설치

> [!NOTE]
> 이 기능은 [Windows Holographic, 버전 20h2 – 12 월 2020 업데이트](hololens-release-notes.md)에서 사용할 수 있었습니다. 이 기능을 사용 하도록 장치가 [업데이트](hololens-update-hololens.md) 되었는지 확인 합니다.

HoloLens 2 장치에 **더욱 원활 하 게 응용 프로그램을 설치할 수 있도록 하는 새로운 기능 (앱 설치 관리자)이 추가** 되었습니다. 이 기능은 **기본적으로 관리 되지 않는 장치에 대해 설정** 됩니다. 엔터프라이즈 중단을 방지 하기 위해 지금은 **관리 되는 장치에 대해** 앱 설치 관리자를 사용할 수 없습니다.  

다음 조건 중 **하나** 에 해당 하는 경우 장치는 "관리" 된 것으로 간주 됩니다.

- MDM [등록](hololens-enroll-mdm.md) 됨
- [프로 비전 패키지](hololens-provisioning.md) 를 사용 하 여 구성
- 사용자 [id](hololens-identity.md) 는 Azure AD입니다.

이제 개발자 모드를 사용 하도록 설정 하거나 장치 포털을 사용 하지 않고도 앱을 설치할 수 있습니다.  장치에 appx 번들을 다운로드 (USB 또는 Microsoft Edge을 통해) 하 고 파일 탐색기에서 appx 번들로 이동 하 여 설치를 시작 하 라는 메시지를 표시 합니다.  또는 [웹 페이지에서 설치를 시작](/windows/msix/app-installer/installing-windows10-apps-web)합니다. MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 서명 [도구](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 를 사용 하 여 앱을 디지털 서명 해야 하며, [서명 하는 데 사용 된 인증서](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 를 HoloLens 장치에서 신뢰할 수 있어야 앱을 배포할 수 있습니다.

## <a name="requirements"></a>요구 사항

### <a name="for-your-devices"></a>장치:

이 기능은 현재 HoloLens 2 장치에 대 한 Windows Holographic 20h2 빌드에서 사용할 수 있습니다. 이 방법을 사용 하는 모든 장치가 [업데이트](hololens-update-hololens.md)되었는지 확인 합니다.

### <a name="for-your-apps"></a>앱의 경우:

앱 설치 관리자는 저장소의 종속성을 사용할 수 있으므로 앱의 솔루션 구성은 **마스터** 또는 **릴리스** 중 하나 여야 합니다. [앱 패키지 만들기](/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 참조 하세요.

이 메서드를 통해 설치 되는 앱은 디지털 서명 되어야 합니다. 인증서를 사용 하 여 앱에 서명 해야 합니다. [MS 신뢰할 수 있는 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)에서 인증서를 가져올 수 있으며,이 경우 추가 작업을 수행할 필요가 없습니다. 또는 자체 인증서를 서명할 수 있지만 인증서를 장치에 푸시 해야 합니다.

- [서명 도구를 사용 하 여](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 앱에 서명 하는 방법입니다.

**인증서 옵션:**

- [MS 신뢰할 수 있는 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**인증서 배포 방법을 선택 합니다.**

- [프로 비전 패키지](hololens-provisioning.md) 를 로컬 장치에 적용할 수 있습니다.
- MDM은 [장치 구성으로 인증서를 적용](/mem/intune/protect/certificates-configure)하는 데 사용할 수 있습니다.
- 장치 [인증서 관리자](certificate-manager.md)에서를 사용 합니다.

## <a name="installation-method"></a>설치 방법

1. 장치가 관리 되는 것으로 간주 되지 않았는지 확인 합니다.
1. HoloLens 2 장치가 켜져 있고 로그인 되어 있는지 확인 합니다.
1. pc에서 사용자 지정 앱으로 이동 하 고 yourapp을 yourdevicename\Internal Storage \downloads.에 복사 합니다.
    파일 복사를 완료 한 후 장치를 분리 하 고 나중에 설치를 완료할 수 있습니다.
1. HoloLens 2 장치에서 **시작 메뉴** 를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 시작 합니다.
1. 다운로드 폴더로 이동 합니다. 앱의 왼쪽 패널에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.
1. Yourapp 파일을 선택 합니다.
1. 앱 설치 관리자가 시작 됩니다. **설치** 단추를 선택 하 여 앱을 설치 합니다.

설치가 완료 되 면 설치 된 앱이 자동으로 시작 됩니다.

![App Installer를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>설치 문제 해결

앱을 설치 하지 못한 경우 다음을 확인 하 여 문제를 해결 합니다.

- 앱은 마스터 또는 릴리스 빌드입니다.
- 장치가이 기능을 사용할 수 있는 빌드로 업데이트 됩니다.
- 사용자가 [인터넷에 연결](hololens-network.md)되어 있습니다.
- [Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.  

## <a name="web-installer"></a>웹 설치 관리자

사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다. 이 흐름은 간편한 다운로드 및 설치 배포 방법과 함께 앱 설치 관리자를 사용 합니다.

### <a name="how-to-set-up-web-install"></a>웹 설치를 설정 하는 방법:

1. 앱이 설치 되도록 올바르게 구성 되어 있는지 확인 합니다.
1. [웹 페이지에서 설치를 사용 하도록 설정 하려면 다음 단계를](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)수행 합니다.

### <a name="end-user-experience"></a>최종 사용자 환경:

1. 사용자가 이전에 선택한 방법을 사용 하 여 장치에 인증서를 받아서 설치 합니다.
1. 사용자가 위 단계에서 만든 URL을 방문 합니다.

이제 앱이 장치에 설치 됩니다. 앱을 찾으려면 **시작 메뉴** 열고 **모든 앱** 단추를 선택 하 여 앱을 찾습니다.

- 앱 설치 관리자 설치 방법 문제를 해결 하는 방법에 대 한 자세한 내용은 [앱 설치 관리자 문제 해결](/windows/msix/app-installer/troubleshoot-appinstaller-issues)을 참조 하세요.

> [!NOTE]
> 업데이트 프로세스 중에 UI가 지원 되지 않습니다. 따라서 [이 페이지](/windows/msix/app-installer/update-settings) 의 showprompt 옵션과 관련 옵션은 지원 되지 않습니다.

## <a name="sample-apps"></a>샘플 앱

사용 가능한 샘플 앱 중 하나를 사용 하 여 앱 설치 관리자를 사용해 보세요. 
> [!div class="nextstepaction"]
> [샘플 앱](/windows/mixed-reality/develop/features-and-samples)
