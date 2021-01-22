---
title: MDM에 HoloLens 등록
description: 여러 장치를 보다 쉽게 관리하기 위해 MDM(모바일 장치 관리)에 HoloLens를 등록하는 방법을 학습합니다.
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
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283189"
---
# <span data-ttu-id="38cda-103">MDM에 HoloLens 등록</span><span class="sxs-lookup"><span data-stu-id="38cda-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="38cda-104">Microsoft [Intune과](https://docs.microsoft.com/intune/windows-holographic-for-business)같은 솔루션을 사용하여 동시에 여러 Microsoft HoloLens 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="38cda-105">설정을 관리하고 앱을 선택해서 설치하며 조직의 요구에 부합하는 보안 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="38cda-106">[Microsoft Intune와 Windows Holographic을 실행하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [Windows Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 및 [Windows Holographic for Business에서 지원되는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38cda-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="38cda-107">VPN, Bitlocker, 및 키오스크 모드 기능을 포함하여 모바일 디바이스 관리(MDM)는 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="38cda-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38cda-108">Requirements</span></span>

 <span data-ttu-id="38cda-109">조직에서 HoloLens 장치를 관리하려면 MDM(모바일 장치 관리)을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="38cda-110">MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="38cda-111">다양한 등록 방법</span><span class="sxs-lookup"><span data-stu-id="38cda-111">Different ways to enroll</span></span>

<span data-ttu-id="38cda-112">OOBE 또는 로그인 후 선택한 ID 유형에 따라 다양한 등록 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="38cda-113">HoloLens의 각 ID 유형에 대한 자세한 내용은 이 페이지를 [방문하세요.](hololens-identity.md)</span><span class="sxs-lookup"><span data-stu-id="38cda-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="38cda-114">Id가 Azure AD인 경우 OOBE \*\*\*\* 또는 설정 앱 액세스 작업 또는 학교 연결 단추  ->  \*\*\*\*  ->  **중** 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="38cda-115">Azure AD의 경우 자동 MDM 등록은 Azure AD가 등록 URL로 구성된 경우만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="38cda-116">ID가 Azure AD인 경우 디바이스가 특정 구성 프로필이 할당된 Intune MDM 서버에 사전 등록된 경우 Azure AD-Join 및 등록이 OOBE 중에 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="38cda-117">[Autopilot 흐름이라고도](hololens2-autopilot.md) [합니다. 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004)빌드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="38cda-118">Identity가 MSA인 경우 **설정 앱**액세스 작업 또는 학교 연결  ->  \*\*\*\*  ->  **단추를** 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="38cda-119">AWA(작업 계정 추가) 흐름이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="38cda-120">ID가 로컬 사용자인 경우 장치 관리 링크에서만 설정 **앱**액세스 작업 또는  ->  **학교**  ->  **등록을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="38cda-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="38cda-121">순수 MDM 등록 흐름이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="38cda-122">장치가 MDM 서버에 등록된 후 설정 앱은 이제 장치가 장치 관리에 등록된 것을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="38cda-123">MDM에 자동 등록</span><span class="sxs-lookup"><span data-stu-id="38cda-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="38cda-124">조직에서 인증을 위해 Azure AD 토큰을 수락하는 Azure AD(Active Directory) 및 MDM 솔루션을 사용하는 경우(현재 Microsoft Intune 및 AirWatch에서만 지원) 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록을 자동으로 허용하도록 Azure AD를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="38cda-125">Azure AD 등록을 구성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="38cda-126">자동 등록을 활성화하는 경우 수동 등록이 추가로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="38cda-127">사용자가 Azure AD 계정으로 로그인하면 장치는 첫 실행 경험이 완료된 후 MDM에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="38cda-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="38cda-128">디바이스가 Azure AD에 가입된 경우 장치 소유자를 고려한 사람에 영향을 [줄 수 있습니다.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="38cda-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="38cda-129">Intune에서 HoloLens의Enroll을 Unenroll(HoloLens)</span><span class="sxs-lookup"><span data-stu-id="38cda-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="38cda-130">디바이스의 사용 안 을(를) 설정하는 방법을 자세히 알아보시고 이 페이지를 [방문하세요.](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)</span><span class="sxs-lookup"><span data-stu-id="38cda-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
