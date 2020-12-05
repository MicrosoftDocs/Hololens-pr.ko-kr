---
title: 배포 가이드 - 원격 지원으로 클라우드 연결 HoloLens 2 배포 대규모 배포 - 유지 관리
description: 클라우드 연결 네트워크를 통해 HoloLens 장치 유지 관리 팁
keywords: HoloLens, 관리, 클라우드 연결, 원격 지원, AAD, Azure AD, MDM, 모바일 장치 관리
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: beee64159415c0635812463f81c0b5565e44e4a8
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196350"
---
# <span data-ttu-id="b5868-104">유지 관리 - 클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="b5868-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="b5868-105">업데이트</span><span class="sxs-lookup"><span data-stu-id="b5868-105">Updates</span></span>

<span data-ttu-id="b5868-106">Microsoft는 장치 그룹에 업데이트를 배포하고 업데이트 설치를 위해 유지 관리 기간을 정의하는 기능 같은 추가 Windows 업데이트 중심 관리 기능을 IT 관리자에게 제공하는 비즈니스용 Windows 업데이트를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="b5868-107">예정된 일수, 예약된 시간 및 장치에서 사용 시간을 설정하여 작업 시간 외에서 업데이트될 수 있도록 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 업데이트를 관리하는 방법을 배워 보십시오.</span><span class="sxs-lookup"><span data-stu-id="b5868-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="b5868-108">원격 도우미는 In-Box 앱으로, Microsoft Store 앱을 통해 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-108">Remote Assist is a In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="b5868-109">Microsoft Store를 통해 다운로드되는 모든 앱의 경우 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 앱 자체를 통해 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="b5868-110">지원 플랜</span><span class="sxs-lookup"><span data-stu-id="b5868-110">Support Plan</span></span>

<span data-ttu-id="b5868-111">지원 계획은 매우 중요한 일입니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="b5868-112">누군가 또는 그룹이 HoloLens 장치에서 등록 프로세스 문제를 해결하고 조직 내에서 HoloLens 디바이스를 일반적으로 사용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="b5868-113">사용자가 문제를 더 빠르게 해결하도록 허용하기 위해 에스컬레이터 프로세스는 다음과 유사한 방식으로 처리하도록 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-113">In order to allow your users to have the faster resolution of their issues we suggest that your escalation process is handled in a similar manner to this:</span></span>

1. <span data-ttu-id="b5868-114">지원 센터</span><span class="sxs-lookup"><span data-stu-id="b5868-114">Your Support desk.</span></span>
2. <span data-ttu-id="b5868-115">HoloLens 전문가 팀</span><span class="sxs-lookup"><span data-stu-id="b5868-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="b5868-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens 문제 해결 Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b5868-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="b5868-117">고객 지원</span><span class="sxs-lookup"><span data-stu-id="b5868-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="b5868-118">개발 계획</span><span class="sxs-lookup"><span data-stu-id="b5868-118">Development Plan</span></span>

<span data-ttu-id="b5868-119">장치를 성공적으로 등록하면 이제 장치에 LOB 앱(LOB 앱)을 배포할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="b5868-120">이러한 앱은 요구 사항을 충족하기 위해&#39;사용자 지정 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="b5868-121">이미 업무용 앱이 있는 경우 [MDM을](https://docs.microsoft.com/hololens/app-deploy-intune)&#39;앱을 배포할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="b5868-122">다른&#39;원하는 경우 [HoloLens 2의](https://docs.microsoft.com/hololens/app-deploy-overview) 응용 프로그램 배포 개요를 검토하여 장치에 LOB 앱을 배포하는 더 많은 방법을 알아보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="b5868-123">아직 LOB 앱을&#39;아직 만들지 않았거나 아직 만드는 프로세스에 있는 경우 혼합 현실 개발 [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) docs를 검토하여 디자인 및 프로토타이핑을 시작하거나 혼합 현실 개발을 시작할 핵심 개념을 배워야 [합니다.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="b5868-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="b5868-124">장치 관리</span><span class="sxs-lookup"><span data-stu-id="b5868-124">Device Management</span></span> 

<span data-ttu-id="b5868-125">이 가이드에서는 MDM(모바일 장치 관리) 설정에 대해 설명하는 동안 장치 제한이나 정책을 장치에 적용하는 데 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="b5868-126">장치 관리를 사용하여 인증서를 푸시하여 액세스를 허용하거나 다양한 장치 제한으로 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="b5868-127">대부분의 경우 디바이스에 연결 제한(예: Bluetooth VPN, USB) 또는 카메라 또는 마이크에 대한 액세스를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="b5868-128">이러한 관심 사항이 있는 경우 일반적인 장치 제한 페이지를 [읽어보는 것이 좋습니다.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="b5868-128">If any of these interest you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="b5868-129">사용할 수 있는 기타 더 복잡한 장치 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="b5868-130">예:</span><span class="sxs-lookup"><span data-stu-id="b5868-130">Such as:</span></span>

- <span data-ttu-id="b5868-131">[SettingsPageVisibility를](settings-uri-list.md)사용하여 설정 앱에서 볼 수 있는 페이지를 제한하여 사용자가 설정 연결 변경과 같이 조정해야 하는 설정에만 액세스할 수 Wi-Fi 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="b5868-132">[키오스크 모드를 사용하여](hololens-kiosk.md) 디바이스의 사용자에게 표시되는 UI를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="b5868-133">키오스크를 설정하여 단일 앱 또는 사용자 지정 시작 페이지가 있는 여러 앱을 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="b5868-134">키오스크는 사용자마다 다른 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="b5868-135">특정 앱 또는 프로세스가 완전히 시작되지 못하도록 [하는 WDAC(Windows](windows-defender-application-control-wdac.md) 응용 프로그램 제어)입니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="b5868-136">장치 관리 또는 장치 제한의 다양한 방법에 대해 알아보고자 하는 경우 다음 단계를 진행하고 장치 관리 개요를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b5868-136">If you'd like to learn about more different methods of device management or device restrictions then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="b5868-137">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b5868-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b5868-138">CSP 및 장치 관리 개요 읽기</span><span class="sxs-lookup"><span data-stu-id="b5868-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)