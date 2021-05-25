---
title: 일반적인 인프라 배포 시나리오
description: 혼합 현실에 대한 다양한 인프라 배포를 기반으로 하는 가장 일반적인 배포 시나리오 중 일부에 대해 알아봅니다.
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397428"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>일반적인 인프라 배포 시나리오 개요

다음 정보는 기업 내에서 Microsoft HoloLens 2개의 디바이스를 배포하고 관리할 때 세 가지 일반적인 시나리오에 대한 대략적인 아키텍처 개요를 제공합니다. 종종 디바이스를 관리하는 방법과 조직의 리소스에 액세스하는 방법은 이미 있는 요인에 따라 크게 결정됩니다. 기존 인프라에 따라 다음 시나리오에서 일반적인 디바이스 관리 스타일을 검토하고 요구 사항에 맞는 시나리오에서 배포하기 위한 가이드를 사용해 보세요.

## <a name="scenarios"></a>시나리오

아래 다이어그램은 HoloLens 2 배포에 대한 두 가지 일반적인 관리형 시나리오를 나타냅니다.
 

오프라인 보안 배포를 허용하는 세 번째 시나리오도 있습니다.

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>시나리오 A: 클라우드 연결 디바이스에 배포

HoloLens 2 주로 회사 네트워크 외부 환경에서 사용하기 위해 배포됩니다. 회사 리소스는 액세스되지 않거나 VPN을 통해 제한될 수 있습니다. 이 배포는 회사 내의 관리되는 모바일 디바이스와 비슷합니다.
 * 기본 일반 구성
   * Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.
   * MDM(모바일 장치 관리) 자동 등록을 사용하여 Azure AD 조인--MDM(Intune) 관리
   * 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
     * 지원되는 디바이스당 단일 또는 여러 사용자
   * 디바이스 잠금 구성의 다양한 수준은 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용됩니다.
   * MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.



* 일반적인 문제
   * 시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정

[![시나리오 A 다이어그램 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

이 시나리오와 유사한 배포 가이드는 [클라우드 연결 환경 배포](hololens2-cloud-connected-overview.md)가이드를 참조 하세요.

> [!div class="nextstepaction"]
> [클라우드 연결 환경 배포 가이드](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [클라우드 연결 환경 (외부 클라이언트) 배포 가이드](hololens2-deployment-guide.md)

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
   * HoloLens 2는 온-프레미스 AD 조인 또는 SCCM을 지원 하지 않습니다. MDM과 Azure AD 조인만 가능합니다. 오늘날 많은 회사에서 온-프레미스 AD 조인 디바이스로 이 시나리오에서 여전히 Windows 10 PC를 배포하고 있으며, SCCM(System Center 구성 관리자)으로 관리되며 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 디바이스를 관리하기 위해 인프라를 배포/구성하지 않았을 수 있습니다.
   * HoloLens 2 클라우드 우선 디바이스이므로 사용자 인증, OS 업데이트, MDM 관리 등을 위해 인터넷 및 클라우드 연결 서비스에 크게 의존합니다. 회사 네트워크에 연결할 때 프록시/방화벽 규칙을 조정하여 HoloLens 2 및 해당 네트워크에서 실행되는 애플리케이션에 액세스할 수 있도록 해야 합니다.
   * 회사 Wi-Fi 연결에는 일반적으로 네트워크에 대한 디바이스 또는 사용자를 인증하기 위한 인증서가 필요합니다. MDM을 통해 Windows 10 디바이스에 인증서를 배포하는 데 필요한 인프라 또는 설정은 구성하기 어려울 수 있습니다.

[![시나리오 B1 다이어그램 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![시나리오 B2 다이어그램 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

이 시나리오와 유사한 배포 가이드는 회사 [네트워크 배포 가이드](hololens2-corp-connected-overview.md)에 대한 가이드를 검토하세요.

> [!div class="nextstepaction"]
> [회사 네트워크 배포 가이드](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>시나리오 C: 안전한 오프라인 환경에 배포

HoloLens 2 네트워크 또는 인터넷 액세스 없이 주로 오프라인에서 사용하도록 배포됩니다. 이는 매우 안전한 위치 또는 기밀 위치에 대한 일반적인 배포입니다.
 * 기본 일반 구성
   * Wi-Fi 연결을 사용할 수 없습니다. 필요한 경우 USB를 통한 이더넷에서 LAN 연결을 사용하도록 설정할 수 있습니다.
   * 관리되지 않습니다.
   * 디바이스 로그인에 대한 로컬 사용자 계정입니다.
     * HoloLens 2 하나의 로컬 계정만 지원합니다.
   * 디바이스 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 프로비전 패키지를 통해 적용됩니다. 이러한 구성은 일반적으로 보안 환경 요구 사항 때문에 제한 됩니다.
   * 프로 비전 패키지를 통해 하나 이상의 응용 프로그램을 배포 합니다.

 * 일반적인 문제
   * 프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합이 있습니다.
   * 클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능을 제한 합니다.
   * 이러한 장치를 수동으로 설정 하 고 구성 하 고 업데이트 해야 하기 때문에 관리 오버 헤드가 더 높습니다.

[![오프 라인 보안 다이어그램 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

이 시나리오와 유사한 배포 가이드는 [오프 라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)를 참조 하세요.

> [!div class="nextstepaction"]
> [오프 라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)
