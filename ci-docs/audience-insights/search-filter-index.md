---
title: Iskanje in filtriranje profilov strank
description: Hitro poiščite informacije o poenotenih profilih strank in filtrirajte za določene atribute.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597163"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="95639-103">Profili strank: Kazalo za iskanje in filtre</span><span class="sxs-lookup"><span data-stu-id="95639-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="95639-104">Rezultat poenotenja podatkov strank je vnos profila stranke, ki zagotavlja poenoten pogled v celotno bazo strank.</span><span class="sxs-lookup"><span data-stu-id="95639-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="95639-105">Za hitro [iskanje informacij o določeni stranki ali skupini strank](customer-profiles.md), lahko konfigurirate zmogljivosti **Iskanje** in **Filter** na strani **Stranke**.</span><span class="sxs-lookup"><span data-stu-id="95639-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="95639-106">Berite dalje, da boste izvedeli, kako uredite atribute na strani **Kazalo za iskanje in filtre**, ki je na voljo uporabnikom za iskanje in filtriranje.</span><span class="sxs-lookup"><span data-stu-id="95639-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="95639-107">![Filter za iskanje](media/search-filter.png "Filter za iskanje")</span><span class="sxs-lookup"><span data-stu-id="95639-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="95639-108">Dodajanje polj in določanje atributov</span><span class="sxs-lookup"><span data-stu-id="95639-108">Add fields and specify attributes</span></span>

<span data-ttu-id="95639-109">Če kot skrbnik prvikrat določate atribute, po katerih je mogoče iskati, morate najprej določiti indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="95639-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="95639-110">Predlagamo, da izberete vse atribute, po katerih lahko uporabniki iščejo in filtrirajo stranke na strani **Stranke**.</span><span class="sxs-lookup"><span data-stu-id="95639-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="95639-111">Določite lahko samo atribute, ki obstajajo v entiteti profila stranke, ki ste jo ustvarili med postopkom poenotenja.</span><span class="sxs-lookup"><span data-stu-id="95639-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="95639-112">Odprite stran **Stranke** in izberite **Kazalo za iskanje in filtre**.</span><span class="sxs-lookup"><span data-stu-id="95639-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="95639-113">Izberite **+ Dodaj**, da določite indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="95639-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="95639-114">Na seznamu izberite atribute, ki jih želite dodati kot indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="95639-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="95639-115">Zmeraj lahko dodate več atributov, tako da izberete **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="95639-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="95639-116">Vse izbrane atribute lahko odstranite tudi tako, da izberete simbol **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="95639-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="95639-117">Raziskovanje indeksirane tabele polj stranke</span><span class="sxs-lookup"><span data-stu-id="95639-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="95639-118">V tabeli so predstavljene naslednje informacije.</span><span class="sxs-lookup"><span data-stu-id="95639-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="95639-119">**Ime**: predstavlja ime atributa, kot je prikazano v entiteti profila stranke.</span><span class="sxs-lookup"><span data-stu-id="95639-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="95639-120">**Vrsta podatkov**: določa, ali je vrsta podatkov niz, številka ali datum.</span><span class="sxs-lookup"><span data-stu-id="95639-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="95639-121">**Vključeno v iskanje**: določa, ali je ta atribut mogoče uporabiti za iskanje strank na strani **Stranke** s poljem **Iskanje**.</span><span class="sxs-lookup"><span data-stu-id="95639-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="95639-122">**Dodaj filter**: kontrolnik za določanje, kako je mogoče ta atribut uporabljati za filtriranje na strani **Stranke**.</span><span class="sxs-lookup"><span data-stu-id="95639-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="95639-123">Urejanje možnosti filtriranja za določen atribut</span><span class="sxs-lookup"><span data-stu-id="95639-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="95639-124">Meni **Filter** na strani **Stranke** lahko vključuje različno število ravni atributa (na primer različne starostne skupine, po katerih se stranke filtrirajo).</span><span class="sxs-lookup"><span data-stu-id="95639-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="95639-125">Izberite **Dodaj filter** za določeni atribut na strani **Kazalo za iskanje in filtre**.</span><span class="sxs-lookup"><span data-stu-id="95639-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="95639-126">Določite lahko število rezultatov in vrsti red, v katerem bodo organizirani.</span><span class="sxs-lookup"><span data-stu-id="95639-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="95639-127">Odvisno od vrste podatkov atributa se prikaže eno od naslednjih podoken.</span><span class="sxs-lookup"><span data-stu-id="95639-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="95639-128">Atributi vrste niza: Določite število želenih rezultatov v podoknu **Možnosti filtra nizov** in politiko vrstnega reda, po kateri bodo organizirani.</span><span class="sxs-lookup"><span data-stu-id="95639-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="95639-129">Atributi vrste numerično: Določite vključene intervale v podoknu **Možnosti filtra številk** in politiko vrstnega reda, po kateri bodo organizirani.</span><span class="sxs-lookup"><span data-stu-id="95639-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="95639-130">Atributi vrste datuma: Določite vključene intervale v podoknu **Možnosti filtra datuma** in politiko vrstnega reda, po kateri bodo organizirani.</span><span class="sxs-lookup"><span data-stu-id="95639-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="95639-131">Če želite uporabiti spremembe, izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="95639-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="95639-132">Izberite **Zaženi**, ko ste pripravljeni na uveljavljanje nastavitev.</span><span class="sxs-lookup"><span data-stu-id="95639-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95639-133">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="95639-133">Next steps</span></span>

<span data-ttu-id="95639-134">Če želite poiskati profile strank, pojdite na stran **Uporabniki**, ali pa za prikaz podmnožice vseh profilov strank uporabite indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="95639-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]