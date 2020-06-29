---
title: HoloLens를 여러 사람과 공유
description: 여러 Azure Active Directory 계정이 나 단일 계정을 사용 하는 여러 사용자가 공유 하도록 HoloLens를 구성할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829289"
---
# HoloLens를 여러 사람과 공유

한 HoloLens를 여러 사람과 공유 하거나 여러 사람이 HoloLens 장치 집합을 공유 하는 것이 일반적입니다.  이 문서에서는 장치를 공유할 수 있는 다양 한 방법에 대해 설명 합니다.

## 각기 고유한 계정을 사용 하 여 여러 사람과 공유 합니다.

**필수 구성 요소**: HoloLens 장치는 Windows 10, 버전 1803 이상을 실행 해야 합니다.  HoloLens (첫번째 gen)도 [비즈니스용 Windows 홀로그램으로 업그레이드](hololens-upgrade-enterprise.md)해야 합니다.

Azure AD (Azure Active Directory) 계정을 사용 하는 경우 여러 사용자가 장치에서 고유한 사용자 설정 및 사용자 데이터를 유지할 수 있습니다.

여러 사람이 HoloLens에서 자신의 계정을 사용할 수 있도록 하려면 다음 단계를 수행 하 여 구성 합니다.

1. 장치에서 Windows 10, 버전 1803 이상을 실행 하 고 있는지 확인 합니다.
   > [!IMPORTANT]
   > HoloLens (1 gen) 장치를 사용 하는 경우 [에는 장치를 비즈니스용 Windows 홀로그램으로 업그레이드](hololens1-upgrade-enterprise.md)합니다.
1. 장치를 설정 하는 경우 **내 회사 또는 학교가 소유** 하 고 Azure AD 계정을 사용 하 여 로그인 합니다.
1. 설치를 완료 한 후 계정 설정 (**설정**  >  **계정**)에 **다른 사용자가**포함 되어 있는지 확인 합니다.

HoloLens를 사용 하기 위해 각 사용자는 다음 단계를 따릅니다.

1. 다른 사용자가 장치를 사용 하 고 있는 경우 다음 중 하나를 수행 합니다.
   - 전원 단추를 한 번 눌러 대기 모드로 이동한 다음 전원 단추를 다시 눌러 잠금 화면으로 돌아갑니다.
   - HoloLens 2 사용자는 시작 메뉴에서 사용자 타일을 선택 하 여 현재 사용자에 게 로그 아웃할 수 있습니다.

1. Azure AD 계정 자격 증명을 사용 하 여 장치에 로그인 합니다.  
    장치를 처음 사용 하는 경우에는 사용자의 눈으로 HoloLens를 [보정](hololens-calibration.md) 해야 합니다.

장치 사용자 목록을 보거나 장치에서 사용자를 제거 하려면 **설정**  >  **계정**(  >  **다른 사용자**)으로 이동 합니다.

## 동일한 계정을 사용 하 여 여러 사람과 공유

단일 사용자 계정을 사용 하는 동안 여러 사용자가 HoloLens 장치를 공유할 수도 있습니다.

**HoloLens 2에서**새 사용자가 처음으로 장치를 해당 헤드에 배치 하는 동안 (로그인 한 동일한 계정을 유지 하는 동안) 새 사용자에 게 보기 환경을 빠르게 보정 하 고 개인 설정 하 라는 메시지가 표시 됩니다. 장치는 향후에 각 사용자의 시청 경험에 대 한 품질과 편안 함을 자동으로 최적화할 수 있도록 보정 정보를 저장할 수 있습니다. 사용자는 장치를 다시 보정할 필요가 없습니다.

**HoloLens (첫번째 gen)에서** 계정을 공유 하는 사용자는 설정 앱에서 다시 보정을 요청 해야 합니다.  [보정](hololens-calibration.md)에 대 한 자세한 내용을 알아보세요.
