---
title: Izvozite podatke Customer Insights v DotDigital
description: Preberite o konfiguraciji povezave s storitvijo DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269120"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="1e23c-103">Povezovalnik za DotDigital (predogled)</span><span class="sxs-lookup"><span data-stu-id="1e23c-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="1e23c-104">Izvozite segmente poenotenih profilov strank v adresarje DotDigital ter jih uporabite za akcije, e-poštno trženje ter sestavljanje segmentov strank s storitvijo DotDigital.</span><span class="sxs-lookup"><span data-stu-id="1e23c-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1e23c-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="1e23c-105">Prerequisites</span></span>

-   <span data-ttu-id="1e23c-106">Imate [račun za DotDigital](https://dotdigital.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="1e23c-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e23c-107">V storitvi DotDigital so na voljo obstoječi adresarji in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="1e23c-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="1e23c-108">ID lahko najdete v URL-ju, ko izberete in odprete adresar.</span><span class="sxs-lookup"><span data-stu-id="1e23c-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="1e23c-109">Za več informacij glejte [Adresarji DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="1e23c-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="1e23c-110">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="1e23c-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1e23c-111">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="1e23c-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="1e23c-112">Povezovanje s storitvijo DotDigital</span><span class="sxs-lookup"><span data-stu-id="1e23c-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="1e23c-113">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1e23c-114">Pod razdelkom **DotDigital** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="1e23c-115">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Podokno konfiguracije za izvoz DotDigital.":::

1. <span data-ttu-id="1e23c-117">Vnesite **uporabniško ime in geslo za DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="1e23c-118">Vpišite svoj **[ID za adresar DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="1e23c-119">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1e23c-120">Izberite **Poveži**, da inicializirate povezavo s storitvijo DotDigital.</span><span class="sxs-lookup"><span data-stu-id="1e23c-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="1e23c-121">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e23c-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1e23c-122">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="1e23c-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1e23c-123">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="1e23c-123">Configure the connector</span></span>

1. <span data-ttu-id="1e23c-124">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="1e23c-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1e23c-125">Ponovite iste korake za druga neobvezna polja, kot so **Ime**, **Priimek**, **Polno ime**, **Spol** in **Poštna številka**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="1e23c-126">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="1e23c-126">Select the segments you want to export.</span></span> <span data-ttu-id="1e23c-127">V DotDigital lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="1e23c-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="1e23c-128">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="1e23c-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1e23c-129">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="1e23c-129">Export the data</span></span>

<span data-ttu-id="1e23c-130">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1e23c-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1e23c-131">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e23c-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e23c-132">V storitvi DotDigital lahko zdaj najdete svoje segmente v [adresarjih DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="1e23c-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e23c-133">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="1e23c-133">Known limitations</span></span>

- <span data-ttu-id="1e23c-134">Do 1 milijon profilov na izvoz v DotDigital.</span><span class="sxs-lookup"><span data-stu-id="1e23c-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="1e23c-135">Izvoz v DotDigital je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="1e23c-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="1e23c-136">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure zaradi omejitev na strani ponudnika.</span><span class="sxs-lookup"><span data-stu-id="1e23c-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="1e23c-137">Število profilov, ki jih lahko izvozite v DotDigital, je odvisno in omejeno glede na vašo pogodbo s podjetjem DotDigital.</span><span class="sxs-lookup"><span data-stu-id="1e23c-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e23c-138">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="1e23c-138">Data privacy and compliance</span></span>

<span data-ttu-id="1e23c-139">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v DotDigital, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="1e23c-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e23c-140">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da DotDigital izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="1e23c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e23c-141">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1e23c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1e23c-142">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="1e23c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]