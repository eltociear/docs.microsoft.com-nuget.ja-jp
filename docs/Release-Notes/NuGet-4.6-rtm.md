---
title: "NuGet 4.6 RTM のリリース ノート | Microsoft Docs"
author: anangaur
ms.author: anangaur
manager: unnir
ms.date: 3/7/2018
ms.topic: article
ms.prod: nuget
ms.technology: 
description: "NuGet 4.6.0 のリリース ノートであり、既知の問題、バグ修正、追加機能、および DCR が含まれています。"
keywords: "NuGet 4.6.0 リリース ノート, バグ修正, 既知の問題, 追加機能, DCR"
ms.reviewer:
- karann-msft
- unniravindranathan
- anangaur
ms.openlocfilehash: 32bfe8a7d5d60a0ad24444749beff64edcaab305
ms.sourcegitcommit: fa31ae10b5a5add7184bf7420554aade8adce6ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2018
---
# <a name="nuget-46-rtm-release-notes"></a><span data-ttu-id="37c85-104">NuGet 4.6 RTM リリース ノート</span><span class="sxs-lookup"><span data-stu-id="37c85-104">NuGet 4.6 RTM Release Notes</span></span>

<span data-ttu-id="37c85-105">[Visual Studio 2017 15.6 RTW](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) には、[NuGet 4.6.0](https://dist.nuget.org/win-x86-commandline/v4.6.0/nuget.exe) が付属しています。</span><span class="sxs-lookup"><span data-stu-id="37c85-105">[Visual Studio 2017 15.6 RTW](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) comes with [NuGet 4.6.0](https://dist.nuget.org/win-x86-commandline/v4.6.0/nuget.exe).</span></span>

## <a name="summary-whats-new-in-this-release"></a><span data-ttu-id="37c85-106">概要: このリリースの新機能</span><span class="sxs-lookup"><span data-stu-id="37c85-106">Summary: What's New in this Release</span></span>
* <span data-ttu-id="37c85-107">[パッケージの署名](https://docs.microsoft.com/en-us/nuget/create-packages/sign-a-package)のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="37c85-107">We have added support for [signing packages](https://docs.microsoft.com/en-us/nuget/create-packages/sign-a-package).</span></span>  
* <span data-ttu-id="37c85-108">Visual Studio 2017 と nuget.exe では、[署名済みパッケージ](https://docs.microsoft.com/en-us/nuget/reference/signed-packages-reference)について、パッケージをインストール、復元する前にパッケージの整合性を検証できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="37c85-108">Visual Studio 2017 and nuget.exe now verifies package integrity before installing, restoring packages for [signed packages](https://docs.microsoft.com/en-us/nuget/reference/signed-packages-reference).</span></span>
* <span data-ttu-id="37c85-109">連続する復元のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="37c85-109">We have improved performance of successive restores.</span></span>

## <a name="known-issues"></a><span data-ttu-id="37c85-110">既知の問題</span><span class="sxs-lookup"><span data-stu-id="37c85-110">Known issues</span></span>
### <a name="issues-with-net-standard-20-with-net-framework--nuget"></a><span data-ttu-id="37c85-111">.NET Framework と NuGet での .NET Standard 2.0 の問題</span><span class="sxs-lookup"><span data-stu-id="37c85-111">Issues with .NET Standard 2.0 with .NET Framework & NuGet</span></span> 

<span data-ttu-id="37c85-112">.NET Standard とそのツールは、.NET Framework 4.6.1 をターゲットとするプロジェクトが、.NET Standard 2.0 以前をターゲットとする NuGet パッケージおよびプロジェクトを使用できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="37c85-112">.NET Standard & its tooling was designed such that projects targeting .NET Framework 4.6.1 can consume NuGet packages & projects targeting .NET Standard 2.0 or earlier.</span></span> <span data-ttu-id="37c85-113">[このドキュメント](https://github.com/dotnet/standard/issues/481)では、そのシナリオに関連する問題の概要、それらの問題を解決する計画、そのツールの今日の状態で展開できる解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="37c85-113">[This document](https://github.com/dotnet/standard/issues/481) summarizes the issues around that scenario, the plan for addressing them, and workarounds you can deploy with today's state of the tooling.</span></span>

## <a name="top-issues-fixed-in-this-release"></a><span data-ttu-id="37c85-114">このリリースで修正された主な問題</span><span class="sxs-lookup"><span data-stu-id="37c85-114">Top issues fixed in this release</span></span>

<span data-ttu-id="37c85-115">**パフォーマンスの改善**</span><span class="sxs-lookup"><span data-stu-id="37c85-115">**Performance fixes**</span></span>
* <span data-ttu-id="37c85-116">変更がない場合に資産ファイルを書き込まない - [#6491](https://github.com/NuGet/Home/issues/6491)</span><span class="sxs-lookup"><span data-stu-id="37c85-116">Don't write asset files when there is no change - [#6491](https://github.com/NuGet/Home/issues/6491)</span></span>
* <span data-ttu-id="37c85-117">子プロジェクトの TFM が親プロジェクトの TFM と一致しない場合、復元によって追加の MSBuild 評価が発生する - [#6311](https://github.com/NuGet/Home/issues/6311)</span><span class="sxs-lookup"><span data-stu-id="37c85-117">Restore causes extra MSBuild evaluations when child projects' TFM do not match with the parent project's - [#6311](https://github.com/NuGet/Home/issues/6311)</span></span>
* <span data-ttu-id="37c85-118">依存関係グラフ仕様の作成を最適化することで NoOp 復元のパフォーマンスを向上する - [#6252](https://github.com/NuGet/Home/issues/6252)</span><span class="sxs-lookup"><span data-stu-id="37c85-118">Improve NoOp restore perf by optimizing dependency graph spec creation - [#6252](https://github.com/NuGet/Home/issues/6252)</span></span>

<span data-ttu-id="37c85-119">**バグ**</span><span class="sxs-lookup"><span data-stu-id="37c85-119">**Bugs**</span></span>
* <span data-ttu-id="37c85-120">ローカル フォルダーにプッシュすると、nupkg がロックされたままになる - [#6325](https://github.com/NuGet/Home/issues/6325)</span><span class="sxs-lookup"><span data-stu-id="37c85-120">Push to local folder leaves nupkg locked - [#6325](https://github.com/NuGet/Home/issues/6325)</span></span>
* <span data-ttu-id="37c85-121">NuGet プラグインの実装: 複数の問題 - [#6149](https://github.com/NuGet/Home/issues/6149)</span><span class="sxs-lookup"><span data-stu-id="37c85-121">NuGet Plugin implementation:  multiple issues - [#6149](https://github.com/NuGet/Home/issues/6149)</span></span>
* <span data-ttu-id="37c85-122">UIHang - VSSolutionManager の MEF の初期化からクエリ サービス呼び出しを削除する - [#6110](https://github.com/NuGet/Home/issues/6110)</span><span class="sxs-lookup"><span data-stu-id="37c85-122">UIHang - Remove query service call from MEF initialization in VSSolutionManager - [#6110](https://github.com/NuGet/Home/issues/6110)</span></span>
* <span data-ttu-id="37c85-123">取り消されたパッケージ ダウンロード タスクのエラー報告の例外 - [#6096](https://github.com/NuGet/Home/issues/6096)</span><span class="sxs-lookup"><span data-stu-id="37c85-123">Error reporting exception for cancelled package download task - [#6096](https://github.com/NuGet/Home/issues/6096)</span></span>
* <span data-ttu-id="37c85-124">NuGet.exe がアセンブリ名の '+' を '%2B' に置換する - [#5956](https://github.com/NuGet/Home/issues/5956)</span><span class="sxs-lookup"><span data-stu-id="37c85-124">NuGet.exe replaces '+' with '%2B' in assembly name - [#5956](https://github.com/NuGet/Home/issues/5956)</span></span>
* <span data-ttu-id="37c85-125">F1 キーを押しても PM UI とコンソールの正しいヘルプ ページが表示されない - [#5912](https://github.com/NuGet/Home/issues/5912)</span><span class="sxs-lookup"><span data-stu-id="37c85-125">Fn+F1 does not take to the right help page for PM UI and Console - [#5912](https://github.com/NuGet/Home/issues/5912)</span></span>
* <span data-ttu-id="37c85-126">特定の状況下で VS NuGet が絶対パスをプロジェクト ファイルに書き込む - [#5888](https://github.com/NuGet/Home/issues/5888)</span><span class="sxs-lookup"><span data-stu-id="37c85-126">VS NuGet writes absolute paths into project files under specific circumstances - [#5888](https://github.com/NuGet/Home/issues/5888)</span></span>
* <span data-ttu-id="37c85-127">4.3 の回帰を修正 - 変換で contentfile 内のプレースホルダー $product$ と $AssemblyGuid$ が置換されない - [#5880](https://github.com/NuGet/Home/issues/5880)</span><span class="sxs-lookup"><span data-stu-id="37c85-127">Fix 4.3 regression - Placeholders $product$ and $AssemblyGuid$ not replaced in contentfile through transformation - [#5880](https://github.com/NuGet/Home/issues/5880)</span></span>
* <span data-ttu-id="37c85-128">ソースが複数ある dotnet restore がクラッシュする - [#5817](https://github.com/NuGet/Home/issues/5817)</span><span class="sxs-lookup"><span data-stu-id="37c85-128">dotnet restore with multiple sources crashes - [#5817](https://github.com/NuGet/Home/issues/5817)</span></span>
* <span data-ttu-id="37c85-129">git のバージョン管理を使用するにはパックでプロジェクトのバージョンを再評価する必要がある - [#4790](https://github.com/NuGet/Home/issues/4790)</span><span class="sxs-lookup"><span data-stu-id="37c85-129">Pack should re-evaluate project versions to allow git versioning - [#4790](https://github.com/NuGet/Home/issues/4790)</span></span>
* <span data-ttu-id="37c85-130">互換性のないパッケージをインストールした場合のわかりづらいエラーを改善 - [#4555](https://github.com/NuGet/Home/issues/4555)</span><span class="sxs-lookup"><span data-stu-id="37c85-130">Improve hard to understand errors when you install an incompatible package - [#4555](https://github.com/NuGet/Home/issues/4555)</span></span>
* <span data-ttu-id="37c85-131">TemplateWizard のオプションで、パッケージを PackageReferences としてインストールする必要がある - [#4549](https://github.com/NuGet/Home/issues/4549)</span><span class="sxs-lookup"><span data-stu-id="37c85-131">TemplateWizard needs option to install packages as PackageReferences - [#4549](https://github.com/NuGet/Home/issues/4549)</span></span>
* <span data-ttu-id="37c85-132">MSBuild.exe が開発者コマンド プロンプト以外から実行された場合にパッケージ配信されたプロパティ ファイルが無視される - [#4530](https://github.com/NuGet/Home/issues/4530)</span><span class="sxs-lookup"><span data-stu-id="37c85-132">Package-delivered props files ignored when MSBuild.exe is run from outside a Developer Command Prompt - [#4530](https://github.com/NuGet/Home/issues/4530)</span></span>
* <span data-ttu-id="37c85-133">プロジェクトに適用されない .NET Standard ライブラリを参照する場合のわかりづらいエラー メッセージを修正 - [#4423](https://github.com/NuGet/Home/issues/4423)</span><span class="sxs-lookup"><span data-stu-id="37c85-133">Fix poor error message when referencing .NET Standard Library that is not applicable to project - [#4423](https://github.com/NuGet/Home/issues/4423)</span></span>
* <span data-ttu-id="37c85-134">ポータブル プロファイルをターゲットとするパッケージの dotnet add package が失敗し、ほとんどガイダンスが表示されない - [#4349](https://github.com/NuGet/Home/issues/4349)</span><span class="sxs-lookup"><span data-stu-id="37c85-134">dotnet add package fails for package targeting portable profile with little guidance - [#4349](https://github.com/NuGet/Home/issues/4349)</span></span>
* <span data-ttu-id="37c85-135">dotnet pack - ProjectReference にバージョンのサフィックスがない - [#4337](https://github.com/NuGet/Home/issues/4337)</span><span class="sxs-lookup"><span data-stu-id="37c85-135">dotnet pack - version suffix missing from ProjectReference - [#4337](https://github.com/NuGet/Home/issues/4337)</span></span>
* <span data-ttu-id="37c85-136">.NET Core テンプレートのビルド エラーと VS のクラッシュ - [#3973](https://github.com/NuGet/Home/issues/3973)</span><span class="sxs-lookup"><span data-stu-id="37c85-136">Build errors and VS crash with .NET Core template - [#3973](https://github.com/NuGet/Home/issues/3973)</span></span>
* <span data-ttu-id="37c85-137">ソースの https:\* のサービス インデックスを読み込むことができない - [#3681](https://github.com/NuGet/Home/issues/3681)</span><span class="sxs-lookup"><span data-stu-id="37c85-137">Unable to load the service index for source https:\* - [#3681](https://github.com/NuGet/Home/issues/3681)</span></span>
* <span data-ttu-id="37c85-138">nuget.exe list -allversions が動作しない - [#3441](https://github.com/NuGet/Home/issues/3441)</span><span class="sxs-lookup"><span data-stu-id="37c85-138">nuget.exe list -allversions doesn't work - [#3441](https://github.com/NuGet/Home/issues/3441)</span></span>
* <span data-ttu-id="37c85-139">誤解を招く依存関係解決のエラー メッセージ - [#2984](https://github.com/NuGet/Home/issues/2984)</span><span class="sxs-lookup"><span data-stu-id="37c85-139">Misleading dependency resolution error message - [#2984](https://github.com/NuGet/Home/issues/2984)</span></span>
* <span data-ttu-id="37c85-140">nuget.exe の復元で .msbuildproj の .props および .targets ファイルが生成されない (v3.3.0-3.4.4 アップグレードの回帰) - [#2921](https://github.com/NuGet/Home/issues/2921)</span><span class="sxs-lookup"><span data-stu-id="37c85-140">nuget.exe restore doesn't produce .props and .targets files for .msbuildproj (regression in v3.3.0-3.4.4 upgrade) - [#2921](https://github.com/NuGet/Home/issues/2921)</span></span>
* <span data-ttu-id="37c85-141">XAML ファイルを開いた状態で NuGet パッケージを更新するときに UI に遅延が生じる - [#2878](https://github.com/NuGet/Home/issues/2878)</span><span class="sxs-lookup"><span data-stu-id="37c85-141">UI delay when updating a NuGet package with XAML file open - [#2878](https://github.com/NuGet/Home/issues/2878)</span></span>
* <span data-ttu-id="37c85-142">パスに不適切な文字があると、IIS の WebSite プロジェクトが失敗する - [#2798](https://github.com/NuGet/Home/issues/2798)</span><span class="sxs-lookup"><span data-stu-id="37c85-142">WebSite project from IIS fails with illegal characters in path - [#2798](https://github.com/NuGet/Home/issues/2798)</span></span>
* <span data-ttu-id="37c85-143">CentOS 上で nuget add がハングする - [#2708](https://github.com/NuGet/Home/issues/2708)</span><span class="sxs-lookup"><span data-stu-id="37c85-143">Nuget add hangs on CentOS - [#2708](https://github.com/NuGet/Home/issues/2708)</span></span>
* <span data-ttu-id="37c85-144">json.net の場合、packagesavemode -nupkg を使用した復元が失敗する - [#2706](https://github.com/NuGet/Home/issues/2706)</span><span class="sxs-lookup"><span data-stu-id="37c85-144">Restore with packagesavemode -nupkg fails for json.net - [#2706](https://github.com/NuGet/Home/issues/2706)</span></span>
* <span data-ttu-id="37c85-145">restore コマンドの vs 出力ウィンドウでパッケージ マネージャー フィルターを使用できない - [#2704](https://github.com/NuGet/Home/issues/2704)</span><span class="sxs-lookup"><span data-stu-id="37c85-145">Package Manager filter not available in vs output window for restore command - [#2704](https://github.com/NuGet/Home/issues/2704)</span></span>


[<span data-ttu-id="37c85-146">このリリースで修正されたすべての問題一覧</span><span class="sxs-lookup"><span data-stu-id="37c85-146">List of all issues fixed in this release</span></span>](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%224.6")