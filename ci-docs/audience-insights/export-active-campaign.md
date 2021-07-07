---
title: Podatke iz storitve Customer Insights izvozite v ActiveCampaign
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314677"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="fcf0f-103">Izvoz segmentov v ActiveCampaign (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="fcf0f-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="fcf0f-104">Segmente poenotenih profilov strank izvozite v ActiveCampaign in jih uporabite za trženjske dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fcf0f-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="fcf0f-105">Prerequisites</span></span>

-   <span data-ttu-id="fcf0f-106">Imate [račun ActiveCampaign](https://www.activecampaign.com/) in ustrezne poverilnice skrbnika.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fcf0f-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fcf0f-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje z e-poštnim naslovom.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fcf0f-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="fcf0f-109">Known limitations</span></span>

- <span data-ttu-id="fcf0f-110">Naenkrat je mogoče v ActiveCampaign izvoziti največ milijon profilov, kar lahko traja do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="fcf0f-111">Pri izvažanju v ActiveCampaign ste omejeni na segmente.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="fcf0f-112">Število profilov, ki jih lahko izvozite v ActiveCampaign, je odvisno od vaše pogodbe z ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="fcf0f-113">Vzpostavite povezavo s storitvijo ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="fcf0f-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="fcf0f-114">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fcf0f-115">Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **ActiveCampaign**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="fcf0f-116">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fcf0f-117">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fcf0f-118">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fcf0f-119">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-119">Choose who can use this connection.</span></span> <span data-ttu-id="fcf0f-120">Privzeto jo lahko uporabljajo samo skrbniki.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-120">By default, it's only administrators.</span></span> <span data-ttu-id="fcf0f-121">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fcf0f-122">Vpišite [ključ API za ActiveCampaign in ime gostitelja končne točke REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="fcf0f-123">Ime gostitelja za končno točko REST je samo ime gostitelja, brez https://.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="fcf0f-124">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fcf0f-125">Za inicializiranje povezave z ActiveCampaign izberite možnost **Poveži**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="fcf0f-126">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fcf0f-127">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fcf0f-128">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="fcf0f-128">Configure an export</span></span>

<span data-ttu-id="fcf0f-129">Izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="fcf0f-130">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fcf0f-131">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fcf0f-132">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fcf0f-133">V polju **Povezava za izvoz**, in sicer v razdelku ActiveCampaign, izberite povezavo.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="fcf0f-134">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fcf0f-135">Vnesite svoj [**ID seznama za ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="fcf0f-136">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fcf0f-137">Segmente morate izvoziti v ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="fcf0f-138">Za bolj prilagojena e-poštna sporočila vam je na voljo možnost izvoza imena, priimka in vsebine telefona.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="fcf0f-139">Izberite Dodaj atribut za preslikavo teh polj.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="fcf0f-140">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-140">Select **Save**.</span></span>

<span data-ttu-id="fcf0f-141">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fcf0f-142">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fcf0f-143">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fcf0f-144">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="fcf0f-144">Data privacy and compliance</span></span>

<span data-ttu-id="fcf0f-145">S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi ActiveCampaign, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fcf0f-146">Microsoft bo tovrstne podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da ActiveCampaign izpolni morebitne obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fcf0f-147">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fcf0f-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="fcf0f-148">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="fcf0f-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
