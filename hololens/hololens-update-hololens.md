---
title: HoloLens 업데이트
description: HoloLens의 빌드 번호, 업데이트, 롤백 업데이트를 확인 합니다.
keywords: 방법, 업데이트, 롤백, HoloLens, 확인, 빌드 번호
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828593"
---
# <span data-ttu-id="6848f-104">HoloLens 업데이트</span><span class="sxs-lookup"><span data-stu-id="6848f-104">Update HoloLens</span></span>

<span data-ttu-id="6848f-105">HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="6848f-106">HoloLens는 전원이 켜져 있고 인터넷에 연결 될 때마다 시스템 업데이트가 자동으로 다운로드 되 고 설치 되며,이는 대기 상태에 있는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="6848f-107">이 문서에서는 다음에 대 한 HoloLens 도구를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="6848f-108">현재 운영 체제 버전 보기 (빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="6848f-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="6848f-109">업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="6848f-109">checking for updates</span></span>
- <span data-ttu-id="6848f-110">수동으로 HoloLens 업데이트</span><span class="sxs-lookup"><span data-stu-id="6848f-110">manually updating HoloLens</span></span>
- <span data-ttu-id="6848f-111">이전 업데이트로 롤백</span><span class="sxs-lookup"><span data-stu-id="6848f-111">rolling back to an older update</span></span>

## <span data-ttu-id="6848f-112">운영 체제 버전 확인 (빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="6848f-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="6848f-113">설정 앱을 열고 **시스템**정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="6848f-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="6848f-114">업데이트 확인 및 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="6848f-114">Check for updates and manually update</span></span>

<span data-ttu-id="6848f-115">설정에서 언제 든 지 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="6848f-116">사용 가능한 업데이트를 보고 새 업데이트를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="6848f-117">**설정** 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="6848f-118">**업데이트 & 보안**  >  **Windows 업데이트**를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="6848f-119">**업데이트 확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-119">Select **Check for updates**.</span></span>

<span data-ttu-id="6848f-120">업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="6848f-121">다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="6848f-122">장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="6848f-123">HoloLens에서 업데이트를 설치 하는 동안에는 회전 하는 기어 및 진행 표시기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="6848f-124">이번 시간에는 HoloLens를 끄지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6848f-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="6848f-125">설치가 완료 되 면 자동으로 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="6848f-126">HoloLens는 한 번에 하나의 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="6848f-127">HoloLens가 최신 버전 뒤에 두 개 이상 있는 경우 업데이트 프로세스를 여러 번 실행 하 여 완전히 최신 상태가 되도록 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="6848f-128">이전 버전으로 돌아가기-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6848f-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="6848f-129">일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6848f-130">고급 복구 도우미를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6848f-131">이전 버전으로 돌아가면 개인 파일 및 설정이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6848f-132">이전 버전의 HoloLens 2로 돌아가려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6848f-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="6848f-133">PC에 전화 또는 Windows 장치가 연결 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6848f-134">PC에서 Microsoft Store의 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="6848f-135">[최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="6848f-136">이러한 다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6848f-137">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 추출** > **추출**을 선택하여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6848f-138">USB-A에서 USB-C 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="6848f-139">(다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)</span><span class="sxs-lookup"><span data-stu-id="6848f-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6848f-140">고급 복구 도우미는 HoloLens를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="6848f-141">**Microsoft HoloLens** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6848f-142">다음 화면에서 **수동 패키지 선택을** 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="6848f-143">(확장명을 가진 파일을 찾습니다.)</span><span class="sxs-lookup"><span data-stu-id="6848f-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6848f-144">**소프트웨어 설치**를 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="6848f-145">이전 버전으로 돌아가기-HoloLens (첫번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="6848f-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="6848f-146">일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6848f-147">Windows 장치 복구 도구를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6848f-148">이전 버전으로 돌아가면 개인 파일 및 설정이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6848f-149">이전 버전의 HoloLens 1로 돌아가려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6848f-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="6848f-150">PC에 전화 또는 Windows 장치가 연결 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6848f-151">PC에서 [WDRT (Windows 장치 복구) 도구](https://support.microsoft.com/help/12379)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="6848f-152">[HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="6848f-153">다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6848f-154">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 고 압축 풀기 **모두 추출을**선택  >  **Extract** 하 여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6848f-155">함께 제공 된 마이크로 USB 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="6848f-156">(다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)</span><span class="sxs-lookup"><span data-stu-id="6848f-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6848f-157">WDRT는 HoloLens를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="6848f-158">**Microsoft HoloLens** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6848f-159">다음 화면에서 **수동 패키지 선택을** 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="6848f-160">(확장명을 가진 파일을 찾습니다.)</span><span class="sxs-lookup"><span data-stu-id="6848f-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6848f-161">**소프트웨어 설치**를 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="6848f-162">WDRT가 HoloLens를 감지 하지 못하는 경우 PC를 다시 시작 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6848f-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="6848f-163">그래도 문제가 해결 **되지 않으면 내 장치를 찾을 수 없음을**선택 하 고 **Microsoft HoloLens**를 선택한 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="6848f-164">HoloLens의 Windows 참가자 프로그램</span><span class="sxs-lookup"><span data-stu-id="6848f-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="6848f-165">HoloLens의 최신 기능을 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="6848f-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="6848f-166">그렇다면 Windows 참가자 프로그램에 가입 하세요. 일반적인 일반 사용자가 사용할 수 있으려면 HoloLens 소프트웨어 업데이트의 preview 빌드에 대 한 액세스 권한을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6848f-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="6848f-167">[Microsoft HoloLens에 대 한 Windows 참가자 미리 보기를 다운로드](hololens-insider.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="6848f-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
