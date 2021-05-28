---
title: Izvozite podatke Customer Insights v Dynamics 365 Sales
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976246"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="b5611-103">Uporaba segmentov v storitvi Dynamics 365 Sales (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="b5611-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b5611-104">Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.</span><span class="sxs-lookup"><span data-stu-id="b5611-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="b5611-105">Predpogoj za povezavo</span><span class="sxs-lookup"><span data-stu-id="b5611-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="b5611-106">Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Sales, preden lahko izvozite segment iz rešitve Customer Insights v Sales.</span><span class="sxs-lookup"><span data-stu-id="b5611-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b5611-107">Preberite več o vključevanju stikov v storitvi [Dynamics 365 Sales z uporabo rešitve Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b5611-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b5611-108">Z izvozom segmentov iz vpogledov v občinstvo v rešitev Sales ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Sales.</span><span class="sxs-lookup"><span data-stu-id="b5611-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b5611-109">Zapise o stikih iz rešitve Sales je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="b5611-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b5611-110">Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.</span><span class="sxs-lookup"><span data-stu-id="b5611-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="b5611-111">Nastavitev povezave s storitvijo Sales</span><span class="sxs-lookup"><span data-stu-id="b5611-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="b5611-112">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="b5611-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b5611-113">Izberite **Dodajanje povezave** in izberite **Dynamics 365 Sales** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="b5611-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="b5611-114">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="b5611-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b5611-115">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="b5611-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b5611-116">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="b5611-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b5611-117">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="b5611-117">Choose who can use this connection.</span></span> <span data-ttu-id="b5611-118">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="b5611-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b5611-119">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b5611-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b5611-120">Vnesite URL za Sales vaše organizacije v polje **Naslov strežnika**.</span><span class="sxs-lookup"><span data-stu-id="b5611-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b5611-121">V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b5611-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b5611-122">Polje za ID stranke preslikajte v ID stika za Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b5611-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b5611-123">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="b5611-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b5611-124">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="b5611-124">Configure an export</span></span>

<span data-ttu-id="b5611-125">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="b5611-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b5611-126">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b5611-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b5611-127">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="b5611-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b5611-128">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="b5611-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b5611-129">V polju **Povezava za izvoz** izberite povezavo v razdelku Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b5611-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="b5611-130">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="b5611-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b5611-131">Izberite enega ali več segmentov.</span><span class="sxs-lookup"><span data-stu-id="b5611-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="b5611-132">Izberite **Shrani**</span><span class="sxs-lookup"><span data-stu-id="b5611-132">Select **Save**</span></span>

<span data-ttu-id="b5611-133">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="b5611-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b5611-134">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b5611-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b5611-135">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b5611-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
