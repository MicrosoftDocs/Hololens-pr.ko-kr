---
title: HoloLens 2 설정
description: 이 가이드는 처음 설정하는 과정을 안내합니다.  Wi-Fi 네트워크와 Microsoft(MSA) 또는 AAD(Azure Active Directory) 계정이 필요합니다.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a0ba32e3caff7695cd284ee3752bb91d80da2194
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903244"
---
# HoloLens 2 설정

HoloLens를 처음 켜면 장치 설정, 사용자 계정으로 로그인, 눈에 맞춰 HoloLens 보정 방법을 안내합니다.  이 섹션에서는 HoloLens 2 초기 설정 환경에 대해 살펴봅니다.

다음 섹션에서는 HoloLens와 작업하고 홀로그램과 상호 작용하는 방법에 대해 알아봅니다. 해당 문서 건너뛰려면 [HoloLens 2 시작](hololens2-basic-usage.md)을 참조하세요.

## 시작하기 전에

시작하려면 먼저 다음 항목이 준비되어 있는지 확인해야 합니다.

**네트워크 연결**. 설정하려면 HoloLens를 네트워크에 연결해야 합니다. HoloLens 2를 사용하면 Wi-Fi에 연결하거나 이더넷을 사용하여 연결할 수 있습니다(USB-C-이더넷 어댑터 필요). 처음 연결할 때 웹 사이트로 이동하거나 인증서를 사용하여 연결할 필요가 없는 열려 있거나 암호로 보호된 네트워크가 필요합니다. [HoloLens에서 사용하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).

**Microsoft 계정**. 또한 Microsoft 계정(또는 조직에서 장치를 소유한 경우, 회사 계정)을 사용하여 HoloLens에 로그인해야 합니다. Microsoft 계정이 아직 없으면 [account.microsoft.com](https://account.microsoft.com)으로 이동하여 무료로 계정을 생성합니다.

**넘어질 위험이 없는 안전하고 밝은 공간**. [상태 및 보안 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661).

HoloLens와 함께 제공되어 가장 편안한 착용감을 제공하는 **옵션 편의 액세서리**. [핏 및 편안함에 대해 자세히 알아보기](hololens2-setup.md#adjust-fit).

## Windows 설정

HoloLens 2를 처음 시작할 때 첫 번째 작업은 Windows Holographic을 설정하는 것입니다.  HoloLens를 시작 하면 음악을 들을 수 있고 Windows 로고가 표시 됩니다.

![처음 부팅 중 첫 번째 화면](images/01-magic-moment.png)

HoloLens 2는 다음 단계를 안내 합니다.

1. 언어를 선택합니다.
    ![언어 선택](images/04-language.png)

1. 지역을 선택합니다.
    ![지역 선택](images/05-region.png)

1. 눈에 맞춰 HoloLens를 보정할 수 있습니다.  보정을 건너뛰도록 선택하면 다음에 로그인할 때 메시지가 표시됩니다.

    보정하려면 대상의 집합(보석이라고 함)을 볼 수 있습니다. 보정을 하는 동안 눈을 깜빡이거나 눈을 감아도 괜찮지만 방에 있는 다른 물체를 응시하지 않도록 합니다. HoloLens는 이 프로세스를 사용하여 홀로그램 세계를 렌더링하기 위해 눈 위치를 학습할 수 있습니다. 보정이 완료되면 바이저가 머리 위에서 움직여도 홀로그램이 올바르게 나타납니다.

    보정 정보는 장치에 로컬로 저장되며 계정 정보와 연결되지 않습니다. 자세한 내용은 [보정 데이터 및 보안](hololens-calibration.md#calibration-data-and-security)을 참조 하세요.

    ![보정 선택 화면](images/06-et-corners.png)

1. 인터넷에 연결합니다(Wi-Fi 또는 이더넷 연결 선택).
     HoloLens는 Wi-Fi 네트워크에서 얻은 정보에 따라 자동으로 표준 시간대를 설정 합니다. 설치가 완료되면 설정 앱을 사용하여 표준 시간대를 변경할 수 있습니다.

    ![Wi-Fi에 연결](images/11-network.png)
> [!NOTE] 
> 2019년 10월 이후 OS 버전을 실행하는 경우 Wi-Fi 단계를 완료한 후에도 설치 중에 다른 네트워크로 전환해야 하는 경우에는 **볼륨 작게** 및 **전원** 단추를 동시에 눌러 이 단계로 돌아올 수 있습니다. 이전 버전의 경우 [디바이스를 초기화](hololens-recovery.md)하거나 Wi-Fi 네트워크를 사용할 수 없는 위치에서 다시 시작하여 자동으로 연결되지 않도록 해야 할 수 있습니다.
> 
> 또한 HoloLens 설정 중에 2분의 자격 증명 제한 시간이 있습니다. 사용자 이름/암호를 2분 이내에 입력해야 합니다. 그렇지 않으면 사용자 이름 필드가 자동으로 지워집니다.

1. 사용자 계정에 로그인합니다. **회사 또는 학교 소유** 또는 **내 소유** 중에서 선택합니다.
    - **회사 또는 학교 소유**를 선택하면 Azure AD 계정을 사용하여 로그인합니다. 조직에서 Azure AD Premium을 사용하고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록됩니다. 조직에서 Azure AD Premium을 사용 하지 않는 경우 자동 MDM 등록을 사용할 수 없습니다. 이 경우 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#different-ways-to-enroll)해야 합니다.
        1. 조직 계정 정보를 입력합니다.
        1. 개인정보처리방침 및 최종 사용자 라이선스 계약에 동의합니다.
        1. Azure AD 자격 증명을 사용하여 로그인합니다. 조직의 로그인 페이지로 다시 이동하게 될 수 있습니다.
        1. 장치 설정을 계속합니다.
    - **내 소유**를 선택하면 Microsoft 계정으로 로그인합니다. 설정이 완료되면 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#different-ways-to-enroll)할 수 있습니다.
        1. Microsoft 계정 정보를 입력합니다.
        2. 암호를 입력합니다. Microsoft 계정에 [2FA(2단계 인증)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)가 필요한 경우 인증 프로세스를 완료합니다.

    ![사용자 설정](images/13-device-owner.png)

1. HoloLens 2에서 음성을 사용할지 여부와 진단 원격 분석을 보낼지 여부를 선택합니다.
    ![Cortana 사용](images/22-do-more-with-voice.png)

1. 원격 분석 수준을 선택합니다. 가능한 경우, 전체 원격 분석을 사용하도록 설정합니다. 이 정보는 HoloLens 엔지니어링 팀에게 매우 유용합니다.
     ![원격 분석 수준](images/24-telemetry.png)

1. HoloLens 2에서 시작 제스처를 사용하는 방법에 대해 알아봅니다.
     ![시작 제스처를 사용하는 방법 배우기, 이미지 1](images/26-01-startmenu-learning.png) ![시작 제스처를 사용하는 방법 알아보기, 이미지 2](images/26-02-startmenu-learning.png)

축하합니다!  설치가 완료되었으며 HoloLens를 사용할 준비가 되었습니다!

## 다음 단계

> [!div class="nextstepaction"]
> [HoloLens 2 시작하기](hololens2-basic-usage.md)
