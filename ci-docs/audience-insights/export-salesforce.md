---
title: Podatke iz storitve Customer Insights izvozite v Saleforce Marketing Cloud
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314675"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="59ac3-103">Izvoz segmentov in drugih podatkov v Salesforce Marketing Cloud (predogled)</span><span class="sxs-lookup"><span data-stu-id="59ac3-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="59ac3-104">Podatke o strankah uporabite v programu Salesforce Marketing Cloud tako, da jih izvozite s pomočjo lokacije protokola za varen prenos datotek (SFTP).</span><span class="sxs-lookup"><span data-stu-id="59ac3-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="59ac3-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="59ac3-105">Prerequisites for connection</span></span>

- <span data-ttu-id="59ac3-106">Razpoložljivost gostitelja SFTP in ustreznih skrbniških poverilnic.</span><span class="sxs-lookup"><span data-stu-id="59ac3-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="59ac3-107">Kako nastaviti lokacije SFTP za Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="59ac3-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="59ac3-108">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="59ac3-108">Known limitations</span></span>

- <span data-ttu-id="59ac3-109">Trajanje izvoza je odvisno od zmogljivosti vašega sistema.</span><span class="sxs-lookup"><span data-stu-id="59ac3-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="59ac3-110">Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika.</span><span class="sxs-lookup"><span data-stu-id="59ac3-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="59ac3-111">Izvoz entitet z največ 100 milijoni profilov strank lahko ob uporabi priporočene minimalne konfiguracije traja 90 minut.</span><span class="sxs-lookup"><span data-stu-id="59ac3-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="59ac3-112">Vzpostavite povezavo s storitvijo Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="59ac3-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="59ac3-113">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="59ac3-114">Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **Salesforce Marketing Cloud**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="59ac3-115">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="59ac3-116">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="59ac3-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="59ac3-117">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="59ac3-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="59ac3-118">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="59ac3-118">Choose who can use this connection.</span></span> <span data-ttu-id="59ac3-119">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="59ac3-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="59ac3-120">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="59ac3-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="59ac3-121">Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.</span><span class="sxs-lookup"><span data-stu-id="59ac3-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="59ac3-122">Če želite preskusiti povezavo, izberite **Preveri**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="59ac3-123">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="59ac3-124">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="59ac3-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="59ac3-125">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="59ac3-125">Configure an export</span></span>

<span data-ttu-id="59ac3-126">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="59ac3-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="59ac3-127">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="59ac3-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="59ac3-128">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="59ac3-129">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="59ac3-130">V polju **Povezava za izvoz** izberite povezavo v razdelku SFTP.</span><span class="sxs-lookup"><span data-stu-id="59ac3-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="59ac3-131">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="59ac3-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="59ac3-132">Izberite, ali želite izvoziti podatke z možnostjo **Gzipped** ali **Razširjeno** in **ločilo polja** za izvožene datoteke.</span><span class="sxs-lookup"><span data-stu-id="59ac3-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="59ac3-133">Izberite entitete, na primer segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="59ac3-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="59ac3-134">Vsaka izbrana entiteta bo ob izvozu razdeljena na do pet izhodnih datotek.</span><span class="sxs-lookup"><span data-stu-id="59ac3-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="59ac3-135">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="59ac3-135">Select **Save**.</span></span>

<span data-ttu-id="59ac3-136">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="59ac3-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="59ac3-137">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="59ac3-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="59ac3-138">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="59ac3-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="59ac3-139">Podatke Customer Insights iz lokacije SFTP izvozite v Saleforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="59ac3-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="59ac3-140">Za uvoz podatkovne datoteke Customer Insights iz lokacije SFTP ustvarite [razširitve podatkov v storitvi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz podatkovne datoteke Customer Insights z lokacije SFTP.</span><span class="sxs-lookup"><span data-stu-id="59ac3-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="59ac3-141">[Uvozite podatke z lokacije SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) v razširitev podatkov Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="59ac3-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="59ac3-142">Za uvoz podatkov v razširitve podatkov nastavite avtomatizacijo.</span><span class="sxs-lookup"><span data-stu-id="59ac3-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="59ac3-143">Preberite več o [avtomatizacijah spuščanja datotek in načrtovanih avtomatizacijah](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="59ac3-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="59ac3-144">Določite [avtomatizacijo spuščanja datotek](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ali  [načrtovano avtomatizacijo](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="59ac3-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="59ac3-145">Tukaj je naveden primer [avtomatizacije s SFTP-jem](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="59ac3-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="59ac3-146">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="59ac3-146">Data privacy and compliance</span></span>

<span data-ttu-id="59ac3-147">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="59ac3-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="59ac3-148">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="59ac3-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="59ac3-149">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="59ac3-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="59ac3-150">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="59ac3-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
