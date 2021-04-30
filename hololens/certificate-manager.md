---
title: 인증서 관리자
description: HoloLens 2 mixed reality 장치에서 인증서를 수동으로 설치, 관리 및 제거 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309245"
---
# <a name="certificate-manager"></a><span data-ttu-id="f67e8-103">인증서 관리자</span><span class="sxs-lookup"><span data-stu-id="f67e8-103">Certificate Manager</span></span>

- <span data-ttu-id="f67e8-104">새 인증서 관리자를 통해 장치 보안 및 규정 준수에 대 한 감사, 진단 및 유효성 검사 도구가 개선 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="f67e8-105">이 기능을 사용 하면 상업적 환경에서 대규모로 인증서를 배포 하 고, 문제를 해결 하 고, 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="f67e8-106">Windows Holographic 버전 20H2에서는 HoloLens 2 설정 앱에서 인증서 관리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="f67e8-107">**설정 > 업데이트 & 보안 > 인증서** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="f67e8-108">이 기능은 장치에서 인증서를 보고 설치 하 고 제거 하는 간단 하 고 사용자에 게 친숙 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="f67e8-109">새 인증서 관리자를 사용 하면 관리자와 사용자가 향상 된 감사, 진단 및 유효성 검사 도구를 사용 하 여 장치가 안전 하 고 규정을 준수 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="f67e8-110">**감사:** 인증서가 올바르게 배포 되었는지 확인 하거나 적절 하 게 제거 되었는지 확인 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="f67e8-111">**진단:** 문제가 발생 하는 경우 장치에 적절 한 인증서가 있는지 확인 하면 시간이 절약 되 고 문제 해결에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="f67e8-112">**유효성 검사:** 인증서가 의도 된 용도를 제공 하 고 작동 하는지 확인 하면, 특히 상업적 환경에서 더 큰 규모로 인증서를 배포 하기 전에 상당한 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="f67e8-113">목록에서 특정 인증서를 빠르게 찾기 위해 이름, 매장 또는 만료 날짜별로 정렬 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="f67e8-114">사용자가 직접 인증서를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="f67e8-115">개별 인증서 속성을 보려면 인증서를 선택 하 고 **정보** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="f67e8-116">인증서 설치는 현재 .cer 및 .crt 파일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="f67e8-117">장치 소유자는 로컬 컴퓨터 및 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자 에게만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="f67e8-118">사용자는 설정 UI에서 직접 설치 된 인증서만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="f67e8-119">인증서가 다른 방법으로 설치 된 경우에도 동일한 메커니즘을 사용 하 여 인증서를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="f67e8-120">인증서를 설치 하려면:</span><span class="sxs-lookup"><span data-stu-id="f67e8-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="f67e8-121">HoloLens 2를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="f67e8-122">설치 하려는 인증서 파일을 HoloLens 2의 한 위치에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="f67e8-123">**설정 앱 > 업데이트 & 보안 > 인증서** 로 이동 하 고 인증서 설치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="f67e8-124">**파일 가져오기** 를 클릭 하 고 인증서를 저장 한 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="f67e8-125">**저장소 위치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="f67e8-126">**인증서 저장소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="f67e8-127">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-127">Click **Install**.</span></span>

<span data-ttu-id="f67e8-128">이제 인증서가 장치에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="f67e8-129">인증서를 제거 하려면:</span><span class="sxs-lookup"><span data-stu-id="f67e8-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="f67e8-130">**설정 앱 > 업데이트 및 보안 > 인증서** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="f67e8-131">검색 상자에서 이름으로 인증서를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="f67e8-132">인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-132">Select the certificate.</span></span>
1. <span data-ttu-id="f67e8-133">**제거** 클릭</span><span class="sxs-lookup"><span data-stu-id="f67e8-133">Click **Remove**</span></span>
1. <span data-ttu-id="f67e8-134">확인하라는 메시지가 표시되면 **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f67e8-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates 아래의 설정 앱에서 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용 하 여 설정에 인증서를 설치 하는 방법을 보여 주는 그림입니다.](images/certificate-device-install.jpg)
