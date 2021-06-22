---
title: Izvoz podatkov Customer Insights v Omnisend
description: Naučite se, kako konfigurirati povezavo in izvažati v Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124553"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="12d50-103">Izvoz segmentov v Omnisend (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="12d50-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="12d50-104">Izvozite segmente poenotenih profilov strank v Omnisend in jih uporabite za tržne dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="12d50-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12d50-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="12d50-105">Prerequisites</span></span>

-   <span data-ttu-id="12d50-106">Imate [račun za Omnisend](https://www.omnisend.com/) in pripadajoče skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="12d50-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="12d50-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="12d50-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="12d50-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="12d50-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="12d50-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="12d50-109">Known limitations</span></span>

- <span data-ttu-id="12d50-110">V Omnisend lahko izvozite do 1 milijon profilov, kar lahko traja do 4 ure.</span><span class="sxs-lookup"><span data-stu-id="12d50-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="12d50-111">Izvoz v Omnisend je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="12d50-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="12d50-112">Število profilov, ki jih lahko izvozite v Omnisend, je odvisno od vaše pogodbe z Omnisendom.</span><span class="sxs-lookup"><span data-stu-id="12d50-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="12d50-113">Nastavitev povezave s storitvijo Omnisend</span><span class="sxs-lookup"><span data-stu-id="12d50-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="12d50-114">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="12d50-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="12d50-115">Izberite možnost **Dodajanje povezave** in izberite **Omnisend** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="12d50-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="12d50-116">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="12d50-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="12d50-117">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="12d50-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="12d50-118">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="12d50-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="12d50-119">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="12d50-119">Choose who can use this connection.</span></span> <span data-ttu-id="12d50-120">Privzeto je storitev namenjena samo skrbnikom.</span><span class="sxs-lookup"><span data-stu-id="12d50-120">By default it's only administrators.</span></span> <span data-ttu-id="12d50-121">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="12d50-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="12d50-122">Vpišite [ključ API-ja za storitev Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="12d50-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="12d50-123">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="12d50-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="12d50-124">Izberite **Poveži** za inicializiranje povezave s storitvijo Omnisend.</span><span class="sxs-lookup"><span data-stu-id="12d50-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="12d50-125">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="12d50-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="12d50-126">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="12d50-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="12d50-127">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="12d50-127">Configure an export</span></span>

<span data-ttu-id="12d50-128">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="12d50-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="12d50-129">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="12d50-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="12d50-130">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="12d50-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="12d50-131">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="12d50-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="12d50-132">V polju **Povezava za izvoz** izberite povezavo v razdelku Omnisend.</span><span class="sxs-lookup"><span data-stu-id="12d50-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="12d50-133">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="12d50-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="12d50-134">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="12d50-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="12d50-135">To je obvezno za izvoz segmentov Omnisend.</span><span class="sxs-lookup"><span data-stu-id="12d50-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="12d50-136">Izbirno lahko izvozite Ime, Priimek, Naslov, Država/regija, Zvezna država, Mesto in Poštna številka, da ustvarite bolj prilagojena e-poštna sporočila.</span><span class="sxs-lookup"><span data-stu-id="12d50-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="12d50-137">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="12d50-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="12d50-138">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="12d50-138">Select **Save**.</span></span>

<span data-ttu-id="12d50-139">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="12d50-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="12d50-140">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="12d50-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="12d50-141">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="12d50-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12d50-142">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="12d50-142">Data privacy and compliance</span></span>

<span data-ttu-id="12d50-143">Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Omnisend, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="12d50-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12d50-144">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Omnisend izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate.</span><span class="sxs-lookup"><span data-stu-id="12d50-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="12d50-145">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="12d50-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="12d50-146">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="12d50-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
