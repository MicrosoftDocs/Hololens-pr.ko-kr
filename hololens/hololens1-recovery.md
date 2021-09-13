---
title: HoloLens 1 다시 시작, 다시 설정 또는 복구
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows Device Recovery 도구를 사용하여 이미지를 HoloLens 1세대로 플래시하는 방법입니다.
keywords: 방법, 다시 부팅, 다시 설정, 복구, 하드 재설정, 일시 재설정, 전원 주기, HoloLens, 종료, wdrt, Windows 디바이스 복구 도구
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033654"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens 다시 시작, 다시 설정 또는 복구(1세대)

HoloLens 문제가 발생하는 경우 다시 시작하거나 다시 설정하거나 디바이스 복구를 사용하여 디바이스를 리플래시할 수도 있습니다. 이 문서에서는 권장되는 복구 단계를 순서대로 안내합니다.

HoloLens 2 복구하려는 경우 프로세스가 다르므로 [HoloLens 2 복구를](hololens-recovery.md)참조하세요.

> [!NOTE]
> 이 문서에서는 HoloLens 디바이스 및 소프트웨어에 중점을 둡니다. 홀로그램이 제대로 보이지 않는 경우 **[홀로그램](hololens-environment-considerations.md)** 품질을 향상시키는 요소에 대한 자세한 내용은 환경 고려 사항 HoloLens 참조하세요.

## <a name="restart"></a>재시작

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana 사용하여 안전하게 다시 시작

HoloLens 다시 시작하는 가장 안전한 방법은 일반적으로 HoloLens 문제가 발생할 때 가장 먼저 시도하는 Cortana 사용하는 것입니다.

> [!NOTE] 
> Cortana 모든 디바이스에서 사용할 수 있는 것은 아닙니다.
> - Cortana 모든 HoloLens(1세대) 디바이스에서 사용할 수 있습니다. 
> - Cortana Windows Holograpic 버전 2004 업데이트 전에 빌드의 HoloLens 2 디바이스에서 사용할 수 있습니다.

1. HoloLens 켭니다.
1. 사용자가 로그인되어 있고 디바이스가 암호 잠금을 해제할 때까지 기다리고 있지 않은지 확인합니다.
2. "Hey Cortana, reboot" 또는 "Hey Cortana, restart"라고 말합니다.
3. Cortana 응답하고 확인하라는 메시지를 표시합니다. 질문 다음에 소리가 재생되기를 기다린 다음, "예"라고 말합니다. 디바이스가 다시 시작됩니다.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>전원 단추를 사용하여 안전하게 다시 시작

여전히 디바이스를 다시 시작할 수 없는 경우 **전원** 단추를 사용하여 디바이스를 다시 시작해 보세요.

1. **전원** 단추를 5초 동안 길게 누릅니다. 1초 후 5개의 LED가 모두 비추고 오른쪽에서 왼쪽으로 하나씩 느리게 꺼집니다. 5초 후에 모든 LED가 꺼져 성공적으로 종료되었음을 나타냅니다.
      
   > [!IMPORTANT]
   > 모든 LED가 꺼진 직후에 단추 누른 채 중지합니다.
1. 종료가 완료되기까지 1분 정도 기다립니다. 디스플레이가 꺼진 후에도 종료가 계속 진행 중일 수 있습니다.
2. 전원 **단추를** 1초 동안 눌러 디바이스를 다시 켭니다.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows 장치 포털 사용하여 안전하게 다시 시작

> [!NOTE]
> 이 프로세스에서는 HoloLens 개발자 디바이스로 구성해야 합니다. 자세한 내용은 [Windows 장치 포털.](/windows/mixed-reality/using-the-windows-device-portal)

이전 절차가 작동하지 않는 경우 [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal)사용하여 디바이스를 다시 시작합니다. 오른쪽 위 모서리에서 디바이스를 다시 시작하거나 종료하는 옵션을 찾습니다.

### <a name="do-an-unsafe-forced-restart"></a>안전하지 않은 강제 다시 시작 수행

이전 메서드가 HoloLens 다시 시작하지 않은 경우 강제로 다시 시작합니다. 이 방법은 배터리를 제거하고 다시 설치하는 것과 같습니다. 디바이스가 손상된 상태로 남겨질 수 있으므로 위험합니다. 이 경우 HoloLens 플래시해야 합니다.  

> [!WARNING]
> 이는 잠재적으로 유해한 방법이며 이전에 언급한 메서드가 작동하지 않는 경우에만 사용해야 합니다.

1. **전원** 단추를 10초 이상 길게 누릅니다.
   - 단추를 10초 넘게 유지해도 괜찮습니다.
   - LED 작업은 무시해도 안전합니다.
1. 단추를 해제하고 2-3초 동안 기다립니다.
1. **전원** 단추를 1초 동안 길게 누릅니다.
1. 여전히 문제가 있는 경우 모든 배터리 표시기가 페이드 아웃되고 화면이 홀로그램 표시를 중지할 때까지 4초 동안 **전원** 단추를 누릅니다. 1분 정도 기다린 다음 **전원** 단추를 다시 눌러 디바이스를 켭니다.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>이전 버전으로 돌아가기 - HoloLens(1세대)

경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아가야 할 수 있습니다. Windows Device Recovery 도구를 사용하여 HoloLens 이전 버전으로 다시 설정하면 됩니다.

> [!NOTE]
> 이전 버전으로 돌아가면 개인 파일 및 설정이 삭제됩니다.

이전 버전의 HoloLens 1로 돌아가려면 다음 단계를 수행합니다.

1. PC에 연결된 휴대폰 또는 Windows 디바이스가 없는지 확인합니다.
1. PC에서 [WDRT(Windows Device Recovery Tool)](https://support.microsoft.com/help/12379)를 다운로드합니다.
1. [HoloLens 1주년 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드합니다.
1. 다운로드가 완료되면 파일 **탐색기**  >  **다운로드를** 엽니다. 방금 다운로드한 압축된 폴더를 마우스 오른쪽 단추로 클릭하고 **압축을** 풀려면 모두  >  **추출을** 선택합니다.
1. 함께 온 마이크로 USB 케이블을 사용하여 PC에 HoloLens 커넥트. (다른 케이블을 사용하여 HoloLens 연결한 경우에도 가장 적합합니다.)
1. WDRT는 HoloLens 자동으로 검색합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 수동 **패키지 선택을** 선택하고 4단계에서 압축을 풀 폴더에 포함된 설치 파일을 선택합니다. (확장이 .ffu인 파일을 찾습니다.)
1. **소프트웨어 설치를** 선택하고 지침을 따릅니다.

> [!NOTE]
> WDRT에서 HoloLens 검색하지 못하면 PC를 다시 시작해 보세요. 그래도 작동하지 않으면 **My device was not detected** 를 선택하고 **Microsoft HoloLens** 를 선택한 후 지침을 따릅니다.

## <a name="reset-to-factory-settings"></a>공장 설정으로 다시 설정

> [!NOTE]
> 배터리를 다시 설정하려면 40% 이상의 충전이 필요합니다.

HoloLens 여전히 문제가 있는 경우 공장 상태로 다시 설정해 보세요. 이 단계에서는 설치된 Windows Holographic 소프트웨어의 버전을 유지하고 다른 모든 것을 공장 설정으로 반환합니다.

>[!WARNING]
> 디바이스를 다시 설정하면 TPM 재설정 정보를 포함하여 모든 개인 데이터, 앱 및 설정이 지워집니다. 다시 설정하면 최신 버전의 Windows Holographic만 설치됩니다. 모든 초기화 단계를 다시 수행해야 합니다(보정, Wi-Fi에 연결, 사용자 계정 만들기, 앱 다운로드 등).

1. 설정 앱을 열고 복구 업데이트를   >  선택합니다.
1. 디바이스 **다시 설정** 옵션을 선택하고 확인 메시지를 읽습니다.
1. 다시 설정을 확인합니다. 디바이스가 다시 시작되고 회전 기어 세트와 진행률 표시줄이 표시됩니다.
1. 이 프로세스가 완료되기까지 약 30분 정도 기다립니다. 완료되면 디바이스가 "바로" 환경으로 다시 시작됩니다.

## <a name="reinstall-the-operating-system"></a>운영 체제 다시 설치

디바이스를 다시 시작하고 다시 시작한 후에도 여전히 문제가 발생하면 컴퓨터의 복구 도구를 사용하여 HoloLens 운영 체제 및 펌웨어를 다시 설치할 수 있습니다.  

HoloLens 다시 설정에 필요한 데이터는 .iso, .wim 또는 .vhd 파일과 유사한 FFU(전체 플래시 업데이트)에 패키지됩니다. [FFU 이미지 파일 형식에 대해 알아봅니다.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows Device Recovery 도구를 사용하여 HoloLens(1세대)에 새 운영 체제를 설치할 수 있습니다. 해당 도구를 사용하기 전에 HoloLens 다시 시작하거나 다시 설정하면 문제가 해결되는지 확인합니다.

복구 프로세스는 시간이 걸릴 수 있습니다. 완료되면 최신 버전의 Windows Holographic 소프트웨어가 설치됩니다.

이 도구를 사용하려면 4GB 이상의 여유 스토리지 공간이 있는 Windows 10 이상을 실행하는 컴퓨터가 필요합니다. 가상 머신에서는 이 도구를 실행할 수 없습니다.

### <a name="recover-your-hololens"></a>HoloLens 복구

1. 컴퓨터에 Windows [Device Recovery 도구를](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 다운로드하여 설치합니다.
1. HoloLens 함께 있는 마이크로 USB 케이블을 사용하여 컴퓨터에 HoloLens(1세대)를 커넥트.
1. Windows Device Recovery 도구를 열고 지침을 따릅니다.

HoloLens(1세대)가 자동으로 검색되지 않으면 **내 디바이스가 검색되지 않음을** 선택합니다. 그런 다음 지침에 따라 디바이스를 복구 모드로 전환합니다.

### <a name="manual-flashing-mode"></a>수동 플래시 모드

디바이스가 검색되지 않으면 다음 단계에 따라 플래시 모드로 전환합니다.

1. 전원에서 디바이스를 분리합니다.
1. 디바이스가 켜진 경우 **전원** 단추가 완전히 꺼질 때까지 누를 수 있습니다.
2. **볼륨 위로** 단추를 누른 상태에서 **전원** 단추를 잠시 누릅니다. 장치가 시작 되 고 중간 LED만 표시 됩니다.
3. 장치를 PC에 연결 합니다.
4. Windows 장치 복구 도구를 엽니다.
5. [ **내 장치]를 검색 하지** 않았습니다 .를 선택 하 고 **HoloLens** 합니다. 
6. 지침에 따라 장치를 복구 합니다.
