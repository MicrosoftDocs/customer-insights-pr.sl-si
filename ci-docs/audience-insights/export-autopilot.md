---
title: Izvoz podatkov iz Customer Insights v storitev Autopilot
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760163"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="4ef91-103">Izvoz segmentov v Autopilot (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="4ef91-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="4ef91-104">Izvozite segmente poenotenih profilov strank v storitev Autopilot in jih uporabite za e-poštno trženje v storitvi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ef91-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4ef91-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="4ef91-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4ef91-106">Imate [račun za storitev Autopilot](https://www.autopilothq.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="4ef91-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4ef91-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="4ef91-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4ef91-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="4ef91-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4ef91-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="4ef91-109">Known limitations</span></span>

- <span data-ttu-id="4ef91-110">V storitev Autopilot lahko izvozite do sto tisoč profilov.</span><span class="sxs-lookup"><span data-stu-id="4ef91-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="4ef91-111">Izvoz v storitev Autopilot je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="4ef91-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="4ef91-112">Izvoz do sto tisoč profilov v storitev Autopilot lahko traja do nekaj ur.</span><span class="sxs-lookup"><span data-stu-id="4ef91-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="4ef91-113">Število profilov, ki jih lahko izvozite v storitev Autopilot, je odvisno in omejeno glede na vašo pogodbo za Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ef91-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="4ef91-114">Nastavitev povezave s storitvijo Autopilot</span><span class="sxs-lookup"><span data-stu-id="4ef91-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="4ef91-115">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4ef91-116">Izberite **Dodajanje povezave** in izberite **Autopilot** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="4ef91-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="4ef91-117">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4ef91-118">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="4ef91-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4ef91-119">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="4ef91-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4ef91-120">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="4ef91-120">Choose who can use this connection.</span></span> <span data-ttu-id="4ef91-121">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="4ef91-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4ef91-122">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4ef91-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="4ef91-123">Vpišite [ključ API-ja za storitev Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="4ef91-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="4ef91-124">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4ef91-125">Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ef91-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="4ef91-126">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4ef91-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4ef91-127">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="4ef91-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4ef91-128">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="4ef91-128">Configure an export</span></span>

<span data-ttu-id="4ef91-129">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="4ef91-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4ef91-130">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4ef91-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4ef91-131">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4ef91-132">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4ef91-133">V polju **Povezava za izvoz** izberite povezavo v razdelku Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ef91-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="4ef91-134">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="4ef91-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="4ef91-135">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="4ef91-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4ef91-136">Ponovite iste korake za druga neobvezna polja, kot so **ime**, **priimek**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="4ef91-137">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="4ef91-137">Select the segments you want to export.</span></span> <span data-ttu-id="4ef91-138">Močno **priporočamo, da v storitev Autopilot skupno ne izvozite več kot sto tisoč profilov strank**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="4ef91-139">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="4ef91-139">Select **Save**.</span></span>

<span data-ttu-id="4ef91-140">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="4ef91-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4ef91-141">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4ef91-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4ef91-142">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4ef91-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4ef91-143">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="4ef91-143">Data privacy and compliance</span></span>

<span data-ttu-id="4ef91-144">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev Autopilot, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="4ef91-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4ef91-145">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Autopilot izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="4ef91-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4ef91-146">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4ef91-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4ef91-147">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="4ef91-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
