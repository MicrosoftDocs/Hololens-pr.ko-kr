---
title: MAC 주소에 HoloLens 장치의 엔터프라이즈 등록으로 제한된 Wi-Fi 환경
description: HoloLens 2 장치의 네트워크에 대한 MAC 주소를 설정하는 방법
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093244"
---
# <span data-ttu-id="a66f2-103">MAC 주소에 HoloLens 장치의 엔터프라이즈 등록으로 제한된 Wi-Fi 환경</span><span class="sxs-lookup"><span data-stu-id="a66f2-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="a66f2-104">이 문서에서는 Wi-Fi가 MAC 주소에 의해 제한되고 혹은 무선 네트워크에 가입하려면 인증서가 필요한 고객의 환경에서 식별한 일반적인 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="a66f2-105">예제 시나리오:</span><span class="sxs-lookup"><span data-stu-id="a66f2-105">Example Scenario</span></span>

<span data-ttu-id="a66f2-106">보안 환경의 많은 고객에게는 무선 또는 유선 네트워크에 대한 제한 사항이 있어 승인된 장치만(MAC 주소 기반) 연결할 수 있습니다(무선 액세스 지점 또는 DHCP 서버에서 MAC 주소 필터링 포함).</span><span class="sxs-lookup"><span data-stu-id="a66f2-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="a66f2-107">또한 일부 무선 네트워크는 PEAP를 사용하여 보호될 수 있으며, 이 경우 무선 네트워크를 성공적으로 인증하기 전에 장치에 인증서를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="a66f2-108">HoloLens 장치에서 두 가지 주요 문제가 발생할 수 있으며 이는 HoloLens 장치를 네트워크에 연결하는 데 지연 시간과 수동 작업을 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="a66f2-109">장치를 무선 네트워크에 연결시키기 전에 무선 PEAP 인증서를 장치에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="a66f2-110">HoloLens Wi-fi 어댑터의 MAC 주소는 등록되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="a66f2-111">이에 대한 주요 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="a66f2-112">MAC 주소는 현재 장치의 설정 앱에서만 식별되거나 Intune을 제대로 등록한 후 Intune에서 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="a66f2-113">MAC 주소가 없으면 장치에서 Wi-Fi 네트워크에 연결하여 등록을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="a66f2-114">이러한 문제의 수동적 해결 방법은 장치에 기술자의 도움을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="a66f2-115">해결 방법</span><span class="sxs-lookup"><span data-stu-id="a66f2-115">Solutions</span></span>

<span data-ttu-id="a66f2-116">환경 내에서 사용할 수 있는 인프라에 따라 이 상황을 개선하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="a66f2-117">솔루션</span><span class="sxs-lookup"><span data-stu-id="a66f2-117">Solution</span></span> | <span data-ttu-id="a66f2-118">장점</span><span class="sxs-lookup"><span data-stu-id="a66f2-118">Benefits</span></span> | <span data-ttu-id="a66f2-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a66f2-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a66f2-120">이더넷 어댑터를 통한 프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="a66f2-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="a66f2-121">OOBE 환경을 개선하고 보다 신속한 기술자 환경을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="a66f2-122">HoloLens와 호환되는 USB C HubTechnician은 MAC용 장치와 캡처 및 OOBE finalisation을 위해 계속 상호 작용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="a66f2-123">이더넷을 통해 Intune이 등록된 Autopilot</span><span class="sxs-lookup"><span data-stu-id="a66f2-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="a66f2-124">고객 환경에 대한 단일 단계 연결 및 장치 등록을 통해 Mac 캡처는 장치와 상호 작용하지 않고도 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="a66f2-125">고객 AAD TenantHoloLens 호환 USB-C 네트워크 어댑터로 Intune 사용</span><span class="sxs-lookup"><span data-stu-id="a66f2-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="a66f2-126">MAC 주소의 자동화된 보고</span><span class="sxs-lookup"><span data-stu-id="a66f2-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="a66f2-127">Intune 테넌트에 장치를 등록한 경우, MAC 주소 보고를 기술자에게 스크립팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="a66f2-128">Intune Powershell Commandlets</span><span class="sxs-lookup"><span data-stu-id="a66f2-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="a66f2-129">이더넷 어댑터를 통한 프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="a66f2-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="a66f2-130">유선 네트워크에서도 MAC 제한이 적용되는 경우, USB-C 이더넷 어댑터/허브의 MAC 주소는 사전 승인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="a66f2-131">이 허브를 사용하여 다른 장치에서 네트워크로 액세스할 수 있으므로 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="a66f2-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a66f2-132">Requirements</span></span>

- <span data-ttu-id="a66f2-133">고객 네트워크에 대한 액세스 권한이 있는 유선 네트워크 포트</span><span class="sxs-lookup"><span data-stu-id="a66f2-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="a66f2-134">이더넷 어댑터를 포함하는 HoloLens 호환 USB-C 허브 - 추가 드라이버나 응용 프로그램을 설치하지 않아도 되는 허브면 적합할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="a66f2-135">프로비저닝 패키지 구성:</span><span class="sxs-lookup"><span data-stu-id="a66f2-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="a66f2-136">무선 네트워크 정보 및 인증서를 포함</span><span class="sxs-lookup"><span data-stu-id="a66f2-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="a66f2-137">선택적으로 조직의 Azure AD에 대한 등록 정보 포함</span><span class="sxs-lookup"><span data-stu-id="a66f2-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="a66f2-138">그 외 필요한 프로비저닝 설정 포함</span><span class="sxs-lookup"><span data-stu-id="a66f2-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="a66f2-139">프로세스</span><span class="sxs-lookup"><span data-stu-id="a66f2-139">Process</span></span>

<span data-ttu-id="a66f2-140">이 프로세스는 장치의 소프트웨어 수준에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="a66f2-141">장치에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004)가 있는 경우, 아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="a66f2-142">프로비전닝 패키지를 USB 스틱의 루트에 놓고 허브에 꽂습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="a66f2-143">이더넷 케이블을 허브에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="a66f2-144">HoloLens 장치에 USB-C 허브를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="a66f2-145">HoloLens 장치를 켜고 착용합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="a66f2-146">**볼륨 작게 및 전원 단추**를 눌러 프로비저닝 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="a66f2-147">이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 장치의 MAC 주소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="a66f2-148">장치에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004) 이전에 OS 빌드를 설치한 경우, 아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="a66f2-149">HoloLens 장치를 켜고 장치를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="a66f2-150">장치가 PC에서 파일 저장소 장치로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="a66f2-151">장치에 프로비저닝 패키지 복사</span><span class="sxs-lookup"><span data-stu-id="a66f2-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="a66f2-152">이더넷 케이블을 허브에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="a66f2-153">HoloLens 장치에 USB-C 허브를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="a66f2-154">장치를 착용합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-154">Wear the device.</span></span>
7. <span data-ttu-id="a66f2-155">**볼륨 작게 및 전원 단추**를 눌러 프로비저닝 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="a66f2-156">이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 장치의 MAC 주소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="a66f2-157">장점</span><span class="sxs-lookup"><span data-stu-id="a66f2-157">Benefits</span></span>

<span data-ttu-id="a66f2-158">이렇게 하면 장치의 &quot;단일 터치&quot;가 올바른 프로비저닝 패키지를 적용하고 장치의 MAC 주소를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="a66f2-159">여기에 나와 있는 지침에 따라 프로비저닝 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="a66f2-160">Intune 등록을 통한 Autopilot</span><span class="sxs-lookup"><span data-stu-id="a66f2-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="a66f2-161">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a66f2-161">Requirements</span></span>

- <span data-ttu-id="a66f2-162">고객 네트워크에 대한 액세스 권한이 있는 유선 네트워크 포트</span><span class="sxs-lookup"><span data-stu-id="a66f2-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="a66f2-163">Windows Holographic 2004를 실행하는 HoloLens 장치</span><span class="sxs-lookup"><span data-stu-id="a66f2-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="a66f2-164">HoloLens 호환 USB-C 허브</span><span class="sxs-lookup"><span data-stu-id="a66f2-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="a66f2-165">Intune을 설정하고 고객 테넌트에 대해 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="a66f2-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="a66f2-166">Autopilot에 등록되어 고객 테넌트로 가져온 장치</span><span class="sxs-lookup"><span data-stu-id="a66f2-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="a66f2-167">장치에 대해 정의된 Intune 정책:</span><span class="sxs-lookup"><span data-stu-id="a66f2-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="a66f2-168">무선 네트워크 정보 및 인증서를 포함</span><span class="sxs-lookup"><span data-stu-id="a66f2-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="a66f2-169">그 외 필요한 프로비저닝 설정 포함</span><span class="sxs-lookup"><span data-stu-id="a66f2-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="a66f2-170">이는 고급 네트워킹 요구 사항을 포함하는 고객은 장치를 자동으로 확장 가능한 방식으로 등록할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="a66f2-171">아래와 같은 추가 필수 조건이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="a66f2-172">Autopilot 미리 보기에 테넌트를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="a66f2-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="a66f2-173">HoloLens 정책을 만들어 Intune 내에서 프로비저닝 패키지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="a66f2-174">HoloLens Intune 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="a66f2-175">올바른 그룹에 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="a66f2-176">프로세스</span><span class="sxs-lookup"><span data-stu-id="a66f2-176">Process</span></span>

1. <span data-ttu-id="a66f2-177">USB-C 허브 및 이더넷 케이블을 HoloLens 2 장치에 꽂습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="a66f2-178">HoloLens 2를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="a66f2-179">장치가 이더넷 어댑터를 통해 OOBE에서 인터넷에 자동으로 연결하고, Autopilot 구성을 감지하고, Azure AD 및 Intune을 통해 자동으로 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="a66f2-180">장치에서 Intune을 통해 필요한 Wi-Fi 인증서와 필요에 따라 추가 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="a66f2-181">완료되면 기술자는 Intune (끝점 관리자) 포털을 로드하고 **홈-> 장치 -> DeviceName -> 하드웨어**에서 장치 속성 페이지에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="a66f2-182">Wifi MAC 주소는 Intune 포털 내에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Intune을 통한 MAC 주소](images/mac-address-intune.jpg)

7. <span data-ttu-id="a66f2-184">기술자는 이 MAC 주소를 허용되는 장치로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="a66f2-185">장점</span><span class="sxs-lookup"><span data-stu-id="a66f2-185">Benefits</span></span>

<span data-ttu-id="a66f2-186">이렇게 하면 기술자가 장치를 착용하거나 HoloLens 환경을 수동으로 조작하지 않고도 &quot;장치 미착용&quot; 상태로 장치는 상자에서 AAD 및 Intune에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="a66f2-187">기술자에게 MAC 주소 보고</span><span class="sxs-lookup"><span data-stu-id="a66f2-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="a66f2-188">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a66f2-188">Requirements</span></span>

- <span data-ttu-id="a66f2-189">고객 테넌트에 대한 &quot;Intune 그래프 Powershell&quot;의 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a66f2-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="a66f2-190">기술자 컴퓨터에 Intune 그래프 Powershell 설치</span><span class="sxs-lookup"><span data-stu-id="a66f2-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="a66f2-191">Intune의 &quot;관리되는 장치&quot; 요소에 대 한 읽기 액세스 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="a66f2-192">(지원 센터 연산자나 상위 또는 사용자 지정 역할)</span><span class="sxs-lookup"><span data-stu-id="a66f2-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="a66f2-193">현재로서는 Intune 내에서 새 장치의 등록을 기반으로 자동화 명령을 트리거하는 &quot;간단한&quot; 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="a66f2-194">따라서 이 명령은 기술자에게 포털에 로그인하여 수동으로 검색할 필요없이 MAC 주소를 검색하는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="a66f2-195">이는 최근 30일 이내에 등록된 모든 HoloLens 장치의 이름과 MAC 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Powershell을 통한 MAC 주소](images/mac-address-powershell.jpg)

### <span data-ttu-id="a66f2-197">프로세스</span><span class="sxs-lookup"><span data-stu-id="a66f2-197">Process</span></span>

<span data-ttu-id="a66f2-198">Intune 등록을 완료한 후, 기술자는 위의 스크립트를 실행하여 MAC 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a66f2-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
