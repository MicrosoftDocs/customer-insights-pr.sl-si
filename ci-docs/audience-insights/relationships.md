---
title: Odnosi med entitetami in poti entitet
description: Ustvarite in upravljajte odnose med entitetami iz več virov podatkov.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171184"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="a0e9a-103">Odnosi med entitetami</span><span class="sxs-lookup"><span data-stu-id="a0e9a-103">Relationships between entities</span></span>

<span data-ttu-id="a0e9a-104">Odnosi povezujejo entitete in definirajo graf vaših podatkov, ko imajo entitete skupni identifikator, tj. tuji ključ.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="a0e9a-105">Ta tuji ključ se lahko sklicuje od ene entitete na drugo.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="a0e9a-106">Povezane entitete omogočajo določitev segmentov in ukrepov na podlagi več virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="a0e9a-107">Obstajajo tri vrste odnosov:</span><span class="sxs-lookup"><span data-stu-id="a0e9a-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="a0e9a-108">Sistemski odnosi, ki jih ni mogoče urejati in jih je ustvaril sistem kot del postopka za poenotenje podatkov</span><span class="sxs-lookup"><span data-stu-id="a0e9a-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="a0e9a-109">Podedovani odnosi, ki jih ni mogoče urejati in se samodejno ustvarijo iz vnesenih virov podatkov</span><span class="sxs-lookup"><span data-stu-id="a0e9a-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="a0e9a-110">Odnosi po meri, ki jih je mogoče urejati in jih ustvarjajo in konfigurirajo uporabniki</span><span class="sxs-lookup"><span data-stu-id="a0e9a-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="a0e9a-111">Sistemski odnosi, ki jih ni mogoče urejati</span><span class="sxs-lookup"><span data-stu-id="a0e9a-111">Non-editable system relationships</span></span>

<span data-ttu-id="a0e9a-112">Med poenotenjem podatkov se sistemski odnosi samodejno ustvarijo na podlagi pametnega ujemanja.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="a0e9a-113">Ti odnosi pomagajo povezati zapise profila stranke z ustreznimi zapisi.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="a0e9a-114">Naslednji diagram prikazuje ustvarjanje treh sistemskih odnosov.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="a0e9a-115">Entiteto stranke se poveže z drugimi entitetami, da se ustvari poenotena entiteta *Stranka*.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s potmi odnosov za entiteto stranke s tremi odnosi 1-n.":::

- <span data-ttu-id="a0e9a-117">**Odnos *CustomerToContact*** je bil ustvarjen med entiteto *Stranka* in entiteto *Stik*.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="a0e9a-118">Za entiteto *Stranka* se uporabi polje ključa Contact_ **contactId** za povezovanje s poljem ključa entitete *Stik* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="a0e9a-119">**Odnos *CustomerToAccount*** je bil ustvarjen med entiteto *Stranka* in entiteto *Kupec*.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="a0e9a-120">Za entiteto *Stranka* se uporabi polje ključa Account_ **accountID** za povezovanje s poljem ključa entitete *Kupec* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="a0e9a-121">**Odnos *CustomerToWebAccount*** je bil ustvarjen med entiteto *Stranka* in entiteto *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="a0e9a-122">Za entiteto *Stranka* se uporabi polje ključa **WebAccount_webaccountID** za povezovanje s poljem ključa entitete *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="a0e9a-123">Podedovani odnosi, ki jih ni mogoče urejati</span><span class="sxs-lookup"><span data-stu-id="a0e9a-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="a0e9a-124">Med postopkom vnosa podatkov sistem preveri obstoječe odnose za vire podatkov.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="a0e9a-125">Če odnosi ne obstajajo, jih sistem samodejno ustvari.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="a0e9a-126">Ti odnosi se uporabljajo tudi v nadaljnjih postopkih.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="a0e9a-127">Ustvarjanje odnosa po meri</span><span class="sxs-lookup"><span data-stu-id="a0e9a-127">Create a custom relationship</span></span>

<span data-ttu-id="a0e9a-128">Odnos je sestavljen iz *izvorne entitete*, ki vsebuje tuji ključ, in *ciljne entitete*, na katero kaže tuji ključ izvorne entitete.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="a0e9a-129">Pri vpogledih v občinstvo izberite **Podatki** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="a0e9a-130">Izberite **Nov odnos**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="a0e9a-131">V podokno **Nov odnos** vnesite te podatke:</span><span class="sxs-lookup"><span data-stu-id="a0e9a-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Podokno za nov odnos s praznimi vnosnimi polji.":::

   - <span data-ttu-id="a0e9a-133">**Ime odnosa**: ime, ki odraža namen odnosa.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="a0e9a-134">Primer: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="a0e9a-135">**Opis**: opis odnosa.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="a0e9a-136">**Izvorna entiteta**: entiteta, ki se v odnosu uporablja kot vir.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="a0e9a-137">Primer: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="a0e9a-138">**Ciljna entiteta**: entiteta, ki se v odnosu uporablja kot cilj.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="a0e9a-139">Primer: Stranka.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-139">Example: Customer.</span></span>
   - <span data-ttu-id="a0e9a-140">**Kardinalnost vira**: določa kardinalnost izvorne entitete.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="a0e9a-141">Kardinalnost opisuje število možnih elementov v naboru.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="a0e9a-142">Navezuje se na ciljno kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="a0e9a-143">Izbirate lahko med **Ena** in **Mnogo**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="a0e9a-144">Podprti so samo odnosi »mnogo proti ena« in »ena proti ena«.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="a0e9a-145">Mnogo proti ena: več izvornih zapisov se lahko nanaša na en ciljni zapis.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="a0e9a-146">Primer: več primerov za podporo iz ene stranke.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="a0e9a-147">Ena proti ena: posamezen izvorni zapis se nanaša na en ciljni zapis.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="a0e9a-148">Primer: en ID zvestobe za eno stranko.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a0e9a-149">Odnose »mnogo proti mnogo« je mogoče ustvariti z dvema odnosoma »mnogo proti ena« in povezovalno entiteto, ki povezuje izvorno entiteto in ciljno entiteto.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="a0e9a-150">**Kardinalnost cilja**: izberite kardinalnost zapisov ciljne entitete.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="a0e9a-151">**Polje izvornega ključa**: polje tujega ključa v izvorni entiteti.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="a0e9a-152">Primer: SupportCase bi lahko uporabil CaseID kot polje tujega ključa.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="a0e9a-153">**Ciljno polje ključa**: polje ključa ciljne entitete.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="a0e9a-154">Primer, kjer bi lahko Stranka uporabila polje ključa **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="a0e9a-155">Izberite možnost **Shrani**, da ustvarite odnos po meri.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="a0e9a-156">Ogled odnosov</span><span class="sxs-lookup"><span data-stu-id="a0e9a-156">View relationships</span></span>

<span data-ttu-id="a0e9a-157">Na strani Odnosi so navedeni vsi ustvarjeni odnosi.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="a0e9a-158">Vsaka vrstica predstavlja odnos, ki vključuje tudi podrobnosti o izvorni entiteti, ciljni entiteti in kardinalnosti.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Seznam odnosov in možnosti v orodni vrstici strani Odnosi.":::

<span data-ttu-id="a0e9a-160">Ta stran ponuja nabor možnosti za obstoječe in nove odnose:</span><span class="sxs-lookup"><span data-stu-id="a0e9a-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="a0e9a-161">**Nov odnos**: [Ustvari odnos po meri](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="a0e9a-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="a0e9a-162">**Vizualizator**: [Raziščite vizualizator odnosov](#explore-the-relationship-visualizer), da si ogledate omrežni diagram obstoječih odnosov in njihovo kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="a0e9a-163">**Filtriraj po**: izberite vrsto odnosov, ki naj se prikažejo na seznamu.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="a0e9a-164">**Iskanje odnosov**: za iskanje lastnosti odnosov uporabite iskanje na podlagi besedila.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="a0e9a-165">Raziščite vizualizator odnosov</span><span class="sxs-lookup"><span data-stu-id="a0e9a-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="a0e9a-166">Vizualizator odnosov prikazuje omrežni diagram obstoječih odnosov med povezanimi entitetami in njihovo kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="a0e9a-167">Če želite prilagoditi pogled, lahko spremenite položaj polj tako, da jih povlečete na platno.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Posnetek zaslona omrežnega diagrama vizualizatorja odnosov s povezavami med povezanimi entitetami.":::

<span data-ttu-id="a0e9a-169">Razpoložljive možnosti:</span><span class="sxs-lookup"><span data-stu-id="a0e9a-169">Available options:</span></span> 
- <span data-ttu-id="a0e9a-170">**Izvozi kot sliko**: shranite trenutni pogled kot slikovno datoteko.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="a0e9a-171">**Spremeni v vodoravno/navpično postavitev**: spremenite poravnavo entitet in odnosov.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="a0e9a-172">**Uredi**: posodobite lastnosti odnosov po meri v podoknu za urejanje in shranite spremembe.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="a0e9a-173">Upravljanje obstoječih odnosov</span><span class="sxs-lookup"><span data-stu-id="a0e9a-173">Manage existing relationships</span></span> 

<span data-ttu-id="a0e9a-174">Na strani Odnosi vsak odnos predstavlja ena vrstica.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="a0e9a-175">Izberite odnos in eno od naslednjih možnosti:</span><span class="sxs-lookup"><span data-stu-id="a0e9a-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="a0e9a-176">**Uredi**: posodobite lastnosti odnosov po meri v podoknu za urejanje in shranite spremembe.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="a0e9a-177">**Izbriši**: izbrišite odnos po meri.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="a0e9a-178">**Pogled**: oglejte si sistemsko ustvarjene in podedovane odnose.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="a0e9a-179">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="a0e9a-179">Next step</span></span>

<span data-ttu-id="a0e9a-180">Sistemski odnosi in odnosi po meri se uporabljajo za [ustvarjanje segmentov](segments.md) na podlagi več virov podatkov, ki niso več ločeni.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
