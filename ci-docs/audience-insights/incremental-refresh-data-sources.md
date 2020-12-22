---
title: Postopno osveževanje za vire podatkov, ki temeljijo na storitvi Power Query
description: Osvežite nove in posodobljene podatke za velike vire podatkov, ki temeljijo na orodju Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406982"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="050cb-103">Postopno osveževanje za vire podatkov, ki temeljijo na orodju Power Query</span><span class="sxs-lookup"><span data-stu-id="050cb-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="050cb-104">Postopno osveževanje za vire podatkov zagotavlja naslednje prednosti:</span><span class="sxs-lookup"><span data-stu-id="050cb-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="050cb-105">**Hitrejša osveževanja** – Osvežijo se sami podatki, ki so spremenjeni.</span><span class="sxs-lookup"><span data-stu-id="050cb-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="050cb-106">Na primer, morda se osveži samo zadnjih pet dni zgodovinskega nabora podatkov.</span><span class="sxs-lookup"><span data-stu-id="050cb-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="050cb-107">**Povečana zanesljivost** – Z manjšimi osveževanji vam ni treba tako dolgo vzdrževati povezav do spremenljivih sistemov virov, zato se zmanjša tveganje za težave pri povezavi.</span><span class="sxs-lookup"><span data-stu-id="050cb-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="050cb-108">**Zmanjšana poraba sredstev** – Osveževanje samo podnabora celotnih podatkov vodi v učinkovitejšo uporabo računalniških sredstev in zmanjša okoljski odtis.</span><span class="sxs-lookup"><span data-stu-id="050cb-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="050cb-109">Konfiguriranje postopnega osveževanja</span><span class="sxs-lookup"><span data-stu-id="050cb-109">Configure incremental refresh</span></span>

<span data-ttu-id="050cb-110">Vpogledi v občinstvo omogočajo postopno osveževanje za vire podatkov, uvožene prek storitve Power Query, ki podpirajo postopen uvoz.</span><span class="sxs-lookup"><span data-stu-id="050cb-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="050cb-111">Na primer, zbirke podatkov Azure SQL s polji datuma in časa, ki označujejo, kdaj so bili podatkovni zapisi nazadnje posodobljeni.</span><span class="sxs-lookup"><span data-stu-id="050cb-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="050cb-112">[Ustvarjanje novega vira podatkov, ki temelji na orodju Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="050cb-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="050cb-113">Podajte ime vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="050cb-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="050cb-114">Izberite vir podatkov, ki podpira postopno osveževanje, kot je zbirka podatkov Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="050cb-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="050cb-115">Izberite entitete ali tabele za zaužitje.</span><span class="sxs-lookup"><span data-stu-id="050cb-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="050cb-116">Dokončajte korake pretvorbe in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="050cb-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="050cb-117">V pogovornem oknu **Nastavitev postopnega osveževanja** izberite **Nastavitev**, da odprete **Nastavitve postopnega osveževanja**.</span><span class="sxs-lookup"><span data-stu-id="050cb-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="050cb-118">Če izberete **Preskoči**, bo vir podatkov osvežil celoten nabor podatkov.</span><span class="sxs-lookup"><span data-stu-id="050cb-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="050cb-119">Postopno osveževanje lahko uporabite tudi pozneje z urejanjem obstoječega vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="050cb-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="050cb-120">V možnosti **Nastavitve postopnega osveževanja** boste konfigurirali postopno osveževanje za vse entitete, ki ste jih izbrali ob ustvarjanju vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="050cb-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="050cb-121">![Konfiguracija entitet v viru podatkov za postopno osveževanje](media/incremental-refresh-settings.png "Konfiguracija entitet v viru podatkov za postopno osveževanje")</span><span class="sxs-lookup"><span data-stu-id="050cb-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="050cb-122">Izberite entiteto in podajte naslednje podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="050cb-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="050cb-123">**Določitev primarnega ključa**: Izberite primarni ključ za entiteto ali tabelo.</span><span class="sxs-lookup"><span data-stu-id="050cb-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="050cb-124">**Določitev polja »zadnja posodobitev«**: To polje bo prikazovalo samo atribute vrste datuma ali časa.</span><span class="sxs-lookup"><span data-stu-id="050cb-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="050cb-125">Izberite atribut, ki označuje, kdaj so bili zapisi nazadnje posodobljeni.</span><span class="sxs-lookup"><span data-stu-id="050cb-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="050cb-126">Uporabil se bo za prepoznavanje zapisov, ki spadajo v časovni okvir postopnega osveževanja.</span><span class="sxs-lookup"><span data-stu-id="050cb-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="050cb-127">**Preverjanje, ali so na voljo posodobitve, in sicer na:**: Določite dolžino časovnega okvira postopnega osveževanja.</span><span class="sxs-lookup"><span data-stu-id="050cb-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="050cb-128">Izberite **Shrani** za dokončanje ustvarjanja vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="050cb-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="050cb-129">Začetno osveževanje podatkov bo popolno osveževanje.</span><span class="sxs-lookup"><span data-stu-id="050cb-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="050cb-130">Po tem se postopno osveževanje podatkov izvaja, kot je konfigurirano v prejšnjem koraku.</span><span class="sxs-lookup"><span data-stu-id="050cb-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
