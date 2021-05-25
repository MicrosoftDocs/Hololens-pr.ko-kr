---
title: 인증서 관리자
description: HoloLens 2 혼합 현실 디바이스에서 인증서를 수동으로 설치, 관리 및 제거하는 방법을 알아봅니다.
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397454"
---
# <a name="certificate-manager"></a><span data-ttu-id="3709a-103">인증서 관리자</span><span class="sxs-lookup"><span data-stu-id="3709a-103">Certificate Manager</span></span>

- <span data-ttu-id="3709a-104">새 인증서 관리자를 통해 디바이스 보안 및 규정 준수를 위한 감사, 진단 및 유효성 검사 도구가 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="3709a-105">이 기능을 사용하면 상용 환경에서 대규모로 인증서를 배포, 문제 해결 및 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="3709a-106">Windows Holographic 버전 20H2에서는 HoloLens 2 설정 앱에 인증서 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="3709a-107">설정 **> 업데이트 & 보안 > 인증서로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="3709a-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="3709a-108">이 기능은 디바이스에서 인증서를 보고, 설치하고, 제거하는 간단하고 사용자에게 친숙한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="3709a-109">이제 새 인증서 관리자를 통해 관리자와 사용자가 감사, 진단 및 유효성 검사 도구를 개선하여 디바이스가 안전하고 규정을 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="3709a-110">**감사:** 인증서가 올바르게 배포되었는지 확인하거나 인증서가 적절하게 제거되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="3709a-111">**진단:** 문제가 발생하면 디바이스에 적절한 인증서가 있는지 확인하면 시간이 절약되고 문제 해결에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="3709a-112">**유효성 검사:** 인증서가 의도한 용도로 사용되고 작동하는지 확인하면 특히 상용 환경에서 상당한 시간을 절약한 후 더 큰 규모로 인증서를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="3709a-113">목록에서 특정 인증서를 빠르게 찾기 위해 이름, 저장 또는 만료 날짜를 기준으로 정렬하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="3709a-114">사용자는 인증서를 직접 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="3709a-115">개별 인증서 속성을 보려면 인증서를 선택하고 **정보** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="3709a-116">인증서 설치는 현재 .cer 및 .crt 파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="3709a-117">디바이스 소유자는 로컬 컴퓨터 및 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자에만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="3709a-118">사용자는 설정 UI에서 직접 설치된 인증서만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="3709a-119">다른 방법을 통해 인증서를 설치한 경우 동일한 메커니즘에 의해서도 인증서를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="3709a-120">인증서를 설치하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="3709a-121">PC에 HoloLens 2 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="3709a-122">설치 하려는 인증서 파일을 HoloLens 2의 한 위치에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="3709a-123">**설정 앱 > 업데이트 & 보안 > 인증서** 로 이동 하 고 인증서 설치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="3709a-124">**파일 가져오기** 를 클릭 하 고 인증서를 저장 한 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="3709a-125">**저장소 위치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="3709a-126">**인증서 저장소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="3709a-127">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-127">Click **Install**.</span></span>

<span data-ttu-id="3709a-128">이제 인증서가 장치에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="3709a-129">인증서를 제거 하려면:</span><span class="sxs-lookup"><span data-stu-id="3709a-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="3709a-130">인증서 관리자에서 MDM 배포 인증서를 볼 수 있지만 인증서 관리자에서는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="3709a-131">MDM을 통해 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="3709a-132">**설정 앱 > 업데이트 및 보안 > 인증서** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="3709a-133">검색 상자에서 이름으로 인증서를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="3709a-134">인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-134">Select the certificate.</span></span>
1. <span data-ttu-id="3709a-135">**제거** 클릭</span><span class="sxs-lookup"><span data-stu-id="3709a-135">Click **Remove**</span></span>
1. <span data-ttu-id="3709a-136">확인하라는 메시지가 표시되면 **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3709a-136">Select **Yes** when prompted for confirmation.</span></span>



![인증서의 설정 앱에서 인증서 뷰어](images/certificate-viewer-device.jpg)

![인증서 UI를 사용 하 여 설정에 인증서를 설치 하는 방법을 보여 주는 그림입니다.](images/certificate-device-install.jpg)
