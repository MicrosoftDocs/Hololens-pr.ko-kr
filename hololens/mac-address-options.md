---
title: MAC 주소가 제한된 Wi-Fi 환경에서 HoloLens 디바이스의 엔터프라이즈 등록
description: HoloLens 2 디바이스의 네트워크에 대한 MAC 주소를 설정하는 방법
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189531"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>MAC 주소가 제한된 Wi-Fi 환경에서 HoloLens 디바이스의 엔터프라이즈 등록

이 문서에서는 Wi-Fi가 MAC 주소에 의해 제한되거나 Wireless 네트워크에 연결하기 위해 인증서가 필요한 고객 환경에서 확인된 일반적인 시나리오에 대해 설명합니다.

## <a name="example-scenario"></a>예제 시나리오

보안 환경의 많은 고객이 무선 또는 유선 네트워크에 제한이 있습니다. 이 제한은 승인된 디바이스(MAC 주소 기반)만 연결할 수 있도록 합니다. 이 제한은 무선 액세스 지점에서 MAC 주소 필터링을 통해 또는 DHCP 서버를 통해 적용될 수 있습니다. 또한 일부 무선 네트워크는 PEAP로 보호될 수 있습니다. 이 경우 무선 네트워크를 인증하기 전에 디바이스에 인증서를 적용해야 합니다.

이 시나리오에서는 두 가지 주요 요구 사항으로 인해 HoloLens 디바이스를 네트워크에 연결할 때 지연이 발생하거나 수동 개입이 필요할 수 있습니다.

- 디바이스가 무선 네트워크에 연결되기 전에 무선 PEAP 인증서를 디바이스에 적용해야 합니다.
- HoloLens Wi-Fi 어댑터의 MAC 주소는 등록되어 있어야 합니다.

위 요구 사항에 대한 핵심 과제는 다음과 같습니다.

1. MAC 주소는 현재 디바이스의 설정 앱에서만 식별되거나 제대로 등록한 후 Intune에서 식별할 수 있습니다.

2. MAC 주소가 없으면 디바이스가 Wi-Fi 네트워크에 연결하여 등록을 시작할 수 없습니다.

3. 이러한 문제를 수동으로 해결하려면 기술자가 디바이스와 상호 작용해야 합니다.

## <a name="solutions"></a>솔루션

환경 내에서 사용할 수 있는 인프라에 따라 이 상황을 개선하는 방법에는 여러 가지가 있습니다.

| 해결 방법 | 이점 | 요구 사항 |
| --- | --- | --- |
| 이더넷 어댑터를 통한 프로비전 패키지 | OOBE 환경을 개선하고 보다 신속한 기술자 환경을 허용합니다. | HoloLens 호환 USB-C Hub + 이더넷 어댑터, 기술자는 여전히 MAC 캡처 및 OOBE 마무리를 위한 디바이스와 상호 작용해야 합니다. |
| 이더넷을 통해 Intune이 등록된 Autopilot | 단일 단계 연결 및 디바이스와 고객 환경에 대한 등록입니다. 디바이스와 상호 작용할 필요 없이 MAC 캡처를 완료할 수 있습니다. | 고객 AAD 테넌트 및 HoloLens 호환 USB-C 이더넷 어댑터로 Intune 사용 |
| MAC 주소의 자동화된 보고 | Intune 테넌트에 디바이스를 등록한 경우, MAC 주소 보고를 기술자에게 스크립팅합니다. | Intune PowerShell cmdlet |

## <a name="provisioning-package-with-ethernet-adaptor"></a>이더넷 어댑터를 통한 프로비전 패키지

> [!NOTE] 
> 유선 네트워크에서도 MAC 제한이 적용되는 경우, USB-C 허브 + 이더넷 어댑터의 MAC 주소도 사전 승인되어야 합니다. 이 어댑터를 사용하여 다른 디바이스에서 네트워크로 액세스할 수 있으므로 주의를 기울여야 합니다.

### <a name="requirements"></a>요구 사항

- 고객 네트워크에 액세스할 수 있는 유선 네트워크 포트
- 이더넷 어댑터가 포함된 HoloLens 호환 USB-C 허브 - 추가 드라이버나 애플리케이션을 설치하지 않아도 되는 어댑터면 적합할 것입니다.
- 다음을 포함하는 프로비전 패키지:
  - 무선 네트워크 정보 및 인증서 포함
  - 선택적으로 조직의 Azure AD에 대한 등록 정보 포함
  - 그 외 필요한 프로비전 설정 포함

### <a name="process"></a>프로세스

프로세스는 디바이스의 소프트웨어 수준에 따라 다를 수 있습니다. 디바이스에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004)가 있는 경우 아래 단계를 수행합니다.

1. 프로비전 패키지를 USB 스틱의 루트에 넣고 허브에 꽂습니다.
2. 허브 + 이더넷 어댑터에 이더넷 케이블을 연결합니다.
3. HoloLens 디바이스에 USB-C 허브를 연결합니다.
4. HoloLens를 켜고 디바이스에 배치합니다.
5. **볼륨 다운 및 전원** 단추를 눌러 프로비전 패키지를 적용합니다.
6. 이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 디바이스의 MAC 주소를 검색할 수 있습니다.

디바이스에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004) 이전 OS 빌드가 있는 경우, 아래 단계를 따릅니다.

1. HoloLens를 켜고 디바이스를 PC에 연결합니다.
2. 디바이스는 PC에 파일 스토리지 디바이스로 표시되어야 합니다.
3. 디바이스에 프로비전 패키지 복사
4. 이더넷 케이블을 허브에 연결합니다.
5. HoloLens 디바이스에 USB-C 허브를 연결합니다.
6. HoloLens에 배치
7. **볼륨 다운 및 전원** 단추를 눌러 프로비전 패키지를 적용합니다.
8. 이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 디바이스의 MAC 주소를 검색할 수 있습니다.

### <a name="benefits"></a>이점

이렇게 하면 디바이스의 "단일 터치"가 허용되어 올바른 프로비전 패키지를 적용하고 디바이스의 MAC 주소를 수집할 수 있습니다. [여기에 나와 있는 지침에 따라 프로비전 패키지를 만들 수 있습니다.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Intune 등록을 통한 Autopilot

### <a name="requirements"></a>요구 사항

- 고객 네트워크에 액세스할 수 있는 유선 네트워크 포트
- Windows Holographic 2004를 실행하는 HoloLens 디바이스
- HoloLens 호환 USB-C 이더넷 어댑터
- 고객 테넌트에서 Intune 설정 및 사용
- Autopilot에 등록되고 고객 테넌트로 가져온 디바이스
- 디바이스에 대해 정의된 Intune 정책:
   - 무선 네트워크 정보 및 인증서 포함
   - 그 외 필요한 프로비전 설정 포함

이렇게 하면 고급 네트워킹 요구 사항을 갖춘 고객이 확장 가능한 핸즈오프 방식으로 디바이스를 등록할 수 있습니다.

아래와 같은 추가 필수 조건이 필요합니다.
1. [Autopilot 미리 보기를 위해 테넌트를 사용합니다](hololens2-autopilot.md).
1. HoloLens 정책을 만들어 Intune 내에서 프로비전 패키지를 대체합니다.
1. HoloLens Intune 정책을 만듭니다.
1. 올바른 그룹에 디바이스를 할당합니다.

### <a name="process"></a>프로세스

1. 이더넷 케이블을 어댑터에 연결하고 HoloLens 2 디바이스의 USB-C 포트에 어댑터를 연결합니다.

2. HoloLens를 켭니다.

3. 이더넷 어댑터를 통해 OOBE 동안 디바이스가 자동으로 인터넷에 연결됩니다. Autopilot 구성을 감지하고 Azure AD 및 Intune에 자동으로 등록해야 합니다.

4. 디바이스는 Intune을 통해 필요에 따라 필요한 Wi-Fi 인증서 및 기타 구성을 적용합니다.

5. 완료되면 기술자는 Intune(엔드포인트 관리자) 포털을 로드하고 **홈 -> 디바이스 -> DeviceName -> 하드웨어** 에서 디바이스 속성 페이지에 연결할 수 있습니다.

6. Wi-Fi MAC 주소는 Intune 포털 내에 표시됩니다.

   ![Intune을 통한 MAC 주소.](images/mac-address-intune.jpg)

7. 기술자는 이 MAC 주소를 허용되는 디바이스로 추가합니다.

### <a name="benefits"></a>이점

이렇게 하면 기술자가 디바이스를 사용하거나 HoloLens 환경과 수동으로 상호 작용할 필요 없이 상자에 있는 디바이스를 Azure AD 및 Intune에 등록할 수 있는 "헤드오프" 배포 환경을 사용할 수 있습니다.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>기술자에게 MAC 주소 보고

### <a name="requirements"></a>요구 사항

- 고객 테넌트에 대한 "Intune Graph PowerShell" 권한 부여
- 기술자 머신에 Intune Graph PowerShell 설치.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune의 "관리 디바이스" 요소에 대한 읽기 액세스. (지원 센터 운영자 이상 또는 사용자 지정 역할)

현재로서는 Intune 내에서 새 디바이스의 등록을 기반으로 자동화 명령을 트리거하는 "간단한" 방법은 없습니다. 따라서 이 명령은 기술자가 포털에 로그인하여 수동으로 검색할 필요 없이 MAC 주소를 검색하는 간단한 방법을 제공합니다.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

그러면 지난 30일 동안 등록된 모든 HoloLens 디바이스의 이름과 MAC 주소가 반환됩니다.

![PowerShell을 통한 MAC 주소.](images/mac-address-powershell.jpg)

### <a name="process"></a>프로세스

Intune 등록을 완료한 후, 기술자는 위의 스크립트를 실행하여 MAC 주소를 검색합니다.
