---
title: Izvozite podatke Customer Insights v Marketo
description: Naučite se, kako konfigurirati povezavo in izvažati v Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759841"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="d4736-103">Izvoz segmentov v Marketo (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="d4736-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="d4736-104">Izvozite segmente poenotenih profilov strank, da akcije, zagotovite e-poštno trženje in uporabite določene skupine strank s storitvijo Marketo.</span><span class="sxs-lookup"><span data-stu-id="d4736-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d4736-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="d4736-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="d4736-106">Imate [račun za Marketo](https://login.marketo.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="d4736-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d4736-107">V storitvi Marketo so na voljo obstoječi seznami in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="d4736-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="d4736-108">Več informacij je na voljo na [seznamih Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="d4736-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="d4736-109">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d4736-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="d4736-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="d4736-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d4736-111">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="d4736-111">Known limitations</span></span>

- <span data-ttu-id="d4736-112">Do 1 milijon profilov na izvoz v Marketo.</span><span class="sxs-lookup"><span data-stu-id="d4736-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="d4736-113">Izvoz v Marketo je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="d4736-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="d4736-114">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure.</span><span class="sxs-lookup"><span data-stu-id="d4736-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="d4736-115">Število profilov, ki jih lahko izvozite v Marketo, je odvisno in omejeno glede na vašo pogodbo s podjetjem Marketo.</span><span class="sxs-lookup"><span data-stu-id="d4736-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="d4736-116">Nastavitev povezave s storitvijo Marketo</span><span class="sxs-lookup"><span data-stu-id="d4736-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="d4736-117">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="d4736-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d4736-118">Izberite **Dodajanje povezave** in izberite **Marketo** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="d4736-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="d4736-119">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="d4736-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d4736-120">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="d4736-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d4736-121">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="d4736-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d4736-122">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="d4736-122">Choose who can use this connection.</span></span> <span data-ttu-id="d4736-123">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="d4736-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d4736-124">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d4736-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d4736-125">Vnesite svoj **[ID odjemalca Marketo, skrivnost odjemalca in ime gostitelja končne točke REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="d4736-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="d4736-126">Izberite **Strinjam se** za potrditev možnosti **Zasebnost podatkov in skladnost** in izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Marketo.</span><span class="sxs-lookup"><span data-stu-id="d4736-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="d4736-127">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d4736-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d4736-128">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="d4736-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d4736-129">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="d4736-129">Configure an export</span></span>

<span data-ttu-id="d4736-130">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="d4736-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d4736-131">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d4736-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d4736-132">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d4736-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d4736-133">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="d4736-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d4736-134">V polju **Povezava za izvoz** izberite povezavo v razdelku Marketo.</span><span class="sxs-lookup"><span data-stu-id="d4736-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="d4736-135">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="d4736-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d4736-136">Vnesite svoj **[ID seznama Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="d4736-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="d4736-137">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="d4736-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d4736-138">Izbirno lahko izvozite **Ime**, **Priimek**, **Mesto**, **Zvezna država** in **Država/regija**, da ustvarite bolj prilagojena e-poštna sporočila.</span><span class="sxs-lookup"><span data-stu-id="d4736-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="d4736-139">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="d4736-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d4736-140">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="d4736-140">Select the segments you want to export.</span></span> <span data-ttu-id="d4736-141">V Marketo lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="d4736-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="d4736-142">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="d4736-142">Select **Save**.</span></span>

<span data-ttu-id="d4736-143">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="d4736-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d4736-144">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d4736-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d4736-145">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d4736-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d4736-146">V storitvi Marketo lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="d4736-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d4736-147">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="d4736-147">Data privacy and compliance</span></span>

<span data-ttu-id="d4736-148">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Marketo, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="d4736-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d4736-149">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Marketo izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="d4736-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d4736-150">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d4736-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d4736-151">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="d4736-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]