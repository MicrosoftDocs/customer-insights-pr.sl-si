---
title: Ustvarjanje okolij v rešitvi Customer Insights
description: Koraki za ustvarjanje okolij z naročnino na storitev Dynamics 365 Customer Insights, za katero imate licenco.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712922"
---
# <a name="create-an-environment-in-customer-insights"></a>Ustvarite okolje v Customer Insights

Ta članek pojasnjuje, kako ustvariti novo okolje, po tem ko je vaša organizacija kupila naročnino za Dynamics 365 Customer Insights. 

Organizacije lahko ustvarijo več okolij za vsako licenco Customer Insights. Če vaša organizacija kupi več licenc, [se obrnite na našo ekipo za podporo](https://go.microsoft.com/fwlink/?linkid=2079641), da povečate število razpoložljivih okolij. Za več informacij o zmogljivosti in dodatni zmogljivosti si oglejte [Vodnik za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Če želite preizkusiti storitev, glejte razdelek [Nastavitev preizkusnega okolja](trial-signup.md).

## <a name="create-a-new-environment"></a>Ustvarite novo okolje

Po nakupu naročniške licence za Customer Insights, globalni skrbnik spletnega mesta Microsoft 365 najemnik prejme e-pošto, ki ga vabi k ustvarjanju okolja. Za začetek pojdite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Vodena izkušnja vam pomaga pri zbiranju vseh potrebnih informacij za novo okolje. Potrebujete [skrbniška dovoljenja](permissions.md) v Customer Insights za ustvarjanje ali upravljanje okolij.

1. Odprite izbirnik okolja in izberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Izberite izbirnik okolja.":::

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

V **Shranjevanje podatkov** korak, izberite, kam želite shraniti podatke Customer Insights.

Na voljo imate dve možnosti: **Shramba storitve Customer Insights** (jezero podatkov Azure, ki ga upravlja ekipa za Customer Insights) in **Azure Data Lake Storage** (vaša lastna storitev Azure Data Lake Storage). Privzeto je izbrana možnost »Shramba za Customer Insights«.

:::image type="content" source="media/data-storage-environment.png" alt-text="Izberite Azure Data Lake Storage za shranjevanje vaših podatkov.":::

S shranjevanjem podatkov v Azure Data Lake Storage se strinjate, da bodo podatki preneseni in shranjeni na ustrezni geografski lokaciji za ta račun za shrambo Azure. Ta lokacija se lahko razlikuje od mesta, kjer so shranjeni podatki storitve Dynamics 365 Customer Insights. Več o tem preberite v [Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

> [!NOTE]
> Storitev Customer Insights trenutno podpira naslednje:  
> - Računi Azure Data Lake Storage iz iste regije Azure, ki ste jo izbrali pri ustvarjanju okolja.
> - Azure Data Lake Storage račune, ki so Gen2 in imajo *hierarhičen imenski prostor* omogočeno. Računi za shranjevanje podatkov Azure Data Lake Gen1 niso podprti.

V sklopu možnosti Azure Data Lake Storage lahko za preverjanje pristnosti izberete možnost, ki temelji na virih, ali možnost, ki temelji na naročnini. Za več informacij glejte [Vzpostavitev povezave z računom Azure Data Lake Storage z glavnim imenom storitve Azure](connect-service-principal.md). Posoda z imenom`customerinsights` mora obstajati na računu za shranjevanje.

Ko so procesi sistema, na primer uvoz podatkov, končani, sistem ustvari ustrezne mape v računu za shrambo, ki ste ga določili. Ustvarijo se podatkovne datoteke in datoteke *model.json*, ki so na podlagi imena procesa dodane v mape.

Če ustvarite več okolij Customer Insights in se odločite shraniti izhodne entitete iz teh okolij v svoj račun za shrambo, storitev Customer Insights ustvari ločene mape za vsako okolje z lastnostjo `ci_environmentID` v vsebniku.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: vzpostavitev povezave z okoljem Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogoča, da povežete Customer Insights s svojim okoljem Dataverse.

Ponudite svoje Microsoft Dataverse okolje za izmenjavo podatkov (profilov in vpogledov) s poslovnimi aplikacijami, ki temeljijo na Dataverse, kot je Dynamics 365 Marketing ali modelsko vodene aplikacije v Power Apps. Pustite to polje prazno, če nimate svojega Dataverse okolje in mi ga bomo zagotovili za vas.

Povezovanje z vašim Dataverse okolje vam tudi omogoča [prenesite podatke iz virov podatkov na mestu uporabe z uporabo Power Platform podatkovni tokovi in prehodi](data-sources.md#add-data-from-on-premises-data-sources).

> [!IMPORTANT]
> 1. Vpogled v stranke in Dataverse morajo biti v isti regiji, da omogočite skupno rabo podatkov.
> 1. Imeti morate vlogo globalnega skrbnika v Dataverse okolje. Preverite, če je to [Dataverse okolje je povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) v določene varnostne skupine in se prepričajte, da ste dodani v te varnostne skupine.
> 1. Nobeno obstoječe okolje Customer Insights ni že povezano s tem Dataverse okolje. Naučite se [odstranite obstoječo povezavo z a Dataverse okolje](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podatkov z Microsoft Dataverse samodejno omogočeno za neto nove primerke.":::

Za več informacij o omogočanju skupne rabe podatkov z Microsoft Dataverse od svojega Azure Data Lake Storage, glej [Poveži z Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Storitev Customer Insights ne podpira naslednjih primerov skupne rabe podatkov.
- Če omogočite skupno rabo podatkov s storitvijo Dataverse, ne boste mogli [ustvariti predvidenih ali manjkajočih vrednosti v entiteti](predictions.md).

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
