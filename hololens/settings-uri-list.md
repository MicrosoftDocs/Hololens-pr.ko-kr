---
title: 페이지 설정 표시 여부
description: PageVisibilityList에 대해 지원되는 URIS 목록과 HoloLens 혼합 현실 장치의 지침에 대한 최신 정보를 유지하세요.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: Holollens, Holollens 2, 액세스 할당, 키오스크, 설정 페이지입니다.
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327392"
---
# <span data-ttu-id="83148-104">페이지 설정 표시 여부</span><span class="sxs-lookup"><span data-stu-id="83148-104">Page Settings Visibility</span></span>

<span data-ttu-id="83148-105">HoloLens 디바이스의 관리 가능한 기능 중 하나는 [Settings/PageVisibilityList 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)을(를) 사용하여 설정 앱에 표시되는 페이지를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="83148-106">PageVisibilityList는 IT 관리자가 시스템 설정 앱의 특정 페이지를 표시 하거나 액세스 하지 못하도록 방지 하거나 지정 된 페이지를 제외한 모든 페이지에 대한 작업을 수행하는 데 사용 하는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="83148-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="83148-107">이 기능은 HoloLens 2 장치용 [Windows 홀로그램, 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2)에서만 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="83148-108">사용하려는 장치가 업데이트되었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="83148-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="83148-109">20개 이상의 새 SettingsURI가 곧 추가될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="83148-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="83148-110">[HoloLens 참가자](hololens-insider.md) 빌드에서 이 설정을 미리 보려면 [Windows 참가자 페이지 - 페이지 설정 표시 여부용 새 SettingsURI](hololens-insider.md#new-settingsuris-for-page-settings-visibility)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="83148-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="83148-111">다음 예제에서는 URI "ms-설정: network-wifi" 및 "ms-설정: Bluetooth"를 각각 포함 하는 정보 및 블루투스 페이지에만 액세스를 허용하는 정책을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="83148-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="83148-112">프로비저닝 패키지를 통해 설정하려면:</span><span class="sxs-lookup"><span data-stu-id="83148-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="83148-113">Windows 구성 디자이너에서 패키지를 만드는 동안 **정책 > 설정 > PageVisibilityList**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="83148-114">**`showonly:network-wifi;network-proxy;bluetooth`** 문자열을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="83148-115">프로비저닝 패키지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="83148-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="83148-116">장치에 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-116">Apply the package to your device.</span></span>
<span data-ttu-id="83148-117">프로비저닝 패키지를 만들고 적용하는 방법에 대한 자세한 내용은 [이 페이지](hololens-provisioning.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="83148-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="83148-118">이 작업은 OMA-URI를 사용하여 Intune을 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="83148-119">**사용자 지정 정책**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="83148-120">OMA-URI를 설정할 때 **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`** 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="83148-121">데이터 선택을 선택할 때: **문자열**</span><span class="sxs-lookup"><span data-stu-id="83148-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="83148-122">값을 입력할 때 **`showonly:network-wifi;network-proxy;bluetooth`** 을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="83148-123">장치가 있는 그룹에 사용자 지정 장치 구성을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="83148-124">Intune 그룹 및 장치 구성에 대한 자세한 내용은 [HoloLens MDM 구성](hololens-mdm-configure.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83148-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="83148-125">선택한 방법에 관계없이 이제 장치가 변경 내용을 수신해야 하며 사용자에게 다음과 같은 설정 앱이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83148-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![설정 앱에서 수정 중인 활성 시간의 스크린샷](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="83148-127">사용자가 선택한 페이지를 표시하거나 숨기도록 설정 앱 페이지를 구성하려면 HoloLens에서 사용 가능한 설정 URI를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="83148-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="83148-128">URI 설정</span><span class="sxs-lookup"><span data-stu-id="83148-128">Settings URIs</span></span>

<span data-ttu-id="83148-129">HoloLens 장치와 Windows 10 장치는 설정 앱 내에서 서로 다른 페이지 선택을 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="83148-130">이 페이지에서는 HoloLens에 있는 설정만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="83148-131">계정</span><span class="sxs-lookup"><span data-stu-id="83148-131">Accounts</span></span>
| <span data-ttu-id="83148-132">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-132">Settings page</span></span>           | <span data-ttu-id="83148-133">URI</span><span class="sxs-lookup"><span data-stu-id="83148-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="83148-134">로그인 옵션</span><span class="sxs-lookup"><span data-stu-id="83148-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="83148-135">Iris 등록</span><span class="sxs-lookup"><span data-stu-id="83148-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="83148-136">회사 또는 학교 계정에 액세스</span><span class="sxs-lookup"><span data-stu-id="83148-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="83148-137">장치</span><span class="sxs-lookup"><span data-stu-id="83148-137">Devices</span></span>
| <span data-ttu-id="83148-138">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-138">Settings page</span></span> | <span data-ttu-id="83148-139">URI</span><span class="sxs-lookup"><span data-stu-id="83148-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="83148-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="83148-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="83148-141">개인 정보</span><span class="sxs-lookup"><span data-stu-id="83148-141">Privacy</span></span>
| <span data-ttu-id="83148-142">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-142">Settings page</span></span>            | <span data-ttu-id="83148-143">URI</span><span class="sxs-lookup"><span data-stu-id="83148-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="83148-144">계정 정보</span><span class="sxs-lookup"><span data-stu-id="83148-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="83148-145">앱 진단</span><span class="sxs-lookup"><span data-stu-id="83148-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="83148-146">배경 앱</span><span class="sxs-lookup"><span data-stu-id="83148-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="83148-147">사용자 이동</span><span class="sxs-lookup"><span data-stu-id="83148-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="83148-148">파일 시스템</span><span class="sxs-lookup"><span data-stu-id="83148-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="83148-149">Calendar</span><span class="sxs-lookup"><span data-stu-id="83148-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="83148-150">통화 기록</span><span class="sxs-lookup"><span data-stu-id="83148-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="83148-151">연락처</span><span class="sxs-lookup"><span data-stu-id="83148-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="83148-152">기타 장치</span><span class="sxs-lookup"><span data-stu-id="83148-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="83148-153">문서</span><span class="sxs-lookup"><span data-stu-id="83148-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="83148-154">이메일</span><span class="sxs-lookup"><span data-stu-id="83148-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="83148-155">피드백 및 진단</span><span class="sxs-lookup"><span data-stu-id="83148-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="83148-156">위치</span><span class="sxs-lookup"><span data-stu-id="83148-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="83148-157">메시지</span><span class="sxs-lookup"><span data-stu-id="83148-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="83148-158">마이크</span><span class="sxs-lookup"><span data-stu-id="83148-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="83148-159">알림</span><span class="sxs-lookup"><span data-stu-id="83148-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="83148-160">사진</span><span class="sxs-lookup"><span data-stu-id="83148-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="83148-161">무선</span><span class="sxs-lookup"><span data-stu-id="83148-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="83148-162">음성 명령</span><span class="sxs-lookup"><span data-stu-id="83148-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="83148-163">작업</span><span class="sxs-lookup"><span data-stu-id="83148-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="83148-164">비디오</span><span class="sxs-lookup"><span data-stu-id="83148-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="83148-165">음성 활성화</span><span class="sxs-lookup"><span data-stu-id="83148-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="83148-166">카메라</span><span class="sxs-lookup"><span data-stu-id="83148-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="83148-167">네트워크 및 인터넷</span><span class="sxs-lookup"><span data-stu-id="83148-167">Network & Internet</span></span>
| <span data-ttu-id="83148-168">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-168">Settings page</span></span> | <span data-ttu-id="83148-169">URI</span><span class="sxs-lookup"><span data-stu-id="83148-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="83148-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="83148-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="83148-171">VPN</span><span class="sxs-lookup"><span data-stu-id="83148-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="83148-172">Proxy (프록시)</span><span class="sxs-lookup"><span data-stu-id="83148-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="83148-173">System</span><span class="sxs-lookup"><span data-stu-id="83148-173">System</span></span>
| <span data-ttu-id="83148-174">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-174">Settings page</span></span>      | <span data-ttu-id="83148-175">URI</span><span class="sxs-lookup"><span data-stu-id="83148-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="83148-176">공유 환경</span><span class="sxs-lookup"><span data-stu-id="83148-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="83148-177">색</span><span class="sxs-lookup"><span data-stu-id="83148-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="83148-178">알림 및 동작</span><span class="sxs-lookup"><span data-stu-id="83148-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="83148-179">저장 공간</span><span class="sxs-lookup"><span data-stu-id="83148-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="83148-180">시간 및 언어</span><span class="sxs-lookup"><span data-stu-id="83148-180">Time & Language</span></span>
| <span data-ttu-id="83148-181">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-181">Settings page</span></span> | <span data-ttu-id="83148-182">URI</span><span class="sxs-lookup"><span data-stu-id="83148-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="83148-183">영역</span><span class="sxs-lookup"><span data-stu-id="83148-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="83148-184">외국어</span><span class="sxs-lookup"><span data-stu-id="83148-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="83148-185">업데이트 및 보안</span><span class="sxs-lookup"><span data-stu-id="83148-185">Update & Security</span></span>
| <span data-ttu-id="83148-186">설정 페이지</span><span class="sxs-lookup"><span data-stu-id="83148-186">Settings page</span></span>                         | <span data-ttu-id="83148-187">URI</span><span class="sxs-lookup"><span data-stu-id="83148-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="83148-188">Windows 참가자 프로그램</span><span class="sxs-lookup"><span data-stu-id="83148-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="83148-189">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="83148-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="83148-190">1</span><span class="sxs-lookup"><span data-stu-id="83148-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="83148-191">1</span><span class="sxs-lookup"><span data-stu-id="83148-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="83148-192">Windows 업데이트 -업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="83148-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="83148-193">고급 옵션</span><span class="sxs-lookup"><span data-stu-id="83148-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="83148-194">1</sup> 다음 두 URI는 실제로 **고급 옵션** 또는 **옵션** 페이지로 이동하지 않고 기본 Windows Update 페이지만 차단 또는 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="83148-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="83148-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="83148-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="83148-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="83148-197">Windows 10 설정 URI의 전체 목록은 [시작 설정](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83148-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
