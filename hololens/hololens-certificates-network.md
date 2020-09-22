---
title: HoloLens 2용 인증서 및 네트워크 프로필 준비
description: HoloLens 2 장치의 네트워크에 대한 인증서를 구성하고 사용하는 방법
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
ms.openlocfilehash: 460b6f42de7413e77eaec041a5ab6141ed959cf4
ms.sourcegitcommit: 9944fd2040fc1267ace1da1bd62ef36b68c7f318
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015527"
---
# <span data-ttu-id="1325e-103">HoloLens 2용 인증서 및 네트워크 프로필 준비</span><span class="sxs-lookup"><span data-stu-id="1325e-103">Prepare certificates and network profiles for HoloLens 2</span></span>

<span data-ttu-id="1325e-104">인증서 기반 인증은 HoloLens 2를 사용하는 고객에게 일반적인 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-104">Certificate-based authentication is a common requirement for customers using HoloLens 2.</span></span> <span data-ttu-id="1325e-105">Wi-Fi에 액세스하거나 VPN 솔루션에 연결하거나 조직의 내부 리소스에 액세스하는 데 인증서가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-105">You might require certificates to access Wi-Fi, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>

<span data-ttu-id="1325e-106">HoloLens 2 장치는 일반적으로 Azure AD(Azure Active Directory)에 연결되고 Intune 또는 기타 MDM 공급자가 관리하므로 사용자는 MDM 솔루션에 통합되는 SCEP(단순 인증서 등록 프로토콜) 또는 PKCS(공개 키 암호 표준) 인증서 인프라를 사용하여 관련 인증서를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-106">Because HoloLens 2 devices are typically joined to Azure Active Directory (Azure AD) and managed by Intune or other MDM provider, you will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span>

## <span data-ttu-id="1325e-107">인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1325e-107">Certificate requirements</span></span>
<span data-ttu-id="1325e-108">SCEP 또는 PKCS 인프라를 통해 인증서를 배포하려면 루트 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-108">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="1325e-109">조직의 다른 응용 프로그램 및 서비스 또한 HoloLens 2 장치에 루트 인증서를 배포해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-109">Other applications and services in your organization might require root certificates to be deployed to your HoloLens 2 devices as well.</span></span> 

## <span data-ttu-id="1325e-110">Wi-Fi 연결 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1325e-110">Wi-Fi connectivity requirements</span></span>
<span data-ttu-id="1325e-111">엔터프라이즈 네트워크에 대한 필수 Wi-Fi 구성과 함께 장치가 자동으로 제공되도록 하려면 Wi-Fi 구성 프로필이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-111">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you will need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="1325e-112">Intune 또는 기타 MDM 공급자를 구성하여 장치에 해당 프로필을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-112">You can configure Intune or other MDM provider to deploy these profiles to your devices.</span></span> <span data-ttu-id="1325e-113">네트워크 보안에서 장치가 로컬 도메인의 일부여야 하는 경우 Wi-Fi 네트워크 인프라를 평가하여 HoloLens 2 장치(HoloLens 2 장치는 Azure AD에만 연결됨)와 호환되는지 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-113">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with HoloLens 2 devices (HoloLens 2 devices are Azure AD-joined only).</span></span>

## <span data-ttu-id="1325e-114">인증서 인프라 배포</span><span class="sxs-lookup"><span data-stu-id="1325e-114">Deploy certificate infrastructure</span></span>
<span data-ttu-id="1325e-115">SCEP 또는 PKCS 인프라가 이미 존재하지 않는 경우 이를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-115">If no SCEP or PKCS infrastructure already exists, you'll need to prepare one.</span></span> <span data-ttu-id="1325e-116">인증에 SCEP 또는 PKCS 인증서의 사용을 지원하려면 Intune에서 [인증서 커넥터](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-116">To support the use of SCEP or PKCS certificates for authentication, Intune requires the use of a [certificate connector](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).</span></span>

> [!NOTE]
> <span data-ttu-id="1325e-117">Microsoft CA와 함께 SCEP를 사용하는 경우 [NDES(네트워크 장치 등록 서비스)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes) 또한 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-117">When you use SCEP with a Microsoft CA, you must also configure the [Network Device Enrollment Service (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span></span>

<span data-ttu-id="1325e-118">자세한 내용은 [Microsoft Intune에서 장치에 대한 인증서 프로필 구성](https://docs.microsoft.com/intune/certificates-configure)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1325e-118">For more information, see [Configure a certificate profile for your devices in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)</span></span>

## <span data-ttu-id="1325e-119">인증서 및 Wi-Fi/VPN 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="1325e-119">Deploy certificates and Wi-Fi/VPN profile</span></span>
<span data-ttu-id="1325e-120">인증서 및 프로필을 배포하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-120">To deploy certificates and profiles, follow these steps:</span></span>
1.  <span data-ttu-id="1325e-121">각 루트와 중간 인증서에 대한 프로필을 만듭니다. ([신뢰할 수 있는 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)를 참조하세요.) 각 프로필에는 YYYY/MM/DD 형식의 만료 날짜를 포함하는 설명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-121">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> **<span data-ttu-id="1325e-122">만료 날짜 없이 인증서 프로필은 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-122">Certificate profiles without an expiration date will not be deployed.</span></span>**
1.  <span data-ttu-id="1325e-123">각 SCEP와 PKCS 인증서에 대한 프로필을 만듭니다. ([SCEP 인증서 프로필 만들기 또는 PKCS 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)를 참조하세요.) 각 프로필에는 YYYY/MM/DD 형식의 만료 날짜를 포함하는 설명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-123">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> **<span data-ttu-id="1325e-124">만료 날짜 없이 인증서 프로필은 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-124">Certificate profiles without an expiration date will not be deployed.</span></span>**

> [!NOTE]
> <span data-ttu-id="1325e-125">HoloLens 2는 많은 사용자에게 공유 장치로 간주되기 때문에 장치별 여러 사용자는 가능한 경우 Wi-Fi 인증을 위해 사용자 인증서 대신 장치 인증서를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-125">As the HoloLens 2 is considered for many to be a shared device, multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible</span></span>

3.  <span data-ttu-id="1325e-126">각 회사 Wi-Fi 네트워크에 대한 프로필을 만듭니다. ([Windows 10 이상의 장치에 대한 Wi-Fi 설정](https://docs.microsoft.com/intune/wi-fi-settings-windows)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="1325e-126">Create a profile for each corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> 
> [!NOTE]
> <span data-ttu-id="1325e-127">가능한 경우 사용자 그룹이 아니라 장치 그룹에 대해 Wi-Fi 프로필을 [할당](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-127">It is recommended that the Wi-Fi profile be [assigned](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) to Device groups rather than User groups where possible.</span></span> 

> [!TIP]
> <span data-ttu-id="1325e-128">회사 네트워크의 Windows 10 PC에서 작업 중인 Wi-Fi 프로필을 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-128">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="1325e-129">이 내보내기에서 현재 모든 설정을 포함하는 XML 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-129">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="1325e-130">그런 다음 해당 파일을 HoloLens 2 장치에 대한 Wi-Fi 프로필로 사용하여 Intune으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1325e-130">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="1325e-131">[Windows 장치에 대한 Wi-Fi 설정 내보내기 및 가져오기](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1325e-131">See [Export and import Wi-Fi settings for Windows devices.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span></span>

4.  <span data-ttu-id="1325e-132">각 회사 VPN에 대한 프로필을 만듭니다. ([Intune을 사용하여 VPN 연결을 추가하려면 Windows 10 및 Windows Holographic 장치 설정](https://docs.microsoft.com/intune/vpn-settings-windows-10)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="1325e-132">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).</span></span>



