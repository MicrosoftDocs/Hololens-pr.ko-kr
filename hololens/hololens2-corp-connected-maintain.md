---
title: 배포 가이드 – Dynamics 365 Guides 통해 회사 연결 HoloLens 2 - 유지 관리
description: Dynamics 365 Guides 사용하여 회사 연결된 네트워크를 통해 HoloLens 2 디바이스를 유지 관리하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660262"
---
# <a name="maintain---corporate-connected-guide"></a>유지 관리 - 회사 연결 가이드

## <a name="update-hololens"></a>HoloLens 업데이트

Microsoft는 IT 관리자에게 디바이스 그룹에 업데이트를 배포하고 업데이트를 설치하기 위한 유지 관리 기간 정의 기능과 같은 추가 Windows 업데이트 중심 관리 기능을 제공하도록 비즈니스용 Windows 업데이트를 설계했습니다.

업데이트를 관리하는 한 가지 인기 있는 방법은 30일의 기능 지연을 수행하는 것입니다. 이를 통해 관리자는 새로운 기능을 업데이트하고 미리 볼 수 있으며, 직접 지식을 얻고 지원 센터에게 새로운 변경 내용을 알릴 수 있습니다.

작업 시간 외에 [업데이트되도록](/hololens/hololens-updates)예약된 일, 예약된 시간 및 디바이스에서 활성 시간 설정을 포함하여 HoloLens 업데이트를 관리하는 방법을 알아봅니다.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 Guides(및 기타 스토어 앱)를 업데이트하는 방법

Dynamics 365 Guides In-Box 앱이며 Microsoft Store 앱을 통해 업데이트할 수 있습니다. Microsoft Store 통해 다운로드되는 모든 앱의 경우 Microsoft Store 앱 자체를 통해 수동으로 [업데이트할](/hololens/holographic-store-apps#update-apps) 수 있습니다.

## <a name="how-to-update-lob-apps"></a>LOB 앱을 업데이트하는 방법

LOB 앱은 Intune에 추가된 것과 동일한 방식으로 업데이트할 수 있습니다. Intune에서 버전 번호가 더 높은 새 앱을 기존 앱 구성에 업로드하여 앱을 업데이트할 수 있습니다. 디바이스가 Intune에 동기화되면 최신 앱 버전이 있고 최신 앱이 다운로드되고 이전 앱을 대체합니다.

1. 최신 앱을 업로드하려면 [MEM 포털](https://endpoint.microsoft.com/#home)  ->  **앱** -> 모든 **앱**  ->  *TheNameOfYourApp*  ->  **속성으로 이동합니다.**
2. 앱 정보 옆에 있는 **편집을 선택합니다.**
3. &quot;업데이트할 파일 선택 값에 대해 &quot; 파일을 선택합니다.
4. 여기에서 상황에 맞는 메뉴를 사용하여 파일 탐색기를 열고 최신 버전의 LOB 앱을 업로드합니다. 필요에 따라 dependencies를 포함해야 합니다.

자세한 내용: [HoloLens Intune 앱 배포](/hololens/app-deploy-intune)

## <a name="development-plan"></a>개발 계획

디바이스가 성공적으로 등록되면 이제 더 많은 LOB 앱을 디바이스에 배포할 준비가 되었습니다. 이 가이드의 기간 동안 샘플 앱을 사용하지만 조직의 요구에 맞게 빌드된 사용자 지정 앱을 사용할 가능성이 더 높습니다.

LOB 앱이 이미 있는 경우 [MDM을 통해 앱을 배포할](/hololens/app-deploy-intune)준비가 된 것입니다. 다른 방법을 원하는 경우 HoloLens 2 대한 [애플리케이션 배포 개요를](/hololens/app-deploy-overview) 검토하여 디바이스에 LOB 앱을 배포하는 방법에 대해 자세히 알아보세요.

아직 사용자 고유의 LOB 앱을 만들지 않았거나 아직 만드는 중이라면 혼합 현실 개발 문서를 검토하여 [디자인 및 프로토타이핑을 시작하거나](/windows/mixed-reality/design/design) 혼합 현실 개발을 시작하기 위한 핵심 개념을 알아보세요. [](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>지원 플랜

지원 플랜은 훌륭한 것입니다. HoloLens 디바이스에서 등록 프로세스 문제 해결에 대해 학습된 사용자 또는 그룹이 있고 조직 내에서 HoloLens 디바이스를 일반적으로 사용하는 것도 유용합니다. 사용자가 문제를 더 빠르게 해결할 수 있도록 에스컬레이션 프로세스가 이 순서와 비슷한 방식으로 처리되는 것이 좋습니다.

1. 지원 센터.
2. HoloLens 전문가 팀
3. [HoloLens Docs](/hololens/)  /  [HoloLens 문제 해결 문서](/hololens/hololens-troubleshooting)
4. [지원 담당자에게 문의](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>디바이스 관리

이 가이드에서는 MDM(모바일 장치 관리) 설정에 대해 설명했으며, 이를 사용하여 일부 디바이스 구성을 설정하고 설정을 적용하여 Wi-Fi 인증서 및 프록시 측면에서 액세스를 허용합니다. 그러나 MDM을 사용하여 CSP 및 정책을 통해 디바이스 제한을 적용할 수도 있습니다.

대부분의 경우 디바이스에는 Bluetooth, VPN, USB 또는 카메라 또는 마이크에 대한 액세스 해제와 같은 연결 제한이 있을 수 있습니다. 이러한 관심 사항이 있는 경우 [일반적인 디바이스 제한 페이지](/hololens/hololens-common-device-restrictions)를 읽어 보시기 바랍니다.

사용할 수 있는 다른 더 복잡한 디바이스 제한이 있습니다. 예:

- [SettingsPageVisibility를](/hololens/settings-uri-list)사용하여 설정 앱에서 볼 수 있는 페이지를 제한하여 사용자가 조정해야 하는 설정(예: Wi-Fi 연결 변경)에만 액세스할 수 있도록 합니다.
- [키오스크 모드를](/hololens/hololens-kiosk) 사용하여 디바이스의 사용자에게 제공된 UI를 제한합니다. 단일 앱 또는 사용자 지정 시작 페이지가 있는 여러 앱을 표시하도록 키오스크를 설정할 수 있습니다. 키오스크는 다른 사용자에게 다른 환경을 표시할 수도 있습니다.
- [WDAC(애플리케이션 제어)를 Windows](/hololens/windows-defender-application-control-wdac) 특정 앱 또는 프로세스가 완전히 시작하지 않도록 합니다.

디바이스 관리 또는 디바이스 제한의 추가 방법에 대해 알아보려면 다음 단계를 진행하여 [장치 관리 개요를](/hololens/hololens-csp-policy-overview)읽어보세요.





