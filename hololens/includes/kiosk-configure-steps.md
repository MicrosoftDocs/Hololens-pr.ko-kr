---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859427"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[단일 앱 키오스크 템플릿 Microsoft Intune](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>단일 앱 키오스크 템플릿 Microsoft Intune

1. 구성 프로필 만들기 <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. 키오스크 템플릿 선택 <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 단일 앱 또는 여러 앱 키오스크를 선택하고 키오스크 모드에 대한 사용자 대상 지정의 종류도 선택합니다. <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. 키오스크 모드에서 실행할 앱 선택 <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. 나머지 옵션은 그대로 둡니다. <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 이 구성 프로필을 할당할 그룹/디바이스 또는 사용자 선택 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. 검토 및 만들기를 통해 구성 프로필 저장
8. 디바이스 또는 Intune에서 MDM 동기화를 수행하여 디바이스에 구성을 적용합니다. [Intune에서](/mem/intune/remote-actions/device-sync#sync-a-device) 또는 **설정 -> 계정 -> Work 또는 school을** 통해 디바이스에서 디바이스 동기화 ->연결된 계정 **-> 정보 -> 동기화를** 선택합니다.
9. 키오스크를 경험하려면 대상 사용자로 로그인합니다.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[다중 앱 키오스크 템플릿 Microsoft Intune](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>다중 앱 키오스크 템플릿 Microsoft Intune

1. 구성 프로필 만들기 <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. 키오스크 템플릿 선택 <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 단일 앱 또는 여러 앱 키오스크를 선택하고 키오스크 모드에 대한 사용자 대상 지정의 종류도 선택합니다. <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. 키오스크 모드에서 실행할 앱 선택 <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. 나머지 옵션은 그대로 둡니다. <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 이 구성 프로필을 할당할 그룹/디바이스 또는 사용자 선택 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. 검토 및 만들기를 통해 구성 프로필 저장
8. 디바이스 또는 Intune에서 MDM 동기화를 수행하여 디바이스에 구성을 적용합니다. [Intune에서](/mem/intune/remote-actions/device-sync#sync-a-device) 또는 **설정 -> 계정 -> Work 또는 school을** 통해 디바이스에서 디바이스 동기화 ->연결된 계정 **-> 정보 -> 동기화를** 선택합니다.
9. 키오스크를 경험하려면 대상 사용자로 로그인합니다.

# <a name="microsoft-intune-custom-template"></a>[사용자 지정 템플릿 Microsoft Intune](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>사용자 지정 템플릿 Microsoft Intune

1. 원하는 키오스크 환경을 위한 xml 구성을 만듭니다. 시작하려면 여기에서 [예제를](../hololens-kiosk-reference.md#kiosk-xml-code-samples) 참조하세요.

1. 사용자 지정 구성 프로필 만들기 <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. 사용자 지정 구성 프로필의 이름을 지정하고 "구성 설정" 섹션에서 "추가"를 클릭하여 OMA-URI 설정을 추가합니다. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. OMA-URI 설정의 이름을 지정합니다.

    1. OMA-URI 텍스트 상자에 **./Device/Vendor/MSFT/AssignedAccess/Configuration을 입력합니다.**
    1. 데이터 형식을 **문자열** 로 선택합니다.
    1. 값 텍스트 상자에 할당된 액세스 구성 xml을 복사하여 붙여넣습니다(복사-붙여넣기 전에 필요에 따라 시나리오 및 업데이트에 따른 예제에 대한 참조 링크 참조).
    1. 저장 단추를 선택하여 설정 및 구성을 저장합니다.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. 이 구성 프로필을 할당할 그룹/디바이스 또는 사용자를 선택합니다. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. 검토 및 만들기를 통해 구성 프로필을 저장합니다.
1. 디바이스 또는 Intune에서 MDM 동기화를 수행하여 디바이스에 구성을 적용합니다. [Intune에서](/mem/intune/remote-actions/device-sync#sync-a-device) 또는 **설정 -> 계정 -> Work 또는 school을** 통해 디바이스에서 디바이스 동기화 ->연결된 계정 **-> 정보 -> 동기화를** 선택합니다.
1. 키오스크를 경험하려면 대상 사용자로 로그인합니다.

# <a name="runtime-provisioning---multi-app"></a>[런타임 프로비저닝 - 다중 앱](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>런타임 프로비저닝 - 다중 앱

1. 원하는 키오스크 환경을 위한 xml 구성을 만듭니다. 시작하려면 여기에서 [예제를](../hololens-kiosk-reference.md#kiosk-xml-code-samples) 참조하세요.

1. Windows 구성 디자이너 를 [엽니다.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. 시작 페이지에서 **HoloLens 디바이스 프로비저닝을 선택합니다.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. **HoloLens 2 디바이스 프로비저닝을** 선택한 후 다음을 선택합니다. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. 프로젝트 이름을 지정합니다. 필요에 따라 설명을 작성합니다. **마침을** 선택하여 계속 진행합니다.

6. 화면 왼쪽 아래에서 **고급 편집기로 전환을 선택합니다.** 예를 선택하여 고급 편집기로 전환을 **확인합니다.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. 왼쪽에서 런타임 설정, AssignedAccess를 확장하고 **MultiAppAssignedAccess 를** 선택합니다. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. **찾아보기...** 선택 단추를 단추를 하여 파일 탐색기를 엽니다. 그리고 구성된 키오스크 xml 파일을 선택합니다.

9. **내보내기,** **패키지 프로비저닝을** 선택합니다.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. 소유자 유형을 **IT 관리자로** 변경합니다. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. **다음** 을 세 번 선택합니다. 그런 **다음, 빌드를** 선택합니다.

12. 프로비전 패키지가 빌드된 후 출력 위치 폴더를 엽니다. .ppkg 파일은 프로비전 패키지입니다. 선택적 단계: 프로젝트를 저장합니다.

13. 이제 프로비전 패키지를 적용할 수 있습니다. [설치하는 동안 프로비전 패키지를 HoloLens 적용하거나 설치](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) [후 프로비전 패키지를 HoloLens 적용할](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)수 있습니다.

14. 키오스크를 경험하려면 대상 사용자로 로그인합니다.

# <a name="runtime-provisioning---single-app"></a>[런타임 프로비저닝 - 단일 앱](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>런타임 프로비저닝 - 단일 앱

1. Windows 구성 디자이너 를 [엽니다.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. 시작 페이지에서 **HoloLens 디바이스 프로비저닝을 선택합니다.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. **HoloLens 2 디바이스 프로비저닝을** 선택한 후 다음을 선택합니다. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. 프로젝트 이름을 지정합니다. 필요에 따라 설명을 작성합니다. **마침을** 선택하여 계속 진행합니다.

5. 화면 왼쪽 아래에서 **고급 편집기로 전환을 선택합니다.** 예를 선택하여 고급 편집기로 전환을 **확인합니다.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. 왼쪽에서 런타임 설정, AssignedAccess를 확장하고 **AssignedAccessSettings** 를 선택합니다. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. 텍스트 상자에서 키오스크를 정의합니다. 예를 들어 다음은 설정 앱인 LocalAccount라는 로컬 계정에 대한 단일 앱 키오스크를 만듭니다.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. **내보내기,** **패키지 프로비저닝을** 선택합니다. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. 소유자 유형을 **IT 관리자로** 변경합니다. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. **다음** 을 세 번 선택합니다. 그런 **다음, 빌드를** 선택합니다.

11. 프로비전 패키지가 빌드된 후 출력 위치 폴더를 엽니다. .ppkg 파일은 프로비전 패키지입니다. 선택적 단계: 프로젝트를 저장합니다.

12. 이제 프로비전 패키지를 적용할 수 있습니다. [설치하는 동안 프로비전 패키지를 HoloLens 적용하거나 설치](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) [후 프로비전 패키지를 HoloLens 적용할](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)수 있습니다.