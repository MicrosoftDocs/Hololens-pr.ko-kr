---
title: Windows Holographic for Business 기능 잠금 해제
description: 비즈니스용 Windows 홀로그램으로 업그레이드 하는 경우 HoloLens는 비즈니스용으로 설계 된 추가 기능을 제공 합니다.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829337"
---
# Windows Holographic for Business 기능 잠금 해제

> [!IMPORTANT]
> 이 페이지는 HoloLens 1 Gen에만 적용 됩니다.

Microsoft HoloLens는 Windows 홀로그램 (HoloLens 용으로 디자인 된 Windows 10 버전)를 실행 하는 *개발 판*에서 사용할 수 있으며, 상업적으로 설계 되는 추가 기능을 제공 하는 [상업용 제품군](hololens-commercial-features.md)입니다.

Commercial Suite를 구입하면 Windows Holographic을 비즈니스용 Windows Holographic으로 업그레이드하는 라이선스를 받습니다. 조직의 [MDM (모바일 디바이스 관리) 공급자나](#edition-upgrade-by-using-mdm) [배포 패키지](#edition-upgrade-by-using-a-provisioning-package)를 사용 하 여 디바이스에이 라이선스를 적용할 수 있습니다.

> [!TIP]
> Windows 10 버전 1803에서 **설정**시스템을 선택 하 여 HoloLens가 business edition으로 업그레이드 되었는지 확인할 수 있습니다  >  **System**.

## MDM을 사용 하 여 버전 업그레이드

[WindowsLicensing CSP(구성 서비스 공급자)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)를 지원하는 모든 MDM 공급자는 엔터프라이즈 라이선스가 적용됩니다. 최신 버전의 Microsoft MDM API는 WindowsLicensing CSP를 지원합니다.

Microsoft Intune을 사용 하 여 HoloLens 업그레이드에 대 한 단계별 지침은 [Windows 홀로그램를 실행 하는 장치를 비즈니스용 Windows 홀로그램으로 업그레이드](https://docs.microsoft.com/intune/holographic-upgrade)를 참조 하세요.

 다른 MDM 공급자에서 정책을 설정 및 배포하는 특정 단계는 다를 수 있습니다.

## 배포 패키지를 사용 하 여 버전 업그레이드

프로비저닝 패키지는 지정한 구성을 장치에 적용하는 Windows 구성 디자이너 도구에서 생성된 파일입니다.

### Windows Holographic 버전을 업그레이드하는 프로비저닝 패키지 만들기

1. [HoloLens용 프로비저닝 패키지를 만듭니다.](hololens-provisioning.md)
1. **런타임 설정** > **EditionUpgrade**로 이동하고 **EditionUpgradeWithLicense**를 선택합니다.

    ![라이선스로 버전 업그레이드 선택됨](images/icd1.png)

1. 상업용 제품군을 구입할 때 제공 된 XML 라이선스 파일을 찾습니다.

    > [!NOTE]
    > [프로비저닝 패키지의 추가 설정](hololens-provisioning.md)을 구성할 수 있습니다.

1. **파일** 메뉴에서 **저장**을 선택 합니다. 

1. 프로젝트 파일에 중요 한 정보가 포함 될 수 있다는 경고를 읽고 **확인**을 클릭 합니다.

    > [!IMPORTANT]
    > 배포 패키지를 빌드할 때 프로젝트 파일과 프로비저닝 패키지 (ppkg) 파일에 중요 한 정보가 포함 될 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 프로젝트 파일을 안전한 위치에 저장 하 고 더 이상 필요 하지 않을 경우 프로젝트 파일을 삭제 해야 합니다.

1. **내보내기** 메뉴에서 **프로비저닝 패키지**를 선택합니다.

1. 이 프로 비전 패키지의 우선 순위를 다른 원본에서이 디바이스에 적용 한 다른 사용자 보다 높게 설정 하 고 **다음**을 선택 하 여 **IT 관리자로** **소유자** 를 변경 합니다.

1. **패키지 버전**에 대한 값을 설정합니다.

    > [!TIP]
    > 기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

1. **배포 패키지에 대 한 보안 세부 정보 선택**에서 **다음**을 선택 합니다.

1. **다음** 을 선택 하 여 배포 패키지가 빌드될 때 사용할 출력 위치를 지정 합니다. 기본적으로 Windows ICD에서는 프로젝트 폴더를 출력 위치로 사용합니다.

    필요에 따라 **찾아보기를** 선택 하 여 기본 출력 위치를 변경할 수 있습니다.

1. **다음**을 선택합니다.

1. **빌드** 를 선택 하 여 패키지 빌드를 시작 합니다. 빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.

1. 빌드가 완료 되 면 **마침을**선택 합니다.

### HoloLens에 프로비저닝 패키지 적용

1. USB 케이블을 사용 하 여 장치를 PC에 연결 합니다. 장치를 시작 하지만 초기 설정 환경의 **맞춤** 페이지 (파란색 상자를 사용 하는 첫 페이지) 이상으로 계속 진행 하지 마십시오. PC에서 HoloLens는 파일 탐색기의 장치로 표시 됩니다.

    > [!NOTE]
    > HoloLens 장치에 Windows 10, 버전 1607이 실행 되 고 있는 경우 장치에서 **볼륨 아래로** 및 **전원** 단추를 잠시 눌렀다가 놓는 방법으로 파일 탐색기를 엽니다.

1. 파일 탐색기에서 프로비저닝 패키지(.ppkg)를 장치 저장소로 끌어 놓습니다.

1. HoloLens가 여전히 **맞춤** 페이지에 있는 동안 **볼륨** 을 길게 눌렀다가 **Power** button을 다시 동시에 놓습니다.

1. HoloLens는 패키지를 신뢰 하 고 적용 하 고 싶은 것인지 묻습니다. 패키지를 신뢰한다고 확인합니다.

1. 패키지가 성공적으로 적용되었는지 여부가 표시됩니다. 성공적으로 적용 되지 않은 경우 패키지를 수정 하 고 다시 시도해 볼 수 있습니다. 성공할 경우 장치 설정으로 진행 합니다.
