---
title: Izpolnite delne podatke z uporabo predvidevanj
description: Z predvidevanji izpolnite nepopolne podatke o strankah.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648731"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="cce75-103">Delne podatke dopolnite s predvidevanji</span><span class="sxs-lookup"><span data-stu-id="cce75-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cce75-104">Predvidevanja omogočajo preprosto ustvarjanje predvidenih vrednosti, ki okrepijo vaše razumevanje stranke.</span><span class="sxs-lookup"><span data-stu-id="cce75-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="cce75-105">Na strani **Obveščanje** > **Predvidevanja** lahko izberete **Moje napovedi**, da si ogledate predvidevanja, ki ste jih konfigurirali v drugih delih vpogledov v občinstvo , in jim omogočite nadaljnjo prilagoditev.</span><span class="sxs-lookup"><span data-stu-id="cce75-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="cce75-106">Te funkcije ne morete uporabljati, če vaše okolje uporablja prostor za shranjevanje Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="cce75-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="cce75-107">Funkcija predvidevanj uporablja avtomatizirana sredstva za ocenjevanje podatkov in pripravo predvidevanj na podlagi teh podatkov, torej ima zmogljivost za uporabo kot način profiliranja, kakor je izraz opredeljen v Splošni uredbi o varstvu podatkov (»GDPR«).</span><span class="sxs-lookup"><span data-stu-id="cce75-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="cce75-108">Za strankino uporabo te funkcije za obdelavo podatkov lahko velja GDPR ali drugi zakoni ali predpisi.</span><span class="sxs-lookup"><span data-stu-id="cce75-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="cce75-109">Sami ste odgovorni za to, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s predvidevanji, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.</span><span class="sxs-lookup"><span data-stu-id="cce75-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cce75-110">Zahteve</span><span class="sxs-lookup"><span data-stu-id="cce75-110">Prerequisites</span></span>

<span data-ttu-id="cce75-111">Preden lahko vaša organizacija uporablja funkcijo predvidevanj, morajo biti izpolnjeni naslednji predpogoji:</span><span class="sxs-lookup"><span data-stu-id="cce75-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="cce75-112">Vaša organizacija ima primerek [nastavljen v storitvi Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) in je v isti organizaciji kot Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cce75-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="cce75-113">Vaše okolje je vezano na vaš primerek Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cce75-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="cce75-114">Če [ustvarjate novo okolje](manage-environments.md), ga konfigurirajte v pogovornem oknu **Ustvarjanje okolja** in izberite **Napredno**.</span><span class="sxs-lookup"><span data-stu-id="cce75-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="cce75-115">Če ste okolje že ustvarili, odprite njegove nastavitve in izberite **Napredno**.</span><span class="sxs-lookup"><span data-stu-id="cce75-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="cce75-116">Kakorkoli že, v razdelku **Uporaba napovedi** vnesite URL primerka Common Data Service, na katerega želite pritrditi svoje okolje.</span><span class="sxs-lookup"><span data-stu-id="cce75-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="cce75-117">Ustvarjanje predvidevanja v entiteti stranke</span><span class="sxs-lookup"><span data-stu-id="cce75-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="cce75-118">Pri vpogledih v občinstvo izberite **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="cce75-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="cce75-119">Izberite entiteto **Stranka**.</span><span class="sxs-lookup"><span data-stu-id="cce75-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="cce75-120">V entiteti **Customer: CustomerInsights** izberite zavihek **Polja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="cce75-121">Poiščite ima atributa, za katerega želite napovedati vrednosti, nato izberite ikono **Pregled** v stolpcu **Povzetek**.</span><span class="sxs-lookup"><span data-stu-id="cce75-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cce75-122">![Ikona pregleda](media/intelligence-overviewicon.png "Ikona pregleda")</span><span class="sxs-lookup"><span data-stu-id="cce75-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="cce75-123">V primeru visoke stopnje manjkajočih vrednosti za atribut izberite **Predvidi manjkajoče vrednosti** za nadaljevanje s predvidevanjem.</span><span class="sxs-lookup"><span data-stu-id="cce75-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cce75-124">![Stanje pregleda s prikazanim gumbom za predvidevanje manjkajočih vrednosti](media/intelligence-overviewpredictmissingvalues.png "Stanje pregleda s prikazanim gumbom za predvidevanje manjkajočih vrednosti")</span><span class="sxs-lookup"><span data-stu-id="cce75-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="cce75-125">Zagotovite **Prikazno ime** in **Ime izhodne entitete** za rezultate predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="cce75-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="cce75-126">Prikazal se bo vnaprej izpolnjen seznam možnosti, kjer lahko preslikate vrednosti v predvideno kategorijo.</span><span class="sxs-lookup"><span data-stu-id="cce75-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="cce75-127">V tem primeru sta edini možnosti kategorije 0 ali 1, saj preslikava poteka na true/false ali binarno naravo predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="cce75-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="cce75-128">V stolpcu kategorije preslikajte vrednosti polj, za katera želite, da so razvrščena kot »0«, v končno predvidevanje na »0« in elemente, za katere želite, da so razvrščeni kot »1«, v končno predvidevanje na »1«.</span><span class="sxs-lookup"><span data-stu-id="cce75-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cce75-129">![Primer, ki prikazuje preslikane vrednosti polj v kategorije](media/intelligence-categorymapping.png "Primer, ki prikazuje preslikane vrednosti polj v kategorije")</span><span class="sxs-lookup"><span data-stu-id="cce75-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="cce75-130">Izberite **Dokončano** in predvidevanje bo obdelano.</span><span class="sxs-lookup"><span data-stu-id="cce75-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="cce75-131">Obdelava traja nekaj časa, odvisno od velikosti in zapletenosti podatkov.</span><span class="sxs-lookup"><span data-stu-id="cce75-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="cce75-132">Rezultati bodo na voljo v novi entiteti, ki temelji na možnosti **Ime izhodne entitete**, predvidevanja, ki ste ga ustvarili.</span><span class="sxs-lookup"><span data-stu-id="cce75-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="cce75-133">Ustvarjanje predvidevanja med ustvarjanjem segmenta</span><span class="sxs-lookup"><span data-stu-id="cce75-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="cce75-134">Predvidevanje manjkajočih vrednosti za določene atribute po izbiri je mogoče tudi pri ustvarjanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="cce75-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="cce75-135">Natančneje, ko hitro ustvarite segment na podlagi bodisi poenotene entitete stranke ali entitete Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="cce75-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="cce75-136">Kot del tega poteka izberete določen atribut, na katerem utemeljite segment, kot je zadovoljstvo strank ali znesek nakupa.</span><span class="sxs-lookup"><span data-stu-id="cce75-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="cce75-137">Ob ustvarjanju segmenta bo sistem predlagal način predvidevanja za vse manjkajoče vrednosti za ta atribut.</span><span class="sxs-lookup"><span data-stu-id="cce75-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="cce75-138">Pri vpogledih v občinstvo odprite **Segmenti** in izberite ploščico **Profili**.</span><span class="sxs-lookup"><span data-stu-id="cce75-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="cce75-139">Izberite **Polje**, v katerem ustvarite segment, in izberite **Operator**, nato izberite **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="cce75-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="cce75-140">Navedite **Ime** in **Prikazno ime** za segment.</span><span class="sxs-lookup"><span data-stu-id="cce75-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="cce75-141">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="cce75-141">Select **Save**.</span></span>

5. <span data-ttu-id="cce75-142">Če ima segment, ki ste ga ustvarili, manjkajoče podatke v izvornem polju, lahko izberete predvidevanje manjkajočih vrednosti.</span><span class="sxs-lookup"><span data-stu-id="cce75-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cce75-143">![Gumb za predvidevanje](media/segments-predictoption.png "Gumb za predvidevanje")</span><span class="sxs-lookup"><span data-stu-id="cce75-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="cce75-144">Zagotovite **Prikazno ime** in **Ime izhodne entitete** za rezultate predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="cce75-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="cce75-145">Izberite **Dokončano**.</span><span class="sxs-lookup"><span data-stu-id="cce75-145">Select **Done**.</span></span> <span data-ttu-id="cce75-146">Vaše predvidevanje bo kmalu ustvarjeno v novi entiteti z imenom, ki ste ga navedli za **Ime izhodne entitete**.</span><span class="sxs-lookup"><span data-stu-id="cce75-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="cce75-147">Ogled predvidevanja</span><span class="sxs-lookup"><span data-stu-id="cce75-147">View a prediction</span></span>

1. <span data-ttu-id="cce75-148">Pri vpogledih v občinstvo izberite **Obveščanje** > **Predvidevanja** > **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="cce75-149">Izberite predvidevanje, ki ga želite pregledati.</span><span class="sxs-lookup"><span data-stu-id="cce75-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="cce75-150">Izberite tri pike v stolpcu **Dejanja** in izberite **Pogled**.</span><span class="sxs-lookup"><span data-stu-id="cce75-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="cce75-151">Videli boste število podatkovnih točk v pogledu predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="cce75-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cce75-152">![Stran predvidevanj](media/intelligence-predictionsviewpage.png "Stran predvidevanj")</span><span class="sxs-lookup"><span data-stu-id="cce75-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="cce75-153">**Predvidene vrednosti** prikazuje preslikavo, ustvarjeno med fazo preslikave vrednosti polja v kategorijo.</span><span class="sxs-lookup"><span data-stu-id="cce75-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="cce75-154">To so vrednosti v naboru podatkov, ki so bile preslikane v določeno kategorijo.</span><span class="sxs-lookup"><span data-stu-id="cce75-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="cce75-155">-**Ključni dejavniki** so dejavniki v naboru podatkov, ki bodo najverjetneje vplivali na zanesljivost predvidevanja za vrednost polja, ki se preslika v določeno kategorijo.</span><span class="sxs-lookup"><span data-stu-id="cce75-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="cce75-156">**Uspešnost** označuje, kako potekajo predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="cce75-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="cce75-157">Za več informacij izberite povezavo.</span><span class="sxs-lookup"><span data-stu-id="cce75-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="cce75-158">**Predogled** prikazuje vzorce izhodnega nabora podatkov iz predvidevanj in verjetnost ali zanesljivost predvidene vrednosti, kjer je 0 negotovo in 1 je gotovo.</span><span class="sxs-lookup"><span data-stu-id="cce75-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="cce75-159">Posodobitev predvidevanja</span><span class="sxs-lookup"><span data-stu-id="cce75-159">Update a prediction</span></span>

1. <span data-ttu-id="cce75-160">Pri vpogledih v občinstvo izberite **Obveščanje** > **Predvidevanja** > **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="cce75-161">Izberite predvidevanje, ki ga želite posodobiti in izberite ikono **Posodobi**.</span><span class="sxs-lookup"><span data-stu-id="cce75-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="cce75-162">Predvidevanje bo razporejeno za obdelavo.</span><span class="sxs-lookup"><span data-stu-id="cce75-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="cce75-163">Čas zadnje posodobitve lahko vidite v stolpcu **Posodobljeno** na strani **Predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="cce75-164">Urejanje predvidevanja</span><span class="sxs-lookup"><span data-stu-id="cce75-164">Edit a prediction</span></span>

<span data-ttu-id="cce75-165">Ko ste ustvarili predvidevanja, lahko prilagodite model v orodju AI Builder, da povečate učinkovitost modela.</span><span class="sxs-lookup"><span data-stu-id="cce75-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="cce75-166">Pri vpogledih v občinstvo izberite **Obveščanje** > **Predvidevanja** > **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="cce75-167">Izberite predvidevanje, ki ga želite urediti.</span><span class="sxs-lookup"><span data-stu-id="cce75-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="cce75-168">Izberite tri pike v stolpcu **Dejanja** in izberite **Pogled**.</span><span class="sxs-lookup"><span data-stu-id="cce75-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="cce75-169">Izberite **Prilagajanje v orodju AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="cce75-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="cce75-170">Posodobite model v orodju AI Builder.</span><span class="sxs-lookup"><span data-stu-id="cce75-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="cce75-171">[Preberite več o upravljanju modelov v orodju AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="cce75-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="cce75-172">Ob naslednjem zagonu predvidevanja bo uporabljen ustvarjeni posodobljeni model.</span><span class="sxs-lookup"><span data-stu-id="cce75-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="cce75-173">Novi modeli, ustvarjeni v storitvi AI Builder, ne bodo prikazani pri vpogledih v občinstvo, razen če je bil model ustvarjen na podlagi zgoraj naštetih izkušenj.</span><span class="sxs-lookup"><span data-stu-id="cce75-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="cce75-174">Odstranjevanje predvidevanja</span><span class="sxs-lookup"><span data-stu-id="cce75-174">Remove a prediction</span></span>

1. <span data-ttu-id="cce75-175">Pri vpogledih v občinstvo izberite **Obveščanje** > **Predvidevanja** > **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="cce75-176">Izberite predvidevanje, ki ga želite izbrisati.</span><span class="sxs-lookup"><span data-stu-id="cce75-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="cce75-177">Izberite tri pike v stolpcu **Dejanja** in izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="cce75-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="cce75-178">Potrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="cce75-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cce75-179">Odpravljanje težav</span><span class="sxs-lookup"><span data-stu-id="cce75-179">Troubleshooting</span></span>

<span data-ttu-id="cce75-180">Če zaradi napake ne morete dokončati priloženega postopka Common Data Service, lahko poskusite postopek dokončati ročno.</span><span class="sxs-lookup"><span data-stu-id="cce75-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="cce75-181">V postopku prilaganja lahko pride do dveh znanih težav:</span><span class="sxs-lookup"><span data-stu-id="cce75-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="cce75-182">Rešitev dodatka za kartice stranke ni nameščena.</span><span class="sxs-lookup"><span data-stu-id="cce75-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="cce75-183">Opravite korake iz navodil za [namestitev in konfiguracijo rešitve](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="cce75-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="cce75-184">Dovoljenja za aplikacije niso podeljena.</span><span class="sxs-lookup"><span data-stu-id="cce75-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="cce75-185">Obiščite spletno mesto [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cce75-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="cce75-186">Izberite **Okolja**.</span><span class="sxs-lookup"><span data-stu-id="cce75-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="cce75-187">Izberite tri pike poleg okolja, ki mu želite dodati dovoljenje, in izberite **Nastavitve**.</span><span class="sxs-lookup"><span data-stu-id="cce75-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="cce75-188">Razširite možnost **Uporabniki in dovoljenja** ter izberite možnost **Uporabniki**.</span><span class="sxs-lookup"><span data-stu-id="cce75-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="cce75-189">Izberite možnost **+ Novo** in nato **Uporabnik**.</span><span class="sxs-lookup"><span data-stu-id="cce75-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="cce75-190">Če možnost **Uporabnik aplikacije** še ni izbrana, jo izberite in vnesite naslednje podatke:</span><span class="sxs-lookup"><span data-stu-id="cce75-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="cce75-191">**Uporabniško ime:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cce75-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="cce75-192">**ID aplikacije:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="cce75-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="cce75-193">**Ime:** stranka</span><span class="sxs-lookup"><span data-stu-id="cce75-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="cce75-194">**Priimek:** Insights</span><span class="sxs-lookup"><span data-stu-id="cce75-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="cce75-195">**Primarni e-poštni naslov:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cce75-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="cce75-196">Izberite **Shrani in zapri**.</span><span class="sxs-lookup"><span data-stu-id="cce75-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="cce75-197">Izberite uporabnika, ki ste ga pravkar ustvarili.</span><span class="sxs-lookup"><span data-stu-id="cce75-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="cce75-198">V zgornji vrstici menija izberite **Upravljanje vlog**.</span><span class="sxs-lookup"><span data-stu-id="cce75-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="cce75-199">Izberite **Skrbnik sistema**, nato pa **V redu**.</span><span class="sxs-lookup"><span data-stu-id="cce75-199">Select **System Administrator**, then select **OK**.</span></span>
