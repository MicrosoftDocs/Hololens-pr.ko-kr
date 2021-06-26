---
title: HoloLens 업데이트 2
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924114"
---
# <a name="update-hololens-2"></a><span data-ttu-id="ae2ce-104">HoloLens 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="ae2ce-104">Update HoloLens 2</span></span>

<span data-ttu-id="ae2ce-105">HoloLens는 다른 Windows 10 장치와 마찬가지로 Windows 업데이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="ae2ce-106">HoloLens는 대기 중인 경우에도 전원에 연결 하 고 인터넷에 연결 될 때마다 자동으로 다운로드 하 여 시스템 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="ae2ce-107">이 문서에서는 다음에 대 한 HoloLens 도구를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="ae2ce-108">현재 운영 체제 버전 보기 (빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="ae2ce-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="ae2ce-109">업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="ae2ce-109">checking for updates</span></span>
- <span data-ttu-id="ae2ce-110">HoloLens 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="ae2ce-110">manually updating HoloLens</span></span>
- <span data-ttu-id="ae2ce-111">이전 업데이트로 롤백</span><span class="sxs-lookup"><span data-stu-id="ae2ce-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="ae2ce-112">운영 체제 버전 확인 (빌드 번호)</span><span class="sxs-lookup"><span data-stu-id="ae2ce-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="ae2ce-113">설정 앱을 열고 **시스템** 정보를 선택 하 여 시스템 버전 번호 (빌드 번호)를 확인할 수 있습니다  >  .</span><span class="sxs-lookup"><span data-stu-id="ae2ce-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="ae2ce-114">업데이트 확인 및 수동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="ae2ce-114">Check for updates and manually update</span></span>

<span data-ttu-id="ae2ce-115">언제 든 지 설정에서 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="ae2ce-116">사용 가능한 업데이트를 확인 하 고 새 업데이트를 확인 하려면:</span><span class="sxs-lookup"><span data-stu-id="ae2ce-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="ae2ce-117">**설정** 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="ae2ce-118">**업데이트 & 보안**  >  **Windows 업데이트** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="ae2ce-119">**업데이트 확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-119">Select **Check for updates**.</span></span>

<span data-ttu-id="ae2ce-120">업데이트를 사용할 수 있는 경우 새 버전 다운로드가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="ae2ce-121">다운로드가 완료 되 면 **지금 다시 시작** 단추를 선택 하 여 설치를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="ae2ce-122">장치가 40% 미만이 고 연결 되지 않은 경우 다시 시작 해도 업데이트 설치가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="ae2ce-123">HoloLens는 업데이트를 설치 하는 동안 회전 하는 기어와 진행률 표시기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="ae2ce-124">이 시간 동안에는 HoloLens를 끄지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="ae2ce-125">설치가 완료 되 면 자동으로 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="ae2ce-126">HoloLens는 한 번에 하나의 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="ae2ce-127">HoloLens가 최신 버전 보다 최신 버전인 경우 업데이트 프로세스를 여러 번 실행 하 여 완전히 최신 상태로 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="ae2ce-128">이전 버전으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="ae2ce-128">Go back to a previous version</span></span>

<span data-ttu-id="ae2ce-129">일부 경우에는 이전 버전의 HoloLens 소프트웨어로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="ae2ce-130">권장 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-130">The recommended steps are:</span></span>

1. <span data-ttu-id="ae2ce-131">지원 서비스에 문의 하 여 문제를 해결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="ae2ce-132">**선택적** 또는 **전체** 원격 분석이 사용 하도록 설정 되어 있는지 확인 합니다. 이렇게 하면 엔지니어가 더 쉽게 실행할 수 있고 엔지니어가 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="ae2ce-133">[파일 피드백](hololens-feedback.md) 을 가능한 한 설명적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="ae2ce-134">버그를 지원과 공유할 수 있도록 제목을 적어 두고 공유 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="ae2ce-135">[지원](https://aka.ms/hlsupport)담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="ae2ce-136">이전 버전으로 돌아가서 문제를 해결 해야 하는 경우에는 장치를 플래시 하기 위해 FFU를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="ae2ce-137">그래도 작동 하지 않는 경우에는 [고급 복구 부록을 사용 하 여 HoloLens 2를 다시 설정 하거나 경감 하기 위해](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ae2ce-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="ae2ce-138">PC의 Microsoft Store에서 [고급 복구 도우미](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="ae2ce-139">휴대폰 또는 Windows 장치가 PC에 연결 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="ae2ce-140">플래시 하려는 버전 선택:</span><span class="sxs-lookup"><span data-stu-id="ae2ce-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="ae2ce-141">[최신 HoloLens 2 릴리스](https://aka.ms/hololens2download)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="ae2ce-142">ARC가 호스트 하는 기본 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="ae2ce-143">(이 옵션을 선택 하는 경우 다음 단계를 건너뜁니다.)</span><span class="sxs-lookup"><span data-stu-id="ae2ce-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="ae2ce-144">에서 제공 하는 빌드 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="ae2ce-145">이러한 다운로드를 마치면 **파일 탐색기**  >  **다운로드** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="ae2ce-146">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 **고 압축 풀기**  >   를 선택 하 여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="ae2ce-147">USB-A USB-C 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="ae2ce-148">(다른 케이블을 사용 하 여 HoloLens를 연결 하는 경우에도이 작업은 가장 효과적입니다.)</span><span class="sxs-lookup"><span data-stu-id="ae2ce-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="ae2ce-149">Advanced Recovery 도우미가 자동으로 HoloLens를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="ae2ce-150">**Microsoft HoloLens** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="ae2ce-151">다음 화면에서 **수동 패키지 선택** 을 선택한 다음 4 단계에서 압축을 푼 폴더에 포함 된 설치 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="ae2ce-152">(.Ffu 확장명을 가진 파일을 찾습니다.)</span><span class="sxs-lookup"><span data-stu-id="ae2ce-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="ae2ce-153">**소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="ae2ce-154">이전 버전으로 돌아가서 개인 파일 및 설정이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="ae2ce-155">또한 현재 설치 된 릴리스를 유지 하려는 경우 업데이트를 수동으로 [일시 중지할](hololens-updates.md#pause-updates-via-device)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="ae2ce-156">그러면 엔지니어링 팀이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="ae2ce-157">HoloLens의 Windows 참가자 프로그램</span><span class="sxs-lookup"><span data-stu-id="ae2ce-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="ae2ce-158">HoloLens의 최신 기능을 보 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="ae2ce-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="ae2ce-159">그렇다면 Windows 참가자 프로그램에 참여 하세요. 일반적으로 일반 사용자에 게 제공 되기 전에 HoloLens 소프트웨어 업데이트의 빌드 미리 보기에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="ae2ce-160">[Microsoft HoloLens 용 Windows Insider preview를 다운로드](hololens-insider.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
