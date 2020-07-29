---
title: HoloLens 1 다시 시작, 초기화 또는 복구
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: de53f8f2cccfe3ece8900c88c5379adf2fb55a7b
ms.sourcegitcommit: 5d38af8d17dfcc028e7e0b2bb888c6c9d1e40524
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899181"
---
# HoloLens 2(1세대) 다시 시작, 초기화 또는 복구

HoloLens에 문제가 발생한 경우 장치 복구를 사용하여 다시 시작하거나 초기화 또는 리플래시하는 것이 좋습니다.

HoloLens가 제대로 작동하지 않는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.  이 문서에서는 권장되는 복구 단계를 연속해서 안내합니다.

HoloLens 2를 복구하려면 프로세스에 차이가 있으므로 [](https://docs.microsoft.com/hololens/hololens-recovery)HoloLens 2복구[ 페이지를 확인하세요.](https://docs.microsoft.com/hololens/hololens-recovery)

이 문서에서는 HoloLens 장치 및 소프트웨어에 중점을 두며 홀로그램이 제대로 보이지 않는 경우 [이 문서](hololens-environment-considerations.md)에서 홀로그램 품질을 개선하는 환경적 요인에 대해 설명합니다.

## 다시 시작

### Cortana를 사용하여 안전하게 다시 시작 수행

HoloLens를 다시 시작하는 가장 안전한 방법은 Cortana를 사용하는 것입니다. 이는 일반적으로 HoloLens에 문제가 발생했을 때 쉽게 해 볼 수 있는 첫 단계입니다. 

> [!NOTE]
> 일부 장치에서는 Cortana를 사용할 수 없습니다. Cortana는 모든 HoloLens (1세대) 장치에서 사용할 수 있습니다.
> Cortana는 Windows Holograpic, 버전 2004 업데이트 이전 빌드의HoloLens 2 장치에서 사용할 수 있습니다.

1. 장치를 착용합니다.
1. 전원이 켜져 있는지, 사용자가 로그인했는지, 장치에서 잠금 해제를 위해 암호 입력을 기다리고 있지 않은지 확인합니다.
1. ‘안녕 코타나, 재부팅’ 또는 ‘안녕 코타나, 다시 시작’이라고 말합니다.
1. Cortana가 인식 후 사용자에게 확인을 요청합니다. Cortana가 질문을 마친 후 사용자의 응답을 듣고 있다는 것을 나타내는 소리가 재생될 때까지 기다린 후 ‘예’라고 말합니다.
1. 이제 장치가 다시 시작됩니다.

### 전원 버튼을 사용하여 안전하게 다시 시작 수행

여전히 장치를 다시 시작할 수 없는 경우 전원 버튼을 사용하여 다시 시작할 수 있습니다

1. 전원 버튼을 5초간 길게 누릅니다. 
   1. 1초 후 5개의 LED가 모두 켜지고 오른쪽에서 왼쪽으로 천천히 꺼집니다.
   1. 5초 후에는 모든 LED가 꺼지며 종료 명령이 성공적으로 실행되었다는 것을 알립니다.
   1. 모든 LED가 꺼지면 바로 버튼을 놓는 것이 중요합니다.
1. 종료가 제대로 완료될 때까지 1분 정도 기다립니다. 디스플레이가 꺼져 있는 경우에도 종료가 계속 진행 중일 수 있습니다.
1. 전원 버튼을 1초간 길게 눌러 장치를 다시 켭니다.

### Windows 장치 포털을 사용하여 안전하게 다시 시작 수행

> [!NOTE]
> 이를 수행하려면 HoloLens가 개발자 장치로 구성되어 있어야 합니다.  
> [Windows 장치 포털에 대해 자세히 알아보기](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

이전 절차로 다시 시작할 수 없는 경우 [Windows 장치 포털](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)을 사용하여 장치를 다시 시작해 보세요. 오른쪽 위 모서리에 장치를 다시 시작하거나 종료하는 옵션이 있습니다.

### 안전하지 않은 강제 다시 시작 수행

이전 모든 방법으로 장치를 다시 시작할 수 없는 경우 강제로 다시 시작할 수 있습니다. 이 방법은 HoloLens에서 배터리를 당겨 분리하는 것과 같습니다.  장치를 손상된 상태로 만들 수 있는 위험한 작업입니다.   장치가 손상된 경우 HoloLens를 플래시해야 합니다.  

> [!WARNING]
> 이는 잠재적으로 위험한 방법이므로 위의 모든 방법으로 다시 시작할 수 없을 때만 사용해야 합니다.

1. 전원 버튼을 최소 10초간 길게 누릅니다. 
   - 10초 이상 버튼을 길게 눌러도 됩니다.
   - 모든 LED 활동을 무시해도 안전합니다.
1. 버튼을 놓고 2-3초간 기다립니다.
1. 전원 버튼을 1초간 길게 눌러 장치를 다시 켭니다.
그래도 문제가 해결되지 않으면 모든 배터리 표시등이 꺼지고 화면에 홀로그램이 표시되지 않을 때까지 전원 버튼을 4초간 누릅니다. 1분 정도 기다렸다가 전원 버튼을 다시 눌러 장치를 켭니다.

## 공장 설정으로 초기화

> [!NOTE]
> 초기화하려면 배터리가 적어도 40% 충전되어 있어야 합니다.

다시 시작한 후에도 계속 HoloLens에 문제가 발생하는 경우 공장 상태로 다시 초기화해 보세요.  HoloLens를 초기화하면 해당 장치에 설치된 Windows Holographic 소프트웨어의 버전이 유지되며 다른 모든 항목은 공장 기본 설정으로 돌아갑니다.

장치를 초기화하면 TPM 초기화를 포함한 모든 개인 데이터, 앱 및 설정 내용이 지워집니다. 초기화하면 최신 설치된 버전의 Windows Holographic만 설치되며 모든 초기화 단계(보정, Wi-Fi 연결, 사용자 계정 만들기, 앱 다운로드 등)를 다시 실행해야 합니다.

1. 설정 앱을 시작하고 **업데이트** > **복구**를 선택합니다.
1. **장치 초기화** 옵션을 선택하고 확인 메시지를 읽습니다.
1. 장치 초기화 동의하면 장치가 다시 시작되고 진행률 표시줄과 함께 회전하는 톱니바퀴가 표시됩니다.
1. 프로세스가 완료될 때까지 30분 정도 기다립니다.
1. 초기화가 완료되면 장치가 기본 제공 환경으로 다시 시작됩니다.

## 운영 체제 재설치

다시 부팅하고 초기화한 후에도 계속 장치에 문제가 있는 경우 컴퓨터에서 복구 도구를 사용하여 HoloLens의 운영 체제와 펌웨어를 다시 설치할 수 있습니다.  

HoloLens 초기화에 필요한 모든 데이터는 FFU(Full Flash Update)에 패키지화되어 있습니다.   이는 iso, wim 또는 vhd와 비슷합니다.  [FFU 이미지 파일 형식에 대해 알아보세요.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

필요한 경우 Windows Device Recovery Tool을 사용하여 HoloLens(1세대)에 완전히 새로운 운영 체제를 설치할 수 있습니다. 

이 도구를 사용하기 전에 HoloLens를 다시 시작하거나 초기화하여 문제를 해결할 수 있는지 확인합니다. 복구 프로세스에 시간이 걸릴 수 있습니다.  작업이 완료되면 HoloLens에 대해 승인된 최신 버전의 Windows Holographic 소프트웨어가 설치됩니다.

이 도구를 사용하려면 Windows 10 이상을 실행하며 4GB의 사용 가능한 저장소 공간이 있는 컴퓨터를 사용해야 합니다.  이 도구는 가상 컴퓨터에서 실행할 수 없습니다.

### HoloLens 복구:

1. PC에서 [Windows Device Recovery Tool(WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)을 다운로드하여 설치합니다.
1. HoloLens와 함께 제공된 마이크로 USB 케이블을 사용하여 컴퓨터에 HoloLens(1세대)를 연결합니다.
1. Windows Device Recovery Tool을 실행하여 지침을 따릅니다.

HoloLens(1세대)가 자동으로 검색되지 않는 경우 **장치가 검색되지 않음**을 선택하고 지침에 따라 장치를 복구 모드로 전환합니다.

### 수동 플래시 모드:

장치가 검색되지 않는 경우 다음 방법을 사용하여 수동으로 플래시 모드로 전환하세요.

1. 모든 전원에서 장치를 분리합니다.
1. 장치가 켜져 있는 경우 완전히 꺼질 때까지 전원 버튼을 누릅니다.
1. **볼륨 크게** 버튼을 누른 다음 **전원 버튼**을 가볍게 탭합니다. 
1. 장치가 부팅되고 중간 LED 표시등이 켜집니다.
1. PC에 장치를 연결합니다.
1. Windows Device Recovery Tool을 실행합니다.
1. *장치가 검색되지 않음**을 선택한 다음 **HoloLens**를 선택해야 합니다. 
1. 지침에 따라 장치를 복구합니다.
