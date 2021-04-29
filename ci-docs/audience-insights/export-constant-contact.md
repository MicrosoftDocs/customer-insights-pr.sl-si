---
title: Izvoz podatkov Customer Insights v Constant Contact
description: Naučite se, kako konfigurirati povezavo in izvažati v Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760636"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="cd45b-103">Izvoz seznamov segmentov v Constant Contact (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="cd45b-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="cd45b-104">Izvozite segmente poenotenih profilov strank v Constant Contact in jih uporabite za tržne dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="cd45b-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="cd45b-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="cd45b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="cd45b-106">Imate [račun za Constant Contact](https://www.constantcontact.com/account-home) in pripadajoče skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="cd45b-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cd45b-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="cd45b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cd45b-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="cd45b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cd45b-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="cd45b-109">Known limitations</span></span>

- <span data-ttu-id="cd45b-110">V Constant Contact lahko izvozite do 1 milijon profilov na izvoz.</span><span class="sxs-lookup"><span data-stu-id="cd45b-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="cd45b-111">Izvoz v Constant Contact je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="cd45b-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="cd45b-112">Izvoz do 1 milijona profilov v Constant Contact lahko traja do 1 uro.</span><span class="sxs-lookup"><span data-stu-id="cd45b-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="cd45b-113">Število profilov, ki jih lahko izvozite v Constant Contact, je odvisno in omejeno od vaše pogodbe za Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="cd45b-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="cd45b-114">Nastavitev povezave s storitvijo Constant Contact</span><span class="sxs-lookup"><span data-stu-id="cd45b-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="cd45b-115">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="cd45b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cd45b-116">Izberite **Dodajanje povezave** in izberite **Constant Contact** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="cd45b-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="cd45b-117">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="cd45b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cd45b-118">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="cd45b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cd45b-119">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="cd45b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cd45b-120">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="cd45b-120">Choose who can use this connection.</span></span> <span data-ttu-id="cd45b-121">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="cd45b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cd45b-122">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cd45b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cd45b-123">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="cd45b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cd45b-124">Izberite **Poveži** za inicializiranje povezave s storitvijo Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="cd45b-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="cd45b-125">Izberite **Preverjanje pristnosti s storitvijo AdRoll** in vnesite skrbniške poverilnice za Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="cd45b-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="cd45b-126">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cd45b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cd45b-127">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="cd45b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cd45b-128">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="cd45b-128">Configure an export</span></span>

<span data-ttu-id="cd45b-129">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="cd45b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cd45b-130">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cd45b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cd45b-131">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="cd45b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cd45b-132">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="cd45b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cd45b-133">V polju **Povezava za izvoz** izberite povezavo v razdelku Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="cd45b-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="cd45b-134">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="cd45b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cd45b-135">Vnesite [**ID seznama storitve Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="cd45b-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="cd45b-136">Odprite seznam v storitvi Constant Contact, da najdete ID seznama v URL-ju.</span><span class="sxs-lookup"><span data-stu-id="cd45b-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="cd45b-137">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="cd45b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cd45b-138">To je obvezno za izvoz segmentov Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="cd45b-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="cd45b-139">Po želji lahko izvozite ime in priimek kot dodatna polja za ustvarjanje bolj prilagojenih e-poštnih sporočil.</span><span class="sxs-lookup"><span data-stu-id="cd45b-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="cd45b-140">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="cd45b-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="cd45b-141">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="cd45b-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="cd45b-142">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="cd45b-142">Select **Save**.</span></span>

<span data-ttu-id="cd45b-143">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="cd45b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cd45b-144">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cd45b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cd45b-145">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cd45b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cd45b-146">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="cd45b-146">Data privacy and compliance</span></span>

<span data-ttu-id="cd45b-147">Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Constant Contact, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="cd45b-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cd45b-148">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Constant Contact izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate.</span><span class="sxs-lookup"><span data-stu-id="cd45b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cd45b-149">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cd45b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="cd45b-150">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="cd45b-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
