---
title: 프로비저닝 패키지를 사용하여 HoloLens 구성(HoloLens)
description: Windows 프로비전을 통해 IT 관리자가 이미징 없이 최종 사용자 장치를 쉽게 구성할 수 있습니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284159"
---
# 프로비저닝 패키지를 사용하여 HoloLens 구성

[Windows 프로비전을](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 통해 IT 관리자가 이미징 없이 최종 사용자 장치를 쉽게 구성할 수 있습니다. Windows 구성 디자이너는 이미지 및 런타임 설정을 구성하기 위한 도구로, 프로비저닝 패키지에 기본 제공됩니다.

프로비저닝 패키지에 적용할 수 있는 일부 HoloLens 구성은 다음과 같습니다.

- 비즈니스용 [Windows Holographic으로 업그레이드](hololens1-upgrade-enterprise.md)
- 로컬 계정 설정
- Wi-Fi 연결 설정
- 장치에 인증서 적용
- 개발자 모드 사용
- 자세한 지침에 따라 키오스크 [모드를 구성합니다.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

## 프로비저닝 패키지 HoloLens 마법사

HoloLens 마법사를 사용하면 프로비저닝 패키지에서 다음 설정을 구성할 수 있습니다.

- Enterprise Edition으로 업그레이드

    > [!NOTE]
    > 이는 HoloLens 1세대 디바이스에만 사용해야 합니다. 프로비저닝 패키지에 비즈니스용 Windows Holographic에 대한 버전 업그레이드 라이선스가 포함되어 있는 경우 또는 장치가 이미 비즈니스용 [Windows Holographic으로](hololens1-upgrade-enterprise.md)업그레이드된 경우 프로비저닝 패키지의 설정이 적용됩니다.

- HoloLens 첫 번째 환경(OOBE) 구성
- 네트워크 Wi-Fi 구성
- Azure Active Directory에 디바이스를 등록하거나 로컬 계정 만들기
- 인증서 추가
- 개발자 모드 사용
- 자세한 지침을 따라 키오스크 [모드를 구성합니다.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

> [!WARNING]
> 마법사 중 하나를 사용하여 Windows 10에서 Windows 구성 디자이너를 실행하여 Azure Active Directory 등록을 구성해야 합니다.

프로비저닝 패키지에는 관리 지침 및 정책, 사용자 지정 네트워크 연결 및 정책이 포함됩니다.

> [!TIP]
> 데스크톱 마법사를 사용하여 일반 설정이 포함된 패키지를 만든 후 기타 설정, 앱, 정책 등을 추가하려면 고급 편집기로 전환합니다.

## 프로비저닝 패키지를 만들기 위한 단계

1. **옵션 1:** [Microsoft Store에서](https://www.microsoft.com/store/apps/9nblggh4tx22) 여기에는 HoloLens 2 기능이 포함됩니다.
2. **옵션 2:** [Windows 10용 Windows ADK(Assessment and Deployment Kit)에서.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Windows ADK에서 Windows 구성 디자이너를 **** 설치하는 경우 설치하려는 기능 선택 대화 상자에서 구성 **디자이너를** 선택합니다. 이 옵션에는 HoloLens 2 기능이 포함되어 있지 않습니다.

> [!NOTE]
> Windows 구성 디자이너에 액세스해야 하는 오프라인 PC를 사용하고 있는 경우 [오프라인 앱 설치( Advanced Recovery Companion에 대한 지침)를 https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 따릅니다. Windows 구성 디자이너를 선택하게 합니다. 

### 2. 프로비저닝 패키지 만들기

Windows 구성 디자이너 도구를 사용하여 프로비전 패키지를 만들 수 있습니다.

1. Windows 구성 디자이너를 엽니다(기본적으로 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. **HoloLens 장치 프로비전을 선택합니다.**

   ![ICD 시작 옵션](images/icd-create-options-1703.png)

3. 프로젝트 이름을 지정하고 완료를 **선택합니다.**

4. 시작 페이지의 지침을 **** 읽고 다음을 **선택합니다.** 데스크톱 프로비전 페이지는 다음 단계를 단계로 진행합니다.
  
> [!IMPORTANT]
> 프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 안전한 장소에 프로젝트 파일을 저장하고 더 이상 필요하지 않은 경우에는 프로젝트 파일을 삭제해야 합니다.

### 설정 구성

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>엔터프라이즈 라이선스 파일을 찾아서 선택하여 HoloLens 에디션을 업그레이드합니다.</br></br>예 또는 아니요를 전환하여 첫 번째 환경의 일부를 <strong> </strong> <strong> </strong> 숨길 수도 있습니다.</br></br>디바이스 네트워크에 연결할 필요 없이 디바이스를 설정하려면 Wi-Fi 건너뛰기 설정을 Wi-Fi <strong> </strong> <strong> </strong> 으로 전환합니다.</br></br>디바이스를 사용할 지역 및 타임존을 선택합니다. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>이 섹션에서는 디바이스가 자동으로 연결해야 하는 Wi-Fi 네트워크의 세부 정보를 입력할 수 있습니다. 이렇게하려면 On을 선택하고 <strong> </strong> SSID, 네트워크 유형(열기 또는 <strong> </strong> <strong> WPA2-개인) 및 </strong> <strong> (WPA2-Personal인 </strong> 경우) 무선 네트워크의 암호를 입력합니다.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Azure Active Directory에 장치를 등록하거나 디바이스에 로컬 계정을 만들 수 있습니다.</br></br>Windows 구성 디자이너 마법사를 사용하여 대량 Azure AD 등록을 구성하려면 먼저 <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">조직에서 Azure AD 가입을 설정</a>합니다. Azure AD 테넌트의 <strong>사용자당 최대 장치 수</strong>는 마법사에서 얻은 대량 토큰을 사용할 수 있는 횟수를 결정합니다. Azure AD에 디바이스를 등록하려면 해당 옵션을 선택하고 마법사를 사용하여 가져올 대량 토큰의 이름을 입력합니다. 토큰의 만료 날짜를 설정합니다(토큰을 가져온 날로부터 최대 30일). 대량 <strong> 토큰을 </strong> 선택합니다. Let <strong>&#39;s get you signed in </strong> window, enter an account that has permissions to join a device to Azure AD, and then the password. 수락을 선택하여 Windows 구성 디자이너에 필요한 사용 <strong> 권한을 </strong> 부여합니다. </br></br>로컬 계정을 만들하려면 해당 옵션을 선택하고 사용자 이름과 암호를 입력합니다. </br></br><strong>중요:</strong> <br />(Windows 10 버전 1607에만 해당) 프로비저닝 패키지에서 로컬 계정을 만드는 경우 42일마다 설정 앱을 사용하여 암호를 <strong> </strong> 변경해야 합니다. 기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>인증서를 사용하여 디바이스를 프로비전하려면 <strong>인증서 추가</strong>를 클릭합니다. 인증서 이름을 입력하고 사용할 인증서를 찾아서 선택합니다.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>예 또는 아니요를 전환하여 <strong> </strong> <strong> </strong> HoloLens에서 개발자 모드를 사용하도록 설정하십시오. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">개발자 모드에 대해 자세히 알아보세요.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>프로비저닝 패키지를 보호하기 위해 암호를 설정하지 않습니다. 프로비저닝 패키지가 암호로 보호되는 경우 HoloLens 장치를 프로비전하지 못합니다.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

완료한 후 만들기를 **선택합니다.** 몇 초 정도 걸립니다. 패키지가 빌드되면 패키지가 저장된 위치가 페이지 맨 위에 하이퍼링크로 표시됩니다.

### 3. 고급 프로비전을 사용하여 HoloLens용 프로비저닝 패키지 만들기

> [!NOTE]
> 고급 프로비저닝에서 **** 만든 프로비저닝 패키지는 HoloLens(1세대)에 적용하기 위해 비즈니스용 Windows Holographic에 대한 버전 업그레이드 라이선스를 포함할 필요가 없습니다. [HoloLens(1세대)의 비즈니스용 Windows Holographic을 참조합니다.](hololens1-upgrade-enterprise.md)

1. Windows 구성 디자이너 시작 페이지에서 **고급 프로비전**을 선택합니다.
2. **프로젝트 세부 정보 입력** 창에서 프로젝트 이름 및 위치를 지정합니다. 선택적으로 프로젝트를 설명하는 간략한 설명을 입력합니다.

3. **다음**을 선택합니다.

4. 창을 **보고** 구성할 설정 선택에서 **Windows 10 Holographic을**선택하고 다음을 **선택합니다.**

5. 완료를 **선택합니다.**

6. 이 **문서의 런타임 설정을** 확장하고 이 문서의 부분에 설명된 설정을 사용하여 [패키지를 사용자 지정합니다.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Windows 10 버전 1607에만 해당) 프로비저닝 패키지에서 로컬 계정을 만드는 경우 42일마다 설정 앱을 사용하여 암호를 변경해야 합니다. **** 기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다. 사용자 계정이 잠긴 경우 [전체 장치 복구를 수행](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)해야 합니다.

7. 파일 ****  >  **저장을 선택합니다.**

8. 프로젝트 파일에 중요한 정보가 포함될 수 있는 경고를 읽고 확인을 **선택합니다.**

    > [!IMPORTANT]
    > 프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 안전한 장소에 프로젝트 파일을 저장하고 더 이상 필요하지 않은 경우에는 프로젝트 파일을 삭제해야 합니다.
    
9. ****  >  **프로비저닝 패키지 내보내기 선택.**

10. **** **소유자를 IT 관리자로 변경합니다.** 이렇게 하면 이 프로비저닝 패키지의 우선 순위가 다른 소스에서 이 장치에 적용된 프로비저닝 패키지보다 더 높게 설정됩니다. **다음**을 선택합니다.

11. **패키지 버전**에 대한 값을 설정합니다.

    > [!TIP]
    > 기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

12. 프로비저닝 **패키지에**대한 보안 세부 정보 선택에서 다음을 **선택합니다.**

    > [!WARNING]
    > 프로비전 패키지를 암호화 하는 경우 HoloLens 장치 프로비전이 실패합니다.  

13. **다음을** 선택하여 구축된 프로비저닝 패키지를 사용할 출력 위치를 지정합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다.

    원하는 경우 찾아보기를 선택하여 기본 출력 위치를 변경할 수 있습니다. ****

14. **다음**을 선택합니다.

15. **빌드를** 선택하여 패키지 빌드를 시작하십시오. 빌드 페이지에서 프로젝트 정보가 표시되며 진행률 표시줄은 빌드 상태를 나타냅니다.

16. 빌드가 완료되면 완료를 **선택합니다.**

<span id="apply" />

## 설치 중에 HoloLens에 프로비저닝 패키지 적용

Windows Holographic 버전 2004 또는 빌드 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 이상에서 HoloLens 2 장치는 USB 드라이브를 사용하여 프로비저닝 패키지를 적용할 수 있습니다. USB 드라이브의 루트에 .ppkg 파일을 복사하기만 합니다. 프로비저닝 패키지는 USB 드라이브의 루트에 있는 경우만 적용됩니다. 여러 프로비저닝 패키지가 시차적으로 적용됩니다.

Windows Holographic 버전 [20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상의 HoloLens 2 장치에는 이 프로세스를 간소화하고 자동으로 만드는 데 도움이 되는 최신 기능이 있습니다. 다음 섹션을 검토하세요.

- [USB에서 자동 시작 프로비전](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE에서 프로비저닝 패키지 자동 확인](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [UI를 사용하지 않고 자동 프로비전](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. USB 케이블을 사용하여 장치를 PC(또는 위에 언급된 HoloLens 2용 USB 드라이브)에 연결한 다음 디바이스를 시작하십시오. OOBE의 **대화** 가능한 첫 번째 순간 페이지를 계속 진행하지 않습니다.   
    - HoloLens(1세대)에서 이 페이지에는 파란색 상자가 있습니다. 
    - HoloLens 2에서 이 페이지에는 허밍버드가 포함되어 있습니다.

2. **볼륨 작게** 단추 및 **전원** 단추를 동시에 잠시 눌렀다 놓습니다. 

3. HoloLens는 PC의 파일 탐색기에서 장치로 표시됩니다.

4. 파일 탐색기에서 프로비저닝 패키지(.ppkg)를 장치 저장소로 끌어 놓습니다.

5. OOBE의 대화 가능한 **** 첫 번째 순간 페이지에서 볼륨 **** 다운 및 전원 단추를 동시에 잠시 누르고 해제합니다. ****

6. 디바이스에서 패키지를 신뢰할 수 있으며 패키지를 적용할지 묻습니다. 패키지를 신뢰한다고 확인합니다.

7. 패키지가 성공적으로 적용되었는지 여부가 표시됩니다. 실패한 경우 패키지 문제를 해결하고 다시 시도할 수 있습니다. 성공한 경우 OOBE를 진행합니다.

> [!NOTE]
> 2016년 8월 전에 장치를 구매한 경우 Microsoft 계정을 사용하여 장치에 로그인하고 최신 운영 체제 업데이트를 다운로드한 다음 프로비저닝 패키지를 적용하기 위해 운영 체제를 다시 설정해야 합니다.

### USB에서 자동 시작 프로비전

- OOBE 중에 프로비저닝 패키지가 있는 USB 드라이브를 사용하는 경우 사용자 조작을 덜 허용하는 자동화된 프로세스입니다.

이 릴리스 전에 사용자는 단추 조합을 사용하여 프로비전하기 위해 OOBE 중에 프로비저닝 화면을 수동으로 시작해야 했습니다. 이제 사용자가 USB 저장소 드라이브에서 프로비저닝 패키지를 사용하여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE가 처음으로 조작 가능한 순간에 프로비저닝 패키지로 USB 드라이브에 연결
1. 장치를 프로비전할 준비가 되면 프로비전 페이지가 있는 프롬프트가 자동으로 열립니다. 

참고: 장치가 부팅되는 동안 USB 드라이브가 연결되어 있는 경우 OOBE는 기존 USB 저장 장치를 열00개하고 연결되는 추가 장치를 확인합니다.

[OOBE 중 프로비저닝 패키지 적용에 대해 읽어 읽습니다.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### OOBE에서 프로비저닝 패키지 자동 확인
- 사용자 상호 작용을 덜 허용하는 자동화된 프로세스로 프로비저닝 패키지 페이지가 표시되면 나열된 모든 패키지가 자동으로 적용됩니다.

프로비저닝 주 화면이 시작될 때 OOBE는 모든 프로비저닝 패키지 적용을 자동으로 시작하기 전에 10초 아래로 계산됩니다. 사용자는 예상한 패키지를 확인한 후 10초 이내에 계속 확인하거나 취소할 수 있습니다.

### UI를 사용하지 않고 자동 프로비전
- 프로비저닝을 위한 축소된 장치 조작을 위한 결합된 자동 프로세스. 

USB 장치에서 프로비저닝 자동 시작과 프로비저닝 패키지의 자동 확인을 결합하면 사용자는 장치의 UI를 사용하지 않고 또는 장치를 착용하지 않고도 HoloLens 2 장치를 자동으로 프로비전할 수 있습니다. 여러 장치에 동일한 USB 드라이브 및 프로비저닝 패키지를 계속 사용할 수 있습니다. 이 기능은 동일한 영역에 여러 장치를 동시에 배포하는 데 유용합니다. 

1. Windows [구성 디자이너를 사용하여](hololens-provisioning.md) 프로비저닝 [패키지를 만드시다.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. USB 저장소 드라이브에 패키지를 복사합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ~ [19041.1361 이상 빌드를 플래시합니다.](https://aka.ms/hololens2previewdownload) 
1. Advanced [Recovery Companion가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 디바이스 깜박이기 작업을 완료하면 USB-C 케이블을 언플러그합니다. 
1. USB 드라이브를 장치에 연결합니다.
1. HoloLens 2 장치가 OOBE로 부팅되면 USB 드라이브에서 프로비저닝 패키지를 자동으로 검색하고 프로비저닝 페이지를 실행합니다.
1. 10초 후 장치는 프로비저닝 패키지를 자동으로 적용합니다. 

이제 장치가 구성되어 프로비전 성공 화면이 표시됩니다.

## 설치 후 HoloLens에 프로비저닝 패키지 적용

> [!NOTE]
> 이러한 단계는 Windows 10 버전 1809에만 적용됩니다.

PC에서 다음 단계를 수행합니다.
1. HoloLens 마법사를 사용하여 HoloLens용 프로비저닝 패키지 만들기에 설명된 프로비저닝 [패키지를 만드시다.](hololens-provisioning.md)
2. USB 케이블을 사용하여 HoloLens 장치를 PC에 연결합니다. HoloLens는 PC의 파일 탐색기에서 장치로 표시됩니다.
3. 프로비저닝 패키지를 HoloLens의 Documents 폴더로 끌어서 놓습니다.

HoloLens에서 다음 단계를 수행합니다.
1. 설정 **계정**  >  **액세스 직장**또는  >  **학교로 이동합니다.** 
2. 관련 **설정에서** **프로비저닝 패키지 추가 또는 제거를 선택합니다.**
3. 다음 페이지에서 패키지 **** 추가를 선택하여 파일 선택을 시작하고 프로비저닝 패키지를 선택합니다. 폴더가 비어 있는 경우 **** 이 장치를 선택하고 문서를 **선택해야 합니다.**

패키지가 적용된 후 설치된 패키지 목록에 **표시됩니다.** 패키지 세부 정보를 보거나 장치에서 패키지를 제거하려면 나열된 패키지를 선택합니다.

## 구성할 수 있는 항목

프로비저닝 패키지는 CSP(구성 서비스 공급자)를 사용합니다. CSP에 대해 잘 모르는 경우 IT 전문가를 위한 [CSP(구성 서비스 공급자) 소개](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)를 참조하세요.

Windows 구성 디자이너에서는 Windows Holographic용 프로비저닝 패키지를 만들 때 **사용 가능한 사용자 지정**의 설정은 [Windows Holographic에서 지원되는 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)를 기반으로 합니다. 다음 표에서는 HoloLens에 구성하려는 설정에 대해 설명합니다.

![HoloLens에 대한 일반적인 런타임 설정](images/icd-settings.png)

| 설정 | 설명 |
| --- | --- |
| **인증서** | HoloLens에 인증서를 배포합니다.  |
| **ConnectivityProfiles** | HoloLens에 Wi-Fi 프로필을 배포합니다.   |
| **EditionUpgrade** | [비즈니스용 Windows Holographic으로 업그레이드합니다.](hololens1-upgrade-enterprise.md)  |
| **정책** | HoloLens에서 개발자 모드를 허용하거나 차단합니다. [Windows Holographic for Business 지원 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## 프로비저닝 패키지를 통해 앱 설치

HoloLens 2 디바이스에서 프로비저닝 패키지를 통해 앱을 설치할 수 있습니다. 이렇게 하면 앱을 배포하는 데 사용할 수 있는 쉽게 다시 사용할 수 있는 패키지를 사용할 수 있습니다. 프로비저닝 패키지를 통해 앱을 배포하기 위한 [전체 지침을 읽어 읽습니다.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens(1세대)는 프로비저닝 패키지를 사용하여 앱**설치(UniversalAppInstall)를**제한적으로 지원하고 있습니다. HoloLens(1세대) 장치는 OOBE 중에만 PPKG를 통해 앱 설치를 지원하며 사용자 컨텍스트 설치만 지원합니다.
