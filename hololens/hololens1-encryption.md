---
title: HoloLens BitLocker 암호화
description: HoloLens에 저장된 파일을 보호하기 위해 Bitlocker 디바이스 암호화를 사용하도록 설정
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
ms.openlocfilehash: 5ab35f0804c6a906cb0bb262211e8ae5ab017459
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865778"
---
# <span data-ttu-id="fb783-103">HoloLens (첫번째 Gen) BitLocker 암호화</span><span class="sxs-lookup"><span data-stu-id="fb783-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="fb783-104">HoloLens (첫번째 gen) 및 HoloLens 2 모두 BitLocker를 사용 하 여 장치 암호화를 지원 하지만 HoloLens 2에서는 항상 BitLocker를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="fb783-105">이 문서는 HoloLens에서 BitLocker를 사용 하 고 관리 하는 데 도움이 됩니다 (1 gen).</span><span class="sxs-lookup"><span data-stu-id="fb783-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="fb783-106">HoloLens (첫번째 gen)에서 BitLocker 장치 암호화를 수동으로 사용 하거나 MDM (모바일 디바이스 관리)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="fb783-107">파일 및 HoloLens에 저장 된 정보를 보호 하기 위해 [BitLocker 장치 암호화](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) 를 사용 하도록 설정 하려면 다음 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="fb783-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="fb783-108">장치 암호화는 CSP (BitLocker 구성 서비스 공급자)의 e 0 [Methodbydrivetype 메서드 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 에 해당 하는 aes-ccmp 128 암호화 메서드를 사용 하 여 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="fb783-109">올바른 암호화 키 (예: 암호)를 사용 하는 사용자는 해독 하거나 데이터 복구를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <span data-ttu-id="fb783-110">MDM을 사용하여 디바이스 암호화를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fb783-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="fb783-111">MDM (모바일 디바이스 관리) 공급자를 사용 하 여 장치 암호화가 필요한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="fb783-112">사용할 정책은 정책 CSP의 [Security/RequireDeviceEncryption 설정](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 입니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="fb783-113">Microsoft Intune을 사용 하 여 장치 암호화를 사용 하도록 설정 하는 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fb783-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="fb783-114">다른 MDM 도구의 경우 MDM 공급자의 설명서의 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb783-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="fb783-115">MDM 공급자가 장치 암호화를 위해 사용자 지정 URI를 요구 하는 경우 다음 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="fb783-116">**이름**: 사용자가 선택한 이름</span><span class="sxs-lookup"><span data-stu-id="fb783-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="fb783-117">**설명**: 선택 사항</span><span class="sxs-lookup"><span data-stu-id="fb783-117">**Description**: optional</span></span>
- <span data-ttu-id="fb783-118">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="fb783-118">**OMA-URI**:</span></span> `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- <span data-ttu-id="fb783-119">**데이터 형식**: 정수</span><span class="sxs-lookup"><span data-stu-id="fb783-119">**Data type**: integer</span></span>
- <span data-ttu-id="fb783-120">**값**:</span><span class="sxs-lookup"><span data-stu-id="fb783-120">**Value**:</span></span> `1`

## <span data-ttu-id="fb783-121">프로비저닝 패키지를 사용하여 디바이스 암호화를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fb783-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="fb783-122">프로비저닝 패키지는 지정한 구성을 장치에 적용하는 Windows 구성 디자이너 도구에서 생성된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <span data-ttu-id="fb783-123">Windows 홀로그램 edition을 업그레이드 하 고 암호화를 사용 하는 프로비저닝 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="fb783-124">HoloLens용 프로비저닝 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="fb783-125">**런타임 설정** > **정책** > **보안**으로 이동하여 **RequireDeviceEncryption**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![디바이스 암호화 설정을 예로 구성 필요](images/device-encryption.png)

1. <span data-ttu-id="fb783-127">상업용 제품군을 구입할 때 제공 된 XML 라이선스 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="fb783-128">Commercial Suite를 구입했을 때 받은 XML 라이선스 파일을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fb783-129">[프로비저닝 패키지의 추가 설정](hololens-provisioning.md)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="fb783-130">**파일** 메뉴에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="fb783-131">프로젝트 파일에 중요 한 정보가 포함 될 수 있음을 설명 하는 경고를 읽고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fb783-132">배포 패키지를 빌드할 때 프로젝트 파일과 프로비저닝 패키지 (ppkg) 파일에 중요 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="fb783-133">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="fb783-134">프로젝트 파일을 안전한 위치에 저장 하 고 더 이상 필요 하지 않을 경우 프로젝트 파일을 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="fb783-135">**내보내기** 메뉴에서 **프로비저닝 패키지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="fb783-136">**소유자**를 **IT 관리자**로 변경합니다. 이렇게 하면 이 프로비저닝 패키지의 우선 순위가 다른 소스에서 이 장치에 적용된 프로비저닝 패키지보다 더 높게 설정됩니다. 그런 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="fb783-137">**패키지 버전**에 대한 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fb783-138">기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="fb783-139">**프로비저닝 패키지에 대한 보안 정보 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="fb783-140">**다음**을 클릭하여 빌드가 끝난 프로비저닝 패키지를 저장할 출력 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="fb783-141">기본적으로 Windows ICD에서는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="fb783-142">필요한 경우 찾아보기를 클릭하여 기본 출력 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="fb783-143">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-143">Click **Next**.</span></span>
1. <span data-ttu-id="fb783-144">패키지 빌드를 시작하려면 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="fb783-145">빌드 페이지에서 프로젝트 정보가 표시되며 진행률 표시줄은 빌드 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="fb783-146">빌드가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-146">When the build completes, click **Finish**.</span></span>

### <span data-ttu-id="fb783-147">HoloLens에 프로비저닝 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="fb783-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="fb783-148">USB를 통해 PC에 장치를 연결하고 시작하되 초기 설정 환경의 **맞춤** 페이지(파란색 상자가 있는 첫 번째 페이지)까지 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="fb783-149">**볼륨 작게** 단추 및 **전원** 단추를 동시에 잠시 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="fb783-150">HoloLens는 PC의 파일 탐색기에서 장치로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="fb783-151">파일 탐색기에서 프로비저닝 패키지(.ppkg)를 장치 저장소로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="fb783-152">**맞춤** 페이지에 있는 동안 다시 **볼륨 작게** 단추 및 **전원** 단추를 동시에 잠시 누르고 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="fb783-153">장치에서 사용자에게 패키지를 신뢰할 수 있고 이를 적용할 것인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="fb783-154">패키지를 신뢰한다고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="fb783-155">패키지가 성공적으로 적용되었는지 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="fb783-156">실패한 경우 패키지 문제를 해결하고 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="fb783-157">성공한 경우 디바이스 설정을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="fb783-158">2016년 8월 이전에 구입한 장치인 경우 Microsoft 계정으로 장치에 로그인하여 최신 OS 업데이트를 다운로드한 다음 OS를 재설정하고 프로비저닝 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <span data-ttu-id="fb783-159">장치 암호화 검증</span><span class="sxs-lookup"><span data-stu-id="fb783-159">Verify device encryption</span></span>

<span data-ttu-id="fb783-160">HoloLens에서 암호화는 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="fb783-161">디바이스 암호화 상태를 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="fb783-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="fb783-162">HoloLens에서 **설정** > **시스템** > **정보**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="fb783-163">장치가 암호화 되어 있으면 **BitLocker** 를 **사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb783-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![BitLocker 사용 가능으로 표시 된 화면 정보](images/about-encryption.png)
