---
title: 배포 가이드 - 원격 지원으로 클라우드 연결 HoloLens 2 배포 규모 - 유지 관리
description: 클라우드 연결 네트워크를 통해 HoloLens 장치 유지 관리 팁
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252699"
---
# 유지 관리 - 클라우드 연결 가이드

## 업데이트

Microsoft는 장치 그룹에 업데이트를 배포하고 업데이트 설치를 위해 유지 관리 기간을 정의하는 기능 같은 추가 Windows 업데이트 중심 관리 기능을 IT 관리자에게 제공하는 비즈니스용 Windows 업데이트를 설계했습니다.

예정된 일수, 예약된 시간 및 장치에서 사용 시간을 설정하여 작업 시간 외에서 업데이트될 수 있도록 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 업데이트를 관리하는 방법을 배워 보십시오.

원격 도우미는 In-Box 앱으로, Microsoft Store 앱을 통해 업데이트할 수 있습니다. Microsoft Store를 통해 다운로드되는 모든 앱의 경우 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 앱 자체를 통해 수동으로 업데이트할 수 있습니다.

## 지원 플랜

지원 계획은 매우 중요한 일입니다. 누군가 또는 그룹이 HoloLens 장치에서 등록 프로세스 문제를 해결하고 조직 내에서 HoloLens 디바이스를 일반적으로 사용하는 데 도움이 됩니다. 사용자가 문제를 더 빠르게 해결하도록 허용하기 위해 에스컬레이터 프로세스는 다음 순서와 유사한 방식으로 처리하는 것이 권장됩니다.

1. 지원 센터
2. HoloLens 전문가 팀
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens 문제 해결 Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [고객 지원](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## 개발 계획

장치를 성공적으로 등록하면 이제 장치에 LOB 앱(LOB 앱)을 배포할 준비가 완료되었습니다. 이러한 앱은 요구 사항을 충족하기 위해&#39;사용자 지정 앱입니다.

이미 비즈니스용 앱이 있는 경우 [MDM을](https://docs.microsoft.com/hololens/app-deploy-intune)&#39;앱을 배포할 준비가 된 것입니다. 다른&#39;원하는 경우 [HoloLens 2의](https://docs.microsoft.com/hololens/app-deploy-overview) 응용 프로그램 배포 개요를 검토하여 장치에 LOB 앱을 배포하는 더 많은 방법을 알아보는 것이 좋습니다.

아직 LOB 앱을&#39;개발 중이면 혼합 현실 개발 docs를 검토하여 디자인 및 프로토타이핑을 시작하거나 혼합 현실 개발을 시작할 핵심 개념을 배워야 [합니다.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) [](https://docs.microsoft.com/windows/mixed-reality/design/design)

## 장치 관리 

이 가이드에서는 MDM(모바일 장치 관리) 설정에 대해 설명하는 동안 장치 제한이나 정책을 장치에 적용하는 데 사용되지 않습니다. 장치 관리를 사용하여 인증서를 푸시하여 액세스를 허용하거나 다양한 장치 제한으로 액세스를 제한할 수 있습니다. 

대부분의 경우 디바이스에 연결 제한(예: Bluetooth VPN, USB) 또는 카메라 또는 마이크에 대한 액세스를 해제할 수 있습니다. 이러한 관심사 중 한 가지가 있는 경우 일반적인 장치 제한 페이지를 [읽어보는 것이 좋습니다.](hololens-common-device-restrictions.md)

사용할 수 있는 기타 더 복잡한 장치 제한이 있습니다. 예:

- [SettingsPageVisibility를](settings-uri-list.md)사용하여 설정 앱에서 볼 수 있는 페이지를 제한하여 사용자가 설정 연결 변경과 같이 조정해야 하는 설정에만 액세스할 Wi-Fi 있습니다.
- [키오스크 모드를 사용하여](hololens-kiosk.md) 디바이스의 사용자에게 표시되는 UI를 제한합니다. 키오스크를 설정하여 단일 앱 또는 사용자 지정 시작 페이지가 있는 여러 앱을 표시하는 데 사용할 수 있습니다. 키오스크는 다른 사용자에게도 다양한 환경을 제공합니다.  
- 특정 앱 또는 프로세스가 완전히 시작되지 못하도록 [하는 WDAC(Windows](windows-defender-application-control-wdac.md) 응용 프로그램 제어)입니다.

장치 관리 또는 장치 제한의 다양한 방법에 대해 알아보고자 하는 경우 다음 단계를 진행하고 장치 관리 개요를 읽어 하세요.

## 다음 단계

> [!div class="nextstepaction"]
> [CSP 및 장치 관리 개요 읽기](hololens-csp-policy-overview.md)