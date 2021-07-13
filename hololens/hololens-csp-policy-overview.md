---
title: CSP 및 디바이스 관리 구성 개요
description: 모바일 장치 관리 및 프로 비전 패키지를 사용 하 여 Csp, 정책 및 장치 관리를 구성 하는 방법을 알아봅니다.
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640460"
---
# <a name="configure-csps-and-device-management-overview"></a>CSP 및 디바이스 관리 구성 개요

IT 관리자는 HoloLens 2에서 정책 설정을 정의 하 고 구현할 수 있습니다. 사용 하는 구성 설정은 배포 시나리오에 따라 다르며, 회사 장치는 광범위 한 제어를 제공 합니다. Windows 10에서 CSP (구성 서비스 공급자)는 장치에서 구성 설정을 읽고, 설정 하거나, 수정 하거나, 삭제 하는 데 사용할 수 있는 인터페이스입니다. 이러한 설정은 레지스트리 키 또는 파일에 매핑됩니다. 일부 구성 서비스 공급자는 WAP 형식을 지원 하 고, 일부 지원 SyncML를 지원 하 고, 둘 다 지원 합니다.

Windows 10 Holographic 장치 관리 csp에 대 한 자세한 내용은 [HoloLens 장치에서 지원 되는 csp](/windows/client-management/mdm/configuration-service-provider-reference#hololens)의 전체 목록을 참조 하세요.
IT 관리자는 장치에서 정책 CSP를 관리할 수도 있습니다. [HoloLens 2에서 지 원하는 정책 csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2)의 전체 목록을 참조 하세요.

## <a name="configuration-methods"></a>구성 방법

### <a name="configure-with-mdm"></a>MDM을 사용 하 여 구성

MDM 시스템에 등록 된 개인 또는 회사 장치에서 Csp 및 정책을 쉽게 관리할 수 있습니다. 장치가 MDM 솔루션에 등록 되 면 장치 구성을 사용 하 여 장치 또는 장치 집합을 관리할 수 있습니다. [MDM을 통해 HoloLens 장치를 관리](hololens-mdm-configure.md)하는 방법에 대해 자세히 알아보세요.

### <a name="configure-with-provisioning-packages"></a>프로 비전 패키지를 사용 하 여 구성

HoloLens 2는 사용자 지정 프로 비전 패키지를 통해 HoloLens 2 장치에 대해 제한 된 CSP 구성 집합을 설정 하는 기능도 지원 합니다. 프로 비전 패키지는 일반적으로 비 MDM 관리 장치에 활용 되며 각 장치에 수동으로 적용 해야 합니다. [HoloLens에 대 한 사용자 지정 프로 비전 패키지](hololens-provisioning.md)작성에 대 한 정보를 참조 하세요.

## <a name="configurations"></a>구성

### <a name="common-device-restrictions"></a>일반적인 디바이스 제한 사항

일부 장치 제한은 간단 하 고 장치에 대 한 기능 또는 연결을 사용 하지 않도록 설정 합니다. 이에 대 한 자세한 내용은 [일반적인 장치 제한 사항을 참조 하세요.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>키오스크 모드

키오스크 모드를 사용 하 여 기본적으로 앱에 액세스할 수 있는 id를 제어 합니다. 키오스크는 단일 앱 또는 여러 앱 UI 환경에 사용할 수 있습니다. 키오스크 구성은 장치를 사용 하는 모든 사용자를 위해 단일 앱에서 다양 한 그룹에 대 한 다양 한 앱을 선택 하는 범위입니다. 키오스크 모드에서는 "허용 된 앱"이 다른 앱을 시작 하는 것을 중지 하지 않으며 의도 하지 않았습니다. [키오스크 모드 및 사용 방법에](hololens-kiosk.md)대해 자세히 알아보세요.

### <a name="settings-page-visibility"></a>설정 페이지 표시 유형

설정 앱 정책을 사용 하 여 기본적으로 설정에 액세스할 수 있는 id를 제어 합니다. 이 정책을 사용 하 여 선택 된 페이지만 표시 하거나 선택한 모든 페이지를 숨기도록 설정 앱을 구성할 수 있습니다. [사용 가능한 페이지를 구성 하는 방법을 참조](settings-uri-list.md)하세요.

이 기능은 현재 [Windows Insider 빌드에서만](hololens-insider.md)사용할 수 있습니다. 이 기능을 사용 하려는 장치가 빌드 19041.1349 +에 있는지 확인 합니다.

### <a name="wdac"></a>설정만

WDAC 구성을 사용 하 여 시스템이 키오스크 모드 인지 여부와 관계 없이 시작할 수 있거나 허용 되지 않는 앱/프로세스를 제어 합니다.
[WDAC에 대 한 개요를 참조 하세요.](windows-defender-application-control-wdac.md)
