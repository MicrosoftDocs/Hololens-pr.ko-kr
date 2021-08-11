---
title: Intune 및 회사 포털
description: Intune, 모바일 디바이스 관리 및 회사 포털을 사용하여 익숙한 사용자 환경을 설정, 할당 및 만드는 방법을 알아봅니다.
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
ms.openlocfilehash: f1c178c940224ed3cd07c58b886b176108614caf7a8463af089e2f2357f45553
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665253"
---
# <a name="intune--company-portal"></a>Intune 및 회사 포털

MDM(모바일 장치 관리)을 사용하면 [Microsoft Endpoint Manager(Intune)를](/intune/windows-holographic-for-business) 통해 사용자 지정 앱을 사용하여 HoloLens 디바이스에 직접 배포할 수 있습니다. Microsoft Intune은 MDM(모바일 디바이스 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다. Intune은 Microsoft의 [Enterprise Mobility + Security(EMS) 제품군](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)에 포함되어 있으므로 사용자는 조직 데이터를 보호하면서 생산성을 높일 수 있습니다. Intune에 대한 자세한 내용은 [Intune이란?을](/mem/intune/fundamentals/what-is-intune)읽어보세요.

## <a name="setup"></a>설치 프로그램

1. 앱을 사업 분야에 업로드 사용자 지정 앱을 Intune 테넌트로 업로드합니다. 앱 [관리 Enterprise](/windows/client-management/mdm/enterprise-app-management)참조하세요.

2. [그룹에 앱을 할당합니다.](/mem/intune/apps/apps-deploy) 선택한 할당 유형에 따라 앱이 자동으로 배달되거나 앱 선택 항목이 있는 경우 즉시 끌어올 수 있습니다.

> [!NOTE]
> appx 번들을 빌드할 때 배포할 디바이스의 아키텍처를 포함해야 합니다. HoloLens 2 ARM64이고 HoloLens(1세대)는 x86입니다. 혼합 디바이스 환경을 사용하려는 경우 둘 다 단일 appx 번들에 포함할 수 있습니다.

## <a name="assignment-types"></a>할당 형식

등록 후 디바이스에 앱을 자동으로 설치하려면 해당 그룹에 **대해 필수를** 선택해야 합니다.
회사 포털을 통해 등록된 디바이스에 앱을 다운로드할 수 있도록 하려면 **등록된 디바이스에 사용 가능을** 선택합니다.

## <a name="end-user-experience"></a>최종 사용자 환경

Intune에서 구성을 설정하면 최종 사용자가 선택한 앱을 받을 준비가 된 것입니다.

다음 단계에 따라 앱을 자동으로 얻습니다.

1. 테넌트에서 디바이스를 등록합니다.
2. 디바이스가 등록을 완료하면 디바이스에서 앱을 받아야 합니다.
3. 앱이 즉시 표시되지 않으면 **설정**  >    >  **계정회사 또는 학교**  >  *계정* 정보로 이동하고 아래로 스크롤하여 설치된 앱 상태에 대한 정보를 확인합니다.

회사 포털 통해 앱에 액세스하는 방법:

1. 시작 **메뉴를** 열고 **Microsoft Store** 선택합니다.
2. **회사 포털** 검색하고 앱을 다운로드합니다.
3. 계정에 로그인합니다.
4. 수신하고 다운로드하려는 앱을 선택합니다.

> [!Tip]
> [Intune에서](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps) [회사 포털 자동 설치](/mem/intune/apps/company-portal-app) 및 앱 배포 및 관리에 대해 자세히 알아봅니다.
