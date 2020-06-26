---
ms.openlocfilehash: bc66462291f4b1959fe1080ab33849c935218ebd
ms.sourcegitcommit: 537dd9ad3826ae7151e47d646b6315b89942173d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2020
ms.locfileid: "10794792"
---
<!-- BEGIN MICROSOFT SECURITY.MD V0.0.5 BLOCK -->

## <span data-ttu-id="d952a-101">보안</span><span class="sxs-lookup"><span data-stu-id="d952a-101">Security</span></span>

<span data-ttu-id="d952a-102">Microsoft는 [microsoft](https://github.com/Microsoft), [Azure](https://github.com/Azure), [DotNet](https://github.com/dotnet), [AspNet](https://github.com/aspnet), [Xamarin](https://github.com/xamarin), 그리고 [github 조직을](https://opensource.microsoft.com/)포함 하는 github 조직을 통해 관리 되는 모든 소스 코드 리포지토리를 포함 하는 소프트웨어 제품 및 서비스의 보안을 진지 하 게 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-102">Microsoft takes the security of our software products and services seriously, which includes all source code repositories managed through our GitHub organizations, which include [Microsoft](https://github.com/Microsoft), [Azure](https://github.com/Azure), [DotNet](https://github.com/dotnet), [AspNet](https://github.com/aspnet), [Xamarin](https://github.com/xamarin), and [our GitHub organizations](https://opensource.microsoft.com/).</span></span>

<span data-ttu-id="d952a-103">Microsoft [의 보안 취약점에 대 한 정의](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc751383(v=technet.10))를 만족 하는 모든 microsoft 소유 저장소의 보안 취약성을 발견 했다고 생각 되는 경우 아래에 설명 된 대로 저희에 게 보고 해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="d952a-103">If you believe you have found a security vulnerability in any Microsoft-owned repository that meets [Microsoft's definition of a security vulnerability](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc751383(v=technet.10)), please report it to us as described below.</span></span>

## <span data-ttu-id="d952a-104">보안 문제 보고</span><span class="sxs-lookup"><span data-stu-id="d952a-104">Reporting Security Issues</span></span>

**<span data-ttu-id="d952a-105">공개 GitHub 문제를 통해 보안 취약점을 보고 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d952a-105">Please do not report security vulnerabilities through public GitHub issues.</span></span>**

<span data-ttu-id="d952a-106">대신 Microsoft 보안 응답 센터 (MSRC)에 보고 하세요 [https://msrc.microsoft.com/create-report](https://msrc.microsoft.com/create-report) .</span><span class="sxs-lookup"><span data-stu-id="d952a-106">Instead, please report them to the Microsoft Security Response Center (MSRC) at [https://msrc.microsoft.com/create-report](https://msrc.microsoft.com/create-report).</span></span>

<span data-ttu-id="d952a-107">로그인 하지 않고 제출 하려면 [secure@microsoft.com](mailto:secure@microsoft.com)에 게 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-107">If you prefer to submit without logging in, send email to [secure@microsoft.com](mailto:secure@microsoft.com).</span></span>  <span data-ttu-id="d952a-108">가능 하면 PGP 키를 사용 하 여 메시지를 암호화 합니다. [Microsoft Security Response CENTER PGP 키 페이지](https://www.microsoft.com/en-us/msrc/pgp-key-msrc)에서 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="d952a-108">If possible, encrypt your message with our PGP key; please download it from the [Microsoft Security Response Center PGP Key page](https://www.microsoft.com/en-us/msrc/pgp-key-msrc).</span></span>

<span data-ttu-id="d952a-109">24 시간 이내에 응답을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-109">You should receive a response within 24 hours.</span></span> <span data-ttu-id="d952a-110">몇 가지 이유로 인해 전자 메일을 통해 원본 메시지를 받았는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d952a-110">If for some reason you do not, please follow up via email to ensure we received your original message.</span></span> <span data-ttu-id="d952a-111">추가 정보는 [microsoft.com/msrc](https://www.microsoft.com/msrc)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-111">Additional information can be found at [microsoft.com/msrc](https://www.microsoft.com/msrc).</span></span> 

<span data-ttu-id="d952a-112">가능한 문제의 특성과 범위를 더 잘 이해 하기 위해 아래에 나열 된 요청 된 정보 (제공할 수 있는 만큼)를 포함 하세요.</span><span class="sxs-lookup"><span data-stu-id="d952a-112">Please include the requested information listed below (as much as you can provide) to help us better understand the nature and scope of the possible issue:</span></span>

  * <span data-ttu-id="d952a-113">문제 유형 (예: 버퍼 오버플로, SQL 주입, 교차 사이트 스크립팅 등)</span><span class="sxs-lookup"><span data-stu-id="d952a-113">Type of issue (e.g. buffer overflow, SQL injection, cross-site scripting, etc.)</span></span>
  * <span data-ttu-id="d952a-114">문제의 manifestation 관련 된 원본 파일의 전체 경로</span><span class="sxs-lookup"><span data-stu-id="d952a-114">Full paths of source file(s) related to the manifestation of the issue</span></span>
  * <span data-ttu-id="d952a-115">영향을 받는 소스 코드의 위치 (tag/branch/commit 또는 direct URL)</span><span class="sxs-lookup"><span data-stu-id="d952a-115">The location of the affected source code (tag/branch/commit or direct URL)</span></span>
  * <span data-ttu-id="d952a-116">문제를 재현 하는 데 필요한 특별 한 구성</span><span class="sxs-lookup"><span data-stu-id="d952a-116">Any special configuration required to reproduce the issue</span></span>
  * <span data-ttu-id="d952a-117">문제를 재현 하는 단계별 지침</span><span class="sxs-lookup"><span data-stu-id="d952a-117">Step-by-step instructions to reproduce the issue</span></span>
  * <span data-ttu-id="d952a-118">개념 입증 또는 악용 코드 (가능 하다 면)</span><span class="sxs-lookup"><span data-stu-id="d952a-118">Proof-of-concept or exploit code (if possible)</span></span>
  * <span data-ttu-id="d952a-119">공격자가 문제를 이용 하는 방법을 포함 하 여 문제의 영향</span><span class="sxs-lookup"><span data-stu-id="d952a-119">Impact of the issue, including how an attacker might exploit the issue</span></span>

<span data-ttu-id="d952a-120">이 정보는 보고서를 보다 신속 하 게 심사 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-120">This information will help us triage your report more quickly.</span></span>

<span data-ttu-id="d952a-121">버그를 bounty 보고 하는 경우 더 많은 보고서가 높은 bounty 수상 내용에 기여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-121">If you are reporting for a bug bounty, more complete reports can contribute to a higher bounty award.</span></span> <span data-ttu-id="d952a-122">활성 프로그램에 대 한 자세한 내용은 [Microsoft 버그 Bounty 프로그램](https://microsoft.com/msrc/bounty) 페이지를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d952a-122">Please visit our [Microsoft Bug Bounty Program](https://microsoft.com/msrc/bounty) page for more details about our active programs.</span></span>

## <span data-ttu-id="d952a-123">기본 설정 언어</span><span class="sxs-lookup"><span data-stu-id="d952a-123">Preferred Languages</span></span>

<span data-ttu-id="d952a-124">모든 통신은 영어로 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-124">We prefer all communications to be in English.</span></span>

## <span data-ttu-id="d952a-125">정책</span><span class="sxs-lookup"><span data-stu-id="d952a-125">Policy</span></span>

<span data-ttu-id="d952a-126">Microsoft는 [통합 된 취약점 공개](https://www.microsoft.com/en-us/msrc/cvd)원칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d952a-126">Microsoft follows the principle of [Coordinated Vulnerability Disclosure](https://www.microsoft.com/en-us/msrc/cvd).</span></span>

<!-- END MICROSOFT SECURITY.MD BLOCK -->