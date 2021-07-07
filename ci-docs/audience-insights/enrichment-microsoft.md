---
title: Obogatitev profilov strank s podatki družbe Microsoft
description: Uporabite lastniške podatke družbe Microsoft, da obogatite podatke o strankah z priljubljenostjo znamk in zanimanj.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305176"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="4e155-103">Obogatitev profilov strank s podatki o afiniteti do blagovnih znamk in zanimanj (predogled)</span><span class="sxs-lookup"><span data-stu-id="4e155-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="4e155-104">Uporabite Microsoftove lastniške podatke, da obogatite podatke o strankah z priljubljenostjo znamk in zanimanj.</span><span class="sxs-lookup"><span data-stu-id="4e155-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="4e155-105">Te afinitete temeljijo na podatkih oseb iz podobne demografske skupine kot vaše stranke.</span><span class="sxs-lookup"><span data-stu-id="4e155-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="4e155-106">Te informacije vam pomagajo bolje razumeti in segmentirati vaše stranke na podlagi njihovih afinitet do določenih blagovnih znamk in zanimanj.</span><span class="sxs-lookup"><span data-stu-id="4e155-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="4e155-107">V vpogledih v občinstvo odprite razdelek **Podatki** > **Obogatitev**, da [konfigurirate in si ogledate obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="4e155-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="4e155-108">Če želite konfigurirati obogatitev priljubljenih blagovnih znamk, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Blagovne znamke**.</span><span class="sxs-lookup"><span data-stu-id="4e155-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="4e155-109">Če želite konfigurirati obogatitev priljubljenih zanimanj, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Zanimanja**.</span><span class="sxs-lookup"><span data-stu-id="4e155-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4e155-110">![Ploščici Blagovne znamke in Zanimanja](media/BrandsInterest-tile-Hub.png "Ploščici Blagovne znamke in Zanimanja")</span><span class="sxs-lookup"><span data-stu-id="4e155-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="4e155-111">Določitev priljubljenosti</span><span class="sxs-lookup"><span data-stu-id="4e155-111">How we determine affinities</span></span>

<span data-ttu-id="4e155-112">Microsoftove podatke o spletnih iskanjih uporabljamo za ugotavljanje priljubljenosti blagovnih znamk in interesov v različnih demografskih segmentih (opredeljenih s starostjo, spolom ali lokacijo).</span><span class="sxs-lookup"><span data-stu-id="4e155-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="4e155-113">Obseg spletnega iskanja blagovne znamke ali zanimanja določa raven afinitete do blagovnih znamk ali zanimanj v posameznem demografskem segmentu v primerjavi z drugimi segmenti.</span><span class="sxs-lookup"><span data-stu-id="4e155-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="4e155-114">Stopnja afinitete in ocena</span><span class="sxs-lookup"><span data-stu-id="4e155-114">Affinity level and score</span></span>

<span data-ttu-id="4e155-115">Za vsak obogateni profil stranke zagotavljamo dve povezani vrednosti: stopnjo afinitete in oceno afinitete.</span><span class="sxs-lookup"><span data-stu-id="4e155-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="4e155-116">Te vrednosti vam pomagajo ugotoviti, kako močna je afiniteta demografskega segmenta tega profila za blagovno znamko ali zanimanje v primerjavi z drugimi demografskimi segmenti.</span><span class="sxs-lookup"><span data-stu-id="4e155-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="4e155-117">*Stopnja afinitete* je sestavljena iz štirih stopenj, *ocena afinitete* pa se izračuna na 100-stopenjski lestvici, ki se preslika v stopnje afinitete.</span><span class="sxs-lookup"><span data-stu-id="4e155-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="4e155-118">Stopnja afinitete</span><span class="sxs-lookup"><span data-stu-id="4e155-118">Affinity level</span></span> |<span data-ttu-id="4e155-119">Ocena afinitete</span><span class="sxs-lookup"><span data-stu-id="4e155-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="4e155-120">Zelo visoka</span><span class="sxs-lookup"><span data-stu-id="4e155-120">Very high</span></span>     | <span data-ttu-id="4e155-121">85–100</span><span class="sxs-lookup"><span data-stu-id="4e155-121">85-100</span></span>       |
|<span data-ttu-id="4e155-122">Velik</span><span class="sxs-lookup"><span data-stu-id="4e155-122">High</span></span>     | <span data-ttu-id="4e155-123">70–84</span><span class="sxs-lookup"><span data-stu-id="4e155-123">70-84</span></span>        |
|<span data-ttu-id="4e155-124">Srednji</span><span class="sxs-lookup"><span data-stu-id="4e155-124">Medium</span></span>     | <span data-ttu-id="4e155-125">35–69</span><span class="sxs-lookup"><span data-stu-id="4e155-125">35-69</span></span>        |
|<span data-ttu-id="4e155-126">Majhen</span><span class="sxs-lookup"><span data-stu-id="4e155-126">Low</span></span>     | <span data-ttu-id="4e155-127">1–34</span><span class="sxs-lookup"><span data-stu-id="4e155-127">1-34</span></span>        |

<span data-ttu-id="4e155-128">Glede na granularnost, ki jo želite za merjenje afinitete, lahko uporabite možnost stopnje afinitete ali ocene afinitete.</span><span class="sxs-lookup"><span data-stu-id="4e155-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="4e155-129">Ocena afinitete omogoča natančnejši nadzor.</span><span class="sxs-lookup"><span data-stu-id="4e155-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="4e155-130">Podprte države/regije</span><span class="sxs-lookup"><span data-stu-id="4e155-130">Supported countries/regions</span></span>

<span data-ttu-id="4e155-131">Trenutno podpiramo naslednje države/regije: Avstralija, Kanada (angleščina), Francija, Nemčija, Združeno kraljestvo ali Združene države (angleščina).</span><span class="sxs-lookup"><span data-stu-id="4e155-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="4e155-132">Če želite izbrati državo ali regijo, odprite **Obogatitev blagovnih znamk** ali **Obogatitev interesov** in izberite možnost **Spremeni** poleg možnost **Država/regija**.</span><span class="sxs-lookup"><span data-stu-id="4e155-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="4e155-133">V podoknu **Nastavitve države/regije** izberite možnost in izberite ukaz **Uporabi**.</span><span class="sxs-lookup"><span data-stu-id="4e155-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="4e155-134">Posledice, povezane z izbiro države/regije</span><span class="sxs-lookup"><span data-stu-id="4e155-134">Implications related to country selection</span></span>

- <span data-ttu-id="4e155-135">Pri [izbiri lastnih blagovnih znamk](#define-your-brands-or-interests) sistem ponuja predloge glede na izbrano državo ali regijo.</span><span class="sxs-lookup"><span data-stu-id="4e155-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="4e155-136">Pri [izbiri panoge](#define-your-brands-or-interests) boste pridobili najbolj ustrezne blagovne znamke ali interese glede na izbrano državo oziroma regijo.</span><span class="sxs-lookup"><span data-stu-id="4e155-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="4e155-137">Med [obogatitvijo profilov](#refresh-enrichment) bomo obogatili vse profile strank, za katere dobimo podatke za izbrane blagovne znamke in interese, vključno s profili, ki niso v izbrani državi ali regiji.</span><span class="sxs-lookup"><span data-stu-id="4e155-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="4e155-138">Če na primer izberete Nemčijo, bomo obogatili profile iz Združenih državah Amerike, če imamo na voljo podatke o izbranih blagovnih znamkah in interesih v ZDA.</span><span class="sxs-lookup"><span data-stu-id="4e155-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="4e155-139">Konfigurirajte obogatitev</span><span class="sxs-lookup"><span data-stu-id="4e155-139">Configure enrichment</span></span>

<span data-ttu-id="4e155-140">Pri konfiguriranju obogatitev vam pomaga vodena izkušnja.</span><span class="sxs-lookup"><span data-stu-id="4e155-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="4e155-141">Določite svoje blagovne znamke ali zanimanja</span><span class="sxs-lookup"><span data-stu-id="4e155-141">Define your brands or interests</span></span>

<span data-ttu-id="4e155-142">Izberite do pet blagovnih znamk ali zanimanj z izbiro ene ali obeh možnosti:</span><span class="sxs-lookup"><span data-stu-id="4e155-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="4e155-143">**Panoga**: Na spustnem seznamu izberite svojo panogo, nato pa izbirajte med najboljšimi blagovnimi znamkami ali zanimanji za to panogo.</span><span class="sxs-lookup"><span data-stu-id="4e155-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="4e155-144">**Izberite svojo**: vnesite blagovno znamko ali zanimanje, ki je relevantno za vašo organizacijo, in nato izberite enega izmed predlogov ujemanja.</span><span class="sxs-lookup"><span data-stu-id="4e155-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="4e155-145">Če med predlogi ni blagovne znamke ali zanimanja, ki ga iščete, nam pošljite povratne informacije prek povezave **Predlagaj**.</span><span class="sxs-lookup"><span data-stu-id="4e155-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="4e155-146">Pregled nastavitev obogatitve</span><span class="sxs-lookup"><span data-stu-id="4e155-146">Review enrichment preferences</span></span>

<span data-ttu-id="4e155-147">Preglejte privzete nastavitve obogatitve in jih po potrebi posodobite.</span><span class="sxs-lookup"><span data-stu-id="4e155-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Posnetek zaslona okna z nastavitvami obogatitve.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="4e155-149">Izberite entiteto za obogatitev</span><span class="sxs-lookup"><span data-stu-id="4e155-149">Select entity to enrich</span></span>

<span data-ttu-id="4e155-150">Izberite možnost **Obogatena entiteta** in izberite nabor podatkov, ki ga želite obogatiti s podatki podjetja družbe Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e155-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="4e155-151">Izberete lahko entiteto Stranka, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="4e155-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="4e155-152">Preslikajte polja</span><span class="sxs-lookup"><span data-stu-id="4e155-152">Map your fields</span></span>

<span data-ttu-id="4e155-153">Preslikajte polja iz enotne entitete stranke, da določite demografski segment, ki ga mora sistem uporabiti za obogatitev podatkov o strankah.</span><span class="sxs-lookup"><span data-stu-id="4e155-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="4e155-154">Preslikajte vrednosti za državo/regijo in vsaj datum rojstva ali spol.</span><span class="sxs-lookup"><span data-stu-id="4e155-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="4e155-155">Poleg tega morate preslikati vsaj en atribut za mesto (in državo/območje) ali poštno številko.</span><span class="sxs-lookup"><span data-stu-id="4e155-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="4e155-156">Izberite **Uredi**, da določite preslikavo polj, in izberite **Uporabi**, ko končate.</span><span class="sxs-lookup"><span data-stu-id="4e155-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="4e155-157">Izberite **Shrani** za dokončanje preslikave polj.</span><span class="sxs-lookup"><span data-stu-id="4e155-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="4e155-158">Podprti so naslednji formati in vrednosti (vrednosti ne razlikujejo med velikimi in malimi črkami):</span><span class="sxs-lookup"><span data-stu-id="4e155-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="4e155-159">**Datum rojstva**: priporočamo, da se datum rojstva med uvozom podatkov pretvori v vrsto DateTime.</span><span class="sxs-lookup"><span data-stu-id="4e155-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="4e155-160">Lahko pa gre za niz v standardu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), in sicer v obliki »llll-MM-dd« ali »llll-MM-ddTHH: mm: ss«.</span><span class="sxs-lookup"><span data-stu-id="4e155-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="4e155-161">**Spol**: moški, ženski, neopredeljen.</span><span class="sxs-lookup"><span data-stu-id="4e155-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="4e155-162">**Poštna številka**: za ZDA veljajo petmestne poštne številke, za druge države pa standardne poštne številke.</span><span class="sxs-lookup"><span data-stu-id="4e155-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="4e155-163">**Mesto**: ime mesta v angleščini.</span><span class="sxs-lookup"><span data-stu-id="4e155-163">**City**: City name in English.</span></span>
- <span data-ttu-id="4e155-164">**Država/provinca**: dvočrkovna okrajšava za ZDA in Kanado.</span><span class="sxs-lookup"><span data-stu-id="4e155-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="4e155-165">Dvo- ali tričrkovna okrajšava za Avstralijo.</span><span class="sxs-lookup"><span data-stu-id="4e155-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="4e155-166">Ne velja za Francijo, Nemčijo ali Združeno kraljestvo.</span><span class="sxs-lookup"><span data-stu-id="4e155-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="4e155-167">**Država/regija**:</span><span class="sxs-lookup"><span data-stu-id="4e155-167">**Country/Region**:</span></span>

  - <span data-ttu-id="4e155-168">ZDA: Združene države Amerike, Združene države, ZDA, Amerika</span><span class="sxs-lookup"><span data-stu-id="4e155-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="4e155-169">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="4e155-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="4e155-170">GB: Združeno kraljestvo, Velika Britanija, Združeno kraljestvo Velike Britanije in Severne Irske, Združeno kraljestvo Velike Britanije</span><span class="sxs-lookup"><span data-stu-id="4e155-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="4e155-171">AU: Avstralija, AU, Avstralska zveza</span><span class="sxs-lookup"><span data-stu-id="4e155-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="4e155-172">FR: Francija, FR, republika Francija</span><span class="sxs-lookup"><span data-stu-id="4e155-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="4e155-173">DE: Nemčija, Zvezna republika Nemčija, Republika Nemčija</span><span class="sxs-lookup"><span data-stu-id="4e155-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="4e155-174">Pregled in poimenovanje obogatitve</span><span class="sxs-lookup"><span data-stu-id="4e155-174">Review and name the enrichment</span></span>

<span data-ttu-id="4e155-175">Na koncu morate pregledati podatke in navesti ime obogatitve.</span><span class="sxs-lookup"><span data-stu-id="4e155-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stran za pregled in poimenovanje interesov.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="4e155-177">Osvežite obogatitev</span><span class="sxs-lookup"><span data-stu-id="4e155-177">Refresh enrichment</span></span>

<span data-ttu-id="4e155-178">Zaženite obogatitev po tem, ko konfigurirate blagovne znamke, zanimanja in preslikavo polj za demografske skupine.</span><span class="sxs-lookup"><span data-stu-id="4e155-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="4e155-179">Če želite začeti postopek, na strani za konfiguracijo blagovne znamke ali zanimanja izberite **Zagon**.</span><span class="sxs-lookup"><span data-stu-id="4e155-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="4e155-180">Poleg tega lahko pustite, da sistem samodejno zažene obogatitev kot del načrtovane osvežitve.</span><span class="sxs-lookup"><span data-stu-id="4e155-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="4e155-181">Glede na velikost podatkov o strankah lahko postopek obogatitve traja nekaj minut.</span><span class="sxs-lookup"><span data-stu-id="4e155-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="4e155-182">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="4e155-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4e155-183">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4e155-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4e155-184">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="4e155-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4e155-185">Ko za eno izmed opravil izberete možnost **Prikaži podrobnosti**, boste lahko dostopali do naslednjih dodatnih informacij: čas obdelave, datum zadnjega poskusa obdelave ter vse napake in opozorila, povezana z nalogo.</span><span class="sxs-lookup"><span data-stu-id="4e155-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="4e155-186">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="4e155-186">Enrichment results</span></span>

<span data-ttu-id="4e155-187">Po zagonu postopka obogatitve odprite razdelek **Moje obogatitve** in preglejte skupno število obogatenih strank ter razčlenitev blagovnih znamk in zanimanj obogatenih profilih strank.</span><span class="sxs-lookup"><span data-stu-id="4e155-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve":::

<span data-ttu-id="4e155-189">Preglejte obogatene podatke tako, da v grafikonu izberete možnost **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="4e155-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="4e155-190">Obogateni podatki za blagovne znamke so poslani v entiteto **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="4e155-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="4e155-191">Podatki za zanimanje so v entiteti **InteresAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="4e155-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="4e155-192">Te entitete boste našli navedene tudi v skupini **Obogatitev** v **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="4e155-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="4e155-193">Glejte podatke o obogatitvi na kartici stranke</span><span class="sxs-lookup"><span data-stu-id="4e155-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="4e155-194">Afinitete do blagovnih znamk in interesov si je mogoče ogledati tudi na posameznih karticah strank.</span><span class="sxs-lookup"><span data-stu-id="4e155-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="4e155-195">Odprite možnost **Stranke** in izberite profil stranke.</span><span class="sxs-lookup"><span data-stu-id="4e155-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="4e155-196">Na kartici stranke boste našli grafikone blagovnih znamk ali zanimanj, ki so priljubljeni pri osebah v demografskem profilu stranke.</span><span class="sxs-lookup"><span data-stu-id="4e155-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki":::

## <a name="next-steps"></a><span data-ttu-id="4e155-198">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="4e155-198">Next steps</span></span>

<span data-ttu-id="4e155-199">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="4e155-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4e155-200">Ustvarite [segmente](segments.md) in [mere](measures.md) ter celo [izvozite podatke](export-destinations.md) in tako svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="4e155-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
