---
title: Entitete in nabori podatkov
description: Oglejte si podatke na strani Entitete.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049414"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="7bef9-103">Entitete pri vpogledih v občinstvo</span><span class="sxs-lookup"><span data-stu-id="7bef9-103">Entities in audience insights</span></span>

<span data-ttu-id="7bef9-104">Po [konfiguraciji virov podatkov](data-sources.md) pojdite na stran **Entitete**, da ocenite kakovost uvoženih podatkov.</span><span class="sxs-lookup"><span data-stu-id="7bef9-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="7bef9-105">Entitete se štejejo za nabore podatkov.</span><span class="sxs-lookup"><span data-stu-id="7bef9-105">Entities are considered datasets.</span></span> <span data-ttu-id="7bef9-106">Več zmožnosti storitve Dynamics 365 Customer Insights je ustvarjenih v povezavi s temi entitetami.</span><span class="sxs-lookup"><span data-stu-id="7bef9-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="7bef9-107">Njihov natančen pregled vam lahko pomaga preveriti veljavnost rezultatov teh zmogljivosti.</span><span class="sxs-lookup"><span data-stu-id="7bef9-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="7bef9-108">Na strani **Entitete** so navedene entitete, vključuje pa tudi več stolpcev:</span><span class="sxs-lookup"><span data-stu-id="7bef9-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="7bef9-109">**Ime**: ime vaše entitete podatkov.</span><span class="sxs-lookup"><span data-stu-id="7bef9-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="7bef9-110">Če poleg imena entitete vidite opozorilni simbol, to pomeni, da se podatki za to entiteto niso uspešno naložili.</span><span class="sxs-lookup"><span data-stu-id="7bef9-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="7bef9-111">**Vir**: vrsta vira podatkov, v katerega je uvožena entiteta</span><span class="sxs-lookup"><span data-stu-id="7bef9-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="7bef9-112">**Ustvaril/-a**: ime osebe, ki je ustvarila entiteto.</span><span class="sxs-lookup"><span data-stu-id="7bef9-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="7bef9-113">**Ustvarjeno**: datum in ura nastanka entitete.</span><span class="sxs-lookup"><span data-stu-id="7bef9-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="7bef9-114">**Posodobil/-a**: ime osebe, ki je posodobila entiteto.</span><span class="sxs-lookup"><span data-stu-id="7bef9-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="7bef9-115">**Zadnja posodobitev**: datum in ura zadnje posodobitve entitete.</span><span class="sxs-lookup"><span data-stu-id="7bef9-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="7bef9-116">**Zadnja osvežitev**: datum in ura zadnje osvežitve podatkov.</span><span class="sxs-lookup"><span data-stu-id="7bef9-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="7bef9-117">Raziskovanje podatkov določene entitete</span><span class="sxs-lookup"><span data-stu-id="7bef9-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="7bef9-118">Izberite entiteto za raziskovanje različnih polj in zapisov, vključenih v to entiteto.</span><span class="sxs-lookup"><span data-stu-id="7bef9-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7bef9-119">![Izberite entiteto](media/data-manager-entities-data.png "Izbira entitete")</span><span class="sxs-lookup"><span data-stu-id="7bef9-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="7bef9-120">Zavihek **Podatki** prikazuje tabelo s podrobnostmi o posameznih zapisih entitete.</span><span class="sxs-lookup"><span data-stu-id="7bef9-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7bef9-121">![Tabela s polji](media/data-manager-entities-fields.PNG "Tabela s polji")</span><span class="sxs-lookup"><span data-stu-id="7bef9-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="7bef9-122">Zavihek **Atributi** je privzeto izbran in prikazuje tabelo za pregled podrobnosti za izbrano entiteto, kot so imena polj, vrste podatkov in vrste.</span><span class="sxs-lookup"><span data-stu-id="7bef9-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="7bef9-123">V stolpcu **Vrste** so prikazane vrste, povezane z modelom Common Data Model, ki jih sistem samodejno identificira ali jih uporabniki [ročno preslikajo](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="7bef9-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="7bef9-124">To so semantične vrste, ki se lahko razlikujejo od vrst podatkov atributov – na primer spodnje polje *E-pošta* ima vrsto podatkov *Besedilo*, vendar je lahko njena (semantična) vrsta za Common Data Model *E-pošta* ali *E-poštni naslov*.</span><span class="sxs-lookup"><span data-stu-id="7bef9-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="7bef9-125">Obe tabeli prikazujeta samo vzorec podatkov vaše entitete.</span><span class="sxs-lookup"><span data-stu-id="7bef9-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="7bef9-126">Če si želite ogledati celoten nabor podatkov, pojdite na stran **Viri podatkov**, izberite entiteto, izberite **Uredi**, nato pa si oglejte podatke te entitete z urejevalnikom Power Query, kot je pojasnjeno v temi [Viri podatkov](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7bef9-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="7bef9-127">Če želite izvedeti več o podatkih, uvoženih v entiteto, vam stolpec **Povzetek** zagotavlja nekatere pomembne značilnosti podatkov, kot so vrednosti nič, manjkajoče vrednosti, edinstvene vrednosti, števila in porazdelitve, kot je primerno za vaše podatke.</span><span class="sxs-lookup"><span data-stu-id="7bef9-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="7bef9-128">Izberite ikono grafikona, če želite videti povzetek podatkov.</span><span class="sxs-lookup"><span data-stu-id="7bef9-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7bef9-129">![Simbol povzetka](media/data-manager-entities-summary.png "Tabela s povzetkom podatkov")</span><span class="sxs-lookup"><span data-stu-id="7bef9-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="7bef9-130">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="7bef9-130">Next step</span></span>

<span data-ttu-id="7bef9-131">Glejte temo [Poenotenje](data-unification.md), če želite izvedeti več o *preslikavi*, *ujemanju* in *spajanju* uvoženih podatkov.</span><span class="sxs-lookup"><span data-stu-id="7bef9-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
