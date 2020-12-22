---
title: Obogatitev z uvozom po meri SFTP
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568504"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f979c-103">Obogatite profile strank s podatki po meri (predogled)</span><span class="sxs-lookup"><span data-stu-id="f979c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f979c-104">Uvoz po meri s protokolom za varen prenos datotek (SFTP) vam omogoča uvoz podatkov, ki jim ni treba iti skozi postopek poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="f979c-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="f979c-105">To je prilagodljiv, varen in enostaven način za vnos podatkov.</span><span class="sxs-lookup"><span data-stu-id="f979c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f979c-106">Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev.</span><span class="sxs-lookup"><span data-stu-id="f979c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f979c-107">Podatke lahko nato obdelamo in obogatimo ter uporabimo uvoz po meri SFTP, da obogatene podatke vrnemo nazaj k zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f979c-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f979c-108">Zahteve</span><span class="sxs-lookup"><span data-stu-id="f979c-108">Prerequisites</span></span>

<span data-ttu-id="f979c-109">Za konfiguracijo uvoza po meri SFTP morajo biti izpolnjeni naslednji predpogoji:</span><span class="sxs-lookup"><span data-stu-id="f979c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f979c-110">Imate uporabniške poverilnice (uporabniško ime in geslo) za lokacijo SFTP, od koder bodo uvoženi podatki.</span><span class="sxs-lookup"><span data-stu-id="f979c-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="f979c-111">Imate URL in številko vrat (običajno 22) za gostitelja STFP.</span><span class="sxs-lookup"><span data-stu-id="f979c-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="f979c-112">Pri gostitelju SFTP imate ime in lokacijo datoteke, ki jo želite uvoziti.</span><span class="sxs-lookup"><span data-stu-id="f979c-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f979c-113">Tam je datoteka *model.json*, ki določa shemo za podatke, ki jih želite uvoziti.</span><span class="sxs-lookup"><span data-stu-id="f979c-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="f979c-114">Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.</span><span class="sxs-lookup"><span data-stu-id="f979c-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f979c-115">Imate [skrbniško](permissions.md#administrator) dovoljenje.</span><span class="sxs-lookup"><span data-stu-id="f979c-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="f979c-116">Konfiguracija</span><span class="sxs-lookup"><span data-stu-id="f979c-116">Configuration</span></span>

1. <span data-ttu-id="f979c-117">Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="f979c-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f979c-118">V **ploščici za uvoz po meri SFTP** izberite **Obogatitev podatkov**.</span><span class="sxs-lookup"><span data-stu-id="f979c-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f979c-119">![Ploščica za uvoz po meri SFTP](media/SFTP_Custom_Import_tile.png "Ploščica za uvoz po meri SFTP")</span><span class="sxs-lookup"><span data-stu-id="f979c-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="f979c-120">Izberite **Začetek** in vnesite poverilnice in naslov strežnika SFTP.</span><span class="sxs-lookup"><span data-stu-id="f979c-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="f979c-121">Na primer sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="f979c-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="f979c-122">Vnesite ime datoteke, ki vsebuje podatke in pot do datoteke v strežniku SFTP, če ni v korenski mapi.</span><span class="sxs-lookup"><span data-stu-id="f979c-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="f979c-123">Potrdite vse vnose z izbiro možnosti **Povezovanje z uvozom po meri**.</span><span class="sxs-lookup"><span data-stu-id="f979c-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f979c-124">![Pojavni meni za konfiguracijo uvoza po meri SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Pojavni meni za konfiguracijo uvoza po meri SFTP")</span><span class="sxs-lookup"><span data-stu-id="f979c-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="f979c-125">Opredelitev preslikav polja</span><span class="sxs-lookup"><span data-stu-id="f979c-125">Defining field mappings</span></span> 

<span data-ttu-id="f979c-126">Imenik, ki vsebuje datoteko za uvoz v strežnik SFTP, mora vsebovati tudi datoteko *model.json*.</span><span class="sxs-lookup"><span data-stu-id="f979c-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f979c-127">Ta datoteka definira shemo za uvoz podatkov.</span><span class="sxs-lookup"><span data-stu-id="f979c-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f979c-128">Shema mora uporabiti [Common Data Model](https://docs.microsoft.com/common-data-model/) za določanje preslikave polja.</span><span class="sxs-lookup"><span data-stu-id="f979c-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f979c-129">Preprost primer datoteke model.json je videti takole:</span><span class="sxs-lookup"><span data-stu-id="f979c-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="f979c-130">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="f979c-130">Enrichment results</span></span>

<span data-ttu-id="f979c-131">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="f979c-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f979c-132">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f979c-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f979c-133">Čas obdelave bo odvisen od velikosti podatkov, ki jih želite uvoziti, in povezave s strežnikom SFTP.</span><span class="sxs-lookup"><span data-stu-id="f979c-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f979c-134">Po končanem postopku obogatitve lahko svoje novo uvožene podatke obogatitve po meri pregledate v razdelku **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="f979c-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f979c-135">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="f979c-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f979c-136">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="f979c-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f979c-137">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="f979c-137">Next steps</span></span>

<span data-ttu-id="f979c-138">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="f979c-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f979c-139">Ustvarite [segmente](segments.md), [mere](measures.md) in [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojene izkušnje.</span><span class="sxs-lookup"><span data-stu-id="f979c-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


