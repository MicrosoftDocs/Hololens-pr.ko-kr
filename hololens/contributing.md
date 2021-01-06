---
title: 참가자 지침
description: GitHub로 정통한 Markdown을 사용하여 docs.microsoft.com 플랫폼에서 HoloLens docs에 기여하는 방법을 알아보고,
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 311da6bc52098d5ba16e4684f68fec9a01e7c23b
ms.sourcegitcommit: 8cea4c04c6d2e22225f4de43e10c05dab840736a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253854"
---
# HoloLens 설명서에 참여

[HoloLens 설명서에 오신 것을 환영합니다!](https://github.com/MicrosoftDocs/Hololens) 이 리포지타에서 만들거나 편집하는 모든 **문서는 일반에게 표시됩니다.** 

HoloLens docs는 Markdig 기능과 함께 GitHub로 docs.microsoft.com Markdown을 사용하는 docs.microsoft.com 플랫폼에 표시됩니다. 이 리포지타입에서 편집하는 콘텐츠는 에 표시되어 스타일이 있는 페이지로 서식이 https://docs.microsoft.com/hololens 설정됩니다. 

이 페이지에는 기여하기 위한 기본 단계 및 지침과 Markdown 기본에 대한 링크가 다수 표시됩니다. 기여해주신 분들 감사합니다.

## 사용 가능한 리포지타시

| 리포지토리 이름 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| 혼합 현실 | [MicrosoftDocs/mixed-reality](https://docs.microsoft.com/windows/mixed-reality) |
| VR 매니아 가이드 | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## 시작하기 전에

아직 계정이 없는 경우 [GitHub 계정을 만들어야 합니다.](https://github.com/join)

>[!NOTE]
>Microsoft 직원인 경우 GitHub 계정을 Microsoft 오픈 소스 포털의 Microsoft 별칭에 [연결합니다.](https://repos.opensource.microsoft.com/) **"Microsoft"** 및 **"MicrosoftDocs" 조직에 가입합니다.**

GitHub 계정을 설정할 때 다음 보안 주의 사항도 권장됩니다.
- [GitHub 계정에 대한 강력한 암호를 만드시다.](https://github.com/settings/admin)
- [2단계 인증을 사용하도록 설정](https://github.com/settings/two_factor_authentication/configure)
- 복구 코드를 [안전한](https://github.com/settings/auth/recovery-codes) 장소에 저장합니다.
- 공용 프로필 [설정을 업데이트합니다.](https://github.com/settings/profile)
   - 이름을 설정하고 공용 전자 ** 메일을 내 전자 메일 주소를 표시하지 않는 *것으로 설정하는 것을 고려합니다.*
   - 작성한 문서 페이지에 미리 보기가 표시 찍기 때문에 프로필 사진을 업로드하는 것이 좋습니다.
- 명령줄을 사용 계획하는 경우 [Windows용 Git 자격](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)증명 관리자를 설정할 수 있습니다. 이렇게 하면 기여할 때마다 암호를 입력할 수 없습니다.

게시 시스템은 GitHub에 있으므로 이러한 단계가 중요합니다. GitHub 별칭을 사용하여 각 문서의 작성자 또는 작성자로 나열됩니다.

## 기존 문서 편집

다음 워크플로를 사용하여 웹 ** 브라우저에서 GitHub를 통해 기존 문서를 업데이트합니다.

1. "mixed-reality-docs" 폴더에서 편집할 문서로 이동합니다.

2. 오른쪽 위에 있는 편집 단추(연필 아이콘)를 선택하면 '마스터' 분기에서 삭제 가능한 분기가 자동으로 분기됩니다.

   ![문서를 편집합니다.](images/editpage.png)
   
3. "Markdown 기본"에 따라 문서의 내용을 [편집합니다.](#markdown-basics)

4. 각 문서 맨 위에 있는 메타데이터를 업데이트합니다.

   * **제목**: 문서를 볼 때 브라우저 탭에 나타나는 페이지 제목입니다. 페이지 제목은 SEO 및 인덱싱에 사용되기 때문에 필요한 경우를 위해 제목을 변경하지 않습니다(설명서가 공개되기 전에 중요하지는 않습니다).
   * **description**: SEO 및 검색을 향상하는 문서 콘텐츠에 대한 간략한 설명을 작성합니다.
   * **author**: 페이지의 기본 소유자인 경우 여기에 GitHub 별칭을 추가합니다.
   * **ms.author**: 페이지의 기본 소유자인 경우 여기에 Microsoft 별칭을 추가합니다(@microsoft.com 필요 없습니다. 별칭만).
   * **ms.date**: 페이지에 주요 콘텐츠를 추가하는 경우 날짜를 업데이트하지만 명확성, 서식 지정, 문법 또는 맞춤법과 같은 수정 내용은 업데이트하지 않습니다.
   * **키워드**: SEO의 키워드 지원(검색 엔진 최적화) 문서와 관련이 있지만 목록의 마지막 키워드 다음에 문장 부호가 없는 키워드를 COMMA와 공백으로 구분하여 추가합니다. 모든 문서에 적용되는 전역 키워드를 추가할 필요는 없습니다. 이러한 키워드는 다른 곳에서 관리됩니다. 
   
5. 문서 편집을 완료한 후 아래로 스크롤하여 파일 변경 **제안을 선택합니다.**

6. 다음 페이지에서 끌어오기 요청 만들기를 선택하여 자동으로 만들어진 분기를 'master.'로 병합합니다. ****

7. 편집하려는 다음 문서에 대해 위의 단계를 반복합니다.

## 기존 문서 이름 변경 또는 삭제

변경 내용에 따라 기존 문서의 이름을 바꾸거나 삭제하는 경우 리디렉션을 추가해야 합니다. 이렇게 하면 기존 문서에 대한 링크가 있는 모든 사람이 여전히 올바른 장소에 있습니다. 리디렉션은 리포지 .openpublishing.redirection.js파일을 통해 관리됩니다.

리디렉션을 .openpublishing.redirection.js배열에 항목을 `redirections` 추가합니다.

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- 제거하고 있는 이전 문서의 상대적 리포지토리 `source_path` 경로입니다. 경로가 .로 시작하고 으로 `mixed-reality-docs` 끝나야 `.md` 합니다.

- 이전 문서에서 새 문서까지의 상대 공용 `redirect_url` URL입니다. 이 **URL에는** 리포지토리 경로가 아니라 공용 URL을 참조하는 URL이 포함되어 `mixed-reality-docs` 있지 `.md` 않은지 확인합니다. 새 문서에서 사용하는 섹션에 대한 `#section` 링크가 허용됩니다. 필요한 경우 여기에서 다른 사이트에 대한 절대 경로를 사용할 수도 있습니다.

- `redirect_document_id` 이전 파일의 문서 ID를 유지할지 여부를 나타냅니다. 기본값은 `false` . 리디렉션된 문서의 특성 값을 `true` `ms.documentid` 유지하려는 경우 사용하세요. 문서 ID를 보존하면 페이지 보기 및 순위와 같은 데이터가 대상 문서로 전송됩니다. 리디렉션이 주로 이름과 같은 일부 콘텐츠만 다루는 다른 문서에 대한 포인터가 아닌 경우 이 작업을 합니다.

리디렉션을 추가하는 경우 이전 파일도 삭제해야 합니다.

## 새 문서 만들기

다음 워크플로를 *사용하여* 웹 브라우저에서 GitHub를 통해 설명서 리포지터에 새 문서를 만듭니다.

1. MicrosoftDocs/mixed-reality 'master' 분기(오른쪽 위에 있는 포크 단추 사용)에서 **포크를** 만드십시오.

   ![마스터 분기를 분기합니다.](images/forkbranch.png)
   
2. "mixed-reality-docs" 폴더에서 오른쪽 **** 위에 새 파일 만들기를 선택합니다.

3. 문서의 페이지 이름을 만들고(공백 대신 하이픈을 사용하며 문장 부호나 아포스트로피를 사용하지 않습니다) ".md"를 추가합니다.

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

5. 위의 섹션의 지침에 따라 관련 메타데이터 [필드를 입력합니다.](#editing-an-existing-article)

6. Markdown 기본을 사용하여 문서 [콘텐츠를 작성합니다.](#markdown-basics)

7. 다른 관련 문서에 대한 링크가 있는 문서 `## See also` 아래쪽에 섹션을 추가합니다.

8. 완료되면 새 **파일 커밋을 선택합니다.**

9. 새 **끌어오기** 요청을 선택하고 포크의 '마스터' 분기를 MicrosoftDocs/mixed-reality 'master'로 병합합니다(화살표가 올바른 방법을 가리키고 있는지 확인).

   ![포크에서 MicrosoftDocs/혼합 현실로 끌어오기 요청 만들기](images/pr-to-master.png)

## Markdown 기본

다음 리소스는 Markdown 언어를 사용하여 설명서를 편집하는 방법을 배우는 데 도움이 됩니다.

- [Markdown 기본](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [표식 작성을 위한 추가 docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### 테이블 추가

표 스타일 docs.microsoft.com 때문에 인라인 CSS를 사용해도 테두리나 사용자 지정 스타일이 없습니다. 잠시 동안 작동하지만 결국 플랫폼에서 스타일이 표에서 제거됩니다. 따라서 테이블을 간단하게 계획하십시오. [다음은 Markdown 테이블을 쉽게 만드는 사이트입니다.](https://www.tablesgenerator.com/markdown_tables)

또한 [문서 코드용 Docs Markdown Extension for Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) 코드를 사용하여 설명서를 편집하는 경우 Visual Studio [코드(아래](#using-visual-studio-code) 참조)를 사용하여 테이블을 쉽게 생성할 수 있습니다.

### 이미지 추가

리포지터의 "mixed-reality-docs/images" 폴더에 이미지를 업로드한 다음 문서에서 적절히 참조해야 합니다. 이미지가 자동으로 전체 크기로 표시되어 큰 이미지가 문서의 전체 너비를 채우게 됩니다. 이미지를 업로드하기 전에 이미지의 크기 조정을 미리 조정하는 것이 좋습니다. 권장되는 너비는 600에서 700픽셀 사이입니다. 그러나 각각 조밀한 스크린샷 또는 스크린샷의 일부인 경우 크기를 조정하거나 작아야 합니다.

>[!IMPORTANT]
>이미지를 포크된 리포지 파일로만 업로드한 다음에야 이 파일을 업로드할 수 있습니다. 따라서 문서에 이미지를 추가하려면 [Visual Studio Code를](#using-visual-studio-code) 사용하여 먼저 포크의 "이미지" 폴더에 이미지를 추가하거나 웹 브라우저에서 다음을 수행해야 합니다.
>
>1. MicrosoftDocs/mixed-reality 리포지토를 포크했습니다.
>2. 포크에서 문서를 편집했습니다.
>3. 문서에서 참조하는 이미지를 포크의 "mixed-reality-docs/images" 폴더에 업로드했습니다.
>4. MicrosoftDocs/mixed-reality '마스터' 분기에 포크를 병합하는 끌어오기 요청을 생성했습니다. ****
>
>자체의 포크 리포지터를 설정하는 방법을 알아보십시오. 새 문서를 만드는 방법에 대한 [지침을 따르세요.](#creating-a-new-article)

## 작업 미리 보기

웹 브라우저를 통해 GitHub에서 편집하는 동안 **** 페이지 위쪽의 미리 보기 탭을 선택하여 커밋하기 전에 작업을 미리 볼 수 있습니다. 

>[!NOTE]
>Microsoft 직원만 review.docs.microsoft.com 변경 내용을 미리 볼 수 있습니다.

Microsoft 직원: 기여한 내용이 '마스터' 분기에 병합된 후 공개되기 전에 콘텐츠를 검토할 수 https://review.docs.microsoft.com/hololens?branch=master 있습니다. 왼쪽 열의 내용 표를 사용하여 문서를 찾아야 합니다.

## 브라우저에서 편집 및 데스크톱 클라이언트로 편집

브라우저에서 편집하는 것이 빠르게 변경하는 가장 쉬운 방법입니다. 그러나 몇 가지 단점이 있습니다.

- 맞춤법 검사를 받을 수 없습니다.
- 다른 문서에 대한 스마트 연결은 얻을 수 없습니다(문서의 파일 이름을 수동으로 입력해야 합니다).
- 이미지를 업로드하고 참조하기가 고민할 수 있습니다.

이러한 문제를 처리하지 않는 경우 기여할 때 몇 가지 유용한 Visual Studio [코드와](https://code.visualstudio.com/) 같은 데스크톱 [클라이언트를](#useful-extensions) 사용 합니다.

## 코드 Visual Studio 사용

위에 [나열된](#editing-in-the-browser-vs-editing-with-a-desktop-client)이유로 웹 브라우저 대신 데스크톱 클라이언트를 사용하여 문서를 편집하는 것이 좋습니다. 이 코드는 Visual Studio [좋습니다.](https://code.visualstudio.com/)

### Setup

다음 단계에 따라 이 리포지 Visual Studio 코드가 작동하도록 구성합니다.

1. 웹 브라우저에서:
    1. [PC용 Git을 설치합니다.](https://git-scm.com/downloads)
    2. 코드 [Visual Studio 설치합니다.](https://code.visualstudio.com/)
    3. [아직 MicrosoftDocs/혼합](#creating-a-new-article) 현실을 포크하지 않은 경우
    4. 포크에서 복제를 **선택하거나 URL을 다운로드하여** 복사합니다.
2. 다음 코드에서 포크의 로컬 복제본을 Visual Studio.
    1. 보기 **메뉴에서** 명령 **팔레트를 선택합니다.**
    2. "Git: Clone"을 입력합니다.
    3. 복사한 URL을 붙여 넣습니다.
    4. PC에서 복제본을 저장할 위치를 선택하십시오.
    5. **팝업에서** 리포지터를 선택합니다.

### 문서 편집

다음 워크플로를 사용하여 Visual Studio 변경합니다.

>[!NOTE]
>문서 편집 [](#editing-an-existing-article) 및 만들기에 대한 모든 지침과 위의 [Markdown](#markdown-basics)편집 기본 사항은 Visual Studio 코드를 사용할 때 적용됩니다. [](#creating-a-new-article)

1. 복제된 포크가 공식 리포지타이어를 통해 최신으로 유지해야 합니다.

   1. 웹 브라우저에서 MicrosoftDocs/mixed-reality '마스터'의 다른 참가자의 최근 변경 내용을 포크에 동기화하는 끌어오기 요청을 생성합니다(화살표가 올바른 방법을 가리키고 있는지 확인).
      
      ![MicrosoftDocs/mixed-reality에서 포크로 변경 내용 동기화](images/sync-repos.png)
      
   2. Visual Studio 코드에서 동기화 단추를 선택하여 최신 업데이트된 포크를 로컬 복제본에 동기화합니다.
      
      ![동기화 단추 이미지 클릭](images/sync-clone.png)
      
2. 코드 코드를 사용하여 복제된 리포지타이트에서 Visual Studio 편집합니다.

   1. 하나 이상의 문서를 편집합니다(필요한 경우 이미지를 "images" 폴더에 추가).
   
   2. **탐색기에서** 변경 **내용을 저장합니다.**
      
      ![탐색기에서 "모두 저장"을 선택](images/explorer-save.png)
      
   3. **원본 제어의** 모든 **변경** 내용을 커밋합니다(메시지가 표시될 때 커밋 메시지 쓰기).
      
   4. 동기화 **단추를 선택하여** 변경 내용을 원본(GitHub의 포크)에 다시 동기화합니다.
      
      ![동기화 단추 클릭](images/sync-back.png)
      
3. 웹 브라우저에서 포크의 새로운 변경 내용을 MicrosoftDocs/mixed-reality '마스터'에 다시 동기화하는 끌어오기 요청을 생성합니다(화살표가 올바른 방법을 가리키고 있는지 확인).

   ![포크에서 MicrosoftDocs/혼합 현실로 끌어오기 요청 만들기](images/pr-to-master.png)

### 유용한 확장

다음 Visual Studio 코드 확장은 문서를 편집할 때 유용합니다.

- Visual Studio 코드에 대한 [Docs Markdown 확장](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt+M을** 사용하여 다음과 같은 docs 제작 옵션의 메뉴를 표시하세요.
   - 업로드한 이미지를 검색하고 참조합니다.
   - 목록, 표 및 docs 관련 설명선과 같은 서식을 `>[!NOTE]` 추가합니다.
   - 내부 링크 및 책갈피(페이지 내의 특정 섹션에 대한 링크)를 검색하고 참조합니다.
   - 서식 오류가 강조 표시됩니다(자세한 내용은 오류 위에 마우스를 놓아야 합니다).
- [코드 맞춤법 검사기](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - 철자가 떨어졌다는 단어에 밑선이 그어지기 올바른 단어의 선택이 없는 단어를 마우스 오른쪽 단추로 클릭하여 변경하거나 사전에 저장합니다.
