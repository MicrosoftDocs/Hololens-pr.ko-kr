---
title: Intune 및 회사 포털
description: Intune, 모바일 장치 관리 및 회사 포털을 사용 하 여 친숙 한 사용자 환경을 설정, 할당 및 만드는 방법을 알아봅니다.
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309730"
---
# <a name="intune--company-portal"></a>Intune & 회사 포털

MDM (모바일 장치 관리)을 사용 하면 사용자 고유의 사용자 지정 앱을 [Intune (Microsoft Endpoint Manager](https://docs.microsoft.com/intune/windows-holographic-for-business) )을 통해 사용 하 여 HoloLens 장치에 직접 배포할 수 있습니다. Microsoft Intune은 MDM(모바일 디바이스 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다. Intune은 Microsoft의 [Enterprise Mobility + Security(EMS) 제품군](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)에 포함되어 있으므로 사용자는 조직 데이터를 보호하면서 생산성을 높일 수 있습니다. Intune에 대해 자세히 알아보려면 [Intune 이란?](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)을 참조 하세요.

## <a name="setup"></a>설치

1. Lob (기간 업무)에 앱을 업로드 하거나 Intune 테 넌 트에 사용자 지정 앱을 업로드 합니다. 참고 항목: [엔터프라이즈 앱 관리](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [앱을 그룹에 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)합니다. 선택한 할당 유형에 따라 앱을 자동으로 배달할 수도 있고 앱을 선택 하는 경우 즉시 끌어올 수도 있습니다.

> [!NOTE]
> Appx 번들을 빌드할 때 배포 하려는 장치의 아키텍처를 포함 하는 것을 고려해 야 합니다. HoloLens 2는 ARM64이 고 HoloLens (첫 번째 Gen)는 x86입니다. 혼합 장치 환경을 보유 하려는 경우에는 단일 appx 번들에 둘 다 포함 될 수 있습니다.

## <a name="assignment-types"></a>할당 형식

등록 후 장치에 앱을 자동으로 설치 하려면 해당 그룹에 대해 **필수** 를 선택 해야 합니다.
회사 포털을 통해 등록 된 장치에 앱을 다운로드할 수 있도록 하려면 등록 된 **장치에 대해 사용 가능** 을 선택 합니다.

## <a name="end-user-experience"></a>최종 사용자 환경

Intune에서 구성을 설정한 후 최종 사용자가 선택한 앱을 받을 준비가 된 것입니다.

앱을 자동으로 다운로드 하려면 다음 단계를 따르세요.

1. 테 넌 트를 사용 하 여 장치를 등록 합니다.
2. 장치가 등록을 완료 하면 장치에서 앱을 받게 됩니다.
3. 앱을 즉시 볼 수 없는 경우 **설정**  >  **계정**  >  **회사 또는 학교**  >  *계정* 정보로 이동 하 고 아래로 스크롤하여 설치 된 앱 상태에 대 한 정보를 확인 합니다.

회사 포털을 통해 앱을 가져오는 방법:

1. **시작 메뉴** 를 열고 **Microsoft Store** 를 선택 합니다.
2. **회사 포털** 를 검색 하 고 앱을 다운로드 합니다.
3. 계정에 로그인 합니다.
4. 수신 하 고 다운로드 하려는 앱을 선택 합니다.

> [!Tip]
> [회사 포털 자동 설치](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 및 [Intune에서 앱 배포 및 관리](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)에 대해 자세히 알아보세요.
