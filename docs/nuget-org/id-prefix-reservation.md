---
title: ID プレフィックスの予約
description: パッケージ ID プレフィックスの予約機能の説明と作成者ガイド。
author: diverdan92
ms.author: diverdan92
ms.date: 10/09/2017
ms.topic: reference
ms.reviewer: ananguar
ms.openlocfilehash: 94036e3ca7c65e6878f24a5a8514cbb0d8816d9c
ms.sourcegitcommit: b6810860b77b2d50aab031040b047c20a333aca3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67427227"
---
# <a name="package-id-prefix-reservation"></a><span data-ttu-id="05d51-103">パッケージ ID プレフィックスの予約</span><span class="sxs-lookup"><span data-stu-id="05d51-103">Package ID prefix reservation</span></span>

<span data-ttu-id="05d51-104">パッケージの所有者は、ID プレフィックスを予約することにより、自分の ID を予約して保護することができます。</span><span class="sxs-lookup"><span data-stu-id="05d51-104">Package owners can reserve and protect their identity by reserving ID prefixes.</span></span> <span data-ttu-id="05d51-105">パッケージのコンシューマーには、パッケージを使用するときに、使用するパッケージの識別プロパティが詐欺的なものでないことを示す追加情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="05d51-105">Package consumers are provided with additional information when consuming packages that the package they are consuming are not deceptive in their identifying properties.</span></span> 

<span data-ttu-id="05d51-106">[nuget.org](https://www.nuget.org/) および Visual Studio 2017 バージョン 15.4 以降では、パッケージが予約済み ID プレフィックスの名前付けパターンと一致する場合、所有者が予約済みパッケージ ID プレフィックスで送信したパッケージの視覚的なインジケーターが示されます。</span><span class="sxs-lookup"><span data-stu-id="05d51-106">[nuget.org](https://www.nuget.org/) and Visual Studio 2017 version 15.4 or later show a visual indicator for packages that are submitted by owners with a reserved package ID prefix, as long as the package matches the reserved ID prefix naming pattern.</span></span> <span data-ttu-id="05d51-107">以下のリファレンスでは、ID プレフィックスの予約に付随することと、所有者が ID プレフィックスを申請する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05d51-107">The below reference explains what the ID prefix reservation entails, and how an owner can apply for an ID prefix.</span></span>

## <a name="id-prefix-reservation-details"></a><span data-ttu-id="05d51-108">ID プレフィックスの予約の詳細</span><span class="sxs-lookup"><span data-stu-id="05d51-108">ID prefix reservation details</span></span>

<span data-ttu-id="05d51-109">パッケージ ID プレフィックスが予約されると、[nuget.org](https://www.nuget.org/) ギャラリーおよび Visual Studio でいくつかのことが行われます。</span><span class="sxs-lookup"><span data-stu-id="05d51-109">When a package ID prefix is reserved, several things happen on the [nuget.org](https://www.nuget.org/) gallery, as well as in Visual Studio.</span></span> <span data-ttu-id="05d51-110">さらに、"パブリック" としてのプレフィックスの設定や、複数の所有者に対するプレフィックスのサブセットの委任など、ID プレフィックスの予約によってサポートされる高度なシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="05d51-110">In addition, there are advanced scenarios that are supported by ID prefix reservations, such as setting a prefix as 'public', delegating prefix subsets to multiple owners.</span></span>

### <a name="id-prefix-reservation-on-nugetorg"></a><span data-ttu-id="05d51-111">nuget.org での ID プレフィックスの予約</span><span class="sxs-lookup"><span data-stu-id="05d51-111">ID prefix reservation on nuget.org</span></span>

<span data-ttu-id="05d51-112">[nuget.org](https://www.nuget.org/) でプレフィックスを予約すると、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="05d51-112">When a prefix is reserved on [nuget.org](https://www.nuget.org/), the following will happen:</span></span>

1. <span data-ttu-id="05d51-113">[nuget.org](https://www.nuget.org/) で、プレフィックスの予約が所有者または所有者のセットに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="05d51-113">A prefix reservation is associated with an owner or set of owners on [nuget.org](https://www.nuget.org/).</span></span>

1. <span data-ttu-id="05d51-114">[nuget.org](https://www.nuget.org/) に送信されたパッケージに、予約された ID プレフィックスと一致する ID が含まれる場合、それが ID プレフィックスを予約した所有者からのものでないときは常に、パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="05d51-114">Whenever a package is submitted to [nuget.org](https://www.nuget.org/) with an ID that matches the reserved ID prefix, the package is rejected unless it originates from the owner(s) that reserved the ID prefix.</span></span>

1. <span data-ttu-id="05d51-115">パッケージが予約済み ID プレフィックスと一致し、その ID プレフィックスを予約した所有者から送られてきたものである場合は、Visual Studio 2017 バージョン 15.4 以降および [nuget.org](https://www.nuget.org/) では視覚的なインジケーターが表示されて、パッケージが予約済み ID プレフィックスのものであることが示されます。</span><span class="sxs-lookup"><span data-stu-id="05d51-115">Any package that matches the reserved ID prefix and originates from the owner(s) that reserved the ID prefix will have a visual indicator in Visual Studio 2017 version 15.4 or later, and on [nuget.org](https://www.nuget.org/) indicating that the package is under a reserved ID prefix.</span></span> <span data-ttu-id="05d51-116">これは、新しいパッケージの送信と、その所有者の既存のパッケージの両方に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="05d51-116">This is true for both new package submissions as well as existing packages under the owner(s).</span></span> <span data-ttu-id="05d51-117">**注:** Visual Studio のインジケーターは、1 つのフィードがパッケージのソースとして選択されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="05d51-117">**Note:** The indicator in Visual Studio appears only if a single feed is selected as the package source.</span></span>

1. <span data-ttu-id="05d51-118">予約済み ID プレフィックスと一致する、以前に存在していたパッケージのうち、予約済みプレフィックスの所有者によって所有されて "*いない*" ものはすべて、変更されずに残っています (一覧からは削除されませんが、視覚的なインジケーターが表示されることもありません)。</span><span class="sxs-lookup"><span data-stu-id="05d51-118">All previously existing packages that match the reserved ID prefix, but are *not* owned by the owner of the reserved prefix will remain unchanged (they will not be unlisted, but they will also not have the visual indicator).</span></span> <span data-ttu-id="05d51-119">さらに、これらのパッケージの所有者は、引き続きパッケージに新しいバージョンを送信できます。</span><span class="sxs-lookup"><span data-stu-id="05d51-119">In addition, owners of these packages will still be able to submit new versions to the package.</span></span>

<span data-ttu-id="05d51-120">これらの変更は次の条件に基づいており、追加の制限がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="05d51-120">These changes are based on the following conditions and impose several additional restrictions:</span></span>

- <span data-ttu-id="05d51-121">視覚的インジケーターが表示されるためには、予約済みプレフィックスを持っているパッケージの所有者が、1 人だけである必要があります (複数の所有者がいるパッケージの場合)。</span><span class="sxs-lookup"><span data-stu-id="05d51-121">Only one owner of a package needs to have the reserved prefix for the visual indicator to appear (for packages with multiple-owners).</span></span>

- <span data-ttu-id="05d51-122">パッケージに複数の所有者がいて、1 人以上の所有者が予約済みプレフィックスを持っていて、1 人以上の所有者が予約済みプレフィックスを持っていない場合、予約済みプレフィックスを持っている所有者だけが、予約済みプレフィックスを持っている他の所有者を削除できます。</span><span class="sxs-lookup"><span data-stu-id="05d51-122">If there is more than one owner of a package where one or more owners has the reserved prefix and one or more owners does not have the reserved prefix, then only the owner(s) with the reserved prefix can remove other owner(s) with a reserved prefix.</span></span> <span data-ttu-id="05d51-123">予約済みプレフィックスを持っていない所有者は、予約済みプレフィックスを持っている所有者を削除できません。</span><span class="sxs-lookup"><span data-stu-id="05d51-123">The owners who do not have the prefix reserved cannot remove owners with the prefix reserved.</span></span> <span data-ttu-id="05d51-124">そのような所有者が削除できるのは、やはり予約済みプレフィックスを持っていない他の所有者だけです。</span><span class="sxs-lookup"><span data-stu-id="05d51-124">They can still remove other owners that also do not have the prefix reserved.</span></span>

- <span data-ttu-id="05d51-125">いったんパッケージに視覚的インジケーターが付いた後は、"*常に*" 視覚インジケーターが付いている必要があります (予約済みプレフィックスを持っている少なくとも 1 人の所有者が、常に所有者として残っていることを保証します)</span><span class="sxs-lookup"><span data-stu-id="05d51-125">Once a package has the visual indicator, it should *always* have the visual indicator (guaranteeing that at least one owner with the reserved prefix will always remain an owner)</span></span>

### <a name="advanced-prefix-reservation-scenarios"></a><span data-ttu-id="05d51-126">高度なプレフィックス予約のシナリオ</span><span class="sxs-lookup"><span data-stu-id="05d51-126">Advanced prefix reservation scenarios</span></span>

<span data-ttu-id="05d51-127">サブプレフィックスの委任や、パブリックとしてのプレフィックスのマークなど、以下で説明するような高度なプレフィックス予約のシナリオがさらにいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="05d51-127">There are several more advanced prefix reservation scenarios described below, including subprefix delegation, and marking prefixes as public.</span></span> <span data-ttu-id="05d51-128">実行できるさらに高度なプレフィックスの予約を次に示します。</span><span class="sxs-lookup"><span data-stu-id="05d51-128">Below are the more advanced prefix reservations that can be made.</span></span> 

- <span data-ttu-id="05d51-129">プレフィックスの予約の間に、所有者は、プレフィックスのサブセット (またはプレフィックス) を他の所有者に委任することを要求できます。</span><span class="sxs-lookup"><span data-stu-id="05d51-129">During prefix reservation, the owner can request delegation of prefix subsets (or the prefix) to other owners.</span></span> <span data-ttu-id="05d51-130">たとえば、"[aspnet](https://www.nuget.org/profiles/aspnet)" が "Microsoft.AspNet.\*" の予約を望んでいるのに、"[Microsoft](https://www.nuget.org/profiles/microsoft)" が "Microsoft.\*" を所有している場合、"[Microsoft](https://www.nuget.org/profiles/microsoft)" は "Microsoft.AspNet.\*" を [aspnet](https://www.nuget.org/profiles/aspnet) アカウントに委任できます。</span><span class="sxs-lookup"><span data-stu-id="05d51-130">For example, if '[Microsoft](https://www.nuget.org/profiles/microsoft)' owns 'Microsoft.\*', but '[aspnet](https://www.nuget.org/profiles/aspnet)' wants to reserve 'Microsoft.AspNet.\*', '[Microsoft](https://www.nuget.org/profiles/microsoft)' can choose to delegate 'Microsoft.AspNet.\*' to the [aspnet](https://www.nuget.org/profiles/aspnet) account.</span></span>

- <span data-ttu-id="05d51-131">プレフィックスの予約の間に、所有者は、プレフィックスをパブリックにすることができます。</span><span class="sxs-lookup"><span data-stu-id="05d51-131">During prefix reservation, the owner can choose to make a prefix public.</span></span> <span data-ttu-id="05d51-132">このようにしてもまだ、パッケージが予約済みプレフィックスからのものであることを示す視覚的インジケーターは表示されていますが、将来任意の所有者がそのプレフィックスでパッケージを送信してもブロック**されません**。</span><span class="sxs-lookup"><span data-stu-id="05d51-132">This will still give them the visual indicator showing that the package originates from a reserved prefix, but it will **not** block future package submissions on the prefix for any owner.</span></span> <span data-ttu-id="05d51-133">これは、多くの共同作成者がいるオープンソース プロジェクトで役に立ちます。上位または中核の共同作成者がプレフィックスを予約しても、すべての共同作成者に対してオープンにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="05d51-133">This is useful for open source projects with many contributors - the top or core contributors can have the prefix reserved, but it can still be open to all contributors.</span></span> 

### <a name="prefix-reservation-visual-indicator"></a><span data-ttu-id="05d51-134">プレフィックスの予約の視覚的インジケーター</span><span class="sxs-lookup"><span data-stu-id="05d51-134">Prefix reservation visual indicator</span></span>

<span data-ttu-id="05d51-135">パッケージが予約済みプレフィックスからのものである場合、[nuget.org](https://www.nuget.org/) ギャラリーおよび Visual Studio 2017 バージョン 15.4 以降では、次のような視覚的インジケーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05d51-135">When a package comes from a reserved prefix, you see the below visual indicators on the [nuget.org](https://www.nuget.org/) gallery and in Visual Studio 2017 version 15.4 or later:</span></span>

<span data-ttu-id="05d51-136">**nuget.org ギャラリー**
![nuget.org ギャラリー](media/nuget-gallery-reserved-prefix.png)</span><span class="sxs-lookup"><span data-stu-id="05d51-136">**nuget.org Gallery**
![nuget.org Gallery](media/nuget-gallery-reserved-prefix.png)</span></span>

<span data-ttu-id="05d51-137">**Visual Studio**
![Visual Studio](media/visual-studio-reserved-prefix.png)</span><span class="sxs-lookup"><span data-stu-id="05d51-137">**Visual Studio**
![Visual Studio](media/visual-studio-reserved-prefix.png)</span></span>

## <a name="id-prefix-reservation-application-process"></a><span data-ttu-id="05d51-138">ID プレフィックスの予約の申請プロセス</span><span class="sxs-lookup"><span data-stu-id="05d51-138">ID prefix reservation application process</span></span>

1. <span data-ttu-id="05d51-139">[プレフィックス ID 予約の条件](#id-prefix-reservation-criteria)を確認します。</span><span class="sxs-lookup"><span data-stu-id="05d51-139">Review the acceptance [criteria for prefix ID reservation](#id-prefix-reservation-criteria).</span></span>

2. <span data-ttu-id="05d51-140">必要となる[高度なプレフィックス予約シナリオ](#advanced-prefix-reservation-scenarios)に加えて、予約するプレフィックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="05d51-140">Determine the prefixes you want to reserve, in addition to any [advanced prefix reservation scenarios](#advanced-prefix-reservation-scenarios) you may require.</span></span>

3. <span data-ttu-id="05d51-141">[nuget.org](https://www.nuget.org/) での所有者の表示名と、要求する予約済みプレフィックスを、[account@nuget.org](mailto:account@nuget.org) にメールで送ります。</span><span class="sxs-lookup"><span data-stu-id="05d51-141">Send a mail to [account@nuget.org](mailto:account@nuget.org) with the owner display name on [nuget.org](https://www.nuget.org/), as well as any reserved prefixes you are requesting.</span></span> <span data-ttu-id="05d51-142">プレフィックスのサブセットを複数の所有者に委任する場合は、すべての所有者の表示名とプレフィックスのサブセットを記載してあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05d51-142">If you are delegating prefix subsets to multiple owners, make sure you mention all owner display names and prefix subsets.</span></span>

<span data-ttu-id="05d51-143">申請を送信した後、受理または拒否 (および拒否の原因となった条件) の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="05d51-143">After the application is submitted, you are notified of acceptance or rejection (with the criteria that caused rejection).</span></span> <span data-ttu-id="05d51-144">所有者の身元を確認するために、追加の身元確認の質問が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="05d51-144">We may need to ask additional identifying questions to confirm owner identity.</span></span>

### <a name="id-prefix-reservation-criteria"></a><span data-ttu-id="05d51-145">ID プレフィックスの予約の条件</span><span class="sxs-lookup"><span data-stu-id="05d51-145">ID prefix reservation criteria</span></span>

<span data-ttu-id="05d51-146">ID プレフィックス予約の申請をレビューするとき、[nuget.org](https://www.nuget.org/) のチームは以下の条件に対して申請を評価します。</span><span class="sxs-lookup"><span data-stu-id="05d51-146">When reviewing any application for ID prefix reservation, the [nuget.org](https://www.nuget.org/) team will evaluate the application against the below criteria.</span></span> <span data-ttu-id="05d51-147">プレフィックスが予約されるためにすべての条件が満たされる必要はありませんが、条件が満たされていることの十分な証拠 (および説明) がない場合、申請が却下される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05d51-147">Not all criteria needs to be met for a prefix to be reserved, but the application may be denied if there is not substantial evidence of the criteria being met (with an explanation given):</span></span>

1. <span data-ttu-id="05d51-148">そのパッケージ ID プレフィックスでは適切かつ明確にパッケージ所有者が示されていますか?</span><span class="sxs-lookup"><span data-stu-id="05d51-148">Does the package ID prefix properly and clearly identify the package owner?</span></span>

1. <span data-ttu-id="05d51-149">そのパッケージ ID プレフィックスの下で所有者によって既に多数のパッケージが送信されていますか?</span><span class="sxs-lookup"><span data-stu-id="05d51-149">Are a significant number of the packages that have already been submitted by the owner under the package ID prefix?</span></span>

1. <span data-ttu-id="05d51-150">そのパッケージ ID プレフィックスには個人所有者または組織に属すべきではない何らかの一般性がありますか?</span><span class="sxs-lookup"><span data-stu-id="05d51-150">Is the package ID prefix something common that should not belong to any individual owner or organization?</span></span>

1. <span data-ttu-id="05d51-151">そのパッケージ ID プレフィックスを予約しても、コミュニティに対してあいまいさや混乱が発生することは "*ありませんか*"?</span><span class="sxs-lookup"><span data-stu-id="05d51-151">Would *not* reserving the package ID prefix cause ambiguity and confusion for the community?</span></span>

1. <span data-ttu-id="05d51-152">そのパッケージ ID プレフィックスと一致するパッケージの識別プロパティは明確かつ一貫していますか (特にパッケージの作成者)?</span><span class="sxs-lookup"><span data-stu-id="05d51-152">Are the identifying properties of the packages that match the package ID prefix clear and consistent (especially the package author)?</span></span>

1. <span data-ttu-id="05d51-153">パッケージにはライセンスがありますか (非推奨になった licenseUrl ではなく、[license](../reference/nuspec.md#license) メタデータ要素を使用)?</span><span class="sxs-lookup"><span data-stu-id="05d51-153">Do the packages have a license (using the [license](../reference/nuspec.md#license) metadata element and NOT licenseUrl which is being deprecated)?</span></span>

## <a name="third-party-feed-provider-scenarios"></a><span data-ttu-id="05d51-154">サード パーティのフィード プロバイダーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="05d51-154">Third party feed provider scenarios</span></span>

<span data-ttu-id="05d51-155">サード パーティのフィード プロバイダーが、独自のサービスを実装してプレフィックスの予約を提供することに興味を持っている場合、NuGet V3 フィード プロバイダーで検索サービスを変更することにより、行うことができます。</span><span class="sxs-lookup"><span data-stu-id="05d51-155">If a third party feed provider is interested in implementing their own service to provide prefix reservations, you can do so by modifying the search service in the NuGet V3 feed providers.</span></span> <span data-ttu-id="05d51-156">フィード検索サービスでの追加は、下の V3 フィードの例での、*verified* プロパティの追加です。</span><span class="sxs-lookup"><span data-stu-id="05d51-156">The addition in the feed search service is to add the *verified* property, with examples for the V3 feeds below.</span></span> <span data-ttu-id="05d51-157">NuGet クライアントでは、V2 フィードで追加されたプロパティはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="05d51-157">The NuGet client will not support the added property in the V2 feed.</span></span>

<span data-ttu-id="05d51-158">詳しくは、[API の検索サービスに関するドキュメント](../api/search-query-service-resource.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="05d51-158">For more information, see the [documentation about the API's search service](../api/search-query-service-resource.md).</span></span>

## <a name="package-id-prefix-reservation-dispute-policy"></a><span data-ttu-id="05d51-159">パッケージ ID プレフィックス予約の争議ポリシー</span><span class="sxs-lookup"><span data-stu-id="05d51-159">Package ID Prefix Reservation Dispute Policy</span></span>
<span data-ttu-id="05d51-160">上記の条件に反している [NuGet.org](https://www.nuget.org) の所有者にパッケージ ID プレフィックスの予約が割り当てられたと信じられる場合、または商標や著作権が侵害されている場合は、問題の ID プレフィックス、その ID プレフィックスの所有者、割り当てられたプレフィックス予約を争議する理由を明記して、[support@nuget.org](mailto:support@nuget.org) までメールをお送りください。</span><span class="sxs-lookup"><span data-stu-id="05d51-160">If you believe an owner on [NuGet.org](https://www.nuget.org) was assigned a package ID prefix reservation that goes against the above listed criteria, or infringes on any trademarks or copyrights, please email [support@nuget.org](mailto:support@nuget.org) with the ID prefix in question, the owner of the ID prefix, and the reason for disputing the assigned prefix reservation.</span></span>
