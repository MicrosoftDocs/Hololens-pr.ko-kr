---
title: 상용 환경에서 HoloLens 2 배포 계획
description: 인프라, Azure Active Directory 및 모바일 장치 관리를 포함 하 여 엔터프라이즈 환경에서 HoloLens를 배포 하 고 관리 하는 방법에 대해 자세히 알아보세요.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924607"
---
# <a name="common-deployment-scenarios"></a>일반 배포 시나리오

## <a name="overview"></a>개요

이 페이지에서는 기업 내에서 Microsoft HoloLens 2 장치를 배포 및 관리 하는 세 가지 일반적인 시나리오에 대 한 개략적인 아키텍처 개요를 제공 합니다.

일반적으로 장치를 관리 하 고 조직의 리소스에 액세스 하는 방법은 이미 마련 된 요인에 따라 결정 됩니다. 기존 인프라에 따라 다음과 같은 시나리오에서 일반적인 MDM (장치 관리 스타일)을 검토 하 고, [상업적 환경에서 HoloLens 2 배포 계획](hololens-core-components.md) 을 읽어 요구 사항과 일치 하는 시나리오를 확인 합니다. 배포 하는 동안 사용할 수 있는 세 가지 해당 가이드도 있습니다.


 1. [클라우드 연결 환경 배포 가이드](hololens2-cloud-connected-overview.md)
     1. [클라우드 연결 환경(외부 클라이언트) 배포 가이드](hololens2-deployment-guide.md)
 1. [회사 네트워크 배포 가이드](hololens2-corp-connected-overview.md)
 1. [오프라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>시나리오 A: 클라우드 연결 장치에 배포

이 시나리오는 회사 내에서 관리 되는 모바일 장치를 배포 하는 것과 유사 합니다. HoloLens 2는 주로 회사 네트워크 외부 환경에서 사용할 수 있도록 배포 됩니다. 회사 리소스에 액세스 하지 않거나 VPN을 통해 제한할 수 있습니다. 
 * 기본 일반 구성
   * Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열립니다.
   * MDM (모바일 장치 관리) 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리
   * 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
     * 지원 되는 장치 당 단일 또는 여러 사용자
   * 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.
   * MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.

* 일반적인 문제
   * 시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정

[![시나리오 A 다이어그램 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

해당 하는 클라우드 연결 가이드는 장치 관리에 HoloLens 2를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설치 시 원격 지원을 즉시 사용할 수 있는지 확인 하는 방법을 다룹니다. 외부 클라이언트 가이드를 사용 하 여 단기 또는 장기 외부 사용을 위해 원격 사이트에 장치를 배포할 수 있습니다.

> [!div class="nextstepaction"]
> [클라우드 연결 환경 배포 가이드](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [클라우드 연결 환경(외부 클라이언트) 배포 가이드](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>시나리오 B: 조직의 네트워크 내에 배포

이 시나리오는 대부분의 Windows 10 Pc에 대 한 클래식 배포와 동일 합니다. HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 대 한 액세스 권한이 있는 회사 네트워크에서 사용할 수 있도록 배포 됩니다. 인터넷 및 클라우드 서비스를 제한할 수 있습니다. 

 * 기본 일반 구성
   * Wi-Fi 네트워크는 내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 이며 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스입니다.
   * MDM 자동 등록을 사용 하는 Azure AD 조인
   * MDM (Intune) 관리
   * 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
     * 지원 되는 장치 당 단일 또는 여러 사용자
   * 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.
   * MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.

 * 일반적인 문제
   * HoloLens 2는 온-프레미스 AD 조인 또는 SCCM을 지원 하지 않습니다. MDM을 사용 하는 Azure AD 조인만 오늘날 대부분의 회사에서는이 시나리오에서 Windows 10 Pc를 System Center Configuration Manager (SCCM)에서 관리 하는 온-프레미스 AD 조인 장치에 배포 하 고, 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 장치를 관리 하기 위해 인프라를 배포/구성 하지 않을 수 있습니다.
   * HoloLens 2는 클라우드 우선 장치 이며, 사용자 인증, OS 업데이트, MDM 관리 등에 대 한 인터넷 및 클라우드 연결 서비스에 크게 의존 합니다. 회사 네트워크에 연결 하는 경우 HoloLens 2 및이를 실행 하는 응용 프로그램에 대 한 액세스를 사용 하도록 설정 하기 위해 프록시/방화벽 규칙을 조정 해야 할 수 있습니다.
   * 회사 Wi-Fi 연결에는 일반적으로 네트워크에 대 한 장치 또는 사용자를 인증 하기 위한 인증서가 필요 합니다. MDM을 통해 Windows 10 장치에 인증서를 배포 하는 데 필요한 인프라 또는 설정은 구성 하기가 어려울 수 있습니다.

[![시나리오 B1 다이어그램 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![시나리오 B2 다이어그램 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

해당 회사 네트워크 가이드는 HoloLens 2를 기존 장치 관리에 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설정 후 사용자 지정 lob (기간 업무) 앱을 사용할 365 수 있는지 확인 하는 방법에 대해 설명 합니다.

> [!div class="nextstepaction"]
> [회사 네트워크 배포 가이드](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>시나리오 C: 보안 오프 라인 환경에서 배포

이는 보안 수준이 높은 또는 기밀 위치의 일반적인 배포입니다. HoloLens 2는 네트워크 또는 인터넷 액세스 없이 주로 오프 라인으로 사용 하기 위해 배포 됩니다. 
 * 기본 일반 구성
   * Wi-Fi 연결을 사용할 수 없습니다. 필요한 경우 USB를 통한 이더넷 LAN 연결을 사용 하도록 설정할 수 있습니다.
   * 관리 되지 않습니다.
   * 장치 로그인에 대 한 로컬 사용자 계정.
     * HoloLens 2는 하나의 로컬 계정만 지원 합니다.
   * 다양 한 수준의 장치 잠금 구성은 특정 사용 사례에 따라 프로 비전 패키지를 통해 적용 됩니다. 이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 제한 됩니다.
   * 프로 비전 패키지를 통해 하나 이상의 응용 프로그램을 배포 합니다.

 * 일반적인 문제
   * 프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합이 있습니다.
   * 클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능을 제한 합니다.
   * 이러한 장치를 수동으로 설정 하 고 구성 하 고 업데이트 해야 하기 때문에 관리 오버 헤드가 더 높습니다.

[![오프 라인 보안 다이어그램 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

해당 오프 라인 보안 가이드에서는 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로 비전 패키지를 적용 하기 위한 지침을 제공 합니다.

> [!div class="nextstepaction"]
> [오프라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)


