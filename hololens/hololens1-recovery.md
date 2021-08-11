---
title: 다시 시작, 다시 설정 또는 복구 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows 장치 복구 도구를 사용 하 여 이미지를 HoloLens 첫 번째 Gen으로 플래시 하는 방법입니다.
keywords: 방법, 재부팅, 다시 설정, 복구, 하드 리셋, 소프트 리셋, 전원 주기, HoloLens, 종료, wdrt, windows 장치 복구 도구
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
ms.openlocfilehash: d6eb706c50e97a81910180c70be1d9dbc52bc6603cbc77ad130c1dd3b6a9010e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661812"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>다시 시작, 다시 설정 또는 복구 HoloLens (첫 번째 Gen)

HoloLens에 문제가 발생 하는 경우 다시 시작 하거나 다시 설정 하거나 장치 복구를 사용 하 여 장치를 경감 하기 위해 할 수 있습니다. 이 문서에서는 권장 되는 복구 단계를 순서 대로 안내 합니다.

HoloLens 2를 복구 하려는 경우 해당 프로세스가 서로 다르므로 [HoloLens 2 복구](hololens-recovery.md)를 참조 하세요.

> [!NOTE]
> 이 문서에서는 HoloLens 장치 및 소프트웨어에 대해 집중적으로 설명 합니다. holograms 적절 하지 않은 경우 홀로그램 품질을 개선 하는 요소에 대 한 자세한 내용은 **[HoloLens 환경 고려 사항](hololens-environment-considerations.md)** 을 참조 하세요.

## <a name="restart"></a>재시작

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana를 사용 하 여 안전 하 게 다시 시작

HoloLens를 다시 시작 하는 가장 안전한 방법은 Cortana를 사용 하는 것입니다 .이는 일반적으로 HoloLens 문제가 발생 했을 때 가장 먼저 시도할 수 있는 작업입니다.

> [!NOTE] 
> Cortana는 모든 장치에서 사용할 수 없습니다.
> - Cortana는 모든 HoloLens (첫 번째 Gen) 장치에서 사용할 수 있습니다. 
> - Cortana Windows Holograpic 버전 2004 업데이트 이전의 빌드 HoloLens 2 장치에서 사용할 수 있습니다.

1. HoloLens를 켭니다.
1. 사용자가 로그인 되어 있고 장치에서 잠금을 해제 하기 위해 대기 하 고 있지 않은지 확인 합니다.
2. "안녕하세요 Cortana, 재부팅" 또는 "안녕하세요 Cortana, restart." 라고 표시 됩니다.
3. Cortana 응답 하 고 확인 메시지를 표시 합니다. 사운드가 질문 후에 재생 될 때까지 기다렸다가 "예"를 클릭 합니다. 장치가 다시 시작 됩니다.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>전원 단추를 사용 하 여 안전 하 게 다시 시작

그래도 장치를 다시 시작할 수 없는 경우에는 **전원** 단추를 사용 하 여 다시 시작 해 보세요.

1. 5 초 동안 **전원** 단추를 길게 누릅니다. 1 초 후에는 5 개의 Led가 모두 켜 지 며, 오른쪽에서 왼쪽으로 하나씩 천천히 켜 집니다. 5 초 후에 모든 Led가 꺼지고 성공적으로 종료 되었음을 나타냅니다.
      
   > [!IMPORTANT]
   > 모든 Led가 꺼진 직후에 단추 누르기를 중지 합니다.
1. 종료가 완료 될 때까지 1 분 기다립니다. 표시 기능이 해제 된 후에도 종료는 계속 진행 중일 수 있습니다.
2. **전원** 단추를 1 초 동안 누르고 있으면 장치를 다시 켭니다.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows 장치 포털을 사용 하 여 안전 하 게 다시 시작

> [!NOTE]
> 이 프로세스의 경우 HoloLens를 개발자 장치로 구성 해야 합니다. [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal)에서 자세히 알아보세요.

이전 절차가 작동 하지 않는 경우 [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal)을 사용 하 여 장치를 다시 시작 합니다. 오른쪽 위 모서리에서 장치를 다시 시작 하거나 종료 하는 옵션을 찾습니다.

### <a name="do-an-unsafe-forced-restart"></a>안전 하 게 강제 다시 시작 수행

이전 방법으로 HoloLens를 다시 시작 하지 않은 경우 강제로 다시 시작 합니다. 이 방법은 배터리를 제거 하 고 다시 설치 하는 것과 같습니다. 장치가 손상 된 상태로 남을 수 있으므로 위험 합니다. 이런 경우에는 HoloLens을 플래시 해야 합니다.  

> [!WARNING]
> 이는 잠재적으로 유해한 방법 이며 이전에 언급 한 메서드가 작동 하지 않은 경우에만 사용 해야 합니다.

1. 최소 10 초 동안 **전원** 단추를 길게 누릅니다.
   - 단추를 10 초 이상 길게 유지 해도 됩니다.
   - 모든 LED 작업을 무시 하는 것이 안전 합니다.
1. 단추를 눌렀다가 2-3 초 동안 기다립니다.
1. 1 초 동안 **전원** 단추를 길게 누릅니다.
1. 문제가 여전히 발생 하는 경우 모든 배터리 표시기가 페이드 아웃 되 고 화면이 holograms 표시를 중지 하기 전까지 4 초간 **전원** 단추를 누릅니다. 1 분 정도 기다린 다음 **전원** 단추를 다시 눌러 장치를 켭니다.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>이전 버전으로 돌아가기-HoloLens (첫 번째 Gen)

경우에 따라 HoloLens 소프트웨어의 이전 버전으로 돌아갈 수 있습니다. Windows 장치 복구 도구를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> 이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.

이전 버전의 HoloLens 1로 돌아가려면 다음 단계를 수행 합니다.

1. 휴대폰 또는 Windows 장치가 PC에 연결 되어 있지 않은지 확인 합니다.
1. PC에서 [wdrt (Windows 장치 복구 도구)](https://support.microsoft.com/help/12379)를 다운로드 합니다.
1. [HoloLens 1주년 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드합니다.
1. 다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드** 를 엽니다. 방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 고 **압축 풀기**  >  를 선택 하 여 압축을 **풉니다** .
1. 제공 된 마이크로 USB 케이블을 사용 하 여 PC에 HoloLens를 커넥트 합니다. HoloLens 연결 하는 데 다른 케이블을 사용한 경우에도이 방법이 가장 잘 작동 합니다.
1. WDRT는 HoloLens를 자동으로 검색 합니다. **Microsoft HoloLens** 타일을 선택합니다.
1. 다음 화면에서 **수동 패키지 선택** 을 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다. (.Ffu 확장명을 가진 파일을 찾습니다.)
1. **소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.

> [!NOTE]
> wdrt가 HoloLens를 검색 하지 않으면 PC를 다시 시작 해 보세요. 그래도 작동하지 않으면 **My device was not detected** 를 선택하고 **Microsoft HoloLens** 를 선택한 후 지침을 따릅니다.

## <a name="reset-to-factory-settings"></a>공장 설정으로 다시 설정

> [!NOTE]
> 배터리를 다시 설정 하려면 적어도 40% 요금이 청구 되어야 합니다.

HoloLens에 여전히 문제가 있는 경우 공장 상태로 다시 설정 해 보세요. 이 단계에서는 설치 된 Windows Holographic 소프트웨어의 버전을 유지 하 고 다른 모든 항목을 공장 설정으로 반환 합니다.

>[!WARNING]
> 장치를 다시 설정 하는 경우 TPM 다시 설정 정보를 포함 하 여 모든 개인 데이터, 앱 및 설정이 지워집니다. 다시 설정 하면 Windows Holographic의 최신 설치 버전만 설치 됩니다. 모든 초기화 단계 (보정, Wi-fi에 연결, 사용자 계정 만들기, 앱 다운로드 등)를 다시 실행 해야 합니다.

1. 설정 앱을 열고 **업데이트**  >  **복구** 를 선택 합니다.
1. **장치 다시 설정** 옵션을 선택 하 고 확인 메시지를 읽습니다.
1. 다시 설정을 확인 합니다. 장치가 다시 시작 되 고 회전 하는 기어 집합과 진행률 표시줄이 표시 됩니다.
1. 이 프로세스가 완료 될 때까지 30 분 정도 기다립니다. 완료 되 면 장치가 "기본 제공" 환경으로 다시 시작 됩니다.

## <a name="reinstall-the-operating-system"></a>운영 체제 다시 설치

다시 시작 하 고 다시 설정한 후에도 장치에 문제가 발생 하는 경우 컴퓨터의 복구 도구를 사용 하 여 HoloLens 운영 체제 및 펌웨어를 다시 설치할 수 있습니다.  

다시 설정 하는 데 필요한 HoloLens 데이터는 .iso, .wim 또는 .vhd 파일과 유사 하 게 전체 플래시 업데이트 (ffu)로 패키지 됩니다. [FFU 이미지 파일 형식에 대해 알아봅니다.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows 장치 복구 도구를 사용 하 여 HoloLens (첫 번째 gen)에 새 운영 체제를 설치할 수 있습니다. 해당 도구를 사용 하기 전에 HoloLens 다시 시작 하거나 다시 설정 하면 문제가 해결 되는지 확인 합니다.

복구 프로세스는 다소 시간이 걸릴 수 있습니다. 완료 되 면 Windows Holographic 소프트웨어의 최신 버전이 설치 됩니다.

이 도구를 사용 하려면 적어도 4gb의 사용 가능한 저장소 공간이 있는 Windows 10 이상을 실행 하는 컴퓨터가 필요 합니다. 가상 머신에서는이 도구를 실행할 수 없습니다.

### <a name="recover-your-hololens"></a>HoloLens 복구

1. 컴퓨터에 [Windows 장치 복구 도구](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 를 다운로드 하 여 설치 합니다.
1. HoloLens와 함께 제공 되는 마이크로 USB 케이블을 사용 하 여 컴퓨터에 HoloLens (첫 번째 gen)를 커넥트 합니다.
1. Windows 장치 복구 도구를 열고 지침을 따릅니다.

HoloLens (첫 번째 gen)가 자동으로 검색 되지 않는 경우 **내 장치를 검색 하지 못했습니다**.를 선택 합니다. 그런 다음 지침에 따라 장치를 복구 모드로 전환 합니다.

### <a name="manual-flashing-mode"></a>수동 깜박임 모드

장치가 검색 되지 않은 경우 다음 단계에 따라 플래시 모드로 전환 합니다.

1. 전원에서 장치를 분리 합니다.
1. 장치가 켜져 있으면 완전히 꺼질 때까지 **전원** 단추를 누릅니다.
2. 볼륨 **위로** 단추를 누르고 **전원** 단추를 잠깐 탭합니다. 디바이스가 시작되고 중간 LED만 표시되어야 합니다.
3. 디바이스를 PC에 연결합니다.
4. Windows Device Recovery 도구를 엽니다.
5. **내 디바이스가 검색되지 않음을** 선택한 다음, **를 HoloLens.** 
6. 지침에 따라 디바이스를 복구합니다.
