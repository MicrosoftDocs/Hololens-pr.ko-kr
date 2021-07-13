---
title: 배포 가이드 – Dynamics 365 Guides를 사용 하 여 회사에 연결 된 HoloLens 2
description: Dynamics 365 Guides를 사용 하 여 회사에 연결 된 네트워크를 통해 HoloLens 2 장치를 유지 관리 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사에 연결 된 Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636999"
---
# <a name="maintain---corporate-connected-guide"></a>유지 관리-회사에 연결 된 가이드

## <a name="update-hololens"></a>HoloLens 업데이트

Microsoft는 IT 관리자에 게 장치 그룹에 업데이트를 배포 하 고 업데이트를 설치 하기 위한 유지 관리 기간을 정의 하는 기능과 같은 추가 Windows 업데이트 중심 관리 기능을 제공 하도록 Windows 업데이트 설계 되었습니다.

업데이트를 관리 하는 널리 사용 되는 방법 중 하나는 30 일간의 기능 지연입니다. 이를 통해 관리자는 새로운 기능을 업데이트 하 고 미리 볼 수 있으며, 처음에는 지식을 얻고 새로운 변경 사항을 지원 센터에 알립니다.

예약 된 날짜, 예약 된 시간 및 장치의 활성 시간 설정을 포함 하 여 [HoloLens 업데이트를 관리](/hololens/hololens-updates)하는 방법을 알아보고 업무 외 시간에 업데이트 합니다.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 Guides 및 기타 스토어 앱을 업데이트 하는 방법

Dynamics 365 Guides은 In-Box 앱 이며 Microsoft Store 앱을 통해 업데이트할 수 있습니다. Microsoft Store을 통해 다운로드 되는 모든 앱의 경우 Microsoft Store 앱 자체를 [통해 수동으로 업데이트할](/hololens/holographic-store-apps#update-apps) 수 있습니다.

## <a name="how-to-update-lob-apps"></a>LOB 앱을 업데이트 하는 방법

LOB 앱은 Intune에 추가 된 것과 동일한 방식으로 업데이트할 수 있습니다. 더 높은 버전 번호의 새 앱을 기존 앱 구성에 업로드 하 여 Intune에서 앱을 업데이트할 수 있습니다. 장치가 Intune에 동기화 되 면 최신 앱 버전이 있고 최신 앱이 다운로드 되 고 이전 앱을 교체 하는 것을 확인할 수 있습니다.

1. 최신 앱을 업로드 하려면 [메모리 포털](https://endpoint.microsoft.com/#home)  ->  **앱** -모든 **앱**>  ->  *TheNameOfYourApp*  ->  **속성** 으로 이동 합니다.
2. 앱 정보 옆에서 편집을 선택 **합니다.**
3. &quot;업데이트할 파일 선택 값에 대해 &quot; 파일을 선택 합니다.
4. 여기에서 상황에 맞는 메뉴를 사용 하 여 파일 탐색기를 열고 최신 버전의 LOB 앱을 업로드 합니다. 필요에 따라 종속성을 포함 해야 합니다.

자세히 보기: [Intune 앱 배포 HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>개발 계획

장치를 성공적으로 등록 하면 이제 장치에 더 많은 LOB 앱을 배포할 준비가 되었습니다. 이 가이드의 기간 동안 샘플 앱을 사용 하지만 조직의 요구에 맞게 빌드된 사용자 지정 앱을 사용 하려고 할 가능성이 높습니다.

LOB 앱이 이미 있는 경우 [MDM을 통해 앱을 배포할](/hololens/app-deploy-intune)준비가 된 것입니다. 다른 방법을 선호 하는 경우 [HoloLens 2에 대 한 응용 프로그램 배포 개요](/hololens/app-deploy-overview) 를 검토 하 여 장치에 LOB 앱을 배포 하는 방법에 대 한 자세한 방법을 알아보세요.

사용자 고유의 LOB 앱을 만들거나 아직 생성 중인 경우에는 혼합 현실 개발 문서를 검토 하 여 혼합 현실 개발을 시작 하기 위한 핵심 개념을 [설계 하 고 프로토타입](/windows/mixed-reality/design/design) 하거나 학습을 시작 [합니다.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>지원 플랜

지원 플랜은 매우 좋은 일입니다. 사용자 또는 그룹을 사용 하면 HoloLens 장치에서 등록 프로세스의 문제를 해결 하 고 조직 내에서 HoloLens 장치를 일반적으로 사용 하는 데 도움이 됩니다. 사용자가 문제를 보다 빠르게 해결할 수 있도록 하기 위해 에스컬레이션 프로세스를 다음과 같은 순서로 처리 하는 것이 좋습니다.

1. 지원 센터.
2. HoloLens 전문가 팀
3. [문서 HoloLens](/hololens/)  /  [HoloLens 문제 해결 문서](/hololens/hololens-troubleshooting)
4. [지원 문의](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>디바이스 관리

이 가이드에서는 MDM (모바일 장치 관리)을 설정 하는 방법에 대해 설명 하 고,이를 사용 하 여 일부 장치 구성을 설정 하 고, Wi-Fi 인증서 및 프록시를 기준으로 액세스를 허용 하는 설정을 적용 합니다. 그러나 MDM은 Csp 및 정책을 통해 장치 제한을 적용 하는 데 사용할 수도 있습니다.

대부분의 경우 장치는 Bluetooth, VPN, USB 등의 연결 제한이 있을 수도 있고 카메라나 마이크에 대 한 액세스를 끌 수도 있습니다. 이러한 관심사가 있으면 [일반적인 장치 제한 페이지](/hololens/hololens-common-device-restrictions)를 참조 하는 것이 좋습니다.

사용할 수 있는 기타 복잡 한 장치 제한이 있습니다. 예:

- [Settingspagevisibility](/hololens/settings-uri-list)를 사용 하 여 설정 앱에서 볼 수 있는 페이지를 제한 하 여 사용자가 조정 해야 하는 설정 (예: Wi-Fi 연결 변경)에만 액세스할 수 있도록 허용 합니다.
- [키오스크 모드](/hololens/hololens-kiosk) 를 사용 하 여 장치에서 사용자에 게 표시 되는 UI를 제한할 수 있습니다. 단일 앱 또는 사용자 지정 시작 페이지를 사용 하 여 여러 앱을 표시 하도록 키오스크를 설정할 수 있습니다. 키오스크는 다른 사용자에 게 다른 환경을 제공할 수도 있습니다.
- [응용 프로그램 제어 (WDAC)를 Windows](/hololens/windows-defender-application-control-wdac) 하 여 특정 앱 또는 프로세스가 완전히 시작 되지 않도록 합니다.

장치 관리 또는 장치 제한의 추가 방법에 대해 알아보려면 다음 단계를 수행 하 고 [장치 관리 개요](/hololens/hololens-csp-policy-overview)를 참조 하세요.





