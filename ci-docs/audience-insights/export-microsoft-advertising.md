---
title: Izvoz podatkov Customer Insights v Microsoft Advertising
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124552"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="06b46-103">Izvoz segmentov v Microsoft Advertising (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="06b46-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="06b46-104">Izvozite segmente Customer Insights v Microsoft Advertising, da ustvarite ciljne skupine za storitev Customer Match.</span><span class="sxs-lookup"><span data-stu-id="06b46-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="06b46-105">Uporabite te ciljne skupine za svoje oglaševalske akcije.</span><span class="sxs-lookup"><span data-stu-id="06b46-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="06b46-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="06b46-106">Prerequisites</span></span>

-   <span data-ttu-id="06b46-107">Imate [račun za Microsoft Advertising](https://ads.microsoft.com/) in pripadajoče skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="06b46-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="06b46-108">Sprejeli ste pogoje uporabe storitve Customer Match.</span><span class="sxs-lookup"><span data-stu-id="06b46-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="06b46-109">[Konfigurirani segmenti](segments.md) v vpogledih za občinstvo.</span><span class="sxs-lookup"><span data-stu-id="06b46-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="06b46-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje z e-poštnim naslovom.</span><span class="sxs-lookup"><span data-stu-id="06b46-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="06b46-111">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="06b46-111">Known limitations</span></span>

- <span data-ttu-id="06b46-112">V Microsoft Advertising lahko izvozite do 500.000 profilov na izvoz.</span><span class="sxs-lookup"><span data-stu-id="06b46-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="06b46-113">Izvoz v Microsoft Advertising je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="06b46-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="06b46-114">Izvoz do 500.000 profilov v Microsoft Advertising lahko traja do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="06b46-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="06b46-115">Nastavitev povezave s storitvijo Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="06b46-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="06b46-116">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="06b46-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="06b46-117">Izberite **Dodajanje povezave** in izberite **Microsoft Advertising** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="06b46-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="06b46-118">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="06b46-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="06b46-119">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="06b46-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="06b46-120">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="06b46-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="06b46-121">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="06b46-121">Choose who can use this connection.</span></span> <span data-ttu-id="06b46-122">Privzeto so nastavljeni skrbniki.</span><span class="sxs-lookup"><span data-stu-id="06b46-122">The default is administrators.</span></span> <span data-ttu-id="06b46-123">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="06b46-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="06b46-124">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="06b46-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="06b46-125">Izberite **Poveži** za inicializiranje povezave s storitvijo Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="06b46-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="06b46-126">Izberite **Preverjanje pristnosti s storitvijo Microsoft Advertising** in vnesite skrbniške poverilnice za Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="06b46-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="06b46-127">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="06b46-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="06b46-128">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="06b46-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="06b46-129">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="06b46-129">Configure an export</span></span>

<span data-ttu-id="06b46-130">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="06b46-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="06b46-131">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="06b46-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="06b46-132">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="06b46-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="06b46-133">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="06b46-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="06b46-134">V polju **Povezava za izvoz** izberite povezavo v razdelku Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="06b46-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="06b46-135">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="06b46-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="06b46-136">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="06b46-136">Select the segments to export.</span></span> <span data-ttu-id="06b46-137">Ciljne skupine storitve Customer Match v programu Microsoft Advertising se samodejno ustvarijo z imeni segmentov, ki so izbrani za izvoz.</span><span class="sxs-lookup"><span data-stu-id="06b46-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="06b46-138">Vsak segment bo prikazal ločeno ciljno skupino za storitev Customer Match.</span><span class="sxs-lookup"><span data-stu-id="06b46-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="06b46-139">Vpišite **ID stranke Microsoft Advertising in ID računa**.</span><span class="sxs-lookup"><span data-stu-id="06b46-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="06b46-140">ID stranke (`cid`) in ID računa (`aid`) lahko najdete v parametrih URL-ja, ko ste prijavljeni v Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="06b46-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="06b46-141">V razdelku **Ujemanje podatkov** v polju **E-pošta** izberite polje v svojem poenotenem profilu stranke, ki ima e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="06b46-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="06b46-142">To je obvezno za izvoz segmentov Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="06b46-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="06b46-143">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="06b46-143">Select **Save**.</span></span>

<span data-ttu-id="06b46-144">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="06b46-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="06b46-145">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="06b46-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="06b46-146">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="06b46-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="06b46-147">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="06b46-147">Data privacy and compliance</span></span>

<span data-ttu-id="06b46-148">Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Microsoft Advertising, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="06b46-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="06b46-149">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Microsoft Advertising izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate.</span><span class="sxs-lookup"><span data-stu-id="06b46-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="06b46-150">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="06b46-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="06b46-151">Vaš skrbnik Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza, da prenehate uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="06b46-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
