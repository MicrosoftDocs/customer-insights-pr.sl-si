---
title: Vključitev podatkov prek povezovalnika Power Query
description: Povezovalniki za podatkovne vire, ki temeljijo na Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406971"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="9b288-103">Povezava z virom podatkov Power Query</span><span class="sxs-lookup"><span data-stu-id="9b288-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="9b288-104">Power Query ponuja širok nabor povezovalnikov za uvoz podatkov.</span><span class="sxs-lookup"><span data-stu-id="9b288-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="9b288-105">Dynamics 365 Customer Insights podpira večino teh povezovalnikov.</span><span class="sxs-lookup"><span data-stu-id="9b288-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="9b288-106">Dodajanje virov podatkov na podlagi povezovalnikov Power Query običajno sledi korakom, opisanim v naslednjem razdelku.</span><span class="sxs-lookup"><span data-stu-id="9b288-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="9b288-107">Vendar pa so glede na povezovalnik, ki ga uporabljate, potrebne drugačne informacije.</span><span class="sxs-lookup"><span data-stu-id="9b288-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="9b288-108">Za več informacij glejte dokumentacijo o posameznih povezovalnikih v [sklicih na povezovalnike Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="9b288-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="9b288-109">Ustvarjanje novega vira podatkov</span><span class="sxs-lookup"><span data-stu-id="9b288-109">Create a new data source</span></span>

1. <span data-ttu-id="9b288-110">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="9b288-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="9b288-111">Izberite **Dodaj vir podatkov**.</span><span class="sxs-lookup"><span data-stu-id="9b288-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="9b288-112">Izberite način **Uvozi podatke** in nato **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="9b288-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="9b288-113">Vnesite **Ime** za vir podatkov in izberite **Naprej**, da ustvarite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="9b288-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="9b288-114">Izberite enega od [razpoložljivih povezovalnikov](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="9b288-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="9b288-115">Za ta primer izberemo povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9b288-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9b288-116">Vnesite zahtevane podrobnosti v **Nastavitve povezave** za izbrani povezovalnik in izberite **Naprej**, da si ogledate predogled podatkov.</span><span class="sxs-lookup"><span data-stu-id="9b288-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="9b288-117">Izberite **Pretvori podatke**.</span><span class="sxs-lookup"><span data-stu-id="9b288-117">Select **Transform data**.</span></span> <span data-ttu-id="9b288-118">V tem koraku boste dodali entitete v vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="9b288-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="9b288-119">Entitete so nabori podatkov.</span><span class="sxs-lookup"><span data-stu-id="9b288-119">Entities are datasets.</span></span> <span data-ttu-id="9b288-120">Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.</span><span class="sxs-lookup"><span data-stu-id="9b288-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="9b288-121">Pogovorno okno **Power Query - Urejanje poizvedb** omogoča pregled in natančnejše določanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="9b288-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="9b288-122">Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.</span><span class="sxs-lookup"><span data-stu-id="9b288-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b288-123">![Pogovorno okno urejanja poizvedb](media/data-manager-configure-edit-queries.png "Pogovorno okno urejanja poizvedb")</span><span class="sxs-lookup"><span data-stu-id="9b288-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="9b288-124">Podatke pa lahko tudi preoblikujete.</span><span class="sxs-lookup"><span data-stu-id="9b288-124">You can also transform your data.</span></span> <span data-ttu-id="9b288-125">Izberite entiteto, ki jo želite urediti ali preoblikovati.</span><span class="sxs-lookup"><span data-stu-id="9b288-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="9b288-126">Uporabite možnosti v oknu Power Query, da uporabite pretvorbe.</span><span class="sxs-lookup"><span data-stu-id="9b288-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="9b288-127">Vsaka pretvorba je navedena pod **Uporabljeni koraki**.</span><span class="sxs-lookup"><span data-stu-id="9b288-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="9b288-128">Power Query ponuja številne vnaprej vgrajene možnosti preoblikovanja.</span><span class="sxs-lookup"><span data-stu-id="9b288-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="9b288-129">Če želite več informacij, glejte razdelek [Pretvorbe Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="9b288-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="9b288-130">Virom podatkov lahko dodate dodatne entitete tako, da izberete **Pridobi podatke** v pogovornem oknu **Urejanje poizvedb**.</span><span class="sxs-lookup"><span data-stu-id="9b288-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="9b288-131">Ta preoblikovanja so zelo priporočljiva:</span><span class="sxs-lookup"><span data-stu-id="9b288-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="9b288-132">Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave.</span><span class="sxs-lookup"><span data-stu-id="9b288-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="9b288-133">Pojdite na **Tabela pretvorb** in izberite **Uporabi glave kot prvo vrstico**.</span><span class="sxs-lookup"><span data-stu-id="9b288-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="9b288-134">Prepričajte se, da je vrsta podatkov pravilno nastavljena.</span><span class="sxs-lookup"><span data-stu-id="9b288-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="9b288-135">Izberite **Shrani** na dnu okna Power Query, da shranite pretvorbe.</span><span class="sxs-lookup"><span data-stu-id="9b288-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="9b288-136">Po shranjevanju boste našli svoj vir podatkov pod **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="9b288-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="9b288-137">Na strani **Viri podatkov** boste opazili, da ima nov vir podatkov stanje **Osveževanje**.</span><span class="sxs-lookup"><span data-stu-id="9b288-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="9b288-138">Razpoložljivi viri podatkov Power Query</span><span class="sxs-lookup"><span data-stu-id="9b288-138">Available Power Query data sources</span></span>

<span data-ttu-id="9b288-139">Glejte [sklicevanje na povezovalnik Power Query](https://docs.microsoft.com/power-query/connectors/) za posodobljen seznam povezovalnikov, ki jih lahko izberete za uvoz podatkov v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9b288-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="9b288-140">Povezovalniki s kljukico v stolpcu **Customer Insights (podatkovni toki)** so na voljo za ustvarjanje novih virov podatkov, ki temeljijo na Power Query.</span><span class="sxs-lookup"><span data-stu-id="9b288-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="9b288-141">Preglejte dokumentacijo določenega povezovalnika, če želite izvedeti več o njegovih predpogojih, omejitvah in drugih podrobnostih.</span><span class="sxs-lookup"><span data-stu-id="9b288-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="9b288-142">Urejanje virov podatkov Power Query</span><span class="sxs-lookup"><span data-stu-id="9b288-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="9b288-143">Morda ne bo mogoče spreminjati virov podatkov, ki se trenutno uporabljajo v enem od procesov aplikacije (na primer *segmentacija*, *ujemanje* ali *spajanje*).</span><span class="sxs-lookup"><span data-stu-id="9b288-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="9b288-144">Na strani **Nastavitve** lahko spremljate potek posameznih dejavnih procesov.</span><span class="sxs-lookup"><span data-stu-id="9b288-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="9b288-145">Ko se proces zaključi, se lahko vrnete na stran **Viri podatkov** in opravite spremembe.</span><span class="sxs-lookup"><span data-stu-id="9b288-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="9b288-146">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="9b288-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9b288-147">Izberite navpične tri pike poleg vira podatkov, ki ga želite spremeniti, in na spustnem meniju izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="9b288-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b288-148">![Možnost urejanja](media/edit-option-data-sources.png "Možnost urejanja")</span><span class="sxs-lookup"><span data-stu-id="9b288-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="9b288-149">Uporabite svoje spremembe in pretvorbe v pogovornem oknu **Power Query - Urejanje poizvedb**, kot je opisano v razdelku [Ustvari nov vir podatkov](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="9b288-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="9b288-150">Izberite **Shrani** v Power Query po zaključitvi sprememb, da shranite spremembe.</span><span class="sxs-lookup"><span data-stu-id="9b288-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
