---
title: HoloLens 2 앱 설치 관리자 통해 앱을 사이드로드하고 설치하는 방법
description: 앱 설치 관리자를 사용하여 앱을 설치하고 문제를 해결하는 방법과 UI를 통해 앱을 테스트용으로 로드 및 설치하는 방법을 알아봅니다.
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635588"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="62674-104">앱 설치 관리자 통해 HoloLens 2 앱 설치</span><span class="sxs-lookup"><span data-stu-id="62674-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="62674-105">이 기능은 Windows [Holographic 버전 20H2 – 2020년 12월 업데이트에서](hololens-release-notes.md)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="62674-106">이 기능을 사용하도록 디바이스가 [업데이트되었는지](hololens-update-hololens.md) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="62674-107">HoloLens 2 디바이스에서 **애플리케이션을 더 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)을 추가했습니다.**</span><span class="sxs-lookup"><span data-stu-id="62674-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="62674-108">이 기능은 **관리되지 않는 디바이스 에 대해 기본적으로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="62674-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="62674-109">엔터프라이즈의 중단을 방지하기 위해 현재 관리 디바이스에 앱 설치 **관리자를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="62674-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="62674-110">다음 **중** 한 가지가 true인 경우 디바이스는 "관리"로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="62674-111">MDM [등록](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="62674-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="62674-112">[프로비전 패키지로](hololens-provisioning.md) 구성됨</span><span class="sxs-lookup"><span data-stu-id="62674-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="62674-113">사용자 [ID는](hololens-identity.md) Azure AD입니다.</span><span class="sxs-lookup"><span data-stu-id="62674-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="62674-114">이제 개발자 모드를 사용하도록 설정하거나 장치 포털 사용하지 않고도 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="62674-115">USB를 통해 또는 Microsoft Edge 통해 Appx 번들을 디바이스에 다운로드하고 파일 탐색기 Appx 번들로 이동하여 설치를 시작하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="62674-116">또는 [웹 페이지 에서 설치를 시작합니다.](/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="62674-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="62674-117">MDM의 LOB 앱 배포 기능을 사용하여 Microsoft Store 또는 사이드로드에서 설치하는 앱과 마찬가지로, 앱은 [서명 도구로](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 디지털 서명되어야 [하며, 서명하는 데 사용되는 인증서를](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 디바이스에서 신뢰해야만 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="62674-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62674-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="62674-119">디바이스의 경우:</span><span class="sxs-lookup"><span data-stu-id="62674-119">For your devices:</span></span>

<span data-ttu-id="62674-120">이 기능은 현재 HoloLens 2 디바이스용 Windows Holographic 20H2 빌드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="62674-121">이 방법을 사용하는 모든 디바이스가 [업데이트되었는지](hololens-update-hololens.md)확인합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="62674-122">앱의 경우:</span><span class="sxs-lookup"><span data-stu-id="62674-122">For your apps:</span></span>

<span data-ttu-id="62674-123">앱의 솔루션 구성은 **마스터** 또는 **릴리스여야** 합니다. 앱 설치 관리자 저장소의 dependencies를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="62674-124">앱 패키지 만들기에 대해 자세히 [참조하세요.](/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="62674-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="62674-125">이 방법을 통해 설치된 앱은 디지털 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="62674-126">인증서를 사용하여 앱에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="62674-127">MS 신뢰할 수 있는 [CA 목록에서](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)인증서를 얻을 수 있습니다. 이 경우 추가 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="62674-128">또는 사용자 고유의 인증서에 서명할 수 있습니다. 그러나 해당 인증서를 디바이스에 푸시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="62674-129">서명 도구를 [사용하여 앱에 서명하는](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 방법</span><span class="sxs-lookup"><span data-stu-id="62674-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="62674-130">**인증서 옵션:**</span><span class="sxs-lookup"><span data-stu-id="62674-130">**Certificate options:**</span></span>

- [<span data-ttu-id="62674-131">MS 신뢰할 수 있는 CA 목록</span><span class="sxs-lookup"><span data-stu-id="62674-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="62674-132">**인증서 배포 방법을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="62674-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="62674-133">[프로비전 패키지는](hololens-provisioning.md) 로컬 디바이스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="62674-134">MDM을 사용하여 [디바이스 구성으로 인증서를 적용할](/mem/intune/protect/certificates-configure)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="62674-135">디바이스 인증서 [관리자](certificate-manager.md)에서 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="62674-136">설치 방법</span><span class="sxs-lookup"><span data-stu-id="62674-136">Installation method</span></span>

1. <span data-ttu-id="62674-137">디바이스가 관리되는 것으로 간주되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="62674-138">HoloLens 2 디바이스의 전원이 켜지고 로그인했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="62674-139">PC에서 사용자 지정 앱으로 이동하고 yourapp.appxbundle을 yourdevicename\Internal Storage\Downloads에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="62674-140">파일 복사를 완료한 후 디바이스의 연결을 끊고 나중에 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="62674-141">HoloLens 2 디바이스에서 **시작 메뉴를** 열고 **모든 앱** 선택하고 **파일 탐색기** 앱을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="62674-142">다운로드 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="62674-143">앱의 왼쪽 패널에서 **이 디바이스를** 먼저 선택한 다음, 다운로드로 이동해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="62674-144">yourapp.appxbundle 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="62674-145">앱 설치 관리자 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-145">The App Installer will launch.</span></span> <span data-ttu-id="62674-146">**설치** 단추를 선택하여 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="62674-147">설치된 앱은 설치가 완료되면 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-147">The installed app will automatically launch upon the completion of installing.</span></span>

![앱 설치 관리자 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="62674-149">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="62674-149">Troubleshooting Installs</span></span>

<span data-ttu-id="62674-150">앱을 설치하지 못한 경우 다음을 확인하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="62674-151">앱이 마스터 또는 릴리스 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="62674-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="62674-152">디바이스가 이 기능을 사용할 수 있는 빌드로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="62674-153">인터넷에 [연결되어](hololens-network.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="62674-154">[Microsoft Store 대한 엔드포인트가](hololens-offline.md) 올바르게 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="62674-155">웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="62674-155">Web Installer</span></span>

<span data-ttu-id="62674-156">사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="62674-157">이 흐름은 쉬운 다운로드 및 설치 배포 방법과 결합된 앱 설치 관리자 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="62674-158">웹 설치를 설정하는 방법:</span><span class="sxs-lookup"><span data-stu-id="62674-158">How to set up web install:</span></span>

1. <span data-ttu-id="62674-159">앱을 설치하도록 올바르게 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="62674-160">웹 [페이지에서 설치를 사용하도록 설정하려면 다음 단계를 수행합니다.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="62674-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="62674-161">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="62674-161">End user experience:</span></span>

1. <span data-ttu-id="62674-162">사용자는 위에서 선택한 방법을 사용하여 인증서를 받아 디바이스에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="62674-163">사용자는 위의 단계에서 만든 URL을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="62674-164">이제 앱이 디바이스에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="62674-164">The app will now install to the device.</span></span> <span data-ttu-id="62674-165">앱을 찾으려면 **시작 메뉴** 열고 **모든 앱** 단추를 선택하여 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="62674-166">앱 설치 관리자 설치 방법 문제 해결에 대한 자세한 도움말은 앱 설치 [관리자 문제 해결을](/windows/msix/app-installer/troubleshoot-appinstaller-issues)참조합니다.</span><span class="sxs-lookup"><span data-stu-id="62674-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="62674-167">업데이트 프로세스 중 UI는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-167">UI during the update process is not supported.</span></span> <span data-ttu-id="62674-168">[따라서 이 페이지의](/windows/msix/app-installer/update-settings) ShowPrompt 옵션 및 관련 옵션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62674-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="62674-169">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="62674-169">Sample Apps</span></span>

<span data-ttu-id="62674-170">사용 가능한 샘플 앱 중 하나를 앱 설치 관리자 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="62674-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="62674-171">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="62674-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
