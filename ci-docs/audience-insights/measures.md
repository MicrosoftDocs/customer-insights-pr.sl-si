---
title: Ustvarjanje in urejanje mer
description: Določite mere, povezane s strankami, za analizo in odraz uspešnosti določenih poslovnih področij.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406990"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="be8a0-103">Določanje in upravljanje mer</span><span class="sxs-lookup"><span data-stu-id="be8a0-103">Define and manage measures</span></span>

<span data-ttu-id="be8a0-104">**Mere** predstavljajo ključne kazalnike uspešnosti (KPI), ki odražajo uspešnost in stanje določenih poslovnih področij.</span><span class="sxs-lookup"><span data-stu-id="be8a0-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="be8a0-105">Vpogledi v občinstvo ponujajo intuitivno izkušnjo za ustvarjanje različnih vrst mer z uporabo graditelja poizvedb, ki ne zahteva ročnega kodiranja ali preverjanja veljavnosti mer.</span><span class="sxs-lookup"><span data-stu-id="be8a0-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="be8a0-106">Na strani **Osnovno** lahko spremljate svoje poslovne mere, na strani **Kartica stranke** si lahko ogledate mere za določeno stranko, na strani **Segmenti** pa lahko uporabite mere za opredelitev segmentov stranke.</span><span class="sxs-lookup"><span data-stu-id="be8a0-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="be8a0-107">Ustvarjanje mere</span><span class="sxs-lookup"><span data-stu-id="be8a0-107">Create a measure</span></span>

<span data-ttu-id="be8a0-108">V tem razdelku so navodila za ustvarjanje mere povsem od začetka.</span><span class="sxs-lookup"><span data-stu-id="be8a0-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="be8a0-109">Mere lahko ustvarite s podatki iz več virov podatkov, ki so povezani prek entitete stranke.</span><span class="sxs-lookup"><span data-stu-id="be8a0-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="be8a0-110">Veljajo nekatere [omejitve storitev](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="be8a0-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="be8a0-111">Pri vpogledih v občinstvo izberite **Mere**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="be8a0-112">Izberite **Nova mera**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-112">Select **New measure**.</span></span>

3. <span data-ttu-id="be8a0-113">Izberite **vrsto** mere:</span><span class="sxs-lookup"><span data-stu-id="be8a0-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="be8a0-114">**Atribut stranke**: eno polje na stranko, ki odraža rezultat, vrednost ali stanje za stranko.</span><span class="sxs-lookup"><span data-stu-id="be8a0-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="be8a0-115">Atributi strank so ustvarjeni kot atributi v novi sistemski entiteti, imenovani **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="be8a0-116">**Mera stranke**: vpogledi v vedenje stranke z razčlenitvijo po izbranih dimenzijah.</span><span class="sxs-lookup"><span data-stu-id="be8a0-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="be8a0-117">Za vsako mero se ustvari nova entiteta, lahko tudi z več zapisi na stranko.</span><span class="sxs-lookup"><span data-stu-id="be8a0-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="be8a0-118">**Poslovna mera**: spremlja poslovno uspešnost in stanje poslovanja.</span><span class="sxs-lookup"><span data-stu-id="be8a0-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="be8a0-119">Poslovne mere imajo lahko dva različna rezultata: številski rezultat, ki je prikazan na strani **Osnovno**, ali novo entiteto, ki jo najdete na strani **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="be8a0-120">Vnesite **ime** in po želji še **Prikazno ime** ter izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="be8a0-121">Na spustnem seznamu v razdelku **Entitete** izberite prvo entiteto.</span><span class="sxs-lookup"><span data-stu-id="be8a0-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="be8a0-122">Na tej točki se morate odločiti, ali so v okviru vaše opredelitve mere potrebne dodatne entitete.</span><span class="sxs-lookup"><span data-stu-id="be8a0-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be8a0-123">![Definicija mere](media/measure-definition.png "Definicija mere")</span><span class="sxs-lookup"><span data-stu-id="be8a0-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="be8a0-124">Če želite dodati več entitet, izberite **Dodaj entiteto** in izberite entitete, ki jih želite uporabiti za mero.</span><span class="sxs-lookup"><span data-stu-id="be8a0-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="be8a0-125">Izberite lahko samo entitete, ki imajo odnos z vašo začetno entiteto.</span><span class="sxs-lookup"><span data-stu-id="be8a0-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="be8a0-126">Če želite več informacij o opredelitvi odnosov, glejte [Odnosi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="be8a0-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="be8a0-127">Po želji lahko konfigurirate spremenljivke.</span><span class="sxs-lookup"><span data-stu-id="be8a0-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="be8a0-128">V razdelku **Spremenljivke** izberite **Nova spremenljivka**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="be8a0-129">Spremenljivke so izračuni, ki so narejeni na vsakem od vaših izbranih zapisov.</span><span class="sxs-lookup"><span data-stu-id="be8a0-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="be8a0-130">Na primer povzetek prodaje na prodajnem mestu (POS) in v spletu za vsakega od zapisov vaše stranke.</span><span class="sxs-lookup"><span data-stu-id="be8a0-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="be8a0-131">Vnesite **ime** za spremenljivko.</span><span class="sxs-lookup"><span data-stu-id="be8a0-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="be8a0-132">V območju **Izraz** izberite polje, s katerim boste začeli izračun.</span><span class="sxs-lookup"><span data-stu-id="be8a0-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="be8a0-133">Vnesite izraz v območje **Izraz** in izberite več polj, ki bodo vključena v vaš izračun.</span><span class="sxs-lookup"><span data-stu-id="be8a0-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="be8a0-134">Trenutno so podprti samo aritmetični izrazi.</span><span class="sxs-lookup"><span data-stu-id="be8a0-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="be8a0-135">Poleg tega izračun spremenljivk ni podprt za entitete z različnih [poti entitet](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="be8a0-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="be8a0-136">Izberite **Dokončano**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-136">Select **Done**.</span></span>

11. <span data-ttu-id="be8a0-137">V razdelku **Opredelitev mere** določite, kako so izbrane entitete in izračunane spremenljivke združene v novi entiteti ali atributu mere.</span><span class="sxs-lookup"><span data-stu-id="be8a0-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="be8a0-138">Izberite **Nova dimenzija**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-138">Select **New dimension**.</span></span> <span data-ttu-id="be8a0-139">Dimenzijo si lahko predstavljate kot funkcijo *združi po*.</span><span class="sxs-lookup"><span data-stu-id="be8a0-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="be8a0-140">Rezultati podatkov entitete ali atributa mere bodo združeni po vseh vaših opredeljenih dimenzijah.</span><span class="sxs-lookup"><span data-stu-id="be8a0-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="be8a0-141">![Izbira cikla združevanja](media/measures-businessreport-measure-definition2.png "Izbira cikla združevanja")</span><span class="sxs-lookup"><span data-stu-id="be8a0-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="be8a0-142">Kot del definicije dimenzije izberite ali vnesite te podatke:</span><span class="sxs-lookup"><span data-stu-id="be8a0-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="be8a0-143">**Entiteta**: če določite entiteto mere, mora vključevati vsaj en atribut.</span><span class="sxs-lookup"><span data-stu-id="be8a0-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="be8a0-144">Če določite atribut mere, bo privzeto vseboval le en atribut.</span><span class="sxs-lookup"><span data-stu-id="be8a0-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="be8a0-145">Pri tem izboru gre za izbiro entitete, ki vključuje ta atribut.</span><span class="sxs-lookup"><span data-stu-id="be8a0-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="be8a0-146">**Polje**: izberite atribut, ki bo vključen v entiteto ali atribut mere.</span><span class="sxs-lookup"><span data-stu-id="be8a0-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="be8a0-147">**Vedro**: izberite, ali želite združiti podatke na dnevni, mesečni ali letni osnovi.</span><span class="sxs-lookup"><span data-stu-id="be8a0-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="be8a0-148">Ta izbira je obvezna le, če ste izbrali atribut vrste datuma.</span><span class="sxs-lookup"><span data-stu-id="be8a0-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="be8a0-149">**Kot**: določa ime vašega novega polja.</span><span class="sxs-lookup"><span data-stu-id="be8a0-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="be8a0-150">**Prikazno ime**: določa prikazno ime vašega polja.</span><span class="sxs-lookup"><span data-stu-id="be8a0-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be8a0-151">Vaša poslovna mera bo shranjena kot entiteta z eno številko in bo prikazana na strani **Osnovno**, razen če v mero dodate več dimenzij.</span><span class="sxs-lookup"><span data-stu-id="be8a0-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="be8a0-152">Ko dodate več dimenzij, mera *ni* prikazana na strani **Domov**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="be8a0-153">Po želji dodajte funkcije združevanja.</span><span class="sxs-lookup"><span data-stu-id="be8a0-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="be8a0-154">Vsako združevanje, ki ga ustvarite, ustvari novo vrednost v entiteti ali atributu »Mere«.</span><span class="sxs-lookup"><span data-stu-id="be8a0-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="be8a0-155">Podprte funkcije združevanja so: **Min.**, **Maks.**, **Povprečno**, **Mediana**, **Vsota**, **Št. enoličnih**, **Prvi** (uporabi prvi zapis vrednosti dimenzije) in **Zadnji** (uporabi zadnji zapis, dodan v vrednost dimenzije).</span><span class="sxs-lookup"><span data-stu-id="be8a0-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="be8a0-156">Izberite **Shrani**, da uporabite spremembe v meri.</span><span class="sxs-lookup"><span data-stu-id="be8a0-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="be8a0-157">Upravljajte svoje mere</span><span class="sxs-lookup"><span data-stu-id="be8a0-157">Manage your measures</span></span>

<span data-ttu-id="be8a0-158">Ko ustvarite vsaj eno mero, boste na strani **Mere** videli seznam mer.</span><span class="sxs-lookup"><span data-stu-id="be8a0-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="be8a0-159">Na voljo so informacije o vrsti mere, ustvarjalcu, datumu in času nastanka, datumu in času zadnjega urejanja, stanju (ali je mera dejavna, nedejavna ali neuspešna) in datumu in času zadnjega osveževanja.</span><span class="sxs-lookup"><span data-stu-id="be8a0-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="be8a0-160">Ko s seznama izberete mero, si lahko ogledate njen predogled.</span><span class="sxs-lookup"><span data-stu-id="be8a0-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="be8a0-161">Če želite hkrati osvežiti vse svoje mere, izberite **Osveži vse**, ne da bi izbrali posamezno mero.</span><span class="sxs-lookup"><span data-stu-id="be8a0-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be8a0-162">![Dejanja za upravljanje posameznih mer](media/measure-actions.png "Dejanja za upravljanje posameznih mer")</span><span class="sxs-lookup"><span data-stu-id="be8a0-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="be8a0-163">S seznama lahko tudi izberete mero in opravite enega od naslednjih dejanj:</span><span class="sxs-lookup"><span data-stu-id="be8a0-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="be8a0-164">Za prikaz podrobnosti izberite ime mere.</span><span class="sxs-lookup"><span data-stu-id="be8a0-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="be8a0-165">Izberete lahko možnost **Uredi** in uredite konfiguracijo mere.</span><span class="sxs-lookup"><span data-stu-id="be8a0-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="be8a0-166">Mero lahko preimenujete prek možnosti **Preimenuj**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-166">**Rename** the measure.</span></span>
- <span data-ttu-id="be8a0-167">Za brisanje mere je na voljo **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-167">**Delete** the measure.</span></span>
- <span data-ttu-id="be8a0-168">Izberite tri pike (...) in nato **Osveži**, da začnete postopek osveževanja za mero.</span><span class="sxs-lookup"><span data-stu-id="be8a0-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="be8a0-169">Izberite tri pike (...) in nato **Prenesi**, če želite pridobiti datoteko .CSV mere.</span><span class="sxs-lookup"><span data-stu-id="be8a0-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="be8a0-170">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="be8a0-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="be8a0-171">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="be8a0-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="be8a0-172">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="be8a0-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="be8a0-173">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="be8a0-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="be8a0-174">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="be8a0-174">Next step</span></span>

<span data-ttu-id="be8a0-175">Obstoječe mere lahko uporabite za ustvarjanje prvega segmenta stranke na strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="be8a0-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="be8a0-176">Če želite več informacij, glejte [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="be8a0-176">For more information, see [Segments](segments.md).</span></span>
