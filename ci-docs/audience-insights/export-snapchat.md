---
title: Izvoz podatkov Customer Insights v Snapchat
description: Naučite se, kako konfigurirati povezavo in izvažati v Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760635"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="a3393-103">Izvoz seznamov segmentov v Snapchat (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="a3393-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="a3393-104">Izvozite segmente poenotenih profilov strank v Snapchat in jih uporabite za oglaševanje.</span><span class="sxs-lookup"><span data-stu-id="a3393-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a3393-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="a3393-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a3393-106">Imate [račun za Snapchat Business](https://business.snapchat.com/), [račun za Snapchat Ads](https://ads.snapchat.com/) in pripadajoče skrbniške poverilnice.</span><span class="sxs-lookup"><span data-stu-id="a3393-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a3393-107">Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="a3393-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a3393-108">Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.</span><span class="sxs-lookup"><span data-stu-id="a3393-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a3393-109">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="a3393-109">Known limitations</span></span>

- <span data-ttu-id="a3393-110">Izvoz v Snapchat je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="a3393-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="a3393-111">Izvoz do 1 milijona profilov v Snapchat lahko traja do 15 minut.</span><span class="sxs-lookup"><span data-stu-id="a3393-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="a3393-112">Nastavitev povezave s storitvijo Snapchat</span><span class="sxs-lookup"><span data-stu-id="a3393-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="a3393-113">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="a3393-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a3393-114">Izberite **Dodajanje povezave** in izberite **Snapchat** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="a3393-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="a3393-115">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="a3393-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a3393-116">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="a3393-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a3393-117">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="a3393-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a3393-118">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="a3393-118">Choose who can use this connection.</span></span> <span data-ttu-id="a3393-119">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="a3393-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a3393-120">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a3393-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a3393-121">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="a3393-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a3393-122">Izberite **Poveži** za inicializiranje povezave s storitvijo Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a3393-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="a3393-123">Izberite **Preverjanje pristnosti z aplikacijo Snapchat** in vnesite skrbniške poverilnice za Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a3393-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="a3393-124">Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3393-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a3393-125">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="a3393-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a3393-126">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="a3393-126">Configure an export</span></span>

<span data-ttu-id="a3393-127">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="a3393-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a3393-128">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a3393-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a3393-129">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="a3393-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3393-130">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="a3393-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a3393-131">V polju **Povezava za izvoz** izberite povezavo v razdelku Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a3393-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="a3393-132">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="a3393-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a3393-133">Vnesite [**ID občinstva storitve Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="a3393-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="a3393-134">V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.</span><span class="sxs-lookup"><span data-stu-id="a3393-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a3393-135">To je obvezno za izvoz segmentov Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a3393-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="a3393-136">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="a3393-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="a3393-137">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="a3393-137">Select **Save**.</span></span>

<span data-ttu-id="a3393-138">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="a3393-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a3393-139">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a3393-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a3393-140">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a3393-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a3393-141">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="a3393-141">Data privacy and compliance</span></span>

<span data-ttu-id="a3393-142">Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Snapchat, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="a3393-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a3393-143">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Snapchat izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate.</span><span class="sxs-lookup"><span data-stu-id="a3393-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a3393-144">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a3393-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a3393-145">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="a3393-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
