---
title: HoloLens의 지역화 된 버전 설치
description: 중국어 및 일본어 버전을 포함 하 여 HoloLens (첫 번째 gen)의 지역화 된 버전을 설치 하는 방법에 대해 알아봅니다.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310060"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="d03d0-103">HoloLens의 지역화 된 버전 설치 (첫 번째 gen)</span><span class="sxs-lookup"><span data-stu-id="d03d0-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="d03d0-104">HoloLens의 중국어 또는 일본어 버전으로 전환 하려면 Windows 장치 복구 도구 (WDRT)를 사용 하 여 PC에서 언어에 대 한 빌드를 다운로드 한 다음 HoloLens에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d03d0-105">WDRT를 사용 하 여 HoloLens의 중국어 또는 일본어 빌드를 설치 하면 HoloLens에서 개인 파일 및 설정과 같은 기존 데이터가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="d03d0-106">PC에서 [WDRT (Windows 장치 복구 도구)](https://support.microsoft.com/help/12379)를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="d03d0-107">PC에 원하는 언어 (  [중국어 간체](https://aka.ms/hololensdownload-ch) 또는 [일본어](https://aka.ms/hololensdownload-jp))의 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="d03d0-108">다운로드가 완료 되 면 **파일 탐색기**  >  **다운로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="d03d0-109">방금 다운로드 한 압축 폴더를 마우스 오른쪽 단추로 클릭 하 **고 압축 풀기**  >   를 선택 하 여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="d03d0-110">제공 된 마이크로 USB 케이블을 사용 하 여 HoloLens를 PC에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="d03d0-111">(다른 케이블을 사용 하 여 HoloLens를 연결 하는 경우에도이 작업은 가장 효과적입니다.)</span><span class="sxs-lookup"><span data-stu-id="d03d0-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="d03d0-112">도구에서 HoloLens를 자동으로 검색 한 후 Microsoft HoloLens 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="d03d0-113">다음 화면에서 **수동 패키지 선택** 을 선택   하 고 4 단계에서 압축을 푼 폴더에 있는 설치 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="d03d0-114">확장명이 ".ffu" 인 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="d03d0-115"> *\*소프트웨어 설치** 를 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="d03d0-116">빌드를 설치한 후에는 HoloLens 설치가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="d03d0-117">장치에를 추가 하 고 설치 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="d03d0-118">설치를 완료 한 후에는 **설정**  >  **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동 하 여 최신 미리 보기 빌드를 받도록 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="d03d0-119">영어 미리 보기 빌드와 마찬가지로, Windows 참가자 프로그램은 최신 미리 보기 빌드를 사용 하 여 최신 버전의 HoloLens를 최신 버전으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="d03d0-120">설정 앱을 사용 하 여 영어, 일본어 및 중국어로 시스템 언어를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="d03d0-121">깜박이는 새 빌드는 장치 시스템 언어를 변경 하는 데 유일 하 게 지원 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="d03d0-122">화면 병음 키보드를 사용 하 여 중국어 간체 또는 일본어 텍스트를 입력할 수 있지만 이번에는 Bluetooth 하드웨어 키보드를 사용 하 여 중국어 간체 또는 일본어 텍스트를 입력 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="d03d0-123">그러나 중국어 또는 일본어 HoloLens에서는 계속 해 서 Bluetooth 키보드를 사용 하 여 영어로 입력할 수 있습니다. 하드웨어 키보드를 영어로 전환 하려면 ~ 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d03d0-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
