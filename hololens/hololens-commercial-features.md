---
title: 상용 기능
description: 기업에서 HoloLens 장치를 보다 쉽게 관리할 수 있는 Microsoft HoloLens Commercial Suite 기능에 대해 알아보세요.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, 상용, 기능, MDM, 모바일 장치 관리, 키오스크 모드
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397864"
---
# <a name="commercial-features"></a>상용 기능

HoloLens에는 기업에서 HoloLens 장치를 더 쉽게 관리할 수 있는 기능이 포함되어 있습니다.

모든 HoloLens 2 장치에서는 상용 기능을 사용할 수 있습니다.

HoloLens(1세대)에는 두 가지 라이선스 옵션인 개발자 라이선스와 상용 라이선스가 제공되었습니다. HoloLens의 상용 기능을 잠금 해제하려면 개발자 라이선스에서 상용 라이선스로 업그레이드하세요. Microsoft HoloLens Commercial Suite를 구매하려면 해당 지역의 Microsoft 계정 관리자에게 문의하세요.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>주요 상용 기능

- **키오스크 모드.** 실행할 수 있는 앱을 제한하기 위해 키오스크 모드를 사용하여 데모 또는 쇼케이스 환경에서 HoloLens를 사용할 수 있습니다.

  ![키오스크 모드를 사용하면 선택한 앱에서 바로 HoloLens가 시작됩니다.](images/201608-kioskmode-400px.png)

- **HoloLens용 MDM(모바일 장치 관리).** IT 부서에서 Microsoft Intune과 같은 솔루션을 사용하여 동시에 여러 HoloLens 장치를 관리할 수 있습니다. 설정을 관리하고, 설치할 앱을 선택하고, 조직의 요구에 맞는 보안 구성을 설정할 수 있습니다.

  ![HoloLens의 모바일 장치 관리는 여러 장치에서 엔터프라이즈급 장치 관리를 제공합니다.](images/201608-enterprisemanagement-400px.png)

- **비즈니스용 Windows 업데이트.** 비즈니스용 Windows 업데이트는 장치 및 장기 서비스 채널 지원에 제어된 운영 체제 업데이트를 제공합니다.
- **데이터 보안.** 다른 Windows 장치와 동일한 수준의 보안 보호 기능을 제공하도록 HoloLens에서 BitLocker 데이터 암호화가 사용됩니다.
- **작업 액세스.** 조직의 모든 사용자가 HoloLens의 VPN(가상 사설망)을 통해 회사 네트워크에 원격으로 연결할 수 있습니다. HoloLens는 자격 증명이 필요한 Wi-Fi 네트워크에도 액세스할 수 있습니다.
- **비즈니스용 Microsoft Store.** IT 부서에서 특정 HoloLens 용도로 회사 앱만 포함하는 엔터프라이즈 개인 저장소를 설정할 수도 있습니다. 선택한 엔터프라이즈 사용자 그룹에 엔터프라이즈 소프트웨어를 안전하게 배포합니다.

## <a name="feature-comparison-between-editions"></a>버전 간 기능 비교

|기능 |HoloLens(1세대) Development Edition |HoloLens(1세대) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|장치 암호화(BitLocker) | |✔️ |✔️ |
|VPN(가상 사설망) | |✔️ |✔️ |
|[키오스크 모드](hololens-kiosk.md) | |✔️ |✔️ |
|**관리 및 배포** | | | |
|MDM(모바일 디바이스 관리) | |✔️ |✔️ |
|등록 해제 차단 기능 | |✔️ |✔️ |
|인증서 기반 회사 Wi-Fi 액세스 | |✔️ |✔️ |
|Microsoft Store(소비자) |소비자 |MDM을 사용하여 필터링 |MDM을 사용하여 필터링 |
|[비즈니스 Store 포털](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**보안 및 ID** | | | |
|Azure AD(Azure Active Directory) 계정을 사용하여 로그인 |✔️ |✔️ |✔️ |
|MSA(Microsoft 계정)를 사용하여 로그인 |✔️ |✔️ |✔️ |
|PIN 잠금 해제를 사용하는 차세대 자격 증명 |✔️ |✔️ |✔️ |
|[보안 부팅](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**서비스 및 지원** | | | |
|도착 시 자동 시스템 업데이트 |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|장기 서비스 채널(LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>상용 기능 사용

조직의 IT 관리자는 비즈니스용 Microsoft Store, 키오스크 모드, 엔터프라이즈 Wi-Fi 액세스와 같은 상용 기능을 설정할 수 있습니다. [Microsoft HoloLens](index.yml) 설명서는 장치를 등록하고 비즈니스용 Microsoft Store에서 앱을 설치하기 위한 단계별 지침을 제공합니다.

## <a name="see-also"></a>참조

- [Microsoft HoloLens](index.yml)
- [키오스크 모드](hololens-kiosk.md)
- [HoloLens 장치에서 지원되는 CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [비즈니스용 Microsoft Store 및 LOB(기간 업무) 애플리케이션](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [기간 업무 앱 사용](/microsoft-store/working-with-line-of-business-apps)
