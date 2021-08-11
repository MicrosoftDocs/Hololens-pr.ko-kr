---
title: HoloLens 파일 찾기 및 저장
description: HoloLens 파일 탐색기 사용하여 혼합 현실 디바이스에서 파일을 열고, 보고, 관리하는 방법을 알아봅니다.
keywords: 방법, 파일 선택기, 파일, 사진, 비디오, 사진, OneDrive, 스토리지, 파일 탐색기, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ad210c9d31d8d7c226345618b6dfabf8457ee2398882935920d7b3217259a644
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664879"
---
# <a name="find-open-and-save-files-on-hololens"></a>HoloLens에서 파일 찾기, 열기 및 저장

사진 및 비디오를 포함하여 HoloLens 만든 파일은 HoloLens 디바이스에 직접 저장됩니다. Windows 10 파일을 관리하는 것과 동일한 방식으로 파일을 보고 관리합니다.

- 파일 탐색기 앱을 사용하여 로컬 폴더에 액세스
- 앱의 스토리지 내에 있습니다.
- 특수 폴더(예: 비디오 또는 음악 라이브러리)
- 앱 및 파일 선택기를 포함하는 스토리지 서비스 사용(예: OneDrive)
- USB 케이블을 사용하여 HoloLens 연결된 데스크톱 PC 사용, MTP(미디어 전송 프로토콜) 지원 사용

## <a name="view-files-on-hololens-using-file-explorer"></a>파일 탐색기 사용하여 HoloLens 파일 보기

> HoloLens Windows 10 [2018년 4월 업데이트(RS4)의 모든 HoloLens 2 디바이스 및 HoloLens(1세대)에](/windows/mixed-reality/release-notes-april-2018)적용됩니다.

HoloLens 파일 탐색기 사용하여 3D 개체, 문서 및 사진을 비롯한 디바이스의 파일을 보고 관리합니다. 시작    >  **모든 앱**   >  **파일 탐색기** 이동하여 시작합니다.

> [!TIP]
> 파일 탐색기 나열된 파일이 없는 경우 왼쪽 위 창에서 **이 디바이스를** 선택합니다.

파일 탐색기 파일이 표시되지 않으면 "최근" 필터가 활성 상태일 수 있습니다(왼쪽 창에 클록 아이콘이 강조 표시되어 있음). 이 문제를 해결하려면 왼쪽 창(시계 아이콘 아래)에서 **이 디바이스** 문서 아이콘을 선택하거나 메뉴를 열고 **이 디바이스** 를 선택합니다.

## <a name="find-and-view-your-photos-and-videos"></a>사진 및 비디오 찾기 및 보기

[혼합 현실 캡처를](holographic-photos-and-videos.md) 사용하면 혼합 현실 사진 및 비디오를 HoloLens 수 있습니다.  이러한 사진 및 비디오는 디바이스의 Camera Roll 폴더에 저장됩니다.

다음을 수행하여 HoloLens 함께 가져온 사진 및 비디오에 액세스할 수 있습니다.

- [사진 앱을](holographic-photos-and-videos.md)통해 카메라 롤에 직접 액세스합니다.
- 사진 및 비디오를 OneDrive 동기화하여 사진 및 비디오를 클라우드 스토리지에 업로드합니다.
- Windows 장치 포털 의 혼합 현실 캡처 페이지를 사용 하 여 [입니다.](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### <a name="photos-app"></a>앱 사진

사진 앱은 **시작** 메뉴의 기본 앱 중 하나이며 HoloLens 함께 기본 제공됩니다. [사진 앱을 사용하여 콘텐츠를 보는 방법에](holographic-photos-and-videos.md)대해 자세히 알아봅니다.

[Microsoft Store OneDrive 앱을](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 설치하여 사진을 다른 디바이스와 동기화할 수도 있습니다.

### <a name="onedrive-app"></a>앱 OneDrive

[OneDrive](https://onedrive.live.com/) 사용하면 모든 디바이스 및 사용자와 사진 및 비디오에 액세스하고 관리하고 공유할 수 있습니다. HoloLens 캡처한 사진 및 비디오에 액세스하려면 HoloLens Microsoft Store OneDrive [앱을](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 다운로드합니다. 다운로드되면 OneDrive 앱을 열고 카메라 업로드 **설정** 선택하고  >  **카메라** **업로드** 를 켭니다.

### <a name="connect-to-a-pc"></a>PC에 커넥트

HoloLens [2018년 4월 업데이트 Windows 10](/windows/mixed-reality/release-notes-april-2018) 실행하는 경우 USB 케이블을 사용하여 MTP(미디어 전송 프로토콜)를 사용하여 디바이스에서 사진 및 비디오를 찾아보는 Windows 10 PC에 HoloLens 연결할 수 있습니다. 디바이스에 PIN 또는 암호가 설정된 경우 파일을 찾아보기 위해 디바이스의 잠금이 해제되었는지 확인해야 합니다.  

[Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal)사용하도록 설정한 경우 디바이스에 저장된 사진 및 비디오를 찾아보고, 검색하고, 관리하는 데 사용할 수 있습니다.

## <a name="access-files-within-an-app"></a>앱 내의 파일에 액세스

애플리케이션이 디바이스에 파일을 저장하는 경우 해당 애플리케이션을 사용하여 액세스할 수 있습니다.

### <a name="requesting-files-from-another-app"></a>다른 앱에서 파일 요청

애플리케이션은 파일 선택기를 사용하여 파일을 저장하거나 다른 앱에서 파일을 열도록 요청할 수 [있습니다.](/windows/mixed-reality/app-model#file-pickers)

### <a name="known-folders"></a>알려진 폴더

HoloLens 앱이 액세스 권한을 요청할 수 있는 [여러 알려진 폴더를](/windows/mixed-reality/app-model#known-folders) 지원합니다.

## <a name="view-hololens-files-on-your-pc"></a>PC에서 HoloLens 파일 보기

다른 모바일 디바이스와 마찬가지로 MTP(미디어 전송 프로토콜)를 사용하여 데스크톱 PC에 HoloLens 연결하고 PC에서 파일 탐색기 열어 쉽게 전송할 수 있도록 HoloLens 라이브러리에 액세스합니다.

PC의 파일 탐색기 HoloLens 파일을 보려면 다음을 수행합니다.

1. HoloLens 로그인한 다음, HoloLens 함께 나온 USB 케이블을 사용하여 PC에 연결합니다.

1. **디바이스 열기를** 선택하여 파일 탐색기 파일을 보거나 PC에서 파일 탐색기 열고 디바이스로 이동합니다.

HoloLens 대한 정보를 보려면 PC의 파일 탐색기 디바이스 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성을** 선택합니다.

> [!NOTE]
> HoloLens(1세대)는 외부 하드 드라이브 또는 SD 카드에 대한 연결을 지원하지 않습니다.

## <a name="sync-to-the-cloud"></a>클라우드에 동기화

HoloLens 사진 및 기타 파일을 클라우드로 동기화하려면 HoloLens OneDrive 설치하고 설정합니다. OneDrive 얻으려면 HoloLens Microsoft Store 검색합니다.

HoloLens 앱 파일과 데이터를 백업하지 않으므로 중요한 OneDrive 저장하는 것이 좋습니다. 이렇게 하면 디바이스를 다시 설정하거나 앱을 제거하면 정보가 백업됩니다.
