---
title: Windows Defender 응용 프로그램 제어-WDAC
description: Windows Defender 응용 프로그램 컨트롤의 정의 및이를 사용 하 여 HoloLens 혼합 현실 장치를 관리 하는 방법에 대 한 개요입니다.
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309405"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="23180-103">Windows Defender 응용 프로그램 제어-WDAC</span><span class="sxs-lookup"><span data-stu-id="23180-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="23180-104">WDAC를 사용 하면 IT 관리자가 장치의 앱 시작을 차단 하도록 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="23180-105">키오스크 모드와 같은 장치 제한의 방법과는 다릅니다. 사용자는 장치에서 앱을 숨기는 UI를 제공 하지만 여전히 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="23180-106">WDAC가 구현 되는 동안 앱은 모든 앱 목록에 계속 표시 되지만, WDAC는 장치 사용자가 해당 앱 및 프로세스를 시작할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23180-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="23180-107">장치에 둘 이상의 WDAC 정책이 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="23180-108">시스템에 여러 개의 WDAC 정책이 설정 되어 있으면 대부분의 제한 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23180-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="23180-109">최종 사용자가 WDAC에 의해 차단 된 앱을 시작 하려고 하면 HoloLens에서 해당 앱을 시작할 수 없다는 알림이 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="23180-110">다음은 사용자가 Microsoft Intune를 사용 하 [여 HoloLens 2 장치에서 앱을 허용 하거나 차단 하는 데 WDAC 및 Windows PowerShell을 사용](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="23180-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="23180-111">사용자가 첫 번째 예제 단계를 사용 하 여 Windows 10 PC에 설치 된 앱을 검색 하는 경우 결과 범위를 좁히기 위해 몇 번의 시도를 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="23180-112">패키지의 전체 이름을 모르는 경우 ' Add-appxpackage-name \* YourBestGuess '를 몇 번 실행 하 여 찾아야 할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="23180-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="23180-113">그런 다음 이름이 ' $package 1 = Get-AppxPackage-name Actual. PackageName '로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23180-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="23180-114">예를 들어 Microsoft Edge에 대해 다음을 실행 하면 둘 이상의 결과가 반환 되지만 해당 목록에서 필요한 전체 이름이 MicrosoftEdge 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="23180-115">HoloLens 앱에 대 한 패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="23180-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="23180-116">위에 연결 된 가이드에서 newPolicy.xml를 수동으로 편집 하 고 패키지 제품군 이름으로 HoloLens에 설치 된 응용 프로그램에 대 한 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="23180-117">사용자가 사용 하는 데 사용할 수 있는 앱이 있는 경우에는 정책에 추가 하려는 데스크톱 PC가 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="23180-118">다음은 HoloLens 2 장치에 일반적으로 사용 되는 앱과 In-Box 앱의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="23180-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="23180-119">앱 이름</span><span class="sxs-lookup"><span data-stu-id="23180-119">App Name</span></span>                   | <span data-ttu-id="23180-120">패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="23180-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="23180-121">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="23180-121">3D Viewer</span></span>                  | <span data-ttu-id="23180-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="23180-123">앱 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="23180-123">App Installer</span></span>              | <span data-ttu-id="23180-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23180-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="23180-125">일정</span><span class="sxs-lookup"><span data-stu-id="23180-125">Calendar</span></span>                   | <span data-ttu-id="23180-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="23180-127">카메라</span><span class="sxs-lookup"><span data-stu-id="23180-127">Camera</span></span>                     | <span data-ttu-id="23180-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="23180-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="23180-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="23180-129">Cortana</span></span>                    | <span data-ttu-id="23180-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="23180-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="23180-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="23180-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="23180-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="23180-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="23180-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="23180-135">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="23180-135">Feedback Hub</span></span>               | <span data-ttu-id="23180-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="23180-137">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="23180-137">File Explorer</span></span>              | <span data-ttu-id="23180-138">c5e2524a-ea46-4f67 6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="23180-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="23180-139">Mail</span><span class="sxs-lookup"><span data-stu-id="23180-139">Mail</span></span>                       | <span data-ttu-id="23180-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="23180-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="23180-141">Microsoft Store</span></span>            | <span data-ttu-id="23180-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="23180-143">TV & 영상</span><span class="sxs-lookup"><span data-stu-id="23180-143">Movies & TV</span></span>                | <span data-ttu-id="23180-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="23180-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="23180-145">OneDrive</span></span>                   | <span data-ttu-id="23180-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="23180-147">사진</span><span class="sxs-lookup"><span data-stu-id="23180-147">Photos</span></span>                     | <span data-ttu-id="23180-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="23180-149">설정</span><span class="sxs-lookup"><span data-stu-id="23180-149">Settings</span></span>                   | <span data-ttu-id="23180-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="23180-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="23180-151">팁</span><span class="sxs-lookup"><span data-stu-id="23180-151">Tips</span></span>                       | <span data-ttu-id="23180-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="23180-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="23180-153">1-앱 설치 관리자를 차단 하면 Microsoft Store 또는 MDM 솔루션과 같은 다른 원본에서 설치 된 앱이 아닌 앱 설치 관리자 앱만 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23180-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="23180-154">패키지 제품군 이름을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="23180-154">How to find a Package Family Name</span></span>

<span data-ttu-id="23180-155">앱이이 목록에 없는 경우 사용자가 장치 포털을 사용할 수 있습니다 .이 경우 앱이 차단 될 것으로 표시 된 HoloLens 2에 연결 된 PackageRelativeID를 확인 하 고 PackageFamilyName을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23180-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="23180-156">HoloLens 2 장치에 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="23180-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="23180-157">개발자를 위한 설정-업데이트 > & > 업데이트를 열고 **개발자 모드** 를 사용 하도록 설정한 다음 **장치 포털** 을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23180-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="23180-158">자세한 내용은 [장치 포털의 설정 및 사용](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23180-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="23180-159">장치 포털이 연결 되 면 **보기** , **앱** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="23180-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="23180-160">설치 된 앱 패널 내에서 드롭다운을 사용 하 여 설치 된 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23180-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="23180-161">PackageRelativeID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="23180-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="23180-162">전에 앱 문자를 복사 합니다. 이러한 문자는 PackageFamilyName 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23180-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


