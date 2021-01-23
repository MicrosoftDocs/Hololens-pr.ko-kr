---
title: 암호화 및 데이터 보호
description: BitLocker 및 Azure 통합을 포함하여 HoloLens 2 장치의 암호화 및 데이터 보호에 대해 알아봅니다.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, 암호화, 데이터 보호, BitLocker 장치, BitLocker, bitlocker, bitlocker 암호화, azure 통합,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e005f04088127a0e38a4dd978cd63e5d4e5c0ab9
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284109"
---
# <span data-ttu-id="39237-104">암호화 및 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="39237-104">Encryption and data protection</span></span>

<span data-ttu-id="39237-105">암호화 및 데이터 보호를 통해 장치가 분실되거나 도난당하는 경우 데이터를 보호하고 권한이 없는 응용 프로그램에서 중요한 정보를 액세스하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39237-105">Encryption and Data Protection protects data when the device is lost or stolen and prevents unauthorized applications from accessing sensitive information.</span></span>

## <span data-ttu-id="39237-106">BitLocker 장치 암호화</span><span class="sxs-lookup"><span data-stu-id="39237-106">BitLocker device encryption</span></span>

<span data-ttu-id="39237-107">BitLocker는 읽기 전용(RO) 미디어 및 쓰기 가능한 미디어의 개인정보 보호에 대한 무결성 보호를 위한 전체 볼륨 암호화 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="39237-107">BitLocker is a full-volume encryption feature for integrity protection of Read Only (RO) media and privacy protection of writable media.</span></span>  <span data-ttu-id="39237-108">이 기능의 개시 후에는 이 기능은 오프 라인 공격 중에 데이터에 대한 무단 액세스에 대한 효과적으로 보호장치가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-108">Since its inception, it has been an effective shield against unauthorized access to the data during offline attacks.</span></span> <span data-ttu-id="39237-109">HoloLens 2를 사용하면 기본적으로 BDE(Bitlocker 장치 암호화)를 장치에 대한 무단 물리적 액세스로부터 데이터를 보호하도록 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-109">HoloLens 2 enables Bitlocker Device Encryption (BDE) by default to protect data from any unauthorized physical access to the device.</span></span> <span data-ttu-id="39237-110">항상 미래의 요구 사항을 충족하기 위해 진화하고 있는 Microsoft는 계속해서 이 기술에 투자하고 개선하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-110">Always evolving to meet the needs of the future, Microsoft continues to invest and enhance this technology.</span></span>

<span data-ttu-id="39237-111">BDE는 장치의 상태 구분된 레이아웃의 모든 볼륨에서 AES-XTS-256 암호화를 사용하는 데이터 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="39237-111">BDE is a data protection feature that employs AES-XTS-256 encryption on all volumes in the state-separated layout of the device.</span></span> <span data-ttu-id="39237-112">BDE는 상태 구분된 레이아웃에 장치 수준 암호화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39237-112">BDE provides device level encryption in a state-separated layout.</span></span> <span data-ttu-id="39237-113">BitLocker 장치 암호화는 운영 체제 및 고정 데이터 볼륨에서 자동으로 사용하도록 설정되며 IT 관리자라도 장치를 끌 수 없어서 장치가 항상 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="39237-113">BitLocker Device Encryption is enabled automatically on operating system and fixed data volumes and cannot be turned off, even by IT administrators, so that the device is always protected.</span></span>

<span data-ttu-id="39237-114">그런 다음 BDE 암호화 키를 사용하여 장치를 부팅하는데 필요한 바이너리와 데이터를 투명하게 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="39237-114">BDE encryption keys are then used to transparently decrypt binaries and the data required to boot the device.</span></span> <span data-ttu-id="39237-115">운영 체제 볼륨이 해제되고 시스템이 부팅 중이면 자동 잠금 해제 보호기의 볼륨 특정 버전을 사용하여 다른 볼륨에 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39237-115">As the operating system volume is unlocked and a system is booting up, other volumes become accessible using a volume-specific version of the auto-unlock protector.</span></span> <span data-ttu-id="39237-116">사용자 개인정보보호를 유지하는데 사용할 수 있는 다른 보호기가 없으며, 이 드라이브는 동일한 장치에서만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-116">No other protectors are available to maintain user privacy and the drive can only be unlocked on the same device.</span></span> <span data-ttu-id="39237-117">첫 번째 부팅부터 필수 볼륨에 대한 읽기 전용(RO) 실시가 적용되고 즉시 실시됩니다.</span><span class="sxs-lookup"><span data-stu-id="39237-117">Read Only (RO) enforcement on required volumes is applied and enforced immediately, starting from the first boot.</span></span>

## <span data-ttu-id="39237-118">Azure 통합</span><span class="sxs-lookup"><span data-stu-id="39237-118">Azure integration</span></span> 

<span data-ttu-id="39237-119">HoloLens 2를 사용하면 고객이 자신의 장치를 Azure 서비스와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-119">HoloLens 2 enables customers to integrate their devices with Azure services.</span></span> <span data-ttu-id="39237-120">HoloLens 2 장치와 Azure 사이의 통신에는 TLS(전송 계층 보안) 프로토콜을 사용하여 자신과 강력한 인증, 메시지 개인정보보호, 무결성을 제공하는 클라우드 서비스 간에 이동하는 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="39237-120">Communications between HoloLens 2 devices and Azure use TLS (Transport Layer Security) protocol to protect data traveling between itself and cloud services which delivers strong authentication, message privacy, and integrity.</span></span> <span data-ttu-id="39237-121">모든 Azure 서비스에서는 TLS 1.2를 완벽하게 지원하며 고객이 TLS 1.2만을 사용하는 모든 서비스는 TLS 1.2 트래픽만을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="39237-121">All Azure services fully support TLS 1.2 and any services where customers are using only TLS 1.2 only accept TLS 1.2 traffic.</span></span> <span data-ttu-id="39237-122">전송되는 데이터에 대한 Azure의 암호화 표준은 [Azure 암호화 개요](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview)에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-122">Azure’s encryption standards for data in transit are detailed in [Azure encryption overview](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview).</span></span> <span data-ttu-id="39237-123">Azure 문서를 방문하여 [Azure 데이터 보안 및 암호화에 대한 모범 사례](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="39237-123">Visit the Azure documentation to learn more about [best practices for Azure data security and encryption](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices).</span></span> 

<span data-ttu-id="39237-124">HoloLens 2와의 클라우드 통합의 예인 OneDrive에는 인터넷에 연결되었을 때 파일 및 문서를 클라우드에 자동으로 업로드할 수 있는 자동 업로드 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-124">OneDrive, an example of cloud integration with HoloLens 2, has an auto upload feature where your files and documents can be automatically uploaded to the cloud when connected to the internet.</span></span> <span data-ttu-id="39237-125">파일의 자동 동기화 일시 중지는 정책을 통해 해제할 수 없지만, UX를 통해 직접 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39237-125">Pausing automatic syncing of files cannot be turned off via policy but is directly configurable via the UX.</span></span> 
