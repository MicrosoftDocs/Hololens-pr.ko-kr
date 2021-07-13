---
title: 페이지 설정 표시
description: PageVisibilityList에 대해 지원되는 URI 목록과 HoloLens 혼합 현실 장치에 대한 지침의 최신 정보를 확인하세요.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 할당된 액세스, 키오스크, 설정 페이지
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924335"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="4d8e8-104">페이지 설정 표시</span><span class="sxs-lookup"><span data-stu-id="4d8e8-104">Page Settings Visibility</span></span>

<span data-ttu-id="4d8e8-105">HoloLens 장치에 대한 관리 가능한 기능 중 하나는 [설정/PageVisibilityList 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)을 사용하여 설정 앱 내에 표시되는 페이지를 제한하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="4d8e8-106">PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지가 표시 또는 액세스되지 않도록 방지하거나 지정된 페이지를 제외한 모든 페이지에 대해서도 표시 또는 액세스를 방지할 수 있도록 하는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8e8-107">이 기능은 HoloLens 2 장치의 [Windows Holographic, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="4d8e8-108">이 기능을 사용하려는 장치가 업데이트되었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="4d8e8-109">다음 예제에서는 각각 URI "ms-settings:network-wifi" 및 "ms-settings:bluetooth"를 포함하는 정보 및 Bluetooth 페이지에만 액세스를 허용하는 정책을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="4d8e8-110">프로비전 패키지를 통해 설정하려면:</span><span class="sxs-lookup"><span data-stu-id="4d8e8-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="4d8e8-111">Windows 구성 디자이너에서 패키지를 만드는 동안 **정책> 설정 > PageVisibilityList** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="4d8e8-112">다음 문자열을 입력합니다. **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="4d8e8-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="4d8e8-113">프로비전 패키지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="4d8e8-114">패키지를 장치에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-114">Apply the package to your device.</span></span>
<span data-ttu-id="4d8e8-115">프로비전 패키지를 만들고 적용하는 방법에 대한 자세한 내용은 [이 페이지](hololens-provisioning.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="4d8e8-116">이 작업은 OMA-URI를 사용하여 Intune을 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="4d8e8-117">**사용자 지정 정책** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="4d8e8-118">OMA-URI를 설정할 때 다음 문자열을 사용합니다. **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="4d8e8-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="4d8e8-119">데이터 선택을 선택할 때 다음을 선택합니다. **문자열**</span><span class="sxs-lookup"><span data-stu-id="4d8e8-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="4d8e8-120">값을 입력할 때 다음을 사용합니다. **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="4d8e8-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="4d8e8-121">장치를 포함시킬 그룹에 사용자 지정 장치 구성을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="4d8e8-122">Intune 그룹 및 장치 구성에 대한 자세한 내용은 [HoloLens MDM 구성](hololens-mdm-configure.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="4d8e8-123">선택한 방법에 관계없이 이제 장치가 변경 내용을 수신해야 하고 사용자에게 다음과 같은 설정 앱이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![설정 앱에서 수정되는 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="4d8e8-125">사용자가 선택한 페이지를 표시하거나 숨기도록 설정 앱 페이지를 구성하려면 HoloLens에서 사용 가능한 설정 URI를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="4d8e8-126">URI 설정</span><span class="sxs-lookup"><span data-stu-id="4d8e8-126">Settings URIs</span></span>

<span data-ttu-id="4d8e8-127">HoloLens 장치와 Windows 10 장치는 설정 앱 내에서 선택할 수 있는 페이지가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="4d8e8-128">이 페이지에서는 HoloLens에 있는 설정만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="4d8e8-129">계정</span><span class="sxs-lookup"><span data-stu-id="4d8e8-129">Accounts</span></span>
| <span data-ttu-id="4d8e8-130">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-130">Settings page</span></span>           | <span data-ttu-id="4d8e8-131">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="4d8e8-132">회사 또는 학교 액세스</span><span class="sxs-lookup"><span data-stu-id="4d8e8-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="4d8e8-133">아이리스 등록</span><span class="sxs-lookup"><span data-stu-id="4d8e8-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="4d8e8-134">로그인 옵션</span><span class="sxs-lookup"><span data-stu-id="4d8e8-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="4d8e8-135">앱</span><span class="sxs-lookup"><span data-stu-id="4d8e8-135">Apps</span></span>
| <span data-ttu-id="4d8e8-136">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-136">Settings page</span></span> | <span data-ttu-id="4d8e8-137">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="4d8e8-138">앱 및 기능<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="4d8e8-139">앱 및 기능 > 고급 옵션 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="4d8e8-140">앱 및 기능 > 오프라인 지도 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="4d8e8-141">앱 및 기능 > 오프라인 지도 > 지도 다운로드 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="4d8e8-142">디바이스</span><span class="sxs-lookup"><span data-stu-id="4d8e8-142">Devices</span></span>
| <span data-ttu-id="4d8e8-143">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-143">Settings page</span></span> | <span data-ttu-id="4d8e8-144">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="4d8e8-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="4d8e8-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="4d8e8-146">마우스 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="4d8e8-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="4d8e8-148">개인 정보 취급 방침</span><span class="sxs-lookup"><span data-stu-id="4d8e8-148">Privacy</span></span>
| <span data-ttu-id="4d8e8-149">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-149">Settings page</span></span>            | <span data-ttu-id="4d8e8-150">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="4d8e8-151">계정 정보</span><span class="sxs-lookup"><span data-stu-id="4d8e8-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="4d8e8-152">앱 진단</span><span class="sxs-lookup"><span data-stu-id="4d8e8-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="4d8e8-153">배경 앱</span><span class="sxs-lookup"><span data-stu-id="4d8e8-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="4d8e8-154">달력</span><span class="sxs-lookup"><span data-stu-id="4d8e8-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="4d8e8-155">통화 기록</span><span class="sxs-lookup"><span data-stu-id="4d8e8-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="4d8e8-156">카메라</span><span class="sxs-lookup"><span data-stu-id="4d8e8-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="4d8e8-157">연락처</span><span class="sxs-lookup"><span data-stu-id="4d8e8-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="4d8e8-158">피드백 및 진단</span><span class="sxs-lookup"><span data-stu-id="4d8e8-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="4d8e8-159">문서</span><span class="sxs-lookup"><span data-stu-id="4d8e8-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="4d8e8-160">메일</span><span class="sxs-lookup"><span data-stu-id="4d8e8-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="4d8e8-161">파일 시스템</span><span class="sxs-lookup"><span data-stu-id="4d8e8-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="4d8e8-162">일반 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="4d8e8-163">수동 입력 및 키 입력 개인 설정 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="4d8e8-164">위치</span><span class="sxs-lookup"><span data-stu-id="4d8e8-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="4d8e8-165">메시징</span><span class="sxs-lookup"><span data-stu-id="4d8e8-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="4d8e8-166">마이크</span><span class="sxs-lookup"><span data-stu-id="4d8e8-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="4d8e8-167">Motion <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="4d8e8-168">알림</span><span class="sxs-lookup"><span data-stu-id="4d8e8-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="4d8e8-169">기타 디바이스</span><span class="sxs-lookup"><span data-stu-id="4d8e8-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="4d8e8-170">사진</span><span class="sxs-lookup"><span data-stu-id="4d8e8-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="4d8e8-171">무선</span><span class="sxs-lookup"><span data-stu-id="4d8e8-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="4d8e8-172">스크린샷 테두리 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="4d8e8-173">스크린샷 및 앱 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="4d8e8-174">Speech</span><span class="sxs-lookup"><span data-stu-id="4d8e8-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="4d8e8-175">작업</span><span class="sxs-lookup"><span data-stu-id="4d8e8-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="4d8e8-176">사용자 이동</span><span class="sxs-lookup"><span data-stu-id="4d8e8-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="4d8e8-177">동영상</span><span class="sxs-lookup"><span data-stu-id="4d8e8-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="4d8e8-178">음성 활성화</span><span class="sxs-lookup"><span data-stu-id="4d8e8-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="4d8e8-179">네트워크 및 인터넷</span><span class="sxs-lookup"><span data-stu-id="4d8e8-179">Network & Internet</span></span>
| <span data-ttu-id="4d8e8-180">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-180">Settings page</span></span> | <span data-ttu-id="4d8e8-181">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="4d8e8-182">비행기 모드 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="4d8e8-183">프록시</span><span class="sxs-lookup"><span data-stu-id="4d8e8-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="4d8e8-184">VPN</span><span class="sxs-lookup"><span data-stu-id="4d8e8-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="4d8e8-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="4d8e8-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="4d8e8-186">시스템</span><span class="sxs-lookup"><span data-stu-id="4d8e8-186">System</span></span>
| <span data-ttu-id="4d8e8-187">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-187">Settings page</span></span>      | <span data-ttu-id="4d8e8-188">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="4d8e8-189">배터리 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="4d8e8-190">배터리 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="4d8e8-191">색</span><span class="sxs-lookup"><span data-stu-id="4d8e8-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="4d8e8-192">홀로그램 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="4d8e8-193">보정 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="4d8e8-194">알림 및 작업</span><span class="sxs-lookup"><span data-stu-id="4d8e8-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="4d8e8-195">Shared Experiences</span><span class="sxs-lookup"><span data-stu-id="4d8e8-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="4d8e8-196">소리 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="4d8e8-197">소리 > 앱 볼륨 및 장치 기본 설정 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="4d8e8-198">소리 > 사운드 장치 관리 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="4d8e8-199">스토리지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="4d8e8-200">저장소 > 저장소 센스 구성 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="4d8e8-201">시간 및 언어</span><span class="sxs-lookup"><span data-stu-id="4d8e8-201">Time & Language</span></span>
| <span data-ttu-id="4d8e8-202">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-202">Settings page</span></span> | <span data-ttu-id="4d8e8-203">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="4d8e8-204">날짜 및 시간 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="4d8e8-205">키보드 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="4d8e8-206">언어 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="4d8e8-207">언어 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="4d8e8-208">언어</span><span class="sxs-lookup"><span data-stu-id="4d8e8-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="4d8e8-209">지역</span><span class="sxs-lookup"><span data-stu-id="4d8e8-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="4d8e8-210">업데이트 및 보안</span><span class="sxs-lookup"><span data-stu-id="4d8e8-210">Update & Security</span></span>
| <span data-ttu-id="4d8e8-211">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="4d8e8-211">Settings page</span></span>                         | <span data-ttu-id="4d8e8-212">URI</span><span class="sxs-lookup"><span data-stu-id="4d8e8-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="4d8e8-213">고급 옵션</span><span class="sxs-lookup"><span data-stu-id="4d8e8-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="4d8e8-214">초기화 및 복구 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4d8e8-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="4d8e8-215"> Windows 참가자 프로그램</span><span class="sxs-lookup"><span data-stu-id="4d8e8-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="4d8e8-216">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="4d8e8-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="4d8e8-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="4d8e8-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="4d8e8-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="4d8e8-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="4d8e8-219">Windows 업데이트 - 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="4d8e8-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="4d8e8-220"><sup>1</sup> -Windows Holographic 버전 21H1 이전 버전의 경우, 다음 두 URI는 실제로 **고급 옵션** 또는 **옵션** 페이지로 이동하지 않습니다. 기본 Windows Update 페이지를 차단하거나 표시할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="4d8e8-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="4d8e8-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="4d8e8-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="4d8e8-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="4d8e8-223"><sup>2</sup> -Windows Holographic 21H1 이상에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="4d8e8-224">Windows 10 설정 URI의 전체 목록은 [시작 설정](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d8e8-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
