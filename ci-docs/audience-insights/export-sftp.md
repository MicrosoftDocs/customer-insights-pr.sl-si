---
title: Izvozite podatke Customer Insights v gostitelje SFTP
description: Preberite, kako konfigurirati povezavo z gostiteljem SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598405"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="68cb3-103">Povezovalnik za SFTP (predogled)</span><span class="sxs-lookup"><span data-stu-id="68cb3-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="68cb3-104">Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite v gostitelja s protokolom za varen prenos datotek (SFTP).</span><span class="sxs-lookup"><span data-stu-id="68cb3-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68cb3-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="68cb3-105">Prerequisites</span></span>

- <span data-ttu-id="68cb3-106">Razpoložljivost gostitelja SFTP in ustreznih poverilnic</span><span class="sxs-lookup"><span data-stu-id="68cb3-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="68cb3-107">Vzpostavitev povezave z SFTP-jem</span><span class="sxs-lookup"><span data-stu-id="68cb3-107">Connect to SFTP</span></span>

1. <span data-ttu-id="68cb3-108">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="68cb3-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="68cb3-109">V razdelku **SFTP** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="68cb3-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="68cb3-110">Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="68cb3-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="68cb3-111">Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.</span><span class="sxs-lookup"><span data-stu-id="68cb3-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="68cb3-112">Če želite preskusiti povezavo, izberite **Preveri**.</span><span class="sxs-lookup"><span data-stu-id="68cb3-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="68cb3-113">Po uspešnem preverjanju izberite, ali želite podatke izvoziti **stisnjeno** ali **razširjeno**, in izberite **ločilo polja** za izvožene datoteke.</span><span class="sxs-lookup"><span data-stu-id="68cb3-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="68cb3-114">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="68cb3-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68cb3-115">Izberite **Naslednji**, če želite začeti konfigurirati izvoz.</span><span class="sxs-lookup"><span data-stu-id="68cb3-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="68cb3-116">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="68cb3-116">Configure the export</span></span>

1. <span data-ttu-id="68cb3-117">Izberite entitete, na primer segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="68cb3-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="68cb3-118">Vsaka izbrana entiteta bo ob izvozu imela do pet izhodnih datotek.</span><span class="sxs-lookup"><span data-stu-id="68cb3-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="68cb3-119">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="68cb3-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="68cb3-120">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="68cb3-120">Export the data</span></span>

<span data-ttu-id="68cb3-121">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="68cb3-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="68cb3-122">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68cb3-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68cb3-123">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="68cb3-123">Known limitations</span></span>

- <span data-ttu-id="68cb3-124">Trajanje izvoza je odvisno od zmogljivosti vašega sistema.</span><span class="sxs-lookup"><span data-stu-id="68cb3-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="68cb3-125">Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika.</span><span class="sxs-lookup"><span data-stu-id="68cb3-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="68cb3-126">Izvoz entitet z do 100 milijoni profilov strank lahko traja 90 minut, če uporabite priporočeno minimalno konfiguracijo dvojedrnega procesorja in 1 Gb pomnilnika.</span><span class="sxs-lookup"><span data-stu-id="68cb3-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68cb3-127">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="68cb3-127">Data privacy and compliance</span></span>

<span data-ttu-id="68cb3-128">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="68cb3-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68cb3-129">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="68cb3-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="68cb3-130">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68cb3-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68cb3-131">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="68cb3-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]