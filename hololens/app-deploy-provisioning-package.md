---
title: 프로비저닝 패키지
description: 앱, 앱 배포, 엔터프라이즈 앱 demployment, 프로비저닝
keywords: 앱, 앱 배포, 엔터프라이즈 앱 demployment, 프로비저닝
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0803b5f1b77ac7f123d534d101cd24903b87094c
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052585"
---
# 프로비저닝 패키지

프로 비전 패키지를 사용 하 여 끝점 관리에 대 한 액세스 권한이 없는 환경에서 디바이스를 준비 하 고 구성할 수 있습니다. 또한 사용자의 id, 등록 상태 (OOBE) 중, [설치 중에 프로비저닝 패키지를 적용](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)하 여 장치에 배포할 수 있습니다.

## 패키지 제공 고려 사항:
* Public이 아닌 앱
* USB 쪽만 로드
* 자동 업데이트 없음 (PPKGs를 통한 수동 업데이트 필요)

> [!NOTE] 
> HoloLens 장치용 프로비저닝 패키지를 만드는 방법에 대 한 기본 사항을 알아보려면 [Hololens 프로비저닝](https://docs.microsoft.com/hololens/hololens-provisioning)을 방문 하세요. 앱을 배포 하려면 고급 프로 비전으로 시작 해야 합니다. 

> [!NOTE] 
> HoloLens (첫번째 gen)는 프로비저닝 패키지를 사용 하 여 앱 (**UniversalAppInstall**)을 제한적으로 설치 하도록 지원 합니다. HoloLens (1 gen) 장치는 OOBE 중에만 PPKG을 사용 하 여 앱을 설치 하 고 사용자 컨텍스트 설치만을 지원 합니다.

## Setup

[Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 내에서 4 단계를 수행 합니다.

1. ApplicationManagement/AllowAllTrustedApps를 "Yes"로 설정 합니다. [Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)을 참조 하세요.
2. **UniversalAppInstall**  >  **UserContextAppLicense** 에서 **PackageFamilyName**를 입력 하십시오. [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)을 참조 하세요. 참고 항목: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - 이 방법을 모를 경우 앱을 이미 설치한 장치에서 디바이스 포털을 사용할 수 있습니다. 앱 페이지를 방문 하 여 PackageRelativeID 줄을 살펴보고 "!" 앞에 있는 모든 정보 **PackageFamilyName**.
3. 그러면 새 섹션 **Applicationfile**이 있다는 것을 알 수 있습니다. 이 영역을 사용 하 여 appx 번들을 업로드 합니다. 
4. 앱을 구입 했거나 고유한 LOB 앱을 빌드 했는지에 따라 라이선스 파일 또는 보안 인증서를 업로드 해야 합니다.
    - 라이선스 파일: **UniversalAppInstall**  >  **UserContextAppLience** 에서 라이선스의 위치로 이동 하 여 업로드 합니다. 
    - 보안 파일의 경우 **인증서** 로 이동한 다음 인증서를 선택 하 여 .appx 번들과 함께 설치 합니다. 

프로젝트를 안전한 위치에 저장 해야 합니다. 그런 다음이를 **프로비저닝 패키지로** **내보냅니다** .  
    
또한 [HoloLens에 provisiong 패키지 적용을](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)참조 하세요.
