---
title: 관리자 없는 운영 체제 보안
description: HoloLens 혼합 현실 디바이스의 관리자 없는 운영 체제, 디바이스 소유자 및 보안에 대해 자세히 알아보세요.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, 관리자 없는, 관리자 없는, 운영 체제, 관리자 없는 운영 체제, 관리자 os, 관리자 없는 os, hololens 2, hololens2 보안,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f4fc79b7f51933418cdda8368c6b4b070e854dd0978754647ce864075c772cfd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665542"
---
# <a name="admin-less-operating-system"></a>관리자가 없는 운영 체제

HoloLens 2는 관리자 그룹에 대한 지원을 사용하지 않고 모든 타사 UWP 애플리케이션 코드를 AppContainer 샌드박스 내의 표준 사용자로만 실행하도록 제한하여 권한 에스컬레이션에 대한 노출 영역을 최소화합니다. 이 코드에는 에스컬레이션되지 않은 사용자를 위해 애플리케이션에 명시적으로 매니페스트되는 기능으로 보호를 받는 리소스와 모든 AppContainers에 액세스할 수 있는 리소스에게 액세스 권한만 부여합니다.
이러한 애플리케이션 기능은 3계층 분류 모델을 계속 유지합니다.
  * 일반
  * 제한
  * Windows

Windows 구성 요소는 시스템 UWP를 통해 AppContainer 샌드박스를 활용할 수도 있습니다. UWP(유니버설 Windows 플랫폼)에 대한 자세한 내용은 [UWP 설명서](/windows/uwp/)를 참조하세요. 또한 더 큰 권한 축소 요구 사항(예: 브라우저 콘텐츠 페이지 또는 파서)을 포함하는 Windows 구성 요소는 모든 AppContainers에 액세스 가능한 리소스 집합에 대한 액세스를 잘라내는 LPAC(낮은 권한 수준의 AppContainer) 샌드박스를 사용합니다.

## <a name="device-owner"></a>디바이스 소유자

마지막으로, 디바이스를 테넌트에 연결하거나 사용자 관리와 같은 특정 디바이스 전체 작업의 실행은 "디바이스 소유자"에게만 허용됩니다. 디바이스의 사용자는 다음 단계 중 하나를 통해 이 그룹을 채웁니다.
  * 디바이스의 첫 번째 사용자는 항상 소유자로 지정됩니다. 
> [!IMPORTANT]
>Azure AD 사용자의 경우 이 규칙의 예외는 디바이스가 Autopilot 또는 비실제 사용자를 사용하는 대량 Azure AD 등록을 통해 조인된 Azure AD인 경우입니다. 이 경우 디바이스에 로그인한 첫 번째 AAD 사용자는 해당 사용자에게 Azure Portal에 할당된 "전역 관리자"또는 "디바이스 관리자" 역할이 없으면 자동으로 디바이스 소유자가 되지 않을 수 있습니다. 자세한 내용은 아래 메모를 참조하세요.  

  * 사용자가 디바이스의 다른 소유자에 의해 설정 UX에서 소유자로 승격되는 경우.
  * 디바이스 소유자를 더 이상 사용할 수 없고(퇴사) 디바이스가 Azure AD에 조인된 경우 테넌트 관리자는 Azure Portal에서 디바이스 소유자를 새 사용자로 변경할 수 있습니다. Azure AD 테넌트의 전역 관리자 및 디바이스 관리자는 이전 단계 중 어느 것도 요구하지 않고 디바이스에 소유자로 암시적으로 로그인합니다.  

 IT 관리자는 [개인 정보 취급](/windows/client-management/mdm/policy-csp-privacy) 정책을 통해 액세스할 수 있는 앱을 관리할 수 있습니다. 

> [!NOTE]
> Azure AD에 조인된 디바이스에서 디바이스 소유자로 지정된 사용자를 자세히 알아보려면 ["로컬 관리자 할당" 설명서](/azure/active-directory/devices/assign-local-admin)를 참조하세요(단, 관리자가 HoloLens에 없으므로 '로컬 관리자'를 '디바이스 소유자'라 함).