---
title: 셀룰러 및 5G에 연결
description: HoloLens 혼합 현실 장치에서 셀룰러 네트워크에 연결
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385647"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="b17ab-103">셀룰러 및 5G에 연결</span><span class="sxs-lookup"><span data-stu-id="b17ab-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="b17ab-104">HoloLens 2는 셀룰러 및 5G 네트워크에 연결하는 두 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="b17ab-105">일반적으로 "핫스팟"이라고 하는 셀룰러 장치에서 제공하는 임시 WiFi 네트워크</span><span class="sxs-lookup"><span data-stu-id="b17ab-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="b17ab-106">USB-C 테더링 장치에 대한 제한된 지원</span><span class="sxs-lookup"><span data-stu-id="b17ab-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="b17ab-107">핫스팟(WiFi)</span><span class="sxs-lookup"><span data-stu-id="b17ab-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="b17ab-108">대부분의 셀룰러 연결 요구는 핫스팟을 통해 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="b17ab-109">HoloLens 2 WiFi는 가장 일반적인 사용 사례에 필요한 대역폭 및 대기 시간 요구 사항을 제공할 수 있는 802.11ac를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="b17ab-110">WiFi에는 케이블이 필요 없으며 최대 수의 셀룰러 장치와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="b17ab-111">핫스팟에 연결</span><span class="sxs-lookup"><span data-stu-id="b17ab-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="b17ab-112">핫스팟 모드를 사용하도록 설정하는 방법에 대한 장치의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b17ab-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="b17ab-113">핫스팟 모드를 사용하도록 설정하고 네트워크 이름과 알려진 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="b17ab-114">HoloLens 2 네트워크 설정에서 2단계에서 만든 WiFi 네트워크를 찾아 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="b17ab-115">USB-C 테더링</span><span class="sxs-lookup"><span data-stu-id="b17ab-115">USB-C Tethering</span></span>

<span data-ttu-id="b17ab-116">USB-C 테더링은 필요한 고급 워크로드의 대기 시간을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="b17ab-117">예를 들어 [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)은 테더링의 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="b17ab-118">테더링에는 셀룰러 장치와 HoloLens 사이에 케이블이 필요하며 제한된 수의 장치에서 테더링이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="b17ab-119">USB-C 호환성</span><span class="sxs-lookup"><span data-stu-id="b17ab-119">USB-C compatibility</span></span>

<span data-ttu-id="b17ab-120">자신을 이더넷 어댑터로 표시하는 장치는 Windows Holographic 버전 2004 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="b17ab-121">자신을 이더넷 어댑터로 표시하지 않는 장치는 일반 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 드라이버를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="b17ab-122">장치의 제조업체에 일반 Microsoft RNDIS 드라이버를 지원하는지 여부를 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="b17ab-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="b17ab-123">RNDIS와 호환되지 않는 장치 또는 드라이버 또는 응용 프로그램을 설치해야 하는 장치는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="b17ab-124">Microsoft는 호환되는 장치 목록을 유지 관리하지는 않지만, [여기](https://aka.ms/HLCommunityCell)에 주제에 대한 커뮤니티 토론이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="b17ab-125">테더링된 장치에 연결</span><span class="sxs-lookup"><span data-stu-id="b17ab-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="b17ab-126">USB를 통해 데이터 공유를 사용하도록 설정하는 방법에 대한 장치 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b17ab-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="b17ab-127">이 설정을 "USB 테더링", "데이터 공유" 또는 "USB 모뎀"이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="b17ab-128">USB를 통해 데이터 공유를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="b17ab-129">장치를 HoloLens USB-C 포트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="b17ab-130">HoloLens 2 네트워크 설정에서 장치는 자동으로 이더넷 연결로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b17ab-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
