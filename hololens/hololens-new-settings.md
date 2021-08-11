---
title: 새 설정 앱 소개
description: 새 설정 앱에 대해 알아보기
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, 설정, 앱 선택기, 볼륨
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 4187ae99a25fc6dd3f407410da27568d4b2b6865934b0c615680f295ec7977be
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663042"
---
# <a name="new-settings-app"></a>새 설정 앱

[Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1)에서는 새 버전의 설정 앱을 도입했습니다. 새 설정 앱에는 소리, 전원 및 절전 모드, 네트워크 및 인터넷, 앱, 계정, 접근성 등의 영역에서 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.

> [!NOTE]
> 새 설정 앱은 레거시 설정 앱과 구별되므로 이전에 사용 환경에 있었던 모든 설정 창은 업데이트 시 제거됩니다.

![새 설정 앱 홈페이지](images/new-settings-app.png)

**새로운 기능 및 설정**
- 설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈페이지에서 설정을 검색합니다.
- 시스템 > [색 보정](hololens2-display.md#how-to-use-display-color-calibration)
    - HoloLens 2 디스플레이의 대체 색 프로필을 선택합니다.
- 시스템 > 소리:
  - 입력 및 출력 오디오 장치: 입력 오디오 장치와 출력 오디오 장치(예: Bluetooth 헤드폰을 통한 오디오 수신 또는 오디오 입력용 USB-C 마이크 사용)를 따로 선택합니다.
    > [!NOTE]
    > Bluetooth 마이크는 HoloLens 2에서 지원하지 않습니다.
  - 앱 볼륨: 각 앱의 볼륨을 따로 조정합니다. [앱당 볼륨 조절](holographic-home.md#per-app-volume-control)을 참조하세요.
- 시스템 > 전원 및 절전: 비활성 기간 후에 장치가 절전 모드로 바뀌어야 하는 시기를 선택합니다.
- 시스템 > 배터리: 수동으로 배터리 절약 모드 모드를 사용하도록 설정하거나 배터리 절약 모드 모드가 자동으로 켜지는 배터리 임계값을 설정합니다.
- 장치 > USB: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.
- 네트워크 및 인터넷:
  - 이제 USB-C 이더넷 어댑터가 네트워크 및 인터넷에 표시됩니다.
  - 이제 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.
  - 이제 HoloLens 2 비행기 모드를 사용하도록 설정할 수 있습니다.
- 앱: 파일 형식과 링크 유형에 사용되는 기본 앱을 다시 설정할 수 있습니다. 자세한 내용은 [기본 앱 선택기](holographic-home.md#default-app-picker)를 참조하세요.
- 계정 > 다른 사용자: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.
- 접근성: 텍스트 크기와 일부 시각적 효과를 변경합니다.

**알려진 문제**
- 이전에 배치된 설정 창이 제거됩니다(위 참고 사항 참조).
- 더 이상 설정 앱을 통해 장치 이름을 바꿀 수 없습니다. IT 관리자는 [HoloLens 2용 Windows Autopilot](hololens2-autopilot.md) 장치 이름 템플릿 또는 MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 노드를 사용하여 장치 이름을 바꿀 수 있습니다.
- 이더넷 페이지에는 항상 가상 이더넷 장치("UsbNcm")가 표시됩니다.
- UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램의 특성 때문에 새 Microsoft Edge 대한 배터리 사용량이 정확하지 않을 수 있습니다(곧 수정될 예정 없음).

