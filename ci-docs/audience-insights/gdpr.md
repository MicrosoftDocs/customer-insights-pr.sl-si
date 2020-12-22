---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odgovorite na zahteve posameznikov, na katere se nanašajo podatki, za zmogljivost vpogledov v občinstvo Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406978"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="623fa-103">Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR</span><span class="sxs-lookup"><span data-stu-id="623fa-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="623fa-104">Odgovorite na zahteve posameznikov, na katere se nanašajo podatki, za izbris za zmogljivost vpogledov v občinstvo Dynamics 365 Customer Insights, v skladu z uredbo GDPR.</span><span class="sxs-lookup"><span data-stu-id="623fa-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="623fa-105">»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR).</span><span class="sxs-lookup"><span data-stu-id="623fa-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="623fa-106">Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.</span><span class="sxs-lookup"><span data-stu-id="623fa-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="623fa-107">Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris</span><span class="sxs-lookup"><span data-stu-id="623fa-107">Manage data subject delete requests</span></span>

<span data-ttu-id="623fa-108">Vpogledi v občinstvo nudijo naslednje izkušnje v izdelkih, s katerimi lahko izbrišete osebne podatke za določeno stranko ali uporabnika:</span><span class="sxs-lookup"><span data-stu-id="623fa-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="623fa-109">**Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="623fa-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="623fa-110">Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v izvirnem viru podatkov.</span><span class="sxs-lookup"><span data-stu-id="623fa-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="623fa-111">**Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="623fa-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="623fa-112">Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="623fa-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="623fa-113">Upravljanje zahtev za izbris podatkov o strankah</span><span class="sxs-lookup"><span data-stu-id="623fa-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="623fa-114">Skrbnik storitve Customer Insights lahko upošteva te korake, da odstrani podatke stranke, ki so bili izbrisani iz vira podatkov:</span><span class="sxs-lookup"><span data-stu-id="623fa-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="623fa-115">Vpis v storitev Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="623fa-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="623fa-116">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="623fa-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="623fa-117">Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:</span><span class="sxs-lookup"><span data-stu-id="623fa-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="623fa-118">Izberite možnost (...) in nato **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="623fa-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="623fa-119">Preverite stanje vira podatkov v razdelku **Stanje**.</span><span class="sxs-lookup"><span data-stu-id="623fa-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="623fa-120">Kljukica pomeni, da je bila osvežitev uspešna.</span><span class="sxs-lookup"><span data-stu-id="623fa-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="623fa-121">Opozorilni trikotnik pomeni, da je prišlo do napake.</span><span class="sxs-lookup"><span data-stu-id="623fa-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="623fa-122">Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="623fa-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="623fa-123">![Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR](media/gdpr-data-sources.png "Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR")</span><span class="sxs-lookup"><span data-stu-id="623fa-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="623fa-124">Upravljanje zahtev za izbris uporabniških podatkov</span><span class="sxs-lookup"><span data-stu-id="623fa-124">Manage delete requests for user data</span></span>

<span data-ttu-id="623fa-125">Skrbnik storitve Customer Insights lahko za izbris uporabniških podatkov storitve Customer Insights upošteva te korake:</span><span class="sxs-lookup"><span data-stu-id="623fa-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="623fa-126">Vpis v storitev Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="623fa-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="623fa-127">Pri vpogledih v občinstvo izberite **Skrbnik** > **Dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="623fa-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="623fa-128">Potrdite polje za uporabnika, ki ga želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="623fa-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="623fa-129">Izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="623fa-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="623fa-130">![Upravljanje zahtev za izbris uporabniških podatkov v skladu z uredbo GDPR](media/gdpr-permissions.png "Upravljanje zahtev za izbris uporabniških podatkov v skladu z uredbo GDPR")</span><span class="sxs-lookup"><span data-stu-id="623fa-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="623fa-131">Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR</span><span class="sxs-lookup"><span data-stu-id="623fa-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="623fa-132">Kot del naše zaveze za sodelovanje z vami na vaši poti do uvedbe Splošne uredbe o varstvu podatkov (GDPR) smo ustvarili dokumentacijo, ki vam bo pomagala pri pripravi.</span><span class="sxs-lookup"><span data-stu-id="623fa-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="623fa-133">Ta dokumentacija opisuje korake, ki jih lahko danes opravite za zagotavljanje skladnosti z uredbo GDPR pri uporabi vpogledov v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="623fa-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="623fa-134">Upravljajte izvoza in ogled zahtev</span><span class="sxs-lookup"><span data-stu-id="623fa-134">Manage export and view requests</span></span>

<span data-ttu-id="623fa-135">Zaradi pravice do prenosljivosti podatkov lahko posamezniki, na katere se nanašajo podatki, zahtevajo kopijo svojih osebnih podatkov v elektronski obliki (tj. »strukturirana, pogosto uporabljena, strojno berljiva in interoperabilna oblika«), ki se jo lahko pošlje drugemu upravljavcu podatkov.</span><span class="sxs-lookup"><span data-stu-id="623fa-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="623fa-136">Izvoz podatkov o stranki (skrbnik najemnika)</span><span class="sxs-lookup"><span data-stu-id="623fa-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="623fa-137">Skrbnik najemnika lahko za izvoz podatkov upošteva ta navodila:</span><span class="sxs-lookup"><span data-stu-id="623fa-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="623fa-138">Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="623fa-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="623fa-139">Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.</span><span class="sxs-lookup"><span data-stu-id="623fa-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="623fa-140">Potrdite potrditev izvoza podatkov za zahtevano stranko.</span><span class="sxs-lookup"><span data-stu-id="623fa-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="623fa-141">Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.</span><span class="sxs-lookup"><span data-stu-id="623fa-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="623fa-142">Izvoz uporabniških podatkov (skrbnik najemnika)</span><span class="sxs-lookup"><span data-stu-id="623fa-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="623fa-143">Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov uporabnika.</span><span class="sxs-lookup"><span data-stu-id="623fa-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="623fa-144">Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.</span><span class="sxs-lookup"><span data-stu-id="623fa-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="623fa-145">Potrdite potrditev izvoza podatkov za zahtevanega uporabnika.</span><span class="sxs-lookup"><span data-stu-id="623fa-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="623fa-146">Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.</span><span class="sxs-lookup"><span data-stu-id="623fa-146">Receive the exported data through the tenant admin email address.</span></span>
