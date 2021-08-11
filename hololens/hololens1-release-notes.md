---
title: HoloLens 1세대 릴리스 정보
description: 각 새 HoloLens 릴리스의 업데이트에 대해 알아봅니다.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661841"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1세대 릴리스 정보

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens(1세대) 장기 서비스
HoloLens(1세대)가 LTS(장기 서비스) 상태로 들어갔습니다. 향후 업데이트는 HoloLens(1세대)용 Windows 10 Holographic 버전 1809 릴리스를 통해 기능 패리티를 유지하면서 문제 및 보안 수정에 초점을 맞출 예정입니다.

개발자의 경우 HoloLens(1세대) 앱은 OpenXR API를 지원하지 않습니다.  이러한 헤드셋은 Unity 2019 LTS에서 Unity 2019 LTS의 전체 수명 주기 동안 WinRT API 백 엔드를 통해 2022년 중순까지 지원됩니다.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, 버전 1809

> **적용:** HoloLens(1세대)

| 기능 | 세부 정보 |
|---|---|
| **빠른 작업 메뉴** | 앱에 있는 경우 이제 앱을 나가지 않고도 일반적으로 사용되는 시스템 기능에 빠르게 액세스할 수 있는 빠른 작업 메뉴가 열립니다. <br> 키오스크 모드의 빠른 작업 메뉴에 대한 자세한 내용은 [키오스크 모드에서](hololens-kiosk.md) HoloLens 설정을 참조하세요.<br><br> |
| **시작 또는 빠른 작업 메뉴에서 비디오 캡처 중지** | 시작 메뉴 또는 빠른 작업 메뉴에서 비디오 캡처를 시작하면 동일한 위치에서 녹화를 중지할 수 있습니다. (잊지 마세요. 항상 음성 명령을 통해 이 작업을 수행할 수 있습니다.) |
| **Miracast 지원 디바이스에 Project** | Microsoft Display 어댑터를 사용하는 경우 가까운 Surface 디바이스 또는 TV/모니터에 HoloLens 콘텐츠를 Project.  **시작에서** **커넥트** 선택한 다음, 프로젝션할 디바이스를 선택합니다. **참고:** 개발자 모드를 사용하지 않고 Miracast 프로젝션을 사용하도록 HoloLens 배포할 수 있습니다. |
| **새 알림** | PC에서와 마찬가지로 HoloLens 알림 알림을 보고 응답합니다. 응시하여 응답하거나 해제합니다(또는 몰입형 환경인 경우 꽃 제스처 사용). |
| **HoloLens 오버레이**<br>(파일 선택기, 키보드, 대화 상자 등) | 이제 몰입형 앱을 사용할 때 키보드, 대화 상자, 파일 선택기 등의 오버레이가 표시됩니다. |
| **볼륨 변경에 대한 시각적 피드백 오버레이 UI** | HoloLens 볼륨 위로/아래로 단추를 사용하면 볼륨 수준의 시각적 표시가 표시됩니다. |
| **디바이스 부팅을 위한 새 UI** | 시스템이 로드하는 시각적 피드백을 제공하기 위해 부팅 프로세스 중에 로드 표시기가 추가되었습니다. 디바이스를 다시 부팅하여 "Hello" 메시지와 Windows 부팅 로고 사이에 있는 새 로딩 표시기를 확인합니다. |
| **주변 공유** | Windows 주변 공유 환경이 추가되어 주변 Windows 디바이스와 캡처를 공유할 수 있습니다. HoloLens 사진 또는 비디오를 캡처하거나 Microsoft Edge 같은 앱에서 공유 단추를 사용하는 경우 공유할 주변 Windows 디바이스를 선택합니다. |
| **Microsoft Edge 공유** | 이제 HoloLens Microsoft Edge 창에서 공유 단추를 사용할 수 있습니다. Microsoft Edge **공유를** 선택합니다. HoloLens 공유 선택기를 사용하여 웹 콘텐츠를 공유합니다. |

#### <a name="for-international-customers"></a>국제 고객의 경우

| 기능 | 세부 정보 |
| --- | --- |
| 지역화된 중국어 및 일본어 빌드 | 지역화된 Pinyin 키보드, 받아쓰기 및 음성 명령을 포함하여 중국어 또는 일본어 간체에 대해 지역화된 사용자 인터페이스와 함께 HoloLens 사용합니다.<br>[중국어 및 일본어 버전의 HoloLens 설치하는 방법을 알아봅니다.](hololens1-install-localized.md) |
| 음성 합성(TTS) | 음성 합성 기능은 이제 중국어, 일본어 및 영어를 지원합니다. |

#### <a name="for-administrators"></a>관리자용

| 기능 |  세부 정보  |
|---|----|
| [설치 후 프로비저닝 사용](hololens-provisioning.md) | 이제 설정 사용하여 언제든지 런타임 프로비저닝 패키지를 **적용할** 수 있습니다. |
| Azure AD 그룹을 통해 할당된 액세스 권한 | 이제 Azure AD 그룹을 사용하여 Windows 할당된 액세스 권한을 구성하여 단일 또는 다중 앱 키오스크 구성을 설정할 수 있습니다. |
| 로그인 화면에서 프로필 스위치의 PIN 로그인 | **이제 다른 사용자** 에 PIN 로그인을 사용할 수 있습니다. |
| 암호를 사용하여 웹 자격 증명 공급자 로그인 | 이제 Globe 로그인 옵션을 선택하여 암호로 웹 로그인을 시작할 수 있습니다. 로그인 화면에서 **로그인 옵션을** 선택하고 Globe 옵션을 선택하여 웹 로그인을 시작합니다. 필요한 경우 사용자 이름을 입력한 다음 암호를 입력합니다. <br>**참고:** 웹 로그인 중에 메시지가 표시되면 PIN/스마트 카드 옵션을 무시하도록 선택할 수 있습니다. |
| 일련 번호로 디바이스를 추적할 수 있도록 MDM을 통해 디바이스 하드웨어 정보를 읽습니다. | IT 관리자는 MDM 콘솔에서 디바이스 일련 번호로 HoloLens 보고 추적할 수 있습니다. 기능 가용성 및 지침은 MDM 설명서를 참조하세요. |
| MDM을 통해 HoloLens 디바이스 이름 설정(이름 바꾸기) | IT 관리자는 MDM 콘솔에서 HoloLens 디바이스를 보고 이름을 바꿀 수 있습니다. 기능 가용성 및 지침은 MDM 설명서를 참조하세요. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 버전 1803 for Microsoft HoloLens

> **적용:** HoloLens(1세대)

Windows 10 버전 1803은 Windows 10 버전 1607에서 릴리스된 이후 Windows Holographic for Business 첫 번째 기능 업데이트입니다. 이 업데이트에서는 다음과 같은 변경 내용이 도입되었습니다.

- 이전에는 VPN이 디바이스에서 사용 가능한 옵션인지 확인하여 상업용 제품군에 대한 업그레이드 라이선스가 HoloLens 디바이스에 적용되었는지만 확인할 수 있었습니다. 이제 **설정**  >  **System은** 업그레이드 **라이선스가** 적용된 후 Windows Holographic for Business 표시합니다. [Windows Holographic for Business 기능의 잠금을 해제하는 방법을 알아봅니다.](hololens1-upgrade-enterprise.md)

- 파일 탐색기 앱 및 Windows [WDRT(Device Recovery Tool)의](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)디바이스 속성에서 운영 체제 빌드 번호를 볼 수 있습니다.
- 이제 Windows 구성 디자이너 도구의 새 HoloLens **디바이스 프로비전** 마법사를 사용하여 HoloLens 디바이스를 더 쉽게 프로비전할 수 있습니다. 마법사에서 설정 환경 및 네트워크 연결을 구성하고, 개발자 모드를 설정하고, 대량 Azure AD 토큰을 가져올 수 있습니다. [HoloLens 간단한 프로비저닝 마법사를 사용하는 방법을 알아봅니다.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- 프로비전 패키지에서 로컬 계정을 만들 때 암호는 42일마다 더 이상 만료되지 않습니다.

- HoloLens [단일 앱 또는 다중 앱 키오스크로 구성할](hololens-kiosk.md)수 있습니다. 다중 앱 키오스크 모드를 사용하면 지정한 앱만 실행하도록 HoloLens 설정할 수 있으며 사용자가 변경할 수 없습니다.

- MTP(미디어 전송 프로토콜)를 사용하면 USB로 HoloLens 디바이스를 PC에 연결하고 HoloLens PC 간에 파일을 전송할 수 있습니다. 파일 탐색기 앱을 사용하여 HoloLens 내에서 파일을 이동하고 삭제할 수도 있습니다.

- 이전에는 Azure AD(Azure Active Directory) 계정으로 디바이스에 로그인한 후 **설정** 회사 리소스에 대한 액세스 권한을 얻기 위해 회사 액세스 권한을 **추가해야** 했습니다. 이제 Azure AD 계정으로 로그인하면 등록이 자동으로 이루어집니다.

- 로그인하기 전에 암호 필드 아래의 네트워크 아이콘을 선택하여 연결할 다른 Wi-Fi 네트워크를 선택할 수 있습니다. 호텔, 회의 센터 또는 비즈니스와 같은 게스트 네트워크에 연결할 수도 있습니다.

- 이제 Azure AD 계정을 사용하여 [여러 사람과 HoloLens](hololens-multiple-users.md) 쉽게 공유할 수 있습니다.

- 설치 또는 로그인이 실패하면 새 **정보 수집** 옵션을 선택하여 문제 해결을 위한 진단 로그를 얻습니다.

- 개별 사용자는 MDM(모바일 디바이스 관리)에 디바이스를 등록하지 않고도 회사 메일을 동기화할 수 있습니다. Microsoft 계정으로 디바이스를 사용하고, 메일 앱을 다운로드 및 설치하고, 메일 계정을 직접 추가할 수 있습니다.

- **설정** 계정 액세스 직장 또는 학교 정보 에서 디바이스에 대한 MDM 동기화 상태를 확인할 수  >    >    >  있습니다. 디바이스 동기화 상태 섹션에서 **동기화를** 시작하고, MDM에서 관리하는 영역을 확인하고, 고급 진단 보고서를 만들고 내보낼 수 있습니다.
