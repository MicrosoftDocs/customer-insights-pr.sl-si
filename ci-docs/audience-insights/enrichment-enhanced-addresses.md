---
title: Obogatitev izboljšave naslova
description: Z Microsoftovimi modeli obogatite in uravnotežite podatke o naslovih za profile strank.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965598"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="e1682-103">Obogatitev profilov strank z izboljšanimi naslovi</span><span class="sxs-lookup"><span data-stu-id="e1682-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="e1682-104">Naslovi v vaših podatkih so lahko nestrukturirani, nepopolni ali napačni.</span><span class="sxs-lookup"><span data-stu-id="e1682-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="e1682-105">Uporabite Microsoftove modele za uravnoteženje in obogatitev naslovov v [obliki Common Data Model](/common-data-model/schema/core/applicationcommon/address) za boljšo natančnost in vpoglede.</span><span class="sxs-lookup"><span data-stu-id="e1682-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="e1682-106">Kako izboljšujemo naslove?</span><span class="sxs-lookup"><span data-stu-id="e1682-106">How we enhance addresses</span></span>

<span data-ttu-id="e1682-107">Naš model gre skozi dvostopenjski postopek za izboljšanje naslova.</span><span class="sxs-lookup"><span data-stu-id="e1682-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="e1682-108">Najprej razčleni naslov, da prepozna njegove komponente, in jih postavi v strukturirano obliko.</span><span class="sxs-lookup"><span data-stu-id="e1682-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="e1682-109">Nato z umetno inteligenco popravimo, dopolnimo in standardiziramo vrednosti v naslovu.</span><span class="sxs-lookup"><span data-stu-id="e1682-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="e1682-110">Primer</span><span class="sxs-lookup"><span data-stu-id="e1682-110">Example</span></span>

<span data-ttu-id="e1682-111">Podatki o naslovih so lahko v nestandardni obliki in vsebujejo napake v črkovanju.</span><span class="sxs-lookup"><span data-stu-id="e1682-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="e1682-112">Model lahko odpravi te težave in ustvari dosledne naslove v poenotenih profilih strank.</span><span class="sxs-lookup"><span data-stu-id="e1682-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="e1682-113">Omejitve</span><span class="sxs-lookup"><span data-stu-id="e1682-113">Limitations</span></span>

<span data-ttu-id="e1682-114">Izboljšani naslovi delujejo samo z vrednostmi, ki že obstajajo v uvoženih podatkih o naslovih.</span><span class="sxs-lookup"><span data-stu-id="e1682-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="e1682-115">Model ne izvaja naslednjega:</span><span class="sxs-lookup"><span data-stu-id="e1682-115">The model doesn't:</span></span> 

1. <span data-ttu-id="e1682-116">Ne preveri, ali je naslov veljaven.</span><span class="sxs-lookup"><span data-stu-id="e1682-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="e1682-117">Ne preveri, ali je katera od vrednosti, na primer poštne številke ali imena ulic, veljavna.</span><span class="sxs-lookup"><span data-stu-id="e1682-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="e1682-118">Ne spremeni vrednosti, ki jih ne prepozna.</span><span class="sxs-lookup"><span data-stu-id="e1682-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="e1682-119">Model za izboljšanje naslovov uporablja tehnike, ki temeljijo na strojnem učenju.</span><span class="sxs-lookup"><span data-stu-id="e1682-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="e1682-120">100-odstotna natančnost ni zagotovljena, čeprav uporabljamo visok prag zanesljivosti, ko model spremeni vhodno vrednost, tako kot pri katerem koli modelu, ki temelji na strojnem učenju.</span><span class="sxs-lookup"><span data-stu-id="e1682-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="e1682-121">Podprte države ali regije</span><span class="sxs-lookup"><span data-stu-id="e1682-121">Supported countries or regions</span></span>

<span data-ttu-id="e1682-122">Trenutno podpiramo obogatitev naslovov v teh državah ali regijah:</span><span class="sxs-lookup"><span data-stu-id="e1682-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="e1682-123">Avstralija</span><span class="sxs-lookup"><span data-stu-id="e1682-123">Australia</span></span>
- <span data-ttu-id="e1682-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="e1682-124">Canada</span></span>
- <span data-ttu-id="e1682-125">Združeno kraljestvo</span><span class="sxs-lookup"><span data-stu-id="e1682-125">United Kingdom</span></span>
- <span data-ttu-id="e1682-126">Združene države</span><span class="sxs-lookup"><span data-stu-id="e1682-126">United States</span></span>

<span data-ttu-id="e1682-127">Naslovi morajo vsebovati vrednost države/regije.</span><span class="sxs-lookup"><span data-stu-id="e1682-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="e1682-128">Ne obdelujemo naslovov za države ali regije, ki niso podprte, in naslovov, ki nimajo nobene države ali regije.</span><span class="sxs-lookup"><span data-stu-id="e1682-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e1682-129">Konfiguriranje obogatitve</span><span class="sxs-lookup"><span data-stu-id="e1682-129">Configure the enrichment</span></span>

1. <span data-ttu-id="e1682-130">Pomaknite se na možnost **Podatki** > **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="e1682-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="e1682-131">Izberite **Obogatitev podatkov** na ploščici **Izboljšani naslovi**.</span><span class="sxs-lookup"><span data-stu-id="e1682-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Posnetek zaslona ploščice Izboljšani naslovi.":::

1. <span data-ttu-id="e1682-133">Izberite možnost **Nabor podatkov o stranki** in izberite entiteto, ki vsebuje naslove, ki jih želite obogatiti.</span><span class="sxs-lookup"><span data-stu-id="e1682-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="e1682-134">Izberete lahko entiteto *Stranka* za obogatitev naslovov v vseh vaših profilih strank ali pa entiteto segmenta za obogatitev naslovov samo v profilih strank v tem segmentu.</span><span class="sxs-lookup"><span data-stu-id="e1682-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="e1682-135">Izberite način oblikovanja naslovov v naboru podatkih.</span><span class="sxs-lookup"><span data-stu-id="e1682-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="e1682-136">Izberite **Naslov z enim atributom**, če naslovi v vaših podatkih uporabljajo eno samo polje.</span><span class="sxs-lookup"><span data-stu-id="e1682-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="e1682-137">Izberite **Naslov z več atributi**, če naslovi v vaših podatkih uporabljajo več kot eno podatkovno polje.</span><span class="sxs-lookup"><span data-stu-id="e1682-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e1682-138">Država/regija je obvezna tako v naslovu z enim kot z več atributi.</span><span class="sxs-lookup"><span data-stu-id="e1682-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="e1682-139">Naslovi, ki ne vsebujejo veljavnih ali podprtih vrednosti držav/regij, ne bodo obogateni</span><span class="sxs-lookup"><span data-stu-id="e1682-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="e1682-140">Preslikajte polja z naslovi iz vaše poenotene entitete stranke.</span><span class="sxs-lookup"><span data-stu-id="e1682-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stran za preslikavo polja z izboljšanim naslovom.":::

1. <span data-ttu-id="e1682-142">Izberite možnost **Naprej**, da dokončate preslikavo polj.</span><span class="sxs-lookup"><span data-stu-id="e1682-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="e1682-143">Navedite ime obogatitve in izhodne entitete.</span><span class="sxs-lookup"><span data-stu-id="e1682-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="e1682-144">Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="e1682-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e1682-145">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="e1682-145">Enrichment results</span></span>

<span data-ttu-id="e1682-146">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="e1682-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e1682-147">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1682-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1682-148">Čas obdelave je odvisen od velikosti podatkov o stranki.</span><span class="sxs-lookup"><span data-stu-id="e1682-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="e1682-149">Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="e1682-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e1682-150">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="e1682-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e1682-151">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="e1682-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1682-152">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="e1682-152">Next steps</span></span>

<span data-ttu-id="e1682-153">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="e1682-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e1682-154">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="e1682-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
