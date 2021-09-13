---
title: 하드웨어 지원 무결성 및 런타임 증명
description: 하드웨어 지원 무결성 및 런타임 증명
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: 보안, hololens, 하드웨어 지원 무결성, 런타임 증명, UEFI, UEFI 보안 부팅, 보안 부팅, TPM, 위협 방지, Windows 지속성 방지 보장, 코드 무결성, 코드 보호
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034678"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>하드웨어 지원 무결성 및 런타임 증명

하드웨어 지원 무결성 및 런타임 증명은 운영 체제 시작 전, 런타임 중, 디바이스가 하드웨어를 사용할 때 발생하는 위협으로부터 보호하고, 시작 시 그리고 런타임 기간 동안 무결성이 유지되도록 보장하는 원격 증명 서비스를 제공합니다.

## <a name="uefi-secure-boot"></a>UEFI 보안 부팅

HoloLens 2는 UEFI(Unified Extensible Firmware Interface) 보안 부팅을 항상 적용하고 UEFI는 Windows Holographic for Business만 부팅합니다.
보안 부팅은 전체 부팅 체인의 무결성이 확인되고 Windows가 항상 올바른 보안 정책이 적용된 상태로 부팅되도록 합니다. [보안 부팅](/windows-hardware/design/device-experiences/oem-secure-boot)에 대해 자세히 알아보세요.

## <a name="tpm"></a>TPM

TPM(신뢰할 수 있는 플랫폼 모듈)은 엔드포인트 디바이스의 특수 칩입니다. HoloLens 2는 하드웨어 기반 키 격리를 제공하는 TPM 2.0을 사용합니다. [TPM 기본 사항](/windows/security/information-protection/tpm/tpm-fundamentals)에 대해 자세히 알아보세요.

## <a name="persistence-access-threat-protection"></a>지속성 액세스 위협 방지

대부분 사이버 공격의 목표는 디바이스에 대한 지속적인 액세스를 유지하는 것입니다. 사이버 범죄의 경우 이러한 지속성을 유지하면 손상된 Windows 디바이스가 봇넷에 조인하거나 디바이스 또는 기타 악의적인 사용자에 대한 액세스를 판매하거나, 반복적인 데이터 도용이 가능해집니다. 표적 공격의 분야에서 지속성은 디바이스에서든 (보다 일반적으로) 전체 네트워크에서든 성공적인 사이버 공격을 위한 필수 요소입니다.  

사실 대상 디바이스 또는 네트워크에 대한 액세스를 관리해야 하는 전략으로 인해 표적 공격은 "지속적인 지능형 위협"으로 간주됩니다. 이러한 이유로 Windows Holographic for Business는 지속성에 대한 방어를 절대적으로 중요한 것으로 고려하며 지속성 방지 기술을 사용하여 철저한 고객 보안을 약속합니다.

### <a name="secure-boot"></a>보안 부팅

HoloLens 2는 모든 핵심 운영 체제 상태에서 UEFI(Unified Extensible Firmware Interface) 보안 부팅을 적용합니다. UEFI는 Microsoft 신뢰할 수 있는 플랫폼만 부팅하므로 전체 부팅 체인의 무결성이 확인되고 Windows가 항상 올바른 보안 정책이 적용된 상태로 부팅됩니다. HoloLens 2는 보안 부팅을 끄거나 타사 부트 로더를 허용하지 않습니다.

> [!Tip]
> [보안 부팅](/windows-hardware/design/device-experiences/oem-secure-boot)에 대해 자세히 알아보세요.

### <a name="windows-anti-persistence-assurance"></a>Windows 지속성 방지 보장

HoloLens 2의 지속성 방지는 시스템의 런타임 손상이 발생한 경우(예: 원격 해킹)와 같이 드문 상황에서도 디바이스의 전원을 끄기만 하면 시스템에서 모든 악성 코드가 제거되어 이러한 이벤트가 완화될 수 있음을 사용자에게 보장합니다. 지속성 방지 기능을 더욱 강화하기 위해 HoloLens 2는 강력한 무결성 보호 기능을 추가하고 읽기 전용 보호 기능을 적용했습니다.

사용자가 변경 가능한 모든 파티션을 지우는 디바이스의 PBR(원스톱 복원)을 수행하지 않는 한 데이터 형태의 운영 체제 데이터에 대한 지속성은 여전히 가능합니다. 변경할 수 없는 파티션에 대한 지속성이 훨씬 더 어려워지지만 사용자는 HoloLens 2를 PBR하여 변경 가능한 부분에서 가능한 위협 지속성을 제거해야 합니다.

## <a name="code-integrity-protection"></a>코드 무결성 보호

CI(코드 무결성)는 최신 운영 체제의 주요 보안 속성입니다. CI를 적용하면 코드 출처가 사용자와 운영 체제 모두에 투명하게 적용되도록 보장하기 때문에 올바른 보안 결정을 내릴 수 있습니다. 완전한 코드 무결성은 과거 이진 이미지 서명을 확장하고 제어 흐름 무결성 및 동적 코드 제한과 같은 런타임 시행을 포함해야 합니다. CI는 랜섬웨어, 원격 코드 실행 익스플로잇 및 기타 다양한 공격 클래스와 같은 사회 공학적 맬웨어를 비롯한 여러 클래스의 공격을 방지하는 데 중요합니다.
