---
title: HoloLens 디바이스 및 홀로그램에 대한 질문과 대답
description: 홀로그램을 HoloLens 또는 상호 작용하는 것에 대한 빠른 질문이 있나요?  이 문서에서는 빠른 답변과 더 많은 리소스를 제공합니다.
keywords: hololens, faq, known issue, help
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
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664624"
---
# <a name="holograms-and-interactions-troubleshooting"></a>홀로그램스 및 상호 작용 문제 해결

이 문서에서는 홀로그램 배치, 공백 작업 및 홀로그램 관련 문제 보고와 관련된 문제를 해결합니다.

문제가 발생할 때마다 다음을 확인합니다.
- [다시 시작하여](hololens-restart-recover.md) 이 문제를 해결하는지 확인합니다.
- 문제를 해결하기 전에 HoloLens [요금이 청구되는지](hololens2-charging.md) 확인합니다(1시간 이상 청구됨). 


피드백 앱을 사용하여 문제에 대한 정보를 보내주세요. [ **시작** 메뉴](holographic-home.md)에서 피드백 앱을 찾을 수 있습니다. 

HoloLens 착용하는 방법에 대한 팁은 [조정 맞춤을](hololens2-setup.md#adjust-fit)참조하세요.

<a id="list"></a>
- [새 공백을 만들 수 없습니다.](#new-spaces-cant-be-created)
- [공백을 식별하거나 로드할 수 없습니다.](#spaces-cant-be-identified-or-loaded)
- [모든 공백을 삭제할 어떻게 할까요? 있나요?](#how-do-i-delete-all-spaces)
- [홀로그램스 제대로 보이지 않거나 이동하고 있습니다.](#holograms-dont-look-right-or-are-moving-around)
- ["공간 찾기" 메시지](#finding-your-space-message)
- [예상 홀로그램이 내 공간에 표시되지 않습니다.](#expected-holograms-arent-showing-in-my-space)
- [홀로그램을 배치하거나 이전에 배치된 홀로그램을 볼 수 없습니다.](#cant-place-holograms-or-see-previously-placed-holograms)
- [홀로그램스 사라지거나 다른 홀로그램 또는 개체에 얽힌 경우](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [홀로그램스 벽의 다른 쪽에 표시됩니다.](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [홀로그램을 벽 위에 놓은 후 부동으로 보입니다.](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [앱을 이동한 후 앱이 너무 가깝게 표시](#apps-appear-too-close-after-moving-them)
- [불안정하거나 부정확한 홀로그램 관련 문제 보고](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>새 공백을 만들 수 없습니다.

가장 가능성이 높은 문제는 스토리지 공간이 부족하다는 것입니다. [일부 디스크 공간을 확보한](hololens-troubleshooting.md#low-disk-space-error) 다음 다시 시도합니다.

[목록으로 돌아가기](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>공백을 식별하거나 로드할 수 없습니다.

HoloLens 자동으로 있는 공간을 식별하고 로드할 수 없는 경우 다음 요소를 확인합니다.

- Wi-Fi 연결되어 있는지 확인합니다.
- 실내에 충분한 조명이 있는지 확인합니다.
- 주변 환경이 크게 변경되지 않았는지 확인합니다.

또한 시스템 공간 설정 **으로** 가서 공간을 수동으로 로드하거나 공간을 관리할 수도  >    >  **있습니다.**

[목록으로 돌아가기](#list)

## <a name="how-do-i-delete-all-spaces"></a>모든 공백을 삭제할 어떻게 할까요? 있나요?

*제공 예정*

[목록으로 돌아가기](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>홀로그램스 제대로 보이지 않거나 이동하고 있습니다.

홀로그램이 제대로 보이지 않는 경우(예: 지터링 또는 깔끔하거나 그 위에 검은색 패치가 표시되는 경우) 다음 수정 사항 중 하나를 시도합니다.

- [디바이스 바이저를 정리하고 센서를](hololens1-hardware.md#care-and-cleaning) 차단하는 것이 없는지 확인합니다.
- 직접 스로가 많지 않은 조명이 잘 켜진 공간에 있는지 확인합니다.
- HoloLens 좀 더 완벽하게 스캔할 수 있도록 주변을 둘러보고 둘러보세요.
- 홀로그램을 많이 배치한 경우 일부 홀로그램을 제거해 보세요.

여전히 문제가 있는 경우 보정 앱을 실행해 보세요. 이 앱은 홀로그램이 최상의 상태로 유지하도록 HoloLens 보정합니다. 이렇게 하려면 **설정**  >  **시스템**  >  **유틸리티 로** 이동합니다. **보정에서** **보정 열기를** 선택합니다.

[목록으로 돌아가기](#list)

## <a name="finding-your-space-message"></a>"공간 찾기" 메시지

HoloLens 공간을 학습하거나 로드하는 경우 "공간 찾기"라는 간단한 메시지가 표시되었을 수 있습니다. 이 메시지가 몇 초 이상 표시되면 시작 메뉴 "여전히 공간을 찾고 있습니다."라는 다른 메시지가 표시됩니다.

이러한 메시지는 HoloLens 공간을 매핑하는 데 문제가 있음을 의미합니다. 이 경우 앱을 열 수 있지만 사용자 환경에 홀로그램을 배치할 수는 없습니다.

이러한 메시지가 자주 표시되는 경우 다음 수정 사항 중 하나 이상을 시도합니다.

- 직접 스로가 많지 않은 조명이 잘 켜진 공간에 있는지 확인합니다.
- 디바이스 바이저가 정리되어 있는지 확인합니다. [visor를 정리하는 방법을 알아봅니다.](hololens1-hardware.md#care-and-cleaning)
- 강력한 Wi-Fi 신호가 있는지 확인합니다. Wi-Fi 또는 약한 Wi-Fi 신호가 없는 새 환경에 들어가면 HoloLens 공간을 찾을 수 없습니다. 설정   >  **네트워크 &amp; 인터넷**  >  **Wi-Fi로** 가서 Wi-Fi 연결을 확인합니다.
- 더 느리게 이동해 보세요.

[목록으로 돌아가기](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>예상 홀로그램이 내 공간에 표시되지 않습니다.

배치한 홀로그램이 표시되지 않거나 예상하지 못한 내용이 표시되는 경우 다음 수정 사항 중 하나 이상을 시도합니다.

- 일부 조명을 켭니다. HoloLens 조명이 잘 켜진 공간에서 가장 잘 작동합니다.
- 시스템 **설정** 홀로그램스 주변 홀로그램 제거로 이동하면 필요하지 않은  >    >    >  **홀로그램을 제거합니다.** 또는 필요한 경우 **모든 홀로그램 제거를 선택합니다.**

  > [!NOTE]
  > 공간의 레이아웃 또는 조명이 크게 변경되면 디바이스에서 공간을 식별하고 홀로그램을 표시하는 데 문제가 있을 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>홀로그램을 배치하거나 이전에 배치된 홀로그램을 볼 수 없습니다.

HoloLens 공간을 매핑하거나 로드할 수 없는 경우 제한 모드로 들어가고 홀로그램을 배치하거나 배치한 홀로그램을 볼 수 없습니다. 다음은 시도해 보기 위한 몇 가지 사항입니다.

- HoloLens 공간을 보고 매핑할 수 있도록 환경에 충분한 조명이 있는지 확인합니다.
- 홀로그램을 배치하려는 위치에서 1~3미터 사이에 서 있습니다.
- 홀로그램을 검은색 또는 반사 표면에 배치하지 마세요.
- Wi-Fi 네트워크에 연결되어 있는지 확인합니다. Wi-Fi에 연결되지 않은 경우 HoloLens 알려진 공간을 식별하고 로드할 수 없습니다.
- HoloLens 주변을 다시 검색할 수 있도록 방 주변을 둘러 봅니다. 이미 검사된 항목을 보려면 에어 탭을 눌러 매핑 메시 그래픽을 표시합니다.
- 새 공간을 만들어야 하는 경우 Wi-Fi에 연결한 다음, HoloLens 다시 시작합니다.
- 올바른 공간이 활성 상태인지 확인하거나 공간을 수동으로 로드하려면 **설정** 시스템 공간 으로  >    >  이동합니다.
- 올바른 공간이 로드되고 여전히 문제가 있는 경우 공간이 손상될 수 있습니다. 이 문제를 해결하려면 공간을 선택한 다음, **제거를** 선택합니다. 공간을 제거한 후 HoloLens 주변을 매핑하고 새 공간을 만들기 시작합니다.

[목록으로 돌아가기](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>홀로그램스 사라지거나 다른 홀로그램 또는 개체에 얽힌 경우

홀로그램에 너무 가까이 있으면 홀로그램을 복원하기 위해 일시적으로 &mdash; 사라집니다. 홀로그램에서 벗어나기만 하면 됩니다. 또한 여러 홀로그램을 가까이 배치한 경우 일부는 사라질 수 있습니다. 몇 가지를 제거해 보세요.

홀로그램스 다른 홀로그램이나 벽과 같은 개체에 의해 차단되거나 둘러싸일 수도 있습니다. 이 경우 다음 수정 사항 중 하나를 시도합니다.

- 홀로그램이 다른 홀로그램에 얽힌 경우, 캡슐된 홀로그램을 다른 위치로 이동합니다. 이렇게 하려면 **조정을** 선택한 다음, 길게 눌러 위치를 지정합니다.
- 홀로그램이 벽으로 얽힌 경우 **조정을** 선택한 다음, 홀로그램이 나타날 때까지 벽 쪽으로 안내합니다. 길게 누운 다음 홀로그램을 벽 밖으로 끌어와서 내보냅니다.
- 제스처를 사용하여 홀로그램을 이동할 수 없는 경우 음성을 사용하여 제거합니다. 홀로그램을 응시한 다음, "제거"라고 말합니다. 그런 다음 홀로그램을 다시 열고 새 위치에 배치합니다.

[목록으로 돌아가기](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>홀로그램스 벽의 반대쪽에 표시됩니다.

벽과 매우 가깝거나 HoloLens 아직 벽에서 스캔하지 않은 경우 다음 방의 홀로그램을 볼 수 있습니다. 벽면을 스캔하려면 벽에서 1~3미터 사이에 서서 벽면을 응시합니다.

벽 근처에 있는 검은색 또는 반사 개체(예: 검은색 벽면 또는 무해한강 냉동)는 HoloLens 벽 스캔을 시도할 때 문제를 일으킬 수 있습니다. 이러한 개체가 있는 경우 벽의 다른 쪽을 스캔합니다.

[목록으로 돌아가기](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>홀로그램을 벽 위에 놓은 후 부동으로 보입니다.

일반적으로 벽 위에 배치하는 홀로그램은 벽에서 1인치 정도 떨어져 있는 것처럼 보입니다. 더 멀리 있는 것처럼 보이는 경우 다음 수정 사항 중 하나 이상을 시도합니다.

- 홀로그램을 벽 위에 놓으면 벽에서 1~3미터 사이에 서 있고 벽면을 직선으로 쳐다 놓습니다.
- 벽면을 에어 탭하여 매핑 메시 그래픽을 보여줍니다. 메시가 벽과 일치하는지 확인합니다. 그렇지 않으면 홀로그램을 제거하고, 벽의 재검사한 다음, 다시 시도합니다.
- 문제가 지속되면 보정 앱을 실행합니다. **설정** 시스템 유틸리티 에서 찾을 수  >    >  **있습니다.**

[목록으로 돌아가기](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>앱을 이동한 후 앱이 너무 가깝게 표시

HoloLens 다른 각도에서 영역을 검사할 수 있도록 앱을 배치하는 영역을 살펴보고 살펴보십시오. [디바이스 바이저를 정리하는](hololens1-hardware.md#care-and-cleaning) 것도 도움이 될 수 있습니다.

[목록으로 돌아가기](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>불안정하거나 부정확한 홀로그램 관련 문제 보고
 
1. 문제에 대한 [혼합 현실 캡처 비디오를](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 녹화하세요. 이 비디오는 나중에 연결된 파일로 피드백 허브 통해 업로드할 수 있습니다.  
1. 설정 앱 **->** **개인 정보 진단**& 피드백을 통해 전체 원격 분석을 사용하도록 설정하고  ->   **선택적 진단 데이터에서** 토글이 **켜기로** 설정되어 있는지 확인합니다.
1. 최신 Windows [Holographic OS(20H2 이상)로](hololens-release-notes.md#windows-holographic-version-20h2)업데이트하여 최신 홀로그램 크기 조정 및 안정성 수정을 얻습니다. 업데이트한 후 다음을 수행합니다.
    1. 설정 앱 **->** **System** 홀로그램스  ->  **->** 통해 모든 홀로그램스 **제거한 다음, 모든 홀로그램 제거를** 선택하고 새 맵으로 시작합니다.
    1. HoloLens 쓰고 방 주변을 둘러보고 공간의 모든 영역과 표면을 살펴보면서 공간의 새 지도를 만듭니다. 2-3분 동안 이 작업을 수행합니다.
    1. IPD 보정을 수행합니다. 설정   >  **시스템**  >  **유틸리티 로** 이동합니다. **보정에서** **보정 열기를** 선택합니다.
    1. 시나리오를 다시 테스트하고 계속 지속되는지 확인합니다.
1. 업데이트해도 문제가 해결되지 않으면 피드백 허브 [문제를](hololens-feedback.md)제출하세요. 피드백을 채운 **후에는 공유** 단추를 사용하여 지원 담당자에게 문의할 때 전송할 수 있는 공유하기 쉬운 링크를 만들 수 있습니다.

[목록으로 돌아가기](#list)