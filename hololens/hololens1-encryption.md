---
title: HoloLens BitLocker 암호화
description: BitLocker 디바이스 암호화를 사용하도록 설정하여 HoloLens 혼합 현실 디바이스에 저장된 파일을 보호하는 방법을 알아봅니다.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635248"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="04338-103">HoloLens(1세대) BitLocker 암호화</span><span class="sxs-lookup"><span data-stu-id="04338-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="04338-104">HoloLens(1세대) 및 HoloLens 2 모두 BitLocker를 사용하여 디바이스 암호화를 지원합니다. 그러나 BitLocker는 항상 HoloLens 2 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="04338-105">이 문서는 HoloLens(1세대)에서 BitLocker를 사용하도록 설정하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="04338-106">HoloLens(1세대)에서는 수동으로 또는 MDM(모바일 디바이스 관리)을 사용하여 BitLocker 디바이스 암호화를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="04338-107">다음 지침에 따라 [BitLocker 디바이스 암호화를](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) 사용하도록 설정하여 HoloLens 저장된 파일 및 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="04338-108">디바이스 암호화는 BitLocker CSP(구성 서비스 공급자)의 [EncryptionMethodByDriveType 메서드 3과](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 동일한 AES-CBC 128 암호화 방법을 사용하여 데이터를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="04338-109">올바른 암호화 키(예: 암호)가 있는 직원은 암호를 해독하거나 데이터 복구를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="04338-110">MDM을 사용하여 디바이스 암호화 사용</span><span class="sxs-lookup"><span data-stu-id="04338-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="04338-111">MDM(모바일 장치 관리) 공급자를 사용하여 디바이스 암호화가 필요한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="04338-112">사용할 정책은 정책 CSP의 [Security/RequireDeviceEncryption 설정입니다.](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption)</span><span class="sxs-lookup"><span data-stu-id="04338-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="04338-113">Microsoft Intune 사용하여 디바이스 암호화를 사용하도록 설정하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04338-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="04338-114">다른 MDM 도구에 대한 지침은 MDM 공급자의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04338-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="04338-115">MDM 공급자에 디바이스 암호화에 대한 사용자 지정 URI가 필요한 경우 다음 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="04338-116">**이름:** 선택한 이름</span><span class="sxs-lookup"><span data-stu-id="04338-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="04338-117">**설명:** 선택 사항</span><span class="sxs-lookup"><span data-stu-id="04338-117">**Description**: optional</span></span>
- <span data-ttu-id="04338-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="04338-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="04338-119">**데이터 형식:** 정수</span><span class="sxs-lookup"><span data-stu-id="04338-119">**Data type**: integer</span></span>
- <span data-ttu-id="04338-120">**값**: `1`</span><span class="sxs-lookup"><span data-stu-id="04338-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="04338-121">프로비전 패키지를 사용하여 디바이스 암호화 사용</span><span class="sxs-lookup"><span data-stu-id="04338-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="04338-122">프로비전 패키지는 디바이스에 지정된 구성을 적용하는 Windows 구성 디자이너 도구에서 만든 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="04338-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="04338-123">Windows Holographic 버전을 업그레이드하고 암호화를 사용하도록 설정하는 프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="04338-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="04338-124">HoloLens 대한 프로비저닝 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04338-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="04338-125">**런타임 설정** 정책 보안 로 이동하여  >    >   **RequireDeviceEncryption을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![디바이스 암호화 설정이 '예'로 구성되어야 함](images/device-encryption.png)

1. <span data-ttu-id="04338-127">Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="04338-128">Commercial Suite를 구매할 때 제공된 XML 라이선스 파일을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="04338-129">[프로비전 패키지 에서 추가 설정을](hololens-provisioning.md)구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="04338-130">**파일** 메뉴에서 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="04338-131">프로젝트 파일에 중요한 정보가 포함될 수 있음을 설명하는 경고를 읽고 **확인을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04338-132">프로비전 패키지를 빌드할 때 프로젝트 파일 및 프로비전 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="04338-133">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="04338-134">프로젝트 파일을 안전한 위치에 저장하고 더 이상 필요하지 않은 경우 프로젝트 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="04338-135">**내보내기** 메뉴에서 **패키지 프로비저닝을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="04338-136">**소유자를** **IT 관리자** 로 변경합니다. 이 프로비전 패키지의 우선 순위는 다른 원본에서 이 디바이스에 적용된 프로비저닝 패키지보다 높게 설정한 후 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="04338-137">**패키지 버전** 에 대한 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="04338-138">기존 패키지를 변경하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="04338-139">**프로비전 패키지에 대한 보안 세부 정보 선택에서** **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="04338-140">**다음** 을 클릭하여 프로비전 패키지가 빌드된 후 이동하려는 출력 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="04338-141">기본적으로 Windows ICD는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="04338-142">필요에 따라 찾아보기를 클릭하여 기본 출력 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="04338-143">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-143">Click **Next**.</span></span>
1. <span data-ttu-id="04338-144">**빌드를** 클릭하여 패키지 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="04338-145">프로젝트 정보가 빌드 페이지에 표시되고 진행률 표시줄에 빌드 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="04338-146">빌드가 완료되면 **마침을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="04338-147">프로비전 패키지를 HoloLens 적용</span><span class="sxs-lookup"><span data-stu-id="04338-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="04338-148">USB를 통해 디바이스를 PC로 커넥트 디바이스를 시작하지만 초기 설정 환경의 **맞춤** 페이지(파란색 상자가 있는 첫 번째 페이지)를 지나서 계속 진행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="04338-149">볼륨 **다운** 및 **전원** 단추를 동시에 짧게 누르고 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="04338-150">HoloLens PC의 파일 탐색기 디바이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="04338-151">파일 탐색기 프로비전 패키지(.ppkg)를 디바이스 스토리지로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="04338-152">**맞춤** 페이지에서 볼륨 **다운** 및 **전원** 단추를 동시에 다시 짧게 누르고 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="04338-153">디바이스에서 패키지를 신뢰하고 적용할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="04338-154">패키지를 신뢰하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="04338-155">패키지가 성공적으로 적용되었는지 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04338-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="04338-156">실패한 경우 패키지를 수정하고 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="04338-157">성공하면 디바이스 설정을 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="04338-158">2016년 8월 이전에 디바이스를 구매한 경우 Microsoft 계정 사용하여 디바이스에 로그인하고, 최신 OS 업데이트를 다운로드한 다음, 프로비전 패키지를 적용하기 위해 OS를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="04338-159">디바이스 암호화 확인</span><span class="sxs-lookup"><span data-stu-id="04338-159">Verify device encryption</span></span>

<span data-ttu-id="04338-160">암호화는 HoloLens 자동입니다.</span><span class="sxs-lookup"><span data-stu-id="04338-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="04338-161">디바이스 암호화 상태를 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="04338-162">HoloLens 설정   >  **시스템**  >  **정보로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="04338-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="04338-163">디바이스가 **암호화된** 경우 **BitLocker를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04338-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![BitLocker를 사용하도록 설정된 화면 정보](images/about-encryption.png)
