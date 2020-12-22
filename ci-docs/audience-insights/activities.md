---
title: Dejavnosti stranke
description: Določite dejavnosti stranke in si jih oglejte na časovnici stranke.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667249"
---
# <a name="customer-activities"></a><span data-ttu-id="326ae-103">Dejavnosti stranke</span><span class="sxs-lookup"><span data-stu-id="326ae-103">Customer activities</span></span>

<span data-ttu-id="326ae-104">Združite dejavnosti stranke iz [različnih virov podatkov](data-sources.md) v storitvi Dynamics 365 Customer Insights, da ustvarite časovnico stranke, v katerem so njene dejavnosti navedene v kronološkem vrstnem redu.</span><span class="sxs-lookup"><span data-stu-id="326ae-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="326ae-105">Časovnico lahko vključite v aplikacije Customer Engagement v storitvi Dynamics 365 prek [dodatka za kartico stranke](customer-card-add-in.md) ali v nadzorni plošči Power BI.</span><span class="sxs-lookup"><span data-stu-id="326ae-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="326ae-106">Določanje dejavnosti</span><span class="sxs-lookup"><span data-stu-id="326ae-106">Define an activity</span></span>

<span data-ttu-id="326ae-107">Vaši viri podatkov vključujejo entitete s transakcijskimi podatki in podatki o dejavnosti iz več virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="326ae-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="326ae-108">Določite te entitete in izberite časovnice, ki si jih želite ogledati na časovnici stranke.</span><span class="sxs-lookup"><span data-stu-id="326ae-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="326ae-109">Izberite entiteto, ki vključuje vašo ciljno dejavnost ali dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="326ae-110">Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="326ae-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="326ae-111">Izberite **Dodaj dejavnost**.</span><span class="sxs-lookup"><span data-stu-id="326ae-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="326ae-112">Entiteta mora imeti vsaj en atribut vrste **Datum**, da je lahko vključena na časovnico stranke, vi pa ne morete dodajati entitet brez polja **Datum**.</span><span class="sxs-lookup"><span data-stu-id="326ae-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="326ae-113">Ukaz **Dodaj dejavnost** je onemogočen, če take entitete ni mogoče najti.</span><span class="sxs-lookup"><span data-stu-id="326ae-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="326ae-114">V podoknu **Dodaj dejavnost** nastavite vrednosti za naslednja polja:</span><span class="sxs-lookup"><span data-stu-id="326ae-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="326ae-115">**Entiteta**: izberite entiteto, ki vključuje transakcijske podatke ali podatke o dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="326ae-116">**Primarni ključ**: izberite polje, ki edinstveno določi zapis.</span><span class="sxs-lookup"><span data-stu-id="326ae-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="326ae-117">Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="326ae-118">**Časovni žig**: izberite polje, ki predstavlja začetni čas vaše dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="326ae-119">**Dogodek**: izberite polje, ki je dogodek za dejavnost.</span><span class="sxs-lookup"><span data-stu-id="326ae-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="326ae-120">**Spletni naslov**: izberite polje, ki predstavlja URL z dodatnimi informacijami o tej dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="326ae-121">Na primer transakcijski sistem, ki je vir te dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="326ae-122">Ta URL je lahko katero koli polje iz vira podatkov, lahko pa je oblikovano kot novo polje s pretvorbo v orodju Power Query.</span><span class="sxs-lookup"><span data-stu-id="326ae-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="326ae-123">Ti podatki URL-ja bodo shranjeni v entiteti Združene dejavnosti, ki jo je mogoče uporabiti na daljavo z uporabo API-jev.</span><span class="sxs-lookup"><span data-stu-id="326ae-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="326ae-124">**Podrobnosti**: po želji izberite polje, ki je dodano za dodatne podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="326ae-125">**Ikona**: po želji izberite ikono, ki predstavlja to dejavnost.</span><span class="sxs-lookup"><span data-stu-id="326ae-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="326ae-126">**Vrsta dejavnosti**: določite sklic vrste dejavnosti kot Common Data Model, ki najbolje opisuje semantično definicijo dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="326ae-127">V razdelku **Nastavitev odnosa** konfigurirajte podrobnosti, da podatke o dejavnosti povežete z ustrezno stranko.</span><span class="sxs-lookup"><span data-stu-id="326ae-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="326ae-128">![Določanje odnosa entitete](media/activities-entities-define.png "Določanje odnosa entitete")</span><span class="sxs-lookup"><span data-stu-id="326ae-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="326ae-129">**Polje entitete dejavnosti** : Izberite polje v svoji entiteti dejavnosti, ki bo uporabljeno za vzpostavitev odnosa z drugo entiteto.</span><span class="sxs-lookup"><span data-stu-id="326ae-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="326ae-130">**Entiteta stranke** : Izberite ustrezno izvorno entiteto stranke, s katero bo vaša entiteta dejavnosti v odnosu.</span><span class="sxs-lookup"><span data-stu-id="326ae-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="326ae-131">Odnose lahko vzpostavite le s tistimi izvornimi entitetami strank, ki so uporabljene v postopku poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="326ae-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="326ae-132">**Polje entitete stranke**: V tem polju je prikazan primarni ključ izvorne entitete stranke, ki je bil izbran v postopku preslikave.</span><span class="sxs-lookup"><span data-stu-id="326ae-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="326ae-133">To polje primarnega ključa v izvorni entiteti stranke se uporablja za vzpostavitev odnosa z entiteto dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="326ae-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="326ae-134">**Ime**: Če odnos med to entiteto dejavnosti in izbrano izvorno entiteto stranke že obstaja, bo ime odnosa na voljo v načinu samo za branje.</span><span class="sxs-lookup"><span data-stu-id="326ae-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="326ae-135">Če odnos ne obstaja, se ustvari nov odnos s tukaj navedenim imenom.</span><span class="sxs-lookup"><span data-stu-id="326ae-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="326ae-136">Če želite uporabiti spremembe, izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="326ae-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="326ae-137">Na strani **Dejavnosti** izberite **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="326ae-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="326ae-138">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="326ae-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="326ae-139">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="326ae-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="326ae-140">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="326ae-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="326ae-141">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="326ae-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="326ae-142">Urejanje dejavnosti</span><span class="sxs-lookup"><span data-stu-id="326ae-142">Edit an activity</span></span>

1. <span data-ttu-id="326ae-143">Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="326ae-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="326ae-144">Izberite entiteto dejavnosti, ki jo želite urediti, in izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="326ae-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="326ae-145">Lahko pa se s kazalcem miške pomaknete na vrstico entitete in izberete ikono **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="326ae-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="326ae-146">Kliknite ikono **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="326ae-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="326ae-147">V podoknu **Uredi dejavnost** posodobite vrednosti in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="326ae-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="326ae-148">Na strani **Dejavnosti** izberite **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="326ae-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="326ae-149">Brisanje dejavnosti</span><span class="sxs-lookup"><span data-stu-id="326ae-149">Delete an activity</span></span>

1. <span data-ttu-id="326ae-150">Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="326ae-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="326ae-151">Izberite entiteto dejavnosti, ki jo želite odstraniti, in izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="326ae-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="326ae-152">Lahko pa se s kazalcem miške pomaknete na vrstico entitete in izberete ikono **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="326ae-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="326ae-153">Poleg tega lahko hkrati izberete več entitet dejavnosti, ki jih želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="326ae-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="326ae-154">![Urejanje ali brisanje odnosa entitete](media/activities-entities-edit-delete.png "Urejanje ali brisanje odnosa entitete")</span><span class="sxs-lookup"><span data-stu-id="326ae-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="326ae-155">Izberite ikono **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="326ae-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="326ae-156">Potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="326ae-156">Confirm your deletion.</span></span>
