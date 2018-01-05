---
title: "NuGet パッケージの公開方法 | Microsoft Docs"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 10/5/2017
ms.topic: article
ms.prod: nuget
ms.technology: 
ms.assetid: 2342aabd-983e-4db1-9230-57c84fa36969
description: "NuGet パッケージを nuget.org やプライベート フィードに公開する方法と nuget.org でパッケージ所有権を管理する方法に関する詳細。"
keywords: "NuGet パッケージ公開, NuGet パッケージを公開する, NuGet パッケージ所有権, nuget.org に公開する, プライベート NuGet フィード"
ms.reviewer:
- anangaur
- karann-msft
- unniravindranathan
ms.openlocfilehash: fab25931165afb65aa3fd09c5bc37492ce814a49
ms.sourcegitcommit: d0ba99bfe019b779b75731bafdca8a37e35ef0d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2017
---
# <a name="publishing-packages"></a>パッケージを公開する

`nuget pack` で[パッケージを作成](../create-packages/creating-a-package.md)したら、簡単な手順を踏むだけで他の開発者に利用してもらうことができます。公開と非公開を選択できます。

- 公開パッケージの場合、このトピックで説明するように、[nuget.org](https://www.nuget.org/packages/manage/upload) 経由で世界中の開発者が利用できます。
- 非公開パッケージの場合、ファイル共有、プライベート NuGet サーバー、 [Visual Studio Team Services Package Management](https://www.visualstudio.com/docs/package/nuget/publish)、あるいは myget、ProGet、Nexus Repository、Artifactory のようなサードパーティ リポジトリで保存することで、チームや組織だけが利用できます。 詳細については、「[Hosting Packages Overview](../hosting-packages/overview.md)」 (パッケージ ホストの概要) を参照してください。

このトピックでは、nuget.org に公開する方法を採り上げます。Visual Studio Team Services に公開する方法については、「[Package Management](https://www.visualstudio.com/docs/package/nuget/publish)」 (パッケージ管理) をご覧ください。

## <a name="publish-to-nugetorg"></a>nuget.org に公開する

nuget.org の場合、最初に[無料アカウントを作成する](https://www.nuget.org/users/account/LogOn?returnUrl=%2F)必要があります。登録済みの場合、サインインしてください。

![NuGet 登録とサインインの場所](media/publish_NuGetSignIn.png)

次に、nuget.org Web ポータルからパッケージをアップロードするか、コマンド ラインから nuget.org にプッシュするか、次のセクションで説明するように、Visual Studio Team Services から CI/CD プロセスの一部として公開できます。

### <a name="web-portal-use-the-upload-package-tab-on-nugetorg"></a>Web ポータル: nuget.org の [Upload Package ] タブを使用する:

![NuGet Package Manager でパッケージをアップロードする](media/publish_UploadYourPackage.PNG)

### <a name="command-line"></a>コマンド ライン:
> [!Important]
> nuget.org にパッケージをプッシュするには、[nuget.exe v4.1.0 以降](https://www.nuget.org/downloads)を使用する必要があります。これは必須の [NuGet プロトコル](../api/nuget-protocols.md)を実装します。

1. ユーザー名をクリックし、アカウント設定に移動します。
2. **[API キー]** の下で、**[クリップボードにコピー]** をクリックし、CLI で必要となるアクセス キーを取得します。

    ![アカウント設定から API キーをコピーする](media/publish_APIKey.png)

3. コマンド プロンプトで次のコマンドを実行します。

    ```
    nuget setApiKey Your-API-Key
    ```

    この操作により、コンピューターに API キーが格納されます。同じコンピューターでこの手順を繰り返す必要がなくなります。

4. コマンドを利用し、NuGet ギャラリーにパッケージをプッシュする:

    ```
    nuget push YourPackage.nupkg -Source https://api.nuget.org/v3/index.json
    ```

5. 一般公開前に、nuget.org にアップロードされたすべてのパッケージはウイルス スキャンが行われ、見つかった場合、拒否されます。 nuget.org の一覧にあるすべてのパッケージも定期的にスキャンされます。

6. nuget.org のアカウントで、**[Manage my packages]** をクリックし、公開したパッケージを確認します。また、確認の電子メールが届きます。 パッケージにインデックスが付けられ、検索結果に表示されるようになり、他のユーザーが検索可能になるまで時間がかかることがあります。その間、パッケージ ページには次のメッセージが表示されます。

    ![パッケージのインデックスがまだ作成されていないことを示すメッセージ](media/publish_NotYetIndexed.png)

### <a name="package-validation-and-indexing"></a>パッケージの検証とインデックスの作成

NuGet.org にプッシュされたパッケージはいくつかの検証を受けます。 パッケージがすべての検証に合格すると、インデックスが作成され、検索結果に表示されるようになりますが、それには時間がかかることがあります。 インデックス作成が完了すると、パッケージが正常に公開されたことを示す確認の電子メールが届きます。 パッケージが検証で不合格になった場合、パッケージの詳細ページが更新され、関連エラーが表示されます。それに関する電子メールも届きます。

パッケージの検証とインデックスの作成は、通常、15 以内で完了します。 パッケージ公開に予想以上の時間がかかる場合、[status.nuget.org](https://status.nuget.org/) にアクセスし、NuGet.org に中断が発生していないか確認してください。 すべてのシステムが動作しているとき、1 時間以内にパッケージが正常に公開されない場合、NuGet.org にログインし、パッケージ ページの [Contact Support] リンクからお問い合わせください。

### <a name="visual-studio-team-services-cicd"></a>Visual Studio Team Services (CI/CD)

CI/CD (継続的インテグレーション/配置) の一部として Visual Studio Team Services を利用して nuget.org にパッケージをプッシュする場合、NuGet タスクで nuget.exe 4.1 以上を使用する必要があります。 詳細は、Microsoft DevOps ブログの「[Using the latest NuGet in your build](https://blogs.msdn.microsoft.com/devops/2017/09/29/using-the-latest-nuget-in-your-build/)」 (ビルドで最新の NuGet を利用する) にあります。

## <a name="managing-package-owners-on-nugetorg"></a>nuget.org でパッケージ所有者を管理する

各 NuGet パッケージの `.nuspec` はパッケージの作成者を定義するものですが、nuget.org ギャラリーでは、所有権の定義にそのメタデータは使用されません。 nuget.org では、パッケージを公開した人に最初の所有権が割り当てられます。 これは nuget.org UI からパッケージをアップロードしたログイン ユーザーになるか、`nuget SetApiKey` または `nuget push` と共に API キーが使用されたユーザーになります。

パッケージ所有者にはすべて、パッケージの完全アクセス許可が与えられます。他の所有者を追加したり、削除したり、更新内容を公開したりできます。

パッケージの所有権は次のように変更します。

1. パッケージの現在の所有者になっているアカウントで nuget.org にサインインします。
1. ユーザー名、**[Manage my packages]**、管理するパッケージの順にクリックします。
1. 左側にある **[Manage owners]** リンクをクリックします。

ここにはいくつかのオプションがあります。

1. 所有者を追加するには、その NuGet アカウント名を入力し、**[Add]** をクリックします。 これでその新しい共同所有者に確認リンクを含む電子メールが送信されます。 確認後、その人に所有者を追加したり、削除したりできる完全アクセス許可が与えられます。 (確認されるまで、**[Manage owners]** ページにはその人の "pending approval" (承認待ち) が表示されます。)
1. 所有者を削除するには、**[Manage owners]** で名前を選択し、**[Remove]** をクリックします。
1. 所有権を譲渡するには (所有権が変更された場合や間違ったアカウントでパッケージが公開された場合)、新しい所有者を追加します。新しい所有者は所有権を確認したら、一覧から他の所有者を削除できます。

会社またはグループに所有権を割り当てるには、適切なチーム メンバーに転送される電子メール エイリアスを利用して nuget.org アカウントを作成します。 たとえば、そのようなエイリアスである [microsoft](http://nuget.org/profiles/microsoft) アカウントや [aspnet](http://nuget.org/profiles/aspnet) アカウントでさまざまな Microsoft ASP.NET パッケージが共同所有されています。

### <a name="recovering-package-ownership"></a>パッケージ所有権を回復する

パッケージにアクティブな所有者が与えられていないことがあります。 たとえば、パッケージを作る会社を元々の所有者が去った場合、nuget.org 資格情報をなくした場合、ギャラリーの早期のバグが原因でパッケージが所有者なしになった場合などです。

自分がパッケージの正当な所有者であり、所有権を取り戻す必要がある場合、nuget.org の[問い合わせフォーム](https://www.nuget.org/policies/Contact)を利用し、NuGet チームに状況を説明してください。 その後、パッケージの所有権を検証するプロセスが開始します。パッケージのプロジェクト URL、Twitter、電子メール、その他の手段で既存の所有者が確認されます。 いずれの方法でも確認できない場合、所有者になるための新しい招待を送信します。