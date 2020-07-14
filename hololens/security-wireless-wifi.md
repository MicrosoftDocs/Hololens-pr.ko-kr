---
title: 무선 및 Wi-Fi
description: 무선 및 Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, HoloLens, 무선, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865773"
---
# <span data-ttu-id="47033-104">무선 및 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="47033-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="47033-105">HoloLens 2 무선 LAN 연결은 다음과 같은 놀라운 범위의 최신 Wi-Fi 보안 표준을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47033-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="47033-106">WPA2(Wi-Fi 보호 액세스 2)</span><span class="sxs-lookup"><span data-stu-id="47033-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="47033-107">TEAP(확장할 수 있는 터널 인증 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="47033-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="47033-108">OWE(편의적 무선 암호화)</span><span class="sxs-lookup"><span data-stu-id="47033-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="47033-109">차세대 엔터프라이즈 네트워크 인증 TEAP를 통해 단일 트랜잭션으로 여러 자격 증명을 안전하게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47033-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="47033-110">따라서 관리자는 동일한 인증 트랜잭션을 수행하는 동안 컴퓨터와 사용자 모두에 대해 유효한 ID를 요구하는 보안 태세를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47033-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="47033-111">HoloLens 2는 최신 무선 및 Wi-Fi 프로토콜을 통해 고객을 최대한으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47033-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="47033-112">HoloLens 2 라디오는 프리미엄 라디오 환경을 제공하는 Qualcomm WCN3990 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="47033-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="47033-113">Wi-Fi는 802.11ac/n으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="47033-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="47033-114">주파수 범위는 사용자가 구성할 수 없으며 사용 국가에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="47033-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="47033-115">미국에서 Wi-Fi는 2.4GHz(1~11) 채널과 5GHz(36~64, 100~165) 채널을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47033-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="47033-116">사용자와 장치 모두 특정 주파수에 대한 허용/거부 목록을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47033-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="47033-117">Bluetooth SIC Core 5.0에는 Wi-Fi와 공유되지 않는 Bluetooth 전용 2.4GHz 안테나가 탑재되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47033-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="47033-118">HoloLens 2 소프트웨어 스택은 HID, HOGP, A2DP, GATT 등의 여러 프로토콜과 프로필을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47033-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="47033-119">IT 관리자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47033-119">IT admins can:</span></span> 
  * <span data-ttu-id="47033-120">[Bluetooth 액세스](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 사용 또는 제한</span><span class="sxs-lookup"><span data-stu-id="47033-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="47033-121">[로컬 Bluetooth 장치 이름](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename) 설정
</span><span class="sxs-lookup"><span data-stu-id="47033-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="47033-122">[장치를 검색할 수 있도록](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode) 허용</span><span class="sxs-lookup"><span data-stu-id="47033-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="47033-123">[Wi-Fi 연결](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 허용/허용 안 함</span><span class="sxs-lookup"><span data-stu-id="47033-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="47033-124">[MDM 서버를 설치한 네트워크 외부에서의 Wi-Fi 연결](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)을 허용 또는 허용 안 함</span><span class="sxs-lookup"><span data-stu-id="47033-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
