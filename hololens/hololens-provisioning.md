---
title: 프로비전 패키지(HoloLens)를 사용하여 HoloLens 구성
description: Windows 프로비전을 통해 IT 관리자가 이미징 없이 최종 사용자 장치를 쉽게 구성할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 917e9fd0e8bf69eb0b7c53165029cb8e42904582
ms.sourcegitcommit: ab9e70e68d546cc6965e1569e5d914995fa508da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "10955460"
---
# <span data-ttu-id="ba72a-103">프로비전 패키지를 사용하여 HoloLens 구성</span><span class="sxs-lookup"><span data-stu-id="ba72a-103">Configure HoloLens by using a provisioning package</span></span>

<span data-ttu-id="ba72a-104">[Windows 프로비저닝을](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 사용하면 IT 관리자가 인식 없이 최종 사용자 장치를 손쉽게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-104">[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) makes it easy for IT administrators to configure end-user devices without imaging.</span></span> <span data-ttu-id="ba72a-105">Windows 구성 디자이너는 이미지 및 런타임 설정을 구성한 후 패키지에 프로비전 패키지에 기본 제공되는 이미지 및 런타임 설정을 구성하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-105">Windows Configuration Designer is a tool for configuring images and runtime settings which are then built into provisioning packages.</span></span>

<span data-ttu-id="ba72a-106">프로비저닝 패키지에서 적용할 수 있는 일부 HoloLens 구성 중 일부는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-106">Some of the HoloLens configurations that you can apply in a provisioning package include the following:</span></span>

- <span data-ttu-id="ba72a-107">여기에서 비즈니스용 Windows Holographic으로 [업그레이드](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ba72a-107">Upgrade to Windows Holographic for Business [here](hololens1-upgrade-enterprise.md)</span></span>
- <span data-ttu-id="ba72a-108">로컬 계정 설정</span><span class="sxs-lookup"><span data-stu-id="ba72a-108">Set up a local account</span></span>
- <span data-ttu-id="ba72a-109">Wi-Fi 연결 설정</span><span class="sxs-lookup"><span data-stu-id="ba72a-109">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="ba72a-110">장치에 인증서 적용</span><span class="sxs-lookup"><span data-stu-id="ba72a-110">Apply certificates to the device</span></span>
- <span data-ttu-id="ba72a-111">개발자 모드 사용</span><span class="sxs-lookup"><span data-stu-id="ba72a-111">Enable Developer Mode</span></span>
- <span data-ttu-id="ba72a-112">선택키 모드 구성(키오스크 모드 구성에 대한 자세한 지침은 여기 있을 수 있음)에서 확인할 수 [있습니다.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="ba72a-112">Configure Kiosk mode (Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).</span></span>

## <span data-ttu-id="ba72a-113">패키지 HoloLens 프로비전 마법사</span><span class="sxs-lookup"><span data-stu-id="ba72a-113">Provisioning package HoloLens wizard</span></span>

<span data-ttu-id="ba72a-114">HoloLens 마법사를 사용하면 프로비전 패키지에서 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-114">The HoloLens wizard helps you configure the following settings in a provisioning package:</span></span>

- <span data-ttu-id="ba72a-115">Enterprise Edition으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ba72a-115">Upgrade to the enterprise edition</span></span>

    > [!NOTE]
    > <span data-ttu-id="ba72a-116">이는 HoloLens 1세대 장치에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-116">This should only be used for HoloLens 1st gen devices.</span></span> <span data-ttu-id="ba72a-117">프로비전 패키지의 설정은 프로비전 패키지에 비즈니스용 Windows Holographic에 대한 편집 라이선스를 포함하거나 장치가 비즈니스용 [Windows Holographic for Business로 이미 업그레이드된 경우에만 적용됩니다.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ba72a-117">Settings in a provisioning package are only be applied if the provisioning package includes an edition upgrade license to Windows Holographic for Business or if [the device has already been upgraded to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

- <span data-ttu-id="ba72a-118">HoloLens 첫 번째 환경 구성(OOBE)</span><span class="sxs-lookup"><span data-stu-id="ba72a-118">Configure the HoloLens first experience (OOBE)</span></span>
- <span data-ttu-id="ba72a-119">Wi-Fi 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="ba72a-119">Configure the Wi-Fi network</span></span>
- <span data-ttu-id="ba72a-120">Azure Active Directory에서 장치를 등록하거나 로컬 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="ba72a-120">Enroll the device in Azure Active Directory, or create a local account</span></span>
- <span data-ttu-id="ba72a-121">인증서 추가</span><span class="sxs-lookup"><span data-stu-id="ba72a-121">Add certificates</span></span>
- <span data-ttu-id="ba72a-122">개발자 모드 사용</span><span class="sxs-lookup"><span data-stu-id="ba72a-122">Enable Developer Mode</span></span>
- <span data-ttu-id="ba72a-123">선택 모드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-123">Configure kiosk mode.</span></span> <span data-ttu-id="ba72a-124">키오스크 모드를 구성하는 자세한 지침은 여기에서 확인할 수 [있습니다.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="ba72a-124">(Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).</span></span>

> [!WARNING]
> <span data-ttu-id="ba72a-125">마법사 중 하나를 사용하여 Windows 10에서 Windows 구성 디자이너를 실행하여 Azure Active Directory 등록을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-125">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using any of the wizards.</span></span>

<span data-ttu-id="ba72a-126">패키지 프로비전에는 관리 지침 및 정책, 사용자 지정 네트워크 연결 및 정책 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-126">Provisioning packages can include management instructions and policies, custom network connections and policies, and more.</span></span>

> [!TIP]
> <span data-ttu-id="ba72a-127">데스크톱 마법사를 사용하여 일반 설정이 포함된 패키지를 만든 후 기타 설정, 앱, 정책 등을 추가하려면 고급 편집기로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-127">Use the desktop wizard to create a package with the common settings, then switch to the advanced editor to add other settings, apps, policies, etc.</span></span>

## <span data-ttu-id="ba72a-128">패키지 프로비전 단계</span><span class="sxs-lookup"><span data-stu-id="ba72a-128">Steps for creating provisioning packages</span></span>

1. <span data-ttu-id="ba72a-129">**옵션 1:** [Microsoft Store에서.](https://www.microsoft.com/store/apps/9nblggh4tx22)</span><span class="sxs-lookup"><span data-stu-id="ba72a-129">**Option 1:** [From Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span> <span data-ttu-id="ba72a-130">여기에는 HoloLens 2의 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-130">This includes HoloLens 2 capabilities.</span></span>
2. <span data-ttu-id="ba72a-131">**옵션 2:** [Windows 10에 대한 Windows 평가 및 배포 키트(ADK)부터.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)</span><span class="sxs-lookup"><span data-stu-id="ba72a-131">**Option 2:** [From the Windows Assessment and Deployment Kit (ADK) for Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="ba72a-132">Windows ADK에서 Windows 구성 디자이너를 설치하는 경우 대화 **상자에서 설치할 기능을 선택하도록 디자이너를** 선택합니다. **Configuration Designer**</span><span class="sxs-lookup"><span data-stu-id="ba72a-132">If you install Windows Configuration Designer from the Windows ADK, select **Configuration Designer** from the **Select the features you want to install** dialog box.</span></span> <span data-ttu-id="ba72a-133">이 옵션에는 HoloLens 2 기능이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-133">This option does not include HoloLens 2 capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="ba72a-134">Windows 구성 디자이너에 액세스할 때는 고급 복구 도구에 대한 오프라인 앱 설치 여기를 설치하되, Windows 확인 대신 선택 영역을 따르세요. [here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store)</span><span class="sxs-lookup"><span data-stu-id="ba72a-134">If you know you will be using an offline PC that needs access to Windows Configuration Designer please follow the offline app install [here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) for Advanced Recovery Companion but making Windows Confiugration Desinger your selection instead.</span></span> 

### <span data-ttu-id="ba72a-135">2. 프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="ba72a-135">2. Create the provisioning package</span></span>

<span data-ttu-id="ba72a-136">Windows 구성 디자이너 도구를 사용하여 프로비전 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-136">Use the Windows Configuration Designer tool to create a provisioning package.</span></span>

1. <span data-ttu-id="ba72a-137">Windows 구성 디자이너를 엽니다(기본적으로 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span><span class="sxs-lookup"><span data-stu-id="ba72a-137">Open Windows Configuration Designer (by default, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span></span>

2. <span data-ttu-id="ba72a-138">**프로비전 HoloLens 장치 선택**</span><span class="sxs-lookup"><span data-stu-id="ba72a-138">Select **Provision HoloLens devices**.</span></span>

   ![ICD 시작 옵션](images/icd-create-options-1703.png)

3. <span data-ttu-id="ba72a-140">프로젝트 이름을 지정하고 **마침을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-140">Name your project and select **Finish**.</span></span>

4. <span data-ttu-id="ba72a-141">시작 페이지에 대한 **지침을 읽고 다음을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-141">Read the instructions on the **Getting started** page and select **Next**.</span></span> <span data-ttu-id="ba72a-142">데스크톱 프로비전 페이지는 다음 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-142">The pages for desktop provisioning walk you through the following steps.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ba72a-143">프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-143">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="ba72a-144">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-144">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="ba72a-145">안전한 장소에 프로젝트 파일을 저장하고 더 이상 필요하지 않은 경우에는 프로젝트 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-145">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

### <span data-ttu-id="ba72a-146">설정 구성</span><span class="sxs-lookup"><span data-stu-id="ba72a-146">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br><span data-ttu-id="ba72a-147">HoloLens Edition을 업그레이드하려면 엔터프라이즈 라이선스 파일을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-147">Browse to and select the enterprise license file to upgrade the HoloLens edition.</span></span></br></br><span data-ttu-id="ba72a-148">토글 키를 하도록 또는 <strong> </strong> 아니요로 <strong> </strong> 설정하여 첫 번째 환경의 일부를 숨올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-148">You can also toggle <strong>Yes</strong> or <strong>No</strong> to hide parts of the first experience.</span></span></br></br><span data-ttu-id="ba72a-149">Wi-Fi 네트워크에 연결할 필요 없이 장치를 설정하려면 <strong> 스크립트 Wi-Fi 설정을 사용으로 </strong> <strong> </strong> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-149">To set up the device without the need to connect to a Wi-Fi network, toggle <strong>Skip Wi-Fi setup</strong> to <strong>On</strong>.</span></span></br></br><span data-ttu-id="ba72a-150">장치를 사용할 지역 및 표준 시간대를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-150">Select a region and timezone in which the device will be used.</span></span> </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br><span data-ttu-id="ba72a-151">이 섹션에서는 장치가 자동으로 연결되어야 하는 Wi-Fi 무선 네트워크의 세부 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-151">In this section, you can enter the details of the Wi-Fi wireless network that the device should automatically connect to.</span></span> <span data-ttu-id="ba72a-152">이렇게 하려면 설정, <strong> </strong> SSID, 네트워크 유형(Open 또는 <strong> </strong> <strong> WPA2-Personal), </strong> <strong> (WPA2-Personal)을 선택하고 무선 네트워크의 </strong> 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-152">To do this, select <strong>On</strong>, enter the SSID, the network type (<strong>Open</strong> or <strong>WPA2-Personal</strong>), and (if <strong>WPA2-Personal</strong>) the password for the wireless network.</span></span></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br><span data-ttu-id="ba72a-153">Azure Active Directory에 장치를 등록하거나 장치에서 로컬 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-153">You can enroll the device in Azure Active Directory, or create a local account on the device</span></span></br></br><span data-ttu-id="ba72a-154">Windows 구성 디자이너 마법사를 사용하여 대량 Azure AD 등록을 구성하려면 먼저 <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">조직에서 Azure AD 가입을 설정</a>합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="ba72a-155">Azure AD 테넌트의 <strong>사용자당 최대 장치 수</strong>는 마법사에서 얻은 대량 토큰을 사용할 수 있는 횟수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="ba72a-156">Azure AD에 디바이스를 등록하려면 해당 옵션을 선택하고 마법사를 사용하여 가져올 대량 토큰의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="ba72a-157">토큰의 만료 날짜를 설정합니다(토큰을 가져온 날로부터 최대 30일).</span><span class="sxs-lookup"><span data-stu-id="ba72a-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="ba72a-158">대중 <strong> 스토어 가져오기를 </strong> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-158">Select <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="ba72a-159">로그인&#39;있는 계정을 입력한 다음, Azure AD에 장치를 참가할 수 있는 권한이 <strong> </strong> 있는 계정을 입력한 다음 해당 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="ba72a-160"><strong>수락을 </strong> 선택하여 Windows 구성 디자이너에게 필요한 사용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-160">Select <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span> </br></br><span data-ttu-id="ba72a-161">로컬 계정을 만들려면 해당 옵션을 선택하고 사용자 이름 및 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-161">To create a local account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="ba72a-162">중요:</span><span class="sxs-lookup"><span data-stu-id="ba72a-162">Important:</span></span></strong> <br /><span data-ttu-id="ba72a-163">(Windows 10, 버전 1607에만 해당) 프로비전 패키지에서 로컬 계정을 만드는 경우 <strong> 42일마다 설정 </strong> 앱을 사용하여 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-163">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="ba72a-164">기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-164">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="ba72a-165">인증서를 사용하여 디바이스를 프로비전하려면 <strong>인증서 추가</strong>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-165">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="ba72a-166">인증서 이름을 입력하고 사용할 인증서를 찾아서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-166">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><span data-ttu-id="ba72a-167">Yes 또는 <strong> </strong> No를 설정하여 <strong> </strong> HoloLens에서 개발자 모드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-167">Toggle <strong>Yes</strong> or <strong>No</strong> to enable Developer Mode on the HoloLens.</span></span> <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)"><span data-ttu-id="ba72a-168">개발자 모드에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="ba72a-168">Learn more about Developer Mode.</span></span></a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br><span data-ttu-id="ba72a-169">프로비전 패키지를 보호할 암호를 설정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ba72a-169">Do not set a password to protect your provisioning package.</span></span> <span data-ttu-id="ba72a-170">프로비전 패키지가 암호에 의해 보호되는 경우 HoloLens 장치를 프로비전할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-170">If the provisioning package is protected by a password, provisioning the HoloLens device will fail.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="ba72a-171">완료한 후 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-171">After you're done, select **Create**.</span></span> <span data-ttu-id="ba72a-172">몇 초 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-172">It only takes a few seconds.</span></span> <span data-ttu-id="ba72a-173">패키지가 빌드되면 패키지가 저장된 위치가 페이지 맨 위에 하이퍼링크로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-173">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

### <span data-ttu-id="ba72a-174">3. 고급 프로비전을 사용하여 HoloLens용 프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="ba72a-174">3. Create a provisioning package for HoloLens by using advanced provisioning</span></span>

> [!NOTE]
> <span data-ttu-id="ba72a-175">고급 프로비전 에서 **Advanced provisioning** 만든 프로비전 패키지는 HoloLens(1세대)에 적용되는 편집 모음 업그레이드 라이선스를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-175">A provisioning package that you create in **Advanced provisioning** does not need to include an edition upgrade license to Windows Holographic for Business to succesfully apply to a HoloLens (1st gen).</span></span> <span data-ttu-id="ba72a-176">[HoloLens(1세)에 대한 자세한 내용을 참고하세요.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ba72a-176">[See more on Windows Holographic for Business for HoloLens (1st gen)](hololens1-upgrade-enterprise.md).</span></span>

1. <span data-ttu-id="ba72a-177">Windows 구성 디자이너 시작 페이지에서 **고급 프로비전**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-177">On the Windows Configuration Designer start page, select **Advanced provisioning**.</span></span>
2. <span data-ttu-id="ba72a-178">**프로젝트 세부 정보 입력** 창에서 프로젝트 이름 및 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-178">In the **Enter project details** window, specify a name for your project and the location for your project.</span></span> <span data-ttu-id="ba72a-179">선택적으로 프로젝트를 설명하는 간략한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-179">Optionally, enter a brief description to describe your project.</span></span>

3. <span data-ttu-id="ba72a-180">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-180">Select **Next**.</span></span>

4. <span data-ttu-id="ba72a-181">창을 **보고 구성할 설정 선택에서** **Windows 10 Holographic을 선택하고 다음을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-181">In the **Choose which settings to view and configure** window, select **Windows 10 Holographic**, and then select **Next**.</span></span>

5. <span data-ttu-id="ba72a-182">**마침을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-182">Select **Finish**.</span></span>

6. <span data-ttu-id="ba72a-183">런타임 **설정을 확장하고** 이 문서의 뒷부분에 나오는 설정중하나를 사용하여 [패키지를 사용자 지정합니다.](#what-you-can-configure)</span><span class="sxs-lookup"><span data-stu-id="ba72a-183">Expand **Runtime settings** and customize the package by using any of the settings [described later in this article](#what-you-can-configure).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ba72a-184">(Windows 10, 버전 1607에만 해당) 프로비전 패키지에서 로컬 계정을 만드는 경우 42일마다 **설정** 앱을 사용하여 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-184">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="ba72a-185">기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-185">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span> <span data-ttu-id="ba72a-186">사용자 계정이 잠긴 경우 [전체 장치 복구를 수행](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-186">If the user account is locked out, you must [perform a full device recovery](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).</span></span>

7. <span data-ttu-id="ba72a-187">파일 **저장을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-187">Select **File** > **Save**.</span></span>

8. <span data-ttu-id="ba72a-188">프로젝트 파일에 중요한 정보가 있을 수도 있는 경고를 읽고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-188">Read the warning that project files may contain sensitive information, and select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ba72a-189">프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-189">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="ba72a-190">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-190">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="ba72a-191">안전한 장소에 프로젝트 파일을 저장하고 더 이상 필요하지 않은 경우에는 프로젝트 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-191">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>
    
9. <span data-ttu-id="ba72a-192">**프로비전**  >  **패키지 내보내기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-192">Select **Export** > **Provisioning package**.</span></span>

10. <span data-ttu-id="ba72a-193">**소유자를** **IT 관리자로 변경합니다.** 이는 다른 소스에서 이 장치에 적용된 프로비전 패키지보다 이 프로비전 패키지의 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-193">Change **Owner** to **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span> <span data-ttu-id="ba72a-194">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-194">Select **Next**.</span></span>

11. <span data-ttu-id="ba72a-195">**패키지 버전**에 대한 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-195">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="ba72a-196">기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-196">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

12. <span data-ttu-id="ba72a-197">**프로비전 패키지에 대한 보안 세부 정보 선택에서 다음을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-197">On the **Select security details for the provisioning package**, select **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="ba72a-198">프로비전 패키지를 암호화 하는 경우 HoloLens 장치 프로비전이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-198">If you encrypt the provisioning package, provisioning the HoloLens device will fail.</span></span>  

13. <span data-ttu-id="ba72a-199">기본 **제공** 된 후 프로비전 패키지로 이동할 출력 위치를 지정하려면 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-199">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="ba72a-200">기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-200">By default, Windows Configuration Designer uses the project folder as the output location.</span></span>

    <span data-ttu-id="ba72a-201">필요에 하면 찾아보기를 **선택하여** 기본 출력 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-201">Optionally, you can select **Browse** to change the default output location.</span></span>

14. <span data-ttu-id="ba72a-202">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-202">Select **Next**.</span></span>

15. <span data-ttu-id="ba72a-203">빌드를 **선택하여** 패키지 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-203">Select **Build** to start building the package.</span></span> <span data-ttu-id="ba72a-204">빌드 페이지에서 프로젝트 정보가 표시되며 진행률 표시줄은 빌드 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-204">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>

16. <span data-ttu-id="ba72a-205">빌드가 완료되면 마침을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-205">When the build completes, select **Finish**.</span></span>

<span id="apply" />

## <span data-ttu-id="ba72a-206">설치 중 HoloLens에 프로비전 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="ba72a-206">Apply a provisioning package to HoloLens during setup</span></span>

<span data-ttu-id="ba72a-207">HoloLens 2 장치, [빌드 19041.1103 이상의](hololens-release-notes.md#windows-holographic-version-2004) HoloLens 2 장치는 USB 드라이브를 사용하여 프로비전 패키지를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-207">HoloLens 2 devices on build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) or later, may use a USB drive to apply a provisioning package.</span></span> <span data-ttu-id="ba72a-208">.ppkg 파일을 USB 드라이브의 루트에 복사하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-208">Simply copy the .ppkg file to the root of the USB drive.</span></span> <span data-ttu-id="ba72a-209">패키지 프로비전 패키지는 USB 드라이브의 루트에 있는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-209">Provisioning packages will only be applied if they’re in the root of the USB drive.</span></span> <span data-ttu-id="ba72a-210">여러 프로비저닝 패키지 프레젠테이션이 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-210">Multiple provisioning package present will be applied sequentially.</span></span>

1. <span data-ttu-id="ba72a-211">USB 음소스를 사용하여 장치를 PC(또는 위에서 설명한 대로 HoloLens 2의 USB 드라이브)에 연결한 다음 장치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-211">Use the USB cable to connect the device to a PC (or USB drive for HoloLens 2 as mentioned above), and then start the device.</span></span> <span data-ttu-id="ba72a-212">OOBE의 첫 번째 관심 **값 페이지를 지나서는** 지나간 관계없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-212">Do not continue past the **First interactable moment** page of OOBE.</span></span>   
    - <span data-ttu-id="ba72a-213">HoloLens(1차)에서 이 페이지에 파란색 상자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-213">On HoloLens (1st gen), this page contains a blue box.</span></span> 
    - <span data-ttu-id="ba72a-214">HoloLens 2에서 이 페이지에는 공백 비례가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-214">On HoloLens 2, this page contains the hummingbird.</span></span>

2. <span data-ttu-id="ba72a-215">**볼륨 작게** 단추 및 **전원** 단추를 동시에 잠시 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-215">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span> 

3. <span data-ttu-id="ba72a-216">HoloLens는 PC의 파일 탐색기에서 장치로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-216">HoloLens shows up as a device in File Explorer on the PC.</span></span>

4. <span data-ttu-id="ba72a-217">파일 탐색기에서 프로비저닝 패키지(.ppkg)를 장치 저장소로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-217">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

5. <span data-ttu-id="ba72a-218">OOBE의 첫 번째 **Volume Down** 상호 운용페이지에서 볼륨 작게와 전원 **단추를 동시에** 반복해서 누릅니다. **Power**</span><span class="sxs-lookup"><span data-stu-id="ba72a-218">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **First interactable moment** page of OOBE.</span></span>

6. <span data-ttu-id="ba72a-219">장치에서 패키지를 신뢰할 것인지, 이를 적용할 것인지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-219">The device asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="ba72a-220">패키지를 신뢰한다고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-220">Confirm that you trust the package.</span></span>

7. <span data-ttu-id="ba72a-221">패키지가 성공적으로 적용되었는지 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-221">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="ba72a-222">실패한 경우 패키지 문제를 해결하고 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-222">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="ba72a-223">성공한 경우 OOBE를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-223">If it succeeded, proceed with OOBE.</span></span>

> [!NOTE]
> <span data-ttu-id="ba72a-224">2016년 8월 이전에 장치를 구입한 경우, Microsoft 계정을 사용하여 장치에 로그인하고 최신 운영 체제 업데이트를 가져오은 다음 운영 체제를 다시 설정해야 프로비전 패키지를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-224">If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.</span></span>

## <span data-ttu-id="ba72a-225">설치 후 HoloLens에 프로비전 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="ba72a-225">Apply a provisioning package to HoloLens after setup</span></span>

> [!NOTE]
> <span data-ttu-id="ba72a-226">이 단계는 Windows 10, 버전 1809에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-226">These steps apply only toWindows 10, version 1809.</span></span>

<span data-ttu-id="ba72a-227">PC에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-227">On your PC, follow these steps:</span></span>
1. <span data-ttu-id="ba72a-228">[HoloLens 마법사를 사용하여 HoloLens용 프로비전](hololens-provisioning.md)패키지를 만들 때 설명한 프로비전 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-228">Create a provisioning package as described at [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).</span></span>
2. <span data-ttu-id="ba72a-229">USB 코블을 사용하여 HoloLens 장치를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-229">Connect the HoloLens device to a PC by using a USB cable.</span></span> <span data-ttu-id="ba72a-230">HoloLens는 PC의 파일 탐색기에서 장치로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-230">HoloLens shows up as a device in File Explorer on the PC.</span></span>
3. <span data-ttu-id="ba72a-231">프로비전 패키지를 HoloLens의 문서 폴더로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-231">Drag and drop the provisioning package to the Documents folder on the HoloLens.</span></span>

<span data-ttu-id="ba72a-232">HoloLens에서 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-232">On your HoloLens, follow these steps:</span></span>
1. <span data-ttu-id="ba72a-233">설정 계정 **액세스 회사**  >  **또는**  >  **학교로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-233">Go to **Settings** > **Accounts** > **Access work or school**.</span></span> 
2. <span data-ttu-id="ba72a-234">관련 **설정에서 프로비전** **패키지 추가 또는 제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-234">In **Related Settings**, select **Add or remove a provisioning package**.</span></span>
3. <span data-ttu-id="ba72a-235">다음 페이지에서 파일 **선택기를 시작할** 패키지 추가를 선택하고 프로비전 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-235">On the next page, select **Add a package** to launch the file picker and select your provisioning package.</span></span> <span data-ttu-id="ba72a-236">폴더가 비어 있는 경우 이 장치를 선택하고 **문서를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-236">If the folder is empty, make sure you select **This Device** and select **Documents**.</span></span>

<span data-ttu-id="ba72a-237">패키지를 적용하고 나면 설치된 패키지 **목록에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ba72a-237">After your package has been applied, it shows up in the list of **Installed packages**.</span></span> <span data-ttu-id="ba72a-238">패키지 세부 정보를 보거나, 장치에서 패키지를 제거하려면 나열된 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-238">To view the package details or to remove the package from the device, select the listed package.</span></span>

## <span data-ttu-id="ba72a-239">구성할 수 있는 항목</span><span class="sxs-lookup"><span data-stu-id="ba72a-239">What you can configure</span></span>

<span data-ttu-id="ba72a-240">프로비저닝 패키지는 CSP(구성 서비스 공급자)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-240">Provisioning packages make use of configuration service providers (CSPs).</span></span> <span data-ttu-id="ba72a-241">CSP에 대해 잘 모르는 경우 IT 전문가를 위한 [CSP(구성 서비스 공급자) 소개](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba72a-241">If you're not familiar with CSPs, see [Introduction to configuration service providers (CSPs) for IT pros](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).</span></span>

<span data-ttu-id="ba72a-242">Windows 구성 디자이너에서는 Windows Holographic용 프로비저닝 패키지를 만들 때 **사용 가능한 사용자 지정**의 설정은 [Windows Holographic에서 지원되는 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-242">In Windows Configuration Designer, when you create a provisioning package for Windows Holographic, the settings in **Available customizations** are based on [CSPs that are supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span> <span data-ttu-id="ba72a-243">다음 표에서는 HoloLens에 구성하려는 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-243">The following table describes settings that you might want to configure for HoloLens.</span></span>

![HoloLens에 대한 일반적인 런타임 설정](images/icd-settings.png)

| <span data-ttu-id="ba72a-245">설정</span><span class="sxs-lookup"><span data-stu-id="ba72a-245">Setting</span></span> | <span data-ttu-id="ba72a-246">설명</span><span class="sxs-lookup"><span data-stu-id="ba72a-246">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="ba72a-247">인증서</span><span class="sxs-lookup"><span data-stu-id="ba72a-247">Certificates</span></span>** | <span data-ttu-id="ba72a-248">HoloLens에 인증서를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-248">Deploy a certificate to HoloLens.</span></span>  |
| **<span data-ttu-id="ba72a-249">ConnectivityProfiles</span><span class="sxs-lookup"><span data-stu-id="ba72a-249">ConnectivityProfiles</span></span>** | <span data-ttu-id="ba72a-250">HoloLens에 Wi-Fi 프로필을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-250">Deploy a Wi-Fi profile to HoloLens.</span></span>   |
| **<span data-ttu-id="ba72a-251">EditionUpgrade</span><span class="sxs-lookup"><span data-stu-id="ba72a-251">EditionUpgrade</span></span>** | [<span data-ttu-id="ba72a-252">비즈니스용 Windows Holographic으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-252">Upgrade to Windows Holographic for Business.</span></span>](hololens1-upgrade-enterprise.md)  |
| **<span data-ttu-id="ba72a-253">정책</span><span class="sxs-lookup"><span data-stu-id="ba72a-253">Policies</span></span>** | <span data-ttu-id="ba72a-254">HoloLens에서 개발자 모드를 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-254">Allow or prevent developer mode on HoloLens.</span></span> [<span data-ttu-id="ba72a-255">Windows Holographic for Business 지원 정책</span><span class="sxs-lookup"><span data-stu-id="ba72a-255">Policies supported by Windows Holographic for Business</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

> [!NOTE]
> <span data-ttu-id="ba72a-256">HoloLens는 현재 프로비저닝 패키지를 사용하여**앱 설치(UniversalAppInstall)를**지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba72a-256">HoloLens does not currently support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span>
