---
title: 프로 비전 패키지를 사용 하 여 HoloLens 구성 (HoloLens)
description: Windows 프로 비전을 사용 하면 IT 관리자가 이미징 없이 최종 사용자 장치를 쉽게 구성할 수 있습니다.
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
ms.openlocfilehash: cf2abe249e40e522b4d8993449b9f19033a64744
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397404"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>프로 비전 패키지를 사용 하 여 HoloLens 구성

[Windows 프로 비전](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 을 사용 하면 it 관리자가 이미징 없이 최종 사용자 장치를 쉽게 구성할 수 있습니다. Windows 구성 디자이너는 프로 비전 패키지에 기본 제공 되는 이미지 및 런타임 설정을 구성 하기 위한 도구입니다.

프로 비전 패키지에 적용할 수 있는 HoloLens 구성에는 다음이 포함 됩니다.

- [비즈니스용 Windows Holographic](hololens1-upgrade-enterprise.md) 로 업그레이드
- 로컬 계정 설정
- Wi-Fi 연결 설정
- 장치에 인증서 적용
- 개발자 모드 사용
- [자세한 지침](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)에 따라 키오스크 모드를 구성 합니다.

## <a name="provisioning-package-hololens-wizard"></a>패키지 HoloLens 마법사 프로 비전

HoloLens 마법사를 사용 하면 프로 비전 패키지에서 다음 설정을 구성할 수 있습니다.

- Enterprise edition으로 업그레이드

    > [!NOTE]
    > 이는 HoloLens 1 세대 장치에만 사용 해야 합니다. 프로 비전 패키지의 설정은 프로 비전 패키지가 Windows Holographic for Business에 대 한 버전 업그레이드 라이선스를 포함 하거나 [장치가 이미 Windows Holographic For business로 업그레이드 된](hololens1-upgrade-enterprise.md)경우에만 적용 됩니다.

- HoloLens first experience (OOBE) 구성
- Wi-Fi 네트워크 구성
- Azure Active Directory에 장치를 등록 하거나 로컬 계정을 만듭니다.
- 인증서 추가
- 개발자 모드 사용
- [자세한 지침](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)에 따라 키오스크 모드를 구성 합니다.

> [!WARNING]
> 마법사를 사용하여 Azure Active Directory 등록을 구성하려면 Windows 10 Windows 구성 디자이너를 실행해야 합니다.

프로비전 패키지에는 관리 지침 및 정책, 사용자 지정 네트워크 연결 및 정책 등이 포함될 수 있습니다.

> [!TIP]
> 데스크톱 마법사를 사용하여 일반 설정이 있는 패키지를 만든 다음 고급 편집기로 전환하여 다른 설정, 앱, 정책 등을 추가합니다.

## <a name="steps-for-creating-provisioning-packages"></a>프로비전 패키지를 만드는 단계

1. **옵션 1:** [Microsoft Store.](https://www.microsoft.com/store/apps/9nblggh4tx22) 여기에는 HoloLens 2 기능이 포함됩니다.
2. **옵션 2:** [Windows 10 용 Windows ADK(평가 및 배포 키트)에서.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Windows ADK에서 Windows 구성 디자이너를 설치하는 경우 **설치할 기능 선택** 대화 상자에서 구성 **디자이너를** 선택합니다. 이 옵션은 HoloLens 2 기능을 포함하지 않습니다.

> [!NOTE]
> Windows 구성 디자이너에 액세스해야 하는 오프라인 PC를 사용하는 경우 [오프라인 앱 설치( https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 고급 복구 도우미에 대한 지침)를 따르세요. Windows 구성 디자이너를 선택 항목으로 지정합니다. 

### <a name="2-create-the-provisioning-package"></a>2. 프로비전 패키지 만들기

Windows 구성 디자이너 도구를 사용하여 프로비전 패키지를 만듭니다.

1. Windows 구성 디자이너를 엽니다(기본적으로 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. **HoloLens 디바이스 프로비저닝을** 선택합니다.

   ![ICD 시작 옵션](images/icd-create-options-1703.png)

3. 프로젝트 이름을 지정하고 **마침을** 선택합니다.

4. 시작 페이지에서 지침을 읽고 **다음을** 선택합니다.  데스크톱 프로비전에 대한 페이지에서는 다음 단계를 안내합니다.
  
> [!IMPORTANT]
> 프로비전 패키지를 빌드할 때 프로젝트 파일 및 프로비전 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. . Ppkg 파일을 암호화 하는 옵션이 있지만 프로젝트 파일은 암호화 되지 않습니다. 프로젝트 파일을 안전한 위치에 저장 하 고 더 이상 필요 하지 않은 경우 프로젝트 파일을 삭제 해야 합니다.

### <a name="configure-settings"></a>설정 구성

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>엔터프라이즈 라이선스 파일을 찾아 선택 하 여 HoloLens 버전을 업그레이드 합니다.</br></br><strong>예</strong> 또는 <strong>아니요</strong> 를 설정 하 여 첫 번째 환경의 일부를 숨길 수도 있습니다.</br></br>Wi-Fi 네트워크에 연결할 필요 없이 장치를 설정 하려면 <strong>Wi-Fi 설정 건너뛰기</strong> <strong>를 켜기로 설정 합니다.</strong></br></br>장치가 사용 될 지역과 표준 시간대를 선택 합니다. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>이 섹션에서는 장치에서 자동으로 연결 해야 하는 Wi-Fi 무선 네트워크의 세부 정보를 입력할 수 있습니다. 이렇게 하려면 <strong>켜기</strong>를 선택 하 고 SSID, 네트워크 유형 (<strong>개방형</strong> 또는 <strong>Wpa2-개인</strong>) 및 ( <strong>WPA2-개인</strong>) 무선 네트워크에 대 한 암호를 입력 합니다.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>장치를 Azure Active Directory에 등록 하거나 장치에서 로컬 계정을 만들 수 있습니다.</br></br>Windows 구성 디자이너 마법사를 사용 하 여 대량 Azure AD 등록을 구성 하기 전에 <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">조직에서 AZURE ad 조인을 설정</a>합니다. Azure AD 테 넌 트의 <strong>사용자 당 최대 장치 수</strong> 설정은 마법사에서 가져온 대량 토큰을 사용할 수 있는 횟수를 결정 합니다. Azure AD에 장치를 등록 하려면 해당 옵션을 선택 하 고 마법사를 사용 하 여 가져올 대량 토큰의 이름을 입력 합니다. 토큰의 만료 날짜를 설정 합니다 (토큰을 가져온 날짜 로부터 최대 30 일). <strong>대량 토큰 가져오기</strong>를 선택 합니다. 사용자가 <strong>로그인 할 수 있습니다</strong> . 창&#39;에서 장치를 Azure AD에 가입 시킬 수 있는 권한이 있는 계정을 입력 한 다음 암호를 입력 합니다. <strong>동의</strong> 를 선택 하 여 Windows 구성 디자이너에 필요한 사용 권한을 부여 합니다. </br></br>로컬 계정을 만들려면 해당 옵션을 선택 하 고 사용자 이름 및 암호를 입력 합니다. </br></br><strong>중요 한</strong> <br />(Windows 10, 버전 1607에만 해당) 프로 비전 패키지에서 로컬 계정을 만드는 경우 42 일 마다 <strong>설정</strong> 앱을 사용 하 여 암호를 변경 해야 합니다. 해당 기간 동안 암호가 변경되지 않으면 계정이 잠기고 로그인할 수 없습니다.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>인증서를 사용하여 디바이스를 프로비전하려면 인증서 <strong>추가를</strong>클릭합니다. 인증서의 이름을 입력한 다음 사용할 인증서를 찾아 선택합니다.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>HoloLens에서 개발자 모드를 사용하도록 설정하려면 <strong>예</strong> 또는 <strong>아니요를</strong> 전환합니다. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">개발자 모드에 대해 자세히 알아보세요.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>프로비전 패키지를 보호하기 위해 암호를 설정하지 마십시오. 프로비전 패키지가 암호로 보호되는 경우 HoloLens 디바이스를 프로비전하지 못합니다.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

완료되면 **만들기** 를 선택합니다. 몇 초밖에 걸리지 않습니다. 패키지를 빌드하면 패키지가 저장되는 위치가 페이지 아래쪽에 하이퍼링크로 표시됩니다.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. 고급 프로비저닝을 사용하여 HoloLens에 대한 프로비저닝 패키지 만들기

> [!NOTE]
> 고급 프로비저닝에서 만든 **프로비전** 패키지는 HoloLens(1세대)에 성공적으로 적용하기 위해 Windows Holographic for Business 버전 업그레이드 라이선스를 포함할 필요가 없습니다. [HoloLens(1세대)의 Windows Holographic for Business 자세히 참조하세요.](hololens1-upgrade-enterprise.md)

1. Windows 구성 디자이너 시작 페이지에서 **고급 프로비저닝을** 선택합니다.
2. 프로젝트 **세부 정보 입력** 창에서 프로젝트의 이름과 프로젝트의 위치를 지정합니다. 필요에 따라 프로젝트를 설명하는 간단한 설명을 입력합니다.

3. **새로 만들기** 를 선택합니다.

4. 보고 **구성할 설정 선택** 창에서 **Windows 10 Holographic** 선택한 후 **다음을** 선택합니다.

5. **마침** 을 선택합니다.

6. **런타임 설정을** 확장하고 이 문서의 후반부에 [설명된](#what-you-can-configure)설정을 사용하여 패키지를 사용자 지정합니다.

    > [!IMPORTANT]
    > (Windows 10 버전 1607에만 해당) 프로비전 패키지에서 로컬 계정을 만드는 경우 42일마다 **설정** 앱을 사용하여 암호를 변경해야 합니다. 해당 기간 동안 암호가 변경되지 않으면 계정이 잠기고 로그인할 수 없습니다. 사용자 계정이 잠겨 있는 경우 [전체 디바이스 복구를 수행해야](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)합니다.

7. **파일** > **저장** 을 선택합니다.

8. 프로젝트 파일에 중요 한 정보가 포함 될 수 있다는 경고를 읽은 다음 **확인** 을 선택 합니다.

    > [!IMPORTANT]
    > 프로 비전 패키지를 빌드할 때 프로젝트 파일 및 프로 비전 패키지 (ppkg) 파일에 중요 한 정보가 포함 될 수 있습니다. . Ppkg 파일을 암호화 하는 옵션이 있지만 프로젝트 파일은 암호화 되지 않습니다. 프로젝트 파일을 안전한 위치에 저장 하 고 더 이상 필요 하지 않은 경우 프로젝트 파일을 삭제 해야 합니다.
    
9.   >  **프로 비전 패키지** 내보내기를 선택 합니다.

10. **소유자** 를 **IT 관리자** 로 변경 합니다. 이는 다른 원본에서이 장치에 적용 된 프로 비전 패키지 보다 높은이 프로 비전 패키지의 우선 순위를 설정 합니다. **새로 만들기** 를 선택합니다.

11. **패키지 버전** 에 대 한 값을 설정 합니다.

    > [!TIP]
    > 기존 패키지를 변경 하 고 버전 번호를 변경 하 여 이전에 적용 된 패키지를 업데이트할 수 있습니다.

12. **프로 비전 패키지에 대 한 보안 세부 정보 선택** 에서 **다음** 을 선택 합니다.

    > [!WARNING]
    > 프로 비전 패키지를 암호화 하는 경우 HoloLens 장치를 프로 비전 하는 작업이 실패 합니다.  

13. **다음** 을 선택 하 여 프로 비전 패키지를 빌드할 때 사용할 출력 위치를 지정 합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용 합니다.

    필요에 따라 **찾아보기** 를 선택 하 여 기본 출력 위치를 변경할 수 있습니다.

14. **새로 만들기** 를 선택합니다.

15. **빌드** 를 선택 하 여 패키지 빌드를 시작 합니다. 빌드 페이지에 프로젝트 정보가 표시 되 고 진행률 표시줄이 빌드 상태를 나타냅니다.

16. 빌드가 완료 되 면 **마침** 을 선택 합니다.

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>설치 하는 동안 HoloLens에 프로 비전 패키지 적용

Windows Holographic 버전 2004 또는 빌드 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 이상에서 HoloLens 2 장치는 USB 드라이브를 사용 하 여 프로 비전 패키지를 적용할 수 있습니다. 파일을 USB 드라이브의 루트에 복사 하면 됩니다. 프로 비전 패키지는 USB 드라이브의 루트에 있는 경우에만 적용 됩니다. 여러 프로비전 패키지가 순차적으로 적용됩니다.

[Windows Holographic 버전 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 이상의 HoloLens 2 디바이스에는 이 프로세스를 자동으로 간소화하고 간소화하는 데 도움이 되는 최신 기능이 있습니다. 다음 섹션을 검토하세요.

- [USB에서 자동 시작 프로비저닝](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE에서 프로비저닝 패키지 자동 확인](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [UI를 사용하지 않고 자동 프로비전](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. USB 케이블을 사용하여 디바이스를 PC(또는 위에서 설명한 대로 HoloLens 2 USB 드라이브)에 연결한 다음 디바이스를 시작합니다. OOBE의 **첫 번째 상호 작용 가능한 순간** 페이지를 지나서 계속하지 마십시오.   
    - HoloLens(1세대)에서 이 페이지에는 파란색 상자가 포함되어 있습니다. 
    - HoloLens 2 이 페이지에는mingbird가 포함되어 있습니다.

2. 볼륨 **다운** 및 **전원** 단추를 동시에 짧게 누르고 놓습니다. 

3. HoloLens는 PC의 파일 탐색기 디바이스로 표시됩니다.

4. 파일 탐색기 프로비전 패키지(.ppkg)를 디바이스 스토리지로 끌어서 놓습니다.

5. OOBE의 **첫 번째 상호 작용 가능한 순간** 페이지에 있는 동안 볼륨 **다운** 및 **전원** 단추를 동시에 잠시 누르고 놓습니다.

6. 디바이스에서 패키지를 신뢰하고 적용할지 묻는 메시지가 표시됩니다. 패키지를 신뢰하는지 확인합니다.

7. 패키지가 성공적으로 적용되었는지 여부가 표시됩니다. 실패한 경우 패키지를 수정하고 다시 시도할 수 있습니다. 성공하면 OOBE를 계속 진행합니다.

> [!NOTE]
> 2016년 8월 이전에 디바이스를 구매한 경우 Microsoft 계정 사용하여 디바이스에 로그인하고, 최신 운영 체제 업데이트를 받은 다음, 프로비전 패키지를 적용하기 위해 운영 체제를 다시 설정해야 합니다.

### <a name="auto-launch-provisioning-from-usb"></a>USB에서 프로 비전 자동 시작

- 프로 비전 패키지를 사용 하는 USB 드라이브가 OOBE 중에 사용 되는 경우 사용자 상호 작용을 줄일 수 있는 자동화 된 프로세스입니다.

이 릴리스는 사용자가 단추 조합을 사용 하 여 프로 비전 하는 동안 수동으로 프로 비전 화면을 시작 해야 합니다. 이제 사용자가 USB 저장소 드라이브에서 프로 비전 패키지를 사용 하 여 단추 조합을 건너뛸 수 있습니다. 

1. OOBE의 첫 번째 interactable 순간에 프로 비전 패키지를 사용 하 여 USB 드라이브에 연결
1. 장치를 프로 비전 할 준비가 되 면 프로 비전 페이지를 사용 하 여 프롬프트가 자동으로 열립니다. 

참고: 장치가 부팅 되는 동안 USB 드라이브가 연결 된 상태를 유지 하는 경우 OOBE는 기존 USB 저장 장치를 열거 하 고 연결 되는 추가 항목을 감시 합니다.

[OOBE 중에 프로 비전 패키지 적용](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)을 참조 하세요.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE에서 프로 비전 패키지 자동 확인
- 사용자 상호 작용을 줄일 수 있는 자동화 된 프로세스, 프로 비전 패키지 페이지가 표시 되 면 나열 된 모든 패키지가 자동으로 적용 됩니다.

프로 비전 주 화면이 나타나면 OOBE는 모든 프로 비전 패키지 적용을 자동으로 시작 하기 전에 10 초 후에 계산 됩니다. 사용자는 예상 되는 패키지를 확인 한 후이 10 초 내에 계속 확인 하거나 취소할 수 있습니다.

### <a name="automatic-provisioning-without-using-ui"></a>UI를 사용 하지 않고 자동 프로 비전
- 프로 비전을 위해 장치 상호 작용을 줄이는 자동 프로세스를 결합 했습니다. 

USB 장치에서 프로 비전의 자동 시작과 프로 비전 패키지의 자동 확인을 결합 하 여 사용자는 장치 UI를 사용 하거나 장치를 사용 하지 않고 HoloLens 2 장치를 자동으로 프로 비전 할 수 있습니다. 여러 장치에 대해 동일한 USB 드라이브 및 프로 비전 패키지를 계속 사용할 수 있습니다. 이는 동일한 영역에서 한 번에 여러 장치를 배포 하는 데 유용 합니다. 

1. [Windows 구성 디자이너](https://www.microsoft.com/store/productId/9NBLGGH4TX22)를 사용 하 여 [프로 비전 패키지를 만듭니다](hololens-provisioning.md) . 
1. 패키지를 USB 저장소 드라이브에 복사 합니다.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ~ [19041.1361 이상 빌드](https://aka.ms/hololens2previewdownload)를 깜박입니다. 
1. [고급 복구 도우미가](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 완료된 경우 디바이스가 USB-C 케이블을 분리합니다. 
1. USB 드라이브를 디바이스에 연결합니다.
1. HoloLens 2 디바이스가 OOBE로 부팅되면 USB 드라이브에서 프로비전 패키지를 자동으로 검색하고 프로비전 페이지를 시작합니다.
1. 10초 후에 디바이스는 자동으로 프로비전 패키지를 적용합니다. 

이제 디바이스가 구성되었으며 프로비전 성공 화면이 표시됩니다.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>설치 후 HoloLens에 프로비저닝 패키지 적용/제거

> [!NOTE]
> 이러한 단계는 Windows Holographic 버전 1809 이상의 모든 HoloLens 2 디바이스 및 HoloLens(1세대) 디바이스에 적용됩니다.

PC에서 다음 단계를 수행합니다.
1. [HoloLens 마법사를 사용하여 HoloLens에 대한 프로비저닝 패키지 만들기에](hololens-provisioning.md)설명된 대로 프로비전 패키지를 만듭니다.
2. USB 케이블을 사용하여 HoloLens 디바이스를 PC에 연결합니다. HoloLens는 PC의 파일 탐색기 디바이스로 표시됩니다.
3. 프로비전 패키지를 HoloLens의 Documents 폴더로 끌어서 놓습니다.

HoloLens에서 다음 단계를 수행합니다.
1. **설정** > **계정** > **회사 또는 학교 액세스** 로 이동합니다. 
2. **관련 설정** 에서 **프로비전 패키지 추가 또는 제거를** 선택합니다.
3. 다음 페이지에서 패키지 **추가를** 선택하여 파일 선택기를 시작하고 프로비전 패키지를 선택합니다. 폴더가 비어 있는 경우 **이 디바이스를** 선택하고 **문서** 를 선택합니다.

패키지가 적용되면 설치된 패키지 목록에 **표시됩니다.** 패키지 세부 정보를 보거나 디바이스에서 패키지를 제거하려면 나열된 패키지를 선택합니다.

## <a name="what-you-can-configure"></a>구성할 수 있는 항목

프로비전 패키지는 CSP(구성 서비스 공급자)를 사용합니다. CSP에 익숙하지 않은 경우 [IT 장점을 위한 CSP(구성 서비스 공급자) 소개를 참조하세요.](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

Windows 구성 디자이너에서 Windows Holographic 프로 비전 패키지를 만들 때 **사용 가능한 사용자 지정** 의 설정은 [windows Holographic에서 지원](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)되는 csp를 기반으로 합니다. 다음 표에서는 HoloLens에 대해 구성할 수 있는 설정을 설명 합니다.

![HoloLens의 일반 런타임 설정](images/icd-settings.png)

| 설정 | 설명 |
| --- | --- |
| **인증서** | HoloLens에 인증서를 배포 합니다.  |
| **ConnectivityProfiles** | HoloLens에 Wi-Fi 프로필을 배포 합니다.   |
| **EditionUpgrade** | [비즈니스용 Windows Holographic로 업그레이드 합니다.](hololens1-upgrade-enterprise.md)  |
| **정책** | HoloLens에서 개발자 모드를 허용 하거나 차단 합니다. [비즈니스용 Windows Holographic에서 지 원하는 정책](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>프로 비전 패키지를 통해 앱 설치

앱은 HoloLens 2 장치에서 프로 비전 패키지를 통해 설치할 수 있습니다. 이렇게 하면 앱을 배포 하는 데 사용할 수 있는 쉽게 다시 사용할 수 있는 패키지를 사용할 수 있습니다. [프로 비전 패키지를 통해 앱을 배포](app-deploy-provisioning-package.md)하는 방법에 대 한 전체 지침을 읽습니다.  

> [!NOTE]
> HoloLens (첫 번째 gen)는 프로 비전 패키지를 사용 하 여 앱 설치 (**UniversalAppInstall**)를 제한적으로 지원 합니다. HoloLens (첫 번째 gen) 장치는 OOBE 중에만 PPKG를 통해 앱을 설치 하 고 사용자 컨텍스트 설치만 지원 합니다.
