---
title: HoloLens 2에 대한 Windows Autopilot 등록 지원
description: HoloLens 2 장치에 대한 Autopilot 등록 지원을 받는 방법에 대해 알아보세요.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427989"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Autopilot를 사용하기 위한 HoloLens 2 등록 지원

이제 고객과 Microsoft CSP(클라우드 솔루션 공급자)는 Microsoft 지원에 직접 요청을 전송하여 HoloLens 2 장치를 등록할 수 있습니다. 이 페이지에는 다음과 같이 지원되는 Autopilot 등록 시나리오에 대한 요구 사항이 간략하게 설명되어 있습니다.

- **HoloLens 2 장치 Autopilot 등록**. Windows Autopilot에 HoloLens 2 장치를 등록해 달라는 요청을 제출합니다.
- **HoloLens 2 장치 하드웨어 해시 요청**. Microsoft 지원에 요청을 제출하여 고객 또는 CSP가 Microsoft Intune 또는 Microsoft 파트너 센터를 통해 장치를 직접 등록하는 데 사용할 수 있는 하드웨어 해시를 제공합니다.
- **HoloLens 2 장치 Autopilot 등록 취소**. Windows Autopilot에서 장치를 삭제해 달라는 요청을 제출합니다. 이는 일반적으로 장치 종료 시나리오에서 사용됩니다.

다음 표에는 Microsoft 지원에 등록 요청을 제출하기 *전에* 수집해야 하는 정보가 자세히 나와 있습니다.

| 필요한 정보 | 설명 | Autopilot 등록  | 하드웨어 해시 요청 | Autopilot 등록 취소 |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory 테넌트 ID    |    Azure Active Directory 테넌트 ID는 조직 이름 또는 도메인과 다른 GUID(Globally Unique Identifier)입니다.    테넌트 ID를 찾으려면 [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)에 로그인합니다.    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory 도메인 이름    |   최상위 도메인 이름(예: contoso.com)    |     ✔️                         |                              |                         ✔️                        |
|  소유권 증명    |   원본 매도 증서나 송장을 PDF 형식으로 업로드하여 소유권 증명을 확인합니다. 스크린샷은 허용되지 않습니다. 매도 증서나 송장에는 장치 일련 번호가 포함되어야 합니다. 회사 이름     |     ✔️                         |              ✔️                |                         ✔️                        |
|  장치 일련 번호    |   Excel 파일을 각 장치 일련 번호가 새 줄에 입력된 CSV 형식으로 업로드합니다.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>지원 요청 제출

> [!div class="nextstepaction"]
> [HoloLens 2에 대한 Autopilot 등록 지원 제출](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
