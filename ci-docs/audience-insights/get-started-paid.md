---
title: Ustvarite in konfigurirajte plačljivo licenco za Customer Insights
description: Koraki za pridobitev licenčne naročnine za Dynamics 365 Customer Insights in njeno konfiguracijo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034472"
---
# <a name="get-started-with-a-paid-subscription"></a>Kako začeti s plačljivo naročnino

Ta članek pojasnjuje, kako ustvariti novo okolje, po tem ko je vaša organizacija kupila naročnino za Dynamics 365 Customer Insights. Če želite kupiti Customer Insights, za naše možnosti kontakta pojdite na [spletno mesto Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Če želite preizkusiti storitev in funkcije, glejte [Nastavitev preskusnega okolja](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Ustvarite okolje v obstoječi organizaciji

Po nakupu naročniške licence za Customer Insights globalni skrbnik najemnika Microsoft 365 prejme e-poštno sporočilo, ki ga povabi k ustvarjanju okolja. Za začetek pojdite na [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

Customer Insights ni licenciran za vsakega uporabnika, zato se ne prikaže na seznamu licenc. Če iščete licenco v skrbniškem središču za Microsoft 365, pojdite na **Vaši izdelki**. 

> [!NOTE]
> Organizacije lahko ustvarijo *dve* okolji za vsako licenco Customer Insights. Če vaša organizacija kupi več kot eno licenco, [se obrnite na našo skupino za podporo](https://go.microsoft.com/fwlink/?linkid=2079641), da vam poveča število razpoložljivih okolij. Za več informacij o zmogljivostih in dodatnih zmogljivostih prenesite datoteko [Priročnik za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Če želite ustvariti okolje:

1. V pogovornem oknu **Ustvari okolje** izberite **Novo okolje**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Pogovorno okno za ustvarjanje novega okolja Customer Insights.":::

   Priporočamo, da pri ustvarjanju okolja začnete od začetka. Če ste skrbnik ali član preskusnega okolja, bi lahko uporabili [kopiranje podatkov iz drugega okolja](manage-environments.md#copy-the-environment-configuration), z možnostjo **Kopiraj iz obstoječega okolja**. Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.

1. Navedite naslednje podrobnosti:
   - **Ime**: ime tega okolja. To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.
   - **Območje**: območje, v katerem je storitev uvedena in gostovana.
   - **Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje. Preizkusna okolja ne dovoljujejo načrtovanega osveževanja podatkov in so namenjena predhodni implementaciji in testiranju.
   
1. Če želite, lahko izberete **Napredne nastavitve**:

   - **Shrani vse podatke v**: določa, kam želite shraniti izhodne podatke, ustvarjene s storitvijo Customer Insights. Na voljo imate dve možnosti: **Shramba storitve Customer Insights** (storitev Azure Data Lake, ki jo upravlja ekipa za Customer Insights) in **Azure Data Lake Storage** (vaša lastna storitev Azure Data Lake Storage). Privzeto je izbrana možnost »Shramba za Customer Insights«.

     > [!NOTE]
     > Če shranite podatke v Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)
     >
     > Trenutno se uvožene entitete iz podatkovnih tokov Power BI shranjujejo v shrambo Data Lake, ki jo upravlja Microsoft Dataverse. 
     > 
     > Podpiramo samo račune Azure Data Lake Storage iz tiste regije v storitvi Azure, ki ste jo izbrali pri ustvarjanju okolja. 
     > 
     > Podpiramo samo račune Azure Data Lake Storage z omogočenim hierarhičnim imenskim prostorom.


   - V sklopu možnosti Azure Data Lake Storage lahko za preverjanje pristnosti izberete možnost, ki temelji na virih, ali možnost, ki temelji na naročnini. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Imena **Zabojnika** ni mogoče spremeniti in ostaja `customerinsights`.
   
   - Če vas zanimajo [v naprej pripravljeni modeli](predictions-overview.md#out-of-box-models), konfigurirajte skupno rabo podatkov z Microsoft Dataverse ali omogočite uvoz podatkov iz virov podatkov na mestu uporabe, navedite URL okolja Microsoft Dataverse pod **Konfiguriraj skupno rabo podatkov z Microsoft Dataverse in omogoči dodatne zmogljivosti**. Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights s storitvijo Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Skupna raba podatkov s storitvijo Microsoft Dataverse Managed Data Lake trenutno ni podprta, če vse podatke shranjujete v shrambi Azure Data Lake Storage.
     > - [Predvidevanje manjkajočih vrednosti v entiteti](predictions.md) trenutno ni podprto, ko omogočite izmenjavo podatkov s storitvijo Microsoft Dataverse Managed Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.":::

   Ko so končani sistemski procesi, kot je uvoz podatkov, sistem ustvari ustrezne mape v računu za shrambo, ki ste ga določili. Ustvarijo se podatkovne datoteke in datoteke model.json, ki so na podlagi imena procesa dodane v mape.

   Če ustvarite več okolij Customer Insights in izhodne entitete iz teh okolij shranite v svoj račun za shranjevanje, bodo za vsako okolje ustvarjene ločene mape, pri čemer bo v vsebniku ci_<environmentid>.

1. Izberite **Ustvari**, da nastavite okolje. 

## <a name="configure-an-environment"></a>Konfiguriranje okolja

Oglejte si naslednje članke, ki vam bodo pomagali začeti s konfiguracijo Customer Insights. 

- [Dodajte več uporabnikov in dodelite dovoljenja](permissions.md).
- [Uvozite svoje vire podatkov](data-sources.md) in jih vodite skozi [postopek poenotenja podatkov](data-unification.md), da nastanejo [enotni profili strank](customer-profiles.md).
- [Obogatite poenotene profile strank](enrichment-hub.md) ali [zaženite modele predvidevanja](predictions-overview.md).
- S [segmenti](segments.md) lahko združujete stranke, z [ukrepi](measures.md) pa pregledate KPI-je.
- Nastavite [povezave](connections.md) in [izvoz](export-destinations.md) za obdelavo podmnožic vaših podatkov v drugih aplikacijah.
