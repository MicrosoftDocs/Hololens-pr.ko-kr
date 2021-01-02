---
title: MAC 주소에 HoloLens 장치의 엔터프라이즈 등록으로 제한된 Wi-Fi 환경
description: HoloLens 2 장치의 네트워크에 대한 MAC 주소를 설정하는 방법
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
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253145"
---
# MAC 주소에 HoloLens 장치의 엔터프라이즈 등록으로 제한된 Wi-Fi 환경

이 문서에서는 Wi-Fi가 MAC 주소에 의해 제한되고 혹은 무선 네트워크에 가입하려면 인증서가 필요한 고객의 환경에서 식별한 일반적인 시나리오를 설명합니다.

## 예제 시나리오:

보안 환경의 많은 고객에게는 무선 또는 유선 네트워크에 대한 제한 사항이 있어 승인된 장치만(MAC 주소 기반) 연결할 수 있습니다(무선 액세스 지점 또는 DHCP 서버에서 MAC 주소 필터링 포함). 또한 일부 무선 네트워크는 PEAP를 사용하여 보호될 수 있으며, 이 경우 무선 네트워크를 성공적으로 인증하기 전에 장치에 인증서를 적용해야 합니다.

HoloLens 장치에서 두 가지 주요 문제가 발생할 수 있으며 이는 HoloLens 장치를 네트워크에 연결하는 데 지연 시간과 수동 작업을 발생시킬 수 있습니다.

- 장치를 무선 네트워크에 연결시키기 전에 무선 PEAP 인증서를 장치에 적용해야 합니다.
- HoloLens Wi-fi 어댑터의 MAC 주소는 등록되어 있어야 합니다.

이에 대한 주요 문제는 다음과 같습니다.

1. MAC 주소는 현재 장치의 설정 앱에서만 식별되거나 Intune을 제대로 등록한 후 Intune에서 식별할 수 있습니다.
2. MAC 주소가 없으면 장치에서 Wi-Fi 네트워크에 연결하여 등록을 시작할 수 없습니다.
3. 이러한 문제의 수동적 해결 방법은 장치에 기술자의 도움을 받아야 합니다.

## 해결 방법

환경 내에서 사용할 수 있는 인프라에 따라 이 상황을 개선하는 방법에는 여러 가지가 있습니다.

| 솔루션 | 장점 | 요구 사항 |
| --- | --- | --- |
| 이더넷 어댑터를 통한 프로비저닝 패키지 | OOBE 환경을 개선하고 보다 신속한 기술자 환경을 허용합니다. | HoloLens와 호환되는 USB C HubTechnician은 MAC용 장치와 캡처 및 OOBE finalisation을 위해 계속 상호 작용해야 합니다. |
| 이더넷을 통해 Intune이 등록된 Autopilot | 고객 환경에 대한 단일 단계 연결 및 장치 등록을 통해 Mac 캡처는 장치와 상호 작용하지 않고도 완료할 수 있습니다. | 고객 Azure AD TenantHoloLens 호환 USB-C 네트워크 어댑터로 Intune 사용 |
| MAC 주소의 자동화된 보고 | Intune 테넌트에 장치를 등록한 경우, MAC 주소 보고를 기술자에게 스크립팅합니다. | Intune PowerShell Commandlets |

## 이더넷 어댑터를 통한 프로비저닝 패키지

> [!NOTE] 
> 유선 네트워크에서도 MAC 제한이 적용되는 경우, USB-C 이더넷 어댑터/허브의 MAC 주소는 사전 승인되어야 합니다. 이 허브를 사용하여 다른 장치에서 네트워크로 액세스할 수 있으므로 주의를 기울여야 합니다.

### 요구 사항

- 고객 네트워크에 대한 액세스 권한이 있는 유선 네트워크 포트
- 이더넷 어댑터를 포함하는 HoloLens 호환 USB-C 허브 - 추가 드라이버나 응용 프로그램을 설치하지 않아도 되는 허브면 적합할 것입니다.
- 프로비저닝 패키지 구성:
  - 무선 네트워크 정보 및 인증서를 포함
  - 선택적으로 조직의 Azure AD에 대한 등록 정보 포함
  - 그 외 필요한 프로비저닝 설정 포함

### 프로세스

이 프로세스는 장치의 소프트웨어 수준에 따라 다를 수 있습니다. 장치에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004)가 있는 경우, 아래 단계를 따릅니다.

1. 프로비전닝 패키지를 USB 스틱의 루트에 놓고 허브에 꽂습니다.
2. 이더넷 케이블을 허브에 연결합니다.
3. HoloLens 장치에 USB-C 허브를 연결합니다.
4. HoloLens 장치를 켜고 착용합니다.
5. **볼륨 작게 및 전원 단추**를 눌러 프로비저닝 패키지를 적용합니다.
6. 이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 장치의 MAC 주소를 검색할 수 있습니다.

장치에 [2004년 5월 업데이트](hololens-release-notes.md#windows-holographic-version-2004) 이전에 OS 빌드를 설치한 경우, 아래 단계를 따릅니다.

1. HoloLens 장치를 켜고 장치를 PC에 연결합니다.
2. 장치가 PC에서 파일 저장소 장치로 표시되어야 합니다.
3. 장치에 프로비저닝 패키지 복사
4. 이더넷 케이블을 허브에 연결합니다.
5. HoloLens 장치에 USB-C 허브를 연결합니다.
6. 장치를 착용합니다.
7. **볼륨 작게 및 전원 단추**를 눌러 프로비저닝 패키지를 적용합니다.
8. 이제 기술자는 OOBE를 따르고, 완료되면, 설정 앱을 열고 장치의 MAC 주소를 검색할 수 있습니다.

### 장점

이렇게 하면 장치의 &quot;단일 터치&quot;가 올바른 프로비저닝 패키지를 적용하고 장치의 MAC 주소를 수집할 수 있습니다. [여기에 나와 있는 지침에 따라 프로비저닝 패키지를 만들 수 있습니다.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Intune 등록을 통한 Autopilot

### 요구 사항

- 고객 네트워크에 대한 액세스 권한이 있는 유선 네트워크 포트
- Windows Holographic 2004를 실행하는 HoloLens 장치
- HoloLens 호환 USB-C 허브
- Intune을 설정하고 고객 테넌트에 대해 사용하도록 설정
- Autopilot에 등록되어 고객 테넌트로 가져온 장치
- 장치에 대해 정의된 Intune 정책:
   - 무선 네트워크 정보 및 인증서를 포함
   - 그 외 필요한 프로비저닝 설정 포함

이는 고급 네트워킹 요구 사항을 포함하는 고객은 장치를 자동으로 확장 가능한 방식으로 등록할 수 있도록 해줍니다.

아래와 같은 추가 필수 조건이 필요합니다.
1. [Autopilot 미리 보기에 테넌트를 사용하도록 설정](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. HoloLens 정책을 만들어 Intune 내에서 프로비저닝 패키지를 대체합니다.
1. HoloLens Intune 정책을 만듭니다.
1. 올바른 그룹에 장치를 할당합니다.

### 프로세스

1. USB-C 허브 및 이더넷 케이블을 HoloLens 2 장치에 꽂습니다.
2. HoloLens 2를 켭니다.
3. 장치가 이더넷 어댑터를 통해 OOBE에서 인터넷에 자동으로 연결하고, Autopilot 구성을 감지하고, Azure AD 및 Intune을 통해 자동으로 등록해야 합니다.
4. 장치에서 Intune을 통해 필요한 Wi-Fi 인증서와 필요에 따라 추가 구성을 적용합니다.
5. 완료되면 기술자는 Intune (끝점 관리자) 포털을 로드하고 **홈-> 장치 -> DeviceName -> 하드웨어**에서 장치 속성 페이지에 연결할 수 있습니다.
6. Wi-Fi MAC 주소는 Intune 포털 내에 표시됩니다.

![Intune을 통한 MAC 주소](images/mac-address-intune.jpg)

7. 기술자는 이 MAC 주소를 허용되는 장치로 추가합니다.

### 장점

이렇게 하면 기술자가 장치를 착용하거나 HoloLens 환경을 수동으로 조작하지 않고도 &quot;장치 미착용&quot; 상태로 장치는 상자에서 Azure AD 및 Intune에 등록됩니다.

## 기술자에게 MAC 주소 보고

### 요구 사항

- 고객 테넌트에 대한 &quot;Intune 그래프 PowerShell&quot;의 권한 부여
- 기술자 컴퓨터에 Intune 그래프 PowerShell 설치
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune의 &quot;관리되는 장치&quot; 요소에 대 한 읽기 액세스 권한입니다. (지원 센터 연산자나 상위 또는 사용자 지정 역할)

현재로서는 Intune 내에서 새 장치의 등록을 기반으로 자동화 명령을 트리거하는 &quot;간단한&quot; 방법이 없습니다. 따라서 이 명령은 기술자에게 포털에 로그인하여 수동으로 검색할 필요없이 MAC 주소를 검색하는 간단한 방법을 제공합니다.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

이는 최근 30일 이내에 등록된 모든 HoloLens 장치의 이름과 MAC 주소를 반환합니다.

![Powershell을 통한 MAC 주소](images/mac-address-powershell.jpg)

### 프로세스

Intune 등록을 완료한 후, 기술자는 위의 스크립트를 실행하여 MAC 주소를 검색합니다.
