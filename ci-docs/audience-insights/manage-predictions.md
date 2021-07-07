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
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315898"
---
# <a name="manage-predictions"></a><span data-ttu-id="33532-103">Upravljanje predvidevanj</span><span class="sxs-lookup"><span data-stu-id="33532-103">Manage predictions</span></span>

<span data-ttu-id="33532-104">Ta članek obravnava nekatere naloge, ki so skupne večini scenarijev predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="33532-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="33532-105">Odpravite težave z neuspešnim predvidevanjem</span><span class="sxs-lookup"><span data-stu-id="33532-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="33532-106">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="33532-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="33532-107">Izberite navpične tri pike poleg predvidevanja, za katere si želite ogledati dnevnike napak.</span><span class="sxs-lookup"><span data-stu-id="33532-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="33532-108">Izberite **Dnevniki**.</span><span class="sxs-lookup"><span data-stu-id="33532-108">Select **Logs**.</span></span>

1. <span data-ttu-id="33532-109">Preglejte vse napake.</span><span class="sxs-lookup"><span data-stu-id="33532-109">Review all the errors.</span></span> <span data-ttu-id="33532-110">Pride lahko do več vrst napak, ki opisujejo, kakšno stanje je povzročilo napako.</span><span class="sxs-lookup"><span data-stu-id="33532-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="33532-111">Primer: napaka, za katero ni dovolj podatkov za natančno predvidevanje, se običajno odpravi z nalaganjem dodatnih podatkov v storitev Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33532-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="33532-112">Poročilo o uporabnosti vhodnih podatkov</span><span class="sxs-lookup"><span data-stu-id="33532-112">Input data usability report</span></span>

<span data-ttu-id="33532-113">Poročilo o uporabnosti vhodnih podatkov ponuja strnjen prikaz napak in opozoril, ki jih lahko ustvarijo vaše vnaprej pripravljene napovedi.</span><span class="sxs-lookup"><span data-stu-id="33532-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="33532-114">Prav tako daje priporočila, kako izboljšati zmogljivost modela.</span><span class="sxs-lookup"><span data-stu-id="33532-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="33532-115">Poročilo je na voljo, ko model zaključi s postopkom kvalificiranja.</span><span class="sxs-lookup"><span data-stu-id="33532-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="33532-116">Ustvarjeno je za vsak model posebej, ne glede na to, ali je bilo uspešno zaključeno ali ne.</span><span class="sxs-lookup"><span data-stu-id="33532-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="33532-117">Ogled poročila o uporabnosti vhodnih podatkov</span><span class="sxs-lookup"><span data-stu-id="33532-117">View the input data usability report</span></span>

<span data-ttu-id="33532-118">Ko vnaprej pripravljen model zaključi korak za kvalificiranje, si oglejte poročilo:</span><span class="sxs-lookup"><span data-stu-id="33532-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="33532-119">Izberite tri pike poleg imena modela in izberite **Poročilo o uporabnosti vhodnih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="33532-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="33532-120">Izberite stanje modela in nato v stranskem podoknu kliknite **Ogled poročila o uporabnosti vhodnih podatkov**.</span><span class="sxs-lookup"><span data-stu-id="33532-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="33532-121">Izberite enega od modelov na seznamu in izberite **Poročilo o uporabnosti vhodnih podatkov** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="33532-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="33532-122">Odprite stran z rezultati modela in nato **Poročilo o uporabnosti vhodnih podatkov** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="33532-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="33532-123">Podatki v poročilu o uporabnosti vhodnih podatkov</span><span class="sxs-lookup"><span data-stu-id="33532-123">Information in the input data usability report</span></span>

<span data-ttu-id="33532-124">Naslednji stolpci poročila vsebujejo koristne informacije za izboljšanje podatkov za model.</span><span class="sxs-lookup"><span data-stu-id="33532-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer poročila o uporabnosti vhodnih podatkov, ki prikazuje tabelo z napakami, opozorili in priporočili.":::

- <span data-ttu-id="33532-126">Ime: opisno ime napake, opozorila ali priporočila.</span><span class="sxs-lookup"><span data-stu-id="33532-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="33532-127">Korak: faza modela, kvalificiranje ali rezultat, na katerega se informacije nanašajo.</span><span class="sxs-lookup"><span data-stu-id="33532-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="33532-128">Stanje: resnost informacij (napaka, opozorilo, priporočilo).</span><span class="sxs-lookup"><span data-stu-id="33532-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="33532-129">Ime stolpca: stolpec v entiteti, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.</span><span class="sxs-lookup"><span data-stu-id="33532-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="33532-130">Ime entitete: ime entitete, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.</span><span class="sxs-lookup"><span data-stu-id="33532-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="33532-131">Podrobnosti: podrobnosti o napaki, opozorilu ali priporočilu.</span><span class="sxs-lookup"><span data-stu-id="33532-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="33532-132">Osveževanje predvidevanja</span><span class="sxs-lookup"><span data-stu-id="33532-132">Refresh a prediction</span></span>

<span data-ttu-id="33532-133">Predvidevanja se bodo samodejno osvežila v istem [urniku, kot ga osvežijo vaši podatki](system.md#schedule-tab), ko se konfigurirajo v nastavitvah.</span><span class="sxs-lookup"><span data-stu-id="33532-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="33532-134">Lahko jih osvežite tudi ročno.</span><span class="sxs-lookup"><span data-stu-id="33532-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="33532-135">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="33532-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="33532-136">Izberite navpične tri pike poleg predvidevanja, ki ga želite osvežiti.</span><span class="sxs-lookup"><span data-stu-id="33532-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="33532-137">Izberite **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="33532-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="33532-138">Brisanje predvidevanja</span><span class="sxs-lookup"><span data-stu-id="33532-138">Delete a prediction</span></span>

<span data-ttu-id="33532-139">Če izbrišete predvidevanje, odstranite tudi njegovo izhodno entiteto.</span><span class="sxs-lookup"><span data-stu-id="33532-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="33532-140">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="33532-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="33532-141">Izberite navpične tri pike poleg predvidevanja, ki ga želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="33532-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="33532-142">Izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="33532-142">Select **Delete**.</span></span>
