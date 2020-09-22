---
title: 웹 설치 관리자를 통해 앱을 설치 하는 방법
description: 앱 설치 관리자를 위해 웹 설치 관리자를 통해 앱 설치
keywords: 앱 관리, 앱, hololens, 앱 설치 관리자, 웹 설치
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027481"
---
# <span data-ttu-id="d095e-104">웹 페이지에서 앱 설치</span><span class="sxs-lookup"><span data-stu-id="d095e-104">Installing apps from a web page</span></span>

<span data-ttu-id="d095e-105">사용자는 웹 서버에서 직접 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="d095e-106">이를 통해 간편 하 게 다운로드 하 고 설치할 수 있는 앱 설치 관리자가 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d095e-107">이 기능은 현재 Windows 참가자 빌드 19041.1366 +에만 avalible 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="d095e-108">[Windows 참가자 빌드에 등록 하는 방법에 대해 자세히 알아보세요](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="d095e-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="d095e-109">설정 하는 방법:</span><span class="sxs-lookup"><span data-stu-id="d095e-109">How to set this up:</span></span>
1.  <span data-ttu-id="d095e-110">앱이 설치 되도록 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="d095e-111">[웹 페이지에서이 기능을 사용 하도록 설정 하려면 다음 단계를](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)따르세요.</span><span class="sxs-lookup"><span data-stu-id="d095e-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="d095e-112">인증서 배포 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="d095e-113">[배포 패키지](hololens-provisioning.md) 는 로컬 장치에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="d095e-114">[장치 구성으로 인증서를 적용](https://docs.microsoft.com/mem/intune/protect/certificates-configure)하는 데 MDM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="d095e-115">장치 [인증서 관리자](hololens-insider.md#certificate-manager)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="d095e-116">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="d095e-116">End User Experience:</span></span>
1.  <span data-ttu-id="d095e-117">사용자가 이전에 위에서 선택한 방법을 사용 하 여 디바이스에 인증서를 받아서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="d095e-118">사용자가 위의 단계에서 만든 URL을 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="d095e-119">이제 앱이 디바이스에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-119">The app will now install to the device.</span></span> <span data-ttu-id="d095e-120">앱을 찾으려면 **시작 메뉴** 를 열고 **모든 앱** 단추를 선택 하 여 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="d095e-121">이 설치 방법 문제 해결에 대 한 도움말은 [앱 설치 관리자 문제 해결](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d095e-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="d095e-122">업데이트 프로세스가 진행 되는 동안 UI가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-122">UI during the update process is not supported.</span></span> <span data-ttu-id="d095e-123">따라서 [이 페이지](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 및 관련 옵션의 showprompt 옵션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d095e-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>