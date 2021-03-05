---
title: Preslikava entitet za poenotenje podatkov
description: Preslikajte podatke za ustvarjanje poenotenih profilov strank.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267055"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="10bb6-103">Entitete in atributi zemljevida</span><span class="sxs-lookup"><span data-stu-id="10bb6-103">Map entities and attributes</span></span>

<span data-ttu-id="10bb6-104">**Preslikava** je prva stopnja v postopku poenotenja podatkov pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="10bb6-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="10bb6-105">Preslikava je sestavljena iz treh faz:</span><span class="sxs-lookup"><span data-stu-id="10bb6-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="10bb6-106">*Izbira entitete*: določite združljive entitete, ki vodijo do nabora podatkov s popolnejšimi informacijami o vaših strankah.</span><span class="sxs-lookup"><span data-stu-id="10bb6-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="10bb6-107">*Izbira atributa:* za vsako entiteto določite stolpce, ki jih želite združiti in uskladiti v fazah *ujemanja* in *spajanja*.</span><span class="sxs-lookup"><span data-stu-id="10bb6-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="10bb6-108">Ti stolpci se imenujejo *Atributi*.</span><span class="sxs-lookup"><span data-stu-id="10bb6-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="10bb6-109">*Izbira primarnega ključa in vrste semantike*: za vsako entiteto določite atribut, ki ga želite definirati kot primarni ključ za to entiteto, za vsak atribut pa vrsto semantike, ki najbolje opisuje ta atribut.</span><span class="sxs-lookup"><span data-stu-id="10bb6-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="10bb6-110">Če želite več informacij o splošnem poteku poenotenja podatkov, glejte [Poenotenje](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="10bb6-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="10bb6-111">Izbira prvih entitet</span><span class="sxs-lookup"><span data-stu-id="10bb6-111">Select the first entities</span></span>

1. <span data-ttu-id="10bb6-112">Pri vpogledih v občinstvo izberite **Podatki** > **Poenoti** > **Preslikaj**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="10bb6-113">Fazo preslikave nastavite tako, da izberete **Izberi entitete**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="10bb6-114">Izberite entitete in atribute, ki jih želite uporabiti v fazah *ujemanja* in *spajanja*.</span><span class="sxs-lookup"><span data-stu-id="10bb6-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="10bb6-115">Obvezne atribute lahko iz entitete izberete posamezno ali pa iz nje vključite vse atribute in sicer tako, da izberete potrditveno polje na ravni entitete **Vključi vsa polja**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="10bb6-116">Priporočamo, da izberete vsaj dve entiteti, da boste lahko izkoristili postopek poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="10bb6-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10bb6-117">![Primer dodajanja entitet](media/data-manager-configure-map-add-entities-example.png "Primer dodajanja entitet")</span><span class="sxs-lookup"><span data-stu-id="10bb6-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="10bb6-118">V tem primeru dodajamo entiteti **eCommerceContacts** in **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="10bb6-119">Če izberete te dve entiteti lahko pridobite vpogled v to, kateri od spletnih poslovnih strank so člani programa zvestobe.</span><span class="sxs-lookup"><span data-stu-id="10bb6-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="10bb6-120">Po ključnih besedah lahko iščete po vseh atributih in entitetah, da izberete zahtevane atribute, ki jih želite preslikati.</span><span class="sxs-lookup"><span data-stu-id="10bb6-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10bb6-121">![Primer polj za iskanje](media/data-manager-configure-map-search-fields-example.png "Primer polj za iskanje")</span><span class="sxs-lookup"><span data-stu-id="10bb6-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="10bb6-122">Izberite **Uporabi** za potrditev izbire.</span><span class="sxs-lookup"><span data-stu-id="10bb6-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="10bb6-123">Izbira primarnega ključa in vrste semantike za atribute</span><span class="sxs-lookup"><span data-stu-id="10bb6-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="10bb6-124">Ko izberete entitete, stran **Preslikava** navede izbrane entitete vam v pregled.</span><span class="sxs-lookup"><span data-stu-id="10bb6-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="10bb6-125">Določite primarni ključ za entiteto in določite vrsto semantike za atribut v entiteti.</span><span class="sxs-lookup"><span data-stu-id="10bb6-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="10bb6-126">**Primarni ključ**: izberite en atribut kot primarni ključ za vsako od entitet.</span><span class="sxs-lookup"><span data-stu-id="10bb6-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="10bb6-127">Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti.</span><span class="sxs-lookup"><span data-stu-id="10bb6-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="10bb6-128">Atributi podatkovnih tipov niz, celo število in GUID so podprti kot primarni ključi in bodo prikazani v polju, iz katerega lahko izbirate.</span><span class="sxs-lookup"><span data-stu-id="10bb6-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="10bb6-129">**Vrsta semantike atributa**: kategorije atributov, na primer e-poštni naslov ali ime.</span><span class="sxs-lookup"><span data-stu-id="10bb6-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="10bb6-130">Če želite uporabiti modele umetne inteligence za pametno predvidevanje semantike, prihranite čas in izboljšajte natančnost, možnost **Pametna preslikava** nastavite na **VKLOPLJENO**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="10bb6-131">Pametna preslikava označi priporočila semantike na podlagi umetne inteligence v polju **Vrsta**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="10bb6-132">Če jo nastavite na **IZKLOPLJENO**, boste videli naša običajna priporočila za preslikavo.</span><span class="sxs-lookup"><span data-stu-id="10bb6-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="10bb6-133">Na razpoložljivem seznamu možnosti lahko izberete katero koli semantično vrsto in preglasite predlagani izbor.</span><span class="sxs-lookup"><span data-stu-id="10bb6-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="10bb6-134">![Vrsta atributa in predvidevanje semantike](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Vrsta atributa in predvidevanje semantike")</span><span class="sxs-lookup"><span data-stu-id="10bb6-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="10bb6-135">Možno je tudi dodajanje vrste semantike po meri.</span><span class="sxs-lookup"><span data-stu-id="10bb6-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="10bb6-136">Izberite polje vrste za atribut in vnesite ime za vrsto semantike po meri.</span><span class="sxs-lookup"><span data-stu-id="10bb6-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="10bb6-137">Tako lahko spremenite tudi vrste atributov, ki jih je sistem prepoznal.</span><span class="sxs-lookup"><span data-stu-id="10bb6-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="10bb6-138">Vsi atributi, za katere je vrsta semantike samodejno določena, so združeni v razdelku **Pregled preslikanih polj**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="10bb6-139">Preglejte te atribute in njihove vrste semantike, ker bodo uporabljeni za združevanje vaših entitet v koraku spajanja, kjer se poenotijo podatki.</span><span class="sxs-lookup"><span data-stu-id="10bb6-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="10bb6-140">Atributi, ki niso samodejno preslikani v vrsto semantike, so združeni v razdelku **Določanje podatkov v nepreslikanih poljih**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="10bb6-141">Izberite polje vrste semantike za nepreslikane atribute ali vnesite ime vrste atributa po meri.</span><span class="sxs-lookup"><span data-stu-id="10bb6-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="10bb6-142">![Primarni ključ in vrsta atributa](media/data-manager-configure-map-add-attributes.png "Primarni ključ in vrsta atributa")</span><span class="sxs-lookup"><span data-stu-id="10bb6-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="10bb6-143">Eno polje se mora preslikati v vrsto semantike »Person.FullName«, da ime stranke vnese v kartico stranke.</span><span class="sxs-lookup"><span data-stu-id="10bb6-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="10bb6-144">Sicer bodo kartice strank prikazane brez imen.</span><span class="sxs-lookup"><span data-stu-id="10bb6-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="10bb6-145">Dodajanje in odstranjevanje atributov in entitet</span><span class="sxs-lookup"><span data-stu-id="10bb6-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="10bb6-146">V razdelku **Poenotenje** > **Preslikava** izberite **Uredi polja**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="10bb6-147">V podoknu **Uredi polja** dodajte ali odstranite atribute in entitete.</span><span class="sxs-lookup"><span data-stu-id="10bb6-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="10bb6-148">Z iskanjem ali drsanjem navzdol in navzgor poiščite atribute in entitete, ki vas zanimajo, in jih izberite.</span><span class="sxs-lookup"><span data-stu-id="10bb6-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="10bb6-149">Atributa ali entitete ne morete odstraniti, če se že ujema.</span><span class="sxs-lookup"><span data-stu-id="10bb6-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10bb6-150">![Dodajanje ali odstranjevanje atributov](media/configure-data-map-edit.png "Dodajanje ali odstranjevanje atributov")</span><span class="sxs-lookup"><span data-stu-id="10bb6-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="10bb6-151">Izberite **Uporabi**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="10bb6-152">Dodajanje slik v profile</span><span class="sxs-lookup"><span data-stu-id="10bb6-152">Add images to profiles</span></span>

<span data-ttu-id="10bb6-153">Če entiteta vsebuje URL-je za javno dostopne slike profilov ali logotipe, jih lahko dodate v poenoten profil stranke.</span><span class="sxs-lookup"><span data-stu-id="10bb6-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="10bb6-154">Izberite entiteto in poiščite polje, ki vsebuje URL slike profila.</span><span class="sxs-lookup"><span data-stu-id="10bb6-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="10bb6-155">V vnosno polje **Vrsta** ročno vnesite naslednjo vrednost:</span><span class="sxs-lookup"><span data-stu-id="10bb6-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="10bb6-156">Za osebo: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="10bb6-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="10bb6-157">Za organizacijo: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="10bb6-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="10bb6-158">Nadaljujte s koraki za poenotenje in poskrbite, da je atribut, ki vsebuje URL slike, dodan tudi v korak [Spajanje](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="10bb6-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="10bb6-159">Nastavitev atributov za organizacije</span><span class="sxs-lookup"><span data-stu-id="10bb6-159">Set attributes for organizations</span></span>

<span data-ttu-id="10bb6-160">Za organizacije (predogledna različica) mora biti vrsta atributa preslikana v »Organization.Name«</span><span class="sxs-lookup"><span data-stu-id="10bb6-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="10bb6-161">![Primarni ključ in vrsta atributa pri prodaji podjetjem](media/configure-data-map-edit-b2b.png "Primarni ključ in vrsta atributa pri prodaji podjetjem")</span><span class="sxs-lookup"><span data-stu-id="10bb6-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="10bb6-162">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="10bb6-162">Next step</span></span>

<span data-ttu-id="10bb6-163">Kot del postopka poenotenja podatkov pojdite na stran **Ujemanje**.</span><span class="sxs-lookup"><span data-stu-id="10bb6-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="10bb6-164">Obiščite stran [**Ujemanje**](match-entities.md), kjer najdete več informacij o tej fazi.</span><span class="sxs-lookup"><span data-stu-id="10bb6-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="10bb6-165">Oglejte si ta videoposnetek: [Uvod: Ustvarjanje poenotenega profila stranke](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="10bb6-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]