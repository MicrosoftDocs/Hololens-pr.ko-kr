---
title: 영향을 주는 지침
description: GitHub-flavored Markdown를 사용 하 여 docs.microsoft.com 플랫폼에서 HoloLens 문서에 참여 하는 방법을 알아봅니다.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: b1efaa77a4b96ed4b55e84147448cbfbc706d677
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659117"
---
# <a name="contributing-to-the-hololens-documentation"></a>HoloLens 설명서에 기여

[HoloLens 설명서](https://github.com/MicrosoftDocs/Hololens)를 시작 합니다. 이 리포지토리에서 만들거나 편집 하는 모든 문서는 **공용에 표시 됩니다.** 

HoloLens 문서는 markdig 기능에서 GitHub-flavored Markdown를 사용 하는 docs.microsoft.com 플랫폼에 표시 됩니다. 이 리포지토리에서 편집 하는 콘텐츠는/hololens.에서 표시 되는 스타일 있는 페이지로 서식 지정 됩니다.

이 페이지에서는 Markdown 기본 사항에 기여 하 고 연결 하는 데 필요한 기본 단계 및 지침을 설명 합니다. 참가 해 주셔서 감사 합니다.

## <a name="available-repos"></a>사용 가능한 리포지토리

| 리포지토리 이름 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-현실](/windows/mixed-reality) |
| VR 매니아 가이드 | [MicrosoftDocs/mixed-현실/열성적인](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>시작하기 전에

계정이 아직 없는 경우 [GitHub 계정을 만들어야](https://github.com/join)합니다.

>[!NOTE]
>microsoft 직원 인 경우 [microsoft 오픈 소스 포털](https://repos.opensource.microsoft.com/)의 microsoft 별칭에 GitHub 계정을 연결 하세요. **"Microsoft"** 및 **"MicrosoftDocs"** 조직에 참여 합니다.

GitHub 계정을 설정할 때 다음과 같은 보안 예방 조치를 권장 합니다.
- [GitHub 계정에 대 한 강력한 암호](https://github.com/settings/admin)를 만듭니다.
- [2 단계 인증](https://github.com/settings/two_factor_authentication/configure)을 사용 하도록 설정 합니다.
- [복구 코드](https://github.com/settings/auth/recovery-codes) 를 안전한 장소에 저장 합니다.
- [공개 프로필 설정을](https://github.com/settings/profile)업데이트 합니다.
   - 사용자의 이름을 설정 하 고 *전자 메일 주소를 표시 하지 않도록* *공용 전자 메일* 을 설정 하는 것이 좋습니다.
   - 사용자가 참여 하는 문서 페이지에 미리 보기가 표시 되기 때문에 프로필 사진을 업로드 하는 것이 좋습니다.
- 명령줄을 사용 하려는 경우 [Windows에 대해 Git 자격 증명 관리자](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)를 설정 하는 것이 좋습니다. 이렇게 하면 기여를 할 때마다 암호를 입력할 필요가 없습니다.

게시 시스템은 GitHub 연결 되어 있으므로 이러한 단계가 중요 합니다. GitHub 별칭을 사용 하 여 각 아티클에 대 한 작성자 또는 참가자로 나열 됩니다.

## <a name="editing-an-existing-article"></a>기존 문서 편집

다음 워크플로를 사용 하 여 웹 브라우저에서 GitHub를 통해 *기존 문서* 를 업데이트 합니다.

1. "Mixed reality-docs" 폴더에서 편집 하려는 문서로 이동 합니다.

2. 오른쪽 위에 있는 편집 단추 (연필 아이콘)를 선택 합니다.

   ![문서를 편집 합니다.](images/editpage.png)

   그러면 기본 분기 _master_ 에서 삭제 가능한 분기가 자동으로 분기 됩니다.

   > [!NOTE]
   > 이 문서에는 Microsoft에서 더 이상 사용 하지 않는 문서인 _master_ 에 대 한 참조가 포함 되어 있습니다. 소프트웨어에서 용어가 제거되면 이 문서에서 해당 용어가 제거됩니다.
   
3. [Markdown 기본 사항](#markdown-basics)에 따라 문서의 내용을 편집 합니다.

4. 각 문서의 맨 위에 있는 메타 데이터를 업데이트 합니다.

   * **제목**: 문서를 볼 때 브라우저 탭에 표시 되는 페이지 제목입니다. 페이지 제목은 SEO 및 인덱싱에 사용 되므로 필요한 경우를 제외 하 고는 제목을 변경 하지 않습니다. 단, 설명서를 공개 하기 전에는이 작업이 중요 하지 않습니다.
   * **설명**: SEO 및 검색을 향상 시키는 아티클의 콘텐츠에 대 한 간단한 설명을 작성 합니다.
   * **작성자**: 페이지의 기본 소유자 인 경우 여기에 GitHub 별칭을 추가 합니다.
   * **ms author**: 페이지의 기본 소유자 인 경우 여기에 Microsoft 별칭을 추가 @microsoft.com 합니다 (별칭만 필요 없음).
   * **ms. 날짜**: 페이지에 주요 콘텐츠를 추가 하는 경우에는 날짜를 업데이트 하지만 설명, 서식, 문법 또는 철자와 같은 픽스는 업데이트 하지 않습니다.
   * **키워드**: SEO의 키워드 지원 (검색 엔진 최적화). 사용자의 문서와 관련 된 키워드를 쉼표와 공백으로 구분 하 고 목록에서 마지막 키워드 뒤에 문장 부호는 추가 하지 않습니다. 모든 문서에 적용 되는 전역 키워드는 다른 곳에서 관리 되므로 추가할 필요가 없습니다. 
   
5. 문서 편집을 완료 한 후 아래로 스크롤하여 **파일 변경 내용 제안** 을 선택 합니다.

6. 다음 페이지에서 **끌어오기 요청 만들기** 를 선택 하 여 자동으로 만든 분기를 기본 분기 _master_ 에 병합 합니다.

7. 편집 하려는 다음 문서에 대해 위의 단계를 반복 합니다.

## <a name="renaming-or-deleting-an-existing-article"></a>기존 아티클 이름 바꾸기 또는 삭제

변경 시 기존 아티클의 이름을 바꾸거나 삭제 하는 경우에는 리디렉션을 추가 해야 합니다. 이렇게 하면 기존 문서에 대 한 링크를 가진 모든 사용자가 올바른 위치가 됩니다. 리디렉션은 리포지토리의 루트에 있는 파일의 .openpublishing.redirection.js에 의해 관리 됩니다.

.openpublishing.redirection.js에 대 한 리디렉션을 추가 하려면 배열에 항목을 추가 합니다 `redirections` .

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- 는 `source_path` 제거 하는 이전 아티클의 상대 저장소 경로입니다. 경로는로 시작 `mixed-reality-docs` 하 고로 끝나야 `.md` 합니다.

- 는 `redirect_url` 이전 문서에서 새 아티클에 대 한 상대 공용 URL입니다. 이 URL은  `mixed-reality-docs` `.md` 리포지토리 경로가 아니라 공용 url을 참조 하므로이 url에 또는가 포함 되지 않아야 합니다. 를 사용 하 여 새 문서 내의 섹션에 연결할 `#section` 수 있습니다. 필요한 경우 여기서 다른 사이트에 대 한 절대 경로를 사용할 수도 있습니다.

- `redirect_document_id` 이전 파일의 문서 ID를 유지할지 여부를 나타냅니다. 기본값은 `false`입니다. `true`리디렉션된 아티클의 특성 값을 유지 하려는 경우에 사용 합니다 `ms.documentid` . 문서 ID를 유지 하는 경우 페이지 보기 및 순위와 같은 데이터가 대상 문서에 전송 됩니다. 리디렉션이 동일한 콘텐츠의 일부만 포함하는 다른 문서에 대한 포인터가 아니라 주로 이름 바꾸기인 경우 이 작업을 수행하세요.

리디렉션을 추가 하는 경우에도 이전 파일을 삭제 해야 합니다.

## <a name="creating-a-new-article"></a>새 문서 만들기

다음 워크플로를 사용 하 여 웹 브라우저에서 GitHub를 통해 설명서 리포지토리에서 *새 문서를 만들* 수 있습니다.

1. 오른쪽 위에 있는 **포크** 단추를 사용 하 여 MicrosoftDocs/mixed의 기본 분기 _마스터_ 에서 포크를 만듭니다.

   ![현재 "master"로 명명 된 기본 분기를 포크 합니다.](images/forkbranch.png)

   > [!NOTE]
   > 이 문서에는 Microsoft에서 더 이상 사용 하지 않는 문서인 _master_ 에 대 한 참조가 포함 되어 있습니다. 소프트웨어에서 용어가 제거되면 이 문서에서 해당 용어가 제거됩니다.
   
2. "Mixed reality-docs" 폴더의 오른쪽 위에서 **새 파일 만들기** 를 선택 합니다.

3. 문서에 대 한 페이지 이름 (공백 대신 하이픈을 사용 하 고 구두점 또는 아포스트로피를 사용 하지 않음)을 만든 후 ".ma"를 추가 합니다.

   ![새 페이지의 이름을로 합니다.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >"Mixed reality-docs" 폴더 내에서 새 문서를 만들어야 합니다. 새 파일 이름 줄에서 "/mixed-reality-docs/"를 확인 하 여이를 확인할 수 있습니다.

4. 새 페이지 위쪽에 다음 메타 데이터 블록을 추가 합니다.

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. 앞서 [기존 문서 편집](#editing-an-existing-article)에서 설명한 대로 관련 메타 데이터 필드를 입력 합니다.

6. [Markdown 기본 사항을](#markdown-basics)사용 하 여 문서 콘텐츠를 작성 합니다.

7. `## See also`문서의 맨 아래에 있는 섹션을 다른 관련 문서에 대 한 링크와 함께 추가 합니다.

8. 완료 되 면 **새 파일 커밋** 을 선택 합니다.

9. **새 끌어오기 요청** 을 선택 하 고 포크의 _마스터_ 분기를 MicrosoftDocs/mixed-현실 _마스터_ 에 병합 합니다. 화살표가 올바른 대상을 가리키는지 확인 합니다.

   ![포크에서 MicrosoftDocs/mixed reality로 끌어오기 요청 만들기](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown 기본 사항

다음 리소스는 Markdown 언어를 사용 하 여 문서를 편집 하는 방법을 배우는 데 도움이 됩니다.

- [Markdown 기본 사항](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Docs.microsoft.com에 대 한 Markdown 쓰기에 대 한 추가 리소스](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>테이블 추가

스타일 docs.microsoft.com 스타일을 지정 하는 방식 때문에 인라인 CSS를 시도 하더라도 테두리나 사용자 지정 스타일은 없습니다. 짧은 시간 동안 작동 하는 것 처럼 보이지만 결국 플랫폼은 테이블에서 스타일을 제거 합니다. 따라서 미리 계획 하 고 테이블을 단순하게 유지 합니다. Markdown 테이블을 쉽게 만드는 사이트는 다음과 같습니다. [Tables 생성기]] ( https://www.tablesgenerator.com/markdown_tables) .

[Visual Studio Code에 대 한 Docs Markdown 확장](/teamblog/docs-extension) 은 [Visual Studio Code (아래 참조)](#using-visual-studio-code) 를 사용 하 여 문서를 편집 하는 경우에도 테이블을 쉽게 생성할 수 있습니다.

### <a name="adding-images"></a>이미지 추가

리포지토리의 "mixed-reality-docs/images" 폴더에 이미지를 업로드한 다음, 문서에서 적절하게 참조해야 합니다. 이미지는 자동으로 전체 크기로 표시됩니다. 즉, 큰 이미지가 문서의 전체 너비를 채웁니다. 이미지를 업로드하기 전에 이미지의 크기를 미리 조정하는 것이 좋습니다. 권장 너비는 600픽셀에서 700픽셀 사이이지만, 조밀한 스크린샷 또는 스크린샷의 일부인 경우 크기를 조정해야 합니다.

>[!IMPORTANT]
>병합하기 전에 포크된 리포지전에만 이미지를 업로드할 수 있습니다. 따라서 문서에 이미지를 추가하려는 경우 [Visual Studio Code 사용하여](#using-visual-studio-code) 먼저 포크의 "images" 폴더에 이미지를 추가하거나 웹 브라우저에서 다음을 수행했는지 확인해야 합니다.
>
>1. MicrosoftDocs/mixed-reality 리포지토리를 포크했습니다.
>2. 포크에서 문서를 편집했습니다.
>3. 문서에서 참조하는 이미지를 포크의 "mixed-reality-docs/images" 폴더에 업로드했습니다.
>4. 포크를 MicrosoftDocs/mixed-reality _마스터_ 분기에 병합하는 **끌어오기 요청을** 만들었습니다.
>
>고유한 포크된 리포지던스를 설정하는 방법을 알아보려면 [새 문서 를 만들기](#creating-a-new-article)위한 지침을 따르세요.

## <a name="previewing-your-work"></a>작업 미리 보기

웹 브라우저를 통해 GitHub 편집하는 동안 커밋하기 전에 페이지 위쪽의 **미리 보기** 탭을 선택하여 작업을 미리 볼 수 있습니다. 

>[!NOTE]
>review.docs.microsoft.com 변경 내용 미리 보기는 Microsoft 직원에게만 제공됩니다.

Microsoft 직원: 기여가 기본 분기인 _마스터_ 에 병합된 경우 콘텐츠를 검토한 후 /hololens?branch=master> <공개할 수 있습니다. 왼쪽 열의 목차를 사용하여 문서를 찾습니다.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>브라우저에서 편집 및 데스크톱 클라이언트를 사용하여 편집

브라우저에서 편집하는 것이 빠르게 변경하는 가장 쉬운 방법이기는 하지만 다음과 같은 몇 가지 단점이 있습니다.

- 맞춤법 검사를 받지 않습니다.
- 다른 문서에 대한 스마트 링크는 얻을 수 없습니다(문서의 파일 이름을 수동으로 입력해야 합니다).
- 이미지를 업로드하고 참조하는 것은 번거로울 수 있습니다.

이러한 문제를 처리하지 않려면 기여할 때 몇 가지 유용한 확장이 [있는 Visual Studio Code](https://code.visualstudio.com/) 같은 데스크톱 [클라이언트를](#useful-extensions) 사용합니다.

## <a name="using-visual-studio-code"></a>Visual Studio Code 사용

[위에](#editing-in-the-browser-vs-editing-with-a-desktop-client)나열된 이유로 데스크톱 클라이언트를 사용하여 웹 브라우저 대신 설명서를 편집하는 것이 좋습니다. [Visual Studio Code](https://code.visualstudio.com/)를 사용하는 것이 좋습니다.

### <a name="setup"></a>설치

다음 단계에 따라 이 리포지 작동하도록 Visual Studio Code 구성합니다.

1. 웹 브라우저에서:
    1. [PC용 Git을 설치합니다.](https://git-scm.com/downloads)
    2. [Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.
    3. [MicrosoftDocs/mixed-reality를](#creating-a-new-article) 포크합니다(아직 없는 경우).
    4. 포크에서 **복제 또는 다운로드를** 선택하고 URL을 복사합니다.
2. Visual Studio Code 포크의 로컬 복제본을 만듭니다.
    1. **보기** 메뉴에서 명령 **팔레트를** 선택합니다.
    2. "Git: Clone"을 입력합니다.
    3. 복사한 URL을 붙여넣습니다.
    4. PC에 클론을 저장할 위치를 선택합니다.
    5. 팝업에서 **리포지점 열기를** 선택합니다.

### <a name="editing-documentation"></a>설명서 편집

다음 워크플로를 사용하여 Visual Studio Code 설명서를 변경합니다.

>[!NOTE]
>문서를 [편집](#editing-an-existing-article) 및 [만들기](#creating-a-new-article) 위한 모든 지침과 위의 [Markdown 편집 기본 사항도](#markdown-basics)Visual Studio Code 사용할 때 적용됩니다.

1. 복제된 포크가 공식 리포지토와 함께 최신인지 확인합니다.

   1. 웹 브라우저에서 끌어오기 요청을 만들어 MicrosoftDocs/mixed-reality, _master_ 의 기본 분기에 있는 다른 기여자의 최근 변경 내용을 포크로 동기화합니다(화살표가 올바른 대상을 가리키는지 확인).
      
      ![MicrosoftDocs/mixed-reality에서 포크로 변경 내용 동기화](images/sync-repos.png)
      
   2. Visual Studio Code 동기화 단추를 선택하여 새로 업데이트된 포크를 로컬 복제본에 동기화합니다.
      
      ![동기화 단추 이미지를 클릭합니다.](images/sync-clone.png)
      
2. Visual Studio Code 사용하여 복제된 리포지션에서 아티클을 만들거나 편집합니다.

   1. 하나 이상의 아티클을 편집합니다(필요한 경우 "images" 폴더에 이미지 추가).
   
   2. **탐색기** 에서 변경 내용을 **저장합니다.**
      
      ![탐색기에서 "모두 저장" 선택](images/explorer-save.png)
      
   3. **소스 제어의** 모든 변경 내용을 **커밋합니다(메시지가** 표시되면 커밋 메시지 작성).
   
      ![소스 제어에서 "모두 커밋" 선택](images/source-control-commit.png)
      
   4. **동기화** 단추를 선택하여 변경 내용을 원본으로 다시 동기화합니다(GitHub 포크).
      
      ![동기화 단추를 클릭합니다.](images/sync-back.png)
      
3. 웹 브라우저에서 끌어오기 요청을 만들어 포크의 새 변경 내용을 MicrosoftDocs/mixed-reality _master에_ 다시 동기화합니다(화살표가 올바른 대상을 가리키는지 확인).

   ![포크에서 MicrosoftDocs/mixed-reality로 끌어오기 요청 만들기](images/pr-to-master.png)

### <a name="useful-extensions"></a>유용한 확장

다음 Visual Studio Code 확장은 설명서를 편집할 때 유용합니다.

- [Visual Studio Code 대한 Docs Markdown 확장](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt+M을** 사용하여 다음과 같은 문서 제작 옵션 메뉴를 표시합니다.
   - 업로드한 이미지를 검색하고 참조합니다.
   - 목록, 테이블 및 문서별 호출(예: )과 같은 서식 지정을 `>[!NOTE]` 추가합니다.
   - 내부 링크 및 책갈피(페이지 내의 특정 섹션에 대한 링크)를 검색하고 참조합니다.
   - 서식 지정 오류가 강조 표시되어 있습니다(자세한 내용은 오류 위로 마우스를 가져가세요).
- [코드 맞춤법 검사기](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - 철자가 잘못된 단어에 밑줄이 표시됩니다. 철자가 잘못된 단어를 마우스 오른쪽 단추로 클릭하여 변경하거나 사전에 저장합니다.
