---
title: 배포 가이드 - 원격 지원으로 클라우드 연결 HoloLens 2 배포 대규모 배포 - 구성
description: 클라우드 연결 네트워크를 통해 HoloLens 장치를 등록하기 위한 구성을 설정하는 방법
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
ms.openlocfilehash: 042a29fe436b21ca37a2fcd7921fc53d6a9686d5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253045"
---
# 구성 - 클라우드 연결 가이드

이 가이드 섹션에서는 테넌트에&#39;설정하는 방법과 Intune 및 원격 지원 둘 다에 대한 라이선스를 적용하는 방법을 설명합니다.

## Azure 사용자 및 그룹

해당 확장에 따라 Azure 및 Intune은 사용자 및 그룹을 사용하여 구성 및 라이선스를 할당합니다. 이 배포 흐름의 유효성을 검사하고 한 사용자에서 다른 사용자로 원격 지원 전화를 걸 수 있도록&#39;계정이 필요합니다.

라이선스를 할당하기 위해 단일 사용자 그룹을 만들 수 있습니다. 두 사용자를 동일한 그룹에 가입하고 해당 그룹에 Intune 및 원격 지원에 대한 라이선스를 적용할 수 있습니다.

사용자 그룹에서&#39;Azure AD 계정에 대한 액세스 권한이 없는 경우 사용할 수 있습니다. 다음은 빠른 시작 가이드입니다.

- [사용자를 만드는 방법](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [그룹을 만드는 방법](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [그룹에 사용자 추가](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) - 그룹을 만들기 위해 만든 사용자 추가
- [사용자 그룹이](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 디바이스에 가입할 수 있도록 Azure AD 구성 - 새 사용자 그룹에 Azure AD에 장치를 등록할 수 있는 권한이 있는지 확인

## HoloLens 2의 자동 등록

원활하고 원활한 환경을 제공하기 위해 HoloLens 2 장치에 대해 Azure Active Directory 가입(AADJ) 및 Intune에 자동 등록을 설정하는 것이 좋은 방법입니다. 이렇게 하면 사용자가 OOBE 중에 조직 로그인 자격 증명을 입력하고 Azure AD에 자동으로 등록하고 디바이스를 MDM에 등록할 수 있습니다.

Microsoft [Endpoint Manager를](https://endpoint.microsoft.com/#home)사용하여 서비스를 선택하고 일부 페이지를 탐색하여 Premium 평가판 다운로드를 선택할 수 있습니다. 자동 등록 P1의 경우 Azure Active Directory Premium 1과 2가 있을 수 있습니다. Intune을 선택하고 자동 등록에 대한 사용자 범위를 선택하고 이전에 만든 그룹을 선택할 수 있습니다.

전체 세부 정보 및 단계는 [Intune에](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)대해 자동 등록을 사용하도록 설정하는 방법에 대한 가이드를 읽어보세요.

## 응용 프로그램 라이선스

응용 프로그램 라이선스를 통해 사용자는 앱을 구입한 회사를 설치하거나 무료 평가판에서 앱의 정식 버전으로 업그레이드할 수 있습니다. 응용 프로그램 라이선스는 사용자, 사용자 그룹 또는 장치 그룹에 적용할 수 있습니다. 원격&#39;사용하려면 조직의 사용자에게 원격 지원 라이선스가 필요합니다. 이 가이드의 목적을 위해 Azure 사용자 및 그룹에서 위에서 만든 사용자 그룹에 원격 지원 라이선스를 [할당합니다.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

라이선스 요구 사항은 사용자가 장치에서 원격 지원 전화를 걸지 또는 Microsoft Teams의 원격 공동 작업자가 될지 여부에 따라 다를 수 있습니다. 기본적으로 원격 지원 및 Teams 확인란은 둘 다 표시됩니다. 이 가이드의 목적을 위해 기본 상자를 선택된 채로 두는 것이 권장됩니다.

1. 역할당 다양한 [라이선싱 및 제품 요구 사항에 대해 자세히 알아보습니다.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) 몇 가지 다른 유형의 원격 지원 라이선스가 있으므로 요구에 맞는 라이선스를 제공해야 합니다.
2. 라이선스를&#39;수 [있습니다.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [그룹에 라이선스를](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 적용합니다.

## 다음 단계

> [!div class="nextstepaction"]
> [클라우드 연결 배포 - 배포](hololens2-cloud-connected-deploy.md)