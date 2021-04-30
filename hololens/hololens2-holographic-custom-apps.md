---
title: HoloLens 용 사용자 지정 앱 관리 2
description: 장치 포털 및 Visual Studio를 사용 하 여 HoloLens 2 장치에 사용자 지정 holographic apps를 설치, 제거 및 함께 로드 하는 방법을 알아봅니다.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, 테스트용으로 로드, 부하, 테스트용 부하, 스토어, uwp, 앱, 설치
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309293"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="d9b7e-104">HoloLens 용 사용자 지정 앱 관리 2</span><span class="sxs-lookup"><span data-stu-id="d9b7e-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="d9b7e-105">HoloLens는 현재 HoloLens 용으로 빌드된 새로운 앱 뿐만 아니라 Microsoft Store의 많은 기존 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7e-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="d9b7e-106">스토어 앱에 대 한 자세한 내용은 [스토어를 사용 하 여 앱 관리](holographic-store-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7e-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9b7e-107">엔터프라이즈 배포의 경우 이러한 방법 모두를 사용 하는 개발자 모드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7e-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="d9b7e-108">안전한 앱 배포 방법에 관심이 있는 경우 [앱 관리: 개요](app-deploy-overview.md)를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7e-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="d9b7e-109">HoloLens 2 장치에 대 한 앱 설치 개발자 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7e-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="d9b7e-110">장치 포털: 앱 설치</span><span class="sxs-lookup"><span data-stu-id="d9b7e-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="d9b7e-111">Visual Studio를 사용 하 여 응용 프로그램 배포 및 디버그</span><span class="sxs-lookup"><span data-stu-id="d9b7e-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="d9b7e-112">HoloLens (첫 번째 gen)에서 사용자 지정 앱을 배포 하려면 [가이드](holographic-custom-apps.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7e-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>