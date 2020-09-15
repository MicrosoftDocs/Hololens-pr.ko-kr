---
title: 전체 할당된 액세스
description: 전체 할당된 액세스 키오스크에 OMA-URI를 사용하는 방법 안내
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, 할당된 액세스, 키오스크
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1a0a3eb8ef3d21b34e13711bcc890af57e5ae2c2
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902303"
---
# 전체 할당된 액세스 - 키오스크

이 기능은 시스템 수준에서 적용되고, 시스템의 ID에 대한 선호도가 없으며, 장치에 로그인하는 모든 사용자에게 적용되는 복수 앱 키오스크 모드로 HoloLens 2 장치를 구성합니다. 

> [!NOTE]
> 이 기능은 현재 Windows 참가자 빌드에서만 사용할 수 있습니다. HoloLens 릴리스로 일반에 제공되기 전에 이 기능을 시험삼아 사용해 보려면 [Windows 참가자](hololens-insider.md) 빌드에 대해 자세히 읽어보세요.
 
## Intune에서 이 기능을 사용하는 방법 

> [!NOTE]
> "<!-"(으)로 표시된 영역에 유의하세요. 이러한 영역을 사용하려면 기본 설정에 따라 수정해야 합니다. 

1.  다음과 같은 방법으로 사용자 지정 OMA URI 장치 구성 프로필을 만들어 HoloLens 장치 그룹에 적용합니다. ![Intune에서 전체 할당된 액세스 OMA-URI](images/global-assigned-access-omauri.png)

2.  값을 업데이트하고 다음 콘텐츠를 붙여넣습니다. 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Windows 구성 디자이너에서 이 기능을 사용하는 방법 
 
1.  XML 파일 형식으로 앞서 설명한 XML BLOB를 업데이트 및 저장합니다. 

2.  [프로비전 패키지를 사용하여 단일 앱 또는 복수 앱 키오스크 설정](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)의 단계, 특히 "프로비전 패키지 2단계 - 프로비전 패키지에 키오스크 구성 XML 파일 추가" 부분을 따르고 이전 단계에서 저장한 XML 파일을 참조합니다. 

## AAD 계정 또는 AAD 그룹 한 개를 제외한 모든 사용자에게 전역 할당이 적용되는 구성을 만들 수 있나요? 

예. 아래의 XML BLOB 예제를 참조하세요. 로그인한 사용자의 특정 프로필을 찾을 수 없는 경우 전체 할당된 액세스 프로필이 HoloLens에 적용되어 로그인한 사용자에 대한 기본 키오스크 모드 구성으로 됩니다. 다음은 사용할 XML BLOB의 예입니다. 

> [!NOTE]
> <!- 강조 표시된 영역에 유의하세요. 이러한 영역을 사용하려면 기본 설정에 따라 수정해야 합니다. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## 전체 할당된 액세스 프로필에서 DeviceOwners 제외

이 기능을 사용하면 Hololens에서 "[장치 소유자](security-adminless-os.md)"로 간주되는 사용자를 전체 할당된 액세스에서 제외할 수 있습니다. 이 기능을 이용하려면 다중 앱 키오스크 구성용 XML BLOB에서 강조 표시된 줄이 추가되었는지 확인합니다. 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
