---
title: CSP 및 장치 관리 구성 개요
description: 모바일 장치 관리 및 프로비저닝 패키지를 사용하여 CSP, 정책 및 장치 관리를 구성하는 방법을 학습합니다.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283249"
---
# CSP 및 장치 관리 구성 개요

IT 관리자는 HoloLens 2에서 정책 설정을 정의하고 구현할 수 있습니다. 사용할 구성 설정은 배포 시나리오에 따라 다르며, IT 부서에 가장 광범위한 제어 범위를 제공하는 것은 회사 장치입니다. Windows 10에서 CSP(구성 서비스 공급자)는 장치에서 구성 설정을 읽고, 설정하고, 수정하거나, 삭제할 수 있는 인터페이스입니다. 이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다. 일부 구성 서비스 공급자는 WAP 형식을 지원하고, 일부는 SyncML을 지원하며, 일부는 두 가지를 모두 지원합니다.

Windows 10 Holographic 장치 관리 CSP에 대한 자세한 내용은 HoloLens 장치에서 지원되는 [전체 CSP 목록을 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
IT 관리자는 장치에서 정책 CSP를 관리할 수 있습니다. [HoloLens 2에서](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)지원하는 정책 CSP의 전체 목록을 참조하세요.

## 구성 방법

### MDM으로 구성

CSP 및 정책은 MDM 시스템에 등록된 개인 또는 회사 장치에서 쉽게 관리할 수 있습니다. 장치가 MDM 솔루션에 등록된 후 장치 구성을 사용하여 해당 장치 또는 장치 집합을 관리할 수 있습니다. [MDM을 통해 HoloLens](hololens-mdm-configure.md)장치를 관리하는 방법에 대해 자세히 알아보습니다.

### 프로비저닝 패키지로 구성

HoloLens 2는 사용자 지정 프로비저닝 패키지를 통해 HoloLens 2 장치에 대한 제한된 CSP 구성 집합 설정도 지원합니다. 프로비저닝 패키지는 일반적으로 MDM이 아닌 관리 장치에 활용되고 각 장치에 수동으로 적용해야 합니다. [HoloLens용 사용자 지정 프로비저닝 패키지를 구축하는 데 대한 정보를 읽습니다.](https://docs.microsoft.com/hololens/hololens-provisioning)

## 구성

### 일반적인 장치 제한 사항

일부 장치 제한은 간단하며 디바이스에 대한 기능 또는 연결을 사용할 수 없습니다. 일반적인 장치 제한에 대해 자세히 [알아보고자 합니다.](hololens-common-device-restrictions.md)

### 키오스크 모드

키오스크 모드를 사용하여 기본적으로 어떤 앱에 액세스할 수 있는 ID를 제어합니다. 키오스크는 단일 앱 또는 여러 앱 UI 경험에 사용할 수 있습니다. 키오스크 구성은 디바이스를 사용하는 모든 사용자용 단일 앱부터 그룹마다 다른 앱 선택에까지 다양합니다. 키오스크 모드는 "허용된 앱"이 다른 앱을 시작하지 못하도록 중지하지는 않습니다. 키오스크 모드 및 사용 방법을 읽어 [자세히 알아보십시오.](hololens-kiosk.md)

### 설정 페이지 표시 여부

설정 앱 정책을 사용하여 기본적으로 설정에 액세스할 수 있는 ID를 제어합니다. 이 정책을 사용하여 선택 페이지만 표시하거나 선택한 모든 페이지를 숨기도록 설정 앱을 구성할 수 있습니다. [사용 가능한 페이지를 구성하는 방법을 읽어 읽습니다.](settings-uri-list.md)

이 기능은 현재 Windows [Insider 빌드에서만 사용할 수 있습니다.](hololens-insider.md) 이 기능을 사용하려는 디바이스가 빌드 19041.1349+에 있도록 합니다.

### WDAC

WDAC 구성을 사용하여 시스템이 키오스크 모드에 있는지 여부와는 무관하게 실행될 수 있는 앱/프로세스를 제어합니다.
[WDAC에 대한 개요를 참조하세요.](windows-defender-application-control-wdac.md)
