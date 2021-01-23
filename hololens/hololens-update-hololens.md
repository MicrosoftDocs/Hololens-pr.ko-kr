---
title: HoloLens 업데이트
description: HoloLens 빌드 번호를 확인하고, 장치 업데이트를 최신으로 유지하며, Insiders 프로그램에 참여하고, 업데이트를 롤백하는 방법을 자세히 알아보는 방법을 확인합니다.
keywords: 방법, 업데이트, 롤백, HoloLens, 빌드 확인, 빌드 번호
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283939"
---
# <span data-ttu-id="8a98b-104">HoloLens 업데이트</span><span class="sxs-lookup"><span data-stu-id="8a98b-104">Update HoloLens</span></span>

<span data-ttu-id="8a98b-105">HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="8a98b-106">HoloLens는 전원에 연결되어 있으며 대기 중이어도 인터넷에 연결될 때마다 시스템 업데이트를 자동으로 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="8a98b-107">이 문서에서는 다음에 대한 HoloLens 도구를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="8a98b-108">현재 운영 체제 버전 보기(빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="8a98b-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="8a98b-109">업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="8a98b-109">checking for updates</span></span>
- <span data-ttu-id="8a98b-110">HoloLens 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="8a98b-110">manually updating HoloLens</span></span>
- <span data-ttu-id="8a98b-111">이전 업데이트로 롤백</span><span class="sxs-lookup"><span data-stu-id="8a98b-111">rolling back to an older update</span></span>

## <span data-ttu-id="8a98b-112">운영 체제 버전 확인(빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="8a98b-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="8a98b-113">설정 앱을 열고 시스템 정보(시스템 정보)를 선택하여 시스템 버전 번호(빌드 번호)를 **확인할**  >  **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8a98b-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="8a98b-114">업데이트 확인 및 수동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="8a98b-114">Check for updates and manually update</span></span>

<span data-ttu-id="8a98b-115">설정에서 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="8a98b-116">사용 가능한 업데이트를 확인하고 새 업데이트를 확인:</span><span class="sxs-lookup"><span data-stu-id="8a98b-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="8a98b-117">설정 **앱을 열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="8a98b-118">보안 **Windows &**  >  **업데이트로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a98b-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="8a98b-119">Select **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="8a98b-119">Select **Check for updates**.</span></span>

<span data-ttu-id="8a98b-120">업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="8a98b-121">다운로드가 완료되면 지금 다시 \*\*\*\* 시작 단추를 선택하여 설치를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="8a98b-122">장치가 40% 미만으로 연결되어 있지 않은 경우 업데이트를 다시 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="8a98b-123">HoloLens에서 업데이트를 설치하는 동안 회전 기어와 진행률 표시기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="8a98b-124">이 시간 동안 HoloLens를 끄지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="8a98b-125">설치가 완료되면 자동으로 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="8a98b-126">HoloLens는 한 번의 업데이트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="8a98b-127">HoloLens가 최신 버전보다 두 개 이상 최신 버전인 경우 업데이트 프로세스를 여러 번 실행하여 완전히 최신 버전을 제공해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="8a98b-128">이전 버전으로 돌아가기 - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8a98b-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="8a98b-129">경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아갈 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="8a98b-130">이 작업을 위해 고급 복구 도우미를 사용하여 HoloLens를 이전 버전으로 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="8a98b-131">이전 버전으로 돌아가면 개인 파일 및 설정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="8a98b-132">HoloLens 2의 이전 버전으로 돌아가려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8a98b-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="8a98b-133">PC에 연결된 휴대폰이나 Windows 장치가 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="8a98b-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="8a98b-134">PC에서 Microsoft Store에서 [Advanced Recovery Companion를](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="8a98b-135">[최근 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="8a98b-136">이러한 다운로드를 마쳤을 때 파일 **탐색기**  >  **다운로드를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8a98b-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="8a98b-137">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 추출** > **추출**을 선택하여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="8a98b-138">USB-A와 USB-C 케이블을 사용하여 HoloLens를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="8a98b-139">(다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)</span><span class="sxs-lookup"><span data-stu-id="8a98b-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="8a98b-140">Advanced Recovery Companion가 HoloLens를 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="8a98b-141">**Microsoft HoloLens** 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="8a98b-142">다음 화면에서 수동 \*\*\*\* 패키지 선택을 선택한 다음 4단계에서 제거한 폴더에 포함된 설치 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="8a98b-143">확장명은 .ffu인 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="8a98b-144">소프트웨어 **설치를**선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="8a98b-145">이전 버전으로 돌아가기 - HoloLens(1세대)</span><span class="sxs-lookup"><span data-stu-id="8a98b-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="8a98b-146">경우에 따라 이전 버전의 HoloLens 소프트웨어로 돌아갈 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="8a98b-147">이 작업을 위해 Windows Device Recovery Tool을 사용하여 HoloLens를 이전 버전으로 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="8a98b-148">이전 버전으로 돌아가면 개인 파일 및 설정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="8a98b-149">이전 버전의 HoloLens 1로 돌아가서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="8a98b-150">PC에 연결된 휴대폰이나 Windows 장치가 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="8a98b-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="8a98b-151">PC에서 [WDRT(Windows Device Recovery Tool)를 다운로드합니다.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="8a98b-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="8a98b-152">[HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="8a98b-153">다운로드가 완료되면 파일 **탐색기**  >  **다운로드를 열어 니다.**</span><span class="sxs-lookup"><span data-stu-id="8a98b-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="8a98b-154">방금 다운로드한 압축된 폴더를 마우스 오른쪽 \*\*\*\* 단추로 클릭하고 압축을 풀려면 추출을  >  \*\*\*\* 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="8a98b-155">HoloLens를 함께 사용한 마이크로 USB 케이블을 사용하여 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="8a98b-156">(다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)</span><span class="sxs-lookup"><span data-stu-id="8a98b-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="8a98b-157">WDRT는 HoloLens를 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="8a98b-158">**Microsoft HoloLens** 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="8a98b-159">다음 화면에서 수동 \*\*\*\* 패키지 선택을 선택하고 4단계에서 제거한 폴더에 포함된 설치 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="8a98b-160">확장명은 .ffu인 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="8a98b-161">소프트웨어 **설치를**선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="8a98b-162">WDRT에서 HoloLens를 검색하지 못하면 PC를 다시 시작해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="8a98b-163">그래도 문제가 해결 되지 않으면 **장치가 감지 되지 않음**을 선택하고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="8a98b-164">HoloLens의 Windows Insider 프로그램</span><span class="sxs-lookup"><span data-stu-id="8a98b-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="8a98b-165">HoloLens의 최신 기능을 보고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8a98b-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="8a98b-166">그렇다면 Windows Insider 프로그램에 참여합니다. HoloLens 소프트웨어 업데이트의 미리 보기 빌드에 대한 액세스 권한을 얻게 되기 전에 일반인에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a98b-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="8a98b-167">[Microsoft HoloLens용 Windows Insider Preview를 다운로드합니다.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="8a98b-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
