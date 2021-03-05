---
title: Izvozite podatke Customer Insights v Marketo
description: Preberite o konfiguraciji povezave s storitvijo Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267101"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="a1c87-103">Povezovalnik za Marketo (predogled)</span><span class="sxs-lookup"><span data-stu-id="a1c87-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="a1c87-104">Izvozite segmente poenotenih profilov strank, da akcije, zagotovite e-poštno trženje in uporabite določene skupine strank s storitvijo Marketo.</span><span class="sxs-lookup"><span data-stu-id="a1c87-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1c87-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="a1c87-105">Prerequisites</span></span>

-   <span data-ttu-id="a1c87-106">Imate [račun za Marketo](https://login.marketo.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="a1c87-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a1c87-107">V storitvi Marketo so na voljo obstoječi seznami in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="a1c87-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="a1c87-108">Več informacij je na voljo na [seznamih Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a1c87-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="a1c87-109">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a1c87-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a1c87-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="a1c87-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="a1c87-111">Povezava s storitvijo Marketo</span><span class="sxs-lookup"><span data-stu-id="a1c87-111">Connect to Marketo</span></span>

1. <span data-ttu-id="a1c87-112">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="a1c87-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a1c87-113">Pod razdelkom **Marketo** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="a1c87-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="a1c87-114">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="a1c87-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a1c87-115">Vnesite svoj **[ID odjemalca Marketo, skrivnost odjemalca in ime gostitelja končne točke REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="a1c87-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="a1c87-116">Vnesite svoj **[ID seznama Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="a1c87-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="a1c87-117">Izberite **Strinjam se** za potrditev možnosti **Zasebnost podatkov in skladnost** in izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Marketo.</span><span class="sxs-lookup"><span data-stu-id="a1c87-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="a1c87-118">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1c87-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Posnetek zaslona izvoza za povezavo Marketo":::

1. <span data-ttu-id="a1c87-120">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="a1c87-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a1c87-121">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="a1c87-121">Configure the connector</span></span>

1. <span data-ttu-id="a1c87-122">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="a1c87-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a1c87-123">Po želji lahko izvozite **ime**, **priimek**, **mesto**, **zvezna država** in **država/regija** kot dodatna polja za ustvarjanje bolj prilagojenih e-poštnih sporočil.</span><span class="sxs-lookup"><span data-stu-id="a1c87-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="a1c87-124">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="a1c87-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a1c87-125">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="a1c87-125">Select the segments you want to export.</span></span> <span data-ttu-id="a1c87-126">V Marketo lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="a1c87-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Izberite polja in segmente, ki jih želite izvoziti v Marketo":::

1. <span data-ttu-id="a1c87-128">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="a1c87-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a1c87-129">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="a1c87-129">Export the data</span></span>

<span data-ttu-id="a1c87-130">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a1c87-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a1c87-131">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1c87-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1c87-132">V storitvi Marketo lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a1c87-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a1c87-133">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="a1c87-133">Known limitations</span></span>

- <span data-ttu-id="a1c87-134">Do 1 milijon profilov na izvoz v Marketo.</span><span class="sxs-lookup"><span data-stu-id="a1c87-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="a1c87-135">Izvoz v Marketo je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="a1c87-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="a1c87-136">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure.</span><span class="sxs-lookup"><span data-stu-id="a1c87-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="a1c87-137">Število profilov, ki jih lahko izvozite v Marketo, je odvisno in omejeno glede na vašo pogodbo s podjetjem Marketo.</span><span class="sxs-lookup"><span data-stu-id="a1c87-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1c87-138">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="a1c87-138">Data privacy and compliance</span></span>

<span data-ttu-id="a1c87-139">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Marketo, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="a1c87-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1c87-140">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Marketo izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="a1c87-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1c87-141">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1c87-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a1c87-142">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="a1c87-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]