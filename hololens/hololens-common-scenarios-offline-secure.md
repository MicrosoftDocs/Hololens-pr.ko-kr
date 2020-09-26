---
title: 일반적인 시나리오 – 오프 라인 보안 HoloLens 2
description: 프로 비전을 통한 오프 라인 보안 배포 및 앱 배포입니다.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080520"
---
# <span data-ttu-id="52ace-104">일반적인 시나리오 – 오프 라인 보안 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="52ace-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="52ace-105">개요</span><span class="sxs-lookup"><span data-stu-id="52ace-105">Overview</span></span>
<span data-ttu-id="52ace-106">이 가이드에서는 다음 제한 사항으로 보안 환경에서 사용 하기 위해 HoloLens 2를 잠그는 샘플 프로비저닝 패키지를 적용 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="52ace-107">WiFi를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-107">Disable WiFi.</span></span>
-   <span data-ttu-id="52ace-108">BlueTooth를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="52ace-109">마이크를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-109">Disable Microphones.</span></span>
-   <span data-ttu-id="52ace-110">배포 패키지를 추가 하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="52ace-111">모든 제한 된 구성 요소를 사용할 수 있는 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="52ace-112">준비</span><span class="sxs-lookup"><span data-stu-id="52ace-112">Prepare</span></span> 
<span data-ttu-id="52ace-113">Windows 10 PC 설치</span><span class="sxs-lookup"><span data-stu-id="52ace-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="52ace-114">[최신 HoloLens 2 OS 파일](https://aka.ms/hololens2download) 을 PC에 직접 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="52ace-115">이 구성에 대 한 지원은 빌드 19041.1117 이상에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="52ace-116">[Microsoft Store에서](https://www.microsoft.com/store/productId/9P74Z35SFRS8) PC에 고급 복구 도우미 (ARC) 도구 다운로드/설치</span><span class="sxs-lookup"><span data-stu-id="52ace-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="52ace-117">PC에 Microsoft Store에서 최신 [Windows 구성 디자이너 (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 도구를 다운로드/설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="52ace-118">[프로젝트 파일과 함께 OfflineSecureHL2_Sample 폴더를 다운로드](https://aka.ms/HoloLensDocs-SecureOfflineSample) 하 여 ppkg을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="52ace-119">[PPKG 배포에 대 한 오프 라인 비즈니스 응용 프로그램](app-deploy-provisioning-package.md)을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="52ace-120">구성</span><span class="sxs-lookup"><span data-stu-id="52ace-120">Configure</span></span>
<span data-ttu-id="52ace-121">보안 구성 프로비저닝 패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="52ace-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="52ace-122">PC에서 WCD 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="52ace-123">**파일 >를 선택 하 여 프로젝트를 엽니다**.</span><span class="sxs-lookup"><span data-stu-id="52ace-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="52ace-124">이전에 저장 한 OfflineSecureHL2_Sample 폴더의 위치로 이동 하 고 다음을 선택 합니다. OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="52ace-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="52ace-125">프로젝트가 열리고 이제 사용 가능한 사용자 지정 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![WCD에서 연 구성 패키지 스크린샷](images/offline-secure-sample-wcd.png)

<span data-ttu-id="52ace-127">이 프로비저닝 패키지에 설정 되는 구성:</span><span class="sxs-lookup"><span data-stu-id="52ace-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="52ace-128">항목</span><span class="sxs-lookup"><span data-stu-id="52ace-128">Item</span></span>                                                |     <span data-ttu-id="52ace-129">설정</span><span class="sxs-lookup"><span data-stu-id="52ace-129">Setting</span></span>                       |     <span data-ttu-id="52ace-130">설명</span><span class="sxs-lookup"><span data-stu-id="52ace-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="52ace-131">계정/사용자</span><span class="sxs-lookup"><span data-stu-id="52ace-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="52ace-132">로컬 사용자 이름 & 암호</span><span class="sxs-lookup"><span data-stu-id="52ace-132">Local User Name & Password</span></span>    |     <span data-ttu-id="52ace-133">이러한 오프 라인 장치의 경우 모든 장치 사용자가 단일 사용자 이름 및 암호를 설정 하 고 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="52ace-134">첫 번째 환경/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="52ace-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="52ace-135">True</span><span class="sxs-lookup"><span data-stu-id="52ace-135">True</span></span>                          |     <span data-ttu-id="52ace-136">초기 장치를 설정 하는 동안에만 보정 생략</span><span class="sxs-lookup"><span data-stu-id="52ace-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="52ace-137">첫 번째 환경/HoloLens/SkipTraining 교육</span><span class="sxs-lookup"><span data-stu-id="52ace-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="52ace-138">True</span><span class="sxs-lookup"><span data-stu-id="52ace-138">True</span></span>                          |     <span data-ttu-id="52ace-139">초기 장치를 설정 하는 동안 디바이스 교육 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="52ace-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="52ace-140">첫 번째 환경/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="52ace-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="52ace-141">True</span><span class="sxs-lookup"><span data-stu-id="52ace-141">True</span></span>                          |     <span data-ttu-id="52ace-142">초기 장치를 설정 하는 동안 Wi-fi 구성 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="52ace-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="52ace-143">정책/연결/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="52ace-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="52ace-144">아니오</span><span class="sxs-lookup"><span data-stu-id="52ace-144">No</span></span>                            |     <span data-ttu-id="52ace-145">Bluetooth 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="52ace-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="52ace-146">정책/경험/o s p s Cortana</span><span class="sxs-lookup"><span data-stu-id="52ace-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="52ace-147">아니오</span><span class="sxs-lookup"><span data-stu-id="52ace-147">No</span></span>                            |     <span data-ttu-id="52ace-148">Cortana를 사용 하지 않도록 설정 (마이크를 사용 하지 않도록 설정 된 후 발생할 수 있는 문제 제거)</span><span class="sxs-lookup"><span data-stu-id="52ace-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="52ace-149">정책/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="52ace-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="52ace-150">예</span><span class="sxs-lookup"><span data-stu-id="52ace-150">Yes</span></span>                           |     <span data-ttu-id="52ace-151">마이크 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="52ace-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="52ace-152">정책/개인 정보/통합 Appsaccesslocation</span><span class="sxs-lookup"><span data-stu-id="52ace-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="52ace-153">강제 거부</span><span class="sxs-lookup"><span data-stu-id="52ace-153">Force deny</span></span>                    |     <span data-ttu-id="52ace-154">앱이 위치 데이터에 액세스 하지 못하도록 방지 (위치 추적을 사용 하지 않도록 설정 된 이후 발생할 수 있는 문제 제거)</span><span class="sxs-lookup"><span data-stu-id="52ace-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="52ace-155">정책/개인 정보/통합 Appsaccessmicrophone</span><span class="sxs-lookup"><span data-stu-id="52ace-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="52ace-156">강제 거부</span><span class="sxs-lookup"><span data-stu-id="52ace-156">Force deny</span></span>                    |     <span data-ttu-id="52ace-157">앱이 마이크에 액세스 하지 못하도록 방지 (마이크를 사용 하지 않도록 설정 된 후 발생할 수 있는 문제 제거)</span><span class="sxs-lookup"><span data-stu-id="52ace-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="52ace-158">정책/보안/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="52ace-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="52ace-159">아니오</span><span class="sxs-lookup"><span data-stu-id="52ace-159">No</span></span>                            |     <span data-ttu-id="52ace-160">잠긴 정책을 재정의 하려고 할 수 있는 프로비저닝 패키지를 추가 하는 것을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="52ace-161">정책/보안/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="52ace-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="52ace-162">아니오</span><span class="sxs-lookup"><span data-stu-id="52ace-162">No</span></span>                            |     <span data-ttu-id="52ace-163">이 잠긴 프로비저닝 패키지를 아무도 제거 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="52ace-164">정책/시스템/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="52ace-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="52ace-165">아니오</span><span class="sxs-lookup"><span data-stu-id="52ace-165">No</span></span>                            |     <span data-ttu-id="52ace-166">장치가 위치 데이터를 추적 하려고 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="52ace-167">정책/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="52ace-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="52ace-168">아니오</span><span class="sxs-lookup"><span data-stu-id="52ace-168">No</span></span>                            |     <span data-ttu-id="52ace-169">Wi-fi 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="52ace-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="52ace-170">런타임 설정에서 **계정/사용자/사용자 이름: Holo/암호** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="52ace-171">원하는 경우 암호와 재설정을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="52ace-172">UniversalAppInstall/UserContextApp으로 이동 하 여 이러한 장치에 배포 하는 [LOB 앱을 구성](app-deploy-provisioning-package.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD에서 앱을 추가 하는 위치 스크린샷](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="52ace-174">완료 되 면 "내보내기" 단추를 선택 하 고 프로 비전 패키지를 만들 때까지 모든 메시지를 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD의이 패키지에 대 한 내보내기 단추 스크린샷](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="52ace-176">배포</span><span class="sxs-lookup"><span data-stu-id="52ace-176">Deploy</span></span>
1. <span data-ttu-id="52ace-177">USB 케이블을 통해 HL2를 Windows 10 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="52ace-178">원호 도구를 시작 하 고 **HoloLens 2** 선택</span><span class="sxs-lookup"><span data-stu-id="52ace-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="52ace-179">다음 화면에서 **수동 패키지 선택 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="52ace-180">이전에 다운로드 한 ffu 파일로 이동 하 고 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="52ace-181">경고 페이지에서 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="52ace-182">ARC 도구가 HoloLens 2 OS 설치를 완료할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="52ace-183">장치가 설치 및 부팅을 완료 하면 PC에서 파일 탐색기로 이동 하 여 이전에 저장 한 PPKG 파일을 장치 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![파일 탐색기 창에 있는 PC의 PPKG 파일](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="52ace-185">HoloLens 2에서 다음 단추 콤보를 눌러 프로비저닝 패키지를 실행 합니다. **볼륨 작게** 및 **전원 단추** 를 동시에 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="52ace-186">프로비저닝 패키지를 적용 하 라는 메시지가 표시 되 면 **확인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="52ace-187">프로비저닝 패키지가 완료 되 면 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="52ace-188">그런 다음 공유 로컬 계정 및 암호를 사용 하 여 장치에 로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="52ace-189">유지 관리</span><span class="sxs-lookup"><span data-stu-id="52ace-189">Maintain</span></span>
<span data-ttu-id="52ace-190">이 구성을 사용 하는 경우 위의 프로세스를 다시 시작 하 고 ARC 도구로 장치를 reflash 새 PPKG을 적용 하 여 OS 및/또는 응용 프로그램에 대 한 업데이트를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="52ace-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

