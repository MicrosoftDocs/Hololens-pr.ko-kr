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
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034666"
---
# <a name="connect-hololens-to-a-network"></a>네트워크에 HoloLens 연결

HoloLens에서 대부분의 작업을 수행하려면 네트워크에 연결되어 있어야 합니다. HoloLens에는 802.11ac를 지원하는 2x2 Wi-Fi 라디오가 포함되며, 이를 네트워크에 연결하는 것은 Windows 10 데스크톱 또는 모바일 장치를 Wi-Fi 네트워크에 연결하는 것과 비슷합니다. 이 가이드는 다음을 지원합니다.

- Wi-Fi를 사용하여 네트워크에 연결하거나, HoloLens 2의 경우에 한해 Wi-Fi Direct 또는 USB-C를 통한 이더넷을 사용하는 방법으로도 네트워크에 연결
- Wi-Fi를 사용하지 않도록 설정했다가 다시 사용하도록 설정

[HoloLens 오프라인 사용](hololens-offline.md)에 대해 자세히 읽어보세요.

## <a name="connecting-for-the-first-time"></a>처음 연결

HoloLens를 처음 사용할 때 Wi-Fi 네트워크에 연결하는 방법에 대한 안내를 받습니다. 설치하는 동안 Wi-Fi에 연결하는 데 문제가 있는 경우, 네트워크가 공개 네트워크인지, 암호로 보호된 네트워크인지 또는 종속 포털 네트워크인지 확인합니다. 또한 네트워크에 연결하기 위해 인증서를 사용할 필요가 없는지 확인합니다. 설정 후, 다른 유형의 Wi-Fi 네트워크에 연결할 수 있습니다.

HoloLens 2 장치에서 사용자는 [USB-C-이더넷 어댑터를 사용](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)하여 장치 설정을 지원하기 위해 Wi-Fi에 직접 연결할 수도 있습니다. 장치가 설정되면 사용자는 어댑터를 계속 사용하거나 어댑터에서 장치를 분리하고 [설정한 후 Wi-Fi에 연결](hololens-network.md#connecting-to-wi-fi-after-setup)할 수 있습니다. 

## <a name="connecting-to-wi-fi-after-setup"></a>설정 후 Wi-Fi에 연결

1. **시작 제스처** 를 수행하고 **설정** 선택합니다. 설정 앱이 자동으로 앞에 배치됩니다.
1. **네트워크 및 인터넷** > **Wi-Fi** 를 선택합니다. Wi-Fi가 켜져 있는지 확인합니다. 네트워크에 표시되지 않으면 목록을 아래로 스크롤합니다.
1. 네트워크를 선택하고 **연결** 을 선택합니다.
1. 네트워크 암호를 묻는 메시지가 표시되면 입력하고 **다음** 을 선택합니다.

![HoloLens Wi-Fi 설정.](./images/hololens-2-wifi-settings.jpg)

Wi-Fi 네트워크에 연결되어 있는지 확인하려면 **시작** 메뉴에서 Wi-Fi 상태를 확인합니다.

1. **시작** 메뉴를 엽니다.
1. **시작** 메뉴의 왼쪽 위에서 Wi-Fi 상태를 확인합니다. Wi-Fi의 상태와 연결된 네트워크의 SSID가 표시됩니다.

> [!TIP]
> Wi-Fi를 사용할 수 없는 경우 [셀룰러 및 5G 네트워크에 연결](hololens-cellular.md)할 수도 있습니다.

> [!IMPORTANT]
> 기본적으로 사용자는 HoloLens 2의 Wi-Fi 로밍 동작을 미세 조정할 수 없습니다. **Wi-Fi 목록을 새로 고치는 유일한 방법은 Wi-Fi를 껐다가 켜는 것입니다**. 이를 통해 장치가 범위에서 벗어나면 AP에 "갇힌" 상태로 유지되는 등의 많은 문제가 방지됩니다.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>엔터프라이즈 Wi-Fi 네트워크에 HoloLens 연결

엔터프라이즈 Wi-Fi 프로필은 EAP(확장할 수 있는 인증 프로토콜)를 사용하여 Wi-Fi 연결을 인증합니다. [Windows 구성 디자이너](/windows/configuration/provisioning-packages/provisioning-packages)에서 생성한 프로비전 패키지 또는 MDM을 통해 HoloLens 엔터프라이즈 Wi-Fi 프로필을 구성할 수 있습니다.

Microsoft Intune 관리 장치의 경우 구성 지침은 [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)을 참조하세요.

WCD에서 Wi-Fi 프로비전 패키지를 만들려면 미리 구성된 Wi-Fi 프로필 .xml 파일이 필요합니다. 다음은 WPA2-엔터프라이즈 EAP-TLS 인증을 위한 샘플 Wi-Fi 프로필입니다.

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


EAP 유형에 따라 장치에 서버 루트 CA 인증서 및 클라이언트 인증서를 프로비전해야 할 수 있습니다.

추가 리소스:

- WLANv1Profile 스키마: [[MS-GPWL]: 무선 LAN 프로필 v1 스키마 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS 스키마: [[MS-GPWL]: Microsoft EAP TLS 스키마 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Wi-Fi에 연결하는 데 문제가 있는 경우 [문제 해결](hololens2-enterprise-troubleshooting.md#) 페이지를 확인하세요.

## <a name="configure-network-proxy"></a>네트워크 프록시 구성

이 섹션에서는 Windows HTTP 스택을 사용하는 HoloLens OS 및 UWP(유니버설 Windows 플랫폼) 앱에 대한 네트워크 프록시에 대해 다룹니다. 비 Windows HTTP 스택을 사용하는 애플리케이션에는 자체 프록시 구성 및 처리가 있을 수 있습니다. 

### <a name="proxy-configurations"></a>프록시 구성 

- PAC(프록시 자동 구성) 스크립트: [PAC 파일](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file)(비 Microsoft 사이트 열기)에는 JavaScript 함수 FindProxyForURL(url, host)이 포함되어 있습니다. 
- 정적 프록시: 서버:포트 형식입니다.  
- WPAD(웹 프록시 자동 검색 프로토콜): DHCP 또는 DNS를 통해 프록시 구성 파일의 URL을 제공합니다. 

### <a name="proxy-provisioning-methods"></a>프록시 프로비전 방법 
프록시를 프로비전하는 방법은 다음 세 가지가 있습니다.

 

1.  **설정 UI:** 
    1. 사용자별 프록시(20H2 이하):
        1. 시작 메뉴를 열고 설정을 선택합니다.
        2. 네트워크 및 인터넷을 선택한 다음, 왼쪽 메뉴에서 프록시를 선택합니다.
        3. 수동 프록시 설정까지 아래로 스크롤하고 프록시 서버 사용을 켜기로 전환합니다.
        4. 프록시 서버의 IP 주소를 입력합니다.
        5. 포트 번호를 입력합니다.
        6. 저장을 클릭합니다.
      1. WiFi 프록시(21H1 이상):
          1. 시작 메뉴를 열고 Wi-Fi 네트워크의 속성 페이지로 이동합니다.
          1. 프록시까지 아래로 스크롤합니다.
          1. 수동 설정으로 변경
          1. 프록시 서버의 IP 주소를 입력합니다.
          1. 포트 번호를 입력합니다.
          1. 적용을 클릭합니다.
        
 2. **MDM** 
     1. Intune - 다음 [단계](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)를 사용하여 Intune에서 프록시를 구성합니다. 섹션의 아래쪽으로 스크롤해야 합니다.
     1. 기타 타사 MDM 솔루션 - [WiFi CSP](/windows/client-management/mdm/wifi-csp)를 사용합니다.

3. **PPKG** 
    1. Windows 구성 디자이너를 엽니다.
    1. Advanced Provisioning을 클릭하고 새 프로젝트 이름을 입력한 후 다음을 클릭합니다.
    1. Windows Holographic(HoloLens 2)을 선택하고 다음을 클릭합니다.
    1. PPKG(선택 사항)를 가져오고 마침을 클릭합니다.
    1. 런타임 설정 -> Connectivity Profiles -> WLAN -> WLAN Proxy를 확장합니다.
    1. Wi-Fi 네트워크의 SSID를 입력하고 추가를 클릭합니다.
    1. 왼쪽 창에서 Wi-Fi 네트워크를 선택하고 원하는 사용자 지정을 입력합니다. 활성화된 사용자 지정은 왼쪽 메뉴에 굵게 표시됩니다.
    1. Save and Exit을 클릭합니다.
    1. HoloLens에 프로비전 패키지 [적용](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

[CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)는 Microsoft Intune과 타사 MDM 서비스 공급자 모두에서 Windows 10에 대한 많은 관리 작업 및 정책 뒤에 있습니다. [Windows 구성 디자이너](/windows/configuration/provisioning-packages/provisioning-install-icd)를 사용하여 [프로비전 패키지](/windows/configuration/provisioning-packages/provisioning-packages)를 만들고 HoloLens 2에 적용할 수도 있습니다.
HoloLens 2에 적용될 가능성이 가장 높은 CSP는 다음과 같습니다.

- [WiFi CSP](/windows/client-management/mdm/wifi-csp): 프로필별 Wi-Fi 프록시 

[HoloLens 장치에서 지원되는 다른 CSP](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN 연결을 사용하면 회사 네트워크와 인터넷에 더 안전하게 연결하고 액세스할 수 있습니다. HoloLens 2는 기본 제공 VPN 클라이언트와 UWP(유니버설 Windows 플랫폼) VPN 플러그 인을 지원합니다. 

지원되는 기본 제공 VPN 프로토콜:
- IKEv2
- L2TP
- PPTP

인증서를 사용하여 기본 제공 VPN 클라이언트를 인증하는 경우에는 필수 클라이언트 인증서를 사용자 인증서 저장소에 추가해야 합니다. 타사 VPN 플러그 인이 HoloLens 2를 지원하는지 확인하려면 저장소로 이동하여 VPN 앱을 찾고, HoloLens가 지원되는 장치에 표시되는지와 시스템 요구 사항 페이지에서 ARM 또는 ARM64 아키텍처를 지원하는지를 확인하세요. HoloLens는 타사 VPN 유니버설 Windows 플랫폼 응용 프로그램만 지원합니다.

 VPN은 [설정/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)을 통해 MDM에서 관리하고 [Vpnv2-csp 정책](/windows/client-management/mdm/vpnv2-csp)을 통해 설정할 수 있습니다.

[다음 가이드](/windows/security/identity-protection/vpn/vpn-guide)를 사용하여 [VPN을 구성하는 방법](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)대해 자세히 알아보세요.  

### <a name="vpn-via-ui"></a>UI를 통한 VPN

VPN은 기본적으로 사용되지 않지만 **설정** 앱을 열고 **네트워크 및 인터넷 -> VPN** 으로 이동하여 수동으로 사용하도록 설정할 수 있습니다.
1. VPN 공급자를 선택합니다.
1. 연결 이름을 만듭니다. 
1. 서버 이름 또는 주소를 입력합니다.
1. VPN 유형을 선택합니다.
1. 로그인 정보 유형을 선택합니다. 
1. 필요에 따라 사용자 이름과 암호를 추가합니다.
1. VPN 설정을 적용합니다. 

![HoloLens VPN 설정.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>프로비전 패키지를 통해 설정된 VPN

> [!TIP] 
> Microsoft의 Windows Holographic, 버전 20H2에서는 VPN 연결을 위한 프록시 구성 문제를 해결했습니다. 이 흐름을 사용하려면 장치를 이 빌드로 업그레이드하는 것이 좋습니다.

1. Windows 구성 디자이너를 시작합니다.
1. **Provision HoloLens devices** 를 클릭한 다음, 대상 장치를 선택하고 **다음** 을 선택합니다.
1. 패키지 이름 및 경로를 입력합니다.
1. **Switch to advanced editor** 를 클릭합니다.
1. **런타임 설정** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings** 를 엽니다.
1. VPNProfileName을 구성합니다.
1. ProfileType: **네이티브** 또는 **제3자** 를 선택합니다.
    1. 네이티브 프로필의 경우 **NativeProtocolType** 을 선택한 다음 서버, 라우팅 정책, 인증 유형 및 기타 설정을 구성합니다.
    1. "제3자" 프로필의 경우 서버 URL, VPN 플러그인 앱 패키지 제품군 이름(사전 정의된 3개만) 및 사용자 지정 구성을 구성합니다.
1. 패키지를 내보냅니다.
1. HoloLens를 연결하고 .ppkg 파일을 장치에 복사합니다. 
1. HoloLens에서 시작 메뉴를 열고 **설정** -> **계정** -> **회사 또는 학교 액세스** -> **Add or remove provisioning package** -> Select your VPN package를 선택하여 VPN .ppkg를 적용합니다.


### <a name="setting-up-vpn-via-intune"></a>Intune을 통해 VPN 설정
시작하려면 Intune 문서의 내용을 그대로 따르세요. 다음 단계를 수행할 때는 HoloLens 장치가 지원하는 기본 제공 VPN 프로토콜을 기억하시기 바랍니다. 

[Intune에서 VPN 서버에 연결할 VPN 프로필 만들기](/mem/intune/configuration/vpn-settings-configure).

[Intune을 사용하여 VPN 연결을 추가하기 위한 Windows 10 및 Windows Holographic 장치 설정](/mem/intune/configuration/vpn-settings-windows-10).

완료되면 [프로필을 할당](/mem/intune/configuration/device-profile-assign)해야 합니다.

### <a name="vpn-via-3rd-party-mdm-solutions"></a>타사 MDM 솔루션을 통한 VPN
타사 VPN 연결 예:
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

네이티브 IKEv2 VPN 예:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>HoloLens(1세대)에서 Wi-Fi를 사용하지 않도록 설정

### <a name="using-the-settings-app-on-hololens"></a>HoloLens에서 설정 앱 사용

1. **시작** 메뉴를 엽니다.
1. **시작** 메뉴의 오른쪽에 있는 **시작** 또는 **모든 앱** 목록에서 **설정** 앱을 선택합니다. **설정** 앱이 자동으로 앞에 배치됩니다.
1. **네트워크 및 인터넷** 을 선택합니다.
1. Wi-Fi 슬라이더 스위치를 선택하여 **Off** 위치로 이동합니다. 그러면 Wi-Fi 라디오의 RF 구성 요소가 꺼지고 HoloLens에서 모든 Wi-Fi 기능을 사용하지 않도록 설정됩니다.

    > [!WARNING]
    > Wi-Fi 라디오를 사용하지 않도록 설정하면 HoloLens에서 [공간](hololens-spaces.md)을 자동으로 로드할 수 없게 됩니다.

1. 슬라이더 스위치를 **On** 위치로 이동하여 Wi-Fi 라디오를 켜고 Microsoft HoloLens에서 Wi-Fi 기능을 복원합니다. 선택한 Wi-Fi 라디오 상태(**On** 또는 **Off**)는 다시 부팅해도 그대로 유지됩니다.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Wi-Fi 네트워크에서 HoloLens의 IP 주소 식별

### <a name="by-using-the-settings-app"></a>설정 앱 사용

1. **시작** 메뉴를 엽니다.
1. **시작** 메뉴의 오른쪽에 있는 **시작** 또는 **모든 앱** 목록에서 **설정** 앱을 선택합니다. **설정** 앱이 자동으로 앞에 배치됩니다.
1. **네트워크 및 인터넷** 을 선택합니다.
1. 사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성** 을 선택합니다.

    ![Wi-Fi 설정의 하드웨어 속성.](./images/wifi-hololens-hwdetails.jpg)

   IP 주소가 **IPv4 주소** 옆에 나타납니다.

### <a name="by-using-voice-commands"></a>음성 명령 사용

장치 구축에 따라 기본 제공 음성 명령 또는 Cortana를 사용하여 IP 주소를 표시할 수 있습니다. [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 이후의 빌드에서 "내 IP 주소가 무엇인가요?"라고 말해 보세요. 그러면 IP 주소가 표시됩니다. 이전 빌드 또는 HoloLens(1세대)의 경우 "Cortana, 내 IP 주소가 무엇인가요?"라고 말해 보세요. 그러면 Cortana가 IP 주소를 표시하고 읽어 줍니다.

### <a name="by-using-windows-device-portal"></a>Windows 장치 포털 사용

1. PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.
1. **네트워킹** 섹션으로 이동합니다.  
   이 섹션에는 IP 주소와 기타 네트워크 정보가 표시됩니다. 이 방법을 사용하여 개발 PC에서 IP 주소를 복사하여 붙여넣을 수 있습니다.

## <a name="change-ip-address-to-static-address"></a>IP 주소를 고정 IP 주소로 변경
### <a name="by-using-settings"></a>설정 사용
 
1. **시작** 메뉴를 엽니다.
1. **시작** 메뉴의 오른쪽에 있는 **시작** 또는 **모든 앱** 목록에서 **설정** 앱을 선택합니다. **설정** 앱이 자동으로 앞에 배치됩니다.
1. **네트워크 및 인터넷** 을 선택합니다.
1. 사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성** 을 선택합니다.
1. **IP 설정 편집** 창에서 첫 번째 필드를 **수동** 으로 변경합니다.
1. 나머지 필드에 원하는 IP 구성을 입력한 다음, **저장** 을 클릭합니다.

### <a name="by-using-windows-device-portal"></a>Windows 장치 포털 사용

1. PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.
1. **네트워킹** 섹션으로 이동합니다.
1. **IPv4 구성** 단추를 선택합니다.
1. **다음 IP 주소 사용** 을 선택하고 원하는 TCP/IP 구성을 입력합니다.
1. **다음 DNS 서버 주소 사용** 을 선택하고 필요한 경우 기본 설정 및 대체 DNS 서버 주소를 입력합니다.
1. **저장** 을 클릭합니다. 
