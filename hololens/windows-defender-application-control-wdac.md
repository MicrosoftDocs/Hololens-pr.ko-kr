---
title: Windows Defender 응용 프로그램 제어 - WDAC
description: WDAC가 무엇일지와 HoloLens 장치를 관리하는 데 사용하는 방법에 대한 개요입니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252649"
---
# <span data-ttu-id="752a6-103">Windows Defender 응용 프로그램 제어 - WDAC</span><span class="sxs-lookup"><span data-stu-id="752a6-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="752a6-104">WDAC를 사용하면 IT 관리자가 디바이스에서 앱 실행을 차단하도록 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="752a6-105">이는 사용자가 디바이스에서 앱을 숨기지만 계속 실행될 수 있는 UI를 표시하는 키오스크 모드와 같은 장치 제한 메서드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="752a6-106">WDAC가 구현되는 동안 앱은 여전히 모든 앱 목록에 표시되지만 WDAC는 해당 앱 및 프로세스가 장치 사용자가 시작하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="752a6-107">디바이스에 두 개 이상의 WDAC 정책이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="752a6-108">시스템에서 여러 WDAC 정책이 설정되어 있는 경우 가장 제한적인 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="752a6-109">최종 사용자가 WDAC에 의해 차단된 앱을 시작하려고 하면 HoloLens에서 해당 앱을 시작하지 못했다는 알림이 수신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="752a6-110">다음은 [Microsoft Intune에서 HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)장치에서 앱을 허용하거나 차단하기 위해 WDAC 및 Windows PowerShell 방법을 알아보는 사용자를 위한 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="752a6-111">사용자가 첫 번째 예제 단계를 사용하여 Windows 10 PC에 설치된 앱을 검색할 때 결과를 좁히기 위해 몇 가지 시도를 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="752a6-112">패키지의 전체 이름을 모르는 경우 'Get-AppxPackage -name \*YourBestGuess\*'를 몇 번 실행하여 패키지를 찾아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="752a6-113">그런 다음 이름이 '$package 1 = Get-AppxPackage -name Actual.PackageName'으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="752a6-114">예를 들어 Microsoft Edge에 대해 다음을 실행하면 결과가 두 개 이상 반환되지만 해당 목록에서 필요한 전체 이름이 Microsoft.MicrosoftEdge임이 식별될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="752a6-115">HoloLens의 앱에 대한 패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="752a6-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="752a6-116">위에 연결된 가이드에서 수동으로 패키지를 편집하고 newPolicy.xml 패밀리 이름으로 HoloLens에만 설치된 응용 프로그램에 대한 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="752a6-117">경우에 따라 정책에 추가하고자 하는 데스크톱 PC에 없는 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="752a6-118">다음은 HoloLens 2 장치에 대해 일반적으로 In-Box 앱의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="752a6-119">앱 이름</span><span class="sxs-lookup"><span data-stu-id="752a6-119">App Name</span></span>                   | <span data-ttu-id="752a6-120">패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="752a6-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="752a6-121">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="752a6-121">3D Viewer</span></span>                  | <span data-ttu-id="752a6-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="752a6-123">앱 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="752a6-123">App Installer</span></span>              | <span data-ttu-id="752a6-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="752a6-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="752a6-125">Calendar</span><span class="sxs-lookup"><span data-stu-id="752a6-125">Calendar</span></span>                   | <span data-ttu-id="752a6-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="752a6-127">카메라</span><span class="sxs-lookup"><span data-stu-id="752a6-127">Camera</span></span>                     | <span data-ttu-id="752a6-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="752a6-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="752a6-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="752a6-129">Cortana</span></span>                    | <span data-ttu-id="752a6-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="752a6-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="752a6-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="752a6-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="752a6-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="752a6-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="752a6-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="752a6-135">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="752a6-135">Feedback Hub</span></span>               | <span data-ttu-id="752a6-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="752a6-137">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="752a6-137">File Explorer</span></span>              | <span data-ttu-id="752a6-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="752a6-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="752a6-139">Mail</span><span class="sxs-lookup"><span data-stu-id="752a6-139">Mail</span></span>                       | <span data-ttu-id="752a6-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="752a6-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="752a6-141">Microsoft Store</span></span>            | <span data-ttu-id="752a6-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="752a6-143">영화 및 TV</span><span class="sxs-lookup"><span data-stu-id="752a6-143">Movies & TV</span></span>                | <span data-ttu-id="752a6-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="752a6-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="752a6-145">OneDrive</span></span>                   | <span data-ttu-id="752a6-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="752a6-147">사진</span><span class="sxs-lookup"><span data-stu-id="752a6-147">Photos</span></span>                     | <span data-ttu-id="752a6-148">Microsoft.Windows.사진_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="752a6-149">설정</span><span class="sxs-lookup"><span data-stu-id="752a6-149">Settings</span></span>                   | <span data-ttu-id="752a6-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="752a6-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="752a6-151">팁</span><span class="sxs-lookup"><span data-stu-id="752a6-151">Tips</span></span>                       | <span data-ttu-id="752a6-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="752a6-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="752a6-153">1 - 앱 설치 관리자를 차단하면 앱 설치 관리자 앱만 차단하고 Microsoft Store 또는 MDM 솔루션과 같은 다른 소스에서 설치된 앱은 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="752a6-154">패키지 패밀리 이름을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="752a6-154">How to find a Package Family Name</span></span>

<span data-ttu-id="752a6-155">앱이 목록에 없는 경우 사용자는 차단하고자 하는 앱을 설치한 HoloLens 2에 연결된 Device Portal을 사용하여 PackageRelativeID를 확인한 다음 해당 장치에서 PackageFamilyName을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="752a6-156">HoloLens 2 장치에 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="752a6-157">Open Settings -> Updates & Security ->, and enable **Developer mode** and then **Device portal.**</span><span class="sxs-lookup"><span data-stu-id="752a6-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="752a6-158">자세한 내용은 여기에서 디바이스 포털의 설정 및 사용에 대해 [자세히 읽어 읽습니다.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="752a6-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="752a6-159">디바이스 포털이 연결되면 **Views로** 이동한 다음 **앱으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="752a6-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="752a6-160">설치된 앱 패널 내에서 드롭다운을 사용하여 설치된 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="752a6-161">PackageRelativeID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="752a6-162">!, 이러한 문자는 PackageFamilyName 앞에 앱 문자를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="752a6-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


