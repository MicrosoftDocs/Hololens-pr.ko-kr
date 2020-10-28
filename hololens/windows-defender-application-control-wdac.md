---
title: Windows Defender Application Control
description: WDAC에 대 한 개요와 HoloLens 장치를 관리 하는 데 사용 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135576"
---
# <span data-ttu-id="e493b-103">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="e493b-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="e493b-104">WDAC는 IT 관리자가 장치에서 앱의 실행을 차단 하도록 장치를 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="e493b-105">이 방법은 사용자에 게 장치에서 앱을 숨기는 UI가 표시 되지만 계속 실행할 수 있는 키오스크 모드와 같은 장치 제한의 방법과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="e493b-106">WDAC가 구현 되는 동안에도 모든 앱 목록에 앱이 표시 되지만, WDAC는 해당 앱과 프로세스를 디바이스 사용자가 시작할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="e493b-107">최종 사용자가 WDAC에 의해 차단 된 앱을 시작 하려고 하면 HoloLens에서 해당 앱을 시작할 수 없다는 알림을 받지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="e493b-108">다음은 [Windows Intune을 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단 하는 데 WDAC 및 Windows PowerShell을 사용](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법을 배우는 사용자를 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="e493b-109">사용자가 첫 번째 예제 단계를 사용 하 여 Windows 10 PC에 설치 된 앱을 검색 하는 경우 결과 범위를 좁히는 몇 가지 시도를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="e493b-110">패키지의 전체 이름을 모르는 경우 검색 하려면 ' Add-appxpackage-name \ \* YourBestGuess \ \* '을 몇 번 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="e493b-111">그런 다음 이름 실행 ' $package 1 = Get-AppxPackage-name PackageName '</span><span class="sxs-lookup"><span data-stu-id="e493b-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="e493b-112">예를 들어 Edge에 대해 다음을 실행 하면 두 개 이상의 결과가 반환 되지만 해당 목록에서 필요한 전체 이름은 Microsoft MicrosoftEdge입니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="e493b-113">HoloLens에서 앱에 대 한 패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="e493b-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="e493b-114">위에 링크 된 가이드에서 newPolicy.xml 수동으로 편집 하 고 패키지 패밀리 이름을 사용 하 여 HoloLens에 설치 된 응용 프로그램에 대 한 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="e493b-115">경우에 따라 정책에 추가 하려는 데스크톱 PC에서 사용 하지 않는 앱이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="e493b-116">다음은 HoloLens 2 장치용으로 자주 사용 되는 앱과 In-Box 하는 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="e493b-117">앱 이름</span><span class="sxs-lookup"><span data-stu-id="e493b-117">App Name</span></span>                   | <span data-ttu-id="e493b-118">패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="e493b-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="e493b-119">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="e493b-119">3D Viewer</span></span>                  | <span data-ttu-id="e493b-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="e493b-121">앱 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="e493b-121">App Installer</span></span>              | <span data-ttu-id="e493b-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="e493b-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="e493b-123">Calendar</span><span class="sxs-lookup"><span data-stu-id="e493b-123">Calendar</span></span>                   | <span data-ttu-id="e493b-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="e493b-125">카메라</span><span class="sxs-lookup"><span data-stu-id="e493b-125">Camera</span></span>                     | <span data-ttu-id="e493b-126">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e493b-126">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="e493b-127">Cortana</span><span class="sxs-lookup"><span data-stu-id="e493b-127">Cortana</span></span>                    | <span data-ttu-id="e493b-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="e493b-129">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="e493b-129">Dynamics 365 Guides</span></span>        | <span data-ttu-id="e493b-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="e493b-131">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e493b-131">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="e493b-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="e493b-133">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="e493b-133">Feedback Hub</span></span>               | <span data-ttu-id="e493b-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="e493b-135">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="e493b-135">File Explorer</span></span>              | <span data-ttu-id="e493b-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e493b-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="e493b-137">Mail</span><span class="sxs-lookup"><span data-stu-id="e493b-137">Mail</span></span>                       | <span data-ttu-id="e493b-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="e493b-139">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e493b-139">Microsoft Store</span></span>            | <span data-ttu-id="e493b-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="e493b-141">영화 및 TV</span><span class="sxs-lookup"><span data-stu-id="e493b-141">Movies & TV</span></span>                | <span data-ttu-id="e493b-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="e493b-143">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e493b-143">OneDrive</span></span>                   | <span data-ttu-id="e493b-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="e493b-145">사진</span><span class="sxs-lookup"><span data-stu-id="e493b-145">Photos</span></span>                     | <span data-ttu-id="e493b-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="e493b-147">설정</span><span class="sxs-lookup"><span data-stu-id="e493b-147">Settings</span></span>                   | <span data-ttu-id="e493b-148">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e493b-148">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="e493b-149">팁</span><span class="sxs-lookup"><span data-stu-id="e493b-149">Tips</span></span>                       | <span data-ttu-id="e493b-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e493b-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="e493b-151">1-차단 앱 설치 관리자는 앱 설치 관리자 앱만 차단 하 고 Microsoft Store 또는 MDM 솔루션 등의 다른 원본에서 설치 된 앱은 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-151">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="e493b-152">패키지 패밀리 이름을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="e493b-152">How to find a Package Family Name</span></span>

<span data-ttu-id="e493b-153">앱이이 목록에 없는 경우 사용자는 디바이스 포털을 사용 하 여 앱을 차단 하기 위해 설치 된 HoloLens 2에 연결 하 고 PackageRelativeID를 확인 하 고 PackageFamilyName를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-153">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="e493b-154">HoloLens 2 장치에 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-154">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="e493b-155">> 설정-개발자를 위해 업데이트 & Securtiy-> 하 고 **개발자 모드** 와 **장치 포털**을 차례로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-155">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="e493b-156">자세한 내용은 [여기에 디바이스 포털의 설정 및 사용](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e493b-156">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="e493b-157">디바이스 포털이 연결 되 면 **보기로** 이동한 다음 **앱**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-157">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="e493b-158">설치 된 앱 패널 내에서 드롭다운을 사용 하 여 설치 된 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-158">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="e493b-159">PackageRelativeID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-159">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="e493b-160">! 앞에 앱 문자를 복사 하면 여러분의 PackageFamilyName 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-160">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

## <span data-ttu-id="e493b-161">샘플 차단 앱 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="e493b-161">Sample - Blocking App Installer</span></span>

<span data-ttu-id="e493b-162">예를 들어 [App Installer](app-deploy-app-installer.md) 앱을 차단 하 고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-162">As an example you may wish to block the [App Installer](app-deploy-app-installer.md) app.</span></span> <span data-ttu-id="e493b-163">이 예제에 대 한 샘플 코드도 몇 가지 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-163">We have included some sample code for this example.</span></span> <span data-ttu-id="e493b-164">[이 예제에 대 한 이러한 코드 샘플을](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="e493b-164">Please download these [code samples for this example](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer).</span></span> <span data-ttu-id="e493b-165">Zip 파일에서 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-165">In the zip file you'll find:</span></span>

| <span data-ttu-id="e493b-166">파일</span><span class="sxs-lookup"><span data-stu-id="e493b-166">File</span></span> | <span data-ttu-id="e493b-167">사용</span><span class="sxs-lookup"><span data-stu-id="e493b-167">Use</span></span> |
|-|-|
| <span data-ttu-id="e493b-168">compiledPolicy</span><span class="sxs-lookup"><span data-stu-id="e493b-168">compiledPolicy.bin</span></span> | [<span data-ttu-id="e493b-169">9 단계에서 생성 되며 마지막 10 단계에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-169">Created in Step 9, used in final Step 10.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="e493b-170">mergedPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="e493b-170">mergedPolicy.xml</span></span> | [<span data-ttu-id="e493b-171">6 단계에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-171">Created in Step 6.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="e493b-172">WDAC_Set syncml</span><span class="sxs-lookup"><span data-stu-id="e493b-172">WDAC_Set.syncml</span></span> | <span data-ttu-id="e493b-173">WDAC에는 사용 되지 않지만 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-173">Not used in WDAC but can be used for for [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)</span></span> |

<span data-ttu-id="e493b-174">앱을 즉시 차단 하려면이 경우 앱 설치 관리자 앱에서 compiledPolicy 파일을 사용 하 고 위의 링크에서 10 단계로 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="e493b-174">If you would like to try immediately blocking an app, in this case the App Installer app, then use the compiledPolicy.bin file and skip to step 10 in the link above.</span></span> <span data-ttu-id="e493b-175">이렇게 하면 사용자 지정 정책을 테스트 하 고 그룹 할당과 정책 구성이 올바른지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-175">This will allow you to test out the custom policy and ensure the group assignments and policy configuration is correct.</span></span> 

<span data-ttu-id="e493b-176">앱 설치 관리자를 위 목록의 다른 앱 이나 다른 앱과 차단 하기 위해 WDAC 정책을 결합 하려는 경우 mergedPolicy.xml 파일을 사용 하 고 새 정책을 계속 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-176">If you would like to combine the WDAC policy for blocking App Installer with other apps from the list above, or any other app, then you may use the mergedPolicy.xml file and continue to merge new policies.</span></span> <span data-ttu-id="e493b-177">위에 명시 된 것 처럼 WDAC 정책은 추가 되지 않으므로이는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-177">As stated above WDAC policies are additive so this is not required.</span></span> 

<span data-ttu-id="e493b-178">파일을 열려고 할 때 앱 설치 관리자 앱이 시작 되기 때문에 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-178">Since the App Installer app is launched via trying to open a file will be presented with a prompt.</span></span> <span data-ttu-id="e493b-179">WDAC에 의해 차단 된 앱 위에 설명 된 바와 같이, 사용자가 장치에서 파일을 열려고 하면 파일을 열 때 오류가 표시 되는 것을 확인 하는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-179">As stated above Apps blocked by WDAC do not present a prompt they are blocked, however since the user is attempting to open a file on their device they are presented with an error for opening the file.</span></span> 

![WDAC에서 앱 설치가 차단 됨](images\wdac-app-installer-no-launch.jpg)

<span data-ttu-id="e493b-181">WDAC를 사용 하지 않으려는 경우에는 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 를 사용 하 여 앱이 모두 실행 되는 응용 프로그램 설치 관리자 UX를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-181">If you do not wish to use WDAC, you may as an alternative use [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) to remove the App Installer UX, which is an app after all.</span></span> <span data-ttu-id="e493b-182">그 결과, 앱 설치 관리자 앱이 장치에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-182">The result of this is that the App Installer app will be uninstalled from the device.</span></span> <span data-ttu-id="e493b-183">.appx,. m 6,. a x번들 및 기타 파일 확장명과 함께 웹-앱 실행을 위한 프로토콜은 앱 설치 관리자 앱에서 더 이상 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-183">.appx, .msix, .msixbundle, and other file extensions as well as protocol for web-to-app launch will no longer be handled by the App Installer app.</span></span> <span data-ttu-id="e493b-184">사용자는 스토어의 파일 확장명/프로토콜에 대 한 처리기를 검색 하 라는 메시지를 받게 되며 앱이 나열 되어 있지 않기 때문에 찾을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e493b-184">The user will get a prompt to search for a handler for the file extension/protocol in the store and they will not find the app because it’s not listed.</span></span>