---
title: 지침 제공
description: GitHub docs.microsoft.com 플랫폼의 HoloLens 문서에 기여하는 방법을 알아봅니다.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032965"
---
# <a name="contributing-to-the-hololens-documentation"></a>HoloLens 설명서에 기여

[HoloLens 설명서를 시작합니다.](https://github.com/MicrosoftDocs/Hololens) 이 리포지언에서 만들거나 편집하는 모든 문서는 **일반에 표시됩니다.** 

HoloLens 문서는 markdig 기능과 함께 GitHub 특징이 있는 Markdown을 사용하는 docs.microsoft.com 플랫폼에 표시됩니다. 이 리포지션에서 편집하는 콘텐츠는 /hololens에 표시된 스타일이 지정된 페이지로 서식이 지정됩니다.

이 페이지에서는 기여를 위한 기본 단계 및 지침과 Markdown 기본 사항 링크를 다룹니다. 기여해 주셔서 감사합니다!

## <a name="available-repos"></a>사용 가능한 리포지토리

| 리포지토리 이름 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-reality](/windows/mixed-reality) |
| VR 마인드 가이드 | [MicrosoftDocs/mixed-reality/사용자 가이드](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>시작하기 전에

계정이 없는 경우 [GitHub 계정을 만들어야](https://github.com/join)합니다.

>[!NOTE]
>Microsoft 직원인 경우 GitHub 계정을 [Microsoft 오픈 소스 포털](https://repos.opensource.microsoft.com/)의 Microsoft 별칭에 연결합니다. **"Microsoft"** 및 **"MicrosoftDocs" 조직에 가입합니다.**

GitHub 계정을 설정하는 경우 다음과 같은 보안 예방 조치도 권장합니다.
- GitHub [계정에 대한 강력한 암호를](https://github.com/settings/admin)만듭니다.
- [2단계 인증을](https://github.com/settings/two_factor_authentication/configure)사용하도록 설정합니다.
- 복구 [코드를](https://github.com/settings/auth/recovery-codes) 안전한 장소에 저장합니다.
- 공개 [프로필 설정을](https://github.com/settings/profile)업데이트합니다.
   - 이름을 설정하고 *공용 메일을* 내 이메일 *주소를 표시 안* 으로 설정하는 것이 좋습니다.
   - 기여하는 문서 페이지에 미리 보기가 표시되므로 프로필 사진을 업로드하는 것이 좋습니다.
- 명령줄을 사용하려는 경우 Windows [대한 Git 자격 증명 관리자](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)설정하는 것이 좋습니다. 이렇게 하면 기여할 때마다 암호를 입력할 필요가 없습니다.

게시 시스템은 GitHub 연결되므로 이러한 단계가 중요합니다. GitHub 별칭을 사용하여 각 문서의 작성자 또는 기여자로 나열됩니다.

## <a name="editing-an-existing-article"></a>기존 문서 편집

다음 워크플로를 사용하여 웹 *브라우저에서* GitHub 통해 기존 문서를 업데이트합니다.

1. "mixed-reality-docs" 폴더에서 편집하려는 문서로 이동합니다.

2. 오른쪽 위에서 편집 단추(연필 아이콘)를 선택합니다.

   ![아티클을 편집합니다.](images/editpage.png)

   그러면 삭제 가능한 분기가 기본 _분기인 마스터_ 에서 자동으로 분기됩니다.

   > [!NOTE]
   > 이 문서에는 Microsoft에서 더 이상 사용하지 않는 용어인 _마스터에_ 대한 참조가 포함되어 있습니다. 소프트웨어에서 용어가 제거되면 이 문서에서 해당 용어가 제거됩니다.
   
3. Markdown 기본 사항 에 따라 문서의 내용을 [편집합니다.](#markdown-basics)

4. 각 문서의 맨 위에 있는 메타데이터를 업데이트합니다.

   * **title**: 문서를 볼 때 브라우저 탭에 표시되는 페이지 제목입니다. 페이지 제목은 SEO 및 인덱싱에 사용되므로 필요한 경우가 아니면 제목을 변경하지 마세요(설명서를 공개하기 전에 덜 중요함).
   * **description**: SEO 및 검색을 향상시키는 문서의 콘텐츠에 대한 간략한 설명을 작성합니다.
   * **author**: 페이지의 기본 소유자인 경우 여기에 GitHub 별칭을 추가합니다.
   * **ms.author:** 페이지의 기본 소유자인 경우 여기에 Microsoft 별칭을 추가합니다(은 필요하지 않으며 @microsoft.com 별칭만 필요).
   * **ms.date:** 페이지에 주요 콘텐츠를 추가하는 경우 날짜를 업데이트하지만 설명, 서식 지정, 문법 또는 맞춤법과 같은 수정은 업데이트하지 않습니다.
   * **키워드:** 키워드는 SEO(검색 엔진 최적화)를 지원합니다. 쉼표와 공백으로 구분된 키워드를 추가합니다. 이 키워드는 문서에만 해당되지만 목록의 마지막 키워드 뒤의 문장 부호는 추가하지 않습니다. 모든 아티클에 적용되는 전역 키워드는 다른 곳에서 관리되기 때문에 추가할 필요가 없습니다. 
   
5. 문서 편집을 완료했으면 아래로 스크롤하여 **파일 변경 제안을** 선택합니다.

6. 다음 페이지에서 **끌어오기 요청 만들기를** 선택하여 자동으로 생성된 분기를 기본 _분기인 마스터_ 에 병합합니다.

7. 편집하려는 다음 문서에 대해 위의 단계를 반복합니다.

## <a name="renaming-or-deleting-an-existing-article"></a>기존 아티클 이름 바꾸기 또는 삭제

변경 내용이 기존 아티클의 이름을 바꾸거나 삭제하는 경우 리디렉션을 추가해야 합니다. 이렇게 하면 기존 문서에 대한 링크가 있는 모든 사용자가 올바른 위치에 있게 됩니다. 리디렉션은 리포지션 루트의 .openpublishing.redirection.json 파일을 통해 관리됩니다.

.openpublishing.redirection.json에 리디렉션을 추가하려면 배열에 항목을 추가합니다. `redirections`

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`는 제거하려는 이전 문서에 대한 상대 리포지토리 경로입니다. 경로가 로 시작하고 로 `mixed-reality-docs` 끝나야 `.md` 합니다.

- `redirect_url`는 이전 문서에서 새 아티클까지의 상대 공용 URL입니다. 이 **URL은** `mixed-reality-docs` `.md` 리포지토리 경로가 아닌 공용 URL을 참조하기 때문에 또는 을 포함하지 않는지 확인합니다. 를 사용하여 새 아티클 내의 섹션에 연결할 `#section` 수 있습니다. 필요한 경우 여기에서 다른 사이트에 대한 절대 경로를 사용할 수도 있습니다.

- `redirect_document_id` 는 이전 파일의 문서 ID를 유지할지 여부를 나타냅니다. 기본값은 `false`입니다. `true` `ms.documentid` 리디렉션된 아티클에서 특성 값을 유지하려면 를 사용합니다. 문서 ID를 유지하면 페이지 보기 및 순위와 같은 데이터가 대상 문서로 전송됩니다. 리디렉션이 동일한 콘텐츠의 일부만 포함하는 다른 문서에 대한 포인터가 아니라 주로 이름 바꾸기인 경우 이 작업을 수행하세요.

리디렉션을 추가하는 경우 이전 파일도 삭제해야 합니다.

## <a name="creating-a-new-article"></a>새 문서 만들기

다음 워크플로를 사용하여 웹 브라우저에서 GitHub 통해 설명서 리포지션에 *새 문서를 만듭니다.*

1. 오른쪽 위에 있는 포크 단추를 사용하여 MicrosoftDocs/mixed-reality의 기본 _분기인 마스터_ 에서 **포크를** 만듭니다.

   ![현재 이름이 "master"인 기본 분기를 포크합니다.](images/forkbranch.png)

   > [!NOTE]
   > 이 문서에는 Microsoft에서 더 이상 사용하지 않는 용어인 _마스터에_ 대한 참조가 포함되어 있습니다. 소프트웨어에서 용어가 제거되면 이 문서에서 해당 용어가 제거됩니다.
   
2. "mixed-reality-docs" 폴더의 오른쪽 위에서 **새 파일 만들기를** 선택합니다.

3. 문서의 페이지 이름을 만들고(공백 대신 하이픈을 사용하고 문장 부호 또는 아포스트로피를 사용하지 마세요) ".md"를 추가합니다.

   ![새 페이지의 이름을 지정합니다.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >"mixed-reality-docs" 폴더 내에서 새 문서를 만들어야 합니다. 새 파일 이름 줄에서 "/mixed-reality-docs/"를 확인하여 이를 확인할 수 있습니다.

4. 새 페이지의 맨 위에 다음 메타데이터 블록을 추가합니다.

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

5. 기존 문서 편집에서 설명한 대로 관련 메타데이터 필드를 [입력합니다.](#editing-an-existing-article)

6. [Markdown 기본 을](#markdown-basics)사용하여 문서 콘텐츠를 작성합니다.

7. 다른 `## See also` 관련 문서에 대한 링크가 있는 섹션을 문서의 맨 아래에 추가합니다.

8. 완료되면 **새 파일 커밋을** 선택합니다.

9. **새 끌어오기 요청을** 선택하고 포크의 _마스터_ 분기를 MicrosoftDocs/mixed-reality _master에_ 병합합니다(화살표가 올바른 대상을 가리키는지 확인).

   ![포크에서 MicrosoftDocs/mixed-reality로 끌어오기 요청을 만듭니다.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown 기본 사항

다음 리소스는 Markdown 언어를 사용하여 설명서를 편집하는 방법을 알아보는 데 도움이 됩니다.

- [Markdown 기본 사항](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [docs.microsoft.com Markdown을 작성하기 위한 추가 리소스](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>테이블 추가

docs.microsoft.com 스타일 테이블의 방식 때문에 인라인 CSS를 사용해도 테두리 또는 사용자 지정 스타일이 없습니다. 짧은 기간 동안 작동하는 것처럼 보이지만, 결국 플랫폼은 테이블에서 스타일을 제거합니다. 따라서 미리 계획하고 테이블을 단순하게 유지합니다. Markdown 테이블을 쉽게 만드는 사이트는 다음과 같습니다. [테이블 생성기]( https://www.tablesgenerator.com/markdown_tables) .

[또한 Visual Studio Code 대한 Docs Markdown 확장을](/teamblog/docs-extension) 사용하면 [Visual Studio Code(아래 참조)를](#using-visual-studio-code) 사용하여 문서를 편집하는 경우 테이블을 쉽게 생성할 수 있습니다.

### <a name="adding-images"></a>이미지 추가

리포지토리의 "mixed reality-docs/images" 폴더에 이미지를 업로드 한 다음 문서에서 적절 하 게 참조 해야 합니다. 이미지가 자동으로 전체 크기로 표시 됩니다. 즉, 큰 이미지는 문서의 전체 너비를 채웁니다. 이미지를 업로드 하기 전에 미리 크기를 조정 하는 것이 좋습니다. 권장 되는 너비는 600 픽셀에서 700 픽셀 사이 이지만, 조밀한 스크린샷 또는 스크린 샷의 분수 인 경우 크기를 조정 하거나 축소 해야 합니다.

>[!IMPORTANT]
>병합 하기 전에 분기 리포지토리에만 이미지를 업로드할 수 있습니다. 따라서 문서에 이미지를 추가 하려면 먼저 [Visual Studio Code를 사용](#using-visual-studio-code) 하 여 포크의 "images" 폴더에 이미지를 추가 하거나 웹 브라우저에서 다음을 수행 해야 합니다.
>
>1. MicrosoftDocs/mixed reality 리포지토리를 분기 합니다.
>2. 포크에서 문서를 편집 했습니다.
>3. 문서에서 참조 하는 이미지를 포크의 "mixed reality-docs/images" 폴더에 업로드 했습니다.
>4. 분기를 MicrosoftDocs/mixed reality _마스터_ 분기에 병합 하는 **끌어오기 요청** 을 만들었습니다.
>
>사용자 고유의 분기 리포지토리를 설정 하는 방법을 알아보려면 [새 문서 만들기](#creating-a-new-article)에 대 한 지침을 따르세요.

## <a name="previewing-your-work"></a>작업 미리 보기

웹 브라우저를 통해 GitHub에서 편집 하는 동안 페이지 맨 위에 있는 **미리 보기** 탭을 선택 하 여 커밋하기 전에 작업을 미리 볼 수 있습니다. 

>[!NOTE]
>Microsoft 직원만 review.docs.microsoft.com에서 변경 내용을 미리 볼 수 있습니다.

Microsoft 직원: 기여를 기본 분기 _마스터_ 에 병합 한 경우 콘텐츠를 검토 하 여 </hololens? branch = master>에서 공개로 설정할 수 있습니다. 왼쪽 열의 목차를 사용 하 여 문서를 찾습니다.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>브라우저에서 편집 및 데스크톱 클라이언트를 사용 하 여 편집

브라우저에서 편집은 빠른 변경을 수행 하는 가장 쉬운 방법 이지만 다음과 같은 몇 가지 단점이 있습니다.

- 맞춤법 검사를 받을 수 없습니다.
- 다른 문서에 대 한 스마트 링크를 얻을 수 없습니다 (문서의 파일 이름을 수동으로 입력 해야 함).
- 이미지를 업로드 하 고 참조 하는 것이 더 나을 수 있습니다.

이러한 문제를 해결 하는 것이 아닌 경우에는 도움이 될 때 도움이 되는 몇 가지 [유용한 확장과](#useful-extensions) 함께 [Visual Studio Code](https://code.visualstudio.com/) 와 같은 데스크톱 클라이언트를 사용 합니다.

## <a name="using-visual-studio-code"></a>Visual Studio Code 사용

[위에](#editing-in-the-browser-vs-editing-with-a-desktop-client)나열 된 이유 때문에 웹 브라우저가 아닌 데스크톱 클라이언트를 사용 하 여 문서를 편집 하는 것이 좋습니다. [Visual Studio Code](https://code.visualstudio.com/)를 사용하는 것이 좋습니다.

### <a name="setup"></a>설정

이 리포지토리를 사용 하도록 Visual Studio Code를 구성 하려면 다음 단계를 수행 합니다.

1. 웹 브라우저에서 다음을 수행 합니다.
    1. [PC 용 Git를](https://git-scm.com/downloads)설치 합니다.
    2. [Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.
    3. [분기 MicrosoftDocs/mixed-현실](#creating-a-new-article) . 아직 없는 경우.
    4. 포크에서 **복제 또는 다운로드** 를 선택 하 고 URL을 복사 합니다.
2. Visual Studio Code에서 포크의 로컬 클론을 만듭니다.
    1. **보기** 메뉴에서 **명령 팔레트** 를 선택 합니다.
    2. "Git: Clone"을 입력 합니다.
    3. 복사한 URL을 붙여 넣습니다.
    4. PC에서 클론을 저장할 위치를 선택 합니다.
    5. 팝업에서 **리포지토리 열기** 를 선택 합니다.

### <a name="editing-documentation"></a>문서 편집

Visual Studio Code를 사용 하 여 설명서를 변경 하려면 다음 워크플로를 사용 합니다.

>[!NOTE]
>Visual Studio Code 사용 하는 경우에는 문서 [편집](#editing-an-existing-article) 및 [만들기](#creating-a-new-article) 에 대 한 모든 지침과 위에서 [Markdown 편집의 기본](#markdown-basics)사항이 적용 됩니다.

1. 복제 된 분기가 공식 리포지토리를 사용 하 여 최신 상태 인지 확인 합니다.

   1. 웹 브라우저에서 끌어오기 요청을 만들어 MicrosoftDocs/mixed-현실, _master_ 의 기본 분기에 있는 다른 참가자의 최근 변경 내용을 포크에 동기화 합니다 (화살표가 올바른 대상을 가리키는지 확인).
      
      ![MicrosoftDocs/mixed-현실에서 포크로 변경 내용을 동기화 합니다.](images/sync-repos.png)
      
   2. Visual Studio Code에서 동기화 단추를 선택 하 여 새로 업데이트 된 포크를 로컬 클론에 동기화 합니다.
      
      ![동기화 단추 이미지를 클릭 합니다.](images/sync-clone.png)
      
2. Visual Studio Code를 사용 하 여 복제 된 리포지토리에서 문서를 만들거나 편집 합니다.

   1. 하나 이상의 문서 (필요한 경우 "images" 폴더에 이미지 추가)를 편집 합니다.
   
   2. **탐색기** 에서 변경 내용을 **저장** 합니다.
      
      ![탐색기에서 "모두 저장"을 선택 합니다.](images/explorer-save.png)
      
   3. **소스 제어** 의 모든 변경 내용 **커밋** (메시지가 표시 되 면 쓰기 커밋 메시지).
   
      ![소스 제어에서 "모두 커밋"을 선택 합니다.](images/source-control-commit.png)
      
   4. **동기화** 단추를 선택 하 여 변경 내용을 원본으로 다시 동기화 합니다 (GitHub 포크).
      
      ![동기화 단추를 클릭 합니다.](images/sync-back.png)
      
3. 웹 브라우저에서 끌어오기 요청을 만들어 포크의 새 변경 내용을 MicrosoftDocs/mixed reality _마스터로_ 동기화 합니다. 화살표가 올바른 대상을 가리키는지 확인 합니다.

   ![포크에서 MicrosoftDocs/mixed reality로 끌어오기 요청을 만듭니다.](images/pr-to-master.png)

### <a name="useful-extensions"></a>유용한 확장

문서를 편집할 때 다음과 같은 Visual Studio Code 확장을 유용 하 게 사용할 수 있습니다.

- [Visual Studio Code 용 docs Markdown 확장](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt + M** 을 사용 하 여 다음과 같은 docs 제작 옵션 메뉴를 표시 합니다.
   - 업로드 한 이미지를 검색 하 고 참조 합니다.
   - 목록과 같이 목록, 테이블 및 문서 특정 호출 등의 서식을 추가 `>[!NOTE]` 합니다.
   - 내부 링크와 책갈피를 검색 하 고 참조 합니다 (페이지 내의 특정 섹션에 대 한 링크).
   - 서식 지정 오류가 강조 표시 됩니다. 자세한 내용은 오류를 마우스로 가리키십시오.
- [코드 맞춤법 검사기](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -철자가 잘못 된 단어에는 밑줄이 그어집니다. 철자가 잘못 된 단어를 마우스 오른쪽 단추로 클릭 하 여 변경 하거나 사전에 저장 합니다.
