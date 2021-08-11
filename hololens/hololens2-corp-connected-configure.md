---
title: 배포 가이드 - Dynamics 365 Guides 사용하는 회사 연결 HoloLens 2 - 구성
description: Dynamics 365 Guides 사용하여 회사 연결된 네트워크를 통해 HoloLens 2 디바이스를 배포하도록 구성을 설정하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 2b855f5891dfa4ca695e4ae3b2a2e82510c5b626f08b434643169be239b48291
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660179"
---
# <a name="configure---corporate-connected-guide"></a>구성 - 회사 연결 가이드

## <a name="azure-users-and-groups"></a>Azure 사용자 및 그룹

해당 확장의 Azure 및 Intune은 사용자 및 그룹을 사용하여 구성 및 라이선스를 할당합니다. 이 배포 흐름의 유효성을 검사하고 가이드를 작성하고 운영할 수 있는지 확인하기 위해 사용자 계정이 필요할&#39;있습니다.

라이선스 할당을 위해 단일 사용자 그룹을 만들 수 있습니다.

사용자 그룹의 두 Azure AD 계정에 대한 액세스 권한이&#39;없는 경우 다음을 사용할 수 있습니다. 다음은 에 대한 빠른 시작 가이드입니다.

- [사용자를 만드는 방법](/mem/intune/fundamentals/quickstart-create-user)
- [그룹을 만드는 방법](/mem/intune/fundamentals/quickstart-create-group)
- [그룹에 사용자 추가](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자를 추가하여 그룹 만들기
- [사용자 그룹이 디바이스에 조인할 수 있도록 Azure AD 구성](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 새 사용자 그룹에 Azure AD에 디바이스를 등록할 수 있는 권한이 있는지 확인합니다.

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 자동 등록

원활하고 원활한 환경을 위해 HoloLens 2 디바이스에 대한 AADJ(Azure Active Directory 조인) 및 Intune에 자동 등록을 설정하는 것이 좋습니다. 이를 통해 사용자는 OOBE 중에 조직 로그인 자격 증명을 입력하고 Azure AD에 자동으로 등록하고 디바이스를 MDM에 등록할 수 있습니다.

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)사용하여 서비스를 선택하고 Premium 평가판 받기를 선택할 수 있을 때까지 몇 페이지를 탐색할 수 있습니다. 자동 등록 P1의 경우 1과 2가 Azure Active Directory Premium 있을 수 있습니다. Intune을 선택하고 자동 등록에 대한 사용자 범위를 선택하고 이전에 만든 그룹을 선택할 수 있습니다.

자세한 내용 및 단계는 [Intune에 자동 등록을 사용하도록 설정하는 방법에 대한 가이드를 참조하세요.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>회사 Wi-Fi 연결

회사 Wi-Fi 연결에는 일반적으로 HoloLens 2 사용하는 고객을 위한 인증서 기반 인증이 필요합니다. MDM 솔루션과 통합된 SCEP(단순 인증서 등록 프로토콜) 또는 PKCS(공개 키 암호화 표준) 인증서 인프라를 사용하여 이러한 인증서를 배포해야 합니다. Intune을 사용하여 Wi-Fi 프로필, 인증서 및 프록시 설정을 배포하면 최종 사용자에게 원활한 환경을 제공합니다.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>인증서 및 Wi-Fi 프로필 배포

Microsoft Endpoint Manager 통해 인증서 및 프로필을 배포하려면 다음 단계를 수행합니다.

1. 각 루트 및 중간 인증서에 대한 프로필을 [만듭니다(신뢰할 수 있는 인증서 프로필 만들기](/intune/protect/certificates-configure#create-trusted-certificate-profiles)참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함된 설명이 있어야 합니다.

    > [!CAUTION]
    > **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**

2. 각 SCEP 또는 PKCS 인증서에 대한 프로필을 만듭니다([SCEP 인증서 프로필 만들기 또는 PKCS 인증서 프로필 만들기](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함된 설명이 있어야 합니다.

    > [!CAUTION]
    > **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**

    > [!Note]
    > HoloLens 2 많은 사용자가 공유 디바이스(예: 디바이스당 여러 사용자)로 간주되기 때문에 가능한 경우 Wi-Fi 인증을 위해 사용자 인증서 대신 디바이스 인증서를 배포하는 것이 좋습니다.

3. 회사 Wi-Fi 네트워크에 대한 프로필을 만듭니다(Windows 10 [이상 디바이스에 대한 Wi-Fi 설정](/intune/wi-fi-settings-windows)참조). Wi-Fi 프로필 내에서 조직 내에서 프록시 설정을 사용하도록 선택할 수 있습니다.

    옵션은 다음과 같습니다.
    - **없음**: 프록시 설정을 구성하지 않습니다.
    - **수동으로 구성**: **프록시 서버 IP 주소** 및 해당 **포트 번호** 를 입력합니다.
    - **자동으로 구성**: PAC(프록시 자동 구성) 스크립트를 가리키는 URL을 입력합니다. 예를 들어 *http://proxy.contoso.com/proxy.pac* 을 입력합니다.

    PAC 파일에 대한 자세한 내용은 [PAC(프록시 자동 구성) 파일](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)(타사 사이트 열기)을 참조하세요.
 
    > [!Note]
    > 가능한 경우 사용자 그룹이 아니라 장치 그룹에 Wi-Fi 프로필을 할당하는 것이 좋습니다.
     
    > [!Tip]
    > 회사 네트워크의 Windows 10 PC에서 사용 중인 Wi-Fi 프로필을 내보낼 수도 있습니다. 이 내보내기를 수행하면 현재 모든 설정이 포함된 XML 파일이 생성됩니다. 그런 다음 이 파일을 Intune으로 가져와 HoloLens 2 장치에 대한 Wi-Fi 프로필로 사용합니다. [Windows 디바이스에 대한 Wi-Fi 설정 내보내기 및 가져오기](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)를 참조하세요.

1.  디바이스 프로필을 HoloLens 디바이스 그룹에 [할당합니다.](/mem/intune/configuration/device-profile-assign)

2.  Intune에서 디바이스 프로필을 [모니터링합니다.](/mem/intune/configuration/device-profile-monitor)

Wi-Fi 프로필에 문제가 있는 경우 [Intune에서 Wi-Fi 디바이스 구성 프로필 문제 해결을 참조하세요.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>회사 연결 시 외부 인터넷 액세스 문제 해결
서비스가 설정된 프록시를 통과하지 않으려면 방화벽을 통해 연결을 시도할 수 있습니다. 방화벽 규칙에 엔드포인트 세부 정보 목록을 추가하여 이러한 문제를 해결할 수 있습니다.

방화벽 포트에서 차단된 경우 HoloLens 몇 가지 공통 [엔드포인트를](/hololens/hololens-offline) 사용하도록 설정합니다.

Microsoft Dynamics CRM Online 연결에 필요한 가이드 특정 포트: [인터넷에 액세스할 수 있는 URL을](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)사용하도록 설정할 수도 있습니다.

## <a name="app-deployment"></a>앱 배포

MDM을 통해 LOB 앱을 배포하는 것은 쉽게 확장 가능하고 생성된 그룹에 등록할 때 디바이스에 자동으로 배포할 수 있는 방법입니다.

여전히 앱을 개발 중이거나 아직 앱이 없는 경우 MRTK 예제 허브의 샘플 앱을 사용할 수 있습니다. 이 샘플 앱은 사용할 준비가 되었으며 Unity 또는 Visual Studio 사용할 필요가 없습니다. [MRTK 예제 샘플 앱을 다운로드합니다.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

사용자 고유의 앱을 사용하거나 Mixed Reality 앱 개발에 관심이 있는 경우 [Mixed Reality 개발자 설명서를](/windows/mixed-reality/design/design)검토하세요.

> [!NOTE]
> HoloLens 디바이스의 시스템 요구 사항은 앱 빌드의 아키텍처를 기반으로 합니다. HoloLens 2 디바이스는 ARM 아키텍처를 사용합니다. Visual Studio 앱을 빌드할 때 디바이스에 대한 올바른 아키텍처를 선택했는지 확인하고 필요한 모든 의존성을 포함해야 합니다.

> [!IMPORTANT]
> LOB 앱을 배포할 때 인증서를 Intune에 업로드하고 앱을 사용하려는 동일한 그룹에 할당해야 합니다. 그렇지 않은 경우 제대로 설치되지 않습니다.

### <a name="upload-and-assign-the-app"></a>앱 업로드 및 할당

1. [MEM 관리 센터](https://endpoint.microsoft.com/#home)로 이동합니다.

2. **앱**  ->  **모든 앱** 선택하고 **+ 추가** 단추를 선택합니다.

3. 기타 아래에서 **사업장 앱 을** 선택합니다. **선택을** 클릭합니다.

4. 앱 패키지 파일( APPXBUNDLE 파일)을 선택하거나, 이 예제의 경우 앱은 _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_ 입니다.

5. 누락된 dependencies에 대한 알림이 받게 됩니다. 이 경우 _Microsoft.VCLibs.ARM.14.00.appx 를_ 업로드해야 합니다. **파일 선택에서 검색합니다.**

6. 확인을 선택합니다.

7. 다음 화면에서는 필수 필드가 자동으로 채워지게 됩니다. **새로 만들기** 를 선택합니다.

8. 필수에서 이전에 만든 그룹을 추가하여 이 앱을 그룹에 필수로 만듭니다. 이렇게 하면 앱이 그룹의 등록된 디바이스에 자동으로 다운로드됩니다. **새로 만들기** 를 선택합니다.

9. **만들기** 를 선택합니다.

자세한 내용: [Microsoft Intune 그룹에 앱 할당](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>설치 가이드: 애플리케이션 라이선스, 데이터 버스 및 제작

Dynamics 365 Guides 사용하려면 몇 가지 준비를 수행해야 합니다. 준비해야 하는 세 가지 영역이 있습니다. 사용자, 데이터버스 및 가이드 자체.

### <a name="users-and-application-licenses"></a>사용자 및 애플리케이션 라이선스

누군가가 가이드를 사용하려면 이전에 이 가이드에서 설정한 Azure AD 계정을 사용해야 합니다.

또한 만든 사용자에게 Dynamics 365 Guides 라이선스를 할당해야 합니다. [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home)에서 이 작업을 수행합니다. 또한 기본 Azure 계정에 라이선스를 할당합니다.

애플리케이션 라이선스 적용에 대한 단계별 지침은 [이 짧은 가이드에](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 따라 사진을 찍습니다.

### <a name="set-up-the-dataverse"></a>Dataverse 설정

[프로덕션 환경을 설정하려면](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 두 가지 필수 구성 요소에 부합해야 합니다. [**시스템 관리자**](/power-platform/admin/database-security) 역할이 있어야 **하며** Power Apps [**라이선스(또는 Power Apps 라이선스가**](/power-platform/admin/signup-question-and-answer) 포함된 [**Dynamics 365 Guides 라이선스)가**](/dynamics365/mixed-reality/guides/setup-step-one) 있어야 합니다. 이 가이드에 따라 Azure AD를 만든 경우 시스템 관리자에 대한 역할 요구 사항을 충족합니다. 이전 단계에서 가이드 라이선스도 할당했습니다.

이 가이드 내에서 [Microsoft Dataverse 환경을 만듭니다.](/dynamics365/mixed-reality/guides/setup-step-two)

1. [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com/environments) 사용하여 새 환경을 만드는 것부터 시작합니다.
2. **새 환경** 을 만들 때 **&#39;형식에** 대해 **프로덕션** 을 선택합니다.
3. 이 환경에 대한 데이터베이스 **만들기를 토글하는 것이 중요합니다.**  옵션을  **예** 로 선택합니다.
4. 데이터베이스  **추가**  대화 상자에서  **Dynamics 365 앱 사용**  옵션을  **예로 설정합니다.**

Dataverse에서 항목의 최대 파일 크기를 늘릴 수 있습니다. 최대 파일 크기를 늘리면 가이드에서 나중에 사용할 더 큰 3D 모델 또는 비디오 파일을 업로드할 수 있습니다. 짧은 가이드에 따라 [최대 업로드 파일 크기를 변경](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)합니다.

마지막으로 솔루션을 설치 하 [고 구성](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)해야 합니다. [전원 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/environments)에서 **리소스** \& gt;를 선택 합니다.  **Dynamics 365 앱** 의 목록에서 **Dynamics 365 Guides** 을 선택 하 고 **설치** 를 선택 합니다.  

앱을 사용 하려면 먼저 [가이드 보안 역할을 추가](/dynamics365/mixed-reality/guides/assign-role) 해야 합니다.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>제작을 통해 PC에서 테스트 가이드 만들기

가이드를 만들 때 항상 PC에서 시작 합니다. 단계 만들기, 모델 선택 및 가이드 고정 방법 그러면 나중에 HoloLens 장치의 제작 모드에서 가이드에 대 한 콘텐츠를 배치 합니다. 이 가이드의 목적에 따라 최소한의 단계와 모델을 사용 하 여 간단한 테스트 가이드를 작성 하는 것이 좋습니다.

가이드 작성에 대 한 학습을 시작 하려면 [제작 개요](/dynamics365/mixed-reality/guides/authoring-overview)를 참조 하세요. 또는 빠른 추적 개요를 보려면이 짧은 동영상을 시청 하세요.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>선택 사항: 키오스크 모드

키오스크 모드는 IT 관리자가 단일 앱 또는 앱 선택을 표시 하도록 시작 메뉴의 UI를 구성 하는 데 사용 되는 모드입니다. 키오스크는 특정 사용자, 그룹 또는 장치 수준에 적용 될 수도 있습니다. 때로는 키오스크에서 특정 사용자를 제외 하 고 일반 시작 메뉴에 대 한 액세스를 허용 하는 경우도 있습니다.

키오스크 모드에는 키오스크를 HoloLens에 배포 하는 방법 뿐만 아니라 설정할 수 있는 범위와 구성 모두 다른 여러 변수가 있습니다. 이러한 모든 변수 때문에 키오스크 모드는이 가이드에 대 한 _선택 사항_ 으로 유지 되며,이를 덮어쓰지 않습니다. 사용자가 사용할 수 있는 앱을 제한 해야 하거나 더 자세히 알고 싶은 경우, [HoloLens를 키오스크로 설정](/hololens/hololens-kiosk)하는 방법을 알아보세요.

## <a name="optional-wdac"></a>선택 사항: WDAC

WDAC를 사용 하면 IT 관리자가 장치의 앱 시작을 차단 하도록 장치를 구성할 수 있습니다. 이는 사용자가 장치에서 앱을 숨기는 UI를 사용 하 여 표시 되지만 여전히 시작할 수 있는 키오스크 모드와 같은 장치 제한 방법과는 다릅니다. WDAC가 구현 되는 동안 앱은 모든 앱 목록에 계속 표시 되지만, WDAC는 장치 사용자가 해당 앱 및 프로세스를 시작할 수 없게 됩니다.

자세한 내용은 [WDAC 및 Windows PowerShell를 사용 하 여 Microsoft Intune를 통해 HoloLens 2 장치에서 앱을 허용 하거나 차단](/mem/intune/configuration/custom-profile-hololens)합니다.

[Windows Defender 애플리케이션 제어 - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사에 연결 된 배포-배포](hololens2-corp-connected-deploy.md)