---
title: Microsoft HoloLens 참가자 미리 보기
description: 간단하게 Insider 빌드를 시작하고 HoloLens의 다음 주요 운영 체제 업데이트에 대한 중요한 피드백을 제공할 수 있습니다.
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 5da96d2838cbe1a02956a3e567c6ecf6da9d6b10
ms.sourcegitcommit: c93f23fe7c27dfa45fef300a4fc91aa811bc8126
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269483"
---
# <span data-ttu-id="b6643-103">Microsoft HoloLens 참가자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="b6643-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="b6643-104">HoloLens용 최신 Insider Preview 빌드를 시작하세요!</span><span class="sxs-lookup"><span data-stu-id="b6643-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="b6643-105">HoloLens의 [](hololens-insider.md#start-receiving-insider-builds) 다음 주요 운영 체제 업데이트에 대해 간단하게 시작하고 중요한 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="b6643-106">Windows Insider Release Notes</span><span class="sxs-lookup"><span data-stu-id="b6643-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="b6643-107">Windows Insiders에 새로운 기능의 플라이트를 다시 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="b6643-108">We will be flighting to the Dev Channel for the latest updates.</span><span class="sxs-lookup"><span data-stu-id="b6643-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="b6643-109">Windows Insider 빌드에 추가 기능 및 업데이트를 추가하면 이 페이지가 계속 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="b6643-110">이러한 업데이트를 현실에 혼합할 수 있도록 기다렸다가 준비하세요.</span><span class="sxs-lookup"><span data-stu-id="b6643-110">Get excited and ready to mix these updates into your reality.</span></span> 

| <span data-ttu-id="b6643-111">기능 이름</span><span class="sxs-lookup"><span data-stu-id="b6643-111">Feature Name</span></span>                                              | <span data-ttu-id="b6643-112">간단한 설명</span><span class="sxs-lookup"><span data-stu-id="b6643-112">Short description</span></span>                                                                      | <span data-ttu-id="b6643-113">빌드에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="b6643-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="b6643-114">새 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b6643-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="b6643-115">이제 HoloLens 2에서 새로운 Chromium 기반 Microsoft Edge를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="b6643-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b6643-116">20279.1006</span></span> |
| [<span data-ttu-id="b6643-117">새 설정 앱</span><span class="sxs-lookup"><span data-stu-id="b6643-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="b6643-118">레거시 설정 앱이 새로운 기능 및 설정으로 업데이트된 버전으로 대체되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="b6643-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b6643-119">20279.1006</span></span> |
| [<span data-ttu-id="b6643-120">기본 앱 선택기</span><span class="sxs-lookup"><span data-stu-id="b6643-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="b6643-121">각 파일 또는 링크 유형에 대해 시작해야 하는 앱 선택</span><span class="sxs-lookup"><span data-stu-id="b6643-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="b6643-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b6643-122">20279.1006</span></span> |
| [<span data-ttu-id="b6643-123">Office Web App</span><span class="sxs-lookup"><span data-stu-id="b6643-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="b6643-124">Office Web App 바로 가기가 이제 "모든 앱"에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="b6643-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b6643-125">20279.1006</span></span> |
| [<span data-ttu-id="b6643-126">스와이프하여 입력</span><span class="sxs-lookup"><span data-stu-id="b6643-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="b6643-127">손가락 팁을 사용하여 홀로그램 키보드에서 단어 "스와이프"</span><span class="sxs-lookup"><span data-stu-id="b6643-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="b6643-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b6643-128">20279.1006</span></span> |

### <span data-ttu-id="b6643-129">새 Microsoft Edge 소개</span><span class="sxs-lookup"><span data-stu-id="b6643-129">Introducing the new Microsoft Edge</span></span>

![새 Microsoft Edge 로고에 대한 레거시 Microsoft Edge 로고 애니메이션](images/new-edge.gif)

<span data-ttu-id="b6643-131">새로운 Microsoft [Edge는 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 오픈 소스 프로젝트를 채택하여 고객에게 더 나은 호환성을 만들고 웹 개발자를 위한 웹 조각화가 줄어 습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-131">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span> 

<span data-ttu-id="b6643-132">이 Insider 미리 보기를 통해 HoloLens 2 고객은 새 Microsoft Edge를 처음으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-132">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="b6643-133">새 Microsoft Edge는 결국 HoloLens 2의 레거시 Microsoft Edge를 대체하는 반면, 현재 두 브라우저는 모두 Insiders에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-133">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="b6643-134">새 Microsoft Edge 또는 피드백 허브를 통해 피드백 보내기 기능을 통해 피드백 및 버그를 팀과 [공유해 주세요.](hololens-feedback.md) \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6643-134">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![새 Microsoft Edge 스크린샷](images/new-edge-ui.png)

#### <span data-ttu-id="b6643-136">새 Microsoft Edge 시작</span><span class="sxs-lookup"><span data-stu-id="b6643-136">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="b6643-137">Insiders에 사용할 수 있는 두 가지 버전의 Microsoft Edge가 있습니다. 새 Microsoft Edge 새 Microsoft Edge 아이콘(파란색 및 녹색 소용구 아이콘으로 표시)과 레거시 ![ Microsoft Edge(흰색 "e" 아이콘으로 표시)가 ](images/new_edge_logo.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-137">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and the legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="b6643-138">새 Microsoft Edge가 시작 메뉴에 고정되고 웹 링크를 활성화하면 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-138">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="b6643-139">레거시 Microsoft Edge를 기본 웹 브라우저로 다시 사용하겠는 경우 아래 지침을 참조하여 기본 앱을 [초기화하세요.](#default-app-picker)</span><span class="sxs-lookup"><span data-stu-id="b6643-139">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="b6643-140">HoloLens 2에서 새 Microsoft Edge를 처음 시작하면 레거시 Microsoft Edge에서 설정 및 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-140">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="b6643-141">새 Microsoft Edge를 시작한 후 레거시 Microsoft Edge를 계속 사용하는 경우 새 데이터는 레거시 Microsoft Edge에서 새 Microsoft Edge로 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-141">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="b6643-142">새 Microsoft Edge에 대한 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b6643-142">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="b6643-143">새로운 Microsoft Edge는 IT 프로에게 이전에 레거시 Microsoft Edge에서 사용할 수 있는 것보다 HoloLens 2의 훨씬 광범위한 브라우저 정책 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-143">The new Microsoft Edge offers IT Pros a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span> 

<span data-ttu-id="b6643-144">다음은 새 Microsoft Edge의 정책 설정 관리에 대한 자세한 정보를 알아보는 데 도움이 되는 몇 가지 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-144">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>
- [<span data-ttu-id="b6643-145">Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b6643-145">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="b6643-146">Microsoft Edge 레거시에서 Microsoft Edge로 정책 매핑</span><span class="sxs-lookup"><span data-stu-id="b6643-146">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="b6643-147">Google Chrome에서 Microsoft Edge로 정책 매핑</span><span class="sxs-lookup"><span data-stu-id="b6643-147">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="b6643-148">전체 [Microsoft Edge Enterprise 설명서](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="b6643-148">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6643-149">새 Microsoft Edge에서 지원되는 브라우저 정책의 양 때문에 Microsoft 팀은 각 새 정책이 HoloLens 2에서 작동하는지 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-149">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="b6643-150">그러나 이전에 HoloLens 2에서 지원했던 각 레거시 Microsoft Edge 정책에 해당하는 새 Microsoft Edge가 예상대로 작동하고 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-150">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="b6643-151">Microsoft [Edge 레거시와 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 정책 매핑을 참조하여 HoloLens 2에서 사용 중이던 각 레거시 Microsoft Edge 브라우저 정책에 해당하는 새 Microsoft Edge를 찾아 보십시오.</span><span class="sxs-lookup"><span data-stu-id="b6643-151">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="b6643-152">HoloLens 2에서 작동하지 않는 \*\* 새로운 Microsoft Edge 정책이 두 개 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-152">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="b6643-153">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="b6643-153">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="b6643-154">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="b6643-154">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="b6643-155">HoloLens 2의 새로운 Microsoft Edge에서 예상할 일</span><span class="sxs-lookup"><span data-stu-id="b6643-155">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="b6643-156">새 Microsoft Edge는 HoloLens 2와 같은 UWP 전용 장치에서 실행될 수 있도록 하는 새로운 UWP 어댑터 계층이 있는 네이티브 Win32 앱이기 때문에 일부 기능을 즉시 사용할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-156">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="b6643-157">앞으로 몇 개월 동안 새로운 시나리오 및 기능을 지원할 예정이니 이 공간에서 최신 정보를 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-157">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="b6643-158">작동해야 하는 시나리오 및 기능:</span><span class="sxs-lookup"><span data-stu-id="b6643-158">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="b6643-159">첫 실행 환경, 프로필에 로그인 및 동기화</span><span class="sxs-lookup"><span data-stu-id="b6643-159">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="b6643-160">웹 사이트가 렌더링 및 예상대로 행동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-160">Websites should render and behave as expected</span></span>
- <span data-ttu-id="b6643-161">대부분의 브라우저 기능(즐겨찾기, 기록 등)이 예상대로 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-161">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="b6643-162">어두운 모드</span><span class="sxs-lookup"><span data-stu-id="b6643-162">Dark mode</span></span>
- <span data-ttu-id="b6643-163">장치에 웹앱 설치</span><span class="sxs-lookup"><span data-stu-id="b6643-163">Installing web apps to the device</span></span>
- <span data-ttu-id="b6643-164">확장 설치(HoloLens 2에서 제대로 작동하지 않는 확장을 사용하는 경우 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="b6643-164">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="b6643-165">PDF 보기 및 표시</span><span class="sxs-lookup"><span data-stu-id="b6643-165">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="b6643-166">단일 브라우저 창의 공간 소리</span><span class="sxs-lookup"><span data-stu-id="b6643-166">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="b6643-167">브라우저의 자동 및 수동 업데이트</span><span class="sxs-lookup"><span data-stu-id="b6643-167">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="b6643-168">인쇄 메뉴에서 PDF 저장("PDF로 저장" 옵션 사용)</span><span class="sxs-lookup"><span data-stu-id="b6643-168">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="b6643-169">곧 제공될 시나리오 및 기능:</span><span class="sxs-lookup"><span data-stu-id="b6643-169">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="b6643-170">WebXR 및 360 뷰어 확장</span><span class="sxs-lookup"><span data-stu-id="b6643-170">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="b6643-171">환경에 배치된 여러 창을 탐색할 때 창을 수정하기 위한 콘텐츠 복원</span><span class="sxs-lookup"><span data-stu-id="b6643-171">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="b6643-172">동시 오디오 스트림이 있는 여러 창의 공간 소리</span><span class="sxs-lookup"><span data-stu-id="b6643-172">Spatial sound for multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="b6643-173">비디오, 혼합 현실 캡처 또는 화면 공유를 사용하여 브라우저를 통해 Microsoft Teams 통화에 참가(오디오를 사용하여 통화에 참가하는 것이 잘 작동)</span><span class="sxs-lookup"><span data-stu-id="b6643-173">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>
- <span data-ttu-id="b6643-174">"참조, 말하기"</span><span class="sxs-lookup"><span data-stu-id="b6643-174">"See it, say it"</span></span>
- <span data-ttu-id="b6643-175">인쇄</span><span class="sxs-lookup"><span data-stu-id="b6643-175">Printing</span></span>

**<span data-ttu-id="b6643-176">가장 알려진 브라우저 문제:</span><span class="sxs-lookup"><span data-stu-id="b6643-176">Top known browser issues:</span></span>**
- <span data-ttu-id="b6643-177">장치를 초기화하면 새 Microsoft Edge가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-177">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="b6643-178">홀로그램 키보드의 돋보기 미리 보기에 잘못된 콘텐츠가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-178">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

### <span data-ttu-id="b6643-179">새 설정 앱</span><span class="sxs-lookup"><span data-stu-id="b6643-179">New Settings app</span></span>

<span data-ttu-id="b6643-180">이 릴리스에서는 새로운 버전의 설정 앱을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-180">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="b6643-181">새 설정 앱에는 소리, Power & 절전, 네트워크 & 인터넷, 앱, 계정, 접근성 등 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-181">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="b6643-182">새 설정 앱은 레거시 설정 앱과는 별개이기 때문에 이전에 환경에 배치한 설정 창은 업데이트 시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-182">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![새 설정 앱 홈페이지](images/new-settings-app.png)

**<span data-ttu-id="b6643-184">새로운 기능 및 설정</span><span class="sxs-lookup"><span data-stu-id="b6643-184">New features and settings</span></span>**
- <span data-ttu-id="b6643-185">설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈에서 설정 검색</span><span class="sxs-lookup"><span data-stu-id="b6643-185">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="b6643-186">시스템 > 소리:</span><span class="sxs-lookup"><span data-stu-id="b6643-186">System > Sound:</span></span>
  - <span data-ttu-id="b6643-187">입력 및 출력 오디오 장치: 입력 및 출력 오디오 장치를 독립적으로 선택하십시오(예: Bluetooth 헤드폰을 통해 오디오를 듣거나 오디오 입력에 USB-C 마이크를 사용).</span><span class="sxs-lookup"><span data-stu-id="b6643-187">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="b6643-188">참고: Bluetooth 마이크는 HoloLens 2에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-188">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="b6643-189">앱 볼륨: 각 앱의 볼륨을 독립적으로 조정</span><span class="sxs-lookup"><span data-stu-id="b6643-189">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="b6643-190">시스템 > 전원 & 절전: 장치가 비활성 기간 후 절전으로 이동해야 하는 시기 선택</span><span class="sxs-lookup"><span data-stu-id="b6643-190">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="b6643-191">시스템 > 배터리: 배터리 절약 모드를 수동으로 사용하도록 설정하거나 배터리 절약 모드가 자동으로 켜진 지점에 배터리 임계값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-191">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="b6643-192">USB > 장치: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-192">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="b6643-193">네트워크 & 인터넷:</span><span class="sxs-lookup"><span data-stu-id="b6643-193">Network & Internet:</span></span>
  - <span data-ttu-id="b6643-194">이제 USB-C 이더넷 어댑터가 네트워크 & 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-194">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="b6643-195">이제 해당 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-195">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="b6643-196">이제 HoloLens 2에서 비행기 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-196">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="b6643-197">앱: 파일 및 링크 유형에 사용되는 기본 앱을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-197">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="b6643-198">자세한 [내용은 기본 앱 선택을](#default-app-picker) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6643-198">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="b6643-199">다른 > 사용자에 대한 계정: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-199">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="b6643-200">접근성: 텍스트 크기 및 일부 시각적 효과 변경</span><span class="sxs-lookup"><span data-stu-id="b6643-200">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="b6643-201">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b6643-201">Known issues</span></span>**
- <span data-ttu-id="b6643-202">이전에 배치된 설정 창이 제거됩니다(위의 참고 참조).</span><span class="sxs-lookup"><span data-stu-id="b6643-202">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="b6643-203">알림 페이지를 방문하면 설정 앱이 충돌할 수 있습니다(조사 중).</span><span class="sxs-lookup"><span data-stu-id="b6643-203">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="b6643-204">현재 이더넷 페이지가 표시되지 않습니다(곧 수정될 예정).</span><span class="sxs-lookup"><span data-stu-id="b6643-204">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="b6643-205">UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램 특성으로 인해 새 Microsoft Edge의 배터리 사용량이 정확하지 않을 수 있습니다(곧 수정이 예상되지 않을 예정입니다).</span><span class="sxs-lookup"><span data-stu-id="b6643-205">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="b6643-206">기본 앱 선택기</span><span class="sxs-lookup"><span data-stu-id="b6643-206">Default app picker</span></span>

<span data-ttu-id="b6643-207">하이퍼링크를 활성화하거나 앱을 지원하는 설치된 앱이 두 개 이상 있는 파일 형식을 열면 파일 또는 링크 형식을 처리해야 하는 설치된 앱을 선택하라는 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-207">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="b6643-208">이 창에서 선택한 앱이 파일 또는 링크 형식 "한 번" 또는 "항상"을 처리하게 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-208">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span> 

![앱 선택기 창](images/default-app-picker.png)

<span data-ttu-id="b6643-210">"항상"을 선택하지만 나중에 특정 파일 또는 링크 형식을 처리하는 앱을 변경하려면 앱의 설정에서 저장된 기본값을 **> 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b6643-210">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="b6643-211">페이지 아래쪽으로 스크롤하고 "파일 \*\*\*\* 형식에 대한 기본 앱" 및/또는 "링크 형식의 기본 앱"에서 지우기 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-211">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="b6643-212">데스크톱 PC의 유사한 설정과 달리 개별 파일 형식 기본값은 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-212">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="b6643-213">Office Web App</span><span class="sxs-lookup"><span data-stu-id="b6643-213">Office web app</span></span>

<span data-ttu-id="b6643-214">Office Web App이 시작 메뉴의 "모든 앱" 목록에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-214">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="b6643-215">이 웹앱은 시작 또는 제거에 고정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-215">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="b6643-216">웹앱이기 때문에 해당 기능은 방문하여 경험하는 기능과 정확히 https://www.office.com 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-216">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="b6643-217">Office Web App 기능은 HoloLens 2에 활성 인터넷 연결이 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-217">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="b6643-218">스와이프하여 입력</span><span class="sxs-lookup"><span data-stu-id="b6643-218">Swipe to type</span></span>

<span data-ttu-id="b6643-219">일부 고객은 입력하려는 단어의 모양을 스와이프하여 가상 키보드에서 "입력"하는 것이 더 빠르며 홀로그램 키보드에 대해 이 기능을 미리 보고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-219">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="b6643-220">홀로그램 키보드의 평면을 통해 손가락 팁을 전달하고 단어의 모양을 스와이프한 다음 키보드 평면에서 손가락 끝을 철회하여 한 단어씩 한 번씩 스와이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-220">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="b6643-221">단어 사이에 있는 키보드에서 손가락을 제거하여 스페이스바를 누르지 않고도 후속 단어를 스와이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-221">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="b6643-222">키보드에서 손가락을 움직일 때 뒤로 미는 내선이 표시될 경우 이 기능이 작동하고 있는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-222">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="b6643-223">휴대폰 디스플레이와 달리 손가락에 대한 저항이 느껴지지 않는 홀로그램 키보드의 특성 때문에 이 기능을 사용 및 마스터하기가 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-223">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="b6643-224">이 기능은 공개 릴리스에서 평가 중이기 때문에 사용자 의견이 중요합니다. 이 기능이 유용하게 사용되거나 생성적 피드백이 있는지 여부에 따라 피드백 허브를 통해 [알려주세요.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="b6643-224">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>





## <span data-ttu-id="b6643-225">Insider 빌드 수신 시작</span><span class="sxs-lookup"><span data-stu-id="b6643-225">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="b6643-226">If you haven't updated recently, please reboot your device to update state and get the latest build.</span><span class="sxs-lookup"><span data-stu-id="b6643-226">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="b6643-227">"다시부팅 장치" 음성 명령이 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-227">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="b6643-228">설정/Windows Insider 프로그램에서 다시 시작 단추를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-228">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="b6643-229">백 엔드에서 발생할 수 있는 버그가 발생하여 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-229">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="b6643-230">HoloLens 2 장치에서 보안 \*\*\*\* Windows & 설정 업데이트로 이동하고  >  \*\*\*\*  >  \*\*\*\* **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6643-230">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="b6643-231">Windows Insider로 등록하는 데 사용한 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-231">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="b6643-232">Windows 내부자는 이제 채널로 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-232">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="b6643-233">빠른 **링은** 개발자 채널이 되고, **슬로우** 링은 \*\*\*\* 베타 채널이 **되고,** 릴리스 미리 보기 링은 릴리스 미리 보기 \*\*\*\* **채널이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b6643-233">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="b6643-234">매핑의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-234">Here is what that mapping looks like:</span></span>

![Windows Insider Channels 설명](images/WindowsInsiderChannels.png)

<span data-ttu-id="b6643-236">자세한 내용은 Windows 블로그에 [Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 소개를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6643-236">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="b6643-237">그런 다음 **Windows의 활성**개발을 선택하고 개발자 \*\*\*\* 채널 또는 \*\*\*\* 베타 채널 빌드를 받을지 여부를 선택하고 프로그램 용어를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-237">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="b6643-238">지금 **다시 > 확인을** 선택하여 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-238">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="b6643-239">장치를 다시 시작한 후 설정 > 업데이트 & **보안** > 최신 빌드를 다운로드하는 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-239">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="b6643-240">FFU 다운로드 및 플래시 길</span><span class="sxs-lookup"><span data-stu-id="b6643-240">FFU download and flash directions</span></span>
<span data-ttu-id="b6643-241">플라이트 서명된 ffu로 테스트하려면 플라이트 서명된 ffu를 깜박이기 전에 먼저 디바이스 잠금 해제를 플라이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-241">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="b6643-242">PC에서:</span><span class="sxs-lookup"><span data-stu-id="b6643-242">On PC:</span></span>

    1. <span data-ttu-id="b6643-243">.에서 PC에 ffu를 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-243">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="b6643-244">Microsoft Store에서 ARC(Advanced Recovery Companion)를 설치합니다. [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="b6643-244">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="b6643-245">HoloLens - 플라이트 \*\*\*\* 잠금 해제: 보안 Windows & 프로그램으로 설정 열기 업데이트 후 장치를 등록하고 장치를  >  \*\*\*\*  >  \*\*\*\* 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-245">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="b6643-246">플래시 FFU - 이제 ARC를 사용하여 플라이트 서명된 FFU를 플래시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-246">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="b6643-247">피드백 제공 및 문제 보고</span><span class="sxs-lookup"><span data-stu-id="b6643-247">Provide feedback and report issues</span></span>

<span data-ttu-id="b6643-248">HoloLens에서 피드백 허브 앱을 사용하여 피드백을 제공하고 문제를 보고하세요. [](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="b6643-248">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="b6643-249">피드백 허브를 사용하면 엔지니어가 문제를 빠르게 디버그하고 해결하는 데 도움이 되는 필요한 모든 진단 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-249">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="b6643-250">중국어 및 일본어 버전의 HoloLens 관련 문제는 동일한 방식으로 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-250">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="b6643-251">피드백 허브가 문서 폴더에 액세스할지 묻는 메시지를 수락해야 합니다(메시지가 표시될 때 예 선택). \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6643-251">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="b6643-252">개발자 참고 사항</span><span class="sxs-lookup"><span data-stu-id="b6643-252">Note for developers</span></span>

<span data-ttu-id="b6643-253">환영합니다. HoloLens의 Insider 빌드를 사용하여 응용 프로그램을 개발해 보시고 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-253">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="b6643-254">[HoloLens 개발자](https://developer.microsoft.com/windows/mixed-reality/development) 설명서를 확인하여 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b6643-254">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="b6643-255">이러한 지침은 HoloLens의 Insider 빌드에서 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-255">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="b6643-256">HoloLens 개발에 이미 사용 중이 Visual Studio Unity와 동일한 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-256">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="b6643-257">Insider 빌드 수신 중지</span><span class="sxs-lookup"><span data-stu-id="b6643-257">Stop receiving Insider builds</span></span>

<span data-ttu-id="b6643-258">Windows Holographic의 Insider 빌드를 더 이상 받지 못하게 하려는 경우 HoloLens가 프로덕션 빌드를 [](hololens-recovery.md) 실행 중일 때 옵트아웃하거나 고급 복구 도우미를 사용하여 장치를 비 Insider 버전의 Windows Holographic으로 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-258">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="b6643-259">Insider Preview 빌드를 수동으로 다시 설치한 후 Insider Preview 빌드에서 등록을 등록하지 않은 사용자가 파란색 화면을 경험하는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-259">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="b6643-260">이후 장치를 수동으로 복구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-260">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="b6643-261">영향이 있을지 아니면 그렇지 않을지에 대한 자세한 내용은 이 알려진 문제에서 자세히 [확인하시기 바랍니다.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)</span><span class="sxs-lookup"><span data-stu-id="b6643-261">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="b6643-262">HoloLens에서 프로덕션 빌드를 실행 중인지 확인:</span><span class="sxs-lookup"><span data-stu-id="b6643-262">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="b6643-263">Settings > **System > About로**이동하고 빌드 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-263">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="b6643-264">[프로덕션 빌드 번호에 대한 릴리스 참고를 참조합니다.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="b6643-264">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="b6643-265">Insider 빌드를 옵트아웃(opt out)하는 경우:</span><span class="sxs-lookup"><span data-stu-id="b6643-265">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="b6643-266">프로덕션 빌드를 실행하는 HoloLens에서 **Windows**> 보안 > 업데이트 & 업데이트로 이동한 > 빌드 중지를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6643-266">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="b6643-267">지침에 따라 디바이스를 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="b6643-267">Follow the instructions to opt out your device.</span></span>
