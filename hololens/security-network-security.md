---
title: 네트워크 보안
description: 네트워크 보안
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, Hololens, 네트워크, 네트워크 보안
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c88a9af7369a6a9d6fb115fb820c0a4da13eafdc
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865843"
---
# <span data-ttu-id="8785f-104">네트워크 보안</span><span class="sxs-lookup"><span data-stu-id="8785f-104">Network security</span></span>

## <span data-ttu-id="8785f-105">네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="8785f-105">Network protocols</span></span>

<span data-ttu-id="8785f-106">오래된 NetBIOS(네트워크 기본 입출력 시스템)는 과거에는 종종 컴퓨터와 공유 폴더에 이름 확인을 제공하는 용도로 주로 LAN 시나리오에서 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="8785f-107">하지만 시간이 지나면서 NetBIOS가 여러 공격에 취약한 것으로 입증되고 다른 더 보안성 있는 프로토콜을 선호하면서 이것의 타당성이 줄었습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="8785f-108">이 취약점 문제를 제거하기 위해 HoloLens 2에서 운영 체제의 NetBIOS 관련 코드를 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="8785f-109">TLS(전송 계층 보안) 프로토콜은 꾸준히 진화하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="8785f-110">이 영역에서 발견된 다양한 보안 악용을 방지하기 위해 컴퓨팅 업계는 더 최신 버전 및 보다 효과적인 버전으로 변화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="8785f-111">모든 서버 배포에서 새 TLS 프로토콜 버전을 채택하는데 필요한 시간 때문에 다른 기본 프로토콜 버전의 클라이언트와 서버에서 전환 기간 동안 계속 통신할 수 있도록 하는 대체 메커니즘을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

<span data-ttu-id="8785f-112">그러나 그러한 대체 메커니즘은 보안 위험을 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-112">However, such fallback mechanisms increase security risks.</span></span> <span data-ttu-id="8785f-113">이 문제를 알고 있기 때문에 HoloLens 2에서 TLS 1.2에서 TLS 1.1 또는 1.0으로의 대체는 사용할 수 없습니다. 이 기능을 사용하는 사용자 인터페이스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-113">Understanding this issue, in HoloLens 2 the fallback from TLS 1.2 to TLS 1.1 or 1.0 has been disabled, and there is no user interface to enable it.</span></span> <span data-ttu-id="8785f-114">또한, TLS 핸드셰이크 중에 클라이언트는 TLS 1.2를 요청하고 서버를 하위 버전으로 다운그레이드하는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-114">Furthermore, during the TLS handshake, the client will ask for TLS 1.2, and does not allow the server to downgrade to a lower version.</span></span>

## <span data-ttu-id="8785f-115">보안 연결</span><span class="sxs-lookup"><span data-stu-id="8785f-115">Secure connectivity</span></span> 

<span data-ttu-id="8785f-116">Windows Defender 방화벽은 장치 연결 보안을 위한 중요한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-116">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="8785f-117">HoloLens 2를 사용하면 방화벽이 항상 사용되고 있으며 이것을 프로그래밍 방식으로 또는 UI를 통해 사용하지 않도록 설정할 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-117">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="8785f-118">모바일 클라이언트에 대한 원격 액세스 및 연결 개인정보 보호는 [UWP VPN 플러그인 플랫폼](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)을 통해 보장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-118">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="8785f-119">타사 VPN 공급자는 AppContainer 샌드박스 내에서 실행되는 WinRT API를 사용하여 고유한 플러그인을 만들 수 있으며, 시스템 수준 드라이버 작성에 자주 관련되는 복잡성과 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8785f-119">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
