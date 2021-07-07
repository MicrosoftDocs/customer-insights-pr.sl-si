---
title: Podatke iz storitve Customer Insights izvozite v Sendinblue
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314676"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="3eb4b-103">Izvoz segmentov v Sendinblue (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="3eb4b-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="3eb4b-104">Za ustvarjanje akcij, zagotovitev e-poštnega trženja in uporabo določenih skupin strank s storitvijo Sendinblue izvozite segmente poenotenih profilov strank.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="3eb4b-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="3eb4b-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="3eb4b-106">Imate [račun Sendinblue](https://www.sendinblue.com/) in ustrezne poverilnice skrbnika.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3eb4b-107">Obstoječi seznami so v storitvi Sendinblue in ustreznih ID-jih.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="3eb4b-108">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3eb4b-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="3eb4b-109">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3eb4b-110">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="3eb4b-110">Known limitations</span></span>

- <span data-ttu-id="3eb4b-111">Največ milijon profilov na vsak izvoz v Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="3eb4b-112">Pri izvažanju v Sendinblue ste omejeni na segmente.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="3eb4b-113">Izvoz segmentov z milijonom profilov lahko traja do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="3eb4b-114">Število profilov, ki jih lahko izvozite v Sendinblue, je omejeno s pogodbo, ki ste jo sklenili s podjetjem Sendinblue, od katere je število profilov odvisno.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="3eb4b-115">Vzpostavite povezavo s storitvijo Sendinblue</span><span class="sxs-lookup"><span data-stu-id="3eb4b-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="3eb4b-116">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3eb4b-117">Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **Sendinblue**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="3eb4b-118">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3eb4b-119">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3eb4b-120">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3eb4b-121">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-121">Choose who can use this connection.</span></span> <span data-ttu-id="3eb4b-122">Privzeto je storitev namenjena samo skrbnikom.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-122">By default it's only administrators.</span></span> <span data-ttu-id="3eb4b-123">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3eb4b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3eb4b-124">Vnesite svoj **[ključ vmesnika API storitve Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="3eb4b-125">Izberite možnost **Strinjam se**, s čimer potrdite, da se strinjate z možnostjo **Zasebnost in skladnost podatkov**, ter izberite možnost **Poveži** in tako inicializirajte povezavo s storitvijo Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="3eb4b-126">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3eb4b-127">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3eb4b-128">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="3eb4b-128">Configure an export</span></span>

<span data-ttu-id="3eb4b-129">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3eb4b-130">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3eb4b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3eb4b-131">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3eb4b-132">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3eb4b-133">V polju **Povezava za izvoz**, in sicer v razdelku Sendinblue, izberite povezavo.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="3eb4b-134">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3eb4b-135">Vnesite svoj ID seznam za **Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="3eb4b-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="3eb4b-136">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="3eb4b-137">Za bolj prilagojena e-poštna sporočila vam je na voljo možnost izvoza **imena**, **priimka** in **vsebine telefona**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="3eb4b-138">Izberite **Dodaj atribut** za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="3eb4b-139">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="3eb4b-140">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-140">Select **Save**.</span></span>

<span data-ttu-id="3eb4b-141">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3eb4b-142">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3eb4b-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3eb4b-143">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3eb4b-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3eb4b-144">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="3eb4b-144">Data privacy and compliance</span></span>

<span data-ttu-id="3eb4b-145">S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi Sendinblue, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3eb4b-146">Microsoft bo tovrstne podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da Sendinblue izpolni morebitne obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3eb4b-147">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3eb4b-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3eb4b-148">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="3eb4b-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
