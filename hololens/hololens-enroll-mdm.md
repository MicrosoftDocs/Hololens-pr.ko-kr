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
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828693"
---
# <span data-ttu-id="7b282-103">MDM에 HoloLens 등록</span><span class="sxs-lookup"><span data-stu-id="7b282-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="7b282-104">[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)과 같은 솔루션을 사용 하 여 여러 Microsoft HoloLens 장치를 동시에 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="7b282-105">설정을 관리하고 앱을 선택해서 설치하며 조직의 요구에 부합하는 보안 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="7b282-106">[Microsoft Intune와 Windows Holographic을 실행하는 장치 관리](https://docs.microsoft.com/intune/windows-holographic-for-business), [Windows Holographic에서 지원되는 CSP(구성 서비스 공급자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 및 [Windows Holographic for Business에서 지원되는 정책](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b282-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="7b282-107">VPN, Bitlocker, 및 키오스크 모드 기능을 포함하여 모바일 디바이스 관리(MDM)는 [Windows Holographic for Business로 업그레이드](hololens1-upgrade-enterprise.md)해야 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="7b282-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b282-108">Requirements</span></span>

 <span data-ttu-id="7b282-109">조직에서는 HoloLens 장치를 관리 하기 위해 MDM (모바일 디바이스 관리)을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="7b282-110">MDM 공급자는 Microsoft Intune 또는 Microsoft MDM API를 사용하는 타사 공급자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="7b282-111">MDM에 자동 등록</span><span class="sxs-lookup"><span data-stu-id="7b282-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="7b282-112">조직이 Azure AD(Azure Active Directory) 및 인증을 위해 AAD 토큰을 허용하는 MDM 솔루션(현재 Microsoft Intune 및 AirWatch에서만 지원됨)을 사용하는 경우, IT 관리자는 Azure AD를 구성하여 사용자가 Azure AD 계정으로 로그인한 후 MDM 등록이 자동으로 진행되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="7b282-113">Azure AD 등록을 구성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="7b282-114">자동 등록을 활성화하는 경우 수동 등록이 추가로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="7b282-115">사용자가 Azure AD 계정으로 로그인하면 장치는 첫 실행 경험이 완료된 후 MDM에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="7b282-116">설정 앱을 통해 등록</span><span class="sxs-lookup"><span data-stu-id="7b282-116">Enroll through Settings app</span></span>

 <span data-ttu-id="7b282-117">첫 실행 경험 동안 장치가 MDM에 등록되지 않는 경우 사용자는 설정 앱을 사용하여 조직의 MDM 서버를 통해 장치를 수동으로 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="7b282-118">**설정** > **계정** > **회사 액세스**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="7b282-119">**장치 관리에 등록**을 선택하고 조직 계정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="7b282-120">조직의 로그인 페이지로 다시 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="7b282-121">MDM 서버에 대한 인증이 성공하면 성공 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="7b282-122">이제 장치가 MDM 서버에 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="7b282-123">이제 설정 앱에서 장치 관리에 장치가 등록되었음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="7b282-124">Intune의 HoloLens 등록 해제</span><span class="sxs-lookup"><span data-stu-id="7b282-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="7b282-125">Intune에서 원격으로 HoloLens를 [등록 해제](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows)할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="7b282-126">관리자가 MDM을 사용하여 장치 등록을 해제할 경우 장치는 Intune 대시보드에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b282-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
