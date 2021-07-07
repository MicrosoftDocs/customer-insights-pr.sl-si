---
title: Dejavnosti stranke
description: Določite dejavnosti stranke in si jih oglejte na časovnici stranke.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304946"
---
# <a name="customer-activities"></a><span data-ttu-id="f04ec-103">Dejavnosti stranke</span><span class="sxs-lookup"><span data-stu-id="f04ec-103">Customer activities</span></span>

<span data-ttu-id="f04ec-104">Združite dejavnosti strank iz [različnih virov podatkov](data-sources.md) v rešitvi Dynamics 365 Customer Insights, da ustvarite časovnico, ki dejavnosti našteva v časovnem zaporedju.</span><span class="sxs-lookup"><span data-stu-id="f04ec-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="f04ec-105">V aplikacijah Dynamics 365 vključite časovnico z rešitvijo [Dodatek za kartico stranke](customer-card-add-in.md) ali v nadzorni plošči storitve Power BI.</span><span class="sxs-lookup"><span data-stu-id="f04ec-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="f04ec-106">Določanje dejavnosti</span><span class="sxs-lookup"><span data-stu-id="f04ec-106">Define an activity</span></span>

<span data-ttu-id="f04ec-107">Vaši viri podatkov lahko vključujejo entitete s transakcijskimi podatki in podatki o dejavnosti iz več virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="f04ec-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="f04ec-108">Določite te entitete in izberite časovnice, ki si jih želite ogledati na časovnici stranke.</span><span class="sxs-lookup"><span data-stu-id="f04ec-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="f04ec-109">Izberite entiteto, ki vključuje vašo ciljno dejavnost ali dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="f04ec-110">Entiteta mora imeti vsaj en atribut vrste **Datum**, da je lahko vključena na časovnico stranke, vi pa ne morete dodajati entitet brez polja **Datum**.</span><span class="sxs-lookup"><span data-stu-id="f04ec-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="f04ec-111">Ukaz **Dodaj dejavnost** je onemogočen, če take entitete ni mogoče najti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="f04ec-112">Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="f04ec-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="f04ec-113">Izberite možnost **Dodaj dejavnost**, da se začne vodena izkušnja za postopek nastavitve dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="f04ec-114">V koraku **Podatki o dejavnosti** nastavite vrednosti za naslednja polja:</span><span class="sxs-lookup"><span data-stu-id="f04ec-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="f04ec-115">**Ime dejavnosti**: izberite ime dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="f04ec-116">**Entiteta**: izberite entiteto, ki vključuje transakcijske podatke ali podatke o dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="f04ec-117">**Primarni ključ**: izberite polje, ki edinstveno določi zapis.</span><span class="sxs-lookup"><span data-stu-id="f04ec-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="f04ec-118">Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavite podatke o dejavnosti za ime, entiteto in primarni ključ.":::

1. <span data-ttu-id="f04ec-120">Izberite možnost **Naprej** za pomik na naslednji korak.</span><span class="sxs-lookup"><span data-stu-id="f04ec-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="f04ec-121">V koraku **Odnos** konfigurirajte podrobnosti za povezavo podatkov o dejavnosti z ustrezno stranko.</span><span class="sxs-lookup"><span data-stu-id="f04ec-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="f04ec-122">V koraku so upodobljene povezave med entitetami.</span><span class="sxs-lookup"><span data-stu-id="f04ec-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="f04ec-123">**Prvič**: tuje polje v entiteti dejavnosti, ki bo uporabljeno za vzpostavitev odnosa z drugo entiteto.</span><span class="sxs-lookup"><span data-stu-id="f04ec-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="f04ec-124">**Drugič**: ustrezna izvorna entiteta stranke, s katero bo entiteta dejavnosti v odnosu.</span><span class="sxs-lookup"><span data-stu-id="f04ec-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="f04ec-125">Nanašate se lahko samo na izvorne entitete strank, ki se uporabljajo v postopku poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="f04ec-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="f04ec-126">**Tretjič**: če odnos med to entiteto dejavnosti in izbrano izvorno entiteto stranke že obstaja, bo ime odnosa v načinu samo za branje.</span><span class="sxs-lookup"><span data-stu-id="f04ec-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="f04ec-127">Če takšen odnos ni na voljo, bo na podlagi imena, ki ste ga navedli v tem polju, ustvarjen nov.</span><span class="sxs-lookup"><span data-stu-id="f04ec-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Določite odnos entitete.":::

1. <span data-ttu-id="f04ec-129">Izberite možnost **Naprej** za pomik na naslednji korak.</span><span class="sxs-lookup"><span data-stu-id="f04ec-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="f04ec-130">V koraku **Poenotenje dejavnosti** izberite dogodek dejavnosti in čas začetka dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="f04ec-131">**Zahtevana polja**</span><span class="sxs-lookup"><span data-stu-id="f04ec-131">**Required fields**</span></span>
      - <span data-ttu-id="f04ec-132">**Dejavnost dogodka**: polje, ki predstavlja dogodek za to dejavnost.</span><span class="sxs-lookup"><span data-stu-id="f04ec-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="f04ec-133">**Časovni žig**: polje, ki predstavlja čas začetka dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="f04ec-134">**Izbirna polja**</span><span class="sxs-lookup"><span data-stu-id="f04ec-134">**Optional fields**</span></span>
      - <span data-ttu-id="f04ec-135">**Dodatne podrobnosti**: polje z relevantnimi informacijami za to dejavnost.</span><span class="sxs-lookup"><span data-stu-id="f04ec-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="f04ec-136">**Ikona**: ikona, ki najbolje predstavlja to vrsto dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="f04ec-137">**Spletni naslov** : polje z URL-jem s podatki o tej dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="f04ec-138">Na primer transakcijski sistem, ki je vir te dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="f04ec-139">Ta URL je lahko katero koli polje iz vira podatkov, lahko pa je oblikovano kot novo polje s pretvorbo v orodju Power Query.</span><span class="sxs-lookup"><span data-stu-id="f04ec-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="f04ec-140">Podatki z URL-ja bodo shranjeni v entiteti *Poenotena dejavnost*, ki se lahko porabi v nadaljnjem toku z uporabo [API-jev](apis.md).</span><span class="sxs-lookup"><span data-stu-id="f04ec-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="V entiteti Poenotena dejavnost navedite podatke o dejavnosti stranke.":::

1. <span data-ttu-id="f04ec-142">Izberite možnost **Naprej** za pomik na naslednji korak.</span><span class="sxs-lookup"><span data-stu-id="f04ec-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="f04ec-143">Izberete lahko možnost **Zaključek in pregled**, da takoj shranite dejavnost z vrsto dejavnosti, nastavljeno na možnost **Drugo**.</span><span class="sxs-lookup"><span data-stu-id="f04ec-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="f04ec-144">V koraku **Vrsta dejavnosti** izberite vrsto dejavnosti in po želji izberite, ali želite semantično preslikati nekatere vrste dejavnosti za uporabo na drugih področjih storitve Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f04ec-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="f04ec-145">Po potrditvi, da se strinjate s preslikavo polij, je mogoče dejavnosti *naročnina* in *SalesOrderLine* semantično preslikati.</span><span class="sxs-lookup"><span data-stu-id="f04ec-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="f04ec-146">Če vrsta dejavnosti za novo dejavnost ni pomembna, lahko izberete možnost *Drugo* ali *Ustvari novo* za prilagojeno vrsto dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="f04ec-147">Izberite možnost **Naprej** za pomik na naslednji korak.</span><span class="sxs-lookup"><span data-stu-id="f04ec-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="f04ec-148">V koraku **Pregled** preverite svoje izbire.</span><span class="sxs-lookup"><span data-stu-id="f04ec-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="f04ec-149">Vrnite se na kateregakoli izmed prejšnjih korakov in posodobite podatke, če je to potrebno.</span><span class="sxs-lookup"><span data-stu-id="f04ec-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Preglejte navedena polja za dejavnost.":::
   
1. <span data-ttu-id="f04ec-151">Izberite možnost **Shrani dejavnost** za uporabo sprememb in izberite možnost **Končano**, da se vrnete v razdelek **Podatki** > **Dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="f04ec-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="f04ec-152">Tukaj vidite, katere dejavnosti so nastavljene za prikaz na časovnici.</span><span class="sxs-lookup"><span data-stu-id="f04ec-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="f04ec-153">Za obdelavo dejavnosti na strani **Dejavnosti** izberite možnost **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="f04ec-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="f04ec-154">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="f04ec-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f04ec-155">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f04ec-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f04ec-156">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="f04ec-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f04ec-157">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="f04ec-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="f04ec-158">Upravljanje obstoječih dejavnosti</span><span class="sxs-lookup"><span data-stu-id="f04ec-158">Manage existing activities</span></span>

<span data-ttu-id="f04ec-159">V razdelku **Podatki** > **Dejavnosti** si lahko ogledate vse shranjene dejavnosti in jih upravljate.</span><span class="sxs-lookup"><span data-stu-id="f04ec-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="f04ec-160">Vsaka dejavnost je predstavljena z vrstico, ki vključuje tudi podrobnosti o viru, entiteti in vrsti dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="f04ec-161">Ko izberete dejavnost, so na voljo naslednja dejanja.</span><span class="sxs-lookup"><span data-stu-id="f04ec-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="f04ec-162">**Uredi**: odpre korak nastavitve dejavnosti v koraku pregleda.</span><span class="sxs-lookup"><span data-stu-id="f04ec-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="f04ec-163">V tem koraku lahko spremenite vse trenutne konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="f04ec-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="f04ec-164">Po spremembi konfiguracije izberite možnost **Shrani dejavnost** in nato izberite možnost **Zaženi** za obdelavo sprememb.</span><span class="sxs-lookup"><span data-stu-id="f04ec-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="f04ec-165">**Preimenujte**: odpre pogovorno okno, kamor lahko za izbrano dejavnost vnesete drugačno poimenovanje.</span><span class="sxs-lookup"><span data-stu-id="f04ec-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="f04ec-166">Če želite uporabiti spremembe, izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="f04ec-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="f04ec-167">**Izbriši**: odpre pogovorno okno za potrditev brisanja izbrane dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="f04ec-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="f04ec-168">Izbrišete lahko tudi več dejavnosti hkrati, in sicer tako, da izberete dejavnosti ter nato izberete ikono za brisanje.</span><span class="sxs-lookup"><span data-stu-id="f04ec-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="f04ec-169">Izberite možnost **Izbriši**, da pordite izbris.</span><span class="sxs-lookup"><span data-stu-id="f04ec-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
