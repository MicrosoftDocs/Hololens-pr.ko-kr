---
title: 비즈니스용 Microsoft Store
description: 비즈니스용 Microsoft Store 사용하여 혼합 현실 애플리케이션을 비즈니스에 게시하는 방법을 알아봅니다.
keywords: 비즈니스용 Microsoft Store, msfb, 앱 배포, 저장소
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924317"
---
# <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store

[이 비즈니스용 Microsoft Store](/microsoft-store/microsoft-store-for-business-overview) 주로 IT 의사 결정자와 기업 또는 조직의 관리자를 위해 설계되었으며, 선택한 시장에서 무료 및 유료 앱을 찾고, 획득하고, 관리하고, 배포하여 대량으로 디바이스를 Windows 10 수 있습니다. 

하나의 인벤토리에서 Microsoft Store 앱과 프라이빗 사업장 앱을 관리하고 필요에 따라 라이선스를 할당하고 다시 사용할 수 있습니다. 조직에 가장 적합한 배포 방법을 선택할 수도 있습니다. 즉, 개인 및 팀에 앱을 직접 할당하거나, Microsoft Store 프라이빗 페이지에 앱을 게시하거나, 관리 솔루션에 연결하여 더 많은 옵션을 선택할 수 있습니다.

최종 사용자가 비즈니스용 Microsoft Store 사용하는 경우 Microsoft Store 앱을 시작합니다. 시작되면 사용자는 조직 이름이 있는 탭을 선택할 수 있습니다. 그러면 해당 사용자 또는 해당 디바이스에서 사용할 수 있는 앱이 표시됩니다.

> [!Note]
> 비즈니스용 Microsoft Store 디바이스에 앱을 자동으로 다운로드(푸시)하지 않습니다. 그러나 비즈니스용 Microsoft Store 앱을 MDM(디바이스 관리) 서버와 연결하여 앱을 대상으로 지정하고 디바이스에 동기화할 수 있습니다.

비즈니스용 Microsoft Store 사용하는 방법에 대해 자세히 알아보려면 다음 페이지를 방문하세요.

* [애플리케이션 설치에 사용되는 사용 권한 수준](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [비즈니스용 스토어에 앱을 추가하는 방법](/mem/intune/apps/store-apps-windows)
* [직원 그룹에 앱을 할당하는 방법](/mem/intune/apps/windows-store-for-business)

비즈니스용 Microsoft Store 연결하려면 [intune에 비즈니스용 Microsoft Store 연결](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)을 방문하세요.

> [!Tip]
> ARC(Advanced Recovery Companion) 및 WCD(Windows Configuration Designer)와 같은 앱을 사용할 때 [오프라인 앱을 배포하는](/microsoft-store/distribute-offline-apps) 방법에 대해 자세히 알아봅니다.

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store 프라이빗 스토어 앱만 사용

- [Windows Holographic 버전 21H2에](hololens-release-notes.md#windows-holographic-version-21h2)도입되었습니다.

RequirePrivateStoreOnly 정책이 HoloLens 사용하도록 설정되었습니다. 이 정책을 사용하면 Microsoft Store 앱이 조직에 대해 구성된 프라이빗 저장소만 표시하도록 구성할 수 있습니다. 사용 가능하게 만든 앱에 대한 액세스만 제한합니다.

[ApplicationManagement/RequirePrivateStoreOnly에](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) 대해 자세히 알아보기

## <a name="smart-retry-for-app-updates"></a>앱 업데이트에 대한 스마트 다시 시도

- [Windows Holographic 버전 21H2에](hololens-release-notes.md#windows-holographic-version-21h2)도입되었습니다.

이제 HoloLens 사용하도록 설정된 것은 IT 관리자가 업데이트를 적용할 수 있도록 허용하는 앱 사용 중으로 인해 업데이트가 실패한 앱을 다시 시작하는 되풀이 또는 일회성 날짜를 설정할 수 있도록 하는 새로운 정책입니다. 예약된 시간 또는 로그인과 같은 몇 가지 다른 트리거에 따라 설정할 수 있습니다. 이 정책을 사용하는 방법에 대한 자세한 내용은 [ApplicationManagement/ScheduleForceRestartForUpdateFailures 를 확인하세요.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)