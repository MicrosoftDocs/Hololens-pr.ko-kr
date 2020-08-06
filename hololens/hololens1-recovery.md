---
title: HoloLens 1 다시 시작, 초기화 또는 복구
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Windows Device Recovery Tool을 사용하여 이미지를 HoloLens 1세대로 플래시하는 방법
keywords: 사용 방법, 다시 부팅, 초기화, 복구, 하드 초기화, 소프트 초기화, 전원 주기, HoloLens, 종료, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915964"
---
# HoloLens 2(1세대) 다시 시작, 초기화 또는 복구

HoloLens에 문제가 발생한 경우 장치 복구를 사용하여 장치를 다시 시작하거나 초기화 또는 리플래시하는 것이 좋습니다. 이 문서에서는 권장되는 복구 단계를 순서대로 안내합니다.

HoloLens 2를 복구하려는 경우에는 해당 프로세스가 다르므로 [HoloLens 2 복구](https://docs.microsoft.com/hololens/hololens-recovery)를 참조하세요.

> [!NOTE]
> 이 문서에서는 HoloLens 장치와 소프트웨어를 중점적으로 다룹니다. 홀로그램이 올바르게 보이지 않는 경우, 홀로그램 품질을 향상시키는 요소에 대한 정보를 보려면 **[HoloLens 환경 고려 사항](hololens-environment-considerations.md)** 을 참조하세요.

## 다시 시작

### Cortana를 사용하여 안전하게 다시 시작 수행

Cortana를 사용하여 HoloLens를 다시 시작하는 것이 가장 안전합니다. 이는 일반적으로 HoloLens에 문제가 발생하는 경우 가장 먼저 시도해 볼 수 있는 방법입니다.

> [!NOTE] 
> 일부 장치에서는 Cortana를 사용할 수 없습니다.
> - Cortana는 모든 HoloLens(1세대) 장치에서 사용할 수 있습니다. 
> - Cortana는 Windows Holograpic, 버전 2004 업데이트 이전 빌드의 HoloLens 2 장치에서 사용할 수 있습니다.

1. HoloLens 켜기
1. 사용자가 로그인했는지, 장치에서 잠금 해제를 위해 암호 입력을 기다리고 있지 않은지 확인합니다.
2. ‘안녕 코타나, 재부팅’ 또는 ‘안녕 코타나, 다시 시작’이라고 말합니다.
3. Cortana가 응답하고 확인하라는 메시지가 표시됩니다. 질문 후에 사운드가 재생될 때까지 기다린 다음 "예"라고 말합니다. 장치가 다시 시작됩니다.

### 전원 단추를 사용하여 안전한 다시 시작

여전히 장치를 다시 시작할 수 없는 경우 **전원** 단추를 사용하여 다시 시작할 수 있습니다

1. **전원** 단추를 5초간 길게 누릅니다. 1초 후 5개의 LED가 모두 켜진 다음, 오른쪽에서 왼쪽으로 하나씩 천천히 꺼집니다. 5초 후 모든 LED가 꺼지면 성공적인 종료된 것입니다.
      
   > [!IMPORTANT]
   > 모든 LED가 꺼진 후 바로 단추 누르기를 중지합니다.
1. 종료가 완료될 때까지 1분 정도 기다립니다. 디스플레이가 꺼진 후에도 종료가 계속 진행 중일 수 있습니다.
2. **전원** 단추를 1초간 길게 눌러 장치를 다시 켭니다.

### Windows 장치 포털을 사용하여 안전하게 다시 시작 수행

> [!NOTE]
> 이 프로세스를 위해 HoloLens가 개발자 장치로 구성되어 있어야 합니다. [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)에서 자세히 알아보세요.

이전 절차로 다시 시작할 수 없는 경우 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용하여 장치를 다시 시작해 보세요. 오른쪽 위 모서리에 장치를 다시 시작하거나 종료하는 옵션이 있습니다.

### 안전하지 않은 강제 다시 시작 수행

이전 방법으로 HoloLens가 다시 시작되지 않는 경우 강제로 다시 시작합니다. 이 방법은 배터리를 제거하고 다시 설치하는 것과 같습니다. 장치가 손상된 상태에서 종료할 수 있으므로 위험합니다. 장치가 손상된 경우 HoloLens를 플래시해야 합니다.  

> [!WARNING]
> 이는 잠재적 위험이 있는 방법으로, 앞에 언급한 방법을 사용할 수 없는 경우에만 사용해야 합니다.

1. **전원** 단추를 10초 이상 길게 누릅니다.
   - 10초 이상 버튼을 길게 눌러도 됩니다.
   - 모든 LED 활동을 무시해도 안전합니다.
1. 단추를 놓고 2~3초 기다립니다.
1. **전원** 단추를 1초간 누릅니다.
1. 그래도 문제가 해결되지 않으면 모든 배터리 표시등이 꺼지고 화면에 홀로그램이 표시되지 않을 때까지 **전원** 단추를 4초간 누릅니다. 1분 정도 기다렸다가 **전원** 단추를 다시 눌러 장치를 켭니다.

## 공장 설정으로 초기화

> [!NOTE]
> 초기화하려면 배터리가 적어도 40% 충전되어 있어야 합니다.

HoloLens에 계속 문제가 있는 경우 공장 상태로 다시 설정해 보세요. 이 단계를 수행하면 해당 장치에 설치된 Windows Holographic 소프트웨어의 버전이 유지되며 다른 모든 항목은 공장 기본 설정으로 돌아갑니다.

>[!WARNING]
> 장치를 초기화하면 TPM 초기화 정보를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다. 초기화하면 설치된 최신 버전의 Windows Holographic만 설치됩니다. 모든 초기화 단계(조정, Wi-Fi에 연결, 사용자 계정 만들기, 앱 다운로드 등)를 다시 실행해야 합니다.

1. 설정 앱을 열고 **업데이트** > **복구**를 선택합니다.
1. **장치 초기화** 옵션을 선택하고 확인 메시지를 읽습니다.
1. 초기화를 확인합니다. 장치가 다시 시작되고 회전하는 기어와 진행률 표시줄이 표시됩니다.
1. 프로세스가 완료될 때까지 30분 정도 기다립니다. 작업이 완료되면 장치가 "기본 제공" 환경으로 다시 시작됩니다.

## 운영 체제 다시 설치

다시 시작하고 초기화한 후에도 계속 장치에 문제가 있는 경우 컴퓨터에서 복구 도구를 사용하여 HoloLens의 운영 체제와 펌웨어를 다시 설치할 수 있습니다.  

초기화를 하는데 HoloLens에 필요한 데이터가 .iso, .wim 또는 .vhd 파일과 유사한 FFU(Full Flash Update)에 패키징되어 있습니다. [FFU 이미지 파일 형식에 대해 알아보세요.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows Device Recovery Tool을 사용하여 HoloLens(1세대)에 새로운 운영 체제를 설치할 수 있습니다.  해당 도구를 사용하기 전에 HoloLens를 다시 시작하거나 초기화하여 문제를 해결할 수 있는지 확인합니다.

복구 프로세스에 시간이 걸릴 수 있습니다. 작업이 완료되면 최신 버전의 Windows Holographic 소프트웨어가 설치됩니다.

이 도구를 사용하려면 Windows 10 이상을 실행하며 4GB의 사용 가능한 저장소 공간이 있는 컴퓨터를 사용해야 합니다. 이 도구는 가상 컴퓨터에서 실행할 수 없습니다.

### HoloLens 복구

1. PC에서 [Windows Device Recovery Tool(WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)을 다운로드하여 설치합니다.
1. HoloLens와 함께 제공된 마이크로 USB 케이블을 사용하여 컴퓨터에 HoloLens(1세대)를 연결합니다.
1. Windows Device Recovery Tool을 열고 지침을 따릅니다.

HoloLens(1세대)가 자동으로 검색되지 않는 경우 **내 장치가 검색되지 않음**을 선택합니다. 그런 다음 지침에 따라 장치를 복구 모드로 설정합니다.

### 수동 플래시 모드

장치가 검색되지 않는 경우 다음 단계에 따라 플래시 모드로 설정합니다.

1. 모든 전원에서 장치를 분리합니다.
1. 장치가 켜져 있는 경우 완전히 꺼질 때까지 **전원** 단추를 누릅니다.
2. **볼륨 크게** 단추를 누른 다음 **전원** 단추를 짧게 탭합니다. 장치가 시작되고 중간 LED 표시등이 켜집니다.
3. PC에 장치를 연결합니다.
4. Windows Device Recovery Tool을 엽니다.
5. **내 장치가 검색되지 않음**을 선택한 다음, **HoloLens**를 선택합니다. 
6. 지침에 따라 장치를 복구합니다.
