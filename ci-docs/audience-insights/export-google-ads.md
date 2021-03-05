---
title: Izvozite podatke Customer Insights v Google Ads
description: Preberite o konfiguraciji povezave s storitvijo Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268982"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="36161-103">Povezovalnik za Google Ads (predogled)</span><span class="sxs-lookup"><span data-stu-id="36161-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="36161-104">Izvozite segmente poenotenih profilov strank na seznam občinstva storitve Google Ads in jih uporabite za oglaševanje v Googlovem iskalniku ter storitvah Gmail, YouTube in Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="36161-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="36161-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="36161-105">Prerequisites</span></span>

-   <span data-ttu-id="36161-106">Imate [račun za Google Ads](https://ads.google.com/) in ustrezne skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="36161-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="36161-107">V storitvi Google Ads so na voljo obstoječa občinstva in ustrezni ID-ji.</span><span class="sxs-lookup"><span data-stu-id="36161-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="36161-108">Če želite več informacij, glejte razdelek [Občinstva Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="36161-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="36161-109">Imate [konfigurirane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="36161-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="36161-110">Poenoteni profili strank v izvoženih segmentih vsebujejo polja, ki predstavljajo e-poštni naslov, ime in priimek.</span><span class="sxs-lookup"><span data-stu-id="36161-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="36161-111">Vzpostavitev povezave s storitvijo Google Ads</span><span class="sxs-lookup"><span data-stu-id="36161-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="36161-112">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="36161-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="36161-113">V razdelku **Google Ads** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="36161-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="36161-114">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="36161-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="36161-115">Vnesite **[ID stranke za Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="36161-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="36161-116">Vnesite **[odobreni žeton razvijalca v storitvi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="36161-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="36161-117">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="36161-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="36161-118">Vnesite **[ID občinstva za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in izberite **Poveži**, da inicializirate povezavo s storitvijo Google Ads.</span><span class="sxs-lookup"><span data-stu-id="36161-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="36161-119">Izberite **Preverjanje pristnosti s storitvijo Google Ads** in vnesite svoje poverilnice za Google Ads.</span><span class="sxs-lookup"><span data-stu-id="36161-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="36161-120">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="36161-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Posnetek zaslona izvoza za povezavo Google Ads":::

1. <span data-ttu-id="36161-122">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="36161-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="36161-123">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="36161-123">Configure the connector</span></span>

1. <span data-ttu-id="36161-124">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="36161-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="36161-125">Ponovite iste korake za polji **Ime** in **Priimek**.</span><span class="sxs-lookup"><span data-stu-id="36161-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="36161-126">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="36161-126">Select the segments you want to export.</span></span> <span data-ttu-id="36161-127">V Google Ads lahko izvozite do 1 milijon profilov strank.</span><span class="sxs-lookup"><span data-stu-id="36161-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="36161-128">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="36161-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="36161-129">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="36161-129">Export the data</span></span>

<span data-ttu-id="36161-130">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="36161-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="36161-131">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36161-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="36161-132">V storitvi Google Ads lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="36161-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="36161-133">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="36161-133">Known limitations</span></span>

- <span data-ttu-id="36161-134">Do 1 milijon profilov na izvoz v Google Ads.</span><span class="sxs-lookup"><span data-stu-id="36161-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="36161-135">Izvoz v Google Ads je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="36161-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="36161-136">Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 5 minut zaradi omejitev na strani ponudnika.</span><span class="sxs-lookup"><span data-stu-id="36161-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="36161-137">Ujemanje v storitvi Google Ads lahko traja do 48 ur.</span><span class="sxs-lookup"><span data-stu-id="36161-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="36161-138">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="36161-138">Data privacy and compliance</span></span>

<span data-ttu-id="36161-139">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Google Ads, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="36161-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="36161-140">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Google Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="36161-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="36161-141">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="36161-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="36161-142">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="36161-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]