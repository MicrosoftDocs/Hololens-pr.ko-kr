---
title: 일반적인 시나리오 - 오프라인 보안 HoloLens 2
description: HoloLens 장치 프로비전을 통해 오프라인 보안 배포 및 앱 배포 시나리오를 설정하는 방법을 설명합니다.
keywords: HoloLens, 관리, 오프라인, 오프라인 보안
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407594"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="81f46-104">일반적인 시나리오 - 오프라인 보안 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="81f46-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="81f46-105">개요</span><span class="sxs-lookup"><span data-stu-id="81f46-105">Overview</span></span>

<span data-ttu-id="81f46-106">이 가이드에서는 다음과 같은 제한 사항이 있는 보안 환경에서 사용하기 위해 HoloLens 2를 잠그는 샘플 프로비저닝 패키지를 적용하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="81f46-107">WiFi를 사용하지 않도록 설정.</span><span class="sxs-lookup"><span data-stu-id="81f46-107">Disable WiFi.</span></span>
-   <span data-ttu-id="81f46-108">BlueTooth를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="81f46-109">마이크를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="81f46-109">Disable Microphones.</span></span>
-   <span data-ttu-id="81f46-110">프로비저닝 패키지 추가 또는 제거를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="81f46-111">어떤 사용자도 위의 제한된 구성 요소를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="81f46-112">준비</span><span class="sxs-lookup"><span data-stu-id="81f46-112">Prepare</span></span>

<span data-ttu-id="81f46-113">Windows 10 PC 설정</span><span class="sxs-lookup"><span data-stu-id="81f46-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="81f46-114">[최신 HoloLens 2 OS 파일을 PC에](https://aka.ms/hololens2download) 직접 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="81f46-115">이 구성에 대한 지원은 빌드 19041.1117 이상에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="81f46-116">[Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC로 ARC(고급 복구 도우미) 도구 다운로드/설치</span><span class="sxs-lookup"><span data-stu-id="81f46-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="81f46-117">Microsoft Store에서 [PC로 최신 WCD(Windows 구성 디자이너)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드/설치합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="81f46-118">[프로젝트 OfflineSecureHL2_Sample](https://aka.ms/HoloLensDocs-SecureOfflineSample) 폴더를 다운로드하여 PPKG를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="81f46-119">PPKG 배포를 위해 오프라인 업무(LINE [OF BUSINESS) 응용 프로그램을 준비합니다.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="81f46-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="81f46-120">구성</span><span class="sxs-lookup"><span data-stu-id="81f46-120">Configure</span></span>

<span data-ttu-id="81f46-121">보안 구성 프로비저닝 패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="81f46-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="81f46-122">PC에서 WCD 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="81f46-123">파일 **-> 열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="81f46-124">이전에 저장한 OfflineSecureHL2_Sample 폴더 위치로 이동한 다음 다음을 OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="81f46-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="81f46-125">프로젝트가 열리면 사용 가능한 사용자 지정 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD에서 열 수 있는 구성 패키지 스크린샷](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="81f46-127">이 프로비저닝 패키지에 설정된 구성:</span><span class="sxs-lookup"><span data-stu-id="81f46-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="81f46-128">항목</span><span class="sxs-lookup"><span data-stu-id="81f46-128">Item</span></span>                                                |     <span data-ttu-id="81f46-129">설정</span><span class="sxs-lookup"><span data-stu-id="81f46-129">Setting</span></span>                       |     <span data-ttu-id="81f46-130">설명</span><span class="sxs-lookup"><span data-stu-id="81f46-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="81f46-131">계정/사용자</span><span class="sxs-lookup"><span data-stu-id="81f46-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="81f46-132">로컬 사용자 이름 & 암호</span><span class="sxs-lookup"><span data-stu-id="81f46-132">Local User Name & Password</span></span>    |     <span data-ttu-id="81f46-133">이러한 오프라인 장치의 경우 장치의 모든 사용자가 단일 사용자 이름과 암호를 설정하고 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="81f46-134">첫 번째 환경/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="81f46-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="81f46-135">True</span><span class="sxs-lookup"><span data-stu-id="81f46-135">True</span></span>                          |     <span data-ttu-id="81f46-136">초기 장치 설정 중에만 보정을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="81f46-137">첫 번째 경험/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="81f46-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="81f46-138">True</span><span class="sxs-lookup"><span data-stu-id="81f46-138">True</span></span>                          |     <span data-ttu-id="81f46-139">초기 장치 설정 중에 장치 교육 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="81f46-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="81f46-140">첫 번째 경험/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="81f46-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="81f46-141">True</span><span class="sxs-lookup"><span data-stu-id="81f46-141">True</span></span>                          |     <span data-ttu-id="81f46-142">초기 장치 Wi-Fi 구성 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="81f46-143">정책/연결/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="81f46-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="81f46-144">아니오</span><span class="sxs-lookup"><span data-stu-id="81f46-144">No</span></span>                            |     <span data-ttu-id="81f46-145">이 기능을 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="81f46-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="81f46-146">정책/환경/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="81f46-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="81f46-147">아니오</span><span class="sxs-lookup"><span data-stu-id="81f46-147">No</span></span>                            |     <span data-ttu-id="81f46-148">Cortana를 사용하지 않도록 설정(마이크를 사용하지 않도록 설정한 이후 발생할 수 있는 문제를 제거하기 위해)</span><span class="sxs-lookup"><span data-stu-id="81f46-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="81f46-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="81f46-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="81f46-150">예</span><span class="sxs-lookup"><span data-stu-id="81f46-150">Yes</span></span>                           |     <span data-ttu-id="81f46-151">마이크를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="81f46-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="81f46-152">정책/개인 정보/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="81f46-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="81f46-153">강제 거부</span><span class="sxs-lookup"><span data-stu-id="81f46-153">Force deny</span></span>                    |     <span data-ttu-id="81f46-154">앱이 위치 데이터에 액세스하지 못하게 합니다(위치 추적을 사용하지 않도록 설정한 이후 발생할 수 있는 문제를 제거하기 위해).</span><span class="sxs-lookup"><span data-stu-id="81f46-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="81f46-155">정책/개인 정보/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="81f46-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="81f46-156">강제 거부</span><span class="sxs-lookup"><span data-stu-id="81f46-156">Force deny</span></span>                    |     <span data-ttu-id="81f46-157">앱이 마이크에 액세스하지 못하게 방지합니다(마이크를 사용하지 않도록 설정한 이후 발생할 수 있는 문제를 제거하기 위해).</span><span class="sxs-lookup"><span data-stu-id="81f46-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="81f46-158">정책/보안/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="81f46-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="81f46-159">아니오</span><span class="sxs-lookup"><span data-stu-id="81f46-159">No</span></span>                            |     <span data-ttu-id="81f46-160">잠긴 정책을 다시 설정하려고 할 수 있는 프로비저닝 패키지를 추가하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="81f46-161">정책/보안/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="81f46-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="81f46-162">아니오</span><span class="sxs-lookup"><span data-stu-id="81f46-162">No</span></span>                            |     <span data-ttu-id="81f46-163">잠긴 프로비저닝 패키지를 제거하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="81f46-164">정책/시스템/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="81f46-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="81f46-165">아니오</span><span class="sxs-lookup"><span data-stu-id="81f46-165">No</span></span>                            |     <span data-ttu-id="81f46-166">디바이스가 위치 데이터를 추적하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="81f46-167">정책/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="81f46-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="81f46-168">아니오</span><span class="sxs-lookup"><span data-stu-id="81f46-168">No</span></span>                            |     <span data-ttu-id="81f46-169">이 기능을 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="81f46-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="81f46-170">런타임 설정에서 계정 **/ 사용자 / 사용자 이름: Holo / 암호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="81f46-171">암호를 메모하고 원하는 경우 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="81f46-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="81f46-172">UniversalAppInstall /UserContextApp으로 이동하여 이러한 장치에 배포할 [LOB](app-deploy-provisioning-package.md) 앱을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가할 위치를 스크린샷합니다.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="81f46-174">완료되면 "내보내기" 단추를 선택하고 프로비저닝 패키지가 만들어질 때까지 모든 프롬프트를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="81f46-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD에서 이 패키지의 내보내기 단추 스크린샷.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="81f46-176">배포</span><span class="sxs-lookup"><span data-stu-id="81f46-176">Deploy</span></span>

1. <span data-ttu-id="81f46-177">USB 케이블을 통해 HL2를 Windows 10 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="81f46-178">ARC 도구를 시작하고 **HoloLens 2를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 클린 리플래시 초기 화면](images/ARC2.png)

1. <span data-ttu-id="81f46-180">다음 화면에서 수동 패키지 **선택 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 정보 화면](images/arc_device_info.png)

1. <span data-ttu-id="81f46-182">이전에 다운로드한 .ffu 파일로 이동하고 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="81f46-183">경고 페이지에서 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 경고 화면](images/arc_warning.png)

1. <span data-ttu-id="81f46-185">ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="81f46-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="81f46-186">장치가 설치를 완료하고 백업을 부팅하면 PC에서 파일 탐색기로 이동하여 이전에 저장된 PPKG 파일을 장치 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창의 PC에 있는 PPKG 파일입니다.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="81f46-188">HoloLens 2에서 다음 단추 콤보를 눌러 프로비저닝 패키지를 실행합니다. **볼륨** 감소 및 **전원** 단추를 동시에 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="81f46-189">프로비저닝 패키지를 적용하라는 메시지가 표시되면 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="81f46-190">프로비저닝 패키지가 완료되면 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f46-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="81f46-191">그런 다음 공유 로컬 계정과 암호를 사용하여 장치에 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="81f46-192">유지 관리</span><span class="sxs-lookup"><span data-stu-id="81f46-192">Maintain</span></span>

<span data-ttu-id="81f46-193">이 구성에서는 위의 프로세스를 다시 시작하고 ARC 도구를 사용하여 장치를 리플래시하고 OS 및/또는 응용 프로그램을 업데이트하기 위해 새 PPKG를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81f46-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
