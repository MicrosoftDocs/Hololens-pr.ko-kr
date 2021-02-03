---
title: Microsoft HoloLens 참가자 미리 보기
description: Insider 빌드를 시작하는 방법을 알아보고 HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공합니다.
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
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e36d25a31495b09e2e9f08f8ea5a8bf34fadafeb
ms.sourcegitcommit: 12d96e5d0c733e733f6ff7da2f4efb8e0f96c27b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311838"
---
# <span data-ttu-id="e3515-103">Microsoft HoloLens 참가자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="e3515-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="e3515-104">HoloLens용 최신 Insider Preview 빌드를 시작하세요!</span><span class="sxs-lookup"><span data-stu-id="e3515-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="e3515-105">HoloLens의 [](hololens-insider.md#start-receiving-insider-builds) 다음 주요 운영 체제 업데이트에 대해 간단하게 시작하고 중요한 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="e3515-106">Windows Insider Release Notes</span><span class="sxs-lookup"><span data-stu-id="e3515-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="e3515-107">Windows Insiders에 새로운 기능의 플라이트를 다시 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="e3515-108">We will be flighting to the Dev Channel for the latest updates.</span><span class="sxs-lookup"><span data-stu-id="e3515-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="e3515-109">Windows Insider 빌드에 추가 기능 및 업데이트를 추가하면 이 페이지가 계속 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="e3515-110">이러한 업데이트를 현실에 혼합할 수 있도록 기다렸다가 준비하세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="e3515-111">기능 이름</span><span class="sxs-lookup"><span data-stu-id="e3515-111">Feature Name</span></span>                                              | <span data-ttu-id="e3515-112">간단한 설명</span><span class="sxs-lookup"><span data-stu-id="e3515-112">Short description</span></span>                                                                      | <span data-ttu-id="e3515-113">빌드에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="e3515-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="e3515-114">새 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e3515-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="e3515-115">이제 HoloLens 2에서 새로운 Chromium 기반 Microsoft Edge를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="e3515-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-116">20279.1006</span></span> |
| [<span data-ttu-id="e3515-117">WebXR 및 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="e3515-117">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="e3515-118">몰입형 웹 환경 및 360 비디오 재생 체험</span><span class="sxs-lookup"><span data-stu-id="e3515-118">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="e3515-119">20289.1000</span><span class="sxs-lookup"><span data-stu-id="e3515-119">20289.1000</span></span> |
| [<span data-ttu-id="e3515-120">새 설정 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-120">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="e3515-121">레거시 설정 앱이 새로운 기능 및 설정으로 업데이트된 버전으로 대체되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-121">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="e3515-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-122">20279.1006</span></span> |
| [<span data-ttu-id="e3515-123">기본 앱 선택기</span><span class="sxs-lookup"><span data-stu-id="e3515-123">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="e3515-124">각 파일 또는 링크 유형에 대해 시작해야 하는 앱 선택</span><span class="sxs-lookup"><span data-stu-id="e3515-124">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="e3515-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-125">20279.1006</span></span> |
| [<span data-ttu-id="e3515-126">Office Web App</span><span class="sxs-lookup"><span data-stu-id="e3515-126">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="e3515-127">Office Web App 바로 가기가 이제 "모든 앱"에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-127">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="e3515-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-128">20279.1006</span></span> |
| [<span data-ttu-id="e3515-129">스와이프하여 입력</span><span class="sxs-lookup"><span data-stu-id="e3515-129">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="e3515-130">손가락 팁을 사용하여 홀로그램 키보드에서 단어 "스와이프"</span><span class="sxs-lookup"><span data-stu-id="e3515-130">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="e3515-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-131">20279.1006</span></span> |
| [<span data-ttu-id="e3515-132">USB-C 외부 마이크 지원</span><span class="sxs-lookup"><span data-stu-id="e3515-132">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="e3515-133">앱 및/또는 원격 지원에 USB-C 마이크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-133">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="e3515-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-134">20279.1006</span></span> |
| [<span data-ttu-id="e3515-135">키오스크 모드의 새 앱용 새 AUMID</span><span class="sxs-lookup"><span data-stu-id="e3515-135">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="e3515-136">새 설정 및 에지 앱용 AUMID</span><span class="sxs-lookup"><span data-stu-id="e3515-136">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="e3515-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-137">20279.1006</span></span> |
| [<span data-ttu-id="e3515-138">개선된 키오스크 모드 오류 수리</span><span class="sxs-lookup"><span data-stu-id="e3515-138">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="e3515-139">키오스크 모드는 비어 있는 시작 메뉴 전에 전역 할당된 액세스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-139">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="e3515-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-140">20279.1006</span></span> |
| [<span data-ttu-id="e3515-141">Fallback Diagnostics 구성</span><span class="sxs-lookup"><span data-stu-id="e3515-141">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="e3515-142">설정 앱에서 Fallback Diagnostic Behavior 설정</span><span class="sxs-lookup"><span data-stu-id="e3515-142">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="e3515-143">20279.1006</span><span class="sxs-lookup"><span data-stu-id="e3515-143">20279.1006</span></span> |

### <span data-ttu-id="e3515-144">새 Microsoft Edge 소개</span><span class="sxs-lookup"><span data-stu-id="e3515-144">Introducing the new Microsoft Edge</span></span>

![새 Microsoft Edge 로고에 대한 레거시 Microsoft Edge 로고 애니메이션](images/new-edge.gif)

<span data-ttu-id="e3515-146">새로운 Microsoft [Edge는 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 오픈 소스 프로젝트를 채택하여 고객에게 더 나은 호환성을 만들고 웹 개발자를 위한 웹 조각화가 줄어 습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-146">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="e3515-147">이 Insider 미리 보기를 통해 HoloLens 2 고객은 새 Microsoft Edge를 처음으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-147">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="e3515-148">새 Microsoft Edge는 결국 HoloLens 2의 레거시 Microsoft Edge를 대체하는 반면, 현재 두 브라우저는 모두 Insiders에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-148">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="e3515-149">새 Microsoft Edge 또는 피드백 허브를 통해 피드백 보내기 기능을 통해 피드백 및 버그를 팀과 [공유해 주세요.](hololens-feedback.md) \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e3515-149">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### <span data-ttu-id="e3515-151">새 Microsoft Edge 시작</span><span class="sxs-lookup"><span data-stu-id="e3515-151">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="e3515-152">Insiders에 사용할 수 있는 두 가지 버전의 Microsoft Edge가 있습니다. 새 Microsoft Edge 새 Microsoft Edge 아이콘(파란색 및 녹색 소용구 아이콘으로 표시) 및 레거시 ![ Microsoft Edge(흰색 "e" 아이콘으로 ](images/new_edge_logo.png) 표시)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-152">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="e3515-153">새 Microsoft Edge가 시작 메뉴에 고정되고 웹 링크를 활성화하면 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-153">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="e3515-154">레거시 Microsoft Edge를 기본 웹 브라우저로 다시 사용하겠는 경우 아래 지침을 참조하여 기본 앱을 [초기화하세요.](#default-app-picker)</span><span class="sxs-lookup"><span data-stu-id="e3515-154">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="e3515-155">HoloLens 2에서 새 Microsoft Edge를 처음 시작하면 레거시 Microsoft Edge에서 설정 및 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-155">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="e3515-156">새 Microsoft Edge를 시작한 후 레거시 Microsoft Edge를 계속 사용하는 경우 새 데이터는 레거시 Microsoft Edge에서 새 Microsoft Edge로 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-156">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="e3515-157">새 Microsoft Edge에 대한 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e3515-157">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="e3515-158">새로운 Microsoft Edge는 IT 관리자에게 이전에 레거시 Microsoft Edge에서 사용할 수 있는 것보다 HoloLens 2의 훨씬 광범위한 브라우저 정책 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-158">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="e3515-159">다음은 새 Microsoft Edge의 정책 설정 관리에 대한 자세한 정보를 알아보는 데 도움이 되는 몇 가지 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-159">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="e3515-160">Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e3515-160">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="e3515-161">Microsoft Edge 레거시에서 Microsoft Edge로 정책 매핑</span><span class="sxs-lookup"><span data-stu-id="e3515-161">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="e3515-162">Google Chrome에서 Microsoft Edge로 정책 매핑</span><span class="sxs-lookup"><span data-stu-id="e3515-162">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="e3515-163">전체 [Microsoft Edge Enterprise 설명서](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="e3515-163">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3515-164">새 Microsoft Edge에서 지원되는 브라우저 정책의 양 때문에 Microsoft 팀은 각 새 정책이 HoloLens 2에서 작동하는지 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-164">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="e3515-165">그러나 이전에 HoloLens 2에서 지원했던 각 레거시 Microsoft Edge 정책에 해당하는 새 Microsoft Edge가 예상대로 작동하고 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-165">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="e3515-166">Microsoft [Edge 레거시와 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 정책 매핑을 참조하여 HoloLens 2에서 사용 중이던 각 레거시 Microsoft Edge 브라우저 정책에 해당하는 새 Microsoft Edge를 찾아 보십시오.</span><span class="sxs-lookup"><span data-stu-id="e3515-166">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="e3515-167">HoloLens 2에서 작동하지 않는 \*\* 새로운 Microsoft Edge 정책이 두 개 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-167">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="e3515-168">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="e3515-168">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="e3515-169">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="e3515-169">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="e3515-170">HoloLens 2의 새로운 Microsoft Edge에서 예상할 일</span><span class="sxs-lookup"><span data-stu-id="e3515-170">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="e3515-171">새 Microsoft Edge는 HoloLens 2와 같은 UWP 전용 장치에서 실행될 수 있도록 하는 새로운 UWP 어댑터 계층이 있는 네이티브 Win32 앱이기 때문에 일부 기능을 즉시 사용할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-171">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="e3515-172">앞으로 몇 개월 동안 새로운 시나리오 및 기능을 지원할 예정이니 이 공간에서 최신 정보를 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-172">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="e3515-173">작동해야 하는 시나리오 및 기능:</span><span class="sxs-lookup"><span data-stu-id="e3515-173">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="e3515-174">첫 실행 환경, 프로필에 로그인 및 동기화</span><span class="sxs-lookup"><span data-stu-id="e3515-174">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="e3515-175">웹 사이트가 렌더링 및 예상대로 행동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-175">Websites should render and behave as expected</span></span>
- <span data-ttu-id="e3515-176">대부분의 브라우저 기능(즐겨찾기, 기록 등)이 예상대로 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-176">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="e3515-177">어두운 모드</span><span class="sxs-lookup"><span data-stu-id="e3515-177">Dark mode</span></span>
- <span data-ttu-id="e3515-178">장치에 웹앱 설치</span><span class="sxs-lookup"><span data-stu-id="e3515-178">Installing web apps to the device</span></span>
- <span data-ttu-id="e3515-179">확장 설치(HoloLens 2에서 제대로 작동하지 않는 확장을 사용하는 경우 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-179">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="e3515-180">PDF 보기 및 표시</span><span class="sxs-lookup"><span data-stu-id="e3515-180">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="e3515-181">단일 브라우저 창의 공간 소리</span><span class="sxs-lookup"><span data-stu-id="e3515-181">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="e3515-182">브라우저의 자동 및 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="e3515-182">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="e3515-183">인쇄 메뉴에서 PDF 저장("PDF로 저장" 옵션 사용)</span><span class="sxs-lookup"><span data-stu-id="e3515-183">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="e3515-184">곧 제공될 시나리오 및 기능:</span><span class="sxs-lookup"><span data-stu-id="e3515-184">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="e3515-185">WebXR 및 360 뷰어 확장</span><span class="sxs-lookup"><span data-stu-id="e3515-185">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="e3515-186">환경에 배치된 여러 창을 탐색할 때 창을 수정하기 위한 콘텐츠 복원</span><span class="sxs-lookup"><span data-stu-id="e3515-186">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="e3515-187">다음과 같은 시나리오 및 기능이 작동하지 않을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-187">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="e3515-188">동시 오디오 스트림이 있는 여러 창의 공간 소리</span><span class="sxs-lookup"><span data-stu-id="e3515-188">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="e3515-189">"참조, 말하기"</span><span class="sxs-lookup"><span data-stu-id="e3515-189">"See it, say it"</span></span>
- <span data-ttu-id="e3515-190">인쇄</span><span class="sxs-lookup"><span data-stu-id="e3515-190">Printing</span></span>

**<span data-ttu-id="e3515-191">가장 알려진 브라우저 문제:</span><span class="sxs-lookup"><span data-stu-id="e3515-191">Top known browser issues:</span></span>**
- <span data-ttu-id="e3515-192">장치를 초기화하면 새 Microsoft Edge가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-192">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="e3515-193">홀로그램 키보드의 돋보기 미리 보기에 잘못된 콘텐츠가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-193">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="e3515-194">Microsoft Edge 내부자 채널</span><span class="sxs-lookup"><span data-stu-id="e3515-194">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="e3515-195">Microsoft Edge 팀은 에지 참여자 커뮤니티에서 세 가지 미리 보기 채널인 Beta, Dev 및 Canary를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-195">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="e3515-196">미리 보기 채널을 설치해도 HoloLens 2에 릴리스된 Microsoft Edge 버전이 제거되지는 않습니다. 동시에 두 개 이상의 Microsoft Edge를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-196">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="e3515-197">Microsoft [Edge Insider 홈페이지를](https://www.microsoftedgeinsider.com) 방문하여 에지 내부자 커뮤니티에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="e3515-197">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="e3515-198">다양한 에지 내부자 채널에 대한 자세한 내용을 알아보고 시작하려면 [Edge Insider 다운로드 페이지를 방문하세요.](https://www.microsoftedgeinsider.com/download)</span><span class="sxs-lookup"><span data-stu-id="e3515-198">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="e3515-199">HoloLens 2에 Microsoft Edge Insider 채널을 설치하는 데 사용할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-199">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="e3515-200">장치에 직접 설치(현재 관리되지 않는 디바이스에서만 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="e3515-200">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="e3515-201">HoloLens 2에서 [에지 Insider 다운로드 페이지를 방문합니다.](https://www.microsoftedgeinsider.com/download)</span><span class="sxs-lookup"><span data-stu-id="e3515-201">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download)</span></span>
  1. <span data-ttu-id="e3515-202">설치하고자 하는 에지 내부자 채널에 대한 **HoloLens 2** 다운로드 단추 선택</span><span class="sxs-lookup"><span data-stu-id="e3515-202">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install</span></span>
  1. <span data-ttu-id="e3515-203">Edge 다운로드 큐 또는 장치의 "다운로드" 폴더에서 다운로드한 .msix 파일 시작(파일 탐색기 사용)</span><span class="sxs-lookup"><span data-stu-id="e3515-203">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer)</span></span>
  1. <span data-ttu-id="e3515-204">[앱 설치 관리자 시작](app-deploy-app-installer.md)</span><span class="sxs-lookup"><span data-stu-id="e3515-204">[App installer](app-deploy-app-installer.md) will launch</span></span>
  1. <span data-ttu-id="e3515-205">설치 **단추** 선택</span><span class="sxs-lookup"><span data-stu-id="e3515-205">Select the **Install** button</span></span>
  1. <span data-ttu-id="e3515-206">설치가 성공하면 시작 메뉴의 모든 앱 목록에서 Microsoft Edge \*\*\*\* Beta, Dev 또는 Canary를 별도의 항목으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-206">After successful install, you will find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu</span></span>

**<span data-ttu-id="e3515-207">Windows Device Portal을 사용하여 [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) PC를 통해 설치(HoloLens 2에서 개발자 모드를 사용하도록 설정해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e3515-207">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="e3515-208">PC에서 [에지 Insider](https://www.microsoftedgeinsider.com/download) 다운로드 페이지 방문</span><span class="sxs-lookup"><span data-stu-id="e3515-208">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download)</span></span>
  1. <span data-ttu-id="e3515-209">설치하고자 \*\*\*\* 하는 에지 내부자 채널의 "Windows 10용 다운로드" 단추 옆에 있는 드롭다운 화살표 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-209">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install</span></span>
  1. <span data-ttu-id="e3515-210">드롭다운 **메뉴에서 HoloLens 2** 선택</span><span class="sxs-lookup"><span data-stu-id="e3515-210">Select **HoloLens 2** in the drop-down menu</span></span>
  1. <span data-ttu-id="e3515-211">.msix 파일을 PC의 "다운로드" 폴더(또는 쉽게 찾을 수 있는 다른 폴더)에 저장</span><span class="sxs-lookup"><span data-stu-id="e3515-211">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find)</span></span>
  1. <span data-ttu-id="e3515-212">PC에서 [Windows Device Portal을](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 사용하여 HoloLens 2에 다운로드된 .msix 파일 설치</span><span class="sxs-lookup"><span data-stu-id="e3515-212">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2</span></span>
  1. <span data-ttu-id="e3515-213">설치가 성공하면 시작 메뉴의 모든 앱 목록에서 Microsoft Edge \*\*\*\* Beta, Dev 또는 Canary를 별도의 항목으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-213">After successful install, you will find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu</span></span>

> [!NOTE]
> <span data-ttu-id="e3515-214">HoloLens 2에 대한 이 Windows Insider 미리 보기 동안 장치의 Microsoft Edge 버전이 일부 또는 전체 Microsoft Edge Insider 채널에서 사용할 수 있는 버전보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-214">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="e3515-215">이는 HoloLens 2의 웹 브라우저를 대상으로 하는 새로운 기능 및 수정이 가능한 한 빨리 Windows Insiders에 연결되도록 보장하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-215">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="e3515-216">다음 Windows 업데이트가 공개된 직후 Microsoft Edge 내부자 채널 빌드는 HoloLens 2의 Microsoft Edge 버전을 능가하고 계속 앞서 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-216">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="e3515-217">WebXR 및 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="e3515-217">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="e3515-218">Windows Insider Build 20289.1000에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-218">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="e3515-219">새로운 Microsoft Edge에는 몰입형 웹 환경을 만들기 위한 새로운 표준인 WebXR에 대한 지원이 포함되어 있습니다(WebVR 대체).</span><span class="sxs-lookup"><span data-stu-id="e3515-219">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="e3515-220">많은 몰입형 웹 환경은 VR을 염두에 두어 디자인했지만(시야를 가상 환경으로 대체) HoloLens 2에서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-220">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="e3515-221">WebXR 표준은 실제 환경을 활용하는 증강 및 혼합 현실 몰입형 웹 환경을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-221">The WebXR standard also enables augmented and mixed reality immersive web experiences that leverage your physical environment.</span></span> <span data-ttu-id="e3515-222">개발자가 WebXR에 더 많은 시간을 소비할수록 HoloLens 2 고객에게 새로운 증강 및 혼합 현실 몰입형 환경이 제공될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-222">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="e3515-223">360 뷰어 확장은 WebXR을 통해 구축되며 HoloLens 2의 새로운 Microsoft Edge와 함께 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-223">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="e3515-224">이 웹 확장은 360도 비디오에 자신을 들이는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-224">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="e3515-225">YouTube에서는 360개 비디오를 가장 많이 선택하기 때문에 이 비디오를 시작하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-225">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <span data-ttu-id="e3515-226">WebXR 사용 방법</span><span class="sxs-lookup"><span data-stu-id="e3515-226">How to use WebXR</span></span>

1. <span data-ttu-id="e3515-227">WebXR 지원을 사용하여 웹 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-227">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="e3515-228">웹 사이트에서 **VR** 입력 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-228">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="e3515-229">이 단추의 위치 및 시각적 표현은 웹 사이트마다 다를 수 있지만 다음과 유사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-229">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![VR 입력 단추 예제](images/75px-enter-vr.png)

1. <span data-ttu-id="e3515-231">특정 도메인에서 WebXR 환경을 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하는 데 동의하도록 요청하고 허용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-231">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="e3515-232">[HoloLens 2 제스처를 사용하여](hololens2-basic-usage.md#the-hand-tracking-frame) 환경을 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-232">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="e3515-233">환경의 종료 단추가 \*\*\*\* 없는 경우 시작 제스처를 [사용하여](hololens2-basic-usage.md#start-gesture) 홈으로 돌아오십시오.</span><span class="sxs-lookup"><span data-stu-id="e3515-233">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="e3515-234">권장 WebXR 샘플</span><span class="sxs-lookup"><span data-stu-id="e3515-234">Recommended WebXR samples</span></span>**
- <span data-ttu-id="e3515-235">360 뷰어(다음 섹션 참조)</span><span class="sxs-lookup"><span data-stu-id="e3515-235">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="e3515-236">XR 공룡</span><span class="sxs-lookup"><span data-stu-id="e3515-236">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="e3515-237">바리타 Express</span><span class="sxs-lookup"><span data-stu-id="e3515-237">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="e3515-238">WebXR 그림판</span><span class="sxs-lookup"><span data-stu-id="e3515-238">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <span data-ttu-id="e3515-239">360 뷰어를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="e3515-239">How to use 360 Viewer</span></span>

1. <span data-ttu-id="e3515-240">YouTube에서 360도 비디오로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-240">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="e3515-241">비디오 프레임에서 혼합 현실 헤드셋 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-241">In the video frame, select the mixed reality headset button:</span></span>

    ![360 뷰어 활성화 단추](images/enter-360-viewer.jpg)

1. <span data-ttu-id="e3515-243">특정 도메인에서 360 Viewer를 처음 시작하려고 하면 브라우저에서 몰입형 보기를 입력하는 데 동의하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-243">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="e3515-244">허용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-244">Select **Allow**.</span></span>
1. <span data-ttu-id="e3515-245">[에어 탭하여](hololens2-basic-usage.md#select-using-air-tap) 재생 컨트롤을 나타 습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-245">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="e3515-246">손 [광선](hololens2-basic-usage.md#select-using-air-tap) 및 에어 탭을 사용하여 재생/일시 중지, 앞으로/뒤로 건너뛰기, 캡션 켜기/끄기 또는 경험을 중지합니다(몰입형 보기를 종료).</span><span class="sxs-lookup"><span data-stu-id="e3515-246">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="e3515-247">재생 컨트롤은 몇 초 동안 비활성 상태일 때 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-247">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <span data-ttu-id="e3515-248">상위 WebXR 및 360 뷰어 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e3515-248">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="e3515-249">WebXR 환경에서는 머리를 기울거나 환경 주위를 이동할 때 홀로그램이 이동하거나 기울어지게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-249">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="e3515-250">WebXR 환경의 복잡도에 따라 프레임 속도는 떨어뜨리거나 스터터될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-250">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="e3515-251">Articulated hand joints are not yet available in WebXR.</span><span class="sxs-lookup"><span data-stu-id="e3515-251">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="e3515-252">WebXR 또는 360 뷰어 환경을 종료할 때 혼합 현실 홈의 홀로그램이 다시 나타남에 30초 이상 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-252">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="e3515-253">YouTube가 아닌 웹 사이트의 360 동영상이 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-253">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="e3515-254">360 비디오가 몰입형 보기를 입력하지 않는 경우(또는 혼합 현실 헤드셋 단추가 나타나지 않는 경우) 페이지를 새로 고쳐 보세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-254">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="e3515-255">HoloLens 2의 360 뷰어에는 캡션이 아직 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-255">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="e3515-256">360 뷰어에서 비디오를 일시 중지하면 비디오 렌더링이 중지되지만 재생 단추를 올바르게 선택하면 재생이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-256">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="e3515-257">360 뷰어의 "다음 비디오" 단추는 현재 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-257">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="e3515-258">몰입형 "비디오" 모드에서 2D 비디오를 재생할 수 있지만 프레임 속도는 30ps 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-258">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <span data-ttu-id="e3515-259">WebXR 및 360 뷰어에 대한 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="e3515-259">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="e3515-260">새 Microsoft Edge의 피드백 보내기 \*\*\*\* 기능을 통해 피드백 및 버그를 팀과 공유해 주세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-260">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <span data-ttu-id="e3515-261">새 설정 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-261">New Settings app</span></span>

<span data-ttu-id="e3515-262">이 릴리스에서는 새로운 버전의 설정 앱을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-262">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="e3515-263">새 설정 앱에는 소리, Power & 절전, 네트워크 & 인터넷, 앱, 계정, 접근성 등 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-263">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="e3515-264">새 설정 앱은 레거시 설정 앱과는 별개이기 때문에 이전에 환경에 배치한 설정 창은 업데이트 시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-264">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![새 설정 앱 홈페이지](images/new-settings-app.png)

**<span data-ttu-id="e3515-266">새로운 기능 및 설정</span><span class="sxs-lookup"><span data-stu-id="e3515-266">New features and settings</span></span>**
- <span data-ttu-id="e3515-267">설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈에서 설정 검색</span><span class="sxs-lookup"><span data-stu-id="e3515-267">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="e3515-268">시스템 > 소리:</span><span class="sxs-lookup"><span data-stu-id="e3515-268">System > Sound:</span></span>
  - <span data-ttu-id="e3515-269">입력 및 출력 오디오 장치: 입력 및 출력 오디오 장치를 독립적으로 선택하십시오(예: Bluetooth 헤드폰을 통해 오디오를 듣거나 오디오 입력에 USB-C 마이크를 사용).</span><span class="sxs-lookup"><span data-stu-id="e3515-269">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="e3515-270">참고: Bluetooth 마이크는 HoloLens 2에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-270">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="e3515-271">앱 볼륨: 각 앱의 볼륨을 독립적으로 조정</span><span class="sxs-lookup"><span data-stu-id="e3515-271">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="e3515-272">시스템 > 전원 & 절전: 장치가 비활성 기간 후 절전으로 이동해야 하는 시기 선택</span><span class="sxs-lookup"><span data-stu-id="e3515-272">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="e3515-273">시스템 > 배터리: 배터리 절약 모드를 수동으로 사용하도록 설정하거나 배터리 절약 모드가 자동으로 켜진 지점에 배터리 임계값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-273">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="e3515-274">USB > 장치: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-274">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="e3515-275">네트워크 & 인터넷:</span><span class="sxs-lookup"><span data-stu-id="e3515-275">Network & Internet:</span></span>
  - <span data-ttu-id="e3515-276">이제 USB-C 이더넷 어댑터가 네트워크 & 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-276">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="e3515-277">이제 해당 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-277">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="e3515-278">이제 HoloLens 2에서 비행기 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-278">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="e3515-279">앱: 파일 및 링크 유형에 사용되는 기본 앱을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-279">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="e3515-280">자세한 [내용은 기본 앱 선택을](#default-app-picker) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-280">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="e3515-281">다른 > 사용자에 대한 계정: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-281">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="e3515-282">접근성: 텍스트 크기 및 일부 시각적 효과 변경</span><span class="sxs-lookup"><span data-stu-id="e3515-282">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="e3515-283">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e3515-283">Known issues</span></span>**
- <span data-ttu-id="e3515-284">이전에 배치된 설정 창이 제거됩니다(위의 참고 참조).</span><span class="sxs-lookup"><span data-stu-id="e3515-284">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="e3515-285">알림 페이지를 방문하면 설정 앱이 충돌할 수 있습니다(조사 중).</span><span class="sxs-lookup"><span data-stu-id="e3515-285">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="e3515-286">현재 이더넷 페이지가 표시되지 않습니다(곧 수정될 예정).</span><span class="sxs-lookup"><span data-stu-id="e3515-286">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="e3515-287">더 이상 설정 앱으로 디바이스 이름을 변경할 수 없습니다(IT 관리자는 프로비저닝 패키지 또는 MDM을 사용하여 장치 이름을 변경할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="e3515-287">You can no longer rename your device with the Settings app (IT admins can use provisioning packages or MDM to rename devices)</span></span>
- <span data-ttu-id="e3515-288">UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램 특성으로 인해 새 Microsoft Edge의 배터리 사용량이 정확하지 않을 수 있습니다(곧 수정이 예상되지 않을 예정입니다).</span><span class="sxs-lookup"><span data-stu-id="e3515-288">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="e3515-289">기본 앱 선택기</span><span class="sxs-lookup"><span data-stu-id="e3515-289">Default app picker</span></span>

<span data-ttu-id="e3515-290">하이퍼링크를 활성화하거나 앱을 지원하는 설치된 앱이 두 개 이상 있는 파일 형식을 열면 파일 또는 링크 형식을 처리해야 하는 설치된 앱을 선택하라는 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-290">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="e3515-291">이 창에서 선택한 앱이 파일 또는 링크 형식 "한 번" 또는 "항상"을 처리하게 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-291">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![앱 선택기 창](images/default-app-picker.png)

<span data-ttu-id="e3515-293">"항상"을 선택하지만 나중에 특정 파일 또는 링크 형식을 처리하는 앱을 변경하려면 앱의 설정에서 저장된 기본값을 **> 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-293">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="e3515-294">페이지 아래쪽으로 스크롤하고 "파일 \*\*\*\* 형식에 대한 기본 앱" 및/또는 "링크 형식의 기본 앱"에서 지우기 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-294">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="e3515-295">데스크톱 PC의 유사한 설정과 달리 개별 파일 형식 기본값은 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-295">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="e3515-296">Office Web App</span><span class="sxs-lookup"><span data-stu-id="e3515-296">Office web app</span></span>

<span data-ttu-id="e3515-297">Office Web App이 시작 메뉴의 "모든 앱" 목록에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-297">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="e3515-298">이 웹앱은 시작 또는 제거에 고정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-298">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="e3515-299">웹앱이기 때문에 해당 기능은 방문하여 경험하는 기능과 정확히 https://www.office.com 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-299">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="e3515-300">Office Web App 기능은 HoloLens 2에 활성 인터넷 연결이 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-300">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="e3515-301">스와이프하여 입력</span><span class="sxs-lookup"><span data-stu-id="e3515-301">Swipe to type</span></span>

<span data-ttu-id="e3515-302">일부 고객은 입력하려는 단어의 모양을 스와이프하여 가상 키보드에서 "입력"하는 것이 더 빠르며 홀로그램 키보드에 대해 이 기능을 미리 보고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-302">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="e3515-303">홀로그램 키보드의 평면을 통해 손가락 팁을 전달하고 단어의 모양을 스와이프한 다음 키보드 평면에서 손가락 끝을 철회하여 한 단어씩 한 번씩 스와이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-303">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="e3515-304">단어 사이에 있는 키보드에서 손가락을 제거하여 스페이스바를 누르지 않고도 후속 단어를 스와이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-304">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="e3515-305">키보드에서 손가락을 움직일 때 뒤로 미는 내선이 표시될 경우 이 기능이 작동하고 있는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-305">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="e3515-306">휴대폰 디스플레이와 달리 손가락에 대한 저항이 느껴지지 않는 홀로그램 키보드의 특성 때문에 이 기능을 사용 및 마스터하기가 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-306">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="e3515-307">이 기능은 공개 릴리스에서 평가 중이기 때문에 사용자 의견이 중요합니다. 이 기능이 유용하게 사용되거나 생성적 피드백이 있는지 여부에 따라 피드백 허브를 통해 [알려주세요.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="e3515-307">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="e3515-308">USB-C 외부 마이크 지원</span><span class="sxs-lookup"><span data-stu-id="e3515-308">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3515-309">USB 마이크를 연결하면 자동으로 입력 장치로 **설정되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-309">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="e3515-310">USB-C 헤드폰 집합을 연결할 때 사용자는 헤드폰의 오디오가 자동으로 헤드폰으로 리디렉션되는 것이 관찰되지만 HoloLens OS는 다른 입력 장치보다 내부 마이크 배열의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-310">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="e3515-311">USB-C 마이크를 사용하려면 아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-311">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="e3515-312">사용자는 소리 설정 패널을 사용하여 USB-C 연결 외부 **마이크를 선택할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-312">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="e3515-313">USB-C 마이크는 통화, 녹음 등에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-313">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="e3515-314">설정 앱을 **열고** **시스템 소리를**  ->  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-314">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![소리 설정](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="e3515-316">원격 도우미와 \*\*\*\* 함께 외부 마이크를 사용하려면 사용자가 "사운드 장치 관리" 하이퍼링크를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-316">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="e3515-317">그런 다음 드롭다운을 사용하여 외부 마이크를 **기본** 또는 통신 기본값으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-317">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="e3515-318">기본값을 **선택하면** 외부 마이크가 모든 곳에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-318">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="e3515-319">통신 **기본값을** 선택하면 외부 마이크가 원격 지원 및 기타 통신 앱에서 사용되지만 HoloLens 마이크 배열을 다른 작업에 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-319">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![사운드 장치 관리](images/usbc-mic-2.png)

<br>

![마이크 기본값 설정](images/usbc-mic-3.jpg)

#### <span data-ttu-id="e3515-322">마이크 지원에 Bluetooth 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="e3515-322">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="e3515-323">안타깝게도 Bluetooth 마이크는 현재 HoloLens 2에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-323">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="e3515-324">USB-C 마이크 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e3515-324">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="e3515-325">일부 USB-C 마이크는 마이크와 스피커 모두로 \*\* 잘못 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-325">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="e3515-326">HoloLens가 아니라 마이크에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-326">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="e3515-327">이러한 마이크 중 하나를 HoloLens에 연결할 때 소리가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-327">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="e3515-328">다행히 간단한 수정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-328">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="e3515-329">설정 **시스템**  ->  **소리에서**기본 제공 스피커(아날로그 기능 오디오 드라이버)를 명시적으로 기본  ->  \*\*\*\* **장치로 설정** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e3515-329">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="e3515-330">HoloLens는 마이크를 제거하고 나중에 다시 연결한 경우에도 이 설정을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-330">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 마이크 문제 해결](images/usbc-mic-4.png)

### <span data-ttu-id="e3515-332">키오스크 모드에서 새 설정 및 에지 앱 사용</span><span class="sxs-lookup"><span data-stu-id="e3515-332">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="e3515-333">키오스크에 [](hololens-kiosk.md)앱을 포함하면 IT 관리자가 종종 앱을 키오스크에 추가하지만 AUMID(앱 사용자 모델 ID)를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-333">When including apps in in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="e3515-334">설정 앱과 Microsoft Edge 앱은 모두 새 앱으로 간주되어 해당 앱에 대해 AUMID를 사용하는 이전 앱 키오스크를 업데이트해야 새 AUMID를 사용할 수 있기 때문에</span><span class="sxs-lookup"><span data-stu-id="e3515-334">Because both the Settings app and Microsoft Edge app are considered new apps and different that the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="e3515-335">새 앱을 포함하도록 키오스크를 수정할 때 새 AUMID를 추가하고 이전 앱을 남겨 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-335">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="e3515-336">이렇게 하면 사용자가 OS를 업데이트할 때 쉽게 전환할 수 있으며 키오스크를 의도한 바에 따라 계속 사용하기 위한 새 정책을 받을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-336">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="e3515-337">앱</span><span class="sxs-lookup"><span data-stu-id="e3515-337">App</span></span>                    | <span data-ttu-id="e3515-338">AUMID</span><span class="sxs-lookup"><span data-stu-id="e3515-338">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="e3515-339">이전 설정 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-339">Old Settings App</span></span>       | <span data-ttu-id="e3515-340">HolographicSystemSettings_cw5n1h2txyewy! 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-340">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="e3515-341">새 설정 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-341">New Settings App</span></span>       | <span data-ttu-id="e3515-342">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-342">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="e3515-343">이전 Microsoft Edge 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-343">Old Microsoft Edge app</span></span> | <span data-ttu-id="e3515-344">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="e3515-344">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="e3515-345">새 Microsoft Edge 앱</span><span class="sxs-lookup"><span data-stu-id="e3515-345">New Microsoft Edge app</span></span> | <span data-ttu-id="e3515-346">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE</span><span class="sxs-lookup"><span data-stu-id="e3515-346">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="e3515-347">오류 처리를 위한 키오스크 모드 동작 변경</span><span class="sxs-lookup"><span data-stu-id="e3515-347">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="e3515-348">이전 빌드에서는 장치에 전역 할당된 액세스와 AAD 그룹 구성원이 할당된 액세스가 모두 조합된 키오스크 구성이 있는 경우 AAD 그룹 구성원 자격 확인에 실패하면["시작"](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)메뉴에 아무 것도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-348">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="e3515-349">Windows Insider 릴리스부터는 AAD 그룹 키오스크 모드 중 오류가 발생하면 키오스크 환경이 전역 키오스크 구성(있는 경우)으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-349">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="e3515-350">설정 앱을 통해 Fallback Diagnostics 구성</span><span class="sxs-lookup"><span data-stu-id="e3515-350">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="e3515-351">이제 설정 앱에서 사용자가 [Fallback Diagnostics의 동작을 구성할 수 있습니다.](hololens-diagnostic-logs.md)</span><span class="sxs-lookup"><span data-stu-id="e3515-351">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="e3515-352">설정 앱에서 개인 **정보**문제 해결 페이지로 이동하여  ->  \*\*\*\* 이 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-352">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="e3515-353">장치에 대해 구성된 MDM 정책이 있는 경우 사용자는 해당 동작을 다시 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-353">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  






## <span data-ttu-id="e3515-354">Insider 빌드 수신 시작</span><span class="sxs-lookup"><span data-stu-id="e3515-354">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="e3515-355">If you haven't updated recently, please reboot your device to update state and get the latest build.</span><span class="sxs-lookup"><span data-stu-id="e3515-355">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="e3515-356">"다시부팅 장치" 음성 명령이 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-356">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="e3515-357">설정/Windows Insider 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-357">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="e3515-358">백 엔드에서 발생할 수 있는 버그가 발생하여 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-358">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="e3515-359">HoloLens 2 장치에서 보안 \*\*\*\* Windows & 설정 업데이트로 이동하고  >  \*\*\*\*  >  \*\*\*\* **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-359">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="e3515-360">Windows Insider로 등록하는 데 사용한 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-360">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="e3515-361">Windows 내부자는 이제 채널로 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-361">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="e3515-362">빠른 **링은** 개발자 채널이 되고, **슬로우** 링은 \*\*\*\* 베타 채널이 **되고,** 릴리스 미리 보기 링은 릴리스 미리 보기 \*\*\*\* **채널이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-362">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="e3515-363">매핑의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-363">Here is what that mapping looks like:</span></span>

![Windows Insider Channels 설명](images/WindowsInsiderChannels.png)

<span data-ttu-id="e3515-365">자세한 내용은 Windows 블로그에 [Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 소개를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-365">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="e3515-366">그런 다음 **Windows의 활성**개발을 선택하고 개발자 \*\*\*\* 채널 또는 \*\*\*\* 베타 채널 빌드를 받을지 여부를 선택하고 프로그램 용어를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-366">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="e3515-367">지금 **다시 > 확인을** 선택하여 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-367">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="e3515-368">장치를 다시 시작한 후 설정 > 업데이트 & **보안** > 최신 빌드를 다운로드하는 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-368">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <span data-ttu-id="e3515-369">해결 0x80070490 오류 업데이트</span><span class="sxs-lookup"><span data-stu-id="e3515-369">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="e3515-370">개발자 또는 베타 0x80070490 업데이트할 때 업데이트 오류가 발생하는 경우 다음과 같은 단기적인 해결 방법을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-370">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="e3515-371">내부자 채널을 이동하고 업데이트를 선택하고 내부자 채널을 다시 이동하는 과정이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-371">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <span data-ttu-id="e3515-372">1단계 - 릴리스 미리 보기</span><span class="sxs-lookup"><span data-stu-id="e3515-372">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="e3515-373">설정, 업데이트 & 보안, Windows Insider Program, 릴리스 미리 보기 **채널을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-373">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="e3515-374">설정, 업데이트 & 보안, Windows 업데이트, **업데이트를 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-374">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="e3515-375">업데이트 후 2단계로 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-375">After the update, continue on to Stage two.</span></span>

#### <span data-ttu-id="e3515-376">2단계 - 개발자 채널</span><span class="sxs-lookup"><span data-stu-id="e3515-376">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="e3515-377">설정, & 업데이트, Windows Insider Program, **개발자 채널을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-377">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="e3515-378">설정, 업데이트 & 보안, Windows 업데이트, **업데이트를 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-378">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <span data-ttu-id="e3515-379">FFU 다운로드 및 플래시 길</span><span class="sxs-lookup"><span data-stu-id="e3515-379">FFU download and flash directions</span></span>
<span data-ttu-id="e3515-380">플라이트 서명된 ffu로 테스트하려면 플라이트 서명된 ffu를 깜박이기 전에 먼저 디바이스 잠금 해제를 플라이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-380">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="e3515-381">PC에서:</span><span class="sxs-lookup"><span data-stu-id="e3515-381">On PC:</span></span>

    1. <span data-ttu-id="e3515-382">.에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-382">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="e3515-383">Microsoft Store에서 ARC(Advanced Recovery Companion)를 설치합니다. [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="e3515-383">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="e3515-384">HoloLens - 플라이트 \*\*\*\* 잠금 해제: 보안 Windows & 프로그램으로 설정 열기 업데이트 후 장치를 등록하고 장치를  >  \*\*\*\*  >  \*\*\*\* 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-384">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="e3515-385">플래시 FFU - 이제 ARC를 사용하여 플라이트 서명된 FFU를 플래시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-385">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="e3515-386">피드백 제공 및 문제 보고</span><span class="sxs-lookup"><span data-stu-id="e3515-386">Provide feedback and report issues</span></span>

<span data-ttu-id="e3515-387">HoloLens에서 피드백 허브 앱을 사용하여 피드백을 제공하고 문제를 보고하세요. [](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="e3515-387">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="e3515-388">피드백 허브를 사용하면 엔지니어가 문제를 빠르게 디버그하고 해결하는 데 도움이 되는 필요한 모든 진단 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-388">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="e3515-389">중국어 및 일본어 버전의 HoloLens 관련 문제는 동일한 방식으로 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-389">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="e3515-390">피드백 허브가 문서 폴더에 액세스할지 묻는 메시지를 수락해야 합니다(메시지가 표시될 때 예 선택). \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e3515-390">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="e3515-391">개발자 참고 사항</span><span class="sxs-lookup"><span data-stu-id="e3515-391">Note for developers</span></span>

<span data-ttu-id="e3515-392">환영합니다. HoloLens의 Insider 빌드를 사용하여 응용 프로그램을 개발해 보시고 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-392">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="e3515-393">[HoloLens 개발자](https://developer.microsoft.com/windows/mixed-reality/development) 설명서를 확인하여 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="e3515-393">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="e3515-394">이러한 지침은 HoloLens의 Insider 빌드에서 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-394">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="e3515-395">HoloLens 개발에 이미 사용 중이 Visual Studio Unity와 동일한 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-395">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="e3515-396">Insider 빌드 수신 중지</span><span class="sxs-lookup"><span data-stu-id="e3515-396">Stop receiving Insider builds</span></span>

<span data-ttu-id="e3515-397">Windows Holographic의 Insider 빌드를 더 이상 받지 못하게 하려는 경우 HoloLens가 프로덕션 빌드를 [](hololens-recovery.md) 실행 중일 때 옵트아웃하거나 고급 복구 도우미를 사용하여 장치를 비 Insider 버전의 Windows Holographic으로 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-397">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="e3515-398">Insider Preview 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 등록하지 않은 사용자가 파란색 화면을 경험하는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-398">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="e3515-399">이후 장치를 수동으로 복구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-399">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="e3515-400">영향이 있을지 아니면 그렇지 않을지에 대한 자세한 내용은 이 알려진 문제에서 자세히 [확인하시기 바랍니다.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)</span><span class="sxs-lookup"><span data-stu-id="e3515-400">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="e3515-401">HoloLens에서 프로덕션 빌드를 실행 중인지 확인:</span><span class="sxs-lookup"><span data-stu-id="e3515-401">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="e3515-402">Settings > **System > About로**이동하고 빌드 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-402">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="e3515-403">[프로덕션 빌드 번호에 대한 릴리스 참고를 참조합니다.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="e3515-403">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="e3515-404">Insider 빌드를 옵트아웃(opt out)하는 경우:</span><span class="sxs-lookup"><span data-stu-id="e3515-404">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="e3515-405">프로덕션 빌드를 실행하는 HoloLens에서 **Windows**> 보안 > 업데이트 & 업데이트로 이동한 > 빌드 중지를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3515-405">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="e3515-406">지침에 따라 디바이스를 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="e3515-406">Follow the instructions to opt out your device.</span></span>
