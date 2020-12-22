---
title: Združevanje entitet za poenotenje podatkov
description: Združite entitete za ustvarjanje poenotenih profilov strank.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406987"
---
# <a name="merge-entities"></a><span data-ttu-id="58912-103">Združevanje entitet</span><span class="sxs-lookup"><span data-stu-id="58912-103">Merge entities</span></span>

<span data-ttu-id="58912-104">Faza spajanja je zadnja faza v postopku poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="58912-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="58912-105">Njen namen je uskladitev podatkov v sporu.</span><span class="sxs-lookup"><span data-stu-id="58912-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="58912-106">Primer podatkov v sporu je na primer ime stranke, ki ga najdemo v dveh zbirkah podatkov, vendar je v vsaki prikazan nekoliko drugače (»Grant Marshall« v primerjavi z »Grant Marshal«), ali telefonska številka, ki se razlikuje v obliki zapisa (617-803-091X v primerjavi s 617803091X).</span><span class="sxs-lookup"><span data-stu-id="58912-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="58912-107">Spajanje teh podatkovnih točk v sporu poteka na osnovi »atribut za atributom«.</span><span class="sxs-lookup"><span data-stu-id="58912-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="58912-108">Po zaključku [faze ujemanja](match-entities.md) fazo spajanja začnete tako, da izberete ploščico **Spajanje** na strani **Poenotenje**.</span><span class="sxs-lookup"><span data-stu-id="58912-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="58912-109">Pregled priporočil sistema</span><span class="sxs-lookup"><span data-stu-id="58912-109">Review system recommendations</span></span>

<span data-ttu-id="58912-110">Na strani **Spajanje** izberete in izključite atribute, ki jih je treba spojiti v entiteti poenotenega profila stranke (rezultat postopka konfiguracije).</span><span class="sxs-lookup"><span data-stu-id="58912-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="58912-111">Sistem samodejno spoji nekatere atribute.</span><span class="sxs-lookup"><span data-stu-id="58912-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="58912-112">Prikaz spojenih atributov</span><span class="sxs-lookup"><span data-stu-id="58912-112">View merged attributes</span></span>

<span data-ttu-id="58912-113">Če si želite ogledati atribute, ki so vključeni v enega od samodejno spojenih atributov, izberite spojen atribut.</span><span class="sxs-lookup"><span data-stu-id="58912-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="58912-114">Atributa, ki sestavljata ta spojeni atribut, sta prikazana v dveh novih vrsticah pod spojenim atributom.</span><span class="sxs-lookup"><span data-stu-id="58912-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="58912-115">![Izbira spojenega atributa](media/configure-data-merge-profile-attributes.png "Izbira spojenega atributa")</span><span class="sxs-lookup"><span data-stu-id="58912-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="58912-116">Ločevanje spojenih atributov</span><span class="sxs-lookup"><span data-stu-id="58912-116">Separate merged attributes</span></span>

<span data-ttu-id="58912-117">Če želite ločiti oz. razdružiti samodejno spojene atribute, poiščite atribut v tabeli **Atributi profila**.</span><span class="sxs-lookup"><span data-stu-id="58912-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="58912-118">Izberite gumb treh pik (...).</span><span class="sxs-lookup"><span data-stu-id="58912-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="58912-119">V spustnem seznamu izberite **Loči polja**.</span><span class="sxs-lookup"><span data-stu-id="58912-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="58912-120">Odstranjevanje spojenih atributov</span><span class="sxs-lookup"><span data-stu-id="58912-120">Remove merged attributes</span></span>

<span data-ttu-id="58912-121">Če želite izključiti atribut iz entitete končnega profila stranke, ga poiščite v tabeli **Atributi profila**.</span><span class="sxs-lookup"><span data-stu-id="58912-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="58912-122">Izberite gumb treh pik (...).</span><span class="sxs-lookup"><span data-stu-id="58912-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="58912-123">V spustnem seznamu izberite **Ne spoji**.</span><span class="sxs-lookup"><span data-stu-id="58912-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="58912-124">Atribut je premaknjen v razdelek **Odstranjeno iz zapisa stranke**.</span><span class="sxs-lookup"><span data-stu-id="58912-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="58912-125">Ročno dodajanje spojenega atributa</span><span class="sxs-lookup"><span data-stu-id="58912-125">Manually add a merged attribute</span></span>

<span data-ttu-id="58912-126">Če želite dodati spojeni atribut, pojdite na stran **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="58912-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="58912-127">Izberite **Dodaj spojeni atribut**.</span><span class="sxs-lookup"><span data-stu-id="58912-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="58912-128">Vnesite **ime**, da ga boste pozneje prepoznali na strani **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="58912-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="58912-129">Vnesete lahko tudi **Prikazno ime**, ki bo prikazano v entiteti poenotenega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="58912-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="58912-130">Konfigurirajte možnost **Izberi podvojene atribute**, da izberete atribute, ki jih želite spojiti iz ujemajočih se entitet.</span><span class="sxs-lookup"><span data-stu-id="58912-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="58912-131">Atribute lahko tudi poiščete.</span><span class="sxs-lookup"><span data-stu-id="58912-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="58912-132">Nastavite **Uvrstitev po pomembnosti** za prednostno obravnavanje določenega atributa pred drugimi.</span><span class="sxs-lookup"><span data-stu-id="58912-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="58912-133">Če entiteta *WebAccountCSV* vključuje najbolj natančne podatke o atributu *Polna imena*, lahko prednostno obravnavate to entiteto pred entiteto *ContactCSV* tako, da izberete *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="58912-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="58912-134">Entiteta *WebAccountCSV* tako postane prva prioriteta, entiteta *ContactCSV* pa druga prioriteta pri klicanju vrednosti za atribut *Polno ime*.</span><span class="sxs-lookup"><span data-stu-id="58912-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="58912-135">Zagon spajanja</span><span class="sxs-lookup"><span data-stu-id="58912-135">Run your merge</span></span>

<span data-ttu-id="58912-136">Ne glede na to, ali atribute spajate ročno ali jih spoji sistem, lahko vedno zaženete spajanje.</span><span class="sxs-lookup"><span data-stu-id="58912-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="58912-137">Za začetek postopka izberite **Zaženi** na strani **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="58912-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="58912-138">![Shranjevanje in zagon spajanja podatkov](media/configure-data-merge-save-run.png "Shranjevanje in zagon spajanja podatkov")</span><span class="sxs-lookup"><span data-stu-id="58912-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="58912-139">Če želite vnesti dodatne spremembe in ponovno zagnati korak, lahko prekličete spajanje v teku.</span><span class="sxs-lookup"><span data-stu-id="58912-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="58912-140">Izberite **Osveževanje ...**, nato pa **Prekliči posel** v stranskem podoknu, ki se prikaže.</span><span class="sxs-lookup"><span data-stu-id="58912-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="58912-141">Po tem, ko se napis **Osveževanje ...** se spremeni v **Uspešno**, je spajanje dokončalo in razrešilo nasprotja v vaših podatkih v skladu z določenimi pravilniki.</span><span class="sxs-lookup"><span data-stu-id="58912-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="58912-142">Spojeni in nespojeni atributi so vključeni v entiteto poenotenega profila.</span><span class="sxs-lookup"><span data-stu-id="58912-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="58912-143">Izključeni atributi niso vključeni v entiteto poenotenega profila.</span><span class="sxs-lookup"><span data-stu-id="58912-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="58912-144">Če to vaša prva uspešna izvedba spajanja, se bodo vsi nadaljnji postopki, vključno z obogatitvijo, segmentacijo in merami, samodejno znova zagnali.</span><span class="sxs-lookup"><span data-stu-id="58912-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="58912-145">Po ponovnem zagonu vseh nadaljnjih postopkov bodo v profilih strank prikazane vaše spremembe.</span><span class="sxs-lookup"><span data-stu-id="58912-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="58912-146">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="58912-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="58912-147">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="58912-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="58912-148">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="58912-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="58912-149">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="58912-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="58912-150">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="58912-150">Next Step</span></span>

<span data-ttu-id="58912-151">Za pridobitev več vpogledov v stranke konfigurirajte možnosti [Dejavnosti](activities.md), [Obogatitev](enrichment-microsoft-graph.md) ali [Odnosi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="58912-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="58912-152">Če ste že konfigurirali dejavnosti, obogatitev ali odnose ali če ste opredelili segmente, bodo samodejno obdelani za uporabo najnovejših podatkov strank.</span><span class="sxs-lookup"><span data-stu-id="58912-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


