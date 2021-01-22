---
title: HoloLens 2용 사용자 지정 앱 관리
description: 장치 포털 및 디바이스 포털을 사용하여 HoloLens 2 장치에 사용자 지정 홀로그램 앱을 설치, 제거 및 테스트용 로드하는 Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, 테스트용 로드, 테스트용 로드, 저장소, uwp, 앱, 설치
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297008"
---
# <span data-ttu-id="ee436-104">HoloLens 2용 사용자 지정 앱 관리</span><span class="sxs-lookup"><span data-stu-id="ee436-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="ee436-105">HoloLens는 Microsoft Store 뿐만 아니라 HoloLens를 위해 특별히 만들어진 모든 새로운 앱에서 다양하고 흥미로운 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ee436-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="ee436-106">스토어 앱에 대한 자세한 내용은 스토어에서 [앱 관리를 참조하세요.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="ee436-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee436-107">엔터프라이즈 배포의 경우 개발자 모드를 사용하도록 설정하지 않는 것이 좋습니다. 이 두 방법 모두에서 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee436-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="ee436-108">보안 앱 배포 방법에 관심이 있는 경우 앱 관리: 개요를 [검토하세요.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ee436-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="ee436-109">HoloLens 2 장치에 대한 앱 설치 개발자 방법을 찾고 있는 경우 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee436-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="ee436-110">디바이스 포털: 앱 설치</span><span class="sxs-lookup"><span data-stu-id="ee436-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="ee436-111">앱 Visual Studio 배포 및 디버그</span><span class="sxs-lookup"><span data-stu-id="ee436-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="ee436-112">HoloLens(1세대)에 사용자 지정 앱을 배포하고자 하는 경우 가이드를 참조하세요. [](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="ee436-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>