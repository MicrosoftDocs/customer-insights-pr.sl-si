---
title: Izvozite podatke Customer Insights v Google Ads
description: Naučite se, kako konfigurirati povezavo in izvažati v Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305360"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="deb65-103">Izvoz segmentov v Google Ads (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="deb65-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="deb65-104">Segmente poenotenih profilov strank izvozite na seznam občinstva Google Ads in jih uporabite za oglaševanje v iskalniku Google, v storitvah Gmail, YouTube in v iskalnem omrežju Google.</span><span class="sxs-lookup"><span data-stu-id="deb65-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="deb65-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="deb65-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="deb65-106">Imate [račun za Google Ads](https://ads.google.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="deb65-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="deb65-107">Imate [odobreni žeton razvijalca v storitvi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span><span class="sxs-lookup"><span data-stu-id="deb65-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="deb65-108">Izpolnjujete zahteve, ki jih določa [Pravilnik o ujemanju strank](https://support.google.com/adspolicy/answer/6299717).</span><span class="sxs-lookup"><span data-stu-id="deb65-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="deb65-109">Izpolnjujete zahteve [velikosti seznama za ponovno trženje](https://support.google.com/google-ads/answer/7558048).</span><span class="sxs-lookup"><span data-stu-id="deb65-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="deb65-110">V storitvi Google Ads so na voljo obstoječa občinstva in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="deb65-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="deb65-111">Če želite več informacij, glejte razdelek [Občinstva Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="deb65-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="deb65-112">Imate [konfigurirane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="deb65-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="deb65-113">Poenoteni profili strank v izvoženih segmentih vsebujejo polja, ki predstavljajo e-poštni naslov ter ime in priimek.</span><span class="sxs-lookup"><span data-stu-id="deb65-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="deb65-114">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="deb65-114">Known limitations</span></span>

- <span data-ttu-id="deb65-115">Do 1 milijon profilov na izvoz v Google Ads.</span><span class="sxs-lookup"><span data-stu-id="deb65-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="deb65-116">Izvoz v Google Ads je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="deb65-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="deb65-117">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 5 minut zaradi omejitev na strani ponudnika.</span><span class="sxs-lookup"><span data-stu-id="deb65-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="deb65-118">Ujemanje v storitvi Google Ads lahko traja do 48 ur.</span><span class="sxs-lookup"><span data-stu-id="deb65-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="deb65-119">Nastavitev povezave s storitvijo Google Ads</span><span class="sxs-lookup"><span data-stu-id="deb65-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="deb65-120">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="deb65-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="deb65-121">Izberite **Dodajanje povezave** in izberite **Google Ads** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="deb65-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="deb65-122">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="deb65-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="deb65-123">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="deb65-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="deb65-124">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="deb65-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="deb65-125">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="deb65-125">Choose who can use this connection.</span></span> <span data-ttu-id="deb65-126">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="deb65-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="deb65-127">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="deb65-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="deb65-128">Vnesite **[ID stranke za Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="deb65-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="deb65-129">Vnesite **[odobreni žeton razvijalca v storitvi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="deb65-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="deb65-130">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="deb65-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="deb65-131">Izberite **Preverjanje pristnosti s storitvijo Google Ads** in vnesite svoje poverilnice za Google Ads.</span><span class="sxs-lookup"><span data-stu-id="deb65-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="deb65-132">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="deb65-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="deb65-133">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="deb65-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="deb65-134">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="deb65-134">Configure an export</span></span>

<span data-ttu-id="deb65-135">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="deb65-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="deb65-136">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="deb65-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="deb65-137">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="deb65-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="deb65-138">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="deb65-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="deb65-139">V polju **Povezava za izvoz** izberite povezavo v razdelku Google Ads.</span><span class="sxs-lookup"><span data-stu-id="deb65-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="deb65-140">Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="deb65-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="deb65-141">Vnesite **[ID občinstva za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in izberite **Poveži**, da inicializirate povezavo s storitvijo Google Ads.</span><span class="sxs-lookup"><span data-stu-id="deb65-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="deb65-142">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="deb65-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="deb65-143">Za polji **Ime** in **Priimek** ponovite iste korake.</span><span class="sxs-lookup"><span data-stu-id="deb65-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="deb65-144">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="deb65-144">Select the segments you want to export.</span></span> <span data-ttu-id="deb65-145">V Google Ads lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="deb65-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="deb65-146">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="deb65-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="deb65-147">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="deb65-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="deb65-148">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="deb65-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="deb65-149">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="deb65-149">Data privacy and compliance</span></span>

<span data-ttu-id="deb65-150">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Google Ads, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="deb65-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="deb65-151">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Google Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="deb65-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="deb65-152">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="deb65-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="deb65-153">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="deb65-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
