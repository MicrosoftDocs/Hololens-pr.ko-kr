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
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034230"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>HoloLens(1세대)에서 3D 뷰어 베타 사용

3D 뷰어 베타를 사용하면 HoloLens(1세대)에서 3D 모델을 볼 수 있습니다. Microsoft Edge, OneDrive 및 기타 앱에서 *지원되는* .fbx 파일을 열고 볼 수 있습니다.

>[!NOTE]
>이 문서는 .fbx 파일을 지원하고 HoloLens(1세대)에서만 사용할 수 있는 몰입형 Unity **3D 뷰어 베타** 앱에 적용됩니다. HoloLens 2에 사전 설치된 **3D 뷰어** 앱은 혼합 현실 홈에서 사용자 지정 .glb 3D 모델을 열 수 있도록 지원합니다(자세한 내용은 [자산 요구 사항 개요](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) 참조).

>[!IMPORTANT]
>3D 뷰어 베타는 HoloLens(1세대)용 Microsoft Store에서 계속 사용할 수 있지만 더 이상 활발하게 개발되거나 지원되지 않습니다.

3D 뷰어 베타에서 3D 모델을 여는 데 문제가 있거나 3D 모델의 특정 기능이 지원되지 않는 경우 아래의 [지원되는 콘텐츠 사양](#supported-content-specifications)을 참조하세요.

3D 뷰어 베타와 함께 사용할 3D 모델을 빌드하거나 최적화하려면 아래의 [3D 뷰어 베타용 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta)를 참조하세요.

HoloLens에서 3D 모델을 여는 방법에는 두 가지가 있습니다. 자세한 내용은 아래의 [HoloLens에서 FBX 파일 보기](#viewing-fbx-files-on-hololens)를 참조하세요.

이 항목을 읽은 후에도 문제가 발생하면 아래의 [문제 해결](#troubleshooting)을 참조하세요.

## <a name="supported-content-specifications"></a>지원되는 콘텐츠 사양

### <a name="file-format"></a>파일 형식

- FBX 형식
- 최대 FBX 릴리스 2015.1.0

### <a name="file-size"></a>파일 크기

- 최소 5KB
- 최대 500MB

### <a name="geometry"></a>기하 도형

- 다각형 모델에만 해당. 세부 표면이나 NURB 없음
- 오른손 좌표계
- 변환 매트릭스의 기울이기는 지원되지 않습니다.

### <a name="textures"></a>텍스처

- 텍스처 맵은 FBX 파일에 포함되어야 합니다.
- 지원되는 이미지 형식
  - JPEG 및 PNG 이미지
  - BMP 이미지(24비트 RGB 트루 컬러)
  - TGA 이미지(24비트 RGB 및 32비트 RGBQ 트루 컬러)
- 최대 텍스처 해상도(2048x2048)
- 메시당 최대 하나의 확산 맵, 하나의 일반 맵 및 하나의 반사 큐브 맵
- 확산 질감의 알파 채널이 50% 이하인 경우 픽셀이 삭제됩니다.

### <a name="animation"></a>애니메이션

- 개별 개체의 배율/회전/변환 애니메이션
- 스키닝이 포함된 골격(rigged) 애니메이션
  - 정점당 최대 4개의 영향

### <a name="materials"></a>재질

- 조정 가능한 매개변수와 함께 Lambert 및 Phong 재질이 지원됩니다.
- Lambert에 대해 지원되는 재질 속성
  - 주 텍스처(RGB + 알파 테스트)
  - 확산 색(RGB)
  - 주변 색(RGB)
- Phong에 대해 지원되는 재질 속성
  - 주 텍스처(RGB + 알파 테스트)
  - 확산 색(RGB)
  - 주변 색(RGB)
  - 반사 색(RGB)
  - 광도
  - 반사도
- 사용자 지정 재질은 지원되지 않습니다.
- 메시 당 최대 1개의 재질
- 최대 1개의 재질 층
- 파일 당 최대 8개의 재질

### <a name="file-and-model-limitations"></a>파일 및 모델 제한 사항

파일 크기와 3D 뷰어 베타에서 동시에 열 수 있는 모델, 버텍스 및 메시의 개수에 대한 하드 제한이 있습니다.

- 모델 당 최대 500MB 파일 크기
- 버텍스: 열려 있는 모든 모델에서 총 600,000개
- 메시: 열려 있는 모든 모델에서 총 1,600개
- 한 번에 최대 40개의 모델 열기

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>3D 뷰어 베타에 대한 3D 모델 최적화

### <a name="special-considerations"></a>특별 고려 사항

- 텍스처 맵에서 검은색 재질 또는 검은색 영역을 피해야 합니다. 홀로그램은 빛으로 만들어지므로 HoloLens는 검은색(빛이 없는 경우)을 투명하게 렌더링합니다.
- 생성 도구에서 FBX로 내보내기 전에 모든 지오메트리가 표시되고 잠금 해제되어 있고 지오메트리를 포함하는 레이어가 꺼져 있거나 템플릿이 없는지 확인합니다. 표시 여부는 적용되지 않습니다.
- 노드 사이에 매우 큰 변환 오프셋을 피해야 합니다(예: 100,000 단위) 이로 인해 모델이 이동/스케일링/회전하는 동안 지터가 발생할 수 있습니다.

### <a name="performance-optimization"></a>성능 최적화

콘텐츠를 제작하는 동안 성능을 염두에 두고 제작 프로세스 동안 HoloLens의 3D 뷰어 베타 앱에서 유효성을 검사하여 최상의 결과를 얻으세요. 3D 뷰어 베타는 실시간으로 콘텐츠를 렌더링하고 성능은 HoloLens 하드웨어 기능의 적용을 받습니다.  

3D 모델에서 성능에 영향을 줄 수 있는 다양한 변수가 있습니다. 3D 뷰어 베타는 버텍스가 150,000개 넘거나 메시가 400개 넘는 경우 로드 시 경고를 표시합니다. 애니메이션은 기타 열린 모델의 성능에 영향을 줄 수 있습니다. 3D 뷰어 베타에서 동시에 열 수 있는 모델, 버텍스, 메시의 총 개수에 대한 하드 제한이 있습니다([파일 및 모델 제한](#file-and-model-limitations) 참조).  

3D 모델이 모델 복잡성으로 인해 제대로 실행되지 않는 경우 다음 사항을 고려하세요.

- 다각형 수 줄이기
- Rigged 애니메이션에서 뼈대의 수 줄이기
- 자가 폐색 방지

3D 뷰어 베타에서 양면 렌더링이 지원되며 성능 상의 이유로 인해 기본적으로 꺼져 있습니다. 이는 **세부 정보** 페이지의 **양면** 단추를 통해 설정할 수 있습니다. 최적의 성능을 위해 콘텐츠에 양면 렌더링이 필요하지 않도록 해야 합니다.

### <a name="validating-your-3d-model"></a>3D 모델 유효성 검사

HoloLens의 3D 뷰어 베타에서 모델을 열어 유효성을 검사합니다. **세부 정보** 단추를 선택하여 지원되지 않는 콘텐츠(있을 경우)의 모델 특성 및 경고를 확인할 수 있습니다.

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>실제에 가까운 치수로 3D 모델 렌더링

기본적으로 3D 뷰어 베타는 3D 모델을 사용자에 비해 편안한 크기와 위치로 표시합니다. 그러나 실제에 가까운 치수로 3D 모델을 렌더링하는 것이 중요한 경우(예: 방에서 가구 모델을 평가하는 경우) 콘텐츠 작성자는 파일의 메타데이터 내에서 플래그를 설정하여 애플리케이션 및 사용자 모두에 의한 해당 모델의 크기 조정을 방지할 수 있습니다.

모델의 크기 조정을 방지하려면 Microsoft_DisableScale 이름의 장면에서 모든 개체에 부울 사용자 지정 특성을 추가하고 이를 True로 설정합니다. 그런 다음, 3D 뷰어 베타는 FBX 파일에 구운 FbxSystemUnit 정보를 준수합니다. 3D 뷰어 베타의 배율은 FBX 단위 당 1미터입니다.

## <a name="viewing-fbx-files-on-hololens"></a>HoloLens에서 FBX 파일 보기

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Microsoft Edge에서 FBX 파일 열기

HoloLens에서 Microsoft Edge를 사용하여 웹 사이트로부터 직접 FBX 파일을 열 수 있습니다.

1. Microsoft Edge에서 보려는 FBX 파일이 포함된 웹 페이지를 탐색합니다.
1. 파일을 선택하여 다운로드합니다.
1. 다운로드가 완료되면 Microsoft Edge에서 **열기** 단추를 선택하여 3D 뷰어 베타에서 파일을 엽니다.

추후에 다시 Microsoft Edge에서 다운로드를 사용하여 다운로드된 파일에 액세스하고 열 수 있습니다. 3D 모델을 저장하고 계속해서 액세스를 보장하려면 사용자의 PC에서 파일을 다운로드하여 OneDrive 계정에 파일을 저장합니다. 그런 다음, HoloLens의 OneDrive 앱에서 해당 파일을 열 수 있습니다.

> [!NOTE]
> 다운로드 가능한 FBX 모델을 포함하는 일부 웹 사이트는 압축된 ZIP 형식으로 해당 모델을 제공합니다. 3D 뷰어 베타는 ZIP 파일을 직접 열 수 없습니다. 대신 사용자의 PC를 사용하여 FBX 파일을 추출하고 OneDrive 계정에 파일을 저장합니다. 그런 다음, HoloLens의 OneDrive 앱에서 해당 파일을 열 수 있습니다.

### <a name="open-an-fbx-file-from-onedrive"></a>OneDrive에서 FBX 파일 열기

HoloLens에서 OneDrive 앱을 사용하여 OneDrive에서 FBX 파일을 열 수 있습니다. HoloLens에서 Microsoft Store 앱을 사용하여 OneDrive를 설치했는지 여부와 이미 사용자의 PC에서 OneDrive에 FBX 파일을 업로드했는지 여부를 확인합니다.

파일이 OneDrive에 있는 경우 다음 두 가지 방법 중 하나로 3D 뷰어 베타를 사용하여 HoloLens에서 FBX 파일을 열 수 있습니다.

- HoloLens에서 OneDrive를 실행하고 FBX 파일을 선택하여 3D 뷰어 베타에서 파일을 엽니다.
- 3D 뷰어 베타를 실행하고 에어 탭하여 도구 모음을 표시하고 **파일 열기** 를 선택합니다. OneDrive가 실행되어 FBX 파일을 선택할 수 있습니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3D 모델을 열 때 경고가 표시됩니다.

3D 뷰어 베타에서 지원하지 않는 기능을 포함하는 3D 모델을 열거나 모델이 너무 복잡하여 성능에 영향을 줄 수 있는 경우 경고가 표시됩니다. 3D 뷰어 베타는 계속해서 3D 모델을 로드하지만 성능이나 시각적 정확도가 손상될 수 있습니다.

자세한 내용은 [지원되는 콘텐츠 사양](#supported-content-specifications) 및 [3D 뷰어 베타용 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta)를 참조하세요.

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>경고가 표시되고 3D 모델이 로드되지 않습니다.

3D 뷰어 베타에서 복잡하거나 파일 크기 때문에 3D 모델을 로드할 수 없는 경우 또는 FBX 파일이 손상되거나 잘못된 경우 오류 메시지가 표시됩니다. 동시에 열 수 있는 모델, 버텍스 또는 메시의 총 개수 제한에 도달하면 오류 메시지가 표시됩니다.  

자세한 내용은 [지원되는 콘텐츠 사양](#supported-content-specifications) 및 [파일 및 모델 제한 사항](#file-and-model-limitations)을 참조하세요.

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>3D 모델이 로드되지만 예상대로 표시되지 않습니다.

3D 뷰어 베타에서 3D 모델이 제대로 표시되지 않은 경우 에어 탭하여 도구 모음을 표시하고 **세부 정보** 를 선택합니다. 3D 뷰어 베타에서 지원하지 않는 파일의 측면이 경고로 강조 표시됩니다.

텍스처는 FBX 파일에 포함되어 있지 않기 때문에 확인할 수 있는 가장 일반적인 문제에서 누락될 수 있습니다. 이 경우 해당 모델은 흰색으로 표시됩니다. 이 문제는 작성 도구에서 텍스처 포함 옵션이 선택된 FBX로 내보냄으로써 작성 프로세스에서 해결할 수 있습니다.

자세한 내용은 [지원되는 콘텐츠 사양](#supported-content-specifications) 및 [3D 뷰어 베타용 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta)를 참조하세요.

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>3D 모델을 보는 동안 성능이 저하됩니다.

3D 모델을 로드하고 볼 때 모델의 복잡성, 동시에 열린 모델의 개수 또는 활성 애니메이션이 포함된 모델의 개수로 인해 성능이 영향을 받을 수 있습니다.

자세한 내용은 [3D 뷰어 베타용 3D 모델 최적화](#optimizing-3d-models-for-3d-viewer-beta) 및 [파일 및 모델 제한 사항](#file-and-model-limitations)을 참조하세요.

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>HoloLens에서 FBX 파일을 열면 3D 뷰어 베타에서 열리지 않습니다.

3D 뷰어 베타를 설치하면 자동으로 .fbx 파일 확장과 연결됩니다.

FBX 파일을 열려고 시도할 때 Microsoft Store로 지시하는 대화 상자가 표시되면 현재 HoloLens에서 .fbx 파일 확장과 연결된 앱이 없는 것입니다.

3D 뷰어 베타가 설치되어 있는지 확인합니다. 설치되어 있지 않은 경우 HoloLens의 Microsoft Store에서 다운로드합니다.

3D 뷰어 베타가 이미 설치되어 있는 경우 3D 뷰어 베타를 실행하고 파일을 다시 엽니다. 문제가 계속되면 3D 뷰어 베타를 제거하고 다시 설치합니다. .fbx 파일 확장명이 3D 뷰어 베타와 다시 연결됩니다.

FBX 파일을 열려고 시도할 때 3D 뷰어 베타가 아닌 다른 앱이 열리는 경우 해당 앱은 3D 뷰어 베타 설치 후에 설치되었으며 .fbx 파일 확장과 연결된 것으로 보입니다. 3D 뷰어 베타를 .fbx 파일 확장에 연결하려는 경우 3D 뷰어 베타를 제거한 후 다시 설치합니다.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3D 뷰어 베타의 파일 열기 단추로 앱을 시작할 수 없습니다.

**파일 열기** 단추를 클릭하면 HoloLens에서 파일 선택기 기능과 연결된 앱이 열립니다. OneDrive가 설치된 경우 **파일 열기** 단추로 OneDrive를 실행해야 합니다. 그러나 현재 HoloLens에 설치된 파일 선택기 기능과 연결되어 있는 앱이 없는 경우 Microsoft Store로 리디렉션됩니다.

**파일 열기** 단추로 OneDrive가 아닌 다른 앱이 실행되는 경우 해당 앱은 OneDrive 이후에 설치되었으며 파일 선택기 기능과 연결된 것으로 보입니다. 3D 뷰어 베타에서 **파일 열기** 단추로 OneDrive를 실행하려는 경우 OneDrive를 제거하고 다시 설치합니다.

**파일 열기** 단추가 활성화되지 않은 경우 3D 뷰어 베타에서 한 번에 열 수 있는 모델의 제한에 도달했을 수 있습니다. 3D 뷰어 베타에서 40개의 모델을 연 경우 모델을 추가로 열려면 먼저 일부를 닫아야 합니다.

## <a name="additional-resources"></a>추가 리소스

- [지원 포럼](http://forums.hololens.com/categories/3d-viewer-beta) - 보관 목적으로만 사용됩니다. 이 포럼은 더 이상 활성 상태가 아닙니다.
- [타사 알림](https://www.microsoft.com/{lang-locale}/legal/products)
