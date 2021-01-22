---
title: 참가자 지침
description: GitHub로 정통한 Markdown을 사용하여 docs.microsoft.com 플랫폼에서 HoloLens docs에 기여하는 방법을 알아보고,
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283666"
---
# <span data-ttu-id="6522c-103">HoloLens 설명서에 참여</span><span class="sxs-lookup"><span data-stu-id="6522c-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="6522c-104">[HoloLens 설명서에 오신 것을 환영합니다!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="6522c-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="6522c-105">이 리포지타에서 만들거나 편집하는 모든 **문서는 일반에게 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6522c-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="6522c-106">HoloLens docs는 Markdig 기능과 함께 GitHub로 docs.microsoft.com Markdown을 사용하는 docs.microsoft.com 플랫폼에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="6522c-107">이 리포지타입에서 편집하는 콘텐츠는 에 표시되어 스타일이 있는 페이지로 서식이 https://docs.microsoft.com/hololens 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="6522c-108">이 페이지에는 기여에 대한 기본 단계와 지침과 Markdown 기본에 대한 링크가 다수 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="6522c-109">기여해주신 덕분에 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="6522c-110">사용 가능한 리포지타시</span><span class="sxs-lookup"><span data-stu-id="6522c-110">Available repos</span></span>

| <span data-ttu-id="6522c-111">리포지토리 이름</span><span class="sxs-lookup"><span data-stu-id="6522c-111">Repository name</span></span> | <span data-ttu-id="6522c-112">URL</span><span class="sxs-lookup"><span data-stu-id="6522c-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="6522c-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="6522c-113">HoloLens</span></span> | [<span data-ttu-id="6522c-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="6522c-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="6522c-115">혼합 현실</span><span class="sxs-lookup"><span data-stu-id="6522c-115">Mixed Reality</span></span> | [<span data-ttu-id="6522c-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="6522c-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="6522c-117">VR 매니아 가이드</span><span class="sxs-lookup"><span data-stu-id="6522c-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="6522c-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="6522c-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="6522c-119">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6522c-119">Before you start</span></span>

<span data-ttu-id="6522c-120">아직 계정이 없는 경우 [GitHub 계정을 만들어야 합니다.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="6522c-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="6522c-121">Microsoft 직원인 경우 GitHub 계정을 Microsoft 오픈 소스 포털의 Microsoft 별칭에 [연결합니다.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6522c-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="6522c-122">**"Microsoft"** 및 **"MicrosoftDocs" 조직에 가입합니다.**</span><span class="sxs-lookup"><span data-stu-id="6522c-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="6522c-123">GitHub 계정을 설정할 때 다음 보안 주의 사항도 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="6522c-124">[GitHub 계정에 대한 강력한 암호를 만드시다.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="6522c-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="6522c-125">[2단계 인증을 사용하도록 설정](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="6522c-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="6522c-126">복구 코드를 [안전한](https://github.com/settings/auth/recovery-codes) 장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="6522c-127">공용 프로필 [설정을 업데이트합니다.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="6522c-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="6522c-128">이름을 설정하고 공용 전자 \*\* 메일을 내 전자 메일 주소를 표시하지 않는 *것으로 설정하는 것을 고려합니다.*</span><span class="sxs-lookup"><span data-stu-id="6522c-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="6522c-129">작성한 문서 페이지에 미리 보기가 표시 찍기 때문에 프로필 사진을 업로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="6522c-130">명령줄을 사용 계획하는 경우 [Windows용 Git 자격](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)증명 관리자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="6522c-131">이렇게 하면 참여할 때마다 암호를 입력할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="6522c-132">게시 시스템은 GitHub에 있으므로 이러한 단계가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="6522c-133">GitHub 별칭을 사용하여 각 문서의 작성자 또는 작성자로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="6522c-134">기존 문서 편집</span><span class="sxs-lookup"><span data-stu-id="6522c-134">Editing an existing article</span></span>

<span data-ttu-id="6522c-135">다음 워크플로를 사용하여 웹 \*\* 브라우저에서 GitHub를 통해 기존 문서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="6522c-136">"mixed-reality-docs" 폴더에서 편집할 문서로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="6522c-137">오른쪽 위에 있는 편집 단추(연필 아이콘)를 선택하면 '마스터' 분기에서 삭제 가능한 분기가 자동으로 분기됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![문서를 편집합니다.](images/editpage.png)
   
3. <span data-ttu-id="6522c-139">"Markdown 기본"에 따라 문서의 내용을 [편집합니다.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="6522c-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="6522c-140">각 문서 맨 위에 있는 메타데이터를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="6522c-141">**제목**: 문서를 볼 때 브라우저 탭에 나타나는 페이지 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="6522c-142">페이지 제목은 SEO 및 인덱싱에 사용되기 때문에 필요한 경우를 위해 제목을 변경하지 않습니다(설명서가 공개되기 전에는 중요하지는 않습니다).</span><span class="sxs-lookup"><span data-stu-id="6522c-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="6522c-143">**description**: SEO 및 검색을 향상하는 문서 콘텐츠에 대한 간략한 설명을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="6522c-144">**author**: 페이지의 기본 소유자인 경우 여기에 GitHub 별칭을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="6522c-145">**ms.author**: 페이지의 기본 소유자인 경우 여기에 Microsoft 별칭을 추가합니다(@microsoft.com 필요 없습니다. 별칭만).</span><span class="sxs-lookup"><span data-stu-id="6522c-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="6522c-146">**ms.date**: 페이지에 주요 콘텐츠를 추가하는 경우 날짜를 업데이트하지만 명확성, 서식 지정, 문법 또는 맞춤법과 같은 수정 내용은 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="6522c-147">**키워드**: SEO의 키워드 지원(검색 엔진 최적화)</span><span class="sxs-lookup"><span data-stu-id="6522c-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="6522c-148">문서와 관련이 있지만 목록의 마지막 키워드 다음에 문장 부호가 없는 키워드를 COMMA와 공백으로 구분하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="6522c-149">모든 문서에 적용되는 전역 키워드를 추가할 필요는 없습니다. 이러한 키워드는 다른 곳에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="6522c-150">문서 편집을 완료한 후 아래로 스크롤하여 파일 변경 **제안을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6522c-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="6522c-151">다음 페이지에서 끌어오기 요청 만들기를 선택하여 자동으로 만들어진 분기를 'master.'로 병합합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6522c-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="6522c-152">편집하려는 다음 문서에 대해 위의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="6522c-153">기존 문서 이름 변경 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="6522c-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="6522c-154">변경 내용에 따라 기존 문서의 이름을 바꾸거나 삭제하는 경우 리디렉션을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="6522c-155">이렇게 하면 기존 문서에 대한 링크가 있는 모든 사람이 여전히 올바른 장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="6522c-156">리디렉션은 리포지 .openpublishing.redirection.js파일을 통해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="6522c-157">리디렉션을 .openpublishing.redirection.js배열에 항목을 `redirections` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="6522c-158">제거하고 있는 이전 문서의 상대적 리포지토리 `source_path` 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="6522c-159">경로가 .로 시작하고 으로 `mixed-reality-docs` 끝나야 `.md` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="6522c-160">이전 문서에서 새 문서까지의 상대 공용 `redirect_url` URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="6522c-161">이 **URL에는** 리포지토리 경로가 아니라 공용 URL을 참조하는 URL이 포함되어 `mixed-reality-docs` 있지 `.md` 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="6522c-162">새 문서에서 사용하는 섹션에 대한 `#section` 링크가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="6522c-163">필요한 경우 여기에서 다른 사이트에 대한 절대 경로를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="6522c-164">이전 파일의 문서 ID를 유지할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="6522c-165">기본값은 `false` .</span><span class="sxs-lookup"><span data-stu-id="6522c-165">The default is `false`.</span></span> <span data-ttu-id="6522c-166">리디렉션된 문서의 특성 값을 `true` `ms.documentid` 유지하려는 경우 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6522c-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="6522c-167">문서 ID를 보존하면 페이지 보기 및 순위와 같은 데이터가 대상 문서로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="6522c-168">리디렉션이 주로 이름과 같은 일부 콘텐츠만 다루는 다른 문서에 대한 포인터가 아닌 경우 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="6522c-169">리디렉션을 추가하는 경우 이전 파일도 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="6522c-170">새 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="6522c-170">Creating a new article</span></span>

<span data-ttu-id="6522c-171">다음 워크플로를 *사용하여* 웹 브라우저에서 GitHub를 통해 설명서 리포지터에 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="6522c-172">MicrosoftDocs/mixed-reality 'master' 분기(오른쪽 위에 있는 포크 단추 사용)에서 **포크를** 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="6522c-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![마스터 분기를 분기합니다.](images/forkbranch.png)
   
2. <span data-ttu-id="6522c-174">"mixed-reality-docs" 폴더에서 오른쪽 \*\*\*\* 위에 새 파일 만들기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="6522c-175">문서의 페이지 이름을 만들고(공백 대신 하이픈을 사용하며 문장 부호나 아포스트로피를 사용하지 않습니다) ".md"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![새 페이지의 이름을 지정합니다.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="6522c-177">"mixed-reality-docs" 폴더 내에서 새 문서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="6522c-178">새 파일 이름 줄에서 "/mixed-reality-docs/"를 확인하여 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="6522c-179">새 페이지의 맨 위에 다음 메타데이터 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="6522c-180">위의 섹션의 지침에 따라 관련 메타데이터 [필드를 입력합니다.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="6522c-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="6522c-181">Markdown 기본을 사용하여 문서 [콘텐츠를 작성합니다.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="6522c-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="6522c-182">다른 관련 문서에 대한 링크가 있는 문서 `## See also` 아래쪽에 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="6522c-183">완료되면 새 **파일 커밋을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6522c-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="6522c-184">새 **끌어오기** 요청을 선택하고 포크의 '마스터' 분기를 MicrosoftDocs/mixed-reality 'master'로 병합합니다(화살표가 올바른 방법을 가리키고 있는지 확인).</span><span class="sxs-lookup"><span data-stu-id="6522c-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![포크에서 MicrosoftDocs/혼합 현실로 끌어오기 요청 만들기](images/pr-to-master.png)

## <span data-ttu-id="6522c-186">Markdown 기본</span><span class="sxs-lookup"><span data-stu-id="6522c-186">Markdown basics</span></span>

<span data-ttu-id="6522c-187">다음 리소스는 Markdown 언어를 사용하여 설명서를 편집하는 방법을 배우는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="6522c-188">Markdown 기본</span><span class="sxs-lookup"><span data-stu-id="6522c-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="6522c-189">표식 작성을 위한 추가 docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6522c-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="6522c-190">테이블 추가</span><span class="sxs-lookup"><span data-stu-id="6522c-190">Adding tables</span></span>

<span data-ttu-id="6522c-191">표 스타일 docs.microsoft.com 때문에 인라인 CSS를 사용해도 테두리나 사용자 지정 스타일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="6522c-192">잠시 동안 작동하지만 결국 플랫폼에서 스타일이 표에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="6522c-193">따라서 테이블을 간단하게 계획하십시오.</span><span class="sxs-lookup"><span data-stu-id="6522c-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="6522c-194">[다음은 Markdown 테이블을 쉽게 만드는 사이트입니다.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="6522c-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="6522c-195">문서 [코드용 Docs Markdown Extension for Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) 코드를 사용하여 설명서를 편집하는 경우 Visual Studio [코드(아래](#using-visual-studio-code) 참조)를 사용하여 테이블을 쉽게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="6522c-196">이미지 추가</span><span class="sxs-lookup"><span data-stu-id="6522c-196">Adding images</span></span>

<span data-ttu-id="6522c-197">리포지터의 "mixed-reality-docs/images" 폴더에 이미지를 업로드한 다음 문서에서 적절히 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="6522c-198">이미지가 자동으로 전체 크기로 표시되어 큰 이미지가 문서의 전체 너비를 채우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="6522c-199">이미지를 업로드하기 전에 이미지의 크기 조정을 미리 조정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="6522c-200">권장되는 너비는 600에서 700픽셀 사이입니다. 그러나 각각 조밀한 스크린샷 또는 스크린샷의 일부인 경우 크기를 조정하거나 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="6522c-201">이미지를 포크된 리포지 파일로만 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="6522c-202">따라서 문서에 이미지를 추가하려면 [Visual Studio Code를](#using-visual-studio-code) 사용하여 먼저 포크의 "이미지" 폴더에 이미지를 추가하거나 웹 브라우저에서 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="6522c-203">MicrosoftDocs/mixed-reality 리포지토를 포크했습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="6522c-204">포크에서 문서를 편집했습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="6522c-205">문서에서 참조하는 이미지를 포크의 "mixed-reality-docs/images" 폴더에 업로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="6522c-206">MicrosoftDocs/mixed-reality '마스터' 분기에 포크를 병합하는 끌어오기 요청을 생성했습니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6522c-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="6522c-207">자체의 포크 리포지터를 설정하는 방법을 알아보십시오. 새 문서를 만드는 방법에 대한 [지침을 따르세요.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="6522c-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="6522c-208">작업 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6522c-208">Previewing your work</span></span>

<span data-ttu-id="6522c-209">웹 브라우저를 통해 GitHub에서 편집하는 동안 \*\*\*\* 페이지 위쪽의 미리 보기 탭을 선택하여 커밋하기 전에 작업을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="6522c-210">Microsoft 직원만 review.docs.microsoft.com 변경 내용을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="6522c-211">Microsoft 직원: 기여한 내용이 '마스터' 분기에 병합된 후 공개되기 전에 콘텐츠를 검토할 수 https://review.docs.microsoft.com/hololens?branch=master 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="6522c-212">왼쪽 열의 내용 표를 사용하여 문서를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="6522c-213">브라우저에서 편집 및 데스크톱 클라이언트로 편집</span><span class="sxs-lookup"><span data-stu-id="6522c-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="6522c-214">브라우저에서 편집하는 것이 빠르게 변경하는 가장 쉬운 방법입니다. 그러나 몇 가지 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="6522c-215">맞춤법 검사를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-215">You don't get spell-check.</span></span>
- <span data-ttu-id="6522c-216">다른 문서에 대한 스마트 연결은 얻을 수 없습니다(문서의 파일 이름을 수동으로 입력해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="6522c-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="6522c-217">이미지를 업로드하고 참조하기가 고민할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="6522c-218">이러한 문제를 처리하지 않는 경우 기여할 때 몇 가지 유용한 Visual Studio [코드와](https://code.visualstudio.com/) 같은 데스크톱 [클라이언트를](#useful-extensions) 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="6522c-219">코드 Visual Studio 사용</span><span class="sxs-lookup"><span data-stu-id="6522c-219">Using Visual Studio Code</span></span>

<span data-ttu-id="6522c-220">위에 [나열된](#editing-in-the-browser-vs-editing-with-a-desktop-client)이유로 웹 브라우저 대신 데스크톱 클라이언트를 사용하여 문서를 편집하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="6522c-221">이 코드는 [Visual Studio 좋습니다.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="6522c-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="6522c-222">Setup</span><span class="sxs-lookup"><span data-stu-id="6522c-222">Setup</span></span>

<span data-ttu-id="6522c-223">다음 단계에 따라 이 리포지 Visual Studio 코드가 작동하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="6522c-224">웹 브라우저에서:</span><span class="sxs-lookup"><span data-stu-id="6522c-224">In a web browser:</span></span>
    1. <span data-ttu-id="6522c-225">[PC용 Git를 설치합니다.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="6522c-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="6522c-226">코드 [Visual Studio 설치합니다.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="6522c-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="6522c-227">[아직 MicrosoftDocs/혼합](#creating-a-new-article) 현실을 포크하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="6522c-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="6522c-228">포크에서 복제를 **선택하거나 URL을 다운로드하여** 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="6522c-229">다음 코드에서 포크의 로컬 복제본을 Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6522c-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="6522c-230">보기 **메뉴에서** 명령 **팔레트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6522c-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="6522c-231">"Git: Clone"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="6522c-232">복사한 URL을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="6522c-233">PC에서 복제본을 저장할 위치를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="6522c-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="6522c-234">**팝업에서** 리포지터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="6522c-235">문서 편집</span><span class="sxs-lookup"><span data-stu-id="6522c-235">Editing documentation</span></span>

<span data-ttu-id="6522c-236">다음 워크플로를 사용하여 Visual Studio 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="6522c-237">문서 편집 [](#editing-an-existing-article) 및 만들기에 대한 모든 지침과 위의 [Markdown](#markdown-basics)편집 기본 사항은 Visual Studio 코드를 사용할 때 적용됩니다. [](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="6522c-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="6522c-238">복제된 포크가 공식 리포지타이어를 통해 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="6522c-239">웹 브라우저에서 MicrosoftDocs/mixed-reality '마스터'의 다른 참가자의 최근 변경 내용을 포크에 동기화하는 끌어오기 요청을 생성합니다(화살표가 올바른 방법을 가리키고 있는지 확인).</span><span class="sxs-lookup"><span data-stu-id="6522c-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![MicrosoftDocs/mixed-reality에서 포크로 변경 내용 동기화](images/sync-repos.png)
      
   2. <span data-ttu-id="6522c-241">Visual Studio 코드에서 동기화 단추를 선택하여 최신 업데이트된 포크를 로컬 복제본에 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![동기화 단추 이미지 클릭](images/sync-clone.png)
      
2. <span data-ttu-id="6522c-243">코드 코드를 사용하여 복제된 리포지타이트에서 Visual Studio 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="6522c-244">하나 이상의 문서를 편집합니다(필요한 경우 이미지를 "images" 폴더에 추가).</span><span class="sxs-lookup"><span data-stu-id="6522c-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="6522c-245">**탐색기에서** 변경 **내용을 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="6522c-245">**Save** changes in **Explorer**.</span></span>
      
      ![탐색기에서 "모두 저장"을 선택](images/explorer-save.png)
      
   3. <span data-ttu-id="6522c-247">**원본 제어의** 모든 변경 내용을 커밋합니다(메시지가 표시될 때 커밋 메시지 쓰기). \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6522c-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![소스 제어에서 "모두 커밋"을 선택](images/source-control-commit.png)
      
   4. <span data-ttu-id="6522c-249">동기화 **단추를 선택하여** 변경 내용을 원본(GitHub의 포크)에 다시 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![동기화 단추 클릭](images/sync-back.png)
      
3. <span data-ttu-id="6522c-251">웹 브라우저에서 포크의 새로운 변경 내용을 MicrosoftDocs/mixed-reality '마스터'에 다시 동기화하는 끌어오기 요청을 생성합니다(화살표가 올바른 방법을 가리키고 있는지 확인).</span><span class="sxs-lookup"><span data-stu-id="6522c-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![포크에서 MicrosoftDocs/혼합 현실로 끌어오기 요청 만들기](images/pr-to-master.png)

### <span data-ttu-id="6522c-253">유용한 확장</span><span class="sxs-lookup"><span data-stu-id="6522c-253">Useful extensions</span></span>

<span data-ttu-id="6522c-254">다음 Visual Studio 코드 확장은 문서를 편집할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="6522c-255">Visual Studio 코드에 대한 [Docs Markdown 확장](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt+M을** 사용하여 다음과 같은 docs 제작 옵션의 메뉴를 표시하세요.</span><span class="sxs-lookup"><span data-stu-id="6522c-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="6522c-256">업로드한 이미지를 검색하고 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="6522c-257">목록, 표 및 docs 관련 설명선과 같은 서식을 `>[!NOTE]` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="6522c-258">내부 링크 및 책갈피(페이지 내의 특정 섹션에 대한 링크)를 검색하고 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="6522c-259">서식 오류가 강조 표시됩니다(자세한 내용은 오류 위에 마우스를 놓아야 합니다).</span><span class="sxs-lookup"><span data-stu-id="6522c-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="6522c-260">[코드 맞춤법 검사기](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - 철자가 떨어졌다는 단어에 밑선이 그어지기 올바른 단어의 선택이 없는 단어를 마우스 오른쪽 단추로 클릭하여 변경하거나 사전에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6522c-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
