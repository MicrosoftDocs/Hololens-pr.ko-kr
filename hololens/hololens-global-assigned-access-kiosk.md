---
title: 전역 할당 액세스
description: Intune 및 Windows 구성 디자이너와 함께 전역 할당 액세스 키오스크의 OMA-URI 사용 가이드를 시작하세요.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, 할당 액세스, 키오스크
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640426"
---
# <a name="global-assigned-access--kiosk"></a>전역 할당 액세스 - 키오스크

이 기능은 시스템 수준에서 적용 가능한 다중 앱 키오스크 모드에 대해 HoloLens 2 디바이스를 구성하고 시스템의 ID와 선호도가 없으며 디바이스에 로그인하는 모든 사람에게 적용됩니다.

> [!NOTE]
> 이 기능은 현재 Windows 참가자 빌드에서만 사용할 수 있습니다. HoloLens 릴리스로 일반에 제공되기 전에 이 기능을 시험 삼아 사용해 보려면 [Windows 참가자](hololens-insider.md) 빌드에 대해 자세히 읽어보세요.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Intune에서 전역 할당 액세스를 사용하는 방법

> [!NOTE]
> "<!-"로 표시된 영역에 유의하세요. 이러한 영역에서는 기본 설정에 따라 수정해야 합니다.

1. 다음과 같이 사용자 지정 OMA URI 디바이스 구성 프로필을 만들고 HoloLens 디바이스 그룹에 적용합니다.

    URI 값: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune의 전역 할당 액세스 OMA-URI](images/global-assigned-access-omauri.png)

2. 값의 경우 다음 콘텐츠를 업데이트하고 붙여넣습니다.

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Windows 구성 디자이너에서 전역 할당 액세스 사용 방법

1. 위에서 언급한 XML Blob을 업데이트하고 XML 파일로 저장합니다. 

2. [프로비전 패키지를 사용하여 단일 앱 또는 다중 앱 키오스크 설정](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)의 단계, 특히 "Prov. 패키지, 2단계 – 키오스크 구성 XML 파일을 프로비전 패키지에 추가" 섹션을 따르고 이전 단계에서 저장한 XML 파일을 참조하세요.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>전역이 모든 사람에게 적용되고 별도의 구성이 1개의 Azure AD 계정 또는 Azure AD 그룹에 적용되는 구성을 만들 수 있나요? 

예. 아래의 XML Blob 예를 참조하세요. 전역 할당 액세스 프로필은 로그인한 사용자에 대한 특정 프로필이 없는 경우 HoloLens에 적용되기 때문에 로그인한 사용자에 대한 기본 키오스크 모드 구성이 됩니다.
사용할 XML Blob의 예는 다음과 같습니다.

> [!NOTE]
> `<!-`로 표시된 강조 표시된 영역에 유의하세요. 이러한 영역에서는 기본 설정에 따라 수정해야 합니다.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>전역 할당 액세스 프로필에서 DeviceOwners 제외

이 기능을 사용하면 HoloLens에서 "[디바이스 소유자](security-adminless-os.md)"로 간주되는 사용자를 전역 할당 액세스에서 제외할 수 있습니다. 이 기능을 활용하려면 다중 앱 키오스크 구성을 위한 XML Blob에서 강조 표시된 줄이 추가되었는지 확인합니다.

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>추가 전역 할당 액세스 예

이는 사용자가 로그인할 때 설정 앱, 피드백 허브 및 Microsoft Edge가 있는 다중 앱 키오스크를 갖게 되는 전역 할당 액세스 키오스크의 예입니다.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

이 예는 디바이스 소유자를 제외하는 전역 할당 액세스 키오스크입니다. 다른 Azure AD 사용자가 로그인하면 설정 앱, 피드백 허브 및 Microsoft Edge가 있는 다중 앱 키오스크를 갖게 됩니다. 이 키오스크에는 잠금 화면에서 누구나 로그인할 수 있는 방문자 계정에 대한 보조 키오스크 구성도 포함됩니다. 사용자가 방문자 계정에 로그인하면 피드백 허브 앱만 있는 다중 앱 키오스크가 제공됩니다.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
