---
title: 상업적 환경에서 HoloLens 설정
description: 엔터프라이즈 환경에서 HoloLens를 배포 하 고 관리 하는 방법에 대해 자세히 알아보세요.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: 8aa8e0f679ad18a2e47f34c5f1233435a502dc0c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830132"
---
# 상용 환경에서 HoloLens 배포

상업용 설정의 배율에서 HoloLens를 배포 하 고 구성할 수 있습니다. 이 문서에서는 상업적 환경에서 HoloLens 장치를 배포 하는 방법에 대 한 지침을 제공 합니다. 이 가이드에서는 HoloLens에 대 한 기초적인 지식이 있다고 가정 합니다. [시작 가이드](hololens1-setup.md) 의 지침에 따라 처음으로 HoloLens를 설정 합니다.

이 문서는 또한 해킹을 회사 네트워크에서 안전 하 게 사용 하는 보안 팀이 평가한 것으로 가정 합니다. 자주 묻는 보안 질문은 [여기](hololens-faq-security.md) 에 나와 있습니다.

## 배포 단계 개요

1. [필요한 기능 결정](hololens-requirements.md#step-1-determine-what-you-need)
1. [필요한 라이선스 결정](hololens-licenses-requirements.md)
1. [HoloLens에 맞게 네트워크를 구성](hololens-commercial-infrastructure.md)합니다.
    1. 이 섹션에서는 방화벽에 허용 해야 하는 대역폭 요구 사항, URL 및 포트를 제공 합니다. Azure AD 지침; MDM (모바일 디바이스 관리) 지침 앱 배포/관리 지침 및 인증서 지침.
1. ) [배포 패키지를 사용 하 여 HoloLens 구성](hololens-provisioning.md)
1. [장치 등록](hololens-enroll-mdm.md)
1. [HoloLens에 대한 링 기반 업데이트 설정](hololens-updates.md)
1. [HoloLens에서 BitLocker 디바이스 암호화 사용](hololens-encryption.md)

## 1단계. 필요 사항 결정

환경에서 HoloLens를 배포 하기 전에 먼저 필요한 기능, 앱 및 id 유형을 결정 하는 것이 중요 합니다. 또한 보안 팀이 회사 네트워크에서 HoloLens 사용을 승인 했는지 확인 하는 것이 중요 합니다. 추가 보안 정보는 [자주 묻는 보안 질문](hololens-faq-security.md) 을 참조 하세요.

### Id 유형

장치에 로그인 하는 데 사용 되는 id 유형을 확인 합니다.

1. **로컬 계정:** 이 계정은 디바이스 (예: windows PC의 로컬 관리자 계정)에 대해 로컬입니다. 이렇게 하면 1 개의 사용자만이 장치에 로그인 할 수 있습니다.
2. **MSA:** 개인 계정 (예: outlook, hotmail, gmail, yahoo 등) 이렇게 하면 1 개의 사용자만이 장치에 로그인 할 수 있습니다.
3. Azure **AD (Active Directory) 계정:** Azure AD에서 만든 계정입니다. 이렇게 하면 회사에 HoloLens 장치를 관리할 수 있는 기능이 부여 됩니다. 이렇게 하면 여러 사용자가 HoloLens 1 Gen 상업용 Suite/HoloLens 2 장치에 로그인 할 수 있습니다.

Id 형식에 대 한 자세한 내용은 [HoloLens id](hololens-identity.md) 문서를 참조 하세요.

### 기능 유형

기능 요구 사항에 따라 필요한 HoloLens가 결정 됩니다. 일반적으로 고객 환경에 배포 되어 표시 되는 인기 기능 중 하나는 키오스크 모드입니다. HoloLens 주요 기능 목록과이를 지 원하는 HoloLens 버전을 [여기](hololens-commercial-features.md)에서 찾아볼 수 있습니다.

**키오스크 모드란?**

키오스크 모드는 사용자가 액세스할 수 있는 앱을 제한할 수 있는 방법입니다. 즉, 사용자가 특정 앱에만 액세스할 수 있습니다.

**어떤 키오스크 모드를 필요로 하나요?**

키오스크 모드에는 단일 앱과 다중 앱의 두 가지 유형이 있습니다. 단일 앱 키오스크 모드에서는 사용자가 앱 하나에만 액세스할 수 있으며, 다중 앱 키오스크 모드에서는 사용자가 여러 개의 지정 된 앱에 액세스할 수 있습니다. 회사에 적합 한 키오스크 모드를 결정 하려면 다음 두 가지 질문에 대 한 답변을 받아야 합니다.

1. **다른 사용자가 다양 한 경험/제한을 필요로 하나요?** 다음 예제를 참조 하세요. 사용자 A는 원격 지원에만 액세스할 수 있는 현장 서비스 엔지니어입니다. 사용자 B는 안내선에 대 한 액세스만 필요로 하는 trainee.
    1. 예를 들어, 다음이 필요 합니다.
        1. Azure AD 계정-장치에 로그인 하는 방법입니다.
        1. **다중 앱** 키오스크 모드입니다.
    1. 아니요, 질문을 두 번 진행 합니다.
1. **다중 앱 환경이 필요 한가요?**
    1. 예를 들어 **다중 앱** 키오스크 모드가 필요 합니다.
    1. 질문 1 및 2에 대 한 대답이 모두 아니요 이면 **단일 앱** 키오스크 모드를 사용할 수 있습니다.

**키오스크 모드를 구성 하는 방법:**

HoloLens에 대 한 키오스크 모드를 배포 하는 두 가지 주요 방법 ([프로비저닝 패키지](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 및 [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk))이 있습니다. 이러한 옵션은 문서 뒷부분에서 설명 합니다. 그러나 위의 링크를 사용 하 여이 문서의 각 섹션으로 이동할 수 있습니다.

### 앱 및 앱 관련 시나리오

이 문서에 있는 대부분의 단계는 다음 앱에도 적용 됩니다.

| 앱 | 앱 관련 시나리오 |
| --- | --- |
| 원격 지원 | [교차 테 넌 트 통신](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| 가이드  | *개봉박두* |
|사용자 지정 앱 | *개봉박두* |

### 등록 방법 결정

1. 배포 패키지의 보안 토큰을 사용 하 여 일괄 등록 합니다.  
  전문가: 가장 자동화 된 접근 방법입니다. \
  단점: 초기 서버 쪽 설정을 수행 합니다.  
1. 사용자 로그인에 대 한 자동 등록  
  전문가: 가장 쉬운 방법  
  단점: 프로 비전 패키지를 적용 한 후에 사용자가 설정을 완료 해야 합니다.
1. _권장 하지 않음_ -설정 후 수동으로 등록 합니다.  
  전문가: 설정 후 등록할 수 있습니다.  
  단점: 대부분의 수동 접근 방식 및 디바이스는 수동으로 등록할 때까지 중앙에서 관리할 수 없습니다.

  자세한 내용은 여기를 참조 [하세요](hololens-enroll-mdm.md) .

### 배포 패키지를 만들어야 하는지 결정

HoloLens 장치 (프로비저닝 패키지 및 MDMs)를 구성 하는 데는 두 가지 방법이 있습니다. MDM을 사용 하 여 HoloLens 장치를 구성 하는 것이 좋습니다. 하지만 배포 패키지를 사용 하는 것이 더 나은 경우도 몇 가지 시나리오가 있습니다.

1. OOBE (부재 중 경험)를 건너뛰기 위해 HoloLens를 구성 하려는 경우
1. 복잡 한 네트워크에서 인증서를 배포 하는 데 문제가 있습니다. 대부분의 경우에는 MDM을 사용 하 여 인증서를 배포할 수 있습니다 (복잡 한 환경에도 해당). 그러나 일부 시나리오에서는 인증서를 제공 하 여 프로비저닝 패키지를 배포 해야 합니다.

프로비저닝 패키지에 적용할 수 있는 일부 HoloLens 구성은 다음과 같습니다.

- 장치에 인증서 적용
- Wi-Fi 연결 설정
- 언어 및 로케일과 같이 자주 묻는 질문에 대한 사전 구성
- (HoloLens 2) 모바일 장치 관리에서 일괄 등록
- (HoloLens v1) 비즈니스용 Windows Holographic을 사용하도록 설정하는 키 적용

프로비저닝 패키지를 사용 하기로 결정 한 경우 [이 가이드](hololens-provisioning.md)를 따르세요.

## 지원 받기

Microsoft 지원 사이트를 통해 지원을 받으세요.

[파일 지원 요청](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
