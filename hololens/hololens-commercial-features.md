---
title: 상업용 기능
description: Microsoft HoloLens Commercial Suite에는 기업에서 HoloLens 장치를 더 쉽게 관리할 수 있는 기능이 포함되어 있습니다. HoloLens 2 장치는 기본적으로 상업용 기능을 갖추고 있습니다.
keywords: HoloLens, 상업용, 기능, mdm, 모바일 장치 관리, 키오스크 모드
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
ms.openlocfilehash: 28898c5c0cbc2a4f66cea13665e5ef63447db382
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828758"
---
# 상업용 기능

HoloLens에는 기업에서 HoloLens 장치를 더 쉽게 관리할 수 있는 기능이 포함되어 있습니다.

모든 HoloLens 2 장치에서는 상업용 기능을 사용할 수 있습니다.

HoloLens(1세대)에는 개발자 라이선스 및 상용 라이선스 등 두 가지 라이선스 옵션이 있습니다. HoloLens의 상업용 기능을 잠금 해제하려면 개발자 라이선스에서 상용 라이선스로 업그레이드하세요. Microsoft HoloLens Commercial Suite를 구매하려면 해당 지역의 Microsoft 계정 관리자에게 문의하세요.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## 주요 상업용 기능

- **키오스크 모드.** 키오스크 모드를 사용하여 데모 또는 쇼케이스 환경에서 HoloLens를 사용하여 실행할 수 있는 앱을 제한할 수 있습니다.

  ![키오스크 모드를 사용하면 HoloLens가 선택한 앱에서 바로 시작됩니다.](images/201608-kioskmode-400px.png)

- **HoloLens용 모바일 장치 관리(MDM).** Microsoft Intune과 같은 솔루션을 사용하여 IT 부서가 동시에 여러 HoloLens 장치를 관리할 수 있습니다. 설정을 관리하고 설치할 앱을 선택하고 조직의 요구에 맞는 보안 구성을 설정할 수 있습니다.

  ![HoloLens의 모바일 장치 관리는 여러 장치에서 엔터프라이즈 수준의 장치 관리를 제공합니다.](images/201608-enterprisemanagement-400px.png)

- **비즈니스용 Windows 업데이트.** 비즈니스용 Windows 업데이트는 장치 및 장기 서비스 채널 지원에 대한 제어된 운영 체제 업데이트를 제공합니다.
- **데이터 보안.** 다른 Windows 장치와 동일한 수준의 보안 보호 기능을 제공하기 위해 HoloLens에서 BitLocker 데이터 암호화를 사용하도록 설정합니다.
- **회사 액세스.** 조직의 모든 사용자가 HoloLens의 VPN(가상 사설망)을 통해 회사 네트워크에 원격으로 연결할 수 있습니다. HoloLens는 자격 증명이 필요한 Wi-Fi 네트워크에도 액세스할 수 있습니다.
- **비즈니스용 Microsoft Store.** IT 부서에서 특정 HoloLens 사용량에 대한 회사 앱만 포함하는 엔터프라이즈 개인 저장소를 설정할 수도 있습니다. 엔터프라이즈 소프트웨어를 선택한 엔터프라이즈 사용자 그룹에 안전하게 배포합니다.

## 에디션 간의 기능 비교

|기능 |HoloLens Development 버전 |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|장치 암호화(BitLocker) | |✔️ |✔️ |
|VPN(가상 사설망) | |✔️ |✔️ |
|[키오스크 모드](hololens-kiosk.md) | |✔️ |✔️ |
|**관리 및 배포** | | | |
|MDM(모바일 장치 관리) | |✔️ |✔️ |
|등록 해제 차단 기능 | |✔️ |✔️ |
|인증서 기반 회사 Wi-Fi 액세스 | |✔️ |✔️ |
|Microsoft Store(소비자) |소비자 |MDM을 사용하여 필터링 |MDM을 사용하여 필터링 |
|[비즈니스 Microsoft Store 포털](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**보안 및 ID** | | | |
|AAD(Azure Active Directory) 계정을 사용하여 로그인 |✔️ |✔️ |✔️ |
|Microsoft 계정(MSA)을 사용하여 로그인 |✔️ |✔️ |✔️ |
|PIN 잠금을 사용하는 차세대 자격 증명 |✔️ |✔️ |✔️ |
|[보안 부팅](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**서비스 및 지원** | | | |
|도착 시 자동 시스템 업데이트 |✔️ |✔️ |✔️ |
|[비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|장기 서비스 채널(LTSC) | |✔️ |✔️ |

## 상업용 기능 사용

조직의 IT 관리자는 비즈니스용 Microsoft Store, 키오스크 모드, 엔터프라이즈 Wi-Fi 액세스 등의 상업용 기능을 설정할 수 있습니다. [Microsoft HoloLens](index.md) 설명서는 장치를 등록하고 비즈니스용 Microsoft Store에서 앱을 설치하기 위한 단계별 지침을 제공합니다.

## 기타 참조

- [Microsoft HoloLens](index.md)
- [키오스크 모드](hololens-kiosk.md)
- [HoloLens 장치에서 지원되는 CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [비즈니스용 Microsoft Store 및 LOB(기간 업무) 응용 프로그램](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [기간 업무 앱으로 작업](/microsoft-store/working-with-line-of-business-apps)
