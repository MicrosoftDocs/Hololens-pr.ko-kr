---
title: HoloLens(1세대)에서 3D 뷰어 베타 사용
description: HoloLens(1세대)에서 3D 뷰어 베타가 지원하는 파일 및 기능의 유형과 해당 앱을 사용하고 문제를 해결하는 방법에 대해 설명합니다.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016289"
---
# <span data-ttu-id="33467-103">HoloLens(1세대)에서 3D 뷰어 베타 사용</span><span class="sxs-lookup"><span data-stu-id="33467-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="33467-104">HoloLens(1세대)에서 3D 뷰어 베타 3D 모델을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="33467-105">Microsoft Edge, OneDrive 및 기타 앱에서 *지원하는* .fbx 파일을 열고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="33467-106">이 문서는 .fbx 파일을 지원하고 HoloLens(1세대)에서만 사용할 수 있는 몰입형 Unity **3D 뷰어 베타** 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="33467-107">HoloLens 2에서 사전 설치된 **3D 뷰어** 앱은 Mixed Reality Home에서 사용자 지정 .glb 3D 모델 열기를 지원합니다. (자세한 내용은 [자산 요건 개요](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="33467-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="33467-108">3D 뷰어 베타는 HoloLens(1세대)용 Microsoft Store에서 계속 사용할 수 있지만 더 이상 활발하게 개발되거나 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="33467-109">3D 뷰어 베타에서 3D 모델을 여는 데 문제가 있거나 3D 모델의 특정 기능을 지원하지 않는 경우에는 아래의 [지원되는 콘텐츠 사양](#supported-content-specifications)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="33467-110">3D 뷰어 베타와 함께 사용할 3D 모델을 만들거나 최적화하려면 아래의 [3D 뷰어 베타에 대한 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="33467-111">HoloLens에서 3D 모델을 여는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="33467-112">자세한 내용은 아래의 [HoloLens에서 FBX 파일 보기](#viewing-fbx-files-on-hololens)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="33467-113">해당 항목을 읽은 후에도 문제가 발생하는 경우 아래에서 [문제 해결](#troubleshooting)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <span data-ttu-id="33467-114">지원되는 콘텐츠 사양</span><span class="sxs-lookup"><span data-stu-id="33467-114">Supported content specifications</span></span>

### <span data-ttu-id="33467-115">파일 형식</span><span class="sxs-lookup"><span data-stu-id="33467-115">File format</span></span>

- <span data-ttu-id="33467-116">FBX 형식</span><span class="sxs-lookup"><span data-stu-id="33467-116">FBX format</span></span>
- <span data-ttu-id="33467-117">최대 FBX 릴리스 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="33467-117">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="33467-118">파일 크기</span><span class="sxs-lookup"><span data-stu-id="33467-118">File size</span></span>

- <span data-ttu-id="33467-119">최소 5KB</span><span class="sxs-lookup"><span data-stu-id="33467-119">Minimum 5 KB</span></span>
- <span data-ttu-id="33467-120">최대 500MB</span><span class="sxs-lookup"><span data-stu-id="33467-120">Maximum 500 MB</span></span>

### <span data-ttu-id="33467-121">기하 도형</span><span class="sxs-lookup"><span data-stu-id="33467-121">Geometry</span></span>

- <span data-ttu-id="33467-122">다각형 모델에만 해당</span><span class="sxs-lookup"><span data-stu-id="33467-122">Polygonal models only.</span></span> <span data-ttu-id="33467-123">세부 표면이나 NURB 없음</span><span class="sxs-lookup"><span data-stu-id="33467-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="33467-124">오른손 좌표계</span><span class="sxs-lookup"><span data-stu-id="33467-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="33467-125">변환 행렬의 기울이기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-125">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="33467-126">텍스처</span><span class="sxs-lookup"><span data-stu-id="33467-126">Textures</span></span>

- <span data-ttu-id="33467-127">텍스처 맵은 FBX 파일에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="33467-128">지원되는 이미지 형식</span><span class="sxs-lookup"><span data-stu-id="33467-128">Supported image formats</span></span>
  - <span data-ttu-id="33467-129">JPEG 및 PNG 이미지</span><span class="sxs-lookup"><span data-stu-id="33467-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="33467-130">BMP 이미지(24비트 RGB 트루 컬러)</span><span class="sxs-lookup"><span data-stu-id="33467-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="33467-131">TGA 이미지(24비트 RGB 및 32비트 RGBQ 트루 컬러)</span><span class="sxs-lookup"><span data-stu-id="33467-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="33467-132">최대 텍스처 해상도(2048x2048)</span><span class="sxs-lookup"><span data-stu-id="33467-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="33467-133">메시 당 최대 1개의 확산 맵, 일반 맵 그리고 리플렉션 큐브 맵</span><span class="sxs-lookup"><span data-stu-id="33467-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="33467-134">확산 질감의 알파 채널이 50% 이하인 경우 픽셀이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="33467-135">애니메이션</span><span class="sxs-lookup"><span data-stu-id="33467-135">Animation</span></span>

- <span data-ttu-id="33467-136">개별 개체의 배율/회전/변환 애니메이션</span><span class="sxs-lookup"><span data-stu-id="33467-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="33467-137">스키닝을 사용하는 스켈레탈(리깅된 상태) 애니메이션</span><span class="sxs-lookup"><span data-stu-id="33467-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="33467-138">버텍스 당 최대 4개의 인플루언스</span><span class="sxs-lookup"><span data-stu-id="33467-138">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="33467-139">재질</span><span class="sxs-lookup"><span data-stu-id="33467-139">Materials</span></span>

- <span data-ttu-id="33467-140">Lambert 및 Phong 재질 지원, 매개 변수 조절 가능</span><span class="sxs-lookup"><span data-stu-id="33467-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="33467-141">Lambert에 대해 지원되는 재질 속성</span><span class="sxs-lookup"><span data-stu-id="33467-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="33467-142">주 텍스처(RGB + 알파 테스트)</span><span class="sxs-lookup"><span data-stu-id="33467-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="33467-143">확산 색(RGB)</span><span class="sxs-lookup"><span data-stu-id="33467-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="33467-144">주변 색(RGB)</span><span class="sxs-lookup"><span data-stu-id="33467-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="33467-145">Phong에 대해 지원되는 재질 속성</span><span class="sxs-lookup"><span data-stu-id="33467-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="33467-146">주 텍스처(RGB + 알파 테스트)</span><span class="sxs-lookup"><span data-stu-id="33467-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="33467-147">확산 색(RGB)</span><span class="sxs-lookup"><span data-stu-id="33467-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="33467-148">주변 색(RGB)</span><span class="sxs-lookup"><span data-stu-id="33467-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="33467-149">반사 색(RGB)</span><span class="sxs-lookup"><span data-stu-id="33467-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="33467-150">광도</span><span class="sxs-lookup"><span data-stu-id="33467-150">Shininess</span></span>
  - <span data-ttu-id="33467-151">반사도</span><span class="sxs-lookup"><span data-stu-id="33467-151">Reflectivity</span></span>
- <span data-ttu-id="33467-152">사용자 지정 재질은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-152">Custom materials are not supported</span></span>
- <span data-ttu-id="33467-153">메시 당 최대 1개의 재질</span><span class="sxs-lookup"><span data-stu-id="33467-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="33467-154">최대 1개의 재질 층</span><span class="sxs-lookup"><span data-stu-id="33467-154">Maximum of one material layer</span></span>
- <span data-ttu-id="33467-155">파일 당 최대 8개의 재질</span><span class="sxs-lookup"><span data-stu-id="33467-155">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="33467-156">파일 및 모델 제한 사항</span><span class="sxs-lookup"><span data-stu-id="33467-156">File and model limitations</span></span>

<span data-ttu-id="33467-157">파일 크기와 3D 뷰어 베타에서 동시에 열 수 있는 모델, 버텍스 및 메시의 개수에 대한 하드 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="33467-158">모델 당 최대 500MB 파일 크기</span><span class="sxs-lookup"><span data-stu-id="33467-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="33467-159">버텍스: 열려 있는 모든 모델에서 총 60만개</span><span class="sxs-lookup"><span data-stu-id="33467-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="33467-160">메시: 열려 있는 모든 모델에서 총 1,600개</span><span class="sxs-lookup"><span data-stu-id="33467-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="33467-161">한 번에 최대 40개의 모델 열기 가능</span><span class="sxs-lookup"><span data-stu-id="33467-161">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="33467-162">3D 뷰어 베타에 대한 3D 모델 최적화</span><span class="sxs-lookup"><span data-stu-id="33467-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <span data-ttu-id="33467-163">특별 고려 사항</span><span class="sxs-lookup"><span data-stu-id="33467-163">Special considerations</span></span>

- <span data-ttu-id="33467-164">텍스처 맵에서 블랙 재질 또는 블랙 영역을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="33467-165">홀로그램은 빛으로 만들어지므로 HoloLens는 투명으로 블랙(빛이 없는 경우)을 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="33467-166">사용자의 작성 도구에서 FBX으로 내보내기 전에 모든 기하 도형이 표시되고 잠금 해제되어 있는지 여부 및 기하 도형이 꺼져 있거나 템플릿이 되어 있는 레이어의 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="33467-167">표시 여부가 준수되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-167">Visibility is not respected.</span></span>
- <span data-ttu-id="33467-168">노드 사이에 매우 큰 변환 오프셋을 피해야 하니다. (예: 10만 단위)</span><span class="sxs-lookup"><span data-stu-id="33467-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="33467-169">이 경우 모델이 이동, 크기 조정, 회전하는 동안 지터될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="33467-170">성능 최적화</span><span class="sxs-lookup"><span data-stu-id="33467-170">Performance optimization</span></span>

<span data-ttu-id="33467-171">최상의 결과를 위해 제작 프로세스 동안 HoloLens의 3D 뷰어 베타 앱에서 성능을 염두에 두고 콘텐츠를 제작하고 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="33467-172">3D 뷰어 베타는 실시간으로 콘텐츠를 렌더링하고 성능은 HoloLens 하드웨어 기능의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="33467-173">3D 모델에서 성능에 영향을 줄 수 있는 다양한 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="33467-174">3D 뷰어 베타는 버텍스가 15만개 이상이거나 메시가 400개 이상인 경우 로드시 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="33467-175">애니메이션은 기타 열린 모델의 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="33467-176">3D 뷰어 베타에서 동시에 열 수 있는 모델, 버텍스, 메시의 총 개수에 대한 하드 제한이 있습니다. ([파일 및 모델 제한 사항](#file-and-model-limitations)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="33467-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="33467-177">3D 모델이 모델 복잡성으로 인해 제대로 실행되지 않는 경우 다음 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="33467-178">다각형 개수 줄이기</span><span class="sxs-lookup"><span data-stu-id="33467-178">Reducing polygon count</span></span>
- <span data-ttu-id="33467-179">리깅된 애니메이션에서 뼈대의 개수 줄이기</span><span class="sxs-lookup"><span data-stu-id="33467-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="33467-180">자가 폐색 방지</span><span class="sxs-lookup"><span data-stu-id="33467-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="33467-181">3D 뷰어 베타에서 양면 렌더링이 지원되며 성능 상의 이유로 인해 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="33467-182">해당 기능은 **세부 정보** 페이지에서 **양면** 버튼을 통해 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="33467-183">최적의 성능을 위해 콘텐츠에 양면 렌더링이 필요하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="33467-184">3D 모델 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="33467-184">Validating your 3D model</span></span>

<span data-ttu-id="33467-185">HoloLens의 3D 뷰어 베타에서 모델을 열어 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="33467-186">**세부 정보** 단추를 선택하여 지원되지 않는 콘텐츠(있을 경우)의 모델 특성 및 경고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="33467-187">실제에 가까운 규격으로 3D 모델 렌더링</span><span class="sxs-lookup"><span data-stu-id="33467-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="33467-188">기본적으로 3D 뷰어 베타는 사용자와 관련하여 편안한 크기와 위치에 3D 모델을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="33467-189">그러나 실제에 가까운 치수로 3D 모델을 렌더링하는 것이 중요한 경우(예: 방에서 가구 모델을 평가하는 경우) 콘텐츠 작성자는 파일의 메타 데이터 내에서 플래그를 설정하여 응용 프로그램 및 사용자 모두에 의한 해당 모델의 크기 조정을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="33467-190">모델의 크기 조정을 방지하려면 Microsoft_DisableScale 이름의 장면에서 모든 개체에 부울 사용자 지정 특성을 추가하고 이를 True로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="33467-191">그런 다음 3D 뷰어 베타는 FBX 파일에 구운 FbxSystemUnit 정보를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="33467-192">3D 뷰어 베타의 배율은 FBX 단위 당 1미터입니다.</span><span class="sxs-lookup"><span data-stu-id="33467-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="33467-193">HoloLens에서 FBX 파일 보기</span><span class="sxs-lookup"><span data-stu-id="33467-193">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="33467-194">Microsoft Edge에서 FBX 파일 열기</span><span class="sxs-lookup"><span data-stu-id="33467-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="33467-195">HoloLens에서 Microsoft Edge를 사용하여 웹 사이트로부터 직접 FBX 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="33467-196">Microsoft Edge에서 보려는 FBX 파일이 포함된 웹 페이지를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="33467-197">파일을 선택하여 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-197">Select the file to download it.</span></span>
1. <span data-ttu-id="33467-198">다운로드가 완료되면 Microsoft Edge에서 **열기** 단추를 선택하여 3D 뷰어 베타에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="33467-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="33467-199">추후에 다시 Microsoft Edge에서 다운로드를 사용하여 다운로드된 파일에 액세스하고 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="33467-200">3D 모델을 저장하고 계속해서 액세스를 보장하려면 사용자의 PC에서 파일을 다운로드하여 OneDrive 계정에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="33467-201">그런 다음 HoloLens의 OneDrive 앱에서 해당 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="33467-202">다운로드 가능한 FBX 모델을 포함하는 일부 웹 사이트는 압축된 ZIP 형식으로 해당 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="33467-203">3D 뷰어 베타는 ZIP 파일을 직접 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="33467-204">대신 사용자의 PC를 사용하여 FBX 파일을 추출하고 OneDrive 계정에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="33467-205">그런 다음 HoloLens의 OneDrive 앱에서 해당 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="33467-206">OneDrive에서 FBX 파일 열기</span><span class="sxs-lookup"><span data-stu-id="33467-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="33467-207">HoloLens에서 OneDrive 앱을 사용하여 OneDrive에서 FBX 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="33467-208">HoloLens에서 Microsoft 스토어 앱을 사용하여 OneDrive를 설치했는지 여부와 이미 사용자의 PC에서 OneDrive에 FBX 파일을 업로드했는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="33467-209">파일이 OneDrive에 있는 경우 다음 두 가지 방법 중 하나로 3D 뷰어 베타를 사용하여 HoloLens에서 FBX 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="33467-210">HoloLens에서 OneDrive를 실행하고 FBX 파일을 선택하여 3D 뷰어 베타에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="33467-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="33467-211">3D 뷰어 베타를 실행하고 에어 탭하여 도구 모음을 표시하고 **파일 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="33467-212">OneDrive가 실행되어 FBX 파일을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="33467-213">문제 해결</span><span class="sxs-lookup"><span data-stu-id="33467-213">Troubleshooting</span></span>

### <span data-ttu-id="33467-214">3D 모델을 열면 경고가 표시되는 경우</span><span class="sxs-lookup"><span data-stu-id="33467-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="33467-215">3D 뷰어 베타에서 지원하지 않는 기능을 포함하는 3D 모델을 열거나 모델이 너무 복잡하여 성능에 영향을 줄 수 있는 경우 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="33467-216">3D 뷰어 베타는 계속해서 3D 모델을 로드하지만 성능이나 시각적 정확도가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="33467-217">자세한 내용은 [지원되는 콘텐츠 사양](#supported-content-specifications) 및 [3D 뷰어 베타에 대한 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="33467-218">경고가 표시되고 3D 모델이 로드되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="33467-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="33467-219">3D 뷰어 베타에서 복잡하거나 파일 크기 때문에 3D 모델을 로드할 수 없는 경우 또는 FBX 파일이 손상되거나 잘못된 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="33467-220">동시에 열 수 있는 모델, 버텍스 또는 메시의 총 개수 제한에 도달하면 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="33467-221">자세한 내용은 [지원되는 콘텐츠 사양](#supported-content-specifications) 및 [파일 및 모델 제한 사항](#file-and-model-limitations)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="33467-222">3D 모델이 로드되지만 예상한 대로 표시되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="33467-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="33467-223">3D 뷰어 베타에서 3D 모델이 제대로 표시되지 않은 경우 에어 탭하여 도구 모음을 표시하고 **세부 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="33467-224">3D 뷰어 베타에서 지원하지 않는 파일의 측면이 경고로 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="33467-225">텍스처는 FBX 파일에 포함되어 있지 않기 때문에 확인할 수 있는 가장 일반적인 문제에서 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="33467-226">이 경우 해당 모델은 흰색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-226">In this case, the model will appear white.</span></span> <span data-ttu-id="33467-227">이 문제는 작성 도구에서 텍스처 포함 옵션이 선택된 FBX로 내보냄으로써 작성 프로세스에서 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="33467-228">자세한 내용은 [지원되는 콘텐츠 사양](#supported-content-specifications) 및 [3D 뷰어 베타에 대한 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="33467-229">3D 모델을 보는 동안 성능이 저하되는 경우</span><span class="sxs-lookup"><span data-stu-id="33467-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="33467-230">3D 모델을 로드하고 볼 때 모델의 복잡성, 동시에 열린 모델의 개수 또는 활성 애니메이션이 포함된 모델의 개수로 인해 성능이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="33467-231">자세한 내용은 [3D 뷰어 베타에 대한 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta) 및 [파일 및 모델 제한 사항](#file-and-model-limitations)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33467-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="33467-232">HoloLens에서 FBX 파일을 열면 3D 뷰어 베타에서 해당 파일이 열리지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="33467-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="33467-233">3D 뷰어 베타를 설치하면 자동으로 .fbx 파일 확장과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="33467-234">FBX 파일을 열려고 시도할 때 Microsoft 스토어로 지시하는 대화 상자가 표시되면 현재 HoloLens에서 .fbx 파일 확장과 연결된 앱이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33467-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="33467-235">3D 뷰어 베타가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="33467-236">설치되어 있지 않은 경우 HoloLens의 Microsoft 스토어에서 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="33467-237">3D 뷰어 베타가 이미 설치되어 있는 경우 3D 뷰어 베타를 실행하고 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="33467-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="33467-238">문제가 계속되면 3D 뷰어 베타를 제거하고 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="33467-239">.fbx 파일 확장명이 3D 뷰어 베타와 다시 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="33467-240">FBX 파일을 열려고 시도할 때 3D 뷰어 베타가 아닌 다른 앱이 열리는 경우 해당 앱은 3D 뷰어 베타 설치 후에 설치되었으며 .fbx 파일 확장과 연결된 것으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="33467-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="33467-241">3D 뷰어 베타를 .fbx 파일 확장에 연결하려는 경우 3D 뷰어 베타를 제거한 후 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <span data-ttu-id="33467-242">3D 뷰어 베타의 파일 열기 단추로 앱이 실행되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="33467-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="33467-243">**파일 열기** 단추를 클릭하면 HoloLens에서 파일 선택기 기능과 연결된 앱이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="33467-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="33467-244">OneDrive가 설치된 경우 **파일 열기** 단추로 OneDrive를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="33467-245">그러나 현재 HoloLens에 설치된 파일 선택기 기능과 연결되어 있는 앱이 없는 경우 Microsoft 스토어로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="33467-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="33467-246">**파일 열기** 단추로 OneDrive가 아닌 다른 앱이 실행되는 경우 해당 앱은 OneDrive 이후에 설치되었으며 파일 선택기 기능과 연결된 것으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="33467-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="33467-247">3D 뷰어 베타에서 **파일 열기** 단추로 OneDrive를 실행하려는 경우 OneDrive를 제거하고 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="33467-248">**파일 열기** 단추가 활성화되지 않은 경우 3D 뷰어 베타에서 한 번에 열 수 있는 모델의 제한에 도달했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33467-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="33467-249">3D 뷰어 베타에서 40개의 모델을 연 경우 모델을 추가로 열려면 먼저 일부를 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33467-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="33467-250">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="33467-250">Additional resources</span></span>

- <span data-ttu-id="33467-251">[지원 포럼](http://forums.hololens.com/categories/3d-viewer-beta) -보관 목적으로만 사용 가능.</span><span class="sxs-lookup"><span data-stu-id="33467-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="33467-252">이 포럼은 더 이상 활성 상태가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="33467-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="33467-253">타사 알림</span><span class="sxs-lookup"><span data-stu-id="33467-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
