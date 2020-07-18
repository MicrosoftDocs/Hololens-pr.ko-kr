---
title: 전체 할당된 액세스
description: 전체 할당된 액세스 키오스크에 OMA-URI를 사용하는 방법 안내
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, 할당된 액세스, 키오스크
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882454"
---
# <span data-ttu-id="ce74c-104">전체 할당된 액세스 - 키오스크</span><span class="sxs-lookup"><span data-stu-id="ce74c-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="ce74c-105">이 기능은 시스템 수준에서 적용되고, 시스템의 ID에 대한 선호도가 없으며, 장치에 로그인하는 모든 사용자에게 적용되는 복수 앱 키오스크 모드로 HoloLens 2 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="ce74c-106">이 기능은 현재 Windows 참가자 빌드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="ce74c-107">HoloLens 릴리스로 일반에 제공되기 전에 이 기능을 시험삼아 사용해 보려면 [Windows 참가자](hololens-insider.md) 빌드에 대해 자세히 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="ce74c-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="ce74c-108">Intune에서 이 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="ce74c-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="ce74c-109">"<!-"(으)로 표시된 영역에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ce74c-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="ce74c-110">이러한 영역을 사용하려면 기본 설정에 따라 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="ce74c-111">다음과 같은 방법으로 사용자 지정 OMA URI 장치 구성 프로필을 만들어 HoloLens 장치 그룹에 적용합니다. ![Intune에서 전체 할당된 액세스 OMA-URI</span><span class="sxs-lookup"><span data-stu-id="ce74c-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="ce74c-112">값을 업데이트하고 다음 콘텐츠를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-112">For value, update and paste following content:</span></span> 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## <span data-ttu-id="ce74c-113">Windows 구성 디자이너에서 이 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="ce74c-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="ce74c-114">XML 파일 형식으로 앞서 설명한 XML BLOB를 업데이트 및 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="ce74c-115">[프로비전 패키지를 사용하여 단일 앱 또는 복수 앱 키오스크 설정](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)의 단계, 특히 "프로비전</span><span class="sxs-lookup"><span data-stu-id="ce74c-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="ce74c-116">패키지 2단계 - 프로비전 패키지에 키오스크 구성 XML 파일 추가" 부분을 따르고 이전 단계에서 저장한 XML 파일을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="ce74c-117">AAD 계정 또는 AAD 그룹 한 개를 제외한 모든 사용자에게 전역 할당이 적용되는 구성을 만들 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ce74c-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="ce74c-118">예. 아래의 XML BLOB 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce74c-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="ce74c-119">로그인한 사용자의 특정 프로필을 찾을 수 없는 경우 전체 할당된 액세스 프로필이 HoloLens에 적용되어 로그인한 사용자에 대한 기본 키오스크 모드 구성으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="ce74c-120">다음은 사용할 XML BLOB의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="ce74c-121"><!- 표시된 영역에 유의하세요. 이러한 영역을 사용하려면 기본 설정에 따라 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce74c-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
