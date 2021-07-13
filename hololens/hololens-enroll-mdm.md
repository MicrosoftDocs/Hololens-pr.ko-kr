---
title: MDM에 HoloLens 등록
description: 여러 디바이스를 보다 쉽게 관리하기 위해 MDM(모바일 디바이스 관리)에 HoloLens 등록하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640409"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="c4af0-103">MDM에 HoloLens 등록</span><span class="sxs-lookup"><span data-stu-id="c4af0-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="c4af0-104">Microsoft Intune 같은 솔루션을 사용하여 여러 [Microsoft HoloLens](/intune/windows-holographic-for-business)디바이스를 동시에 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="c4af0-105">설정을 관리하고, 앱을 선택하여 조직의 요구에 맞는 보안 구성을 설치하고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="c4af0-106">Microsoft Intune, Windows [Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)및 Windows Holographic for Business [에서 지원하는 정책을](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)Windows [Holographic을 실행하는 디바이스 관리를](/intune/windows-holographic-for-business)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4af0-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="c4af0-107">VPN, Bitlocker 및 키오스크 모드 기능을 포함한 MDM(모바일 디바이스 관리)은 [Windows Holographic for Business 로 업그레이드할](hololens1-upgrade-enterprise.md)때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="c4af0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4af0-108">Requirements</span></span>

 <span data-ttu-id="c4af0-109">조직에서는 HoloLens 디바이스를 관리하기 위해 MDM(모바일 장치 관리)을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="c4af0-110">MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="c4af0-111">등록하는 다양한 방법</span><span class="sxs-lookup"><span data-stu-id="c4af0-111">Different ways to enroll</span></span>

<span data-ttu-id="c4af0-112">OOBE 또는 로그인 후 선택한 [ID](hololens-identity.md) 유형에 따라 다양한 등록 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="c4af0-113">ID가 Azure AD인 경우 OOBE 또는 **설정 앱** 액세스 작업 또는 학교 커넥트 단추 중  ->    ->   하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="c4af0-114">Azure AD의 경우 [자동 MDM 등록은](hololens-enroll-mdm.md#auto-enrollment-in-mdm) Azure AD가 등록 URL로 구성된 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="c4af0-115">ID가 Azure AD이고 디바이스가 할당된 특정 구성 프로필이 있는 Intune MDM 서버에 미리 등록된 경우 OOBE 중에 Azure AD-Join [및 자동 MDM 등록이](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="c4af0-116">[Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+(19041.1103 이상에서](hololens-release-notes.md#windows-holographic-version-2004)사용 가능)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="c4af0-117">ID가 MSA인 경우 **설정 앱**  ->  **액세스 작업 또는 학교**  ->  **커넥트** 단추를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c4af0-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="c4af0-118">AWA(작업 계정 추가) 흐름이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="c4af0-119">ID가 로컬 사용자인 경우 디바이스 관리 링크에서만 **설정 앱** 액세스  ->  **작업 또는 학교**  ->  **등록을** 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c4af0-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="c4af0-120">순수 MDM 등록 흐름이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="c4af0-121">디바이스가 MDM 서버에 등록되면 이제 디바이스가 디바이스 관리에 등록되었다는 설정 앱이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="c4af0-122">MDM의 자동 등록</span><span class="sxs-lookup"><span data-stu-id="c4af0-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="c4af0-123">조직에 [Azure Premium 구독이](https://azure.microsoft.com/overview/)있는 경우 는 인증을 위해 Azure AD 토큰을 수락하는 Azure Active Directory(Azure AD) 및 MDM 솔루션을 사용하고 있습니다(현재 Microsoft Intune 및 AirWatch에서만 지원됨). IT 관리자는 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록을 자동으로 허용하도록 Azure AD를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="c4af0-124">Azure AD 등록을 구성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="c4af0-125">자동 등록을 사용하도록 설정하면 추가 수동 등록이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="c4af0-126">사용자가 Azure AD 계정으로 로그인하면 첫 번째 실행 환경을 완료한 후 디바이스가 MDM에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="c4af0-127">디바이스가 Azure AD 조인된 경우 디바이스 [소유자](security-adminless-os.md#device-owner)를 고려한 사람에게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="c4af0-128">Intune에서 HoloLens 등록 취소</span><span class="sxs-lookup"><span data-stu-id="c4af0-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="c4af0-129">등록 방법에 따라 디바이스 등록 취소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="c4af0-130">디바이스가 Azure AD 계정 또는 Autopilot에 등록된 경우 Intune에서 등록을 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="c4af0-131">Azure AD에서 HoloLens 조인을 해제하거나 Azure AD 테넌트에서 다른 테넌트로 다시 조인하려면 디바이스를 [다시 설정/리플래시해야](hololens-recovery.md#reset-the-device) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="c4af0-132">디바이스가 작업 계정을 추가한 MSA 계정 또는 디바이스 관리에만 등록된 로컬 계정에서 등록된 경우 디바이스 등록을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="c4af0-133">시작 메뉴 열고 앱 액세스   ->  **작업 또는 학교**  ->  *사용자계정*  ->  **연결 끊기** 단추를 설정 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4af0-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>