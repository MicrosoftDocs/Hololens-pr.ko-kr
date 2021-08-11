---
title: HoloLens BitLocker 암호화
description: BitLocker 디바이스 암호화를 사용하도록 설정하여 HoloLens 혼합 현실 디바이스에 저장된 파일을 보호하는 방법을 알아봅니다.
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
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b07bb87b34ec966472bcbde000106590570fd7e7063ab503724884fa266bb34
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662675"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens(1세대) BitLocker 암호화

HoloLens(1세대) 및 HoloLens 2 모두 BitLocker를 사용하여 디바이스 암호화를 지원합니다. 그러나 BitLocker는 항상 HoloLens 2 사용하도록 설정됩니다.

이 문서는 HoloLens(1세대)에서 BitLocker를 사용하도록 설정하고 관리하는 데 도움이 됩니다.

HoloLens(1세대)에서는 수동으로 또는 MDM(모바일 디바이스 관리)을 사용하여 BitLocker 디바이스 암호화를 사용하도록 설정할 수 있습니다. 다음 지침에 따라 [BitLocker 디바이스 암호화를](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) 사용하도록 설정하여 HoloLens 저장된 파일 및 정보를 보호합니다. 디바이스 암호화는 BitLocker CSP(구성 서비스 공급자)의 [EncryptionMethodByDriveType 메서드 3과](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 동일한 AES-CBC 128 암호화 방법을 사용하여 데이터를 보호하는 데 도움이 됩니다. 올바른 암호화 키(예: 암호)가 있는 직원은 암호를 해독하거나 데이터 복구를 수행할 수 있습니다.

## <a name="enable-device-encryption-using-mdm"></a>MDM을 사용하여 디바이스 암호화 사용

MDM(모바일 장치 관리) 공급자를 사용하여 디바이스 암호화가 필요한 정책을 적용할 수 있습니다. 사용할 정책은 정책 CSP의 [Security/RequireDeviceEncryption 설정입니다.](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption)

[Microsoft Intune 사용하여 디바이스 암호화를 사용하도록 설정하는 방법에 대한 지침을 참조하세요.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

다른 MDM 도구에 대한 지침은 MDM 공급자의 설명서를 참조하세요. MDM 공급자에 디바이스 암호화에 대한 사용자 지정 URI가 필요한 경우 다음 구성을 사용합니다.

- **이름:** 선택한 이름
- **설명:** 선택 사항
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **데이터 형식:** 정수
- **값**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>프로비전 패키지를 사용하여 디바이스 암호화 사용

프로비전 패키지는 디바이스에 지정된 구성을 적용하는 Windows 구성 디자이너 도구에서 만든 파일입니다. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Windows Holographic 버전을 업그레이드하고 암호화를 사용하도록 설정하는 프로비전 패키지 만들기

1. [HoloLens 대한 프로비전 패키지를 만듭니다.](hololens-provisioning.md)
1. **런타임 설정** 정책 보안 로 이동하여  >    >   **RequireDeviceEncryption을** 선택합니다.

    ![디바이스 암호화 설정이 '예'로 구성되어야 함](images/device-encryption.png)

1. Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾습니다.

1. Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾아 선택합니다.
    > [!NOTE]
    > [프로비전 패키지 에서 추가 설정을](hololens-provisioning.md)구성할 수 있습니다.

1. **파일** 메뉴에서 **저장** 을 클릭합니다. 

1. 프로젝트 파일에 중요한 정보가 포함될 수 있음을 설명하는 경고를 읽고 **확인을** 클릭합니다.

    > [!IMPORTANT]
    > 프로비전 패키지를 빌드할 때 프로젝트 파일 및 프로비전 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 프로젝트 파일을 안전한 위치에 저장하고 더 이상 필요하지 않은 경우 프로젝트 파일을 삭제해야 합니다.

1. **내보내기** 메뉴에서 **패키지 프로비저닝을** 클릭합니다.
1. **소유자를** **IT 관리자** 로 변경합니다. 이 프로비전 패키지의 우선 순위는 다른 원본에서 이 디바이스에 적용된 프로비저닝 패키지보다 높게 설정한 후 **다음을** 선택합니다.
1. **패키지 버전** 에 대한 값을 설정합니다.

    > [!TIP]
    > 기존 패키지를 변경하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

1. **프로비전 패키지에 대한 보안 세부 정보 선택에서** **다음을** 클릭합니다.
1. **다음** 을 클릭하여 프로비전 패키지가 빌드된 후 이동하려는 출력 위치를 지정합니다. 기본적으로 Windows ICD는 프로젝트 폴더를 출력 위치로 사용합니다.

    필요에 따라 찾아보기를 클릭하여 기본 출력 위치를 변경할 수 있습니다.

1. **다음** 을 클릭합니다.
1. **빌드를** 클릭하여 패키지 빌드를 시작합니다. 프로젝트 정보가 빌드 페이지에 표시되고 진행률 표시줄에 빌드 상태가 표시됩니다.
1. 빌드가 완료되면 **마침을** 클릭합니다.

### <a name="apply-the-provisioning-package-to-hololens"></a>프로비전 패키지를 HoloLens 적용

1. USB를 통해 디바이스를 PC로 커넥트 디바이스를 시작하지만 초기 설정 환경의 **맞춤** 페이지(파란색 상자가 있는 첫 번째 페이지)를 지나서 계속 진행하지 않습니다.
1. 볼륨 **다운** 및 **전원** 단추를 동시에 짧게 누르고 놓습니다.
1. HoloLens PC의 파일 탐색기 디바이스로 표시됩니다.
1. 파일 탐색기 프로비전 패키지(.ppkg)를 디바이스 스토리지로 끌어서 놓습니다.
1. **맞춤** 페이지에서 볼륨 **다운** 및 **전원** 단추를 동시에 다시 짧게 누르고 놓습니다.
1. 디바이스에서 패키지를 신뢰하고 적용할지 묻는 메시지가 표시됩니다. 패키지를 신뢰하는지 확인합니다.
1. 패키지가 성공적으로 적용되었는지 여부가 표시됩니다. 실패한 경우 패키지를 수정하고 다시 시도할 수 있습니다. 성공하면 디바이스 설정을 계속 진행합니다.

> [!NOTE]
> 2016년 8월 이전에 디바이스를 구매한 경우 Microsoft 계정 사용하여 디바이스에 로그인하고, 최신 OS 업데이트를 다운로드한 다음, 프로비전 패키지를 적용하기 위해 OS를 다시 설정해야 합니다.

## <a name="verify-device-encryption"></a>디바이스 암호화 확인

암호화는 HoloLens 자동입니다. 디바이스 암호화 상태를 확인하려면 다음을 수행합니다.

- HoloLens 설정   >  **시스템**  >  **정보로** 이동합니다. 디바이스가 **암호화된** 경우 **BitLocker를** 사용할 수 있습니다. 

    ![BitLocker를 사용하도록 설정된 화면 정보](images/about-encryption.png)
