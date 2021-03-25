---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 유지 관리
description: Dynamics 365 가이드를 통해 회사 연결 네트워크를 통해 HoloLens 2 장치를 유지 관리하는 방법을 알아보세요.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448598"
---
# <a name="maintain---corporate-connected-guide"></a>유지 관리 - 회사 연결 가이드

## <a name="update-hololens"></a>HoloLens 업데이트

Microsoft는 장치 그룹에 업데이트를 배포하고 업데이트 설치를 위해 유지 관리 기간을 정의하는 기능 같은 추가 Windows 업데이트 중심 관리 기능을 IT 관리자에게 제공하는 비즈니스용 Windows 업데이트를 설계했습니다.

인기 있는 업데이트 관리 방법 중 하나는 기능 지연을 30일로 연기하는 것입니다. 이를 통해 관리자는 새 기능을 업데이트하고 미리 보고, 먼저 지식을 얻고 지원 센터에 새로운 변경 내용을 알릴 수 있습니다.

예정된 일, 예약된 시간 및 장치에서 사용 시간을 설정하는 [등 HoloLens](https://docs.microsoft.com/hololens/hololens-updates)업데이트를 관리하는 방법을 알아보고, 작업 시간 외에서 업데이트됩니다.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 가이드(및 기타 스토어 앱)를 업데이트하는 방법

Dynamics 365 가이드는 In-Box 앱으로, Microsoft Store 앱을 통해 업데이트할 수 있습니다. Microsoft Store를 통해 다운로드되는 모든 앱의 경우 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 앱 자체를 통해 수동으로 업데이트할 수 있습니다.

## <a name="how-to-update-lob-apps"></a>LOB 앱을 업데이트하는 방법

LOB 앱은 Intune에 추가된 방식으로 업데이트할 수 있습니다. 더 높은 버전 번호의 새 앱을 기존 앱 구성에 업로드하여 Intune에서 앱을 업데이트할 수 있습니다. 장치가 Intune에 동기화하면 최신 앱 버전이 있으며 최신 앱이 다운로드된 후 이전 앱을 대체합니다.

1. 새 앱을 업로드하려면 [MEM 포털](https://endpoint.microsoft.com/#home)앱  ->  **** -> 모든 **앱**  ->  *TheNameOfYourApp 속성으로*  ->  **이동합니다.**
2. 앱 정보 옆에 있는 편집을 **선택합니다.**
3. 업데이트할 파일 &quot; 선택의 값으로 &quot; 파일을 선택합니다.
4. 여기에서 상황에 맞는 메뉴를 사용하여 파일 탐색기를 열고 최신 버전의 LOB 앱을 업로드합니다. 종속성은 필요한 경우 포함해야 합니다.

자세한 내용은 [다음을 참조하세요. HoloLens용 Intune 앱 배포](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>개발 계획

장치가 성공적으로 등록되면 이제 장치에 더 많은 LOB 앱을 배포할 준비가 완료되었습니다. 이 가이드의 기간 동안 샘플 앱을 사용하지만 조직의 요구에 따라 구축된 사용자 지정 앱을 사용할 가능성이 더 높습니다.

LOB 앱이 이미 있는 경우 [MDM을](https://docs.microsoft.com/hololens/app-deploy-intune)통해 앱을 배포할 준비가 된 것입니다. 다른 방법을 원할 경우 [HoloLens 2의](https://docs.microsoft.com/hololens/app-deploy-overview) 응용 프로그램 배포 개요를 검토하여 장치에 LOB 앱을 배포하는 더 많은 방법을 알아보하세요.

아직 LOB 앱을 만들지 않았거나 아직 만드는 중이면 혼합 현실 개발 docs를 [](https://docs.microsoft.com/windows/mixed-reality/design/design) 검토하여 혼합 현실 개발을 시작하여 디자인 및 프로토타이핑을 시작하거나 혼합 현실 개발을 시작하기 위한 핵심 개념을 배워야 [합니다.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>지원 플랜

지원 계획은 매우 중요한 일입니다. HoloLens 장치에서 등록 프로세스 문제를 해결하고 조직 내에서 HoloLens 디바이스를 일반적으로 사용하는 방법을 교육한 사람이나 그룹이 있는 것이 유용합니다. 사용자가 문제를 보다 빠르게 해결하도록 허용하기 위해 에스컬레이터 프로세스는 다음 순서와 유사한 방식으로 처리하는 것이 있습니다.

1. 지원 센터
2. HoloLens 전문가 팀
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens 문제 해결 Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [고객 지원](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>장치 관리

이 가이드에서는 MDM(모바일 장치 관리)을 설정하는 데 대해 설명하고 일부 장치 구성을 설정하고 인증서 및 프록시와 관련한 액세스가 허용되는 Wi-Fi 사용했습니다. 그러나 MDM을 사용하여 CSP 및 정책을 통해 장치 제한을 적용할 수도 있습니다.

대부분의 경우 디바이스에 연결 제한이 있을 수 있습니다(예: Bluetooth, VPN, USB 또는 카메라 또는 마이크에 대한 액세스 끄기). 이러한 관심사 중 한 가지가 있는 경우 일반적인 장치 제한 페이지를 [읽어보는 것이 좋습니다.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

사용할 수 있는 기타 더 복잡한 장치 제한이 있습니다. 예:

- [SettingsPageVisibility를](https://docs.microsoft.com/hololens/settings-uri-list)사용하여 설정 앱에서 볼 수 있는 페이지를 제한하여 사용자가 설정 연결을 변경하는 등 조정해야 하는 설정에만 액세스할 Wi-Fi 있습니다.
- [키오스크 모드를 사용하여](https://docs.microsoft.com/hololens/hololens-kiosk) 디바이스의 사용자에게 표시되는 UI를 제한합니다. 키오스크를 설정하여 단일 앱 또는 사용자 지정 시작 페이지가 있는 여러 앱을 표시하는 데 사용할 수 있습니다. 키오스크는 사용자마다 다른 환경을 제공 할 수도 있습니다.
- 특정 앱 또는 프로세스가 완전히 시작되지 못하도록 [하는 WDAC(Windows](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 응용 프로그램 제어)입니다.

장치 관리 또는 장치 제한의 추가 방법에 대해 알아보고자 하는 경우 다음 단계를 진행하고 장치 관리 개요 [를 읽어 하세요.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





