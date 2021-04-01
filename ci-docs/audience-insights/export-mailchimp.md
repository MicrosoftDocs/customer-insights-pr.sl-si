---
title: Izvozite podatke Customer Insights v Mailchimp
description: Preberite o konfiguraciji povezave s storitvijo Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598221"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="7ed55-103">Povezovalnik za Mailchimp (predogled)</span><span class="sxs-lookup"><span data-stu-id="7ed55-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="7ed55-104">Izvozite segmente poenotenih profilov strank v Mailchimp, da ustvarite glasila in e-poštne akcije.</span><span class="sxs-lookup"><span data-stu-id="7ed55-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ed55-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="7ed55-105">Prerequisites</span></span>

-   <span data-ttu-id="7ed55-106">Imate [račun za Mailchimp](https://mailchimp.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="7ed55-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7ed55-107">V storitvi Mailchimp so na voljo obstoječa občinstva in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="7ed55-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="7ed55-108">Če želite več informacij, glejte razdelek [Občinstva Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7ed55-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="7ed55-109">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7ed55-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7ed55-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="7ed55-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="7ed55-111">Vzpostavitev povezave s storitvijo Mailchimp</span><span class="sxs-lookup"><span data-stu-id="7ed55-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="7ed55-112">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7ed55-113">Pod razdelkom **Mailchimp** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="7ed55-114">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7ed55-115">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7ed55-116">Vnesite **[ID občinstva za Mailchimp](https://mailchimp.com/help/find-audience-id/)** in izberite **Poveži**, da inicializirate povezavo s storitvijo Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7ed55-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="7ed55-117">Izberite **Preverjanje pristnosti s storitvijo Mailchimp** in vnesite svoje poverilnice za Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7ed55-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="7ed55-118">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7ed55-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Posnetek zaslona izvoza za povezavo Mailchimp":::

1. <span data-ttu-id="7ed55-120">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="7ed55-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7ed55-121">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="7ed55-121">Configure the connector</span></span>

1. <span data-ttu-id="7ed55-122">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="7ed55-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7ed55-123">Po želji lahko izvozite **ime** in **priimek** kot dodatna polja za ustvarjanje bolj prilagojenih e-poštnih sporočil.</span><span class="sxs-lookup"><span data-stu-id="7ed55-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="7ed55-124">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="7ed55-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7ed55-125">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="7ed55-125">Select the segments you want to export.</span></span> <span data-ttu-id="7ed55-126">V Mailchimp lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="7ed55-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Izberite polja in segmente, ki jih želite izvoziti v Mailchimp":::

1. <span data-ttu-id="7ed55-128">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7ed55-129">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="7ed55-129">Export the data</span></span>

<span data-ttu-id="7ed55-130">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7ed55-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7ed55-131">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7ed55-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7ed55-132">V storitvi Mailchimp lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7ed55-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7ed55-133">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="7ed55-133">Known limitations</span></span>

- <span data-ttu-id="7ed55-134">Do 1 milijon profilov na izvoz v Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7ed55-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="7ed55-135">Izvoz v Mailchimp je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="7ed55-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="7ed55-136">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do tri ure zaradi omejitev na strani ponudnika.</span><span class="sxs-lookup"><span data-stu-id="7ed55-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="7ed55-137">Število profilov, ki jih lahko izvozite v Mailchimp, je odvisno in omejeno glede na vašo pogodbo s podjetjem Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7ed55-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7ed55-138">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="7ed55-138">Data privacy and compliance</span></span>

<span data-ttu-id="7ed55-139">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Mailchimp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="7ed55-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7ed55-140">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Mailchimp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="7ed55-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7ed55-141">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7ed55-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7ed55-142">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="7ed55-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]