---
title: HoloLens 업데이트
description: HoloLens 빌드 번호를 확인 하 고, 장치 업데이트를 최신 상태로 유지 하 고, 참가자 프로그램에 참여 하 고, 업데이트를 롤백하는 방법에 대해 알아봅니다.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309512"
---
# <a name="update-hololens"></a><span data-ttu-id="bd2a0-104">HoloLens 업데이트</span><span class="sxs-lookup"><span data-stu-id="bd2a0-104">Update HoloLens</span></span>

<span data-ttu-id="bd2a0-105">HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="bd2a0-106">HoloLens는 대기 중인 경우에도 전원에 연결 하 고 인터넷에 연결 될 때마다 자동으로 다운로드 하 여 시스템 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="bd2a0-107">이 문서에서는 다음에 대 한 HoloLens 도구를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="bd2a0-108">현재 운영 체제 버전 보기 (빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="bd2a0-109">업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="bd2a0-109">checking for updates</span></span>
- <span data-ttu-id="bd2a0-110">HoloLens 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="bd2a0-110">manually updating HoloLens</span></span>
- <span data-ttu-id="bd2a0-111">이전 업데이트로 롤백</span><span class="sxs-lookup"><span data-stu-id="bd2a0-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="bd2a0-112">운영 체제 버전 확인 (빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="bd2a0-113">설정 앱을 열고 **시스템** 정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  .</span><span class="sxs-lookup"><span data-stu-id="bd2a0-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="bd2a0-114">업데이트 확인 및 수동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="bd2a0-114">Check for updates and manually update</span></span>

<span data-ttu-id="bd2a0-115">언제 든 지 설정에서 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="bd2a0-116">사용 가능한 업데이트를 확인 하 고 새 업데이트를 확인 하려면:</span><span class="sxs-lookup"><span data-stu-id="bd2a0-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="bd2a0-117">**설정** 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="bd2a0-118">**업데이트 & 보안**  >  **Windows 업데이트** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="bd2a0-119">**업데이트 확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-119">Select **Check for updates**.</span></span>

<span data-ttu-id="bd2a0-120">업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="bd2a0-121">다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="bd2a0-122">장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="bd2a0-123">HoloLens는 업데이트를 설치 하는 동안 회전 하는 기어와 진행률 표시기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="bd2a0-124">이 시간 동안에는 HoloLens를 끄지 마세요.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="bd2a0-125">설치가 완료 되 면 자동으로 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="bd2a0-126">HoloLens는 한 번에 하나의 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="bd2a0-127">HoloLens가 최신 버전 보다 최신 버전인 경우 업데이트 프로세스를 여러 번 실행 하 여 완전히 최신 상태로 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="bd2a0-128">이전 버전으로 돌아가기-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bd2a0-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="bd2a0-129">일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="bd2a0-130">고급 복구 도우미를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2a0-131">이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="bd2a0-132">이전 버전의 HoloLens 2로 돌아가려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="bd2a0-133">휴대폰 또는 Windows 장치가 PC에 연결 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="bd2a0-134">PC의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="bd2a0-135">[최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="bd2a0-136">이러한 다운로드를 마치면 **파일 탐색기**  >  **다운로드** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="bd2a0-137">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 **고 압축 풀기**  >   를 선택 하 여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="bd2a0-138">USB-A USB-C 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="bd2a0-139">(다른 케이블을 사용 하 여 HoloLens를 연결 하는 경우에도이 작업은 가장 효과적입니다.)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="bd2a0-140">Advanced Recovery 도우미가 자동으로 HoloLens를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="bd2a0-141">**Microsoft HoloLens** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="bd2a0-142">다음 화면에서 **수동 패키지 선택** 을 선택한 다음 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="bd2a0-143">(.Ffu 확장명을 가진 파일을 찾습니다.)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="bd2a0-144">**소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="bd2a0-145">이전 버전으로 돌아가기-HoloLens (첫 번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="bd2a0-146">일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="bd2a0-147">Windows 장치 복구 도구를 사용 하 여 HoloLens를 이전 버전으로 다시 설정 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2a0-148">이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="bd2a0-149">이전 버전의 HoloLens 1로 돌아가려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="bd2a0-150">휴대폰 또는 Windows 장치가 PC에 연결 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="bd2a0-151">PC에서 [WDRT (Windows 장치 복구 도구)](https://support.microsoft.com/help/12379)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="bd2a0-152">[HoloLens 기념일 업데이트 복구 패키지](https://aka.ms/hololensrecovery)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="bd2a0-153">다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="bd2a0-154">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 고 **압축 풀기**  >  를 선택 하 여 압축을 **풉니다** .</span><span class="sxs-lookup"><span data-stu-id="bd2a0-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="bd2a0-155">동봉 된 마이크로 USB 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="bd2a0-156">(다른 케이블을 사용 하 여 HoloLens를 연결 하는 경우에도이 작업은 가장 효과적입니다.)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="bd2a0-157">WDRT는 HoloLens를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="bd2a0-158">**Microsoft HoloLens** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="bd2a0-159">다음 화면에서 **수동 패키지 선택** 을 선택 하 고 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="bd2a0-160">(.Ffu 확장명을 가진 파일을 찾습니다.)</span><span class="sxs-lookup"><span data-stu-id="bd2a0-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="bd2a0-161">**소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2a0-162">WDRT가 HoloLens를 검색 하지 않으면 PC를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="bd2a0-163">그래도 작동 하지 않으면 **내 장치를 찾을 수 없음** 을 선택 하 고 **Microsoft HoloLens** 를 선택한 후 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="bd2a0-164">HoloLens의 Windows 참가자 프로그램</span><span class="sxs-lookup"><span data-stu-id="bd2a0-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="bd2a0-165">HoloLens의 최신 기능을 보 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="bd2a0-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="bd2a0-166">그렇다면 Windows 참가자 프로그램에 참여 하세요. 일반적으로 일반 사용자에 게 제공 되기 전에 HoloLens 소프트웨어 업데이트의 빌드 미리 보기에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="bd2a0-167">[Microsoft HoloLens 용 Windows Insider preview를 다운로드](hololens-insider.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2a0-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
