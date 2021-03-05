---
title: Povezovalnik Power BI
description: Seznanite se z uporabo povezovalnika Dynamics 365 Customer Insights v storitvi Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477108"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="a4075-103">Povezovalnik za Power BI (predogled)</span><span class="sxs-lookup"><span data-stu-id="a4075-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="a4075-104">Ustvarite vizualizacije svojih podatkov s storitvijo Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="a4075-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="a4075-105">Ustvarite dodatne vpoglede in poročila s svojimi poenotenimi podatki o strankah.</span><span class="sxs-lookup"><span data-stu-id="a4075-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4075-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="a4075-106">Prerequisites</span></span>

- <span data-ttu-id="a4075-107">Imate poenotene profile strank.</span><span class="sxs-lookup"><span data-stu-id="a4075-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="a4075-108">Najnovejša različica storitve [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nameščena v računalnik.</span><span class="sxs-lookup"><span data-stu-id="a4075-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="a4075-109">[Preberite več o storitvi Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="a4075-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="a4075-110">Konfiguracija povezovalnika za Power BI</span><span class="sxs-lookup"><span data-stu-id="a4075-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="a4075-111">V storitvi Power BI Desktop izberite možnost **Datoteka** > **Pridobi podatke**.</span><span class="sxs-lookup"><span data-stu-id="a4075-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="a4075-112">Izberite **Prikaži več** in poiščite storitev **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="a4075-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="a4075-113">Izberite **Vzpostavljanje povezave**.</span><span class="sxs-lookup"><span data-stu-id="a4075-113">Select **Connect**.</span></span>

1. <span data-ttu-id="a4075-114">Opravite **Vpis** z enakim računom organizacije, ki ga uporabljate za storitev Customer Insights, in izberite možnost **Poveži**.</span><span class="sxs-lookup"><span data-stu-id="a4075-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a4075-115">Račun, ki ga navedete v tem koraku, se uporablja za pridobivanje podatkov iz storitve Customer Insights in ni nujno enak tistemu, v katerega ste prijavljeni v Power BI.</span><span class="sxs-lookup"><span data-stu-id="a4075-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="a4075-116">Če želite ponastaviti račun, ki se uporablja za pridobivanje podatkov, odprite Power BI in izberite **Datoteka** > **Možnosti** > **Nastavitve** > **Nastavitve vira podatkov**.</span><span class="sxs-lookup"><span data-stu-id="a4075-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="a4075-117">Na seznamu virov podatkov izberite **Prijava v Dynamics 365 Customer Insights** in izberite **Počisti dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="a4075-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="a4075-118">V pogovornem oknu **Krmilnik**.</span><span class="sxs-lookup"><span data-stu-id="a4075-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="a4075-119">Prikazan je seznam vseh okolij, do katerih imate dostop.</span><span class="sxs-lookup"><span data-stu-id="a4075-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="a4075-120">Razširite okolje in odprite katero koli mapo (entitete, mere, segmenti, obogatitve).</span><span class="sxs-lookup"><span data-stu-id="a4075-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="a4075-121">Odprite na primer mapo **Entitete** za ogled vseh entitet, ki jih lahko uvozite.</span><span class="sxs-lookup"><span data-stu-id="a4075-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="a4075-122">![Krmilnik povezovalnika storitve Power BI](media/power-bi-navigator.png "Krmilnik povezovalnika storitve Power BI")</span><span class="sxs-lookup"><span data-stu-id="a4075-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="a4075-123">Izberite potrditvena polja poleg entitet, ki jih želite vključiti, in nato **Naloži**.</span><span class="sxs-lookup"><span data-stu-id="a4075-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="a4075-124">Izberete lahko več entitet iz več okolij.</span><span class="sxs-lookup"><span data-stu-id="a4075-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="a4075-125">Med nalaganjem entitet bo prikazano pogovorno okno za nalaganje.</span><span class="sxs-lookup"><span data-stu-id="a4075-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="a4075-126">Ko se naložijo vse vaše izbrane entitete, lahko uporabite zmožnosti Power BI za vizualizacijo podatkov.</span><span class="sxs-lookup"><span data-stu-id="a4075-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="a4075-127">Obsežni nabori podatkov</span><span class="sxs-lookup"><span data-stu-id="a4075-127">Large data sets</span></span>

<span data-ttu-id="a4075-128">Povezovalnik Customer Insights za Power BI je zasnovan tako, da deluje za nabore podatkov, ki imajo do 1 milijona profilov strank.</span><span class="sxs-lookup"><span data-stu-id="a4075-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="a4075-129">Uvoz večjih naborov podatkov lahko deluje, vendar traja dolgo.</span><span class="sxs-lookup"><span data-stu-id="a4075-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="a4075-130">Poleg tega lahko zaradi omejitev storitve Power BI pride do časovnih omejitev.</span><span class="sxs-lookup"><span data-stu-id="a4075-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="a4075-131">Za več informacij glejte [Power BI: priporočila za obsežne nabore podatkov](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="a4075-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="a4075-132">Delo s podmnožico želenih podatkov</span><span class="sxs-lookup"><span data-stu-id="a4075-132">Work with a subset of data</span></span>

<span data-ttu-id="a4075-133">Razmislite o delu s podmnožico svojih podatkov.</span><span class="sxs-lookup"><span data-stu-id="a4075-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="a4075-134">Lahko na primer ustvarite [segmente](segments.md) namesto izvoza vseh zapisov strank v storitev Power BI.</span><span class="sxs-lookup"><span data-stu-id="a4075-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a4075-135">Odpravljanje težav</span><span class="sxs-lookup"><span data-stu-id="a4075-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="a4075-136">Okolje storitve Customer Insights se ne prikaže v storitvi Power BI</span><span class="sxs-lookup"><span data-stu-id="a4075-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="a4075-137">Okolja, ki imajo opredeljen več kot en [odnos](relationships.md) med dvema enakima entitetama v vpogledih v občinstvo, ne bodo na voljo v povezovalniku storitve Power BI.</span><span class="sxs-lookup"><span data-stu-id="a4075-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="a4075-138">Podvojene odnose lahko prepoznate in jih odstranite.</span><span class="sxs-lookup"><span data-stu-id="a4075-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="a4075-139">V vpogledih v občinstvo odprite razdelek **Podatki** > **Odnosi** za okolje, ki manjka v storitvi Power BI.</span><span class="sxs-lookup"><span data-stu-id="a4075-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="a4075-140">Prepoznajte podvojene odnose:</span><span class="sxs-lookup"><span data-stu-id="a4075-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="a4075-141">Preverite, ali je med istima entitetama določen več kot en odnos.</span><span class="sxs-lookup"><span data-stu-id="a4075-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="a4075-142">Preverite, ali je odnos ustvarjen med entitetama, ki sta vključeni v postopek poenotenja.</span><span class="sxs-lookup"><span data-stu-id="a4075-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="a4075-143">Med vsemi entitetami, vključenimi v postopek združevanja, je določen implicitni odnos.</span><span class="sxs-lookup"><span data-stu-id="a4075-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="a4075-144">Odstranite vse prepoznane podvojene odnose.</span><span class="sxs-lookup"><span data-stu-id="a4075-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="a4075-145">Po odstranitvi podvojenih odnosov poskusite znova konfigurirati povezovalnik storitve Power BI.</span><span class="sxs-lookup"><span data-stu-id="a4075-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="a4075-146">Okolje bi moralo biti zdaj na voljo.</span><span class="sxs-lookup"><span data-stu-id="a4075-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

