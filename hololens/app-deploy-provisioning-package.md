---
title: 프로비전 패키지
description: HoloLens 디바이스용 앱 패키징, 프로비저닝, 배포 및 엔터프라이즈 앱 배포에 대해 알아봅니다.
keywords: 앱, 앱 배포, 엔터프라이즈 앱 배포, 프로비전
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: f480d3cc8d549fa356e05df6ce15e9517f5b978a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2021
ms.locfileid: "123610992"
---
# <a name="provisioning-package"></a>프로비전 패키지

프로비전 패키지는 엔드포인트 관리에 액세스하지 않고 환경에서 디바이스를 준비하고 구성하는 데 사용할 수 있습니다. 사용자의 ID, 등록 상태, OOBE(첫 실행 경험) 중 또는 [설치 중에 프로비전 패키지를 적용하여](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)디바이스에 배포할 수도 있습니다.

## <a name="provisioning-packages-considerations"></a>패키지 프로비전 고려 사항

* 비공용 앱
* USB 쪽 로드 전용
* 자동 업데이트 없음(PPKG를 통한 수동 업데이트 필요)

프로비전 패키지를 통해 설치된 앱은 로컬 머신 저장소의 인증서로 서명해야 합니다. 프로비전 패키지는 디바이스(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있습니다. 따라서 동일한 프로비전 패키지를 통해 앱과 인증서를 설치할 수 있습니다. MDM에서 인증서를 배포하거나 [인증서 관리자를](certificate-manager.md)통해 설치하는 경우 로컬 컴퓨터 저장소에 인증서를 배포하여 이러한 방식으로 설치된 앱에 서명해야 합니다.

HoloLens 디바이스용 프로비저닝 패키지를 만드는 기본 사항 알아보려면 [HoloLens 프로비전 을](/hololens/hololens-provisioning)방문하세요. 앱을 배포하려면 고급 프로비저닝으로 시작해야 합니다.

> [!NOTE]
> HoloLens(1세대)는 프로비전 패키지를 사용하여 앱 **설치(UniversalAppInstall)를** 제한했습니다. HoloLens(1세대) 디바이스는 OOBE 중에만 PPKG를 통해서만 사용자 컨텍스트 설치를 통해서만 앱 설치를 지원합니다.

## <a name="setup"></a>설치 프로그램

[Windows 구성 디자이너 내에서](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 다음 네 단계를 수행합니다.

1. ApplicationManagement/AllowAllTrustedApps를 "예"로 설정합니다. [ApplicationManagement/AllowAllTrustedApps를 참조하세요.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. **UniversalAppInstall**  >  **UserContextApp으로** 이동하여 **PackageFamilyName 을** 입력합니다. [UniversalAppInstall을](/windows/configuration/wcd/wcd-universalappinstall)참조하세요.

   앱을 이미 설치한 디바이스에서 장치 포털 사용할 수 있습니다. 앱 페이지를 방문하여 PackageRelativeID 줄, "!" 앞에 있는 모든 정보를 살펴봅다. **PackageFamilyName 입니다.**

3. 그러면 **ApplicationFile이라는** 새 섹션이 표시됩니다. 이 영역을 사용하여 appx 번들을 업로드합니다.

4. 앱을 구입했거나 사용자 고유의 LOB 앱을 빌드한 경우에 따라 라이선스 파일 또는 보안 인증서를 업로드해야 합니다.

    - 라이선스 파일의 경우: **UniversalAppInstall**  >  **UserContextAppLicence로** 이동하여 라이선스 제품 ID를 입력합니다. 새 <b>섹션 LicenseProductID:</b><i>yourlicenseproductid가</i> 만들어지고, 이 새 섹션을 선택하고, 라이선스의 위치를 찾아서 업로드합니다.
        - [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)를 참조하세요.
    - 보안 파일의 경우 **인증서로** 이동하여 .appx 번들과 함께 설치할 인증서를 선택합니다.

프로젝트를 안전한 위치에 저장해야 합니다. 그런 다음 **프로비전 패키지로 내보냅니다.**   

참고: [프로비전 패키지를 HoloLens 적용합니다.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
