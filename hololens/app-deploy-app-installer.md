---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 로드 하 고 설치 하는 방법
description: 앱 설치 관리자를 사용 하 여 앱을 설치 하 고 문제를 해결 하 고 UI를 통해 앱을 로드 하 고 설치 하는 방법을 알아봅니다
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
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924131"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="6679a-104">앱 설치 관리자를 통해 HoloLens 2에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="6679a-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="6679a-105">이 기능은 [Windows Holographic 버전 20H2 – 12 월 2020 업데이트](hololens-release-notes.md)에서 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="6679a-106">이 기능을 사용 하도록 장치가 [업데이트](hololens-update-hololens.md) 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="6679a-107">HoloLens 2 장치에 **더욱 원활 하 게 응용 프로그램을 설치할 수 있도록 하는 새로운 기능 (앱 설치 관리자)이 추가** 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="6679a-108">이 기능은 **기본적으로 관리 되지 않는 장치에 대해 설정** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="6679a-109">엔터프라이즈 중단을 방지 하기 위해 지금은 **관리 되는 장치에 대해** 앱 설치 관리자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="6679a-110">다음 조건 중 **하나** 에 해당 하는 경우 장치는 "관리" 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="6679a-111">MDM [등록](hololens-enroll-mdm.md) 됨</span><span class="sxs-lookup"><span data-stu-id="6679a-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="6679a-112">[프로 비전 패키지](hololens-provisioning.md) 를 사용 하 여 구성</span><span class="sxs-lookup"><span data-stu-id="6679a-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="6679a-113">사용자 [id](hololens-identity.md) 는 Azure AD입니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="6679a-114">이제 개발자 모드를 사용 하도록 설정 하거나 장치 포털을 사용 하지 않고도 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="6679a-115">장치에 Appx 번들을 다운로드 하 여 (USB를 통해 또는 Microsoft Edge를 통해) 파일 탐색기에서 Appx 번들로 이동 하 여 설치를 시작 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="6679a-116">또는 [웹 페이지에서 설치를 시작](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="6679a-117">MDM의 LOB 앱 배포 기능을 사용 하 여 Microsoft Store 또는 테스트용으로 로드에서 설치 하는 앱과 마찬가지로 서명 [도구](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 를 사용 하 여 앱을 디지털 서명 해야 하며, [서명 하는 데 사용 되는 인증서](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 는 앱을 배포 하기 전에 HoloLens 장치에서 신뢰할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="6679a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6679a-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="6679a-119">장치:</span><span class="sxs-lookup"><span data-stu-id="6679a-119">For your devices:</span></span>

<span data-ttu-id="6679a-120">이 기능은 현재 HoloLens 2 장치에 대 한 Windows Holographic 20H2 빌드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="6679a-121">이 방법을 사용 하는 모든 장치가 [업데이트](hololens-update-hololens.md)되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="6679a-122">앱의 경우:</span><span class="sxs-lookup"><span data-stu-id="6679a-122">For your apps:</span></span>

<span data-ttu-id="6679a-123">앱 설치 관리자는 저장소의 종속성을 사용할 수 있으므로 앱의 솔루션 구성은 **마스터** 또는 **릴리스** 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="6679a-124">[앱 패키지 만들기](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6679a-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="6679a-125">이 메서드를 통해 설치 되는 앱은 디지털 서명 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="6679a-126">인증서를 사용 하 여 앱에 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="6679a-127">[MS 신뢰할 수 있는 CA 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)에서 인증서를 가져올 수 있으며,이 경우 추가 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="6679a-128">또는 자체 인증서를 서명할 수 있지만 인증서를 장치에 푸시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="6679a-129">[서명 도구를 사용 하 여](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 앱에 서명 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="6679a-130">**인증서 옵션:**</span><span class="sxs-lookup"><span data-stu-id="6679a-130">**Certificate options:**</span></span>

- [<span data-ttu-id="6679a-131">MS 신뢰할 수 있는 CA 목록</span><span class="sxs-lookup"><span data-stu-id="6679a-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="6679a-132">**인증서 배포 방법을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6679a-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="6679a-133">[프로 비전 패키지](hololens-provisioning.md) 를 로컬 장치에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="6679a-134">MDM은 [장치 구성으로 인증서를 적용](https://docs.microsoft.com/mem/intune/protect/certificates-configure)하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="6679a-135">장치 [인증서 관리자](certificate-manager.md)에서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="6679a-136">설치 방법</span><span class="sxs-lookup"><span data-stu-id="6679a-136">Installation method</span></span>

1. <span data-ttu-id="6679a-137">장치가 관리 되는 것으로 간주 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="6679a-138">HoloLens 2 장치의 전원이 켜져 있고 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="6679a-139">PC에서 사용자 지정 앱으로 이동 하 고 yourapp을 yourdevicename\Internal Storage\downloadss에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="6679a-140">파일 복사를 완료 한 후 장치를 분리 하 고 나중에 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="6679a-141">HoloLens 2 장치에서 **시작 메뉴** 를 열고 **모든 앱** 을 선택 하 고 **파일 탐색기** 앱을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="6679a-142">다운로드 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="6679a-143">앱의 왼쪽 패널에서 **이 장치** 를 먼저 선택한 다음 다운로드로 이동 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="6679a-144">Yourapp 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="6679a-145">앱 설치 관리자가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-145">The App Installer will launch.</span></span> <span data-ttu-id="6679a-146">**설치** 단추를 선택 하 여 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="6679a-147">설치가 완료 되 면 설치 된 앱이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-147">The installed app will automatically launch upon the completion of installing.</span></span>

![App Installer를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="6679a-149">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6679a-149">Troubleshooting Installs</span></span>

<span data-ttu-id="6679a-150">앱을 설치 하지 못한 경우 다음을 확인 하 여 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="6679a-151">앱은 마스터 또는 릴리스 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="6679a-152">장치가이 기능을 사용할 수 있는 빌드로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="6679a-153">사용자가 [인터넷에 연결](hololens-network.md)되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="6679a-154">[Microsoft Store에 대 한 끝점이](hololens-offline.md) 올바르게 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="6679a-155">웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6679a-155">Web Installer</span></span>

<span data-ttu-id="6679a-156">사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="6679a-157">이 흐름은 간편한 다운로드 및 설치 배포 방법과 함께 앱 설치 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="6679a-158">웹 설치를 설정 하는 방법:</span><span class="sxs-lookup"><span data-stu-id="6679a-158">How to set up web install:</span></span>

1. <span data-ttu-id="6679a-159">앱이 설치 되도록 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="6679a-160">[웹 페이지에서 설치를 사용 하도록 설정 하려면 다음 단계를](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="6679a-161">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="6679a-161">End user experience:</span></span>

1. <span data-ttu-id="6679a-162">사용자가 이전에 선택한 방법을 사용 하 여 장치에 인증서를 받아서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="6679a-163">사용자가 위 단계에서 만든 URL을 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="6679a-164">이제 앱이 장치에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-164">The app will now install to the device.</span></span> <span data-ttu-id="6679a-165">앱을 찾으려면 **시작 메뉴** 를 열고 **모든 앱** 단추를 선택 하 여 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="6679a-166">앱 설치 관리자 설치 방법 문제를 해결 하는 방법에 대 한 자세한 내용은 [앱 설치 관리자 문제 해결](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6679a-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="6679a-167">업데이트 프로세스 중에 UI가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-167">UI during the update process is not supported.</span></span> <span data-ttu-id="6679a-168">따라서 [이 페이지](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 의 showprompt 옵션과 관련 옵션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6679a-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="6679a-169">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="6679a-169">Sample Apps</span></span>

<span data-ttu-id="6679a-170">사용 가능한 샘플 앱 중 하나를 사용 하 여 앱 설치 관리자를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6679a-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="6679a-171">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="6679a-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
