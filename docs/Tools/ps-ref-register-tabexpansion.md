---
title: "NuGet のレジスタ TabExpansion PowerShell リファレンス |Microsoft ドキュメント"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 12/07/2017
ms.topic: reference
ms.prod: nuget
ms.technology: 
ms.assetid: 8314ec69-ee8c-4933-84ef-e6d8a412d268
description: "Visual Studio で NuGet パッケージ マネージャー コンソールでのレジスタ TabExpansion PowerShell コマンドのリファレンスです。"
keywords: "NuGet パッケージ マネージャー コンソールで、NuGet Powershell コマンドでは、NuGet Powershell リファレンス、レジスタ TabExpansion"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 498b8638c81b800e5f20f7604b36e6af76da0283
ms.sourcegitcommit: d0ba99bfe019b779b75731bafdca8a37e35ef0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2017
---
# <a name="register-tabexpansion-package-manager-console-in-visual-studio"></a>レジスタ TabExpansion (Visual Studio でパッケージ マネージャー コンソール)

*内でのみ使用可能な[NuGet Package Manager Console](Package-Manager-Console.md) Windows 上の Visual Studio でします。*

対象のパラメーターに使用できるオプションとして、展開可能な値が表示されます タブは、コマンドを入力するときに使用する場合など、指定されたコマンドのパラメーターにタブ拡張を登録します。 コマンドの前、展開が上書きされます。

## <a name="syntax"></a>構文

```ps
Register-TabExpansion [-Name] <String> [-Definition] <Object> [<CommonParameters>]
```

## <a name="parameters"></a>パラメーター

| パラメーター | 説明 |
| --- | --- |
| 名前 | (必須)拡張を登録するためにコマンド。 -Name スイッチ自体は省略可能です。 |
| 定義 | (必須)構文では、引数を表すオブジェクトです。`@{'<parameter>' = {'<value1>', '<value2>', ...}}`場所`<parameter>`を変更するパラメーターとそれぞれの名前を指定`<value>`固有の展開を提供します。 両方単一引用符と二重引用符が受け入れられます。 |

これらのパラメーターのいずれもには、パイプラインの入力またはワイルドカード文字がそのまま使用します。

## <a name="common-parameters"></a>共通パラメーター

`Register-TabExpansion`次のサポート[一般的な PowerShell パラメーター](http://go.microsoft.com/fwlink/?LinkID=113216): デバッグ、エラー アクション、ErrorVariable、OutBuffer、OutVariable、PipelineVariable、Verbose、WarningAction、WarningVariable、します。

## <a name="examples"></a>例

次の 3 つのプロジェクト名 EventManager、ユーティリティ、および SpecialParser を含むソリューションを検討してください。 開発者が頻繁に使用、`Update-Package`これらの各プロジェクトに異なるタイミングでコマンド。 彼女は都合のよいことが、`Update-Package`コマンドでは、オートコンプリートの展開の提供、`-ProjectName`引数ため、彼女はプロジェクト名をその都度入力する必要はありませんの。 

次のコマンドがの拡張として次に、これら 3 つのプロジェクトの名前を登録、`-ProjectName`パラメーター。

```ps
Register-TabExpansion Update-Package @{'ProjectName' = {'EventManager', 'Utilities', 'SpecialParser'}}    
```

開発者は入力できますし、 `Update-Package -ProjectName `、Tab キーを押して、オートコンプリートの選択肢として提示の展開を参照してください。

![レジスタ TabExpansion の使用例](media/Register-TabExpansion-Example.png)