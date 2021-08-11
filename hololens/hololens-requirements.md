---
title: 일반 배포 시나리오
description: 인프라, Azure Active Directory 및 모바일 디바이스 관리를 포함하여 엔터프라이즈 환경에서 HoloLens 배포하고 관리하는 방법에 대해 자세히 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 27fd7f81d2868134344c7563ebc0a93133a18c0a217d6eff820b5f322e9271a7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662920"
---
# <a name="common-deployment-scenarios"></a>일반 배포 시나리오

## <a name="overview"></a>개요

새 디바이스를 처음 사용해 볼 때 새 디바이스를 배포하는 방법을 파악하는 것은 어려울 수 있습니다. 여기서는 조직 내에서 Microsoft HoloLens 2개의 디바이스를 배포하고 관리하는 다양한 방법을 공유합니다.

대규모로 배포된 솔루션을 원합니다. 그곳으로 돌아가려고 합니다. 먼저 D365 Remote Assist, 가이드 또는 만든 Azure 혼합 현실 서비스 사용 애플리케이션을 사용하든 관계없이 대상 혼합 현실 시나리오에 대한 가치를 얻기 위해 디바이스를 배포하는 단계( 홀로그램)에 대해 살펴보겠습니다.

조직 내에서 HoloLens 채택하려는 비즈니스 의사 결정자, IT 전문가 또는 혁신 팀일 수 있습니다. 개념 증명에서 확장된 배포로 빌드할 때 배포 가이드는 규모에 관계없이 IT 인프라 내에서 HoloLens 이해합니다. 가장 일반적인 배포 시나리오는 다음과 같습니다.

| 시나리오 |사용량 | 핵심 내용 |
|---------|---------|---------|
| [시나리오 A: 클라우드 연결 디바이스](hololens2-cloud-connected-overview.md) | 배포를 처음 시작할 때는 소규모로 시작하여 클라우드에 연결된 단일 디바이스를 배포하여 기본 프로세스를 확인할 수 있습니다. | 디바이스는 클라우드 서비스 및 공용 인터넷에 연결됩니다. 이는 고객 사용 사례, 현장 서비스 및 개념 증명에 가장 적합합니다.|
| [시나리오 B: 조직의 네트워크](hololens2-corp-connected-overview.md) | 대규모 프로덕션에 배포할 때 조직의 네트워크와 통합해야 할 수 있습니다. | 디바이스는 "회사" wi-fi 네트워크에 연결됩니다. 이는 내부 사용자에게 가장 적합하거나 회사 환경 내에서 사용합니다.|
| [시나리오 C: 오프라인 보안 환경](hololens-common-scenarios-offline-secure.md) | 일부 중요 비즈니스용 프로세스 또는 일부 회사 정책에서는 오프라인 환경 사용을 요구할 수 있습니다. | 디바이스는 매우 제한적인 네트워크에 연결되거나 전적으로 오프라인 디바이스가 됩니다. 이는 매우 안전한 환경 또는 원격 영역의 인터넷 연결 제한에 가장 적합합니다. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>시나리오 A: 클라우드 연결 디바이스에 배포

이 시나리오는 회사 내에서 관리되는 모바일 디바이스를 배포하는 것과 비슷합니다. HoloLens 2 주로 회사 네트워크 외부 환경에서 사용하기 위해 배포됩니다. 회사 리소스는 액세스되지 않거나 VPN을 통해 제한될 수 있습니다.

[![시나리오 다이어그램](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>사용 시기

다음 배포 모델을 고려해 보십시오.

* 개념 증명, 파일럿 및 현장 서비스 배포
* [Remote Assist](hololens2-options-remote-assist.md) 배포

### <a name="basic-common-configurations"></a>기본 일반 구성

* Wi-Fi 네트워크는 일반적으로 인터넷 및 클라우드 서비스에 완전히 열려 있습니다.
* MDM(모바일 장치 관리) 자동 등록을 사용하여 Azure AD 조인--MDM(Intune) 관리
* 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
  * 지원되는 디바이스당 단일 또는 여러 사용자
* 디바이스 잠금 구성의 다양한 수준은 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용됩니다.
* MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.

### <a name="common-challenges"></a>일반적인 과제

* 시나리오 요구 사항에 따라 HoloLens 2 적용할 MDM 구성 결정

해당 클라우드 연결 가이드에서는 디바이스 관리에 HoloLens 2 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 디바이스 설정 시 Remote Assist 즉시 사용할 수 있는지 확인하는 방법을 설명합니다.

> [!div class="nextstepaction"]
> [클라우드 연결 배포 가이드](hololens2-cloud-connected-overview.md)

단기 또는 장기 외부 사용을 위해 외부 클라이언트 가이드를 사용하여 원격 사이트에 디바이스를 배포합니다.

> [!div class="nextstepaction"]
> [클라우드 연결(외부 클라이언트) 배포 가이드](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>시나리오 B: 조직의 네트워크 내에 배포

이 시나리오는 대부분의 Windows 10 PC에 대한 클래식 배포와 동일합니다. HoloLens 2 주로 회사 네트워크에서 내부 회사 리소스에 액세스할 수 있도록 배포됩니다. 인터넷 및 클라우드 서비스가 제한될 수 있습니다. 

[![시나리오 B1 다이어그램](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![시나리오 B2 다이어그램](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>사용 시기

다음 배포 모델을 고려해 보십시오.

* 내부 사용자
* 회사 환경 내에서 대규모(파일럿 및 프로덕션) 배포

### <a name="basic-common-configurations"></a>기본 일반 구성

* Wi-Fi 네트워크는 내부 리소스에 액세스하고 인터넷 또는 클라우드 서비스에 대한 액세스가 제한된 내부 회사 네트워크입니다.
* MDM 자동 등록을 사용하여 Azure AD 조인
* MDM(Intune) 관리
* 사용자가 자신의 회사 계정(Azure AD)으로 로그인합니다.
  * 지원되는 디바이스당 단일 또는 여러 사용자
* 디바이스 잠금 구성의 다양한 수준은 완전 열기에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용됩니다.
* MDM을 통해 하나 이상의 애플리케이션이 배포됩니다.

### <a name="common-challenges"></a>일반적인 과제

* HoloLens 2 온-프레미스 AD 조인 또는 SCCM(System Center Configuration Manager)을 지원하지 않습니다. MDM과 Azure AD 조인만 가능합니다. 오늘날 많은 회사는 SCCM에서 관리하는 온-프레미스 AD 조인 디바이스와 같이 이 시나리오에서 여전히 Windows 10 PC를 배포하며, 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 디바이스를 관리하기 위해 인프라를 배포/구성하지 않을 수 있습니다.
* HoloLens 2 클라우드 우선 디바이스이므로 사용자 인증, OS 업데이트, MDM 관리 등을 위해 인터넷 및 클라우드 연결 서비스에 크게 의존합니다. 회사 네트워크에 연결할 때 프록시/방화벽 규칙을 조정하여 HoloLens 2 및 해당 네트워크에서 실행되는 애플리케이션에 액세스할 수 있도록 해야 합니다.
* 회사 Wi-Fi 연결에는 일반적으로 네트워크에 대한 디바이스 또는 사용자를 인증하기 위한 인증서가 필요합니다. MDM을 통해 Windows 10 디바이스에 인증서를 배포하는 데 필요한 인프라 또는 설정은 구성하기 어려울 수 있습니다.

해당 회사 연결 가이드에서는 디바이스를 설정한 후 기존 디바이스 관리에 HoloLens 2 등록하고, 필요에 따라 라이선스를 적용하고, 최종 사용자가 Dynamics 365 가이드를 작동하고 사용자 지정 기간 업무 앱을 사용할 수 있는지 확인하는 방법을 설명합니다.

> [!div class="nextstepaction"]
> [회사 연결 배포 가이드](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>시나리오 C: 안전한 오프라인 환경에 배포

이는 매우 안전한 위치 또는 기밀 위치에 대한 일반적인 배포입니다. HoloLens 2 네트워크 또는 인터넷 액세스 없이 주로 오프라인에서 사용하도록 배포됩니다.

[![오프라인 보안 다이어그램 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>사용 시기

다음 배포 모델을 고려해 보십시오.

* 데이터를 사내에 보존해야 하는 매우 안전한 환경
* 공용에서 디바이스를 사용하는 "환경"
* 원격 영역의 인터넷 연결 문제

### <a name="basic-common-configurations"></a>기본 일반 구성

* Wi-Fi 연결을 사용할 수 없습니다. 필요한 경우 USB를 통한 이더넷에서 LAN 연결을 사용하도록 설정할 수 있습니다.
* 관리되지 않음
* 디바이스 로그인에 대한 로컬 사용자 계정
  * HoloLens 2 하나의 로컬 계정만 지원합니다.
* 디바이스 잠금 구성의 다양한 수준은 특정 사용 사례에 따라 프로비전 패키지를 통해 적용됩니다. 이러한 구성은 일반적으로 보안 환경 요구 사항으로 인해 제한됩니다.
* 하나 이상의 애플리케이션이 프로비전 패키지를 통해 배포됩니다.

### <a name="common-challenges"></a>일반적인 과제

* 프로비전 패키지를 통해 사용할 수 있는 제한된 구성 집합이 있습니다.
* 클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능이 제한됩니다.
* 이러한 디바이스를 수동으로 설정, 구성 및 업데이트해야 하기 때문에 관리 오버헤드가 높아집니다.

해당 오프라인 보안 가이드에서는 보안 환경에서 사용하기 위해 HoloLens 2 잠그는 샘플 프로비전 패키지를 적용하기 위한 지침을 제공합니다.

> [!div class="nextstepaction"]
> [오프라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)
