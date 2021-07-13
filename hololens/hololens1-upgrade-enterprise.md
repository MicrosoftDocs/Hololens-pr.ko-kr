---
title: Windows Holographic for Business 기능 잠금 해제
description: Windows Holographic for Business 업그레이드하는 경우 HoloLens 비즈니스용으로 설계된 추가 기능을 제공합니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635197"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Windows Holographic for Business 기능 잠금 해제

> [!IMPORTANT]
> 이 페이지는 HoloLens 1세대에만 적용됩니다.

Microsoft HoloLens Holographic(HoloLens 위해 설계된 Windows 10 버전)Windows 실행되는 *Development Edition* 및 비즈니스용으로 설계된 추가 기능을 제공하는 [Commercial Suite에서](hololens-commercial-features.md)사용할 수 있습니다.

Commercial Suite를 구매하면 holographic을 Windows Windows Holographic for Business 업그레이드하는 라이선스가 제공됩니다. 조직의 [MDM(모바일 디바이스 관리) 공급자](#edition-upgrade-by-using-mdm) 또는 [프로비전 패키지를](#edition-upgrade-by-using-a-provisioning-package)사용하여 디바이스에 이 라이선스를 적용할 수 있습니다.

> [!TIP]
> Windows 10 버전 1803에서는 설정 시스템을 선택하여 HoloLens 비즈니스 버전으로 업그레이드되었는지 확인할 수   >  있습니다.

## <a name="edition-upgrade-by-using-mdm"></a>MDM을 사용하여 버전 업그레이드

엔터프라이즈 라이선스는 [WindowsLicensing CSP(구성 서비스 공급자)를](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)지원하는 모든 MDM 공급자가 적용할 수 있습니다. 최신 버전의 Microsoft MDM API는 WindowsLicensing CSP를 지원합니다.

Microsoft Intune 사용하여 HoloLens 업그레이드하는 단계별 지침은 Windows [Holographic을 실행하는 디바이스를 Windows Holographic for Business](/intune/holographic-upgrade)참조하세요.

 다른 MDM 공급자에서는 정책을 설정하고 배포하기 위한 특정 단계가 다를 수 있습니다.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>프로비전 패키지를 사용하여 버전 업그레이드

프로비전 패키지는 디바이스에 지정된 구성을 적용하는 Windows 구성 디자이너 도구에서 만든 파일입니다.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Windows Holographic 버전을 업그레이드하는 프로비저닝 패키지 만들기

1. [HoloLens 대한 프로비저닝 패키지를 만듭니다.](hololens-provisioning.md)
1. **런타임 설정**  >  **버전업그레이드로** 이동하여 **EditionUpgradeWithLicense** 를 선택합니다.

    ![라이선스 설정이 선택된 버전 업그레이드](images/icd1.png)

1. Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾습니다.

    > [!NOTE]
    > [프로비전 패키지 에서 추가 설정을](hololens-provisioning.md)구성할 수 있습니다.

1. **파일** 메뉴에서 **저장** 을 선택합니다. 

1. 프로젝트 파일에 중요한 정보가 포함될 수 있다는 경고를 읽고 **확인을** 클릭합니다.

    > [!IMPORTANT]
    > 프로비전 패키지를 빌드할 때 프로젝트 파일 및 프로비전 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 프로젝트 파일을 안전한 위치에 저장하고 더 이상 필요하지 않은 경우 프로젝트 파일을 삭제해야 합니다.

1. **내보내기** 메뉴에서 **패키지 프로비저닝을** 선택합니다.

1. **소유자를** **IT 관리자로** 변경합니다. 이 프로비저닝 패키지의 우선 순위를 다른 원본에서 이 디바이스에 적용된 다른 패키지보다 높게 설정한 후 **다음을** 선택합니다.

1. **패키지 버전** 에 대한 값을 설정합니다.

    > [!TIP]
    > 기존 패키지를 변경하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

1. **프로비전 패키지에 대한 보안 세부 정보 선택에서** **다음을** 선택합니다.

1. **다음을** 선택하여 프로비전 패키지가 빌드된 후 이동하려는 출력 위치를 지정합니다. 기본적으로 Windows ICD는 프로젝트 폴더를 출력 위치로 사용합니다.

    필요에 따라 **찾아보기를** 선택하여 기본 출력 위치를 변경할 수 있습니다.

1. **다음** 을 선택합니다.

1. **빌드를** 선택하여 패키지 빌드를 시작합니다. 빌드 페이지에 프로젝트 정보가 표시되고 진행률 표시줄에 빌드 상태가 표시됩니다.

1. 빌드가 완료되면 **마침을** 선택합니다.

### <a name="apply-the-provisioning-package-to-hololens"></a>프로비전 패키지를 HoloLens 적용

1. USB 케이블을 사용하여 디바이스를 PC에 연결합니다. 디바이스를 시작하지만 초기 설정 환경의 **맞춤** 페이지(파란색 상자가 있는 첫 번째 페이지)를 지나서 계속 진행하지 않습니다. PC에서 HoloLens 파일 탐색기 디바이스로 표시됩니다.

    > [!NOTE]
    > HoloLens 디바이스가 Windows 10 버전 1607 이하를 실행하는 경우 디바이스에서 볼륨 **다운** 및 **전원** 단추를 동시에 누르고 해제하여 파일 탐색기 엽니다.

1. 파일 탐색기 프로비전 패키지(.ppkg)를 디바이스 스토리지로 끌어서 놓습니다.

1. HoloLens **여전히 적합** 페이지에 있는 동안 잠시 누르고 **볼륨 다운** 및 **전원** 단추를 동시에 해제합니다.

1. HoloLens 패키지를 신뢰하고 적용할지 묻는 메시지가 표시됩니다. 패키지를 신뢰하는지 확인합니다.

1. 패키지가 성공적으로 적용되었는지 여부가 표시됩니다. 성공적으로 적용되지 않은 경우 패키지를 수정하고 다시 시도할 수 있습니다. 성공하면 디바이스 설정을 계속 진행합니다.
