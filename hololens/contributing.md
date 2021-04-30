---
title: 영향을 주는 지침
description: Flavored Markdown를 사용 하 여 docs.microsoft.com 플랫폼에서 HoloLens 문서에 참여 하는 방법을 알아봅니다.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309216"
---
# <a name="contributing-to-the-hololens-documentation"></a>HoloLens 설명서에 기여

[HoloLens 설명서](https://github.com/MicrosoftDocs/Hololens)를 시작 합니다. 이 리포지토리에서 만들거나 편집 하는 모든 문서는 **공용에 표시 됩니다.** 

HoloLens 문서는 docs.microsoft.com 플랫폼에 표시 되며, 여기서는 GitHub-flavored Markdown를 사용 하 여 Markdig 기능을 사용 합니다. 이 리포지토리에서 편집 하는 콘텐츠는에 표시 되는 스타일 있는 페이지로 서식 지정 https://docs.microsoft.com/hololens 됩니다. 

이 페이지에서는 Markdown 기본 사항에 기여 하 고 연결 하는 데 필요한 기본 단계 및 지침을 설명 합니다. 참가 해 주셔서 감사 합니다.

## <a name="available-repos"></a>사용 가능한 리포지토리

| 리포지토리 이름 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-현실](https://docs.microsoft.com/windows/mixed-reality) |
| VR 매니아 가이드 | [MicrosoftDocs/mixed-현실/열성적인](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>시작하기 전에

아직 없는 경우 [GitHub 계정을 만들어야](https://github.com/join)합니다.

>[!NOTE]
>Microsoft 직원 인 경우 microsoft [오픈 소스 포털](https://repos.opensource.microsoft.com/)의 microsoft 별칭에 GitHub 계정을 연결 하세요. **"Microsoft"** 및 **"MicrosoftDocs"** 조직에 참여 합니다.

GitHub 계정을 설정할 때 다음과 같은 보안 예방 조치를 권장 합니다.
- [GitHub 계정에 대 한 강력한 암호](https://github.com/settings/admin)를 만듭니다.
- [2 단계 인증](https://github.com/settings/two_factor_authentication/configure)을 사용 하도록 설정 합니다.
- [복구 코드](https://github.com/settings/auth/recovery-codes) 를 안전한 장소에 저장 합니다.
- [공개 프로필 설정을](https://github.com/settings/profile)업데이트 합니다.
   - 사용자의 이름을 설정 하 고 *전자 메일 주소를 표시 하지 않도록* *공용 전자 메일* 을 설정 하는 것이 좋습니다.
   - 사용자가 참여 하는 문서 페이지에 미리 보기가 표시 되기 때문에 프로필 사진을 업로드 하는 것이 좋습니다.
- 명령줄을 사용할 계획인 경우 [Windows 용 Git 자격 증명 관리자](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)를 설정 하는 것이 좋습니다. 이렇게 하면 기여를 할 때마다 암호를 입력할 필요가 없습니다.

게시 시스템은 GitHub에 연결 되므로 이러한 단계가 중요 합니다. GitHub 별칭을 사용 하 여 각 아티클에 대 한 작성자 또는 참가자로 나열 됩니다.

## <a name="editing-an-existing-article"></a>기존 문서 편집

웹 브라우저에서 GitHub를 통해 *기존 문서* 를 업데이트 하려면 다음 워크플로를 사용 합니다.

1. "Mixed reality-docs" 폴더에서 편집 하려는 문서로 이동 합니다.

2. 오른쪽 위에 있는 편집 단추 (연필 아이콘)를 선택 하면 삭제 가능한 분기가 ' 마스터 ' 분기 밖으로 자동으로 분기 합니다.

   ![문서를 편집 합니다.](images/editpage.png)
   
3. ["Markdown 기본 사항"](#markdown-basics)에 따라 아티클의 내용을 편집 합니다.

4. 각 문서의 맨 위에 있는 메타 데이터를 업데이트 합니다.

   * **제목**: 문서를 볼 때 브라우저 탭에 표시 되는 페이지 제목입니다. 페이지 제목은 SEO 및 인덱싱에 사용 되므로 필요한 경우를 제외 하 고는 제목을 변경 하지 않습니다. 단, 설명서를 공개 하기 전에는이 작업이 중요 하지 않습니다.
   * **설명**: SEO 및 검색을 향상 시키는 아티클의 콘텐츠에 대 한 간단한 설명을 작성 합니다.
   * **작성자**: 페이지의 기본 소유자 인 경우 여기에 GitHub 별칭을 추가 합니다.
   * **ms author**: 페이지의 기본 소유자 인 경우 여기에 Microsoft 별칭을 추가 @microsoft.com 합니다 (별칭만 필요 없음).
   * **ms. 날짜**: 페이지에 주요 콘텐츠를 추가 하는 경우에는 날짜를 업데이트 하지만 설명, 서식, 문법 또는 철자와 같은 픽스는 업데이트 하지 않습니다.
   * **키워드**: SEO의 키워드 지원 (검색 엔진 최적화). 사용자의 문서와 관련 된 키워드를 쉼표와 공백으로 구분 하 고 목록에서 마지막 키워드 뒤에 문장 부호는 추가 하지 않습니다. 모든 문서에 적용 되는 전역 키워드는 다른 곳에서 관리 되므로 추가할 필요가 없습니다. 
   
5. 문서 편집을 완료 한 후 아래로 스크롤하여 **파일 변경 내용 제안** 을 선택 합니다.

6. 다음 페이지에서 **끌어오기 요청 만들기** 를 선택 하 여 자동으로 생성 된 분기를 ' 마스터 '에 병합 합니다.

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

- `redirect_document_id` 이전 파일의 문서 ID를 유지할지 여부를 나타냅니다. 기본값은 `false`입니다. `true`리디렉션된 아티클의 특성 값을 유지 하려는 경우에 사용 합니다 `ms.documentid` . 문서 ID를 유지 하는 경우 페이지 보기 및 순위와 같은 데이터가 대상 문서에 전송 됩니다. 리디렉션이 주로 이름 바꾸기 인 경우에는이 작업을 수행 하 고, 동일한 콘텐츠 중 일부만 포함 하는 다른 문서에 대 한 포인터는 그렇지 않습니다.

리디렉션을 추가 하는 경우에도 이전 파일을 삭제 해야 합니다.

## <a name="creating-a-new-article"></a>새 문서 만들기

웹 브라우저에서 GitHub를 통해 설명서 리포지토리에서 *새 문서를 만들려면* 다음 워크플로를 사용 합니다.

1. 오른쪽 위에 있는 **포크** 단추를 사용 하 여 MicrosoftDocs/mixed reality ' master ' 분기에서 포크를 만듭니다.

   ![마스터 분기를 포크 합니다.](images/forkbranch.png)
   
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

5. [위의 섹션](#editing-an-existing-article)에 설명 된 지침에 따라 관련 메타 데이터 필드를 입력 합니다.

6. [Markdown 기본 사항을](#markdown-basics)사용 하 여 문서 콘텐츠를 작성 합니다.

7. `## See also`문서의 맨 아래에 있는 섹션을 다른 관련 문서에 대 한 링크와 함께 추가 합니다.

8. 완료 되 면 **새 파일 커밋** 을 선택 합니다.

9. **새 끌어오기 요청** 을 선택 하 고 포크의 ' 마스터 ' 분기를 MicrosoftDocs/mixed-현실 ' master '에 병합 합니다 (화살표가 올바른 방법을 가리키는지 확인).

   ![포크에서 MicrosoftDocs/mixed reality로 끌어오기 요청 만들기](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown 기본 사항

다음 리소스는 Markdown 언어를 사용 하 여 문서를 편집 하는 방법을 배우는 데 도움이 됩니다.

- [Markdown 기본 사항](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Docs.microsoft.com에 대 한 Markdown 쓰기에 대 한 추가 리소스](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>테이블 추가

스타일 docs.microsoft.com 스타일을 지정 하는 방식 때문에 인라인 CSS를 시도 하더라도 테두리나 사용자 지정 스타일은 없습니다. 짧은 시간 동안 작동 하는 것 처럼 보이지만 결국 플랫폼은 테이블에서 스타일을 제거 합니다. 따라서 미리 계획 하 고 테이블을 단순하게 유지 합니다. [Markdown 테이블을 쉽게 만들 수 있는 사이트는 다음과 같습니다](https://www.tablesgenerator.com/markdown_tables).

[Visual Studio Code에 대 한 Docs Markdown 확장](https://docs.microsoft.com/teamblog/docs-extension) 은 [Visual Studio Code (아래 참조)](#using-visual-studio-code) 를 사용 하 여 문서를 편집 하는 경우에도 테이블을 쉽게 생성할 수 있습니다.

### <a name="adding-images"></a>이미지 추가

리포지토리의 "mixed reality-docs/images" 폴더에 이미지를 업로드 한 다음 문서에서 적절 하 게 참조 해야 합니다. 이미지가 자동으로 전체 크기로 표시 됩니다. 즉, 큰 이미지는 문서의 전체 너비를 채웁니다. 이미지를 업로드 하기 전에 미리 크기를 조정 하는 것이 좋습니다. 권장 되는 너비는 600 픽셀에서 700 픽셀 사이 이지만, 조밀한 스크린샷 또는 스크린 샷의 분수 인 경우 크기를 조정 하거나 축소 해야 합니다.

>[!IMPORTANT]
>병합 하기 전에 분기 리포지토리에만 이미지를 업로드할 수 있습니다. 따라서 문서에 이미지를 추가 하려면 먼저 [Visual Studio Code를 사용](#using-visual-studio-code) 하 여 포크의 "images" 폴더에 이미지를 추가 하거나 웹 브라우저에서 다음을 수행 해야 합니다.
>
>1. MicrosoftDocs/mixed reality 리포지토리를 분기 합니다.
>2. 포크에서 문서를 편집 했습니다.
>3. 문서에서 참조 하는 이미지를 포크의 "mixed reality-docs/images" 폴더에 업로드 했습니다.
>4. 분기를 MicrosoftDocs/mixed-현실 ' master ' 분기에 병합 하는 **끌어오기 요청** 을 만들었습니다.
>
>사용자 고유의 분기 리포지토리를 설정 하는 방법을 알아보려면 [새 문서 만들기](#creating-a-new-article)에 대 한 지침을 따르세요.

## <a name="previewing-your-work"></a>작업 미리 보기

웹 브라우저를 통해 GitHub에서 편집 하는 동안 페이지 맨 위에 있는 **미리 보기** 탭을 선택 하 여 커밋 전 작업을 미리 볼 수 있습니다. 

>[!NOTE]
>review.docs.microsoft.com의 변경 내용 미리 보기는 Microsoft 직원 에게만 제공 됩니다.

Microsoft 직원: 기여를 ' 마스터 ' 분기에 병합 한 후에는에서 공개 되기 전에 콘텐츠를 검토할 수 있습니다 https://review.docs.microsoft.com/hololens?branch=master . 왼쪽 열에 있는 목차를 사용 하 여 문서를 찾습니다.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>브라우저에서 편집 및 데스크톱 클라이언트를 사용 하 여 편집

브라우저에서 편집은 빠른 변경을 수행 하는 가장 쉬운 방법 이지만 다음과 같은 몇 가지 단점이 있습니다.

- 맞춤법 검사를 받을 수 없습니다.
- 다른 문서에 대 한 스마트 링크를 얻을 수 없습니다 (문서의 파일 이름을 직접 입력 해야 함).
- 이미지를 업로드 하 고 참조 하는 것이 더 나을 수 있습니다.

이러한 문제를 해결 하는 것이 아닌 경우에는 도움이 될 때 도움이 되는 몇 가지 [유용한 확장과](#useful-extensions) 함께 [Visual Studio Code](https://code.visualstudio.com/) 와 같은 데스크톱 클라이언트를 사용 합니다.

## <a name="using-visual-studio-code"></a>Visual Studio Code 사용

[위에](#editing-in-the-browser-vs-editing-with-a-desktop-client)나열 된 이유 때문에 웹 브라우저가 아닌 데스크톱 클라이언트를 사용 하 여 문서를 편집 하는 것이 좋습니다. [Visual Studio Code](https://code.visualstudio.com/)를 사용 하는 것이 좋습니다.

### <a name="setup"></a>설치

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

   1. 웹 브라우저에서 끌어오기 요청을 만들어 MicrosoftDocs/mixed reality의 다른 참가자의 최근 변경 내용을 포크에 동기화 합니다. 화살표가 올바른 방법을 가리키고 있는지 확인 합니다.
      
      ![MicrosoftDocs/mixed-현실에서 포크로 변경 내용 동기화](images/sync-repos.png)
      
   2. Visual Studio Code에서 동기화 단추를 선택 하 여 새로 업데이트 된 포크를 로컬 클론에 동기화 합니다.
      
      ![동기화 단추 이미지를 클릭 합니다.](images/sync-clone.png)
      
2. Visual Studio Code를 사용 하 여 복제 된 리포지토리에서 문서를 만들거나 편집 합니다.

   1. 하나 이상의 문서 (필요한 경우 "images" 폴더에 이미지 추가)를 편집 합니다.
   
   2. **탐색기** 에서 변경 내용을 **저장** 합니다.
      
      ![탐색기에서 "모두 저장"을 선택 합니다.](images/explorer-save.png)
      
   3. **소스 제어** 의 모든 변경 내용 **커밋** (메시지가 표시 되 면 쓰기 커밋 메시지).
   
      ![소스 제어에서 "모두 커밋"을 선택 합니다.](images/source-control-commit.png)
      
   4. **동기화** 단추를 선택 하 여 변경 내용을 원본으로 다시 동기화 합니다 (GitHub의 포크).
      
      ![동기화 단추를 클릭 합니다.](images/sync-back.png)
      
3. 웹 브라우저에서 끌어오기 요청을 만들어 분기의 새 변경 내용을 MicrosoftDocs/mixed-현실 ' master '로 다시 동기화 합니다. 화살표가 올바른 방법을 가리키고 있는지 확인 합니다.

   ![포크에서 MicrosoftDocs/mixed reality로 끌어오기 요청 만들기](images/pr-to-master.png)

### <a name="useful-extensions"></a>유용한 확장

문서를 편집할 때 다음과 같은 Visual Studio Code 확장을 유용 하 게 사용할 수 있습니다.

- [Visual Studio Code 용 Docs Markdown 확장](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt + M** 을 사용 하 여 다음과 같은 docs 제작 옵션 메뉴를 표시 합니다.
   - 업로드 한 이미지를 검색 하 고 참조 합니다.
   - 목록과 같이 목록, 테이블 및 문서 특정 호출 등의 서식을 추가 `>[!NOTE]` 합니다.
   - 내부 링크와 책갈피를 검색 하 고 참조 합니다 (페이지 내의 특정 섹션에 대 한 링크).
   - 서식 지정 오류가 강조 표시 됩니다. 자세한 내용은 오류를 마우스로 가리키십시오.
- [코드 맞춤법 검사기](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -철자가 잘못 된 단어에는 밑줄이 그어집니다. 철자가 잘못 된 단어를 마우스 오른쪽 단추로 클릭 하 여 변경 하거나 사전에 저장 합니다.
