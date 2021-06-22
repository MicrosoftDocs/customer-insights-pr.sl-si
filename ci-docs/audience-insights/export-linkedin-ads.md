---
title: Izvoz podatkov Customer Insights v LinkedIn Ads
description: Naučite se, kako konfigurirati povezavo in izvažati v LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124554"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="86d1f-103">Izvoz segmentov v LinkedIn Ads (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="86d1f-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="86d1f-104">Izvozite segmente poenotenih profilov strank v LinkedIn Ads, da ustvarite ujemajoče se ciljne skupine.</span><span class="sxs-lookup"><span data-stu-id="86d1f-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="86d1f-105">Uporabite ujemajoče se ciljne skupine za ciljanje podjetij in stikov.</span><span class="sxs-lookup"><span data-stu-id="86d1f-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86d1f-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="86d1f-106">Prerequisites</span></span>

-   <span data-ttu-id="86d1f-107">Imate račun za [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) in pripadajoče skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="86d1f-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="86d1f-108">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="86d1f-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="86d1f-109">Profili strank v izvoženih segmentih vsebujejo polje z e-poštnim naslovom.</span><span class="sxs-lookup"><span data-stu-id="86d1f-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="86d1f-110">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="86d1f-110">Known limitations</span></span>

- <span data-ttu-id="86d1f-111">V LinkedIn Ads lahko izvozite do 100.000 profilov na izvoz.</span><span class="sxs-lookup"><span data-stu-id="86d1f-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="86d1f-112">Izvoz v LinkedIn Ads je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="86d1f-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="86d1f-113">Izvoz do 100.000 profilov v LinkedIn Ads lahko traja do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="86d1f-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="86d1f-114">Nastavitev povezave z LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="86d1f-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="86d1f-115">V pogledih v občinstvo odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="86d1f-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="86d1f-116">Izberite **Dodajanje povezave** in izberite **LinkedIn Ads** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="86d1f-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="86d1f-117">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="86d1f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="86d1f-118">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="86d1f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="86d1f-119">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="86d1f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="86d1f-120">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="86d1f-120">Choose who can use this connection.</span></span> <span data-ttu-id="86d1f-121">Če ne izvedete nobenih dejanj, so privzeto izbrani skrbniki.</span><span class="sxs-lookup"><span data-stu-id="86d1f-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="86d1f-122">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="86d1f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="86d1f-123">Navedite svoj [ID računa LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="86d1f-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="86d1f-124">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="86d1f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="86d1f-125">Izberite **Poveži** za inicializiranje povezave s storitvijo Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="86d1f-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="86d1f-126">Izberite **Preverjanje pristnosti z aplikacijo LinkedIn** in vnesite svoje skrbniške poverilnice za LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="86d1f-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="86d1f-127">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="86d1f-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="86d1f-128">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="86d1f-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="86d1f-129">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="86d1f-129">Configure an export</span></span>

<span data-ttu-id="86d1f-130">Izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="86d1f-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="86d1f-131">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="86d1f-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="86d1f-132">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="86d1f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="86d1f-133">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="86d1f-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="86d1f-134">V polju **Povezava za izvoz** izberite povezavo iz razdelka LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="86d1f-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="86d1f-135">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="86d1f-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="86d1f-136">Izberite, ali želite izvoziti podatke za [ciljanje na stike](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ali [ciljanje na podjetja](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) v orodju LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="86d1f-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="86d1f-137">V razdelku **Ujemanje podatkov** izberite polje v svojem poenotenem profilu stranke, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="86d1f-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="86d1f-138">To je obvezno za izvoz segmentov LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="86d1f-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="86d1f-139">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="86d1f-139">Select the segments you want to export.</span></span> <span data-ttu-id="86d1f-140">Ujemajoče se ciljne skupine v LinkedIn Campaign Manager bodo samodejno ustvarjene z imenom segmentov za izvoz.</span><span class="sxs-lookup"><span data-stu-id="86d1f-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="86d1f-141">Vsak segment bo prikazal ločeno ciljno skupino.</span><span class="sxs-lookup"><span data-stu-id="86d1f-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="86d1f-142">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="86d1f-142">Select **Save**.</span></span>

<span data-ttu-id="86d1f-143">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="86d1f-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="86d1f-144">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="86d1f-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="86d1f-145">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="86d1f-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="86d1f-146">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="86d1f-146">Data privacy and compliance</span></span>

<span data-ttu-id="86d1f-147">Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v LinkedIn Ads, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="86d1f-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="86d1f-148">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da LinkedIn Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate.</span><span class="sxs-lookup"><span data-stu-id="86d1f-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="86d1f-149">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="86d1f-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="86d1f-150">Vaš skrbnik Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza, da prenehate uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="86d1f-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
