---
title: HoloLens에서 파일 찾기 및 저장
description: HoloLens에서 파일 탐색기를 사용 하 여 혼합 현실 장치에서 파일을 열고, 보고, 관리 하는 방법에 대해 알아봅니다.
keywords: 방법, 파일 선택기, 파일, 사진, 비디오, 그림, OneDrive, 저장소, 파일 탐색기, hololens
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033186"
---
# <a name="find-open-and-save-files-on-hololens"></a>HoloLens에서 파일 찾기, 열기 및 저장

사진 및 비디오를 포함 하 여 HoloLens에서 만드는 파일은 HoloLens 장치에 직접 저장 됩니다. Windows 10에서 파일을 관리 하는 것과 동일한 방식으로 뷰를 보고 관리 합니다.

- 파일 탐색기 앱을 사용 하 여 로컬 폴더에 액세스
- 앱의 저장소 내에 있습니다.
- 특수 폴더 (예: 비디오 또는 음악 라이브러리)
- 앱 및 파일 선택기 (예: OneDrive)를 포함 하는 저장소 서비스 사용.
- MTP (미디어 전송 프로토콜) 지원을 사용 하 여 USB 케이블을 사용 하 여 HoloLens에 연결 된 데스크톱 PC를 사용 합니다.

## <a name="view-files-on-hololens-using-file-explorer"></a>파일 탐색기를 사용 하 여 HoloLens에서 파일 보기

> [HoloLens 용 RS4 (Windows 10 4 월 2018 업데이트)](/windows/mixed-reality/release-notes-april-2018)의 모든 HoloLens 2 장치 및 HoloLens (첫 번째 gen)에 적용 됩니다.

HoloLens의 파일 탐색기를 사용 하 여 3d 개체, 문서 및 그림을 비롯 한 장치에서 파일을 보고 관리할 수 있습니다. 시작 하려면    >  **모든 앱**   >  **파일 탐색기** 시작으로 이동 합니다.

> [!TIP]
> 파일 탐색기에 나열 된 파일이 없는 경우 왼쪽 위 창에서 **이 장치** 를 선택 합니다.

파일 탐색기에 파일이 표시 되지 않으면 "최근" 필터가 활성화 되어 있을 수 있습니다 (왼쪽 창에 클록 아이콘이 강조 표시 됨). 이 문제를 해결 하려면 왼쪽 창 (시계 아이콘 아래)에서 **이 장치** 문서 아이콘을 선택 하거나 메뉴를 열고 **이 장치** 를 선택 합니다.

## <a name="find-and-view-your-photos-and-videos"></a>사진과 동영상 찾기 및 보기

[혼합 현실 캡처](holographic-photos-and-videos.md) 를 사용 하면 HoloLens에 대 한 현실 사진과 비디오를 혼합 하 여 사용할 수 있습니다.  이러한 사진과 비디오는 장치의 카메라 롤 폴더에 저장 됩니다.

다음을 수행 하 여 HoloLens 된 사진과 비디오에 액세스할 수 있습니다.

- [사진 앱](holographic-photos-and-videos.md)을 통해 직접 카메라 롤에 액세스 합니다.
- 사진과 비디오를 OneDrive에 동기화 하 여 사진 및 비디오를 클라우드 저장소에 업로드 합니다.
- [Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)의 혼합 현실 캡처 페이지를 사용 합니다.

### <a name="photos-app"></a>사진 앱

사진 앱은 **시작** 메뉴의 기본 앱 중 하나 이며 HoloLens를 사용 하 여 기본 제공 됩니다. [사진 앱을 사용 하 여 콘텐츠를 보는](holographic-photos-and-videos.md)방법에 대해 자세히 알아보세요.

Microsoft Store에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 설치 하 여 사진을 다른 장치와 동기화 할 수도 있습니다.

### <a name="onedrive-app"></a>OneDrive 앱

[OneDrive](https://onedrive.live.com/) 를 사용 하면 모든 장치 및 모든 사용자에 게 사진과 비디오를 액세스, 관리 및 공유할 수 있습니다. HoloLens에서 캡처된 사진과 비디오에 액세스 하려면 HoloLens의 Microsoft Store에서 [OneDrive 앱](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 을 다운로드 합니다. 다운로드 한 후 OneDrive 앱을 열고 **설정**  >  **카메라 업로드** 를 선택한 후 **카메라 업로드** 를 켭니다.

### <a name="connect-to-a-pc"></a>PC에 커넥트

HoloLens에서 [Windows 10 4 월 2018 업데이트](/windows/mixed-reality/release-notes-april-2018) 이상을 실행 하는 경우 MTP (미디어 전송 프로토콜)를 사용 하 여 장치에서 사진과 비디오를 검색 하는 데 USB 케이블을 사용 하 여 HoloLens를 Windows 10 PC에 연결할 수 있습니다. 장치에 PIN 또는 암호가 설정 되어 있는 경우 파일을 검색 하기 위해 장치의 잠금이 해제 되었는지 확인 해야 합니다.  

[Windows 장치 포털](/windows/mixed-reality/using-the-windows-device-portal)을 사용 하도록 설정한 경우이를 사용 하 여 장치에 저장 된 사진과 비디오를 찾아보고 검색 하 고 관리할 수 있습니다.

## <a name="access-files-within-an-app"></a>앱 내의 파일 액세스

응용 프로그램이 장치에 파일을 저장 하는 경우 해당 응용 프로그램을 사용 하 여 파일에 액세스할 수 있습니다.

### <a name="requesting-files-from-another-app"></a>다른 앱에서 파일 요청

응용 프로그램은 [파일 선택기](/windows/mixed-reality/app-model#file-pickers)를 사용 하 여 파일을 저장 하거나 다른 앱에서 파일을 열도록 요청할 수 있습니다.

### <a name="known-folders"></a>알려진 폴더

HoloLens는 앱이 액세스할 수 있는 권한을 요청할 수 있는 많은 수의 [알려진 폴더](/windows/mixed-reality/app-model#known-folders) 를 지원 합니다.

## <a name="view-hololens-files-on-your-pc"></a>PC에서 HoloLens 파일 보기

다른 모바일 장치와 마찬가지로, MTP (미디어 전송 프로토콜)를 사용 하 여 데스크톱 pc에 HoloLens 연결 하 고 PC에서 파일 탐색기를 열어 쉽게 전송할 수 있도록 HoloLens 라이브러리에 액세스 합니다.

PC의 파일 탐색기에서 HoloLens 파일을 보려면 다음을 수행 합니다.

1. HoloLens에 로그인 한 다음 HoloLens 함께 제공 된 USB 케이블을 사용 하 여 PC에 연결 합니다.

1. **장치 열기를 선택 하 여 파일 탐색기** 에서 파일을 보거나 PC에서 파일 탐색기를 열고 장치로 이동 합니다.

HoloLens에 대 한 정보를 보려면 PC의 파일 탐색기에서 장치 이름을 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 합니다.

> [!NOTE]
> HoloLens (첫 번째 gen)는 외부 하드 드라이브나 SD 카드에 연결 하는 것을 지원 하지 않습니다.

## <a name="sync-to-the-cloud"></a>클라우드로 동기화

HoloLens의 사진 및 기타 파일을 클라우드로 동기화 하려면 HoloLens에 OneDrive를 설치 하 고 설정 합니다. OneDrive를 얻으려면 HoloLens의 Microsoft Store에서 검색 합니다.

HoloLens는 앱 파일과 데이터를 백업 하지 않으므로 OneDrive 하는 데 중요 한 내용을 저장 하는 것이 좋습니다. 이렇게 하면 장치를 초기화 하거나 앱을 제거 하는 경우 정보가 백업 됩니다.
