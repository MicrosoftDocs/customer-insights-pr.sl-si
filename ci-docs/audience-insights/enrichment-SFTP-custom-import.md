---
title: Obogatitev z uvozom po meri SFTP
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304670"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="d8ff3-103">Obogatite profile strank s podatki po meri (predogled)</span><span class="sxs-lookup"><span data-stu-id="d8ff3-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="d8ff3-104">Uvoz po meri s protokolom za varen prenos datotek (SFTP) vam omogoča uvoz podatkov, ki jim ni treba iti skozi postopek poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="d8ff3-105">To je prilagodljiv, varen in enostaven način za vnos podatkov.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="d8ff3-106">Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="d8ff3-107">Podatke je nato mogoče obdelati in obogatiti, s pomočjo uvoza po meri SFTP pa obogatene podatke vrniti nazaj k možnosti vpogledov občinstva Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8ff3-108">Zahteve</span><span class="sxs-lookup"><span data-stu-id="d8ff3-108">Prerequisites</span></span>

<span data-ttu-id="d8ff3-109">Za konfiguracijo uvoza po meri SFTP morajo biti izpolnjeni naslednji predpogoji:</span><span class="sxs-lookup"><span data-stu-id="d8ff3-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d8ff3-110">Ime in mesto (pot) datoteke, ki jo je treba uvoziti, se nahajata v gostitelju SFTP .</span><span class="sxs-lookup"><span data-stu-id="d8ff3-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="d8ff3-111">Obstaja datoteka z obliko zapisa *model.json*, ki določa [shemo za podatkovni model Common Data Model](/common-data-model/) za uvoz podatkov.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="d8ff3-112">Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="d8ff3-113">Skrbnik je že konfiguriral povezavo SFTP *oziroma* imate vi [skrbniška](permissions.md#administrator) dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="d8ff3-114">Potrebujete uporabniške poverilnice, URL in številko vrat za lokacijo SFTP, iz katere želite uvoziti podatke.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="d8ff3-115">Konfiguriranje uvoza</span><span class="sxs-lookup"><span data-stu-id="d8ff3-115">Configure the import</span></span>

1. <span data-ttu-id="d8ff3-116">Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="d8ff3-117">Na **ploščici za uvoz po meri SFTP** izberite možnost **Obogatitev podatkov** in nato izberite možnost **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ploščica za uvoz po meri SFTP.":::

1. <span data-ttu-id="d8ff3-119">Na spustnem seznamu izberite možnost [povezava](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d8ff3-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="d8ff3-120">Če ni na voljo nobena povezava, se obrnite na skrbnika.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d8ff3-121">Če ste skrbnik, lahko povezavo vzpostavite tako, da na spustnem seznamu izberete možnost **Dodaj povezavo**, nato pa **Uvoz po meri SFTP**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="d8ff3-122">Izberite možnost **Poveži z uvozom po meri** za potrditev izbrane povezave.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="d8ff3-123">Izberite **Naprej** in vnesite **Pot** ter **Ime podatkovne datoteke**, ki jo želite uvoziti.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Posnetek zaslona vnosa lokacije podatkov.":::

1. <span data-ttu-id="d8ff3-125">Izberite možnost **Naprej** ter navedite ime obogatitve in izhodne entitete.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="d8ff3-126">Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="d8ff3-127">Konfiguriranje povezave za uvoz uvoz po meri SFTP</span><span class="sxs-lookup"><span data-stu-id="d8ff3-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="d8ff3-128">Za konfiguriranje povezav morate biti skrbnik.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d8ff3-129">Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Uvoz po meri izberite možnost **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="d8ff3-130">Vnesite ime povezave v polje za **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d8ff3-131">Vnesite veljavno uporabniško ime, geslo in URL gostitelja za strežnik SFTP, v katerem se nahajajo podatki, ki jih želite uvoziti.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="d8ff3-132">Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d8ff3-133">Izberite možnost **Potrdi** za potrditev konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d8ff3-134">Ko zaključite s preverjanjem, lahko povezavo shranite tako, da izberete možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d8ff3-135">![Experian – stran za konfiguracijo povezave](media/enrichment-SFTP-connection.png "Experian – stran za konfiguracijo povezave")</span><span class="sxs-lookup"><span data-stu-id="d8ff3-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="d8ff3-136">Opredelitev preslikav polja</span><span class="sxs-lookup"><span data-stu-id="d8ff3-136">Defining field mappings</span></span> 

<span data-ttu-id="d8ff3-137">Imenik, ki vsebuje datoteko za uvoz v strežnik SFTP, mora vsebovati tudi datoteko *model.json*.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="d8ff3-138">Ta datoteka definira shemo za uvoz podatkov.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="d8ff3-139">Da bi določili preslikavo polja, mora biti za shemo uporabljen [Common Data Model](/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="d8ff3-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="d8ff3-140">Preprost primer datoteke model.json je videti takole:</span><span class="sxs-lookup"><span data-stu-id="d8ff3-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="d8ff3-141">Rezultati obogatitve</span><span class="sxs-lookup"><span data-stu-id="d8ff3-141">Enrichment results</span></span>

<span data-ttu-id="d8ff3-142">Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d8ff3-143">Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d8ff3-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d8ff3-144">Čas obdelave bo odvisen od velikosti podatkov, ki jih želite uvoziti, in povezave s strežnikom SFTP.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="d8ff3-145">Po končanem postopku obogatitve lahko svoje novo uvožene podatke obogatitve po meri pregledate v razdelku **Moje obogatitve**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="d8ff3-146">Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d8ff3-147">Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8ff3-148">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="d8ff3-148">Next steps</span></span>

<span data-ttu-id="d8ff3-149">Nadgradite svoje obogatene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d8ff3-150">Ustvarite [segmente](segments.md) in [mere](measures.md) ter celo [izvozite podatke](export-destinations.md) in tako svojim strankam zagotovite prilagojeno izkušnjo.</span><span class="sxs-lookup"><span data-stu-id="d8ff3-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
