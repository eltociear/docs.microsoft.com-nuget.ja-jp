---
title: "NuGet CLI config コマンド |Microsoft ドキュメント"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 01/18/2018
ms.topic: reference
ms.prod: nuget
ms.technology: 
description: "Nuget.exe config コマンドのリファレンス"
keywords: "nuget config 参照、config コマンド"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 31abc5c1ade0aff9a2f23ec89ec7082acedb3653
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="config-command-nuget-cli"></a><span data-ttu-id="62ddb-104">config コマンド (NuGet CLI)</span><span class="sxs-lookup"><span data-stu-id="62ddb-104">config command (NuGet CLI)</span></span>

<span data-ttu-id="62ddb-105">**適用されます:**すべて&bullet;**サポートされているバージョン**: すべて</span><span class="sxs-lookup"><span data-stu-id="62ddb-105">**Applies to:** all &bullet; **Supported versions**: all</span></span>

<span data-ttu-id="62ddb-106">取得または NuGet の構成値を設定します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-106">Gets or sets NuGet configuration values.</span></span> <span data-ttu-id="62ddb-107">追加の使用率は、次を参照してください。 [NuGet の動作を構成する](../consume-packages/configuring-nuget-behavior.md)です。</span><span class="sxs-lookup"><span data-stu-id="62ddb-107">For additional usage, see [Configuring NuGet Behavior](../consume-packages/configuring-nuget-behavior.md).</span></span> <span data-ttu-id="62ddb-108">使用可能なキー名の詳細についてを参照してください、 [NuGet config ファイル参照](../Schema/nuget-config-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="62ddb-108">For details on allowable key names, refer to the [NuGet config file reference](../Schema/nuget-config-file.md).</span></span>

## <a name="usage"></a><span data-ttu-id="62ddb-109">使用法</span><span class="sxs-lookup"><span data-stu-id="62ddb-109">Usage</span></span>

```cli
nuget config -Set <name>=[<value>] [<name>=<value> ...] [options]
nuget config -AsPath <name> [options]
```

<span data-ttu-id="62ddb-110">ここで`<name>`と`<value>`構成で設定するキー/値ペアを指定します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-110">where `<name>` and `<value>` specify a key-value pair to be set in the configuration.</span></span> <span data-ttu-id="62ddb-111">必要に応じて多くのペアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62ddb-111">You can specify as many pairs as desired.</span></span> <span data-ttu-id="62ddb-112">値を削除するには、名前を指定し、`=`記号が、値はありません。</span><span class="sxs-lookup"><span data-stu-id="62ddb-112">To remove a value, specify the name and the `=` sign but no value.</span></span>

<span data-ttu-id="62ddb-113">使用可能なキー名では、次を参照してください。、 [NuGet config ファイル参照](../Schema/nuget-config-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="62ddb-113">For allowable key names, see the [NuGet config file reference](../Schema/nuget-config-file.md).</span></span>

<span data-ttu-id="62ddb-114">NuGet 3.4 以降で`<value>`使える[環境変数](cli-ref-environment-variables.md)です。</span><span class="sxs-lookup"><span data-stu-id="62ddb-114">In NuGet 3.4+, `<value>` can use [environment variables](cli-ref-environment-variables.md).</span></span>

## <a name="options"></a><span data-ttu-id="62ddb-115">オプション</span><span class="sxs-lookup"><span data-stu-id="62ddb-115">Options</span></span>

| <span data-ttu-id="62ddb-116">オプション</span><span class="sxs-lookup"><span data-stu-id="62ddb-116">Option</span></span> | <span data-ttu-id="62ddb-117">説明</span><span class="sxs-lookup"><span data-stu-id="62ddb-117">Description</span></span> |
| --- | --- |
| <span data-ttu-id="62ddb-118">AsPath</span><span class="sxs-lookup"><span data-stu-id="62ddb-118">AsPath</span></span> | <span data-ttu-id="62ddb-119">構成は、パスとして値を返しますするときに無視`-Set`を使用します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-119">Returns the config value as a path, ignored when `-Set` is used.</span></span> |
| <span data-ttu-id="62ddb-120">ConfigFile</span><span class="sxs-lookup"><span data-stu-id="62ddb-120">ConfigFile</span></span> | <span data-ttu-id="62ddb-121">NuGet 構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-121">The NuGet configuration file to modify.</span></span> <span data-ttu-id="62ddb-122">指定しない場合、 *%AppData%\NuGet\NuGet.Config*を使用します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-122">If not specified, *%AppData%\NuGet\NuGet.Config* is used.</span></span> |
| <span data-ttu-id="62ddb-123">ForceEnglishOutput</span><span class="sxs-lookup"><span data-stu-id="62ddb-123">ForceEnglishOutput</span></span> | <span data-ttu-id="62ddb-124">*(3.5 +)*インバリアント、英語ベースのカルチャを使用して実行する nuget.exe を強制します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-124">*(3.5+)* Forces nuget.exe to run using an invariant, English-based culture.</span></span> |
| <span data-ttu-id="62ddb-125">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="62ddb-125">Help</span></span> | <span data-ttu-id="62ddb-126">ヘルプ コマンドに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-126">Displays help information for the command.</span></span> |
| <span data-ttu-id="62ddb-127">NonInteractive</span><span class="sxs-lookup"><span data-stu-id="62ddb-127">NonInteractive</span></span> | <span data-ttu-id="62ddb-128">ユーザー入力または確認を要求するプロンプトを抑制します。</span><span class="sxs-lookup"><span data-stu-id="62ddb-128">Suppresses prompts for user input or confirmations.</span></span> |
| <span data-ttu-id="62ddb-129">詳細度</span><span class="sxs-lookup"><span data-stu-id="62ddb-129">Verbosity</span></span> | <span data-ttu-id="62ddb-130">出力に表示される詳細情報の量を指定します:*通常*、 *quiet*、*詳細*です。</span><span class="sxs-lookup"><span data-stu-id="62ddb-130">Specifies the amount of detail displayed in the output: *normal*, *quiet*, *detailed*.</span></span> |

<span data-ttu-id="62ddb-131">参照してください[環境変数](cli-ref-environment-variables.md)</span><span class="sxs-lookup"><span data-stu-id="62ddb-131">Also see [Environment variables](cli-ref-environment-variables.md)</span></span>

### <a name="examples"></a><span data-ttu-id="62ddb-132">使用例</span><span class="sxs-lookup"><span data-stu-id="62ddb-132">Examples</span></span>

```cli
nuget config -Set repositoryPath=c:\packages -configfile c:\my.config

nuget config -Set repositoryPath=

nuget config -Set repositoryPath=%PACKAGE_REPO% -configfile %ProgramData%\NuGet\NuGetDefaults.Config

nuget config -Set HTTP_PROXY=http://127.0.0.1 -set HTTP_PROXY.USER=domain\user
```