---
title: HoloLens 설정 (첫 번째 gen)
description: Microsoft (MSA) 또는 Azure Active Directory (AAD) 계정으로 Wi-Fi 네트워크를 통해 처음으로 HoloLens를 설정 하는 방법에 대해 알아봅니다.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309365"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens 설정 (첫 번째 gen)

HoloLens를 처음 켤 때 장치를 보정 하 고 장치를 설정 하 고 로그인 하는 과정을 안내 합니다.  이 문서에서는 HoloLens (첫 번째 gen) 첫 번째 시작 및 설정 환경을 안내 합니다.

다음 섹션에서는 HoloLens를 사용 하 여 holograms와 상호 작용 하는 방법을 알아봅니다. 해당 문서로 건너뛰려면 [HoloLens 시작 (첫 번째 gen)](hololens1-basic-usage.md)을 참조 하세요.

## <a name="before-you-start"></a>시작하기 전에

시작 하기 전에 다음을 사용할 수 있는지 확인 합니다.

**Wi-Fi 연결** 입니다. 설정 하려면 HoloLens를 Wi-Fi 네트워크에 연결 해야 합니다. 처음 연결 하는 경우에는 웹 사이트로 이동 하거나 인증서를 사용 하 여 연결할 필요가 없는 개방 또는 암호로 보호 된 네트워크가 필요 합니다. [HoloLens에서 사용 하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).

**Microsoft 계정 또는 회사 계정**. 또한 Microsoft 계정 (또는 조직에서 장치를 소유 하는 경우)를 사용 하 여 HoloLens에 로그인 해야 합니다. Microsoft 계정 없는 경우 [account.microsoft.com](https://account.microsoft.com) 으로 이동 하 여 무료로 설정 합니다.

**안전 하 고, 안전 하 고, 작동 하지 않는 공간** 입니다. [상태 및 안전 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661)

HoloLens와 함께 제공 되는 **선택적 편리한 액세서리** 로 가장 편안한 맞춤을 활용할 수 있습니다. [맞춤 및 편안](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)함.

> [!NOTE]
>  
> - HoloLens를 처음 사용 하는 경우 [Cortana](hololens-cortana.md) 는 이미 사용 중 이며 사용자를 안내할 준비가 되어 있습니다 (장치를 설정한 후에도 질문에 응답할 수 없음). Cortana 설정에서 언제 든 지 Cortana를 해제할 수 있습니다.
> - HoloLens의 중국어 또는 일본어 버전으로 전환 하려면 PC에서 언어에 대 한 빌드를 다운로드 한 다음 HoloLens에 설치 해야 합니다. 자세한 내용은 [HoloLens의 지역화 된 버전 설치 (첫 번째 gen)](hololens1-install-localized.md)를 참조 하세요.

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens 시작 및 Windows 설정

HoloLens를 처음 시작할 때 첫 번째 작업은 장치에서 Windows Holographic를 설정 하는 것입니다.

1. 인터넷에 연결 합니다 (HoloLens 가이드를 선택 하 Wi-Fi 네트워크).

1. 사용자 계정에 로그인 합니다. 회사 또는 학교에서 소유 **하 고** 있는 **회사 또는 학교** 를 선택 합니다.
    - **내 회사 또는 학교 소유의 회사** 를 선택 하는 경우 Azure AD 계정을 사용 하 여 로그인 합니다. 조직에서 Azure AD Premium를 사용 하 고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록 됩니다. 조직에서 Azure AD Premium 사용 하지 않는 경우 자동 MDM 등록을 사용할 수 없으므로 [장치 관리에 HoloLens를 수동으로 등록](hololens-enroll-mdm.md#different-ways-to-enroll)해야 합니다. 회사 또는 학교 계정을 사용 하 여 처음으로 장치에 로그인 하려면 다음 단계를 수행 합니다.
        1. 조직 계정 정보를 입력 합니다.
        1. 개인 정보 취급 방침에 동의 합니다.
        1. Azure AD 자격 증명을 사용 하 여 로그인 합니다. 조직의 로그인 페이지로 리디렉션될 수 있습니다.
        1. 장치를 계속 설정 합니다.
    - **본인** 을 선택 하는 경우 Microsoft 계정를 사용 하 여 로그인 합니다. 설치가 완료 되 면 [장치 관리에 HoloLens를 수동으로 등록할](hololens-enroll-mdm.md#different-ways-to-enroll)수 있습니다.
        1. Microsoft 계정 정보를 입력 합니다.
        1. 암호를 입력합니다. Microsoft 계정 [2 단계 인증 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)을 요구 하는 경우 확인 프로세스를 완료 합니다.

1. 장치는 Wi-Fi 네트워크에서 가져온 정보에 따라 표준 시간대를 설정 합니다.

## <a name="calibration"></a>보정

Cortana가 자신을 소개 하 고 나면 다음 설치 단계는 보정입니다. 최상의 HoloLens 환경을 위해 설치 중에 보정 프로세스를 완료 해야 합니다.

HoloLens (첫 번째 gen)는 pupils (IPD 또는 [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) 사이의 거리를 사용 하 여 holograms 명확 하 고 쉽게 상호 작용할 수 있도록 합니다. IPD이 잘못 된 경우 holograms는 불안정 하거나 잘못 된 거리에 있는 것 처럼 보일 수 있습니다.

보정을 수행 하는 동안 HoloLens는 눈에 따라 6 개 대상 시리즈를 사용 하 여 손가락을 맞추는 것을 요청 합니다. HoloLens는이 프로세스를 사용 하 여 눈에 맞는 올바른 IPD를 설정 합니다. 새 사용자에 대해 보정을 업데이트 하거나 조정 해야 하는 경우 새 사용자는 설치 외부에서 보정 앱을 실행할 수 있습니다.

![두 번째 단계의 IPD 손가락 맞춤 화면](./images/ipd-finger-alignment-300px.jpg)

*두 번째 단계의 IPD 손가락 맞춤 화면*

축하합니다! 설치가 완료 되 고 HoloLens 사용을 시작할 수 있습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [HoloLens 시작 (첫 번째 gen)](hololens1-basic-usage.md)
