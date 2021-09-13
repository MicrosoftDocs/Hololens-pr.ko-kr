---
title: 암호화 및 데이터 보호
description: BitLocker 및 Azure 통합을 포함하여 HoloLens 2 디바이스의 암호화 및 데이터 보호에 대해 알아봅니다.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 보안, hololens, 암호화, 데이터 보호, BitLocker 디바이스, BitLocker, bitlocker, bitlocker 암호화, azure 통합,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034717"
---
# <a name="encryption-and-data-protection"></a>암호화 및 데이터 보호

암호화 및 데이터 보호를 통해 디바이스가 분실되거나 도난당하는 경우 데이터를 보호하고 권한이 없는 애플리케이션에서 중요한 정보를 액세스하지 못하도록 합니다.

## <a name="bitlocker-device-encryption"></a>BitLocker 디바이스 암호화

BitLocker는 읽기 전용(RO) 미디어 및 쓰기 가능한 미디어의 개인 정보 보호에 대한 무결성 보호를 위한 전체 볼륨 암호화 기능입니다.  이 기능의 개시 후에 이 기능은 오프라인 공격 중에 데이터에 대한 무단 액세스에 대하여 효과적인 보호장치가 되었습니다. HoloLens 2를 사용하면 기본적으로 BDE(Bitlocker 디바이스 암호화)를 디바이스에 대한 무단 물리적 액세스로부터 데이터를 보호하도록 사용할 수 있습니다. 항상 미래의 요구 사항을 충족하기 위해 진화하고 있는 Microsoft는 계속해서 이 기술에 투자하고 개선하고 있습니다.

BDE는 디바이스의 상태 분리된 레이아웃의 모든 볼륨에서 AES-XTS-256 암호화를 사용하는 데이터 보호 기능입니다. BDE는 상태 분리된 레이아웃에 디바이스 수준 암호화를 제공합니다. BitLocker 디바이스 암호화는 운영 체제 및 고정 데이터 볼륨에서 자동으로 사용하도록 설정되며 IT 관리자라도 디바이스를 끌 수 없어서 디바이스가 항상 보호됩니다.

그런 다음, BDE 암호화 키를 사용하여 디바이스를 부팅하는데 필요한 바이너리와 데이터를 투명하게 해독합니다. 운영 체제 볼륨이 해제되고 시스템이 부팅 중이면 자동 잠금 해제 보호기의 볼륨 특정 버전을 사용하여 다른 볼륨에 액세스할 수 있게 됩니다. 사용자 개인 정보 보호를 유지하는데 사용할 수 있는 다른 보호기가 없으며, 이 드라이브는 동일한 디바이스에서만 해제할 수 있습니다. 첫 번째 부팅부터 필수 볼륨에 대한 RO(읽기 전용) 실행이 적용되고 즉시 실시됩니다. HoloLens 2 수명 주기에는 Bitlocker 복구 키가 필요하지 않습니다.

## <a name="azure-integration"></a>Azure 통합 

HoloLens 2를 사용하면 고객이 자신의 디바이스를 Azure 서비스와 통합할 수 있습니다. HoloLens 2 디바이스와 Azure 사이의 통신에는 TLS(전송 계층 보안) 프로토콜을 사용하여 자신과 강력한 인증, 메시지 개인정보보호, 무결성을 제공하는 클라우드 서비스 간에 이동하는 데이터를 보호합니다. 모든 Azure 서비스에서는 TLS 1.2를 완벽하게 지원하며 고객이 TLS 1.2만을 사용하는 모든 서비스는 TLS 1.2 트래픽만을 허용합니다. 전송 중인 데이터에 대한 Azure의 암호화 표준은 [Azure 암호화 개요](/azure/security/fundamentals/encryption-overview)에 자세히 설명되어 있습니다. [Azure 데이터 보안 및 암호화 모범 사례](/azure/security/fundamentals/data-encryption-best-practices)에 대해 자세히 알아보려면 Azure 설명서를 참조하세요. 

HoloLens 2와의 클라우드 통합의 예인 OneDrive에는 인터넷에 연결되었을 때 파일 및 문서를 클라우드에 자동으로 업로드할 수 있는 자동 업로드 기능이 있습니다. 파일의 자동 동기화 일시 중지는 정책을 통해 해제할 수 없지만, UX를 통해 직접 구성할 수 있습니다. 
