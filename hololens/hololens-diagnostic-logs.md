---
title: HoloLens 장치에서 진단 정보 수집 및 사용
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b3071c2c66bf1e9c07ba2481b3e22a0d5125bc6d
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919139"
---
# <span data-ttu-id="54f4b-102">HoloLens 장치에서 진단 정보 수집 및 사용</span><span class="sxs-lookup"><span data-stu-id="54f4b-102">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="54f4b-103">HoloLens 사용자와 관리자는 다음 네 가지 방법 중 하나를 선택 하 여 HoloLens의 진단 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-103">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="54f4b-104">피드백 허브 앱</span><span class="sxs-lookup"><span data-stu-id="54f4b-104">Feedback Hub app</span></span>
- <span data-ttu-id="54f4b-105">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="54f4b-105">DiagnosticLog CSP</span></span>
- <span data-ttu-id="54f4b-106">설정 앱</span><span class="sxs-lookup"><span data-stu-id="54f4b-106">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="54f4b-107">장치 진단 로그에는 일반 작업 중 사용자가 시작 하는 프로세스 또는 응용 프로그램에 대 한 정보 등 PII (개인 식별 가능 정보)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-107">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="54f4b-108">여러 사용자가 HoloLens 장치를 공유 하는 경우 (예를 들어 사용자가 다른 Microsoft Azure Active Directory (AAD) 계정을 사용 하 여 동일한 장치에 로그인 하는 경우) 진단 로그에 여러 사용자에 게 적용 되는 PII 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-108">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="54f4b-109">자세한 내용은 [Microsoft 개인 정보 취급](https://privacy.microsoft.com/privacystatement)방침을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="54f4b-109">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="54f4b-110">다음 표에서는 세 가지 컬렉션 메서드를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-110">The following table compares the three collection methods.</span></span> <span data-ttu-id="54f4b-111">메서드 이름은 표 다음에 나오는 섹션의 자세한 정보에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-111">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="54f4b-112">메서드</span><span class="sxs-lookup"><span data-stu-id="54f4b-112">Method</span></span> |<span data-ttu-id="54f4b-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="54f4b-113">Prerequisites</span></span> |<span data-ttu-id="54f4b-114">데이터 위치</span><span class="sxs-lookup"><span data-stu-id="54f4b-114">Data locations</span></span> |<span data-ttu-id="54f4b-115">데이터 액세스 및 사용</span><span class="sxs-lookup"><span data-stu-id="54f4b-115">Data access and use</span></span> |<span data-ttu-id="54f4b-116">데이터 보존</span><span class="sxs-lookup"><span data-stu-id="54f4b-116">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="54f4b-117">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="54f4b-117">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="54f4b-118">네트워크 및 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="54f4b-118">Network and internet connection</span></span><br /><br /><span data-ttu-id="54f4b-119">피드백 허브 앱</span><span class="sxs-lookup"><span data-stu-id="54f4b-119">Feedback Hub app</span></span><br /><br /><span data-ttu-id="54f4b-120">Microsoft 클라우드에 파일을 업로드할 수 있는 권한</span><span class="sxs-lookup"><span data-stu-id="54f4b-120">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="54f4b-121">Microsoft 클라우드</span><span class="sxs-lookup"><span data-stu-id="54f4b-121">Microsoft cloud</span></span><br /><br /><span data-ttu-id="54f4b-122">HoloLens 장치 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="54f4b-122">HoloLens device (optional)</span></span> |<span data-ttu-id="54f4b-123">사용자가 도움을 요청 하 고, 사용 약관에 동의 하 고, 데이터를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-123">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="54f4b-124">Microsoft 직원 들이 사용 약관에 일치 하는 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="54f4b-124">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="54f4b-125">클라우드의 데이터는 NGP (차세대 개인 정보 취급 방침)에 의해 정의 된 기간 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-125">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="54f4b-126">그러면 데이터가 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-126">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="54f4b-127">장치 **소유자** 또는 **관리자** 권한이 있는 사용자가 언제 든 지 장치의 데이터를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-127">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="54f4b-128">설정 문제 해결사</span><span class="sxs-lookup"><span data-stu-id="54f4b-128">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="54f4b-129">설정 앱</span><span class="sxs-lookup"><span data-stu-id="54f4b-129">Settings app</span></span> |<span data-ttu-id="54f4b-130">HoloLens 장치</span><span class="sxs-lookup"><span data-stu-id="54f4b-130">HoloLens device</span></span><br /><br /><span data-ttu-id="54f4b-131">연결 된 컴퓨터 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="54f4b-131">Connected computer (optional)</span></span> |<span data-ttu-id="54f4b-132">사용자가 데이터를 저장 하 고 사용자가 특정 데이터를 다른 사용자와 공유 하지 않는 경우에만 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-132">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="54f4b-133">데이터는 사용자가 삭제할 때까지 유지 됩니다. \*</span><span class="sxs-lookup"><span data-stu-id="54f4b-133">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="54f4b-134">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="54f4b-134">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="54f4b-135">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="54f4b-135">Network connection</span></span><br /><br /><span data-ttu-id="54f4b-136">DiagnosticLog CSP를 지 원하는 MDM 환경</span><span class="sxs-lookup"><span data-stu-id="54f4b-136">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="54f4b-137">관리자가 저장소 위치를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-137">Administrator configures storage locations</span></span> |<span data-ttu-id="54f4b-138">관리 환경에서는 사용자가 데이터에 대 한 관리자 액세스 권한을 암시적으로 동의.</span><span class="sxs-lookup"><span data-stu-id="54f4b-138">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="54f4b-139">관리자가 액세스 역할 및 사용 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-139">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="54f4b-140">관리자가 보존 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-140">Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="54f4b-141">오프 라인 진단</span><span class="sxs-lookup"><span data-stu-id="54f4b-141">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="54f4b-142">장치 구성:</span><span class="sxs-lookup"><span data-stu-id="54f4b-142">Device configuration:</span></span><ul><li><span data-ttu-id="54f4b-143">전원을 켜고 컴퓨터에 연결</span><span class="sxs-lookup"><span data-stu-id="54f4b-143">Powered on and connected to computer</span></span></li><li><span data-ttu-id="54f4b-144">전원 및 볼륨 단추가 작동</span><span class="sxs-lookup"><span data-stu-id="54f4b-144">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="54f4b-145">HoloLens 장치</span><span class="sxs-lookup"><span data-stu-id="54f4b-145">HoloLens device</span></span><br /><br /><span data-ttu-id="54f4b-146">연결 된 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="54f4b-146">Connected computer</span></span> |<span data-ttu-id="54f4b-147">사용자가 데이터를 저장 하 고 사용자가 특정 데이터를 다른 사용자와 공유 하지 않는 경우에만 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-147">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="54f4b-148">데이터는 사용자가 삭제할 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-148">The data is retained until the user deletes it.</span></span> | 


-   <span data-ttu-id="54f4b-149">최종 사용자는 다른 사람과 로그를 공유할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-149">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="54f4b-150">이러한 파일은 고객 서비스 및 지원에 문의 하는 데 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-150">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="54f4b-151">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="54f4b-151">Feedback Hub</span></span>

<span data-ttu-id="54f4b-152">HoloLens 사용자는 Microsoft 피드백 허브 데스크톱 앱을 사용 하 여 진단 정보를 Microsoft 지원에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-152">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="54f4b-153">자세한 내용과 자세한 지침은 [사용자 의견 제공](hololens-feedback.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54f4b-153">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="54f4b-154">**상용 또는 엔터프라이즈 사용자:** 피드백 허브 앱을 사용 하 여 MDM, 프로비저닝 또는 기타 장치 관리 측면과 관련 된 문제를 보고 하는 경우 앱 범주를 **엔터프라이즈 관리**  >  **장치 범주로**변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-154">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="54f4b-155">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="54f4b-155">Prerequisites</span></span>

- <span data-ttu-id="54f4b-156">디바이스가 네트워크에 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-156">The device is connected to a network.</span></span>
- <span data-ttu-id="54f4b-157">사용자의 데스크톱 컴퓨터에서 피드백 허브 앱을 사용할 수 있으며 사용자가 Microsoft 클라우드에 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-157">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="54f4b-158">데이터 위치, 액세스 및 보존</span><span class="sxs-lookup"><span data-stu-id="54f4b-158">Data locations, access, and retention</span></span>

<span data-ttu-id="54f4b-159">피드백 허브의 사용 약관에 동의 하면 사용자는 해당 계약에 정의 된 대로 데이터의 저장 및 사용량을 명시적으로 동의.</span><span class="sxs-lookup"><span data-stu-id="54f4b-159">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="54f4b-160">피드백 허브는 사용자가 진단 정보를 저장할 수 있는 두 가지 장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-160">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="54f4b-161">**Microsoft 클라우드**.</span><span class="sxs-lookup"><span data-stu-id="54f4b-161">**The Microsoft cloud**.</span></span> <span data-ttu-id="54f4b-162">피드백 허브 앱을 사용 하 여 사용자가 업로드 하는 데이터는 NGP (차세대 개인 정보) 요구 사항과 일치 하는 일 수에 맞게 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-162">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="54f4b-163">Microsoft 직원이이 기간 동안 해당 정보에 액세스 하는 데 NGP 준수 뷰어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-163">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="54f4b-164">이러한 요구 사항은 모든 피드백 허브 범주의 데이터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-164">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="54f4b-165">**HoloLens 장치**입니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-165">**The HoloLens device**.</span></span> <span data-ttu-id="54f4b-166">피드백 허브에서 보고서를 작성 하는 동안 사용자는 **피드백을 제공할 때 생성 되는 진단 및 첨부 파일의 로컬 복사본 저장**을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-166">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="54f4b-167">사용자가이 옵션을 선택 하면 피드백 허브에 HoloLens 장치에 대 한 진단 정보 복사본이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-167">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="54f4b-168">이 정보는 사용자가 액세스할 수 있으며 (또는 해당 계정을 사용 하는 모든 사용자가 HoloLens에 로그인 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="54f4b-168">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="54f4b-169">이 정보를 삭제 하려면 사용자가 장치에 대 한 **디바이스 소유자** 또는 **관리자** 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-169">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="54f4b-170">적절 한 사용 권한이 있는 사용자는 피드백 허브에 로그인 하 고, **설정**  >  **보기 진단 로그**를 선택 하 고, 정보를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-170">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="54f4b-171">설정 문제 해결사</span><span class="sxs-lookup"><span data-stu-id="54f4b-171">Settings Troubleshooter</span></span>

<span data-ttu-id="54f4b-172">HoloLens 사용자는 장치의 설정 앱을 사용 하 여 문제를 해결 하 고 진단 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-172">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="54f4b-173">이렇게 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="54f4b-173">To do this, follow these steps:</span></span>

1. <span data-ttu-id="54f4b-174">설정 앱을 열고 **& 보안**  >  **문제 해결** 페이지 업데이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-174">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="54f4b-175">적절 한 영역을 선택 하 고 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-175">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="54f4b-176">문제를 재현해 보세요.</span><span class="sxs-lookup"><span data-stu-id="54f4b-176">Reproduce the issue.</span></span>
1. <span data-ttu-id="54f4b-177">문제를 재현 한 후 설정으로 돌아간 다음 **중지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-177">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="54f4b-178">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="54f4b-178">Prerequisites</span></span>

- <span data-ttu-id="54f4b-179">설정 앱이 디바이스에 설치 되어 있으며 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-179">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="54f4b-180">데이터 위치, 액세스 및 보존</span><span class="sxs-lookup"><span data-stu-id="54f4b-180">Data locations, access, and retention</span></span>

<span data-ttu-id="54f4b-181">사용자가 데이터 수집을 시작 하기 때문에 사용자는 암시적으로 진단 정보 저장소에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-181">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="54f4b-182">사용자 또는 사용자가 데이터를 공유 하는 모든 사람이 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-182">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="54f4b-183">진단 정보는 장치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-183">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="54f4b-184">장치가 사용자의 컴퓨터에 연결 되어 있는 경우 해당 정보는 컴퓨터의 다음 파일에도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-184">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="54f4b-185">이 PC\\ \<*HoloLens device name*> \\Internal Storage\\document\ \ 추적 \<*ddmmyyhhmmss*> . .etl</span><span class="sxs-lookup"><span data-stu-id="54f4b-185">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="54f4b-186">이 파일 경로와 이름에는 \<*HoloLens device name*> HoloLens 장치의 이름을 나타내고 \<*ddmmyyhhmmss*> 파일을 만든 날짜와 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-186">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="54f4b-187">진단 정보는 사용자가 삭제할 때까지 해당 위치에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-187">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="54f4b-188">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="54f4b-188">DiagnosticLog CSP</span></span>

<span data-ttu-id="54f4b-189">MDM (모바일 디바이스 관리) 환경에서 IT 관리자는 [DiagnosticLog 구성 서비스 공급자 (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 를 사용 하 여 등록 된 HoloLens 장치에서 진단 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-189">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="54f4b-190">IT 관리자는 등록 된 디바이스에서 로그를 수집 하도록 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-190">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="54f4b-191">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="54f4b-191">Prerequisites</span></span>

- <span data-ttu-id="54f4b-192">디바이스가 네트워크에 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-192">The device is connected to a network.</span></span>
- <span data-ttu-id="54f4b-193">장치가 DiagnosticLog CSP를 지 원하는 MDM 환경에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-193">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="54f4b-194">데이터 위치, 액세스 및 보존</span><span class="sxs-lookup"><span data-stu-id="54f4b-194">Data locations, access, and retention</span></span>

<span data-ttu-id="54f4b-195">장치가 관리 되는 환경의 일부 이므로 사용자는 암시적으로 진단 정보에 대 한 관리 액세스 권한을 동의.</span><span class="sxs-lookup"><span data-stu-id="54f4b-195">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="54f4b-196">IT 관리자는 DiagnosticLog CSP를 사용 하 여 다음을 제어 하는 정책을 포함 하 여 데이터 저장소, 보존 및 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-196">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="54f4b-197">진단 정보를 저장 하는 클라우드 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-197">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="54f4b-198">진단 정보의 보존 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-198">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="54f4b-199">진단 정보에 대 한 액세스를 제어 하는 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-199">Permissions that control access to the diagnostic information.</span></span>

## <span data-ttu-id="54f4b-200">오프 라인 진단</span><span class="sxs-lookup"><span data-stu-id="54f4b-200">Offline diagnostics</span></span>
<span data-ttu-id="54f4b-201">장치에서 피드백 허브 또는 설정 문제 해결사를 통해 진단 유틸리티를 수집할 수 없는 경우에는 진단을 수동으로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-201">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="54f4b-202">이 기능이 필요한 한 가지 시나리오는 장치가 Wi-fi에 연결할 수 없는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-202">One scenario where this is necessary is when the device cannot connect to Wi-Fi.</span></span> <span data-ttu-id="54f4b-203">진단 유틸리티는 Microsoft 지원 엔지니어가 문제를 격리 하는 데 도움이 되는 장치에서 크래시 덤프와 로그를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-203">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="54f4b-204">이는 장치가 USB 케이블로 PC에 연결한 후 파일 탐색기에 표시 되는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-204">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span> 


> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="54f4b-205">진단 유틸리티를 수집 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="54f4b-205">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="54f4b-206">USB 케이블을 사용 하 여 장치를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-206">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="54f4b-207">PC의 파일 탐색기에서 **'이 PC \<hololens-device> \ 내부 저장소 '** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-207">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="54f4b-208">**내부 저장소** 폴더가 표시 되지 않으면 사용자가 로그인 할 때까지 장치가 대기 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-208">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="54f4b-209">전원 단추를 10 초 동안 눌러 장치를 로그인 하거나 전원을 껐다가 켭니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-209">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="54f4b-210">바로 **전원 + 볼륨 아래로** 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-210">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="54f4b-211">장치가 zip 보관 파일을 준비 하는 데 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-211">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="54f4b-212">(HololensDiagnostics 이라는 임시 파일은 장치가 zip 보관 함을 생성 하는 동안 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-212">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="54f4b-213">해당 파일에 액세스 하거나 저장 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="54f4b-213">Do not access or save that file.</span></span> <span data-ttu-id="54f4b-214">프로세스가 완료 되 면 zip 보관 함으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-214">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="54f4b-215">파일 탐색기를 새로 고치고 **' \Documents '** 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-215">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="54f4b-216">진단 ZIP 파일을 복사 하 여 Microsoft 지원 팀과 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-216">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

<span data-ttu-id="54f4b-217">일부 진단 ZIP 파일에는 개인 식별 가능 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f4b-217">Note, some of the diagnostics ZIP files may contain personally identifiable information.</span></span>

