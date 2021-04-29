---
title: Izvoz podatkov storitve Customer Insights v storitev AdRoll
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895979"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="c3796-103">Izvoz seznamov segmentov v AdRoll (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="c3796-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="c3796-104">Izvozite segmente poenotenih profilov strank v storitev AdRoll in jih uporabite za oglaševanje.</span><span class="sxs-lookup"><span data-stu-id="c3796-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c3796-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="c3796-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c3796-106">Imate [račun za AdRoll](https://www.adroll.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="c3796-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c3796-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="c3796-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c3796-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="c3796-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c3796-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="c3796-109">Known limitations</span></span>

- <span data-ttu-id="c3796-110">V storitev AdRoll lahko ob vsakem izvozu izvozite do 250.000 profilov.</span><span class="sxs-lookup"><span data-stu-id="c3796-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="c3796-111">V storitev AdRoll ne morete izvoziti segmentov z manj kot 100 profili.</span><span class="sxs-lookup"><span data-stu-id="c3796-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="c3796-112">Izvoz v storitev AdRoll je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="c3796-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="c3796-113">Izvoz do 250.000 profilov v storitev AdRoll lahko traja do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="c3796-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="c3796-114">Število profilov, ki jih lahko izvozite v storitev AdRoll, je odvisno in omejeno glede na vašo pogodbo s storitvijo AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c3796-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="c3796-115">Nastavitev povezave s storitvijo AdRoll</span><span class="sxs-lookup"><span data-stu-id="c3796-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="c3796-116">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="c3796-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c3796-117">Izberite možnost **Dodajanje povezave** in izberite **AdRoll** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="c3796-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="c3796-118">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="c3796-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c3796-119">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="c3796-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c3796-120">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="c3796-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c3796-121">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="c3796-121">Choose who can use this connection.</span></span> <span data-ttu-id="c3796-122">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="c3796-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c3796-123">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c3796-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c3796-124">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="c3796-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c3796-125">Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c3796-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="c3796-126">Izberite **Preverjanje pristnosti s storitvijo AdRoll** in vnesite svoje skrbniške poverilnice za AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c3796-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="c3796-127">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c3796-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c3796-128">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="c3796-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c3796-129">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="c3796-129">Configure an export</span></span>

<span data-ttu-id="c3796-130">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="c3796-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c3796-131">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c3796-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c3796-132">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c3796-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c3796-133">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="c3796-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c3796-134">V polju **Povezava za izvoz** izberite povezavo v razdelku AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c3796-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="c3796-135">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="c3796-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c3796-136">Vpišite **ID za AdRoll Advertiser** Za več informacij glejte razdelek [Profili storitve AdRoll Advertiser](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="c3796-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="c3796-137">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="c3796-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c3796-138">Segmente je treba izvoziti v storitev AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c3796-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="c3796-139">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="c3796-139">Select the segments you want to export.</span></span> <span data-ttu-id="c3796-140">Izberite segment z vsaj 100 člani.</span><span class="sxs-lookup"><span data-stu-id="c3796-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="c3796-141">Manjših segmentov ni mogoče izvoziti.</span><span class="sxs-lookup"><span data-stu-id="c3796-141">You can't export smaller segments.</span></span> <span data-ttu-id="c3796-142">Poleg tega je največja velikost segmenta za izvoz 250.000 članov na izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3796-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="c3796-143">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="c3796-143">Select **Save**.</span></span>

<span data-ttu-id="c3796-144">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="c3796-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c3796-145">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c3796-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c3796-146">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c3796-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c3796-147">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="c3796-147">Data privacy and compliance</span></span>

<span data-ttu-id="c3796-148">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev AdRoll, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="c3796-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c3796-149">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da storitev AdRoll izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="c3796-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c3796-150">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c3796-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c3796-151">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="c3796-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
