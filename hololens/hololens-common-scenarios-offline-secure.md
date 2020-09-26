---
title: 일반적인 시나리오 – 오프 라인 보안 HoloLens 2
description: 프로 비전을 통한 오프 라인 보안 배포 및 앱 배포입니다.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080520"
---
# 일반적인 시나리오 – 오프 라인 보안 HoloLens 2

## 개요
이 가이드에서는 다음 제한 사항으로 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로비저닝 패키지를 적용 하기 위한 지침을 제공 합니다.
-   WiFi를 비활성화 합니다.
-   BlueTooth를 비활성화 합니다.
-   마이크를 비활성화 합니다.
-   배포 패키지를 추가 하거나 제거할 수 없습니다.
-   모든 제한 된 구성 요소를 사용할 수 있는 사용자가 없습니다.

## 준비 
Windows 10 PC 설치
1. [최신 HoloLens 2 OS 파일](https://aka.ms/hololens2download) 을 PC에 직접 다운로드 합니다. 
   1. 이 구성에 대 한 지원은 빌드 19041.1117 이상에 포함 되어 있습니다.
1. [Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC에 고급 복구 도우미 (ARC) 도구 다운로드/설치
1. PC에 Microsoft Store에서 최신 [Windows 구성 디자이너 (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드/설치 합니다.
1. [프로젝트 파일과 함께 OfflineSecureHL2_Sample 폴더를 다운로드](https://aka.ms/HoloLensDocs-SecureOfflineSample) 하 여 ppkg을 빌드합니다.
1. [PPKG 배포에 대 한 오프 라인 비즈니스 응용 프로그램](app-deploy-provisioning-package.md)을 준비 합니다. 


## 구성
보안 구성 프로비저닝 패키지 빌드

1. PC에서 WCD 도구를 실행 합니다.
1. **파일 >를 선택 하 여 프로젝트를 엽니다**.
  1. 이전에 저장 한 OfflineSecureHL2_Sample 폴더의 위치로 이동 하 고 다음을 선택 합니다. OfflineSecureHL2_Sample.icdproj.xml
1. 프로젝트가 열리고 이제 사용 가능한 사용자 지정 목록이 표시 됩니다. 

   > [!div class="mx-imgBorder"]
   > ![WCD에서 연 구성 패키지 스크린샷](images/offline-secure-sample-wcd.png)

이 프로비저닝 패키지에 설정 되는 구성:

|     항목                                                |     설정                       |     설명                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     계정/사용자                                    |     로컬 사용자 이름 & 암호    |     이러한 오프 라인 장치의 경우 모든 장치 사용자가 단일 사용자 이름 및 암호를 설정 하 고 공유 해야 합니다.          |
|     첫 번째 환경/HoloLens/SkipCalibration       |     True                          |     초기 장치를 설정 하는 동안에만 보정 생략                                                                             |
|     첫 번째 환경/HoloLens/SkipTraining 교육          |     True                          |     초기 장치를 설정 하는 동안 디바이스 교육 건너뛰기                                                                              |
|     첫 번째 환경/HoloLens/WiFi                  |     True                          |     초기 장치를 설정 하는 동안 Wi-fi 구성 건너뛰기                                                                                 |
|     정책/연결/AllowBluetooth                |     아니오                            |     Bluetooth 사용 안 함                                                                                                             |
|     정책/경험/o s p s Cortana                    |     아니오                            |     Cortana를 사용 하지 않도록 설정 (마이크를 사용 하지 않도록 설정 된 후 발생할 수 있는 문제 제거)                                          |
|     정책/MixedReality/MicrophoneDisabled            |     예                           |     마이크 사용 안 함                                                                                                            |
|     정책/개인 정보/통합 Appsaccesslocation              |     강제 거부                    |     앱이 위치 데이터에 액세스 하지 못하도록 방지 (위치 추적을 사용 하지 않도록 설정 된 이후 발생할 수 있는 문제 제거)    |
|     정책/개인 정보/통합 Appsaccessmicrophone            |     강제 거부                    |     앱이 마이크에 액세스 하지 못하도록 방지 (마이크를 사용 하지 않도록 설정 된 후 발생할 수 있는 문제 제거)           |
|     정책/보안/AllowAddProvisioningPackage       |     아니오                            |     잠긴 정책을 재정의 하려고 할 수 있는 프로비저닝 패키지를 추가 하는 것을 방지 합니다.                         |
|     정책/보안/AllowRemoveProvisioningPackage    |     아니오                            |     이 잠긴 프로비저닝 패키지를 아무도 제거 하지 못하도록 합니다.                                                           |
|     정책/시스템/AllowLocation                       |     아니오                            |     장치가 위치 데이터를 추적 하려고 하지 않도록 합니다.                                                                        |
|     정책/WiFi/AllowWiFi                             |     아니오                            |     Wi-fi 사용 안 함                                                                                                                 |

4. 런타임 설정에서 **계정/사용자/사용자 이름: Holo/암호** 를 선택 합니다. 
    - 원하는 경우 암호와 재설정을 기록해 둡니다.
5. UniversalAppInstall/UserContextApp으로 이동 하 여 이러한 장치에 배포 하는 [LOB 앱을 구성](app-deploy-provisioning-package.md) 합니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가 하는 위치 스크린샷](images/offline-secure-sample-wcd-usercontextapp.png)

6. 완료 되 면 "내보내기" 단추를 선택 하 고 프로 비전 패키지를 만들 때까지 모든 메시지를 팔 로우 합니다.

   > [!div class="mx-imgBorder"]
   > ![WCD의이 패키지에 대 한 내보내기 단추 스크린샷](images/offline-secure-sample-wcd-export.png)


## 배포
1. USB 케이블을 통해 HL2를 Windows 10 PC에 연결 합니다.
1. 원호 도구를 시작 하 고 **HoloLens 2** 선택

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. 다음 화면에서 **수동 패키지 선택 항목**을 선택 합니다.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. 이전에 다운로드 한 ffu 파일로 이동 하 고 **열기**를 선택 합니다.
1. 경고 페이지에서 **계속**을 선택 합니다.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다립니다.
1. 장치가 설치 및 부팅을 완료 하면 PC에서 파일 탐색기로 이동 하 여 이전에 저장 한 PPKG 파일을 장치 폴더에 복사 합니다.

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창에 있는 PC의 PPKG 파일](images/offline-secure-file-explorer.png)

1. HoloLens 2에서 다음 단추 콤보를 눌러 프로비저닝 패키지를 실행 합니다. **볼륨 작게** 및 **전원 단추** 를 동시에 탭 합니다.
1. 프로비저닝 패키지를 적용 하 라는 메시지가 표시 되 면 **확인** 을 선택 합니다.
1. 프로비저닝 패키지가 완료 되 면 **확인을**선택 합니다.
1. 그런 다음 공유 로컬 계정 및 암호를 사용 하 여 장치에 로그인 하 라는 메시지가 표시 됩니다.

## 유지 관리
이 구성을 사용 하는 경우 위의 프로세스를 다시 시작 하 고 ARC 도구로 장치를 reflash 새 PPKG을 적용 하 여 OS 및/또는 응용 프로그램에 대 한 업데이트를 수행 하는 것이 좋습니다. 

