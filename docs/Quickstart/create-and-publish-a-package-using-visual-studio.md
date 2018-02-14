---
title: "Visual Studio を使用して NuGet パッケージを作成し公開するための入門ガイド | Microsoft Docs"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 02/02/2018
ms.topic: get-started-article
ms.prod: nuget
ms.technology: 
description: "Visual Studio 2017 を使用した、NuGet パッケージの作成と公開に関するチュートリアル。"
keywords: "NuGet パッケージの作成、NuGet パッケージの公開、NuGet チュートリアル、Visual Studio による NuGet パッケージの作成、msbuild pack"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: a4d60fdc0f27f9c4080266e212ac1cfe470ba925
ms.sourcegitcommit: eabd401616a98dda2ae6293612acb3b81b584967
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="create-and-publish-a-package-using-visual-studio"></a>Visual Studio を使用した、パッケージの作成と公開

Visual Studio で.NET クラス ライブラリから NuGet パッケージを作成し、CLI ツールを使用してパッケージを nuget.org に公開する簡単なプロセスです。

## <a name="pre-requisites"></a>前提条件

1. [visualstudio.com](https://www.visualstudio.com/) から Visual Studio 2017 の任意のエディションと、.NET 関連の任意のワークロードをインストールします。 Visual Studio 2017 では、.NET ワークロードをインストールする際、NuGet 機能は自動的に含まれません。

1. `nuget.exe` CLI をインストールします。[nuget.org](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe)からその `.exe`ファイルをダウンロードし、適切なフォルダーに保存して、そのフォルダーを PATH 環境変数に追加してください。

    または、[.NET Core SDK](https://www.microsoft.com/net/download/) をインストールしている場合は、`dotnet` CLI を使用できます。

1. まだ持っていない場合は、[nuget.org で無料アカウントを登録](https://www.nuget.org/users/account/LogOn?returnUrl=%2F)します。 新しいアカウントを作成すると、確認メールが送信されます。 パッケージをアップロードするには、その前にアカウントを確認する必要があります。

## <a name="create-a-class-library-project"></a>クラス ライブラリ プロジェクトを作成する

パッケージ化するコードに既存の .NET クラス ライブラリ プロジェクトを使用することも、次の手順に従って単純なプロジェクトを作成することもできます。

1. Visual Studio で、**[ファイル]、[新規]、[プロジェクト]** の順に選択し、**[Visual C#]、[.NET Standard]** ノードの順に展開して "クラス ライブラリ (.NET Standard)" テンプレートを選択し、プロジェクトに AppLogger という名前を付け、**[OK]** をクリックします。

1. 作成されたプロジェクト ファイルを右クリックし、**[ビルド]** を選択して、プロジェクトが正しく作成されたことを確認します。 DLL は、デバッグ フォルダー (または代わりにその構成をビルドした場合はリリース フォルダー) 内にあります。

実際の NuGet パッケージ内ではもちろん、多くの便利な機能を実装し、他のユーザーはそれを使用してアプリケーションをビルドできます。 しかし、このチュートリアルでは、パッケージを作成するには、テンプレートのクラス ライブラリで十分なため、追加のコードを記述することはありません。 それでも、パッケージの一部の機能コードが必要な場合は、次のように使用します。

```cs
namespace AppLogger
{
    public class Logger
    {
        public void Log(string text)
        {
            Console.WriteLine(text);
        }
    }
}
```

> [!Tip]
> それ以外を選択する理由がない限り、.NET Standard は最も広い範囲の使用プロジェクトとの互換性を提供するため、NuGet パッケージの優先ターゲットです。

## <a name="configure-package-properties"></a>パッケージのプロパティを構成する

1. **[プロジェクト]、[プロパティ]** メニュー コマンドの順に選択し、**[パッケージ]** タブを選択します。

    ![Visual Studio プロジェクト内の NuGet パッケージのプロパティ](media/qs_create-vs-01-package-properties.png)

    > [!Note]
    > 公開用にビルドされたパッケージの場合は、**Tags**プロパティに特に注意してください。これらのタグは他のユーザーがパッケージを検索して、パッケージの動作を理解するのに役立ちます。

1. パッケージに一意の識別子を付けて、他の必要なプロパティを指定します。 さまざまなプロパティについては、[.nuspec ファイルのリファレンス](../reference/nuspec.md) ページを参照してください。 これらのプロパティはすべて、Visual Studio でプロジェクト用に作成された `.nuspec`マニフェストに保存されます。

    > [!Important]
    > パッケージには、nuget.org または使用しているホスト全体で一意の識別子を付ける必要があります。 このチュートリアルでは、以降の公開手順でパッケージを一般公開するので (ただし、誰かが実際に使用する可能性はありません)、名前に "Sample" または "Test" を含めることをお勧めします。
    >
    > 既に存在する名前のパッケージを公開しようとすると、エラーが表示されます。

1. 省略可能: プロジェクト ファイルで直接プロパティを表示するには、ソリューション エクスプローラーでプロジェクトを右クリックし、**[Edit AppLogger.csproj]\(AppLogger.csproj の編集\)** を選択します。

## <a name="run-the-pack-command"></a>pack コマンドを実行する

1. 構成を **[リリース]** に設定します。

1. **ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[パック]** コマンドを選択します。

    ![Visual Studio プロジェクトのコンテキスト メニューの NuGet パック コマンド](media/qs_create-vs-02-pack-command.png)

1. Visual Studio により、プロジェクトがビルドされ、`.nupkg` ファイルが作成されます。 **[出力]** ウィンドウで (次のような) 詳細を確認します。このウィンドウには、パッケージ ファイルへのパスが表示されます。 ビルドされたアセンブリは .NET Standard 2.0 ターゲットに適合するため `bin\Release\netstandard2.0` にもあります。

    ```output
    1>------ Build started: Project: AppLogger, Configuration: Release Any CPU ------
    1>AppLogger -> d:\proj\AppLogger\AppLogger\bin\Release\netstandard2.0\AppLogger.dll
    1>Successfully created package 'd:\proj\AppLogger\AppLogger\bin\Release\AppLogger.1.0.0.nupkg'.
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

### <a name="alternate-option-pack-with-msbuild"></a>別のオプション: MSBuild の pack

**Pack** メニュー コマンドを使用する代わりとして、NuGet 4.x+ と MSBuild 15.1+ ではプロジェクトに必要なパッケージ データが含まれている場合に `pack` ターゲットをサポートしています。

```cli
msbuild /t:pack /p:Configuration=Release
```

このパッケージは `bin\Release` フォルダーにあります。

`msbuild /t:pack` のその他のオプションについては、「[NuGet pack and restore as MSBuild targets](../reference/msbuild-targets.md#pack-target)」(MSBuild ターゲットとしての NuGet のパックと復元) をご覧ください。

## <a name="publish-the-package"></a>パッケージを公開する

`.nupkg` ファイルを作成したら、`nuget.exe` CLI または `dotnet.exe` CLI と、nuget.org から取得した API キーを使用して、そのファイルを nuget.org に公開します。

[!INCLUDE[publish-notes](includes/publish-notes.md)]

### <a name="acquire-your-api-key"></a>API キーを取得する

[!INCLUDE[publish-api-key](includes/publish-api-key.md)]

### <a name="publish-with-nuget-push"></a>nuget push を使用して公開する

この手順は、`dotnet.exe`の使用に代わる方法です。

1. `.nupkg`ファイルを含むフォルダーに変更します。

1. 次のコマンドでパッケージ名を指定し、キーを API キーに置き換えて、コマンドを実行します。

    ```cli
    nuget push AppLogger.1.0.0.nupkg qz2jga8pl3dvn2akksyquwcs9ygggg4exypy3bhxy6w6x6 -Source https://api.nuget.org/v3/index.json
    ```

1. nuget.exe によって公開プロセスの結果が表示されます。

    ```output
    Pushing AppLogger.1.0.0.nupkg to 'https://www.nuget.org/api/v2/package'...
        PUT https://www.nuget.org/api/v2/package/
        Created https://www.nuget.org/api/v2/package/ 6829ms
    Your package was pushed.
    ```

[nuget push](../tools/cli-ref-push.md)に関するページを参照してください。

### <a name="publish-with-dotnet-nuget-push"></a>dotnet nuget push を使用して公開する

この手順は、`nuget.exe`の使用に代わる方法です。

[!INCLUDE[publish-dotnet](includes/publish-dotnet.md)]

### <a name="publish-errors"></a>公開エラー

[!INCLUDE[publish-errors](includes/publish-errors.md)]

### <a name="manage-the-published-package"></a>公開済みパッケージを管理する

[!INCLUDE[publish-manage](includes/publish-manage.md)]

## <a name="related-topics"></a>関連トピック

- [パッケージの作成](../create-packages/creating-a-package.md)
- [パッケージの公開](../create-packages/publish-a-package.md)
- [複数のターゲット フレームワークのサポート](../create-packages/supporting-multiple-target-frameworks.md)
- [パッケージのバージョン管理](../reference/package-versioning.md)
- [ローカライズされたパッケージを作成する](../create-packages/creating-localized-packages.md)
- [.NET Standard ライブラリのドキュメント](/dotnet/articles/standard/library)
- [.NET Framework から .NET Core への移植](/dotnet/articles/core/porting/index)