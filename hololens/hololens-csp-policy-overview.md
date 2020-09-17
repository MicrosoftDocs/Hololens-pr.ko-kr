---
title: Csp 및 장치 관리 개요 구성
description: Csp, 정책 및 장치 관리를 구성 하는 방법
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016800"
---
# Csp 및 장치 관리 개요 구성

IT 관리자는 HoloLens 2에서 정책 설정을 정의 하 고 구현할 수 있습니다. 사용할 구성 설정은 배포 시나리오에 따라 다르며, IT 부서에 가장 광범위한 제어 범위를 제공하는 것은 회사 장치입니다. Windows 10의 경우 CSP (구성 서비스 공급자)는 디바이스에서 구성 설정을 읽고, 설정, 수정 또는 삭제 하는 인터페이스입니다. 이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다. 일부 구성 서비스 공급자는 WAP 형식, 일부 지원, 그리고 두 가지를 모두 지원 합니다. 

Windows 10 홀로그램 장치 관리 Csp에 대 한 자세한 내용은 [HoloLens 장치에서 지원 되는 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)의 전체 목록을 참조 하세요. IT 관리자는 디바이스에서 정책 CSP를 관리할 수도 있으며, [HoloLens 2에서 지원 되는 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)csp의 전체 목록을 참조 하세요.

## 구성 방법

### MDM으로 구성
사용자는 MDM 시스템에 등록 된 개인 또는 회사 장치에서 Csp 및 정책을 쉽게 관리할 수 있습니다. 장치가 MDM 솔루션에 등록 되 면 장치 구성을 사용 하 여 해당 장치 또는 장치 집합을 관리할 수 있습니다. [MDM을 통해 HoloLens 장치를 관리](hololens-mdm-configure.md)하는 방법에 대해 자세히 알아보세요.

### 배포 패키지를 사용 하 여 구성
HoloLens 2는 또한 사용자 지정 프로비저닝 패키지를 통해 HoloLens 2 장치에 대해 제한 된 CSP 구성 집합을 설정 하는 것을 지원 합니다. 일반적으로 프로 비전 패키지는 MDM이 아닌 관리 장치에 활용 되며 각 장치에 수동으로 적용 해야 합니다. [HoloLens에 대 한 사용자 지정 프로비저닝 패키지](https://docs.microsoft.com/hololens/hololens-provisioning)빌드에 대 한 정보를 읽어 보세요. 

## 구성 

### 일반적인 장치 제한 사항
일부 장치 제한은 간단 하며 장치에 대 한 기능 또는 연결을 비활성화 합니다. [일반적인 장치 제한 사항](hololens-common-device-restrictions.md) 에 대 한 자세한 내용은 다음을 참고 하세요.

### 키오스크 모드
키오스크 모드를 사용 하 여 기본적으로 어떤 앱에 액세스할 수 있는 id를 제어 합니다. 키오스크는 단일 앱 또는 여러 앱 UI 환경에 사용할 수 있습니다. 키오스크 구성은 장치를 사용 하는 모든 사용자가 다른 그룹에 대 한 앱을 다양 하 게 선택 하는 단일 앱의 범위입니다. 이는 다른 앱을 실행 하는 것이 아니라 "허용 된 앱"이 중지 되지 않도록 하는 것입니다. 자세한 내용은 [키오스크 모드 및 사용 방법에 대 한 읽기 시작](hololens-kiosk.md)을 참조 하세요.

### 설정 페이지 표시 여부
설정 앱 정책을 사용 하 여 기본적으로 설정에 액세스할 수 있는 id를 제어 합니다. 이 정책에서는 설정 앱을 구성 하 여 선택 페이지만 표시 하거나 선택한 모든 페이지를 숨길 수 있습니다. [사용 가능한 페이지를 구성 하는 방법에 대해 자세히](settings-uri-list.md)알아보세요.

이 기능은 현재 [Windows 참가자 빌드](hololens-insider.md)에만 avalible. 이를 사용 하려는 장치가 빌드 19041.1349 +에 있는지 확인 하세요.

### 설정만
WDAC 구성을 사용 하 여 시스템이 키오스크 모드 인지 여부에 관계 없이 실행할 수 있거나 허용 되지 않는 앱/프로세스를 제어 합니다.
[WDAC에 대 한 개요를 참조 하세요.](windows-defender-application-control-wdac.md)
