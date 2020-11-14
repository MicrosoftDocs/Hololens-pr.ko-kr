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
ms.openlocfilehash: 7932ba493f8434c0fa5fc7a0efdd4d43eedd51bd
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163043"
---
# <span data-ttu-id="4cc2f-104">네트워크에 HoloLens 연결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="4cc2f-105">HoloLens에서 대부분의 작업을 수행하려면 네트워크에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="4cc2f-106">이 가이드는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-106">This guide will help you:</span></span>

- <span data-ttu-id="4cc2f-107">Wi-Fi 또는 USB-C에서 이더넷을 사용하여(HoloLens 2에만 해당) 네트워크에 연결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="4cc2f-108">Wi-Fi를 사용하지 않도록 설정하고 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4cc2f-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="4cc2f-109">[오프라인으로 HoloLens 사용](hololens-offline.md)에 대한 자세한 내용을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="4cc2f-110">처음 연결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-110">Connecting for the first time</span></span>

<span data-ttu-id="4cc2f-111">HoloLens를 처음 사용할 때 Wi-Fi 네트워크에 연결하는 방법에 대한 안내를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="4cc2f-112">설치하는 동안 Wi-Fi에 연결하는 데 문제가 있는 경우, 네트워크가 공개, 암호로 보호된 네트워크 또는 종속 포털 네트워크인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="4cc2f-113">네트워크에 연결할 때 인증서를 사용할 필요가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="4cc2f-114">설정 후, 다른 유형의 Wi-Fi 네트워크에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="4cc2f-115">HoloLens 2 장치의 경우 사용자가 [USB 타입 C에서 이더넷 어댑터](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)를 사용하여 Wi-Fi에 직접 연결하여 장치 설정을 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="4cc2f-116">장치가 설정되면 사용자가 어댑터를 계속 사용할 수도 있고 설정 후 장치와 어댑터의 연결을 끊고 [Wi-Fi에 연결](hololens-network.md#connecting-to-wi-fi-after-setup)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="4cc2f-117">설치 후 Wi-Fi에 연결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="4cc2f-118">**Start gesture** and select **Settings**을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="4cc2f-119">설정 앱이 자동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="4cc2f-120">**네트워크 및 인터넷** > **Wi-Fi**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="4cc2f-121">Wi-Fi가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="4cc2f-122">네트워크에 표시되지 않으면 목록을 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="4cc2f-123">네트워크를 선택하고 **연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="4cc2f-124">네트워크 암호를 묻는 메시지가 표시되면 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="4cc2f-125">HoloLens에는 802.11ac 가능, 2x2 Wi-Fi 무선 송수신 장치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="4cc2f-126">HoloLens를 Wi-Fi 네트워크에 연결하는 것은 Windows 10 데스크톱 또는 모바일 장치를 Wi-Fi 네트워크에 연결하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens Wi-Fi 설정](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="4cc2f-128">**시작** 메뉴에서 Wi-Fi 상태를 확인하여 Wi-Fi 네트워크에 연결되어 있는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="4cc2f-129">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="4cc2f-130">**시작** 메뉴의 왼쪽 위에 있는 Wi-Fi 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="4cc2f-131">Wi-Fi의 상태와 연결된 네트워크의 SSID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="4cc2f-132">Wi-Fi에 대한 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="4cc2f-133">Wi-Fi에 연결하는 데 문제가 있는 경우 [Wi-Fi에 연결할 수 없음](./hololens-faq.md#i-cant-connect-to-wi-fi)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="4cc2f-134">장치에서 엔터프라이즈 또는 조직 계정에 로그인하는 경우 IT 관리자가 정책을 구성한다면 MDM(모바일 장치 관리) 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="4cc2f-135">HoloLens를 엔터프라이즈 Wi-Fi 네트워크에 연결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="4cc2f-136">엔터프라이즈 Wi-Fi 프로필은 EAP(확장할 수 있는 인증 프로토콜)를 사용하여 Wi-Fi 연결을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="4cc2f-137">[](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)Windows 구성 디자이너[](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)에서 생성한 프로비저닝 패키지 또는 MDM을 통해 HoloLens 엔터프라이즈 Wi-Fi 프로필을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="4cc2f-138">Microsoft Intune 관리 디바이스의 경우 구성 지침은 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)을(를) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="4cc2f-139">WCD에서 Wi-Fi 프로비저닝 패키지를 생성하려면 미리 구성된 Wi-Fi 프로필 .xml 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="4cc2f-140">다음은 WPA2-엔터프라이즈 EAP-TLS 인증을 위한 샘플 Wi-Fi 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="4cc2f-141">EAP 유형에 따라 장치에 서버 루트 CA 인증서 및 클라이언트 인증서를 프로비저닝해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="4cc2f-142">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="4cc2f-142">Additional resources:</span></span>

- <span data-ttu-id="4cc2f-143">WLANv1Profile Schema: [[MS-GPWL]: 무선 LAN 프로필 V1 스키마 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="4cc2f-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="4cc2f-144">EAP-TLS 스키마: [[MS-GPWL]: MICROSOFT EAP TLS 스키마 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="4cc2f-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="4cc2f-145">EAP 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4cc2f-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="4cc2f-146">이중 확인 Wi-Fi 프로필의 설정이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="4cc2f-147">EAP 유형이 올바르게 구성되어 있습니다. 일반적인 EAP 유형: EAP-TLS(13), EAP-TTLS(21), PEAP(25).</span><span class="sxs-lookup"><span data-stu-id="4cc2f-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="4cc2f-148">Wi-Fi SSID 이름이 올바르고 HEX 문자열과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="4cc2f-149">EAP-TLS의 경우 TrustedRootCA에는 서버&#39;s의 신뢰할 수 있는 루트 CA 인증서의 SHA-1 해시가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="4cc2f-150">Windows PC &quot;certutil에서 사용할 수 있습니다.exe -dump cert\_file\_name&quot; 명령은 인증서&#39;s SHA-1 해시 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="4cc2f-151">액세스 지점 또는 컨트롤러 또는 AAA 서버 로그에서 네트워크 패킷 캡처를 수집하여 EAP 세션이 실패하는 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="4cc2f-152">HoloLens에서 제공하는 EAP ID가 필요하지 않을 경우 Wi-Fi 프로필이나 클라이언트 인증서를 통해 ID가 올바르게 프로비저닝되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="4cc2f-153">서버가 HoloLens 클라이언트 인증서를 거부하는 경우 필요한 클라이언트 인증서가 장치에 프로비저닝되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="4cc2f-154">HoloLens가 서버 인증서를 거부하는 경우, 서버 루트 CA 인증서가 HoloLens에서 프로비저닝되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="4cc2f-155">엔터프라이즈 프로파일이 Wi-Fi 프로비저닝 패키지를 통해 프로비저닝된 경우 Windows 10 PC에서 프로비저닝 패키지를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="4cc2f-156">Windows 10 PC에서도 오류가 발생하면 [Windows 클라이언트 802.1X 인증 문제 해결 가이드](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="4cc2f-157">[피드백 허브](https://docs.microsoft.com/hololens/hololens-feedback)를 통해 피드백을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="4cc2f-158">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="4cc2f-158">Additional resources:</span></span>
- [<span data-ttu-id="4cc2f-159">Windows 장치에서 Wi-Fi 설정 내보내기</span><span class="sxs-lookup"><span data-stu-id="4cc2f-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="4cc2f-160">VPN</span><span class="sxs-lookup"><span data-stu-id="4cc2f-160">VPN</span></span>
<span data-ttu-id="4cc2f-161">VPN 연결을 사용 하면 회사 네트워크와 인터넷에 더 안전하게 연결하고 액세스 하는데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="4cc2f-162">HoloLens 2는 기본 제공 VPN 클라이언트와 UWP(Universal Windows Platform) VPN 플러그 인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="4cc2f-163">지원되는 기본 제공 VPN 프로토콜:</span><span class="sxs-lookup"><span data-stu-id="4cc2f-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="4cc2f-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="4cc2f-164">IKEv2</span></span>
- <span data-ttu-id="4cc2f-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="4cc2f-165">L2TP</span></span>
- <span data-ttu-id="4cc2f-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="4cc2f-166">PPTP</span></span>

<span data-ttu-id="4cc2f-167">기본 제공 VPN 클라이언트를 인증 하는데 인증서를 사용하는 경우에는 필수 클라이언트 인증서를 사용자 인증서 저장소에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="4cc2f-168">타사 VPN 플러그 인이 HoloLens 2를 지원 하는지 확인 하려면 스토어로 이동하여 VPN 앱을 찾고, HoloLens가 지원 되는 장치에 표시 되는지 여부를 확인하고 시스템 요구 사항 페이지에서 ARM 또는 ARM64 아키텍처를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="4cc2f-169">HoloLens는 타사 VPN 유니버설 Windows 플랫폼 응용 프로그램만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="4cc2f-170">[설정/허용VPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)를 통해 MDM으로 VPN을 관리하고 [Vpnv2-csp 정책](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="4cc2f-171">[가이드를](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide) 사용하여 [VPN을 구성하는 방법](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="4cc2f-172">UI를 통한 VPN</span><span class="sxs-lookup"><span data-stu-id="4cc2f-172">VPN via UI</span></span>

<span data-ttu-id="4cc2f-173">VPN은 기본적으로 사용 하도록 설정 되지 않지만 앱**설정**을 열고 **네트워크 및 인터넷 > VPN**으로 이동하여 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="4cc2f-174">VPN 제공자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="4cc2f-175">연결 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-175">Create a connection name.</span></span> 
1. <span data-ttu-id="4cc2f-176">서버 이름 또는 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="4cc2f-177">VPN 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-177">Select the VPN type.</span></span>
1. <span data-ttu-id="4cc2f-178">로그인 정보 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="4cc2f-179">선택적으로 사용자 이름과 암호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="4cc2f-180">VPN 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-180">Apply the VPN settings.</span></span> 

![HoloLens VPN 설정입니다.](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="4cc2f-182">Provisioning 패키지를 통해 VPN이 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="4cc2f-183">Microsoft의 Windows 홀로그래픽 버전 20H2에서는 VPN 연결을 위한 프록시 구성 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="4cc2f-184">이 흐름을 사용하려면 장치를 이 빌드로 업그레이드해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="4cc2f-185">Windows Configuration Designer를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="4cc2f-186">**HoloLens 디바이스 프로비저닝**을(를) 클릭한 후 대상 디바이스와 **다음**을(를) 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="4cc2f-187">패키지 이름 및 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-187">Enter package name and path.</span></span>
1. <span data-ttu-id="4cc2f-188">**고급 편집기로 전환**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="4cc2f-189">**런타임 설정** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="4cc2f-190">VPNProfileName을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="4cc2f-191">ProfileType: **기본** 또는 **제3자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="4cc2f-192">네이티브 프로파일의 경우 **NativeProtocolType**을(를) 선택한 다음 서버, 라우팅 정책, 인증 유형 및 기타 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="4cc2f-193">"타사" 프로파일의 경우 서버 URL, VPN 플러그인 앱 패키지 제품군 이름(사전 정의된 3개만) 및 사용자 지정 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="4cc2f-194">패키지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-194">Export your package.</span></span>
1. <span data-ttu-id="4cc2f-195">HoloLens를 연결하고 .ppkg 파일을 장치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="4cc2f-196">HoloLens에서 시작 메뉴를 열고 **설정**  -> **계정** -> \*\* 액세스 회사 또는 학교\*\* -> **를 선택하여 VPN .ppkg를 적용합니다. 프로비저닝 패키지 추가 또는 제거**-> VPN 패키지 선택.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="4cc2f-197">Intune을 통해 VPN 설정</span><span class="sxs-lookup"><span data-stu-id="4cc2f-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="4cc2f-198">시작하려면 Intune 문서의 내용을 따르기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="4cc2f-199">다음 단계를 수행할 때는 HoloLens 장치가 지원하는 기본 제공 VPN 프로토콜을 기억하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="4cc2f-200">[Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)의 VPN 서버에 연결할 VPN 프로파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="4cc2f-201">[Intune을 사용하여 VPN 연결을 추가하려면 Windows 10 및 Windows Holographic 장치 설정](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="4cc2f-202">완료되면 [프로파일을 할당](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="4cc2f-203">타사 MDM 솔루션을 통한 VPN</span><span class="sxs-lookup"><span data-stu-id="4cc2f-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="4cc2f-204">타사 VPN 연결 예:</span><span class="sxs-lookup"><span data-stu-id="4cc2f-204">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="4cc2f-205">기본 IKEv2 VPN 예:</span><span class="sxs-lookup"><span data-stu-id="4cc2f-205">Native IKEv2 VPN example:</span></span>
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
## <span data-ttu-id="4cc2f-206">HoloLens(1세대)에서 Wi-Fi 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4cc2f-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="4cc2f-207">HoloLens에서 설정 앱 사용</span><span class="sxs-lookup"><span data-stu-id="4cc2f-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="4cc2f-208">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="4cc2f-209">**시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="4cc2f-210">**설정** 앱이 자동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="4cc2f-211">**네트워크 및 인터넷**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="4cc2f-212">Wi-Fi 슬라이더 스위치를 선택하여 **끄기** 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="4cc2f-213">이는 Wi-Fi 무선 송수신 장치의 RF 구성 요소를 끄고 HoloLens에서 모든 Wi-Fi 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="4cc2f-214">Wi-Fi 무선 송수신 장치를 사용하지 않도록 설정하면 HoloLens에서 자동으로 [공백을](hololens-spaces.md)로드할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="4cc2f-215">슬라이더 스위치를 **켜기** 위치로 이동하여 Wi-Fi 무선 송수신 장치를 켜고 Microsoft HoloLens에서 Wi-Fi 기능을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="4cc2f-216">선택한 Wi-Fi 무선 송수신 장치 상태(**켜기** 또는 **끄기**)는 다시 부팅하는 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="4cc2f-217">Wi-Fi 네트워크에서 HoloLens의 IP 주소 식별</span><span class="sxs-lookup"><span data-stu-id="4cc2f-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="4cc2f-218">설정 앱 사용</span><span class="sxs-lookup"><span data-stu-id="4cc2f-218">By using the Settings app</span></span>

1. <span data-ttu-id="4cc2f-219">**시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="4cc2f-220">**시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="4cc2f-221">**설정** 앱이 자동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="4cc2f-222">**네트워크 및 인터넷**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="4cc2f-223">사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 설정의 하드웨어 속성](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="4cc2f-225">IP 주소는 **IPv4 주소**옆에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="4cc2f-226">음성 명령을 사용하여</span><span class="sxs-lookup"><span data-stu-id="4cc2f-226">By using voice commands</span></span>

<span data-ttu-id="4cc2f-227">장치 구축에 따라 기본 제공 음성 명령 또는 Cortana를 사용하여 IP 주소를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="4cc2f-228">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 후 빌드에 "내 IP 주소가 무엇인가요?" 말하기</span><span class="sxs-lookup"><span data-stu-id="4cc2f-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="4cc2f-229">그러면 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-229">and it will be displayed.</span></span> <span data-ttu-id="4cc2f-230">이전 빌드 또는 HoloLens(1세대)의 경우 "안녕 Cortana 내 IP 주소가 무엇인가요?"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="4cc2f-231">Cortana가 IP 주소를 표시하고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="4cc2f-232">Windows 장치 포털 사용</span><span class="sxs-lookup"><span data-stu-id="4cc2f-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="4cc2f-233">PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="4cc2f-234">**네트워킹** 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="4cc2f-235">이 섹션에는 IP 주소와 기타 네트워크 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="4cc2f-236">이 방법을 사용하여 개발 PC에서 IP 주소를 복사하여 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
