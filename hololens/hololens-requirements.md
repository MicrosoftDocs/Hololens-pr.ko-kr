---
title: 일반 배포 시나리오
description: 인프라, Azure Active Directory 및 모바일 장치 관리를 포함 하 여 엔터프라이즈 환경에서 HoloLens 배포 및 관리에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033829"
---
# <a name="common-deployment-scenarios"></a>일반 배포 시나리오

## <a name="overview"></a>개요

처음으로 사용해 볼 때 새 장치를 배포 하는 방법을 파악 하는 것이 더 나을 수 있습니다. 여기서는 조직 내에서 Microsoft HoloLens 2 장치를 배포 하 고 관리 하는 다양 한 방법을 공유 합니다.

솔루션을 대규모로 배포 하려고 합니다. 사용자의 도움을 받고 싶습니다. 먼저, D365 원격 지원, 가이드 또는 만든 Azure mixed reality 서비스 사용 응용 프로그램을 사용 하 든 관계 없이 대상 혼합 현실 시나리오에 대 한 가치를 얻기 위해 장치를 배포 하는 단계에 대해 설명 하겠습니다.

조직 내에서 HoloLens를 채택 하려는 비즈니스 의사 결정자, IT 전문가 또는 혁신 팀 일 수 있습니다. 개념 증명에서 크기 조정 된 배포에 대해 구축 하는 경우 배포 가이드는 규모에 관계 없이 IT 인프라 내에서 HoloLens을 의미 합니다. 가장 일반적인 배포 시나리오는 다음과 같습니다.

| 시나리오 |사용량 | 핵심 내용 |
|---------|---------|---------|
| [시나리오 A: 클라우드 연결 장치](hololens2-cloud-connected-overview.md) | 배포를 처음 시작 하는 경우 small을 시작 하 고 클라우드로 연결 된 단일 장치를 배포 하 여 기본 프로세스를 확인할 수 있습니다. | 장치가 클라우드 서비스 및 공용 인터넷에 연결 됩니다. 이는 고객 사용 사례, 현장 서비스 및 개념 증명에 가장 적합 합니다.|
| [시나리오 B: 조직의 네트워크](hololens2-corp-connected-overview.md) | 대규모로 프로덕션에 배포 하는 경우 조직의 네트워크와 통합 해야 할 수 있습니다. | 장치가 "회사" wi-fi 네트워크에 연결 됩니다. 이는 내부 사용자 또는 회사 환경 내에서 사용 하기에 가장 적합 합니다.|
| [시나리오 C: 오프 라인 보안 환경](hololens-common-scenarios-offline-secure.md) | 일부 업무상 중요 한 프로세스 또는 일부 회사 정책은 오프 라인 환경 사용을 요구할 수 있습니다. | 장치는 매우 제한적인 네트워크에 연결 되거나, 순수 하 게 오프 라인 장치입니다. 이는 보안 수준이 높은 환경 또는 원격 영역에서 인터넷 연결 제한에 가장 적합 합니다. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>시나리오 A: 클라우드 연결 장치에 배포

이 시나리오는 회사 내에서 관리 되는 모바일 장치를 배포 하는 것과 유사 합니다. HoloLens 2는 주로 회사 네트워크 외부 환경에서 사용할 수 있도록 배포 됩니다. 회사 리소스에 액세스 하지 않거나 VPN을 통해 제한할 수 있습니다.

[![시나리오 다이어그램입니다.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>사용 시기

다음에 대 한 배포 모델을 고려 합니다.

* 개념 증명, 파일럿 및 현장 서비스 배포
* [원격 지원](hololens2-options-remote-assist.md) 배포

### <a name="basic-common-configurations"></a>기본 일반 구성

* 일반적으로 인터넷 및 클라우드 서비스에 대 한 Wi-Fi 네트워크가 완전히 열립니다.
* MDM (모바일 장치 관리) 자동 등록을 사용 하는 Azure AD 조인--MDM (Intune) 관리
* 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
  * 지원 되는 장치 당 단일 또는 여러 사용자
* 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.
* MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.

### <a name="common-challenges"></a>일반적인 문제

* 시나리오 요구 사항에 따라 HoloLens 2에 적용할 MDM 구성 결정

해당 클라우드 연결 가이드에서는 장치 관리에 HoloLens 2를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치 설치 시 원격 지원을 즉시 사용할 수 있는지 확인 하는 방법에 대해 설명 합니다.

> [!div class="nextstepaction"]
> [클라우드 연결 배포 가이드](hololens2-cloud-connected-overview.md)

외부 클라이언트 가이드를 사용 하 여 단기 또는 장기 외부 사용을 위해 원격 사이트에 장치를 배포할 수 있습니다.

> [!div class="nextstepaction"]
> [클라우드 연결 (외부 클라이언트) 배포 가이드](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>시나리오 B: 조직의 네트워크 내에 배포

이 시나리오는 대부분의 Windows 10 pc에 대 한 클래식 배포와 동일 합니다. HoloLens 2는 주로 회사 네트워크에서 내부 회사 리소스에 대 한 액세스 권한이 있는 회사 네트워크에서 사용할 수 있도록 배포 됩니다. 인터넷 및 클라우드 서비스를 제한할 수 있습니다. 

[![시나리오 B1 다이어그램](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![시나리오 B2 다이어그램.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>사용 시기

다음에 대 한 배포 모델을 고려 합니다.

* 내부 사용자
* 회사 환경 내에서 대규모로 배포 (파일럿 및 프로덕션)

### <a name="basic-common-configurations"></a>기본 일반 구성

* Wi-Fi 네트워크는 내부 리소스에 대 한 액세스 권한이 있는 회사 내부 네트워크 이며 인터넷 또는 클라우드 서비스에 대 한 제한 된 액세스입니다.
* MDM 자동 등록을 사용 하는 Azure AD 조인
* MDM (Intune) 관리
* 사용자가 자신의 회사 계정 (Azure AD)으로 로그인
  * 지원 되는 장치 당 단일 또는 여러 사용자
* 다양 한 수준의 장치 잠금 구성은 완전히 열린 앱에서 단일 앱 키오스크까지 특정 사용 사례에 따라 적용 됩니다.
* MDM을 통해 하나 이상의 응용 프로그램을 배포 합니다.

### <a name="common-challenges"></a>일반적인 문제

* HoloLens 2은 온-프레미스 AD 조인 또는 System Center Configuration Manager (SCCM)를 지원 하지 않습니다. MDM을 사용 하는 Azure AD 조인만 오늘날 대부분의 기업은이 시나리오에서 Windows 10 pc를 아직 배포 하 고 있으며,이는 SCCM에서 관리 되는 온-프레미스 AD 조인 된 장치로, 클라우드 기반 MDM 솔루션을 통해 내부 Windows 10 장치를 관리 하기 위해 인프라를 배포/구성 하지 않을 수 있습니다.
* HoloLens 2은 클라우드 우선 장치 이며, 사용자 인증, OS 업데이트, MDM 관리 등에 대해 인터넷 및 클라우드 연결 된 서비스에 크게 의존 합니다. 회사 네트워크에 연결 하는 경우 HoloLens 2 및 해당 응용 프로그램에서 실행 되는 응용 프로그램에 대 한 액세스를 가능 하 게 하기 위해 프록시/방화벽 규칙을 조정 해야 할 수 있습니다.
* 회사 Wi-Fi 연결에는 일반적으로 네트워크에 대 한 장치 또는 사용자를 인증 하기 위한 인증서가 필요 합니다. MDM을 통해 Windows 10 장치에 인증서를 배포 하는 데 필요한 인프라 또는 설정은 구성 하기가 어려울 수 있습니다.

해당 회사 연결 가이드에서는 기존 장치 관리에 HoloLens 2를 등록 하 고, 필요에 따라 라이선스를 적용 하 고, 최종 사용자가 장치를 설정한 후 사용자 지정 lob (기간 업무) 앱을 사용할 365 수 있는지 확인 하는 방법에 대해 설명 합니다.

> [!div class="nextstepaction"]
> [회사에 연결 된 배포 가이드](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>시나리오 C: 보안 오프 라인 환경에서 배포

이는 보안 수준이 높은 또는 기밀 위치의 일반적인 배포입니다. HoloLens 2는 네트워크 또는 인터넷에 액세스 하지 않고 주로 오프 라인으로 사용할 수 있도록 배포 됩니다.

[![오프 라인 보안 다이어그램 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>사용 시기

다음에 대 한 배포 모델을 고려 합니다.

* 데이터를 보관 해야 하는 매우 안전한 환경
* 공용에서 장치를 사용 하는 "환경"
* 원격 영역에서 인터넷 연결 문제

### <a name="basic-common-configurations"></a>기본 일반 구성

* Wi-Fi 연결을 사용할 수 없습니다. 필요한 경우 USB를 통한 이더넷 LAN 연결을 사용 하도록 설정할 수 있습니다.
* 관리 되지 않음
* 장치 로그인에 대 한 로컬 사용자 계정
  * HoloLens 2는 로컬 계정을 하나만 지원 합니다.
* 다양 한 수준의 장치 잠금 구성은 특정 사용 사례에 따라 프로 비전 패키지를 통해 적용 됩니다. 이러한 구성은 보안 환경 요구 사항으로 인해 일반적으로 제한 됩니다.
* 프로 비전 패키지를 통해 하나 이상의 응용 프로그램을 배포 합니다.

### <a name="common-challenges"></a>일반적인 문제

* 프로 비전 패키지를 통해 사용할 수 있는 제한 된 구성 집합이 있습니다.
* 클라우드 서비스를 사용할 수 없으므로 HoloLens 2 기능이 제한 됩니다.
* 이러한 장치를 수동으로 설정 하 고 구성 하 고 업데이트 해야 하기 때문에 관리 오버 헤드가 더 높습니다.

해당 오프 라인 보안 가이드에서는 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로 비전 패키지를 적용 하기 위한 지침을 제공 합니다.

> [!div class="nextstepaction"]
> [오프라인 보안 환경 배포 가이드](hololens-common-scenarios-offline-secure.md)
