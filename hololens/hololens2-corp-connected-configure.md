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
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637084"
---
# <a name="configure---corporate-connected-guide"></a><span data-ttu-id="d880f-104">구성-회사에 연결 된 가이드</span><span class="sxs-lookup"><span data-stu-id="d880f-104">Configure - Corporate Connected Guide</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="d880f-105">Azure 사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="d880f-105">Azure Users and Groups</span></span>

<span data-ttu-id="d880f-106">Azure 및 Intune은이 확장에 의해 사용자 및 그룹을 사용 하 여 구성과 라이선스를 할당 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-106">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="d880f-107">이 배포 흐름의 유효성을 검사 하 고 가이드를 작성 하 고 운영할 수 있는 것을 확인할 수 있도록 사용자 계정이 필요&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-107">For the sake of validating this deployment flow and being able to check that you can author and operate a guide, you&#39;ll need a user account.</span></span>

<span data-ttu-id="d880f-108">사용자는 라이선스 할당을 위해 특별히 단일 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-108">We can make a single user group specifically for assigning licenses.</span></span>

<span data-ttu-id="d880f-109">사용자 그룹의 두 Azure AD 계정에 대 한 액세스 권한이 이미 있는&#39;없는 경우에는를 사용할 수 있습니다. 다음은에 대 한 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-109">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="d880f-110">사용자를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="d880f-110">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="d880f-111">그룹을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="d880f-111">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="d880f-112">[그룹에 사용자 추가](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 만든 사용자를 추가 하 여 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-112">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="d880f-113">[사용자 그룹이 장치에 연결할 수 있도록 AZURE Ad 구성](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 새 사용자 그룹에 장치를 azure ad에 등록할 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-113">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="d880f-114">HoloLens 2에 대 한 자동 등록</span><span class="sxs-lookup"><span data-stu-id="d880f-114">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="d880f-115">원활한 원활한 환경을 제공 하기 위해 Azure Active Directory Join (AADJ) 및 HoloLens 2 장치에 대 한 Intune에 자동 등록을 설정 하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-115">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="d880f-116">이를 통해 사용자는 OOBE 중에 조직 로그인 자격 증명을 입력 하 고 Azure AD에 자동으로 등록 하 고 장치를 MDM에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-116">This allows users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="d880f-117">[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)를 사용 하 여 서비스를 선택 하 고 몇 페이지로 이동 하 여 Premium 평가판 받기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-117">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="d880f-118">Azure Active Directory Premium 1 및 2-자동 등록에 대 한 P1이 충분 하다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-118">You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="d880f-119">Intune을 선택 하 고 자동 등록에 대 한 사용자 범위를 선택 하 고 이전에 만든 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-119">We can select Intune and select the user scope for automatic enrollment and select the group that was previously created.</span></span>

<span data-ttu-id="d880f-120">전체 세부 정보 및 단계는 [Intune에 대 한 자동 등록을 사용 하도록 설정 하는 방법](/mem/intune/enrollment/quickstart-setup-auto-enrollment)에 대 한 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-120">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="corporate-wi-fi-connectivity"></a><span data-ttu-id="d880f-121">회사 Wi-Fi 연결</span><span class="sxs-lookup"><span data-stu-id="d880f-121">Corporate Wi-Fi Connectivity</span></span>

<span data-ttu-id="d880f-122">회사 Wi-Fi 연결은 일반적으로 HoloLens 2를 사용 하는 고객에 게 인증서 기반 인증을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-122">Corporate Wi-Fi connections will commonly require certificate-based authentication for customers using HoloLens 2.</span></span> <span data-ttu-id="d880f-123">MDM 솔루션과 통합 된 SCEP (단순 인증서 등록 프로토콜) 또는 PKCS (공개 키 암호화 표준) 인증서 인프라를 사용 하 여 이러한 인증서를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-123">You will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> <span data-ttu-id="d880f-124">Intune을 사용 하 여 Wi-Fi 프로필, 인증서 및 프록시 설정을 배포 하면 최종 사용자에 게 원활한 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-124">Using Intune to deploy Wi-Fi profiles, certificates, and proxy settings creates a seamless experience for end users.</span></span>
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a><span data-ttu-id="d880f-125">인증서 및 Wi-Fi 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="d880f-125">Deploy certificates and Wi-Fi profiles</span></span>

<span data-ttu-id="d880f-126">Microsoft Endpoint Manager를 통해 인증서 및 프로필을 배포 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-126">To deploy certificates and profiles through Microsoft Endpoint Manager, follow these steps:</span></span>

1. <span data-ttu-id="d880f-127">각 루트 및 중간 인증서에 대 한 프로필을 만듭니다 ( [신뢰할 수 있는 인증서 프로필 만들기](/intune/protect/certificates-configure#create-trusted-certificate-profiles)참조).</span><span class="sxs-lookup"><span data-stu-id="d880f-127">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#create-trusted-certificate-profiles)).</span></span> <span data-ttu-id="d880f-128">이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함 된 설명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-128">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="d880f-129">**만료 날짜가 없는 인증서 프로필은 배포 되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-129">**Certificate profiles without an expiration date will not be deployed**.</span></span>

2. <span data-ttu-id="d880f-130">각 SCEP 또는 PKCS 인증서에 대 한 프로필 만들기 ( [scep 인증서 프로필 만들기 또는 pkcs 인증서 프로필 만들기](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)참조) 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함 된 설명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-130">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="d880f-131">**만료 날짜가 없는 인증서 프로필은 배포 되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="d880f-131">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!Note]
    > <span data-ttu-id="d880f-132">여러 사용자가 장치 당 여러 사용자를 공유 하는 것으로 간주 되기 때문에 가능 하면 Wi-Fi 인증을 위해 사용자 인증서 대신 장치 인증서를 배포 하는 것이 좋습니다. HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d880f-132">As the HoloLens 2 is considered for many to be a shared device, i.e., multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible.</span></span>

3. <span data-ttu-id="d880f-133">회사 Wi-Fi 네트워크에 대 한 프로필을 만듭니다 ( [Windows 10 이상 장치의 경우 wi-fi 설정](/intune/wi-fi-settings-windows)참조).</span><span class="sxs-lookup"><span data-stu-id="d880f-133">Create a profile for your corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span> <span data-ttu-id="d880f-134">Wi-Fi 프로필 내에서 조직 내의 프록시 설정을 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-134">Within your Wi-Fi profile, you can select to use the proxy settings within your organization.</span></span>

    <span data-ttu-id="d880f-135">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-135">Your options:</span></span>
    - <span data-ttu-id="d880f-136">**없음**: 프록시 설정을 구성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-136">**None**: No proxy settings are configured.</span></span>
    - <span data-ttu-id="d880f-137">**수동으로 구성**: **프록시 서버 IP 주소** 및 해당 **포트 번호** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-137">**Manually configure**: Enter the **Proxy server IP address** and its **Port number**.</span></span>
    - <span data-ttu-id="d880f-138">**자동으로 구성**: PAC(프록시 자동 구성) 스크립트를 가리키는 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-138">**Automatically configure**: Enter the URL pointing to a proxy auto configuration (PAC) script.</span></span> <span data-ttu-id="d880f-139">예를 들어 *http://proxy.contoso.com/proxy.pac* 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-139">For example, enter *http://proxy.contoso.com/proxy.pac*.</span></span>

    <span data-ttu-id="d880f-140">PAC 파일에 대한 자세한 내용은 [PAC(프록시 자동 구성) 파일](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)(타사 사이트 열기)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-140">For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).</span></span>
 
    > [!Note]
    > <span data-ttu-id="d880f-141">가능 하면 사용자 그룹이 아닌 장치 그룹에 Wi-Fi 프로필을 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-141">It is recommended that the Wi-Fi profile be assigned to Device groups rather than User groups where possible.</span></span>
     
    > [!Tip]
    > <span data-ttu-id="d880f-142">회사 네트워크의 Windows 10 PC에서 작업 중인 Wi-Fi 프로필을 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-142">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="d880f-143">이 내보내기는 모든 현재 설정을 포함 하는 XML 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-143">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="d880f-144">그런 다음이 파일을 Intune으로 가져와 HoloLens 2 장치에 대 한 Wi-Fi 프로필로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-144">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="d880f-145">[Windows 디바이스에 대한 Wi-Fi 설정 내보내기 및 가져오기](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-145">See [Export and import Wi-Fi settings for Windows devices](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).</span></span>

1.  <span data-ttu-id="d880f-146">장치 프로필을 HoloLens 장치 그룹에 [할당](/mem/intune/configuration/device-profile-assign) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-146">[Assign](/mem/intune/configuration/device-profile-assign) the device profiles to the HoloLens device group.</span></span>

2.  <span data-ttu-id="d880f-147">Intune에서 장치 프로필을 [모니터링](/mem/intune/configuration/device-profile-monitor) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-147">[Monitor](/mem/intune/configuration/device-profile-monitor) the device profiles in Intune.</span></span>

<span data-ttu-id="d880f-148">Wi-Fi 프로필에 문제가 있는 경우 [Intune에서 장치 구성 프로필 Wi-Fi 문제 해결](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-148">If there are issues with Wi-Fi profiles, reference [Troubleshoot Wi-Fi device configuration profiles in Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).</span></span>

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a><span data-ttu-id="d880f-149">Corp가 연결 된 경우 외부 인터넷 액세스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d880f-149">Troubleshooting External Internet Access When Corp Connected</span></span>
<span data-ttu-id="d880f-150">서비스가 설정 된 프록시를 통과 하지 못하는 경우 방화벽을 통해 연결을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-150">When services try to not go through a set Proxy, they may attempt to connect through the firewall.</span></span> <span data-ttu-id="d880f-151">이러한 문제를 해결 하기 위해 방화벽 규칙에 끝점의 특정 목록을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-151">You can add a list of endpoint specifics to your firewall rules to troubleshoot these issues.</span></span>

<span data-ttu-id="d880f-152">방화벽 포트에서 차단 하는 경우 HoloLens에 대해 몇 가지 일반적인 [끝점](/hololens/hololens-offline) 을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-152">If you're blocked at firewall ports, enable some common [endpoints](/hololens/hololens-offline) for HoloLens.</span></span>

<span data-ttu-id="d880f-153">특정 포트를 사용 하도록 설정할 수도 있습니다. [Microsoft Dynamics CRM Online 연결 하는 데 필요한 인터넷 액세스 가능 url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)입니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-153">You can also enable the Guides specific ports: [Internet accessible URLs required for connectivity to Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).</span></span>

## <a name="app-deployment"></a><span data-ttu-id="d880f-154">앱 배포</span><span class="sxs-lookup"><span data-stu-id="d880f-154">App Deployment</span></span>

<span data-ttu-id="d880f-155">MDM을 통해 LOB 앱을 배포 하는 것은 쉽게 확장할 수 있으며, 생성 된 그룹에 등록 시 장치에 자동으로 배포 될 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-155">Deploying a LOB app via MDM is a method that's easily scalable and can be automatically deployed to your devices upon enrollment in a created group.</span></span>

<span data-ttu-id="d880f-156">아직 앱을 개발 하 고 있거나 아직 없는 경우 MRTK 예제 허브의 샘플 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-156">If you are still developing your Apps or don't have one yet, you can use a sample app of the MRTK examples hub.</span></span> <span data-ttu-id="d880f-157">이 샘플 앱은 사용할 준비가 되었으며 Unity 또는 Visual Studio을 사용 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-157">This sample app is ready to use, and won't require the use of either Unity or Visual Studio.</span></span> <span data-ttu-id="d880f-158">[MRTK 예제 샘플 앱을 다운로드](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-158">[Download the MRTK Examples Sample app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).</span></span>

<span data-ttu-id="d880f-159">사용자 고유의 앱을 사용 하거나 혼합 현실 용 앱 개발에 관심이 있는 경우 [혼합 현실 개발자 설명서](/windows/mixed-reality/design/design)를 자유롭게 검토해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-159">If you would prefer to use your own app or are interested in app development for Mixed Reality, then feel free to review our [Mixed Reality developer documentation](/windows/mixed-reality/design/design).</span></span>

> [!NOTE]
> <span data-ttu-id="d880f-160">HoloLens 장치에 대 한 시스템 요구 사항은 앱 빌드의 아키텍처를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-160">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="d880f-161">HoloLens 2 장치는 ARM 아키텍처를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-161">HoloLens 2 devices use ARM architecture.</span></span> <span data-ttu-id="d880f-162">Visual Studio에서 앱을 빌드하는 경우 장치에 대 한 올바른 아키텍처를 선택 하 고 필요한 종속성을 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-162">When building your apps in Visual Studio, ensure that you have selected the correct architecture for the device and include any needed dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d880f-163">LOB 앱을 배포 하는 경우 Intune에 인증서를 업로드 하 고 앱을 사용 하기 위한 동일한 그룹에 할당 하는 것이 중요 합니다. 그렇지 않으면 제대로 설치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-163">When deploying LOB apps, it's important to also upload the certificate to Intune, and assign it to the same group that is intended to use the app or it will not install properly.</span></span>

### <a name="upload-and-assign-the-app"></a><span data-ttu-id="d880f-164">앱 업로드 및 할당</span><span class="sxs-lookup"><span data-stu-id="d880f-164">Upload and Assign the App</span></span>

1. <span data-ttu-id="d880f-165">[메모리 관리 센터로](https://endpoint.microsoft.com/#home)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-165">Navigate to the [MEM admin center](https://endpoint.microsoft.com/#home).</span></span>

2. <span data-ttu-id="d880f-166">**앱**  ->  **모든 앱** 을 선택 하 고 **+ 추가** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-166">Select **Apps** -> **All apps** and select the **+ Add** button.</span></span>

3. <span data-ttu-id="d880f-167">기타 아래에서 lob ( **기간 업무) 앱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-167">Underneath Other, Select **Line-of-business app**.</span></span> <span data-ttu-id="d880f-168">**선택** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-168">Click **select**.</span></span>

4. <span data-ttu-id="d880f-169">앱 패키지 파일을 선택 합니다 .이 파일은 사용자의 .APPXBUNDLE 파일이 며,이 예제에서 앱은 _Mrtk 예제 허브 \_ 2.4.2.0 \_ arm \_ 마스터 .appxbundle_ 입니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-169">Select the app package file, this is your APPXBUNDLE file, or in our case of this example the app is _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.</span></span>

5. <span data-ttu-id="d880f-170">누락 된 종속성에 대 한 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-170">You will be notified of missing dependencies.</span></span> <span data-ttu-id="d880f-171">이 경우에는 _v14.00_ 를 업로드 해야 하 고,</span><span class="sxs-lookup"><span data-stu-id="d880f-171">In this case, we need to upload _Microsoft.VCLibs.ARM.14.00.appx_.</span></span> <span data-ttu-id="d880f-172">**파일 선택** 에서이를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-172">Search for it under **Select a file**.</span></span>

6. <span data-ttu-id="d880f-173">확인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-173">Select OK.</span></span>

7. <span data-ttu-id="d880f-174">다음 화면에서 필수 필드는 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-174">In the next screen, the required fields will be auto-filled.</span></span> <span data-ttu-id="d880f-175">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-175">Select **Next**.</span></span>

8. <span data-ttu-id="d880f-176">필요한 경우 이전에 만든 그룹을 추가 하 여이 앱을 그룹에 필요한 것으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-176">Under Required, add our previously created group to make this app required for the group.</span></span> <span data-ttu-id="d880f-177">이렇게 하면 앱이 그룹의 등록 된 장치에 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-177">This will cause the app to automatically download to enrolled devices in the group.</span></span> <span data-ttu-id="d880f-178">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-178">Select **Next**.</span></span>

9. <span data-ttu-id="d880f-179">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-179">Select **Create**.</span></span>

<span data-ttu-id="d880f-180">자세한 내용은 [Microsoft Intune의 그룹에 앱 할당](/mem/intune/apps/apps-deploy#assign-an-app) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-180">Read more: [Assign apps to groups in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)</span></span>

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a><span data-ttu-id="d880f-181">설정 가이드: 응용 프로그램 라이선스, dataverse 및 제작</span><span class="sxs-lookup"><span data-stu-id="d880f-181">Setup Guides: Application licenses, dataverse, and authoring</span></span>

<span data-ttu-id="d880f-182">Dynamics 365 Guides를 사용 하려면 몇 가지 준비 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-182">In order to use Dynamics 365 Guides, you'll need to do some preparation.</span></span> <span data-ttu-id="d880f-183">준비 해야 하는 세 가지 영역이 있습니다. 사용자, dataverse 및 가이드 자체.</span><span class="sxs-lookup"><span data-stu-id="d880f-183">There are three areas in which we'll need to prepare; users, dataverse, and the guides themselves.</span></span>

### <a name="users-and-application-licenses"></a><span data-ttu-id="d880f-184">사용자 및 응용 프로그램 라이선스</span><span class="sxs-lookup"><span data-stu-id="d880f-184">Users and application licenses</span></span>

<span data-ttu-id="d880f-185">사용자가 가이드를 사용 하려면 이전에이 가이드에서 설정한 Azure AD 계정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-185">For someone to use Guides, they'll need to use an Azure AD account, which we have set up in this guide previously.</span></span>

<span data-ttu-id="d880f-186">또한 사용자가 만든 사용자에 게 Dynamics 365 Guides 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-186">You'll also need to assign Dynamics 365 Guides license to the user you've created.</span></span> <span data-ttu-id="d880f-187">[Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home)에서이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-187">You'll do this from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/Home).</span></span> <span data-ttu-id="d880f-188">또한 기본 Azure 계정에 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-188">Also assign the license to your primary Azure Account.</span></span>

<span data-ttu-id="d880f-189">응용 프로그램 라이선스를 적용 하는 방법에 대 한 단계별 지침은 [이 짧은 가이드](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-189">Follow [this short guide](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) with pictures for step-by-step instructions on applying application licenses.</span></span>

### <a name="set-up-the-dataverse"></a><span data-ttu-id="d880f-190">Dataverse 설정</span><span class="sxs-lookup"><span data-stu-id="d880f-190">Set up the Dataverse</span></span>

<span data-ttu-id="d880f-191">[프로덕션 환경을 설정](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 하려면 두 가지 필수 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-191">In order to [set up a production environment](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) you will need to meet two prerequisites.</span></span> <span data-ttu-id="d880f-192">[**시스템 관리자**](/power-platform/admin/database-security) 역할이 있어야 하 **고** [**Power Apps 라이선스**](/power-platform/admin/signup-question-and-answer) (또는 Power Apps 라이선스를 포함 하는 [**Dynamics 365 Guides 라이선스**](/dynamics365/mixed-reality/guides/setup-step-one) )가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-192">You must have the [**System Administrator**](/power-platform/admin/database-security) role,  **and**  you must have a [**Power Apps license**](/power-platform/admin/signup-question-and-answer) (or a [**Dynamics 365 Guides license**](/dynamics365/mixed-reality/guides/setup-step-one) that includes a Power Apps license).</span></span> <span data-ttu-id="d880f-193">이 가이드를 따라 Azure AD를 만든 경우 시스템 관리자에 대 한 역할 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-193">If following this guide you created the Azure AD, then you meet the role requirements for System Administrator.</span></span> <span data-ttu-id="d880f-194">또한 이전 단계에서 가이드 라이선스를 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-194">We also have assigned a Guides License in the previous step.</span></span>

<span data-ttu-id="d880f-195">이 가이드에서 [Microsoft Dataverse 환경을 만드는](/dynamics365/mixed-reality/guides/setup-step-two)방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-195">Within this guide to [create a Microsoft Dataverse environment](/dynamics365/mixed-reality/guides/setup-step-two):</span></span>

1. <span data-ttu-id="d880f-196">먼저 [전원 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/environments) 를 사용 하 여 새 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-196">Start by using the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments) and creating a New Environment.</span></span>
2. <span data-ttu-id="d880f-197">**새 환경을** 만들 때 **형식** 에 대해 **프로덕션** 을 선택할&#39;있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-197">When creating the **New Environment**, for the **Type** you&#39;ll be selecting **Production**.</span></span>
3. <span data-ttu-id="d880f-198">**이 환경에 대 한 데이터베이스 만들기를** 설정/해제 하는 것이 중요 한가요?</span><span class="sxs-lookup"><span data-stu-id="d880f-198">It is important that you toggle **Create a database for this environment?**</span></span>  <span data-ttu-id="d880f-199">**예** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-199">option to  **Yes**.</span></span>
4. <span data-ttu-id="d880f-200">**데이터베이스 추가** 대화 상자에서 **Dynamics 365 앱 사용** 옵션을 예로 설정 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="d880f-200">In the  **Add database**  dialog box, set the  **Enable Dynamics 365 apps**  option to  **Yes.**</span></span>

<span data-ttu-id="d880f-201">Dataverse에서 항목의 최대 파일 크기를 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-201">You'll want to increase the maximum file size of items in your dataverse.</span></span> <span data-ttu-id="d880f-202">최대 파일 크기를 늘리면 가이드에서 나중에 사용할 더 큰 3D 모델 또는 비디오 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-202">Increasing the max file size will allow you to upload larger 3D models or video files that you'll use later in your guides.</span></span> <span data-ttu-id="d880f-203">짧은 가이드에 따라 [최대 업로드 파일 크기를 변경](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-203">Follow a short guide [to change the maximum upload file size](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).</span></span>

<span data-ttu-id="d880f-204">마지막으로 솔루션을 설치 하 [고 구성](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-204">Lastly, you'll need to [install and configure the solution](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution).</span></span> <span data-ttu-id="d880f-205">[전원 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/environments)에서 **리소스** \& gt;를 선택 합니다.  **Dynamics 365 앱** 의 목록에서 **Dynamics 365 Guides** 을 선택 하 고 **설치** 를 선택 합니다.  </span><span class="sxs-lookup"><span data-stu-id="d880f-205">In the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments), select  **Resources**  \&gt;  **Dynamics 365 apps**, select  **Dynamics 365 Guides**  in the list, and then select  **Install**.</span></span>

<span data-ttu-id="d880f-206">앱을 사용 하려면 먼저 [가이드 보안 역할을 추가](/dynamics365/mixed-reality/guides/assign-role) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-206">You need [add a Guides security role](/dynamics365/mixed-reality/guides/assign-role) before you’re able to use the apps.</span></span>

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a><span data-ttu-id="d880f-207">제작을 통해 PC에서 테스트 가이드 만들기</span><span class="sxs-lookup"><span data-stu-id="d880f-207">Create a test Guide on your PC via Authoring</span></span>

<span data-ttu-id="d880f-208">가이드를 만들 때 항상 PC에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-208">When creating Guides you will always start on your PC.</span></span> <span data-ttu-id="d880f-209">단계 만들기, 모델 선택 및 가이드 고정 방법</span><span class="sxs-lookup"><span data-stu-id="d880f-209">Creating the steps, selecting models, and how to anchor the guide.</span></span> <span data-ttu-id="d880f-210">그러면 나중에 HoloLens 장치의 제작 모드에서 가이드에 대 한 콘텐츠를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-210">This will be followed by placing content for your guide later in in authoring mode on your HoloLens device.</span></span> <span data-ttu-id="d880f-211">이 가이드의 목적에 따라 최소한의 단계와 모델을 사용 하 여 간단한 테스트 가이드를 작성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-211">For the purposes of this guide, we suggest making a short test guide with minimal steps and models.</span></span>

<span data-ttu-id="d880f-212">가이드 작성에 대 한 학습을 시작 하려면 [제작 개요](/dynamics365/mixed-reality/guides/authoring-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-212">If you'd like to start learning about authoring for Guides, start here with the [authoring overview](/dynamics365/mixed-reality/guides/authoring-overview).</span></span> <span data-ttu-id="d880f-213">또는 빠른 추적 개요를 보려면이 짧은 동영상을 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-213">Or to get a fast track overview, watch this short video.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a><span data-ttu-id="d880f-214">선택 사항: 키오스크 모드</span><span class="sxs-lookup"><span data-stu-id="d880f-214">Optional: Kiosk mode</span></span>

<span data-ttu-id="d880f-215">키오스크 모드는 IT 관리자가 단일 앱 또는 앱 선택을 표시 하도록 시작 메뉴의 UI를 구성 하는 데 사용 되는 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-215">Kiosk mode is a mode that let's an IT Admin configure the start menu's UI to show only a single app, or selection of apps.</span></span> <span data-ttu-id="d880f-216">키오스크는 특정 사용자, 그룹 또는 장치 수준에 적용 될 수도 있습니다. 때로는 키오스크에서 특정 사용자를 제외 하 고 일반 시작 메뉴에 대 한 액세스를 허용 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-216">A kiosk can also be applied to specific users, groups, or at the device level; and in some cases, exclude certain users from the Kiosk still allowing them access to the regular start menu.</span></span>

<span data-ttu-id="d880f-217">키오스크 모드에는 키오스크를 HoloLens에 배포 하는 방법 뿐만 아니라 설정할 수 있는 범위와 구성 모두 다른 여러 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-217">Kiosk mode has many different variables, both in scope and configurations that can be set as well as methods of deploying the Kiosk to the HoloLens.</span></span> <span data-ttu-id="d880f-218">이러한 모든 변수 때문에 키오스크 모드는이 가이드에 대 한 _선택 사항_ 으로 유지 되며,이를 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-218">Because of all these variables, Kiosk mode is being left as _optional_ for this guide and won't be revisited.</span></span> <span data-ttu-id="d880f-219">사용자가 사용할 수 있는 앱을 제한 해야 하거나 더 자세히 알고 싶은 경우, [HoloLens를 키오스크로 설정](/hololens/hololens-kiosk)하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d880f-219">If you believe you have a business need to restrict available apps to users or would like to learn more, then feel free to learn how to [Set up HoloLens as a kiosk](/hololens/hololens-kiosk).</span></span>

## <a name="optional-wdac"></a><span data-ttu-id="d880f-220">선택 사항: WDAC</span><span class="sxs-lookup"><span data-stu-id="d880f-220">Optional: WDAC</span></span>

<span data-ttu-id="d880f-221">WDAC를 사용 하면 IT 관리자가 장치의 앱 시작을 차단 하도록 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-221">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="d880f-222">이는 사용자가 장치에서 앱을 숨기는 UI를 사용 하 여 표시 되지만 여전히 시작할 수 있는 키오스크 모드와 같은 장치 제한 방법과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-222">This is different than methods of device restriction, such as Kiosk mode, where the user is presented with a UI that hides the apps on the device, but they can still be launched.</span></span> <span data-ttu-id="d880f-223">WDAC가 구현 되는 동안 앱은 모든 앱 목록에 계속 표시 되지만, WDAC는 장치 사용자가 해당 앱 및 프로세스를 시작할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-223">While WDAC is implemented, the apps are still visible in the All Apps list, but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="d880f-224">자세한 내용은 [WDAC 및 Windows PowerShell를 사용 하 여 Microsoft Intune를 통해 HoloLens 2 장치에서 앱을 허용 하거나 차단](/mem/intune/configuration/custom-profile-hololens)합니다.</span><span class="sxs-lookup"><span data-stu-id="d880f-224">For more information, reference [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

[<span data-ttu-id="d880f-225">Windows Defender 애플리케이션 제어 - WDAC</span><span class="sxs-lookup"><span data-stu-id="d880f-225">Windows Defender Application Control - WDAC</span></span>](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a><span data-ttu-id="d880f-226">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d880f-226">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="d880f-227">회사에 연결 된 배포-배포</span><span class="sxs-lookup"><span data-stu-id="d880f-227">Corporate connected deployment - Deploy</span></span>](hololens2-corp-connected-deploy.md)