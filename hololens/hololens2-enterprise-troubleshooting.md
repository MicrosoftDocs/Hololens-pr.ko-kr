---
title: HoloLens 2 구현 및 관리되는 장치 문제 해결
description: 엔터프라이즈 환경에서 HoloLens 2 장치 문제 해결
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: 문제 해결
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961502"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="fec8e-104">구현 및 관리되는 장치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="fec8e-105">이 문서에서는 HoloLens 2의 구현 및 관리와 관련하여 몇 가지 문제를 해결하거나 질문에 답변하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="fec8e-106">문제 해결 절차를 시작하기 전에 가능한 경우 장치의 배터리 용량이 **20~40%** 정도 충전되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="fec8e-107">전원 단추 아래에 있는 [배터리 표시등](hololens2-setup.md#lights-that-indicate-the-battery-level)으로 장치에 로그인하지 않고 배터리 용량을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="fec8e-108">EAP 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="fec8e-109">Wi-Fi 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="fec8e-110">네트워크 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="fec8e-111">이전에 설정된 HoloLens 장치에 로그인할 수 없음</span><span class="sxs-lookup"><span data-stu-id="fec8e-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="fec8e-112">Windows Holographic 21H1로 업데이트한 후 로그인할 수 없음</span><span class="sxs-lookup"><span data-stu-id="fec8e-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="fec8e-113">Autopilot 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="fec8e-114">관리되는 HoloLens 장치 FAQ</span><span class="sxs-lookup"><span data-stu-id="fec8e-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="fec8e-115">EAP 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="fec8e-116">Wi-Fi 프로필이 올바르게 설정되었는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="fec8e-117">EAP 유형이 올바르게 구성되어 있습니다. 일반 EAP 유형은 EAP-TLS(13), EAP-TTLS(21), PEAP(25)입니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="fec8e-118">Wi-Fi SSID 이름이 올바르고 HEX 문자열과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="fec8e-119">EAP-TLS의 경우 TrustedRootCA에는 서버의 신뢰할 수 있는 루트 CA 인증서의 SHA-1 해시가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="fec8e-120">Windows PC에서 "certutil.exe -dump cert_file_name" 명령이 인증서의 SHA-1 해시 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="fec8e-121">액세스 지점 또는 컨트롤러 또는 AAA 서버 로그의 네트워크 패킷 캡처를 수집하여 EAP 세션이 실패하는 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="fec8e-122">HoloLens에서 제공하는 EAP ID가 필요하지 않을 경우 Wi-Fi 프로필이나 클라이언트 인증서를 통해 ID가 올바르게 프로비전되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="fec8e-123">서버가 HoloLens 클라이언트 인증서를 거부하는 경우 필요한 클라이언트 인증서가 장치에 프로비전되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="fec8e-124">HoloLens가 서버 인증서를 거부하는 경우, 서버 루트 CA 인증서가 HoloLens에 프로비전되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="fec8e-125">엔터프라이즈 프로필이 Wi-Fi 프로비전 패키지를 통해 프로비전된 경우 Windows 10 PC에서 프로비전 패키지를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="fec8e-126">Windows 10 PC에서도 실패할 경우 Windows 클라이언트 802.1X 인증 문제 해결 가이드를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="fec8e-127">피드백 허브를 통해 피드백을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="fec8e-128">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="fec8e-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="fec8e-129">Wi-Fi 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="fec8e-130">HoloLens를 Wi-Fi 네트워크에 연결할 수 없는 경우 다음과 같은 작업을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="fec8e-131">Wi-Fi가 켜져 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="fec8e-132">확인하려면 시작 제스처를 사용하고 설정 > 네트워크 및 인터넷 > Wi-Fi를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="fec8e-133">Wi-Fi가 켜져 있으면 끈 다음 다시 켜보세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="fec8e-134">라우터 또는 액세스 지점에 좀 더 가깝게 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="fec8e-135">Wi-Fi 라우터를 다시 시작한 다음 HoloLens를 다시 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="fec8e-136">다시 연결해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-136">Try connecting again.</span></span>
4. <span data-ttu-id="fec8e-137">이러한 작업을 수행할 수 없는 경우 라우터가 최신 펌웨어를 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="fec8e-138">제조업체 웹 사이트에서 이 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="fec8e-139">장치에서 엔터프라이즈 또는 조직 계정에 로그인하면 IT 관리자가 정책을 구성하는 경우 MDM(모바일 장치 관리) 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="fec8e-140">네트워크 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-140">Network Troubleshooting</span></span>
<span data-ttu-id="fec8e-141">네트워크 문제로 인해 조직에서 HoloLens 2를 성공적으로 배포하고 사용하는 데 문제가 발생하는 경우 잘 알려진 두 가지 네트워크 진단 도구인 Fiddler와 Wireshark를 사용하여 문제를 검사, 진단 및 식별하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="fec8e-142">자세한 내용은 이 [블로그](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="fec8e-143">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="fec8e-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="fec8e-144">이전에 설정된 HoloLens 장치에 로그인할 수 없음</span><span class="sxs-lookup"><span data-stu-id="fec8e-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="fec8e-145">이전에 다른 사람 즉, 클라이언트나 이전 직원에 대해 장치를 설정했고 장치의 잠금을 해제하는 암호가 없는 경우 Intune을 사용하여 원격으로 장치를 [초기화](https://docs.microsoft.com/intune/remote-actions/devices-wipe)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="fec8e-146">그러면 장치가 자체 리플래시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="fec8e-147">장치를 초기화하는 경우 **Retain enrollment state and user account** 선택이 취소되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="fec8e-148">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="fec8e-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="fec8e-149">Windows Holographic 21H1로 업데이트한 후 로그인할 수 없음</span><span class="sxs-lookup"><span data-stu-id="fec8e-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="fec8e-150">증상</span><span class="sxs-lookup"><span data-stu-id="fec8e-150">Symptoms</span></span>
- <span data-ttu-id="fec8e-151">올바른 PIN을 입력한 후 PIN을 사용한 로그온이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="fec8e-152">웹 페이지에서 성공적으로 로그인한 후 웹 로그온 방법이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="fec8e-153">장치가 [Azure Portal](https://portal.azure.com/) -> Azure Active Directory ->장치에서 “Azure AD 조인됨”으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="fec8e-154">원인</span><span class="sxs-lookup"><span data-stu-id="fec8e-154">Cause</span></span>
<span data-ttu-id="fec8e-155">영향을 받는 장치가 Azure AD 테넌트에서 삭제되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="fec8e-156">예를 들어, 다음과 같은 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-156">For example, this may happen because:</span></span>

- <span data-ttu-id="fec8e-157">관리자나 사용자가 Azure Portal에서 또는 PowerShell을 사용하여 장치를 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="fec8e-158">비활성으로 인해 Azure AD 테넌트에서 장치를 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="fec8e-159">효율적인 관리 환경을 위해 일반적으로 IT 관리자는 [Azure AD 테넌트에서 오래된 비활성 장치를 제거](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="fec8e-160">Azure AD 테넌트가 삭제된 후에 영향을 받는 장치가 Azure AD 테넌트에 다시 연결하려고 하면 Azure AD로 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="fec8e-161">PIN을 통한 캐시된 로그온으로 사용자가 계속 로그온할 수 있으므로 이 효과가 장치 사용자에게 표시되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="fec8e-162">완화 방법</span><span class="sxs-lookup"><span data-stu-id="fec8e-162">Mitigation</span></span>
<span data-ttu-id="fec8e-163">삭제된 HoloLens 장치를 Azure AD에 다시 추가할 수 있는 방법은 현재 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="fec8e-164">영향을 받는 장치는 [장치 리플래시](hololens-recovery.md#clean-reflash-the-device)에 대한 지침에 따라 클린 리플래시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="fec8e-165">Autopilot 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="fec8e-166">다음 문서는 자세한 정보를 알아보고 Autopilot 문제를 해결하는 데 유용한 리소스가 될 수 있지만, 이러한 문서가 Windows 10 데스크톱을 기반으로 하며 모든 정보가 HoloLens에 적용되는 것은 아니라는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="fec8e-167">Windows Autopilot - 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="fec8e-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="fec8e-168">Microsoft Intune에서 iOS 디바이스 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fec8e-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="fec8e-169">Windows Autopilot - 정책 충돌</span><span class="sxs-lookup"><span data-stu-id="fec8e-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="fec8e-170">관리되는 HoloLens 장치 FAQ</span><span class="sxs-lookup"><span data-stu-id="fec8e-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="fec8e-171">SCCM(System Center Configuration Manager)을 사용하여 HoloLens 장치를 관리할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fec8e-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="fec8e-172">아니요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-172">No.</span></span> <span data-ttu-id="fec8e-173">HoloLens 장치를 관리하려면 MDM 시스템을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="fec8e-174">AD DS(Active Directory Domain Services)를 사용하여 HoloLens 사용자 계정을 관리할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fec8e-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="fec8e-175">아니요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-175">No.</span></span> <span data-ttu-id="fec8e-176">HoloLens 장치에 대한 사용자 계정을 관리하려면 Azure AD(Azure Active Directory)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="fec8e-177">HoloLens는 ADCS(자동화된 데이터 캡처 시스템) 자동 등록이 가능한가요?</span><span class="sxs-lookup"><span data-stu-id="fec8e-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="fec8e-178">아니요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="fec8e-179">HoloLens는 통합 Windows 인증에 참여할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fec8e-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="fec8e-180">아니요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="fec8e-181">HoloLens는 브랜딩을 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="fec8e-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="fec8e-182">아니요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-182">No.</span></span> <span data-ttu-id="fec8e-183">하지만 다음 접근 방식 중 하나를 사용하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="fec8e-184">사용자 지정 앱을 만든 다음 [키오스크 모드를 사용하도록 설정](hololens-kiosk.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="fec8e-185">사용자 지정 앱은 브랜딩이 있을 수 있고 다른 앱(예: Remote Assist)을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="fec8e-186">Azure AD의 모든 사용자 프로필 사진을 회사 로고로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="fec8e-187">그러나 이 방법은 모든 시나리오에 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="fec8e-188">HoloLens 2가 제공하는 로깅 기능은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="fec8e-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="fec8e-189">로깅은 개발 또는 문제 해결 시나리오에서 캡처할 수 있는 추적 또는 장치가 Microsoft 서버로 전송하는 원격 분석으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec8e-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="fec8e-190">HoloLens 장치 보안에 대한 질문</span><span class="sxs-lookup"><span data-stu-id="fec8e-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="fec8e-191">[HoloLens 2 보안 정보](security-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="fec8e-192">HoloLens 1세대 장치에 대해서는 [이 FAQ](hololens1-faq-security.md)를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="fec8e-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="fec8e-193">목록으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="fec8e-193">Back to list</span></span>](#list)
