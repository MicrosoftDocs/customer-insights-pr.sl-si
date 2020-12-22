---
title: Obogatitev profilov podjetij z neodvisnimi obogatitvami Leadspace
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668743"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="85899-103">Obogatitev profilov podjetja z Leadspace (predogled)</span><span class="sxs-lookup"><span data-stu-id="85899-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="85899-104">Leadspace je podjetje, ki se ukvarja s podatki in zagotavlja platformo s podatki o strankah za prodajo podjetjem.</span><span class="sxs-lookup"><span data-stu-id="85899-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="85899-105">Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="85899-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="85899-106">Obogatitve vključujejo dodatne atribute, kot je velikost podjetja, lokacija, panoga in druge.</span><span class="sxs-lookup"><span data-stu-id="85899-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85899-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="85899-107">Prerequisites</span></span>

<span data-ttu-id="85899-108">Za konfiguracijo storitve Leadspace morajo biti izpolnjeni naslednji pogoji:</span><span class="sxs-lookup"><span data-stu-id="85899-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="85899-109">Imate aktivno licenco Leadspace in časovno neomejen ključ (imenovan **žeton za Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="85899-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="85899-110">Za podrobnosti o izdelku se obrnite neposredno na [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="85899-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="85899-111">Imate [skrbniška](permissions.md#administrator) dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="85899-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="85899-112">Za podjetja imate [poenotene profile strank](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="85899-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="85899-113">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="85899-113">Configuration</span></span>

1. <span data-ttu-id="85899-114">Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="85899-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="85899-115">Izberite **Obogatite moje podatke** na ploščici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="85899-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. <span data-ttu-id="85899-117">Izberite **Začetek** in nato vnesite aktiven **žeton za Leadspace** (časovno neomejen ključ).</span><span class="sxs-lookup"><span data-stu-id="85899-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="85899-118">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="85899-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="85899-119">Potrdite oba vnosa z izbiro možnosti **Vzpostavi povezavo z Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="85899-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="85899-120">Izberite **Preslikaj podatke** in določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o podjetju Leadspace.</span><span class="sxs-lookup"><span data-stu-id="85899-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="85899-121">Polje **Ime podjetja** je obvezno.</span><span class="sxs-lookup"><span data-stu-id="85899-121">The **Name of company** field is required.</span></span> <span data-ttu-id="85899-122">Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.</span><span class="sxs-lookup"><span data-stu-id="85899-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::
   
1. <span data-ttu-id="85899-124">Izberite **Uporabi** za dokončanje preslikave polja.</span><span class="sxs-lookup"><span data-stu-id="85899-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="85899-125">Izberite **Zagon** za obogatitev profilov podjetja.</span><span class="sxs-lookup"><span data-stu-id="85899-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="85899-126">Kako dolgo traja obogatitev, je odvisno od števila poenotenih profilov strank.</span><span class="sxs-lookup"><span data-stu-id="85899-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="85899-127">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="85899-127">Enrichment results</span></span>

<span data-ttu-id="85899-128">Po osvežitvi obogatitve lahko pregledate novo obogatene podatke podjetja v razdelku [Moje obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="85899-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="85899-129">Ogledate si lahko čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="85899-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="85899-130">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="85899-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="85899-131">Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="85899-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="85899-132">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="85899-132">Next steps</span></span>

<span data-ttu-id="85899-133">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="85899-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="85899-134">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="85899-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="85899-135">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="85899-135">Data privacy and compliance</span></span>

<span data-ttu-id="85899-136">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Leadspace, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="85899-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="85899-137">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Leadspace izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="85899-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="85899-138">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="85899-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="85899-139">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="85899-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>