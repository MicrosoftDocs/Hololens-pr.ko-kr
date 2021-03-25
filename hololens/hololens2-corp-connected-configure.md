---
title: 배포 가이드 - Dynamics 365 가이드를 통해 회사에서 연결된 HoloLens 2 - 구성
description: Dynamics 365 가이드를 통해 회사 연결 네트워크를 통해 HoloLens 2 장치를 배포하기 위한 구성을 설정하는 방법을 알아보세요.
keywords: HoloLens, 관리, 회사 연결, Dynamics 365 가이드, AAD, Azure AD, MDM, 모바일 장치 관리
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448600"
---
# <a name="configure---corporate-connected-guide"></a>구성 - 회사 연결 가이드

## <a name="azure-users-and-groups"></a>Azure 사용자 및 그룹

Azure 및 해당 확장의 Intune은 사용자 및 그룹을 사용하여 구성 및 라이선스를 할당합니다. 이 배포 흐름의 유효성을 검사하고 가이드를 작성 및 운영할 수&#39;수 있도록 사용자 계정이 필요합니다.

라이선스를 할당하기 위한 단일 사용자 그룹을 만들 수 있습니다.

사용자 그룹에서&#39;Azure AD 계정에 대한 액세스 권한이 없는 경우 사용할 수 있습니다. 다음은 빠른 시작 가이드입니다.

- [사용자를 만드는 방법](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [그룹을 만드는 방법](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [그룹에 사용자 추가](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자 추가를 사용하여 그룹 만들기
- [사용자 그룹이](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 디바이스에 가입할 수 있도록 Azure AD 구성 - 새 사용자 그룹에 Azure AD에 장치를 등록할 수 있는 권한이 있는지 확인

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2에 자동 등록

원활하고 원활한 환경을 제공하기 위해 HoloLens 2 디바이스용 Azure Active Directory 가입(AADJ) 및 Intune에 자동 등록을 설정하는 것이 가장 좋은 방법입니다. 이렇게 하면 사용자가 OOBE 중에 조직 로그인 자격 증명을 입력하고 Azure AD에 자동으로 등록하고 디바이스를 MDM에 등록할 수 있습니다.

Microsoft [Endpoint Manager를](https://endpoint.microsoft.com/#home)사용하여 서비스를 선택하고 프리미엄 평가판 다운로드를 선택할 때까지 몇 페이지를 탐색할 수 있습니다. 자동 등록 P1의 경우 Azure Active Directory Premium 1과 2가 있을 수 있습니다. Intune을 선택하고 자동 등록에 대한 사용자 범위를 선택하고 이전에 만든 그룹을 선택할 수 있습니다.

자세한 내용 및 단계는 Intune에서 자동 등록을 사용하도록 설정하는 방법에 대한 [가이드를 읽어보세요.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>회사 Wi-Fi 연결

회사 Wi-Fi 연결에는 일반적으로 HoloLens 2를 사용하는 고객에게 인증서 기반 인증이 필요합니다. MDM 솔루션과 통합된 SCEP(Simple Certificate Enrollment Protocol) 또는 PKCS(공개 키 암호화 표준) 인증서 인프라를 사용하여 이러한 인증서를 배포해야 합니다. Intune을 사용하여 Wi-Fi, 인증서 및 프록시 설정을 배포하면 최종 사용자에게 원활한 환경이 구축됩니다.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>인증서 및 Wi-Fi 프로필 배포

Microsoft Endpoint Manager를 통해 인증서 및 프로필을 배포하려면 다음 단계를 수행합니다.

1. 각 루트 및 중간 인증서에 대한 프로필을 만들 수 있습니다(신뢰할 수 있는 인증서 프로필 [만들기 참조).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) 이러한 각 프로필에는 만료 날짜가 DD/MM/YYYY 형식으로 포함된 설명이 있어야 합니다. 

    > [!CAUTION]
    > **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**

2.  각 SCEP와 PKCS 인증서에 대한 프로필을 만듭니다. ([SCEP 인증서 프로필 만들기 또는 PKCS 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)를 참조하세요.) 각 프로필에는 YYYY/MM/DD 형식의 만료 날짜를 포함하는 설명이 있어야 합니다. 

    > [!CAUTION]
    > **만료 날짜 없이 인증서 프로필은 배포되지 않습니다.**

    > [!Note]
    > HoloLens 2는 많은 사용자가 공유 장치로 간주되는 경우(즉, 장치당 여러 사용자) 가능한 경우 Wi-Fi 인증을 위해 사용자 인증서 대신 장치 인증서를 배포하는 것이 좋습니다.

3.  회사 네트워크용 프로필을 [Wi-Fi(Windows 10](https://docs.microsoft.com/intune/wi-fi-settings-windows)이상 장치에 대한 Wi-Fi 설정 참조). 조직 Wi-Fi 내에서 프록시 설정을 사용 하게 선택할 수 있습니다.
 
    옵션:
    - **없음:** 프록시 설정이 구성되지 않습니다.
    - **수동으로 구성:** 프록시 **서버 IP 주소와** 포트 **번호를 입력합니다.**
    - **자동 구성:** PAC(프록시 자동 구성) 스크립트를 지정하는 URL을 입력합니다. 예를 들어 를 *http://proxy.contoso.com/proxy.pac* 입력합니다.

    PAC 파일에 대한 자세한 내용은 [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site)을 참조하십시오.
 
    > [!Note]
    > 가능한 경우 사용자 그룹이 아니라 장치 그룹에 대해 Wi-Fi 프로필을 할당하는 것이 좋습니다.
     
    > [!Tip]
    > 회사 네트워크의 Windows 10 PC에서 작업 중인 Wi-Fi 프로필을 내보낼 수도 있습니다. 이 내보내기에서 현재 모든 설정을 포함하는 XML 파일을 만듭니다. 그런 다음 해당 파일을 HoloLens 2 장치에 대한 Wi-Fi 프로필로 사용하여 Intune으로 가져옵니다. [Windows 장치에 대한 Wi-Fi 내보내기 및 가져오기 설정을 참조하세요.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

1.  [장치](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 프로필을 HoloLens 장치 그룹에 할당합니다.

2.  [](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Intune에서 장치 프로필을 모니터링합니다.

사용자 프로필에 문제가 Wi-Fi [Intune에서](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)장치 Wi-Fi 프로필 문제 해결을 참조하세요.

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp가 연결된 경우 외부 인터넷 액세스 문제 해결
서비스가 설정된 프록시를 통과하지 못하게 하려고 할 때 방화벽을 통해 연결을 시도할 수 있습니다. 방화벽 규칙에 끝점 관련 목록을 추가하여 이러한 문제를 해결할 수 있습니다.

방화벽 포트에서 차단된 경우 [HoloLens에](https://docs.microsoft.com/hololens/hololens-offline) 대한 몇 가지 일반적인 끝점을 사용하도록 설정합니다.

또한 에 연결하기 위해 필요한 인터넷 액세스 URL인 가이드 특정 포트를 사용하도록 설정할 [Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>앱 배포

MDM을 통해 LOB 앱을 배포하는 것은 쉽게 확장할 수 있으며 생성된 그룹에 등록할 때 장치에 자동으로 배포할 수 있는 방법입니다.

아직 앱을 개발 중이거나 아직 개발하지 않은 경우 MRTK 예제 허브의 샘플 앱을 사용할 수 있습니다. 이 샘플 앱은 사용할 수 있으며 Unity 또는 2013을 사용할 필요가 Visual Studio. [MRTK 예제 샘플 앱을 다운로드합니다.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

자체 앱을 사용하거나 혼합 현실용 앱 개발에 관심이 있는 경우 Mixed Reality 개발자 설명서를 자유롭게 [검토하세요.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> HoloLens 장치에 대한 시스템 요구 사항은 앱 빌드의 아키텍처를 기반으로 합니다. HoloLens 2 장치는 ARM 사용됩니다. 앱에서 앱을 Visual Studio 장치에 대한 올바른 아키텍처를 선택하고 필요한 종속성도 포함해야 합니다.

> [!IMPORTANT]
> LOB 앱을 배포할 때 Intune에 인증서를 업로드하고 앱을 사용하기 위한 동일한 그룹에 할당하거나 제대로 설치하지 않는 것이 중요합니다.

### <a name="upload-and-assign-the-app"></a>앱 업로드 및 할당

1. [MEM 관리 센터로 이동합니다.](https://endpoint.microsoft.com/#home)

2. 앱 **모든 앱을**  ->  **선택하고** + 추가 **단추를** 선택합니다.

3. 기타 아래에서 업무 앱 **을 선택합니다.** 선택을 **클릭합니다.**

4. 앱 패키지 파일(APPXBUNDLE 파일)을 선택하거나 이 예제의 경우 앱이 _MRTK 예제 Hub\_2.4.2.0\_arm\_Master.appxbundle입니다._

5. 종속성 누락에 대한 알림을 제공합니다. 이 경우 _Microsoft.VCLibs.ARM.14.00.appx를 업로드해야 합니다._ 파일 **선택에서 검색합니다.**

6. 확인을 선택합니다.

7. 다음 화면에서 필수 필드는 자동으로 채워집니다. **다음**을 선택합니다.

8. 필수 아래에서 이전에 만든 그룹을 추가하여 이 앱을 그룹에 요구합니다. 이렇게 하면 앱이 그룹에 등록된 장치에 자동으로 다운로드됩니다. **다음**을 선택합니다.

9. **만들기**를 선택합니다.

자세히 읽기: [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 그룹에 앱 할당

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>설치 가이드: 응용 프로그램 라이선스, 데이터버스 및 제작

Dynamics 365 가이드를 사용하려면 몇 가지 준비를 해야 합니다. 준비해야 할 세 가지 영역이 있습니다. 사용자, 데이터버스 및 가이드 자체.

### <a name="users-and-application-licenses"></a>사용자 및 응용 프로그램 라이선스

다른 사용자가 가이드를 사용하려면 이전에 이 가이드에서 설정한 Azure AD 계정을 사용해야 합니다.

또한 만든 사용자에게 Dynamics 365 가이드 라이선스를 할당해야 합니다. Microsoft [365](https://admin.microsoft.com/AdminPortal/Home)관리 센터에서 이 작업을 합니다. 또한 기본 Azure 계정에 라이선스를 할당합니다.

응용 [프로그램 라이선스 적용에](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 대한 단계별 지침은 그림과 함께 이 짧은 가이드를 따릅니다.

### <a name="set-up-the-dataverse"></a>Dataverse 설정

프로덕션 환경을 [설정하려면](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 두 가지 선행 요구 사항을 충족해야 합니다. 시스템 관리자 [****](https://docs.microsoft.com/power-platform/admin/database-security) 역할이 있어야 **합니다.** Power Apps 라이선스(또는 [**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) 라이선스가 포함된 [**Dynamics 365 가이드**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) 라이선스)가 있어야 합니다. 이 가이드를 따라 Azure AD를 만든 경우 시스템 관리자에 대한 역할 요구 사항을 충족합니다. 또한 이전 단계에서 가이드 라이선스를 할당했습니다.

이 가이드 내에서 [Microsoft Dataverse](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)환경을 만들 수 있습니다.

1. 먼저 Power [Platform](https://admin.powerplatform.microsoft.com/environments) 관리 센터를 사용하고 새 환경을 만들어야 합니다.
2. 새 환경 **을**만들 **** 때 새 환경 유형에&#39;프로덕션 을 **선택합니다.**
3. 이 환경에 대한 데이터베이스 만들기를 **전환해야 합니까?**  옵션을 **예로 선택합니다.**
4. 데이터베이스  **추가 대화**  상자에서  **Dynamics 365**  앱 사용 옵션을 예로  **설정합니다.**

데이터버스에 있는 항목의 최대 파일 크기를 늘리면 됩니다. 최대 파일 크기를 늘리면 나중에 가이드에서 사용할 더 큰 3D 모델 또는 비디오 파일을 업로드할 수 있습니다. 짧은 가이드에 따라 [최대 업로드 파일 크기를 변경합니다.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

마지막으로 솔루션을 설치하고 [구성해야 합니다.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Power [Platform 관리 센터에서](https://admin.powerplatform.microsoft.com/environments)리소스 ****   \ &gt; **Dynamics 365 앱을**선택하고 목록에서 **Dynamics 365 가이드를** 선택한 다음 설치를 **선택합니다.**  

앱을 [사용하려면 먼저 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) 보안 역할을 추가해야 합니다.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>제작을 통해 PC에 테스트 가이드 만들기

가이드를 만들 때 항상 PC에서 시작할 수 있습니다. 단계 만들기, 모델 선택 및 가이드 고정 방법 이 다음에는 나중에 HoloLens 디바이스의 제작 모드에서 가이드의 콘텐츠를 배치합니다. 이 가이드의 목적을 위해 최소한의 단계와 모델을 사용하며 짧은 테스트 가이드를 만드는 것이 권장됩니다.

가이드 제작에 대해 알아보고자 하는 경우 여기에서 제작 개요로 [시작하세요.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) 또는 빠른 트랙 개요를 얻거나 이 짧은 비디오를 시청하세요.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>선택 사항: 키오스크 모드

키오스크 모드는 IT 관리자가 시작 메뉴의 UI를 구성하여 단일 앱 또는 앱 선택을 표시하도록 구성하는 모드입니다. 키오스크는 특정 사용자, 그룹 또는 장치 수준에 적용할 수도 있습니다. 일부 경우에는 특정 사용자를 일반 시작 메뉴에 액세스할 수 있도록 허용하는 키오스크에서 제외합니다.

키오스크 모드에는 설정할 수 있는 범위 및 구성과 HoloLens에 키오스크를 배포하는 방법 등 다양한 변수가 있습니다. 이러한 변수가 모두 있기 때문에 키오스크 모드는 이 가이드의 선택 사항으로 남아 있으며 다시 재시도되지 않습니다. __ 비즈니스에서 사용 가능한 앱을 사용자에게 제한해야 하거나 자세한 내용을 알아보고자 하는 경우 [HoloLens를](https://docs.microsoft.com/hololens/hololens-kiosk)키오스크로 설정하는 방법을 자유롭게 배울 수 있습니다.

## <a name="optional-wdac"></a>선택 사항: WDAC

WDAC를 사용하면 IT 관리자가 디바이스에서 앱 실행을 차단하도록 장치를 구성할 수 있습니다. 이는 사용자가 디바이스에서 앱을 숨기는 UI를 제공하지만 계속 실행될 수 있는 키오스크 모드와 같은 장치 제한 방법과 다릅니다. WDAC를 구현하는 동안 앱은 여전히 모든 앱 목록에 표시되지만 WDAC는 해당 앱 및 프로세스가 장치 사용자가 시작하지 못하도록 합니다.

자세한 내용은 WDAC 및 Windows PowerShell 사용하여 [Microsoft Intune을 사용하여 HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)장치에서 앱을 허용하거나 차단을 참조하세요.

[Windows Defender 응용 프로그램 제어 - WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>다음 단계 
> [!div class="nextstepaction"]
> [회사 연결 배포 - 배포](hololens2-corp-connected-deploy.md)