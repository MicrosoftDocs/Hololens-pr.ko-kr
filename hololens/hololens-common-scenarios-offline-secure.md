---
title: 일반적인 시나리오 – 오프라인 보안 HoloLens 2
description: HoloLens 디바이스에 대한 프로비저닝을 사용하여 오프라인 보안 배포 및 앱 배포 시나리오를 설정하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 오프라인, 오프라인 보안
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
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189123"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>일반적인 시나리오 – 오프라인 보안 HoloLens 2

## <a name="overview"></a>개요

이 가이드에서는 다음과 같은 제한 사항으로 보안 환경에서 사용하기 위해 HoloLens 2 잠그는 샘플 프로비전 패키지를 적용하기 위한 지침을 제공합니다.

-   WiFi를 사용하지 않도록 설정합니다.
-   BlueTooth를 사용하지 않도록 설정합니다.
-   마이크를 사용하지 않도록 설정합니다.
-   프로비전 패키지를 추가하거나 제거할 수 없게 합니다.
-   어떤 사용자도 위의 제한된 구성 요소를 사용하도록 설정할 수 없습니다.

[![오프라인 보안 시나리오. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>준비

Windows 10 PC 설치
1. [최신 HoloLens 2 OS 파일을](https://aka.ms/hololens2download) PC에 직접 다운로드합니다. 
   1. 이 구성에 대한 지원은 빌드 19041.1117 이상에 포함되어 있습니다.
1. [MICROSOFT STORE](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ARC(Advanced Recovery Companion) 도구를 다운로드/설치합니다.
1. Microsoft Store PC로 최신 [Windows 구성 디자이너(WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드/설치합니다.
1. [프로젝트 파일이 있는 OfflineSecureHL2_Sample 폴더를 다운로드하여](https://aka.ms/HoloLensDocs-SecureOfflineSample) PPKG를 빌드합니다.
1. [PPKG 배포를 위해 오프라인 사업장 애플리케이션을](app-deploy-provisioning-package.md)준비합니다. 


## <a name="configure"></a>구성

보안 구성 프로비저닝 패키지 빌드

1. PC에서 WCD 도구를 시작합니다.
1. **파일 -> 프로젝트 열기를** 선택합니다.
  1. 이전에 저장한 OfflineSecureHL2_Sample 폴더의 위치로 이동하고 다음을 선택합니다OfflineSecureHL2_Sample.icdproj.xml
1. 프로젝트가 열리고 이제 사용 가능한 사용자 지정 목록이 표시됩니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 열린 구성 패키지의 스크린샷.](images/offline-secure-sample-wcd.png)

   이 프로비저닝 패키지에 설정된 구성:
   
   |     항목                                                |     설정                       |     설명                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     계정/사용자                                    |     로컬 사용자 이름 & 암호    |     이러한 오프라인 디바이스의 경우 디바이스의 모든 사용자가 단일 사용자 이름 및 암호를 설정하고 공유해야 합니다.          |
   |     첫 번째 환경/HoloLens/SkipCalibration       |     True                          |     초기 디바이스 설정 중에만 보정을 건너뜁니다.                                                                             |
   |     첫 번째 환경/HoloLens/SkipTraining          |     True                          |     초기 디바이스 설정 중 디바이스 학습을 건너뜁니다.                                                                              |
   |     첫 번째 환경/HoloLens/WiFi                  |     True                          |     초기 디바이스를 설정하는 동안 Wi-Fi 구성을 건너뜁니다.                                                                                 |
   |     Policies/Connectivity/AllowBluetooth                |     No                            |     Bluetooth 사용하지 않도록 설정                                                                                                             |
   |     Policies/Experience/AllowCortana                    |     No                            |     Cortana 사용하지 않도록 설정합니다(마이크가 비활성화되어 잠재적인 문제를 제거하기 위해).                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Yes                           |     마이크를 사용하지 않도록 설정                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     강제 거부                    |     앱이 위치 데이터에 액세스하지 못하도록 차단합니다(위치 추적을 사용하지 않도록 설정되었기 때문에 잠재적인 문제를 제거하기 위해).    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     강제 거부                    |     앱이 마이크에 액세스하지 못하도록 차단합니다(마이크가 비활성화되어 잠재적인 문제를 제거하기 위해).           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     잠긴 정책을 재정의하려고 할 수 있는 프로비저닝 패키지를 추가하지 못하도록 합니다.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     이 잠긴 프로비저닝 패키지를 제거할 수 없습니다.                                                           |
   |     Policies/System/AllowLocation                       |     No                            |     디바이스가 위치 데이터를 추적하지 못하도록 합니다.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     No                            |     Wi-Fi 사용하지 않도록 설정                                                                                                                 |

1. 런타임 설정 **계정/사용자/사용자 이름: Holo/암호를** 선택합니다.

   암호를 적어두고 원하는 경우 다시 설정합니다.

1. UniversalAppInstall / UserContextApp으로 이동하여 이러한 디바이스에 배포할 [LOB 앱을 구성합니다.](app-deploy-provisioning-package.md)

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가할 위치의 스크린샷.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 완료되면 "내보내기" 단추를 선택하고 프로비전 패키지가 만들어질 때까지 모든 프롬프트를 따릅니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 이 패키지에 대한 내보내기 단추의 스크린샷.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>배포

1. USB 케이블을 통해 Windows 10 PC에 HL2를 커넥트.
1. ARC 도구를 시작하고 **HoloLens 2** 선택합니다.

   ![초기 화면을 HoloLens 2 정리합니다.](images/ARC2.png)

1. 다음 화면에서 **수동 패키지 선택을** 선택합니다.

   ![HoloLens 2 ARC 정보 화면.](images/arc_device_info.png)

1. 이전에 다운로드한 .ffu 파일로 이동하고 **열기를** 선택합니다.
1. 경고 페이지에서 **계속을** 선택합니다.

   ![HoloLens 2 ARC 경고 화면.](images/arc_warning.png)

1. ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다립니다.
1. 디바이스가 설치를 완료하고 백업을 부팅하면 PC에서 파일 탐색기 이동하여 이전에 저장된 PPKG 파일을 디바이스 폴더에 복사합니다.

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창의 PC에 있는 PPKG 파일입니다.](images/offline-secure-file-explorer.png)

1. HoloLens 2 다음 단추 콤보를 눌러 프로비전 패키지를 실행합니다. **볼륨 다운** 및 **전원 단추를** 동시에 탭합니다.
1. 프로비전 패키지를 적용하라는 메시지가 표시되면 **확인을** 선택합니다.
1. 프로비전 패키지가 완료되면 **확인을** 선택합니다.
1. 그런 다음 공유 로컬 계정 및 암호를 사용하여 디바이스에 로그인하라는 메시지가 표시됩니다.

## <a name="maintain"></a>유지 관리

이 구성을 사용하면 위의 프로세스를 다시 시작하고 ARC 도구를 사용하여 디바이스를 반사하고 새 PPKG를 적용하여 OS 및/또는 애플리케이션을 업데이트하는 것이 좋습니다.
