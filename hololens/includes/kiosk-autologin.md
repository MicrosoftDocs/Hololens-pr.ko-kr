---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859407"
---
# <a name="non-aad-configuration"></a>[비 AAD 구성](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>비 AAD 구성

1. 다음을 수행 하는 프로 비전 패키지를 만듭니다.
    1. 방문자 계정을 허용 하도록 런타임 설정/AssignedAccess를 구성 합니다.
    1. 필요에 따라 MDM (런타임 설정/작업 공간/등록)에 장치를 등록 하 여 나중에 관리할 수 있도록 합니다.
    1. 로컬 계정 만들기 안 함
2. [프로 비전 패키지를 적용](../hololens-provisioning.md)합니다.

# <a name="aad-configuration"></a>[AAD 구성](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD 구성

키오스크 모드에 대해 구성 된 AAD 조인 장치는 로그인 화면에서 단일 단추 탭을 사용 하 여 방문자 계정에 로그인 할 수 있습니다. 방문자 계정에 로그인 한 후에는 방문자가 시작 메뉴에서 명시적으로 로그 아웃 하거나 장치를 다시 시작할 때까지 장치에 로그인 하 라는 메시지가 다시 표시 되지 않습니다.

방문자 자동 로그온은 [사용자 지정 OMA URI 정책을](/mem/intune/configuration/custom-settings-windows-10)통해 관리할 수 있습니다.

- URI 값:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 정책 | 설명 | 구성 |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 방문자가 키오스크에 자동으로 로그온 하도록 허용 합니다. | 1 (예), 0 (아니요, 기본값) |