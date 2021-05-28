---
title: Izvozite podatke Customer Insights v DotDigital
description: Naučite se, kako konfigurirati povezavo in izvažati v DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976866"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="427d6-103">Izvoz seznamov segmentov v DotDigital (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="427d6-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="427d6-104">Izvozite segmente poenotenih profilov strank v adresarje DotDigital ter jih uporabite za akcije, e-poštno trženje ter sestavljanje segmentov strank s storitvijo DotDigital.</span><span class="sxs-lookup"><span data-stu-id="427d6-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="427d6-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="427d6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="427d6-106">Imate [račun za DotDigital](https://dotdigital.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="427d6-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="427d6-107">V storitvi DotDigital so na voljo obstoječi adresarji in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="427d6-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="427d6-108">ID lahko najdete v URL-ju, ko izberete in odprete adresar.</span><span class="sxs-lookup"><span data-stu-id="427d6-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="427d6-109">Za več informacij glejte [Adresarji DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="427d6-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="427d6-110">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="427d6-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="427d6-111">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="427d6-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="427d6-112">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="427d6-112">Known limitations</span></span>

- <span data-ttu-id="427d6-113">Do 1 milijon profilov na izvoz v DotDigital.</span><span class="sxs-lookup"><span data-stu-id="427d6-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="427d6-114">Izvoz v DotDigital je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="427d6-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="427d6-115">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure zaradi omejitev na strani ponudnika.</span><span class="sxs-lookup"><span data-stu-id="427d6-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="427d6-116">Število profilov, ki jih lahko izvozite v DotDigital, je odvisno in omejeno glede na vašo pogodbo s podjetjem DotDigital.</span><span class="sxs-lookup"><span data-stu-id="427d6-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="427d6-117">Nastavitev povezave s storitvijo DotDigital</span><span class="sxs-lookup"><span data-stu-id="427d6-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="427d6-118">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="427d6-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="427d6-119">Izberite **Dodajanje povezave** in izberite **DotDigital** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="427d6-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="427d6-120">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="427d6-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="427d6-121">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="427d6-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="427d6-122">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="427d6-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="427d6-123">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="427d6-123">Choose who can use this connection.</span></span> <span data-ttu-id="427d6-124">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="427d6-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="427d6-125">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="427d6-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="427d6-126">Vnesite **uporabniško ime in geslo za DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="427d6-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="427d6-127">Vpišite svoj **[ID za adresar DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="427d6-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="427d6-128">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="427d6-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="427d6-129">Izberite **Poveži**, da inicializirate povezavo s storitvijo DotDigital.</span><span class="sxs-lookup"><span data-stu-id="427d6-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="427d6-130">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="427d6-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="427d6-131">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="427d6-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="427d6-132">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="427d6-132">Configure an export</span></span>

<span data-ttu-id="427d6-133">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="427d6-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="427d6-134">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="427d6-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="427d6-135">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="427d6-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="427d6-136">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="427d6-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="427d6-137">V polju **Povezava za izvoz** izberite povezavo v razdelku DotDigital.</span><span class="sxs-lookup"><span data-stu-id="427d6-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="427d6-138">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="427d6-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="427d6-139">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="427d6-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="427d6-140">Ponovite iste korake za druga neobvezna polja, kot so **Ime**, **Priimek**, **Polno ime**, **Spol** in **Poštna številka**.</span><span class="sxs-lookup"><span data-stu-id="427d6-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="427d6-141">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="427d6-141">Select the segments you want to export.</span></span> <span data-ttu-id="427d6-142">V DotDigital lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="427d6-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="427d6-143">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="427d6-143">Select **Save**.</span></span>

<span data-ttu-id="427d6-144">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="427d6-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="427d6-145">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="427d6-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="427d6-146">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="427d6-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="427d6-147">V storitvi DotDigital lahko zdaj najdete svoje segmente v [adresarjih DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="427d6-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="427d6-148">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="427d6-148">Data privacy and compliance</span></span>

<span data-ttu-id="427d6-149">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v DotDigital, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="427d6-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="427d6-150">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da DotDigital izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="427d6-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="427d6-151">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="427d6-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="427d6-152">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="427d6-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
