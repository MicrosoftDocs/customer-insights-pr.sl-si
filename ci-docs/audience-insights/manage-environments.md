---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270132"
---
# <a name="manage-environments"></a><span data-ttu-id="4b54c-103">Upravljanje okolij</span><span class="sxs-lookup"><span data-stu-id="4b54c-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4b54c-104">Ta članek pojasnjuje, kako ustvariti novo organizacijo in kako omogočiti uporabo okolja.</span><span class="sxs-lookup"><span data-stu-id="4b54c-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="4b54c-105">Prijavite se in ustvarite organizacijo</span><span class="sxs-lookup"><span data-stu-id="4b54c-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="4b54c-106">Pojdite na spletno mesto [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="4b54c-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="4b54c-107">Izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="4b54c-108">Izberite želeni scenarij prijave in ustrezno povezavo.</span><span class="sxs-lookup"><span data-stu-id="4b54c-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="4b54c-109">Sprejmite določila in pogoje in izberite **Nadaljuj**, da začnete ustvarjati organizacijo.</span><span class="sxs-lookup"><span data-stu-id="4b54c-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="4b54c-110">Ko je okolje ustvarjeno, boste preusmerjeni na storitev [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="4b54c-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="4b54c-111">Uporabite predstavitveno okolje za raziskovanje aplikacije ali pa ustvarite novo okolje po korakih, opisanih v naslednjem razdelku.</span><span class="sxs-lookup"><span data-stu-id="4b54c-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="4b54c-112">Ko določite nastavitve okolja, izberite **Ustvari**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="4b54c-113">Po uspešnem ustvarjanju okolja boste prijavljeni.</span><span class="sxs-lookup"><span data-stu-id="4b54c-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="4b54c-114">Ustvarite okolje v obstoječi organizaciji</span><span class="sxs-lookup"><span data-stu-id="4b54c-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="4b54c-115">Novo okolje lahko ustvarite na dva načina.</span><span class="sxs-lookup"><span data-stu-id="4b54c-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="4b54c-116">Lahko določite popolnoma novo konfiguracijo ali kopirate nekatere konfiguracijske nastavitve iz obstoječega okolja.</span><span class="sxs-lookup"><span data-stu-id="4b54c-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="4b54c-117">Če želite ustvariti okolje:</span><span class="sxs-lookup"><span data-stu-id="4b54c-117">To create an environment:</span></span>

1. <span data-ttu-id="4b54c-118">V glavi aplikacije izberite izbirnik **Okolje**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="4b54c-119">Izberite **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4b54c-120">![Nastavitve okolja](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="4b54c-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="4b54c-121">V pogovornem oknu **Ustvari novo okolje** izberite **Novo okolje**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="4b54c-122">Če želite [prekopirati podatke iz trenutnega okolja](#additional-considerations-for-copy-configuration-preview), izberite **Kopiraj iz obstoječega okolja**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="4b54c-123">Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.</span><span class="sxs-lookup"><span data-stu-id="4b54c-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="4b54c-124">Navedite naslednje podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="4b54c-124">Provide the following details:</span></span>
   - <span data-ttu-id="4b54c-125">**Ime**: ime tega okolja.</span><span class="sxs-lookup"><span data-stu-id="4b54c-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="4b54c-126">To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.</span><span class="sxs-lookup"><span data-stu-id="4b54c-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="4b54c-127">**Območje**: območje, v katerem je storitev uvedena in gostovana.</span><span class="sxs-lookup"><span data-stu-id="4b54c-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="4b54c-128">**Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje.</span><span class="sxs-lookup"><span data-stu-id="4b54c-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="4b54c-129">Če želite, lahko izberete **Napredne nastavitve**:</span><span class="sxs-lookup"><span data-stu-id="4b54c-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="4b54c-130">**Shrani vse podatke v**: določa, kam želite shraniti izhodne podatke, ustvarjene s storitvijo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4b54c-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="4b54c-131">Na voljo imate dve možnosti: **Shramba za Customer Insights** (shramba Azure Data Lake, ki jo upravlja ekipa za Customer Insights) in **Azure Data Lake Storage Gen2** (vaša shramba Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="4b54c-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="4b54c-132">Privzeto je izbrana možnost »Shramba za Customer Insights«.</span><span class="sxs-lookup"><span data-stu-id="4b54c-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4b54c-133">Če shranite podatke v Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4b54c-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="4b54c-134">Več o tem preberite v Microsoftovem središču zaupanja.</span><span class="sxs-lookup"><span data-stu-id="4b54c-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="4b54c-135">Trenutno se uvožene entitete vedno shranijo v shrambo Data Lake, ki jo upravlja aplikacija Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4b54c-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="4b54c-136">Podpiramo samo račune za shranjevanje Azure Data Lake Gen2 iz iste regije Azure, ki ste jo izbrali pri ustvarjanju okolja.</span><span class="sxs-lookup"><span data-stu-id="4b54c-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="4b54c-137">Podpiramo samo račune za shrambo z omogočenim hierarhičnim imenskim prostorom (HNS) shrambe Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="4b54c-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="4b54c-138">Za možnost Azure Data Lake Storage Gen2 lahko izbirate med možnostjo, ki temelji na viru, in možnostjo preverjanja pristnosti, ki temelji na naročnini.</span><span class="sxs-lookup"><span data-stu-id="4b54c-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="4b54c-139">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="4b54c-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="4b54c-140">Imena **Vsebnik** ni mogoče spremeniti in bo naslednji: customerinsights.</span><span class="sxs-lookup"><span data-stu-id="4b54c-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="4b54c-141">Če želite uporabiti [predvidevanja](predictions.md) ali konfigurirati skupno rabo podatkov z aplikacijami in rešitvami, ki temeljijo na storitvi Microsoft Dataverse, navedite URL okolja Microsoft Dataverse pod razdelkom **Konfigurirajte skupno rabo podatkov z Microsoft Dataverse in omogočite dodatne zmogljivosti**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="4b54c-142">Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights s storitvijo Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="4b54c-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="4b54c-143">Skupna raba podatkov s storitvijo Microsoft Dataverse Managed Data Lake trenutno ni podprta, če vse podatke shranjujete v shrambi Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="4b54c-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="4b54c-144">[Predvidevanje manjkajočih vrednosti v entiteti](predictions.md) trenutno ni podprto, če je omogočena skupna rabo podatkov s storitvijo Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="4b54c-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="4b54c-145">![Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="4b54c-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="4b54c-146">Ko zaženete postopke, na primer uvoz podatkov ali ustvarjanje segmenta, bodo v zgoraj navedenem računu za shranjevanje ustvarjene ustrezne mape.</span><span class="sxs-lookup"><span data-stu-id="4b54c-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="4b54c-147">Podatkovne datoteke in datoteke model.json bodo ustvarjene in dodane v zadevne podmape na podlagi procesa, ki ga izvajate.</span><span class="sxs-lookup"><span data-stu-id="4b54c-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="4b54c-148">Če ustvarite več okolij Customer Insights in izhodne entitete iz teh okolij shranite v svoj račun za shranjevanje, bodo za vsako okolje ustvarjene ločene mape, pri čemer bo v vsebniku ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="4b54c-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="4b54c-149">Dodatni premisleki glede konfiguracije kopiranja (predogled)</span><span class="sxs-lookup"><span data-stu-id="4b54c-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="4b54c-150">Kopirane so naslednje konfiguracijske nastavitve:</span><span class="sxs-lookup"><span data-stu-id="4b54c-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="4b54c-151">Konfiguracije funkcije</span><span class="sxs-lookup"><span data-stu-id="4b54c-151">Feature configurations</span></span>
- <span data-ttu-id="4b54c-152">Vključeni/uvoženi viri podatkov</span><span class="sxs-lookup"><span data-stu-id="4b54c-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="4b54c-153">Konfiguracija poenotenja podatkov (preslikava, ujemanje, spajanje)</span><span class="sxs-lookup"><span data-stu-id="4b54c-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="4b54c-154">Segmenti</span><span class="sxs-lookup"><span data-stu-id="4b54c-154">Segments</span></span>
- <span data-ttu-id="4b54c-155">Mere</span><span class="sxs-lookup"><span data-stu-id="4b54c-155">Measures</span></span>
- <span data-ttu-id="4b54c-156">Odnosi</span><span class="sxs-lookup"><span data-stu-id="4b54c-156">Relationships</span></span>
- <span data-ttu-id="4b54c-157">Dejavnosti</span><span class="sxs-lookup"><span data-stu-id="4b54c-157">Activities</span></span>
- <span data-ttu-id="4b54c-158">Kazalo za iskanje in filtre</span><span class="sxs-lookup"><span data-stu-id="4b54c-158">Search & filter Index</span></span>
- <span data-ttu-id="4b54c-159">Izvoz ciljev</span><span class="sxs-lookup"><span data-stu-id="4b54c-159">Export destinations</span></span>
- <span data-ttu-id="4b54c-160">Načrtovano osveževanje</span><span class="sxs-lookup"><span data-stu-id="4b54c-160">Scheduled refresh</span></span>
- <span data-ttu-id="4b54c-161">Obogatitve</span><span class="sxs-lookup"><span data-stu-id="4b54c-161">Enrichments</span></span>
- <span data-ttu-id="4b54c-162">Upravljanje modelov</span><span class="sxs-lookup"><span data-stu-id="4b54c-162">Model management</span></span>
- <span data-ttu-id="4b54c-163">Dodelitve vloge</span><span class="sxs-lookup"><span data-stu-id="4b54c-163">Role assignments</span></span>

<span data-ttu-id="4b54c-164">Naslednje nastavitve *niso* kopirane:</span><span class="sxs-lookup"><span data-stu-id="4b54c-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="4b54c-165">Profili strank</span><span class="sxs-lookup"><span data-stu-id="4b54c-165">Customer profiles.</span></span>
- <span data-ttu-id="4b54c-166">Poverilnice virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="4b54c-166">Data source credentials.</span></span> <span data-ttu-id="4b54c-167">Za vsak vir podatkov boste morali zagotoviti poverilnice in ročno osvežiti vire podatkov.</span><span class="sxs-lookup"><span data-stu-id="4b54c-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="4b54c-168">Viri podatkov iz mape Common Data Model in upravljanega jezera Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4b54c-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="4b54c-169">Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.</span><span class="sxs-lookup"><span data-stu-id="4b54c-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="4b54c-170">Ko kopirate okolje, boste videli potrditveno sporočilo, da je bilo ustvarjeno novo okolje.</span><span class="sxs-lookup"><span data-stu-id="4b54c-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="4b54c-171">Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="4b54c-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="4b54c-172">Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="4b54c-173">Uredite vire podatkov in vnesite poverilnice, da jih osvežite.</span><span class="sxs-lookup"><span data-stu-id="4b54c-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b54c-174">![Viri podatkov kopirani](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="4b54c-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="4b54c-175">Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="4b54c-176">Tukaj so na voljo nastavitve iz izvornega okolja.</span><span class="sxs-lookup"><span data-stu-id="4b54c-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="4b54c-177">Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.</span><span class="sxs-lookup"><span data-stu-id="4b54c-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="4b54c-178">Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.</span><span class="sxs-lookup"><span data-stu-id="4b54c-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="4b54c-179">Urejanje obstoječega okolja</span><span class="sxs-lookup"><span data-stu-id="4b54c-179">Edit an existing environment</span></span>

<span data-ttu-id="4b54c-180">Uredite lahko določene podatke obstoječih okolij.</span><span class="sxs-lookup"><span data-stu-id="4b54c-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="4b54c-181">V glavi aplikacije izberite izbirnik **Okolje**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="4b54c-182">Izberite ikono za **urejanje**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="4b54c-183">V polju **Uredi okolje** lahko posodobite **prikazno ime** okolja, vendar pa ne morete spremeniti **regije** ali **tipa**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="4b54c-184">Če je okolje konfigurirano za shranjevanje podatkov v shrambi Azure Data Lake Storage Gen2, lahko posodobite **ključ računa**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="4b54c-185">Vendar pa ne morete spremeniti možnosti **Ime računa** ali imena razdelka **Vsebnik**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="4b54c-186">Po želji lahko posodobitev opravite prek povezave na podlagi ključa kupca s povezavo, ki temelji na viru ali naročnini.</span><span class="sxs-lookup"><span data-stu-id="4b54c-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="4b54c-187">Po nadgradnji ne morete povrniti ključa kupca po posodobitvi.</span><span class="sxs-lookup"><span data-stu-id="4b54c-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="4b54c-188">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="4b54c-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="4b54c-189">Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="4b54c-190">Ponastavitev obstoječega okolja</span><span class="sxs-lookup"><span data-stu-id="4b54c-190">Reset an existing environment</span></span>

<span data-ttu-id="4b54c-191">Če želite izbrisati vse konfiguracije in odstraniti vključene podatke, lahko kot administrator okolje ponastavite v prazno stanje.</span><span class="sxs-lookup"><span data-stu-id="4b54c-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="4b54c-192">V glavi aplikacije izberite izbirnik **Okolje**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="4b54c-193">Izberite okolje, ki ga želite ponastaviti, in izberite tri pike **...**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="4b54c-194">Izberite možnost **Ponastavi**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="4b54c-195">Če želite potrditi brisanje, vnesite ime okolja in izberite **Ponastavi**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="4b54c-196">Izbris obstoječega okolja (na voljo samo za skrbnike)</span><span class="sxs-lookup"><span data-stu-id="4b54c-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="4b54c-197">Kot skrbnik lahko izbrišete okolja, katerih skrbnik ste.</span><span class="sxs-lookup"><span data-stu-id="4b54c-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="4b54c-198">V glavi aplikacije izberite izbirnik **Okolje**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="4b54c-199">Izberite okolje, ki ga želite ponastaviti, in izberite tri pike **...**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="4b54c-200">Izberite možnost **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="4b54c-201">Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="4b54c-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]