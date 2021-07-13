---
title: 배포 가이드-원격 지원으로 대규모 클라우드 연결 HoloLens 2 배포-유지 관리
description: 클라우드 연결 네트워크를 통해 HoloLens 장치를 유지 관리 하 고 지 원하는 데 대 한 팁을 최신 상태로 유지 하세요.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635163"
---
# <a name="maintain---cloud-connected-guide"></a>유지 관리-클라우드 연결 가이드

## <a name="updates"></a>업데이트

Microsoft는 IT 관리자에 게 장치 그룹에 업데이트를 배포 하 고 업데이트를 설치 하기 위한 유지 관리 기간을 정의 하는 기능과 같은 추가 Windows 업데이트 중심 관리 기능을 제공 하도록 Windows 업데이트 설계 되었습니다.

예약 된 날짜, 예약 된 시간을 비롯 하 여 [HoloLens 업데이트를 관리](/hololens/hololens-updates) 하는 방법 및 장치에서 활성 시간을 설정 하 여 업무 외 시간에 업데이트 하는 방법을 알아봅니다.

원격 지원 In-Box 앱 이며 Microsoft Store 앱을 통해 업데이트할 수 있습니다. Microsoft Store을 통해 다운로드 되는 모든 앱의 경우 Microsoft Store 앱 자체 [를 통해 수동으로 업데이트할](/hololens/holographic-store-apps#update-apps) 수 있습니다.

## <a name="support-plan"></a>지원 플랜

지원 플랜은 매우 좋은 일입니다. HoloLens 장치에서 등록 프로세스의 문제를 해결 하 고 조직 내에서 HoloLens 장치를 일반적으로 사용 하는 것이 좋습니다. 사용자가 문제를 보다 빠르게 해결할 수 있도록 하기 위해 에스컬레이션 프로세스를 다음과 같은 순서로 처리 하는 것이 좋습니다.

1. 지원 센터.
2. HoloLens 전문가 팀
3. [문서 HoloLens](/hololens/)  /  [HoloLens 문제 해결 문서](/hololens/hololens-troubleshooting)
4. [지원 문의](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>개발 계획

장치를 성공적으로 등록 하면 LOB (기간 업무) 앱을 장치에 배포할 준비가 되었습니다. 이러한 앱은 조직&#39;필요에 맞게 빌드된 사용자 지정 앱입니다.

Lob (기간 업무) 앱이 이미 있는 경우 [MDM을 통해 앱을 배포할](/hololens/app-deploy-intune)준비를&#39;있습니다. d를 사용&#39;하 여 다른 방법을 선호 하는 경우 [에는 HoloLens 2에 대 한 응용 프로그램 배포 개요](/hololens/app-deploy-overview) 를 검토 하 여 장치에 LOB 앱을 배포 하는 방법에 대 한 자세한 방법을 알아보세요.

사용자 고유의 LOB 앱을 만들거나 아직 만든 프로세스에 있는 경우에는 혼합 현실 개발 문서를 검토 하 여 [혼합 현실](/windows/mixed-reality/discover/get-started-with-mr) 개발을 시작 하는 데&#39;도움이 되는 핵심 개념을 [설계 하 고 프로토타입](/windows/mixed-reality/design/design) 하는 방법에 대해 알아봅니다.

## <a name="device-management"></a>디바이스 관리 

이 가이드는 장치 제한을 적용 하는 데 사용 되지 않은 MDM (모바일 장치 관리) 설정에 대해 설명 했지만 장치에 적용 되었습니다. 장치 관리를 사용 하 여 인증서를 푸시하여 액세스를 허용 하거나 다양 한 장치 제한 사항으로 액세스를 제한할 수 있습니다. 

대부분의 경우 장치는 Bluetooth, VPN, USB 등의 연결 제한이 있거나 카메라 또는 마이크에 대 한 액세스를 끌 수 있습니다. 이러한 관심사가 있으면 [일반적인 장치 제한 페이지](hololens-common-device-restrictions.md)를 참조 하는 것이 좋습니다.

사용할 수 있는 기타 복잡 한 장치 제한이 있습니다. 예:

- [Settingspagevisibility](settings-uri-list.md)를 사용 하 여 설정 앱에서 볼 수 있는 페이지를 제한 하 여 사용자가 Wi-Fi 연결을 변경 하는 등 조정 해야 하는 설정에만 액세스할 수 있도록 합니다.
- [키오스크 모드](hololens-kiosk.md) 를 사용 하 여 장치에서 사용자에 게 표시 되는 UI를 제한할 수 있습니다. 단일 앱 또는 사용자 지정 시작 페이지를 사용 하 여 여러 앱을 표시 하도록 키오스크를 설정할 수 있습니다. 키오스크는 다른 사용자에 게 다른 환경을 제공할 수도 있습니다.  
- [응용 프로그램 제어 (WDAC)를 Windows](windows-defender-application-control-wdac.md) 하 여 특정 앱 또는 프로세스가 완전히 시작 되지 않도록 합니다.

장치 관리 또는 장치 제한에 대 한 다른 방법을 알아보려면 다음 단계를 수행 하 고 장치 관리 개요를 참조 하세요.

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [Csp 및 장치 관리 개요 읽기](hololens-csp-policy-overview.md)