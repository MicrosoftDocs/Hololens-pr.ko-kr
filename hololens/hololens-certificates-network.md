---
title: HoloLens 2용 인증서 및 네트워크 프로필 준비
description: HoloLens 2 혼합 현실 장치에서 네트워크에 대한 인증서를 구성, 사용, 배포 및 문제 해결하는 방법을 학습합니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 1bfac948b493c2e55207e45042d6b022c1818969
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283439"
---
# HoloLens 2용 인증서 및 네트워크 프로필 준비

인증서 기반 인증은 HoloLens 2를 사용하는 고객에게 일반적인 요구 사항입니다. Wi-Fi에 액세스하거나 VPN 솔루션에 연결하거나 조직의 내부 리소스에 액세스하는 데 인증서가 필요할 수 있습니다.

HoloLens 2 장치는 일반적으로 Azure AD(Azure Active Directory)에 연결되고 Intune 또는 기타 MDM 공급자가 관리하므로 사용자는 MDM 솔루션에 통합되는 SCEP(단순 인증서 등록 프로토콜) 또는 PKCS(공개 키 암호 표준) 인증서 인프라를 사용하여 관련 인증서를 배포해야 합니다.

## 인증서 요구 사항
SCEP 또는 PKCS 인프라를 통해 인증서를 배포하려면 루트 인증서가 필요합니다. 조직의 다른 응용 프로그램 및 서비스 또한 HoloLens 2 장치에 루트 인증서를 배포해야 할 수 있습니다. 

## Wi-Fi 연결 요구 사항
엔터프라이즈 네트워크에 대한 필수 Wi-Fi 구성과 함께 장치가 자동으로 제공되도록 하려면 Wi-Fi 구성 프로필이 있어야 합니다. Intune 또는 기타 MDM 공급자를 구성하여 장치에 해당 프로필을 배포할 수 있습니다. 네트워크 보안에서 장치가 로컬 도메인의 일부여야 하는 경우 Wi-Fi 네트워크 인프라를 평가하여 HoloLens 2 장치(HoloLens 2 장치는 Azure AD에만 연결됨)와 호환되는지 확인해야 할 수 있습니다.

## 인증서 인프라 배포
SCEP 또는 PKCS 인프라가 이미 존재하지 않는 경우 이를 준비해야 합니다. 인증에 SCEP 또는 PKCS 인증서의 사용을 지원하려면 Intune에서 [인증서 커넥터](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)를 사용해야 합니다.

> [!NOTE]
> Microsoft CA와 함께 SCEP를 사용하는 경우 [NDES(네트워크 장치 등록 서비스)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes) 또한 구성해야 합니다.

자세한 내용은 [Microsoft Intune에서 장치에 대한 인증서 프로필 구성](https://docs.microsoft.com/intune/certificates-configure)을 참조하세요.

## 인증서 및 Wi-Fi/VPN 프로필 배포
인증서 및 프로필을 배포하려면 다음 단계를 따릅니다.
1.  각 루트와 중간 인증서에 대한 프로필을 만듭니다. ([신뢰할 수 있는 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)를 참조하세요.) 각 프로필에는 YYYY/MM/DD 형식의 만료 날짜를 포함하는 설명이 있어야 합니다. **만료 날짜 없이 인증서 프로필은 배포되지 않습니다.**
1.  각 SCEP와 PKCS 인증서에 대한 프로필을 만듭니다. ([SCEP 인증서 프로필 만들기 또는 PKCS 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)를 참조하세요.) 각 프로필에는 YYYY/MM/DD 형식의 만료 날짜를 포함하는 설명이 있어야 합니다. **만료 날짜 없이 인증서 프로필은 배포되지 않습니다.**

    > [!NOTE]
    > HoloLens 2는 많은 사용자에게 공유 장치로 간주되기 때문에 장치별 여러 사용자는 가능한 경우 Wi-Fi 인증을 위해 사용자 인증서 대신 장치 인증서를 배포하는 것이 좋습니다.

3.  각 회사 Wi-Fi 네트워크에 대한 프로필을 만듭니다. ([Windows 10 이상의 장치에 대한 Wi-Fi 설정](https://docs.microsoft.com/intune/wi-fi-settings-windows)을 참조하세요.) 
    > [!NOTE]
    > 가능한 경우 사용자 그룹이 아니라 장치 그룹에 대해 Wi-Fi 프로필을 [할당](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)하는 것이 좋습니다. 

    > [!TIP]
    > 회사 네트워크의 Windows 10 PC에서 작업 중인 Wi-Fi 프로필을 내보낼 수도 있습니다. 이 내보내기에서 현재 모든 설정을 포함하는 XML 파일을 만듭니다. 그런 다음 해당 파일을 HoloLens 2 장치에 대한 Wi-Fi 프로필로 사용하여 Intune으로 가져옵니다. [Windows 장치에 대한 Wi-Fi 설정 내보내기 및 가져오기](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)를 참조하세요.

4.  각 회사 VPN에 대한 프로필을 만듭니다. ([Intune을 사용하여 VPN 연결을 추가하려면 Windows 10 및 Windows Holographic 장치 설정](https://docs.microsoft.com/intune/vpn-settings-windows-10)을 참조하세요.)

## 인증서 문제 해결

인증서가 올바르게 배포 되었는지 확인해야 하는 경우 장치의 [인증서 관리자](certificate-manager.md)를 사용하여 인증서가 있는지 확인하세요.  


