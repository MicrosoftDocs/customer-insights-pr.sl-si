---
title: Izvoz podatkov storitve Customer Insights v storitev AdRoll
description: Preberite o konfiguraciji povezave s storitvijo AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697094"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="e1e2e-103">Povezovalnik za storitev AdRoll (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="e1e2e-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="e1e2e-104">Izvozite segmente poenotenih profilov strank v storitev AdRoll in jih uporabite za oglaševanje.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e1e2e-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="e1e2e-105">Prerequisites</span></span>

-   <span data-ttu-id="e1e2e-106">Imate [račun za AdRoll](https://www.adroll.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e1e2e-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e1e2e-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="e1e2e-109">Vzpostavljanje povezave s storitvijo AdRoll</span><span class="sxs-lookup"><span data-stu-id="e1e2e-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="e1e2e-110">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e1e2e-111">V razdelku **AdRoll** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="e1e2e-112">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfiguracijsko podokno za povezavo s storitvijo AdRoll":::

1. <span data-ttu-id="e1e2e-114">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e1e2e-115">Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e1e2e-116">Izberite **Preverjanje pristnosti s storitvijo AdRoll** in vnesite svoje skrbniške poverilnice za AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e1e2e-117">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e1e2e-118">Vnesite **ID oglaševalca AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e1e2e-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="e1e2e-119">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e1e2e-120">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="e1e2e-120">Configure the connector</span></span>

1. <span data-ttu-id="e1e2e-121">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e1e2e-122">Segmente je treba izvoziti v storitev AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e1e2e-123">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-123">Select the segments you want to export.</span></span> <span data-ttu-id="e1e2e-124">Izberite segment z vsaj 100 člani.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e1e2e-125">Manjših segmentov ni mogoče izvoziti.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-125">You can't export smaller segments.</span></span> <span data-ttu-id="e1e2e-126">Poleg tega je največja velikost segmenta za izvoz 250.000 članov na izvoz.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e1e2e-127">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e1e2e-128">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="e1e2e-128">Export the data</span></span>

<span data-ttu-id="e1e2e-129">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e1e2e-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e1e2e-130">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1e2e-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e1e2e-131">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="e1e2e-131">Known limitations</span></span>

- <span data-ttu-id="e1e2e-132">V storitev AdRoll lahko ob vsakem izvozu izvozite do 250.000 profilov.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="e1e2e-133">V storitev AdRoll ne morete izvoziti segmentov z manj kot 100 profili.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e1e2e-134">Izvoz v storitev AdRoll je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e1e2e-135">Izvoz do 250.000 profilov v storitev AdRoll lahko traja do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e1e2e-136">Število profilov, ki jih lahko izvozite v storitev AdRoll, je odvisno in omejeno glede na vašo pogodbo s storitvijo AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e1e2e-137">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="e1e2e-137">Data privacy and compliance</span></span>

<span data-ttu-id="e1e2e-138">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev AdRoll, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e1e2e-139">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da storitev AdRoll izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e1e2e-140">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e1e2e-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e1e2e-141">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="e1e2e-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
