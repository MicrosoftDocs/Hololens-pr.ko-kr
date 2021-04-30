---
title: 배포 가이드 – Dynamics 365를 사용 하 여 회사에 연결 된 HoloLens 2 가이드-개요
description: 회사 연결 네트워크를 통해 Dynamics 365 가이드를 사용 하 여 HoloLens 2 장치를 등록 하는 방법을 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309775"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>배포 가이드-Dynamics 365의 회사 연결 HoloLens 2 가이드-개요

이 가이드는 IT 전문가가 Dynamics 365 가이드 (가이드)를 사용 하 여 조직에 Microsoft HoloLens 2 장치를 계획 하 고 배포 하는 데 도움이 됩니다. 이 가이드는 파일럿 및 프로덕션 배포에 적합 하며, [시나리오 B: 조직의 네트워크 내 배포](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 가이드와 비슷합니다. 개념 증명을 테스트 한 후이 가이드를 사용 하 여 HoloLens를 조직에 통합 하는 데 사용 합니다.

이 가이드에서는 기존 장치 관리에 장치를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설정 후 사용자 지정 lob (기간 업무) 앱을 사용할 365 수 있는지 확인 하는 방법에 대해 설명 합니다. 

## <a name="prerequisites"></a>필수 조건

다음 인프라는 이미 준비 되어 있어야 합니다.
- Wi-Fi
    - 내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 및 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스
    - 장치 기반 인증서 인증.
- MDM 자동 등록을 사용 하는 Azure Active Directory (Azure AD) 가입 ([AZURE Ad P1 구독](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 필요)
- MDM (Intune) 관리
    - 하나 이상의 응용 프로그램은 MDM을 통해 배포 됩니다.
- 네트워크 
    - 인증서 (SCEP 또는 PKCS)
    - 프록시 구성
- 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
    - 장치당 단일 또는 여러 사용자가 지원 됩니다.
- 특정 사용 사례에 따라 적용 되는 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 적용 됩니다.

## <a name="guides-licensing-and-requirements"></a>[지침 라이선스 및 요구 사항](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD 계정
- Dynamics 365 가이드 응용 프로그램 PC 및 HoloLens
- Dynamics 365 가이드 구독
    - Microsoft Dataverse (포함)
    - Power Apps (포함)
- Power BI Desktop
- 네트워크 연결

![Corp 연결 네트워크 다이어그램](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>배포 단계
### <a name="prepare"></a>준비
> [!div class="checklist"]
>- [HoloLens 2 장치에 대 한 인프라 essentials에 대해 알아봅니다.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure AD에 대 한 자세한 정보를 확인 하 고 없는 경우 하나를 설정 합니다.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Id 관리 및 Azure AD 계정을 최적으로 설정 하는 방법에 대해 알아봅니다.](hololens2-corp-connected-prepare.md#identity-management)
>- [MDM에 대해 자세히 알아보고 아직 준비 하지 않은 경우 Intune을 사용 하 여 설정 합니다.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [인증서 기반 Wi-fi에 익숙해져야 합니다.](hololens2-corp-connected-prepare.md#certificates)
>- [프록시를 숙지 합니다.](hololens2-corp-connected-prepare.md#proxy)
>- [Lob (기간 업무) 앱을 사용 하는 방법을 이해 합니다.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [조직에서 가이드를 사용할 수 있는 방법에 대해 자세히 알아보세요.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>구성
> [!div class="checklist"]
>- [사용자 및 그룹을 만드는 방법](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [자동 등록을 설정 하는 방법](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [회사 Wi-Fi 연결에 대 한 Wi-Fi 인증서 및 프로필을 설정 하는 방법입니다.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [LOB (기간 업무) 앱 패키지를 업로드 하 고 할당 합니다.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 가이드를 설정 합니다.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [키오스크 모드를 구성 하는 방법 (옵션)](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC를 구성 하는 방법 (옵션).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>배포
> [!div class="checklist"]
>-  [장치 및 MDM을 통해 등록의 유효성을 검사 합니다.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Wi-Fi 인증서의 유효성을 검사 합니다.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB 앱 설치의 유효성을 검사 합니다.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [제작 및 운영을 통해 가이드의 유효성을 검사 합니다.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>유지 관리
> [!div class="checklist"]
>- [HoloLens 2를 업데이트 합니다.](hololens2-corp-connected-maintain.md#update-hololens)
>- [가이드를 업데이트 하는 방법 (스토어 앱).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB 앱을 업데이트 하는 방법입니다.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [개발 계획.](hololens2-corp-connected-maintain.md#development-plan) 
>- [지원 계획을 만드는 중입니다.](hololens2-corp-connected-maintain.md#support-plan)
>- [장치 관리 옵션입니다.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사에 연결 된 배포-준비](hololens2-corp-connected-prepare.md)
