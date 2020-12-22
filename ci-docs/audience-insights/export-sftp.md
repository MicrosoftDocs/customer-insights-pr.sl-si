---
title: Izvozite podatke Customer Insights v gostitelje SFTP
description: Preberite, kako konfigurirati povezavo z gostiteljem SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643523"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="bb218-103">Povezovalnik za SFTP (predogled)</span><span class="sxs-lookup"><span data-stu-id="bb218-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="bb218-104">Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite v gostitelja s protokolom za varen prenos datotek (SFTP).</span><span class="sxs-lookup"><span data-stu-id="bb218-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb218-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="bb218-105">Prerequisites</span></span>

- <span data-ttu-id="bb218-106">Razpoložljivost gostitelja SFTP in ustreznih poverilnic.</span><span class="sxs-lookup"><span data-stu-id="bb218-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="bb218-107">Vzpostavite povezavo z gostiteljem SFTP</span><span class="sxs-lookup"><span data-stu-id="bb218-107">Connect to SFTP</span></span>

1. <span data-ttu-id="bb218-108">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="bb218-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bb218-109">V razdelku **SFTP** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="bb218-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="bb218-110">Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="bb218-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bb218-111">Vnesite **uporabniško ime**, **geslo** in **ime gostitelja** za vaš račun SFTP.</span><span class="sxs-lookup"><span data-stu-id="bb218-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="bb218-112">Primer: če je korenska mapa vašega strežnika SFTP /root/folder in želite, da se podatki izvozijo v /root/folder/ci_export_destination_folder, mora biti gostitelj sftp://<server_address>/ci_export_destination_folder.</span><span class="sxs-lookup"><span data-stu-id="bb218-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="bb218-113">Če želite preskusiti povezavo, izberite **Preveri**.</span><span class="sxs-lookup"><span data-stu-id="bb218-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="bb218-114">Po uspešnem preverjanju se odločite, ali želite podatke izvoziti v **Stisnjeni mapi** ali **Nestisnjeni mapi** in izberite **ločilni znak za polje** za izvožene datoteke.</span><span class="sxs-lookup"><span data-stu-id="bb218-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="bb218-115">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="bb218-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bb218-116">Izberite **Naslednji**, če želite začeti konfigurirati izvoz.</span><span class="sxs-lookup"><span data-stu-id="bb218-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="bb218-117">Konfiguriraj povezavo</span><span class="sxs-lookup"><span data-stu-id="bb218-117">Configure the connection</span></span>

1. <span data-ttu-id="bb218-118">Izberite **atribute strank**, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="bb218-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="bb218-119">Lahko izvozite enega ali več atributov.</span><span class="sxs-lookup"><span data-stu-id="bb218-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="bb218-120">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="bb218-120">Select **Next**.</span></span>

1. <span data-ttu-id="bb218-121">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="bb218-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="bb218-122">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="bb218-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bb218-123">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="bb218-123">Export the data</span></span>

<span data-ttu-id="bb218-124">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bb218-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bb218-125">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb218-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb218-126">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="bb218-126">Data privacy and compliance</span></span>

<span data-ttu-id="bb218-127">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="bb218-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb218-128">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="bb218-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb218-129">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb218-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bb218-130">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="bb218-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
