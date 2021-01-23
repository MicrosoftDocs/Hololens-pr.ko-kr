---
title: 일반적인 시나리오 - 오프라인 보안 HoloLens 2
description: HoloLens 장치를 프로비전하여 오프라인 보안 배포 및 앱 배포 시나리오를 설정하는 방법을 설명합니다.
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283419"
---
# <span data-ttu-id="e9e05-104">일반적인 시나리오 - 오프라인 보안 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e9e05-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="e9e05-105">개요</span><span class="sxs-lookup"><span data-stu-id="e9e05-105">Overview</span></span>

<span data-ttu-id="e9e05-106">이 가이드에서는 다음과 같은 제한 사항으로 보안 환경에서 사용하기 위해 HoloLens 2를 잠그는 샘플 프로비저닝 패키지를 적용하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="e9e05-107">WiFi를 사용하지 않도록 설정.</span><span class="sxs-lookup"><span data-stu-id="e9e05-107">Disable WiFi.</span></span>
-   <span data-ttu-id="e9e05-108">BlueTooth를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="e9e05-109">마이크를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-109">Disable Microphones.</span></span>
-   <span data-ttu-id="e9e05-110">프로비저닝 패키지 추가 또는 제거를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="e9e05-111">어떤 사용자도 위의 제한된 구성 요소를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="e9e05-112">준비</span><span class="sxs-lookup"><span data-stu-id="e9e05-112">Prepare</span></span>

<span data-ttu-id="e9e05-113">Windows 10 PC 설치</span><span class="sxs-lookup"><span data-stu-id="e9e05-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="e9e05-114">[최신 HoloLens 2 OS 파일을 PC에](https://aka.ms/hololens2download) 직접 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="e9e05-115">이 구성에 대한 지원은 빌드 19041.1117 이상에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="e9e05-116">[Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC로 ARC(Advanced Recovery Companion) 도구 다운로드/설치</span><span class="sxs-lookup"><span data-stu-id="e9e05-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="e9e05-117">Microsoft Store에서 PC로 최신 [WCD(Windows 구성 디자이너)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="e9e05-118">[프로젝트 OfflineSecureHL2_Sample](https://aka.ms/HoloLensDocs-SecureOfflineSample) 폴더를 다운로드하여 PPKG를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="e9e05-119">[PPKG 배포를 위해](app-deploy-provisioning-package.md)오프라인 비즈니스 응용 프로그램을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="e9e05-120">구성</span><span class="sxs-lookup"><span data-stu-id="e9e05-120">Configure</span></span>

<span data-ttu-id="e9e05-121">보안 구성 프로비저닝 패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="e9e05-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="e9e05-122">PC에서 WCD 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="e9e05-123">파일 **-> 열기 프로젝트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e05-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="e9e05-124">이전에 저장한 OfflineSecureHL2_Sample 폴더의 위치로 이동한 후 다음을 OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="e9e05-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="e9e05-125">프로젝트가 열리면 사용 가능한 사용자 지정 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![WCD에서 열 수 있는 구성 패키지 스크린샷](images/offline-secure-sample-wcd.png)

<span data-ttu-id="e9e05-127">이 프로비저닝 패키지에 설정된 구성:</span><span class="sxs-lookup"><span data-stu-id="e9e05-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="e9e05-128">항목</span><span class="sxs-lookup"><span data-stu-id="e9e05-128">Item</span></span>                                                |     <span data-ttu-id="e9e05-129">설정</span><span class="sxs-lookup"><span data-stu-id="e9e05-129">Setting</span></span>                       |     <span data-ttu-id="e9e05-130">설명</span><span class="sxs-lookup"><span data-stu-id="e9e05-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="e9e05-131">계정/사용자</span><span class="sxs-lookup"><span data-stu-id="e9e05-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="e9e05-132">로컬 사용자 이름 & 암호</span><span class="sxs-lookup"><span data-stu-id="e9e05-132">Local User Name & Password</span></span>    |     <span data-ttu-id="e9e05-133">이러한 오프라인 장치의 경우 디바이스의 모든 사용자가 단일 사용자 이름 및 암호를 설정하고 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="e9e05-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="e9e05-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="e9e05-135">True</span><span class="sxs-lookup"><span data-stu-id="e9e05-135">True</span></span>                          |     <span data-ttu-id="e9e05-136">초기 장치 설정 중에만 보정 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="e9e05-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="e9e05-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="e9e05-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="e9e05-138">True</span><span class="sxs-lookup"><span data-stu-id="e9e05-138">True</span></span>                          |     <span data-ttu-id="e9e05-139">초기 장치 설정 중에 장치 교육 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="e9e05-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="e9e05-140">First Experience / HoloLens /WiFi</span><span class="sxs-lookup"><span data-stu-id="e9e05-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="e9e05-141">True</span><span class="sxs-lookup"><span data-stu-id="e9e05-141">True</span></span>                          |     <span data-ttu-id="e9e05-142">초기 Wi-Fi 구성 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="e9e05-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="e9e05-143">정책/연결/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="e9e05-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="e9e05-144">아니오</span><span class="sxs-lookup"><span data-stu-id="e9e05-144">No</span></span>                            |     <span data-ttu-id="e9e05-145">비동기 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e9e05-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="e9e05-146">정책/환경/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="e9e05-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="e9e05-147">아니오</span><span class="sxs-lookup"><span data-stu-id="e9e05-147">No</span></span>                            |     <span data-ttu-id="e9e05-148">Cortana를 사용하지 않도록 설정(마이크를 사용하지 않도록 설정한 후 잠재적인 문제를 제거하기 위해)</span><span class="sxs-lookup"><span data-stu-id="e9e05-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="e9e05-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="e9e05-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="e9e05-150">예</span><span class="sxs-lookup"><span data-stu-id="e9e05-150">Yes</span></span>                           |     <span data-ttu-id="e9e05-151">마이크를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e9e05-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="e9e05-152">정책/개인 정보/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="e9e05-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="e9e05-153">강제 거부</span><span class="sxs-lookup"><span data-stu-id="e9e05-153">Force deny</span></span>                    |     <span data-ttu-id="e9e05-154">앱이 위치 데이터에 액세스하지 못하게 방지합니다(위치 추적을 사용하지 않도록 설정한 이후의 잠재적인 문제 제거)</span><span class="sxs-lookup"><span data-stu-id="e9e05-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="e9e05-155">정책/개인 정보/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="e9e05-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="e9e05-156">강제 거부</span><span class="sxs-lookup"><span data-stu-id="e9e05-156">Force deny</span></span>                    |     <span data-ttu-id="e9e05-157">앱이 마이크에 액세스하지 못하게 방지(마이크를 사용하지 않도록 설정한 경우 잠재적인 문제를 제거하기 위해)</span><span class="sxs-lookup"><span data-stu-id="e9e05-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="e9e05-158">정책/보안/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="e9e05-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="e9e05-159">아니오</span><span class="sxs-lookup"><span data-stu-id="e9e05-159">No</span></span>                            |     <span data-ttu-id="e9e05-160">잠긴 정책을 다시 설정하려고 할 수 있는 프로비저닝 패키지를 추가하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="e9e05-161">정책/보안/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="e9e05-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="e9e05-162">아니오</span><span class="sxs-lookup"><span data-stu-id="e9e05-162">No</span></span>                            |     <span data-ttu-id="e9e05-163">잠긴 이 프로비저닝 패키지를 제거하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="e9e05-164">정책/시스템/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="e9e05-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="e9e05-165">아니오</span><span class="sxs-lookup"><span data-stu-id="e9e05-165">No</span></span>                            |     <span data-ttu-id="e9e05-166">디바이스가 위치 데이터를 추적하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="e9e05-167">정책/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="e9e05-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="e9e05-168">아니오</span><span class="sxs-lookup"><span data-stu-id="e9e05-168">No</span></span>                            |     <span data-ttu-id="e9e05-169">이 기능을 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e9e05-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="e9e05-170">런타임 설정에서 **계정/사용자/사용자 이름 선택: Holo /Password**</span><span class="sxs-lookup"><span data-stu-id="e9e05-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="e9e05-171">암호를 메모하고 원하는 경우 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9e05-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="e9e05-172">UniversalAppInstall/UserContextApp으로 이동하여 이러한 장치에 배포할 [LOB](app-deploy-provisioning-package.md) 앱을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가할 위치의 스크린샷.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="e9e05-174">완료되면 "내보내기" 단추를 선택하고 프로비저닝 패키지가 만들어질 때까지 모든 프롬프트를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="e9e05-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD에서 이 패키지의 내보내기 단추 스크린샷.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="e9e05-176">배포</span><span class="sxs-lookup"><span data-stu-id="e9e05-176">Deploy</span></span>

1. <span data-ttu-id="e9e05-177">USB 케이블을 통해 HL2를 Windows 10 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="e9e05-178">ARC 도구를 시작하고 **HoloLens 2 선택**</span><span class="sxs-lookup"><span data-stu-id="e9e05-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="e9e05-179">다음 화면에서 수동 패키지 **선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e05-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="e9e05-180">이전에 다운로드한 .ffu 파일로 이동한 후 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e05-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="e9e05-181">경고 페이지에서 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e05-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="e9e05-182">ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="e9e05-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="e9e05-183">장치가 설치를 완료하고 백업을 부팅하면 PC에서 파일 탐색기로 이동하여 이전에 저장된 PPKG 파일을 장치 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창의 PC에 있는 PPKG 파일입니다.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="e9e05-185">HoloLens 2에서 다음 단추 콤보를 눌러 프로비저닝 패키지를 실행합니다. **볼륨** 감소 및 **전원** 단추를 동시에 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="e9e05-186">프로비저닝 패키지를 적용하라는 메시지가 표시되면 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e05-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="e9e05-187">프로비저닝 패키지가 완료되면 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e05-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="e9e05-188">그런 다음 공유 로컬 계정 및 암호를 사용하여 장치에 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="e9e05-189">유지 관리</span><span class="sxs-lookup"><span data-stu-id="e9e05-189">Maintain</span></span>

<span data-ttu-id="e9e05-190">이 구성에서는 위의 프로세스를 다시 시작하고 ARC 도구를 사용하여 장치를 다시 래시한 다음 OS 및/또는 응용 프로그램을 업데이트하기 위해 새 PPKG를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e05-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

