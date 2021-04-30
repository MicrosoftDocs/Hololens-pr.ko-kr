---
title: 배포 가이드 – 클라우드로 연결 된 HoloLens 2 배포, 원격 지원-구성
description: 원격 지원을 통해 대규모 클라우드 연결 네트워크를 통해 HoloLens 장치를 등록 하는 구성을 설정 하는 방법에 대해 알아봅니다.
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309360"
---
# <a name="configure---cloud-connected-guide"></a>구성-클라우드 연결 가이드

가이드의이 섹션에서는 테 넌 트에 대 한 자동 등록을 설정 하는 방법 및 Intune 및 원격 지원에 대 한 라이선스를 적용 하는 방법을 설명&#39;.

## <a name="azure-users-and-groups"></a>Azure 사용자 및 그룹

Azure 및 Intune은이 확장에 의해 사용자 및 그룹을 사용 하 여 구성과 라이선스를 할당 하는 데 도움을 줍니다. 이 배포 흐름의 유효성을 검사 하 고 한 사용자에서 다른 사용자에 게 원격 지원을 제공할 수 있도록 하기 위해 두 개의 사용자 계정이 필요&#39;.

라이선스를 할당 하기 위해 단일 사용자 그룹을 만들 수 있습니다. 두 사용자를 동일한 그룹에 조인 하 고 Intune 및 원격 지원에 대 한 라이선스를 해당 그룹에 적용할 수 있습니다.

사용자 그룹의 두 Azure AD 계정에 대 한 액세스 권한이 이미 있는&#39;없는 경우에는를 사용할 수 있습니다. 다음은에 대 한 빠른 시작 가이드입니다.

- [사용자를 만드는 방법](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [그룹을 만드는 방법](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [그룹에 사용자 추가](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자를 추가 하 여 그룹을 만듭니다.
- [사용자 그룹이 장치에 연결할 수 있도록 AZURE Ad 구성](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 새 사용자 그룹에 장치를 azure ad에 등록할 수 있는 권한이 있는지 확인 합니다.

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens에서 자동 등록 2

원활한 원활한 환경을 제공 하기 위해 AADJ (Azure Active Directory Join) 및 HoloLens 2 장치에 대 한 Intune에 자동 등록을 설정 하는 방법이 있습니다. 이렇게 하면 사용자가 OOBE 중에 조직 로그인 자격 증명을 입력 하 여 Azure AD에 자동으로 등록 하 고 장치를 MDM에 등록할 수 있습니다.

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)를 사용 하 여 서비스를 선택 하 고 몇 페이지로 이동 하 여 프리미엄 평가판 가져오기를 선택할 수 있습니다. 자동 등록에 대 한 P1이 충분 한 Azure Active Directory Premium 1 및 2가 있는 것을 알 수 있습니다. Intune을 선택 하 고 자동 등록에 대 한 사용자 범위를 선택 하 고 이전에 만든 그룹을 선택할 수 있습니다.

전체 세부 정보 및 단계는 [Intune에 대 한 자동 등록을 사용 하도록 설정 하는 방법](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)에 대 한 가이드를 참조 하세요.

## <a name="application-licenses"></a>응용 프로그램 라이선스

응용 프로그램 라이선스를 통해 사용자는 회사의 구매한 앱을 설치 하거나 무료 평가판에서 앱의 정식 버전으로 업그레이드할 수 있습니다. 응용 프로그램 라이선스는 사용자, 사용자 그룹 또는 장치 그룹에 적용 될 수 있습니다. 조직의 사용자가 원격 지원을 사용 하려면 원격 지원 라이선스가 필요&#39;. 이 가이드에서는 [Azure 사용자 및 그룹](hololens2-cloud-connected-configure.md#azure-users-and-groups)에서 앞서 만든 사용자 그룹에 원격 지원 라이선스를 할당 합니다.

라이선스에 대 한 요구 사항은 사용자가 장치에서 원격 지원을 받을 것인지 아니면 Microsoft 팀의 원격 협력자가 될 지에 따라 달라질 수 있습니다. 기본적으로 원격 지원 및 팀 확인란이 모두 표시 됩니다. 이 가이드의 목적에 맞게 기본 확인란을 선택 된 상태로 두는 것이 좋습니다.

1. 각 [역할별 라이선스 및 제품 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)에 대해 자세히 알아보세요. 몇 가지 유형의 원격 지원 라이선스가 있으므로 요구 사항에 맞게 올바른 라이선스를 확보 해야 합니다.
2. [라이선스를 취득](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)해야&#39;있습니다.
3. [라이선스를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 그룹에 적용 합니다.

## <a name="next-step"></a>다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포-배포](hololens2-cloud-connected-deploy.md)