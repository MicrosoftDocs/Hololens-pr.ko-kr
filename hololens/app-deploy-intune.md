---
title: Intune 및 회사 포털
description: intune, 앱 관리, 앱, 회사 포털, 포털
keywords: intune, 앱 관리, 앱, 회사 포털, 포털, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7fcd65d5e49fa9cdd771828401749a0a41e50238
ms.sourcegitcommit: d319ac257b9ace484acf5dcfb16c9d4e19ea50a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247220"
---
# 인투네 & 컴퍼니 포털

MDM(모바일 장치 관리)을 사용하면 Microsoft [Endpoint Manager(Intune)를](https://docs.microsoft.com/intune/windows-holographic-for-business) 통해 사용자 지정 앱을 사용하여 HoloLens 장치에 직접 배포할 수 있습니다. Microsoft Intune은 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 두는 클라우드 기반 서비스입니다. Intune은 [Microsoft의 EMS(Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)제품군에 포함되어 있으며 조직 데이터를 보호하면서 생산성을 유지할 수 있도록 합니다. Intune에 대한 자세한 내용은 [Intune을 읽어 읽습니다.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## Setup

1. 비즈니스용 앱을 업로드하거나 사용자 지정 앱을 Intune 테넌트에 업로드합니다. 엔터프라이즈 앱 [관리도 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [그룹에 앱을 할당합니다.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) 선택한 할당 유형에 따라 앱을 자동으로 제공하거나, 선택한 앱이 있는 경우 앱을 쉽게 끌어오게 할 수 있습니다. 

> [!NOTE] 
> appx 번들을 구축할 때 배포하는 디바이스의 아키텍처를 포함해야 합니다. HoloLens 2는 ARM64, HoloLens(1세대)는 x86입니다. 장치 환경이 혼합된 환경을 계획하는 경우 단일 appx 번들에 둘 다 포함할 수 있습니다.

## 배정 유형

등록 후 장치에 앱을 자동으로 설치하려면 해당 그룹에 대해 **** 필수를 선택해야 합니다.
회사 포털을 통해 등록된 앱에 앱을 다운로드할 수 있도록 설정하려면 등록된 장치에 대해 사용 **가능을 선택합니다.**


## 최종 사용자 환경

Intune에서 구성을 설정한 후 최종 사용자가 선택한 앱을 받을 준비가 된 것입니다.

다음 단계에 따라 앱을 자동으로 다운로드합니다.
1. 테넌트에 디바이스를 등록합니다. 
2. 디바이스가 등록을 완료하면 디바이스에서 앱을 수신해야 합니다. 
3. 즉시 앱이 표시되지 않는 경우 설정 **** 계정 작업 또는 학교  >  ****  >  ****  >  **사용자account** 정보로 이동한 다음 아래로 스크롤하여 설치된 앱 상태에 대한 정보를 확인합니다.

회사 포털을 통해 앱에 액세스하는 방법:
1. 시작 **메뉴를 열고** **Microsoft Store를 선택합니다.** 
2. 회사 **포털을 검색하고** 앱을 다운로드합니다.
3. 계정에 로그인합니다.
4. 수신할 앱을 선택하고 다운로드합니다.

> [!Tip]
> 회사 포털 [자동](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 설치 및 [Intune에서](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)앱 배포 및 관리에 대해 자세히 알아보고
