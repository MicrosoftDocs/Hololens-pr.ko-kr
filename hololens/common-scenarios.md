---
title: 일반적인 인프라 배포 시나리오
description: 혼합 현실에 대해 다양 한 인프라 배포를 기반으로 하는 가장 일반적인 배포 시나리오 중 일부에 대해 알아봅니다.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309480"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>일반적인 인프라 배포 시나리오 개요

다음 정보는 기업 내에서 Microsoft HoloLens 2 장치를 배포 및 관리 하는 세 가지 일반적인 시나리오에 대 한 개략적인 아키텍처 개요를 제공 합니다. 일반적으로 장치를 관리 하는 방법과 조직의 리소스에 액세스 하는 방법은 이미 사용 되는 요인에 따라 결정 됩니다. 기존 인프라에 따라 다음과 같은 시나리오에서 일반적인 장치 관리 스타일을 검토 하 고 필요에 맞는 시나리오에서 배포를 위한 가이드를 사용해 보세요.

## <a name="scenarios"></a>시나리오

아래 다이어그램은 HoloLens 2 배포에 대 한 세 가지 일반적인 시나리오를 나타냅니다.
![시나리오 다이어그램](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>시나리오 A: 클라우드 연결 장치에 배포

HoloLens 2는 주로 회사 네트워크 외부 환경에서 사용할 수 있도록 배포 됩니다. 회사 리소스에 액세스 하지 않거나 VPN을 통해 제한할 수 있습니다. 이 배포는 회사 내에서 관리 되는 모바일 장치와 유사 합니다.
 * 기본 일반 구성
   * Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열립니다.
   * MDM (모바일 장치 관리) 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리
   * 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
     * 지원 되는 장치 당 단일 또는 여러 사용자
   * 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.
   * MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.

* 일반적인 문제
   * 시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정

시나리오와 유사한 배포 가이드는 [원격 지원에 대 한 클라우드 연결 HoloLens 2](hololens2-cloud-connected-overview.md)가이드를 검토 하세요.

> [!div class="nextstepaction"]
> [배포 가이드-클라우드 연결 HoloLens 2 (원격 지원 포함)](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>시나리오 B: 조직의 네트워크 내에 배포

HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 대 한 액세스 권한이 있는 회사 네트워크에서 사용할 수 있도록 배포 됩니다. 인터넷 및 클라우드 서비스를 제한할 수 있습니다. 이 배포는 대부분의 Windows 10 Pc에 대 한 일반적인 배포입니다.

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

> [!div class="nextstepaction"]
> [배포 가이드 – Dynamics 365 가이드를 사용 하 여 회사에 연결 된 HoloLens 2](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>시나리오 C: 보안 오프 라인 환경에서 배포

HoloLens 2는 네트워크 또는 인터넷 액세스 없이 주로 오프 라인으로 사용 하기 위해 배포 됩니다. 이는 보안 수준이 높은 또는 기밀 위치의 일반적인 배포입니다.
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

이 시나리오와 유사한 배포 가이드는 [오프 라인 보안 배포 가이드](hololens-common-scenarios-offline-secure.md)를 참조 하세요.

> [!div class="nextstepaction"]
> [배포 가이드-오프 라인 보안 HoloLens 2](hololens-common-scenarios-offline-secure.md)
