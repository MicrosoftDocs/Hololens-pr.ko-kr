---
title: 여러 사람과 HoloLens 공유
description: 여러 Azure Active Directory 계정이 나 단일 계정을 사용 하는 여러 사용자가 공유 하도록 HoloLens를 구성할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033913"
---
# <a name="share-your-hololens-with-multiple-people"></a>여러 사람과 HoloLens 공유

## <a name="overview"></a>개요
기업은 종종 많은 공유 HoloLens 장치에 투자 합니다. HoloLens 사용 하는 방법은 개별 요구 사항에 따라 보드에서 유연 합니다. 몇 가지 다중 사용자 환경의 예는 다음과 같습니다. 

- 요금이 청구 되 고 Dynamics 365 Guides 된 장치 이며 직원이 설정 앱을 열어 필요한 Wi-Fi를 조정할 수 있도록 허용 하지만 페이지 설정 표시 유형 정책은 설정 앱에서 사용할 수 있는 페이지 수를 제한 하는 데 사용 됩니다.
- 원격 지원을 위한 장치 및 다른 회사에 임대 하는 기간 업무 앱입니다. 이러한 장치에는 앱 및 원격 지원만 포함 된 키오스크가 있습니다. WDAC는 설정 앱과 Microsoft Edge를 시작 하는 데 사용 됩니다. 장치를 여러 번의 이동에 대 한 완전 한 요금으로 유지 하기 위한 USB-C 배터리 팩이 포함 되어 있습니다.
- 모든 장치가 Autopilot에 대해 설정 되 고 모든 회사 앱을 다운로드 합니다. 서로 다른 Azure AD 그룹을 대상으로 하는 몇 가지 다른 키오스크 프로필을 설정 했습니다. 각 사용자는 FIDO2 키를 사용 하 고 고유한 Azure AD 계정에 로그인 하 여 HoloLens에 로그인 하 고 맞춤식 환경으로 제공 됩니다.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>각자의 계정을 사용 하 여 여러 사람과 공유

**필수 구성 요소**: HoloLens 장치 Windows 10 버전 1803 이상을 실행 해야 합니다.  HoloLens (첫 번째 gen)도 [Windows Holographic for Business로 업그레이드](hololens-upgrade-enterprise.md)해야 합니다.

사용자가 자신의 고유한 Azure Active Directory (Azure AD) 계정을 사용 하는 경우 여러 사용자가 장치에서 고유한 사용자 설정 및 사용자 데이터를 유지할 수 있습니다.

여러 사용자가 HoloLens에서 자신의 계정을 사용할 수 있도록 하려면 다음 단계를 수행 하 여 구성 하세요.

1. 장치가 Windows 10 버전 1803 이상을 실행 하 고 있는지 확인 합니다.
   > [!IMPORTANT]
   > HoloLens (첫 번째 gen) 장치를 사용 하는 경우 [장치를 Windows Holographic for Business으로 업그레이드](hololens1-upgrade-enterprise.md)합니다.
1. 장치를 설정 하는 경우 **내 회사 또는 학교 소유의 회사 또는 학교** 를 선택 하 고 Azure AD 계정을 사용 하 여 로그인 합니다.
1. 설치를 완료 한 후 계정 설정 (**설정**  >  **계정**)에 **다른 사용자가** 포함 되어 있는지 확인 합니다.

HoloLens 사용 하기 위해 각 사용자는 다음 단계를 따릅니다.

1. 다른 사용자가 장치를 사용 하 고 있는 경우 다음 옵션 중 하나를 선택 합니다.
   - 전원 단추를 한 번 눌러 대기로 이동한 다음 전원 단추를 다시 클릭 하 여 잠금 화면으로 돌아갑니다.
   - HoloLens 2 사용자는 시작 메뉴에서 사용자 타일을 선택 하 여 현재 사용자를 로그 아웃할 수 있습니다.

1. Azure AD 계정 자격 증명을 사용 하 여 장치에 로그인 합니다.  
    장치를 처음 사용 하는 경우 HoloLens 사용자의 눈에 맞게 [조정](hololens-calibration.md) 해야 합니다.

장치 사용자 목록을 보거나 장치에서 사용자를 제거 하려면 **설정**  >    >  **다른 사용자** 계정으로 이동 합니다.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>동일한 계정을 사용 하 여 여러 사람과 공유

단일 사용자 계정을 사용 하는 동안 여러 사용자가 HoloLens 장치를 공유할 수도 있습니다.

**HoloLens 2에서** 새 사용자가 처음으로 장치를 처음으로 배치 하는 경우 (동일한 계정에 로그인 된 상태를 유지 하는 동안), 장치는 새 사용자에 게 보기 환경을 신속 하 게 보정 하 고 개인 설정 하 라는 메시지를 표시 합니다. 장치에서 보정 정보를 저장할 수 있으므로 나중에 장치는 각 사용자의 보기 환경에 대 한 품질 및 편안 함을 자동으로 최적화할 수 있습니다. 사용자는 장치를 다시 보정할 필요가 없습니다.

**HoloLens (첫 번째 gen)에서** 계정을 공유 하는 사용자는 설정 앱에서 보정을 요청 해야 합니다.  [보정](hololens-calibration.md)에 대 한 자세한 내용을 참조 하세요.