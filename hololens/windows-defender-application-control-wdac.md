---
title: Windows Defender 애플리케이션 제어 - WDAC
description: 애플리케이션 제어의 Windows Defender 및 이를 사용하여 HoloLens 혼합 현실 디바이스를 관리하는 방법에 대한 개요입니다.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639933"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="5dbda-103">Windows Defender 애플리케이션 제어 - WDAC</span><span class="sxs-lookup"><span data-stu-id="5dbda-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="5dbda-104">WDAC를 사용하면 IT 관리자가 디바이스에서 앱의 출시를 차단하도록 디바이스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="5dbda-105">이는 키오스크 모드와 같이 디바이스에서 앱을 숨기는 UI가 사용자에게 표시되지만 여전히 시작될 수 있는 디바이스 제한 방법과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="5dbda-106">WDAC가 구현되는 동안 앱은 여전히 모든 앱 목록에 표시되지만 WDAC는 해당 앱 및 프로세스가 디바이스 사용자가 시작하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="5dbda-107">디바이스에 WDAC 정책이 두 개 이상 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="5dbda-108">시스템에 여러 WDAC 정책이 설정된 경우 가장 제한적인 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="5dbda-109">최종 사용자가 WDAC에 의해 차단된 앱을 시작하려고 하면 HoloLens 해당 앱을 시작할 수 없다는 알림이 수신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="5dbda-110">다음은 사용자가 [WDAC 및 Windows PowerShell 사용하여 Microsoft Intune HoloLens 2 디바이스에서 앱을 허용하거나 차단하는](/mem/intune/configuration/custom-profile-hololens)방법을 알아보는 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="5dbda-111">사용자가 첫 번째 예제 단계를 사용하여 Windows 10 PC에 설치된 앱을 검색할 때 결과의 범위를 좁히기 위해 몇 가지 시도를 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="5dbda-112">패키지의 전체 이름을 모르는 경우 'Get-AppxPackage -name \* YourBestGuess'를 몇 \* 번 실행하여 찾아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="5dbda-113">그런 다음 이름이 '$package 1 = Get-AppxPackage -name Actual.PackageName'을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="5dbda-114">예를 들어 Microsoft Edge 대해 다음을 실행하면 결과가 두 개 이상 반환되지만 해당 목록에서 필요한 전체 이름이 Microsoft.MicrosoftEdge임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="5dbda-115">HoloLens 앱의 패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="5dbda-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="5dbda-116">위에 링크된 가이드에서는 newPolicy.xml 수동으로 편집하고 패키지 패밀리 이름으로 HoloLens 설치되는 애플리케이션에 대한 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="5dbda-117">경우에 따라 정책에 추가하려는 데스크톱 PC에 없는 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="5dbda-118">다음은 HoloLens 2 디바이스에 일반적으로 사용되고 In-Box 앱의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="5dbda-119">앱 이름</span><span class="sxs-lookup"><span data-stu-id="5dbda-119">App Name</span></span>                   | <span data-ttu-id="5dbda-120">패키지 패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="5dbda-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="5dbda-121">3D 뷰어</span><span class="sxs-lookup"><span data-stu-id="5dbda-121">3D Viewer</span></span>                  | <span data-ttu-id="5dbda-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="5dbda-123">앱 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="5dbda-123">App Installer</span></span>              | <span data-ttu-id="5dbda-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5dbda-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="5dbda-125">캘린더</span><span class="sxs-lookup"><span data-stu-id="5dbda-125">Calendar</span></span>                   | <span data-ttu-id="5dbda-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="5dbda-127">카메라</span><span class="sxs-lookup"><span data-stu-id="5dbda-127">Camera</span></span>                     | <span data-ttu-id="5dbda-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="5dbda-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="5dbda-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="5dbda-129">Cortana</span></span>                    | <span data-ttu-id="5dbda-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="5dbda-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="5dbda-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="5dbda-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="5dbda-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="5dbda-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="5dbda-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="5dbda-135">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="5dbda-135">Feedback Hub</span></span>               | <span data-ttu-id="5dbda-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="5dbda-137">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="5dbda-137">File Explorer</span></span>              | <span data-ttu-id="5dbda-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="5dbda-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="5dbda-139">Mail</span><span class="sxs-lookup"><span data-stu-id="5dbda-139">Mail</span></span>                       | <span data-ttu-id="5dbda-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="5dbda-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="5dbda-141">Microsoft Store</span></span>            | <span data-ttu-id="5dbda-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="5dbda-143">영화 & TV</span><span class="sxs-lookup"><span data-stu-id="5dbda-143">Movies & TV</span></span>                | <span data-ttu-id="5dbda-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="5dbda-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="5dbda-145">OneDrive</span></span>                   | <span data-ttu-id="5dbda-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="5dbda-147">사진</span><span class="sxs-lookup"><span data-stu-id="5dbda-147">Photos</span></span>                     | <span data-ttu-id="5dbda-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="5dbda-149">설정</span><span class="sxs-lookup"><span data-stu-id="5dbda-149">Settings</span></span>                   | <span data-ttu-id="5dbda-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="5dbda-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="5dbda-151">팁</span><span class="sxs-lookup"><span data-stu-id="5dbda-151">Tips</span></span>                       | <span data-ttu-id="5dbda-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5dbda-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="5dbda-153">1 - 앱 설치 관리자 차단하면 앱 설치 관리자 앱만 차단되고 Microsoft Store 같은 다른 원본 또는 MDM 솔루션에서 설치된 앱은 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="5dbda-154">패키지 패밀리 이름을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5dbda-154">How to find a Package Family Name</span></span>

<span data-ttu-id="5dbda-155">앱이 이 목록에 없는 경우 사용자는 차단하려는 앱을 설치한 HoloLens 2 연결된 장치 포털 사용하여 PackageRelativeID를 확인하고 이 목록에서 PackageFamilyName을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="5dbda-156">HoloLens 2 디바이스에 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="5dbda-157">개발자용 설정 -> 업데이트 & 보안 -> 열고 **개발자 모드를** 사용하도록 설정한 다음, **디바이스 포털 을** 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="5dbda-158">자세한 지침은 [여기에서 디바이스 포털 설정 및 사용에](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)대해 자세히 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="5dbda-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="5dbda-159">장치 포털 연결되면 **보기,** **앱으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="5dbda-160">설치된 앱 패널 내에서 드롭다운을 사용하여 설치된 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="5dbda-161">PackageRelativeID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="5dbda-162">!앞에 앱 문자를 복사합니다. 이러한 문자는 PackageFamilyName이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dbda-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


