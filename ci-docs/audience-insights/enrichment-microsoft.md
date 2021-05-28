---
title: Obogatitev profilov strank s podatki družbe Microsoft
description: Uporabite lastniške podatke družbe Microsoft, da obogatite podatke o strankah z priljubljenostjo znamk in zanimanj.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064911"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="ba97e-103">Obogatitev profilov strank s podatki o afiniteti do blagovnih znamk in zanimanj (predogled)</span><span class="sxs-lookup"><span data-stu-id="ba97e-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="ba97e-104">Uporabite Microsoftove lastniške podatke, da obogatite podatke o strankah z priljubljenostjo znamk in zanimanj.</span><span class="sxs-lookup"><span data-stu-id="ba97e-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="ba97e-105">Te afinitete so določene na podlagi podatkov ljudi s podobno demografijo, kot jo imajo vaše stranke.</span><span class="sxs-lookup"><span data-stu-id="ba97e-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="ba97e-106">Te informacije vam pomagajo bolje razumeti in segmentirati vaše stranke na podlagi njihovih afinitet do določenih blagovnih znamk in zanimanj.</span><span class="sxs-lookup"><span data-stu-id="ba97e-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="ba97e-107">V vpogledih v občinstvo odprite razdelek **Podatki** > **Obogatitev**, da [konfigurirate in si ogledate obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="ba97e-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="ba97e-108">Če želite konfigurirati obogatitev priljubljenih blagovnih znamk, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Blagovne znamke**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="ba97e-109">Če želite konfigurirati obogatitev priljubljenih zanimanj, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Zanimanja**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba97e-110">![Ploščice z blagovnimi znamkami in zanimanji](media/BrandsInterest-tile-Hub.png "Ploščice z blagovnimi znamkami in zanimanji")</span><span class="sxs-lookup"><span data-stu-id="ba97e-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="ba97e-111">Določitev priljubljenosti</span><span class="sxs-lookup"><span data-stu-id="ba97e-111">How we determine affinities</span></span>

<span data-ttu-id="ba97e-112">Microsoftove podatke o spletnih iskanjih uporabljamo za ugotavljanje priljubljenosti blagovnih znamk in interesov v različnih demografskih segmentih (opredeljenih s starostjo, spolom ali lokacijo).</span><span class="sxs-lookup"><span data-stu-id="ba97e-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="ba97e-113">Obseg spletnega iskanja blagovne znamke ali zanimanja določa raven afinitete do blagovnih znamk ali zanimanj v posameznem demografskem segmentu v primerjavi z drugimi segmenti.</span><span class="sxs-lookup"><span data-stu-id="ba97e-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="ba97e-114">Stopnja afinitete in ocena</span><span class="sxs-lookup"><span data-stu-id="ba97e-114">Affinity level and score</span></span>

<span data-ttu-id="ba97e-115">Za vsak obogateni profil stranke zagotavljamo dve povezani vrednosti – stopnjo afinitete in oceno afinitete.</span><span class="sxs-lookup"><span data-stu-id="ba97e-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="ba97e-116">Te vrednosti vam pomagajo ugotoviti, kako močna je afiniteta demografskega segmenta tega profila za blagovno znamko ali zanimanje v primerjavi z drugimi demografskimi segmenti.</span><span class="sxs-lookup"><span data-stu-id="ba97e-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="ba97e-117">*Stopnja afinitete* je sestavljena iz štirih stopenj, *ocena afinitete* pa se izračuna na 100-stopenjski lestvici, ki se preslika v stopnje afinitete.</span><span class="sxs-lookup"><span data-stu-id="ba97e-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="ba97e-118">Stopnja afinitete</span><span class="sxs-lookup"><span data-stu-id="ba97e-118">Affinity level</span></span> |<span data-ttu-id="ba97e-119">Ocena afinitete</span><span class="sxs-lookup"><span data-stu-id="ba97e-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="ba97e-120">Zelo visoka</span><span class="sxs-lookup"><span data-stu-id="ba97e-120">Very high</span></span>     | <span data-ttu-id="ba97e-121">85–100</span><span class="sxs-lookup"><span data-stu-id="ba97e-121">85-100</span></span>       |
|<span data-ttu-id="ba97e-122">Velik</span><span class="sxs-lookup"><span data-stu-id="ba97e-122">High</span></span>     | <span data-ttu-id="ba97e-123">70–84</span><span class="sxs-lookup"><span data-stu-id="ba97e-123">70-84</span></span>        |
|<span data-ttu-id="ba97e-124">Srednji</span><span class="sxs-lookup"><span data-stu-id="ba97e-124">Medium</span></span>     | <span data-ttu-id="ba97e-125">35–69</span><span class="sxs-lookup"><span data-stu-id="ba97e-125">35-69</span></span>        |
|<span data-ttu-id="ba97e-126">Majhen</span><span class="sxs-lookup"><span data-stu-id="ba97e-126">Low</span></span>     | <span data-ttu-id="ba97e-127">1–34</span><span class="sxs-lookup"><span data-stu-id="ba97e-127">1-34</span></span>        |

<span data-ttu-id="ba97e-128">Glede na granularnost, ki jo želite za merjenje afinitete, lahko uporabite možnost stopnje afinitete ali ocene afinitete.</span><span class="sxs-lookup"><span data-stu-id="ba97e-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="ba97e-129">Ocena afinitete omogoča natančnejši nadzor.</span><span class="sxs-lookup"><span data-stu-id="ba97e-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="ba97e-130">Podprte države/regije</span><span class="sxs-lookup"><span data-stu-id="ba97e-130">Supported countries/regions</span></span>

<span data-ttu-id="ba97e-131">Trenutno podpiramo naslednje države/regije: Avstralija, Kanada (angleščina), Francija, Nemčija, Združeno kraljestvo ali Združene države (angleščina).</span><span class="sxs-lookup"><span data-stu-id="ba97e-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="ba97e-132">Če želite izbrati državo, odprite meni **Obogatitev blagovnih znamk** ali **Obogatitev zanimanja** in izberite možnost **Sprememba** zraven polja **Država/regija**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="ba97e-133">V podoknu **Nastavitve države/regije** izberite možnost in izberite ukaz **Uporabi**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="ba97e-134">Posledice, povezane z izbiro države/regije</span><span class="sxs-lookup"><span data-stu-id="ba97e-134">Implications related to country selection</span></span>

- <span data-ttu-id="ba97e-135">Pri [izbiri lastnih blagovnih znamk](#define-your-brands-or-interests) sistem ponuja predloge glede na izbrano državo ali regijo.</span><span class="sxs-lookup"><span data-stu-id="ba97e-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="ba97e-136">Pri [izbiri panoge](#define-your-brands-or-interests) boste pridobili najbolj ustrezne blagovne znamke ali interese glede na izbrano državo oziroma regijo.</span><span class="sxs-lookup"><span data-stu-id="ba97e-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="ba97e-137">Pri [obogatitvi profilov](#refresh-enrichment) bomo obogatili vse profile strank, za katere dobimo podatke za izbrane blagovne znamke in interese.</span><span class="sxs-lookup"><span data-stu-id="ba97e-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="ba97e-138">Vključno s profili, ki niso v izbrani državi ali regiji.</span><span class="sxs-lookup"><span data-stu-id="ba97e-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="ba97e-139">Če na primer izberete Nemčijo, bomo obogatili profile iz Združenih državah Amerike, če imamo na voljo podatke o izbranih blagovnih znamkah in interesih v ZDA.</span><span class="sxs-lookup"><span data-stu-id="ba97e-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="ba97e-140">Konfiguracija obogatitve</span><span class="sxs-lookup"><span data-stu-id="ba97e-140">Configure Enrichment</span></span>

<span data-ttu-id="ba97e-141">Pri konfiguriranju obogatitev vam pomaga vodena izkušnja.</span><span class="sxs-lookup"><span data-stu-id="ba97e-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="ba97e-142">Določite svoje blagovne znamke ali zanimanja</span><span class="sxs-lookup"><span data-stu-id="ba97e-142">Define your brands or interests</span></span>

<span data-ttu-id="ba97e-143">Izberite eno od teh možnosti:</span><span class="sxs-lookup"><span data-stu-id="ba97e-143">Select one of the following options:</span></span>

- <span data-ttu-id="ba97e-144">**Panoga**: sistem prepozna glavne blagovne znamke ali zanimanja, pomembne za vašo panogo, in z njimi obogati podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="ba97e-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="ba97e-145">**Izberite svoje**: na seznamu blagovnih znamk ali zanimanj, ki so najbolj pomembni za vašo organizacijo, izberite največ pet elementov.</span><span class="sxs-lookup"><span data-stu-id="ba97e-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="ba97e-146">Če želite dodati blagovno znamko ali zanimanje, ga vnesite v območje za vnos, da pridobite predloge glede na ustrezne pogoje.</span><span class="sxs-lookup"><span data-stu-id="ba97e-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="ba97e-147">Če med predlogi ni blagovne znamke ali zanimanja, ki ga iščete, nam pošljite povratne informacije prek povezave **Predlagaj**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="ba97e-148">Pregled nastavitev obogatitve</span><span class="sxs-lookup"><span data-stu-id="ba97e-148">Review enrichment preferences</span></span>

<span data-ttu-id="ba97e-149">Preglejte privzete nastavitve obogatitve in jih po potrebi posodobite.</span><span class="sxs-lookup"><span data-stu-id="ba97e-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Posnetek zaslona okna z nastavitvami obogatitve.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="ba97e-151">Izberite entiteto za obogatitev</span><span class="sxs-lookup"><span data-stu-id="ba97e-151">Select entity to enrich</span></span>

<span data-ttu-id="ba97e-152">Izberite možnost **Obogatena entiteta** in izberite nabor podatkov, ki ga želite obogatiti s podatki podjetja družbe Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba97e-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="ba97e-153">Izberete lahko entiteto Stranka, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="ba97e-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="ba97e-154">Preslikajte polja</span><span class="sxs-lookup"><span data-stu-id="ba97e-154">Map your fields</span></span>

<span data-ttu-id="ba97e-155">Preslikajte polja iz enotne entitete stranke, da določite demografski segment, ki ga mora sistem uporabiti za obogatitev podatkov o strankah.</span><span class="sxs-lookup"><span data-stu-id="ba97e-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="ba97e-156">Preslikajte vrednosti za državo/regijo in vsaj datum rojstva ali spol.</span><span class="sxs-lookup"><span data-stu-id="ba97e-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="ba97e-157">Poleg tega morate preslikati vsaj en atribut za mesto (in državo/območje) ali poštno številko.</span><span class="sxs-lookup"><span data-stu-id="ba97e-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="ba97e-158">Izberite **Uredi**, da določite preslikavo polj, in izberite **Uporabi**, ko končate.</span><span class="sxs-lookup"><span data-stu-id="ba97e-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="ba97e-159">Izberite **Shrani** za dokončanje preslikave polj.</span><span class="sxs-lookup"><span data-stu-id="ba97e-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="ba97e-160">Podprti so naslednji formati in vrednosti; vrednosti niso občutljive na male in male črke:</span><span class="sxs-lookup"><span data-stu-id="ba97e-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="ba97e-161">**Datum rojstva**: priporočamo, da se datum rojstva med uvozom podatkov pretvori v vrsto DateTime.</span><span class="sxs-lookup"><span data-stu-id="ba97e-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="ba97e-162">Lahko pa je tudi niz v [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) oblika "yyyy-MM-dd" ali "yyyy-MM-ddTHH: mm: ssZ".</span><span class="sxs-lookup"><span data-stu-id="ba97e-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="ba97e-163">**Spol**: moški, ženska, neznano</span><span class="sxs-lookup"><span data-stu-id="ba97e-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="ba97e-164">**Poštna številka**: petmestne poštne številke za ZDA, standardne poštne številke povsod drugje</span><span class="sxs-lookup"><span data-stu-id="ba97e-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="ba97e-165">**Mesto**: ime mesta v angleščini</span><span class="sxs-lookup"><span data-stu-id="ba97e-165">**City**: City name in English</span></span>
- <span data-ttu-id="ba97e-166">**Država/provinca**: dvočrkovna okrajšava za ZDA in Kanado.</span><span class="sxs-lookup"><span data-stu-id="ba97e-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="ba97e-167">Okrajšava z dvema ali tremi črkami za Avstralijo.</span><span class="sxs-lookup"><span data-stu-id="ba97e-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="ba97e-168">Ne velja za Francijo, Nemčijo ali Združeno kraljestvo.</span><span class="sxs-lookup"><span data-stu-id="ba97e-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="ba97e-169">**Država/regija**:</span><span class="sxs-lookup"><span data-stu-id="ba97e-169">**Country/Region**:</span></span>

  - <span data-ttu-id="ba97e-170">ZDA: Združene države Amerike, Združene države, ZDA, Amerika</span><span class="sxs-lookup"><span data-stu-id="ba97e-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="ba97e-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="ba97e-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="ba97e-172">GB: Združeno kraljestvo, Velika Britanija, Združeno kraljestvo Velike Britanije in Severne Irske, Združeno kraljestvo Velike Britanije</span><span class="sxs-lookup"><span data-stu-id="ba97e-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="ba97e-173">AU: Avstralija, AU, Skupnost narodov Avstralije</span><span class="sxs-lookup"><span data-stu-id="ba97e-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="ba97e-174">FR: Francija, FR, republika Francija</span><span class="sxs-lookup"><span data-stu-id="ba97e-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="ba97e-175">DE: Nemčija, Zvezna republika Nemčija, Republika Nemčija</span><span class="sxs-lookup"><span data-stu-id="ba97e-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="ba97e-176">Pregled in poimenovanje obogatitve</span><span class="sxs-lookup"><span data-stu-id="ba97e-176">Review and name the enrichment</span></span>

<span data-ttu-id="ba97e-177">Na koncu morate pregledati podatke in navesti ime obogatitve.</span><span class="sxs-lookup"><span data-stu-id="ba97e-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stran za pregled in poimenovanje interesov.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="ba97e-179">Osvežite obogatitev</span><span class="sxs-lookup"><span data-stu-id="ba97e-179">Refresh enrichment</span></span>

<span data-ttu-id="ba97e-180">Zaženite obogatitev po tem, ko konfigurirate blagovne znamke, zanimanja in preslikavo polj za demografske skupine.</span><span class="sxs-lookup"><span data-stu-id="ba97e-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="ba97e-181">Če želite začeti postopek, na strani za konfiguracijo blagovne znamke ali zanimanja izberite **Zagon**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="ba97e-182">Poleg tega lahko pustite, da sistem samodejno zažene obogatitev kot del načrtovane osvežitve.</span><span class="sxs-lookup"><span data-stu-id="ba97e-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="ba97e-183">Glede na velikost podatkov o strankah lahko postopek obogatitve traja nekaj minut.</span><span class="sxs-lookup"><span data-stu-id="ba97e-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="ba97e-184">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="ba97e-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ba97e-185">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ba97e-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ba97e-186">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="ba97e-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ba97e-187">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="ba97e-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ba97e-188">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="ba97e-188">Enrichment results</span></span>

<span data-ttu-id="ba97e-189">Po zagonu postopka obogatitve odprite razdelek **Moje obogatitve** in preglejte skupno število obogatenih strank ter razčlenitev blagovnih znamk in zanimanj obogatenih profilih strank.</span><span class="sxs-lookup"><span data-stu-id="ba97e-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve":::

<span data-ttu-id="ba97e-191">Preglejte obogatene podatke tako, da v grafikonu izberete možnost **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="ba97e-192">Obogateni podatki za blagovne znamke so poslani v entiteto **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="ba97e-193">Podatki za zanimanje so v entiteti **InteresAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="ba97e-194">Te entitete boste našli navedene tudi v skupini **Obogatitev** v **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="ba97e-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="ba97e-195">Glejte podatke o obogatitvi na kartici stranke</span><span class="sxs-lookup"><span data-stu-id="ba97e-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="ba97e-196">Afinitete do blagovnih znamk in interesov si je mogoče ogledati tudi na posameznih karticah strank.</span><span class="sxs-lookup"><span data-stu-id="ba97e-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="ba97e-197">Odprite možnost **Stranke** in izberite profil stranke.</span><span class="sxs-lookup"><span data-stu-id="ba97e-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="ba97e-198">Na kartici stranke boste našli grafikone blagovnih znamk ali zanimanj, ki so priljubljeni pri osebah v demografskem profilu stranke.</span><span class="sxs-lookup"><span data-stu-id="ba97e-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki":::

## <a name="next-steps"></a><span data-ttu-id="ba97e-200">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="ba97e-200">Next steps</span></span>

<span data-ttu-id="ba97e-201">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="ba97e-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ba97e-202">Ustvarite [Segmente](segments.md), [Mere](measures.md) in celo [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="ba97e-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
