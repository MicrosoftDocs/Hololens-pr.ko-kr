---
title: 프로비전 패키지
description: 앱, 앱 배포, 엔터프라이즈 앱 실무, 프로비저닝
keywords: 앱, 앱 배포, 엔터프라이즈 앱 실무, 프로비저닝
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
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219225"
---
# 프로비전 패키지

프로비저닝 패키지를 사용하여 끝점 관리에 액세스하지 않고도 환경에서 장치를 준비하고 구성할 수 있습니다. 또한 사용자의 ID, 등록 상태, OOBE(첫 실행 경험) 중 또는 설치 중에 프로비저닝 패키지를 적용하여 장치에 배포할 [수도 있습니다.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## 프로비저닝 패키지 고려 사항:
* 비공용 앱
* USB 테스트용 로드만
* 자동 업데이트 없음(PPKG를 통한 수동 업데이트 필요)

프로비저닝 패키지를 통해 설치된 앱은 로컬 컴퓨터 저장소의 인증서로 서명해야 합니다. 프로비저닝 패키지는 장치(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있으므로 동일한 프로비저닝 패키지를 통해 앱과 인증서를 설치할 수 있습니다. MDM에서 인증서를 배포하거나 인증서 관리자를 [](certificate-manager.md)통해 설치하는 경우 로컬 컴퓨터 저장소에 인증서를 배포하여 이러한 방식으로 설치된 앱에 서명해야 합니다.

HoloLens 장치에 대한 프로비저닝 패키지를 만드는 기본 방법을 알아보고 [HoloLens 프로비전을 방문합니다.](https://docs.microsoft.com/hololens/hololens-provisioning) 앱을 배포하려면 고급 프로비전으로 시작해야 합니다.

> [!NOTE]
> HoloLens(1세대)는 프로비저닝 패키지를 사용하여 앱**설치(UniversalAppInstall)를**제한적으로 지원하고 있습니다. HoloLens(1세대) 장치는 OOBE 중에만 PPKG를 통해 앱 설치를 지원하며 사용자 컨텍스트 설치만 지원합니다.

## Setup

[Windows 구성 디자이너 내에서는](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 4단계를 수행합니다.

1. ApplicationManagement/AllowAllTrustedApps를 "예"로 설정 See: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. **UniversalAppInstall**  >  **UserContextAppLicense** 아래에 **PackageFamilyName을 입력하십시오.** [UniversalAppInstall을 참조합니다.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall) See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   이미 앱을 설치한 디바이스에서 Device Portal을 사용할 수 있습니다. 앱 페이지를 방문하고 PackageRelativeID 줄에서 "!" 앞에 있는 모든 정보를 살펴 봐야 합니다. **PackageFamilyName인 경우.**
    
3. 그러면 새 섹션 **ApplicationFile이 표시됩니다.** 이 영역을 사용하여 appx 번들을 업로드합니다.

4. 앱을 구매하거나 LOB 앱을 직접 구축한 경우 라이선스 파일 또는 보안 인증서를 업로드해야 합니다.

    - 라이선스 파일의 경우: **UniversalAppInstall**  >  **UserContextAppLience에서** 라이선스 위치를 찾아 업로드합니다. 
    - 보안 파일이 **인증서로** 이동하고 .appx 번들과 함께 설치할 인증서를 선택합니다.

프로젝트를 안전한 위치에 저장해야 합니다. 그런 **다음 프로비저닝** **패키지로 내보낼 수 있습니다.**  
    
참조: [HoloLens에 프로비저닝](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)패키지 적용
