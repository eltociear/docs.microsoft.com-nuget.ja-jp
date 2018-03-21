---
title: "Visual Studio テンプレートの NuGet パッケージ | Microsoft Docs"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 01/03/2018
ms.topic: article
ms.prod: nuget
ms.technology: 
description: "NuGet パッケージを Visual Studio プロジェクトと項目テンプレートの一部として含める方法について説明します。"
keywords: "Visual Studio の NuGet、Visual Studio プロジェクト テンプレート、Visual Studio 項目テンプレート、プロジェクト テンプレートのパッケージ、項目テンプレートのパッケージ"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 65b914e1fa59c28615f195b470880a12bf80efbb
ms.sourcegitcommit: 4651b16a3a08f6711669fc4577f5d63b600f8f58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2018
---
# <a name="packages-in-visual-studio-templates"></a><span data-ttu-id="52459-104">Visual Studio テンプレートのパッケージ</span><span class="sxs-lookup"><span data-stu-id="52459-104">Packages in Visual Studio templates</span></span>

<span data-ttu-id="52459-105">Visual Studio プロジェクト テンプレートと項目テンプレートは多くの場合、プロジェクトまたは項目が作成されるときに特定のパッケージがインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52459-105">Visual Studio project and item templates often need to ensure that certain packages are installed when a project or item is created.</span></span> <span data-ttu-id="52459-106">たとえば、ASP.NET MVC 3 テンプレートは、jQuery、Modernizr、およびその他のパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="52459-106">For example, the ASP.NET MVC 3 template installs jQuery, Modernizr, and other packages.</span></span>

<span data-ttu-id="52459-107">これをサポートするため、テンプレートの作成者は、NuGet に個々のライブラリではなく、必要なパッケージをインストールするように指示できます。</span><span class="sxs-lookup"><span data-stu-id="52459-107">To support this, template authors can instruct NuGet to install the necessary packages, rather than individual libraries.</span></span> <span data-ttu-id="52459-108">こうすることで、開発者が後から好きなときにこれらのパッケージを簡単に更新できます。</span><span class="sxs-lookup"><span data-stu-id="52459-108">Developers can then easily update those packages at any later time.</span></span>

<span data-ttu-id="52459-109">テンプレートそのものを作成する詳細については、「[方法 : プロジェクト テンプレートを作成する](/visualstudio/ide/how-to-create-project-templates)」または「[Creating Custom Project and Item Templates](/visualstudio/extensibility/creating-custom-project-and-item-templates)」(カスタムのプロジェクトおよび項目テンプレートを作成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52459-109">To learn more about authoring templates themselves, refer to [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates) or [Creating Custom Project and Item Templates](/visualstudio/extensibility/creating-custom-project-and-item-templates).</span></span>

<span data-ttu-id="52459-110">このセクションの残りの部分では、NuGet パッケージを正しく含めるテンプレートを作成するときに実行する具体的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="52459-110">The remainder of this section describes the specific steps to take when authoring a template to properly include NuGet packages.</span></span>

- [<span data-ttu-id="52459-111">パッケージをテンプレートに追加する</span><span class="sxs-lookup"><span data-stu-id="52459-111">Adding packages to a template</span></span>](#adding-packages-to-a-template)
- [<span data-ttu-id="52459-112">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="52459-112">Best practices</span></span>](#best-practices)

<span data-ttu-id="52459-113">例については、[NuGetInVsTemplates のサンプル](https://bitbucket.org/marcind/nugetinvstemplates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52459-113">For an example, see the [NuGetInVsTemplates sample](https://bitbucket.org/marcind/nugetinvstemplates).</span></span>

## <a name="adding-packages-to-a-template"></a><span data-ttu-id="52459-114">パッケージをテンプレートに追加する</span><span class="sxs-lookup"><span data-stu-id="52459-114">Adding packages to a template</span></span>

<span data-ttu-id="52459-115">テンプレートがインスタンス化されるときに、インストールするパッケージのリストとともにこれらのパッケージがある場所に関する情報を読み込むため、[テンプレート ウィザード](/visualstudio/extensibility/how-to-use-wizards-with-project-templates)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="52459-115">When a template is instantiated, a [template wizard](/visualstudio/extensibility/how-to-use-wizards-with-project-templates) is invoked to load the list of packages to install along with information about where to find those packages.</span></span> <span data-ttu-id="52459-116">パッケージは、VSIX に埋め込んだり、テンプレートに埋め込むことができます。または、レジストリ キーを使用してファイル パスを参照する場合は、ローカル ハード ドライブ上に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="52459-116">Packages can be embedded in the VSIX, embedded in the template, or located on the local hard drive in which case you use a registry key to reference the file path.</span></span> <span data-ttu-id="52459-117">これらの場所の詳細については、このセクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="52459-117">Details on these locations are given later in this section.</span></span>

<span data-ttu-id="52459-118">[テンプレート ウィザード](/visualstudio/extensibility/how-to-use-wizards-with-project-templates)を使用して、プレインストールされたパッケージが機能します。</span><span class="sxs-lookup"><span data-stu-id="52459-118">Preinstalled packages work using [template wizards](/visualstudio/extensibility/how-to-use-wizards-with-project-templates).</span></span> <span data-ttu-id="52459-119">テンプレートがインスタンス化されるときに、特殊なウィザードが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="52459-119">A special wizard gets invoked when the template gets instantiated.</span></span> <span data-ttu-id="52459-120">このウィザードはインストールする必要があるパッケージのリストを読み込み、その情報を適切な NuGet API に渡します。</span><span class="sxs-lookup"><span data-stu-id="52459-120">The wizard loads the list of packages that need to be installed and passes that information to the appropriate NuGet APIs.</span></span>

<span data-ttu-id="52459-121">テンプレートにパッケージを含める手順:</span><span class="sxs-lookup"><span data-stu-id="52459-121">Steps to include packages in a template:</span></span>

1. <span data-ttu-id="52459-122">`vstemplate` ファイルに、[`WizardExtension`](/visualstudio/extensibility/wizardextension-element-visual-studio-templates) 要素を追加して、NuGet テンプレート ウィザードへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="52459-122">In your `vstemplate` file, add a reference to the NuGet template wizard by adding a [`WizardExtension`](/visualstudio/extensibility/wizardextension-element-visual-studio-templates) element:</span></span>

    ```xml
    <WizardExtension>
        <Assembly>NuGet.VisualStudio.Interop, Version=1.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a</Assembly>
        <FullClassName>NuGet.VisualStudio.TemplateWizard</FullClassName>
    </WizardExtension>
    ```

    <span data-ttu-id="52459-123">`NuGet.VisualStudio.Interop.dll` は、`TemplateWizard` クラスのみを含むアセンブリで、`NuGet.VisualStudio.dll` で実際の実装を呼び出す単純なラッパーです。</span><span class="sxs-lookup"><span data-stu-id="52459-123">`NuGet.VisualStudio.Interop.dll` is an assembly that contains only the `TemplateWizard` class, which is a simple wrapper that calls into the actual implementation in `NuGet.VisualStudio.dll`.</span></span> <span data-ttu-id="52459-124">プロジェクト/項目テンプレートが新しいバージョンの NuGet で引き続き機能するように、アセンブリのバージョンは変わりません。</span><span class="sxs-lookup"><span data-stu-id="52459-124">The assembly version will never change so that project/item templates continue to work with new versions of NuGet.</span></span>

1. <span data-ttu-id="52459-125">プロジェクトにインストールするパッケージのリストを追加します。</span><span class="sxs-lookup"><span data-stu-id="52459-125">Add the list of packages to install in the project:</span></span>

    ```xml
    <WizardData>
        <packages>
            <package id="jQuery" version="1.6.2" />
        </packages>
    </WizardData>
    ```

    <span data-ttu-id="52459-126">*(NuGet 2.2.1 以降)* 複数のパッケージ ソースをサポートするため、ウィザードは複数の `<package>` 要素をサポートします。</span><span class="sxs-lookup"><span data-stu-id="52459-126">*(NuGet 2.2.1+)* The wizard supports multiple `<package>` elements to support multiple package sources.</span></span> <span data-ttu-id="52459-127">`id` と `version` の両方の属性が必要です。つまり、新しいバージョンが利用可能な場合でも、パッケージの特定のバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="52459-127">Both the `id` and `version` attributes are required, meaning that specific version of a package will be installed even if a newer version is available.</span></span> <span data-ttu-id="52459-128">これによりパッケージの更新によりテンプレートが破損されるのを防ぎ、テンプレートを使用する開発者にパッケージの更新の選択を任せます。</span><span class="sxs-lookup"><span data-stu-id="52459-128">This prevents package updates from breaking the template, leaving the choice to update the package to the developer using the template.</span></span>

1. <span data-ttu-id="52459-129">次のセクションで説明するように、NuGet がパッケージを検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="52459-129">Specify the repository where NuGet can find the packages as described in the following sections.</span></span>

### <a name="vsix-package-repository"></a><span data-ttu-id="52459-130">VSIX パッケージ リポジトリ</span><span class="sxs-lookup"><span data-stu-id="52459-130">VSIX package repository</span></span>

<span data-ttu-id="52459-131">Visual Studio プロジェクト/項目テンプレートの推奨される配置方法は、[VSIX 拡張機能](/visualstudio/extensibility/shipping-visual-studio-extensions)です。これを使用すると、複数のプロジェクト/項目テンプレートをまとめてパッケージ化し、開発者が VS 拡張機能マネージャーまたは Visual Studio ギャラリーを使用して、テンプレートを簡単に検出することができるからです。</span><span class="sxs-lookup"><span data-stu-id="52459-131">The recommended deployment approach for Visual Studio project/item templates is a [VSIX extension](/visualstudio/extensibility/shipping-visual-studio-extensions) because it allows you to package multiple project/item templates together and allows developers to easily discover your templates using the VS Extension Manager or the Visual Studio Gallery.</span></span> <span data-ttu-id="52459-132">拡張機能への更新プログラムも、[Visual Studio 拡張機能マネージャーの自動更新メカニズム](/visualstudio/extensibility/how-to-update-a-visual-studio-extension)を使用して簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="52459-132">Updates to the extension are also easy to deploy using the [Visual Studio Extension Manager automatic update mechanism](/visualstudio/extensibility/how-to-update-a-visual-studio-extension).</span></span>

<span data-ttu-id="52459-133">VSIX 自体は、テンプレートで必要となるパッケージのソースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="52459-133">The VSIX itself can serve as the source for packages required by the template:</span></span>

1. <span data-ttu-id="52459-134">`.vstemplate` ファイルで次のように `<packages>` 要素を変更します。</span><span class="sxs-lookup"><span data-stu-id="52459-134">Modify the `<packages>` element in the `.vstemplate` file as follows:</span></span>

    ```xml
    <packages repository="extension" repositoryId="MyTemplateContainerExtensionId">
        <!-- ... -->
    </packages>
    ```

    <span data-ttu-id="52459-135">`repository` 属性がリポジトリの種類を `extension` として指定するのに対し、`repositoryId` は VSIX 自体の一意の識別子です (これが、拡張機能の `vsixmanifest` ファイル内の `ID` 属性の値です。「[VSIX 拡張機能スキーマ 2.0 リファレンス](/visualstudio/extensibility/vsix-extension-schema-2-0-reference)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="52459-135">The `repository` attribute specifies the type of repository as `extension` while `repositoryId` is the unique identifier of the VSIX itself (This is the value of the `ID` attribute in the extension’s `vsixmanifest` file, see [VSIX Extension Schema 2.0 Reference](/visualstudio/extensibility/vsix-extension-schema-2-0-reference)).</span></span>

1. <span data-ttu-id="52459-136">`nupkg` ファイルを VSIX 内の `Packages` というフォルダー内に配置します。</span><span class="sxs-lookup"><span data-stu-id="52459-136">Place your `nupkg` files in a folder called `Packages` within the VSIX.</span></span>

1. <span data-ttu-id="52459-137">必要なパッケージ ファイルを `<Asset>` として `vsixmanifest` ファイルに追加します (「[VSIX 拡張機能スキーマ 2.0 リファレンス](/visualstudio/extensibility/vsix-extension-schema-2-0-reference)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="52459-137">Add the necessary package files as `<Asset>` in your `vsixmanifest` file (see [VSIX Extension Schema 2.0 Reference](/visualstudio/extensibility/vsix-extension-schema-2-0-reference)):</span></span>

    ```xml
    <Asset Type="Moq.4.0.10827.nupkg" d:Source="File" Path="Packages\Moq.4.0.10827.nupkg" d:VsixSubPath="Packages" />
    ```

1. <span data-ttu-id="52459-138">パッケージは、プロジェクト テンプレートと同じ VSIX に配布することも、別の VSIX に配置する (自分のシナリオにとってその方が合理的な場合) こともできます。</span><span class="sxs-lookup"><span data-stu-id="52459-138">Note that you can deliver packages in the same VSIX as your project templates or you can put them in a separate VSIX if that makes more sense for your scenario.</span></span> <span data-ttu-id="52459-139">ただし、制御できない VSIX を参照しないでください。その拡張機能への変更によりテンプレートが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="52459-139">However, do not reference any VSIX over which you do not have control, because changes to that extension could break your template.</span></span>

### <a name="template-package-repository"></a><span data-ttu-id="52459-140">テンプレート パッケージ リポジトリ</span><span class="sxs-lookup"><span data-stu-id="52459-140">Template package repository</span></span>

<span data-ttu-id="52459-141">1 つのプロジェクト/項目テンプレートのみを配布して、複数のテンプレートをまとめてパッケージ化する必要がない場合は、プロジェクト/項目テンプレートの ZIP ファイルにパッケージを直接含める、よりシンプルですがより制限された方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="52459-141">If you are distributing only a single project/item template and do not need to package multiple templates together, you can use a simpler but more limited approach that includes packages directly in the project/item template ZIP file:</span></span>

1. <span data-ttu-id="52459-142">`.vstemplate` ファイルで次のように `<packages>` 要素を変更します。</span><span class="sxs-lookup"><span data-stu-id="52459-142">Modify the `<packages>` element in the `.vstemplate` file as follows:</span></span>

    ```xml
    <packages repository="template"">
        <!-- ... -->
    </packages>
    ```

    <span data-ttu-id="52459-143">`repository` 属性には値 `template` があり、`repositoryId` 属性は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="52459-143">The `repository` attribute has the value `template` and the `repositoryId` attribute is not required.</span></span>

1. <span data-ttu-id="52459-144">プロジェクト/項目テンプレートの ZIP ファイルのルート フォルダーにパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="52459-144">Place packages in the root folder of the project/item template ZIP file.</span></span>

<span data-ttu-id="52459-145">複数のテンプレートを含む VSIX でこの方法を使用すると、テンプレートで 1 つ以上のパッケージが共通するときに、不要な肥大化につながることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="52459-145">Note that using this approach in a VSIX that contains multiple templates leads to unnecessary bloat when one or more packages are common to the templates.</span></span> <span data-ttu-id="52459-146">このような場合、前のセクションで説明したように、[VSIX をリポジトリとして](#vsix-package-repository)使用します。</span><span class="sxs-lookup"><span data-stu-id="52459-146">In such cases, use the [VSIX as the repository](#vsix-package-repository) as described in the previous section.</span></span>

### <a name="registry-specified-folder-path"></a><span data-ttu-id="52459-147">レジストリで指定されたフォルダーのパス</span><span class="sxs-lookup"><span data-stu-id="52459-147">Registry-specified folder path</span></span>

<span data-ttu-id="52459-148">MSI を使用してインストールされる SDK は、開発者のマシンに直接 NuGet パッケージをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="52459-148">SDKs that are installed using an MSI can install NuGet packages directly on the developer's machine.</span></span> <span data-ttu-id="52459-149">これにより、プロジェクト テンプレートまたは項目テンプレートを使用するときに、パッケージを抽出することなく、すぐに利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="52459-149">This makes them immediately available when a project or item template is used, rather than having to extract them during that time.</span></span> <span data-ttu-id="52459-150">ASP.NET テンプレートは、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="52459-150">ASP.NET templates use this approach.</span></span>

1. <span data-ttu-id="52459-151">MSI にパッケージをマシンにインストールさせます。</span><span class="sxs-lookup"><span data-stu-id="52459-151">Have the MSI install packages to the machine.</span></span> <span data-ttu-id="52459-152">`.nupkg` ファイルだけをインストールすることも、ファイルと共に展開されたコンテンツをインストールして、テンプレートを使用するときに追加の手順を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="52459-152">You can install only the `.nupkg` files, or you can install those along with the expanded contents, which saves an additional step when the template is used.</span></span> <span data-ttu-id="52459-153">この場合、`.nupkg` ファイルがルート フォルダーにあり、各パッケージが ID/バージョンのペアが名前になったサブフォルダーを持つ、NuGet の標準のフォルダー構造に従います。</span><span class="sxs-lookup"><span data-stu-id="52459-153">In this case, follow NuGet's standard folder structure wherein the `.nupkg` files are in the root folder, and then each package has a subfolder with the id/version pair as the subfolder name.</span></span>

1. <span data-ttu-id="52459-154">パッケージの場所を識別するレジストリ キーを記述します。</span><span class="sxs-lookup"><span data-stu-id="52459-154">Write a registry key to identify the package location:</span></span>

    - <span data-ttu-id="52459-155">キーの場所: マシン全体の `HKEY_LOCAL_MACHINE\SOFTWARE[\Wow6432Node]\NuGet\Repository`、またはユーザーごとにインストールされるテンプレートとパッケージの場合は、代わりに `HKEY_CURRENT_USER\SOFTWARE\NuGet\Repository` を使用します。</span><span class="sxs-lookup"><span data-stu-id="52459-155">Key location: Either the machine-wide `HKEY_LOCAL_MACHINE\SOFTWARE[\Wow6432Node]\NuGet\Repository` or if it's per-user installed templates and packages, alternatively use `HKEY_CURRENT_USER\SOFTWARE\NuGet\Repository`</span></span>
    - <span data-ttu-id="52459-156">キー名: 自分にとって一意の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="52459-156">Key name: use a name that's unique to you.</span></span> <span data-ttu-id="52459-157">たとえば、VS 2012 の ASP.NET MVC 4 テンプレートでは、`AspNetMvc4VS11` を使用します。</span><span class="sxs-lookup"><span data-stu-id="52459-157">For example, the ASP.NET MVC 4 templates for VS 2012 use `AspNetMvc4VS11`.</span></span>
    - <span data-ttu-id="52459-158">値: パッケージ フォルダーへの完全パス。</span><span class="sxs-lookup"><span data-stu-id="52459-158">Values: the full path to the packages folder.</span></span>

1. <span data-ttu-id="52459-159">`.vstemplate` ファイル内の `<packages>` 要素に、属性 `repository="registry"` を追加し、`keyName` 属性でレジストリ キーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="52459-159">In the `<packages>` element in the `.vstemplate` file, add the attribute `repository="registry"` and specify your registry key name in the `keyName` attribute.</span></span>

    - <span data-ttu-id="52459-160">解凍前のパッケージがある場合は、`isPreunzipped="true"` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="52459-160">If you have pre-unzipped your packages, use the `isPreunzipped="true"` attribute.</span></span>
    - <span data-ttu-id="52459-161">*(NuGet 3.2 以降)* パッケージのインストール終了時にデザイン時ビルドを強制する場合は、`forceDesignTimeBuild="true"` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="52459-161">*(NuGet 3.2+)* If you want to force a design-time build at the end of package installation, add the `forceDesignTimeBuild="true"` attribute.</span></span>
    - <span data-ttu-id="52459-162">テンプレート自体には既に必要な参照が含まれているため、最適化として `skipAssemblyReferences="true"` を追加します。</span><span class="sxs-lookup"><span data-stu-id="52459-162">As an optimization, add `skipAssemblyReferences="true"` because the template itself already includes the necessary references.</span></span>

        ```xml
        <packages repository="registry" keyName="AspNetMvc4VS11" isPreunzipped="true">
            <package id="EntityFramework" version="5.0.0" skipAssemblyReferences="true" />
            <-- ... -->
        </packages>
        ```

## <a name="best-practices"></a><span data-ttu-id="52459-163">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="52459-163">Best Practices</span></span>

1. <span data-ttu-id="52459-164">NuGet VSIX で依存関係を宣言するため、VSIX マニフェストに依存関係への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="52459-164">Declare a dependency on the NuGet VSIX by adding a reference to it in your VSIX manifest:</span></span>

    ```xml
    <Reference Id="NuPackToolsVsix.Microsoft.67e54e40-0ae3-42c5-a949-fddf5739e7a5" MinVersion="1.7.30402.9028">
        <Name>NuGet Package Manager</Name>
        <MoreInfoUrl>http://docs.microsoft.com/nuget/</MoreInfoUrl>
    </Reference>
    <!-- ... -->
    ```

1. <span data-ttu-id="52459-165">`.vstemplate` ファイルに [`<PromptForSaveOnCreation>true</PromptForSaveOnCreation>`](/visualstudio/extensibility/promptforsaveoncreation-element-visual-studio-templates) を含めることにより、作成時にプロジェクト/項目テンプレートが保存されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="52459-165">Require project/item templates to be saved on creation by including [`<PromptForSaveOnCreation>true</PromptForSaveOnCreation>`](/visualstudio/extensibility/promptforsaveoncreation-element-visual-studio-templates) in the `.vstemplate` file.</span></span>

1. <span data-ttu-id="52459-166">テンプレートに、`packages.config` ファイルは含まれません。また、NuGet パッケージがインストールされるときに追加される参照やコンテンツも含まれません。</span><span class="sxs-lookup"><span data-stu-id="52459-166">Templates do not include a `packages.config` file, and do not include or any references or content that would be added when NuGet packages are installed.</span></span>