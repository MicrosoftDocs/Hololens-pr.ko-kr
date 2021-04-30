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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309126"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>일반적인 시나리오 – 오프 라인 보안 HoloLens 2

## <a name="overview"></a>개요

이 가이드에서는 다음 제한 사항을 사용 하 여 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로 비전 패키지를 적용 하기 위한 지침을 제공 합니다.

-   WiFi를 사용 하지 않도록 설정 합니다.
-   BlueTooth를 사용 하지 않도록 설정 합니다.
-   마이크를 사용 하지 않도록 설정 합니다.
-   프로 비전 패키지를 추가 하거나 제거 하지 않습니다.
-   사용자가 위의 제한 된 구성 요소를 사용 하도록 설정할 수 없습니다.

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
1. **파일-> 프로젝트 열기** 를 선택 합니다.
  1. 이전에 저장 된 OfflineSecureHL2_Sample 폴더의 위치로 이동 하 고 다음을 선택 OfflineSecureHL2_Sample.icdproj.xml
1. 프로젝트를 열어야 하며 이제 사용할 수 있는 사용자 지정 목록이 있습니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에 열려 있는 구성 패키지의 스크린샷](images/offline-secure-sample-wcd.png)

   이 프로 비전 패키지에 설정 되는 구성:
   
   |     항목                                                |     설정                       |     Description                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     계정/사용자                                    |     로컬 사용자 이름 & 암호    |     이러한 오프 라인 장치의 경우 장치의 모든 사용자가 단일 사용자 이름 및 암호를 설정 하 고 공유 해야 합니다.          |
   |     첫 번째 경험/HoloLens/SkipCalibration       |     True                          |     초기 장치 설치 중에만 보정을 건너뜁니다.                                                                             |
   |     첫 번째 경험/HoloLens/SkipTraining          |     True                          |     초기 장치를 설정 하는 동안 장치 교육을 건너뜁니다.                                                                              |
   |     첫 번째 경험/HoloLens/WiFi                  |     True                          |     초기 장치를 설정 하는 동안 Wi-Fi 구성을 건너뜁니다.                                                                                 |
   |     정책/연결/o s a Bluetooth                |     No                            |     Bluetooth 사용 안 함                                                                                                             |
   |     정책/환경/o s Cortana                    |     No                            |     Cortana를 사용 하지 않도록 설정 (마이크를 사용 하지 않도록 설정 된 후 발생할 수 있는 문제 제거)                                          |
   |     정책/MixedReality/MicrophoneDisabled            |     Yes                           |     마이크 사용 안 함                                                                                                            |
   |     정책/개인 정보/전 Appsaccesslocation              |     강제 거부                    |     앱에서 위치 데이터에 액세스 하는 것을 방지 합니다 (위치 추적을 사용 하지 않도록 설정 된 후 잠재적인 문제 제거).    |
   |     정책/개인 정보/전 Appsaccess마이크            |     강제 거부                    |     앱이 마이크에 액세스 하지 못하도록 차단 합니다 (마이크가 사용 하지 않도록 설정 된 경우 잠재적인 문제 제거).           |
   |     정책/보안/AllowAddProvisioningPackage       |     No                            |     잠긴 정책을 재정의 하려고 할 수 있는 프로 비전 패키지를 모든 사용자가 추가 하지 못하도록 합니다.                         |
   |     정책/보안/AllowRemoveProvisioningPackage    |     No                            |     사용자가이 잠긴 프로 비전 패키지를 제거 하지 못하도록 합니다.                                                           |
   |     정책/시스템/AllowLocation                       |     No                            |     장치에서 위치 데이터를 추적 하지 못하도록 합니다.                                                                        |
   |     정책/a p/a s i Wifi                             |     No                            |     Wi-Fi 사용 안 함                                                                                                                 |

1. 런타임 설정에서 **계정/사용자/사용자 이름: Holo/Password** 를 선택 합니다.

   암호를 확인 하 고 원하는 경우 다시 설정 합니다.

1. UniversalAppInstall/UserContextApp으로 이동 하 고 이러한 장치에 배포할 [LOB 앱을 구성](app-deploy-provisioning-package.md) 합니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가할 위치의 스크린샷](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 완료 되 면 "내보내기" 단추를 선택 하 고 프로 비전 패키지를 만들 때까지 모든 프롬프트를 따릅니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서이 패키지에 대 한 내보내기 단추의 스크린샷](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>배포

1. USB 케이블을 통해 Windows 10 PC에 HL2를 연결 합니다.
1. 호 도구를 시작 하 고 **HoloLens 2** 를 선택 합니다.

   ![HoloLens 2 clean 경감 하기 위해 초기 화면](images/ARC2.png)

1. 다음 화면에서 **수동 패키지 선택** 을 선택 합니다.

   ![HoloLens 2 호 정보 화면](images/arc_device_info.png)

1. 이전에 다운로드 한 ffu 파일로 이동 하 고 **열기** 를 선택 합니다.
1. 경고 페이지에서 **계속** 을 선택 합니다.

   ![HoloLens 2 호 경고 화면](images/arc_warning.png)

1. ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다립니다.
1. 장치가 설치를 완료 하 고 다시 부팅 되 면 PC에서 파일 탐색기로 이동 하 여 이전에 저장 된 PPKG 파일을 장치 폴더에 복사 합니다.

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창에 있는 PC의 PPKG 파일.](images/offline-secure-file-explorer.png)

1. HoloLens 2에서 프로 비전 패키지를 실행 하려면 다음 단추 콤보를 누릅니다. **볼륨 아래로 이동** 및 **전원 단추** 를 동시에 누릅니다.
1. 프로 비전 패키지를 적용 하 라는 메시지가 표시 되 면 **확인** 을 선택 합니다.
1. 프로 비전 패키지가 완료 되 면 **확인을** 선택 합니다.
1. 그러면 공유 로컬 계정 및 암호를 사용 하 여 장치에 로그인 하 라는 메시지가 표시 됩니다.

## <a name="maintain"></a>유지 관리

이 구성을 사용 하는 경우 위의 프로세스를 다시 시작 하 고 ARC 도구를 사용 하 여 장치를 경감 하기 위해 하 고, OS 및/또는 응용 프로그램에 대 한 업데이트를 수행 하기 위해 새 PPKG를 적용 하는 것이 좋습니다.
