---
title: "NuGet 4.0 RC のリリース ノート | Microsoft Docs"
author: anangaur
ms.author: anangaur
manager: unniravindranathan
ms.date: 03/03/2017
ms.topic: article
ms.prod: nuget
ms.technology: 
description: "既知の問題、バグ修正、追加された機能、DCR を含む NuGet 4.0 RTM のリリース ノート。"
keywords: "NuGet 4.0 RTM のリリース ノート, バグ修正, 既知の問題, 追加機能, DCR"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: d1ab89f0decb64a64d04dc293e5273b577e8398b
ms.sourcegitcommit: 7969f6cd94eccfee5b62031bb404422139ccc383
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2018
---
# <a name="nuget-40-rtm-release-notes"></a><span data-ttu-id="68f41-104">NuGet 4.0 RTM リリース ノート</span><span class="sxs-lookup"><span data-stu-id="68f41-104">NuGet 4.0 RTM Release Notes</span></span>

<span data-ttu-id="68f41-105">[Visual Studio 2017](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) には NuGet 4.0 が付属しています。NuGet 4.0 には .NET Core のサポートが追加され、品質の改善とパフォーマンスの向上が図られています。</span><span class="sxs-lookup"><span data-stu-id="68f41-105">[Visual Studio 2017](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) comes with NuGet 4.0 which adds support for .NET Core, has a bunch of quality fixes and improves performance.</span></span> <span data-ttu-id="68f41-106">このリリースでは、PackageReference のサポート、MSBuild ターゲットとしての NuGet コマンド、バックグラウンド パッケージの復元など、いくつかの改善点もあります。</span><span class="sxs-lookup"><span data-stu-id="68f41-106">This release also brings several improvements like support for PackageReference, NuGet commands as MSBuild targets, background package restores, and more.</span></span>

## <a name="known-issues"></a><span data-ttu-id="68f41-107">既知の問題</span><span class="sxs-lookup"><span data-stu-id="68f41-107">Known issues</span></span>

### <a name="nuget-restore-may-fail-when-you-have-multiple-projects-referencing-another-project-in-a-solution"></a><span data-ttu-id="68f41-108">複数のプロジェクト参照が 1 つのソリューションの別のプロジェクトを参照しているとき、NuGet の復元が失敗することがある</span><span class="sxs-lookup"><span data-stu-id="68f41-108">NuGet restore may fail when you have multiple projects referencing another project in a solution</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-109">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-109">Issue</span></span>

<span data-ttu-id="68f41-110">あるソリューションで大文字/小文字の区別または相対パスが異なる同じプロジェクトが参照されているとき、NuGet 復元が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="68f41-110">NuGet restore may not work if, in a solution, you have project references to the same project with different casing or with different relative paths.</span></span> [<span data-ttu-id="68f41-111">NuGet#4574</span><span class="sxs-lookup"><span data-stu-id="68f41-111">NuGet#4574</span></span>](https://github.com/NuGet/Home/issues/4574)

#### <a name="workaround"></a><span data-ttu-id="68f41-112">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-112">Workaround</span></span>

<span data-ttu-id="68f41-113">大文字/小文字または相対パスをすべてのプロジェクト参照で同じになるように修正します。</span><span class="sxs-lookup"><span data-stu-id="68f41-113">Fix the casings or relative paths to be the same for all project references.</span></span>

### <a name="while-using-package-manager-console-enter-key-may-not-work"></a><span data-ttu-id="68f41-114">パッケージ マネージャー コンソールの使用中、'Enter' キーが機能しない</span><span class="sxs-lookup"><span data-stu-id="68f41-114">While using Package Manager Console, 'Enter' key may not work</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-115">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-115">Issue</span></span>

<span data-ttu-id="68f41-116">パッケージ マネージャー コンソールで、Enter キーが機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="68f41-116">Occasionally, the enter key does not work in the Package Manager Console.</span></span> <span data-ttu-id="68f41-117">その場合、修正プログラムで進捗状況を確認してください。再現手順について役に立つ情報があれば提供してください。</span><span class="sxs-lookup"><span data-stu-id="68f41-117">If you see this, please check out the progress on the fix, and provide any additional helpful information about your repro steps.</span></span> <span data-ttu-id="68f41-118">[NuGet#4204](https://github.com/NuGet/Home/issues/4204) [NuGet#4570](https://github.com/NuGet/Home/issues/4570)</span><span class="sxs-lookup"><span data-stu-id="68f41-118">[NuGet#4204](https://github.com/NuGet/Home/issues/4204) [NuGet#4570](https://github.com/NuGet/Home/issues/4570)</span></span>

#### <a name="workaround"></a><span data-ttu-id="68f41-119">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-119">Workaround</span></span>

<span data-ttu-id="68f41-120">ソリューションを開く前に、Visual Studio を再起動し、PMC を開いてください。</span><span class="sxs-lookup"><span data-stu-id="68f41-120">Restart Visual Studio and open the PMC before opening the solution.</span></span> <span data-ttu-id="68f41-121">または、`project.lock.json` を削除し、もう一度復元してください。</span><span class="sxs-lookup"><span data-stu-id="68f41-121">Alternatively, try deleting the `project.lock.json` and restoring again.</span></span>

### <a name="in-net-core-projects-you-may-end-up-in-infinite-restore-loop-when-you-use-a-package-containing-an-assembly-with-an-invalid-signature"></a><span data-ttu-id="68f41-122">.NET Core プロジェクトで、署名が無効なアセンブリを含むパッケージを使用するとき、無限の復元ループが発生することがある</span><span class="sxs-lookup"><span data-stu-id="68f41-122">In .NET Core projects, you may end up in infinite restore loop when you use a package containing an assembly with an invalid signature</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-123">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-123">Issue</span></span>

<span data-ttu-id="68f41-124">無効なアセンブリを含むパッケージを使用するとき、あるいはパッケージ バージョンに 'DateTime' ティッカーが設定されているとき、パッケージ復元が無限ループになることがあります。</span><span class="sxs-lookup"><span data-stu-id="68f41-124">Occassionally, when you use a package containing an assembly with an invalid signature or when the package version is set with 'DateTime' ticker, it causes package auto-restore to run in infinite loop.</span></span> [<span data-ttu-id="68f41-125">NuGet#4542</span><span class="sxs-lookup"><span data-stu-id="68f41-125">NuGet#4542</span></span>](https://github.com/NuGet/Home/issues/4542)

#### <a name="workaround"></a><span data-ttu-id="68f41-126">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-126">Workaround</span></span>

<span data-ttu-id="68f41-127">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="68f41-127">There is no workaround at this time.</span></span>

### <a name="you-are-unable-to-view-add-or-update-dotnetclitools-using-nuget-package-manager"></a><span data-ttu-id="68f41-128">NuGet パッケージ マネージャーを使用した DotNetCLITools の表示、追加、更新ができない</span><span class="sxs-lookup"><span data-stu-id="68f41-128">You are unable to view, add, or update DotNetCLITools, using Nuget Package Manager</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-129">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-129">Issue</span></span>

<span data-ttu-id="68f41-130">NuGet パッケージ マネージャーが表示されず、DotNetCLITools を追加または更新できません。</span><span class="sxs-lookup"><span data-stu-id="68f41-130">NuGet Package Manager does not display and does not allow add/update of DotNetCLITools.</span></span> [<span data-ttu-id="68f41-131">NuGet#4256</span><span class="sxs-lookup"><span data-stu-id="68f41-131">NuGet#4256</span></span>](https://github.com/NuGet/Home/issues/4256)

#### <a name="workaround"></a><span data-ttu-id="68f41-132">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-132">Workaround</span></span>

<span data-ttu-id="68f41-133">DotNetCLIToolReferences はプロジェクト ファイルで手動編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68f41-133">DotNetCLIToolReferences must be manually edited in your project file.</span></span>

### <a name="nuget-restore-will-fail-when-you-set-packageid-property-for-projects"></a><span data-ttu-id="68f41-134">プロジェクトの PackageId プロパティを設定すると、NuGet の復元が失敗する</span><span class="sxs-lookup"><span data-stu-id="68f41-134">NuGet restore will fail when you set PackageId property for projects</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-135">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-135">Issue</span></span>

<span data-ttu-id="68f41-136">.NET Core プロジェクトの場合、Visual Studio の NuGet 復元では、プロジェクトの PackageId プロパティが適用されません。</span><span class="sxs-lookup"><span data-stu-id="68f41-136">For .NET Core projects, NuGet restore in Visual Studio does not respect PackageId property of projects.</span></span> [<span data-ttu-id="68f41-137">NuGet#4586</span><span class="sxs-lookup"><span data-stu-id="68f41-137">NuGet#4586</span></span>](https://github.com/NuGet/Home/issues/4586)

#### <a name="workaround"></a><span data-ttu-id="68f41-138">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-138">Workaround</span></span>

<span data-ttu-id="68f41-139">コマンドラインを使用して復元を実行します。</span><span class="sxs-lookup"><span data-stu-id="68f41-139">Run restore using the command-line.</span></span>

### <a name="when-your-project-does-not-have-obj-folder-package-restore-may-fail"></a><span data-ttu-id="68f41-140">プロジェクトに 'obj' フォルダーがないとき、パッケージ復元に失敗する</span><span class="sxs-lookup"><span data-stu-id="68f41-140">When your project does not have 'obj' folder, package restore may fail</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-141">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-141">Issue</span></span>

<span data-ttu-id="68f41-142">'obj' フォルダーが削除されると、Visual Studio は PackageReferences を復元できません。</span><span class="sxs-lookup"><span data-stu-id="68f41-142">Visual Studio fails to restore PackageReferences when 'obj' folder has been deleted.</span></span> [<span data-ttu-id="68f41-143">NuGet#4528</span><span class="sxs-lookup"><span data-stu-id="68f41-143">NuGet#4528</span></span>](https://github.com/NuGet/Home/issues/4528)

#### <a name="workaround"></a><span data-ttu-id="68f41-144">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-144">Workaround</span></span>

<span data-ttu-id="68f41-145">'obj' フォルダーを手動作成すると、復元できるようになります。</span><span class="sxs-lookup"><span data-stu-id="68f41-145">Create 'obj' folder manually and the restore should work.</span></span>

### <a name="manually-updating-packages-using-update-package-in-console-may-fail"></a><span data-ttu-id="68f41-146">コンソールで Update-Package を使用するとき、パッケージを手動更新できないことがある</span><span class="sxs-lookup"><span data-stu-id="68f41-146">Manually updating packages using Update-Package in console may fail</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-147">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-147">Issue</span></span>

<span data-ttu-id="68f41-148">Update-Package は、変換されたばかりの PackageReferences プロジェクトに対して、コンソールで 1 回だけ手動で利用できます。</span><span class="sxs-lookup"><span data-stu-id="68f41-148">Using Update-Package manually in the console only works once for PackageReferences projects that were just converted.</span></span> [<span data-ttu-id="68f41-149">NuGet#4431</span><span class="sxs-lookup"><span data-stu-id="68f41-149">NuGet#4431</span></span>](https://github.com/NuGet/Home/issues/4431)

#### <a name="workaround"></a><span data-ttu-id="68f41-150">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-150">Workaround</span></span>

<span data-ttu-id="68f41-151">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="68f41-151">There is no workaround at this time.</span></span>

### <a name="retargeting-target-framework-version-may-lead-to-incomplete-intellisense"></a><span data-ttu-id="68f41-152">ターゲット フレームワーク バージョンを再ターゲットすると、IntelliSense が不完全になる</span><span class="sxs-lookup"><span data-stu-id="68f41-152">Retargeting target framework version may lead to incomplete Intellisense</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-153">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-153">Issue</span></span>

<span data-ttu-id="68f41-154">Visual Studio では、ターゲット フレームワーク バージョンを再ターゲットすると、IntelliSense が不完全になることがあります。</span><span class="sxs-lookup"><span data-stu-id="68f41-154">Retargeting target framework version may lead to incomplete Intellisense, in Visual Studio.</span></span> <span data-ttu-id="68f41-155">これは、パッケージ マネージャー形式として PackageReferences を使用しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="68f41-155">This happens when you are using PackageReferences as the package manager format.</span></span> [<span data-ttu-id="68f41-156">NuGet#4216</span><span class="sxs-lookup"><span data-stu-id="68f41-156">NuGet#4216</span></span>](https://github.com/NuGet/Home/issues/4216)

#### <a name="workaround"></a><span data-ttu-id="68f41-157">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-157">Workaround</span></span>

<span data-ttu-id="68f41-158">手動で復元します。</span><span class="sxs-lookup"><span data-stu-id="68f41-158">Do a manual restore.</span></span>

### <a name="msbuild-trestore-fails-when-a-project-targeting-net461-references-another-project-targeting-netstandard"></a><span data-ttu-id="68f41-159">.NET461 をターゲットにするプロジェクトが .NETStandard をターゲットにする別のプロジェクトを参照するとき、msbuild /t:restore が失敗する</span><span class="sxs-lookup"><span data-stu-id="68f41-159">msbuild /t:restore fails when a project targeting .NET461 references another project targeting .NETStandard</span></span>

#### <a name="issue"></a><span data-ttu-id="68f41-160">懸案事項</span><span class="sxs-lookup"><span data-stu-id="68f41-160">Issue</span></span>

<span data-ttu-id="68f41-161">.NET461 をターゲットにする PackageReferenece ベースのプロジェクトが .NETStandard をターゲットにする別の PackageReferenece ベースのプロジェクトを参照するとき、msbuild /t:restore が失敗します。</span><span class="sxs-lookup"><span data-stu-id="68f41-161">msbuild /t:restore fails when a PackageReferenece based project targeting .NET461 references another PackageReference based project targeting .NETStandard.</span></span>  [<span data-ttu-id="68f41-162">NuGet#4532</span><span class="sxs-lookup"><span data-stu-id="68f41-162">NuGet#4532</span></span>](https://github.com/NuGet/Home/issues/4532)

#### <a name="workaround"></a><span data-ttu-id="68f41-163">回避策</span><span class="sxs-lookup"><span data-stu-id="68f41-163">Workaround</span></span>

<span data-ttu-id="68f41-164">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="68f41-164">There is no workaround at this time.</span></span>

## <a name="issues-fixed-in-nuget-40-rtm-timeframe"></a><span data-ttu-id="68f41-165">NuGet 4.0 RTM の時間枠で修正された問題</span><span class="sxs-lookup"><span data-stu-id="68f41-165">Issues fixed in NuGet 4.0 RTM timeframe</span></span>

<span data-ttu-id="68f41-166">[NuGet 4.0 RC のリリースノート](../release-notes/nuget-4.0-RC.md) - NuGet 4.0 RC で修正されたすべての問題が掲載されています</span><span class="sxs-lookup"><span data-stu-id="68f41-166">[NuGet 4.0 RC Release Notes](../release-notes/nuget-4.0-RC.md) - Lists all the issues fixed for NuGet 4.0 RC</span></span>

### <a name="features"></a><span data-ttu-id="68f41-167">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="68f41-167">Features</span></span>

- <span data-ttu-id="68f41-168">NuGet.Core.sln の文字列をローカライズする - [#2041](https://github.com/NuGet/Home/issues/2041)</span><span class="sxs-lookup"><span data-stu-id="68f41-168">Localize strings in NuGet.Core.sln - [#2041](https://github.com/NuGet/Home/issues/2041)</span></span>

- <span data-ttu-id="68f41-169">NuGet で強制的に Web アプリケーション プロジェクトを LSL モードに読み込む - [#4258](https://github.com/NuGet/Home/issues/4258)</span><span class="sxs-lookup"><span data-stu-id="68f41-169">Nuget forces to load web application projects in LSL mode - [#4258](https://github.com/NuGet/Home/issues/4258)</span></span>

- <span data-ttu-id="68f41-170">AutoReferenced PackageReference で、"sdk がインストールされている" パッケージの UI のバージョン変更をブロックする機能をサポートする - [#4044](https://github.com/NuGet/Home/issues/4044)</span><span class="sxs-lookup"><span data-stu-id="68f41-170">AutoReferenced PackageReference support to block version changes in UI for "sdk installed" packages - [#4044](https://github.com/NuGet/Home/issues/4044)</span></span>

- <span data-ttu-id="68f41-171">任意のプロジェクトの依存関係に対して PackageSpec.Version を正しく伝える (PackageRef) - [#3902](https://github.com/NuGet/Home/issues/3902)</span><span class="sxs-lookup"><span data-stu-id="68f41-171">Correctly communicate PackageSpec.Version for any project dependencies (PackageRef) - [#3902](https://github.com/NuGet/Home/issues/3902)</span></span>

- <span data-ttu-id="68f41-172">コマンドラインから `.csproj` への参照を削除するためのサポート - [#4101](https://github.com/NuGet/Home/issues/4101)</span><span class="sxs-lookup"><span data-stu-id="68f41-172">support for removing references into `.csproj` from commandline(s) - [#4101](https://github.com/NuGet/Home/issues/4101)</span></span>

- <span data-ttu-id="68f41-173">PackageReference プロジェクト (通常と xplat) と Lightweight ソリューション読み込みの復元をサポートする - [#4003](https://github.com/NuGet/Home/issues/4003)</span><span class="sxs-lookup"><span data-stu-id="68f41-173">Support restore for PackageReference projects (normal and xplat) and Lightweight Solution Load - [#4003](https://github.com/NuGet/Home/issues/4003)</span></span>

- <span data-ttu-id="68f41-174">コマンドラインからの `.csproj` への参照を追加する機能のサポート - [#3751](https://github.com/NuGet/Home/issues/3751)</span><span class="sxs-lookup"><span data-stu-id="68f41-174">support for adding references into `.csproj` from commandline(s) - [#3751](https://github.com/NuGet/Home/issues/3751)</span></span>

- <span data-ttu-id="68f41-175">`packages.config` or `project.json` の NuGet 復元のライトウェイト ソリューション ロードのサポート  - [#3711](https://github.com/NuGet/Home/issues/3711)</span><span class="sxs-lookup"><span data-stu-id="68f41-175">Support NuGet restore for Lightweight Solution Load for `packages.config` or `project.json` - [#3711](https://github.com/NuGet/Home/issues/3711)</span></span>

- <span data-ttu-id="68f41-176">nuget で生成されたターゲット ファイルの contentFiles のサポート - [#3683](https://github.com/NuGet/Home/issues/3683)</span><span class="sxs-lookup"><span data-stu-id="68f41-176">contentFiles support in nuget generated targets file - [#3683](https://github.com/NuGet/Home/issues/3683)</span></span>

- <span data-ttu-id="68f41-177">MSBuild を使用して Mac 上で nuget.exe の検証の Mono CI を確立する - [#3646](https://github.com/NuGet/Home/issues/3646)</span><span class="sxs-lookup"><span data-stu-id="68f41-177">Establish a Mono CI for nuget.exe validation on Mac using MSBuild - [#3646](https://github.com/NuGet/Home/issues/3646)</span></span>

- <span data-ttu-id="68f41-178">v2 NuGet.Core 依存関係から NuGet を移動する - [#3645](https://github.com/NuGet/Home/issues/3645)</span><span class="sxs-lookup"><span data-stu-id="68f41-178">Move NuGet off of v2 NuGet.Core dependencies - [#3645](https://github.com/NuGet/Home/issues/3645)</span></span>

### <a name="bugs"></a><span data-ttu-id="68f41-179">バグ</span><span class="sxs-lookup"><span data-stu-id="68f41-179">Bugs</span></span>

- <span data-ttu-id="68f41-180">Visual Studio の NuGet 復元で、プロジェクトの PackageId プロパティが適用されない - [#4586](https://github.com/NuGet/Home/issues/4586)</span><span class="sxs-lookup"><span data-stu-id="68f41-180">NuGet restore in Visual Studio does not respect PackageId property of projects - [#4586](https://github.com/NuGet/Home/issues/4586)</span></span>

- <span data-ttu-id="68f41-181">vsix パッケージにパッケージを追加するときの NuGet ProjectSystemCache エラー - [#4545](https://github.com/NuGet/Home/issues/4545)</span><span class="sxs-lookup"><span data-stu-id="68f41-181">NuGet ProjectSystemCache error when adding package in vsix package - [#4545](https://github.com/NuGet/Home/issues/4545)</span></span>

- <span data-ttu-id="68f41-182">IncludeSource が複数の TFM を持つプロジェクトで使用されている場合、パックから例外がスローされる - [#4536](https://github.com/NuGet/Home/issues/4536)</span><span class="sxs-lookup"><span data-stu-id="68f41-182">Pack throws exception if IncludeSource is used in a project with multiple TFMs - [#4536](https://github.com/NuGet/Home/issues/4536)</span></span>

- <span data-ttu-id="68f41-183">ソリューション全体のパッケージ管理から更新プログラムを使用すると、VS 2017 RC3 がクラッシュする - [#4474](https://github.com/NuGet/Home/issues/4474)</span><span class="sxs-lookup"><span data-stu-id="68f41-183">VS 2017 RC3 crashes on using update from Solution-wide package management - [#4474](https://github.com/NuGet/Home/issues/4474)</span></span>

- <span data-ttu-id="68f41-184">新しくインストールしたパッケージをアンインストールできない - [#4435](https://github.com/NuGet/Home/issues/4435)</span><span class="sxs-lookup"><span data-stu-id="68f41-184">Cannot uninstall newly installed package  - [#4435](https://github.com/NuGet/Home/issues/4435)</span></span>

- <span data-ttu-id="68f41-185">PackageRef に移行すると、ハイブリッド ソリューションで復元動作が正常に実行されません - [#4433](https://github.com/NuGet/Home/issues/4433)</span><span class="sxs-lookup"><span data-stu-id="68f41-185">When migrating to PackageRef, hybrid solutions have strange restore behavior - [#4433](https://github.com/NuGet/Home/issues/4433)</span></span>

- <span data-ttu-id="68f41-186">NuGet 操作 (インストール、更新、復元) を開始した直後にビルドすると、VS がハングすることがある - [#4420](https://github.com/NuGet/Home/issues/4420)</span><span class="sxs-lookup"><span data-stu-id="68f41-186">Building soon after starting NuGet operation (install, update, restore), can cause VS to Hang - [#4420](https://github.com/NuGet/Home/issues/4420)</span></span>

- <span data-ttu-id="68f41-187">UI ハング - NuGet.SolutionRestoreManager.RestoreManagerPackage の初期化中のデッドロック - [#4371](https://github.com/NuGet/Home/issues/4371)</span><span class="sxs-lookup"><span data-stu-id="68f41-187">UI Hang - Deadlock initializing NuGet.SolutionRestoreManager.RestoreManagerPackage [#4371](https://github.com/NuGet/Home/issues/4371)</span></span>

- <span data-ttu-id="68f41-188">パッケージの追加コマンドで、要素ではなく属性としてバージョンが追加される必要がある - [#4325](https://github.com/NuGet/Home/issues/4325)</span><span class="sxs-lookup"><span data-stu-id="68f41-188">add package command should add version as attribute instead of element - [#4325](https://github.com/NuGet/Home/issues/4325)</span></span>

- <span data-ttu-id="68f41-189">Dotnet Restore foo.sln -- SLN の構成によって復元グラフにプロジェクトの重複が発生する (ただし、構成は異なる) ときに失敗する - [#4316](https://github.com/NuGet/Home/issues/4316)</span><span class="sxs-lookup"><span data-stu-id="68f41-189">Dotnet Restore foo.sln -- fails when configurations in SLN cause duplicate (but diff config) projects in restore graph - [#4316](https://github.com/NuGet/Home/issues/4316)</span></span>

- <span data-ttu-id="68f41-190">コンテンツのみのパッケージ - [#3668](https://github.com/NuGet/Home/issues/3668)</span><span class="sxs-lookup"><span data-stu-id="68f41-190">Content only packages - [#3668](https://github.com/NuGet/Home/issues/3668)</span></span>

- <span data-ttu-id="68f41-191">既定で、パッケージ形式の選択オプションが無効になっている - [#4468](https://github.com/NuGet/Home/issues/4468)</span><span class="sxs-lookup"><span data-stu-id="68f41-191">By default opt out of package format selector option - [#4468](https://github.com/NuGet/Home/issues/4468)</span></span>

- <span data-ttu-id="68f41-192">パフォーマンス: CreateUAP_CSharp_VS.01.1.Create プロジェクトの Duration_TotalElapsedTime が 3,153.570 ミリ秒 (149.1%) 遅くなった。</span><span class="sxs-lookup"><span data-stu-id="68f41-192">Perf: CreateUAP_CSharp_VS.01.1.Create project regressed Duration_TotalElapsedTime by 3,153.570 ms (149.1%).</span></span> <span data-ttu-id="68f41-193">ベースライン 26129.02 - [#4452](https://github.com/NuGet/Home/issues/4452)</span><span class="sxs-lookup"><span data-stu-id="68f41-193">Baseline 26129.02 - [#4452](https://github.com/NuGet/Home/issues/4452)</span></span>

- <span data-ttu-id="68f41-194">パフォーマンス: ManagedLangs_CS_DDRIT.0300.Rebuild ソリューションの Duration_TotalElapsedTime が 1.5 秒遅くなった。</span><span class="sxs-lookup"><span data-stu-id="68f41-194">Perf: ManagedLangs_CS_DDRIT.0300.Rebuild Solution regressed Duration_TotalElapsedTime by 1.5sec.</span></span> <span data-ttu-id="68f41-195">ベースライン 26105 - [#4441](https://github.com/NuGet/Home/issues/4441)</span><span class="sxs-lookup"><span data-stu-id="68f41-195">Baseline 26105 - [#4441](https://github.com/NuGet/Home/issues/4441)</span></span>

- <span data-ttu-id="68f41-196">マルチ TFM プロジェクトで候補表示が失敗する - [#4419](https://github.com/NuGet/Home/issues/4419)</span><span class="sxs-lookup"><span data-stu-id="68f41-196">Nomination fails in multi-TFM projects - [#4419](https://github.com/NuGet/Home/issues/4419)</span></span>

- <span data-ttu-id="68f41-197">パフォーマンス: WebForms_DDRIT.1200.Close Solution の VM_ImagesInMemory_Total_devenv は 3.000 カウント (0.5%) 低下しました。</span><span class="sxs-lookup"><span data-stu-id="68f41-197">Perf: WebForms_DDRIT.1200.Close Solution regressed VM_ImagesInMemory_Total_devenv by 3.000 Count (0.5%).</span></span> <span data-ttu-id="68f41-198">ベースライン 26123.04 - [#4408](https://github.com/NuGet/Home/issues/4408)</span><span class="sxs-lookup"><span data-stu-id="68f41-198">Baseline 26123.04 - [#4408](https://github.com/NuGet/Home/issues/4408)</span></span>

- <span data-ttu-id="68f41-199">vsfeedback - netcoreapp1.1 をターゲットとするときのパックの警告 - [#4397](https://github.com/NuGet/Home/issues/4397)</span><span class="sxs-lookup"><span data-stu-id="68f41-199">vsfeedback - Pack warnings when targeting netcoreapp1.1 - [#4397](https://github.com/NuGet/Home/issues/4397)</span></span>

- <span data-ttu-id="68f41-200">空の ASP.NET Core Web アプリケーションに NuGet パッケージを追加しようとすると、PathTooLongException が発生する - [#4391](https://github.com/NuGet/Home/issues/4391)</span><span class="sxs-lookup"><span data-stu-id="68f41-200">PathTooLongException when trying to add a NuGet package to empty ASP.NET Core web application - [#4391](https://github.com/NuGet/Home/issues/4391)</span></span>

- <span data-ttu-id="68f41-201">パックの実行頻度が高すぎる -- ターゲット "Pack" が関係するターゲット依存関係グラフに循環依存の関係が存在するため、dotnet pack が失敗する - [#4381](https://github.com/NuGet/Home/issues/4381)</span><span class="sxs-lookup"><span data-stu-id="68f41-201">Pack runs too often -- dotnet pack fails with There is a circular dependency in the target dependency graph involving target "Pack"  - [#4381](https://github.com/NuGet/Home/issues/4381)</span></span>

- <span data-ttu-id="68f41-202">パックの実行頻度が高すぎる -- NuGet パッケージの生成にすべての構成が含まれていない - [#4380](https://github.com/NuGet/Home/issues/4380)</span><span class="sxs-lookup"><span data-stu-id="68f41-202">Pack runs too often -- Generate NuGet package doesn't include all the configurations  - [#4380](https://github.com/NuGet/Home/issues/4380)</span></span>

- <span data-ttu-id="68f41-203">C++ プロジェクトで packageref を使用して NuGet を追加するときに NullReferenceException が発生する - [#4378](https://github.com/NuGet/Home/issues/4378)</span><span class="sxs-lookup"><span data-stu-id="68f41-203">NullReferenceException adding  nuget with packageref in  C++  project - [#4378](https://github.com/NuGet/Home/issues/4378)</span></span>

- <span data-ttu-id="68f41-204">アクセシビリティ: ナレーターで、パッケージをインストールするプロジェクトを選択するためのチェックボックスが読み上げられない - [#4366](https://github.com/NuGet/Home/issues/4366)</span><span class="sxs-lookup"><span data-stu-id="68f41-204">Accessibility : Narrator does not narrate the checkbox to select the projects to install the package to - [#4366](https://github.com/NuGet/Home/issues/4366)</span></span>

- <span data-ttu-id="68f41-205">NuGet VS17 がときどき VSO/VSTS フィードへの接続に失敗する - VS バグ 365798 - [#4365](https://github.com/NuGet/Home/issues/4365)</span><span class="sxs-lookup"><span data-stu-id="68f41-205">NuGet VS17 sporadically fails connecting to VSO/VSTS feeds - VS Bug 365798 - [#4365](https://github.com/NuGet/Home/issues/4365)</span></span>

- <span data-ttu-id="68f41-206">PackagePath が path を "contentFiles" として指定した場合、contentFiles は不適切な場所に出力される - [#4348](https://github.com/NuGet/Home/issues/4348)</span><span class="sxs-lookup"><span data-stu-id="68f41-206">contentFiles get output to wrong location if PackagePath specifies path as "contentFiles" - [#4348](https://github.com/NuGet/Home/issues/4348)</span></span>

- <span data-ttu-id="68f41-207">パック ターゲットで、PackageVersion プロパティに VersionSuffix が付加される - [#4324](https://github.com/NuGet/Home/issues/4324)</span><span class="sxs-lookup"><span data-stu-id="68f41-207">Pack target appends PackageVersion property with VersionSuffix - [#4324](https://github.com/NuGet/Home/issues/4324)</span></span>

- <span data-ttu-id="68f41-208">パッケージ パスを指定しても dotnet pack で機能しない - [#4321](https://github.com/NuGet/Home/issues/4321)</span><span class="sxs-lookup"><span data-stu-id="68f41-208">Specifying package path doesn't work with dotnet pack - [#4321](https://github.com/NuGet/Home/issues/4321)</span></span>

- <span data-ttu-id="68f41-209">NuGet から復元中に重複するインポートに関する警告が出力される - [#4304](https://github.com/NuGet/Home/issues/4304)</span><span class="sxs-lookup"><span data-stu-id="68f41-209">NuGet outputs a bunch of warnings about duplicate imports during restore - [#4304](https://github.com/NuGet/Home/issues/4304)</span></span>

- <span data-ttu-id="68f41-210">暗い色のテーマの場合、[NuGet パッケージ マネージャーの形式の選択] ダイアログが適切に表示されない - [#4300](https://github.com/NuGet/Home/issues/4300)</span><span class="sxs-lookup"><span data-stu-id="68f41-210">Choose "NuGet Package Manager Format" dialog looks bad under dark theme - [#4300](https://github.com/NuGet/Home/issues/4300)</span></span>

- <span data-ttu-id="68f41-211">ビルドの復元時に VS がクラッシュする - [#4298](https://github.com/NuGet/Home/issues/4298)</span><span class="sxs-lookup"><span data-stu-id="68f41-211">VS crash on build restore - [#4298](https://github.com/NuGet/Home/issues/4298)</span></span>

- <span data-ttu-id="68f41-212">ターゲット フレームワークに TFM を追加して保存しビルドすると、Visual Studio はデッドロックします。</span><span class="sxs-lookup"><span data-stu-id="68f41-212">Visual Studio deadlocks if you add TFM in targetframeworks, save, then build.</span></span> <span data-ttu-id="68f41-213">時間の 10% - [#4295](https://github.com/NuGet/Home/issues/4295)</span><span class="sxs-lookup"><span data-stu-id="68f41-213">10% of time - [#4295](https://github.com/NuGet/Home/issues/4295)</span></span>

- <span data-ttu-id="68f41-214">プロジェクトのパック化に成功しても、NuGet パックから成功メッセージが出力されない - [#4294](https://github.com/NuGet/Home/issues/4294)</span><span class="sxs-lookup"><span data-stu-id="68f41-214">nuget pack does not output success message on packing a project successfully - [#4294](https://github.com/NuGet/Home/issues/4294)</span></span>

- <span data-ttu-id="68f41-215">System.IO.Compression 4.1 が見つからないため、PackTask が失敗する - [#4290](https://github.com/NuGet/Home/issues/4290)</span><span class="sxs-lookup"><span data-stu-id="68f41-215">PackTask fails due to System.IO.Compression 4.1 not being found - [#4290](https://github.com/NuGet/Home/issues/4290)</span></span>

- <span data-ttu-id="68f41-216">パックの実行頻度が高すぎる - PackTask がファイル アクセスの競合で頻繁に失敗する - [#4289](https://github.com/NuGet/Home/issues/4289)</span><span class="sxs-lookup"><span data-stu-id="68f41-216">Pack runs too often -- PackTask frequently fails with file access conflict - [#4289](https://github.com/NuGet/Home/issues/4289)</span></span>

- <span data-ttu-id="68f41-217">NuGet で、バックグラウンドの復元中に出力ウィンドウが開く - [#4274](https://github.com/NuGet/Home/issues/4274)</span><span class="sxs-lookup"><span data-stu-id="68f41-217">NuGet opens the output window during background restore - [#4274](https://github.com/NuGet/Home/issues/4274)</span></span>

- <span data-ttu-id="68f41-218">ServiceProvider を危険な (ハングを引き起こす可能性がある) コーディング パターンとして削除する - [#4268 ](https://github.com/NuGet/Home/issues/4268)</span><span class="sxs-lookup"><span data-stu-id="68f41-218">Eliminate ServiceProvider as dangerous coding pattern (which can cause hangs) - [#4268](https://github.com/NuGet/Home/issues/4268)</span></span>

- <span data-ttu-id="68f41-219">パフォーマンス/UI ハング - DownloadTimeoutStream の読み取りの改善 - [#4266](https://github.com/NuGet/Home/issues/4266)</span><span class="sxs-lookup"><span data-stu-id="68f41-219">Perf/UIHang - Improve DownloadTimeoutStream reads - [#4266](https://github.com/NuGet/Home/issues/4266)</span></span>

- <span data-ttu-id="68f41-220">NuGet の復元が完了する前にプロジェクトを閉じると、Visual Studio がデッドロックする - [#4257](https://github.com/NuGet/Home/issues/4257)</span><span class="sxs-lookup"><span data-stu-id="68f41-220">Visual Studio deadlocks if you attempt to close a project before NuGet restore has finished - [#4257](https://github.com/NuGet/Home/issues/4257)</span></span>

- <span data-ttu-id="68f41-221">PackTask とパッキングに関する問題 `.nuspec` - [#4250](https://github.com/NuGet/Home/issues/4250)</span><span class="sxs-lookup"><span data-stu-id="68f41-221">Issues with PackTask and packing `.nuspec` - [#4250](https://github.com/NuGet/Home/issues/4250)</span></span>

- <span data-ttu-id="68f41-222">[vsfeedback] 新しいプロジェクトで NuGet パッケージを解決できない (Visual Studio を再起動する必要がある) - [#4217](https://github.com/NuGet/Home/issues/4217)</span><span class="sxs-lookup"><span data-stu-id="68f41-222">[vsfeedback] Cannot resolve nuget packages on new project (needs to restart visual studio) - [#4217](https://github.com/NuGet/Home/issues/4217)</span></span>

- <span data-ttu-id="68f41-223">[vsfeedback] 使用可能なパッケージ バージョンが表示される [バージョン] ドロップ ダウンが、選択した NuGet パッケージと同期状態を保つことが困難 - [#4198](https://github.com/NuGet/Home/issues/4198)</span><span class="sxs-lookup"><span data-stu-id="68f41-223">[vsfeedback] The "Version" drop down that shows available package versions, struggles to stay in-sync with the selected nuGet package...  - [#4198](https://github.com/NuGet/Home/issues/4198)</span></span>

- <span data-ttu-id="68f41-224">Nuget.Client は、デッドロックを防ぐために CPS と対話するときに、CPS JoinableTaskFactory を使用する必要がある - [#4185](https://github.com/NuGet/Home/issues/4185)</span><span class="sxs-lookup"><span data-stu-id="68f41-224">Nuget.Client should use CPS JoinableTaskFactory when interacting with CPS to prevent deadlocks - [#4185](https://github.com/NuGet/Home/issues/4185)</span></span>

- <span data-ttu-id="68f41-225">NuGet 3.5.0 がパッケージの `.targets` をアンパックしない - [#4171](https://github.com/NuGet/Home/issues/4171)</span><span class="sxs-lookup"><span data-stu-id="68f41-225">NuGet 3.5.0 not unpacking `.targets` from package - [#4171](https://github.com/NuGet/Home/issues/4171)</span></span>

- <span data-ttu-id="68f41-226">`.csproj` で dotnet pack がタイトルをサポートしていない  - [#4150](https://github.com/NuGet/Home/issues/4150)</span><span class="sxs-lookup"><span data-stu-id="68f41-226">dotnet pack does not support title in `.csproj` - [#4150](https://github.com/NuGet/Home/issues/4150)</span></span>

- <span data-ttu-id="68f41-227">VS2017 RC で Install-Package の結果、エラー ダイアログが表示される - [#4127](https://github.com/NuGet/Home/issues/4127)</span><span class="sxs-lookup"><span data-stu-id="68f41-227">Install-Package results in error dialog in VS2017 RC - [#4127](https://github.com/NuGet/Home/issues/4127)</span></span>

- <span data-ttu-id="68f41-228">UI が候補から CPS 更新プログラムを取得しないため、.NET Core プロジェクトのパッケージの更新が機能しません。</span><span class="sxs-lookup"><span data-stu-id="68f41-228">Updating a package for .net core project appears to not work, as the UI doesn't get the CPS update from the nominate.</span></span><span data-ttu-id="68f41-229"> - [#4035](https://github.com/NuGet/Home/issues/4035)</span><span class="sxs-lookup"><span data-stu-id="68f41-229"> - [#4035](https://github.com/NuGet/Home/issues/4035)</span></span>

- <span data-ttu-id="68f41-230">未解決の参照警告を改善する - [#3955 ](https://github.com/NuGet/Home/issues/3955)</span><span class="sxs-lookup"><span data-stu-id="68f41-230">Improve unresolved reference warning - [#3955](https://github.com/NuGet/Home/issues/3955)</span></span>

- <span data-ttu-id="68f41-231">dotnet pack - ProjectReference でバージョン情報が失われる - [#3953](https://github.com/NuGet/Home/issues/3953)</span><span class="sxs-lookup"><span data-stu-id="68f41-231">dotnet pack - ProjectReference loses version information - [#3953](https://github.com/NuGet/Home/issues/3953)</span></span>

- <span data-ttu-id="68f41-232">UWP アプリ作成プロジェクトを作成し、総経過時間の回帰をリビルドする - [#3873](https://github.com/NuGet/Home/issues/3873)</span><span class="sxs-lookup"><span data-stu-id="68f41-232">Create UWP app create project & rebuild total elapsed time regressions - [#3873](https://github.com/NuGet/Home/issues/3873)</span></span>

- <span data-ttu-id="68f41-233">復元中にエラーが発生した後でも、成功の復元メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68f41-233">Successful restore message is displayed even after error during restore.</span></span><span data-ttu-id="68f41-234"> - [#3799](https://github.com/NuGet/Home/issues/3799)</span><span class="sxs-lookup"><span data-stu-id="68f41-234"> - [#3799](https://github.com/NuGet/Home/issues/3799)</span></span>

- <span data-ttu-id="68f41-235">Nuget.CommandLine 3.4.4 を Nuget.org に再発行する - [#2931](https://github.com/NuGet/Home/issues/2931)</span><span class="sxs-lookup"><span data-stu-id="68f41-235">re-Publish Nuget.CommandLine 3.4.4 to Nuget.org - [#2931](https://github.com/NuGet/Home/issues/2931)</span></span>

- <span data-ttu-id="68f41-236">移行時に、プロジェクトが `project.json` から `.csproj` に変更される --- 復元に失敗する - [#4297](https://github.com/NuGet/Home/issues/4297)</span><span class="sxs-lookup"><span data-stu-id="68f41-236">On Migrate, projects change from `project.json` to `.csproj` --- restore fails - [#4297](https://github.com/NuGet/Home/issues/4297)</span></span>

- <span data-ttu-id="68f41-237">新しく作成された xunit テスト プロジェクトで復元に失敗する - [#4296](https://github.com/NuGet/Home/issues/4296)</span><span class="sxs-lookup"><span data-stu-id="68f41-237">Restore failing on newly created xunit Test project  - [#4296](https://github.com/NuGet/Home/issues/4296)</span></span>

- <span data-ttu-id="68f41-238">コア プロジェクトがハングし、UI が開いたままロックされることがある - [#4269](https://github.com/NuGet/Home/issues/4269)</span><span class="sxs-lookup"><span data-stu-id="68f41-238">Core projects can hang, lock up UI on open - [#4269](https://github.com/NuGet/Home/issues/4269)</span></span>

- <span data-ttu-id="68f41-239">ビルド タスクのターゲット ファイルを修正する - [#4267](https://github.com/NuGet/Home/issues/4267)</span><span class="sxs-lookup"><span data-stu-id="68f41-239">fix targets file for build tasks - [#4267](https://github.com/NuGet/Home/issues/4267)</span></span>

- <span data-ttu-id="68f41-240">参照先プロジェクトをアンロードするビルド ソリューションの後にエラー リストにエラーが発生する - [#4208](https://github.com/NuGet/Home/issues/4208)</span><span class="sxs-lookup"><span data-stu-id="68f41-240">Error list has error after build solution which unload the referenced project - [#4208](https://github.com/NuGet/Home/issues/4208)</span></span>

- <span data-ttu-id="68f41-241">MSB4057: ターゲット "_GenerateRestoreGraphProjectEntry" がプロジェクトに存在しません。</span><span class="sxs-lookup"><span data-stu-id="68f41-241">MSB4057: The target "_GenerateRestoreGraphProjectEntry" does not exist in the project.</span></span><span data-ttu-id="68f41-242"> - [#4194](https://github.com/NuGet/Home/issues/4194)</span><span class="sxs-lookup"><span data-stu-id="68f41-242"> - [#4194](https://github.com/NuGet/Home/issues/4194)</span></span>

- <span data-ttu-id="68f41-243">vsfeedback: すべてのプロジェクトを選択するとソリューションがクラッシュする NuGet マネージャー UI - [#4191](https://github.com/NuGet/Home/issues/4191)</span><span class="sxs-lookup"><span data-stu-id="68f41-243">vsfeedback: nuget manager ui for solution crashes when you select all projects - [#4191](https://github.com/NuGet/Home/issues/4191)</span></span>

- <span data-ttu-id="68f41-244">nuget.exe の msbuildpath の末尾にスラッシュがあると、msbuildpath が失敗する - [#4180](https://github.com/NuGet/Home/issues/4180)</span><span class="sxs-lookup"><span data-stu-id="68f41-244">nuget.exe msbuildpath fails when there is a trailing slash - [#4180](https://github.com/NuGet/Home/issues/4180)</span></span>

- <span data-ttu-id="68f41-245">vsfeedback: NuGet の復元で、LinqToTwitter プロジェクトに関するプロジェクト参照の警告を受け取る - [#4156](https://github.com/NuGet/Home/issues/4156)</span><span class="sxs-lookup"><span data-stu-id="68f41-245">vsfeedback: NuGet restore give several project reference warnings for LinqToTwitter project - [#4156](https://github.com/NuGet/Home/issues/4156)</span></span>

- <span data-ttu-id="68f41-246">`.csproj` のパックに minClientVersion 属性が含まれていない - [#4135](https://github.com/NuGet/Home/issues/4135)</span><span class="sxs-lookup"><span data-stu-id="68f41-246">Pack from `.csproj` does not include the minClientVersion attribute  - [#4135](https://github.com/NuGet/Home/issues/4135)</span></span>

- <span data-ttu-id="68f41-247">VS2017 (d15rel 26014.00) で NuGet.Build.Tasks.Pack.dll は遅延署名された状態でリリースされた - [#4122](https://github.com/NuGet/Home/issues/4122)</span><span class="sxs-lookup"><span data-stu-id="68f41-247">NuGet.Build.Tasks.Pack.dll shipped delay signed in VS2017 (d15rel 26014.00) - [#4122](https://github.com/NuGet/Home/issues/4122)</span></span>

- <span data-ttu-id="68f41-248">VSFeedback: CMake 3.7.1 で生成された VS 2015 プロジェクトの復元に失敗する - [#4114](https://github.com/NuGet/Home/issues/4114)</span><span class="sxs-lookup"><span data-stu-id="68f41-248">VSFeedback: Restore fails for a VS 2015 project generated with CMake 3.7.1 - [#4114](https://github.com/NuGet/Home/issues/4114)</span></span>

- <span data-ttu-id="68f41-249">VSFeedback: 復元エラーにより、ビルドで発生する詳細なエラー メッセージがあいまいになることがある - [#4113](https://github.com/NuGet/Home/issues/4113)</span><span class="sxs-lookup"><span data-stu-id="68f41-249">VSFeedback: Restore errors can obscure more complete error messages that build could give - [#4113](https://github.com/NuGet/Home/issues/4113)</span></span>

- <span data-ttu-id="68f41-250">[VSFeedback] Web サイト プロジェクトの NuGet パッケージを復元するときにエラー "値を null にすることはできません" が発生する</span><span class="sxs-lookup"><span data-stu-id="68f41-250">[VSFeedback] Error occurred while restoring NuGet packages for website project: Value cannot be null.</span></span><span data-ttu-id="68f41-251"> - [#4092](https://github.com/NuGet/Home/issues/4092)</span><span class="sxs-lookup"><span data-stu-id="68f41-251"> - [#4092](https://github.com/NuGet/Home/issues/4092)</span></span>

- <span data-ttu-id="68f41-252">移行時に NuGet.PackageManagement.VisualStudio.SolutionRestoreWorker で "オブジェクト参照の例外" がスローされる - [#4067](https://github.com/NuGet/Home/issues/4067)</span><span class="sxs-lookup"><span data-stu-id="68f41-252">Migration Throws "Object reference Exception" in NuGet.PackageManagement.VisualStudio.SolutionRestoreWorker - [#4067](https://github.com/NuGet/Home/issues/4067)</span></span>

- <span data-ttu-id="68f41-253">dotnet pack は、パッケージがビルドされたバージョンでツールをパックする必要がある - [#4063](https://github.com/NuGet/Home/issues/4063)</span><span class="sxs-lookup"><span data-stu-id="68f41-253">dotnet pack should pack tools with the versions that the package was built against - [#4063](https://github.com/NuGet/Home/issues/4063)</span></span>

- <span data-ttu-id="68f41-254">新しいバックグラウンド復元で、復元に数秒かかるときに、ステータス バーにミリ秒が書き込まれる - [#4036](https://github.com/NuGet/Home/issues/4036)</span><span class="sxs-lookup"><span data-stu-id="68f41-254">New background restore writes milliseconds to status bar when it takes seconds to restore - [#4036](https://github.com/NuGet/Home/issues/4036)</span></span>

- <span data-ttu-id="68f41-255">すべてのプロジェクト参照を解決できなかった場合の誤植 - [#4018](https://github.com/NuGet/Home/issues/4018)</span><span class="sxs-lookup"><span data-stu-id="68f41-255">Typo on failed to resolve all project references - [#4018](https://github.com/NuGet/Home/issues/4018)</span></span>

- <span data-ttu-id="68f41-256">パッケージ参照シナリオで PCM ワークフローを有効にする - [#4016](https://github.com/NuGet/Home/issues/4016)</span><span class="sxs-lookup"><span data-stu-id="68f41-256">Enable PCM workflows in package reference scenarios - [#4016](https://github.com/NuGet/Home/issues/4016)</span></span>

- <span data-ttu-id="68f41-257">パッケージ マネージャーの UI でインストールされたパッケージが見つからない - [#4015](https://github.com/NuGet/Home/issues/4015)</span><span class="sxs-lookup"><span data-stu-id="68f41-257">Can not find installed packages in package manager UI - [#4015](https://github.com/NuGet/Home/issues/4015)</span></span>

- <span data-ttu-id="68f41-258">PackagePath が空の場合、dotnet pack が失敗する - [#3993](https://github.com/NuGet/Home/issues/3993)</span><span class="sxs-lookup"><span data-stu-id="68f41-258">dotnet pack fails when PackagePath is empty - [#3993](https://github.com/NuGet/Home/issues/3993)</span></span>

- <span data-ttu-id="68f41-259">マルチ ユーザー シナリオで復元タスクが失敗する - [#3897](https://github.com/NuGet/Home/issues/3897)</span><span class="sxs-lookup"><span data-stu-id="68f41-259">Restore task fails in an multi user scenario - [#3897](https://github.com/NuGet/Home/issues/3897)</span></span>

- <span data-ttu-id="68f41-260">NuGet パック タスクを使用してパックするときに、コンテンツ タイプを変更できない - [#3895](https://github.com/NuGet/Home/issues/3895)</span><span class="sxs-lookup"><span data-stu-id="68f41-260">Cannot change Content type when packing using NuGet Pack Task - [#3895](https://github.com/NuGet/Home/issues/3895)</span></span>

- <span data-ttu-id="68f41-261">MsBuild /t:pack について ContentFiles の既定のコピーが正しくない - [#3894](https://github.com/NuGet/Home/issues/3894)</span><span class="sxs-lookup"><span data-stu-id="68f41-261">Default Copy of ContentFiles are incorrect for MsBuild /t:pack - [#3894](https://github.com/NuGet/Home/issues/3894)</span></span>

- <span data-ttu-id="68f41-262">インストール パッケージの復元で、パッケージの復元メッセージのログが二重に記録される - [#3785](https://github.com/NuGet/Home/issues/3785)</span><span class="sxs-lookup"><span data-stu-id="68f41-262">Install package restore double logs the restoring packages message - [#3785](https://github.com/NuGet/Home/issues/3785)</span></span>

- <span data-ttu-id="68f41-263">Guardrails の削除 - "runtimes" セクションの復元を現在のプロジェクトにのみ適用するようにする - [#3768](https://github.com/NuGet/Home/issues/3768)</span><span class="sxs-lookup"><span data-stu-id="68f41-263">Remove Guardrails - Restore of "runtimes" section should only apply to the current project - [#3768](https://github.com/NuGet/Home/issues/3768)</span></span>

- <span data-ttu-id="68f41-264">パック タスクで、コンテンツ ファイルが 'content/' と 'contentFiles/' の両方に配置される - [#3718](https://github.com/NuGet/Home/issues/3718)</span><span class="sxs-lookup"><span data-stu-id="68f41-264">Pack task puts content files in both 'content/' and 'contentFiles/' - [#3718](https://github.com/NuGet/Home/issues/3718)</span></span>

- <span data-ttu-id="68f41-265">dotnet pack3 で、余計なタグ分割が行われる - [#3701](https://github.com/NuGet/Home/issues/3701)</span><span class="sxs-lookup"><span data-stu-id="68f41-265">dotnet pack3 does extra tag splitting - [#3701](https://github.com/NuGet/Home/issues/3701)</span></span>

- <span data-ttu-id="68f41-266">dotnet pack: パッケージ参照があるプロジェクトのパックで重複インポートの警告が表示される - [#3665](https://github.com/NuGet/Home/issues/3665)</span><span class="sxs-lookup"><span data-stu-id="68f41-266">dotnet pack: packing projects with package references results in duplicate import warning - [#3665](https://github.com/NuGet/Home/issues/3665)</span></span>

- <span data-ttu-id="68f41-267">VS の復元ログ記録が表示されないことがある - [#3633](https://github.com/NuGet/Home/issues/3633)</span><span class="sxs-lookup"><span data-stu-id="68f41-267">Restore logging in VS doesn't always show - [#3633](https://github.com/NuGet/Home/issues/3633)</span></span>

- <span data-ttu-id="68f41-268">nuget locals のヘルプ テキストで、まだパッケージ キャッシュについて言及されている - [#3592](https://github.com/NuGet/Home/issues/3592)</span><span class="sxs-lookup"><span data-stu-id="68f41-268">nuget locals help text still mentioned packages cache - [#3592](https://github.com/NuGet/Home/issues/3592)</span></span>

- <span data-ttu-id="68f41-269">Restore3 は PackageReferences を TargetFrameworks と結合する。</span><span class="sxs-lookup"><span data-stu-id="68f41-269">Restore3 couples PackageReferences with TargetFrameworks.</span></span><span data-ttu-id="68f41-270"> - [#3504](https://github.com/NuGet/Home/issues/3504)</span><span class="sxs-lookup"><span data-stu-id="68f41-270"> - [#3504](https://github.com/NuGet/Home/issues/3504)</span></span>

- <span data-ttu-id="68f41-271">VS "15" Preview 4 dev コマンド プロンプトで、Nuget によって予期しないバージョンの MSBuild が選択される</span><span class="sxs-lookup"><span data-stu-id="68f41-271">Nuget picks unexpected version of MSBuild in VS "15" Preview 4 dev.</span></span> <span data-ttu-id="68f41-272">- [#3408](https://github.com/NuGet/Home/issues/3408)</span><span class="sxs-lookup"><span data-stu-id="68f41-272">command prompt - [#3408](https://github.com/NuGet/Home/issues/3408)</span></span>

- <span data-ttu-id="68f41-273">失敗した復元でターゲット/プロパティ ファイルを書き出す - [#3399](https://github.com/NuGet/Home/issues/3399)</span><span class="sxs-lookup"><span data-stu-id="68f41-273">Write out targets/props files on failed restore - [#3399](https://github.com/NuGet/Home/issues/3399)</span></span>

- <span data-ttu-id="68f41-274">VS 15 コマンド プロンプトで実行するときに、復元中の NuGet が、MSBuild と同じ互換 shim を使用しない - [#3387](https://github.com/NuGet/Home/issues/3387)</span><span class="sxs-lookup"><span data-stu-id="68f41-274">NuGet during restore doesn't respect the same compat shims as MSBuild when running in VS 15 command prompt - [#3387](https://github.com/NuGet/Home/issues/3387)</span></span>

- <span data-ttu-id="68f41-275">VS15 の場合に PackFromProjectWithDevelopmentDependencySet を再び有効にする - [#3272](https://github.com/NuGet/Home/issues/3272)</span><span class="sxs-lookup"><span data-stu-id="68f41-275">Re-enable PackFromProjectWithDevelopmentDependencySet for VS15 - [#3272](https://github.com/NuGet/Home/issues/3272)</span></span>

- <span data-ttu-id="68f41-276">Blend と NuGet の問題 - [#4043](https://github.com/NuGet/Home/issues/4043)</span><span class="sxs-lookup"><span data-stu-id="68f41-276">Blend problems with NuGet - [#4043](https://github.com/NuGet/Home/issues/4043)</span></span>

- <span data-ttu-id="68f41-277">4.0.0.2067 を CLI と SDK リポジトリに統合して RC2 と共にリリースする - [#4029](https://github.com/NuGet/Home/issues/4029)</span><span class="sxs-lookup"><span data-stu-id="68f41-277">Integrate 4.0.0.2067 into CLI and SDK repos to ship with RC2 - [#4029](https://github.com/NuGet/Home/issues/4029)</span></span>

- <span data-ttu-id="68f41-278">新しいコア コンソール アプリケーションを作成し、ソリューションを終了し、ソリューションを開き、ソリューションを閉じるときに VS がハングする - [#4008](https://github.com/NuGet/Home/issues/4008)</span><span class="sxs-lookup"><span data-stu-id="68f41-278">VS Hangs when you Create new Core Console App, Close Solution, Open Solution and Close Solution  - [#4008](https://github.com/NuGet/Home/issues/4008)</span></span>

- <span data-ttu-id="68f41-279">d15prerel.25916.01 に対してプロジェクトを開こうとするとハングする - [#3982](https://github.com/NuGet/Home/issues/3982)</span><span class="sxs-lookup"><span data-stu-id="68f41-279">Hitting hang opening project against d15prerel.25916.01 - [#3982](https://github.com/NuGet/Home/issues/3982)</span></span>

- <span data-ttu-id="68f41-280">dotnet/nuget.exe のローカル ドキュメント/ヘルプ メッセージの修正 - [#3919](https://github.com/NuGet/Home/issues/3919)</span><span class="sxs-lookup"><span data-stu-id="68f41-280">Fix dotnet/nuget.exe locals doc/help message - [#3919](https://github.com/NuGet/Home/issues/3919)</span></span>

- <span data-ttu-id="68f41-281">末尾または先頭の空白に関する問題の PackTask の検査 - [#3906](https://github.com/NuGet/Home/issues/3906)</span><span class="sxs-lookup"><span data-stu-id="68f41-281">Inspect PackTask for issues with trailing or leading whitespace - [#3906](https://github.com/NuGet/Home/issues/3906)</span></span>

- <span data-ttu-id="68f41-282">dotnet pack が bin ではなく obj からパックを実行する - [#3880](https://github.com/NuGet/Home/issues/3880)</span><span class="sxs-lookup"><span data-stu-id="68f41-282">dotnet pack is packing from obj not bin - [#3880](https://github.com/NuGet/Home/issues/3880)</span></span>

- <span data-ttu-id="68f41-283">dotnet pack が ProjectReference のバージョンを常に 1.0.0 に設定しているように見える - [#3874](https://github.com/NuGet/Home/issues/3874)</span><span class="sxs-lookup"><span data-stu-id="68f41-283">dotnet pack always seems to set ProjectReference version to 1.0.0 - [#3874](https://github.com/NuGet/Home/issues/3874)</span></span>

- <span data-ttu-id="68f41-284">dotnet pack がプロジェクト参照と <TargetFramework> で失敗する  - [#3865](https://github.com/NuGet/Home/issues/3865)</span><span class="sxs-lookup"><span data-stu-id="68f41-284">dotnet pack fails with project references and <TargetFramework> - [#3865](https://github.com/NuGet/Home/issues/3865)</span></span>

- <span data-ttu-id="68f41-285">ProjectSystemCache.TryGetProjectNameByShortName の LockRecursionException - [#3861](https://github.com/NuGet/Home/issues/3861)</span><span class="sxs-lookup"><span data-stu-id="68f41-285">LockRecursionException in ProjectSystemCache.TryGetProjectNameByShortName - [#3861](https://github.com/NuGet/Home/issues/3861)</span></span>

- <span data-ttu-id="68f41-286">MSBuild プロパティから空白を削除する - [#3819](https://github.com/NuGet/Home/issues/3819)</span><span class="sxs-lookup"><span data-stu-id="68f41-286">Trim whitespace from MSBuild properties - [#3819](https://github.com/NuGet/Home/issues/3819)</span></span>

- <span data-ttu-id="68f41-287">プロジェクトの読み込み時に発生する 2 つのプロジェクト イベントを統合する - [#3759](https://github.com/NuGet/Home/issues/3759)</span><span class="sxs-lookup"><span data-stu-id="68f41-287">Consolidate the two project events raised on project load - [#3759](https://github.com/NuGet/Home/issues/3759)</span></span>

- <span data-ttu-id="68f41-288">`project.assets.json` ファイルの P2P ライブラリのバージョンが正しくない - [#3748](https://github.com/NuGet/Home/issues/3748)</span><span class="sxs-lookup"><span data-stu-id="68f41-288">P2P libraries in `project.assets.json` file have incorrect Version - [#3748](https://github.com/NuGet/Home/issues/3748)</span></span>

- <span data-ttu-id="68f41-289">応答しないフィードと使用できないパッケージによる復元のクラッシュ - [#3672](https://github.com/NuGet/Home/issues/3672)</span><span class="sxs-lookup"><span data-stu-id="68f41-289">Restore crash due to unresponsive feed and unavailable package - [#3672](https://github.com/NuGet/Home/issues/3672)</span></span>

- <span data-ttu-id="68f41-290">大量の MSBuild エラー出力で、nuget.exe がハングする可能性がある - [#3572](https://github.com/NuGet/Home/issues/3572)</span><span class="sxs-lookup"><span data-stu-id="68f41-290">nuget.exe could hang on a large amount of MSBuild error output - [#3572](https://github.com/NuGet/Home/issues/3572)</span></span>

- <span data-ttu-id="68f41-291">Blend のビルド時の復元が、初回は失敗し 2 回目に成功する (VS シナリオは固定) - [#2121](https://github.com/NuGet/Home/issues/2121)</span><span class="sxs-lookup"><span data-stu-id="68f41-291">Restore-on-build for Blend fails first time, succeeds second time (VS scenario fixed) - [#2121](https://github.com/NuGet/Home/issues/2121)</span></span>

### <a name="dcrs"></a><span data-ttu-id="68f41-292">DCR</span><span class="sxs-lookup"><span data-stu-id="68f41-292">DCRs</span></span>

- <span data-ttu-id="68f41-293">v2 vsix から v3 vsix への vsix の移行 - [#4196](https://github.com/NuGet/Home/issues/4196)</span><span class="sxs-lookup"><span data-stu-id="68f41-293">migrate vsix from v2 vsix to v3 vsix - [#4196](https://github.com/NuGet/Home/issues/4196)</span></span>

- <span data-ttu-id="68f41-294">MSBuild でロック ファイルへのパスを取得するメカニズムが NuGet に必要 - [#3351](https://github.com/NuGet/Home/issues/3351)</span><span class="sxs-lookup"><span data-stu-id="68f41-294">NuGet should have a mechanism for getting the path to the lock file in MSBuild - [#3351](https://github.com/NuGet/Home/issues/3351)</span></span>

- <span data-ttu-id="68f41-295">ビルド アセットを TFM 互換性チェックとアセット ファイルに追加する - [#3296](https://github.com/NuGet/Home/issues/3296)</span><span class="sxs-lookup"><span data-stu-id="68f41-295">Add build assets to the TFM compatibility check and assets file - [#3296](https://github.com/NuGet/Home/issues/3296)</span></span>

- <span data-ttu-id="68f41-296">パッケージ関連の機能を有効にするためにパック ターゲットに新しい ProjectCapability "パック" を定義する - [#4146](https://github.com/NuGet/Home/issues/4146)</span><span class="sxs-lookup"><span data-stu-id="68f41-296">Define a new ProjectCapability "Pack" in Pack targets for enabling Package related capabilities - [#4146](https://github.com/NuGet/Home/issues/4146)</span></span>

- <span data-ttu-id="68f41-297">"GeneratePackageOnBuild" MSBuild プロパティに基づく条件で、ビルド後のターゲットとしてパックを実行する - [#4145](https://github.com/NuGet/Home/issues/4145)</span><span class="sxs-lookup"><span data-stu-id="68f41-297">Run Pack as a post build target conditioned on "GeneratePackageOnBuild" MSBuild property - [#4145](https://github.com/NuGet/Home/issues/4145)</span></span>

- <span data-ttu-id="68f41-298">NuGet プロパティ RestoreProjectStyle を使用して特定の NuGet プロジェクトを作成する - [#4134](https://github.com/NuGet/Home/issues/4134)</span><span class="sxs-lookup"><span data-stu-id="68f41-298">Use NuGet property RestoreProjectStyle to create specific NuGet project - [#4134](https://github.com/NuGet/Home/issues/4134)</span></span>

- <span data-ttu-id="68f41-299">推移的プロジェクト参照の変更に復元を適応させる - [#4076](https://github.com/NuGet/Home/issues/4076)</span><span class="sxs-lookup"><span data-stu-id="68f41-299">Adapt Restore for Transitive Project References change - [#4076](https://github.com/NuGet/Home/issues/4076)</span></span>

- <span data-ttu-id="68f41-300">非 UWP プロジェクトのターゲット ファイルに NuGet プロパティを追加する - [#4030](https://github.com/NuGet/Home/issues/4030)</span><span class="sxs-lookup"><span data-stu-id="68f41-300">Add NuGet properties in target file for non-UWP projects - [#4030](https://github.com/NuGet/Home/issues/4030)</span></span>

- <span data-ttu-id="68f41-301">UWP TargetPlatformVersion のサポート - [#3923](https://github.com/NuGet/Home/issues/3923)</span><span class="sxs-lookup"><span data-stu-id="68f41-301">UWP TargetPlatformVersion support - [#3923](https://github.com/NuGet/Home/issues/3923)</span></span>

- <span data-ttu-id="68f41-302">プロジェクト参照メタデータを NuGet プロジェクト システムに伝える - [#3922](https://github.com/NuGet/Home/issues/3922)</span><span class="sxs-lookup"><span data-stu-id="68f41-302">Communicate project reference metadata to NuGet project system - [#3922](https://github.com/NuGet/Home/issues/3922)</span></span>

- <span data-ttu-id="68f41-303">パッケージ モードの UI を追加する - [#3921](https://github.com/NuGet/Home/issues/3921)</span><span class="sxs-lookup"><span data-stu-id="68f41-303">Add UI for packaging mode - [#3921](https://github.com/NuGet/Home/issues/3921)</span></span>

- <span data-ttu-id="68f41-304">従来の `.csproj` では、NugetTargetMoniker と RuntimeIdentifier を proj/targets に設定する必要がある - [#3854](https://github.com/NuGet/Home/issues/3854)</span><span class="sxs-lookup"><span data-stu-id="68f41-304">Legacy `.csproj` needs NugetTargetMoniker and RuntimeIdentifiers set in proj/targets - [#3854](https://github.com/NuGet/Home/issues/3854)</span></span>

- <span data-ttu-id="68f41-305">自動復元時にインストール パッケージが重複することがある - [#3836](https://github.com/NuGet/Home/issues/3836)</span><span class="sxs-lookup"><span data-stu-id="68f41-305">Install package may overlap with auto-restore - [#3836](https://github.com/NuGet/Home/issues/3836)</span></span>

- <span data-ttu-id="68f41-306">VSPackage が読み込まれない場合にコンテキスト メニュー QueryStatus が生成されない - [#3835](https://github.com/NuGet/Home/issues/3835)</span><span class="sxs-lookup"><span data-stu-id="68f41-306">Context menu QueryStatus doesn't happen when VSPackage is not loaded - [#3835](https://github.com/NuGet/Home/issues/3835)</span></span>

- <span data-ttu-id="68f41-307">ソリューションの復元とビルドの復元でダイアログが表示され続ける - [#3789](https://github.com/NuGet/Home/issues/3789)</span><span class="sxs-lookup"><span data-stu-id="68f41-307">Solution Restore and Build Restore still show dialogs - [#3789](https://github.com/NuGet/Home/issues/3789)</span></span>

- <span data-ttu-id="68f41-308">NuGet.Clients ソリューション ビルドで VSSDK のバージョンを分離する - [#3890](https://github.com/NuGet/Home/issues/3890)</span><span class="sxs-lookup"><span data-stu-id="68f41-308">Isolate VSSDK version in NuGet.Clients solution build - [#3890](https://github.com/NuGet/Home/issues/3890)</span></span>

## <a name="links-to-github-issues-fixed-in-rtm"></a><span data-ttu-id="68f41-309">RTM で修正された GitHub の問題へのリンク</span><span class="sxs-lookup"><span data-stu-id="68f41-309">Links to GitHub issues fixed in RTM</span></span>
[<span data-ttu-id="68f41-310">懸案事項リスト 1</span><span class="sxs-lookup"><span data-stu-id="68f41-310">Issues list 1</span></span>](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%224.0 RTM")  
[<span data-ttu-id="68f41-311">懸案事項リスト 2</span><span class="sxs-lookup"><span data-stu-id="68f41-311">Issues list 2</span></span>](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%224.0 RC4")  
[<span data-ttu-id="68f41-312">懸案事項リスト 3</span><span class="sxs-lookup"><span data-stu-id="68f41-312">Issues list 3</span></span>](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%224.0 RC3")  
[<span data-ttu-id="68f41-313">懸案事項リスト 4</span><span class="sxs-lookup"><span data-stu-id="68f41-313">Issues list 4</span></span>](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%224.0 RC2")  
[<span data-ttu-id="68f41-314">懸案事項リスト 5</span><span class="sxs-lookup"><span data-stu-id="68f41-314">Issues list 5</span></span>](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%224.0 RC")