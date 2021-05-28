---
title: Izvoz podatkov iz Customer Insights v storitev SendGrid
description: Naučite se, kako konfigurirati povezavo in izvažati v SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976936"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="57dab-103">Izvoz segmentov v SendGrid (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="57dab-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="57dab-104">Izvozite segmente poenotenih profilov strank v seznam strank storitve SendGrid in jih uporabite za akcije ter e-poštno trženje v storitvi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="57dab-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="57dab-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="57dab-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="57dab-106">Imate [račun za SendGrid](https://sendgrid.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="57dab-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="57dab-107">V storitvi SendGrid so na voljo obstoječi seznami stikov in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="57dab-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="57dab-108">Za več informacij glejte razdelek [SendGrid - upravljanje stikov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="57dab-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="57dab-109">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="57dab-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="57dab-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="57dab-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="57dab-111">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="57dab-111">Known limitations</span></span>

- <span data-ttu-id="57dab-112">Do sto tisoč profilov v storitvi SendGrid</span><span class="sxs-lookup"><span data-stu-id="57dab-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="57dab-113">Izvoz v storitev SendGrid je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="57dab-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="57dab-114">Izvoz do sto tisoč profilov v storitev SendGrid lahko traja do nekaj ur.</span><span class="sxs-lookup"><span data-stu-id="57dab-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="57dab-115">Število profilov, ki jih lahko izvozite v storitev SendGrid, je odvisno in omejeno glede na vašo pogodbo s podjetjem SendGrid.</span><span class="sxs-lookup"><span data-stu-id="57dab-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="57dab-116">Nastavitev povezave s storitvijo SendGrid</span><span class="sxs-lookup"><span data-stu-id="57dab-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="57dab-117">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="57dab-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="57dab-118">Izberite **Dodajanje povezave** in izberite **SendGrid** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="57dab-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="57dab-119">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="57dab-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="57dab-120">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="57dab-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="57dab-121">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="57dab-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="57dab-122">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="57dab-122">Choose who can use this connection.</span></span> <span data-ttu-id="57dab-123">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="57dab-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="57dab-124">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="57dab-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="57dab-125">Vpiši **ključ za API storitve SendGrid** [Ključ za API storitve SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="57dab-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="57dab-126">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="57dab-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="57dab-127">Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo SendGrid.</span><span class="sxs-lookup"><span data-stu-id="57dab-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="57dab-128">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="57dab-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="57dab-129">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="57dab-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="57dab-130">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="57dab-130">Configure an export</span></span>

<span data-ttu-id="57dab-131">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="57dab-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="57dab-132">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="57dab-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="57dab-133">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="57dab-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="57dab-134">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="57dab-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="57dab-135">V polju **Povezava za izvoz** izberite povezavo v razdelku SendGrid.</span><span class="sxs-lookup"><span data-stu-id="57dab-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="57dab-136">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="57dab-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="57dab-137">Vnesite **[ID seznama SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="57dab-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="57dab-138">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="57dab-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="57dab-139">Ponovite te korake še za druga neobvezna polja, kot so **ime**, **priimek**, **država/regija**, **zvezna država**, **mesto** in **poštna številka**.</span><span class="sxs-lookup"><span data-stu-id="57dab-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="57dab-140">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="57dab-140">Select the segments you want to export.</span></span> <span data-ttu-id="57dab-141">Močno **priporočamo, da v storitev SendGrid skupno ne izvozite več kot sto tisoč profilov strank**.</span><span class="sxs-lookup"><span data-stu-id="57dab-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="57dab-142">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="57dab-142">Select **Save**.</span></span>

<span data-ttu-id="57dab-143">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="57dab-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="57dab-144">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57dab-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="57dab-145">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="57dab-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="57dab-146">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="57dab-146">Data privacy and compliance</span></span>

<span data-ttu-id="57dab-147">Ko storitvi Dynamics 365 Customer Insights omogočite prenos podatkov v storitev SendGrid, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="57dab-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="57dab-148">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da SendGrid izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="57dab-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="57dab-149">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="57dab-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="57dab-150">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="57dab-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]