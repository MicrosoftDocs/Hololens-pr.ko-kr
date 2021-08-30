---
title: 배포 가이드 – Dynamics 365 Guides 있는 회사 연결 HoloLens 2 - 개요
description: 회사 연결 네트워크를 통해 Dynamics 365 Guides HoloLens 2 디바이스를 등록하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190177"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>배포 가이드 - Dynamics 365 Guides 있는 회사 연결 HoloLens 2 - 개요

이 가이드는 IT 전문가가 Dynamics 365 Guides(가이드)를 사용하여 Microsoft HoloLens 2개 디바이스를 계획하고 조직에 배포하는 데 도움이 됩니다. 이 가이드는 파일럿 및 프로덕션 배포에 적합하며 시나리오 B: 조직의 네트워크 내부 배포 가이드와 [유사합니다.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 개념 증명을 테스트한 후에는 이 가이드를 사용하여 조직에 HoloLens 통합합니다.

이 가이드에서는 디바이스를 기존 디바이스 관리에 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 디바이스를 설정한 후 Dynamics 365 가이드를 작동하고 사용자 지정 기간 업무 앱을 사용할 수 있는지 확인하는 방법을 설명합니다. 

## <a name="prerequisites"></a>사전 요구 사항

다음 인프라가 이미 있어야 합니다.
- Wi-Fi
    - 내부 리소스에 액세스하고 인터넷 또는 클라우드 서비스에 대한 액세스가 제한된 내부 회사 네트워크
    - 디바이스 기반 인증서 인증.
- MDM 자동 등록을 사용하여 Azure Active Directory(Azure AD) 조인([Azure AD P1 구독](/azure/active-directory/fundamentals/active-directory-whatis) 필요)
- MDM(Intune) 관리
    - MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.
- 네트워크 
    - 인증서(SCEP 또는 PKCS)
    - 프록시 구성
- 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
    - 디바이스당 단일 또는 여러 사용자가 지원됩니다.
- 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용되는 다양한 수준의 디바이스 잠금 구성입니다.

## <a name="guides-licensing-and-requirements"></a>[라이선스 및 요구 사항 가이드](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD 계정
- Dynamics 365 Guides 애플리케이션 PC 및 HoloLens
- Dynamics 365 Guides 구독
    - Microsoft Dataverse(포함)
    - Power Apps(포함)
- Power BI Desktop
- 네트워크 연결

[![회사 연결 네트워크 다이어그램, 1단계. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Corp 연결 네트워크 다이어그램, 2단계. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>이 가이드에서는 다음을 수행합니다.
### <a name="prepare"></a>준비
> [!div class="checklist"]
>- [HoloLens 2 디바이스의 인프라 필수 요소에 대해 알아봅니다.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure AD에 대해 자세히 알아보고 없는 경우 설정합니다.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법에 대해 알아봅니다.](hololens2-corp-connected-prepare.md#identity-management)
>- [MDM에 대해 자세히 알아보고 준비되지 않은 경우 Intune으로 설정합니다.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [인증서 기반 Wi-Fi를 숙지합니다.](hololens2-corp-connected-prepare.md#certificates)
>- [프록시를 숙지합니다.](hololens2-corp-connected-prepare.md#proxy)
>- [사업장 앱을 사용하는 방법을 이해합니다.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [조직에 대한 가이드를 사용하는 방법에 대해 자세히 알아보세요.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>구성
> [!div class="checklist"]
>- [사용자 및 그룹을 만드는 방법](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [자동 등록을 설정하는 방법](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [회사 Wi-Fi 연결에 대한 Wi-Fi 인증서 및 프로필을 설정하는 방법입니다.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [LOB(LoB) 앱 패키지를 업로드 및 할당합니다.](hololens2-corp-connected-configure.md#app-deployment)
>- [설치 Dynamics 365 Guides.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [키오스크 모드를 구성하는 방법(선택 사항).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC를 구성하는 방법(선택 사항).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>배포
> [!div class="checklist"]
>-  [디바이스 및 MDM을 통해 등록의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Wi-Fi 인증서의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB 앱 설치의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [작성 및 운영을 통해 가이드의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>유지 관리
> [!div class="checklist"]
>- [HoloLens 2 업데이트합니다.](hololens2-corp-connected-maintain.md#update-hololens)
>- [가이드를 업데이트하는 방법(스토어 앱).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB 앱을 업데이트하는 방법](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [개발 계획.](hololens2-corp-connected-maintain.md#development-plan) 
>- [지원 계획 수립](hololens2-corp-connected-maintain.md#support-plan)
>- [디바이스 관리 옵션.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 준비](hololens2-corp-connected-prepare.md)
