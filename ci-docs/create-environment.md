---
title: Kako - Ustvarite novo okolje
description: Koraki za ustvarjanje okolij z za Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 795eaa3598257f5188070f6ea02d04e4423b66eb
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833604"
---
# <a name="how-to-create-a-new-environment"></a>Kako: ustvariti novo okolje

Po [nakup naročniške licence za Dynamics 365 Customer Insights](paid-license.md), globalni skrbnik Microsoft 365 najemnik prejme e-pošto, ki ga vabi k ustvarjanju okolja. Za začetek pojdite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). V tem scenariju lahko greste neposredno na [1. korak: Navedite osnovne informacije](#step-1-provide-basic-information).

Ko je prvo okolje ustvarjeno, globalni skrbnik za Microsoft 365 najemnik lahko [dodaj uporabnike iz svoje organizacije kot skrbnike](permissions.md). V prihodnje lahko ti skrbniki upravljajo uporabnike in okolja. Če vaša organizacija kupi več kot eno licenco za Customer Insights, [kontaktirajte našo ekipo za podporo](https://go.microsoft.com/fwlink/?linkid=2079641) povečati število razpoložljivih okolij. Za več informacij o zmogljivosti in dodatni zmogljivosti si oglejte [Vodnik za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Če želite preizkusiti storitev, glejte razdelek [Nastavitev preizkusnega okolja](trial-signup.md).

## <a name="prerequisites"></a>Zahteve

Potrebujete [skrbniška dovoljenja](permissions.md) v Customer Insights za ustvarjanje ali upravljanje okolij.

## <a name="start-the-environment-creation-process"></a>Začnite postopek ustvarjanja okolja

1. Odprite izbirnik okolja in izberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Izberite izbirnik okolja.":::

1. Sledite vodeni izkušnji, opisani v naslednjih razdelkih, da zagotovite vse potrebne informacije za novo okolje. Če ste okolje konfigurirali prej, lahko tudi [kopirajte konfiguracijo](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>1. korak: Navedite osnovne informacije

V koraku **Osnovni podatki** izberite, ali želite ustvariti okolje od začetka ali [kopirati podatke iz drugega okolja](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Pogovorno okno za ustvarjanje novega okolja Customer Insights.":::

Navedite naslednje podrobnosti:

- **Ime**: ime tega okolja. To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.
- **Izberite svoje podjetje**: izberite primarno občinstvo za novo okolje. Sodelujete lahko s posameznimi potrošniki (prodaja strankam) ali [poslovnimi kupci](work-with-business-accounts.md) (podjetja podjetjem). Če vaša organizacija posluje predvsem s posamezniki, na primer s trgovcem na drobno ali kavarnami, izberite posamezne potrošnike. Če so vaša glavna občinstvo druga podjetja, na primer proizvajalec avtomobilov ali papirnica, izberite poslovne račune.
- **Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje. Preizkusna okolja ne dovoljujejo načrtovanega osveževanja podatkov in so namenjena predhodni implementaciji in testiranju. Okolja peskovnika uporabljajo isto primarno občinstvo kot trenutno izbrano produkcijsko okolje.
- **Območje**: območje, v katerem je storitev uvedena in gostovana. Za [uporabite svoje Azure Data Lake Storage račun](own-data-lake-storage.md) oz [povezati z obstoječo Microsoft Dataverse organizacija](customer-insights-dataverse.md), mora biti okolje Customer Insights v isti regiji.

## <a name="step-2-configure-data-storage"></a>2. korak: konfiguracija shranjevanja podatkov

V **Shranjevanje podatkov** korak, izberite, kam želite shraniti podatke Customer Insights.

Izbirate lahko med dvema možnostma:

- **Shramba Customer Insights** : Shranjevanje podatkov upravlja ekipa Customer Insights. To je privzeta možnost in razen če obstajajo posebne zahteve za shranjevanje podatkov v svoj račun za shranjevanje, priporočamo uporabo te možnosti.
- **Azure Data Lake Storage**: Določite svoje Azure Data Lake Storage račun za shranjevanje podatkov, tako da imate popoln nadzor, kje so podatki shranjeni. Za več informacij glejte [Uporabite svoje Azure Data Lake Storage račun](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Izberite želeno možnost za shranjevanje vaših podatkov.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: vzpostavitev povezave z okoljem Microsoft Dataverse

Korak **Microsoft Dataverse** vam omogoča, da povežete Customer Insights s svojim okoljem Dataverse. Delite podatke z Dataverse za uporabo s poslovnimi aplikacijami, ki temeljijo na Dataverse, kot je Dynamics 365 Marketing ali modelsko vodene aplikacije v Power Apps.

Pustite to polje prazno, če nimate svojega Dataverse okolje in ustvarili ga bomo za vas.

Za več informacij glejte [Delajte s podatki Customer Insights v Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podatkov z Microsoft Dataverse samodejno omogočeno za net nova okolja.":::

### <a name="step-4-finalize-the-settings"></a>4. korak: dokončanje nastavitev

V **Pregled** korak, pojdite skozi vse navedene nastavitve. Ko je vse videti dokončano, izberite možnost **Ustvari**, da nastavite okolje.

Nekatere nastavitve lahko pozneje spremenite. Za več informacij glejte [Upravljanje okolij](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Delajte z novim okoljem

Preglejte naslednje članke, ki vam bodo pomagali začeti s konfiguriranjem storitve Customer Insights:

- [Dodajte več uporabnikov in dodelite dovoljenja](permissions.md).
- [Uvozite svoje vire podatkov](data-sources.md) in jih vodite skozi [postopek poenotenja podatkov](data-unification.md), da nastanejo [enotni profili strank](customer-profiles.md).
- [Obogatite poenotene profile strank](enrichment-hub.md) ali [zaženite modele predvidevanja](predictions-overview.md).
- [Ustvarite segmente](segments.md) za združevanje strank in [mere](measures.md) za pregled KPI-jev.
- [Nastavite povezave](connections.md) in [izvoz](export-destinations.md) za obdelavo podmnožic vaših podatkov v drugih aplikacijah.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okolja

Kot skrbnik se lahko odločite za kopiranje konfiguracije iz obstoječega okolja, ko ustvarite novo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Posnetek zaslona možnosti nastavitev v nastavitvah okolja.":::

Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.

Kopirane so naslednje konfiguracijske nastavitve:

- Viri podatkov, uvoženi prek Power Query
- Konfiguracija združevanja podatkov
- Segmenti
- Mere
- Relacije
- dejavnosti
- Kazalo za iskanje in filtre
- Izvozi
- Osveži urnik
- Obogatitve
- Predvidevanje modeli
- Dodelitve vloge

## <a name="set-up-a-copied-environment"></a>Nastavite kopirano okolje

Ko kopirate konfiguracijo okolja, morate opraviti nekaj dodatnih korakov za potrditev poverilnic:

- Profili strank Najprej preverite pristnost in zaužijte svoje vire podatkov ter zaženite poenotenje podatkov, da ponovno ustvarite profile strank.
- Poverilnice virov podatkov. Za preverjanje pristnosti in ročno osvežitev virov podatkov morate zagotoviti poverilnice za vsak vir podatkov.
- Viri podatkov iz mape Common Data Model in Dataverse. Te vire podatkov morate ustvariti ročno z istim imenom kot v izvornem okolju.
- Povezovalne skrivnosti, ki se uporabljajo za izvoz in obogatitev. Ponovno morate potrditi pristnost povezav in nato ponovno aktivirati obogatitve in izvoze.

Ko je kopirano okolje ustvarjeno, boste videli potrditveno sporočilo. Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.

Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**. Uredite vire podatkov in vnesite poverilnice, da jih osvežite.

:::image type="content" source="media/data-sources-copied.png" alt-text="Seznam virov podatkov, ki so bili kopirani in potrebujejo preverjanje pristnosti.":::

Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**. Tukaj so na voljo nastavitve iz izvornega okolja. Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.

Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.

Preden znova aktivirate izvoze in obogatitve, pojdite na **Admin** > **Povezave** za ponovno preverjanje pristnosti povezav v vašem novem okolju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
