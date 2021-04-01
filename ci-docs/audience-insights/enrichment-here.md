---
title: Obogatitev z neodvisnimi obogatitvami HERE Technologies
description: Splošne informacije o neodvisni obogatitvi HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597761"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="96c57-103">Obogatitev profilov strank v sodelovanju z družbo HERE Technologies (predogled)</span><span class="sxs-lookup"><span data-stu-id="96c57-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="96c57-104">HERE Technologies je podjetje z lokacijsko platformo, ki ponuja lokacijsko usmerjene podatke in storitve.</span><span class="sxs-lookup"><span data-stu-id="96c57-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="96c57-105">S storitvami za obogatitev podatkov podjetja HERE Technologies lahko z normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več zagotovite natančnejše razumevanje lokacije svojih strank.</span><span class="sxs-lookup"><span data-stu-id="96c57-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96c57-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="96c57-106">Prerequisites</span></span>

<span data-ttu-id="96c57-107">Za konfiguracijo obogatitve HERE Technologies morajo biti izpolnjeni naslednji predpogoji:</span><span class="sxs-lookup"><span data-stu-id="96c57-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="96c57-108">Imate aktivno naročnino HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="96c57-109">Če želite naročnino, se lahko [prijavite tukaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ali neposredno [stopite v stik z družbo HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="96c57-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="96c57-110">Preberite več o obogatitvi lokacije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="96c57-111">Imate ključ API za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="96c57-112">Imate [skrbniška](permissions.md#administrator) dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="96c57-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="96c57-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="96c57-113">Configuration</span></span>

1. <span data-ttu-id="96c57-114">Pomaknite se na možnost **Podatki** > **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="96c57-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="96c57-115">Izberite **Obogatitev podatkov** na ploščici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96c57-116">![Ploščica HERE Technologies](media/HERE-tile.png "Ploščica HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="96c57-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="96c57-117">Vnesite aktiven **ključ API za HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="96c57-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="96c57-118">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="96c57-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="96c57-119">Potrdite oba vnosa z izbiro možnosti **Povezovanje s HERE**.</span><span class="sxs-lookup"><span data-stu-id="96c57-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="96c57-120">Izberite možnost **Dodaj podatke** in izberite **nabor podatkov o strankah**, ki ga želite obogatiti s podatki o lokaciji iz podjetja HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="96c57-121">Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="96c57-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. <span data-ttu-id="96c57-123">Izberite, ali želite polja preslikati na primarni in/ali sekundarni naslov.</span><span class="sxs-lookup"><span data-stu-id="96c57-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="96c57-124">Za oba naslova lahko določite preslikavo polj (na primer domači in poslovni naslov) in obogatite profile za oba naslova posebej.</span><span class="sxs-lookup"><span data-stu-id="96c57-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="96c57-125">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="96c57-125">Select **Next**.</span></span>

1. <span data-ttu-id="96c57-126">Določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o lokaciji družbe HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="96c57-127">Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov.</span><span class="sxs-lookup"><span data-stu-id="96c57-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="96c57-128">Za večjo natančnost ujemanja lahko dodate več polj.</span><span class="sxs-lookup"><span data-stu-id="96c57-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96c57-129">![Stran za konfiguracijo obogatitve HERE Technologies](media/enrichment-HERE-configuration.png "Stran za konfiguracijo obogatitve HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="96c57-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="96c57-130">Izberite **Uporabi** za dokončanje preslikave polja.</span><span class="sxs-lookup"><span data-stu-id="96c57-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="96c57-131">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="96c57-131">Enrichment results</span></span>

<span data-ttu-id="96c57-132">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="96c57-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="96c57-133">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="96c57-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="96c57-134">Čas obdelave bo odvisen od velikosti podatkov o vaših strankah in odzivnega časa API-ja družbe HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="96c57-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="96c57-135">Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="96c57-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="96c57-136">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="96c57-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="96c57-137">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="96c57-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96c57-138">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="96c57-138">Next steps</span></span>

<span data-ttu-id="96c57-139">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="96c57-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="96c57-140">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="96c57-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="96c57-141">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="96c57-141">Data privacy and compliance</span></span>

<span data-ttu-id="96c57-142">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v HERE Technologies, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="96c57-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="96c57-143">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da HERE Technologies izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="96c57-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="96c57-144">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="96c57-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="96c57-145">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="96c57-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]