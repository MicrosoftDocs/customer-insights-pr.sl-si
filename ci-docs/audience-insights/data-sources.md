---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887914"
---
# <a name="data-sources-overview"></a><span data-ttu-id="37fee-103">Pregled virov podatkov</span><span class="sxs-lookup"><span data-stu-id="37fee-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="37fee-104">Zmogljivost vpogledov v občinstvo v storitvi Dynamics 365 Customer Insights se poveže s podatki iz širokega nabora virov.</span><span class="sxs-lookup"><span data-stu-id="37fee-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="37fee-105">Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*.</span><span class="sxs-lookup"><span data-stu-id="37fee-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="37fee-106">Po zaužitju podatkov lahko jih lahko [poenotite](data-unification.md) in jih uporabite.</span><span class="sxs-lookup"><span data-stu-id="37fee-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="37fee-107">Dodajanje vira podatkov</span><span class="sxs-lookup"><span data-stu-id="37fee-107">Add a data source</span></span>

<span data-ttu-id="37fee-108">Glejte podrobne članke o tem, kako dodati vir podatkov, odvisno od tega, katero možnost izberete.</span><span class="sxs-lookup"><span data-stu-id="37fee-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="37fee-109">Vir podatkov lahko dodate na tri glavne načine:</span><span class="sxs-lookup"><span data-stu-id="37fee-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="37fee-110">S pomočjo številnih priključkov Power Query</span><span class="sxs-lookup"><span data-stu-id="37fee-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="37fee-111">Iz mape Common Data Model</span><span class="sxs-lookup"><span data-stu-id="37fee-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="37fee-112">Iz svojega jezera storitve Common Data Service</span><span class="sxs-lookup"><span data-stu-id="37fee-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="37fee-113">Dodajanje podatkov iz virov podatkov na mestu uporabe</span><span class="sxs-lookup"><span data-stu-id="37fee-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="37fee-114">Uvoz podatkov iz virov podatkov na mestu uporabe v vpogledih v občinstvo je podprt na podlagi podatkovnih tokov iz storitve Power Platform.</span><span class="sxs-lookup"><span data-stu-id="37fee-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="37fee-115">Podatkovne tokove lahko omogočite v storitvi Customer Insights, in sicer tako, da med nastavitvijo okolja [navedete URL povezave za okolje Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="37fee-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="37fee-116">Za vire podatkov, ustvarjene ob vzpostavitvi povezave med okoljem storitve Dataverse in storitvijo Customer Insights, se privzeto uporabljajo [podatkovni tokovi iz storitve Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="37fee-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="37fee-117">Za podatkovne tokove je prek prehodov za podatke podprta povezljivost na mestu uporabe.</span><span class="sxs-lookup"><span data-stu-id="37fee-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="37fee-118">Odstranite vire podatkov, ki so bili uporabljeni vzpostavitvijo povezave z okoljem Dataverse za uporabo prehodov za podatke na mestu uporabe, in jih znova ustvarite.</span><span class="sxs-lookup"><span data-stu-id="37fee-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="37fee-119">Prehodi za podatke iz obstoječega okolja storitve Power BI ali Power Apps bodo vidni v storitvi Customer Insights, kjer jih lahko znova uporabite.</span><span class="sxs-lookup"><span data-stu-id="37fee-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="37fee-120">Na strani z viri podatkov je prikazana povezava do okolja Power Platform, kjer si lahko ogledate prehode za podatke na mestu uporabe in jih konfigurirate.</span><span class="sxs-lookup"><span data-stu-id="37fee-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Posnetek zaslona strani z viri podatkov, na kateri so prikazane povezave za preusmeritev na okolje storitve Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="37fee-122">Pregled zaužitih podatkov</span><span class="sxs-lookup"><span data-stu-id="37fee-122">Review ingested data</span></span>

<span data-ttu-id="37fee-123">Videli boste ime vsakega zaužitega vira podatkov, njegovo stanje in čas, ko so bili podatki za ta vir nazadnje osveženi.</span><span class="sxs-lookup"><span data-stu-id="37fee-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="37fee-124">Seznam virov podatkov lahko razvrstite po vseh stolpcih.</span><span class="sxs-lookup"><span data-stu-id="37fee-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37fee-125">![Vir podatkov je dodan](media/configure-data-datasource-added.png "Vir podatkov je dodan")</span><span class="sxs-lookup"><span data-stu-id="37fee-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="37fee-126">Stanje</span><span class="sxs-lookup"><span data-stu-id="37fee-126">Status</span></span>  |<span data-ttu-id="37fee-127">Opis</span><span class="sxs-lookup"><span data-stu-id="37fee-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="37fee-128">Uspelo</span><span class="sxs-lookup"><span data-stu-id="37fee-128">Successful</span></span>   |<span data-ttu-id="37fee-129">Vir podatkov je bil uspešno vključen, če je čas omenjen v stolpcu **Osveženo**.</span><span class="sxs-lookup"><span data-stu-id="37fee-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="37fee-130">Ni začeto</span><span class="sxs-lookup"><span data-stu-id="37fee-130">Not started</span></span>   |<span data-ttu-id="37fee-131">Vir podatkov še nima vključenih podatkov ali je še v načinu osnutka.</span><span class="sxs-lookup"><span data-stu-id="37fee-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="37fee-132">Osveževanje</span><span class="sxs-lookup"><span data-stu-id="37fee-132">Refreshing</span></span>    |<span data-ttu-id="37fee-133">Uvažanje podatkov je v teku.</span><span class="sxs-lookup"><span data-stu-id="37fee-133">Data ingestion is in progress.</span></span> <span data-ttu-id="37fee-134">Ta postopek lahko prekličete tako, da v stolpcu **Dejanja** izberete **Ustavi osveževanje**.</span><span class="sxs-lookup"><span data-stu-id="37fee-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="37fee-135">Ustavitev osveževanja vira podatkov bo povrnjena na zadnje stanje osveževanja.</span><span class="sxs-lookup"><span data-stu-id="37fee-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="37fee-136">Neuspelo</span><span class="sxs-lookup"><span data-stu-id="37fee-136">Failed</span></span>     |<span data-ttu-id="37fee-137">Pri uvozu podatkov je prišlo do napak.</span><span class="sxs-lookup"><span data-stu-id="37fee-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="37fee-138">Če si želite ogledati več podrobnosti, izberite vrednost stolpca **Stanje** katerega koli vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="37fee-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="37fee-139">V podoknu **Podrobnosti o napredku** razširite možnost **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="37fee-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="37fee-140">Izberite možnost **Prikaži podrobnosti** za pregled več podrobnosti o stanju osveževanja, vključno s podrobnostmi o napakah in posodobitvami nadaljnjih postopkov.</span><span class="sxs-lookup"><span data-stu-id="37fee-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="37fee-141">Nalaganje podatkov lahko traja nekaj časa.</span><span class="sxs-lookup"><span data-stu-id="37fee-141">Loading data can take some time.</span></span> <span data-ttu-id="37fee-142">Po uspešni osvežitvi je mogoče uvožene podatke pregledati na strani **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="37fee-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="37fee-143">Za več informacij glejte [Entitete](entities.md).</span><span class="sxs-lookup"><span data-stu-id="37fee-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="37fee-144">Osveževanje vira podatkov</span><span class="sxs-lookup"><span data-stu-id="37fee-144">Refresh a data source</span></span>

<span data-ttu-id="37fee-145">Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo.</span><span class="sxs-lookup"><span data-stu-id="37fee-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="37fee-146">Izberite **Skrbnik** > **Sistem** > [**Načrtovanje**](system.md#schedule-tab) za konfiguriranje načrtovanih osvežitev vseh vključenih virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="37fee-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="37fee-147">Če želite osvežiti vir podatkov na zahtevo, sledite tem korakom:</span><span class="sxs-lookup"><span data-stu-id="37fee-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="37fee-148">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="37fee-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="37fee-149">Izberite navpične tri pike poleg vira podatkov, ki ga želite osvežiti, in izberite **Osveži** s spustnega seznama.</span><span class="sxs-lookup"><span data-stu-id="37fee-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="37fee-150">Vir podatkov se zdaj sproži za ročno osvežitev.</span><span class="sxs-lookup"><span data-stu-id="37fee-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="37fee-151">Če osvežite vir podatkov, se posodobijo tudi shema entitet in podatki za vse entitete, določene v viru podatkov.</span><span class="sxs-lookup"><span data-stu-id="37fee-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="37fee-152">Izberite **Ustavi osveževanje**, če želite preklicati obstoječo osvežitev, in se bo vir podatkov vrnil na zadnje stanje osveževanja.</span><span class="sxs-lookup"><span data-stu-id="37fee-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="37fee-153">Brisanje vira podatkov</span><span class="sxs-lookup"><span data-stu-id="37fee-153">Delete a data source</span></span>

1. <span data-ttu-id="37fee-154">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="37fee-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="37fee-155">Izberite navpične tri pike poleg vira podatkov, ki ga želite odstraniti, in na spustnem meniju izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="37fee-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="37fee-156">Potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="37fee-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
