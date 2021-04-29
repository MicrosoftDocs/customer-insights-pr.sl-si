---
title: Obogatitev z neodvisnimi obogatitvami Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896393"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8bf40-103">Obogatitev profilov strank z demografskimi podatki podjetja Experian (predogled)</span><span class="sxs-lookup"><span data-stu-id="8bf40-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8bf40-104">Družba Experian je vodilna v svetu pri kreditnem poročanju o potrošniških in podjetjih ter tržnih storitvah.</span><span class="sxs-lookup"><span data-stu-id="8bf40-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8bf40-105">S storitvami za obogatitev podatkov družbe Experian lahko globlje razumete svoje stranke tako, da svoje profile strank obogatite z demografskimi podatki, kot so velikost gospodinjstva, dohodek in drugo.</span><span class="sxs-lookup"><span data-stu-id="8bf40-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8bf40-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="8bf40-106">Prerequisites</span></span>

<span data-ttu-id="8bf40-107">Za konfiguracijo storitve Experian je treba izpolnjevati naslednje predpogoje:</span><span class="sxs-lookup"><span data-stu-id="8bf40-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8bf40-108">Imate aktivno naročnino za Experian.</span><span class="sxs-lookup"><span data-stu-id="8bf40-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8bf40-109">Če želite naročnino, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="8bf40-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8bf40-110">[Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8bf40-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="8bf40-111">Skrbnik je že konfiguriral povezavo s storitvijo Experian *oziroma* imate vi [skrbniška](permissions.md#administrator) dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="8bf40-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="8bf40-112">Potrebujete tudi ID uporabnika, ID stranke in številko modela za račun storitve Secure Transport (ST) z omogočenim protokolom SSH, ki ga je za vas ustvaril Experian.</span><span class="sxs-lookup"><span data-stu-id="8bf40-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8bf40-113">Konfiguriranje obogatitve</span><span class="sxs-lookup"><span data-stu-id="8bf40-113">Configure the enrichment</span></span>

1. <span data-ttu-id="8bf40-114">Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8bf40-115">Izberite **Obogatitev podatkov** na ploščici storitve Experian.</span><span class="sxs-lookup"><span data-stu-id="8bf40-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8bf40-116">![Ploščica storitve Experian](media/experian-tile.png "Ploščica storitve Experian")</span><span class="sxs-lookup"><span data-stu-id="8bf40-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="8bf40-117">Na spustnem seznamu izberite [povezavo](connections.md).</span><span class="sxs-lookup"><span data-stu-id="8bf40-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="8bf40-118">Če ni na voljo nobena povezava, se obrnite na skrbnika.</span><span class="sxs-lookup"><span data-stu-id="8bf40-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="8bf40-119">Če ste skrbnik, lahko vzpostavite povezavo tako, da izberete možnost **Dodaj povezavo** in na spustnem meniju izberete možnost Experian.</span><span class="sxs-lookup"><span data-stu-id="8bf40-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="8bf40-120">Izberite možnost **Poveži z Experian** za potrditev izbire povezave.</span><span class="sxs-lookup"><span data-stu-id="8bf40-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="8bf40-121">Izberite možnost **Naprej** in izberite **nabor podatkov o stranki**, ki ga želite obogatiti z demografskimi podatki podjetja Experian.</span><span class="sxs-lookup"><span data-stu-id="8bf40-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8bf40-122">Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="8bf40-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. <span data-ttu-id="8bf40-124">Izberite možnost **Naprej** in določite, katero vrsto polj iz vaših poenotenih profilov je treba uporabiti za iskanje ustreznih demografskih podatkov iz Experiana.</span><span class="sxs-lookup"><span data-stu-id="8bf40-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8bf40-125">Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="8bf40-126">Za večjo natančnost ujemanja lahko dodate do dve dodatni polji.</span><span class="sxs-lookup"><span data-stu-id="8bf40-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="8bf40-127">Ta izbira vpliva na polja za preslikavo, do katerih imate dostop v naslednjem koraku.</span><span class="sxs-lookup"><span data-stu-id="8bf40-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="8bf40-128">Več atributov identifikatorjev ključev, poslanih Experianu, bo verjetno povzročilo višjo stopnjo ujemanja.</span><span class="sxs-lookup"><span data-stu-id="8bf40-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8bf40-129">Izberite možnost **Naprej**, da začnete preslikavo polj.</span><span class="sxs-lookup"><span data-stu-id="8bf40-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="8bf40-130">Določite, katero vrsto polj iz vaših poenotenih profilov je treba uporabiti za iskanje ustreznih demografskih podatkov iz Experiana.</span><span class="sxs-lookup"><span data-stu-id="8bf40-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8bf40-131">Obvezna polja so označena.</span><span class="sxs-lookup"><span data-stu-id="8bf40-131">Required fields are marked.</span></span>

1. <span data-ttu-id="8bf40-132">Navedite ime obogatitve in izhodne entitete.</span><span class="sxs-lookup"><span data-stu-id="8bf40-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="8bf40-133">Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="8bf40-134">Konfiguriranje povezave z Experian</span><span class="sxs-lookup"><span data-stu-id="8bf40-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="8bf40-135">Za konfiguriranje povezav morate biti skrbnik.</span><span class="sxs-lookup"><span data-stu-id="8bf40-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8bf40-136">Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Experian izberite možnost **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="8bf40-137">Izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="8bf40-138">Vnesite ime povezave v polje za **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8bf40-139">Vnesite veljaven ID uporabnika, ID stranke in številko modela za svoj račun Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="8bf40-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="8bf40-140">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="8bf40-141">Izberite možnost **Potrdi** za potrditev konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="8bf40-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8bf40-142">Po zaključku potrjevanja izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno za konfiguriranje povezave z Experianom.":::

## <a name="enrichment-results"></a><span data-ttu-id="8bf40-144">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="8bf40-144">Enrichment results</span></span>

<span data-ttu-id="8bf40-145">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="8bf40-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8bf40-146">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8bf40-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8bf40-147">Čas obdelave bo odvisen od velikosti podatkov o strankah in postopkov obogatitve, ki jih je za vaš račun nastavil Experian.</span><span class="sxs-lookup"><span data-stu-id="8bf40-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8bf40-148">Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8bf40-149">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="8bf40-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8bf40-150">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="8bf40-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8bf40-151">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="8bf40-151">Next steps</span></span>

<span data-ttu-id="8bf40-152">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="8bf40-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8bf40-153">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="8bf40-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8bf40-154">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="8bf40-154">Data privacy and compliance</span></span>

<span data-ttu-id="8bf40-155">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Experian dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="8bf40-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8bf40-156">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Experian izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="8bf40-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8bf40-157">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8bf40-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8bf40-158">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="8bf40-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
