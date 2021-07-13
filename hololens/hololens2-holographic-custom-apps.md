---
title: HoloLens 2에 대한 사용자 지정 앱 관리
description: 장치 포털 및 Visual Studio 사용하여 HoloLens 2 디바이스에서 사용자 지정 홀로그램 앱을 설치, 제거 및 사이드로드하는 방법을 알아봅니다.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, sideload, side load, side-load, store, uwp, app, install
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
ms.openlocfilehash: d2280a794455090c61a7bf30bc5dc5b8faf5adbe
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636404"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="baf84-104">HoloLens 2에 대한 사용자 지정 앱 관리</span><span class="sxs-lookup"><span data-stu-id="baf84-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="baf84-105">HoloLens Microsoft Store 많은 기존 애플리케이션뿐만 아니라 HoloLens 위해 특별히 빌드된 새 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="baf84-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="baf84-106">스토어 앱에 대한 자세한 내용은 [스토어를](holographic-store-apps.md)통해 앱 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baf84-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="baf84-107">엔터프라이즈 배포의 경우 두 방법 모두에 사용되는 개발자 모드를 사용하도록 설정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="baf84-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="baf84-108">보안 앱 배포 방법에 관심이 있는 경우 [앱 관리: 개요를](app-deploy-overview.md)검토하세요.</span><span class="sxs-lookup"><span data-stu-id="baf84-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="baf84-109">HoloLens 2 디바이스에 대한 앱 설치의 개발자 방법을 원하는 경우 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baf84-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>

- [<span data-ttu-id="baf84-110">장치 포털: 앱 설치</span><span class="sxs-lookup"><span data-stu-id="baf84-110">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="baf84-111">Visual Studio 사용하여 앱 배포 및 디버그</span><span class="sxs-lookup"><span data-stu-id="baf84-111">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="baf84-112">HoloLens(1세대)에 사용자 지정 앱을 배포하려면 [가이드를](holographic-custom-apps.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baf84-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>
