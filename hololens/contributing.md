---
title: 영향을 주는 지침
description: GitHub-flavored Markdown를 사용 하 여 docs.microsoft.com 플랫폼에서 HoloLens 문서에 참여 하는 방법을 알아봅니다.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635673"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="a79d0-103">HoloLens 설명서에 기여</span><span class="sxs-lookup"><span data-stu-id="a79d0-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="a79d0-104">[HoloLens 설명서](https://github.com/MicrosoftDocs/Hololens)를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="a79d0-105">이 리포지토리에서 만들거나 편집 하는 모든 문서는 **공용에 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a79d0-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="a79d0-106">HoloLens 문서는 markdig 기능에서 GitHub-flavored Markdown를 사용 하는 docs.microsoft.com 플랫폼에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="a79d0-107">이 리포지토리에서 편집 하는 콘텐츠는/hololens.에서 표시 되는 스타일 있는 페이지로 서식 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="a79d0-108">이 페이지에서는 Markdown 기본 사항에 기여 하 고 연결 하는 데 필요한 기본 단계 및 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="a79d0-109">참가 해 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="a79d0-110">사용 가능한 리포지토리</span><span class="sxs-lookup"><span data-stu-id="a79d0-110">Available repos</span></span>

| <span data-ttu-id="a79d0-111">리포지토리 이름</span><span class="sxs-lookup"><span data-stu-id="a79d0-111">Repository name</span></span> | <span data-ttu-id="a79d0-112">URL</span><span class="sxs-lookup"><span data-stu-id="a79d0-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="a79d0-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="a79d0-113">HoloLens</span></span> | [<span data-ttu-id="a79d0-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="a79d0-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="a79d0-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="a79d0-115">Mixed Reality</span></span> | [<span data-ttu-id="a79d0-116">MicrosoftDocs/mixed-현실</span><span class="sxs-lookup"><span data-stu-id="a79d0-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="a79d0-117">VR 매니아 가이드</span><span class="sxs-lookup"><span data-stu-id="a79d0-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="a79d0-118">MicrosoftDocs/mixed-현실/열성적인</span><span class="sxs-lookup"><span data-stu-id="a79d0-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="a79d0-119">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="a79d0-119">Before you start</span></span>

<span data-ttu-id="a79d0-120">계정이 아직 없는 경우 [GitHub 계정을 만들어야](https://github.com/join)합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="a79d0-121">microsoft 직원 인 경우 [microsoft 오픈 소스 포털](https://repos.opensource.microsoft.com/)의 microsoft 별칭에 GitHub 계정을 연결 하세요.</span><span class="sxs-lookup"><span data-stu-id="a79d0-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="a79d0-122">**"Microsoft"** 및 **"MicrosoftDocs"** 조직에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="a79d0-123">GitHub 계정을 설정할 때 다음과 같은 보안 예방 조치를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="a79d0-124">[GitHub 계정에 대 한 강력한 암호](https://github.com/settings/admin)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="a79d0-125">[2 단계 인증](https://github.com/settings/two_factor_authentication/configure)을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="a79d0-126">[복구 코드](https://github.com/settings/auth/recovery-codes) 를 안전한 장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="a79d0-127">[공개 프로필 설정을](https://github.com/settings/profile)업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="a79d0-128">사용자의 이름을 설정 하 고 *전자 메일 주소를 표시 하지 않도록* *공용 전자 메일* 을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="a79d0-129">사용자가 참여 하는 문서 페이지에 미리 보기가 표시 되기 때문에 프로필 사진을 업로드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="a79d0-130">명령줄을 사용 하려는 경우 [Windows에 대해 Git 자격 증명 관리자](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="a79d0-131">이렇게 하면 기여를 할 때마다 암호를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="a79d0-132">게시 시스템은 GitHub 연결 되어 있으므로 이러한 단계가 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="a79d0-133">GitHub 별칭을 사용 하 여 각 아티클에 대 한 작성자 또는 참가자로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="a79d0-134">기존 문서 편집</span><span class="sxs-lookup"><span data-stu-id="a79d0-134">Editing an existing article</span></span>

<span data-ttu-id="a79d0-135">다음 워크플로를 사용 하 여 웹 브라우저에서 GitHub를 통해 *기존 문서* 를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="a79d0-136">"Mixed reality-docs" 폴더에서 편집 하려는 문서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="a79d0-137">오른쪽 위에 있는 편집 단추 (연필 아이콘)를 선택 하면 삭제 가능한 분기가 ' 마스터 ' 분기 밖으로 자동으로 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![문서를 편집 합니다.](images/editpage.png)
   
3. <span data-ttu-id="a79d0-139">["Markdown 기본 사항"](#markdown-basics)에 따라 아티클의 내용을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="a79d0-140">각 문서의 맨 위에 있는 메타 데이터를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="a79d0-141">**제목**: 문서를 볼 때 브라우저 탭에 표시 되는 페이지 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="a79d0-142">페이지 제목은 SEO 및 인덱싱에 사용 되므로 필요한 경우를 제외 하 고는 제목을 변경 하지 않습니다. 단, 설명서를 공개 하기 전에는이 작업이 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="a79d0-143">**설명**: SEO 및 검색을 향상 시키는 아티클의 콘텐츠에 대 한 간단한 설명을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="a79d0-144">**작성자**: 페이지의 기본 소유자 인 경우 여기에 GitHub 별칭을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="a79d0-145">**ms author**: 페이지의 기본 소유자 인 경우 여기에 Microsoft 별칭을 추가 @microsoft.com 합니다 (별칭만 필요 없음).</span><span class="sxs-lookup"><span data-stu-id="a79d0-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="a79d0-146">**ms. 날짜**: 페이지에 주요 콘텐츠를 추가 하는 경우에는 날짜를 업데이트 하지만 설명, 서식, 문법 또는 철자와 같은 픽스는 업데이트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="a79d0-147">**키워드**: SEO의 키워드 지원 (검색 엔진 최적화).</span><span class="sxs-lookup"><span data-stu-id="a79d0-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="a79d0-148">사용자의 문서와 관련 된 키워드를 쉼표와 공백으로 구분 하 고 목록에서 마지막 키워드 뒤에 문장 부호는 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="a79d0-149">모든 문서에 적용 되는 전역 키워드는 다른 곳에서 관리 되므로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="a79d0-150">문서 편집을 완료 한 후 아래로 스크롤하여 **파일 변경 내용 제안** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="a79d0-151">다음 페이지에서 **끌어오기 요청 만들기** 를 선택 하 여 자동으로 생성 된 분기를 ' 마스터 '에 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="a79d0-152">편집 하려는 다음 문서에 대해 위의 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="a79d0-153">기존 아티클 이름 바꾸기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="a79d0-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="a79d0-154">변경 시 기존 아티클의 이름을 바꾸거나 삭제 하는 경우에는 리디렉션을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="a79d0-155">이렇게 하면 기존 문서에 대 한 링크를 가진 모든 사용자가 올바른 위치가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="a79d0-156">리디렉션은 리포지토리의 루트에 있는 파일의 .openpublishing.redirection.js에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="a79d0-157">.openpublishing.redirection.js에 대 한 리디렉션을 추가 하려면 배열에 항목을 추가 합니다 `redirections` .</span><span class="sxs-lookup"><span data-stu-id="a79d0-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="a79d0-158">는 `source_path` 제거 하는 이전 아티클의 상대 저장소 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="a79d0-159">경로는로 시작 `mixed-reality-docs` 하 고로 끝나야 `.md` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="a79d0-160">는 `redirect_url` 이전 문서에서 새 아티클에 대 한 상대 공용 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="a79d0-161">이 URL은  `mixed-reality-docs` `.md` 리포지토리 경로가 아니라 공용 url을 참조 하므로이 url에 또는가 포함 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="a79d0-162">를 사용 하 여 새 문서 내의 섹션에 연결할 `#section` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="a79d0-163">필요한 경우 여기서 다른 사이트에 대 한 절대 경로를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="a79d0-164">`redirect_document_id` 이전 파일의 문서 ID를 유지할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="a79d0-165">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-165">The default is `false`.</span></span> <span data-ttu-id="a79d0-166">`true`리디렉션된 아티클의 특성 값을 유지 하려는 경우에 사용 합니다 `ms.documentid` .</span><span class="sxs-lookup"><span data-stu-id="a79d0-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="a79d0-167">문서 ID를 유지 하는 경우 페이지 보기 및 순위와 같은 데이터가 대상 문서에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="a79d0-168">리디렉션이 주로 이름 바꾸기 인 경우에는이 작업을 수행 하 고, 동일한 콘텐츠 중 일부만 포함 하는 다른 문서에 대 한 포인터는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="a79d0-169">리디렉션을 추가 하는 경우에도 이전 파일을 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="a79d0-170">새 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="a79d0-170">Creating a new article</span></span>

<span data-ttu-id="a79d0-171">다음 워크플로를 사용 하 여 웹 브라우저에서 GitHub를 통해 설명서 리포지토리에서 *새 문서를 만들* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="a79d0-172">오른쪽 위에 있는 **포크** 단추를 사용 하 여 MicrosoftDocs/mixed reality ' master ' 분기에서 포크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![마스터 분기를 포크 합니다.](images/forkbranch.png)
   
2. <span data-ttu-id="a79d0-174">"Mixed reality-docs" 폴더의 오른쪽 위에서 **새 파일 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="a79d0-175">문서에 대 한 페이지 이름 (공백 대신 하이픈을 사용 하 고 구두점 또는 아포스트로피를 사용 하지 않음)을 만든 후 ".ma"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![새 페이지의 이름을로 합니다.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="a79d0-177">"Mixed reality-docs" 폴더 내에서 새 문서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="a79d0-178">새 파일 이름 줄에서 "/mixed-reality-docs/"를 확인 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="a79d0-179">새 페이지 위쪽에 다음 메타 데이터 블록을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="a79d0-180">[위의 섹션](#editing-an-existing-article)에 설명 된 지침에 따라 관련 메타 데이터 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="a79d0-181">[Markdown 기본 사항을](#markdown-basics)사용 하 여 문서 콘텐츠를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="a79d0-182">`## See also`문서의 맨 아래에 있는 섹션을 다른 관련 문서에 대 한 링크와 함께 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="a79d0-183">완료 되 면 **새 파일 커밋** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="a79d0-184">**새 끌어오기 요청** 을 선택 하 고 포크의 ' 마스터 ' 분기를 MicrosoftDocs/mixed-현실 ' master '에 병합 합니다 (화살표가 올바른 방법을 가리키는지 확인).</span><span class="sxs-lookup"><span data-stu-id="a79d0-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![포크에서 MicrosoftDocs/mixed reality로 끌어오기 요청 만들기](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="a79d0-186">Markdown 기본 사항</span><span class="sxs-lookup"><span data-stu-id="a79d0-186">Markdown basics</span></span>

<span data-ttu-id="a79d0-187">다음 리소스는 Markdown 언어를 사용 하 여 문서를 편집 하는 방법을 배우는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="a79d0-188">Markdown 기본 사항</span><span class="sxs-lookup"><span data-stu-id="a79d0-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="a79d0-189">Docs.microsoft.com에 대 한 Markdown 쓰기에 대 한 추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a79d0-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="a79d0-190">테이블 추가</span><span class="sxs-lookup"><span data-stu-id="a79d0-190">Adding tables</span></span>

<span data-ttu-id="a79d0-191">스타일 docs.microsoft.com 스타일을 지정 하는 방식 때문에 인라인 CSS를 시도 하더라도 테두리나 사용자 지정 스타일은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="a79d0-192">짧은 시간 동안 작동 하는 것 처럼 보이지만 결국 플랫폼은 테이블에서 스타일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="a79d0-193">따라서 미리 계획 하 고 테이블을 단순하게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="a79d0-194">[Markdown 테이블을 쉽게 만들 수 있는 사이트는 다음과 같습니다](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="a79d0-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="a79d0-195">[Visual Studio Code에 대 한 Docs Markdown 확장](/teamblog/docs-extension) 은 [Visual Studio Code (아래 참조)](#using-visual-studio-code) 를 사용 하 여 문서를 편집 하는 경우에도 테이블을 쉽게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="a79d0-196">이미지 추가</span><span class="sxs-lookup"><span data-stu-id="a79d0-196">Adding images</span></span>

<span data-ttu-id="a79d0-197">리포지토리의 "mixed reality-docs/images" 폴더에 이미지를 업로드 한 다음 문서에서 적절 하 게 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="a79d0-198">이미지가 자동으로 전체 크기로 표시 됩니다. 즉, 큰 이미지는 문서의 전체 너비를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="a79d0-199">이미지를 업로드 하기 전에 미리 크기를 조정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="a79d0-200">권장 되는 너비는 600 픽셀에서 700 픽셀 사이 이지만, 조밀한 스크린샷 또는 스크린 샷의 분수 인 경우 크기를 조정 하거나 축소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a79d0-201">병합 하기 전에 분기 리포지토리에만 이미지를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="a79d0-202">따라서 문서에 이미지를 추가 하려면 먼저 [Visual Studio Code를 사용](#using-visual-studio-code) 하 여 포크의 "images" 폴더에 이미지를 추가 하거나 웹 브라우저에서 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="a79d0-203">MicrosoftDocs/mixed reality 리포지토리를 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="a79d0-204">포크에서 문서를 편집 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="a79d0-205">문서에서 참조 하는 이미지를 포크의 "mixed reality-docs/images" 폴더에 업로드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="a79d0-206">분기를 MicrosoftDocs/mixed-현실 ' master ' 분기에 병합 하는 **끌어오기 요청** 을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="a79d0-207">사용자 고유의 분기 리포지토리를 설정 하는 방법을 알아보려면 [새 문서 만들기](#creating-a-new-article)에 대 한 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a79d0-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="a79d0-208">작업 미리 보기</span><span class="sxs-lookup"><span data-stu-id="a79d0-208">Previewing your work</span></span>

<span data-ttu-id="a79d0-209">웹 브라우저를 통해 GitHub에서 편집 하는 동안 페이지 맨 위에 있는 **미리 보기** 탭을 선택 하 여 커밋하기 전에 작업을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="a79d0-210">review.docs.microsoft.com의 변경 내용 미리 보기는 Microsoft 직원 에게만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="a79d0-211">Microsoft 직원: 기여를 ' 마스터 ' 분기에 병합 한 후에는 콘텐츠를 검토 하 여 </hololens? branch = master>에서 공용으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="a79d0-212">왼쪽 열에 있는 목차를 사용 하 여 문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="a79d0-213">브라우저에서 편집 및 데스크톱 클라이언트를 사용 하 여 편집</span><span class="sxs-lookup"><span data-stu-id="a79d0-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="a79d0-214">브라우저에서 편집은 빠른 변경을 수행 하는 가장 쉬운 방법 이지만 다음과 같은 몇 가지 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="a79d0-215">맞춤법 검사를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-215">You don't get spell-check.</span></span>
- <span data-ttu-id="a79d0-216">다른 문서에 대 한 스마트 링크를 얻을 수 없습니다 (문서의 파일 이름을 직접 입력 해야 함).</span><span class="sxs-lookup"><span data-stu-id="a79d0-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="a79d0-217">이미지를 업로드 하 고 참조 하는 것이 더 나을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="a79d0-218">이러한 문제를 해결 하는 것이 아닌 경우에는 도움이 될 때 도움이 되는 몇 가지 [유용한 확장과](#useful-extensions) 함께 [Visual Studio Code](https://code.visualstudio.com/) 와 같은 데스크톱 클라이언트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="a79d0-219">Visual Studio Code 사용</span><span class="sxs-lookup"><span data-stu-id="a79d0-219">Using Visual Studio Code</span></span>

<span data-ttu-id="a79d0-220">[위에](#editing-in-the-browser-vs-editing-with-a-desktop-client)나열 된 이유 때문에 웹 브라우저가 아닌 데스크톱 클라이언트를 사용 하 여 문서를 편집 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="a79d0-221">[Visual Studio Code](https://code.visualstudio.com/)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="a79d0-222">설치 프로그램</span><span class="sxs-lookup"><span data-stu-id="a79d0-222">Setup</span></span>

<span data-ttu-id="a79d0-223">이 리포지토리를 사용 하도록 Visual Studio Code를 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="a79d0-224">웹 브라우저에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-224">In a web browser:</span></span>
    1. <span data-ttu-id="a79d0-225">[PC 용 Git를](https://git-scm.com/downloads)설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="a79d0-226">[Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="a79d0-227">[분기 MicrosoftDocs/mixed-현실](#creating-a-new-article) . 아직 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="a79d0-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="a79d0-228">포크에서 **복제 또는 다운로드** 를 선택 하 고 URL을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="a79d0-229">Visual Studio Code에서 포크의 로컬 클론을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="a79d0-230">**보기** 메뉴에서 **명령 팔레트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="a79d0-231">"Git: Clone"을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="a79d0-232">복사한 URL을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="a79d0-233">PC에서 클론을 저장할 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="a79d0-234">팝업에서 **리포지토리 열기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="a79d0-235">문서 편집</span><span class="sxs-lookup"><span data-stu-id="a79d0-235">Editing documentation</span></span>

<span data-ttu-id="a79d0-236">Visual Studio Code를 사용 하 여 설명서를 변경 하려면 다음 워크플로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="a79d0-237">Visual Studio Code 사용 하는 경우에는 문서 [편집](#editing-an-existing-article) 및 [만들기](#creating-a-new-article) 에 대 한 모든 지침과 위에서 [Markdown 편집의 기본](#markdown-basics)사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="a79d0-238">복제 된 분기가 공식 리포지토리를 사용 하 여 최신 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="a79d0-239">웹 브라우저에서 끌어오기 요청을 만들어 MicrosoftDocs/mixed reality의 다른 참가자의 최근 변경 내용을 포크에 동기화 합니다. 화살표가 올바른 방법을 가리키고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![MicrosoftDocs/mixed-현실에서 포크로 변경 내용 동기화](images/sync-repos.png)
      
   2. <span data-ttu-id="a79d0-241">Visual Studio Code에서 동기화 단추를 선택 하 여 새로 업데이트 된 포크를 로컬 클론에 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![동기화 단추 이미지를 클릭 합니다.](images/sync-clone.png)
      
2. <span data-ttu-id="a79d0-243">Visual Studio Code를 사용 하 여 복제 된 리포지토리에서 문서를 만들거나 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="a79d0-244">하나 이상의 문서 (필요한 경우 "images" 폴더에 이미지 추가)를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="a79d0-245">**탐색기** 에서 변경 내용을 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-245">**Save** changes in **Explorer**.</span></span>
      
      ![탐색기에서 "모두 저장"을 선택 합니다.](images/explorer-save.png)
      
   3. <span data-ttu-id="a79d0-247">**소스 제어** 의 모든 변경 내용 **커밋** (메시지가 표시 되 면 쓰기 커밋 메시지).</span><span class="sxs-lookup"><span data-stu-id="a79d0-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![소스 제어에서 "모두 커밋"을 선택 합니다.](images/source-control-commit.png)
      
   4. <span data-ttu-id="a79d0-249">**동기화** 단추를 선택 하 여 변경 내용을 원본으로 다시 동기화 합니다 (GitHub 포크).</span><span class="sxs-lookup"><span data-stu-id="a79d0-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![동기화 단추를 클릭 합니다.](images/sync-back.png)
      
3. <span data-ttu-id="a79d0-251">웹 브라우저에서 끌어오기 요청을 만들어 분기의 새 변경 내용을 MicrosoftDocs/mixed-현실 ' master '로 다시 동기화 합니다. 화살표가 올바른 방법을 가리키고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![포크에서 MicrosoftDocs/mixed reality로 끌어오기 요청 만들기](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="a79d0-253">유용한 확장</span><span class="sxs-lookup"><span data-stu-id="a79d0-253">Useful extensions</span></span>

<span data-ttu-id="a79d0-254">문서를 편집할 때 다음과 같은 Visual Studio Code 확장을 유용 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="a79d0-255">[Visual Studio Code 용 docs Markdown 확장](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt + M** 을 사용 하 여 다음과 같은 docs 제작 옵션 메뉴를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="a79d0-256">업로드 한 이미지를 검색 하 고 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="a79d0-257">목록과 같이 목록, 테이블 및 문서 특정 호출 등의 서식을 추가 `>[!NOTE]` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="a79d0-258">내부 링크와 책갈피를 검색 하 고 참조 합니다 (페이지 내의 특정 섹션에 대 한 링크).</span><span class="sxs-lookup"><span data-stu-id="a79d0-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="a79d0-259">서식 지정 오류가 강조 표시 됩니다. 자세한 내용은 오류를 마우스로 가리키십시오.</span><span class="sxs-lookup"><span data-stu-id="a79d0-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="a79d0-260">[코드 맞춤법 검사기](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -철자가 잘못 된 단어에는 밑줄이 그어집니다. 철자가 잘못 된 단어를 마우스 오른쪽 단추로 클릭 하 여 변경 하거나 사전에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79d0-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
