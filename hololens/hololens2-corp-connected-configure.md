---
title: 배포 가이드-Dynamics 365 Guides를 사용 하 여 회사에 연결 된 HoloLens 2
description: Dynamics 365 Guides를 사용 하 여 회사에 연결 된 네트워크를 통해 HoloLens 2 장치를 배포 하도록 구성을 설정 하는 방법을 알아봅니다.
keywords: HoloLens, 관리, 회사에 연결 된 Dynamics 365 Guides, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033505"
---
# <a name="configure---corporate-connected-guide"></a>구성-회사에 연결 된 가이드

## <a name="azure-users-and-groups"></a>Azure 사용자 및 그룹

Azure 및 Intune은이 확장에 의해 사용자 및 그룹을 사용 하 여 구성과 라이선스를 할당 하는 데 도움을 줍니다. 이 배포 흐름의 유효성을 검사 하 고 가이드를 작성 하 고 운영할 수 있는 것을 확인할 수 있도록 사용자 계정이 필요&#39;있습니다.

사용자는 라이선스 할당을 위해 특별히 단일 사용자 그룹을 만들 수 있습니다.

사용자 그룹의 두 Azure AD 계정에 대 한 액세스 권한이 이미 있는&#39;없는 경우에는를 사용할 수 있습니다. 다음은에 대 한 빠른 시작 가이드입니다.

- [사용자를 만드는 방법](/mem/intune/fundamentals/quickstart-create-user)
- [그룹을 만드는 방법](/mem/intune/fundamentals/quickstart-create-group)
- [그룹에 사용자 추가](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자를 추가 하 여 그룹을 만듭니다.
- [사용자 그룹이 장치에 연결할 수 있도록 AZURE Ad 구성](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 새 사용자 그룹에 장치를 azure ad에 등록할 수 있는 권한이 있는지 확인 합니다.

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2에 대 한 자동 등록

원활한 원활한 환경을 제공 하기 위해 Azure Active Directory Join (AADJ) 및 HoloLens 2 장치에 대 한 Intune에 자동 등록을 설정 하는 방법이 있습니다. 이를 통해 사용자는 OOBE 중에 조직 로그인 자격 증명을 입력 하 고 Azure AD에 자동으로 등록 하 고 장치를 MDM에 등록할 수 있습니다.

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)를 사용 하 여 서비스를 선택 하 고 몇 페이지로 이동 하 여 Premium 평가판 받기를 선택할 수 있습니다. Azure Active Directory Premium 1 및 2-자동 등록에 대 한 P1이 충분 하다는 것을 알 수 있습니다. Intune을 선택 하 고 자동 등록에 대 한 사용자 범위를 선택 하 고 이전에 만든 그룹을 선택할 수 있습니다.

전체 세부 정보 및 단계는 [Intune에 대 한 자동 등록을 사용 하도록 설정 하는 방법](/mem/intune/enrollment/quickstart-setup-auto-enrollment)에 대 한 가이드를 참조 하세요.

## <a name="corporate-wi-fi-connectivity"></a>회사 Wi-Fi 연결

회사 Wi-Fi 연결은 일반적으로 HoloLens 2를 사용 하는 고객에 게 인증서 기반 인증을 요구 합니다. MDM 솔루션과 통합 된 SCEP (단순 인증서 등록 프로토콜) 또는 PKCS (공개 키 암호화 표준) 인증서 인프라를 사용 하 여 이러한 인증서를 배포 해야 합니다. Intune을 사용 하 여 Wi-Fi 프로필, 인증서 및 프록시 설정을 배포 하면 최종 사용자에 게 원활한 환경을 만들 수 있습니다.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>인증서 및 Wi-Fi 프로필 배포

Microsoft Endpoint Manager를 통해 인증서 및 프로필을 배포 하려면 다음 단계를 수행 합니다.

1. 각 루트 및 중간 인증서에 대 한 프로필을 만듭니다 ( [신뢰할 수 있는 인증서 프로필 만들기](/intune/protect/certificates-configure#create-trusted-certificate-profiles)참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함 된 설명이 있어야 합니다.

    > [!CAUTION]
    > **만료 날짜가 없는 인증서 프로필은 배포 되지** 않습니다.

2. 각 SCEP 또는 PKCS 인증서에 대한 프로필을 만듭니다([SCEP 인증서 프로필 만들기 또는 PKCS 인증서 프로필 만들기](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함된 설명이 있어야 합니다.

    > [!CAUTION]
    > **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**

    > [!Note]
    > 여러 사용자가 장치 당 여러 사용자를 공유 하는 것으로 간주 되기 때문에 가능 하면 Wi-Fi 인증을 위해 사용자 인증서 대신 장치 인증서를 배포 하는 것이 좋습니다. HoloLens 2

3. 회사 Wi-Fi 네트워크에 대 한 프로필을 만듭니다 ( [Windows 10 이상 장치의 경우 wi-fi 설정](/intune/wi-fi-settings-windows)참조). Wi-Fi 프로필 내에서 조직 내의 프록시 설정을 사용 하도록 선택할 수 있습니다.

    옵션은 다음과 같습니다.
    - **없음**: 프록시 설정을 구성하지 않습니다.
    - **수동으로 구성**: **프록시 서버 IP 주소** 및 해당 **포트 번호** 를 입력합니다.
    - **자동으로 구성**: PAC(프록시 자동 구성) 스크립트를 가리키는 URL을 입력합니다. 예를 들어 *http://proxy.contoso.com/proxy.pac* 을 입력합니다.

    PAC 파일에 대한 자세한 내용은 [PAC(프록시 자동 구성) 파일](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)(타사 사이트 열기)을 참조하세요.
 
    > [!Note]
    > 가능한 경우 사용자 그룹이 아니라 장치 그룹에 Wi-Fi 프로필을 할당하는 것이 좋습니다.
     
    > [!Tip]
    > 회사 네트워크의 Windows 10 PC에서 사용 중인 Wi-Fi 프로필을 내보낼 수도 있습니다. 이 내보내기를 수행하면 현재 모든 설정이 포함된 XML 파일이 생성됩니다. 그런 다음 이 파일을 Intune으로 가져와 HoloLens 2 장치에 대한 Wi-Fi 프로필로 사용합니다. [Windows 디바이스에 대한 Wi-Fi 설정 내보내기 및 가져오기](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)를 참조하세요.

1.  장치 프로필을 HoloLens 장치 그룹에 [할당](/mem/intune/configuration/device-profile-assign) 합니다.

2.  Intune에서 장치 프로필을 [모니터링](/mem/intune/configuration/device-profile-monitor) 합니다.

Wi-Fi 프로필에 문제가 있는 경우 [Intune에서 장치 구성 프로필 Wi-Fi 문제 해결](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)을 참조 하세요.

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp가 연결 된 경우 외부 인터넷 액세스 문제 해결
서비스가 설정 된 프록시를 통과 하지 못하는 경우 방화벽을 통해 연결을 시도할 수 있습니다. 이러한 문제를 해결 하기 위해 방화벽 규칙에 끝점의 특정 목록을 추가할 수 있습니다.

방화벽 포트에서 차단 하는 경우 HoloLens에 대해 몇 가지 일반적인 [끝점](/hololens/hololens-offline) 을 사용 하도록 설정 합니다.

특정 포트를 사용 하도록 설정할 수도 있습니다. [Microsoft Dynamics CRM Online 연결 하는 데 필요한 인터넷 액세스 가능 url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)입니다.

## <a name="app-deployment"></a>앱 배포

MDM을 통해 LOB 앱을 배포 하는 것은 쉽게 확장할 수 있으며, 생성 된 그룹에 등록 시 장치에 자동으로 배포 될 수 있는 방법입니다.

아직 앱을 개발 하 고 있거나 아직 없는 경우 MRTK 예제 허브의 샘플 앱을 사용할 수 있습니다. 이 샘플 앱은 사용할 준비가 되었으며 Unity 또는 Visual Studio을 사용 하지 않아도 됩니다. [MRTK 예제 샘플 앱을 다운로드](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)합니다.

사용자 고유의 앱을 사용 하거나 혼합 현실 용 앱 개발에 관심이 있는 경우 [혼합 현실 개발자 설명서](/windows/mixed-reality/design/design)를 자유롭게 검토해 보세요.

> [!NOTE]
> HoloLens 디바이스의 시스템 요구 사항은 앱 빌드의 아키텍처를 기반으로 합니다. HoloLens 2 장치는 ARM 아키텍처를 사용 합니다. Visual Studio에서 앱을 빌드하는 경우 장치에 대 한 올바른 아키텍처를 선택 하 고 필요한 종속성을 포함 하는지 확인 합니다.

> [!IMPORTANT]
> LOB 앱을 배포 하는 경우 Intune에 인증서를 업로드 하 고 앱을 사용 하기 위한 동일한 그룹에 할당 하는 것이 중요 합니다. 그렇지 않으면 제대로 설치 되지 않습니다.

### <a name="upload-and-assign-the-app"></a>앱 업로드 및 할당

1. [메모리 관리 센터로](https://endpoint.microsoft.com/#home)이동 합니다.

2. **앱**  ->  **모든 앱** 을 선택 하 고 **+ 추가** 단추를 선택 합니다.

3. 기타 아래에서 lob ( **기간 업무) 앱** 을 선택 합니다. **선택** 을 클릭 합니다.

4. 앱 패키지 파일을 선택 합니다 .이 파일은 사용자의 .APPXBUNDLE 파일이 며,이 예제에서 앱은 _Mrtk 예제 허브 \_ 2.4.2.0 \_ arm \_ 마스터 .appxbundle_ 입니다.

5. 누락 된 종속성에 대 한 알림이 표시 됩니다. 이 경우에는 _v14.00_ 를 업로드 해야 하 고, **파일 선택** 에서이를 검색 합니다.

6. 확인을 선택합니다.

7. 다음 화면에서 필수 필드는 자동으로 채워집니다. **다음** 을 선택합니다.

8. 필요한 경우 이전에 만든 그룹을 추가 하 여이 앱을 그룹에 필요한 것으로 만듭니다. 이렇게 하면 앱이 그룹의 등록 된 장치에 자동으로 다운로드 됩니다. **다음** 을 선택합니다.

9. **만들기** 를 선택합니다.

자세한 내용은 [Microsoft Intune의 그룹에 앱 할당](/mem/intune/apps/apps-deploy#assign-an-app) 을 참조 하세요.

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>설정 가이드: 응용 프로그램 라이선스, dataverse 및 제작

Dynamics 365 Guides를 사용 하려면 몇 가지 준비 작업을 수행 해야 합니다. 준비 해야 하는 세 가지 영역이 있습니다. 사용자, dataverse 및 가이드 자체.

### <a name="users-and-application-licenses"></a>사용자 및 응용 프로그램 라이선스

사용자가 가이드를 사용 하려면 이전에이 가이드에서 설정한 Azure AD 계정을 사용 해야 합니다.

또한 사용자가 만든 사용자에 게 Dynamics 365 Guides 라이선스를 할당 해야 합니다. [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home)에서이 작업을 수행 합니다. 또한 기본 Azure 계정에 라이선스를 할당 합니다.

응용 프로그램 라이선스를 적용 하는 방법에 대 한 단계별 지침은 [이 짧은 가이드](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 를 참조 하세요.

### <a name="set-up-the-dataverse"></a>Dataverse 설정

[프로덕션 환경을 설정](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 하려면 두 가지 필수 조건을 충족 해야 합니다. [**시스템 관리자**](/power-platform/admin/database-security) 역할이 있어야 하 **고** [**Power Apps 라이선스**](/power-platform/admin/signup-question-and-answer) (또는 Power Apps 라이선스를 포함 하는 [**Dynamics 365 Guides 라이선스**](/dynamics365/mixed-reality/guides/setup-step-one) )가 있어야 합니다. 이 가이드를 따라 Azure AD를 만든 경우 시스템 관리자에 대 한 역할 요구 사항을 충족 해야 합니다. 또한 이전 단계에서 가이드 라이선스를 할당 했습니다.

이 가이드에서 [Microsoft Dataverse 환경을 만드는](/dynamics365/mixed-reality/guides/setup-step-two)방법을 설명 합니다.

1. 먼저 [전원 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/environments) 를 사용 하 여 새 환경을 만듭니다.
2. **새 환경을** 만들 때 **형식** 에 대해 **프로덕션** 을 선택할&#39;있습니다.
3. **이 환경에 대 한 데이터베이스 만들기를** 설정/해제 하는 것이 중요 한가요?  **예** 를 선택 합니다.
4. **데이터베이스 추가** 대화 상자에서 **Dynamics 365 앱 사용** 옵션을 예로 설정 **합니다.**

dataverse에서 항목의 최대 파일 크기를 늘릴 수 있습니다. 최대 파일 크기를 늘리면 나중에 가이드에서 사용할 더 큰 3D 모델 또는 비디오 파일을 업로드할 수 있습니다. 짧은 가이드에 따라 [최대 업로드 파일 크기를 변경합니다.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

마지막으로 [솔루션을 설치하고 구성해야](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)합니다. [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com/environments)에서 리소스 gt; **를 선택합니다.** \&  **Dynamics 365 앱** 목록에서 **Dynamics 365 Guides** 선택한 다음, **설치를** 선택합니다.  

앱을 사용하려면 [가이드 보안 역할을 추가해야](/dynamics365/mixed-reality/guides/assign-role) 합니다.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>제작을 통해 PC에서 테스트 가이드 만들기

가이드를 만들 때 항상 PC에서 시작합니다. 단계 만들기, 모델 선택 및 가이드를 고정하는 방법 나중에 HoloLens 디바이스의 제작 모드에서 가이드의 콘텐츠를 배치합니다. 이 가이드에서는 최소한의 단계와 모델로 짧은 테스트 가이드를 만드는 것이 좋습니다.

가이드 작성에 대한 학습을 시작하려면 여기에서 [작성 개요를](/dynamics365/mixed-reality/guides/authoring-overview)참조하세요. 또는 빠른 트랙 개요를 보려면 이 짧은 비디오를 시청하세요.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>선택 사항: 키오스크 모드

키오스크 모드는 IT 관리자가 단일 앱 또는 앱 선택을 표시하도록 시작 메뉴의 UI를 구성할 수 있는 모드입니다. 키오스크는 특정 사용자, 그룹 또는 디바이스 수준에서 적용할 수도 있습니다. 경우에 따라 키오스크에서 특정 사용자를 제외하여 일반 시작 메뉴에 계속 액세스할 수 있습니다.

키오스크 모드에는 키오스크를 HoloLens 배포하는 방법뿐만 아니라 설정할 수 있는 범위와 구성 모두에서 다양한 변수가 있습니다. 이러한 모든 변수로 인해 키오스크 모드는 이 가이드의 _선택 사항으로_ 남아 있으며 다시 방문하지 않습니다. 비즈니스에서 사용 가능한 앱을 사용자로 제한해야 하거나 자세히 알아보려면 [키오스크로 HoloLens 설정하는](/hololens/hololens-kiosk)방법을 자유롭게 알아보세요.

## <a name="optional-wdac"></a>선택 사항: WDAC

WDAC를 사용하면 IT 관리자가 디바이스에서 앱의 출시를 차단하도록 디바이스를 구성할 수 있습니다. 이는 키오스크 모드와 같이 디바이스에서 앱을 숨기는 UI가 사용자에게 표시되지만 여전히 시작될 수 있는 디바이스 제한 방법과 다릅니다. WDAC가 구현되는 동안 앱은 여전히 모든 앱 목록에 표시되지만 WDAC는 해당 앱 및 프로세스를 디바이스 사용자가 실행할 수 없도록 합니다.

자세한 내용은 [WDAC 및 Windows PowerShell 사용하여 Microsoft Intune](/mem/intune/configuration/custom-profile-hololens)HoloLens 2 디바이스에서 앱 허용 또는 차단을 참조하세요.

[Windows Defender 애플리케이션 제어 - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 배포](hololens2-corp-connected-deploy.md)