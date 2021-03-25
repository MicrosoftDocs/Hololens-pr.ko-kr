---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 유지 관리
description: Dynamics 365 가이드를 통해 회사 연결 네트워크를 통해 HoloLens 2 장치를 유지 관리하는 방법을 알아보세요.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448598"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="3c50a-104">유지 관리 - 회사 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="3c50a-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="3c50a-105">HoloLens 업데이트</span><span class="sxs-lookup"><span data-stu-id="3c50a-105">Update HoloLens</span></span>

<span data-ttu-id="3c50a-106">Microsoft는 장치 그룹에 업데이트를 배포하고 업데이트 설치를 위해 유지 관리 기간을 정의하는 기능 같은 추가 Windows 업데이트 중심 관리 기능을 IT 관리자에게 제공하는 비즈니스용 Windows 업데이트를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="3c50a-107">인기 있는 업데이트 관리 방법 중 하나는 기능 지연을 30일로 연기하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="3c50a-108">이를 통해 관리자는 새 기능을 업데이트하고 미리 보고, 먼저 지식을 얻고 지원 센터에 새로운 변경 내용을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="3c50a-109">예정된 일, 예약된 시간 및 장치에서 사용 시간을 설정하는 [등 HoloLens](https://docs.microsoft.com/hololens/hololens-updates)업데이트를 관리하는 방법을 알아보고, 작업 시간 외에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-109">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="3c50a-110">Dynamics 365 가이드(및 기타 스토어 앱)를 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="3c50a-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="3c50a-111">Dynamics 365 가이드는 In-Box 앱으로, Microsoft Store 앱을 통해 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="3c50a-112">Microsoft Store를 통해 다운로드되는 모든 앱의 경우 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 앱 자체를 통해 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="3c50a-113">LOB 앱을 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="3c50a-113">How to update LOB apps</span></span>

<span data-ttu-id="3c50a-114">LOB 앱은 Intune에 추가된 방식으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="3c50a-115">더 높은 버전 번호의 새 앱을 기존 앱 구성에 업로드하여 Intune에서 앱을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="3c50a-116">장치가 Intune에 동기화하면 최신 앱 버전이 있으며 최신 앱이 다운로드된 후 이전 앱을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="3c50a-117">새 앱을 업로드하려면 [MEM 포털](https://endpoint.microsoft.com/#home)앱  ->  \*\*\*\* -> 모든 **앱**  ->  *TheNameOfYourApp 속성으로*  ->  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c50a-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="3c50a-118">앱 정보 옆에 있는 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c50a-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="3c50a-119">업데이트할 파일 &quot; 선택의 값으로 &quot; 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="3c50a-120">여기에서 상황에 맞는 메뉴를 사용하여 파일 탐색기를 열고 최신 버전의 LOB 앱을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="3c50a-121">종속성은 필요한 경우 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="3c50a-122">자세한 내용은 [다음을 참조하세요. HoloLens용 Intune 앱 배포](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="3c50a-122">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="3c50a-123">개발 계획</span><span class="sxs-lookup"><span data-stu-id="3c50a-123">Development Plan</span></span>

<span data-ttu-id="3c50a-124">장치가 성공적으로 등록되면 이제 장치에 더 많은 LOB 앱을 배포할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="3c50a-125">이 가이드의 기간 동안 샘플 앱을 사용하지만 조직의 요구에 따라 구축된 사용자 지정 앱을 사용할 가능성이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="3c50a-126">LOB 앱이 이미 있는 경우 [MDM을](https://docs.microsoft.com/hololens/app-deploy-intune)통해 앱을 배포할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="3c50a-127">다른 방법을 원할 경우 [HoloLens 2의](https://docs.microsoft.com/hololens/app-deploy-overview) 응용 프로그램 배포 개요를 검토하여 장치에 LOB 앱을 배포하는 더 많은 방법을 알아보하세요.</span><span class="sxs-lookup"><span data-stu-id="3c50a-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="3c50a-128">아직 LOB 앱을 만들지 않았거나 아직 만드는 중이면 혼합 현실 개발 docs를 [](https://docs.microsoft.com/windows/mixed-reality/design/design) 검토하여 혼합 현실 개발을 시작하여 디자인 및 프로토타이핑을 시작하거나 혼합 현실 개발을 시작하기 위한 핵심 개념을 배워야 [합니다.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="3c50a-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="3c50a-129">지원 플랜</span><span class="sxs-lookup"><span data-stu-id="3c50a-129">Support Plan</span></span>

<span data-ttu-id="3c50a-130">지원 계획은 매우 중요한 일입니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="3c50a-131">HoloLens 장치에서 등록 프로세스 문제를 해결하고 조직 내에서 HoloLens 디바이스를 일반적으로 사용하는 방법을 교육한 사람이나 그룹이 있는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="3c50a-132">사용자가 문제를 보다 빠르게 해결하도록 허용하기 위해 에스컬레이터 프로세스는 다음 순서와 유사한 방식으로 처리하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="3c50a-133">지원 센터</span><span class="sxs-lookup"><span data-stu-id="3c50a-133">Your Support desk.</span></span>
2. <span data-ttu-id="3c50a-134">HoloLens 전문가 팀</span><span class="sxs-lookup"><span data-stu-id="3c50a-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="3c50a-135">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens 문제 해결 Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="3c50a-135">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="3c50a-136">고객 지원</span><span class="sxs-lookup"><span data-stu-id="3c50a-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="3c50a-137">장치 관리</span><span class="sxs-lookup"><span data-stu-id="3c50a-137">Device Management</span></span>

<span data-ttu-id="3c50a-138">이 가이드에서는 MDM(모바일 장치 관리)을 설정하는 데 대해 설명하고 일부 장치 구성을 설정하고 인증서 및 프록시와 관련한 액세스가 허용되는 Wi-Fi 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="3c50a-139">그러나 MDM을 사용하여 CSP 및 정책을 통해 장치 제한을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="3c50a-140">대부분의 경우 디바이스에 연결 제한이 있을 수 있습니다(예: Bluetooth, VPN, USB 또는 카메라 또는 마이크에 대한 액세스 끄기).</span><span class="sxs-lookup"><span data-stu-id="3c50a-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="3c50a-141">이러한 관심사 중 한 가지가 있는 경우 일반적인 장치 제한 페이지를 [읽어보는 것이 좋습니다.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)</span><span class="sxs-lookup"><span data-stu-id="3c50a-141">If any of these interests you, then we encourage you to read our [common device restrictions page](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="3c50a-142">사용할 수 있는 기타 더 복잡한 장치 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="3c50a-143">예:</span><span class="sxs-lookup"><span data-stu-id="3c50a-143">Such as:</span></span>

- <span data-ttu-id="3c50a-144">[SettingsPageVisibility를](https://docs.microsoft.com/hololens/settings-uri-list)사용하여 설정 앱에서 볼 수 있는 페이지를 제한하여 사용자가 설정 연결을 변경하는 등 조정해야 하는 설정에만 액세스할 Wi-Fi 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="3c50a-145">[키오스크 모드를 사용하여](https://docs.microsoft.com/hololens/hololens-kiosk) 디바이스의 사용자에게 표시되는 UI를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-145">Use [Kiosk mode](https://docs.microsoft.com/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="3c50a-146">키오스크를 설정하여 단일 앱 또는 사용자 지정 시작 페이지가 있는 여러 앱을 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="3c50a-147">키오스크는 사용자마다 다른 환경을 제공 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="3c50a-148">특정 앱 또는 프로세스가 완전히 시작되지 못하도록 [하는 WDAC(Windows](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 응용 프로그램 제어)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c50a-148">[Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="3c50a-149">장치 관리 또는 장치 제한의 추가 방법에 대해 알아보고자 하는 경우 다음 단계를 진행하고 장치 관리 개요 [를 읽어 하세요.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)</span><span class="sxs-lookup"><span data-stu-id="3c50a-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).</span></span>





