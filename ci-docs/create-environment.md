---
title: Ustvarjanje novega okolja
description: Koraki za ustvarjanje okolij v Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304285"
---
# <a name="create-a-new-environment"></a>Ustvarjanje novega okolja

Po [nakup naročniške licence za Dynamics 365 Customer Insights](paid-license.md), globalni skrbnik za Microsoft 365 najemnik prejme e-poštno sporočilo, ki ga vabi k ustvarjanju okolja. Za začetek pojdite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). V tem scenariju začnite z [1. korak: Navedite osnovne informacije](#step-1-provide-basic-information).

Ko je ustvarjeno prvo okolje, globalni skrbnik za Microsoft 365 najemnik lahko [dodajo uporabnike iz svoje organizacije kot skrbnike](permissions.md). Ti skrbniki lahko nato upravljajo uporabnike in okolja. Če vaša organizacija kupi več kot eno licenco za Customer Insights, [stopite v stik z našo skupino za podporo](https://go.microsoft.com/fwlink/?linkid=2079641) povečati število razpoložljivih okolij. Za več informacij o zmogljivosti in dodatni zmogljivosti si oglejte [Vodnik za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Ko imate možnost ustvariti dodatna okolja, pojdite na [Začnite postopek ustvarjanja okolja](#start-the-environment-creation-process).

> [!TIP]
> Če želite preizkusiti storitev, glejte razdelek [Nastavitev preizkusnega okolja](trial-signup.md).

## <a name="prerequisites"></a>Zahteve

[Skrbniška dovoljenja](permissions.md) v Customer Insights

## <a name="start-the-environment-creation-process"></a>Začnite postopek ustvarjanja okolja

1. Odprite izbirnik okolja in izberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Izberite izbirnik okolja.":::

1. Sledite vodeni izkušnji, opisani v naslednjih razdelkih, da zagotovite vse potrebne informacije za novo okolje.

## <a name="step-1-provide-basic-information"></a>1. korak: Navedite osnovne informacije

1. Izberite, ali želite ustvariti okolje iz nič ali kopirati podatke iz drugega okolja. [Kopiranje podatkov iz drugega okolja](#copy-the-environment-configuration) zahteva dodatne korake.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Pogovorno okno za ustvarjanje novega okolja Customer Insights.":::

1. Navedite naslednje podrobnosti:

   - **Ime** : ime za to okolje. To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.
   - **Izberite svoje podjetje** : Primarni občinstvo za novo okolje: individualni porabniki (B-to-C) oz.[poslovne račune](work-with-business-accounts.md) (B-do-B). Če vaša organizacija večinoma posluje s posamezniki, kot je prodajalec na drobno ali kavarna, izberite posamezne potrošnike. Če so vaš glavni občinstvo druga podjetja, na primer proizvajalec avtomobilov ali papirnica, izberite poslovne račune.
   - **Vrsta** : Vrsta okolja: proizvodnja ali peskovnik. Preizkusna okolja ne dovoljujejo načrtovanega osveževanja podatkov in so namenjena predhodni implementaciji in testiranju. Okolja peskovnika uporabljajo isto primarno občinstvo kot trenutno izbrano produkcijsko okolje.
   - **Regija** : Regija, v kateri je storitev razporejena in gostuje. Za [uporabite svojega Azure Data Lake Storage račun](own-data-lake-storage.md) oz [povezati z obstoječim Microsoft Dataverse organizacija](customer-insights-dataverse.md), mora biti okolje Customer Insights v isti regiji.

1. Izberite **Naprej**.

## <a name="step-2-configure-data-storage"></a>2. korak: konfiguracija shranjevanja podatkov

1. Izberite, kam želite shraniti podatke Customer Insights:

   - **Shramba Customer Insights** : Shranjevanje podatkov se upravlja samodejno. To je privzeta možnost in priporočamo uporabo te možnosti, razen če obstajajo posebne zahteve za shranjevanje podatkov v vašem računu za shranjevanje.
   - **Azure Data Lake Storage**: Lastne Azure Data Lake Storage račun za shranjevanje podatkov, tako da imate popoln nadzor, kje so shranjeni podatki. Sledite korakom v [Uporabite svojega Azure Data Lake Storage račun](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Izberite želeno možnost za shranjevanje vaših podatkov.":::

1. Izberite **Naprej**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: vzpostavitev povezave z okoljem Microsoft Dataverse

Če imate a Dataverse okolje, povežite Customer Insights. Delite podatke z Dataverse za uporabo s poslovnimi aplikacijami, ki temeljijo na Dataverse, kot je Dynamics 365 Marketing ali aplikacije, ki temeljijo na modelu Power Apps.

1. Sledite korakom v [Delajte s podatki Customer Insights v Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podatkov z Microsoft Dataverse samodejno omogočeno za spletna nova okolja.":::

1. Izberite **Naprej**.

## <a name="step-4-finalize-the-settings"></a>4. korak: dokončanje nastavitev

Preglejte navedene nastavitve. Ko je vse videti dokončano, izberite možnost **Ustvari**, da nastavite okolje.

Če želite pozneje spremeniti nekatere nastavitve, glejte [Upravljajte okolja](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Delajte z novim okoljem

Preglejte naslednje članke, ki vam bodo pomagali začeti s konfiguriranjem storitve Customer Insights:

- [Dodajte več uporabnikov in dodelite dovoljenja](permissions.md).
- [Uvozite svoje vire podatkov](data-sources.md) in jih vodite skozi [postopek poenotenja podatkov](data-unification.md), da nastanejo [enotni profili strank](customer-profiles.md).
- [Obogatite poenotene profile strank](enrichment-hub.md) ali [zaženite modele predvidevanja](predictions-overview.md).
- [Ustvarite segmente](segments.md) za združevanje strank in [mere](measures.md) za pregled KPI-jev.
- [Nastavite povezave](connections.md) in [izvoz](export-destinations.md) za obdelavo podmnožic vaših podatkov v drugih aplikacijah.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okolja

Če se kot skrbnik odločite za kopiranje konfiguracije iz obstoječega okolja, izberite s seznama vseh razpoložljivih okolij v vaši organizaciji.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Posnetek zaslona možnosti nastavitev v nastavitvah okolja.":::

Kopirane so naslednje konfiguracijske nastavitve:

- Viri podatkov, uvoženi prek Power Query
- Konfiguracija poenotenja podatkov
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

### <a name="set-up-a-copied-environment"></a>Nastavite kopirano okolje

Ko kopirate konfiguracijo okolja, se prikaže potrditveno sporočilo, ko je bilo kopirano okolje ustvarjeno. Za potrditev poverilnic izvedite naslednje korake.

1. Izberite **Na vire podatkov**, da prikažete seznam virov podatkov. Vsi viri podatkov kažejo **Zahtevane poverilnice** stanje.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Seznam virov podatkov, ki so bili kopirani in potrebujejo preverjanje pristnosti.":::

1. Uredite vire podatkov in vnesite poverilnice, da jih osvežite. Viri podatkov iz mape Common Data Model in Dataverse je treba ustvariti ročno z istim imenom kot v izvornem okolju.

1. Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**. Tukaj so na voljo nastavitve iz izvornega okolja. Po potrebi jih uredite ali izberite **Poenotiti** > **Poenotite profile strank in odvisnosti** da začnete postopek združevanja podatkov in ustvarite enotno strankino entiteto.

   > [!TIP]
   > Za račune in stike izberite **Poenotite račune** > **Poenotite profile in odvisnosti**.

1. Ko je združevanje podatkov končano, pojdite na **Ukrepi** in **Segmenti** da jih osvežim.

1. Pojdi do **skrbnik** > **Povezave** za ponovno avtentifikacijo povezav v vašem novem okolju.

1. Pojdi do **podatki** > **Obogatitev** in **podatki** > **Izvozi** da jih ponovno aktivirate.

[!INCLUDE [footer-include](includes/footer-banner.md)]
