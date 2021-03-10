---
title: HoloLens 2 하드웨어
description: Windows 10을 실행하는 최신 홀로그래픽 Microsoft 컴퓨터의 진화된 Microsoft HoloLens 2를 구성하는 구성 요소에 대해 알아보세요.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: feedb0093b8766de75079a61c286c99817ab18f9
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400698"
---
# <a name="hololens-2-hardware"></a>HoloLens 2 하드웨어

![HoloLens 2 측면 보기](images/hololens2-breakdown.png)

Microsoft HoloLens 2는 테더링되지 않은 홀로그램 컴퓨터입니다.  HoloLens(1세대)에 의해 시작된 홀로그램 컴퓨팅 여정을 조정하여 보다 편안하고 몰입감 있는 경험을 혼합 현실에서 협업할 수 있는 더 많은 옵션과 함께 제공합니다.

## <a name="hololens-components"></a>HoloLens 구성 요소

- **바이저**. HoloLens 센서 및 디스플레이를 포함합니다. HoloLens를 착용한 상태에서 바이저를 위로 회전시킬 수 있습니다.
- **헤드밴드**. HoloLens를 착용하려면 조정 휠을 사용하여 헤드밴드를 확장합니다. HoloLens를 장착한 상태에서 헤드밴드가 편안해질 때까지 오른쪽으로 돌려 조정 휠을 조입니다.
- **밝기 단추**. HoloLens를 착용하면 밝기 단추는 템플 근처 바이저 왼쪽에 있습니다.
- **볼륨 단추**. HoloLens를 착용하면 볼륨 단추는 템플 근처 바이저 오른쪽에 있습니다.
- **전원 단추.** HoloLens를 착용하면 전원 단추가 뒤쪽 외부 덮개 오른쪽에 있습니다.
- **USB-C 포트**. HoloLens를 착용하면 USB-C 포트가 전원 단추 아래의 뒤쪽 외부 덮개 오른쪽에 있습니다.

## <a name="in-the-box"></a>상자 안

- **[브로우 패드](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**. 필요에 따라 브로우 패드를 제거하고 교체할 수 있습니다.
- **[오버헤드 스트랩](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)**. 이동 중에 HoloLens를 착용할 때는 오버헤드 스트랩을 사용하여 장치를 제자리에 고정합니다. HoloLens를 장시간 착용할 경우 오버헤드 스트랩이 있어 장치를 착용하기에 더 편할 수 있습니다.
- **[USB-C 충전기 및 케이블](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**. 전원 공급 장치를 전원 콘센트에 연결합니다. USB-C 케이블을 사용하여 HoloLens를 전원 공급 장치에 연결하여 충전하거나 HoloLens를 컴퓨터에 연결합니다.
- **극세사 천**. HoloLens 바이저를 청소할 때 사용합니다.

### <a name="power-supply-details"></a>전원 공급 장치 세부 정보

디바이스와 함께 제공되는 전원 공급 장치와 USB 케이블이 충전을 가장 잘 지원하는 메커니즘입니다. 전원 공급 장치는 18W 충전기입니다.  2A에서 9V를 공급합니다.

충전 속도는 디바이스가 실행되는 환경에 따라 다를 수 있습니다.

디바이스가 켜져 있는 동안 내부 배터리 충전 비율을 유지/향상하려면 최소한 15W 충전기에 연결해야 합니다.

## <a name="device-specifications"></a>디바이스 사양

### <a name="display"></a>표시

|   |   |
| - | - |
| 광학 | 시스루 홀로그램 렌즈(웨이브가이드) |
| 홀로그램 해상도 | 2k 3:2 라이트 엔진 |
| 홀로그램 밀도 | >2.5 k 복사(라디언당 광점) |
| 눈 기반 렌더링 | 3D 눈 위치를 위한 디스플레이 최적화 |

### <a name="sensors"></a>센서

|   |   |
| - | - |
| 머리 추적 | 가시광선 카메라 4대 |
| 시선 추적 | 적외선(IR) 카메라 2대 |
| 깊이 | 1-MP 비행 시간 깊이 센서 |
| IMU(관성 측정 장치) | 가속도계, 자이로스코프, 자력계 |
| 카메라 | 8-MP 스틸, 1080p30 동영상 |

![HoloLens 2 센서](images/hololens2-front-view.png)

> [!NOTE]
> 그림에서 호출된 센서를 덮지 마세요. 머리 추적 카메라는 매우 넓은 FOV를 사용 중입니다. 카메라를 덮지 않을 뿐만 아니라 아무 것도 덮지 말아야 합니다.

### <a name="audio-and-speech"></a>오디오 및 음성

|   |   |
| - | - |
| 마이크 배열 | 5 채널 |
| 스피커 | 기본 제공 공간 음향 |

### <a name="compute-and-connectivity"></a>계산 및 연결

|   |   |
| - | - |
| 칩의 시스템 | Qualcomm Snapdragon 850 계산 플랫폼 [세부 정보](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| 홀로그램 처리 장치 | 2세대 사용자 지정 홀로그램 처리 장치 |
| 메모리 | 4GB LPDDR4x 시스템 DRAM |
| 저장 공간 | 64GB UFS 2.1 |
| WiFi | 802.11 ac 2x2 |
| Bluetooth | 5.0 |
| USB | USB 유형-C |

### <a name="power"></a>전원

|   |   |
| - | - |
| 배터리 사용 시간 | 2~3 시간의 활성 사용. 대기 모드 시간 최대 2주. |
| 배터리 기술 | [리튬 배터리](https://www.microsoft.com/download/details.aspx?id=43388) |
| 충전 동작 | 충전 시 완벽하게 작동 |
| 냉각 종류 | 소극적 냉각(팬 없음) |
| 전력 인출 | 디바이스가 켜져 있는 동안 내부 배터리 충전 비율을 유지/향상하려면 최소한 15W 충전기에 연결해야 합니다. |

### <a name="fit"></a>핏

|   |   |
| - | - |
| 크기 조정 | 조절 가능한 밴드가 있는 단일 사이즈.  안경 위로 핏 |
| 무게 | 566그램 |

## <a name="device-capabilities"></a>장치 접근 권한 값

### <a name="human-understanding"></a>사람 이해

|   |   |
| - | - |
| 손 추적 | 두 손으로 완전히 연결한 모델, 직접 조작 |
| 시선 추적 | 실시간 추적 |
| 음성 | 장치에서 명령 및 제어 인터넷 연결이 가능한 Cortana 자연 언어 |

### <a name="environment-understanding"></a>환경 이해

|   |   |
| - | - |
| 6 자유도(6DoF) 추적 | 세계 규모의 위치 추적 |
| 공간 매핑 | 실시간 환경 메시 |
| 혼합 현실 캡처 | 혼합 홀로그램 및 물리적 환경 사진 및 동영상 |

## <a name="pre-installed-software"></a>사전 설치된 소프트웨어

|   |   |
| - | - |
| Windows 홀로그램 운영 체제 | Windows 10 사용자는 Windows Holographic으로 HoloLens 2를 통해 혼합된 현실 환경에서 일부 앱과 게임을 사용할 수 있습니다.
| 3D 뷰어 | [3D 뷰어](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab)를 사용하면 3D 모델과 애니메이션을 실시간으로 쉽게 볼 수 있습니다.|
| Cortana | 여러분의 개인 생산성 도우미인 [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab)는 중요한 정보를 계속 확인하여 필요한 정보를 찾을 시간을 절약할 수 있습니다.  |
| Dynamics 365 Guides |  [Dynamics 365 Guides](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab)는 직원들이 HoloLens 장치에서 새로운 기술을 더 빨리 배울 수 있도록 지원합니다. |
| Dynamics 365 Remote Assist | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab)는 기술자가 Microsoft Teams 또는 Dynamics 365 Remote Assist를 사용하여 원격 공동 작업을 수행하고 문제를 해결할 수 있도록 지원합니다.  |
| 피드백 허브 | [피드백 허브](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab)를 사용하면 제안 또는 문제를 공유하여 Windows 및 앱에 대한 피드백을 제공할 수 있습니다.  |
| 파일 탐색기 | 파일 탐색기는 파일 시스템에 액세스하기 위한 그래픽 사용자 인터페이스를 제공합니다. |
| 메일 및 일정 | [메일 및 일정](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) 앱은 전자 메일의 최신 정보를 유지하고, 스케줄을 관리하며, 연락처에 있는 사람들과 연락하는 데 도움이 됩니다. |  
| Microsoft Edge | Microsoft Edge는 탐색하는 동안 더 많은 개인 정보 보호, 생산성 및 더 많은 가치를 제공하는 세계적인 성능을 제공합니다. |
| Microsoft Store | HoloLens와 작동하는 앱과 게임을 얻으려면 [Microsoft Store](https://www.microsoft.com)를 방문하세요.|
| 영화 및 TV | [영화 및 TV는](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) 간단하고 빠르며 우아한 하나의 앱으로 최신 엔터테인먼트를 제공합니다. |
| OneDrive | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab)를 통해 어디서나 모든 장치에서 파일에 액세스하고 편집할 수 있습니다.  |
| 사진| [사진](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab)을 사용하면 사진 및 비디오를 보고 편집하고, 영화를 만들고, 앨범을 만들 수 있습니다.  |
| 설정 | 설정 앱은 Windows Holographic의 작동 방식을 자세히 사용자 지정하는 곳입니다.  |
| 팁 | [팁](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab)을 사용하면 Windows Holographic에서 할 수 있는 놀랍고 덜 알려진 작업을 마스터할 수 있습니다. |

## <a name="device-certifications"></a>장치 인증

### <a name="safety"></a>안전

* [제품 안전](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [제품 안전 경고 및 지침](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* 시력 안전: HoloLens 2는 ANSI Z87.1, CSA Z94.3 및 EN 166의 기본 충격 보호 요건을 준수하며 테스트를 완료했습니다.
* [SAR 정보](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>규제 정보
[HoloLens 규제](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): 온도, 처분, 라디오 및 TV 간섭 등에 대한 정보를 포함합니다.

## <a name="warranty-information"></a>보증 정보

Microsoft HoloLens 2에는 표준 제한 [보증](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5)이 제공됩니다. 

구매는[ Microsoft Store 사용 및 판매 약관](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1)이 적용됩니다. 

HoloLens 2를 구매하면 [소프트웨어 사용권 계약](https://www.microsoft.com/Useterms/)에 동의하게 됩니다.

## <a name="package-dimensions"></a>패키지 치수

|      치수               |      미터법     |      야드파운드법     |
|--------------------------------|-----------------------|-------------------------|
|     단위 길이                |     378.97mm          |     14.920인치       |
|     단위 너비                 |     247.90mm          |     9.760인치        |
|     단위 깊이                 |     163.07mm          |     6.420인치        |
|     단위 가중치                |     2.878kg           |     6.344lbs           |
|     외부 포장 길이    |     446.00mm          |     17.559인치       |
|     외부 포장 너비     |     257.99mm          |     10.157인치       |
|     외부 포장 깊이     |     172.01mm          |     6.772인치        |
|     외부 포장 중량    |     3.284kg           |     7.240lbs           |

> [!NOTE]
> - 유닛: 검은색 소매 스타일 상자 HoloLens 2가 판매됩니다.
> - 외부 포장: 장치를 감싼 보호 배송 포장

## <a name="finding-the-serial-number"></a>일련 번호 찾기

HoloLens 2 장치의 일련 번호는 바이저 아래에 적혀 있습니다.

1. 장치의 바이저를 들어 올립니다.
1. 브로우 패드 근처를 살펴보세요.
1. 힌지 근처에 일련 번호를 찾을 수 있을 것입니다.

<img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

일련 번호는 연결된 PC를 통해 찾을 수도 있습니다.

1. 장치 연결
1. 파일 탐색기에서 **이 PC**로 이동
1. 마우스 오른쪽 단추를 클릭한 후 HoloLens 장치의 **속성**을 선택
1. 아래 스크린샷과 같이 장치의 일련 번호가 표시됩니다.

<img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [HoloLens 2 설정 및 시작](hololens2-setup.md)
