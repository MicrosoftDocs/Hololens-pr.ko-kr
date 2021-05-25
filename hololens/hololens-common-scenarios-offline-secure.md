---
title: 일반적인 시나리오 – 오프 라인 보안 HoloLens 2
description: HoloLens 장치를 프로 비전 하 여 오프 라인 보안 배포 및 앱 배포 시나리오를 설정 하는 방법에 대해 알아봅니다.
keywords: HoloLens, 관리, 오프 라인, 오프 라인 보안
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397884"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="638c4-104">일반적인 시나리오 – 오프 라인 보안 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="638c4-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="638c4-105">개요</span><span class="sxs-lookup"><span data-stu-id="638c4-105">Overview</span></span>

<span data-ttu-id="638c4-106">이 가이드에서는 다음 제한 사항을 사용 하 여 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로 비전 패키지를 적용 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="638c4-107">WiFi를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-107">Disable WiFi.</span></span>
-   <span data-ttu-id="638c4-108">BlueTooth를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="638c4-109">마이크를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-109">Disable Microphones.</span></span>
-   <span data-ttu-id="638c4-110">프로 비전 패키지를 추가 하거나 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="638c4-111">사용자가 위의 제한 된 구성 요소를 사용 하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="638c4-112">[![오프 라인 보안 시나리오 ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="638c4-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="638c4-113">준비</span><span class="sxs-lookup"><span data-stu-id="638c4-113">Prepare</span></span>

<span data-ttu-id="638c4-114">Windows 10 PC 설치</span><span class="sxs-lookup"><span data-stu-id="638c4-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="638c4-115">[최신 HoloLens 2 OS 파일](https://aka.ms/hololens2download) 을 PC에 직접 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="638c4-116">이 구성에 대 한 지원은 빌드 19041.1117 이상에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="638c4-117">[Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC로 고급 복구 도우미 (ARC) 도구 다운로드/설치</span><span class="sxs-lookup"><span data-stu-id="638c4-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="638c4-118">Microsoft Store에서 PC로 최신 [WCD (Windows 구성 디자이너)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="638c4-119">[프로젝트 파일을 사용 하 여 OfflineSecureHL2_Sample 폴더를 다운로드](https://aka.ms/HoloLensDocs-SecureOfflineSample) 하 여 ppkg를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="638c4-120">[PPKG 배포를 위한 오프 라인 lob (기간 업무) 응용 프로그램](app-deploy-provisioning-package.md)을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="638c4-121">구성</span><span class="sxs-lookup"><span data-stu-id="638c4-121">Configure</span></span>

<span data-ttu-id="638c4-122">보안 구성 프로 비전 패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="638c4-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="638c4-123">PC에서 WCD 도구를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="638c4-124">**파일 -> 프로젝트 열기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="638c4-125">이전에 저장한 OfflineSecureHL2_Sample 폴더의 위치로 이동하고 다음을 선택합니다OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="638c4-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="638c4-126">프로젝트가 열리고 이제 사용 가능한 사용자 지정 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="638c4-127">![WCD에서 열린 구성 패키지의 스크린샷](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="638c4-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="638c4-128">이 프로비저닝 패키지에 설정된 구성:</span><span class="sxs-lookup"><span data-stu-id="638c4-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="638c4-129">항목</span><span class="sxs-lookup"><span data-stu-id="638c4-129">Item</span></span>                                                |     <span data-ttu-id="638c4-130">설정</span><span class="sxs-lookup"><span data-stu-id="638c4-130">Setting</span></span>                       |     <span data-ttu-id="638c4-131">설명</span><span class="sxs-lookup"><span data-stu-id="638c4-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="638c4-132">계정/사용자</span><span class="sxs-lookup"><span data-stu-id="638c4-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="638c4-133">로컬 사용자 이름 & 암호</span><span class="sxs-lookup"><span data-stu-id="638c4-133">Local User Name & Password</span></span>    |     <span data-ttu-id="638c4-134">이러한 오프라인 디바이스의 경우 디바이스의 모든 사용자가 단일 사용자 이름 및 암호를 설정하고 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="638c4-135">첫 번째 환경/HoloLens/ SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="638c4-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="638c4-136">True</span><span class="sxs-lookup"><span data-stu-id="638c4-136">True</span></span>                          |     <span data-ttu-id="638c4-137">초기 디바이스 설정 중에만 보정을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="638c4-138">첫 번째 환경/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="638c4-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="638c4-139">True</span><span class="sxs-lookup"><span data-stu-id="638c4-139">True</span></span>                          |     <span data-ttu-id="638c4-140">초기 디바이스 설정 중 디바이스 학습을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="638c4-141">첫 번째 환경/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="638c4-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="638c4-142">True</span><span class="sxs-lookup"><span data-stu-id="638c4-142">True</span></span>                          |     <span data-ttu-id="638c4-143">초기 디바이스를 설정하는 동안 Wi-Fi 구성을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="638c4-144">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="638c4-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="638c4-145">아니요</span><span class="sxs-lookup"><span data-stu-id="638c4-145">No</span></span>                            |     <span data-ttu-id="638c4-146">Bluetooth를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="638c4-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="638c4-147">Policies/Experience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="638c4-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="638c4-148">아니요</span><span class="sxs-lookup"><span data-stu-id="638c4-148">No</span></span>                            |     <span data-ttu-id="638c4-149">Cortana를 사용하지 않도록 설정합니다(마이크가 비활성화되어 잠재적인 문제를 제거하기 위해).</span><span class="sxs-lookup"><span data-stu-id="638c4-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="638c4-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="638c4-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="638c4-151">예</span><span class="sxs-lookup"><span data-stu-id="638c4-151">Yes</span></span>                           |     <span data-ttu-id="638c4-152">마이크를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="638c4-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="638c4-153">정책/개인 정보/전 Appsaccesslocation</span><span class="sxs-lookup"><span data-stu-id="638c4-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="638c4-154">강제 거부</span><span class="sxs-lookup"><span data-stu-id="638c4-154">Force deny</span></span>                    |     <span data-ttu-id="638c4-155">앱에서 위치 데이터에 액세스 하는 것을 방지 합니다 (위치 추적을 사용 하지 않도록 설정 된 후 잠재적인 문제 제거).</span><span class="sxs-lookup"><span data-stu-id="638c4-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="638c4-156">정책/개인 정보/전 Appsaccess마이크</span><span class="sxs-lookup"><span data-stu-id="638c4-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="638c4-157">강제 거부</span><span class="sxs-lookup"><span data-stu-id="638c4-157">Force deny</span></span>                    |     <span data-ttu-id="638c4-158">앱이 마이크에 액세스 하지 못하도록 차단 합니다 (마이크가 사용 하지 않도록 설정 된 경우 잠재적인 문제 제거).</span><span class="sxs-lookup"><span data-stu-id="638c4-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="638c4-159">정책/보안/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="638c4-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="638c4-160">아니요</span><span class="sxs-lookup"><span data-stu-id="638c4-160">No</span></span>                            |     <span data-ttu-id="638c4-161">잠긴 정책을 재정의 하려고 할 수 있는 프로 비전 패키지를 모든 사용자가 추가 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="638c4-162">정책/보안/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="638c4-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="638c4-163">아니요</span><span class="sxs-lookup"><span data-stu-id="638c4-163">No</span></span>                            |     <span data-ttu-id="638c4-164">사용자가이 잠긴 프로 비전 패키지를 제거 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="638c4-165">정책/시스템/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="638c4-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="638c4-166">아니요</span><span class="sxs-lookup"><span data-stu-id="638c4-166">No</span></span>                            |     <span data-ttu-id="638c4-167">장치에서 위치 데이터를 추적 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="638c4-168">정책/a p/a s i Wifi</span><span class="sxs-lookup"><span data-stu-id="638c4-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="638c4-169">아니요</span><span class="sxs-lookup"><span data-stu-id="638c4-169">No</span></span>                            |     <span data-ttu-id="638c4-170">Wi-Fi 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="638c4-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="638c4-171">런타임 설정에서 **계정/사용자/사용자 이름: Holo/Password** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="638c4-172">암호를 확인 하 고 원하는 경우 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="638c4-173">UniversalAppInstall/UserContextApp으로 이동 하 고 이러한 장치에 배포할 [LOB 앱을 구성](app-deploy-provisioning-package.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="638c4-174">![WCD에서 앱을 추가할 위치의 스크린샷](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="638c4-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="638c4-175">완료 되 면 "내보내기" 단추를 선택 하 고 프로 비전 패키지를 만들 때까지 모든 프롬프트를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="638c4-176">![WCD에서이 패키지에 대 한 내보내기 단추의 스크린샷](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="638c4-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="638c4-177">배포</span><span class="sxs-lookup"><span data-stu-id="638c4-177">Deploy</span></span>

1. <span data-ttu-id="638c4-178">USB 케이블을 통해 Windows 10 PC에 HL2를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="638c4-179">ARC 도구를 시작하고 **HoloLens 2** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 정리 리플래시 초기 화면](images/ARC2.png)

1. <span data-ttu-id="638c4-181">다음 화면에서 **수동 패키지 선택** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-181">On the next screen select **Manual package selection**.</span></span>

   ![ARC 정보 화면 HoloLens 2](images/arc_device_info.png)

1. <span data-ttu-id="638c4-183">이전에 다운로드한 .ffu 파일로 이동하고 **열기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="638c4-184">경고 페이지에서 **계속을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-184">At the Warning page select **Continue**.</span></span>

   ![ARC 경고 화면 HoloLens 2](images/arc_warning.png)

1. <span data-ttu-id="638c4-186">ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="638c4-187">디바이스가 설치를 완료하고 다시 부팅하면 PC에서 파일 탐색기 이동하여 이전에 저장된 PPKG 파일을 디바이스 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="638c4-188">![파일 탐색기 창의 PC에 있는 PPKG 파일입니다.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="638c4-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="638c4-189">HoloLens 2 다음 단추 콤보를 눌러 프로비전 패키지를 실행합니다. **볼륨 다운** 및 **전원 단추를** 동시에 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="638c4-190">프로비전 패키지를 적용하라는 메시지가 표시되면 **확인을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="638c4-191">프로비전 패키지가 완료되면 **확인을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="638c4-192">그런 다음 공유 로컬 계정 및 암호를 사용하여 디바이스에 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="638c4-193">유지 관리</span><span class="sxs-lookup"><span data-stu-id="638c4-193">Maintain</span></span>

<span data-ttu-id="638c4-194">이 구성을 사용하면 위의 프로세스를 다시 시작하고 ARC 도구를 사용하여 디바이스를 반사하고 새 PPKG를 적용하여 OS 및/또는 애플리케이션을 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="638c4-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
