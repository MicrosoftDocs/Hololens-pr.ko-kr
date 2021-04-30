---
title: HoloLens BitLocker 암호화
description: Bitlocker 장치 암호화를 사용 하 여 HoloLens mixed reality 장치에 저장 된 파일을 보호 하는 방법에 대해 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309066"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (첫 번째 Gen) BitLocker 암호화

HoloLens (첫 번째 gen) 및 HoloLens 2는 모두 BitLocker를 사용 하 여 장치 암호화를 지원 하지만, BitLocker는 항상 HoloLens 2에서 사용 하도록 설정 됩니다.

이 문서는 HoloLens (첫 번째 gen)에서 BitLocker를 사용 하도록 설정 하 고 관리 하는 데 도움이 됩니다.

HoloLens (첫 번째 gen)에서 BitLocker 장치 암호화를 수동으로 사용 하도록 설정 하거나 MDM (모바일 장치 관리)을 사용할 수 있습니다. 다음 지침에 따라 파일 및 HoloLens에 저장 된 정보를 보호 하기 위해 [BitLocker 장치 암호화](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) 를 사용 하도록 설정 합니다. 장치 암호화를 사용 하면 BitLocker 구성 서비스 공급자 (CSP)의 안 [Methodbydrivetype 메서드 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 에 해당 하는 AES cbc-mac 128 암호화 방법을 사용 하 여 데이터를 보호할 수 있습니다. 올바른 암호화 키 (예: 암호)가 있는 직원은 암호를 해독 하거나 데이터 복구를 수행할 수 있습니다.

## <a name="enable-device-encryption-using-mdm"></a>MDM을 사용 하 여 장치 암호화 사용

MDM (모바일 장치 관리) 공급자를 사용 하 여 장치 암호화가 필요한 정책을 적용할 수 있습니다. 사용할 정책은 정책 CSP의 [Security/RequireDeviceEncryption 설정](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 입니다.

[Microsoft Intune를 사용 하 여 장치 암호화 사용에 대 한 지침을 참조 하세요.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

기타 MDM 도구의 지침은 MDM 공급자 설명서를 참조 하세요. MDM 공급자에서 장치 암호화를 위한 사용자 지정 URI를 요구 하는 경우 다음 구성을 사용 합니다.

- **이름**: 선택한 이름입니다.
- **설명**: 선택 사항
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **데이터 형식**: integer
- **값**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>프로 비전 패키지를 사용 하 여 장치 암호화 사용

프로 비전 패키지는 지정 된 구성을 장치에 적용 하는 Windows 구성 디자이너 도구를 통해 생성 되는 파일입니다. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Windows Holographic edition을 업그레이드 하 고 암호화를 사용 하도록 설정 하는 프로 비전 패키지 만들기

1. [HoloLens의 프로 비전 패키지를 만듭니다.](hololens-provisioning.md)
1. **런타임 설정** 정책 보안으로 이동 하 여  >    >   **requiredeviceencryption** 을 선택 합니다.

    ![장치 암호화 설정을 예로 구성 해야 합니다.](images/device-encryption.png)

1. 상용 제품군을 구입할 때 제공 된 XML 라이선스 파일을 찾습니다.

1. 상용 제품군을 구입할 때 제공 된 XML 라이선스 파일을 찾아 선택 합니다.
    > [!NOTE]
    > [프로 비전 패키지에서 추가 설정을](hololens-provisioning.md)구성할 수 있습니다.

1. **파일** 메뉴에서 **저장** 을 클릭합니다. 

1. 프로젝트 파일에 중요 한 정보가 포함 될 수 있음을 설명 하는 경고를 읽고 **확인** 을 클릭 합니다.

    > [!IMPORTANT]
    > 프로 비전 패키지를 빌드할 때 프로젝트 파일 및 프로 비전 패키지 (ppkg) 파일에 중요 한 정보가 포함 될 수 있습니다. . Ppkg 파일을 암호화 하는 옵션이 있지만 프로젝트 파일은 암호화 되지 않습니다. 프로젝트 파일을 안전한 위치에 저장 하 고 더 이상 필요 하지 않은 경우 프로젝트 파일을 삭제 해야 합니다.

1. **내보내기** 메뉴에서 **패키지 프로 비전** 을 클릭 합니다.
1. **소유자** 를 **IT 관리자** 로 변경 합니다 .이 프로 비전 패키지의 우선 순위를 다른 원본에서이 장치에 적용 된 프로 비전 패키지 보다 높게 설정 하 고 **다음** 을 선택 합니다.
1. **패키지 버전** 에 대 한 값을 설정 합니다.

    > [!TIP]
    > 기존 패키지를 변경 하 고 버전 번호를 변경 하 여 이전에 적용 된 패키지를 업데이트할 수 있습니다.

1. **프로 비전 패키지에 대 한 보안 세부 정보 선택** 에서 **다음** 을 클릭 합니다.
1. **다음** 을 클릭 하 여 프로 비전 패키지를 빌드할 때 사용할 출력 위치를 지정 합니다. 기본적으로 Windows ICD는 프로젝트 폴더를 출력 위치로 사용 합니다.

    필요에 따라 찾아보기를 클릭 하 여 기본 출력 위치를 변경할 수 있습니다.

1. **다음** 을 클릭합니다.
1. **빌드** 를 클릭 하 여 패키지 빌드를 시작 합니다. 빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.
1. 빌드가 완료 되 면 **마침** 을 클릭 합니다.

### <a name="apply-the-provisioning-package-to-hololens"></a>HoloLens에 프로 비전 패키지 적용

1. USB를 통해 장치를 PC에 연결 하 고 장치를 시작 하지만 초기 설치 환경의 **맞춤** 페이지 (파란색 상자를 사용 하는 첫 페이지)를 계속 해 서 사용 하지 마십시오.
1. **볼륨** 을 잠시 누르고 **전원** 단추를 동시에 해제 합니다.
1. HoloLens는 PC의 파일 탐색기에 장치로 표시 됩니다.
1. 파일 탐색기에서 프로 비전 패키지 (ppkg)를 장치 저장소로 끌어 놓습니다.
1. **크기 조정** 페이지에서 **볼륨** 을 잠시 누르고 **전원** 단추를 동시에 다시 해제 합니다.
1. 패키지를 신뢰 하 고 해당 패키지를 적용할지 여부를 묻는 메시지가 장치에 표시 됩니다. 패키지를 신뢰 하는지 확인 합니다.
1. 패키지가 성공적으로 적용 되었는지 여부가 표시 됩니다. 실패 한 경우 패키지를 수정 하 고 다시 시도할 수 있습니다. 성공한 경우 장치 설정으로 진행 합니다.

> [!NOTE]
> 8 월 2016 일 전에 장치를 구매한 경우 Microsoft 계정를 사용 하 여 장치에 로그인 하 고, 최신 OS 업데이트를 가져온 후 프로 비전 패키지를 적용 하기 위해 OS를 다시 설정 해야 합니다.

## <a name="verify-device-encryption"></a>장치 암호화 확인

암호화는 HoloLens에서 자동으로 설정 됩니다. 장치 암호화 상태를 확인 하려면:

- HoloLens에서 **설정**  >  **시스템**  >  **정보** 로 이동 합니다. 장치가 암호화 된 경우 **BitLocker** 를 **사용할 수** 있습니다. 

    ![BitLocker 사용을 보여 주는 화면 정보](images/about-encryption.png)
