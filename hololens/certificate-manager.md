---
title: 인증서 관리자
description: HoloLens 2에서 수동으로 인증서를 관리 하는 방법에 대해 알아보세요.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163226"
---
# <span data-ttu-id="2d07e-103">인증서 관리자</span><span class="sxs-lookup"><span data-stu-id="2d07e-103">Certificate Manager</span></span>

- <span data-ttu-id="2d07e-104">새로운 인증서 관리자를 통해 장치 보안 및 준수에 대 한 감사, 진단, 유효성 검사 도구를 개선 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="2d07e-105">이 접근 권한 값을 통해 상업용 환경에서 규모의 인증서를 배포 하 고, 문제를 해결 하 고, 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="2d07e-106">Windows 홀로그램 버전 20H2에서 HoloLens 2 설정 앱에서 인증서 관리자를 추가 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="2d07e-107">**& 보안 > 인증서를 업데이트 > 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="2d07e-108">이 기능을 사용 하면 간단 하 고 사용자에 게 장치에서 인증서를 보고, 설치 하 고, 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="2d07e-109">새 인증서 관리자를 통해 관리자와 사용자는 향상 된 감사, 진단 및 유효성 검사 도구를 사용 하 여 디바이스를 안전 하 고 준수 하도록 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="2d07e-110">**감사:** 인증서가 올바르게 배포 되었는지 확인 하거나 적절 하 게 제거 되었는지 확인 하는 기능.</span><span class="sxs-lookup"><span data-stu-id="2d07e-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="2d07e-111">**진단:** 문제가 발생 하면 장치에 적절 한 인증서가 있는지 확인 하 여 시간을 절약 하 고 문제를 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="2d07e-112">**유효성 검사:** 인증서가 의도 한 목적을 제공 하 고 작동 하는지 확인 하는 것은 중요 한 시간을 크게 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="2d07e-113">목록에서 특정 인증서를 빠르게 찾으려면 이름, 저장 또는 만료 날짜별로 정렬 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="2d07e-114">사용자가 직접 인증서를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="2d07e-115">개별 인증서 속성을 보려면 인증서를 선택 하 고 **정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="2d07e-116">인증서 설치는 현재 .cer 및 .crt 파일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="2d07e-117">장치 소유자는 로컬 컴퓨터와 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자 에게만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="2d07e-118">사용자는 설정 UI에서 직접 설치한 인증서만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="2d07e-119">다른 수단을 통해 인증서를 설치한 경우 같은 메커니즘을 통해서도이를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="2d07e-120">인증서를 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="2d07e-121">HoloLens 2를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="2d07e-122">설치할 인증서 파일을 HoloLens 2의 위치에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="2d07e-123">설정 앱으로 이동 하 여 **& 보안 > 인증서를 업데이트 >** 하 고 인증서 설치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="2d07e-124">**파일 가져오기를** 클릭 하 고 인증서를 저장 한 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="2d07e-125">**스토어 위치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="2d07e-126">**인증서 저장소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="2d07e-127">**설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-127">Click **Install**.</span></span>

<span data-ttu-id="2d07e-128">이제 인증서가 장치에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="2d07e-129">인증서를 제거 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="2d07e-130">**설정 앱 > 업데이트 및 보안 > 인증서**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="2d07e-131">검색 상자에서 이름으로 인증서를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="2d07e-132">인증서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-132">Select the certificate.</span></span>
1. <span data-ttu-id="2d07e-133">**제거** 클릭</span><span class="sxs-lookup"><span data-stu-id="2d07e-133">Click **Remove**</span></span>
1. <span data-ttu-id="2d07e-134">확인 메시지가 표시 되 면 **예** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d07e-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates 아래의 설정 앱에서 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용 하 여 설정에 인증서를 설치 하는 방법을 보여 주는 그림](images/certificate-device-install.jpg)
