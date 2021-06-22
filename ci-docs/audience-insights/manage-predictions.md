---
title: Opravila v skupni rabi za scenarije predvidevanja
description: Naučite se upravljati, odpravljati težave in izboljšati predvidevanja.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095752"
---
# <a name="manage-predictions"></a><span data-ttu-id="46471-103">Upravljanje predvidevanj</span><span class="sxs-lookup"><span data-stu-id="46471-103">Manage predictions</span></span>

<span data-ttu-id="46471-104">Ta članek obravnava nekatere naloge, ki so skupne večini scenarijev predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="46471-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="46471-105">Odpravite težave z neuspešnim predvidevanjem</span><span class="sxs-lookup"><span data-stu-id="46471-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="46471-106">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="46471-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="46471-107">Izberite navpične tri pike poleg predvidevanja, za katere si želite ogledati dnevnike napak.</span><span class="sxs-lookup"><span data-stu-id="46471-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="46471-108">Izberite **Dnevniki**.</span><span class="sxs-lookup"><span data-stu-id="46471-108">Select **Logs**.</span></span>

1. <span data-ttu-id="46471-109">Preglejte vse napake.</span><span class="sxs-lookup"><span data-stu-id="46471-109">Review all the errors.</span></span> <span data-ttu-id="46471-110">Pride lahko do več vrst napak, ki opisujejo, kakšno stanje je povzročilo napako.</span><span class="sxs-lookup"><span data-stu-id="46471-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="46471-111">Primer: napaka, za katero ni dovolj podatkov za natančno predvidevanje, se običajno odpravi z nalaganjem dodatnih podatkov v storitev Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46471-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="46471-112">Poročilo o uporabnosti vhodnih podatkov</span><span class="sxs-lookup"><span data-stu-id="46471-112">Input data usability report</span></span>

<span data-ttu-id="46471-113">Poročilo o uporabnosti vhodnih podatkov ponuja strnjen prikaz napak in opozoril, ki jih lahko ustvarijo vaše vnaprej pripravljene napovedi.</span><span class="sxs-lookup"><span data-stu-id="46471-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="46471-114">Prav tako daje priporočila, kako izboljšati zmogljivost modela.</span><span class="sxs-lookup"><span data-stu-id="46471-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="46471-115">Poročilo je na voljo, ko model zaključi s postopkom kvalificiranja.</span><span class="sxs-lookup"><span data-stu-id="46471-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="46471-116">Ustvarjeno je za vsak model posebej, ne glede na to, ali je bilo uspešno zaključeno ali ne.</span><span class="sxs-lookup"><span data-stu-id="46471-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="46471-117">Trenutno ta funkcija deluje samo za model izgube transakcije.</span><span class="sxs-lookup"><span data-stu-id="46471-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="46471-118">Ogled poročila o uporabnosti vhodnih podatkov</span><span class="sxs-lookup"><span data-stu-id="46471-118">View the input data usability report</span></span>

<span data-ttu-id="46471-119">Ko vnaprej pripravljen model zaključi korak za kvalificiranje, si oglejte poročilo:</span><span class="sxs-lookup"><span data-stu-id="46471-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="46471-120">Izberite tri pike poleg imena modela in izberite **Poročilo o uporabnosti vhodnih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="46471-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="46471-121">Izberite stanje modela in nato v stranskem podoknu kliknite **Ogled poročila o uporabnosti vhodnih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="46471-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="46471-122">Izberite enega od modelov na seznamu in izberite **Poročilo o uporabnosti vhodnih podatkov** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="46471-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="46471-123">Odprite stran z rezultati modela in nato **Poročilo o uporabnosti vhodnih podatkov** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="46471-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="46471-124">Podatki v poročilu o uporabnosti vhodnih podatkov</span><span class="sxs-lookup"><span data-stu-id="46471-124">Information in the input data usability report</span></span>

<span data-ttu-id="46471-125">Naslednji stolpci poročila vsebujejo koristne informacije za izboljšanje podatkov za model.</span><span class="sxs-lookup"><span data-stu-id="46471-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer poročila o uporabnosti vhodnih podatkov, ki prikazuje tabelo z napakami, opozorili in priporočili.":::

- <span data-ttu-id="46471-127">Ime: opisno ime napake, opozorila ali priporočila.</span><span class="sxs-lookup"><span data-stu-id="46471-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="46471-128">Korak: faza modela, kvalificiranje ali rezultat, na katerega se informacije nanašajo.</span><span class="sxs-lookup"><span data-stu-id="46471-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="46471-129">Stanje: resnost informacij (napaka, opozorilo, priporočilo).</span><span class="sxs-lookup"><span data-stu-id="46471-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="46471-130">Ime stolpca: stolpec v entiteti, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.</span><span class="sxs-lookup"><span data-stu-id="46471-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="46471-131">Ime entitete: ime entitete, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.</span><span class="sxs-lookup"><span data-stu-id="46471-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="46471-132">Podrobnosti: podrobnosti o napaki, opozorilu ali priporočilu.</span><span class="sxs-lookup"><span data-stu-id="46471-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="46471-133">Osveževanje predvidevanja</span><span class="sxs-lookup"><span data-stu-id="46471-133">Refresh a prediction</span></span>

<span data-ttu-id="46471-134">Predvidevanja se bodo samodejno osvežila v istem [urniku, kot ga osvežijo vaši podatki](system.md#schedule-tab), ko se konfigurirajo v nastavitvah.</span><span class="sxs-lookup"><span data-stu-id="46471-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="46471-135">Lahko jih osvežite tudi ročno.</span><span class="sxs-lookup"><span data-stu-id="46471-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="46471-136">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="46471-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="46471-137">Izberite navpične tri pike poleg predvidevanja, ki ga želite osvežiti.</span><span class="sxs-lookup"><span data-stu-id="46471-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="46471-138">Izberite **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="46471-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="46471-139">Brisanje predvidevanja</span><span class="sxs-lookup"><span data-stu-id="46471-139">Delete a prediction</span></span>

<span data-ttu-id="46471-140">Če izbrišete predvidevanje, odstranite tudi njegovo izhodno entiteto.</span><span class="sxs-lookup"><span data-stu-id="46471-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="46471-141">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="46471-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="46471-142">Izberite navpične tri pike poleg predvidevanja, ki ga želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="46471-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="46471-143">Izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="46471-143">Select **Delete**.</span></span>
