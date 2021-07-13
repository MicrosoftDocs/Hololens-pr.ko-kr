---
title: 새 설정 앱 소개
description: 새 설정 앱에 대해 알아보기
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, 설정, 앱 선택기, 볼륨
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398910"
---
# <a name="new-settings-app"></a><span data-ttu-id="51af8-104">새 설정 앱</span><span class="sxs-lookup"><span data-stu-id="51af8-104">New Settings app</span></span>

<span data-ttu-id="51af8-105">[Windows Holographic, 버전 21H1](hololens-release-notes.md#windows-holographic-version-21h1)에서는 새 버전의 설정 앱을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="51af8-106">새 설정 앱에는 소리, 전원 및 절전 모드, 네트워크 및 인터넷, 앱, 계정, 접근성 등의 영역에서 HoloLens 2에 대한 새로운 기능과 확장된 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="51af8-107">새 설정 앱은 레거시 설정 앱과 구별되므로 이전에 사용 환경에 있었던 모든 설정 창은 업데이트 시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![새 설정 앱 홈페이지](images/new-settings-app.png)

<span data-ttu-id="51af8-109">**새로운 기능 및 설정**</span><span class="sxs-lookup"><span data-stu-id="51af8-109">**New features and settings**</span></span>
- <span data-ttu-id="51af8-110">설정 검색: 키워드 또는 설정 이름을 사용하여 설정 홈페이지에서 설정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="51af8-111">시스템 > [색 보정](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="51af8-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="51af8-112">HoloLens 2 디스플레이의 대체 색 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="51af8-113">시스템 > 소리:</span><span class="sxs-lookup"><span data-stu-id="51af8-113">System > Sound:</span></span>
  - <span data-ttu-id="51af8-114">입력 및 출력 오디오 장치: 입력 오디오 장치와 출력 오디오 장치(예: Bluetooth 헤드폰을 통한 오디오 수신 또는 오디오 입력용 USB-C 마이크 사용)를 따로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="51af8-115">Bluetooth 마이크는 HoloLens 2에서 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="51af8-116">앱 볼륨: 각 앱의 볼륨을 따로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="51af8-117">[앱당 볼륨 조절](holographic-home.md#per-app-volume-control)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51af8-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="51af8-118">시스템 > 전원 및 절전: 비활성 기간 후에 장치가 절전 모드로 바뀌어야 하는 시기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="51af8-119">시스템 > 배터리: 수동으로 배터리 절약 모드 모드를 사용하도록 설정하거나 배터리 절약 모드 모드가 자동으로 켜지는 배터리 임계값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="51af8-120">장치 > USB: 기본적으로 USB 연결을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="51af8-121">네트워크 및 인터넷:</span><span class="sxs-lookup"><span data-stu-id="51af8-121">Network & Internet:</span></span>
  - <span data-ttu-id="51af8-122">이제 USB-C 이더넷 어댑터가 네트워크 및 인터넷에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="51af8-123">이제 IP 주소를 포함하여 USB-C 이더넷 어댑터 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="51af8-124">이제 HoloLens 2 비행기 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="51af8-125">앱: 파일 형식과 링크 유형에 사용되는 기본 앱을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="51af8-126">자세한 내용은 [기본 앱 선택기](holographic-home.md#default-app-picker)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51af8-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="51af8-127">계정 > 다른 사용자: 장치 소유자는 사용자를 추가하고, 표준 사용자를 장치 소유자로 업그레이드하고, 장치 소유자를 표준 사용자로 다운그레이드하고, 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="51af8-128">접근성: 텍스트 크기와 일부 시각적 효과를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="51af8-129">**알려진 문제**</span><span class="sxs-lookup"><span data-stu-id="51af8-129">**Known issues**</span></span>
- <span data-ttu-id="51af8-130">이전에 배치된 설정 창이 제거됩니다(위 참고 사항 참조).</span><span class="sxs-lookup"><span data-stu-id="51af8-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="51af8-131">더 이상 설정 앱을 통해 장치 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="51af8-132">IT 관리자는 [HoloLens 2용 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 장치 이름 템플릿 또는 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 노드를 사용하여 장치 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="51af8-133">이더넷 페이지에는 항상 가상 이더넷 장치("UsbNcm")가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51af8-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="51af8-134">UWP 어댑터 계층에서 지원하는 Win32 데스크톱 응용 프로그램의 특성 때문에 새 Microsoft Edge 대한 배터리 사용량이 정확하지 않을 수 있습니다(곧 수정될 예정 없음).</span><span class="sxs-lookup"><span data-stu-id="51af8-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

