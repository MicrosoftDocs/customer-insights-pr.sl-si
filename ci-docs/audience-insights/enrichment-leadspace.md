---
title: Obogatitev profilov podjetij z neodvisnimi obogatitvami Leadspace
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597669"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="631b1-103">Obogatitev profilov podjetja z Leadspace (predogled)</span><span class="sxs-lookup"><span data-stu-id="631b1-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="631b1-104">Leadspace je podjetje, ki se ukvarja s podatki in zagotavlja platformo s podatki o strankah za prodajo podjetjem.</span><span class="sxs-lookup"><span data-stu-id="631b1-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="631b1-105">Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="631b1-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="631b1-106">Obogatitve vključujejo dodatne atribute, kot je velikost podjetja, lokacija, panoga in druge.</span><span class="sxs-lookup"><span data-stu-id="631b1-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="631b1-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="631b1-107">Prerequisites</span></span>

<span data-ttu-id="631b1-108">Za konfiguracijo storitve Leadspace morajo biti izpolnjeni naslednji pogoji:</span><span class="sxs-lookup"><span data-stu-id="631b1-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="631b1-109">Imate aktivno licenco Leadspace in časovno neomejen ključ (imenovan **žeton za Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="631b1-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="631b1-110">Za podrobnosti o izdelku se obrnite neposredno na [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="631b1-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="631b1-111">Imate [skrbniška](permissions.md#administrator) dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="631b1-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="631b1-112">Za podjetja imate [poenotene profile strank](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="631b1-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="631b1-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="631b1-113">Configuration</span></span>

1. <span data-ttu-id="631b1-114">Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="631b1-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="631b1-115">Izberite **Obogatite moje podatke** na ploščici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="631b1-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. <span data-ttu-id="631b1-117">Izberite **Začetek** in nato vnesite aktiven **žeton za Leadspace** (časovno neomejen ključ).</span><span class="sxs-lookup"><span data-stu-id="631b1-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="631b1-118">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="631b1-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="631b1-119">Potrdite oba vnosa z izbiro možnosti **Vzpostavi povezavo z Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="631b1-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="631b1-120">Izberite možnost **Preslikaj podatke** in izberite nabor podatkov, ki ga želite obogatiti s podatki o podjetju Leadspace.</span><span class="sxs-lookup"><span data-stu-id="631b1-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="631b1-121">Izberete lahko entiteto *Stranka*, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="631b1-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Izbira med obogatitvijo profila strank in obogatitvijo segmenta.":::

1. <span data-ttu-id="631b1-123">Izberite možnost **Naprej** in določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o podjetju Leadspace.</span><span class="sxs-lookup"><span data-stu-id="631b1-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="631b1-124">Polje **Ime podjetja** je obvezno.</span><span class="sxs-lookup"><span data-stu-id="631b1-124">The **Name of company** field is required.</span></span> <span data-ttu-id="631b1-125">Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.</span><span class="sxs-lookup"><span data-stu-id="631b1-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::
   
1. <span data-ttu-id="631b1-127">Izberite **Uporabi** za dokončanje preslikave polja.</span><span class="sxs-lookup"><span data-stu-id="631b1-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="631b1-128">Izberite **Zagon** za obogatitev profilov podjetja.</span><span class="sxs-lookup"><span data-stu-id="631b1-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="631b1-129">Kako dolgo traja obogatitev, je odvisno od števila poenotenih profilov strank.</span><span class="sxs-lookup"><span data-stu-id="631b1-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="631b1-130">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="631b1-130">Enrichment results</span></span>

<span data-ttu-id="631b1-131">Po osvežitvi obogatitve lahko pregledate novo obogatene podatke podjetja v razdelku [Moje obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="631b1-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="631b1-132">Ogledate si lahko čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="631b1-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="631b1-133">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="631b1-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="631b1-134">Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="631b1-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="631b1-135">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="631b1-135">Next steps</span></span>

<span data-ttu-id="631b1-136">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="631b1-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="631b1-137">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="631b1-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="631b1-138">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="631b1-138">Data privacy and compliance</span></span>

<span data-ttu-id="631b1-139">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Leadspace, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="631b1-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="631b1-140">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Leadspace izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="631b1-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="631b1-141">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="631b1-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="631b1-142">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="631b1-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]