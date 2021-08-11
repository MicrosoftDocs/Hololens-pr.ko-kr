---
title: HoloLens(1세대) 설정
description: Microsoft(MSA) 또는 AAD(Azure Active Directory) 계정을 사용하여 Wi-Fi 네트워크를 통해 처음으로 HoloLens(1세대)를 설정하는 방법을 알아봅니다.
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
ms.openlocfilehash: 9e09ba1a022428b098392464e5cd2abf84911bd6a86d8e699036b8fc4f91470a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661872"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens(1세대) 설정

HoloLens 처음 켜면 디바이스 보정, 디바이스 설정 및 로그인을 안내합니다.  이 문서에서는 HoloLens(1세대) 첫 번째 시작 및 설정 환경을 안내합니다.

다음 섹션에서는 HoloLens와 작업하고 홀로그램과 상호 작용하는 방법을 알아봅니다. 해당 문서로 건너뛰려면 [HoloLens(1세대) 시작을 참조하세요.](hololens1-basic-usage.md)

## <a name="before-you-start"></a>시작하기 전에

시작하려면 먼저 다음 항목이 준비되어 있는지 확인해야 합니다.

**Wi-Fi 연결 입니다.** HoloLens Wi-Fi 네트워크에 연결하여 설정해야 합니다. 처음 연결할 때 웹 사이트로 이동하거나 인증서를 사용하여 연결할 필요가 없는 공개 네트워크나 암호로 보호된 네트워크가 필요합니다. [HoloLens 사용하는 웹 사이트에 대해 자세히 알아보세요](hololens-offline.md).

**Microsoft 계정 또는 작업 계정 입니다.** 또한 Microsoft 계정(또는 조직에서 디바이스를 소유하는 경우 작업 계정)를 사용하여 HoloLens 로그인해야 합니다. Microsoft 계정이 없는 경우 [account.microsoft.com](https://account.microsoft.com)으로 이동하여 무료로 설정하세요.

**넘어질 위험이 없는, 안전하고 환한 공간**. [건강 및 안전 정보](https://go.microsoft.com/fwlink/p/?LinkId=746661).

HoloLens와 함께 제공되는 **편안한 액세서리(선택 사항)** 로 가장 편안하게 맞출 수 있습니다. [맞춤 및 편안함에 대한 자세한 정보](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - HoloLens 처음 사용하는 [경우 Cortana](hololens-cortana.md) 이미 시작되어 안내할 준비가 된 것입니다(디바이스를 설정한 후에야 질문에 응답할 수 없음). Cortana 설정에서 언제든지 Cortana 해제할 수 있습니다.
> - 중국어 또는 일본어 버전의 HoloLens 전환하려면 PC에서 언어에 대한 빌드를 다운로드한 다음 HoloLens 설치해야 합니다. 자세한 내용은 [지역화된 버전의 HoloLens(1세대) 설치를](hololens1-install-localized.md)참조하세요.

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens 시작 및 Windows 설정

HoloLens 처음 시작할 때 첫 번째 작업은 디바이스에서 Windows Holographic을 설정하는 것입니다.

1. 인터넷에 커넥트(HoloLens Wi-Fi 네트워크 선택 안내)

1. 사용자 계정에 로그인합니다. 내 **직장 또는 학교 소유와** **소유** 중에서 선택합니다.
    - **내 직장 또는 학교 소유를** 선택하면 Azure AD 계정을 사용하여 로그인합니다. 조직에서 Azure AD Premium을 사용하고 자동 MDM 등록을 구성한 경우 HoloLens가 MDM에 자동으로 등록됩니다. 조직에서 Azure AD Premium 사용하지 않는 경우 자동 MDM 등록을 사용할 수 없으므로 [디바이스 관리 에 HoloLens 수동으로 등록해야](hololens-enroll-mdm.md#different-ways-to-enroll)합니다. 직장 또는 학교 계정을 사용하여 처음으로 디바이스에 로그인하려면 다음 단계를 수행합니다.
        1. 조직 계정 정보를 입력합니다.
        1. 개인정보처리방침에 동의합니다.
        1. Azure AD 자격 증명을 사용하여 로그인합니다. 조직의 로그인 페이지로 다시 이동하게 될 수 있습니다.
        1. 장치 설정을 계속합니다.
    - **내가 소유하는 를** 선택하면 Microsoft 계정 사용하여 로그인합니다. 설정이 완료된 후 [장치 관리에서 수동으로 HoloLens를 등록](hololens-enroll-mdm.md#different-ways-to-enroll)할 수 있습니다.
        1. Microsoft 계정 정보를 입력합니다.
        1. 암호를 입력합니다. Microsoft 계정에 [2FA(2단계 인증)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)가 필요한 경우 인증 프로세스를 완료합니다.

1. 디바이스는 Wi-Fi 네트워크에서 가져온 정보에 따라 표준 시간대를 설정합니다.

## <a name="calibration"></a>보정

Cortana 자신을 소개한 후 다음 설정 단계는 보정입니다. 최상의 HoloLens 환경을 위해 설치하는 동안 보정 프로세스를 완료해야 합니다.

HoloLens(1세대)는 눈동자 간 거리(IPD 또는 [보조 거리)를](https://en.wikipedia.org/wiki/Interpupillary_distance)사용하여 홀로그램을 명확하고 쉽게 상호 작용할 수 있도록 합니다. IPD가 올바르지 않으면 홀로그램이 불안정하거나 잘못된 거리에 있는 것처럼 보일 수 있습니다.

보정하는 동안 HoloLens 손가락에 눈당 6개의 대상을 맞추도록 요청합니다. HoloLens 이 프로세스를 사용하여 눈의 올바른 IPD를 설정합니다. 새 사용자에 대해 보정을 업데이트하거나 조정해야 하는 경우 새 사용자는 설정 외부에서 보정 앱을 실행할 수 있습니다.

![두 번째 단계에서 IPD 손가락 정렬 화면](./images/ipd-finger-alignment-300px.jpg)

*두 번째 단계에서 IPD 손가락 정렬 화면*

축하합니다! 설치가 완료되었으며 HoloLens 사용을 시작할 수 있습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [HoloLens(1세대) 시작하기](hololens1-basic-usage.md)
