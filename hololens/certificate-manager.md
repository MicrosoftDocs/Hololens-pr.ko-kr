---
title: 인증서 관리자
description: HoloLens 2 혼합 현실 장치에서 인증서를 수동으로 설치, 관리 및 제거하는 방법을 학습합니다.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283689"
---
# <span data-ttu-id="269ae-103">인증서 관리자</span><span class="sxs-lookup"><span data-stu-id="269ae-103">Certificate Manager</span></span>

- <span data-ttu-id="269ae-104">새 인증서 관리자를 통해 장치 보안 및 규정 준수를 위한 감사, 진단 및 유효성 검사 도구가 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="269ae-105">이 기능을 사용하면 상업적 환경에서 인증서를 대규모로 배포, 문제 해결 및 유효성 검사를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="269ae-106">Windows Holographic 버전 20H2에서는 HoloLens 2 설정 앱에 인증서 관리자를 추가하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="269ae-107">Go to **Settings > Update & Security > Certificates.**</span><span class="sxs-lookup"><span data-stu-id="269ae-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="269ae-108">이 기능은 장치에서 인증서를 보고 설치하고 제거하는 간단하고 친숙한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="269ae-109">이제 관리자와 사용자는 새로운 인증서 관리자를 통해 감사, 진단 및 유효성 검사 도구를 개선하여 장치가 안전하고 규정을 준수하는지 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="269ae-110">**감사:** 인증서가 올바르게 배포되어 있는지 확인하거나 인증서가 적절히 제거된지 확인하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="269ae-111">**진단:** 문제가 발생하면 장치에 적절한 인증서가 존재하는지 확인하면 시간이 절약되어 문제 해결에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="269ae-112">**유효성 검사:** 인증서가 의도된 용도에 작동하고 있는지 확인하면 특히 대규모로 인증서를 배포하기 전에 상업적 환경에서 상당한 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="269ae-113">목록에서 특정 인증서를 빠르게 찾기 위해 이름, 저장소 또는 만료 날짜별로 정렬할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="269ae-114">사용자는 인증서를 직접 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="269ae-115">개별 인증서 속성을 보려면 인증서를 선택하고 정보를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="269ae-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="269ae-116">인증서 설치는 현재 .cer 및 .crt 파일을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="269ae-117">장치 소유자는 로컬 컴퓨터 및 현재 사용자에 인증서를 설치할 수 있습니다.  다른 모든 사용자는 현재 사용자에만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="269ae-118">사용자는 설정 UI에서 직접 설치된 인증서만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="269ae-119">다른 수단을 통해 인증서를 설치한 경우 동일한 메커니즘을 통해 인증서도 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="269ae-120">인증서를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="269ae-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="269ae-121">HoloLens 2를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="269ae-122">설치하려는 인증서 파일을 HoloLens 2의 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="269ae-123">Settings **App > Update & Security > 인증서로**이동한 다음 인증서 설치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="269ae-124">파일 **가져오기를** 클릭하고 인증서를 저장한 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="269ae-125">스토어 **위치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="269ae-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="269ae-126">인증서 **저장소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="269ae-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="269ae-127">**설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-127">Click **Install**.</span></span>

<span data-ttu-id="269ae-128">이제 인증서가 장치에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="269ae-129">인증서를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="269ae-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="269ae-130">설정 앱 업데이트 및 > 및 보안 > **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="269ae-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="269ae-131">검색 상자에서 이름으로 인증서를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="269ae-132">인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-132">Select the certificate.</span></span>
1. <span data-ttu-id="269ae-133">제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="269ae-133">Click **Remove**</span></span>
1. <span data-ttu-id="269ae-134">확인 **메시지가** 표시될 때 예를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="269ae-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates 아래 설정 앱의 인증서 뷰어](images/certificate-viewer-device.jpg)

![설정에서 인증서 UI를 사용하여 인증서를 설치하는 방법을 보여주는 그림입니다.](images/certificate-device-install.jpg)
