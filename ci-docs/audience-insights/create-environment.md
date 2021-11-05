---
title: Ustvarjanje okolij v rešitvi Customer Insights
description: Koraki za ustvarjanje okolij z naročnino na storitev Dynamics 365 Customer Insights, za katero imate licenco.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673411"
---
# <a name="create-an-environment-in-audience-insights"></a>Ustvarite okolje v vpogledih v občinstvo

Ta članek pojasnjuje, kako ustvariti novo okolje, po tem ko je vaša organizacija kupila naročnino za Dynamics 365 Customer Insights. 

Organizacije lahko ustvarijo *dve* okolji za vsako licenco Customer Insights. Če vaša organizacija kupi več licenc, [se obrnite na našo ekipo za podporo](https://go.microsoft.com/fwlink/?linkid=2079641), da povečate število razpoložljivih okolij. Za več informacij o zmogljivostih in dodatnih zmogljivostih prenesite datoteko [Priročnik za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Če želite preizkusiti storitev, glejte razdelek [Nastavitev preizkusnega okolja](../trial-signup.md).

## <a name="create-a-new-environment"></a>Ustvarite novo okolje

Po nakupu naročniške licence za Customer Insights globalni skrbnik najemnika Microsoft 365 prejme e-poštno sporočilo, ki ga povabi k ustvarjanju okolja. Za začetek pojdite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Vodena izkušnja vam pomaga pri zbiranju vseh potrebnih informacij za novo okolje. Za ustvarjanje ali upravljanje okolij potrebujete [skrbniška dovoljenja](permissions.md) v vpogledih v občinstva.

1. V vpogledih v občinstvo odprite izbirnik okolja in izberite možnost **+ Novo**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Izberite izbirnik okolja.":::

1. Sledite vodenim izkušnjam, opisanim v naslednjih razdelkih.

### <a name="step-1-provide-environment-information"></a>1. korak: posredovanje informacij o okolju

V koraku **Osnovni podatki** izberite, ali želite ustvariti okolje od začetka ali [kopirati podatke iz drugega okolja](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Pogovorno okno za ustvarjanje novega okolja Customer Insights.":::

Navedite naslednje podrobnosti:
   - **Ime**: ime tega okolja. To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.
   - **Izberite svoje podjetje**: izberite primarno občinstvo za novo okolje. Sodelujete lahko s posameznimi potrošniki (prodaja strankam) ali [poslovnimi kupci](work-with-business-accounts.md) (podjetja podjetjem).
   - **Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje. Preizkusna okolja ne dovoljujejo načrtovanega osveževanja podatkov in so namenjena predhodni implementaciji in testiranju. Okolja peskovnika uporabljajo isto primarno občinstvo kot trenutno izbrano produkcijsko okolje.
   - **Območje**: območje, v katerem je storitev uvedena in gostovana.

### <a name="step-2-configure-data-storage"></a>2. korak: konfiguracija shranjevanja podatkov

V koraku **Shranjevanje podatkov** izberite, kam želite shraniti podatke iz vpogledov v občinstvo.

Na voljo imate dve možnosti: **Shramba storitve Customer Insights** (jezero podatkov Azure, ki ga upravlja ekipa za Customer Insights) in **Azure Data Lake Storage** (vaša lastna storitev Azure Data Lake Storage). Privzeto je izbrana možnost »Shramba za Customer Insights«.

:::image type="content" source="media/data-storage-environment.png" alt-text="Izberite Azure Data Lake Storage za shranjevanje podatkov o vpogledih v občinstvo.":::

S shranjevanjem podatkov v Azure Data Lake Storage se strinjate, da bodo podatki preneseni in shranjeni na ustrezni geografski lokaciji za ta račun za shrambo Azure. Ta lokacija se lahko razlikuje od mesta, kjer so shranjeni podatki storitve Dynamics 365 Customer Insights. Več o tem preberite v [Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

> [!NOTE]
> Storitev Customer Insights trenutno podpira naslednje:
> - Uvožene entitete iz podatkovnih tokov Power BI, ki so shranjeni v okolju Microsoft Dataverse, ki ga upravlja Data Lake.  
> - Računi Azure Data Lake Storage iz iste regije Azure, ki ste jo izbrali pri ustvarjanju okolja.
> - Računi Azure Data Lake Storage, ki imajo omogočen *hierarhičen imenski prostor*.

V sklopu možnosti Azure Data Lake Storage lahko za preverjanje pristnosti izberete možnost, ki temelji na virih, ali možnost, ki temelji na naročnini. Za več informacij glejte [Vzpostavitev povezave z računom Azure Data Lake Storage z glavnim imenom storitve Azure](connect-service-principal.md). Ime **vsebnika** bo `customerinsights` in ga ni mogoče spremeniti.

Ko so procesi sistema, na primer uvoz podatkov, končani, sistem ustvari ustrezne mape v računu za shrambo, ki ste ga določili. Ustvarijo se podatkovne datoteke in datoteke *model.json*, ki so na podlagi imena procesa dodane v mape.

Če ustvarite več okolij Customer Insights in se odločite shraniti izhodne entitete iz teh okolij v svoj račun za shrambo, storitev Customer Insights ustvari ločene mape za vsako okolje z lastnostjo `ci_environmentID` v vsebniku.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: vzpostavitev povezave z okoljem Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogoča, da povežete Customer Insights s svojim okoljem Dataverse.

Če želite uporabiti [pripravljene modele predvidevanja](predictions-overview.md#out-of-box-models), konfigurirajte skupno rabo podatkov z okoljem Dataverse. Ali pa omogočite uvoz podatkov iz virov podatkov na mestu uporabe, ki zagotavljajo URL za okolje Microsoft Dataverse, ki ga upravlja vaša organizacija. Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights z upravljanim jezerom podatkov Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.":::

> [!NOTE]
> Storitev Customer Insights ne podpira naslednjih primerov skupne rabe podatkov.
> - Če vse podatke shranite v svojo shrambo Azure Data Lake Storage, ne boste mogli omogočiti skupne rabe podatkov z upravljanim jezerom podatkov Dataverse.
> - Če omogočite skupno rabo podatkov s storitvijo Dataverse, ne boste mogli [ustvariti predvidenih ali manjkajočih vrednosti v entiteti](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4. korak: dokončanje nastavitev

V koraku **Pregled** pojdite skozi vse navedene nastavitve. Ko je vse videti dokončano, izberite možnost **Ustvari**, da nastavite okolje. 

Večino nastavitev lahko spremenite tudi pozneje. Za več informacij glejte [Upravljanje okolij](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Delajte z novim okoljem

Preglejte naslednje članke, ki vam bodo pomagali začeti s konfiguriranjem storitve Customer Insights: 

- [Dodajte več uporabnikov in dodelite dovoljenja](permissions.md).
- [Uvozite svoje vire podatkov](data-sources.md) in jih vodite skozi [postopek poenotenja podatkov](data-unification.md), da nastanejo [enotni profili strank](customer-profiles.md).
- [Obogatite poenotene profile strank](enrichment-hub.md) ali [zaženite modele predvidevanja](predictions-overview.md).
- [Ustvarite segmente](segments.md) za združevanje strank in [mere](measures.md) za pregled KPI-jev.
- [Nastavite povezave](connections.md) in [izvoz](export-destinations.md) za obdelavo podmnožic vaših podatkov v drugih aplikacijah.
