---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976820"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="3f403-103">Uporaba segmentov v storitvi Dynamics 365 Marketing (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="3f403-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3f403-104">S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3f403-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="3f403-105">Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="3f403-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="3f403-106">Predpogoj za povezavo</span><span class="sxs-lookup"><span data-stu-id="3f403-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="3f403-107">Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Marketing, preden lahko izvozite segment iz rešitve Customer Insights v Marketing.</span><span class="sxs-lookup"><span data-stu-id="3f403-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="3f403-108">Preberite več o vključevanju stikov v storitvi [Dynamics 365 Marketing z uporabo rešitve Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3f403-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="3f403-109">Z izvozom segmentov iz vpogledov v občinstvo v rešitev Marketing ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Marketing.</span><span class="sxs-lookup"><span data-stu-id="3f403-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="3f403-110">Zapise o stikih iz rešitve Marketing je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="3f403-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="3f403-111">Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.</span><span class="sxs-lookup"><span data-stu-id="3f403-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="3f403-112">Nastavitev povezave s storitvijo Marketing</span><span class="sxs-lookup"><span data-stu-id="3f403-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="3f403-113">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="3f403-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3f403-114">Izberite **Dodajanje povezave** in izberite **Dynamics 365 Marketing** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="3f403-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="3f403-115">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="3f403-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3f403-116">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="3f403-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3f403-117">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="3f403-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3f403-118">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="3f403-118">Choose who can use this connection.</span></span> <span data-ttu-id="3f403-119">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="3f403-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3f403-120">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3f403-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3f403-121">Vnesite URL za Marketing vaše organizacije v polje **Naslov strežnika**.</span><span class="sxs-lookup"><span data-stu-id="3f403-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="3f403-122">V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3f403-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="3f403-123">Polje za ID stranke preslikajte v ID stika za Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3f403-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="3f403-124">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="3f403-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="3f403-125">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="3f403-125">Configure an export</span></span>

<span data-ttu-id="3f403-126">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="3f403-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3f403-127">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3f403-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3f403-128">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="3f403-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3f403-129">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="3f403-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3f403-130">V polju **Povezava za izvoz** izberite povezavo v razdelku Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3f403-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="3f403-131">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="3f403-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3f403-132">Izberite enega ali več segmentov.</span><span class="sxs-lookup"><span data-stu-id="3f403-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="3f403-133">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="3f403-133">Select **Save**.</span></span>

<span data-ttu-id="3f403-134">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="3f403-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3f403-135">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3f403-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3f403-136">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3f403-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
