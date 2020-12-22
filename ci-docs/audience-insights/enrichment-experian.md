---
title: Obogatitev z neodvisnimi obogatitvami Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668833"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="38705-103">Obogatitev profilov strank z demografskimi podatki podjetja Experian (predogled)</span><span class="sxs-lookup"><span data-stu-id="38705-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="38705-104">Družba Experian je vodilna v svetu pri kreditnem poročanju o potrošniških in podjetjih ter tržnih storitvah.</span><span class="sxs-lookup"><span data-stu-id="38705-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="38705-105">S storitvami za obogatitev podatkov družbe Experian lahko globlje razumete svoje stranke tako, da svoje profile strank obogatite z demografskimi podatki, kot so velikost gospodinjstva, dohodek in drugo.</span><span class="sxs-lookup"><span data-stu-id="38705-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38705-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="38705-106">Prerequisites</span></span>

<span data-ttu-id="38705-107">Za konfiguracijo storitve Experian je treba izpolnjevati naslednje predpogoje:</span><span class="sxs-lookup"><span data-stu-id="38705-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="38705-108">Imate aktivno naročnino za Experian.</span><span class="sxs-lookup"><span data-stu-id="38705-108">You have an active Experian subscription.</span></span> <span data-ttu-id="38705-109">Če želite naročnino, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="38705-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="38705-110">[Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="38705-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="38705-111">Imate ID uporabnika, ID stranke in številko modela za svoj račun za zaščiten promet (ST) z omogočenim SSH, ki ga je za vas ustvaril Experian.</span><span class="sxs-lookup"><span data-stu-id="38705-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="38705-112">Imate dovoljenja [skrbnika](permissions.md#administrator) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="38705-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="38705-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="38705-113">Configuration</span></span>

1. <span data-ttu-id="38705-114">Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="38705-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="38705-115">Izberite **Obogatitev podatkov** na ploščici storitve Experian.</span><span class="sxs-lookup"><span data-stu-id="38705-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38705-116">![Ploščica storitve Experian](media/experian-tile.png "Ploščica storitve Experian")</span><span class="sxs-lookup"><span data-stu-id="38705-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="38705-117">Izberite **Začetek** in vnesite ID uporabnika, ID stranke in številko modela za svoj račun Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="38705-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="38705-118">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="38705-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="38705-119">Potrdite vse vnose z izbiro **Uporabi**.</span><span class="sxs-lookup"><span data-stu-id="38705-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="38705-120">Preslikajte polja</span><span class="sxs-lookup"><span data-stu-id="38705-120">Map your fields</span></span>

1. <span data-ttu-id="38705-121">Izberite **Dodajte podatke** in izberite svoje identifikatorje ključev med možnostmi **Ime in naslov**, **E-pošta** ali **Telefon**, ki jih želite poslati v Experian za razreševanje identitete.</span><span class="sxs-lookup"><span data-stu-id="38705-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="38705-122">Več atributov identifikatorjev ključev, poslanih Experianu, bo verjetno povzročilo višjo stopnjo ujemanja.</span><span class="sxs-lookup"><span data-stu-id="38705-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="38705-123">Izberite **Naslednji** in preslikajte ustrezne atribute iz vaše enotne entitete stranke za izbrana polja identifikatorja ključa.</span><span class="sxs-lookup"><span data-stu-id="38705-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="38705-124">Izberite **Dodaj atribut** za preslikavo dodatnih atributov, ki bi jih radi poslali Experianu.</span><span class="sxs-lookup"><span data-stu-id="38705-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="38705-125">Izberite **Shrani** za dokončanje preslikave polj.</span><span class="sxs-lookup"><span data-stu-id="38705-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38705-126">![Preslikave polja Experian](media/experian-field-mapping.png "Preslikave polja Experian")</span><span class="sxs-lookup"><span data-stu-id="38705-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="38705-127">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="38705-127">Enrichment results</span></span>

<span data-ttu-id="38705-128">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="38705-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="38705-129">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="38705-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="38705-130">Čas obdelave bo odvisen od velikosti podatkov o strankah in postopkov obogatitve, ki jih je za vaš račun nastavil Experian.</span><span class="sxs-lookup"><span data-stu-id="38705-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="38705-131">Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="38705-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="38705-132">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="38705-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="38705-133">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="38705-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="38705-134">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="38705-134">Next steps</span></span>

<span data-ttu-id="38705-135">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="38705-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="38705-136">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="38705-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="38705-137">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="38705-137">Data privacy and compliance</span></span>

<span data-ttu-id="38705-138">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Experian dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="38705-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="38705-139">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Experian izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="38705-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="38705-140">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="38705-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="38705-141">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="38705-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
