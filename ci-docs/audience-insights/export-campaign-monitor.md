---
title: Izvoz podatkov Customer Insights v Campaign Monitor
description: Naučite se, kako konfigurirati povezavo in izvažati v Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124201"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="71e36-103">Izvoz segmentov v Campaign Monitor (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="71e36-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="71e36-104">Izvozite segmente poenotenih profilov strank v Campaign Monitor in jih uporabite za tržne dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="71e36-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71e36-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="71e36-105">Prerequisites</span></span>

-   <span data-ttu-id="71e36-106">Imate [račun za Campaign Monitor](https://www.campaignmonitor.com/) in pripadajoče skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="71e36-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="71e36-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="71e36-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="71e36-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="71e36-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="71e36-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="71e36-109">Known limitations</span></span>

- <span data-ttu-id="71e36-110">V Campaign Monitor lahko izvozite do 1 milijon profilov na izvoz.</span><span class="sxs-lookup"><span data-stu-id="71e36-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="71e36-111">Izvoz v Campaign Monitor je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="71e36-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="71e36-112">Izvoz do 1 milijona profilov v Campaign Monitor lahko traja do 20 minut.</span><span class="sxs-lookup"><span data-stu-id="71e36-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="71e36-113">Število profilov, ki jih lahko izvozite v Campaign Monitor, je odvisno in omejeno od vaše pogodbe za Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="71e36-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="71e36-114">Nastavitev povezave s storitvijo Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="71e36-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="71e36-115">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="71e36-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="71e36-116">Izberite **Dodajanje povezave** in izberite **Campaign Monitor** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="71e36-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="71e36-117">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="71e36-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="71e36-118">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="71e36-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="71e36-119">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="71e36-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="71e36-120">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="71e36-120">Choose who can use this connection.</span></span> <span data-ttu-id="71e36-121">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="71e36-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="71e36-122">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="71e36-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="71e36-123">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="71e36-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="71e36-124">Izberite **Poveži** za inicializiranje povezave s storitvijo Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="71e36-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="71e36-125">Izberite **Preverjanje pristnosti s storitvijo Campaign Monitor** in vnesite skrbniške poverilnice za Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="71e36-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="71e36-126">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71e36-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="71e36-127">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="71e36-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="71e36-128">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="71e36-128">Configure an export</span></span>

<span data-ttu-id="71e36-129">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="71e36-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="71e36-130">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="71e36-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="71e36-131">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="71e36-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="71e36-132">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="71e36-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="71e36-133">V polju **Povezava za izvoz** izberite povezavo v razdelku Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="71e36-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="71e36-134">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="71e36-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="71e36-135">Vnesite [**ID seznama storitve Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="71e36-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="71e36-136">Najprej [ustvarite ključ API](https://www.campaignmonitor.com/api/getting-started/) iz možnosti **Nastavitve računa** v storitvi Campaign Monitor, da prikažete ID seznama API-jev.</span><span class="sxs-lookup"><span data-stu-id="71e36-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="71e36-137">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="71e36-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="71e36-138">To je obvezno za izvoz segmentov Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="71e36-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="71e36-139">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="71e36-139">Select **Save**.</span></span>

<span data-ttu-id="71e36-140">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="71e36-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="71e36-141">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="71e36-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="71e36-142">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="71e36-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="71e36-143">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="71e36-143">Data privacy and compliance</span></span>

<span data-ttu-id="71e36-144">Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Campaign Monitor, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="71e36-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="71e36-145">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Campaign Monitor izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate.</span><span class="sxs-lookup"><span data-stu-id="71e36-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="71e36-146">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="71e36-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="71e36-147">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="71e36-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
