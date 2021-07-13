---
title: HoloLens 2 앱 설치 관리자 통해 앱을 사이드로드하고 설치하는 방법
description: 앱 설치 관리자를 사용하여 앱을 설치하고 문제를 해결하는 방법과 UI를 통해 앱을 테스트용으로 로드 및 설치하는 방법을 알아봅니다.
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635588"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>앱 설치 관리자 통해 HoloLens 2 앱 설치

> [!NOTE]
> 이 기능은 Windows [Holographic 버전 20H2 – 2020년 12월 업데이트에서](hololens-release-notes.md)사용할 수 있습니다. 이 기능을 사용하도록 디바이스가 [업데이트되었는지](hololens-update-hololens.md) 확인합니다.

HoloLens 2 디바이스에서 **애플리케이션을 더 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)을 추가했습니다.** 이 기능은 **관리되지 않는 디바이스 에 대해 기본적으로 설정됩니다.** 엔터프라이즈의 중단을 방지하기 위해 현재 관리 디바이스에 앱 설치 **관리자를 사용할 수 없습니다.**  

다음 **중** 한 가지가 true인 경우 디바이스는 "관리"로 간주됩니다.

- MDM [등록](hololens-enroll-mdm.md)
- [프로비전 패키지로](hololens-provisioning.md) 구성됨
- 사용자 [ID는](hololens-identity.md) Azure AD입니다.

이제 개발자 모드를 사용하도록 설정하거나 장치 포털 사용하지 않고도 앱을 설치할 수 있습니다.  USB를 통해 또는 Microsoft Edge 통해 Appx 번들을 디바이스에 다운로드하고 파일 탐색기 Appx 번들로 이동하여 설치를 시작하라는 메시지를 표시합니다.  또는 [웹 페이지 에서 설치를 시작합니다.](/windows/msix/app-installer/installing-windows10-apps-web) MDM의 LOB 앱 배포 기능을 사용하여 Microsoft Store 또는 사이드로드에서 설치하는 앱과 마찬가지로, 앱은 [서명 도구로](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 디지털 서명되어야 [하며, 서명하는 데 사용되는 인증서를](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 디바이스에서 신뢰해야만 앱을 배포할 수 있습니다.

## <a name="requirements"></a>요구 사항

### <a name="for-your-devices"></a>디바이스의 경우:

이 기능은 현재 HoloLens 2 디바이스용 Windows Holographic 20H2 빌드에서 사용할 수 있습니다. 이 방법을 사용하는 모든 디바이스가 [업데이트되었는지](hololens-update-hololens.md)확인합니다.

### <a name="for-your-apps"></a>앱의 경우:

앱의 솔루션 구성은 **마스터** 또는 **릴리스여야** 합니다. 앱 설치 관리자 저장소의 dependencies를 사용하게 됩니다. 앱 패키지 만들기에 대해 자세히 [참조하세요.](/windows/msix/app-installer/create-appinstallerfile-vs)

이 방법을 통해 설치된 앱은 디지털 서명되어야 합니다. 인증서를 사용하여 앱에 서명해야 합니다. MS 신뢰할 수 있는 [CA 목록에서](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)인증서를 얻을 수 있습니다. 이 경우 추가 작업을 수행하지 않아도 됩니다. 또는 사용자 고유의 인증서에 서명할 수 있습니다. 그러나 해당 인증서를 디바이스에 푸시해야 합니다.

- 서명 도구를 [사용하여 앱에 서명하는](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 방법

**인증서 옵션:**

- [MS 신뢰할 수 있는 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**인증서 배포 방법을 선택합니다.**

- [프로비전 패키지는](hololens-provisioning.md) 로컬 디바이스에 적용할 수 있습니다.
- MDM을 사용하여 [디바이스 구성으로 인증서를 적용할](/mem/intune/protect/certificates-configure)수 있습니다.
- 디바이스 인증서 [관리자](certificate-manager.md)에서 를 사용합니다.

## <a name="installation-method"></a>설치 방법

1. 디바이스가 관리되는 것으로 간주되지 않는지 확인합니다.
1. HoloLens 2 디바이스의 전원이 켜지고 로그인했는지 확인합니다.
1. PC에서 사용자 지정 앱으로 이동하고 yourapp.appxbundle을 yourdevicename\Internal Storage\Downloads에 복사합니다.
    파일 복사를 완료한 후 디바이스의 연결을 끊고 나중에 설치를 완료할 수 있습니다.
1. HoloLens 2 디바이스에서 **시작 메뉴를** 열고 **모든 앱** 선택하고 **파일 탐색기** 앱을 시작합니다.
1. 다운로드 폴더로 이동합니다. 앱의 왼쪽 패널에서 **이 디바이스를** 먼저 선택한 다음, 다운로드로 이동해야 할 수 있습니다.
1. yourapp.appxbundle 파일을 선택합니다.
1. 앱 설치 관리자 시작됩니다. **설치** 단추를 선택하여 앱을 설치합니다.

설치된 앱은 설치가 완료되면 자동으로 시작됩니다.

![앱 설치 관리자 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>설치 문제 해결

앱을 설치하지 못한 경우 다음을 확인하여 문제를 해결합니다.

- 앱이 마스터 또는 릴리스 빌드입니다.
- 디바이스가 이 기능을 사용할 수 있는 빌드로 업데이트됩니다.
- 인터넷에 [연결되어](hololens-network.md)있습니다.
- [Microsoft Store 대한 엔드포인트가](hololens-offline.md) 올바르게 구성되었습니다.  

## <a name="web-installer"></a>웹 설치 관리자

사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다. 이 흐름은 쉬운 다운로드 및 설치 배포 방법과 결합된 앱 설치 관리자 사용합니다.

### <a name="how-to-set-up-web-install"></a>웹 설치를 설정하는 방법:

1. 앱을 설치하도록 올바르게 구성되었는지 확인합니다.
1. 웹 [페이지에서 설치를 사용하도록 설정하려면 다음 단계를 수행합니다.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>최종 사용자 환경:

1. 사용자는 위에서 선택한 방법을 사용하여 인증서를 받아 디바이스에 설치합니다.
1. 사용자는 위의 단계에서 만든 URL을 방문합니다.

이제 앱이 디바이스에 설치됩니다. 앱을 찾으려면 **시작 메뉴** 열고 **모든 앱** 단추를 선택하여 앱을 찾습니다.

- 앱 설치 관리자 설치 방법 문제 해결에 대한 자세한 도움말은 앱 설치 [관리자 문제 해결을](/windows/msix/app-installer/troubleshoot-appinstaller-issues)참조합니다.

> [!NOTE]
> 업데이트 프로세스 중 UI는 지원되지 않습니다. [따라서 이 페이지의](/windows/msix/app-installer/update-settings) ShowPrompt 옵션 및 관련 옵션은 지원되지 않습니다.

## <a name="sample-apps"></a>샘플 앱

사용 가능한 샘플 앱 중 하나를 앱 설치 관리자 사용해 보세요. 
> [!div class="nextstepaction"]
> [샘플 앱](/windows/mixed-reality/develop/features-and-samples)
