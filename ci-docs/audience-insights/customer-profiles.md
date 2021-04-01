---
title: Ogled profilov strank
description: Pridobite kombiniran pogled vaših poenotenih podatkov o strankah.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596887"
---
# <a name="customer-profiles"></a><span data-ttu-id="fa59c-103">Profili strank</span><span class="sxs-lookup"><span data-stu-id="fa59c-103">Customer profiles</span></span>

<span data-ttu-id="fa59c-104">Stran **Stranke** prikazuje kombiniran pogled vaših strank na podlagi podatkov o profilu, zbranih iz [vseh virov podatkov](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="fa59c-105">Profili strank so na voljo, ko [ustvarite poenoteno entiteto stranke](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="fa59c-106">Za podrobnejše prikaze strank dokončajte postopek poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="fa59c-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="fa59c-107">Stran omogoča tudi iskanje strank.</span><span class="sxs-lookup"><span data-stu-id="fa59c-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="fa59c-108">Stranke so lahko posamezniki ali organizacije (predogled).</span><span class="sxs-lookup"><span data-stu-id="fa59c-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="fa59c-109">Ploščica predstavlja vsak posamezni profil stranke ali organizacije.</span><span class="sxs-lookup"><span data-stu-id="fa59c-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="fa59c-110">Izberite ploščico in si oglejte dodatne informacije o določeni stranki ali organizaciji.</span><span class="sxs-lookup"><span data-stu-id="fa59c-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="fa59c-111">Za prikaz dodatnih zapisov uporabite kontrolnik za oštevilčevanje strani na dnu strani.</span><span class="sxs-lookup"><span data-stu-id="fa59c-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="fa59c-112">![Profili strank pri prodaji strankam](media/profiles-customers.png "Profili strank pri prodaji strankam")</span><span class="sxs-lookup"><span data-stu-id="fa59c-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="fa59c-113">Organizacije (predogled)</span><span class="sxs-lookup"><span data-stu-id="fa59c-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="fa59c-114">![Profili strank pri prodaji podjetjem](media/profile-customers-b2b.png "Profili strank pri prodaji podjetjem")</span><span class="sxs-lookup"><span data-stu-id="fa59c-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="fa59c-115">Če pri krmarjenju po izbiri možnosti **Stranke** ne vidite ploščic, mora vaš skrbnik [določiti vsaj en atribut, ki je omogočen za iskanje](search-filter-index.md), v možnosti **Kazalo za iskanje in filtre**.</span><span class="sxs-lookup"><span data-stu-id="fa59c-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="fa59c-116">Iskanje strank</span><span class="sxs-lookup"><span data-stu-id="fa59c-116">Search for customers</span></span>

<span data-ttu-id="fa59c-117">Stranke poiščete tako, da v polje za iskanje vnesete ime ali kakšen drug atribut.</span><span class="sxs-lookup"><span data-stu-id="fa59c-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="fa59c-118">Iskanje deluje samo v entiteti »Profil stranke«, ki je bila ustvarjena med postopkom poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="fa59c-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="fa59c-119">Kot skrbnik lahko konfigurirate atribute, omogočene za iskanje, na strani **Kazalo za iskanje in filtriranje**.</span><span class="sxs-lookup"><span data-stu-id="fa59c-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="fa59c-120">Za več informacij glejte [Upravljanje kazala za iskanje in filtriranje](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="fa59c-121">Filtriranje strank</span><span class="sxs-lookup"><span data-stu-id="fa59c-121">Filter customers</span></span>

<span data-ttu-id="fa59c-122">Stranke lahko filtrirate po poljih entitete »Profil stranke«.</span><span class="sxs-lookup"><span data-stu-id="fa59c-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="fa59c-123">Podobno kot pri iskanju mora vaš skrbnik na strani **Kazalo za iskanje in filtriranje** najprej omogočiti filtriranje za polja.</span><span class="sxs-lookup"><span data-stu-id="fa59c-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="fa59c-124">Izberite **Filter** na strani **Stranke**.</span><span class="sxs-lookup"><span data-stu-id="fa59c-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="fa59c-125">Potrdite polja poleg atributov, po katerih želite filtrirati stranke.</span><span class="sxs-lookup"><span data-stu-id="fa59c-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="fa59c-126">![Profili strank](media/profiles-customers3.png "Profili strank")</span><span class="sxs-lookup"><span data-stu-id="fa59c-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="fa59c-127">Odstranite filtre tako, da izberete **Počisti filtre** na strani **Stranke**.</span><span class="sxs-lookup"><span data-stu-id="fa59c-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="fa59c-128">Stran s podrobnostmi o stranki</span><span class="sxs-lookup"><span data-stu-id="fa59c-128">Customer details page</span></span>

<span data-ttu-id="fa59c-129">Izberite katero koli ploščico stranke, da odprete **stran s podrobnostmi o stranki**.</span><span class="sxs-lookup"><span data-stu-id="fa59c-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="fa59c-130">Ta pogled vsebuje poenotene podatke za izbrano stranko.</span><span class="sxs-lookup"><span data-stu-id="fa59c-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="fa59c-131">Podrobnosti o stranki vključujejo:</span><span class="sxs-lookup"><span data-stu-id="fa59c-131">Customer details include:</span></span>

-   <span data-ttu-id="fa59c-132">**Ploščica profila stranke:** ta ploščica prikazuje različne vrednosti iz poenotene entitete profila stranke.</span><span class="sxs-lookup"><span data-stu-id="fa59c-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="fa59c-133">Te podrobnosti lahko vključujejo e-poštni naslov, ime, mesto itd.</span><span class="sxs-lookup"><span data-stu-id="fa59c-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="fa59c-134">**Morebitna zanimanja, morebitne blagovne znamke:** pokaže, ali ste konfigurirali lastno obogatitev.</span><span class="sxs-lookup"><span data-stu-id="fa59c-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="fa59c-135">Predstavlja potencialne interese in priljubljene blagovne znamke za stranke s podobnim profilom kot ta stranka.</span><span class="sxs-lookup"><span data-stu-id="fa59c-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="fa59c-136">Za več informacij glejte [Obogatitev profilov strank s priljubljenimi blagovnimi znamkami in zanimanji](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="fa59c-137">**Mere:** prikaže, ali ste konfigurirali eno ali več mer določene vrste: mere atributov stranke.</span><span class="sxs-lookup"><span data-stu-id="fa59c-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="fa59c-138">Vključujejo izračunane KPI-je v zvezi z vašimi strankami na ravni posamezne stranke.</span><span class="sxs-lookup"><span data-stu-id="fa59c-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="fa59c-139">Za več informacij glejte [Določanje in upravljanje mer](measures.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="fa59c-140">**Časovnica dejavnosti:** prikazuje, ali ste konfigurirali dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="fa59c-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="fa59c-141">Pogled časovnice vsebuje kronološko razvrščene dejavnosti te stranke, pri čemer se začne z najnovejšo dejavnostjo.</span><span class="sxs-lookup"><span data-stu-id="fa59c-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="fa59c-142">Za več informacij glejte [Dejavnosti stranke](activities.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="fa59c-143">Izberite **Nazaj k strankam** za vrnitev na stran za iskanje strank.</span><span class="sxs-lookup"><span data-stu-id="fa59c-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa59c-144">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="fa59c-144">Next steps</span></span>

<span data-ttu-id="fa59c-145">[Dodajte več virov podatkov](data-sources.md) ali [ustvarite segmente strank](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fa59c-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]