---
title: Povezovanje z entitetami v upravljanem jezeru Common Data Service
description: Uvozite podatke iz upravljanega jezera podatkov Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643418"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="32d21-103">Povezovanje s podatki v upravljanem jezeru podatkov Common Data Service</span><span class="sxs-lookup"><span data-stu-id="32d21-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="32d21-104">Ta članek vsebuje informacije o tem, kako se lahko obstoječe stranke Dynamics 365 hitro povežejo s svojimi analitičnimi entitetami v Common Data Service upravljanem jezeru.</span><span class="sxs-lookup"><span data-stu-id="32d21-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="32d21-105">Biti morate skrbnik organizacije Common Data Service, da lahko nadaljujete in si ogleda seznam entitet, ki so na voljo v upravljanem jezeru.</span><span class="sxs-lookup"><span data-stu-id="32d21-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="32d21-106">Pomembni premisleki</span><span class="sxs-lookup"><span data-stu-id="32d21-106">Important considerations</span></span>

<span data-ttu-id="32d21-107">Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="32d21-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="32d21-108"> Z uvažanjem podatkov ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se podatki lahko prenesejo in shranijo v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="32d21-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="32d21-109">Povezava z upravljanim jezerom Common Data Service</span><span class="sxs-lookup"><span data-stu-id="32d21-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="32d21-110">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="32d21-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="32d21-111">Izberite **Dodaj vir podatkov**.</span><span class="sxs-lookup"><span data-stu-id="32d21-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="32d21-112">Izberite **Vzpostavi povezavo z Common Data Service** in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="32d21-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="32d21-113">Vnesite **ime** za vir podatkov in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="32d21-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="32d21-114">Navedite **Naslov strežnika** za svojo organizacijo Common Data Service in izberite **Vpis**.</span><span class="sxs-lookup"><span data-stu-id="32d21-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32d21-115">![Pogovorno okno za vnos naslova strežnika za Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="32d21-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="32d21-116">Na seznamu razpoložljivih možnosti izberite entitete, ki jih želite vključiti.</span><span class="sxs-lookup"><span data-stu-id="32d21-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="32d21-117">Če so nekatere entitete že izbrane, jih lahko uporabljajo druge aplikacije Dynamics 365 (kot so Dynamics 365 Sales Insights ali Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="32d21-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="32d21-118">Tega izbora ni mogoče spremeniti.</span><span class="sxs-lookup"><span data-stu-id="32d21-118">You can't change the selection.</span></span> <span data-ttu-id="32d21-119">Te entitete bodo na voljo, ko bo ustvarjen vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="32d21-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32d21-120">![Pogovorno okno s seznamom entitet v organizaciji Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="32d21-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="32d21-121">Shranite izbor, da začnete sinhronizirati izbrane entitete v upravljano jezero Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="32d21-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="32d21-122">Novo dodano povezavo najdete na strani **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="32d21-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="32d21-123">Dana bo v čakalno vrsto za osvežitev in število entitet bo prikazano kot 0, dokler niso vse entitete sinhronizirane.</span><span class="sxs-lookup"><span data-stu-id="32d21-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="32d21-124">Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="32d21-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="32d21-125">Urejanje vira podatkov upravljanega jezera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="32d21-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="32d21-126">Izbor entitet uredite šele po ustvarjanju vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="32d21-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="32d21-127">Če bi bili na primer dodane dodatne entitete v Common Data Service in želite uvoziti tudi njih.</span><span class="sxs-lookup"><span data-stu-id="32d21-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="32d21-128">Če se želite povezati v drugo Common Data Service, [ustvarite nov vir podatkov](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="32d21-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="32d21-129">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="32d21-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="32d21-130">Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.</span><span class="sxs-lookup"><span data-stu-id="32d21-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="32d21-131">Na seznamu izberite možnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="32d21-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="32d21-132">Izberite dodatne entitete z razpoložljivega seznama entitet in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="32d21-132">Select additional entities from the available list of entities and select **Save**.</span></span>
