---
title: 하드웨어 기반 무결성 및 런타임 증명
description: 하드웨어 기반 무결성 및 런타임 증명
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, HoloLens, 하드웨어 기반 무결성, 런타임 증명, UEFI, UEFI 보안 부팅, 보안 부팅, TPM, 위협 방지, Windows 지속성 방지 보장, 코드 무결성, 코드 보호
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b3986d7310650c2fac20204488ae5f882754deab
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009476"
---
# <span data-ttu-id="75118-104">하드웨어 기반 무결성 및 런타임 증명</span><span class="sxs-lookup"><span data-stu-id="75118-104">Hardware-backed integrity and runtime attestation</span></span>

<span data-ttu-id="75118-105">하드웨어 기반 무결성 및 런타임 증명은 운영 체제를 시작하기 전에 발생한 위협에 대해 보호하고 런타임 동안 장치가 하드웨어를 사용하는 경우 무결성을 보장하는 원격 증명 서비스는 시작 및 런타임 기간에 걸쳐 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="75118-105">Hardware-backed integrity and runtime attestation protects against threats that originate prior to the start of an operating system, during runtime, when the device uses hardware, and remote attestation services to ensure integrity is maintained at startup and throughout runtime duration.</span></span>

## <span data-ttu-id="75118-106">UEFI 보안 부팅</span><span class="sxs-lookup"><span data-stu-id="75118-106">UEFI secure boot</span></span>

<span data-ttu-id="75118-107">HoloLens2는 UEFI(통합 EFI) 보안 부팅을 항상 적용하고 UEFI는 비즈니스용 Windows Holographic을 부팅만 합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-107">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot at all times, and UEFI only boots Windows Holographic for Business.</span></span>
<span data-ttu-id="75118-108">보안 부팅은 전체 부팅 체인의 무결성을 확인하고 Windows가 항상 이에 적용된 올바른 보안 정책을 사용하여 부팅하도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-108">Secure Boot ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="75118-109">보안 부팅에 대한 자세한 내용은 여기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75118-109">To learn more about Secure Boot go here.</span></span>

## <span data-ttu-id="75118-110">TPM</span><span class="sxs-lookup"><span data-stu-id="75118-110">TPM</span></span>

<span data-ttu-id="75118-111">TPM(신뢰할 수 있는 플랫폼 모듈)은 끝점 장치의 특수 칩입니다.</span><span class="sxs-lookup"><span data-stu-id="75118-111">The Trusted Platform Module (TPM) is a specialized chip on an endpoint device.</span></span> <span data-ttu-id="75118-112">HoloLens2에서는 하드웨어 적용 키 격리를 제공하는 TPM 2.0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-112">HoloLens 2 uses a TPM 2.0 which provides hardware-enforced key isolation.</span></span>

## <span data-ttu-id="75118-113">지속성 액세스 위협 방지</span><span class="sxs-lookup"><span data-stu-id="75118-113">Persistence Access Threat Protection</span></span>

<span data-ttu-id="75118-114">대부분 사이버 공격의 목표는 장치에 대한 지속적인 액세스를 유지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75118-114">The goal of most cyberattacks is to maintain persistent access to a device.</span></span> <span data-ttu-id="75118-115">사이버 범죄의 경우 이 지속성을 유지하면 손상된 Windows 장치가 봇네트에 참가하거나 장치 또는 기타 악성 사용자에게 액세스 권한을 판매하거나 반복적인 데이터 도용 등의 행위가 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="75118-115">For cybercrime, maintaining this persistence enables a compromised Windows device to join a botnet, sell access to the device or other nefarious users, or to enable repeated data theft.</span></span> <span data-ttu-id="75118-116">표적 공격의 분야에서 지속성은 장치에서든 전체 네트워크에서든(보다 일반적으로) 성공적인 사이버 공격을 위한 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="75118-116">In the world of targeted attacks, persistence is essential to a successful cyberattack – whether on a device or (more commonly), an entire network.</span></span>  

<span data-ttu-id="75118-117">사실 대상 장치 또는 네트워크에 대한 액세스를 관리해야 하는 전략으로 인해 표적 공격은 "고급 지속적인 위협"으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="75118-117">In fact, targeted attacks are considered “advanced persistent threats”, due to their strategic need to maintain access to a target device or network.</span></span> <span data-ttu-id="75118-118">이러한 이유로 비즈니스용 Windows Holographic은 지속성에 대한 방어를 절대적으로 중요한 것으로 고려하며 지속성 방지 기술을 사용하여 완벽한 고객 보안 약속을 이룹니다.</span><span class="sxs-lookup"><span data-stu-id="75118-118">For this reason, Windows Holographic for Business considers defending against persistence absolutely crucial and uses anti-persistence technology to make an ironclad customer security promise.</span></span>

### <span data-ttu-id="75118-119">보안 부팅</span><span class="sxs-lookup"><span data-stu-id="75118-119">Secure boot</span></span> 

<span data-ttu-id="75118-120">HoloLens2는 모든 핵심 운영 체제 상태에서 UEFI(통합 EFI) 보안 부팅을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-120">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot on all core operating system state.</span></span> <span data-ttu-id="75118-121">UEFI는 전체 부팅 체인의 무결성을 확인하고 Windows가 항상 이에 적용된 올바른 보안 정책을 사용하여 부팅하도록 보장하는 Microsoft 신뢰할 수 있는 플랫폼만 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-121">UEFI only boots Microsoft trusted platforms which ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="75118-122">HoloLens2는 보안 부팅을 해제하지 않으며 타사 부팅 로더를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75118-122">HoloLens 2 does not Secure Boot to be turned off, nor does it allow 3rd party boot loaders.</span></span>

> [!Tip]
> <span data-ttu-id="75118-123">[보안 부팅](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)에 대한 자세한 내용</span><span class="sxs-lookup"><span data-stu-id="75118-123">Learn more about [Secure boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

### <span data-ttu-id="75118-124">Windows 지속성 방지 보장</span><span class="sxs-lookup"><span data-stu-id="75118-124">Windows Anti-Persistence Assurance</span></span>

<span data-ttu-id="75118-125">HoloLens2의 지속성 방지는 시스템의 런타임 손상이 발생한 경우(예: 원격 해킹)와 같이 드문 상황에서도 사용자를 보장하고 이와 같은 이벤트는 간단히 장치의 전원을 끄면 시스템에서 모든 악성 코드가 제거되어 완화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75118-125">HoloLens 2 anti-persistence guarantees its users that even in the rare situation that a runtime compromise of the system were to ever occur – such as a remote exploit – such an event would be mitigated with all malicious code removed from the system simply by powering off the device.</span></span> <span data-ttu-id="75118-126">지속성 방지를 보다 강화하기 위해 HoloLens2는 강력한 무결성 보호를 추가하고 현재 위치에서 읽기 전용 보호를 설정하였습니다.</span><span class="sxs-lookup"><span data-stu-id="75118-126">To further strengthen its anti-persistence, HoloLens 2 has added powerful integrity protection, and put read-only protections in place.</span></span>

<span data-ttu-id="75118-127">사용자가 변경 가능한 모든 파티션을 초기화하는 장치의 PBR(원스톱 복원)을 수행하는 경우가 아니면 데이터 형태의 운영 체제 데이터 지속성은 계속 가능한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="75118-127">Persistence to operating system data in form of data is still possible, unless the user performs Push-button reset (PBR) of the device that wipes all mutable partitions.</span></span> <span data-ttu-id="75118-128">변경이 불가능한 파티션의 지속성은 훨씬 더 힘들어지는 반면 사용자는 Hololens2에 대해 PBR을 수행하여 변경 가능한 부분에서 모든 위협 요소를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-128">While persistence to immutable partitions is made much harder, the user needs to PBR the Hololens 2 to remove any possible threat-persistence from mutable parts.</span></span>

## <span data-ttu-id="75118-129">코드 무결성 보호</span><span class="sxs-lookup"><span data-stu-id="75118-129">Code integrity protection</span></span> 

<span data-ttu-id="75118-130">CI(코드 무결성)는 최신 운영 체제의 주요 보안 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="75118-130">Code integrity (CI) is a key security property of a modern operating system.</span></span> <span data-ttu-id="75118-131">CI를 적용하면 코드의 출처가 사용자 및 운영 체제 모두에 투명하게 보장되므로 철저한 보안 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75118-131">Enforcing CI enables sound security decisions, because it guarantees the provenance of code is transparent to both the user and operating system.</span></span> <span data-ttu-id="75118-132">전체 코드 무결성은 이진 이미지 서명을 지나 확장해야 하며 제어 흐름 무결성 및 동적 코드 제한과 같은 런타임 적용을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-132">Complete code integrity needs to extend past binary image signing and include runtime enforcement, such as control flow integrity and dynamic code restrictions.</span></span> <span data-ttu-id="75118-133">CI는 랜섬웨어, 원격 코드 실행 익스플로잇, 다양한 기타 공격 유형 등 사회적으로 엔지니어링된 맬웨어를 포함하여 여러 유형의 공격을 방지하는 데 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="75118-133">CI is critical to preventing multiple classes of attacks including socially engineered malware, such as ransomware, remote code execution exploits, and various other attack classes.</span></span>
