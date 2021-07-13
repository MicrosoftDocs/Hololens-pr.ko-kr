---
title: Windows Holographic for Business 기능 잠금 해제
description: Windows Holographic for Business 업그레이드하는 경우 HoloLens 비즈니스용으로 설계된 추가 기능을 제공합니다.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635197"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="c312a-103">Windows Holographic for Business 기능 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="c312a-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c312a-104">이 페이지는 HoloLens 1세대에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="c312a-105">Microsoft HoloLens Holographic(HoloLens 위해 설계된 Windows 10 버전)Windows 실행되는 *Development Edition* 및 비즈니스용으로 설계된 추가 기능을 제공하는 [Commercial Suite에서](hololens-commercial-features.md)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="c312a-106">Commercial Suite를 구매하면 holographic을 Windows Windows Holographic for Business 업그레이드하는 라이선스가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="c312a-107">조직의 [MDM(모바일 디바이스 관리) 공급자](#edition-upgrade-by-using-mdm) 또는 [프로비전 패키지를](#edition-upgrade-by-using-a-provisioning-package)사용하여 디바이스에 이 라이선스를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="c312a-108">Windows 10 버전 1803에서는 설정 시스템을 선택하여 HoloLens 비즈니스 버전으로 업그레이드되었는지 확인할 수   >  있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="c312a-109">MDM을 사용하여 버전 업그레이드</span><span class="sxs-lookup"><span data-stu-id="c312a-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="c312a-110">엔터프라이즈 라이선스는 [WindowsLicensing CSP(구성 서비스 공급자)를](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)지원하는 모든 MDM 공급자가 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="c312a-111">최신 버전의 Microsoft MDM API는 WindowsLicensing CSP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="c312a-112">Microsoft Intune 사용하여 HoloLens 업그레이드하는 단계별 지침은 Windows [Holographic을 실행하는 디바이스를 Windows Holographic for Business](/intune/holographic-upgrade)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c312a-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="c312a-113">다른 MDM 공급자에서는 정책을 설정하고 배포하기 위한 특정 단계가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="c312a-114">프로비전 패키지를 사용하여 버전 업그레이드</span><span class="sxs-lookup"><span data-stu-id="c312a-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="c312a-115">프로비전 패키지는 디바이스에 지정된 구성을 적용하는 Windows 구성 디자이너 도구에서 만든 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="c312a-116">Windows Holographic 버전을 업그레이드하는 프로비저닝 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="c312a-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="c312a-117">HoloLens 대한 프로비저닝 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="c312a-118">**런타임 설정**  >  **버전업그레이드로** 이동하여 **EditionUpgradeWithLicense** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![라이선스 설정이 선택된 버전 업그레이드](images/icd1.png)

1. <span data-ttu-id="c312a-120">Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c312a-121">[프로비전 패키지 에서 추가 설정을](hololens-provisioning.md)구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="c312a-122">**파일** 메뉴에서 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="c312a-123">프로젝트 파일에 중요한 정보가 포함될 수 있다는 경고를 읽고 **확인을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c312a-124">프로비전 패키지를 빌드할 때 프로젝트 파일 및 프로비전 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="c312a-125">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="c312a-126">프로젝트 파일을 안전한 위치에 저장하고 더 이상 필요하지 않은 경우 프로젝트 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="c312a-127">**내보내기** 메뉴에서 **패키지 프로비저닝을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="c312a-128">**소유자를** **IT 관리자로** 변경합니다. 이 프로비저닝 패키지의 우선 순위를 다른 원본에서 이 디바이스에 적용된 다른 패키지보다 높게 설정한 후 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="c312a-129">**패키지 버전** 에 대한 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c312a-130">기존 패키지를 변경하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="c312a-131">**프로비전 패키지에 대한 보안 세부 정보 선택에서** **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="c312a-132">**다음을** 선택하여 프로비전 패키지가 빌드된 후 이동하려는 출력 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="c312a-133">기본적으로 Windows ICD는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="c312a-134">필요에 따라 **찾아보기를** 선택하여 기본 출력 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="c312a-135">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-135">Select **Next**.</span></span>

1. <span data-ttu-id="c312a-136">**빌드를** 선택하여 패키지 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="c312a-137">빌드 페이지에 프로젝트 정보가 표시되고 진행률 표시줄에 빌드 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="c312a-138">빌드가 완료되면 **마침을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="c312a-139">프로비전 패키지를 HoloLens 적용</span><span class="sxs-lookup"><span data-stu-id="c312a-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="c312a-140">USB 케이블을 사용하여 디바이스를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="c312a-141">디바이스를 시작하지만 초기 설정 환경의 **맞춤** 페이지(파란색 상자가 있는 첫 번째 페이지)를 지나서 계속 진행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="c312a-142">PC에서 HoloLens 파일 탐색기 디바이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c312a-143">HoloLens 디바이스가 Windows 10 버전 1607 이하를 실행하는 경우 디바이스에서 볼륨 **다운** 및 **전원** 단추를 동시에 누르고 해제하여 파일 탐색기 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="c312a-144">파일 탐색기 프로비전 패키지(.ppkg)를 디바이스 스토리지로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="c312a-145">HoloLens **여전히 적합** 페이지에 있는 동안 잠시 누르고 **볼륨 다운** 및 **전원** 단추를 동시에 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="c312a-146">HoloLens 패키지를 신뢰하고 적용할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="c312a-147">패키지를 신뢰하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="c312a-148">패키지가 성공적으로 적용되었는지 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="c312a-149">성공적으로 적용되지 않은 경우 패키지를 수정하고 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="c312a-150">성공하면 디바이스 설정을 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c312a-150">If successful, proceed with device setup.</span></span>
