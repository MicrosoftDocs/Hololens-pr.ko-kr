---
title: HoloLens(1세대) 설정
description: 이 가이드는 처음 설정하는 과정을 안내합니다.  Wi-Fi 네트워크와 Microsoft(MSA) 또는 Azure AD(Azure Active Directory) 계정이 필요합니다.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9a20a2ddd52c08a2b44dad452aac07ad9e69de85
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903234"
---
# HoloLens(1세대) 설정

HoloLens를 처음 켜면 장치 보정, 장치 설정 및 로그인 과정을 안내합니다.  이 문서는 HoloLens(1세대)의 첫 번째 시작 및 설정 환경에 대해 안내합니다.

다음 섹션에서는 HoloLens와 작업하고 홀로그램과 상호 작용하는 방법에 대해 알아봅니다. 해당 문서를 건너뛰려면 [HoloLens(1세대) 시작](hololens1-basic-usage.md)을 참조하세요.

## 시작하기 전 확인 사항

시작하려면 먼저 다음 항목이 준비되어 있는지 확인해야 합니다.

**Wi-Fi 연결**. Wi-Fi 네트워크를 설정하려면 HoloLens를 연결해야 합니다. 처음 연결할 때 웹 사이트로 이동하거나 인증서를 사용하여 연결할 필요가 없는 열려 있거나 암호로 보호된 네트워크가 필요합니다. [HoloLens에서 사용하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).

**Microsoft 계정 또는 회사 계정** 또한 Microsoft 계정(또는 조직에서 장치를 소유한 경우, 회사 계정)을 사용하여 HoloLens에 로그인해야 합니다. Microsoft 계정이 아직 없으면 [account.microsoft.com](https://account.microsoft.com)으로 이동하여 무료로 계정을 생성합니다.

**넘어질 위험이 없는 안전하고 밝은 공간**. [상태 및 보안 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661).

HoloLens와 함께 제공되어 가장 편안한 착용감을 제공하는 **옵션 편의 액세서리**. [핏 및 편안함에 대해 자세히 알아보기](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - HoloLens를 처음 사용하는 경우 [Cortana](hololens-cortana.md)는 이미 켜져 있으며 안내할 준비가 되어 있습니다(단, 장치를 설정한 후에야 질문에 응답할 수 있음). 사용자는 언제라도 Cortana 설정에서 Cortana 기능을 끌 수 있습니다.
> - 중국어 또는 일본어 버전의 HoloLens로 전환하려면 PC에서 언어 빌드를 다운로드한 다음 HoloLens에 설치해야 합니다. 자세한 내용은 [지역화된 버전의 HoloLens(1세대) 설치](hololens1-install-localized.md)를 참조하세요.

## HoloLens 시작 및 Windows 설정

HoloLens를 처음 시작할 때 첫 번째 작업은 장치에 Windows Holographic을 설정하는 것입니다.

1. 인터넷에 연결합니다(HoloLens에서는 Wi-Fi 네트워크를 선택하도록 안내합니다).

1. 사용자 계정에 로그인합니다. **회사 또는 학교 소유** 또는 **내 소유** 중에서 선택합니다.
    - **회사 또는 학교 소유**를 선택하면 Azure AD 계정을 사용하여 로그인합니다. 조직에서 Azure AD Premium을 사용하고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록됩니다. 조직에서 Azure AD Premium을 사용하지 않는 경우에는 자동 MDM 등록을 사용할 수 없으므로 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#different-ways-to-enroll)해야 합니다. 회사 또는 학교 계정을 사용하여 처음으로 장치에 로그인하려면 다음 단계를 수행합니다.
        1. 조직 계정 정보를 입력합니다.
        1. 개인정보처리방침에 동의합니다.
        1. Azure AD 자격 증명을 사용하여 로그인합니다. 조직의 로그인 페이지로 다시 이동하게 될 수 있습니다.
        1. 장치 설정을 계속합니다.
    - **내 소유**를 선택하면 Microsoft 계정을 사용하여 로그인합니다. 설정이 완료되면 [장치 관리에서 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#different-ways-to-enroll)할 수 있습니다.
        1. Microsoft 계정 정보를 입력합니다.
        1. 암호를 입력합니다. Microsoft 계정에 [2FA(2단계 인증)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)가 필요한 경우 인증 프로세스를 완료합니다.

1. 장치는 Wi-Fi 네트워크에서 가져오는 정보에 따라 표준 시간대를 설정 합니다.

## 보정

Cortana가 자신을 소개하면 다음 설정 단계는 보정입니다. 최상의 HoloLens 환경을 위해 설정 중에 보정 프로세스를 완료해야 합니다.

HoloLens(1세대)는 동공 사이의 거리(IPD 또는 [동공 간 거리](https://en.wikipedia.org/wiki/Interpupillary_distance))를 사용하여 홀로그램을 선명하고 쉽게 상호작용하도록 합니다. IPD가 올바르지 않으면 홀로그램이 불안정하거나 잘못된 거리에 있는 것처럼 보일 수 있습니다.

보정하는 동안 HoloLens에서는 눈 하나당 6개의 대상에 손가락을 정렬하도록 요청합니다. HoloLens는 이 프로세스를 사용하여 눈에 맞는 IPD를 설정합니다. 새 사용자에 대해 보정을 업데이트하거나 조정해야 하는 경우 새 사용자는 설정 외부에서 보정 앱을 실행할 수 있습니다.

![두 번째 단계에서 IPD 손가락 맞춤 화면](./images/ipd-finger-alignment-300px.jpg)

*두 번째 단계에서 IPD 손가락 맞춤 화면*

축하합니다. 설정이 완료되었으며 HoloLens 사용을 시작할 수 있습니다.

## 다음 단계

> [!div class="nextstepaction"]
> [HoloLens(1세대) 시작하기](hololens1-basic-usage.md)
