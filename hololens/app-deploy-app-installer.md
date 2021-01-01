---
title: HoloLens 2 앱 설치 관리자를 통해 앱을 테스트용 로드 및 설치하는 방법
description: UI를 통해 슬라이드 로드 및 앱 설치
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
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253095"
---
# <span data-ttu-id="af4dd-104">앱 설치 관리자를 통해 HoloLens 2에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="af4dd-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="af4dd-105">**HoloLens** 2 장치에 응용 프로그램을 보다 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)을 추가하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="af4dd-106">이 기능은 관리되지 않는 장치에 대해 기본적으로 **설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="af4dd-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="af4dd-107">엔터프라이즈 중단을 방지하기 위해 현재 관리되는 디바이스에서는 앱 설치 관리자를 사용할 **수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="af4dd-108">이 기능은 Windows [Holographic 버전 20H2 – 2020년 12월 업데이트에서 사용할 수 있습니다.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="af4dd-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="af4dd-109">이 기능을 [사용하기 위해](hololens-update-hololens.md) 장치가 업데이트되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="af4dd-110">**HoloLens** 2 장치에 응용 프로그램을 보다 원활하게 설치할 수 있도록 새로운 기능(앱 설치 관리자)이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="af4dd-111">이 기능은 관리되지 않는 장치에 대해 기본적으로 **설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="af4dd-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="af4dd-112">엔터프라이즈 중단을 방지하기 위해 현재 관리되는 디바이스에서는 앱 설치 관리자를 사용할 **수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="af4dd-113">다음 중 한 가지가 \*\*\*\* 참이면 디바이스가 "관리"되는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="af4dd-114">MDM [등록](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="af4dd-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="af4dd-115">프로비저닝 [패키지로 구성](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="af4dd-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="af4dd-116">사용자 [ID가](hololens-identity.md) Azure AD입니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="af4dd-117">이제 개발자 모드를 사용하도록 설정하거나 디바이스 포털을 사용하지 않고도 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="af4dd-118">USB를 통해 또는 Microsoft Edge를 통해 Appx 번들을 장치에 다운로드하고 파일 탐색기에서 Appx 번들로 이동하여 설치를 시작하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="af4dd-119">또는 웹 [페이지에서 설치를 시작하십시오.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="af4dd-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="af4dd-120">Microsoft Store에서 설치하거나 MDM의 LOB 앱 배포 기능을 사용하여 사이드로드하는 앱과 마찬가지로 앱은 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 서명 도구를 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 사용하여 디지털 서명해야 합니다. 서명에 사용되는 인증서를 HoloLens 장치에서 신뢰해야 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="af4dd-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af4dd-121">Requirements</span></span>

### <span data-ttu-id="af4dd-122">디바이스의 경우:</span><span class="sxs-lookup"><span data-stu-id="af4dd-122">For your devices:</span></span>

 <span data-ttu-id="af4dd-123">기능은 현재 HoloLens 2 디바이스용 Windows Holographic 20H2 빌드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="af4dd-124">이 메서드를 사용하는 모든 장치가 [업데이트되도록 합니다.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="af4dd-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="af4dd-125">앱의 경우:</span><span class="sxs-lookup"><span data-stu-id="af4dd-125">For your apps:</span></span> 
<span data-ttu-id="af4dd-126">앱 설치 관리자에서 스토어의 \*\*\*\* 종속성에 따라 앱의 솔루션 구성이 마스터 또는 릴리스가 되어야 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="af4dd-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="af4dd-127">앱 패키지 [만들기에 대한 자세한 내용은 다음을 참조하세요.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="af4dd-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="af4dd-128">이 방법을 통해 설치된 앱은 디지털 서명을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="af4dd-129">인증서를 사용하여 앱에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="af4dd-130">MS 신뢰할 수 있는 [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)목록에서 인증서를 얻을 수 있습니다. 이 경우 추가 작업을 수행하지 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="af4dd-131">또는 인증서를 장치에 푸시해야 하는 자체 인증서에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="af4dd-132">서명 도구를 사용하여 [앱에 서명하는 방법](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="af4dd-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="af4dd-133">인증서 옵션:</span><span class="sxs-lookup"><span data-stu-id="af4dd-133">Certificate options:</span></span>**

- [<span data-ttu-id="af4dd-134">MS 신뢰할 수 있는 CA 목록</span><span class="sxs-lookup"><span data-stu-id="af4dd-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="af4dd-135">인증서 배포 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="af4dd-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="af4dd-136">[프로비저닝 패키지는](hololens-provisioning.md) 로컬 장치에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="af4dd-137">MDM을 사용하여 장치 구성을 사용하여 [인증서를 적용할 수 있습니다.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="af4dd-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="af4dd-138">디바이스 인증서 [관리자를 사용합니다.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="af4dd-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="af4dd-139">설치 방법</span><span class="sxs-lookup"><span data-stu-id="af4dd-139">Installation method</span></span>

1. <span data-ttu-id="af4dd-140">장치가 관리되는 것으로 간주되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="af4dd-141">HoloLens 2 디바이스가 전원이 설정 및 로그인된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="af4dd-142">PC에서 사용자 지정 앱으로 이동하고app.appxbundle을devicename\Internal Storage\Downloads에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="af4dd-143">파일 복사를 마친 후 장치 연결을 끊고 나중에 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="af4dd-144">HoloLens 2 장치에서 시작 메뉴를 열고 **모든**앱을 **선택하고** 파일 탐색기 **앱을 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="af4dd-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="af4dd-145">다운로드 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="af4dd-146">앱의 왼쪽 패널에서 이 디바이스를 \*\*\*\* 먼저 선택한 다음 다운로드로 이동해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="af4dd-147">yourapp.appxbundle 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="af4dd-148">앱 설치 관리자가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-148">The App Installer will launch.</span></span> <span data-ttu-id="af4dd-149">설치 **단추를** 선택하여 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="af4dd-150">설치가 완료되면 설치된 앱이 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-150">The installed app will automatically launch upon the completion of installing.</span></span>

![앱 설치 관리자를 통해 MRTK 예제 설치](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="af4dd-152">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="af4dd-152">Troubleshooting Installs</span></span>

<span data-ttu-id="af4dd-153">앱이 설치에 실패한 경우 다음을 확인하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="af4dd-154">앱은 마스터 또는 릴리스 빌드입니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="af4dd-155">디바이스가 이 기능을 사용할 수 있는 빌드로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="af4dd-156">인터넷에 [연결되어 있습니다.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="af4dd-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="af4dd-157">[Microsoft Store에 대한 끝점이](hololens-offline.md) 올바르게 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="af4dd-158">웹 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="af4dd-158">Web Installer</span></span>

<span data-ttu-id="af4dd-159">사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="af4dd-160">이 흐름은 간편한 다운로드 및 설치 배포 방법과 결합된 앱 설치 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="af4dd-161">웹 설치를 설정하는 방법:</span><span class="sxs-lookup"><span data-stu-id="af4dd-161">How to set up web install:</span></span>

1. <span data-ttu-id="af4dd-162">앱이 설치되도록 올바르게 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="af4dd-163">웹 페이지에서 [설치를 사용하도록 설정하려면 다음 단계를 수행합니다.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="af4dd-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="af4dd-164">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="af4dd-164">End user experience:</span></span>

1. <span data-ttu-id="af4dd-165">사용자가 위에서 선택한 방법을 사용하여 인증서를 받아 장치에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="af4dd-166">사용자가 위의 단계에서 만든 URL을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="af4dd-167">이제 앱이 장치에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-167">The app will now install to the device.</span></span> <span data-ttu-id="af4dd-168">앱을 찾으하려면 시작 \*\*\*\* 메뉴를 열고 앱 **찾기를** 위해 모든 앱 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="af4dd-169">앱 설치 관리자 설치 방법 문제 해결에 대한 자세한 도움말은 앱 설치 관리자 [문제 해결을 방문하세요.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="af4dd-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="af4dd-170">업데이트 프로세스 중 UI는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af4dd-170">UI during the update process is not supported.</span></span> <span data-ttu-id="af4dd-171">따라서 이 페이지의 ShowPrompt 옵션 및 관련 옵션은 지원되지 않습니다. [](https://docs.microsoft.com/windows/msix/app-installer/update-settings)</span><span class="sxs-lookup"><span data-stu-id="af4dd-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="af4dd-172">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="af4dd-172">Sample Apps</span></span>

<span data-ttu-id="af4dd-173">일부 샘플 앱에서 앱 설치 관리자를 시도하려면 사용 가능한 샘플 중 일부를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="af4dd-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="af4dd-174">MRTK 예제 허브</span><span class="sxs-lookup"><span data-stu-id="af4dd-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="af4dd-175">표면</span><span class="sxs-lookup"><span data-stu-id="af4dd-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="af4dd-176">테스트에 사용할 수 있는 UWP 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="af4dd-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
