---
title: Microsoft HoloLens에 대한 참가자 미리 보기
description: 참가자 빌드를 시작하고 HoloLens 대한 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공하는 방법을 알아봅니다.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636096"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="9803c-103">Microsoft HoloLens에 대한 참가자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="9803c-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="9803c-104">HoloLens 위한 최신 Insider Preview 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="9803c-105">HoloLens 대한 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 [간단하게 시작하고](hololens-insider.md#start-receiving-insider-builds) 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="9803c-106">Windows 참가자 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="9803c-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="9803c-107">새 기능을 다시 Windows 위해 플라이팅을 시작하게 되어 기쁩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="9803c-108">새 빌드는 최신 업데이트를 위해 개발 및 베타 채널로 플라이팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="9803c-109">Windows Insider 빌드에 더 많은 기능 및 업데이트를 추가함에 따라 이 페이지를 계속 업데이트할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="9803c-110">이러한 업데이트를 현실에 혼합할 준비가 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="9803c-111">기능</span><span class="sxs-lookup"><span data-stu-id="9803c-111">Feature</span></span>                 | <span data-ttu-id="9803c-112">Description</span><span class="sxs-lookup"><span data-stu-id="9803c-112">Description</span></span>                | <span data-ttu-id="9803c-113">사용자 또는 시나리오</span><span class="sxs-lookup"><span data-stu-id="9803c-113">User or Scenario</span></span> | <span data-ttu-id="9803c-114">빌드 소개</span><span class="sxs-lookup"><span data-stu-id="9803c-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="9803c-115">HoloLens 세부 정보를 보고하기 위한 CSP 변경 내용</span><span class="sxs-lookup"><span data-stu-id="9803c-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="9803c-116">데이터를 쿼리하는 에 대한 새 CSP</span><span class="sxs-lookup"><span data-stu-id="9803c-116">New CSPs for to query data</span></span> | <span data-ttu-id="9803c-117">IT 관리자</span><span class="sxs-lookup"><span data-stu-id="9803c-117">IT Admins</span></span>    | <span data-ttu-id="9803c-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="9803c-118">20348.1403</span></span>                 |
| [<span data-ttu-id="9803c-119">CSP에서 제어하는 자동 로그인 정책</span><span class="sxs-lookup"><span data-stu-id="9803c-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="9803c-120">자동으로 계정에 로그인하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="9803c-120">Used to log in an account automatically</span></span> | <span data-ttu-id="9803c-121">IT 관리자</span><span class="sxs-lookup"><span data-stu-id="9803c-121">IT Admins</span></span> | <span data-ttu-id="9803c-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9803c-122">20348.1405</span></span> |
| [<span data-ttu-id="9803c-123">인증서 관리자에 대한 PFX 파일 지원</span><span class="sxs-lookup"><span data-stu-id="9803c-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="9803c-124">설정 UI를 통해 PFX 인증서 추가</span><span class="sxs-lookup"><span data-stu-id="9803c-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="9803c-125">최종 사용자</span><span class="sxs-lookup"><span data-stu-id="9803c-125">End User</span></span> | <span data-ttu-id="9803c-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9803c-126">20348.1405</span></span> |
| [<span data-ttu-id="9803c-127">HoloLens 설정 고급 진단 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="9803c-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="9803c-128">디바이스에서 MDM 진단 로그 보기</span><span class="sxs-lookup"><span data-stu-id="9803c-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="9803c-129">문제 해결</span><span class="sxs-lookup"><span data-stu-id="9803c-129">Troubleshooting</span></span> | <span data-ttu-id="9803c-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9803c-130">20348.1405</span></span> |
| [<span data-ttu-id="9803c-131">오프라인 진단 알림</span><span class="sxs-lookup"><span data-stu-id="9803c-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="9803c-132">로그 수집에 대한 오디오바이저 피드백</span><span class="sxs-lookup"><span data-stu-id="9803c-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="9803c-133">문제 해결</span><span class="sxs-lookup"><span data-stu-id="9803c-133">Troubleshooting</span></span> | <span data-ttu-id="9803c-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9803c-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="9803c-135">HoloLens 세부 정보를 보고하기 위한 CSP 변경 내용</span><span class="sxs-lookup"><span data-stu-id="9803c-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="9803c-136">Windows Insider 빌드에 도입된 20348.1403</span><span class="sxs-lookup"><span data-stu-id="9803c-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="9803c-137">다음 CSP는 HoloLens 디바이스에서 정보를 보고하는 새로운 방법으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="9803c-138">DevDetail CSP - 무료 Storage</span><span class="sxs-lookup"><span data-stu-id="9803c-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="9803c-139">이제 DevDetail CSP는 HoloLens 디바이스에 사용 중인 스토리지 공간도 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="9803c-140">이 값은 설정 앱의 Storage 페이지에 표시된 값과 거의 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="9803c-141">다음은 이 정보를 포함하는 특정 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="9803c-142">./DevDetail/Ext/Microsoft/FreeStorage(GET 작업만 해당)</span><span class="sxs-lookup"><span data-stu-id="9803c-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="9803c-143">DeviceStatus CSP - SSID 및 BSSID</span><span class="sxs-lookup"><span data-stu-id="9803c-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="9803c-144">이제 DeviceStatus CSP는 HoloLens 적극적으로 연결된 Wi-Fi 네트워크의 SSID 및 BSSID도 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="9803c-145">다음은 이 정보를 포함하는 특정 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="9803c-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="9803c-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="9803c-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="9803c-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="9803c-148">NetworkIdentifiers를 쿼리하는 syncml Blob 예제(MDM 공급업체용)</span><span class="sxs-lookup"><span data-stu-id="9803c-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="9803c-149">CSP에서 제어하는 자동 로그인 정책</span><span class="sxs-lookup"><span data-stu-id="9803c-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="9803c-150">이 새로운 AutoLogonUser 정책은 사용자가 자동으로 로그온되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="9803c-151">일부 고객은 ID에 연결되어 있지만 로그인 환경을 원하지 않는 디바이스를 설정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="9803c-152">디바이스를 선택하고 원격 지원을 즉시 사용하는 Imagine.</span><span class="sxs-lookup"><span data-stu-id="9803c-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="9803c-153">또는 HoloLens 디바이스를 신속하게 배포하고 최종 사용자가 로그인을 신속하게 수행할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="9803c-154">정책이 비어있지 않은 값으로 설정된 경우 자동 로그온 사용자의 이메일 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="9803c-155">자동 로그온을 사용하려면 지정된 사용자가 디바이스에 한 번 이상 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="9803c-156">새 정책 문자열 값의 OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`</span><span class="sxs-lookup"><span data-stu-id="9803c-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="9803c-157">이메일 주소가 동일한 사용자는 자동 로그온을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="9803c-158">이 정책이 구성된 디바이스에서 정책에 지정된 사용자는 한 번 이상 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="9803c-159">첫 번째 로그온 후 디바이스를 다시 부팅하면 지정된 사용자가 자동으로 로그온됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="9803c-160">단일 자동 로그온 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="9803c-161">사용하도록 설정하면 자동으로 로그온된 사용자는 수동으로 로그아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="9803c-162">다른 사용자로 로그온하려면 먼저 정책을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="9803c-163">주요 OS 업데이트와 같은 일부 이벤트는 지정된 사용자가 디바이스에 다시 로그온하여 자동 로그온 동작을 다시 시작하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="9803c-164">자동 로그온은 MSA 및 AAD 사용자에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="9803c-165">인증서 관리자에 대한 PFX 파일 지원</span><span class="sxs-lookup"><span data-stu-id="9803c-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="9803c-166">Windows Insider 빌드 20348.1405에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="9803c-167">이제 .pfx 인증서를 사용할 수 있도록 [인증서 관리자에](certificate-manager.md) 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="9803c-168">사용자가 **설정** 업데이트 & 보안 인증서 로 이동하고  >    >   **인증서 설치를** 선택하면 이제 UI에서 .pfx 인증서 파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="9803c-169">사용자는 프라이빗 키가 있는 .pfx 인증서를 사용자 저장소 또는 컴퓨터 저장소로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="9803c-170">HoloLens 설정 고급 진단 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="9803c-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="9803c-171">동작 문제를 해결할 때 관리되는 디바이스의 경우 예상되는 정책 구성이 적용되는지 확인하는 것이 중요한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="9803c-172">이전에는 이 새로운 기능을 사용하려면 MDM을 통해 디바이스에서 또는 디바이스 근처에서 수행되어야 했습니다. **이** 작업은 설정 계정을 통해 수집된 MDM 진단 로그를 내보낸 후 작업 또는 학교 에  ->    >  **액세스하고** **관리 로그 내보내기를** 선택하여 주변 PC에서 볼 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="9803c-173">이제 Edge 브라우저를 사용하여 디바이스에서 MDM 진단을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="9803c-174">MDM 진단 보고서를 더 쉽게 보려면 작업 또는 학교 액세스 페이지로 이동하고 **고급 진단 보고서 보기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="9803c-175">그러면 새 Edge 창에서 보고서가 생성되고 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-175">This will generate and open the report in a new Edge window.</span></span>

![설정 앱에서 고급 진단 보고서를 봅니다.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="9803c-177">오프라인 진단 알림</span><span class="sxs-lookup"><span data-stu-id="9803c-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="9803c-178">오프라인 진단이라는 기존 기능에 대한 [업데이트입니다.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9803c-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="9803c-179">이전에는 사용자에게 진단 수집을 트리거했거나 완료되었다는 명확한 표시기가 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="9803c-180">이제 Windows 참가자 빌드에 추가되었습니다. 오프라인 진단에 대한 두 가지 형태의 시청각 피드백이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="9803c-181">첫 번째는 컬렉션이 시작되고 완료될 때 둘 다에 대해 표시되는 알림 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="9803c-182">사용자가 로그인하고 시각적 개체를 가지고 있을 때 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-182">These will be displayed when the user is logged in and has visuals.</span></span>

![로그를 수집하기 위한 알림입니다.](./images/logcollection1.jpg)

![로그 수집이 완료되면 알림 메시지입니다.](./images/logcollection2.jpg)
 
<span data-ttu-id="9803c-185">사용자가 디스플레이에 액세스할 수 없거나 로그인할 수 없거나 여전히 OOBE에 있는 경우 오프라인 진단을 대체 로그 수집 메커니즘으로 사용하기 때문에 로그가 수집될 때 오디오 큐가 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="9803c-186">이 소리는 알림 메시지 외에도 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="9803c-187">이 새로운 기능은 디바이스가 업데이트될 때 사용하도록 설정되며 사용하도록 설정하거나 관리하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="9803c-188">이 새 피드백을 표시하거나 들어 볼 수 없는 경우에도 오프라인 진단이 계속 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="9803c-189">이 새로운 오디오 피드백 추가를 통해 진단 데이터를 더 쉽게 수집하고 문제를 보다 신속하게 해결할 수 있기를 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="9803c-190">수정 및 개선 사항:</span><span class="sxs-lookup"><span data-stu-id="9803c-190">Fixes and improvements:</span></span>

- <span data-ttu-id="9803c-191">잠긴 [파일을 다운로드하라는 프롬프트가 없는 장치 포털 대해 알려진 문제가 해결되었습니다.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="9803c-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="9803c-192">파일 [업로드 및 다운로드 시간 장치 포털 대한 알려진 문제를 해결했습니다.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="9803c-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="9803c-193">참가자 빌드 수신 시작</span><span class="sxs-lookup"><span data-stu-id="9803c-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="9803c-194">최근에 업데이트하지 않은 경우 디바이스를 다시 부팅하여 상태를 업데이트하고 최신 빌드를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="9803c-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="9803c-195">"디바이스 다시 부팅" 음성 명령이 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="9803c-196">설정/Windows 참가자 프로그램 다시 시작 단추를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="9803c-197">발생한 백 엔드에 버그가 있으므로 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="9803c-198">HoloLens 2 디바이스에서 **설정** 업데이트 & 보안 Windows 참가자 프로그램 이동하여  >    >   **시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="9803c-199">Windows 참가자로 등록하는 데 사용한 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="9803c-200">Windows 참가자는 이제 채널로 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="9803c-201">**빠른** 링이 **개발 채널이** **되고, 느린** 링이 **베타 채널** 되고, 릴리스 **미리 보기** 링이 릴리스 미리 **보기 채널** 이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="9803c-202">매핑은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-202">Here is what that mapping looks like:</span></span>

![Windows 참가자 채널 설명](images/WindowsInsiderChannels.png)

<span data-ttu-id="9803c-204">자세한 내용은 Windows 블로그에서 [Windows 참가자 채널 소개를](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9803c-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="9803c-205">그런 다음, **Windows 활성 개발을** **선택하고, 개발 채널** 또는 **베타 채널** 빌드를 받을지 선택하고, 프로그램 용어를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="9803c-206">확인을 > **지금 다시 시작을** 선택하여 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="9803c-207">디바이스가 다시 부팅된 후 설정 > 업데이트 & 보안 > 업데이트 확인으로 이동하여 최신 빌드를 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="9803c-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="9803c-208">업데이트 오류 0x80070490 해결</span><span class="sxs-lookup"><span data-stu-id="9803c-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="9803c-209">Dev 또는 Beta 채널에서 업데이트할 때 업데이트 오류 0x80070490 발생하는 경우 다음과 같은 단기 해결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="9803c-210">여기에는 참가자 채널을 이동하고, 업데이트를 선택하고, 참가자 채널을 다시 이동하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="9803c-211">1단계 - 릴리스 미리 보기</span><span class="sxs-lookup"><span data-stu-id="9803c-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="9803c-212">설정 & 보안 업데이트 Windows 참가자 프로그램 **릴리스 미리 보기 채널을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="9803c-213">설정, 업데이트 & 보안, Windows 업데이트, 업데이트 **확인**</span><span class="sxs-lookup"><span data-stu-id="9803c-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="9803c-214">업데이트 후 2단계로 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="9803c-215">2단계 - 개발 채널</span><span class="sxs-lookup"><span data-stu-id="9803c-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="9803c-216">설정 & 보안을 업데이트하고 Windows 참가자 프로그램 **개발 채널을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="9803c-217">설정, 업데이트 & 보안, Windows 업데이트, 업데이트 **확인**</span><span class="sxs-lookup"><span data-stu-id="9803c-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="9803c-218">FFU 다운로드 및 플래시 방향</span><span class="sxs-lookup"><span data-stu-id="9803c-218">FFU download and flash directions</span></span>

<span data-ttu-id="9803c-219">비행 서명 ffu를 사용하여 테스트하려면 먼저 항공편 서명 ffu를 플래시하기 전에 디바이스의 잠금을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="9803c-220">On PC:</span><span class="sxs-lookup"><span data-stu-id="9803c-220">On PC:</span></span>
    1. <span data-ttu-id="9803c-221">에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="9803c-222">Microsoft Store ARC(고급 복구 도우미)를 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="9803c-223">HoloLens - 플라이트 잠금 해제: **설정** 업데이트 & 보안 Windows 참가자 프로그램 열고  >    >   등록한 후 디바이스를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="9803c-224">Flash FFU - 이제 ARC를 사용하여 비행 서명된 FFU를 플래시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="9803c-225">피드백 제공 및 문제 보고</span><span class="sxs-lookup"><span data-stu-id="9803c-225">Provide feedback and report issues</span></span>

<span data-ttu-id="9803c-226">HoloLens [피드백 허브 앱을](hololens-feedback.md) 사용하여 피드백을 제공하고 문제를 보고하세요.</span><span class="sxs-lookup"><span data-stu-id="9803c-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="9803c-227">피드백 허브 사용하면 엔지니어가 문제를 신속하게 디버그하고 해결할 수 있도록 필요한 진단 정보가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="9803c-228">중국어 및 일본어 버전의 HoloLens 문제는 동일한 방식으로 보고되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="9803c-229">Documents 폴더에 액세스하도록 피드백 허브 여부를 묻는 프롬프트를 수락해야 합니다(메시지가 표시되면 **예** 선택).</span><span class="sxs-lookup"><span data-stu-id="9803c-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="9803c-230">개발자를 위한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="9803c-230">Note for developers</span></span>

<span data-ttu-id="9803c-231">HoloLens 참가자 빌드를 사용하여 애플리케이션을 개발하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="9803c-232">[HoloLens 개발자 설명서를](https://developer.microsoft.com/windows/mixed-reality/development) 확인하여 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="9803c-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="9803c-233">이러한 동일한 지침은 HoloLens 참가자 빌드에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="9803c-234">HoloLens 개발에 이미 사용 중인 Unity 및 Visual Studio 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="9803c-235">참가자 빌드 수신 중지</span><span class="sxs-lookup"><span data-stu-id="9803c-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="9803c-236">더 이상 Windows Holographic의 참가자 빌드를 수신하지 않으려는 경우 HoloLens 프로덕션 빌드를 실행할 때 옵트아웃하거나 고급 복구 도우미를 사용하여 [디바이스를](hololens-recovery.md) 비 참가자 버전의 Windows Holographic으로 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="9803c-237">새 미리 보기 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 취소하는 사용자에게 파란색 화면이 발생하는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="9803c-238">그런 다음 디바이스를 수동으로 복구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="9803c-239">영향을 받을지 여부에 대한 자세한 내용은 이 [알려진 문제에](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)대한 자세한 내용을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9803c-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="9803c-240">HoloLens 프로덕션 빌드를 실행하고 있는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="9803c-241">설정 > **시스템 > 정보로** 이동하여 빌드 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="9803c-242">[프로덕션 빌드 번호는 릴리스 정보 를 참조하세요.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="9803c-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="9803c-243">참가자 빌드를 옵트아웃하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="9803c-244">프로덕션 빌드를 실행하는 HoloLens 설정 > 업데이트 **& 보안 > Windows 참가자 프로그램** 로 이동하고 **참가자 빌드 중지를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="9803c-245">지침에 따라 디바이스를 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="9803c-245">Follow the instructions to opt out your device.</span></span>
