---
title: 일반적인 시나리오 - 오프라인 보안 HoloLens 2
description: HoloLens 장치를 프로비전하여 오프라인 보안 배포 및 앱 배포 시나리오를 설정하는 방법을 설명합니다.
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283419"
---
# 일반적인 시나리오 - 오프라인 보안 HoloLens 2

## 개요

이 가이드에서는 다음과 같은 제한 사항으로 보안 환경에서 사용하기 위해 HoloLens 2를 잠그는 샘플 프로비저닝 패키지를 적용하기 위한 지침을 제공합니다.
-   WiFi를 사용하지 않도록 설정.
-   BlueTooth를 사용하지 않도록 설정합니다.
-   마이크를 사용하지 않도록 설정합니다.
-   프로비저닝 패키지 추가 또는 제거를 방지합니다.
-   어떤 사용자도 위의 제한된 구성 요소를 사용하도록 설정할 수 없습니다.

## 준비

Windows 10 PC 설치
1. [최신 HoloLens 2 OS 파일을 PC에](https://aka.ms/hololens2download) 직접 다운로드합니다. 
   1. 이 구성에 대한 지원은 빌드 19041.1117 이상에 포함되어 있습니다.
1. [Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC로 ARC(Advanced Recovery Companion) 도구 다운로드/설치
1. Microsoft Store에서 PC로 최신 [WCD(Windows 구성 디자이너)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드하여 설치합니다.
1. [프로젝트 OfflineSecureHL2_Sample](https://aka.ms/HoloLensDocs-SecureOfflineSample) 폴더를 다운로드하여 PPKG를 빌드합니다.
1. [PPKG 배포를 위해](app-deploy-provisioning-package.md)오프라인 비즈니스 응용 프로그램을 준비합니다. 


## 구성

보안 구성 프로비저닝 패키지 빌드

1. PC에서 WCD 도구를 실행합니다.
1. 파일 **-> 열기 프로젝트를 선택합니다.**
  1. 이전에 저장한 OfflineSecureHL2_Sample 폴더의 위치로 이동한 후 다음을 OfflineSecureHL2_Sample.icdproj.xml
1. 프로젝트가 열리면 사용 가능한 사용자 지정 목록이 표시됩니다. 

   > [!div class="mx-imgBorder"]
   > ![WCD에서 열 수 있는 구성 패키지 스크린샷](images/offline-secure-sample-wcd.png)

이 프로비저닝 패키지에 설정된 구성:

|     항목                                                |     설정                       |     설명                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     계정/사용자                                    |     로컬 사용자 이름 & 암호    |     이러한 오프라인 장치의 경우 디바이스의 모든 사용자가 단일 사용자 이름 및 암호를 설정하고 공유해야 합니다.          |
|     First Experience / HoloLens / SkipCalibration       |     True                          |     초기 장치 설정 중에만 보정 건너뛰기                                                                             |
|     First Experience / HoloLens / SkipTraining          |     True                          |     초기 장치 설정 중에 장치 교육 건너뛰기                                                                              |
|     First Experience / HoloLens /WiFi                  |     True                          |     초기 Wi-Fi 구성 건너뛰기                                                                                 |
|     정책/연결/AllowBluetooth                |     아니오                            |     비동기 Bluetooth                                                                                                             |
|     정책/환경/AllowCortana                    |     아니오                            |     Cortana를 사용하지 않도록 설정(마이크를 사용하지 않도록 설정한 후 잠재적인 문제를 제거하기 위해)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     예                           |     마이크를 사용하지 않도록 설정                                                                                                            |
|     정책/개인 정보/LetAppsAccessLocation              |     강제 거부                    |     앱이 위치 데이터에 액세스하지 못하게 방지합니다(위치 추적을 사용하지 않도록 설정한 이후의 잠재적인 문제 제거)    |
|     정책/개인 정보/LetAppsAccessMicrophone            |     강제 거부                    |     앱이 마이크에 액세스하지 못하게 방지(마이크를 사용하지 않도록 설정한 경우 잠재적인 문제를 제거하기 위해)           |
|     정책/보안/AllowAddProvisioningPackage       |     아니오                            |     잠긴 정책을 다시 설정하려고 할 수 있는 프로비저닝 패키지를 추가하지 못하게 합니다.                         |
|     정책/보안/AllowRemoveProvisioningPackage    |     아니오                            |     잠긴 이 프로비저닝 패키지를 제거하지 못하게 합니다.                                                           |
|     정책/시스템/AllowLocation                       |     아니오                            |     디바이스가 위치 데이터를 추적하지 못하게 합니다.                                                                        |
|     정책/WiFi/AllowWiFi                             |     아니오                            |     이 기능을 Wi-Fi                                                                                                                 |

4. 런타임 설정에서 **계정/사용자/사용자 이름 선택: Holo /Password** 
    - 암호를 메모하고 원하는 경우 다시 설정하십시오.
5. UniversalAppInstall/UserContextApp으로 이동하여 이러한 장치에 배포할 [LOB](app-deploy-provisioning-package.md) 앱을 구성합니다.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가할 위치의 스크린샷.](images/offline-secure-sample-wcd-usercontextapp.png)

6. 완료되면 "내보내기" 단추를 선택하고 프로비저닝 패키지가 만들어질 때까지 모든 프롬프트를 따르십시오.

   > [!div class="mx-imgBorder"]
   > ![WCD에서 이 패키지의 내보내기 단추 스크린샷.](images/offline-secure-sample-wcd-export.png)


## 배포

1. USB 케이블을 통해 HL2를 Windows 10 PC에 연결합니다.
1. ARC 도구를 시작하고 **HoloLens 2 선택**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. 다음 화면에서 수동 패키지 **선택을 선택합니다.**
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. 이전에 다운로드한 .ffu 파일로 이동한 후 **열기 를 선택합니다.**
1. 경고 페이지에서 계속을 **선택합니다.**

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다렸다가
1. 장치가 설치를 완료하고 백업을 부팅하면 PC에서 파일 탐색기로 이동하여 이전에 저장된 PPKG 파일을 장치 폴더로 복사합니다.

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창의 PC에 있는 PPKG 파일입니다.](images/offline-secure-file-explorer.png)

1. HoloLens 2에서 다음 단추 콤보를 눌러 프로비저닝 패키지를 실행합니다. **볼륨** 감소 및 **전원** 단추를 동시에 탭합니다.
1. 프로비저닝 패키지를 적용하라는 메시지가 표시되면 **확인을 선택합니다.**
1. 프로비저닝 패키지가 완료되면 확인을 **선택합니다.**
1. 그런 다음 공유 로컬 계정 및 암호를 사용하여 장치에 로그인하라는 메시지가 표시됩니다.

## 유지 관리

이 구성에서는 위의 프로세스를 다시 시작하고 ARC 도구를 사용하여 장치를 다시 래시한 다음 OS 및/또는 응용 프로그램을 업데이트하기 위해 새 PPKG를 적용하는 것이 좋습니다. 

