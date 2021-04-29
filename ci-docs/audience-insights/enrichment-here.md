---
title: Obogatitev z neodvisnimi obogatitvami HERE Technologies
description: Splošne informacije o neodvisni obogatitvi HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896071"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="bfe75-103">Obogatitev profilov strank v sodelovanju z družbo HERE Technologies (predogled)</span><span class="sxs-lookup"><span data-stu-id="bfe75-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="bfe75-104">HERE Technologies je podjetje z lokacijsko platformo, ki ponuja lokacijsko usmerjene podatke in storitve.</span><span class="sxs-lookup"><span data-stu-id="bfe75-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="bfe75-105">S storitvami za obogatitev podatkov podjetja HERE Technologies lahko z normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več zagotovite natančnejše razumevanje lokacije svojih strank.</span><span class="sxs-lookup"><span data-stu-id="bfe75-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfe75-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="bfe75-106">Prerequisites</span></span>

<span data-ttu-id="bfe75-107">Za konfiguracijo obogatitve HERE Technologies morajo biti izpolnjeni naslednji predpogoji:</span><span class="sxs-lookup"><span data-stu-id="bfe75-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bfe75-108">Imate aktivno naročnino HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="bfe75-109">Če želite naročnino, se lahko [prijavite tukaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ali neposredno [stopite v stik z družbo HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="bfe75-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="bfe75-110">Preberite več o obogatitvi lokacije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="bfe75-111">Na voljo je [povezava](connections.md) za storitev HERE *oziroma* imate vi [skrbniška](permissions.md#administrator) dovoljenja in ključ za API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="bfe75-112">Konfiguriranje obogatitve</span><span class="sxs-lookup"><span data-stu-id="bfe75-112">Configure the enrichment</span></span>

1. <span data-ttu-id="bfe75-113">Pomaknite se na možnost **Podatki** > **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="bfe75-114">Na ploščici za HERE Technologies izberite možnost **Obogatitev podatkov** in izberite možnost **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfe75-115">![Ploščica HERE Technologies](media/HERE-tile.png "Ploščica HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bfe75-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="bfe75-116">Na spustnem seznamu izberite [povezavo](connections.md).</span><span class="sxs-lookup"><span data-stu-id="bfe75-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="bfe75-117">Če ni na voljo nobena povezava, se obrnite na skrbnika.</span><span class="sxs-lookup"><span data-stu-id="bfe75-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="bfe75-118">Če ste skrbnik, lahko vzpostavite povezavo z izbiro možnosti **Dodaj povezavo**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="bfe75-119">Na spustnem meniju izberite možnost **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="bfe75-120">Izberite možnost **Poveži z družbo HERE Technologies** za potrditev izbire.</span><span class="sxs-lookup"><span data-stu-id="bfe75-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="bfe75-121">Izberite možnost **Naprej** in izberite **nabor podatkov o stranki**, ki ga želite obogatiti s podatki o lokaciji podjetja HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="bfe75-122">Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="bfe75-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. <span data-ttu-id="bfe75-124">Izberite, ali želite polja preslikati na primarni in/ali sekundarni naslov.</span><span class="sxs-lookup"><span data-stu-id="bfe75-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="bfe75-125">Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej.</span><span class="sxs-lookup"><span data-stu-id="bfe75-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="bfe75-126">Gre za primere, ko je na primer na voljo domač in poslovni naslov.</span><span class="sxs-lookup"><span data-stu-id="bfe75-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="bfe75-127">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-127">Select **Next**.</span></span>

1. <span data-ttu-id="bfe75-128">Določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o lokaciji družbe HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="bfe75-129">Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov.</span><span class="sxs-lookup"><span data-stu-id="bfe75-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="bfe75-130">Za večjo natančnost ujemanja lahko dodate več polj.</span><span class="sxs-lookup"><span data-stu-id="bfe75-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfe75-131">![Stran za konfiguracijo obogatitve HERE Technologies](media/enrichment-HERE-configuration.png "Stran za konfiguracijo obogatitve HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bfe75-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="bfe75-132">Izberite možnost **Naprej**, da dokončate preslikavo polj.</span><span class="sxs-lookup"><span data-stu-id="bfe75-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="bfe75-133">Navedite ime obogatitve.</span><span class="sxs-lookup"><span data-stu-id="bfe75-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="bfe75-134">1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="bfe75-135">Konfiguriranje povezave z družbo HERE technologies</span><span class="sxs-lookup"><span data-stu-id="bfe75-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="bfe75-136">Za konfiguriranje povezav morate biti skrbnik.</span><span class="sxs-lookup"><span data-stu-id="bfe75-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="bfe75-137">Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici HERE Technologies izberite možnost **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="bfe75-138">Vnesite ime povezave v polje za **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="bfe75-139">Navedite veljaven ključ za API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="bfe75-140">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="bfe75-141">Izberite možnost **Potrdi** za potrditev konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="bfe75-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="bfe75-142">Po zaključku potrjevanja izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfe75-143">![Stran za konfiguriranje povezave z družbo HERE technologies](media/enrichment-HERE-connection.png "Stran za konfiguriranje povezave z družbo HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="bfe75-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bfe75-144">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="bfe75-144">Enrichment results</span></span>

<span data-ttu-id="bfe75-145">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="bfe75-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bfe75-146">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfe75-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bfe75-147">Čas obdelave bo odvisen od velikosti podatkov o vaših strankah in odzivnega časa API-ja družbe HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bfe75-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="bfe75-148">Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bfe75-149">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="bfe75-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bfe75-150">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="bfe75-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bfe75-151">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="bfe75-151">Next steps</span></span>

<span data-ttu-id="bfe75-152">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="bfe75-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bfe75-153">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="bfe75-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bfe75-154">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="bfe75-154">Data privacy and compliance</span></span>

<span data-ttu-id="bfe75-155">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v HERE Technologies, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="bfe75-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bfe75-156">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da HERE Technologies izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="bfe75-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bfe75-157">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bfe75-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bfe75-158">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="bfe75-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
