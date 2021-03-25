---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 개요
description: 회사 연결 네트워크를 통해 Dynamics 365 가이드를 통해 HoloLens 2 장치를 등록하는 방법을 알아보세요.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448599"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 개요

이 가이드는 IT 전문가가 Dynamics 365 가이드(가이드)를 통해 Microsoft HoloLens 2 장치를 계획하고 조직에 배포하는 데 도움이 됩니다. 이 가이드는 파일럿 및 프로덕션 배포에 매우 잘 사용하며, 시나리오 [B:](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 조직의 네트워크 가이드 내에서 배포와 유사합니다. 개념 증명을 테스트한 후 이 가이드를 사용하여 HoloLens를 조직에 통합합니다.

이 가이드에서는 장치를 기존 장치 관리에 등록하고, 필요한 경우 라이선스를 적용하고, 최종 사용자가 Dynamics 365 가이드를 운영하고, 장치 설정 후 사용자 지정 기간 업무(LINE)을 사용할 수 있는지 검증하는 방법에 대해 다 진행합니다. 

## <a name="prerequisites"></a>필수 구성 요소

다음 인프라가 이미 구축되어 있습니다.
- Wi-Fi
    - 내부 리소스에 대한 액세스 및 인터넷 또는 클라우드 서비스에 대한 제한된 액세스 권한이 있는 내부 회사 네트워크
    - 장치 기반 인증서 인증.
- MDM 자동 등록을 사용하여 Azure AD(Azure Active Directory) 가입([Azure AD P1 구독](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 필요)
- MDM(Intune) 관리
    - 하나 이상의 응용 프로그램이 MDM을 통해 배포됩니다.
- 네트워크 
    - 인증서(SCEP 또는 PKCS)
    - 프록시 구성
- 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
    - 장치당 한명 또는 여러 사용자가 지원됩니다.
- 특정 사용 사례에 따라 적용되는 장치 잠금 구성의 다양한 수준(완전히 열기에서 단일 앱 키오스크까지)

## [<a name="guides-licensing-and-requirements"></a>라이선스 및 요구 사항 가이드](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD 계정
- Dynamics 365 가이드 응용 프로그램 PC 및 HoloLens
- Dynamics 365 가이드 구독
    - Microsoft Dataverse(포함)
    - Power Apps(포함)
- Power BI Desktop
- 네트워크 연결

![Corp 연결된 네트워크 다이어그램](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>배포 단계
### <a name="prepare"></a>준비
> [!div class="checklist"]
>- [HoloLens 2 장치의 인프라 필수 요소에 대해 자세히 알아보습니다.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure AD에 대해 자세히 알아보고 없는 경우 설정하세요.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [ID 관리 및 Azure AD 계정을 가장 잘 설정하는 방법에 대해 설명합니다.](hololens2-corp-connected-prepare.md#identity-management)
>- [아직 준비되지 않은 경우 MDM에 대해 자세히 알아보고 Intune을 통해 설정합니다.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [인증서 기반 Wi-Fi에 익숙해지세요.](hololens2-corp-connected-prepare.md#certificates)
>- [프록시에 익숙해지세요.](hololens2-corp-connected-prepare.md#proxy)
>- [업무용 앱을 사용하는 방법을 이해합니다.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [조직에 대한 가이드를 사용하는 방식에 대해 자세히 알아보세요.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>구성
> [!div class="checklist"]
>- [사용자 및 그룹을 만드는 방법](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [자동 등록을 설정하는 방법](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [회사 Wi-Fi 연결에 대한 인증서 및 프로필을 Wi-Fi 방법](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [LOB(LOB) 앱 패키지를 업로드하고 할당합니다.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 가이드 설정](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [키오스크 모드를 구성하는 방법(선택 사항).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC를 구성하는 방법(선택 사항).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>배포
> [!div class="checklist"]
>-  [장치 및 MDM을 통해 등록의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [인증서 Wi-Fi 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB 앱 설치의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [제작 및 운영을 통해 가이드의 유효성을 검사합니다.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>유지 관리
> [!div class="checklist"]
>- [HoloLens 2를 업데이트합니다.](hololens2-corp-connected-maintain.md#update-hololens)
>- [가이드(스토어 앱)를 업데이트하는 방법](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB 앱을 업데이트하는 방법](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [개발 계획.](hololens2-corp-connected-maintain.md#development-plan) 
>- [지원 계획 만들기](hololens2-corp-connected-maintain.md#support-plan)
>- [장치 관리 옵션.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 준비](hololens2-corp-connected-prepare.md)
