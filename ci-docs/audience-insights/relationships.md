---
title: Odnosi med entitetami in poti entitet
description: Ustvarite in upravljajte odnose med entitetami iz več virov podatkov.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269901"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="c3582-103">Odnosi med entitetami</span><span class="sxs-lookup"><span data-stu-id="c3582-103">Relationships between entities</span></span>

<span data-ttu-id="c3582-104">Odnosi vam pomagajo pri povezovanju entitet in ustvarjanju grafa vaših podatkov, kadar si entitete delijo skupni identifikator (tuji ključ), na katerega se je mogoče sklicevati iz ene entitete v drugo.</span><span class="sxs-lookup"><span data-stu-id="c3582-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="c3582-105">Povezane entitete vam omogočajo, da določite segmente in mere na podlagi več virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="c3582-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="c3582-106">Obstajata dve vrsti odnosov.</span><span class="sxs-lookup"><span data-stu-id="c3582-106">There are two types of relationships.</span></span> <span data-ttu-id="c3582-107">Sistemski odnosi, ki so ustvarjeni samodejno in jih ni mogoče urejati, ter odnosi po meri, ki jih ustvarijo in konfigurirajo uporabniki.</span><span class="sxs-lookup"><span data-stu-id="c3582-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="c3582-108">Med postopki ujemanja in spajanja so sistemski odnosi ustvarjeni v ozadju na osnovi pametnega ujemanja.</span><span class="sxs-lookup"><span data-stu-id="c3582-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="c3582-109">Ti odnosi pomagajo povezati zapise profila stranke z drugimi ustreznimi zapisi entitet.</span><span class="sxs-lookup"><span data-stu-id="c3582-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="c3582-110">Spodnji diagram prikazuje ustvarjanje treh sistemskih odnosov, ko se entiteta stranke ujema z dodatnimi entitetami in se ustvari entiteta končnega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="c3582-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3582-111">![Ustvarjanje odnosa](media/relationships-entities-merge.png "Ustvarjanje odnosa")</span><span class="sxs-lookup"><span data-stu-id="c3582-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="c3582-112">**Odnos *CustomerToContact*** je bil ustvarjen med entiteto stranke in entiteto stika.</span><span class="sxs-lookup"><span data-stu-id="c3582-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="c3582-113">Za entiteto stranke se uporabi polje ključa **Contact_contactId** za povezovanje s poljem ključa entitete stika **contactId**.</span><span class="sxs-lookup"><span data-stu-id="c3582-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="c3582-114">**Odnos *CustomerToAccount*** je bil ustvarjen med entiteto stranke in entiteto kupca.</span><span class="sxs-lookup"><span data-stu-id="c3582-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="c3582-115">Za entiteto stranke se uporabi polje ključa **Account_accountId** za povezovanje s poljem ključa entitete kupca **accountId**.</span><span class="sxs-lookup"><span data-stu-id="c3582-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="c3582-116">**Odnos *CustomerToWebAccount*** je bil ustvarjen med entiteto stranke in entiteto spletnega kupca.</span><span class="sxs-lookup"><span data-stu-id="c3582-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="c3582-117">Za entiteto stranke se uporabi polje ključa **WebAccount_webaccountId** za povezovanje s poljem ključa entitete spletnega kupca **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="c3582-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="c3582-118">Ustvarjanje odnosa</span><span class="sxs-lookup"><span data-stu-id="c3582-118">Create a relationship</span></span>

<span data-ttu-id="c3582-119">Na strani **Odnosi** določite odnose po meri.</span><span class="sxs-lookup"><span data-stu-id="c3582-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="c3582-120">Vsak odnos je sestavljen iz izvorne entitete (entiteta, ki ima tuji ključ) in ciljne entitete (entiteta, na katero kaže tuji ključ izvorne entitete).</span><span class="sxs-lookup"><span data-stu-id="c3582-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="c3582-121">Pri vpogledih v občinstvo izberite **Podatki** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="c3582-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c3582-122">Izberite **Nov odnos**.</span><span class="sxs-lookup"><span data-stu-id="c3582-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="c3582-123">V podoknu **Dodaj odnos** vnesite te podatke:</span><span class="sxs-lookup"><span data-stu-id="c3582-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3582-124">![Vnos podrobnosti o odnosu](media/relationships-add.png "Vnos podrobnosti o odnosu")</span><span class="sxs-lookup"><span data-stu-id="c3582-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="c3582-125">**Ime odnosa**: ime, ki odraža namen odnosa (npr. **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="c3582-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="c3582-126">**Opis**: opis odnosa.</span><span class="sxs-lookup"><span data-stu-id="c3582-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="c3582-127">**Izvorna entiteta**: izberite entiteto, ki se uporablja kot vir v odnosu (na primer WebLog).</span><span class="sxs-lookup"><span data-stu-id="c3582-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="c3582-128">**Kardinalnost**: izberite kardinalnost zapisov izvorne entitete.</span><span class="sxs-lookup"><span data-stu-id="c3582-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="c3582-129">»Mnogo« na primer pomeni, da je več zapisov Weblog povezanih z eno entiteto WebAccount.</span><span class="sxs-lookup"><span data-stu-id="c3582-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c3582-130">**Polje izvornega ključa**: predstavlja polje za tuji ključ v izvorni entiteti.</span><span class="sxs-lookup"><span data-stu-id="c3582-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="c3582-131">WebLog ima na primer polje za tuji ključ **accountId**.</span><span class="sxs-lookup"><span data-stu-id="c3582-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="c3582-132">**Ciljna entiteta**: izberite entiteto, ki se uporablja kot cilj v odnosu (na primer WebAccount).</span><span class="sxs-lookup"><span data-stu-id="c3582-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="c3582-133">**Kardinalnost cilja**: izberite kardinalnost zapisov ciljne entitete.</span><span class="sxs-lookup"><span data-stu-id="c3582-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="c3582-134">»Ena« na primer pomeni, da je več zapisov Weblog povezanih z eno entiteto WebAccount.</span><span class="sxs-lookup"><span data-stu-id="c3582-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c3582-135">**Ciljno polje ključa**: to polje predstavlja polje ključa ciljne entitete.</span><span class="sxs-lookup"><span data-stu-id="c3582-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="c3582-136">WebAccount ima na primer polje ključa **accountId**.</span><span class="sxs-lookup"><span data-stu-id="c3582-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="c3582-137">Podprti so samo odnosi »mnogo proti ena« in »ena proti ena«.</span><span class="sxs-lookup"><span data-stu-id="c3582-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="c3582-138">Odnose »mnogo proti mnogo« lahko ustvarite z uporabo dveh odnosov »mnogo proti ena« in entiteto povezave (entiteta, ki se uporablja za povezovanje izvorne in ciljne entitete).</span><span class="sxs-lookup"><span data-stu-id="c3582-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="c3582-139">Brisanje odnosa</span><span class="sxs-lookup"><span data-stu-id="c3582-139">Delete a relationship</span></span>

1. <span data-ttu-id="c3582-140">Pri vpogledih v občinstvo izberite **Podatki** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="c3582-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c3582-141">Potrdite polja pri odnosih, ki jih želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="c3582-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="c3582-142">Izberite **Izbriši** na vrhu tabele **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="c3582-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="c3582-143">Potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="c3582-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="c3582-144">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="c3582-144">Next step</span></span>

<span data-ttu-id="c3582-145">Sistemski odnosi in odnosi po meri se uporabljajo za ustvarjanje segmentov na podlagi več virov podatkov, ki niso več ločeni.</span><span class="sxs-lookup"><span data-stu-id="c3582-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="c3582-146">Če želite več informacij, glejte [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c3582-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]