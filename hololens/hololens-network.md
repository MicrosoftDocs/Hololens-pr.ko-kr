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
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442597"
---
# <a name="connect-hololens-to-a-network"></a>네트워크에 HoloLens 연결

HoloLens에서 대부분의 작업을 수행하려면 네트워크에 연결되어 있어야 합니다. HoloLens에는 802.11ac 지원, 2x2 Wi-Fi 라디오가 포함되며 네트워크에 연결하는 것은 Windows 10 데스크톱 또는 모바일 장치를 Wi-Fi 네트워크에 연결하는 것과 비슷합니다. 이 가이드는 다음을 지원합니다.

- Wi-Fi 또는 USB-C에서 이더넷을 사용하여(HoloLens 2에만 해당) 네트워크에 연결
- Wi-Fi를 사용하지 않도록 설정하고 다시 사용하도록 설정

[오프라인으로 HoloLens 사용](hololens-offline.md)에 대한 자세한 내용을 알아보세요.

## <a name="connecting-for-the-first-time"></a>처음 연결

HoloLens를 처음 사용할 때 Wi-Fi 네트워크에 연결하는 방법에 대한 안내를 받습니다. 설치하는 동안 Wi-Fi에 연결하는 데 문제가 있는 경우, 네트워크가 공개, 암호로 보호된 네트워크 또는 종속 포털 네트워크인지 확인합니다. 또한 네트워크에 연결하기 위해 인증서를 사용할 필요가 없는지 확인합니다. 설정 후, 다른 유형의 Wi-Fi 네트워크에 연결할 수 있습니다.

HoloLens 2 장치에서 사용자는 [USB-C에서 이더넷 어댑터를 사용](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)하여 Wi-Fi에 직접 연결하여 장치 설정을 지원할 수도 있습니다. 장치가 설정되면 사용자는 어댑터를 계속 사용하거나 어댑터에서 장치를 분리하고 [설정 후에 Wi-Fi에 연결할 수 있습니다.](hololens-network.md#connecting-to-wi-fi-after-setup) 

## <a name="connecting-to-wi-fi-after-setup"></a>설치 후 Wi-Fi에 연결

1. **Start gesture** and select **Settings**을 실행합니다. 설정 앱이 자동 배치됩니다.
1. **네트워크 및 인터넷** > **Wi-Fi**를 선택합니다. Wi-Fi가 켜져 있는지 확인합니다. 네트워크에 표시되지 않으면 목록을 아래로 스크롤합니다.
1. 네트워크를 선택하고 **연결**을 선택합니다.
1. 네트워크 암호를 묻는 메시지가 표시되면 입력하고 **다음**을 선택합니다.

![HoloLens Wi-Fi 설정](./images/hololens-2-wifi-settings.jpg)

Wi-Fi 네트워크에 연결되어 있는지 확인하려면 **시작** 메뉴에서 Wi-Fi 상태를 확인합니다.

1. **시작** 메뉴를 엽니다.
1. **시작** 메뉴의 왼쪽 위에 있는 Wi-Fi 상태를 확인합니다. Wi-Fi의 상태와 연결된 네트워크의 SSID가 표시됩니다.

> [!TIP]
> Wi-Fi를 사용할 수 없는 경우 [셀룰러 및 5G네트워크에 연결](https://docs.microsoft.com/hololens/hololens-cellular)할 수도 있습니다.

> [!IMPORTANT]
> 기본적으로 사용자는 HoloLens 2의 Wi-Fi 로밍 동작을 미세 조정할 수 없습니다. **Wi-Fi 목록을 새로 고칠 수 있는 유일한 방법은 Wi-Fi를 끄고 켜는 것입니다.** 이를 통해 장치가 범위에서 벗어나면 AP에 "갇힌" 상태로 유지되는 것과 같은 많은 문제가 방지됩니다.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>Wi-Fi에 대한 연결 문제 해결

Wi-Fi에 연결하는 데 문제가 있는 경우 [Wi-Fi에 연결할 수 없음](./hololens-faq.md#i-cant-connect-to-wi-fi)을 참조하세요.

장치에서 엔터프라이즈 또는 조직 계정에 로그인하는 경우 IT 관리자가 정책을 구성한다면 MDM(모바일 장치 관리) 정책을 적용할 수도 있습니다.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>HoloLens를 엔터프라이즈 Wi-Fi 네트워크에 연결

엔터프라이즈 Wi-Fi 프로필은 EAP(확장할 수 있는 인증 프로토콜)를 사용하여 Wi-Fi 연결을 인증합니다. [](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)Windows 구성 디자이너[](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)에서 생성한 프로비저닝 패키지 또는 MDM을 통해 HoloLens 엔터프라이즈 Wi-Fi 프로필을 구성할 수 있습니다.

Microsoft Intune 관리 디바이스의 경우 구성 지침은 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)을(를) 참조합니다.

WCD에서 Wi-Fi 프로비저닝 패키지를 생성하려면 미리 구성된 Wi-Fi 프로필 .xml 파일이 필요합니다. 다음은 WPA2-엔터프라이즈 EAP-TLS 인증을 위한 샘플 Wi-Fi 프로필입니다.

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


EAP 유형에 따라 장치에 서버 루트 CA 인증서 및 클라이언트 인증서를 프로비저닝해야 할 수 있습니다.

추가 리소스:

- WLANv1Profile Schema: [[MS-GPWL]: 무선 LAN 프로필 V1 스키마 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS 스키마: [[MS-GPWL]: MICROSOFT EAP TLS 스키마 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### <a name="eap-troubleshooting"></a>EAP 문제 해결

1. 이중 확인 Wi-Fi 프로필의 설정이 올바른지 확인합니다.
   1. EAP 유형이 올바르게 구성되어 있습니다. 일반적인 EAP 유형: EAP-TLS(13), EAP-TTLS(21), PEAP(25).
   1. Wi-Fi SSID 이름이 올바르고 HEX 문자열과 일치합니다.
   1. EAP-TLS의 경우 TrustedRootCA에는 서버&#39;s의 신뢰할 수 있는 루트 CA 인증서의 SHA-1 해시가 포함되어 있습니다. Windows PC &quot;certutil에서 사용할 수 있습니다.exe -dump cert\_file\_name&quot; 명령은 인증서&#39;s SHA-1 해시 문자열을 표시합니다.
1. 액세스 지점 또는 컨트롤러 또는 AAA 서버 로그에서 네트워크 패킷 캡처를 수집하여 EAP 세션이 실패하는 위치를 확인합니다.
   1. HoloLens에서 제공하는 EAP ID가 필요하지 않을 경우 Wi-Fi 프로필이나 클라이언트 인증서를 통해 ID가 올바르게 프로비저닝되었는지 확인합니다.
   1. 서버가 HoloLens 클라이언트 인증서를 거부하는 경우 필요한 클라이언트 인증서가 장치에 프로비저닝되었는지 확인합니다.
   1. HoloLens가 서버 인증서를 거부하는 경우, 서버 루트 CA 인증서가 HoloLens에서 프로비저닝되었는지 확인합니다.
1. 엔터프라이즈 프로파일이 Wi-Fi 프로비저닝 패키지를 통해 프로비저닝된 경우 Windows 10 PC에서 프로비저닝 패키지를 적용하는 것이 좋습니다. Windows 10 PC에서도 오류가 발생하면 [Windows 클라이언트 802.1X 인증 문제 해결 가이드](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)를 따릅니다.
1. [피드백 허브](https://docs.microsoft.com/hololens/hololens-feedback)를 통해 피드백을 보내주세요.

### <a name="additional-resources"></a>추가 리소스:
- [Windows 장치에서 Wi-Fi 설정 내보내기](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a>VPN
VPN 연결을 사용 하면 회사 네트워크와 인터넷에 더 안전하게 연결하고 액세스 하는데 도움이 됩니다. HoloLens 2는 기본 제공 VPN 클라이언트와 UWP(Universal Windows Platform) VPN 플러그 인을 지원합니다. 

지원되는 기본 제공 VPN 프로토콜:
- IKEv2
- L2TP
- PPTP

기본 제공 VPN 클라이언트를 인증 하는데 인증서를 사용하는 경우에는 필수 클라이언트 인증서를 사용자 인증서 저장소에 추가 해야 합니다. 타사 VPN 플러그 인이 HoloLens 2를 지원 하는지 확인 하려면 스토어로 이동하여 VPN 앱을 찾고, HoloLens가 지원 되는 장치에 표시 되는지 여부를 확인하고 시스템 요구 사항 페이지에서 ARM 또는 ARM64 아키텍처를 지원합니다. HoloLens는 타사 VPN 유니버설 Windows 플랫폼 응용 프로그램만 지원 합니다.

 [설정/허용VPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)를 통해 MDM으로 VPN을 관리하고 [Vpnv2-csp 정책](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)을 통해 설정할 수 있습니다.

[가이드를](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide) 사용하여 [VPN을 구성하는 방법](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)에 대해 자세히 알아보세요.  

### <a name="vpn-via-ui"></a>UI를 통한 VPN

VPN은 기본적으로 사용 하도록 설정 되지 않지만 앱**설정**을 열고 **네트워크 및 인터넷 > VPN**으로 이동하여 수동으로 설정할 수 있습니다.
1. VPN 제공자를 선택합니다.
1. 연결 이름을 만듭니다. 
1. 서버 이름 또는 주소를 입력합니다.
1. VPN 유형을 선택합니다.
1. 로그인 정보 유형을 선택합니다. 
1. 선택적으로 사용자 이름과 암호를 추가합니다.
1. VPN 설정을 적용합니다. 

![HoloLens VPN 설정입니다.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Provisioning 패키지를 통해 VPN이 설정되었습니다.

> [!TIP] 
> Microsoft의 Windows 홀로그래픽 버전 20H2에서는 VPN 연결을 위한 프록시 구성 문제를 해결했습니다. 이 흐름을 사용하려면 장치를 이 빌드로 업그레이드해 주십시오.

1. Windows Configuration Designer를 시작합니다.
1. **HoloLens 디바이스 프로비저닝**을(를) 클릭한 후 대상 디바이스와 **다음**을(를) 선택합니다.
1. 패키지 이름 및 경로를 입력합니다.
1. **고급 편집기로 전환**을 클릭합니다.
1. **런타임 설정** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**을 엽니다.
1. VPNProfileName을 구성합니다.
1. ProfileType: **기본** 또는 **제3자**를 선택합니다.
    1. 네이티브 프로파일의 경우 **NativeProtocolType**을(를) 선택한 다음 서버, 라우팅 정책, 인증 유형 및 기타 설정을 구성합니다.
    1. "타사" 프로파일의 경우 서버 URL, VPN 플러그인 앱 패키지 제품군 이름(사전 정의된 3개만) 및 사용자 지정 구성을 구성합니다.
1. 패키지를 내보냅니다.
1. HoloLens를 연결하고 .ppkg 파일을 장치에 복사합니다. 
1. HoloLens에서 시작 메뉴를 열고 **설정**  -> **계정** -> ** 액세스 회사 또는 학교** -> **를 선택하여 VPN .ppkg를 적용합니다. 프로비저닝 패키지 추가 또는 제거**-> VPN 패키지 선택.


### <a name="setting-up-vpn-via-intune"></a>Intune을 통해 VPN 설정
시작하려면 Intune 문서의 내용을 따르기면 됩니다. 다음 단계를 수행할 때는 HoloLens 장치가 지원하는 기본 제공 VPN 프로토콜을 기억하시기 바랍니다. 

[Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)의 VPN 서버에 연결할 VPN 프로파일을 생성합니다.

[Intune을 사용하여 VPN 연결을 추가하려면 Windows 10 및 Windows Holographic 장치 설정](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)을 참조하세요.

완료되면 [프로파일을 할당](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)해야 합니다.

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

기본 IKEv2 VPN 예:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>HoloLens(1세대)에서 Wi-Fi 사용 안 함

### <a name="using-the-settings-app-on-hololens"></a>HoloLens에서 설정 앱 사용

1. **시작** 메뉴를 엽니다.
1. **시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다. **설정** 앱이 자동 배치됩니다.
1. **네트워크 및 인터넷**을 선택합니다.
1. Wi-Fi 슬라이더 스위치를 선택하여 **끄기** 위치로 이동합니다. 이는 Wi-Fi 무선 송수신 장치의 RF 구성 요소를 끄고 HoloLens에서 모든 Wi-Fi 기능을 사용하지 않도록 설정합니다.

    > [!WARNING]
    > Wi-Fi 무선 송수신 장치를 사용하지 않도록 설정하면 HoloLens에서 자동으로 [공백을](hololens-spaces.md)로드할 수 없게 됩니다.

1. 슬라이더 스위치를 **켜기** 위치로 이동하여 Wi-Fi 무선 송수신 장치를 켜고 Microsoft HoloLens에서 Wi-Fi 기능을 복원합니다. 선택한 Wi-Fi 무선 송수신 장치 상태(**켜기** 또는 **끄기**)는 다시 부팅하는 동안 유지됩니다.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Wi-Fi 네트워크에서 HoloLens의 IP 주소 식별

### <a name="by-using-the-settings-app"></a>설정 앱 사용

1. **시작** 메뉴를 엽니다.
1. **시작** 또는 **시작** 메뉴의 오른쪽에 있는 **모든 앱** 목록에 있는 **설정** 앱을 선택합니다. **설정** 앱이 자동 배치됩니다.
1. **네트워크 및 인터넷**을 선택합니다.
1. 사용할 수 있는 Wi-Fi 네트워크 목록 아래까지 아래로 스크롤하고 **하드웨어 속성**을 선택합니다.

    ![Wi-Fi 설정의 하드웨어 속성](./images/wifi-hololens-hwdetails.jpg)

   IP 주소는 **IPv4 주소**옆에 나타납니다.

### <a name="by-using-voice-commands"></a>음성 명령을 사용하여

장치 구축에 따라 기본 제공 음성 명령 또는 Cortana를 사용하여 IP 주소를 표시할 수 있습니다. [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 후 빌드에 "내 IP 주소가 무엇인가요?" 말하기 그러면 표시 됩니다. 이전 빌드 또는 HoloLens(1세대)의 경우 "안녕 Cortana 내 IP 주소가 무엇인가요?"라고 말합니다. Cortana가 IP 주소를 표시하고 읽습니다.

### <a name="by-using-windows-device-portal"></a>Windows 장치 포털 사용

1. PC의 웹 브라우저에서 [장치 포털](/windows/mixed-reality/using-the-windows-device-portal.md#networking)을 엽니다.
1. **네트워킹** 섹션으로 이동합니다.  
   이 섹션에는 IP 주소와 기타 네트워크 정보가 표시됩니다. 이 방법을 사용하여 개발 PC에서 IP 주소를 복사하여 붙여 넣을 수 있습니다.
