---
title: "ID プレフィックス予約リファレンス |Microsoft ドキュメント"
author: diverdan92
ms.author: diverdan92
manager: unniravindranathan
ms.date: 10/09/2017
ms.topic: reference
ms.prod: nuget
ms.technology: 
description: "パッケージ ID プレフィックス予約機能の説明、作成者ガイドです。"
keywords: "NuGet パッケージ ID、プレフィックス、予約"
ms.reviewer:
- ananguar
- karann-msft
- unniravindranathan
ms.openlocfilehash: adea51fdd435b36e236028ad51d9f26969d15a09
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="package-id-prefix-reservation"></a><span data-ttu-id="ce061-104">パッケージ ID のプレフィックスの予約</span><span class="sxs-lookup"><span data-stu-id="ce061-104">Package ID prefix reservation</span></span>

<span data-ttu-id="ce061-105">パッケージの所有者は、予約し、ID のプレフィックスを予約して自身の id を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ce061-105">Package owners are can reserve and protect their identity by reserving ID prefixes.</span></span> <span data-ttu-id="ce061-106">パッケージ使用者が追加情報をパッケージの使用時に消費しているか、パッケージは、識別プロパティの不正な提供されます。</span><span class="sxs-lookup"><span data-stu-id="ce061-106">Package consumers are provided with additional information when consuming packages that the package they are consuming are not deceptive in their identifying properties.</span></span> 

<span data-ttu-id="ce061-107">[nuget.org](https://www.nuget.org/)し、パッケージには予約済み ID が一致する限り、予約済みのパッケージ ID のプレフィックスの所有者から送信されたパッケージの名前付けパターンのプレフィックスの Visual Studio 2017 15.4 またはそれ以降のバージョンが視覚インジケータを表示します。</span><span class="sxs-lookup"><span data-stu-id="ce061-107">[nuget.org](https://www.nuget.org/) and Visual Studio 2017 version 15.4 or later show a visual indicator for packages that are submitted by owners with a reserved package ID prefix, as long as the package matches the reserved ID prefix naming pattern.</span></span> <span data-ttu-id="ce061-108">下方向へ ID プレフィックス予約任せます、ID のプレフィックスの所有者を適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce061-108">The below reference explains what the ID prefix reservation entails, and how an owner can apply for an ID prefix.</span></span>

## <a name="id-prefix-reservation-details"></a><span data-ttu-id="ce061-109">ID プレフィックス予約の詳細</span><span class="sxs-lookup"><span data-stu-id="ce061-109">ID prefix reservation details</span></span>

<span data-ttu-id="ce061-110">パッケージ ID のプレフィックスは予約されていますがと、にいくつかの処理が行われます、 [nuget.org](https://www.nuget.org/)ギャラリーも Visual Studio と同様にします。</span><span class="sxs-lookup"><span data-stu-id="ce061-110">When a package ID prefix is reserved, several things happen on the [nuget.org](https://www.nuget.org/) gallery, as well as in Visual Studio.</span></span> <span data-ttu-id="ce061-111">さらに、'public' として、複数の所有者にプレフィックスのサブセットを委任するプレフィックスを設定するなど、ID プレフィックス予約によってサポートされるシナリオ、上級です。</span><span class="sxs-lookup"><span data-stu-id="ce061-111">In addition, there are advanced scenarios that are supported by ID prefix reservations, such as setting a prefix as 'public', delegating prefix subsets to multiple owners.</span></span>

### <a name="id-prefix-reservation-on-nugetorg"></a><span data-ttu-id="ce061-112">Nuget.org の ID のプレフィックスの予約</span><span class="sxs-lookup"><span data-stu-id="ce061-112">ID prefix reservation on nuget.org</span></span>

<span data-ttu-id="ce061-113">プレフィックスが予約されて[nuget.org](https://www.nuget.org/)次が発生します。</span><span class="sxs-lookup"><span data-stu-id="ce061-113">When a prefix is reserved on [nuget.org](https://www.nuget.org/), the following will happen:</span></span>

1. <span data-ttu-id="ce061-114">プレフィックス予約に関連付けられている所有者または所有者のセットで[nuget.org](https://www.nuget.org/)です。</span><span class="sxs-lookup"><span data-stu-id="ce061-114">A prefix reservation is associated with an owner or set of owners on [nuget.org](https://www.nuget.org/).</span></span>

1. <span data-ttu-id="ce061-115">パッケージを送信するたびに[nuget.org](https://www.nuget.org/) ID のプレフィックスを予約済みの所有者から発生しない限り、予約済み ID のプレフィックスに一致する ID を持つパッケージが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="ce061-115">Whenever a package is submitted to [nuget.org](https://www.nuget.org/) with an ID that matches the reserved ID prefix, the package is rejected unless it originates from the owner(s) that reserved the ID prefix.</span></span>

1. <span data-ttu-id="ce061-116">Visual Studio 2017 バージョン 15.4 以降で、予約済み ID のプレフィックスに一致し、ID のプレフィックスを予約されている所有者に由来するパッケージは視覚的になります[nuget.org](https://www.nuget.org/)パッケージがあることを示す予約済み ID プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="ce061-116">Any package that matches the reserved ID prefix and originates from the owner(s) that reserved the ID prefix will have a visual indicator in Visual Studio 2017 version 15.4 or later, and on [nuget.org](https://www.nuget.org/) indicating that the package is under a reserved ID prefix.</span></span> <span data-ttu-id="ce061-117">これは新しいパッケージの送信と所有者の下にある既存のパッケージの両方に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ce061-117">This is true for both new package submissions as well as existing packages under the owner(s).</span></span> <span data-ttu-id="ce061-118">**注:**単一フィードがパッケージのソースとして選択されている場合にのみ、Visual Studio でのインジケーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce061-118">**Note:** The indicator in Visual Studio appears only if a single feed is selected as the package source.</span></span>

1. <span data-ttu-id="ce061-119">予約済み ID のプレフィックスに一致するすべての既存のパッケージが、*いない*予約済みの所有者によって所有されているプレフィックスは変更されません (、一覧にないことはできませんが、視覚インジケーターが付いていませんも)。</span><span class="sxs-lookup"><span data-stu-id="ce061-119">All previously existing packages that match the reserved ID prefix, but are *not* owned by the owner of the reserved prefix will remain unchanged (they will not be unlisted, but they will also not have the visual indicator).</span></span> <span data-ttu-id="ce061-120">さらに、これらのパッケージの所有者は、パッケージに新しいバージョンを送信できます。</span><span class="sxs-lookup"><span data-stu-id="ce061-120">In addition, owners of these packages will still be able to submit new versions to the package.</span></span>

<span data-ttu-id="ce061-121">これらの変更は、次の条件に基づいており、いくつかの追加制限します。</span><span class="sxs-lookup"><span data-stu-id="ce061-121">These changes are based on the following conditions and impose several additional restrictions:</span></span>

- <span data-ttu-id="ce061-122">パッケージの 1 つだけの所有者には、(複数の所有者を持つパッケージ) 用に表示される視覚インジケータの予約済みのプレフィックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce061-122">Only one owner of a package needs to have the reserved prefix for the visual indicator to appear (for packages with multiple-owners).</span></span>

- <span data-ttu-id="ce061-123">場所 1 つまたは複数の所有者には、予約済みのプレフィックスと、1 つまたは複数の所有者には、予約済みのプレフィックスはありません。 パッケージの 1 つ以上の所有者がある場合、予約済みのプレフィックスを持つ所有者だけは予約されたプレフィックスを持つ他の従属性を削除できます。</span><span class="sxs-lookup"><span data-stu-id="ce061-123">If there is more than one owner of a package where one or more owners has the reserved prefix and one or more owners does not have the reserved prefix, then only the owner(s) with the reserved prefix can remove other owner(s) with a reserved prefix.</span></span> <span data-ttu-id="ce061-124">予約済みのプレフィックスを持たない所有者は、予約済みのプレフィックスを持つ所有者を削除できません。</span><span class="sxs-lookup"><span data-stu-id="ce061-124">The owners who do not have the prefix reserved cannot remove owners with the prefix reserved.</span></span> <span data-ttu-id="ce061-125">ほかの所有者もない予約済みのプレフィックスを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce061-125">They can still remove other owners that also do not have the prefix reserved.</span></span>

- <span data-ttu-id="ce061-126">パッケージが視覚インジケーターを持つ、*常に*視覚インジケーターがある (予約済みのプレフィックスを持つ、少なくとも 1 つその所有者の保証は常に、所有者)</span><span class="sxs-lookup"><span data-stu-id="ce061-126">Once a package has the visual indicator, it should *always* have the visual indicator (guaranteeing that at least one owner with the reserved prefix will always remain an owner)</span></span>

### <a name="advanced-prefix-reservation-scenarios"></a><span data-ttu-id="ce061-127">高度なプレフィックス予約シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce061-127">Advanced prefix reservation scenarios</span></span>

<span data-ttu-id="ce061-128">Subprefix 委任、および public としてマーキング プレフィックスを含めて、次に示すいくつかのより高度なプレフィックス予約シナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="ce061-128">There are several more advanced prefix reservation scenarios described below, including subprefix delegation, and marking prefixes as public.</span></span> <span data-ttu-id="ce061-129">可能なプレフィックスのより高度な予約を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ce061-129">Below are the more advanced prefix reservations that can be made.</span></span> 

- <span data-ttu-id="ce061-130">プレフィックス予約中に、所有者は、その他の所有者にプレフィックスのサブセットの委任 (プレフィックス) を要求できます。</span><span class="sxs-lookup"><span data-stu-id="ce061-130">During prefix reservation, the owner can request delegation of prefix subsets (or the prefix) to other owners.</span></span> <span data-ttu-id="ce061-131">たとえば場合、'[Microsoft](https://www.nuget.org/profiles/microsoft)'を所有している' Microsoft\*'、が、'[aspnet](https://www.nuget.org/profiles/aspnet)'に予約する必要がある' Microsoft.AspNet。\*'、'[Microsoft](https://www.nuget.org/profiles/microsoft)' ことができます。デリゲートを ' Microsoft.AspNet です。\*' に、 [aspnet](https://www.nuget.org/profiles/aspnet)アカウント。</span><span class="sxs-lookup"><span data-stu-id="ce061-131">For example, if '[Microsoft](https://www.nuget.org/profiles/microsoft)' owns 'Microsoft.\*', but '[aspnet](https://www.nuget.org/profiles/aspnet)' wants to reserve 'Microsoft.AspNet.\*', '[Microsoft](https://www.nuget.org/profiles/microsoft)' can choose to delegate 'Microsoft.AspNet.\*' to the [aspnet](https://www.nuget.org/profiles/aspnet) account.</span></span>

- <span data-ttu-id="ce061-132">プレフィックス予約中に、プレフィックスを公開して、所有者を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ce061-132">During prefix reservation, the owner can choose to make a prefix public.</span></span> <span data-ttu-id="ce061-133">これは許可することを示すこと、パッケージは、予約済みのプレフィックスから発生しますが、視覚インジケータ**いない**任意の所有者のプレフィックスに将来のパッケージの送信をブロックします。</span><span class="sxs-lookup"><span data-stu-id="ce061-133">This will still give them the visual indicator showing that the package originates from a reserved prefix, but it will **not** block future package submissions on the prefix for any owner.</span></span> <span data-ttu-id="ce061-134">これは、オープン ソース プロジェクトは、多くの共同作成者の場合に便利です - 上部または core の投稿者で予約されたプレフィックスを持つことができますが、すべてのコントリビューターに開いていることができます。</span><span class="sxs-lookup"><span data-stu-id="ce061-134">This is useful for open source projects with many contributors - the top or core contributors can have the prefix reserved, but it can still be open to all contributors.</span></span> 

### <a name="prefix-reservation-visual-indicator"></a><span data-ttu-id="ce061-135">プレフィックスの予約の視覚インジケーター</span><span class="sxs-lookup"><span data-stu-id="ce061-135">Prefix reservation visual indicator</span></span>

<span data-ttu-id="ce061-136">パッケージ ソース予約済みのプレフィックスがある場合と表示されますでの視覚インジケーターの下、 [nuget.org](https://www.nuget.org/)ギャラリーと Visual Studio 2017 15.4 またはそれ以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="ce061-136">When a package comes from a reserved prefix, you will see the below visual indicators on the [nuget.org](https://www.nuget.org/) gallery and in Visual Studio 2017 version 15.4 or later:</span></span>

<span data-ttu-id="ce061-137">**nuget.org ギャラリー**
![nuget.org ギャラリー](media/nuget-gallery-reserved-prefix.png)</span><span class="sxs-lookup"><span data-stu-id="ce061-137">**nuget.org Gallery**
![nuget.org Gallery](media/nuget-gallery-reserved-prefix.png)</span></span>

<span data-ttu-id="ce061-138">**Visual Studio**
![Visual Studio](media/visual-studio-reserved-prefix.png)</span><span class="sxs-lookup"><span data-stu-id="ce061-138">**Visual Studio**
![Visual Studio](media/visual-studio-reserved-prefix.png)</span></span>

## <a name="id-prefix-reservation-application-process"></a><span data-ttu-id="ce061-139">ID プレフィックスの予約アプリケーション プロセス</span><span class="sxs-lookup"><span data-stu-id="ce061-139">ID prefix reservation application process</span></span>

1. <span data-ttu-id="ce061-140">確認して、受け入れ[プレフィックス ID 予約の条件](#id-prefix-reservation-criteria)です。</span><span class="sxs-lookup"><span data-stu-id="ce061-140">Review the acceptance [criteria for prefix ID reservation](#id-prefix-reservation-criteria).</span></span>

1. <span data-ttu-id="ce061-141">他にも、予約する名前空間を決定[プレフィックス予約シナリオを高度な](#advanced-prefix-reservation-scenarios)が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce061-141">Determine the namespaces you want to reserve, in addition to any [advanced prefix reservation scenarios](#advanced-prefix-reservation-scenarios) you may require.</span></span>

1. <span data-ttu-id="ce061-142">電子メールを送信[ account@nuget.org ](mailto:account@nuget.org)オーナーを使用して表示名で[nuget.org](https://www.nuget.org/)、要求している、予約済みのプレフィックスとします。</span><span class="sxs-lookup"><span data-stu-id="ce061-142">Send a mail to [account@nuget.org](mailto:account@nuget.org) with the owner display name on [nuget.org](https://www.nuget.org/), as well as any reserved prefixes you are requesting.</span></span> <span data-ttu-id="ce061-143">複数の所有者にプレフィックスのサブセットを委任する場合は、すべての所有者の表示名を説明し、サブセットのプレフィックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce061-143">If you are delegating prefix subsets to multiple owners, make sure you mention all owner display names and prefix subsets.</span></span>

<span data-ttu-id="ce061-144">アプリケーションが送信されると後の受理または拒否の原因となった条件) (の拒否が通知されます。</span><span class="sxs-lookup"><span data-stu-id="ce061-144">After the application is submitted, you will be notified of acceptance or rejection (with the criteria that caused rejection).</span></span> <span data-ttu-id="ce061-145">所有者の身元を識別する追加の質問を投稿する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce061-145">We may need to ask additional identifying questions to confirm owner identity.</span></span>

### <a name="id-prefix-reservation-criteria"></a><span data-ttu-id="ce061-146">ID プレフィックス予約条件</span><span class="sxs-lookup"><span data-stu-id="ce061-146">ID prefix reservation criteria</span></span>

<span data-ttu-id="ce061-147">ID プレフィックスの予約のすべてのアプリケーションを表示するときに、 [nuget.org](https://www.nuget.org/)チームに対してアプリケーションを評価する、条件の下。</span><span class="sxs-lookup"><span data-stu-id="ce061-147">When reviewing any application for ID prefix reservation, the [nuget.org](https://www.nuget.org/) team will evaluate the application against the below criteria.</span></span> <span data-ttu-id="ce061-148">プレフィックスを予約に満たす必要がないすべての条件が必要ですが、(後で指定された説明) が満たされている条件の大幅な証拠が存在しない場合、アプリケーションが拒否された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce061-148">Not all criteria needs to be met for a prefix to be reserved, but the application may be denied if there is not substantial evidence of the criteria being met (with an explanation given):</span></span>

1. <span data-ttu-id="ce061-149">パッケージ ID プレフィックス適切かつ明確に識別パッケージの所有者ですか。</span><span class="sxs-lookup"><span data-stu-id="ce061-149">Does the package ID prefix properly and clearly identify the package owner?</span></span>

1. <span data-ttu-id="ce061-150">パッケージ ID のプレフィックスの所有者によって多数の送信済みのパッケージとは</span><span class="sxs-lookup"><span data-stu-id="ce061-150">Are a significant number of the packages that have already been submitted by the owner under the package ID prefix?</span></span>

1. <span data-ttu-id="ce061-151">パッケージ ID のプレフィックスを任意の所有者または組織に属する必要がありますいないを共通のものですか。</span><span class="sxs-lookup"><span data-stu-id="ce061-151">Is the package ID prefix something common that should not belong to any individual owner or organization?</span></span>

1. <span data-ttu-id="ce061-152">*いない*あいまいさとコミュニティの混乱が発生するパッケージ ID のプレフィックスを予約しますか?</span><span class="sxs-lookup"><span data-stu-id="ce061-152">Would *not* reserving the package ID prefix cause ambiguity and confusion for the community?</span></span>

1. <span data-ttu-id="ce061-153">パッケージ ID プレフィックス、はっきりと一貫性のある (特に、パッケージの作成者) に一致するパッケージの識別プロパティとは</span><span class="sxs-lookup"><span data-stu-id="ce061-153">Are the identifying properties of the packages that match the package ID prefix clear and consistent (especially the package author)?</span></span>

## <a name="third-party-feed-provider-scenarios"></a><span data-ttu-id="ce061-154">サード パーティ製のフィード プロバイダー シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce061-154">Third party feed provider scenarios</span></span>

<span data-ttu-id="ce061-155">サード パーティのフィード プロバイダーがプレフィックスの予約を提供する独自のサービスを実装する目的の場合は、NuGet V3 で search サービスのプロバイダーのフィードを変更してようにを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ce061-155">If a third party feed provider is interested in implementing their own service to provide prefix reservations, you can do so by modifying the search service in the NuGet V3 feed providers.</span></span> <span data-ttu-id="ce061-156">フィードの search サービスの追加は、追加する、*検証*V3 フィードを次の例のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ce061-156">The addition in the feed search service is to add the *verified* property, with examples for the V3 feeds below.</span></span> <span data-ttu-id="ce061-157">NuGet クライアントは、フィード、V2 で追加されたプロパティをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ce061-157">The NuGet client will not support the added property in the V2 feed.</span></span>

<span data-ttu-id="ce061-158">詳細については、次を参照してください。、 [API の search サービスに関するドキュメント](../api/search-query-service-resource.md)です。</span><span class="sxs-lookup"><span data-stu-id="ce061-158">For more information, see the [documentation about the API's search service](../api/search-query-service-resource.md).</span></span>