---
title: 프로 비전 패키지
description: HoloLens 장치에 대 한 앱 패키징, 프로 비전, 배포 및 엔터프라이즈 앱 배포에 대해 알아봅니다.
keywords: 앱, 앱 배포, 엔터프라이즈 앱 배포, 프로 비전
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309408"
---
# <a name="provisioning-package"></a>프로 비전 패키지

프로 비전 패키지를 사용 하 여 끝점 관리에 액세스 하지 않고도 환경에서 장치를 준비 하 고 구성할 수 있습니다. 또한 OOBE (첫 실행 경험)를 사용 하거나 [설치 중에 프로 비전 패키지를 적용](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)하 여 사용자 id, 등록 상태에 관계 없이 장치에 배포할 수 있습니다.

## <a name="provisioning-packages-considerations"></a>프로 비전 패키지 고려 사항:

* 공용이 아닌 앱
* USB 테스트용 로드만
* 자동 업데이트 없음 (PPKGs를 통한 수동 업데이트 필요)

프로 비전 패키지를 통해 설치 된 앱은 로컬 컴퓨터 저장소에 있는 인증서로 서명 되어야 합니다. 프로 비전 패키지는 장치 (로컬 컴퓨터) 저장소에 인증서를 설치할 수 있으므로 동일한 프로 비전 패키지를 통해 앱과 인증서를 설치할 수 있습니다. MDM에서 인증서를 배포 하거나 [인증서 관리자](certificate-manager.md)를 통해 설치 하는 경우이 방식으로 설치 된 앱에 서명 하려면 인증서를 로컬 컴퓨터 저장소에 배포 해야 합니다.

HoloLens 장치에 대 한 프로 비전 패키지를 만드는 기본 사항을 알아보려면 [Hololens 프로 비전](https://docs.microsoft.com/hololens/hololens-provisioning)을 방문 하세요. 앱을 배포 하려면 고급 프로 비전으로 시작 해야 합니다.

> [!NOTE]
> HoloLens (첫 번째 gen)는 프로 비전 패키지를 사용 하 여 앱 설치 (**UniversalAppInstall**)를 제한적으로 지원 합니다. HoloLens (첫 번째 gen) 장치는 OOBE 중에만 PPKG를 통해 앱을 설치 하 고 사용자 컨텍스트 설치만 지원 합니다.

## <a name="setup"></a>설치

[Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 내에서 다음 네 단계를 수행 합니다.

1. ApplicationManagement/AllowAllTrustedApps을 "Yes"로 설정 합니다. [Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)를 참조 하세요.

2. **UniversalAppInstall**  >  **UserContextAppLicense** **PackageFamilyName** 을 입력 합니다. [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)를 참조 하세요. 참고 항목: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)

   앱을 이미 설치한 장치에서 장치 포털을 사용할 수 있습니다. 앱 페이지를 방문 하 여 "!" 앞에 있는 모든 정보를 PackageRelativeID. **PackageFamilyName** 입니다.

3. 그러면 새 섹션인 **Applicationfile** 이 표시 됩니다. 이 영역을 사용 하 여 appx 번들을 업로드 합니다.

4. 앱을 구입 했거나 사용자 고유의 LOB 앱을 빌드 했는지에 따라 라이선스 파일이 나 보안 인증서를 업로드 해야 합니다.

    - 라이선스 파일의 경우: **UniversalAppInstall**  >  **usercontext** 로 이동 하 여 라이선스의 위치로 이동 하 여 업로드 합니다.
    - 보안 파일에 대해 **인증서** 로 이동 하 고 .appx 번들과 함께 설치할 인증서를 선택 합니다.

프로젝트를 안전한 위치에 저장 해야 합니다. 그런 다음 **프로 비전 패키지로** **내보냅니다** .  

참고 항목: [HoloLens에 프로 비전 패키지 적용을](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)참조 하세요.
