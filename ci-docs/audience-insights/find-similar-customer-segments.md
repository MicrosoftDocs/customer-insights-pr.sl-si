---
title: Poišči podobne stranke z umetno inteligenco
description: Poiščite podobne segmente strank z umetno inteligenco.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596795"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="406b7-103">Podobne stranke (predogled)</span><span class="sxs-lookup"><span data-stu-id="406b7-103">Similar Customers (preview)</span></span>

<span data-ttu-id="406b7-104">Ta funkcija vam omogoča, da z uporabo umetne inteligence v mreži strank najdete podobne stranke.</span><span class="sxs-lookup"><span data-stu-id="406b7-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="406b7-105">Za uporabo te funkcije morate ustvariti vsaj en segment.</span><span class="sxs-lookup"><span data-stu-id="406b7-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="406b7-106">Razširjanje meril obstoječega segmenta pomaga najti stranke, ki so podobne temu segmentu.</span><span class="sxs-lookup"><span data-stu-id="406b7-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="406b7-107">Storitev *Poiščite podobne stranke* uporablja avtomatizirana sredstva za ocenjevanje podatkov in delanje prognoze na podlagi teh podatkov, zato se lahko uporabi kot metoda profiliranja, saj je ta izraz opredeljen v Splošni uredbi o varstvu podatkov ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="406b7-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="406b7-108">Za strankino uporabo te funkcije za obdelavo podatkov lahko velja GDPR ali drugi zakoni ali predpisi.</span><span class="sxs-lookup"><span data-stu-id="406b7-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="406b7-109">Sami ste odgovorni za to, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s predvidevanji, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.</span><span class="sxs-lookup"><span data-stu-id="406b7-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="406b7-110">Iskanje podobnih strank</span><span class="sxs-lookup"><span data-stu-id="406b7-110">Finding similar customers</span></span>

1. <span data-ttu-id="406b7-111">V razdelku vpogledov v občinstvo odprite možnost **Segmenti** in izberite segment, na katerem želite, da temelji vaš novi segment.</span><span class="sxs-lookup"><span data-stu-id="406b7-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="406b7-112">To je *izvorni segment*.</span><span class="sxs-lookup"><span data-stu-id="406b7-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="406b7-113">V vrstici z dejanji izberite **Poišči podobne stranke**.</span><span class="sxs-lookup"><span data-stu-id="406b7-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="406b7-114">Preglejte predlagano ime za novi segment in ga po potrebi spremenite.</span><span class="sxs-lookup"><span data-stu-id="406b7-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="406b7-115">Preglejte polja, ki opredeljujejo novi segment.</span><span class="sxs-lookup"><span data-stu-id="406b7-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="406b7-116">Ta polja določajo osnovo, na kateri bo sistem skušal najti podobne kupce kot v vašem izvornem segmentu.</span><span class="sxs-lookup"><span data-stu-id="406b7-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="406b7-117">Sistem bo privzeto izbral priporočena polja.</span><span class="sxs-lookup"><span data-stu-id="406b7-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="406b7-118">Polja, ki lahko znatno zmanjšajo zmogljivost modela, so samodejno izključena:</span><span class="sxs-lookup"><span data-stu-id="406b7-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="406b7-119">Polja z naslednjimi vrstami podatkov: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="406b7-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="406b7-120">Polja s kardinalnostjo (število elementov v polju) manjšo od 2 ali večjo kot 30</span><span class="sxs-lookup"><span data-stu-id="406b7-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="406b7-121">Odločite se, če želite v novi segment vključiti **Vse stranke** ali samo stranke v **Specifičnem obstoječem segmentu**.</span><span class="sxs-lookup"><span data-stu-id="406b7-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="406b7-122">Izključite stranke v izvornem segmentu tako, da izberete potrditveno polje **Izključite vse v izvornem segmentu**.</span><span class="sxs-lookup"><span data-stu-id="406b7-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="406b7-123">Sistem privzeto predlaga, da v svoj izhod vključite le 20 % velikosti ciljnega občinstva.</span><span class="sxs-lookup"><span data-stu-id="406b7-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="406b7-124">Ta prag uredite po potrebi.</span><span class="sxs-lookup"><span data-stu-id="406b7-124">Edit this threshold as needed.</span></span> <span data-ttu-id="406b7-125">Zvišanje praga bo zmanjšalo natančnost.</span><span class="sxs-lookup"><span data-stu-id="406b7-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="406b7-126">Izberite **Zaženi** na dnu strani, da začnete opravilo dvojiške razvrstitve (metoda strojnega učenja), ki analizira nabor podatkov.</span><span class="sxs-lookup"><span data-stu-id="406b7-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="406b7-127">Oglejte si podoben segment</span><span class="sxs-lookup"><span data-stu-id="406b7-127">View the similar segment</span></span>

<span data-ttu-id="406b7-128">Po obdelavi podobnega segmenta boste novi segment našli na seznamu na strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="406b7-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="406b7-129">![Segment podobnih strank](media/expanded-segment.png "Segment podobnih strank")</span><span class="sxs-lookup"><span data-stu-id="406b7-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="406b7-130">V delovni vrstici izberite **Pogled**, da odprete podrobnosti o segmentu.</span><span class="sxs-lookup"><span data-stu-id="406b7-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="406b7-131">Ta pogled vsebuje informacije o porazdelitvi rezultatov v [ocenah podobnosti](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="406b7-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="406b7-132">Vrednosti ocen podobnosti boste našli tudi v **Predogledu članov segmenta**.</span><span class="sxs-lookup"><span data-stu-id="406b7-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="406b7-133">Uporabite izhod podobnega segmenta</span><span class="sxs-lookup"><span data-stu-id="406b7-133">Use the output of a similar segment</span></span>

<span data-ttu-id="406b7-134">Delate lahko [z izhodom podobnega segmenta](segments.md), tako kot pri drugih segmentih.</span><span class="sxs-lookup"><span data-stu-id="406b7-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="406b7-135">Na primer: izvozite segment ali sestavite mero.</span><span class="sxs-lookup"><span data-stu-id="406b7-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="406b7-136">Osvežite in uredite podoben segment</span><span class="sxs-lookup"><span data-stu-id="406b7-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="406b7-137">Če želite osvežiti podoben segment, ga izberite na strani **Segmenti** in izberite **Osveži** v vrstici z dejanji.</span><span class="sxs-lookup"><span data-stu-id="406b7-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="406b7-138">Če uredite podoben segment, bodo podatki ponovno obdelani.</span><span class="sxs-lookup"><span data-stu-id="406b7-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="406b7-139">Prejšnji ustvarjeni segment se posodobi z osveženimi podatki.</span><span class="sxs-lookup"><span data-stu-id="406b7-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="406b7-140">Če želite urediti podoben segment, ga izberite na strani **Segmenti** in izberite **Uredi** v vrstici z dejanji.</span><span class="sxs-lookup"><span data-stu-id="406b7-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="406b7-141">Uporabite spremembe in izberite **Zaženi** za začetek obdelave.</span><span class="sxs-lookup"><span data-stu-id="406b7-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="406b7-142">Izbrišite podoben segment</span><span class="sxs-lookup"><span data-stu-id="406b7-142">Delete a similar segment</span></span>

<span data-ttu-id="406b7-143">Izberite segment na strani **Segmenti** in izberite **Izbriši** v vrstici z dejanji.</span><span class="sxs-lookup"><span data-stu-id="406b7-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="406b7-144">Nato potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="406b7-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="406b7-145">O ocenah podobnosti</span><span class="sxs-lookup"><span data-stu-id="406b7-145">About similarity scores</span></span>

<span data-ttu-id="406b7-146">Dvojiška razvrstitev modela strojnega učenja dodeli oceno strankam v podobnem segmentu.</span><span class="sxs-lookup"><span data-stu-id="406b7-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="406b7-147">Rezultat temelji na podobnosti s strankami v izvornem segmentu.</span><span class="sxs-lookup"><span data-stu-id="406b7-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="406b7-148">Ocene podobnosti pod 0,55 so kupci, ki jih sistem uvršča kot *ni podobno* strankam v izvornem segmentu</span><span class="sxs-lookup"><span data-stu-id="406b7-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="406b7-149">Ocene podobnosti med 0,55 – 0,7 so razvrščene kot *nekoliko podobno*</span><span class="sxs-lookup"><span data-stu-id="406b7-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="406b7-150">Ocene podobnosti med 0,7 – 0,85 so razvrščene kot *podobno*</span><span class="sxs-lookup"><span data-stu-id="406b7-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="406b7-151">Ocene podobnosti med 0,85 – 1 so stranke, ki jih sistem uvršča kot *zelo podobno*</span><span class="sxs-lookup"><span data-stu-id="406b7-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="406b7-152">Stranke z ocenami podobnosti pod 0,4 niso vključeni v izhod modela.</span><span class="sxs-lookup"><span data-stu-id="406b7-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="406b7-153">Sistem jih ne zaznava kot dovolj podobne izvornemu segmentu.</span><span class="sxs-lookup"><span data-stu-id="406b7-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]