---
title: Windows Defender Application Control-WDAC
description: WDAC에 대 한 개요와 HoloLens 장치를 관리 하는 데 사용 하는 방법에 대해 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016796"
---
# <span data-ttu-id="cddda-103">Windows Defender Application Control-WDAC</span><span class="sxs-lookup"><span data-stu-id="cddda-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="cddda-104">WDAC는 IT 관리자가 장치에서 앱의 실행을 차단 하도록 장치를 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="cddda-105">이 방법은 사용자에 게 장치에서 앱을 숨기는 UI가 표시 되지만 계속 실행할 수 있는 키오스크 모드와 같은 장치 제한의 방법과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="cddda-106">WDAC가 구현 되는 동안에도 모든 앱 목록에 앱이 표시 되지만, WDAC는 해당 앱과 프로세스를 디바이스 사용자가 시작할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="cddda-107">최종 사용자가 WDAC에 의해 차단 된 앱을 시작 하려고 하면 HoloLens에서 해당 앱을 시작할 수 없다는 알림을 받지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="cddda-108">다음은 [Windows Intune을 사용 하 여 HoloLens 2 장치에서 앱을 허용 하거나 차단 하는 데 WDAC 및 Windows PowerShell을 사용](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)하는 방법을 배우는 사용자를 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="cddda-109">사용자가 첫 번째 예제 단계를 사용 하 여 Windows 10 PC에 설치 된 앱을 검색 하는 경우 결과 범위를 좁히는 몇 가지 시도를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="cddda-110">패키지의 전체 이름을 모르는 경우 검색 하려면 ' Add-appxpackage-name \ \* YourBestGuess \ \* '을 몇 번 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="cddda-111">그런 다음 ' $package 1 = Get-Add-appxpackage-name ' 이라는 이름을 사용 하 여 ' PackageName '를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="cddda-112">예를 들어 Edge에 대해 다음을 실행 하면 두 개 이상의 결과가 반환 되지만 해당 목록에서 필요한 전체 이름은 Microsoft MicrosoftEdge입니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="cddda-113">HoloLens에서 앱에 대 한 패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="cddda-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="cddda-114">위에 링크 된 가이드에서 newPolicy.xml 수동으로 편집 하 고 패키지 패밀리 이름을 사용 하 여 HoloLens에 설치 된 응용 프로그램에 대 한 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="cddda-115">경우에 따라 정책에 추가 하려는 데스크톱 PC에서 사용 하지 않는 앱이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="cddda-116">다음은 HoloLens 2 장치용으로 자주 사용 하는 앱 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="cddda-117">앱 이름</span><span class="sxs-lookup"><span data-stu-id="cddda-117">App Name</span></span>                   | <span data-ttu-id="cddda-118">패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="cddda-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="cddda-119">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="cddda-119">3D Viewer</span></span>                  | <span data-ttu-id="cddda-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="cddda-121">Calendar</span><span class="sxs-lookup"><span data-stu-id="cddda-121">Calendar</span></span>                   | <span data-ttu-id="cddda-122">microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="cddda-123">카메라</span><span class="sxs-lookup"><span data-stu-id="cddda-123">Camera</span></span>                     | <span data-ttu-id="cddda-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="cddda-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="cddda-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="cddda-125">Cortana</span></span>                    | <span data-ttu-id="cddda-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="cddda-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="cddda-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="cddda-128">Dynamics365. Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="cddda-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="cddda-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="cddda-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="cddda-131">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="cddda-131">Feedback Hub</span></span>               | <span data-ttu-id="cddda-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="cddda-133">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="cddda-133">File Explorer</span></span>              | <span data-ttu-id="cddda-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="cddda-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="cddda-135">Mail</span><span class="sxs-lookup"><span data-stu-id="cddda-135">Mail</span></span>                       | <span data-ttu-id="cddda-136">microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="cddda-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cddda-137">Microsoft Store</span></span>            | <span data-ttu-id="cddda-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="cddda-139">영화 및 TV</span><span class="sxs-lookup"><span data-stu-id="cddda-139">Movies & TV</span></span>                | <span data-ttu-id="cddda-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="cddda-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cddda-141">OneDrive</span></span>                   | <span data-ttu-id="cddda-142">microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="cddda-143">사진</span><span class="sxs-lookup"><span data-stu-id="cddda-143">Photos</span></span>                     | <span data-ttu-id="cddda-144">Microsoft. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="cddda-145">설정</span><span class="sxs-lookup"><span data-stu-id="cddda-145">Settings</span></span>                   | <span data-ttu-id="cddda-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="cddda-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="cddda-147">팁</span><span class="sxs-lookup"><span data-stu-id="cddda-147">Tips</span></span>                       | <span data-ttu-id="cddda-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cddda-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="cddda-149">앱이이 목록에 없는 경우 사용자는 디바이스 포털을 사용 하 여 앱을 차단 하기 위해 설치 된 HoloLens 2에 연결 하 고 PackageRelativeID를 확인 하 고 PackageFamilyName를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="cddda-150">HoloLens 2 장치에 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="cddda-151">> 설정-개발자를 위해 업데이트 & Securtiy-> 하 고 **개발자 모드** 와 **장치 포털**을 차례로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="cddda-152">자세한 내용은 [여기에 디바이스 포털의 설정 및 사용](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cddda-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="cddda-153">디바이스 포털이 연결 되 면 **보기로** 이동한 다음 **앱**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="cddda-154">설치 된 앱 패널 내에서 드롭다운을 사용 하 여 설치 된 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="cddda-155">PackageRelativeID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="cddda-156">! 앞에 앱 문자를 복사 하면 여러분의 PackageFamilyName 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddda-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

