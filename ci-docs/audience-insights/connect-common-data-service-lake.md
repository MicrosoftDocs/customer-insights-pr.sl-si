---
title: Povezovanje z entitetami v upravljanem jezeru Common Data Service
description: Uvozite podatke iz upravljanega jezera podatkov Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596979"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="f0fc0-103">Povezovanje s podatki v upravljanem jezeru podatkov Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f0fc0-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f0fc0-104">Ta članek vsebuje informacije o tem, kako se lahko obstoječe stranke Dynamics 365 hitro povežejo s svojimi analitičnimi entitetami v Common Data Service upravljanem jezeru.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="f0fc0-105">Biti morate skrbnik organizacije Common Data Service, da lahko nadaljujete in si ogleda seznam entitet, ki so na voljo v upravljanem jezeru.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="f0fc0-106">Pomembni premisleki</span><span class="sxs-lookup"><span data-stu-id="f0fc0-106">Important considerations</span></span>

<span data-ttu-id="f0fc0-107">Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="f0fc0-108"> Z uvažanjem podatkov ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se podatki lahko prenesejo in shranijo v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="f0fc0-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="f0fc0-109">Povezava z upravljanim jezerom Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f0fc0-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="f0fc0-110">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f0fc0-111">Izberite **Dodaj vir podatkov**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="f0fc0-112">Izberite **Vzpostavi povezavo z Common Data Service** in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="f0fc0-113">Vnesite **ime** za vir podatkov in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="f0fc0-114">Smernice za poimenovanje:</span><span class="sxs-lookup"><span data-stu-id="f0fc0-114">Name guidelines:</span></span> 
   - <span data-ttu-id="f0fc0-115">Začnite s črko.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-115">Start with a letter.</span></span>
   - <span data-ttu-id="f0fc0-116">Uporabljajte samo črke in številke.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-116">Use letters and numbers only.</span></span> <span data-ttu-id="f0fc0-117">Posebni znaki in presledki niso dovoljeni.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="f0fc0-118">Uporabite od 3 do 64 znakov.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="f0fc0-119">Navedite **Naslov strežnika** za svojo organizacijo Common Data Service in izberite **Vpis**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f0fc0-120">![Pogovorno okno za vnos naslova strežnika za Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="f0fc0-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="f0fc0-121">Na seznamu razpoložljivih možnosti izberite entitete, ki jih želite vključiti.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="f0fc0-122">Če so nekatere entitete že izbrane, jih lahko uporabljajo druge aplikacije Dynamics 365 (kot so Dynamics 365 Sales Insights ali Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="f0fc0-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="f0fc0-123">Tega izbora ni mogoče spremeniti.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-123">You can't change the selection.</span></span> <span data-ttu-id="f0fc0-124">Te entitete bodo na voljo, ko bo ustvarjen vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f0fc0-125">![Pogovorno okno s seznamom entitet v organizaciji Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="f0fc0-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="f0fc0-126">Shranite izbor, da začnete sinhronizirati izbrane entitete v upravljano jezero Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="f0fc0-127">Novo dodano povezavo najdete na strani **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="f0fc0-128">Dana bo v čakalno vrsto za osvežitev in število entitet bo prikazano kot 0, dokler niso vse entitete sinhronizirane.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="f0fc0-129">Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="f0fc0-130">Urejanje vira podatkov upravljanega jezera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f0fc0-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="f0fc0-131">Izbor entitet uredite šele po ustvarjanju vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="f0fc0-132">Če bi bili na primer dodane dodatne entitete v Common Data Service in želite uvoziti tudi njih.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="f0fc0-133">Če se želite povezati v drugo Common Data Service, [ustvarite nov vir podatkov](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="f0fc0-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="f0fc0-134">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f0fc0-135">Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="f0fc0-136">Na seznamu izberite možnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="f0fc0-137">Izberite dodatne entitete z razpoložljivega seznama entitet in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]