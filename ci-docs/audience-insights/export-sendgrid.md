---
title: Izvoz podatkov iz Customer Insights v storitev SendGrid
description: Preberite o konfiguraciji povezave s storitvijo SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268752"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="13ed7-103">Povezovalnik za SendGrid (predogled)</span><span class="sxs-lookup"><span data-stu-id="13ed7-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="13ed7-104">Izvozite segmente poenotenih profilov strank v seznam strank storitve SendGrid in jih uporabite za akcije ter e-poštno trženje v storitvi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="13ed7-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="13ed7-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="13ed7-105">Prerequisites</span></span>

-   <span data-ttu-id="13ed7-106">Imate [račun za SendGrid](https://sendgrid.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="13ed7-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="13ed7-107">V storitvi SendGrid so na voljo obstoječi seznami stikov in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="13ed7-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="13ed7-108">Za več informacij glejte razdelek [SendGrid - upravljanje stikov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="13ed7-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="13ed7-109">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="13ed7-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="13ed7-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="13ed7-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="13ed7-111">Vzpostavljanje povezave s storitvijo SendGrid</span><span class="sxs-lookup"><span data-stu-id="13ed7-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="13ed7-112">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="13ed7-113">Pod razdelkom **SendGrid** izberite možnost **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="13ed7-114">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Podokno za konfiguracijo izvoza v storitvi SendGrid.":::

1. <span data-ttu-id="13ed7-116">Vpiši **ključ za API storitve SendGrid** [Ključ za API storitve SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="13ed7-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="13ed7-117">Vnesite **[ID seznama SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="13ed7-118">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="13ed7-119">Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo SendGrid.</span><span class="sxs-lookup"><span data-stu-id="13ed7-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="13ed7-120">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="13ed7-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="13ed7-121">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="13ed7-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="13ed7-122">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="13ed7-122">Configure the connector</span></span>

1. <span data-ttu-id="13ed7-123">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="13ed7-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="13ed7-124">Ponovite te korake še za druga neobvezna polja, kot so **ime**, **priimek**, **država/regija**, **zvezna država**, **mesto** in **poštna številka**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="13ed7-125">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="13ed7-125">Select the segments you want to export.</span></span> <span data-ttu-id="13ed7-126">Močno **priporočamo, da v storitev SendGrid skupno ne izvozite več kot sto tisoč profilov strank**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="13ed7-127">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="13ed7-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="13ed7-128">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="13ed7-128">Export the data</span></span>

<span data-ttu-id="13ed7-129">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="13ed7-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="13ed7-130">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="13ed7-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="13ed7-131">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="13ed7-131">Known limitations</span></span>

- <span data-ttu-id="13ed7-132">Do sto tisoč profilov v storitvi SendGrid</span><span class="sxs-lookup"><span data-stu-id="13ed7-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="13ed7-133">Izvoz v storitev SendGrid je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="13ed7-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="13ed7-134">Izvoz do sto tisoč profilov v storitev SendGrid lahko traja do nekaj ur.</span><span class="sxs-lookup"><span data-stu-id="13ed7-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="13ed7-135">Število profilov, ki jih lahko izvozite v storitev SendGrid, je odvisno in omejeno glede na vašo pogodbo s podjetjem SendGrid.</span><span class="sxs-lookup"><span data-stu-id="13ed7-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="13ed7-136">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="13ed7-136">Data privacy and compliance</span></span>

<span data-ttu-id="13ed7-137">Ko storitvi Dynamics 365 Customer Insights omogočite prenos podatkov v storitev SendGrid, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="13ed7-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="13ed7-138">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da SendGrid izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="13ed7-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="13ed7-139">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="13ed7-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="13ed7-140">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="13ed7-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]