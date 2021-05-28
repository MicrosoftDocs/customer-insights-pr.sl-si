---
title: Izvozite podatke Customer Insights v gostitelje SFTP
description: Naučite se, kako konfigurirati povezavo in izvažati na lokacijo SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976959"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="bd759-103">Izvoz seznamov segmentov in drugih podatkov v SFTP (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="bd759-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="bd759-104">Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite na lokacijo protokola za varen prenos datotek (SFTP).</span><span class="sxs-lookup"><span data-stu-id="bd759-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bd759-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="bd759-105">Prerequisites for connection</span></span>

- <span data-ttu-id="bd759-106">Razpoložljivost gostitelja SFTP in ustreznih poverilnic</span><span class="sxs-lookup"><span data-stu-id="bd759-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bd759-107">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="bd759-107">Known limitations</span></span>

- <span data-ttu-id="bd759-108">Trajanje izvoza je odvisno od zmogljivosti vašega sistema.</span><span class="sxs-lookup"><span data-stu-id="bd759-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="bd759-109">Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika.</span><span class="sxs-lookup"><span data-stu-id="bd759-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="bd759-110">Izvoz entitet z do 100 milijoni profilov strank lahko traja 90 minut, če uporabite priporočeno minimalno konfiguracijo dvojedrnega procesorja in 1 Gb pomnilnika.</span><span class="sxs-lookup"><span data-stu-id="bd759-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="bd759-111">Nastavitev povezave s storitvijo SFTP</span><span class="sxs-lookup"><span data-stu-id="bd759-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="bd759-112">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="bd759-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bd759-113">Izberite **Dodajanje povezave** in izberite **SFTP** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="bd759-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="bd759-114">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="bd759-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bd759-115">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="bd759-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bd759-116">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="bd759-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bd759-117">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="bd759-117">Choose who can use this connection.</span></span> <span data-ttu-id="bd759-118">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="bd759-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bd759-119">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bd759-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bd759-120">Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.</span><span class="sxs-lookup"><span data-stu-id="bd759-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="bd759-121">Če želite preskusiti povezavo, izberite **Preveri**.</span><span class="sxs-lookup"><span data-stu-id="bd759-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="bd759-122">Izberite, ali želite izvoziti podatke z možnostjo **Gzipped** ali **Razširjeno** in **ločilo polja** za izvožene datoteke.</span><span class="sxs-lookup"><span data-stu-id="bd759-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="bd759-123">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="bd759-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bd759-124">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="bd759-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bd759-125">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="bd759-125">Configure an export</span></span>

<span data-ttu-id="bd759-126">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="bd759-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bd759-127">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bd759-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bd759-128">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="bd759-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd759-129">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="bd759-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bd759-130">V polju **Povezava za izvoz** izberite povezavo v razdelku SFTP.</span><span class="sxs-lookup"><span data-stu-id="bd759-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="bd759-131">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="bd759-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bd759-132">Izberite entitete, na primer segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="bd759-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bd759-133">Vsaka izbrana entiteta bo ob izvozu razdeljena na do pet izhodnih datotek.</span><span class="sxs-lookup"><span data-stu-id="bd759-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="bd759-134">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="bd759-134">Select **Save**.</span></span>

<span data-ttu-id="bd759-135">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="bd759-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bd759-136">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd759-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd759-137">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd759-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bd759-138">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="bd759-138">Data privacy and compliance</span></span>

<span data-ttu-id="bd759-139">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="bd759-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bd759-140">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="bd759-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bd759-141">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bd759-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bd759-142">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="bd759-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
