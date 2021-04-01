---
title: Izvoz podatkov iz Customer Insights v storitev Autopilot
description: Preberite o konfiguraciji povezave s storitvijo Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596151"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="93479-103">Povezovalnik za Autopilot (predogled)</span><span class="sxs-lookup"><span data-stu-id="93479-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="93479-104">Izvozite segmente poenotenih profilov strank v storitev Autopilot in jih uporabite za e-poštno trženje v storitvi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="93479-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="93479-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="93479-105">Prerequisites</span></span>

-   <span data-ttu-id="93479-106">Imate [račun za storitev Autopilot](https://www.autopilothq.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="93479-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="93479-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="93479-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="93479-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="93479-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="93479-109">Vzpostavljanje povezave s storitvijo Autopilot</span><span class="sxs-lookup"><span data-stu-id="93479-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="93479-110">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="93479-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="93479-111">Pod razdelkom **Autopilot** izberite možnost **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="93479-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="93479-112">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="93479-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfiguracijsko podokno za povezavo s storitvijo Autopilot.":::

1. <span data-ttu-id="93479-114">Vnesite **ključ za API storitve Autopilot** [Ključ za API storitve Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="93479-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="93479-115">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="93479-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="93479-116">Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Autopilot.</span><span class="sxs-lookup"><span data-stu-id="93479-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="93479-117">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93479-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="93479-118">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="93479-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="93479-119">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="93479-119">Configure the connector</span></span>

1. <span data-ttu-id="93479-120">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="93479-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="93479-121">Ponovite iste korake za druga neobvezna polja, kot so **ime**, **priimek**.</span><span class="sxs-lookup"><span data-stu-id="93479-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="93479-122">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="93479-122">Select the segments you want to export.</span></span> <span data-ttu-id="93479-123">Močno **priporočamo, da v storitev Autopilot skupno ne izvozite več kot sto tisoč profilov strank**.</span><span class="sxs-lookup"><span data-stu-id="93479-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="93479-124">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="93479-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="93479-125">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="93479-125">Export the data</span></span>

<span data-ttu-id="93479-126">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="93479-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="93479-127">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="93479-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="93479-128">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="93479-128">Known limitations</span></span>

- <span data-ttu-id="93479-129">V storitev Autopilot lahko izvozite do sto tisoč profilov.</span><span class="sxs-lookup"><span data-stu-id="93479-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="93479-130">Izvoz v storitev Autopilot je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="93479-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="93479-131">Izvoz do sto tisoč profilov v storitev Autopilot lahko traja do nekaj ur.</span><span class="sxs-lookup"><span data-stu-id="93479-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="93479-132">Število profilov, ki jih lahko izvozite v storitev Autopilot, je odvisno in omejeno glede na vašo pogodbo za Autopilot.</span><span class="sxs-lookup"><span data-stu-id="93479-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="93479-133">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="93479-133">Data privacy and compliance</span></span>

<span data-ttu-id="93479-134">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev Autopilot, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="93479-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="93479-135">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Autopilot izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="93479-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="93479-136">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="93479-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="93479-137">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="93479-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]