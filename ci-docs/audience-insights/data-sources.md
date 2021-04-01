---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595967"
---
# <a name="data-sources-overview"></a><span data-ttu-id="44fc3-103">Pregled virov podatkov</span><span class="sxs-lookup"><span data-stu-id="44fc3-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="44fc3-104">Zmogljivost vpogledov v občinstvo v storitvi Dynamics 365 Customer Insights se poveže s podatki iz širokega nabora virov.</span><span class="sxs-lookup"><span data-stu-id="44fc3-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="44fc3-105">Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*.</span><span class="sxs-lookup"><span data-stu-id="44fc3-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="44fc3-106">Po zaužitju podatkov lahko jih lahko [poenotite](data-unification.md) in jih uporabite.</span><span class="sxs-lookup"><span data-stu-id="44fc3-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="44fc3-107">Dodajanje vira podatkov</span><span class="sxs-lookup"><span data-stu-id="44fc3-107">Add a data source</span></span>

<span data-ttu-id="44fc3-108">Glejte podrobne članke o tem, kako dodati vir podatkov, odvisno od tega, katero možnost izberete.</span><span class="sxs-lookup"><span data-stu-id="44fc3-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="44fc3-109">Vir podatkov lahko dodate na tri glavne načine:</span><span class="sxs-lookup"><span data-stu-id="44fc3-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="44fc3-110">S pomočjo številnih priključkov Power Query</span><span class="sxs-lookup"><span data-stu-id="44fc3-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="44fc3-111">Iz mape Common Data Model</span><span class="sxs-lookup"><span data-stu-id="44fc3-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="44fc3-112">Iz svojega jezera storitve Common Data Service</span><span class="sxs-lookup"><span data-stu-id="44fc3-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="44fc3-113">Podatkov iz virov podatkov na mestu uporabe še ne morete dodati.</span><span class="sxs-lookup"><span data-stu-id="44fc3-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="44fc3-114">Pregled zaužitih podatkov</span><span class="sxs-lookup"><span data-stu-id="44fc3-114">Review ingested data</span></span>

<span data-ttu-id="44fc3-115">Videli boste ime vsakega zaužitega vira podatkov, njegovo stanje in čas, ko so bili podatki za ta vir nazadnje osveženi.</span><span class="sxs-lookup"><span data-stu-id="44fc3-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="44fc3-116">Seznam virov podatkov lahko razvrstite po vseh stolpcih.</span><span class="sxs-lookup"><span data-stu-id="44fc3-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44fc3-117">![Vir podatkov je dodan](media/configure-data-datasource-added.png "Vir podatkov je dodan")</span><span class="sxs-lookup"><span data-stu-id="44fc3-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="44fc3-118">Stanje</span><span class="sxs-lookup"><span data-stu-id="44fc3-118">Status</span></span>  |<span data-ttu-id="44fc3-119">Opis</span><span class="sxs-lookup"><span data-stu-id="44fc3-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="44fc3-120">Uspelo</span><span class="sxs-lookup"><span data-stu-id="44fc3-120">Successful</span></span>   |<span data-ttu-id="44fc3-121">Vir podatkov je bil uspešno vključen, če je čas omenjen v stolpcu **Osveženo**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="44fc3-122">Ni začeto</span><span class="sxs-lookup"><span data-stu-id="44fc3-122">Not started</span></span>   |<span data-ttu-id="44fc3-123">Vir podatkov še nima vključenih podatkov ali je še v načinu osnutka.</span><span class="sxs-lookup"><span data-stu-id="44fc3-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="44fc3-124">Osveževanje</span><span class="sxs-lookup"><span data-stu-id="44fc3-124">Refreshing</span></span>    |<span data-ttu-id="44fc3-125">Uvažanje podatkov je v teku.</span><span class="sxs-lookup"><span data-stu-id="44fc3-125">Data ingestion is in progress.</span></span> <span data-ttu-id="44fc3-126">Ta postopek lahko prekličete tako, da v stolpcu **Dejanja** izberete **Ustavi osveževanje**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="44fc3-127">Ustavitev osveževanja vira podatkov bo povrnjena na zadnje stanje osveževanja.</span><span class="sxs-lookup"><span data-stu-id="44fc3-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="44fc3-128">Neuspelo</span><span class="sxs-lookup"><span data-stu-id="44fc3-128">Failed</span></span>     |<span data-ttu-id="44fc3-129">Pri uvozu podatkov je prišlo do napak.</span><span class="sxs-lookup"><span data-stu-id="44fc3-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="44fc3-130">Če si želite ogledati več podrobnosti, izberite vrednost stolpca **Stanje** katerega koli vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="44fc3-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="44fc3-131">V podoknu **Podrobnosti o napredku** razširite možnost **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="44fc3-132">Izberite možnost **Prikaži podrobnosti** za pregled več podrobnosti o stanju osveževanja, vključno s podrobnostmi o napakah in posodobitvami nadaljnjih postopkov.</span><span class="sxs-lookup"><span data-stu-id="44fc3-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="44fc3-133">Nalaganje podatkov lahko traja nekaj časa.</span><span class="sxs-lookup"><span data-stu-id="44fc3-133">Loading data can take some time.</span></span> <span data-ttu-id="44fc3-134">Po uspešni osvežitvi je mogoče uvožene podatke pregledati na strani **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="44fc3-135">Za več informacij glejte [Entitete](entities.md).</span><span class="sxs-lookup"><span data-stu-id="44fc3-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="44fc3-136">Osveževanje vira podatkov</span><span class="sxs-lookup"><span data-stu-id="44fc3-136">Refresh a data source</span></span>

<span data-ttu-id="44fc3-137">Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo.</span><span class="sxs-lookup"><span data-stu-id="44fc3-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="44fc3-138">Izberite **Skrbnik** > **Sistem** > [**Načrtovanje**](system.md#schedule-tab) za konfiguriranje načrtovanih osvežitev vseh vključenih virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="44fc3-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="44fc3-139">Če želite osvežiti vir podatkov na zahtevo, sledite tem korakom:</span><span class="sxs-lookup"><span data-stu-id="44fc3-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="44fc3-140">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="44fc3-141">Izberite navpične tri pike poleg vira podatkov, ki ga želite osvežiti, in izberite **Osveži** s spustnega seznama.</span><span class="sxs-lookup"><span data-stu-id="44fc3-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="44fc3-142">Vir podatkov se zdaj sproži za ročno osvežitev.</span><span class="sxs-lookup"><span data-stu-id="44fc3-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="44fc3-143">Če osvežite vir podatkov, boste posodobili tako shemo entitet kot tudi podatke za vse entitete, določene v viru podatkov.</span><span class="sxs-lookup"><span data-stu-id="44fc3-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="44fc3-144">Izberite **Ustavi osveževanje**, če želite preklicati obstoječo osvežitev, in se bo vir podatkov vrnil na zadnje stanje osveževanja.</span><span class="sxs-lookup"><span data-stu-id="44fc3-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="44fc3-145">Brisanje vira podatkov</span><span class="sxs-lookup"><span data-stu-id="44fc3-145">Delete a data source</span></span>

1. <span data-ttu-id="44fc3-146">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="44fc3-147">Izberite navpične tri pike poleg vira podatkov, ki ga želite odstraniti, in na spustnem meniju izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="44fc3-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="44fc3-148">Potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="44fc3-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]