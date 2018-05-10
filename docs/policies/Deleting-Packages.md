---
title: nuget.org から NuGet パッケージを削除する
description: nuget.org の一覧からパッケージを削除するポリシーです。パッケージが他のポリシーに違反しない限り、完全な削除はサポートされません。
author: kraigb
ms.author: kraigb
manager: douge
ms.date: 01/18/2018
ms.topic: conceptual
ms.openlocfilehash: bea4f1589f184d38da27e5d82c3ce17a183fbdd1
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="deleting-packages"></a>パッケージの削除

nuget.org では、パッケージの完全な削除はサポートされていません。 この操作を行うには、パッケージの機能に応じて、特にパッケージの復元を含むビルドのワークフローで、すべてのプロジェクトを中断します。

nuget.org では、Web サイト上のパッケージ管理ページで実行できる、パッケージの*一覧からの削除*はサポートされません。 一覧から削除されたパッケージは、nuget.org または Visual Studio UI に表示されません。また、検索結果にも表示されません。 ただし、一覧から削除されたパッケージは、引き続きパッケージの復元をサポートする正確なバージョン番号を使用し、ダウンロードしてインストールすることができます。 さらに、一覧から削除されたパッケージは、次の特定のシナリオで引き続き検出される可能性があります。

- バージョンまたは依存関係の制約を満たす使用できる最新パッケージが一覧から削除されたパッケージの場合の、最新バージョンを使用したパッケージの復元 (例: `1.0.0-*`)。
- (カタログに一覧から削除されたパッケージも含まれるように) カタログを使用したパッケージのレプリケーション。

## <a name="exceptions"></a>例外

著作権侵害や問題を起こす可能性のあるコンテンツなどの例外状況では、パッケージは NuGet チームによって手動で削除することができます。 このプロセスを開始するには、[NuGet ギャラリー](http://www.nuget.org)からサポート リクエストを送信します。

## <a name="prohibited-use"></a>禁止事項

次のいずれかの基準を満たすパッケージは、パブリック NuGet ギャラリー上で許可されません。また、そのようなパッケージは、ディスカッションされることなく、すぐに削除されます。 ただし、パッケージの所有者は、削除の通知を受けます。

- マルウェア、アドウェア、またはあらゆる種類のスパイウェアが含まれる
- 開発者のワークステーションまたは組織に損害を与えるように設計されている
- 著作権を侵害したり、ライセンスに違反したりしている
- 違法なコンテンツを含む
- 生産性のないコンテンツを含むパッケージなど、パッケージの識別子を占拠するために使用されている。 パッケージにコードが含まれるか、所有者が実際に出荷する製品を所有しているユーザーに識別子を譲る必要があります。
- ギャラリーで明示的に実行するように設計されていない操作を行うようにしている。

これらの項目のいずれかに違反しているパッケージを見つけた場合は、パッケージの詳細ページで **[不正使用を報告]** リンクをクリックして、レポートを送信します。

NuGet チームと .NET Foundation は、いつでもこれらの条件を変更する権利を保有することに注意してください。