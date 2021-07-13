---
title: 배포 가이드-원격 지원으로 대규모 클라우드 연결 HoloLens 2 배포-유지 관리
description: 클라우드 연결 네트워크를 통해 HoloLens 장치를 유지 관리 하 고 지 원하는 데 대 한 팁을 최신 상태로 유지 하세요.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635163"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="f6e49-104">유지 관리-클라우드 연결 가이드</span><span class="sxs-lookup"><span data-stu-id="f6e49-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="f6e49-105">업데이트</span><span class="sxs-lookup"><span data-stu-id="f6e49-105">Updates</span></span>

<span data-ttu-id="f6e49-106">Microsoft는 IT 관리자에 게 장치 그룹에 업데이트를 배포 하 고 업데이트를 설치 하기 위한 유지 관리 기간을 정의 하는 기능과 같은 추가 Windows 업데이트 중심 관리 기능을 제공 하도록 Windows 업데이트 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="f6e49-107">예약 된 날짜, 예약 된 시간을 비롯 하 여 [HoloLens 업데이트를 관리](/hololens/hololens-updates) 하는 방법 및 장치에서 활성 시간을 설정 하 여 업무 외 시간에 업데이트 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="f6e49-108">원격 지원 In-Box 앱 이며 Microsoft Store 앱을 통해 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="f6e49-109">Microsoft Store을 통해 다운로드 되는 모든 앱의 경우 Microsoft Store 앱 자체 [를 통해 수동으로 업데이트할](/hololens/holographic-store-apps#update-apps) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="f6e49-110">지원 플랜</span><span class="sxs-lookup"><span data-stu-id="f6e49-110">Support Plan</span></span>

<span data-ttu-id="f6e49-111">지원 플랜은 매우 좋은 일입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="f6e49-112">HoloLens 장치에서 등록 프로세스의 문제를 해결 하 고 조직 내에서 HoloLens 장치를 일반적으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="f6e49-113">사용자가 문제를 보다 빠르게 해결할 수 있도록 하기 위해 에스컬레이션 프로세스를 다음과 같은 순서로 처리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="f6e49-114">지원 센터.</span><span class="sxs-lookup"><span data-stu-id="f6e49-114">Your Support desk.</span></span>
2. <span data-ttu-id="f6e49-115">HoloLens 전문가 팀</span><span class="sxs-lookup"><span data-stu-id="f6e49-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="f6e49-116">[문서 HoloLens](/hololens/)  /  [HoloLens 문제 해결 문서](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="f6e49-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="f6e49-117">지원 문의</span><span class="sxs-lookup"><span data-stu-id="f6e49-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="f6e49-118">개발 계획</span><span class="sxs-lookup"><span data-stu-id="f6e49-118">Development Plan</span></span>

<span data-ttu-id="f6e49-119">장치를 성공적으로 등록 하면 LOB (기간 업무) 앱을 장치에 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="f6e49-120">이러한 앱은 조직&#39;필요에 맞게 빌드된 사용자 지정 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="f6e49-121">Lob (기간 업무) 앱이 이미 있는 경우 [MDM을 통해 앱을 배포할](/hololens/app-deploy-intune)준비를&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="f6e49-122">d를 사용&#39;하 여 다른 방법을 선호 하는 경우 [에는 HoloLens 2에 대 한 응용 프로그램 배포 개요](/hololens/app-deploy-overview) 를 검토 하 여 장치에 LOB 앱을 배포 하는 방법에 대 한 자세한 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f6e49-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="f6e49-123">사용자 고유의 LOB 앱을 만들거나 아직 만든 프로세스에 있는 경우에는 혼합 현실 개발 문서를 검토 하 여 [혼합 현실](/windows/mixed-reality/discover/get-started-with-mr) 개발을 시작 하는 데&#39;도움이 되는 핵심 개념을 [설계 하 고 프로토타입](/windows/mixed-reality/design/design) 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="f6e49-124">디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="f6e49-124">Device Management</span></span> 

<span data-ttu-id="f6e49-125">이 가이드는 장치 제한을 적용 하는 데 사용 되지 않은 MDM (모바일 장치 관리) 설정에 대해 설명 했지만 장치에 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="f6e49-126">장치 관리를 사용 하 여 인증서를 푸시하여 액세스를 허용 하거나 다양 한 장치 제한 사항으로 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="f6e49-127">대부분의 경우 장치는 Bluetooth, VPN, USB 등의 연결 제한이 있거나 카메라 또는 마이크에 대 한 액세스를 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="f6e49-128">이러한 관심사가 있으면 [일반적인 장치 제한 페이지](hololens-common-device-restrictions.md)를 참조 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="f6e49-129">사용할 수 있는 기타 복잡 한 장치 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="f6e49-130">예:</span><span class="sxs-lookup"><span data-stu-id="f6e49-130">Such as:</span></span>

- <span data-ttu-id="f6e49-131">[Settingspagevisibility](settings-uri-list.md)를 사용 하 여 설정 앱에서 볼 수 있는 페이지를 제한 하 여 사용자가 Wi-Fi 연결을 변경 하는 등 조정 해야 하는 설정에만 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="f6e49-132">[키오스크 모드](hololens-kiosk.md) 를 사용 하 여 장치에서 사용자에 게 표시 되는 UI를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="f6e49-133">단일 앱 또는 사용자 지정 시작 페이지를 사용 하 여 여러 앱을 표시 하도록 키오스크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="f6e49-134">키오스크는 다른 사용자에 게 다른 환경을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="f6e49-135">[응용 프로그램 제어 (WDAC)를 Windows](windows-defender-application-control-wdac.md) 하 여 특정 앱 또는 프로세스가 완전히 시작 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e49-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="f6e49-136">장치 관리 또는 장치 제한에 대 한 다른 방법을 알아보려면 다음 단계를 수행 하 고 장치 관리 개요를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6e49-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="f6e49-137">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f6e49-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f6e49-138">Csp 및 장치 관리 개요 읽기</span><span class="sxs-lookup"><span data-stu-id="f6e49-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)