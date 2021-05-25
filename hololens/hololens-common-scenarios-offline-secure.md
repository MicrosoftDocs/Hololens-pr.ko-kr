---
title: 일반적인 시나리오 – 오프 라인 보안 HoloLens 2
description: HoloLens 장치를 프로 비전 하 여 오프 라인 보안 배포 및 앱 배포 시나리오를 설정 하는 방법에 대해 알아봅니다.
keywords: HoloLens, 관리, 오프 라인, 오프 라인 보안
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397884"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>일반적인 시나리오 – 오프 라인 보안 HoloLens 2

## <a name="overview"></a>개요

이 가이드에서는 다음 제한 사항을 사용 하 여 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로 비전 패키지를 적용 하기 위한 지침을 제공 합니다.

-   WiFi를 사용 하지 않도록 설정 합니다.
-   BlueTooth를 사용 하지 않도록 설정 합니다.
-   마이크를 사용 하지 않도록 설정 합니다.
-   프로 비전 패키지를 추가 하거나 제거 하지 않습니다.
-   사용자가 위의 제한 된 구성 요소를 사용 하도록 설정할 수 없습니다.

[![오프 라인 보안 시나리오 ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>준비

Windows 10 PC 설치
1. [최신 HoloLens 2 OS 파일](https://aka.ms/hololens2download) 을 PC에 직접 다운로드 합니다. 
   1. 이 구성에 대 한 지원은 빌드 19041.1117 이상에 포함 되어 있습니다.
1. [Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC로 고급 복구 도우미 (ARC) 도구 다운로드/설치
1. Microsoft Store에서 PC로 최신 [WCD (Windows 구성 디자이너)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드 하 여 설치 합니다.
1. [프로젝트 파일을 사용 하 여 OfflineSecureHL2_Sample 폴더를 다운로드](https://aka.ms/HoloLensDocs-SecureOfflineSample) 하 여 ppkg를 빌드합니다.
1. [PPKG 배포를 위한 오프 라인 lob (기간 업무) 응용 프로그램](app-deploy-provisioning-package.md)을 준비 합니다. 


## <a name="configure"></a>구성

보안 구성 프로 비전 패키지 빌드

1. PC에서 WCD 도구를 시작 합니다.
1. **파일 -> 프로젝트 열기를** 선택합니다.
  1. 이전에 저장한 OfflineSecureHL2_Sample 폴더의 위치로 이동하고 다음을 선택합니다OfflineSecureHL2_Sample.icdproj.xml
1. 프로젝트가 열리고 이제 사용 가능한 사용자 지정 목록이 표시됩니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 열린 구성 패키지의 스크린샷](images/offline-secure-sample-wcd.png)

   이 프로비저닝 패키지에 설정된 구성:
   
   |     항목                                                |     설정                       |     설명                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     계정/사용자                                    |     로컬 사용자 이름 & 암호    |     이러한 오프라인 디바이스의 경우 디바이스의 모든 사용자가 단일 사용자 이름 및 암호를 설정하고 공유해야 합니다.          |
   |     첫 번째 환경/HoloLens/ SkipCalibration       |     True                          |     초기 디바이스 설정 중에만 보정을 건너뜁니다.                                                                             |
   |     첫 번째 환경/HoloLens/SkipTraining          |     True                          |     초기 디바이스 설정 중 디바이스 학습을 건너뜁니다.                                                                              |
   |     첫 번째 환경/HoloLens/WiFi                  |     True                          |     초기 디바이스를 설정하는 동안 Wi-Fi 구성을 건너뜁니다.                                                                                 |
   |     Policies/Connectivity/AllowBluetooth                |     아니요                            |     Bluetooth를 사용하지 않도록 설정                                                                                                             |
   |     Policies/Experience/AllowCortana                    |     아니요                            |     Cortana를 사용하지 않도록 설정합니다(마이크가 비활성화되어 잠재적인 문제를 제거하기 위해).                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     예                           |     마이크를 사용하지 않도록 설정                                                                                                            |
   |     정책/개인 정보/전 Appsaccesslocation              |     강제 거부                    |     앱에서 위치 데이터에 액세스 하는 것을 방지 합니다 (위치 추적을 사용 하지 않도록 설정 된 후 잠재적인 문제 제거).    |
   |     정책/개인 정보/전 Appsaccess마이크            |     강제 거부                    |     앱이 마이크에 액세스 하지 못하도록 차단 합니다 (마이크가 사용 하지 않도록 설정 된 경우 잠재적인 문제 제거).           |
   |     정책/보안/AllowAddProvisioningPackage       |     아니요                            |     잠긴 정책을 재정의 하려고 할 수 있는 프로 비전 패키지를 모든 사용자가 추가 하지 못하도록 합니다.                         |
   |     정책/보안/AllowRemoveProvisioningPackage    |     아니요                            |     사용자가이 잠긴 프로 비전 패키지를 제거 하지 못하도록 합니다.                                                           |
   |     정책/시스템/AllowLocation                       |     아니요                            |     장치에서 위치 데이터를 추적 하지 못하도록 합니다.                                                                        |
   |     정책/a p/a s i Wifi                             |     아니요                            |     Wi-Fi 사용 안 함                                                                                                                 |

1. 런타임 설정에서 **계정/사용자/사용자 이름: Holo/Password** 를 선택 합니다.

   암호를 확인 하 고 원하는 경우 다시 설정 합니다.

1. UniversalAppInstall/UserContextApp으로 이동 하 고 이러한 장치에 배포할 [LOB 앱을 구성](app-deploy-provisioning-package.md) 합니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가할 위치의 스크린샷](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 완료 되 면 "내보내기" 단추를 선택 하 고 프로 비전 패키지를 만들 때까지 모든 프롬프트를 따릅니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서이 패키지에 대 한 내보내기 단추의 스크린샷](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>배포

1. USB 케이블을 통해 Windows 10 PC에 HL2를 연결합니다.
1. ARC 도구를 시작하고 **HoloLens 2** 선택합니다.

   ![HoloLens 2 정리 리플래시 초기 화면](images/ARC2.png)

1. 다음 화면에서 **수동 패키지 선택** 를 선택합니다.

   ![ARC 정보 화면 HoloLens 2](images/arc_device_info.png)

1. 이전에 다운로드한 .ffu 파일로 이동하고 **열기를** 선택합니다.
1. 경고 페이지에서 **계속을** 선택합니다.

   ![ARC 경고 화면 HoloLens 2](images/arc_warning.png)

1. ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다립니다.
1. 디바이스가 설치를 완료하고 다시 부팅하면 PC에서 파일 탐색기 이동하여 이전에 저장된 PPKG 파일을 디바이스 폴더에 복사합니다.

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창의 PC에 있는 PPKG 파일입니다.](images/offline-secure-file-explorer.png)

1. HoloLens 2 다음 단추 콤보를 눌러 프로비전 패키지를 실행합니다. **볼륨 다운** 및 **전원 단추를** 동시에 탭합니다.
1. 프로비전 패키지를 적용하라는 메시지가 표시되면 **확인을** 선택합니다.
1. 프로비전 패키지가 완료되면 **확인을** 선택합니다.
1. 그런 다음 공유 로컬 계정 및 암호를 사용하여 디바이스에 로그인하라는 메시지가 표시됩니다.

## <a name="maintain"></a>유지 관리

이 구성을 사용하면 위의 프로세스를 다시 시작하고 ARC 도구를 사용하여 디바이스를 반사하고 새 PPKG를 적용하여 OS 및/또는 애플리케이션을 업데이트하는 것이 좋습니다.
