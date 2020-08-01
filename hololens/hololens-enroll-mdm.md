---
title: MDM에 HoloLens 등록
description: 여러 장치를 더 쉽게 관리하기 위해 MDM(모바일 장치 관리)에 HoloLens를 등록합니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903224"
---
# <span data-ttu-id="6ea81-103">MDM에 HoloLens 등록</span><span class="sxs-lookup"><span data-stu-id="6ea81-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="6ea81-104">[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)과 같은 솔루션을 사용 하 여 여러 Microsoft HoloLens 장치를 동시에 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="6ea81-105">설정을 관리하고 앱을 선택해서 설치하며 조직의 요구에 부합하는 보안 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="6ea81-106">[Microsoft Intune와 Windows Holographic을 실행하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [Windows Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 및 [Windows Holographic for Business에서 지원되는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea81-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="6ea81-107">VPN, Bitlocker, 및 키오스크 모드 기능을 포함하여 모바일 디바이스 관리(MDM)는 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="6ea81-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ea81-108">Requirements</span></span>

 <span data-ttu-id="6ea81-109">조직에서는 HoloLens 장치를 관리 하기 위해 MDM (모바일 디바이스 관리)을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="6ea81-110">MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="6ea81-111">다양 한 등록 방법</span><span class="sxs-lookup"><span data-stu-id="6ea81-111">Different ways to enroll</span></span>

<span data-ttu-id="6ea81-112">OOBE 또는 post 로그인 중에 선택한 id 유형에 따라 다양 한 등록 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="6ea81-113">HoloLens의 각 Id 유형에 대 한 자세한 내용을 보려면 [이 페이지](hololens-identity.md)를 방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea81-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="6ea81-114">Id가 AAD 이면 OOBE 또는 **설정 앱**  ->  **액세스 작업 또는 학교**  ->  **연결** 단추 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="6ea81-115">AAD의 경우 자동 MDM 등록은 AAD가 등록 Url로 구성 된 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="6ea81-116">Id가 AAD이 고 장치가 지정 된 특정 구성 프로필이 있는 Intune MDM 서버에 미리 등록 된 경우 OOBE 중에 AAD 조인과 등록이 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="6ea81-117">[19041.1103 + 빌드에서](hololens-release-notes.md#windows-holographic-version-2004)사용할 수 있는 [Autopilot 흐름이](hololens2-autopilot.md) 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="6ea81-118">Id가 MSA 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **연결** 단추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="6ea81-119">AWA (작업 계정 추가) 흐름이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="6ea81-120">Id가 로컬 사용자 인 경우 **설정 앱**  ->  **액세스 회사 또는 학교**  ->  **등록을 장치 관리 링크 에서만** 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="6ea81-121">순수한 MDM 등록 흐름이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="6ea81-122">디바이스를 MDM 서버에 등록 한 후에는 설정 앱이 장치 관리에 디바이스를 등록 했음을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="6ea81-123">MDM에 자동 등록</span><span class="sxs-lookup"><span data-stu-id="6ea81-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="6ea81-124">조직이 Azure AD(Azure Active Directory) 및 인증을 위해 AAD 토큰을 허용하는 MDM 솔루션(현재 Microsoft Intune 및 AirWatch에서만 지원됨)을 사용하는 경우, IT 관리자는 Azure AD를 구성하여 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록이 자동으로 진행되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="6ea81-125">Azure AD 등록을 구성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="6ea81-126">자동 등록을 활성화하는 경우 수동 등록이 추가로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="6ea81-127">사용자가 Azure AD 계정으로 로그인하면 장치는 첫 실행 경험이 완료된 후 MDM에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea81-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="6ea81-128">Intune의 HoloLens 등록 해제</span><span class="sxs-lookup"><span data-stu-id="6ea81-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="6ea81-129">장치 unenrolling에 대해 자세히 알아보려면 [이 페이지](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)를 방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea81-129">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
