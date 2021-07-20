---
title: 셀룰러 및 5G에 연결
description: HoloLens 혼합 현실 장치에서 셀룰러 네트워크에 연결합니다.
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
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635843"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="bddef-103">셀룰러 및 5G에 연결</span><span class="sxs-lookup"><span data-stu-id="bddef-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="bddef-104">HoloLens 2는 셀룰러 및 5G 네트워크에 연결하도록 다음 두 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="bddef-105">일반적으로 "핫스팟"이라고 하는 셀룰러 장치에서 제공하는 임시 WiFi 네트워크</span><span class="sxs-lookup"><span data-stu-id="bddef-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="bddef-106">USB-C 테더링 장치에 대한 제한된 지원</span><span class="sxs-lookup"><span data-stu-id="bddef-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="bddef-107">핫스팟(WiFi)</span><span class="sxs-lookup"><span data-stu-id="bddef-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="bddef-108">셀룰러 연결이 필요한 대부분의 경우 핫스팟을 통해 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="bddef-109">HoloLens 2 WiFi는 가장 일반적인 사용 사례에 필요한 대역폭과 대기 시간 요구 사항을 제공할 수 있는 802.11ac를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="bddef-110">WiFi는 케이블 없이 가장 많은 수의 셀룰러 장치와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="bddef-111">핫스팟에 연결</span><span class="sxs-lookup"><span data-stu-id="bddef-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="bddef-112">장치 설명서에서 핫스팟 모드를 사용하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bddef-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="bddef-113">핫스팟 모드를 사용하도록 설정하여 네트워크 이름과 알려진 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="bddef-114">HoloLens 2 네트워크 설정에서 2단계에서 만든 WiFi 네트워크를 찾아 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="bddef-115">USB-C 테더링</span><span class="sxs-lookup"><span data-stu-id="bddef-115">USB-C Tethering</span></span>

<span data-ttu-id="bddef-116">USB-C 테더링은 낮은 대기 시간이 필요한 고급 워크로드의 대기 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="bddef-117">예를 들어 [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)은 테더링의 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="bddef-118">테더링하려면 셀룰러 장치와 HoloLens 사이에 케이블이 필요하며 제한된 수의 장치에서 테더링이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="bddef-119">USB-C 호환성</span><span class="sxs-lookup"><span data-stu-id="bddef-119">USB-C compatibility</span></span>

<span data-ttu-id="bddef-120">이더넷 어댑터로 표시되는 장치는 Windows Holographic 버전 2004 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="bddef-121">이더넷 어댑터로 표시되지 않는 장치는 일반 Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 드라이버를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="bddef-122">그러나 이러한 장치는 제한된 수만 HoloLens 2와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="bddef-123">장치의 제조업체에 일반 Microsoft RNDIS 드라이버를 지원하는지를 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="bddef-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="bddef-124">RNDIS와 호환되지 않는 장치나, 드라이버 또는 응용 프로그램을 설치해야 하는 장치는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="bddef-125">Microsoft는 호환되는 장치 목록을 유지 관리하지 않지만, [여기](https://aka.ms/HLCommunityCell)에 해당 주제에 관한 커뮤니티 토론이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="bddef-126">테더링된 장치에 연결</span><span class="sxs-lookup"><span data-stu-id="bddef-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="bddef-127">장치 설명서에서 USB를 통해 데이터 공유를 사용하도록 설정하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bddef-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="bddef-128">이 설정은 "USB 테더링", "데이터 공유" 또는 "USB 모뎀"이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="bddef-129">USB를 통해 데이터 공유를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="bddef-130">장치를 HoloLens USB-C 포트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="bddef-131">HoloLens 2 네트워크 설정에서 이 장치가 자동으로 이더넷 연결로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bddef-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
