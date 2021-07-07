---
title: Obogatitev z neodvisno obogatitvijo Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309840"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="fe3a9-103">Profile strank obogatite z demografskimi podatki iz storitve Experian (predogled)</span><span class="sxs-lookup"><span data-stu-id="fe3a9-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="fe3a9-104">Experian je vodilno podjetje v svetu na področju poročanja o potrošniških in poslovnih kreditih in na področju trženjskih storitev.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="fe3a9-105">S pomočjo storitev za obogatitev podatkov Experian lahko poglobite razumevanje svojih strank, in sicer tako, da njihove profile obogatite s pomočjo demografskih podatkov, kot so velikost gospodinjstva, dohodek itd.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe3a9-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="fe3a9-106">Prerequisites</span></span>

<span data-ttu-id="fe3a9-107">Da bi lahko konfigurirali Experian, morate izpolnjevati naslednje predpogoje:</span><span class="sxs-lookup"><span data-stu-id="fe3a9-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fe3a9-108">Imeti morate aktivno naročnino na Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-108">You have an active Experian subscription.</span></span> <span data-ttu-id="fe3a9-109">Če se želite naročiti, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="fe3a9-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="fe3a9-110">[Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="fe3a9-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="fe3a9-111">Povezavo Experian je konfiguriral skrbnik, *v nasprotnem primeru* pa imate [skrbnikovo](permissions.md#administrator) dovoljenje vi.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="fe3a9-112">Potrebujete tudi ID uporabnika, ID stranke in številko modela za račun storitve Secure Transport (ST) z omogočeno funkcijo SSH, ki ga je za vas ustvaril Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="fe3a9-113">Podprte države/regije</span><span class="sxs-lookup"><span data-stu-id="fe3a9-113">Supported countries/regions</span></span>

<span data-ttu-id="fe3a9-114">Obogatitev profilov strank trenutno omogočamo samo v ZDA.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="fe3a9-115">Konfiguriranje obogatitve</span><span class="sxs-lookup"><span data-stu-id="fe3a9-115">Configure the enrichment</span></span>

1. <span data-ttu-id="fe3a9-116">Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="fe3a9-117">Izberite možnost **Obogatitev mojih podatkov** na ploščici Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe3a9-118">![Experian ploščic](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="fe3a9-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="fe3a9-119">Na spustnem seznamu izberite možnost [povezava](connections.md).</span><span class="sxs-lookup"><span data-stu-id="fe3a9-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="fe3a9-120">Če ni na voljo nobena povezava, se obrnite na skrbnika.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="fe3a9-121">Če ste skrbnik, lahko vzpostavite povezavo tako, da izberete možnost **Dodaj povezavo** in na spustnem seznamu izberete Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="fe3a9-122">Za potrditev izbire povezave zberite možnost **Poveži z Experian**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="fe3a9-123">Izberite možnost **Naprej**, nato pa možnost **Nabor podatkov o strankah**, ki jih želite obogatiti z demografskimi podatki iz storitve Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="fe3a9-124">Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. <span data-ttu-id="fe3a9-126">Izberite možnost **Naslednji** in določite, katera vrsta polj iz vaših poenotenih profilov mora biti uporabljena za iskanje ujemajočih se demografskih podatkov iz storitve Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="fe3a9-127">Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="fe3a9-128">Za večjo natančnost ujemanja lahko dodate do dve dodatni polji.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="fe3a9-129">Ta izbira vpliva na polja za preslikavo, do katerih imate dostop v naslednjem koraku.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="fe3a9-130">Več atributov identifikatorja ključa, poslanih storitvi Experian, lahko doprinese višjo stopnjo ujemanja.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="fe3a9-131">Izberite možnost **Naprej**, da začnete preslikavo polj.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="fe3a9-132">Določite, katera polja iz vaših poenotenih profilov morajo biti uporabljena za iskanje ujemajočih se demografskih podatkov iz storitve Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="fe3a9-133">Obvezna polja so označena.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-133">Required fields are marked.</span></span>

1. <span data-ttu-id="fe3a9-134">Navedite ime obogatitve in izhodne entitete.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="fe3a9-135">Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="fe3a9-136">Konfigurirajte povezavo za Experian</span><span class="sxs-lookup"><span data-stu-id="fe3a9-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="fe3a9-137">Za konfiguriranje povezav morate biti skrbnik.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="fe3a9-138">Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali možnost* **Skrbnik** > **Povezave** ter izberite **Nastavi** na ploščici storitve Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="fe3a9-139">Izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="fe3a9-140">Vnesite ime povezave v polje za **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="fe3a9-141">Vnesite veljaven ID uporabnika, ID stranke in številko modela za svoj račun Secure Transport v storitvi Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="fe3a9-142">Preglejte in podajte soglasje, tako da v razdelku **Zasebnost in skladnost podatkov** izberete možnost **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="fe3a9-143">Izberite možnost **Potrdi** za potrditev konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="fe3a9-144">Po zaključku potrjevanja izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian podokno konfiguracije povezave.":::

## <a name="enrichment-results"></a><span data-ttu-id="fe3a9-146">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="fe3a9-146">Enrichment results</span></span>

<span data-ttu-id="fe3a9-147">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fe3a9-148">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fe3a9-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fe3a9-149">Čas obdelave bo odvisen od velikosti vaših podatkov o strankah in od postopkov obogatitve, ki jih je za vaš račun vzpostavil Experian.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="fe3a9-150">Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fe3a9-151">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fe3a9-152">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe3a9-153">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="fe3a9-153">Next steps</span></span>

<span data-ttu-id="fe3a9-154">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fe3a9-155">Ustvarite [segmente](segments.md) in [mere](measures.md) ter celo [izvozite podatke](export-destinations.md) in tako svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fe3a9-156">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="fe3a9-156">Data privacy and compliance</span></span>

<span data-ttu-id="fe3a9-157">S tem ko dovolite, da Dynamics 365 Customer Insights podatke prenese storitvi Experian, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fe3a9-158">Microsoft bo take podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da Experian izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fe3a9-159">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fe3a9-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fe3a9-160">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.</span><span class="sxs-lookup"><span data-stu-id="fe3a9-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
