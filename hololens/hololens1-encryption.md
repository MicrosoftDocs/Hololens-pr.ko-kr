---
title: HoloLens BitLocker 암호화
description: Bitlocker 장치 암호화를 사용하도록 설정하여 HoloLens 혼합 현실 장치에 저장된 파일을 보호하는 방법을 배워야 합니다.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284029"
---
# HoloLens(1세대) BitLocker 암호화

HoloLens(1세대) 및 HoloLens 2는 모두 BitLocker를 사용하여 장치 암호화를 지원하나, HoloLens 2에서는 BitLocker가 항상 사용하도록 설정됩니다.

이 문서는 HoloLens(1세대)에서 BitLocker를 사용하도록 설정하고 관리하는 데 도움이 될 것입니다.

HoloLens(1세대)에서는 수동으로 또는 MDM(모바일 장치 관리)을 사용하여 BitLocker 장치 암호화를 사용하도록 설정할 수 있습니다. 다음 지침에 따라 [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) 장치 암호화를 사용하도록 설정하여 HoloLens에 저장된 파일 및 정보를 보호합니다. 장치 암호화는 BitLocker CSP(구성 서비스 공급자)의 [EncryptionMethodByDriveType 메서드 3에](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 해당하는 AES-CBC 128 암호화 방법을 사용하여 데이터를 보호하는 데 도움이 됩니다. 올바른 암호화 키(예: 암호)가 있는 직원은 암호를 해독하거나 데이터 복구를 수행할 수 있습니다.

## MDM을 사용하여 디바이스 암호화를 사용하도록 설정

MDM(모바일 장치 관리) 공급자를 사용하여 장치 암호화가 필요한 정책을 적용할 수 있습니다. 사용할 정책은 정책 CSP의 [Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 설정입니다.

[Microsoft Intune을 사용하여 장치 암호화를 사용하도록 설정하는 방법에 대한 지침을 참조하세요.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

다른 MDM 도구의 경우 MDM 공급자의 설명서의 지침을 참조하세요. MDM 공급자가 장치 암호화를 위해 사용자 지정 URI를 필요로 하는 경우 다음 구성을 사용합니다.

- **이름**: 사용자가 선택한 이름
- **설명**: 선택 사항
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **데이터 형식**: 정수
- **값**: `1`

## 프로비저닝 패키지를 사용하여 디바이스 암호화를 사용하도록 설정

프로비저닝 패키지는 지정한 구성을 장치에 적용하는 Windows 구성 디자이너 도구에서 생성된 파일입니다. 

### Windows Holographic 에디션을 업그레이드하고 암호화를 사용하는 프로비저닝 패키지 만들기

1. [HoloLens용 프로비저닝 패키지를 만듭니다.](hololens-provisioning.md)
1. **런타임 설정** > **정책** > **보안**으로 이동하여 **RequireDeviceEncryption**을 선택합니다.

    ![디바이스 암호화 설정을 예로 구성 필요](images/device-encryption.png)

1. Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾아야 합니다.

1. Commercial Suite를 구입했을 때 받은 XML 라이선스 파일을 찾아 선택합니다.
    > [!NOTE]
    > [프로비저닝 패키지의 추가 설정](hololens-provisioning.md)을 구성할 수 있습니다.

1. **파일** 메뉴에서 **저장**을 클릭합니다. 

1. 프로젝트 파일에 중요한 정보가 포함될 수 있는 경우를 설명하는 경고를 읽고 확인을 **클릭합니다.**

    > [!IMPORTANT]
    > 프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 프로젝트 파일을 안전한 위치에 저장하고 더 이상 필요하지 않는 경우 프로젝트 파일을 삭제해야 합니다.

1. **내보내기** 메뉴에서 **프로비저닝 패키지**를 클릭합니다.
1. **소유자**를 **IT 관리자**로 변경합니다. 이렇게 하면 이 프로비저닝 패키지의 우선 순위가 다른 소스에서 이 장치에 적용된 프로비저닝 패키지보다 더 높게 설정됩니다. 그런 후 **다음**을 선택합니다.
1. **패키지 버전**에 대한 값을 설정합니다.

    > [!TIP]
    > 기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

1. **프로비저닝 패키지에 대한 보안 정보 선택** 창에서 **다음**을 클릭합니다.
1. **다음**을 클릭하여 빌드가 끝난 프로비저닝 패키지를 저장할 출력 위치를 지정합니다. 기본적으로 Windows ICD에서는 프로젝트 폴더를 출력 위치로 사용합니다.

    필요한 경우 찾아보기를 클릭하여 기본 출력 위치를 변경할 수 있습니다.

1. **다음**을 클릭합니다.
1. 패키지 빌드를 시작하려면 **빌드**를 클릭합니다. 빌드 페이지에서 프로젝트 정보가 표시되며 진행률 표시줄은 빌드 상태를 나타냅니다.
1. 빌드가 완료되면 **마침**을 클릭합니다.

### HoloLens에 프로비저닝 패키지 적용

1. USB를 통해 PC에 장치를 연결하고 시작하되 초기 설정 환경의 **맞춤** 페이지(파란색 상자가 있는 첫 번째 페이지)까지 진행합니다.
1. **볼륨 작게** 단추 및 **전원** 단추를 동시에 잠시 눌렀다 놓습니다.
1. HoloLens는 PC의 파일 탐색기에서 장치로 표시됩니다.
1. 파일 탐색기에서 프로비저닝 패키지(.ppkg)를 장치 저장소로 끌어 놓습니다.
1. **맞춤** 페이지에 있는 동안 다시 **볼륨 작게** 단추 및 **전원** 단추를 동시에 잠시 누르고 놓습니다.
1. 장치에서 사용자에게 패키지를 신뢰할 수 있고 이를 적용할 것인지 묻습니다. 패키지를 신뢰한다고 확인합니다.
1. 패키지가 성공적으로 적용되었는지 여부가 표시됩니다. 실패한 경우 패키지 문제를 해결하고 다시 시도할 수 있습니다. 성공한 경우 디바이스 설정을 진행합니다.

> [!NOTE]
> 2016년 8월 이전에 구입한 장치인 경우 Microsoft 계정으로 장치에 로그인하여 최신 OS 업데이트를 다운로드한 다음 OS를 재설정하고 프로비저닝 패키지를 적용합니다.

## 장치 암호화 검증

HoloLens에서 암호화는 자동으로 적용됩니다. 디바이스 암호화 상태를 확인하려면:

- HoloLens에서 **설정** > **시스템** > **정보**로 이동합니다. 장치가 **암호화된** 경우 **BitLocker를** 사용할 수 있습니다. 

    ![BitLocker를 사용하도록 설정한 화면을 보여 주면](images/about-encryption.png)
