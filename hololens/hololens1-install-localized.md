---
title: 지역화된 버전의 HoloLens 설치
description: 중국어 또는 일본어 버전의 HoloLens를 설치하는 방법 알아보기
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829557"
---
# <span data-ttu-id="3c216-103">지역화된 버전의 HoloLens(1세대) 설치</span><span class="sxs-lookup"><span data-stu-id="3c216-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="3c216-104">HoloLens의 중국어 또는 일본어 버전으로 전환하려면 Windows Device Recovery Tool(WDRT)를 사용하여 PC에서 해당 언어의 빌드를 다운로드한 다음 HoloLens에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c216-105">WDRT를 사용하여 HoloLens의 중국어 또는 일본어 빌드를 설치하면 HoloLens에서 개인 파일 및 설정과 같은 기존 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="3c216-106">PC에서 [Windows Device Recovery Tool(WDRT)](https://support.microsoft.com/help/12379)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="3c216-107">PC에 사용할 언어의 패키지([중국어 간체](https://aka.ms/hololensdownload-ch) 또는 [일본어](https://aka.ms/hololensdownload-jp))를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="3c216-108">다운로드가 완료되면 **파일 탐색기** > **다운로드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="3c216-109">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 추출** > **추출**을 선택하여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="3c216-110">함께 제공된 마이크로 USB 케이블을 사용하여 HoloLens를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="3c216-111">(다른 케이블을 사용하여 HoloLens를 연결하는 경우에도 이 방법이 가장 적합합니다.)</span><span class="sxs-lookup"><span data-stu-id="3c216-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="3c216-112">도구에서 HoloLens를 자동으로 검색한 후 Microsoft HoloLens 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="3c216-113">다음 화면에서 **수동 패키지 선택** 을 선택하고 4단계에서 압축을 푼 폴더에 있는 설치 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="3c216-114">". ,ffu"라는 확장명을 가진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="3c216-115"> *\*소프트웨어 설치*\*를 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="3c216-116">빌드 설치가 완료되면 HoloLens 설치가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="3c216-117">장치에 배치하고 설치 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="3c216-118">설치를 완료한 경우 **설정** > **업데이트 및 보안** > **Windows 참가자 프로그램**으로 이동하여 최신 미리 보기 빌드를 받도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="3c216-119">영어 미리 보기 빌드와 마찬가지로 Windows 참가자 프로그램은 최신 미리 보기 빌드를 사용하여 중국어 및 일본어 버전의 HoloLens를 항상 최신 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="3c216-120">설정 앱을 사용하여 영어, 일본어, 중국어 간의 시스템 언어를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="3c216-121">새 빌드를 플래시하는 것이 장치 시스템 언어를 변경하는 유일한 지원되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="3c216-122">화상 Pinyin 키보드를 사용하여 중국어 간체 또는 일본어 텍스트를 입력할 수 있지만 이번에는 Bluetooth 하드웨어 키보드를 사용하여 중국어 간체 또는 일본어 텍스트를 입력하는 것이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c216-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="3c216-123">그러나 중국어 또는 일본어 HoloLens에서는 Bluetooth 키보드를 사용하여 영어로 입력할 수 있습니다(영어를 입력하도록 하드웨어 키보드를 전환하려면 ~ 키를 누릅니다).</span><span class="sxs-lookup"><span data-stu-id="3c216-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
