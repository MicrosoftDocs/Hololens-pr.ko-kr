---
title: HoloLens 장치 및 홀로그램에 대한 질문과 대답
description: HoloLens 또는 홀로그램과의 상호 작용하는 방법에 대한 간단한 질문이 있나요?  이 문서에서는 간단한 대답과 추가 리소스를 제공합니다.
keywords: hololens, faq, 알려진 문제, 도움말
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 51cbef57cc3384b7026ae5d0b1ea98fdd942291f
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865577"
---
# HoloLens 장치 및 홀로그램에 대한 질문과 대답

이 문서에서는 홀로그램 배치, 공간을 사용하여 작업하는 방법 등을 포함하는 HoloLens를 사용하는 방법에 대한 몇 가지 질문에 답변합니다.

문제가 있을 때마다 HoloLens가 [충전되어 있는지](https://support.microsoft.com/help/12627/hololens-charge-your-hololens) 확인하세요. [다시 시작](hololens-restart-recover.md)하여 문제가 해결되었는지 확인해 보세요. 피드백 앱을 사용하여 문제에 대한 정보를 보내주세요. [**시작** 메뉴](holographic-home.md)에서 피드백 앱을 찾을 수 있습니다.

HoloLens를 착용하는 방법에 대한 팁은 [HoloLens(1세대) 핏 및 편안함 자주 묻는 질문](hololens1-fit-comfort-faq.md)을 확인하세요.

이 문서에서는 다음 질문과 문제를 다룹니다.
<a id="list"></a>

- [홀로그램이 제대로 보이지 않거나 움직입니다.](#my-holograms-dont-look-right-or-are-moving-around)
- ["공간 찾는 중"이라는 메시지가 표시됩니다.](#i-see-a-message-that-says-finding-your-space)
- [내 공간에서 볼 것으로 예상되는 홀로그램을 볼 수 없습니다.](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [원하는 위치에 홀로그램을 배치할 수 없습니다.](#i-cant-place-holograms-where-i-want-to)
- [홀로그램이 사라지거나 다른 홀로그램이나 개체에서 둘러싸여 있습니다.](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [벽의 반대편에 있는 홀로그램을 볼 수 있습니다.](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [홀로그램을 벽에 놓으면 홀로그램이 떠다니는 것 같습니다.](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [앱을 이동하려고 할 때 앱이 나와 너무 가까이 나타납니다.](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [디스크 공간 부족 오류가 발생합니다.](#im-getting-a-low-disk-space-error)
- [HoloLens가 내 제스처에 응답하지 않습니다.](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens가 내 목소리에 응답하지 않습니다.](#hololens-doesnt-respond-to-my-voice)
- [연결하는 데 문제가 있거나 Bluetooth 장치를 사용하는 데 문제가 있습니다.](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [HoloLens 설정이 사용 가능한 장치를 표시하지만 장치가 작동하지 않습니다.](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [HoloLens clicker를 사용하는 데 문제가 있습니다.](#im-having-problems-using-the-hololens-clicker)
- [Wi-Fi에 연결할 수 없습니다.](#i-cant-connect-to-wi-fi)
- [내 HoloLens가 제대로 실행되지 않거나, 응답하지 않거나, 시작되지 않습니다.](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [이전에 다른 사용자를 위해 설정되었기 때문에 HoloLens 장치에 로그인할 수 없습니다.](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [HoloLens 장치 관리에 대한 질문](#questions-about-managing-hololens-devices)
- [HoloLens 장치 보안에 대한 질문](#questions-about-securing-hololens-devices)
- [모든 공간을 삭제하려면 어떻게 해야 하나요?](#how-do-i-delete-all-spaces)
- [HoloLens 2 에뮬레이터에서 입력하기 위해 키보드를 찾거나 사용할 수 없습니다.](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## 홀로그램이 제대로 보이지 않거나 움직입니다.

홀로그램이 제대로 보이지 않는 경우(예: 떨림 또는 흔들림, 또는 위에 검은색 패치가 보이는 경우) 다음 수정 방법 중 하나를 시도해 보세요.

- [장치 바이저를 청소](hololens1-hardware.md#care-and-cleaning)하고 센서를 차단하는 것이 없는지 확인합니다.
- 직사광선이 많이 비치지 않는, 불이 잘 들어오는 공간에 있는지 확인합니다.
- HoloLens가 더욱 완벽하게 스캔할 수 있도록 돌아다니며 주변을 응시해 보세요.
- 많은 홀로그램를 배치한 경우 일부를 제거해 보세요.

문제가 계속 발생하는 경우에는 보정 앱을 실행해 보세요. 이 앱은 사용자가 홀로그램을 최상의 상태로 볼 수 있도록 HoloLens를 교정합니다. 이 작업을 수행하려면 **설정** > **시스템** > **유틸리티**로 이동합니다. **보정**에서**보정 열기**를 선택합니다.

[목록으로 돌아가기](#list)

## "공간 찾는 중"이라는 메시지가 표시됩니다.

HoloLens가 공간을 학습하거나 로드하는 중에 "공간 찾는 중"이라는 짧은 메시지가 표시될 수 있습니다. 이 메시지가 몇 초 이상 표시되는 경우 시작 메뉴 아래에 "계속 공간을 찾고 있습니다."라는 다른 메시지가 표시됩니다.

이러한 메시지는 HoloLens에서 공간을 매핑하는 데 문제가 있음을 의미합니다. 이 경우 앱은 열 수 있지만 환경에 홀로그램을 배치할 수 없습니다.

이러한 메시지가 자주 표시되는 경우 다음 수정 중 하나 이상을 시도해 보세요.

- 직사광선이 많이 비치지 않는, 불이 잘 들어오는 공간에 있는지 확인합니다.
- 장치 바이저가 깨끗한지 확인합니다. [바이저를 청소하는 방법에 대해 알아보기](hololens1-hardware.md#care-and-cleaning)
- 강력한 Wi-Fi 신호가 있는지 확인합니다. Wi-Fi 신호가 없거나 Wi-Fi 신호가 약한 경우 새 환경을 입력하면 HoloLens에서 공간을 찾을 수 없습니다. **설정** > **네트워크 &amp; 인터넷** > **Wi-Fi**로 이동하여 Wi-Fi 연결을 확인합니다.
- 더 천천히 움직여 보세요.

[목록으로 돌아가기](#list)

## 내 공간에서 볼 것으로 예상되는 홀로그램을 볼 수 없습니다.

배치한 홀로그램이 보이지 않거나 원치 않는 것이 보이는 경우 다음 수정 중 하나 이상을 시도해 보세요.

- 약간의 조명을 켭니다. HoloLens는 불이 잘 들어오는 공간에서 가장 잘 작동합니다.
- **설정** > **시스템** > **홀로그램** > **근처 홀로그램 제거**로 이동하여 필요 없는 홀로그램을 제거합니다. 또는 필요한 경우 **홀로그램 모두 제거**를 선택합니다.

  > [!NOTE]
  > 공간에서 레이아웃이나 조명이 크게 변경되면 장치에서 공간을 식별하고 홀로그램을 표시하는 데 문제가 생길 수 있습니다.

[목록으로 돌아가기](#list)

## 원하는 위치에 홀로그램을 배치할 수 없습니다.

H홀로그램을 배치하는 데 문제가 있는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.

- 홀로그램을 배치하려고 하는 곳에서 1~3미터 사이에 섭니다.
- 검은색 또는 반사 표면에 홀로그램을 배치하지 마세요.
- 직사광선이 많이 비치지 않는, 불이 잘 들어오는 공간에 있는지 확인합니다.
- HoloLens가 주변을 다시 스캔할 수 있도록 방을 걸어 다닙니다. 이미 스캔한 내용을 보려면 에어 탭하여 매핑 망 그래픽을 표시합니다.

[목록으로 돌아가기](#list)

## 홀로그램이 사라지거나 다른 홀로그램이나 개체에서 둘러싸여 있습니다.

홀로그램에 너무 가까이 가면 홀로그램을 복원하려고&mdash;홀로그램이 잠시 사라집니다. 그 곳에서 이동하세요. 또한 여러 홀로그램을 함께 가까이 배치했다면 일부는 사라질 수 있습니다. 몇 개를 제거해 보세요.

홀로그램은 다른 홀로그램 또는 벽 같은 개체로 막히거나 둘러싸일 수 있습니다.  이 경우 다음 수정 중 하나를 수행합니다.

- 홀로그램이 다른 홀로그램으로 둘러싸여 있으면 둘러싸인 홀로그램을 다른 위치로 이동합니다. 이렇게 하려면 **조정**을 선택하고 길게 눌러 위치를 지정합니다.
- 홀로그램이 벽에 둘러싸인 경우 **조정**을 선택하고 홀로그램이 나타날 때까지 벽으로 이동합니다. 길게 누른 다음 홀롤그램을 벽에서 당겨 앞으로 꺼냅니다.
- 제스처를 사용하여 홀로그램을 움직일 수 없는 경우 음성을 사용하여 제거합니다. 홀로그램을 응시하고 "제거"라고 말합니다. 그런 다음 홀로그램을 다시 열고 새 위치에 배치합니다.

[목록으로 돌아가기](#list)

## 벽의 반대편에 있는 홀로그램을 볼 수 있습니다.

벽에 아주 가까이 있거나 HoloLens가 아직 벽면을 스캔하지 않은 경우 다음 방에 있는 홀로그램을 볼 수 있습니다. 벽을 스캔하려면 벽에서 1~3미터 사이에 서서 벽을 응시합니다.

벽 근처의 검은색 또는 반사 개체(예: 검은색 소파 또는 스테인리스 스틸 냉장고)는 HoloLens가 벽을 스캔하려고 할 때 문제가 발생할 수 있습니다. 그러한 개체가 있는 경우에는 벽의 반대쪽을 스캔합니다.

[목록으로 돌아가기](#list)

## 홀로그램을 벽에 놓으면 홀로그램이 떠다니는 것 같습니다.

벽에 배치하는 홀로그램은 일반적으로 벽에서 1인치 정도 떨어져서 표시됩니다. 더 멀리 떨어져서 표시되면 다음 수정 사항 중 하나 이상을 시도해 보세요.

- 벽에 홀로그램을 배치하는 경우 벽에서 1~3미터 사이에 서서 벽을 똑바로 마주합니다.
- 벽을 에어 탭하여 지도 망 그래픽을 표시합니다. 망이 벽에 정렬되는지 확인합니다. 정렬되지 않으면 홀로그램을 제거하고, 벽을 다시 스캔한 다음 다시 시도하세요.
- 문제가 계속되면 보정 앱을 실행합니다. **설정** > **시스템** > **유틸리티**에서 찾을 수 있습니다.

[목록으로 돌아가기](#list)

## 앱을 이동하려고 할 때 앱이 나와 너무 가까이 나타납니다.

HoloLens가 다양한 각도로 영역을 스캔하도록 앱을 배치하는 영역을 걸어 다니고 둘러봅니다. [장치 바이저 청소](hololens1-hardware.md#care-and-cleaning)도 도움이 될 수 있습니다.

[목록으로 돌아가기](#list)

## 디스크 공간 부족 오류가 발생합니다.

다음 중 하나 이상을 수행하여 저장소 공간을 확보합니다.

- 배치한 홀로그램을 제거하거나 앱 내에서 저장된 일부 데이터를 제거합니다. [내 데이터를 찾으려면 어떻게 하나요?](holographic-data.md)
- 사진 앱에서 일부 사진과 비디오를 삭제합니다.
- HoloLens에서 일부 앱을 제거합니다. **모든 앱** 목록에서 제거할 앱을 길게 누른 다음 **제거**를 선택합니다. (앱을 제거하면 앱에서 장치에 저장하는 모든 데이터도 삭제됩니다.)

[목록으로 돌아가기](#list)

## HoloLens가 내 제스처에 응답하지 않습니다.

HoloLens가 제스처를 볼 수 있도록 하려면 제스처 프레임에 손을 두세요. 제스처 프레임은 양쪽으로 몇 피트 정도를 연장합니다. 또한 HoloLens는 몸 앞으로 약 18인치에 손을 유지하면 손을 가장 잘 볼 수 있습니다(정확한 것은 아님). HoloLens가 손을 볼 수 있으면 커서가 점에서 링으로 바뀝니다. [Hololens 2에서 제스처 사용](hololens2-basic-usage.md) 또는 [HoloLens(1세대)에서 제스처 사용](hololens1-basic-usage.md)에 대해 자세히 알아 보세요.

[목록으로 돌아가기](#list)

## HoloLens가 내 목소리에 응답하지 않습니다.

HoloLens(1세대) 및 HoloLens 2에는 음성 인식이 내장되어 있으며 Cortana(온라인 음성 인식)도 지원합니다.

### 기본 제공되는 음성 명령이 작동하지 않습니다.

HoloLens(1세대)에서는 내장 음성 인식을 구성할 수 없습니다. 이 기능은 항상 켜져 있습니다. HoloLens 2에서는 장치를 설정하는 동안 음성 인식과 Cortana를 둘 다 사용하도록 설정할지를 선택할 수 있습니다.

HoloLens 2가 목소리에 응답하지 않는 경우 음성 인식이 설정되었는지 확인합니다. **시작** > **설정** > **개인 정보** > **음성**으로 이동하여 **음성 인식**을 켭니다.

### Cortana 또는 받아쓰기가 작동하지 않습니다.

Cortana 또는 받아쓰기가 목소리에 응답하지 않는 경우 온라인 음성 인식이 설정되었는지 확인합니다. **시작** > **설정** > **개인 정보** > **음성**으로 이동하여 **온라인 음성 인식** 설정을 확인합니다. 

그래도 Cortana가 응답하지 않는 경우 다음 중 하나를 수행하여 Cortana를 사용하도록 설정되어 있는지 확인합니다.

- **모든 앱**에서 **Cortana** > **메뉴** > **노트북** > **설정**을 선택하여 변경합니다.
- HoloLens 2에서는 **음성 설정** 단추를 선택하거나 "음성 설정"이라고 말합니다.

말할 수 있는 내용에 대한 자세한 내용은 [음성으로 HoloLens 사용](hololens-cortana.md)을 참조하세요.

[목록으로 돌아가기](#list)

## 연결하는 데 문제가 있거나 Bluetooth 장치를 사용하는 데 문제가 있습니다.

[Bluetooth 장치를 연결](hololens-connect-devices.md)하는 데 문제가 있는 경우 다음을 시도해 보세요.

- **설정** > **장치**로 이동하여 Bluetooth가 켜져 있는지 확인합니다. 꺼져 있다면 껐다가 다시 켭니다.
- Bluetooth 장치가 완전히 충전되어 있는지 배터리가 최신 상태인지 확인합니다.
- 그래도 연결할 수 없는 경우 [HoloLens를 다시 시작](hololens-recovery.md)합니다.

[목록으로 돌아가기](#list)

## HoloLens 설정이 사용 가능한 장치를 표시하지만 장치가 작동하지 않습니다.

HoloLens는 Bluetooth 오디오 프로필을 지원하지 않습니다. 스피커 및 헤드셋과 같은 Bluetooth 오디오 장치는 HoloLens 설정에서 사용할 수 있음으로 표시되지만 지원되지 않습니다.

Bluetooth 장치를 사용하는 데 문제가 있는 경우 장치를 지원하는지 확인합니다. 지원되는 장치는 다음과 같습니다.

- 영어-언어 QWERTY Bluetooth 키보드(홀로그래픽 키보드를 사용하는 모든 위치에서 사용할 수 있음)
- Bluetooth 마우스
- [HoloLens clicker](hololens1-clicker.md)

다른 Bluetooth HID와 GATT 장치를 HoloLens와 함께 연결할 수 있습니다. 그러나 실제 장치를 사용하려면 Microsoft 스토어에서 해당하는 안내용 앱을 설치해야 할 수 있습니다.

[목록으로 돌아가기](#list)

## HoloLens clicker를 사용하는 데 문제가 있습니다.

[clicker](hololens1-clicker.md)를 사용하여 홀로그램을 선택, 스크롤, 이동, 크기 조정합니다. 개별 앱은 추가 clicker 제스처를 지원할 수 있습니다.

Clicker을 사용하는 데 문제가 있는 경우 clicker가 충전이 되어 있고 HoloLens와 페어링되어 있는지 확인하세요. 배터리가 낮은 경우 표시등이 주황색으로 깜박입니다. Clicker가 페어링되었는지 확인하려면 **설정** > **장치**로 이동하여 해당 위치에 표시되는지 확인합니다. 자세한 내용은 [clicker 페어링](hololens-connect-devices.md#hololens-1st-gen-pair-the-clicker)을 참조하세요.

Clicker가 충전, 페어링되어 있고 계속해서 문제가 발생하는 경우 메인 단추와 페어링 단추를 15초 동안 눌러 다시 설정합니다. 그런 다음 clicker를 HoloLens와 다시 페어링합니다.

Clicker를 재설정해도 도움이 되지 않는 경우에는 [HoloLens clicker 다시 시작 또는 복구](hololens1-clicker.md#restart-or-recover-the-clicker)를 참조하세요.

[목록으로 돌아가기](#list)

## Wi-Fi에 연결할 수 없습니다.

HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음 몇 가지를 시도해 볼 수 있습니다.

- Wi-Fi가 켜져 있는지 확인합니다. 확인하려면 시작 제스처를 사용하여 **설정** > **네트워크 &amp; 인터넷** > **Wi-Fi**를 선택합니다. Wi-Fi가 켜져 있는 경우 끈 다음 다시 켭니다.
- 라우터나 액세스 지점에 가깝게 이동합니다.
- Wi-Fi 라우터를 다시 시작한 다음 [HoloLens를 다시 시작](hololens-recovery.md)합니다. 다시 연결해 보세요.
- 어느 것으로도 해결되지 않으면 라우터에서 최신 펌웨어를 사용 중인지 확인합니다. 이 정보는 제조업체 웹 사이트에서 찾을 수 있습니다.

[목록으로 돌아가기](#list)

## 내 HoloLens가 제대로 실행되지 않거나, 응답하지 않거나, 시작되지 않습니다.

장치가 제대로 작동하지 않으면 [HoloLens 다시 시작, 재설정 또는 복구](hololens-recovery.md)를 참조하세요.

[목록으로 돌아가기](#list)

## 이전에 다른 사용자를 위해 설정되었기 때문에 HoloLens 장치에 로그인할 수 없습니다.

이전에 다른 사용자(고객이나 전 직원)를 위해 장치를 설정했고 장치를 잠금 해제하기 위한 암호가 없는 경우 다음 중 하나를 수행할 수 있습니다.

- Intune MDM(모바일 장치 관리)에 등록된 장치의 경우 Intune을 사용하여 원격으로 장치 [초기화](https://docs.microsoft.com/intune/remote-actions/devices-wipe)를 할 수 있습니다. 그러면 장치가 다시 깜박입니다.  
   > [!IMPORTANT]  
   > 장치를 초기화하는 경우 **등록 상태와 사용자 계정을 유지** 선택 취소해야 합니다.
- MDM 장치가 아닌 장치의 경우 [장치를 **깜박임 모드**로 전환하고 고급 복구 도우미를 사용](hololens-recovery.md#clean-reflash-the-device)하여 장치를 복구할 수 있습니다.

[목록으로 돌아가기](#list)

## HoloLens 장치 관리에 대한 질문

### SCCM(System Center Configuration Manager)를 사용하여 HoloLens 장치를 관리할 수 있나요?

아니요. HoloLens 장치를 관리하려면 MDM 시스템을 사용해야 합니다.

### AD DS(Active Directory 도메인 서비스)를 사용하여 HoloLens 사용자 계정을 관리할 수 있나요?

아니요. HoloLens 장치에 대한 사용자 계정을 관리하려면 AAD(Azure Active Directory)를 사용해야 합니다.

### HoloLens는 ADCS(Automated Data Capture Systems) 자동 등록이 가능한가요?

아니요.

### HoloLens가 Windows 통합 인증에 참여할 수 있나요?

아니요.

### HoloLens는 브랜딩을 지원하나요?

아니요. 그러나 다음 방법 중 하나를 사용하여 이 문제를 해결할 수 있습니다.

- 사용자 지정 앱을 만든 다음 [키오스크 모드를 사용하도록 설정](hololens-kiosk.md)합니다. 사용자 지정 앱에는 브랜딩을 포함할 수 있으며 다른 앱(예: 원격 지원)을 시작할 수 있습니다.  
- AAD에서 모든 사용자 프로필 사진을 회사 로고로 변경합니다. 그러나 일부 시나리오에는 이 방법이 바람직하지 않을 수 있습니다.

### HoloLens(1세대) 및 HoloLens 2는 어떤 로깅 기능을 제안하나요?

로깅은 개발 또는 문제 해결 시나리오에서 캡처할 수 있는 추적 또는 장치가 Microsoft 서버에 보내는 원격 분석으로 제한됩니다.

[목록으로 돌아가기](#list)

## HoloLens 장치 보안에 대한 질문

[HoloLens 2 보안 정보](security-overview.md)를 참조 하세요.
HoloLens 1 Gen 디바이스의 경우 [이 FAQ](hololens1-faq-security.md)를 검토 하세요.

[목록으로 돌아가기](#list)

## 모든 공간을 삭제하려면 어떻게 해야 하나요?

*출시 예정*

[목록으로 돌아가기](#list)

## HoloLens 2 에뮬레이터에서 입력하기 위해 키보드를 찾거나 사용할 수 없습니다.

*출시 예정*

[목록으로 돌아가기](#list)
