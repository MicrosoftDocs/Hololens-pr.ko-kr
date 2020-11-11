---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 로드 하 고 설치 하는 방법
description: UI를 통해 앱 로드 및 설치
keywords: 앱 관리, 앱, hololens, 앱 설치 관리자
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eba1fd00215ef197f9e32949e958bdbded089d6d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162893"
---
# <span data-ttu-id="9c4f1-104">앱 설치 관리자를 통해 HoloLens 2에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="9c4f1-104">Install Apps on HoloLens 2 via App Installer</span></span>


<span data-ttu-id="9c4f1-105">Windows 홀로그램, 버전 20H2 업데이트 직후에 앱 설치 관리자 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-105">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="9c4f1-106">HoloLens 2 장치에 **응용 프로그램을 더욱 원활 하 게 설치할 수 있도록 새 접근 권한 (앱 설치 관리자)을 추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-106">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="9c4f1-107">**관리 되지 않는 장치에 대 한 기능은 기본적으로 설정**됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-107">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="9c4f1-108">엔터프라이즈에 대 한 혼란을 방지 하기 위해 지금은 **관리 장치에** 앱 설치 관리자를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-108">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="9c4f1-109">이 기능은 현재 Windows 참가자 빌드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-109">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="9c4f1-110">[Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="9c4f1-110">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="9c4f1-111">Windows 참가자 릴리스에서 HoloLens 2 장치에 **응용 프로그램을 더욱 원활 하 게 설치할 수 있도록 새 기능 (앱 설치 관리자)을 추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-111">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="9c4f1-112">**관리 되지 않는 장치에 대 한 기능은 기본적으로 설정**됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-112">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="9c4f1-113">엔터프라이즈에 대 한 혼란을 방지 하기 위해 지금은 **관리 장치에** 앱 설치 관리자를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-113">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="9c4f1-114">다음과 **같은 경우에** 는 장치가 "관리"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-114">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="9c4f1-115">MDM [등록](hololens-enroll-mdm.md) 됨</span><span class="sxs-lookup"><span data-stu-id="9c4f1-115">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="9c4f1-116">[배포 패키지](hololens-provisioning.md) 를 사용 하 여 구성</span><span class="sxs-lookup"><span data-stu-id="9c4f1-116">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="9c4f1-117">사용자 [id](hololens-identity.md) 가 AAD입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-117">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="9c4f1-118">이제 개발자 모드를 사용 하거나 디바이스 포털을 사용할 필요 없이 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-118">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="9c4f1-119">장치에 Appx 번들을 다운로드 하 고 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지가 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-119">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="9c4f1-120">또는 [웹 페이지에서 설치를 시작](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-120">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="9c4f1-121">MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 앱을 배포 하려면 [서명 도구로](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 디지털 서명 하 고 [서명에 사용 되는 인증서](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 를 HoloLens 장치에서 신뢰 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-121">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="9c4f1-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c4f1-122">Requirements</span></span>

### <span data-ttu-id="9c4f1-123">장치:</span><span class="sxs-lookup"><span data-stu-id="9c4f1-123">For your devices:</span></span> 
<span data-ttu-id="9c4f1-124">현재이는 HoloLens 2 장치에 대 한 [Windows 참가자 빌드](hololens-insider.md) 에 avalible입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-124">This is currently avalible in [Windows Insider builds](hololens-insider.md) for HoloLens 2 devices.</span></span> <span data-ttu-id="9c4f1-125">이 방법을 사용 하는 모든 장치가 [업데이트](hololens-update-hololens.md)되었는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-125">Please ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span> 

### <span data-ttu-id="9c4f1-126">앱:</span><span class="sxs-lookup"><span data-stu-id="9c4f1-126">For your apps:</span></span> 
<span data-ttu-id="9c4f1-127">앱 설치 관리자가 스토어의 종속성을 사용 하므로 앱의 솔루션 구성이 **Master** 또는 **Release** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-127">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="9c4f1-128">[앱 패키지 만들기](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-128">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="9c4f1-129">이 방법을 통해 설치 된 앱은 디지털 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-129">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="9c4f1-130">앱에 서명 하는 데 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-130">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="9c4f1-131">[MS 신뢰 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)에서 인증서를 가져올 수 있으며,이 경우 추가 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-131">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="9c4f1-132">또는 인증서를 장치에 푸시 해야 하지만 본인의 인증서에 서명할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-132">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="9c4f1-133">[서명 도구를 사용 하 여](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 앱에 서명 하는 방법</span><span class="sxs-lookup"><span data-stu-id="9c4f1-133">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="9c4f1-134">인증서 옵션:</span><span class="sxs-lookup"><span data-stu-id="9c4f1-134">Certificate options:</span></span>** 
- [<span data-ttu-id="9c4f1-135">MS 신뢰할 수 있는 CA 목록</span><span class="sxs-lookup"><span data-stu-id="9c4f1-135">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="9c4f1-136">인증서 배포 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-136">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="9c4f1-137">[배포 패키지](hololens-provisioning.md) 는 로컬 장치에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-137">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="9c4f1-138">[장치 구성으로 인증서를 적용](https://docs.microsoft.com/mem/intune/protect/certificates-configure)하는 데 MDM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-138">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="9c4f1-139">장치 [인증서 관리자](certificate-manager.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-139">Use the on device [Certificate Manager](certificate-manager.md).</span></span> 

## <span data-ttu-id="9c4f1-140">설치 방법</span><span class="sxs-lookup"><span data-stu-id="9c4f1-140">Installation method</span></span>

1.  <span data-ttu-id="9c4f1-141">장치가 관리 되는 것으로 간주 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-141">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="9c4f1-142">HoloLens 2 디바이스의 전원이 켜져 있고 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-142">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="9c4f1-143">PC에서 사용자 지정 앱으로 이동 하 고 yourapp를 yourdevicename\Internal Storage\Downloads.에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-143">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="9c4f1-144">파일 복사가 완료 되 면 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-144">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="9c4f1-145">HoloLens 2 장치에서 **시작 메뉴**를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-145">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="9c4f1-146">다운로드 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-146">Navigate to the Downloads folder.</span></span> <span data-ttu-id="9c4f1-147">앱의 왼쪽 창에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-147">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="9c4f1-148">Yourapp 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-148">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="9c4f1-149">앱 설치 관리자가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-149">The App Installer will launch.</span></span> <span data-ttu-id="9c4f1-150">**설치** 단추를 선택 하 여 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-150">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="9c4f1-151">설치가 완료 되 면 설치 된 앱이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-151">The installed app will automatically launch upon the completion of installing.</span></span> 

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="9c4f1-153">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9c4f1-153">Troubleshooting Installs</span></span>
<span data-ttu-id="9c4f1-154">앱을 설치 하지 못한 경우 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-154">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="9c4f1-155">앱이 마스터 또는 릴리스 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-155">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="9c4f1-156">장치가이 기능을 사용할 수 있는 빌드로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-156">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="9c4f1-157">[인터넷에 연결](hololens-network.md)되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-157">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="9c4f1-158">[Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-158">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="9c4f1-159">웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="9c4f1-159">Web Installer</span></span>

<span data-ttu-id="9c4f1-160">사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-160">Users can install an app directly from a web server.</span></span> <span data-ttu-id="9c4f1-161">이를 통해 간편 하 게 다운로드 하 고 설치할 수 있는 앱 설치 관리자가 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-161">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="9c4f1-162">웹 설치를 설정 하는 방법:</span><span class="sxs-lookup"><span data-stu-id="9c4f1-162">How to set up web install:</span></span>
1.  <span data-ttu-id="9c4f1-163">앱이 설치 되도록 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-163">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="9c4f1-164">[웹 페이지에서이 기능을 사용 하도록 설정 하려면 다음 단계를](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)따르세요.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-164">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="9c4f1-165">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="9c4f1-165">End user experience:</span></span>
1. <span data-ttu-id="9c4f1-166">사용자가 이전에 위에서 선택한 방법을 사용 하 여 디바이스에 인증서를 받아서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-166">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="9c4f1-167">사용자가 위의 단계에서 만든 URL을 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-167">User visits the URL created from the step above.</span></span>

<span data-ttu-id="9c4f1-168">이제 앱이 디바이스에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-168">The app will now install to the device.</span></span> <span data-ttu-id="9c4f1-169">앱을 찾으려면 **시작 메뉴** 를 열고 **모든 앱** 단추를 선택 하 여 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-169">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="9c4f1-170">이 설치 방법 문제 해결에 대 한 도움말은 [앱 설치 관리자 문제 해결](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-170">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="9c4f1-171">업데이트 프로세스가 진행 되는 동안 UI가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-171">UI during the update process is not supported.</span></span> <span data-ttu-id="9c4f1-172">따라서 [이 페이지](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 및 관련 옵션의 showprompt 옵션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-172">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="9c4f1-173">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="9c4f1-173">Sample Apps</span></span>

<span data-ttu-id="9c4f1-174">샘플 앱을 사용 하 여이 작업을 수행해 보려면 사용 가능한 샘플 중 일부를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-174">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="9c4f1-175">MRTK 예제 허브</span><span class="sxs-lookup"><span data-stu-id="9c4f1-175">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="9c4f1-176">평면</span><span class="sxs-lookup"><span data-stu-id="9c4f1-176">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="9c4f1-177">테스트에 사용할 수 있는 UWP 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="9c4f1-177">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
