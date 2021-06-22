---
title: Izvozite podatke Customer Insights v Mailchimp
description: Naučite se, kako konfigurirati povezavo in izvažati v Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124247"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="9d267-103">Izvoz segmentov v Mailchimp (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="9d267-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="9d267-104">Izvozite segmente poenotenih profilov strank v Mailchimp, da ustvarite glasila in e-poštne akcije.</span><span class="sxs-lookup"><span data-stu-id="9d267-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9d267-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="9d267-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9d267-106">Imate [račun za Mailchimp](https://mailchimp.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="9d267-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9d267-107">V storitvi Mailchimp so na voljo obstoječa občinstva in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="9d267-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="9d267-108">Če želite več informacij, glejte razdelek [Občinstva Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="9d267-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="9d267-109">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="9d267-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="9d267-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="9d267-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9d267-111">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="9d267-111">Known limitations</span></span>

- <span data-ttu-id="9d267-112">Do 1 milijon profilov na izvoz v Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9d267-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="9d267-113">Izvoz v Mailchimp je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="9d267-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="9d267-114">Izvoz segmentov z 1 milijonom profilov lahko traja do tri ure.</span><span class="sxs-lookup"><span data-stu-id="9d267-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="9d267-115">Število profilov, ki jih lahko izvozite v Mailchimp, je odvisno in omejeno glede na vašo pogodbo s podjetjem Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9d267-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="9d267-116">Nastavitev povezave s storitvijo Mailchimp</span><span class="sxs-lookup"><span data-stu-id="9d267-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="9d267-117">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="9d267-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9d267-118">Izberite **Dodajanje povezave** in izberite **Autopilot** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="9d267-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="9d267-119">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="9d267-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9d267-120">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="9d267-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9d267-121">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="9d267-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9d267-122">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="9d267-122">Choose who can use this connection.</span></span> <span data-ttu-id="9d267-123">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="9d267-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9d267-124">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9d267-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9d267-125">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="9d267-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9d267-126">Izberite **Poveži** za inicializiranje povezave z Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9d267-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="9d267-127">Izberite **Preverjanje pristnosti s storitvijo Mailchimp** in vnesite svoje poverilnice za Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9d267-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="9d267-128">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d267-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9d267-129">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="9d267-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="9d267-130">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="9d267-130">Configure the connector</span></span>

<span data-ttu-id="9d267-131">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="9d267-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9d267-132">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9d267-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9d267-133">Pomaknite se na možnost **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="9d267-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="9d267-134">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="9d267-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9d267-135">V polju **Povezava za izvoz** izberite povezavo v razdelku Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9d267-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="9d267-136">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="9d267-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9d267-137">Vnesite svoj **[ID občinstva storitve Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="9d267-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="9d267-138">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="9d267-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9d267-139">Izbirno lahko izvozite **Ime** in **Priimek**, da ustvarite bolj prilagojena e-poštna sporočila.</span><span class="sxs-lookup"><span data-stu-id="9d267-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="9d267-140">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="9d267-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9d267-141">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="9d267-141">Select the segments you want to export.</span></span> <span data-ttu-id="9d267-142">V Mailchimp lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="9d267-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="9d267-143">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="9d267-143">Select **Save**.</span></span>

<span data-ttu-id="9d267-144">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="9d267-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9d267-145">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9d267-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9d267-146">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9d267-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9d267-147">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="9d267-147">Data privacy and compliance</span></span>

<span data-ttu-id="9d267-148">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Mailchimp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="9d267-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9d267-149">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Mailchimp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="9d267-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9d267-150">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9d267-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9d267-151">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="9d267-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
