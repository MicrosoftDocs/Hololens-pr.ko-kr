---
title: 네트워크에 HoloLens 연결
description: HoloLens로 인터넷에 연결하는 방법 및 장치의 IP 주소를 식별하는 방법에 대한 지침입니다.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, 무선, 인터넷, IP, IP 주소
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009526"
---
# <span data-ttu-id="d719c-104">네트워크에 HoloLens 연결</span><span class="sxs-lookup"><span data-stu-id="d719c-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="d719c-105">HoloLens에서 대부분의 작업을 수행하려면 네트워크에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="d719c-106">이 가이드는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-106">This guide will help you:</span></span>

- <span data-ttu-id="d719c-107">Wi-Fi 또는 USB-C에서 이더넷을 사용하여(HoloLens 2에만 해당) 네트워크에 연결</span><span class="sxs-lookup"><span data-stu-id="d719c-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="d719c-108">Wi-Fi를 사용하지 않도록 설정하고 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d719c-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="d719c-109">[오프라인으로 HoloLens 사용](hololens-offline.md)에 대한 자세한 내용을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d719c-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="d719c-110">처음 연결</span><span class="sxs-lookup"><span data-stu-id="d719c-110">Connecting for the first time</span></span>

<span data-ttu-id="d719c-111">HoloLens를 처음 사용할 때 Wi-Fi 네트워크에 연결하는 방법에 대한 안내를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="d719c-112">설치하는 동안 Wi-Fi에 연결하는 데 문제가 있는 경우, 네트워크가 공개, 암호로 보호된 네트워크 또는 종속 포털 네트워크인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="d719c-113">네트워크에 연결할 때 인증서를 사용할 필요가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="d719c-114">설정 후, 다른 유형의 Wi-Fi 네트워크에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="d719c-115">HoloLens 2 장치의 경우 사용자가 [USB 타입 C에서 이더넷 어댑터](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)를 사용하여 Wi-Fi에 직접 연결하여 장치 설정을 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="d719c-116">장치가 설정되면 사용자가 어댑터를 계속 사용할 수도 있고 설정 후 장치와 어댑터의 연결을 끊고 [Wi-Fi에 연결](hololens-network.md#connecting-to-wi-fi-after-setup)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="d719c-117">설치 후 Wi-Fi에 연결</span><span class="sxs-lookup"><span data-stu-id="d719c-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="d719c-118">**Start gesture** and select **Settings**을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="d719c-119">설정 앱이 자동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="d719c-120">**네트워크 및 인터넷** > **Wi-Fi**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="d719c-121">Wi-Fi가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="d719c-122">네트워크에 표시되지 않으면 목록을 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="d719c-123">네트워크를 선택하고 **연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="d719c-124">네트워크 암호를 묻는 메시지가 표시되면 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="d719c-125">HoloLens에는 802.11ac 가능, 2x2 Wi-Fi 무선 송수신 장치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="d719c-126">HoloLens를 Wi-Fi 네트워크에 연결하는 것은 Windows 10 데스크톱 또는 모바일 장치를 Wi-Fi 네트워크에 연결하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens Wi-Fi 설정](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="d719c-128">**시작** 메뉴에서 Wi-Fi 상태를 확인하여 Wi-Fi 네트워크에 연결되어 있는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="d719c-129">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="d719c-130">**시작** 메뉴의 왼쪽 위에 있는 Wi-Fi 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="d719c-131">Wi-Fi의 상태와 연결된 네트워크의 SSID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="d719c-132">Wi-Fi에 대한 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d719c-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="d719c-133">Wi-Fi에 연결하는 데 문제가 있는 경우 [Wi-Fi에 연결할 수 없음](./hololens-faq.md#i-cant-connect-to-wi-fi)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d719c-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="d719c-134">장치에서 엔터프라이즈 또는 조직 계정에 로그인하는 경우 IT 관리자가 정책을 구성한다면 MDM(모바일 장치 관리) 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="d719c-135">VPN</span><span class="sxs-lookup"><span data-stu-id="d719c-135">VPN</span></span>
<span data-ttu-id="d719c-136">VPN 연결을 사용 하면 회사 네트워크와 인터넷에 더 안전하게 연결하고 액세스 하는데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-136">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="d719c-137">HoloLens 2는 기본 제공 VPN 클라이언트와 UWP(Universal Windows Platform) VPN 플러그 인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-137">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="d719c-138">지원되는 기본 제공 VPN 프로토콜:</span><span class="sxs-lookup"><span data-stu-id="d719c-138">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="d719c-139">IKEv2</span><span class="sxs-lookup"><span data-stu-id="d719c-139">IKEv2</span></span>
- <span data-ttu-id="d719c-140">L2TP</span><span class="sxs-lookup"><span data-stu-id="d719c-140">L2TP</span></span>
- <span data-ttu-id="d719c-141">PPTP</span><span class="sxs-lookup"><span data-stu-id="d719c-141">PPTP</span></span>

<span data-ttu-id="d719c-142">기본 제공 VPN 클라이언트를 인증 하는데 인증서를 사용하는 경우에는 필수 클라이언트 인증서를 사용자 인증서 저장소에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-142">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="d719c-143">타사 VPN 플러그 인이 HoloLens 2를 지원 하는지 확인 하려면 스토어로 이동하여 VPN 앱을 찾고, HoloLens가 지원 되는 장치에 표시 되는지 여부를 확인하고 시스템 요구 사항 페이지에서 ARM 또는 ARM64 아키텍처를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-143">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="d719c-144">HoloLens는 타사 VPN 유니버설 Windows 플랫폼 응용 프로그램만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-144">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="d719c-145">VPN은 기본적으로 사용 하도록 설정 되지 않지만 앱**설정**을 열고 **네트워크 및 인터넷 > VPN**으로 이동하여 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-145">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="d719c-146">[설정/허용VPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)를 통해 MDM으로 VPN을 관리하고 [Vpnv2-csp 정책](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-146">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="d719c-147">[가이드를](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide) 사용하여 [VPN을 구성하는 방법](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d719c-147">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="d719c-148">HoloLens(1세대)에서 Wi-Fi 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d719c-148">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="d719c-149">HoloLens에서 설정 앱 사용</span><span class="sxs-lookup"><span data-stu-id="d719c-149">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="d719c-150">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-150">Open the **Start** menu.</span></span>
1. <span data-ttu-id="d719c-151">**시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-151">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="d719c-152">**설정** 앱이 자동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-152">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="d719c-153">**네트워크 및 인터넷**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-153">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="d719c-154">Wi-Fi 슬라이더 스위치를 선택하여 **끄기** 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-154">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="d719c-155">이는 Wi-Fi 무선 송수신 장치의 RF 구성 요소를 끄고 HoloLens에서 모든 Wi-Fi 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-155">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="d719c-156">Wi-Fi 무선 송수신 장치를 사용하지 않도록 설정하면 HoloLens에서 자동으로 [공백을](hololens-spaces.md)로드할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-156">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="d719c-157">슬라이더 스위치를 **켜기** 위치로 이동하여 Wi-Fi 무선 송수신 장치를 켜고 Microsoft HoloLens에서 Wi-Fi 기능을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-157">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="d719c-158">선택한 Wi-Fi 무선 송수신 장치 상태(**켜기** 또는 **끄기**)는 다시 부팅하는 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-158">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="d719c-159">Wi-Fi 네트워크에서 HoloLens의 IP 주소 식별</span><span class="sxs-lookup"><span data-stu-id="d719c-159">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="d719c-160">설정 앱 사용</span><span class="sxs-lookup"><span data-stu-id="d719c-160">By using the Settings app</span></span>

1. <span data-ttu-id="d719c-161">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-161">Open the **Start** menu.</span></span>
1. <span data-ttu-id="d719c-162">**시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-162">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="d719c-163">**설정** 앱이 자동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-163">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="d719c-164">**네트워크 및 인터넷**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-164">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="d719c-165">사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-165">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 설정의 하드웨어 속성](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="d719c-167">IP 주소는 **IPv4 주소**옆에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-167">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="d719c-168">음성 명령을 사용하여</span><span class="sxs-lookup"><span data-stu-id="d719c-168">By using voice commands</span></span>

<span data-ttu-id="d719c-169">장치 구축에 따라 기본 제공 음성 명령 또는 Cortana를 사용하여 IP 주소를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-169">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="d719c-170">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 후 빌드에 "내 IP 주소가 무엇인가요?" 말하기</span><span class="sxs-lookup"><span data-stu-id="d719c-170">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="d719c-171">그러면 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-171">and it will be displayed.</span></span> <span data-ttu-id="d719c-172">이전 빌드 또는 HoloLens(1세대)의 경우 "안녕 Cortana 내 IP 주소가 무엇인가요?"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-172">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="d719c-173">Cortana가 IP 주소를 표시하고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-173">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="d719c-174">Windows 장치 포털 사용</span><span class="sxs-lookup"><span data-stu-id="d719c-174">By using Windows Device Portal</span></span>

1. <span data-ttu-id="d719c-175">PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-175">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="d719c-176">**네트워킹** 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-176">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="d719c-177">이 섹션에는 IP 주소와 기타 네트워크 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-177">This section displays your IP address and other network information.</span></span> <span data-ttu-id="d719c-178">이 방법을 사용하여 개발 PC에서 IP 주소를 복사하여 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d719c-178">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
