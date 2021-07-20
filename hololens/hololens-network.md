---
title: 네트워크에 HoloLens 연결
description: HoloLens를 사용하여 인터넷을 설정하고 연결하는 방법과 장치 IP 주소를 식별하는 방법을 알아봅니다.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, 무선, 인터넷, IP, IP 주소
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640222"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="5270c-104">네트워크에 HoloLens 연결</span><span class="sxs-lookup"><span data-stu-id="5270c-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="5270c-105">HoloLens에서 대부분의 작업을 수행하려면 네트워크에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="5270c-106">HoloLens에는 802.11ac를 지원하는 2x2 Wi-Fi 라디오가 포함되며, 이를 네트워크에 연결하는 것은 Windows 10 데스크톱 또는 모바일 장치를 Wi-Fi 네트워크에 연결하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="5270c-107">이 가이드는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-107">This guide will help you:</span></span>

- <span data-ttu-id="5270c-108">Wi-Fi를 사용하여 네트워크에 연결하거나, HoloLens 2의 경우에 한해 Wi-Fi Direct 또는 USB-C를 통한 이더넷을 사용하는 방법으로도 네트워크에 연결</span><span class="sxs-lookup"><span data-stu-id="5270c-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="5270c-109">Wi-Fi를 사용하지 않도록 설정했다가 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5270c-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="5270c-110">[HoloLens 오프라인 사용](hololens-offline.md)에 대해 자세히 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="5270c-111">처음 연결</span><span class="sxs-lookup"><span data-stu-id="5270c-111">Connecting for the first time</span></span>

<span data-ttu-id="5270c-112">HoloLens를 처음 사용할 때 Wi-Fi 네트워크에 연결하는 방법에 대한 안내를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="5270c-113">설치하는 동안 Wi-Fi에 연결하는 데 문제가 있는 경우, 네트워크가 공개 네트워크인지, 암호로 보호된 네트워크인지 또는 종속 포털 네트워크인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="5270c-114">또한 네트워크에 연결하기 위해 인증서를 사용할 필요가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="5270c-115">설정 후, 다른 유형의 Wi-Fi 네트워크에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="5270c-116">HoloLens 2 장치에서 사용자는 [USB-C-이더넷 어댑터를 사용](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)하여 장치 설정을 지원하기 위해 Wi-Fi에 직접 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="5270c-117">장치가 설정되면 사용자는 어댑터를 계속 사용하거나 어댑터에서 장치를 분리하고 [설정한 후 Wi-Fi에 연결](hololens-network.md#connecting-to-wi-fi-after-setup)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="5270c-118">설정 후 Wi-Fi에 연결</span><span class="sxs-lookup"><span data-stu-id="5270c-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="5270c-119">**시작 제스처** 를 수행하고 **설정** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="5270c-120">설정 앱이 자동으로 앞에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="5270c-121">**네트워크 및 인터넷** > **Wi-Fi** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="5270c-122">Wi-Fi가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="5270c-123">네트워크에 표시되지 않으면 목록을 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="5270c-124">네트워크를 선택하고 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="5270c-125">네트워크 암호를 묻는 메시지가 표시되면 입력하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi 설정](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="5270c-127">Wi-Fi 네트워크에 연결되어 있는지 확인하려면 **시작** 메뉴에서 Wi-Fi 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="5270c-128">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="5270c-129">**시작** 메뉴의 왼쪽 위에서 Wi-Fi 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="5270c-130">Wi-Fi의 상태와 연결된 네트워크의 SSID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="5270c-131">Wi-Fi를 사용할 수 없는 경우 [셀룰러 및 5G 네트워크에 연결](hololens-cellular.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5270c-132">기본적으로 사용자는 HoloLens 2의 Wi-Fi 로밍 동작을 미세 조정할 수 없습니다. **Wi-Fi 목록을 새로 고치는 유일한 방법은 Wi-Fi를 껐다가 켜는 것입니다**.</span><span class="sxs-lookup"><span data-stu-id="5270c-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="5270c-133">이를 통해 장치가 범위에서 벗어나면 AP에 "갇힌" 상태로 유지되는 등의 많은 문제가 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="5270c-134">엔터프라이즈 Wi-Fi 네트워크에 HoloLens 연결</span><span class="sxs-lookup"><span data-stu-id="5270c-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="5270c-135">엔터프라이즈 Wi-Fi 프로필은 EAP(확장할 수 있는 인증 프로토콜)를 사용하여 Wi-Fi 연결을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="5270c-136">[Windows 구성 디자이너](/windows/configuration/provisioning-packages/provisioning-packages)에서 생성한 프로비전 패키지 또는 MDM을 통해 HoloLens 엔터프라이즈 Wi-Fi 프로필을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="5270c-137">Microsoft Intune 관리 장치의 경우 구성 지침은 [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="5270c-138">WCD에서 Wi-Fi 프로비전 패키지를 만들려면 미리 구성된 Wi-Fi 프로필 .xml 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="5270c-139">다음은 WPA2-엔터프라이즈 EAP-TLS 인증을 위한 샘플 Wi-Fi 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="5270c-140">EAP 유형에 따라 장치에 서버 루트 CA 인증서 및 클라이언트 인증서를 프로비전해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="5270c-141">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="5270c-141">Additional resources:</span></span>

- <span data-ttu-id="5270c-142">WLANv1Profile 스키마: [[MS-GPWL]: 무선 LAN 프로필 v1 스키마 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="5270c-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="5270c-143">EAP-TLS 스키마: [[MS-GPWL]: Microsoft EAP TLS 스키마 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="5270c-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="5270c-144">Wi-Fi에 연결하는 데 문제가 있는 경우 [문제 해결](hololens2-enterprise-troubleshooting.md#) 페이지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="5270c-145">네트워크 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="5270c-145">Configure Network Proxy</span></span>

<span data-ttu-id="5270c-146">이 섹션에서는 Windows HTTP 스택을 사용하는 HoloLens OS 및 UWP(유니버설 Windows 플랫폼) 앱에 대한 네트워크 프록시에 대해 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="5270c-147">비 Windows HTTP 스택을 사용하는 애플리케이션에는 자체 프록시 구성 및 처리가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="5270c-148">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="5270c-148">Proxy Configurations</span></span> 

- <span data-ttu-id="5270c-149">PAC(프록시 자동 구성) 스크립트: [PAC 파일](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file)(비 Microsoft 사이트 열기)에는 JavaScript 함수 FindProxyForURL(url, host)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="5270c-150">정적 프록시: 서버:포트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="5270c-151">WPAD(웹 프록시 자동 검색 프로토콜): DHCP 또는 DNS를 통해 프록시 구성 파일의 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="5270c-152">프록시 프로비전 방법</span><span class="sxs-lookup"><span data-stu-id="5270c-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="5270c-153">프록시를 프로비전하는 방법은 다음 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="5270c-154">**설정 UI:**</span><span class="sxs-lookup"><span data-stu-id="5270c-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="5270c-155">사용자별 프록시(20H2 이하):</span><span class="sxs-lookup"><span data-stu-id="5270c-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="5270c-156">시작 메뉴를 열고 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="5270c-157">네트워크 및 인터넷을 선택한 다음, 왼쪽 메뉴에서 프록시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="5270c-158">수동 프록시 설정까지 아래로 스크롤하고 프록시 서버 사용을 켜기로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="5270c-159">프록시 서버의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="5270c-160">포트 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-160">Enter the port number.</span></span>
        6. <span data-ttu-id="5270c-161">저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-161">Click Save.</span></span>
      1. <span data-ttu-id="5270c-162">WiFi 프록시(21H1 이상):</span><span class="sxs-lookup"><span data-stu-id="5270c-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="5270c-163">시작 메뉴를 열고 Wi-Fi 네트워크의 속성 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="5270c-164">프록시까지 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="5270c-165">수동 설정으로 변경</span><span class="sxs-lookup"><span data-stu-id="5270c-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="5270c-166">프록시 서버의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="5270c-167">포트 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-167">Enter the port number.</span></span>
          1. <span data-ttu-id="5270c-168">적용을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="5270c-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="5270c-169">**MDM**</span></span> 
     1. <span data-ttu-id="5270c-170">Intune - 다음 [단계](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)를 사용하여 Intune에서 프록시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="5270c-171">섹션의 아래쪽으로 스크롤해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="5270c-172">기타 타사 MDM 솔루션 - [WiFi CSP](/windows/client-management/mdm/wifi-csp)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="5270c-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="5270c-173">**PPKG**</span></span> 
    1. <span data-ttu-id="5270c-174">Windows 구성 디자이너를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="5270c-175">Advanced Provisioning을 클릭하고 새 프로젝트 이름을 입력한 후 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="5270c-176">Windows Holographic(HoloLens 2)을 선택하고 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="5270c-177">PPKG(선택 사항)를 가져오고 마침을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="5270c-178">런타임 설정 -> Connectivity Profiles -> WLAN -> WLAN Proxy를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="5270c-179">Wi-Fi 네트워크의 SSID를 입력하고 추가를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="5270c-180">왼쪽 창에서 Wi-Fi 네트워크를 선택하고 원하는 사용자 지정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="5270c-181">활성화된 사용자 지정은 왼쪽 메뉴에 굵게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="5270c-182">Save and Exit을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="5270c-183">HoloLens에 프로비전 패키지 [적용](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)</span><span class="sxs-lookup"><span data-stu-id="5270c-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="5270c-184">[CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)는 Microsoft Intune과 타사 MDM 서비스 공급자 모두에서 Windows 10에 대한 많은 관리 작업 및 정책 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="5270c-185">[Windows 구성 디자이너](/windows/configuration/provisioning-packages/provisioning-install-icd)를 사용하여 [프로비전 패키지](/windows/configuration/provisioning-packages/provisioning-packages)를 만들고 HoloLens 2에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="5270c-186">HoloLens 2에 적용될 가능성이 가장 높은 CSP는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="5270c-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): 프로필별 Wi-Fi 프록시</span><span class="sxs-lookup"><span data-stu-id="5270c-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="5270c-188">HoloLens 장치에서 지원되는 다른 CSP</span><span class="sxs-lookup"><span data-stu-id="5270c-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="5270c-189">VPN</span><span class="sxs-lookup"><span data-stu-id="5270c-189">VPN</span></span>
<span data-ttu-id="5270c-190">VPN 연결을 사용하면 회사 네트워크와 인터넷에 더 안전하게 연결하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="5270c-191">HoloLens 2는 기본 제공 VPN 클라이언트와 UWP(유니버설 Windows 플랫폼) VPN 플러그 인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="5270c-192">지원되는 기본 제공 VPN 프로토콜:</span><span class="sxs-lookup"><span data-stu-id="5270c-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="5270c-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="5270c-193">IKEv2</span></span>
- <span data-ttu-id="5270c-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="5270c-194">L2TP</span></span>
- <span data-ttu-id="5270c-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="5270c-195">PPTP</span></span>

<span data-ttu-id="5270c-196">인증서를 사용하여 기본 제공 VPN 클라이언트를 인증하는 경우에는 필수 클라이언트 인증서를 사용자 인증서 저장소에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="5270c-197">타사 VPN 플러그 인이 HoloLens 2를 지원하는지 확인하려면 저장소로 이동하여 VPN 앱을 찾고, HoloLens가 지원되는 장치에 표시되는지와 시스템 요구 사항 페이지에서 ARM 또는 ARM64 아키텍처를 지원하는지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="5270c-198">HoloLens는 타사 VPN 유니버설 Windows 플랫폼 응용 프로그램만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="5270c-199">VPN은 [설정/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)을 통해 MDM에서 관리하고 [Vpnv2-csp 정책](/windows/client-management/mdm/vpnv2-csp)을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="5270c-200">[다음 가이드](/windows/security/identity-protection/vpn/vpn-guide)를 사용하여 [VPN을 구성하는 방법](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="5270c-201">UI를 통한 VPN</span><span class="sxs-lookup"><span data-stu-id="5270c-201">VPN via UI</span></span>

<span data-ttu-id="5270c-202">VPN은 기본적으로 사용되지 않지만 **설정** 앱을 열고 **네트워크 및 인터넷 -> VPN** 으로 이동하여 수동으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="5270c-203">VPN 공급자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="5270c-204">연결 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-204">Create a connection name.</span></span> 
1. <span data-ttu-id="5270c-205">서버 이름 또는 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="5270c-206">VPN 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-206">Select the VPN type.</span></span>
1. <span data-ttu-id="5270c-207">로그인 정보 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="5270c-208">필요에 따라 사용자 이름과 암호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="5270c-209">VPN 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-209">Apply the VPN settings.</span></span> 

![HoloLens VPN 설정](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="5270c-211">프로비전 패키지를 통해 설정된 VPN</span><span class="sxs-lookup"><span data-stu-id="5270c-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="5270c-212">Microsoft의 Windows Holographic, 버전 20H2에서는 VPN 연결을 위한 프록시 구성 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="5270c-213">이 흐름을 사용하려면 장치를 이 빌드로 업그레이드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="5270c-214">Windows 구성 디자이너를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="5270c-215">**Provision HoloLens devices** 를 클릭한 다음, 대상 장치를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="5270c-216">패키지 이름 및 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-216">Enter package name and path.</span></span>
1. <span data-ttu-id="5270c-217">**Switch to advanced editor** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="5270c-218">**런타임 설정** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="5270c-219">VPNProfileName을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="5270c-220">ProfileType: **네이티브** 또는 **제3자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="5270c-221">네이티브 프로필의 경우 **NativeProtocolType** 을 선택한 다음 서버, 라우팅 정책, 인증 유형 및 기타 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="5270c-222">"제3자" 프로필의 경우 서버 URL, VPN 플러그인 앱 패키지 제품군 이름(사전 정의된 3개만) 및 사용자 지정 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="5270c-223">패키지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-223">Export your package.</span></span>
1. <span data-ttu-id="5270c-224">HoloLens를 연결하고 .ppkg 파일을 장치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="5270c-225">HoloLens에서 시작 메뉴를 열고 **설정** -> **계정** -> **회사 또는 학교 액세스** -> **Add or remove provisioning package** -> Select your VPN package를 선택하여 VPN .ppkg를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="5270c-226">Intune을 통해 VPN 설정</span><span class="sxs-lookup"><span data-stu-id="5270c-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="5270c-227">시작하려면 Intune 문서의 내용을 그대로 따르세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="5270c-228">다음 단계를 수행할 때는 HoloLens 장치가 지원하는 기본 제공 VPN 프로토콜을 기억하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="5270c-229">[Intune에서 VPN 서버에 연결할 VPN 프로필 만들기](/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="5270c-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="5270c-230">[Intune을 사용하여 VPN 연결을 추가하기 위한 Windows 10 및 Windows Holographic 장치 설정](/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="5270c-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="5270c-231">완료되면 [프로필을 할당](/mem/intune/configuration/device-profile-assign)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="5270c-232">타사 MDM 솔루션을 통한 VPN</span><span class="sxs-lookup"><span data-stu-id="5270c-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="5270c-233">타사 VPN 연결 예:</span><span class="sxs-lookup"><span data-stu-id="5270c-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="5270c-234">네이티브 IKEv2 VPN 예:</span><span class="sxs-lookup"><span data-stu-id="5270c-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="5270c-235">HoloLens(1세대)에서 Wi-Fi를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5270c-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="5270c-236">HoloLens에서 설정 앱 사용</span><span class="sxs-lookup"><span data-stu-id="5270c-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="5270c-237">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="5270c-238">**시작** 메뉴의 오른쪽에 있는 **시작** 또는 **모든 앱** 목록에서 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="5270c-239">**설정** 앱이 자동으로 앞에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="5270c-240">**네트워크 및 인터넷** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="5270c-241">Wi-Fi 슬라이더 스위치를 선택하여 **Off** 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="5270c-242">그러면 Wi-Fi 라디오의 RF 구성 요소가 꺼지고 HoloLens에서 모든 Wi-Fi 기능을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="5270c-243">Wi-Fi 라디오를 사용하지 않도록 설정하면 HoloLens에서 [공간](hololens-spaces.md)을 자동으로 로드할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="5270c-244">슬라이더 스위치를 **On** 위치로 이동하여 Wi-Fi 라디오를 켜고 Microsoft HoloLens에서 Wi-Fi 기능을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="5270c-245">선택한 Wi-Fi 라디오 상태(**On** 또는 **Off**)는 다시 부팅해도 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="5270c-246">Wi-Fi 네트워크에서 HoloLens의 IP 주소 식별</span><span class="sxs-lookup"><span data-stu-id="5270c-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="5270c-247">설정 앱 사용</span><span class="sxs-lookup"><span data-stu-id="5270c-247">By using the Settings app</span></span>

1. <span data-ttu-id="5270c-248">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="5270c-249">**시작** 메뉴의 오른쪽에 있는 **시작** 또는 **모든 앱** 목록에서 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="5270c-250">**설정** 앱이 자동으로 앞에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="5270c-251">**네트워크 및 인터넷** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="5270c-252">사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 설정의 하드웨어 속성](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="5270c-254">IP 주소가 **IPv4 주소** 옆에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="5270c-255">음성 명령 사용</span><span class="sxs-lookup"><span data-stu-id="5270c-255">By using voice commands</span></span>

<span data-ttu-id="5270c-256">장치 구축에 따라 기본 제공 음성 명령 또는 Cortana를 사용하여 IP 주소를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="5270c-257">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 이후의 빌드에서 "내 IP 주소가 무엇인가요?"라고 말해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="5270c-258">그러면 IP 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-258">and it will be displayed.</span></span> <span data-ttu-id="5270c-259">이전 빌드 또는 HoloLens(1세대)의 경우 "Cortana, 내 IP 주소가 무엇인가요?"라고 말해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5270c-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="5270c-260">그러면 Cortana가 IP 주소를 표시하고 읽어 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="5270c-261">Windows 장치 포털 사용</span><span class="sxs-lookup"><span data-stu-id="5270c-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="5270c-262">PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="5270c-263">**네트워킹** 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="5270c-264">이 섹션에는 IP 주소와 기타 네트워크 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="5270c-265">이 방법을 사용하여 개발 PC에서 IP 주소를 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="5270c-266">IP 주소를 고정 IP 주소로 변경</span><span class="sxs-lookup"><span data-stu-id="5270c-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="5270c-267">설정 사용</span><span class="sxs-lookup"><span data-stu-id="5270c-267">By using Settings</span></span>
 
1. <span data-ttu-id="5270c-268">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="5270c-269">**시작** 메뉴의 오른쪽에 있는 **시작** 또는 **모든 앱** 목록에서 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="5270c-270">**설정** 앱이 자동으로 앞에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="5270c-271">**네트워크 및 인터넷** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="5270c-272">사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="5270c-273">**IP 설정 편집** 창에서 첫 번째 필드를 **수동** 으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="5270c-274">나머지 필드에 원하는 IP 구성을 입력한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="5270c-275">Windows 장치 포털 사용</span><span class="sxs-lookup"><span data-stu-id="5270c-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="5270c-276">PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="5270c-277">**네트워킹** 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="5270c-278">**IPv4 구성** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="5270c-279">**다음 IP 주소 사용** 을 선택하고 원하는 TCP/IP 구성을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="5270c-280">**다음 DNS 서버 주소 사용** 을 선택하고 필요한 경우 기본 설정 및 대체 DNS 서버 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="5270c-281">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5270c-281">Click **Save**.</span></span> 
