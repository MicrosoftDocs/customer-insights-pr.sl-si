---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644153"
---
# <a name="manage-environments"></a><span data-ttu-id="dedb0-103">Upravljanje okolij</span><span class="sxs-lookup"><span data-stu-id="dedb0-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="dedb0-104">Ta članek pojasnjuje, kako ustvariti novo organizacijo in kako omogočiti uporabo okolja.</span><span class="sxs-lookup"><span data-stu-id="dedb0-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="dedb0-105">Prijavite se in ustvarite organizacijo</span><span class="sxs-lookup"><span data-stu-id="dedb0-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="dedb0-106">Pojdite na spletno mesto [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="dedb0-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="dedb0-107">Izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="dedb0-108">Izberite želeni scenarij prijave in ustrezno povezavo.</span><span class="sxs-lookup"><span data-stu-id="dedb0-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="dedb0-109">Sprejmite določila in pogoje in izberite **Nadaljuj**, da začnete ustvarjati organizacijo.</span><span class="sxs-lookup"><span data-stu-id="dedb0-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="dedb0-110">Ko je okolje ustvarjeno, boste preusmerjeni na storitev [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="dedb0-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="dedb0-111">Uporabite predstavitveno okolje za raziskovanje aplikacije ali pa ustvarite novo okolje po korakih, opisanih v naslednjem razdelku.</span><span class="sxs-lookup"><span data-stu-id="dedb0-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="dedb0-112">Ko določite nastavitve okolja, izberite **Ustvari**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="dedb0-113">Po uspešnem ustvarjanju okolja boste prijavljeni.</span><span class="sxs-lookup"><span data-stu-id="dedb0-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="dedb0-114">Ustvarite okolje v obstoječi organizaciji</span><span class="sxs-lookup"><span data-stu-id="dedb0-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="dedb0-115">Novo okolje lahko ustvarite na dva načina.</span><span class="sxs-lookup"><span data-stu-id="dedb0-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="dedb0-116">Lahko določite popolnoma novo konfiguracijo ali kopirate nekatere konfiguracijske nastavitve iz obstoječega okolja.</span><span class="sxs-lookup"><span data-stu-id="dedb0-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="dedb0-117">Če želite ustvariti okolje:</span><span class="sxs-lookup"><span data-stu-id="dedb0-117">To create an environment:</span></span>

1. <span data-ttu-id="dedb0-118">Izberite simbol za **Nastavitve** v glavi aplikacije.</span><span class="sxs-lookup"><span data-stu-id="dedb0-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="dedb0-119">Izberite **Novo okolje**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dedb0-120">![Nastavitve okolja](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="dedb0-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="dedb0-121">V pogovornem oknu **Ustvari novo okolje** izberite **Novo okolje**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="dedb0-122">Če želite [prekopirati podatke iz trenutnega okolja](#additional-considerations-for-copy-configuration-preview), izberite **Kopiraj iz obstoječega okolja**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="dedb0-123">Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.</span><span class="sxs-lookup"><span data-stu-id="dedb0-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="dedb0-124">Navedite naslednje podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="dedb0-124">Provide the following details:</span></span>
   - <span data-ttu-id="dedb0-125">**Ime**: ime tega okolja.</span><span class="sxs-lookup"><span data-stu-id="dedb0-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="dedb0-126">To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.</span><span class="sxs-lookup"><span data-stu-id="dedb0-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="dedb0-127">**Območje**: območje, v katerem je storitev uvedena in gostovana.</span><span class="sxs-lookup"><span data-stu-id="dedb0-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="dedb0-128">**Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje.</span><span class="sxs-lookup"><span data-stu-id="dedb0-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="dedb0-129">Če želite, lahko izberete **Napredne nastavitve**:</span><span class="sxs-lookup"><span data-stu-id="dedb0-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="dedb0-130">**Shrani vse podatke v**: določa, kam želite shraniti izhodne podatke, ustvarjene s storitvijo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dedb0-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="dedb0-131">Na voljo imate dve možnosti: **Shramba za Customer Insights** (shramba Azure Data Lake, ki jo upravlja ekipa za Customer Insights) in **Azure Data Lake Storage Gen2** (vaša shramba Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="dedb0-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="dedb0-132">Privzeto je izbrana možnost »Shramba za Customer Insights«.</span><span class="sxs-lookup"><span data-stu-id="dedb0-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dedb0-133">Če shranite podatke v Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dedb0-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="dedb0-134">Več o tem preberite v Microsoftovem središču zaupanja.</span><span class="sxs-lookup"><span data-stu-id="dedb0-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="dedb0-135">Trenutno se uvožene entitete vedno shranijo v shrambo Data Lake, ki jo upravlja aplikacija Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dedb0-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="dedb0-136">Podpiramo samo račune za shranjevanje Azure Data Lake Gen2 iz iste regije Azure, ki ste jo izbrali pri ustvarjanju okolja.</span><span class="sxs-lookup"><span data-stu-id="dedb0-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="dedb0-137">Podpiramo samo račune za shrambo z omogočenim hierarhičnim imenskim prostorom (HNS) shrambe Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="dedb0-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="dedb0-138">Za možnost Azure Data Lake Storage Gen2 lahko izbirate med možnostjo, ki temelji na viru, in možnostjo preverjanja pristnosti, ki temelji na naročnini.</span><span class="sxs-lookup"><span data-stu-id="dedb0-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="dedb0-139">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="dedb0-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="dedb0-140">Imena **Vsebnik** ni mogoče spremeniti in bo naslednji: customerinsights.</span><span class="sxs-lookup"><span data-stu-id="dedb0-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="dedb0-141">Če želite uporabiti [predvidevanja](predictions.md), vnesite URL primerka za Common Data Service v polje **Naslov strežnika** pod možnostjo **Uporaba napovedi**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="dedb0-142">Ko zaženete postopke, na primer uvoz podatkov ali ustvarjanje segmenta, bodo v zgoraj navedenem računu za shranjevanje ustvarjene ustrezne mape.</span><span class="sxs-lookup"><span data-stu-id="dedb0-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="dedb0-143">Podatkovne datoteke in datoteke model.json bodo ustvarjene in dodane v zadevne podmape na podlagi procesa, ki ga izvajate.</span><span class="sxs-lookup"><span data-stu-id="dedb0-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="dedb0-144">Če ustvarite več okolij Customer Insights in izhodne entitete iz teh okolij shranite v svoj račun za shranjevanje, bodo za vsako okolje ustvarjene ločene mape, pri čemer bo v vsebniku ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="dedb0-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="dedb0-145">Dodatni premisleki glede konfiguracije kopiranja (predogled)</span><span class="sxs-lookup"><span data-stu-id="dedb0-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="dedb0-146">Kopirane so naslednje konfiguracijske nastavitve:</span><span class="sxs-lookup"><span data-stu-id="dedb0-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="dedb0-147">Konfiguracije funkcije</span><span class="sxs-lookup"><span data-stu-id="dedb0-147">Feature configurations</span></span>
- <span data-ttu-id="dedb0-148">Vneseni/uvoženi viri podatkov</span><span class="sxs-lookup"><span data-stu-id="dedb0-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="dedb0-149">Konfiguracija poenotenja podatkov (preslikava, ujemanje, spajanje)</span><span class="sxs-lookup"><span data-stu-id="dedb0-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="dedb0-150">Segmenti</span><span class="sxs-lookup"><span data-stu-id="dedb0-150">Segments</span></span>
- <span data-ttu-id="dedb0-151">Mere</span><span class="sxs-lookup"><span data-stu-id="dedb0-151">Measures</span></span>
- <span data-ttu-id="dedb0-152">Odnosi</span><span class="sxs-lookup"><span data-stu-id="dedb0-152">Relationships</span></span>
- <span data-ttu-id="dedb0-153">Dejavnosti</span><span class="sxs-lookup"><span data-stu-id="dedb0-153">Activities</span></span>
- <span data-ttu-id="dedb0-154">Kazalo za iskanje in filtre</span><span class="sxs-lookup"><span data-stu-id="dedb0-154">Search & filter Index</span></span>
- <span data-ttu-id="dedb0-155">Izvoz ciljev</span><span class="sxs-lookup"><span data-stu-id="dedb0-155">Export destinations</span></span>
- <span data-ttu-id="dedb0-156">Načrtovano osveževanje</span><span class="sxs-lookup"><span data-stu-id="dedb0-156">Scheduled refresh</span></span>
- <span data-ttu-id="dedb0-157">Obogatitve</span><span class="sxs-lookup"><span data-stu-id="dedb0-157">Enrichments</span></span>
- <span data-ttu-id="dedb0-158">Upravljanje modelov</span><span class="sxs-lookup"><span data-stu-id="dedb0-158">Model management</span></span>
- <span data-ttu-id="dedb0-159">Dodelitve vloge</span><span class="sxs-lookup"><span data-stu-id="dedb0-159">Role assignments</span></span>

<span data-ttu-id="dedb0-160">Naslednje nastavitve *niso* kopirane:</span><span class="sxs-lookup"><span data-stu-id="dedb0-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="dedb0-161">Profili strank</span><span class="sxs-lookup"><span data-stu-id="dedb0-161">Customer profiles.</span></span>
- <span data-ttu-id="dedb0-162">Poverilnice virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="dedb0-162">Data source credentials.</span></span> <span data-ttu-id="dedb0-163">Za vsak vir podatkov boste morali zagotoviti poverilnice in ročno osvežiti vire podatkov.</span><span class="sxs-lookup"><span data-stu-id="dedb0-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="dedb0-164">Viri podatkov iz mape Common Data Model in upravljanega jezera Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="dedb0-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="dedb0-165">Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.</span><span class="sxs-lookup"><span data-stu-id="dedb0-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="dedb0-166">Ko kopirate okolje, boste videli potrditveno sporočilo, da je bilo ustvarjeno novo okolje.</span><span class="sxs-lookup"><span data-stu-id="dedb0-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="dedb0-167">Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.</span><span class="sxs-lookup"><span data-stu-id="dedb0-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="dedb0-168">Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="dedb0-169">Uredite vire podatkov in vnesite poverilnice, da jih osvežite.</span><span class="sxs-lookup"><span data-stu-id="dedb0-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dedb0-170">![Viri podatkov kopirani](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="dedb0-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="dedb0-171">Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="dedb0-172">Tukaj so na voljo nastavitve iz izvornega okolja.</span><span class="sxs-lookup"><span data-stu-id="dedb0-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="dedb0-173">Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.</span><span class="sxs-lookup"><span data-stu-id="dedb0-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="dedb0-174">Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.</span><span class="sxs-lookup"><span data-stu-id="dedb0-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="dedb0-175">Urejanje obstoječega okolja</span><span class="sxs-lookup"><span data-stu-id="dedb0-175">Edit an existing environment</span></span>

<span data-ttu-id="dedb0-176">Uredite lahko določene podatke obstoječih okolij.</span><span class="sxs-lookup"><span data-stu-id="dedb0-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="dedb0-177">Odprite **Skrbnik** > **Sistem** > **O**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="dedb0-178">Izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-178">Select **Edit**.</span></span>

3. <span data-ttu-id="dedb0-179">Lahko posodobite možnost **Prikazno ime** okolja, vendar ne morete spremeniti možnosti **Območje** ali **Vrsta**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="dedb0-180">Če je okolje konfigurirano za shranjevanje podatkov v shrambi Azure Data Lake Storage Gen2, lahko posodobite **ključ računa**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="dedb0-181">Vendar pa ne morete spremeniti možnosti **Ime računa** ali imena razdelka **Vsebnik**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="dedb0-182">Po želji lahko posodobitev opravite prek povezave na podlagi ključa kupca s povezavo, ki temelji na viru ali naročnini.</span><span class="sxs-lookup"><span data-stu-id="dedb0-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="dedb0-183">Po nadgradnji ne morete povrniti ključa kupca po posodobitvi.</span><span class="sxs-lookup"><span data-stu-id="dedb0-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="dedb0-184">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="dedb0-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="dedb0-185">Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="dedb0-186">Ponastavitev obstoječega okolja</span><span class="sxs-lookup"><span data-stu-id="dedb0-186">Reset an existing environment</span></span>

<span data-ttu-id="dedb0-187">Če želite izbrisati vse konfiguracije in odstraniti uvožene podatke, lahko okolje ponastavite v prazno stanje.</span><span class="sxs-lookup"><span data-stu-id="dedb0-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="dedb0-188">Odprite **Skrbnik** > **Sistem** > **O**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="dedb0-189">Izberite **Ponastavi**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="dedb0-190">Če želite potrditi brisanje, vnesite ime okolja in izberite **Ponastavi**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="dedb0-191">Brisanje obstoječega okolja</span><span class="sxs-lookup"><span data-stu-id="dedb0-191">Delete an existing environment</span></span>

1. <span data-ttu-id="dedb0-192">Odprite **Skrbnik** > **Sistem** > **O**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="dedb0-193">Izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-193">Select **Delete**.</span></span>

1. <span data-ttu-id="dedb0-194">Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="dedb0-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
