---
title: Intune 및 회사 포털
description: intune, app management, 앱, 회사 포털, 포털
keywords: intune, app management, 앱, 회사 포털, 포털, hololens
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6a79224d02b4251a76f97f0463d4a11f6496670
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857938"
---
# Intune & 회사 포털

MDM (모바일 디바이스 관리)을 사용 하 여 사용자 지정 앱을 [Intune (Microsoft Endpoint Manager)](https://docs.microsoft.com/intune/windows-holographic-for-business) 을 통해 직접 HoloLens 장치에 배포할 수 있습니다. Microsoft Intune은 MDM (모바일 디바이스 관리) 및 MAM (모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다. Intune은 Microsoft의[엔터프라이즈 Mobility + Security (EMS) 제품군](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)에 포함 되어 있으며, 사용자는 조직 데이터를 보호 하면서 생산성을 높일 수 있습니다. Intune에 대 한 자세한 내용은 [intune의 기능](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)을 참조 하세요.

## Setup

1. 비즈니스 라인에 앱을 업로드 하거나 사용자 지정 앱을 Intune 테 넌 트에 업로드 합니다. [엔터프라이즈 앱 관리](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)참고 항목을 참조 하세요.

2. [앱을 그룹에 할당](https://docs.microsoft.com/mem/intune/apps/apps-deploy)합니다. 선택한 할당 유형을 기반으로 앱을 선택 하는 경우 앱이 자동으로 제공 되도록 하거나 바로 사용할 수 있도록 설정할 수 있습니다. 

> [!NOTE] 
> Appx 번들을 빌드할 때에는 배포 하려는 디바이스에 대 한 아키텍처 포함을 고려해 야 합니다. HoloLens 2는 ARM64, HoloLens (첫번째 Gen)는 x86입니다. 혼합 디바이스 환경을 보유 하려는 경우 단일 appx 번들에 둘 다 포함 될 수 있습니다.

## 과제 유형

등록 후 앱을 장치에 자동으로 설치 하려는 경우 해당 그룹에 대해 **필수** 를 선택 해야 합니다.
회사 포털을 통해 등록 된 앱을 다운로드할 수 있도록 하려면 **등록 된 장치에서 사용 가능**을 선택 합니다.


## 최종 사용자 환경

Intune에서 구성을 설정한 후 최종 사용자가 선택한 앱을 받을 준비가 되었습니다.

앱을 자동으로 가져오려면 다음 단계를 따르세요.
1. 테 넌 트를 사용 하 여 디바이스를 등록 합니다. 
2. 장치가 등록을 완료 하면 장치에서 앱을 받게 됩니다. 
3. 앱이 즉시 표시 되지 않는 경우 **설정**  >  **계정**  >  **회사 또는 학교**  >  **계정** 정보로 이동 하 고 아래로 스크롤하여 설치 된 앱 상태에 대 한 정보를 확인 합니다.

회사 포털을 통해 앱에 액세스 하는 방법:
1. **시작 메뉴** 를 열고 **Microsoft Store**를 선택 합니다. 
2. **회사 포털** 을 검색 하 고 앱을 다운로드 합니다.
3. 계정에 로그인 합니다.
4. 수신 하려는 앱을 선택 하 고 다운로드 합니다.

> [!Tip]
> [회사 포털 자동 설치](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 및 [Intune에서 앱 배포 및 관리](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)에 대해 자세히 알아보세요.
