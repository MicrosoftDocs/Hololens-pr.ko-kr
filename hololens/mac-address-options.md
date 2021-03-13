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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407623"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="3a8fd-103">MAC 주소에 HoloLens 장치의 엔터프라이즈 등록으로 제한된 Wi-Fi 환경</span><span class="sxs-lookup"><span data-stu-id="3a8fd-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="3a8fd-104">이 문서에서는 Wi-Fi가 MAC 주소에 의해 제한되고 혹은 무선 네트워크에 가입하려면 인증서가 필요한 고객의 환경에서 식별한 일반적인 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="3a8fd-105">예제 시나리오:</span><span class="sxs-lookup"><span data-stu-id="3a8fd-105">Example Scenario</span></span>

<span data-ttu-id="3a8fd-106">보안 환경의 많은 고객이 무선 또는 유선 네트워크에 제한이 있습니다. 이 제한은 승인된 장치(MAC 주소 기반)만 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="3a8fd-107">이 제한은 무선 액세스 지점에서 MAC 주소 필터링을 통해 또는 DHCP 서버를 통해 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="3a8fd-108">또한 일부 무선 네트워크는 PEAP로 보호될 수 있습니다. 이 경우 무선 네트워크를 인증하기 전에 장치에 인증서를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="3a8fd-109">이 시나리오에서는 HoloLens 장치를 네트워크에 가입할 때 두 가지 주요 요구 사항으로 인해 지연이 발생하거나 수동으로 개입해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="3a8fd-110">장치를 무선 네트워크에 연결시키기 전에 무선 PEAP 인증서를 장치에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="3a8fd-111">HoloLens Wi-Fi 어댑터의 MAC 주소는 등록되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="3a8fd-112">위 요구 사항을 충족할 때 주요 과제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="3a8fd-113">MAC 주소는 현재 장치의 설정 앱에서만 식별되거나 제대로 등록한 후 Intune에서 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="3a8fd-114">MAC 주소가 없으면 장치에서 Wi-Fi 네트워크에 연결하여 등록을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="3a8fd-115">이러한 문제를 수동으로 해결하려면 기술자가 장치와 상호 작용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="3a8fd-116">해결 방법</span><span class="sxs-lookup"><span data-stu-id="3a8fd-116">Solutions</span></span>

<span data-ttu-id="3a8fd-117">환경 내에서 사용할 수 있는 인프라에 따라 이 상황을 개선하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="3a8fd-118">솔루션</span><span class="sxs-lookup"><span data-stu-id="3a8fd-118">Solution</span></span> | <span data-ttu-id="3a8fd-119">장점</span><span class="sxs-lookup"><span data-stu-id="3a8fd-119">Benefits</span></span> | <span data-ttu-id="3a8fd-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a8fd-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="3a8fd-121">이더넷 어댑터를 통한 프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="3a8fd-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="3a8fd-122">OOBE 환경을 개선하고 보다 신속한 기술자 환경을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="3a8fd-123">HoloLens 호환 USB-C Hub + 이더넷 어댑터, 기술자는 여전히 MAC 캡처 및 OOBE 마무리를 위한 장치와 상호 작용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="3a8fd-124">이더넷을 통해 Intune이 등록된 Autopilot</span><span class="sxs-lookup"><span data-stu-id="3a8fd-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="3a8fd-125">단일 단계 연결 및 장치와 고객 환경에 대한 등록입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="3a8fd-126">장치와 상호 작용할 필요 없이 MAC 캡처를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="3a8fd-127">고객 AAD 테넌트 및 HoloLens 호환 USB-C 이더넷 어댑터로 Intune 사용</span><span class="sxs-lookup"><span data-stu-id="3a8fd-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="3a8fd-128">MAC 주소의 자동화된 보고</span><span class="sxs-lookup"><span data-stu-id="3a8fd-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="3a8fd-129">Intune 테넌트에 장치를 등록한 경우, MAC 주소 보고를 기술자에게 스크립팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="3a8fd-130">Intune PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="3a8fd-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="3a8fd-131">이더넷 어댑터를 통한 프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="3a8fd-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="3a8fd-132">유선 네트워크에서도 MAC 제한이 적용되는 경우, USB-C 허브 + 이더넷 어댑터의 MAC 주소도 사전 승인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="3a8fd-133">이 어댑터를 사용하여 다른 장치에서 네트워크로 액세스할 수 있으므로 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a8fd-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a8fd-134">Requirements</span></span>

- <span data-ttu-id="3a8fd-135">고객 네트워크에 대한 액세스 권한이 있는 유선 네트워크 포트</span><span class="sxs-lookup"><span data-stu-id="3a8fd-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="3a8fd-136">이더넷 어댑터가 포함된 HoloLens 호환 USB-C 허브 - 추가 드라이버나 응용 프로그램을 설치하지 않아도 되는 어댑터면 적합할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="3a8fd-137">프로비저닝 패키지 구성:</span><span class="sxs-lookup"><span data-stu-id="3a8fd-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="3a8fd-138">무선 네트워크 정보 및 인증서를 포함</span><span class="sxs-lookup"><span data-stu-id="3a8fd-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="3a8fd-139">선택적으로 조직의 Azure AD에 대한 등록 정보 포함</span><span class="sxs-lookup"><span data-stu-id="3a8fd-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="3a8fd-140">그 외 필요한 프로비저닝 설정 포함</span><span class="sxs-lookup"><span data-stu-id="3a8fd-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="3a8fd-141">프로세스</span><span class="sxs-lookup"><span data-stu-id="3a8fd-141">Process</span></span>

<span data-ttu-id="3a8fd-142">이 프로세스는 장치의 소프트웨어 수준에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="3a8fd-143">장치에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004)가 있는 경우, 아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="3a8fd-144">프로비전닝 패키지를 USB 스틱의 루트에 놓고 허브에 꽂습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="3a8fd-145">허브 + 이더넷 어댑터에 이더넷 케이블을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="3a8fd-146">HoloLens 장치에 USB-C 허브를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="3a8fd-147">HoloLens를 켜고 장치에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="3a8fd-148">**볼륨 작게 및 전원 단추**를 눌러 프로비저닝 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="3a8fd-149">이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 장치의 MAC 주소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="3a8fd-150">장치에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004) 이전에 OS 빌드를 설치한 경우, 아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="3a8fd-151">HoloLens를 켜고 장치를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="3a8fd-152">장치가 PC에서 파일 저장소 장치로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="3a8fd-153">장치에 프로비저닝 패키지 복사</span><span class="sxs-lookup"><span data-stu-id="3a8fd-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="3a8fd-154">이더넷 케이블을 허브에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="3a8fd-155">HoloLens 장치에 USB-C 허브를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="3a8fd-156">HoloLens를 두기</span><span class="sxs-lookup"><span data-stu-id="3a8fd-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="3a8fd-157">**볼륨 작게 및 전원 단추**를 눌러 프로비저닝 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="3a8fd-158">이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 장치의 MAC 주소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="3a8fd-159">장점</span><span class="sxs-lookup"><span data-stu-id="3a8fd-159">Benefits</span></span>

<span data-ttu-id="3a8fd-160">이렇게 하면 장치의 “단일 터치”가 올바른 프로비저닝 패키지를 적용하고 장치의 MAC 주소를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="3a8fd-161">여기에 나와 있는 지침에 따라 프로비저닝 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="3a8fd-162">Intune 등록을 통한 Autopilot</span><span class="sxs-lookup"><span data-stu-id="3a8fd-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="3a8fd-163">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a8fd-163">Requirements</span></span>

- <span data-ttu-id="3a8fd-164">고객 네트워크에 대한 액세스 권한이 있는 유선 네트워크 포트</span><span class="sxs-lookup"><span data-stu-id="3a8fd-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="3a8fd-165">Windows Holographic 2004를 실행하는 HoloLens 장치</span><span class="sxs-lookup"><span data-stu-id="3a8fd-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="3a8fd-166">HoloLens 호환 USB-C 이더넷 어댑터</span><span class="sxs-lookup"><span data-stu-id="3a8fd-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="3a8fd-167">Intune을 설정하고 고객 테넌트에 대해 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3a8fd-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="3a8fd-168">Autopilot에 등록되어 고객 테넌트로 가져온 장치</span><span class="sxs-lookup"><span data-stu-id="3a8fd-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="3a8fd-169">장치에 대해 정의된 Intune 정책:</span><span class="sxs-lookup"><span data-stu-id="3a8fd-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="3a8fd-170">무선 네트워크 정보 및 인증서를 포함</span><span class="sxs-lookup"><span data-stu-id="3a8fd-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="3a8fd-171">그 외 필요한 프로비저닝 설정 포함</span><span class="sxs-lookup"><span data-stu-id="3a8fd-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="3a8fd-172">이는 고급 네트워킹 요구 사항을 포함하는 고객은 장치를 자동으로 확장 가능한 방식으로 등록할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="3a8fd-173">아래와 같은 추가 필수 조건이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="3a8fd-174">[Autopilot 미리 보기에 테넌트를 사용하도록 설정](https://docs.microsoft.com/hololens/hololens2-autopilot)</span><span class="sxs-lookup"><span data-stu-id="3a8fd-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="3a8fd-175">HoloLens 정책을 만들어 Intune 내에서 프로비저닝 패키지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="3a8fd-176">HoloLens Intune 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="3a8fd-177">올바른 그룹에 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="3a8fd-178">Process</span><span class="sxs-lookup"><span data-stu-id="3a8fd-178">Process</span></span>

1. <span data-ttu-id="3a8fd-179">이더넷 케이블을 어댑터에 연결하고 HoloLens 2 장치의 USB-C 포트에 어댑터를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="3a8fd-180">HoloLens 2를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="3a8fd-181">이더넷 어댑터를 통해 OOBE 동안 장치가 자동으로 인터넷에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="3a8fd-182">자동 업데이트 구성을 감지하고 Azure AD 및 Intune에 자동으로 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="3a8fd-183">장치에서 Intune을 통해 필요한 Wi-Fi 인증서와 필요에 따라 추가 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="3a8fd-184">완료되면 기술자는 Intune (끝점 관리자) 포털을 로드하고 **홈-> 장치 -> DeviceName -> 하드웨어**에서 장치 속성 페이지에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="3a8fd-185">Wi-Fi MAC 주소는 Intune 포털 내에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Intune을 통한 MAC 주소](images/mac-address-intune.jpg)

7. <span data-ttu-id="3a8fd-187">기술자는 이 MAC 주소를 허용되는 장치로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="3a8fd-188">장점</span><span class="sxs-lookup"><span data-stu-id="3a8fd-188">Benefits</span></span>

<span data-ttu-id="3a8fd-189">이렇게 하면 기술자가 장치를 착용하거나 HoloLens 환경과 수동으로 상호 작용할 필요 없이 장치가 상자에서 Azure AD 및 Intune에 등록된 상태로 이동할 수있는 "장치 미착용" 배포 환경이 기술자에게 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="3a8fd-190">기술자에게 MAC 주소 보고</span><span class="sxs-lookup"><span data-stu-id="3a8fd-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="3a8fd-191">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a8fd-191">Requirements</span></span>

- <span data-ttu-id="3a8fd-192">고객 테넌트에 대한 “Intune Graph PowerShell”의 권한 부여</span><span class="sxs-lookup"><span data-stu-id="3a8fd-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="3a8fd-193">기술자 컴퓨터에 Intune Graph PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="3a8fd-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="3a8fd-194">Intune의 “관리되는 장치” 요소에 대 한 읽기 액세스 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="3a8fd-195">(지원 센터 연산자나 상위 또는 사용자 지정 역할)</span><span class="sxs-lookup"><span data-stu-id="3a8fd-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="3a8fd-196">현재로서는 Intune 내에서 새 장치의 등록을 기반으로 자동화 명령을 트리거하는 “간단한” 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="3a8fd-197">따라서 이 명령은 기술자에게 포털에 로그인하여 수동으로 검색할 필요없이 MAC 주소를 검색하는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="3a8fd-198">이는 최근 30일 이내에 등록된 모든 HoloLens 장치의 이름과 MAC 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![PowerShell을 통한 MAC 주소](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="3a8fd-200">프로세스</span><span class="sxs-lookup"><span data-stu-id="3a8fd-200">Process</span></span>

<span data-ttu-id="3a8fd-201">Intune 등록을 완료한 후, 기술자는 위의 스크립트를 실행하여 MAC 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8fd-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
