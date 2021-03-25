---
title: 공통 인프라 구축 시나리오
description: 혼합 현실에 대한 다양한 인프라 배포를 기반으로 하는 가장 일반적인 배포 시나리오 중 일부에 대해 설명합니다.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: HoloLens
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448496"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>일반적인 인프라 배포 시나리오 개요

다음 정보는 엔터프라이즈 내에서 Microsoft HoloLens 2 장치를 배포하고 관리할 때의 세 가지 일반적인 시나리오에 대한 간략한 아키텍처 개요를 제공합니다. 종종 장치를 관리하는 방법과 조직의 리소스에 액세스하는 방법에 대한 결정은 이미 있는 요인에 따라 크게 결정됩니다. 기존 인프라에 따라 다음과 같은 시나리오에서 일반적인 장치 관리 스타일을 검토하고 요구에 일치하는 시나리오에서 배포에 대한 가이드를 참조하세요.

## <a name="scenarios"></a>시나리오

아래 다이어그램은 HoloLens 2 배포에 대한 세 가지 일반적인 시나리오를 표시합니다.
![시나리오 다이어그램](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>시나리오 A: 클라우드 연결 장치에 배포

HoloLens 2는 주로 회사 네트워크 외부의 환경에서 사용하기 위해 배포됩니다. 회사 리소스에 액세스하지 못하거나 VPN을 통해 제한될 수 있습니다. 이 배포는 회사 내에서 관리되는 모바일 장치와 유사합니다.
 * 기본 일반 구성
   * Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.
   * MDM(모바일 장치 관리)을 사용하여 Azure AD 가입 자동 등록--MDM(Intune) 관리
   * 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
     * 지원되는 장치당 사용자 한명 또는 여러명
   * 장치 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 완전히 열기에서 단일 앱 키오스크까지 적용됩니다.
   * 하나 이상의 응용 프로그램이 MDM을 통해 배포됩니다.

* 일반적인 문제
   * 시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정

시나리오와 유사한 배포 가이드의 경우 원격 지원을 사용하여 클라우드 연결 [HoloLens 2에 대한 가이드를 검토하세요.](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [배포 가이드 - 원격 지원을 사용하여 클라우드에 연결된 HoloLens 2](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>시나리오 B: 조직의 네트워크 내부 배포

HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 액세스할 수 있도록 배포됩니다. 인터넷 및 클라우드 서비스가 제한될 수 있습니다. 이 배포는 대부분의 Windows 10 PC에 대한 일반적인 배포입니다.

 * 기본 일반 구성
   * Wi-Fi 네트워크는 내부 리소스에 액세스할 수 있는 내부 회사 네트워크로, 인터넷 또는 클라우드 서비스에 대한 액세스가 제한됩니다.
   * MDM 자동 등록을 사용하여 Azure AD 가입
   * MDM(Intune) 관리
   * 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
     * 지원되는 장치당 사용자 한명 또는 여러명
   * 장치 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 완전히 열기에서 단일 앱 키오스크까지 적용됩니다.
   * 하나 이상의 응용 프로그램이 MDM을 통해 배포됩니다.

 * 일반적인 문제
   * HoloLens 2는 온-프레미스 AD 조인 또는 SCCM을 지원하지 않습니다. MDM을 사용하여 Azure AD 조인만 합니다. 이 시나리오에서는 현재 많은 회사에서 여전히 Windows 10 PC를 SCCM(System Center Configuration Manager)에서 관리하며 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 장치를 관리하기 위해 배포/구성한 인프라가 없는 온-프레미스 AD 가입 장치로 배포하고 있습니다.
   * HoloLens 2는 클라우드 첫 번째 장치이기 때문에 사용자 인증, OS 업데이트, MDM 관리 등 인터넷 및 클라우드 연결 서비스에 크게 의존합니다. 회사 네트워크에 연결할 때 HoloLens 2 및 해당 네트워크에서 실행된 응용 프로그램에 액세스할 수 있도록 프록시/방화벽 규칙을 조정해야 할 수 있습니다.
   * 회사 Wi-Fi 연결하려면 일반적으로 인증서가 장치 또는 사용자를 네트워크에 인증해야 합니다. MDM을 통해 Windows 10 디바이스에 인증서를 배포하는 데 필요한 인프라 또는 설정은 구성하기 어려울 수 있습니다.

> [!div class="nextstepaction"]
> [배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>시나리오 C: 안전한 오프라인 환경에 배포

HoloLens 2는 주로 네트워크 또는 인터넷 액세스가 없는 오프라인으로 사용하기 위해 배포됩니다. 이는 보안이 높거나 기밀 위치에 대한 일반적인 배포입니다.
 * 기본 일반 구성
   * Wi-Fi 사용하지 않도록 설정됩니다. 필요한 경우 USB를 통한 이더넷을 LAN 연결에 사용할 수 있습니다.
   * 관리되지 않습니다.
   * 디바이스 로그인에 대한 로컬 사용자 계정입니다.
     * HoloLens 2는 하나의 로컬 계정만 지원됩니다.
   * 장치 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 프로비저닝 패키지를 통해 적용됩니다. 이러한 구성은 일반적으로 보안 환경 요구 사항으로 제한됩니다.
   * 프로비저닝 패키지를 통해 하나 이상의 응용 프로그램이 배포됩니다.

 * 일반적인 문제
   * 프로비저닝 패키지를 통해 사용할 수 있는 제한된 구성 집합이 있습니다.
   * 클라우드 서비스는 사용할 수 없습니다. 따라서 HoloLens 2 기능이 제한됩니다.
   * 이러한 장치를 수동으로 설정, 구성 및 업데이트해야 하기 때문에 관리 오버헤드가 높아야 합니다.

이 시나리오와 유사한 배포 가이드의 경우 오프라인 보안 배포 [가이드를 검토하세요.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [배포 가이드 - 오프라인 보안 HoloLens 2](hololens-common-scenarios-offline-secure.md)
