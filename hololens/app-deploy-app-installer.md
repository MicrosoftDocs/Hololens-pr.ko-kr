---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 로드 하 고 설치 하는 방법
description: UI를 통해 앱 로드 및 설치
keywords: 앱 관리, 앱, hololens, 앱 설치 관리자
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135529"
---
# <span data-ttu-id="96f47-104">앱 설치 관리자를 통해 HoloLens 2에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="96f47-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="96f47-105">Windows 참가자 릴리스에서 HoloLens 2 장치에 **응용 프로그램을 더욱 원활 하 게 설치할 수 있도록 새 기능 (앱 설치 관리자)을 추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-105">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span>  <span data-ttu-id="96f47-106">이제 개발자 모드를 사용 하거나 디바이스 포털을 사용할 필요 없이 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-106">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="96f47-107">장치에 Appx 번들을 다운로드 하 고 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지가 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-107">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="96f47-108">또는 [웹 페이지에서 설치를 시작](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-108">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="96f47-109">MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 앱을 배포 하려면 [서명 도구로](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 디지털 서명 하 고 [서명에 사용 되는 인증서](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 를 HoloLens 장치에서 신뢰 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-109">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

<span data-ttu-id="96f47-110">이 업데이트 [는 기본적으로 테스트용 로드를 사용 하는](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/) 데스크톱에 맞게 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-110">This update aligns with desktop where [Sideloading is Enabled by Default](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96f47-111">이 기능은 현재 Windows 참가자 빌드 19041.1377 +에만 avalible 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-111">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="96f47-112">[Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="96f47-112">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="96f47-113">이 기능을 사용 하지 않도록 설정 하려는 IT 관리자의 경우 [WDAC 정책의](windows-defender-application-control-wdac.md)일부로 다음 패키지 패밀리 이름을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="96f47-113">For IT Admins who wish to disable this feature please use the following package family name as part of your [WDAC policy](windows-defender-application-control-wdac.md).</span></span> <span data-ttu-id="96f47-114">앱 설치 관리자 앱만 차단 되며 Microsoft Store 또는 MDM 솔루션 등의 다른 원본에서 설치 된 앱이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-114">This will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> <span data-ttu-id="96f47-115">앱을 제어 하는 데 [WDAC 정책을](windows-defender-application-control-wdac.md) 사용 하는 것이 좋지만, microsoft store 앱만 허용 하려는 경우 [Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) policy를 명시적으로 "허용 안 함"으로 설정 하도록 구성 된 장치에서 microsoft store에서 앱만 설치할 수 있도록 허용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-115">It is recommended to use [WDAC policy](windows-defender-application-control-wdac.md) to control apps, however if you only want to allow Microsoft Store apps, devices configured to set the [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) policy explicitly to “not allow” will only allow apps to be installed from the Microsoft Store.</span></span> 

## <span data-ttu-id="96f47-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96f47-116">Requirements</span></span>

### <span data-ttu-id="96f47-117">장치:</span><span class="sxs-lookup"><span data-stu-id="96f47-117">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="96f47-118">이 기능은 현재 Windows 참가자 빌드 19041.1377 +에만 avalible 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-118">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="96f47-119">[Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="96f47-119">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="96f47-120">앱:</span><span class="sxs-lookup"><span data-stu-id="96f47-120">For your apps:</span></span> 
<span data-ttu-id="96f47-121">앱 설치 관리자가 스토어의 종속성을 사용 하므로 앱의 솔루션 구성이 **Master** 또는 **Release** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-121">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="96f47-122">[앱 패키지 만들기](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="96f47-122">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="96f47-123">이 방법을 통해 설치 된 앱은 디지털 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-123">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="96f47-124">앱에 서명 하는 데 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-124">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="96f47-125">[MS 신뢰 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)에서 인증서를 가져올 수 있으며,이 경우 추가 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-125">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="96f47-126">또는 인증서를 장치에 푸시 해야 하지만 본인의 인증서에 서명할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-126">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="96f47-127">[서명 도구를 사용 하 여](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 앱에 서명 하는 방법</span><span class="sxs-lookup"><span data-stu-id="96f47-127">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="96f47-128">인증서 옵션:</span><span class="sxs-lookup"><span data-stu-id="96f47-128">Certificate options:</span></span>** 
- [<span data-ttu-id="96f47-129">MS 신뢰할 수 있는 CA 목록</span><span class="sxs-lookup"><span data-stu-id="96f47-129">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="96f47-130">인증서 배포 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-130">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="96f47-131">[배포 패키지](hololens-provisioning.md) 는 로컬 장치에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-131">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="96f47-132">[장치 구성으로 인증서를 적용](https://docs.microsoft.com/mem/intune/protect/certificates-configure)하는 데 MDM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-132">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="96f47-133">장치 [인증서 관리자](hololens-insider.md#certificate-manager)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-133">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="96f47-134">설치 방법</span><span class="sxs-lookup"><span data-stu-id="96f47-134">Installation method</span></span>

1.  <span data-ttu-id="96f47-135">HoloLens 2 디바이스의 전원이 켜져 있고 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-135">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="96f47-136">PC에서 사용자 지정 앱으로 이동 하 고 yourapp를 yourdevicename\Internal Storage\Downloads.에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-136">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="96f47-137">파일 복사가 완료 되 면 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-137">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="96f47-138">HoloLens 2 장치에서 **시작 메뉴**를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-138">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="96f47-139">다운로드 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-139">Navigate to the Downloads folder.</span></span> <span data-ttu-id="96f47-140">앱의 왼쪽 창에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-140">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="96f47-141">Yourapp 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-141">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="96f47-142">앱 설치 관리자가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-142">The App Installer will launch.</span></span> <span data-ttu-id="96f47-143">**설치** 단추를 선택 하 여 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-143">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="96f47-144">설치가 완료 되 면 설치 된 앱이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-144">The installed app will automatically launch upon the completion of installing.</span></span> 

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="96f47-146">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="96f47-146">Troubleshooting Installs</span></span>
<span data-ttu-id="96f47-147">앱을 설치 하지 못한 경우 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-147">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="96f47-148">앱이 마스터 또는 릴리스 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-148">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="96f47-149">장치가이 기능을 사용할 수 있는 빌드로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-149">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="96f47-150">[인터넷에 연결](hololens-network.md)되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-150">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="96f47-151">[Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-151">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="96f47-152">웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="96f47-152">Web Installer</span></span>

<span data-ttu-id="96f47-153">사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-153">Users can install an app directly from a web server.</span></span> <span data-ttu-id="96f47-154">이를 통해 간편 하 게 다운로드 하 고 설치할 수 있는 앱 설치 관리자가 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-154">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="96f47-155">웹 설치를 설정 하는 방법:</span><span class="sxs-lookup"><span data-stu-id="96f47-155">How to set up web install:</span></span>
1.  <span data-ttu-id="96f47-156">앱이 설치 되도록 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-156">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="96f47-157">[웹 페이지에서이 기능을 사용 하도록 설정 하려면 다음 단계를](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)따르세요.</span><span class="sxs-lookup"><span data-stu-id="96f47-157">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="96f47-158">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="96f47-158">End user experience:</span></span>
1. <span data-ttu-id="96f47-159">사용자가 이전에 위에서 선택한 방법을 사용 하 여 디바이스에 인증서를 받아서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-159">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="96f47-160">사용자가 위의 단계에서 만든 URL을 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-160">User visits the URL created from the step above.</span></span>

<span data-ttu-id="96f47-161">이제 앱이 디바이스에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-161">The app will now install to the device.</span></span> <span data-ttu-id="96f47-162">앱을 찾으려면 **시작 메뉴** 를 열고 **모든 앱** 단추를 선택 하 여 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-162">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="96f47-163">이 설치 방법 문제 해결에 대 한 도움말은 [앱 설치 관리자 문제 해결](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96f47-163">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="96f47-164">업데이트 프로세스가 진행 되는 동안 UI가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-164">UI during the update process is not supported.</span></span> <span data-ttu-id="96f47-165">따라서 [이 페이지](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 및 관련 옵션의 showprompt 옵션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96f47-165">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="96f47-166">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="96f47-166">Sample Apps</span></span>

<span data-ttu-id="96f47-167">샘플 앱을 사용 하 여이 작업을 수행해 보려면 사용 가능한 샘플 중 일부를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="96f47-167">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="96f47-168">MRTK 예제 허브</span><span class="sxs-lookup"><span data-stu-id="96f47-168">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="96f47-169">평면</span><span class="sxs-lookup"><span data-stu-id="96f47-169">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="96f47-170">테스트에 사용할 수 있는 UWP 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="96f47-170">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
