---
title: Obogatitev profilov podjetij z neodvisnimi obogatitvami Leadspace
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895933"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="13481-103">Obogatitev profilov podjetja z Leadspace (predogled)</span><span class="sxs-lookup"><span data-stu-id="13481-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="13481-104">Leadspace je podjetje, ki se ukvarja s podatki in zagotavlja platformo s podatki o strankah za prodajo podjetjem.</span><span class="sxs-lookup"><span data-stu-id="13481-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="13481-105">Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="13481-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="13481-106">Obogatitve vključujejo več atributov, kot so velikost podjetja, lokacija, panoga in drugo.</span><span class="sxs-lookup"><span data-stu-id="13481-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13481-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="13481-107">Prerequisites</span></span>

<span data-ttu-id="13481-108">Za konfiguracijo storitve Leadspace morajo biti izpolnjeni naslednji pogoji:</span><span class="sxs-lookup"><span data-stu-id="13481-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="13481-109">Imate aktivno licenco za Leadspace.</span><span class="sxs-lookup"><span data-stu-id="13481-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="13481-110">Za podjetja imate [poenotene profile strank](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="13481-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="13481-111">Skrbnik je že konfiguriral povezavo z Leadscape oziroma imate vi [skrbniška](permissions.md#administrator) dovoljenja in "trajni ključ" (imenovan žeton **Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="13481-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="13481-112">Za podrobnosti o izdelku stopite v stik neposredno z družbo [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="13481-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="13481-113">Konfiguriranje obogatitve</span><span class="sxs-lookup"><span data-stu-id="13481-113">Configure the enrichment</span></span>

1. <span data-ttu-id="13481-114">Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="13481-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="13481-115">Na ploščici za Leadspace izberite možnost **Obogatitev podatkov** in izberite možnost **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="13481-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. <span data-ttu-id="13481-117">Na spustnem seznamu izberite [povezavo](connections.md).</span><span class="sxs-lookup"><span data-stu-id="13481-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="13481-118">Če ni na voljo nobena povezava, se obrnite na skrbnika.</span><span class="sxs-lookup"><span data-stu-id="13481-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="13481-119">Če ste skrbnik, lahko vzpostavite povezavo z izbiro možnosti **Dodaj povezavo** in izbiro možnosti **Leadscape**.</span><span class="sxs-lookup"><span data-stu-id="13481-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="13481-120">Izberite možnost **Poveži z Leadscape** za potrditev povezave.</span><span class="sxs-lookup"><span data-stu-id="13481-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="13481-121">Izberite možnost **Naprej** in izberite **nabor podatkov o stranki**, ki ga želite obogatiti s podatki o podjetju družbe Leadspace.</span><span class="sxs-lookup"><span data-stu-id="13481-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="13481-122">Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.</span><span class="sxs-lookup"><span data-stu-id="13481-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. <span data-ttu-id="13481-124">Izberite možnost **Naprej** in določite, katere vrste polj iz vaših poenotenih profilov se uporabljajo za iskanje ustreznih podatkov o podjetju iz storitev Leadspace.</span><span class="sxs-lookup"><span data-stu-id="13481-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="13481-125">Polje **Ime podjetja** je obvezno.</span><span class="sxs-lookup"><span data-stu-id="13481-125">The **Name of company** field is required.</span></span> <span data-ttu-id="13481-126">Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.</span><span class="sxs-lookup"><span data-stu-id="13481-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::

1. <span data-ttu-id="13481-128">Izberite možnost **Naprej**, da dokončate preslikavo polj.</span><span class="sxs-lookup"><span data-stu-id="13481-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="13481-129">Navedite ime obogatitve in po pregledu vaše izbire izberite možnost **Shrani obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="13481-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="13481-130">Konfiguriranje povezave z Leadspace</span><span class="sxs-lookup"><span data-stu-id="13481-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="13481-131">Za konfiguriranje povezav morate biti skrbnik.</span><span class="sxs-lookup"><span data-stu-id="13481-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="13481-132">Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Leadspace izberite možnost **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="13481-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="13481-133">Izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="13481-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="13481-134">Vnesite ime povezave v polje za **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="13481-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="13481-135">Vnesite veljaven žeton za Leadspace.</span><span class="sxs-lookup"><span data-stu-id="13481-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="13481-136">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="13481-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="13481-137">Izberite možnost **Potrdi** za potrditev konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="13481-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="13481-138">Po zaključku potrjevanja izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="13481-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stran za konfiguriranje povezave z Leadscape.":::

## <a name="enrichment-results"></a><span data-ttu-id="13481-140">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="13481-140">Enrichment results</span></span>

<span data-ttu-id="13481-141">Po osvežitvi obogatitve lahko pregledate novo obogatene podatke podjetja v razdelku [Moje obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="13481-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="13481-142">Ogledate si lahko čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="13481-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="13481-143">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="13481-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="13481-144">Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="13481-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="13481-145">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="13481-145">Next steps</span></span>

<span data-ttu-id="13481-146">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="13481-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="13481-147">Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="13481-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="13481-148">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="13481-148">Data privacy and compliance</span></span>

<span data-ttu-id="13481-149">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Leadspace, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="13481-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="13481-150">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Leadspace izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="13481-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="13481-151">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="13481-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="13481-152">Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.</span><span class="sxs-lookup"><span data-stu-id="13481-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
