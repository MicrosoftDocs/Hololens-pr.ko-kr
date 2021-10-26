---
title: HoloLens 2에 대한 인증서 및 네트워크 프로필 준비
description: HoloLens 2 혼합 현실 장치에서 네트워크에 대한 인증서를 구성, 사용, 배포하고, 문제를 해결하는 방법을 알아보세요.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c7c15cc0630f11d1687db19f2e6b28b8347dd4c3
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151678"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>HoloLens 2에 대한 인증서 및 네트워크 프로필 준비

HoloLens 2를 사용하는 고객에게 인증서 기반 인증은 공통적인 요구 사항입니다. Wi-Fi에 액세스하거나 VPN 솔루션에 연결하거나 조직의 내부 리소스에 액세스하는 데 인증서가 필요할 수 있습니다.

HoloLens 2 장치는 일반적으로 Azure AD(Azure Active Directory)에 연결되고 Intune 또는 기타 MDM 공급자가 관리하므로 사용자는 MDM 솔루션에 통합되는 SCEP(단순 인증서 등록 프로토콜) 또는 PKCS(공개 키 암호 표준) 인증서 인프라를 사용하여 관련 인증서를 배포해야 합니다. 

>[!NOTE]
> MDM 공급자가 없는 경우에도 [Windows 구성 디자이너](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)의 [프로비전 패키지](hololens-provisioning.md#create-the-provisioning-package)나 [인증서 관리자](certificate-manager.md)를 통해 **설정 > 업데이트 및 보안 > 인증서 관리자** 로 이동하여 인증서를 배포할 수 있습니다.

## <a name="certificate-requirements"></a>인증서 요구 사항
SCEP 또는 PKCS 인프라를 통해 인증서를 배포하려면 루트 인증서가 필요합니다. 조직의 다른 응용 프로그램 및 서비스를 이용할 경우에도 HoloLens 2 장치에 루트 인증서를 배포해야 할 수 있습니다. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi 연결 요구 사항
엔터프라이즈 네트워크에 필요한 Wi-Fi 구성을 장치에 자동으로 제공하려면 Wi-Fi 구성 프로필이 필요합니다. 장치에 해당 프로필을 배포하도록 Intune 또는 기타 MDM 공급자를 구성할 수 있습니다. 네트워크 보안에서 장치가 로컬 도메인에 속해야 하는 경우 Wi-Fi 네트워크 인프라를 평가하여 HoloLens 2 장치(HoloLens 2 장치는 Azure AD에만 조인됨)와 호환되는지 확인해야 할 수도 있습니다.

## <a name="deploy-certificate-infrastructure"></a>인증서 인프라 배포
SCEP 또는 PKCS 인프라가 아직 존재하지 않는 경우 이를 준비해야 합니다. SCEP 또는 PKCS 인증서를 사용하여 인증하도록 지원하려면 Intune에서 [인증서 커넥터](/mem/intune/protect/certificate-connectors)를 사용해야 합니다.

> [!NOTE]
> Microsoft CA와 함께 SCEP를 사용하는 경우 [NDES(네트워크 장치 등록 서비스)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)도 구성해야 합니다.

자세한 내용은 [Microsoft Intune에서 장치에 대한 인증서 프로필 구성](/intune/certificates-configure)을 참조하세요.

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>인증서 및 Wi-Fi/VPN 프로필 배포
인증서 및 프로필을 배포하려면 다음 단계를 따르세요.
1.  각 루트 및 중간 인증서에 대한 프로필을 만듭니다([신뢰할 수 있는 인증서 프로필 만들기](/intune/protect/certificates-configure#create-trusted-certificate-profiles) 참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함된 설명이 있어야 합니다. **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**
1.  각 SCEP 또는 PKCS 인증서에 대한 프로필을 만듭니다([SCEP 인증서 프로필 만들기 또는 PKCS 인증서 프로필 만들기](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함된 설명이 있어야 합니다. **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**

    > [!NOTE]
    > HoloLens 2는 많은 사용자에게 공유 장치(장치 하나를 여러 사용자가 사용)로 간주되기 때문에, 가능한 경우 Wi-Fi 인증을 위해 사용자 인증서 대신 장치 인증서를 배포하는 것이 좋습니다.

3.  각 회사 Wi-Fi 네트워크에 대한 프로필을 만듭니다([Windows 10 이상 장치에 대한 Wi-Fi 설정](/intune/wi-fi-settings-windows) 참조). 
    > [!NOTE]
    > 가능한 경우 사용자 그룹이 아니라 장치 그룹에 Wi-Fi 프로필을 [할당](/mem/intune/configuration/device-profile-assign)하는 것이 좋습니다. 

    > [!TIP]
    > 회사 네트워크의 Windows 10 PC에서 사용 중인 Wi-Fi 프로필을 내보낼 수도 있습니다. 이 내보내기를 수행하면 현재 모든 설정이 포함된 XML 파일이 생성됩니다. 그런 다음 이 파일을 Intune으로 가져와 HoloLens 2 장치에 대한 Wi-Fi 프로필로 사용합니다. [Windows 장치에 대한 Wi-Fi 설정 내보내기 및 가져오기](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)를 참조하세요.

4.  각 회사 VPN에 대한 프로필을 만듭니다([Intune을 사용하여 VPN 연결을 추가하기 위한 Windows 10 및 Windows Holographic 장치 설정](/intune/vpn-settings-windows-10) 참조).

## <a name="troubleshooting-certificates"></a>인증서 문제 해결

인증서가 올바르게 배포되었는지 확인해야 하는 경우 장치의 [인증서 관리자](certificate-manager.md)를 사용하여 인증서가 있는지 확인하세요.  

>[!WARNING]
> 인증서 관리자에서 MDM 배포 인증서를 볼 수는 있지만 인증서 관리자에서 해당 인증서를 제거할 수는 없습니다. MDM을 통해 제거해야 합니다.


