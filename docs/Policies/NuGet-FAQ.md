---
title: "NuGet に関してよく寄せられる質問 | Microsoft Docs"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 01/11/2018
ms.topic: article
ms.prod: nuget
ms.technology: 
description: "コマンド ラインと Visual Studio での NuGet の使用、および NuGet ギャラリーでの作業に関する一般的な質問と回答。"
keywords: "NuGet に関する Q&A, 質問と回答, 一般的な問題, NuGet のバージョン, パッケージのバージョン"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 3782fe5dcf8df002d99446aa7548a6eacc62211c
ms.sourcegitcommit: 74c21b406302288c158e8ae26057132b12960be8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="nuget-frequently-asked-questions"></a><span data-ttu-id="ef4d0-104">NuGet に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ef4d0-104">NuGet frequently-asked questions</span></span>

<span data-ttu-id="ef4d0-105">**NuGet を実行するために必要なものは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-105">**What is required to run NuGet?**</span></span>

<span data-ttu-id="ef4d0-106">UI とコマンド ライン ツールの両方に関するすべての情報は、[インストール ガイド](../install-nuget-client-tools.md)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-106">All the information around both UI and command-line tools is available in the [Install guide](../install-nuget-client-tools.md).</span></span>

<span data-ttu-id="ef4d0-107">**NuGet で Mono はサポートされますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-107">**Does NuGet support Mono?**</span></span>

<span data-ttu-id="ef4d0-108">コマンド ライン ツール `nuget.exe` は Mono 3.2+ でビルドおよび実行され、Mono でパッケージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-108">The command-line tool, `nuget.exe`, builds and runs under Mono 3.2+ and can create packages in Mono.</span></span>

<span data-ttu-id="ef4d0-109">`nuget.exe` は Windows では完全に動作しますが、Linux と OS X では既知の問題があります。GitHub の [Mono に関する問題](https://github.com/NuGet/Home/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+mono)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-109">Although `nuget.exe` works fully on Windows, there are known issues on Linux and OS X. Refer to [Mono issues](https://github.com/NuGet/Home/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+mono) on GitHub.</span></span>

<span data-ttu-id="ef4d0-110">[グラフィカル クライアント](https://github.com/mrward/monodevelop-nuget-addin)は、MonoDevelop 用のアドインとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-110">A [graphical client](https://github.com/mrward/monodevelop-nuget-addin) is available as an add-in for MonoDevelop.</span></span>

<span data-ttu-id="ef4d0-111">**パッケージの内容と、それが自分のアプリケーションに対して安定したものであり、役立つものであるかどうかはどのように判別すればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-111">**How can I determine what a package contains and whether it's stable and useful for my application?**</span></span>

<span data-ttu-id="ef4d0-112">パッケージについて学習するための主なソースとして、nuget.org (または別のプライベート フィード) のリスト ページがあります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-112">The primary source for learning about a package is its listing page on nuget.org (or another private feed).</span></span> <span data-ttu-id="ef4d0-113">nuget.org の各パッケージ ページには、パッケージ、そのバージョン履歴、使用状況の統計の説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-113">Each package page on nuget.org includes a description of the package, its version history, and usage statistics.</span></span> <span data-ttu-id="ef4d0-114">パッケージ ページの **[情報]** セクションには、プロジェクトの Web サイトへのリンクも含まれています。通常はこのサイトで、パッケージの使用方法について学習する際に役立つ多くの例とその他のドキュメントを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-114">The **Info** section on the package page also contains a link to the project's web site where you typically find many examples and other documentation to help you learn how the package is used.</span></span>

<span data-ttu-id="ef4d0-115">詳細については、「[パッケージの検索と選択](../consume-packages/finding-and-choosing-packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-115">For more information, see [Finding and choosing packages](../consume-packages/finding-and-choosing-packages.md).</span></span>

## <a name="nuget-in-visual-studio"></a><span data-ttu-id="ef4d0-116">Visual Studio の NuGet</span><span class="sxs-lookup"><span data-stu-id="ef4d0-116">NuGet in Visual Studio</span></span>

<span data-ttu-id="ef4d0-117">**別の Visual Studio 製品では NuGet はどのようにサポートされますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-117">**How is NuGet supported in different Visual Studio products?**</span></span>

- <span data-ttu-id="ef4d0-118">Windows の Visual Studio では、[パッケージ マネージャー UI](../tools/package-manager-ui.md) と[パッケージ マネージャー コンソール](../tools/package-manager-console.md)がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-118">Visual Studio on Windows supports the [Package Manager UI](../tools/package-manager-ui.md) and the [Package Manager Console](../tools/package-manager-console.md).</span></span>
- <span data-ttu-id="ef4d0-119">「[プロジェクトに NuGet パッケージを含める](/visualstudio/mac/nuget-walkthrough)」で説明されているように、Visual Studio for Mac には NuGet 機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-119">Visual Studio for Mac has built-in NuGet capabilities as described on [Including a NuGet package in your project](/visualstudio/mac/nuget-walkthrough).</span></span>
- <span data-ttu-id="ef4d0-120">Visual Studio Code (すべてのプラットフォーム) には、直接 NuGet は統合されていません。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-120">Visual Studio Code (all platforms) does not have any direct NuGet integration.</span></span> <span data-ttu-id="ef4d0-121">[NuGet CLI](../tools/nuget-exe-cli-reference.md) または [dotnet CLI](../tools/dotnet-commands.md) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-121">Use the [NuGet CLI](../tools/nuget-exe-cli-reference.md) or the [dotnet CLI](../tools/dotnet-commands.md).</span></span>
- <span data-ttu-id="ef4d0-122">Visual Studio Team Services では、[NuGet パッケージを復元するためのビルド ステップ](/vsts/build-release/tasks/package/nuget)が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-122">Visual Studio Team Services provides [a build step to restore NuGet packages](/vsts/build-release/tasks/package/nuget).</span></span> <span data-ttu-id="ef4d0-123">[Team Services でプライベート NuGet パッケージ フィードをホストする](https://www.visualstudio.com/docs/package/nuget/publish)こともできます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-123">You can also [host private NuGet package feeds on Team Services](https://www.visualstudio.com/docs/package/nuget/publish).</span></span>

<span data-ttu-id="ef4d0-124">**インストールされている NuGet ツールの正確なバージョンはどのように確認すればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-124">**How do I check the exact version of the NuGet tools that are installed?**</span></span>

<span data-ttu-id="ef4d0-125">Visual Studio で、**[ヘルプ]、[Microsoft Visual Studio のバージョン情報]** コマンドを使用して、**[NuGet パッケージ マネージャー]** の横に表示されるバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-125">In Visual Studio, use the **Help > About Microsoft Visual Studio** command and look at the version displayed next to **NuGet Package Manager**.</span></span>

<span data-ttu-id="ef4d0-126">または、パッケージ マネージャー コンソールを起動 (**[ツール]、[NuGet パッケージ マネージャー]、[パッケージ マネージャー コンソール]** の順に選択) し、「`$host`」と入力して、バージョンを含む NuGet に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-126">Alternatively, launch the Package Manager Console (**Tools > NuGet Package Manager > Package Manager Console**) and enter `$host` to see information about NuGet including the version.</span></span>

<span data-ttu-id="ef4d0-127">**NuGet ではどのようなプログラミング言語がサポートされますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-127">**What programming languages are supported by NuGet?**</span></span>

<span data-ttu-id="ef4d0-128">通常、NuGet は .NET 言語に対して動作し、プロジェクトに .NET ライブラリを取り込むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-128">NuGet generally works for .NET languages and is designed to bring .NET libraries into a project.</span></span> <span data-ttu-id="ef4d0-129">また、いくつかのプロジェクトの種類で MSBuild と Visual Studio オートメーションがサポートされるため、程度の差はありますが他のプロジェクトと言語もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-129">Because it also supports MSBuild and Visual Studio automation in some project types, it also supports other projects and languages to various degrees.</span></span>

<span data-ttu-id="ef4d0-130">最新バージョンの NuGet では C#、Visual Basic、F#、WiX、C++ がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-130">The most recent version of NuGet supports C#, Visual Basic, F#, WiX, and C++.</span></span>

<span data-ttu-id="ef4d0-131">**NuGet ではどのようなプロジェクト テンプレートがサポートされますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-131">**What project templates are supported by NuGet?**</span></span>

<span data-ttu-id="ef4d0-132">NuGet では、Windows、Web、クラウド、SharePoint、Wix などのさまざまなプロジェクト テンプレートが完全にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-132">NuGet has full support for a variety of project templates like Windows, Web, Cloud, SharePoint, Wix, and so on.</span></span>

<span data-ttu-id="ef4d0-133">**Visual Studio テンプレートの一部であるパッケージはどのように更新すればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-133">**How do I update packages that are part of Visual Studio templates?**</span></span>

<span data-ttu-id="ef4d0-134">パッケージ マネージャー UI の **[更新]** タブに移動して、**[すべて更新]** を選択するか、パッケージ マネージャー コンソールで [`Update-Package` コマンド](../tools/ps-ref-update-package.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-134">Go to the **Updates** tab in the Package Manager UI and select **Update All**, or use the [`Update-Package` command](../tools/ps-ref-update-package.md) from the Package Manager Console.</span></span>

<span data-ttu-id="ef4d0-135">テンプレート自体を更新するには、テンプレート リポジトリを手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-135">To update the template itself, you need to manually update the template repository.</span></span> <span data-ttu-id="ef4d0-136">これについては、[Xavier Decoster のブログ](http://www.xavierdecoster.com/update-project-template-to-latest-nuget-packages)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-136">See [Xavier Decoster's blog](http://www.xavierdecoster.com/update-project-template-to-latest-nuget-packages) on this subject.</span></span> <span data-ttu-id="ef4d0-137">最新バージョンのすべての依存関係が相互に互換性がない場合、手動で更新するとテンプレートが壊れる可能性があるため、これは自身の責任で行うことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-137">Note that this is done at your own risk, because manual updates might corrupt the template if the latest version of all dependencies are not compatible with each other.</span></span>

<span data-ttu-id="ef4d0-138">**Visual Studio 外部で NuGet を使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-138">**Can I use NuGet outside of Visual Studio?**</span></span>

<span data-ttu-id="ef4d0-139">はい。NuGet はコマンド ラインから直接動作します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-139">Yes, NuGet works directly from the command line.</span></span> <span data-ttu-id="ef4d0-140">[インストール ガイド](../install-nuget-client-tools.md)と [CLI 参照](../tools/nuget-exe-cli-reference.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-140">See the [Install guide](../install-nuget-client-tools.md) and the [CLI reference](../tools/nuget-exe-cli-reference.md).</span></span>

## <a name="nuget-command-line"></a><span data-ttu-id="ef4d0-141">NuGet コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="ef4d0-141">NuGet command line</span></span>

<span data-ttu-id="ef4d0-142">**最新バージョンの NuGet コマンド ライン ツールはどのように取得すればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-142">**How do I get the latest version of NuGet command line tool?**</span></span>

<span data-ttu-id="ef4d0-143">[インストール ガイド](../install-nuget-client-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-143">See the [Install guide](../install-nuget-client-tools.md).</span></span>

<span data-ttu-id="ef4d0-144">**nuget.exe のライセンスとは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-144">**What is the license for nuget.exe?**</span></span>

<span data-ttu-id="ef4d0-145">MIT ライセンスの条件に従って、nuget.exe を再配布できます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-145">You are allowed to redistribute nuget.exe under the terms of the MIT license.</span></span> <span data-ttu-id="ef4d0-146">再配布を選択した nuget.exe のコピーを更新および修正するのは、お客様の責任です。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-146">You are responsible for updating and servicing any copies of nuget.exe that you choose to redistribute.</span></span>

<span data-ttu-id="ef4d0-147">**NuGet コマンド ライン ツールを拡張することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-147">**Is it possible to extend the NuGet command line tool?**</span></span>

<span data-ttu-id="ef4d0-148">はい。[Rob Reynold の投稿](http://geekswithblogs.net/robz/archive/2011/07/15/extend-nuget-command-line.aspx)で説明されているように、`nuget.exe` にカスタム コマンドを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-148">Yes, it's possible to add custom commands to `nuget.exe`, as described in [Rob Reynold's post](http://geekswithblogs.net/robz/archive/2011/07/15/extend-nuget-command-line.aspx).</span></span>

## <a name="nuget-package-manager-console-visual-studio-on-windows"></a><span data-ttu-id="ef4d0-149">NuGet パッケージ マネージャー コンソール (Windows の Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ef4d0-149">NuGet Package Manager Console (Visual Studio on Windows)</span></span>

<span data-ttu-id="ef4d0-150">**パッケージ マネージャー コンソールでは DTE オブジェクトにどのようにアクセスするのですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-150">**How do I get access to the DTE object in the Package Manager console?**</span></span>

<span data-ttu-id="ef4d0-151">Visual Studio オートメーション オブジェクト モデルのトップ レベル オブジェクトは、DTE (開発ツール環境) オブジェクトと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-151">The top-level object in the Visual Studio automation object model is called the DTE (Development Tools Environment) object.</span></span> <span data-ttu-id="ef4d0-152">コンソールでは、`$DTE` という名前の変数を通じてこれが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-152">The console provides this through a variable named `$DTE`.</span></span> <span data-ttu-id="ef4d0-153">詳細については、Visual Studio 機能拡張ドキュメントの「[オートメーション モデルの概要](/visualstudio/extensibility/internals/automation-model-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-153">For more information, see [Automation Model Overview](/visualstudio/extensibility/internals/automation-model-overview) in the Visual Studio Extensibility documentation.</span></span>

<span data-ttu-id="ef4d0-154">**$DTE 変数を DTE2 型にキャストしようとしましたが、""EnvDTE.DTEClass" 型の "EnvDTE.DTEClass" 値を "EnvDTE80.DTE2" 型に変換できません" という内容のエラーが表示されました。何が問題なのでしょうか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-154">**I try to cast the $DTE variable to the type DTE2, but I get an error: Cannot convert the "EnvDTE.DTEClass" value of type "EnvDTE.DTEClass" to type "EnvDTE80.DTE2". What's wrong?**</span></span>

<span data-ttu-id="ef4d0-155">これは、PowerShell が COM オブジェクトと対話する方法に関する既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-155">This is a known issue with how PowerShell interacts with a COM object.</span></span> <span data-ttu-id="ef4d0-156">以下を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-156">Try the following:</span></span>

```ps
`$dte2 = Get-Interface $dte ([EnvDTE80.DTE2])`
```

<span data-ttu-id="ef4d0-157">`Get-Interface` は、NuGet PowerShell ホストによって追加されたヘルパー関数です。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-157">`Get-Interface` is a helper function added by the NuGet PowerShell host.</span></span>

## <a name="creating-and-publishing-packages"></a><span data-ttu-id="ef4d0-158">パッケージの作成と発行</span><span class="sxs-lookup"><span data-stu-id="ef4d0-158">Creating and publishing packages</span></span>

<span data-ttu-id="ef4d0-159">**フィードではどのように自分のパッケージをリストするのですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-159">**How do I list my package in a feed?**</span></span>

<span data-ttu-id="ef4d0-160">「[パッケージの作成と発行](../quickstart/create-and-publish-a-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-160">See [Creating and publishing a package](../quickstart/create-and-publish-a-package.md).</span></span>

<span data-ttu-id="ef4d0-161">**異なるバージョンの .NET Framework をターゲットとする複数バージョンのライブラリがあります。これをサポートする 1 つのパッケージをビルドするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-161">**I have multiple versions of my library that target different versions of the .NET Framework. How do I build a single package that supports this?**</span></span>

<span data-ttu-id="ef4d0-162">[複数の .NET Framework バージョンとプロファイルのサポート](../create-packages/supporting-multiple-target-frameworks.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-162">See [Supporting Multiple .NET Framework Versions and Profiles](../create-packages/supporting-multiple-target-frameworks.md).</span></span>

<span data-ttu-id="ef4d0-163">**独自のリポジトリまたはフィードを設定するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-163">**How do I set up my own repository or feed?**</span></span>

<span data-ttu-id="ef4d0-164">[パッケージのホスティングの概要](../hosting-packages/overview.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-164">See the [Hosting packages overview](../hosting-packages/overview.md).</span></span>

<span data-ttu-id="ef4d0-165">**パッケージを自分の NuGet フィードに一括でアップロードするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-165">**How can I upload packages to my NuGet feed in bulk?**</span></span>

<span data-ttu-id="ef4d0-166">「[Bulk publishing NuGet packages」](http://jeffhandley.com/archive/2012/12/13/Bulk-Publishing-NuGet-Packages.aspx) (NuGet パッケージの一括発行) (jeffhandly.com) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-166">See [Bulk publishing NuGet packages](http://jeffhandley.com/archive/2012/12/13/Bulk-Publishing-NuGet-Packages.aspx) (jeffhandly.com).</span></span>

## <a name="working-with-packages"></a><span data-ttu-id="ef4d0-167">パッケージの操作</span><span class="sxs-lookup"><span data-stu-id="ef4d0-167">Working with packages</span></span>

<span data-ttu-id="ef4d0-168">**プロジェクト レベルのパッケージとソリューション レベルのパッケージの違いは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-168">**What is the difference between a project-level package and a solution-level package?**</span></span>

<span data-ttu-id="ef4d0-169">ソリューション レベルのパッケージ (NuGet 3.x+) はソリューションに 1 回だけインストールされ、ソリューション内のすべてのプロジェクトで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-169">A solution-level package (NuGet 3.x+) is installed only once in a solution and is then available for all projects in the solution.</span></span> <span data-ttu-id="ef4d0-170">プロジェクト レベルのパッケージは、このパッケージを使用するプロジェクトごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-170">A project-level package is installed in each project that uses it.</span></span> <span data-ttu-id="ef4d0-171">ソリューション レベルのパッケージでは、パッケージ マネージャー コンソール内から呼び出すことができる新しいコマンドがインストールされる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-171">A solution-level package might also install new commands that can be called from within the Package Manager Console.</span></span>

<span data-ttu-id="ef4d0-172">**インターネットに接続せずに NuGet パッケージをインストールすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-172">**Is it possible to install NuGet packages without Internet connectivity?**</span></span>

<span data-ttu-id="ef4d0-173">はい。Scott Hanselman のブログ投稿「[How to access NuGet when nuget.org is down (or you're on a plane)](http://www.hanselman.com/blog/HowToAccessNuGetWhenNuGetorgIsDownOrYoureOnAPlane.aspx)」 (nuget.org がダウンしたとき (または飛行機内で) NuGet にアクセスする方法) (hanselman.com) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-173">Yes, see Scott Hanselman's Blog post [How to access NuGet when nuget.org is down (or you're on a plane)](http://www.hanselman.com/blog/HowToAccessNuGetWhenNuGetorgIsDownOrYoureOnAPlane.aspx) (hanselman.com).</span></span>

<span data-ttu-id="ef4d0-174">**既定のパッケージ フォルダーとは異なる場所にパッケージをインストールするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-174">**How do I install packages in a different location from the default packages folder?**</span></span>

<span data-ttu-id="ef4d0-175">`nuget config -set repositoryPath=<path>` を使用して、`Nuget.Config` で [`repositoryPath`](../reference/nuget-config-file.md#config-section) を設定します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-175">Set the [`repositoryPath`](../reference/nuget-config-file.md#config-section) setting in `Nuget.Config` using `nuget config -set repositoryPath=<path>`.</span></span>

<span data-ttu-id="ef4d0-176">**NuGet パッケージ フォルダーがソース管理に追加されないようにするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-176">**How do I avoid adding the NuGet packages folder into to source control?**</span></span>

<span data-ttu-id="ef4d0-177">`Nuget.Config` の [`disableSourceControlIntegration`](../reference/nuget-config-file.md#solution-section) を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-177">Set the [`disableSourceControlIntegration`](../reference/nuget-config-file.md#solution-section) in `Nuget.Config` to `true`.</span></span> <span data-ttu-id="ef4d0-178">このキーはソリューション レベルで動作するため、`$(Solutiondir)\.nuget\Nuget.Config` ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-178">This key works at the solution level and hence need to be added to the `$(Solutiondir)\.nuget\Nuget.Config` file.</span></span> <span data-ttu-id="ef4d0-179">Visual Studio からのパッケージの復元を有効にすると、このファイルは自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-179">Enabling package restore from Visual Studio creates this file automatically.</span></span>

<span data-ttu-id="ef4d0-180">**パッケージの復元を無効にするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-180">**How do I turn off package restore?**</span></span>

<span data-ttu-id="ef4d0-181">「[パッケージの復元の有効化と無効化](../consume-packages/package-restore.md#enabling-and-disabling-package-restore)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-181">See [Enabling and disabling package restore](../consume-packages/package-restore.md#enabling-and-disabling-package-restore).</span></span>

<span data-ttu-id="ef4d0-182">**リモートの依存関係があるローカル パッケージをインストールするときに、"依存関係を解決できません" という内容のエラーが表示されるのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-182">**Why do I get an "Unable to resolve dependency error" when installing a local package with remote dependencies?**</span></span>

<span data-ttu-id="ef4d0-183">プロジェクトにローカル パッケージをインストールする場合は、**すべて**のソースを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-183">You need to select the **All** source when installing a local package into the project.</span></span> <span data-ttu-id="ef4d0-184">これにより、フィードを 1 つだけ使用するのではなく、すべて集約することになります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-184">This aggregates all the feeds instead of using just one.</span></span> <span data-ttu-id="ef4d0-185">このエラーが表示されるのは、ローカル リポジトリのユーザーは、多くの場合、企業ポリシーにより、リモート パッケージが誤ってインストールされないようにする必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-185">The reason this error appears is that users of a local repository often want to avoid accidentally installing a remote package due to corporate polices.</span></span>

<span data-ttu-id="ef4d0-186">**同じフォルダーに複数のプロジェクトがあります。プロジェクトごとに別個の packages.config ファイルを使用するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-186">**I have multiple projects in the same folder, how can I use separate packages.config files for each project?**</span></span>

<span data-ttu-id="ef4d0-187">別個のプロジェクトが別個のフォルダーに存在するほとんどのプロジェクトでは、NuGet で各プロジェクトの `packages.config` ファイルが特定されるため、これは問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-187">In most projects where separate projects live in separate folders, this is not a problem as NuGet identifies the `packages.config` files in each project.</span></span> <span data-ttu-id="ef4d0-188">NuGet 3.3+ では、同じフォルダーに複数のプロジェクトがある場合、プロジェクトの名前を `packages.config` ファイル名に挿入できます (パターン `packages.{project-name}.config` を使用)。NuGet はそのファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-188">With NuGet 3.3+ and multiple projects in the same folder, you can insert the name of the project into the `packages.config` filenames use the pattern `packages.{project-name}.config`, and NuGet uses that file.</span></span>

<span data-ttu-id="ef4d0-189">各プロジェクト ファイルには独自の依存関係リストが含まれるため、PackageReference を使用する場合、これは問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-189">This is not an issue when using PackageReference, as each project file contains its own list of dependencies.</span></span>

<span data-ttu-id="ef4d0-190">**自分のリポジトリ リストに nuget.org が表示されません。これを戻すにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-190">**I don't see nuget.org in my list of repositories, how do I get it back?**</span></span>

- <span data-ttu-id="ef4d0-191">自分のソース リストに `https://api.nuget.org/v3/index.json` を追加します。または、</span><span class="sxs-lookup"><span data-stu-id="ef4d0-191">Add `https://api.nuget.org/v3/index.json` to your list of sources, or</span></span>
- <span data-ttu-id="ef4d0-192">`%appdata%\.nuget\NuGet.Config` (Windows) または `~/.nuget/NuGet/NuGet.Config` (Mac/Linux) を削除し、NuGet で自動的に再作成します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-192">Delete `%appdata%\.nuget\NuGet.Config` (Windows) or `~/.nuget/NuGet/NuGet.Config` (Mac/Linux) and let NuGet re-create it.</span></span>

<span data-ttu-id="ef4d0-193">**パッケージで特定のライセンス情報が提供されない場合の既定のライセンス条項は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-193">**What are the default license terms if a package doesn't provide specific license information?**</span></span>

<span data-ttu-id="ef4d0-194">各パッケージには、パッケージに含まれている条項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-194">Each package is governed by the terms that are included with the package.</span></span> <span data-ttu-id="ef4d0-195">パッケージのアクセス、ダウンロード、または取得の前に、適用される条項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-195">You should review the applicable terms before accessing, downloading, or acquiring any packages.</span></span> <span data-ttu-id="ef4d0-196">nuget.org で、パッケージ ページの **[ライセンス情報]** リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-196">On nuget.org, use the **License Info** link on the package page.</span></span>

<span data-ttu-id="ef4d0-197">パッケージでライセンス条項が指定されていない場合は、nuget.org パッケージ ページの **[Contact owners]\(所有者に問い合わせる\)** リンクを使用して、パッケージ所有者に直接問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-197">If a package does not specify the licensing terms, contact the package owner directly using the **Contact owners** link on the nuget.org package page.</span></span> <span data-ttu-id="ef4d0-198">Microsoft はサードパーティのパッケージ プロバイダーを通じてユーザーに知的財産ライセンスを付与することはありません。また、サードパーティによって提供される情報について責任を負いません。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-198">Microsoft does not license any intellectual property to you from third party package providers and is not responsible for information provided by third parties.</span></span>

## <a name="managing-packages-on-nugetorg"></a><span data-ttu-id="ef4d0-199">nuget.org でのパッケージの管理</span><span class="sxs-lookup"><span data-stu-id="ef4d0-199">Managing packages on nuget.org</span></span>

<span data-ttu-id="ef4d0-200">**パッケージ メタデータをアップロードしてから編集することはできますか? nuspec を編集し、新しいパッケージをアップロードしてパッケージ メタデータを変更するように求められるのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-200">**Can I edit package metadata after it's been uploaded? Why do you require editing the nuspec and uploading a new package for making changes to package metadata?**</span></span>

<span data-ttu-id="ef4d0-201">NuGet では、すべてのパッケージに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-201">NuGet requires all packages to be signed.</span></span> <span data-ttu-id="ef4d0-202">パッケージ署名の設計原理は、署名付きパッケージ コンテンツ (nuspec を含む) は不変でなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-202">A design principle of package signing is that signed package content must be immutable, which includes the nuspec.</span></span> <span data-ttu-id="ef4d0-203">パッケージ メタデータを編集すると、nuspec が変更され、既存の署名が無効になります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-203">Editing the package metadata results in changes to the nuspec, invalidating existing signatures.</span></span> <span data-ttu-id="ef4d0-204">パッケージが作成された後にパッケージ メタデータの編集が必要とならないように、既存のワークフローを変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-204">We recommend modifying existing workflows to not require editing the package metadata after the package has been created.</span></span>

<span data-ttu-id="ef4d0-205">パッケージに対してリストされる依存関係は、パッケージ自体から自動的に生成されるものであり、編集できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-205">Note that dependencies listed for your package are generated automatically from the package itself and cannot be edited.</span></span>

<span data-ttu-id="ef4d0-206">また、パッケージを [staging.nuget.org](http://staging.nuget.org) にアップロードすることは、パブリック ギャラリーでパッケージを使用できるようにせずに、パッケージをテストして検証する優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-206">In addition, uploading packages to [staging.nuget.org](http://staging.nuget.org) is a great way to test and validate your package without making a package available in the public gallery.</span></span>

<span data-ttu-id="ef4d0-207">**今後発行されるパッケージの名前を予約することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-207">**Is it possible to reserve names for packages that will be published in future?**</span></span>

<span data-ttu-id="ef4d0-208">はい。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-208">Yes.</span></span> <span data-ttu-id="ef4d0-209">ご使用のアカウントのパッケージ ID プレフィックスを要求することで、[nuget.org](https://www.nuget.org/) でパッケージの ID を予約できます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-209">You can reserve IDs for packages on [nuget.org](https://www.nuget.org/) by requesting a package ID prefix for your account.</span></span> <span data-ttu-id="ef4d0-210">パッケージ ID プレフィックスを要求するには、[ドキュメント](https://docs.microsoft.com/nuget/reference/id-prefix-reservation)の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-210">In order to request a package ID prefix, follow the instructions in the [documentation](https://docs.microsoft.com/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="ef4d0-211">**パッケージの所有権はどのように要求するのですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-211">**How do I claim ownership for packages ?**</span></span>

<span data-ttu-id="ef4d0-212">「[nuget.org でパッケージ所有者を管理する](../create-packages/publish-a-package.md#managing-package-owners-on-nugetorg)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-212">See [Managing package owners on nuget.org](../create-packages/publish-a-package.md#managing-package-owners-on-nugetorg).</span></span>

<span data-ttu-id="ef4d0-213">**ソフトウェア ライセンスに違反しているパッケージ所有者にはどのように対処するのですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-213">**How do I deal with a package owner who is violating my software license?**</span></span>

<span data-ttu-id="ef4d0-214">NuGet コミュニティと協力して、パッケージ所有者と他のソフトウェアの所有者間で発生する可能性のある紛争を解決することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-214">We encourage the NuGet community to work together to resolve any disputes that may arise between package owners and the owners of other software.</span></span> <span data-ttu-id="ef4d0-215">[紛争解決プロセス](../policies/dispute-resolution.md)が作成されています。nuget.org 管理者に仲裁を求める前にこのプロセスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-215">We have crafted a [dispute resolution process](../policies/dispute-resolution.md) to follow before asking nuget.org administrators to intercede.</span></span>

<span data-ttu-id="ef4d0-216">**nuget.org に自分のテスト パッケージをアップロードするよう勧めされていますか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-216">**Is it recommended to upload my test packages to nuget.org?**</span></span>

<span data-ttu-id="ef4d0-217">テスト目的で、[staging.nuget.org](http://staging.nuget.org) を使用することができます。また、[myget.org](https://myget.org) や [Visual Studio Team Services](https://blogs.msdn.microsoft.com/visualstudioalm/2015/08/27/announcing-package-management-support-for-vsotfs/) などのパブリック NuGet サーバーを代わりに使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-217">For test purposes, you can use [staging.nuget.org](http://staging.nuget.org), or alternative public NuGet servers like [myget.org](https://myget.org) or [Visual Studio Team Services](https://blogs.msdn.microsoft.com/visualstudioalm/2015/08/27/announcing-package-management-support-for-vsotfs/).</span></span>

<span data-ttu-id="ef4d0-218">staging.nuget.org にアップロードされたパッケージは保持されない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-218">Note that packages uploaded to staging.nuget.org may not be preserved.</span></span> <span data-ttu-id="ef4d0-219">[preview の終了](http://blog.nuget.org/20130419/goodbye-preview.html)に関するページ参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-219">See [Goodbye preview](http://blog.nuget.org/20130419/goodbye-preview.html).</span></span>

<span data-ttu-id="ef4d0-220">**nuget.org にアップロードできるパッケージの最大サイズは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-220">**What is the maximum size of packages I can upload to nuget.org?**</span></span>

<span data-ttu-id="ef4d0-221">nuget.org では最大 250 MB のパッケージをアップロードできますが、可能な場合はパッケージを 1 MB 未満に保ち、依存関係を使用してパッケージを相互にリンクさせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-221">nuget.org allows packages up to 250MB, but we recommend keeping packages under 1MB if possible and using dependencies to link packages together.</span></span> <span data-ttu-id="ef4d0-222">一般に、競合を避けるため、パッケージにはアセンブリを 1 つだけ含めます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-222">As a rule of thumb, packages contain only one assembly to avoid collisions.</span></span>

<span data-ttu-id="ef4d0-223">NuGet では HTTP を使用してパッケージをダウンロードするため、パッケージが大きいと、小さいパッケージよりもインストールに失敗する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-223">NuGet uses HTTP to download packages, so larger packages have a higher likelihood of failed installs than smaller ones.</span></span>

<span data-ttu-id="ef4d0-224">複数のパッケージ間で依存関係を共有することはできます。これにより、NuGet パッケージのコンシューマーの合計ダウンロード サイズが小さくなります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-224">It is possible to share dependencies between multiple packages, making the total download size for consumers of your NuGet packages smaller.</span></span>

<span data-ttu-id="ef4d0-225">依存関係は、ほとんどの場合、静的なものであり、変わることはありません。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-225">Dependencies are mostly static and never change.</span></span> <span data-ttu-id="ef4d0-226">コードでバグを修正するときは、依存関係の更新が必要ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-226">When fixing a bug in code, the dependencies may not need to be updated.</span></span> <span data-ttu-id="ef4d0-227">依存関係をバンドルする場合、結局は毎回大きなパッケージを再配布することになります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-227">If you bundle dependencies, you end up reshipping larger packages every time.</span></span> <span data-ttu-id="ef4d0-228">NuGet パッケージを関連する依存関係に分割することで、パッケージのコンシューマーに応じて、アップグレードをより細かく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-228">By splitting NuGet packages into related dependencies, upgrades are much more fine-grained for consumers of your package.</span></span>

## <a name="nugetorg-not-accessible"></a><span data-ttu-id="ef4d0-229">nuget.org にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="ef4d0-229">nuget.org not accessible</span></span>

<span data-ttu-id="ef4d0-230">**nuget.org でパッケージのダウンロードやアップロードができないのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-230">**Why can't I download packages from or upload packages to nuget.org?**</span></span>

<span data-ttu-id="ef4d0-231">まず、最新バージョンの NuGet を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-231">First, make sure you're using the latest versions of NuGet.</span></span> <span data-ttu-id="ef4d0-232">そのバージョンでも失敗する場合は、[サポートに問い合わせて](https://www.nuget.org/policies/Contact)、次の内容を含む、追加の接続のトラブルシューティングに関する情報を提供してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-232">If that version continues to fail, [contact support](https://www.nuget.org/policies/Contact) and provide additional connection troubleshooting information including:</span></span>

- <span data-ttu-id="ef4d0-233">使用している NuGet のバージョン</span><span class="sxs-lookup"><span data-stu-id="ef4d0-233">The version of NuGet you're using</span></span>
- <span data-ttu-id="ef4d0-234">使用しているパッケージ ソース</span><span class="sxs-lookup"><span data-stu-id="ef4d0-234">The package sources you're using</span></span>
- <span data-ttu-id="ef4d0-235">詳細な復元ログ</span><span class="sxs-lookup"><span data-stu-id="ef4d0-235">A restore log with detailed verbosity</span></span>
- <span data-ttu-id="ef4d0-236">MTR または Fiddler のトレース (下記参照)</span><span class="sxs-lookup"><span data-stu-id="ef4d0-236">MTR or a Fiddler traces (see below)</span></span>
- <span data-ttu-id="ef4d0-237">地理的地域</span><span class="sxs-lookup"><span data-stu-id="ef4d0-237">Your geographical area</span></span>
- <span data-ttu-id="ef4d0-238">ご利用のオペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="ef4d0-238">Your operating system version</span></span>
- <span data-ttu-id="ef4d0-239">コンピューターの構成 (CPU、ネットワーク、ハード ドライブ)</span><span class="sxs-lookup"><span data-stu-id="ef4d0-239">Machine configuration (CPU, Network, hard drive)</span></span>
- <span data-ttu-id="ef4d0-240">コンピューターがプロキシとファイアウォールのどちらの背後にあるのか</span><span class="sxs-lookup"><span data-stu-id="ef4d0-240">Whether is your machine behind a proxy or firewall</span></span>
- <span data-ttu-id="ef4d0-241">コンピューターにインストールされている .NET のバージョン</span><span class="sxs-lookup"><span data-stu-id="ef4d0-241">The versions of .NET that are installed on the machine</span></span>
- <span data-ttu-id="ef4d0-242">.NET CLI などのクロスプラットフォーム ツール、または使用している DNU のバージョン</span><span class="sxs-lookup"><span data-stu-id="ef4d0-242">Versions of cross-platform tools such as .NET CLI, or DNU that you're using</span></span>

<span data-ttu-id="ef4d0-243">*MTR をキャプチャするには:*</span><span class="sxs-lookup"><span data-stu-id="ef4d0-243">*To capture MTR:*</span></span>

- <span data-ttu-id="ef4d0-244">[http://winmtr.net/download/](http://winmtr.net/) から WinMTR をダウンロードします</span><span class="sxs-lookup"><span data-stu-id="ef4d0-244">Download WinMTR from [http://winmtr.net/download/](http://winmtr.net/)</span></span>
- <span data-ttu-id="ef4d0-245">ホスト名として「`api.nuget.org`」を入力して、**[開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-245">Enter `api.nuget.org` as the hostname and click **Start**.</span></span>
- <span data-ttu-id="ef4d0-246">**[送信]** 列が 100 以上になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-246">Wait until the **Sent** column is >= 100.</span></span>

    ![MTR のキャプチャ](media/mtr.png)

- <span data-ttu-id="ef4d0-248">クリップボードにテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-248">Copy text to clipboard.</span></span>

<span data-ttu-id="ef4d0-249">*Fiddler をキャプチャするには:*</span><span class="sxs-lookup"><span data-stu-id="ef4d0-249">*To capture Fiddler:*</span></span>

- <span data-ttu-id="ef4d0-250">最新バージョンの [Fiddler](http://www.telerik.com/download/fiddler) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-250">Install the latest version of [Fiddler](http://www.telerik.com/download/fiddler).</span></span>
- <span data-ttu-id="ef4d0-251">Fiddler を起動し、**[ファイル]、[Capture Traffic]\(トラフィックのキャプチャ\)** メニューを使用してトラフィックのキャプチャを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-251">Start Fiddler and disable capturing traffic using the **File > Capture Traffic** menu.</span></span>
- <span data-ttu-id="ef4d0-252">すべてのセッションを削除します (リストのすべての項目を選択して、**Delete** キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-252">Remove all sessions (select all items in the list, press the **Delete** key).</span></span>
- <span data-ttu-id="ef4d0-253">**[ツール]、[Fiddler Options...]\(Fiddler オプション...\)** メニューの **[HTTPS]** タブにある **[Decrypt HTTPS traffic]\(HTTPS トラフィックの暗号化解除\)** をオフにして、HTTPS トラフィックをキャプチャするように Fiddler を構成します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-253">Configure Fiddler to capture HTTPS traffic by checking **Decrypt HTTPS traffic** in the **HTTPS** tab of the **Tools > Fiddler Options...** menu.</span></span>
- <span data-ttu-id="ef4d0-254">Visual Studio を閉じます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-254">Close Visual Studio.</span></span>
- <span data-ttu-id="ef4d0-255">**[ファイル]、[Capture Traffic]\(トラフィックのキャプチャ\)** メニューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-255">Enable the **File > Capture Traffic** menu.</span></span>
- <span data-ttu-id="ef4d0-256">Visual Studio または nuget.exe を起動して、機能していないアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-256">Start Visual Studio or nuget.exe .exe and perform the actions that are not working.</span></span> <span data-ttu-id="ef4d0-257">これらのアクションによって生成されるトラフィックは Fiddler に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-257">The traffic generated by these actions should show up in Fiddler.</span></span>
- <span data-ttu-id="ef4d0-258">アクションが実行されたら、**[ファイル]、[保存]、[すべてのセッション]** を使用して、キャプチャされたセッションを保存します。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-258">Once the actions have run, use **File > Save > All Sessions** to store the captured sessions.</span></span>

<span data-ttu-id="ef4d0-259">注: Fiddler を介して NuGet トラフィックをルーティングするために、`HTTP_PROXY` 環境変数を `http://127.0.0.1:8888` に設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-259">Note: it may be required to set the `HTTP_PROXY` environment variable to `http://127.0.0.1:8888` for routing NuGet traffic through Fiddler.</span></span>

<span data-ttu-id="ef4d0-260">これが失敗した場合は、[この StackOverflow の投稿に記載されているヒント](http://stackoverflow.com/questions/21049908/using-fiddler-to-sniff-visual-studio-2013-requests-proxy-firewall)を試してください。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-260">If that fails, try the [tips mentioned in this StackOverflow post](http://stackoverflow.com/questions/21049908/using-fiddler-to-sniff-visual-studio-2013-requests-proxy-firewall).</span></span>

<span data-ttu-id="ef4d0-261">**nuget.org の API エンドポイントは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ef4d0-261">**What are the API endpoints for nuget.org?**</span></span>

<span data-ttu-id="ef4d0-262">V3: `https://api.nuget.org/v3/index.json` V2: `https://www.nuget.org/api/v2/` (V2 API は使用されなくなり、NuGet 4+ では機能しないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="ef4d0-262">V3: `https://api.nuget.org/v3/index.json` V2: `https://www.nuget.org/api/v2/` (Note that the V2 API is deprecated and does not work with NuGet 4+.)</span></span>