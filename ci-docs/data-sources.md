---
title: Pregled virov podatkov
description: Naučite se uvoziti ali vnesti podatke iz različnih virov.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610072"
---
# <a name="data-sources-overview"></a>Pregled virov podatkov

Dynamics 365 Customer Insights zagotavlja povezave za prenos podatkov iz širokega nabora virov. Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*. Po zaužitju podatkov lahko [poenotiti](data-unification.md), ustvarite vpoglede in aktivirajte podatke za ustvarjanje prilagojenih izkušenj.

## <a name="add-or-edit-data-sources"></a>Dodajte ali uredite vire podatkov

Vire podatkov lahko priložite ali uvozite v Customer Insights. Na spodnjih povezavah so navodila za dodajanje in urejanje virov podatkov.

**Priložite vir podatkov**

Če imate podatke pripravljene v eni od Microsoftovih podatkovnih storitev Azure, se lahko Customer Insights preprosto poveže z vir podatkov, ne da bi morali znova vnesti podatke. Izberite eno od teh možnosti:
- [Azure Data Lake Storage(datoteke csv ali parquet v mapi Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Baze podatkov o jezerih)](connect-synapse.md)
- [Microsoft Dataverse podatkovno jezero](connect-dataverse-managed-lake.md)

**Uvozi in transformiraj**

Če uporabljate lokalne vire podatkov, podatke Microsofta ali tretjih oseb, uvozite in preoblikujte podatke z uporabo Power Query priključki.
- [Power Query priključki](connect-power-query.md)

## <a name="review-data-sources"></a>Preglejte vire podatkov

Če je bilo vaše okolje konfigurirano za uporabo shrambe Customer Insights in uporabljate lokalne vire podatkov, uporabite Power Platform podatkovnih tokov. z Power Platform podatkovnih tokov si lahko ogledate skupne vire podatkov in vire podatkov, ki jih upravljajo drugi. The **Viri podatkov** stran navaja vire podatkov v treh razdelkih:
- **V skupni rabi** : Viri podatkov, ki jih lahko upravljajo vsi skrbniki Customer Insights. Power Platform podatkovnih tokov, svoj račun za shranjevanje in pripenjanje na a Dataverse -upravljano podatkovno jezero je primer skupnih podatkovnih virov.
- **Upravljam jaz** :Power Platform podatkovnih tokov, ki jih ustvarite in upravljate samo vi. Drugi skrbniki Customer Insights si lahko samo ogledajo te tokove podatkov, ne pa jih urejajo, osvežujejo ali brišejo.
- **Upravljajo drugi** :Power Platform podatkovnih tokov, ki so jih ustvarili drugi skrbniki. Lahko si jih samo ogledate. Navaja lastnika podatkovnega toka, na katerega se lahko obrnete za pomoč.
> [!NOTE]
> Vse entitete si lahko ogledajo in uporabljajo drugi uporabniki. Medtem ko so viri podatkov v lasti uporabnika, ki jih je ustvaril, lahko entitete, ki izhajajo iz vnosa podatkov, uporablja vsak uporabnik Customer Insights.

Če vaše okolje ne uporablja Power Platform podatkovnih tokov, the **Viri podatkov** stran vsebuje le seznam vseh virov podatkov. Ni prikazanih razdelkov.

## <a name="manage-existing-data-sources"></a>Upravljajte obstoječe vire podatkov

Pojdi do **podatki** > **Viri podatkov** za ogled imena vsakega vnesenega vir podatkov, njegovega statusa in zadnjega osveževanja podatkov za ta vir. Seznam podatkovnih virov lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete vir podatkov, ki ga želite upravljati.

Za ogled razpoložljivih dejanj izberite vir podatkov.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Vir podatkov je dodan.":::

- [**Uredi**](#add-or-edit-data-sources) vir podatkov, da spremenite njegove lastnosti.
- [**Osveži**](#refresh-data-sources) vir podatkov za vključitev najnovejših podatkov.
- [**Obogatiti**](data-sources-enrichment.md) vir podatkov pred združitvijo.
- **Izbriši** vir podatkov. Vir podatkov je mogoče izbrisati le, če se podatki ne uporabljajo pri nobeni obdelavi, kot so poenotenje, vpogledi, aktivacije ali izvozi.

## <a name="refresh-data-sources"></a>Osveževanje virov podatkov

Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo. [Lokalni viri podatkov](connect-power-query.md#add-data-from-on-premises-data-sources) osvežujejo po svojih urnikih, ki so nastavljeni med vnosom podatkov. Za nasvete za odpravljanje težav glejte [Odpravite težave s PPDF Power Query na osnovi vir podatkov težave z osveževanjem](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Za priložene vire podatkov vnos podatkov porabi najnovejše podatke, ki so na voljo iz tega vir podatkov.

Pojdi do **skrbnik** > **Sistem** > [**Urnik**](schedule-refresh.md) da konfigurirate sistemsko načrtovane osvežitve virov vnesenih podatkov.

Za osvežitev vir podatkov na zahtevo:

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite vir podatkov, ki ga želite osvežiti, in izberite **Osveži**. Vir podatkov se zdaj sproži za ročno osvežitev. Če osvežite vir podatkov, se posodobijo tudi shema entitet in podatki za vse entitete, določene v viru podatkov.

1. Izberite stanje, da odprete **Podrobnosti o napredku** podokno in si oglejte napredek. Za preklic opravila izberite **Prekliči delo** na dnu podokna.

## <a name="corrupt-data-sources"></a>Pokvarjeni viri podatkov

Vneseni podatki imajo lahko poškodovane zapise, kar lahko povzroči, da se postopek vnosa podatkov zaključi z napakami ali opozorili.

> [!NOTE]
> Če se vnos podatkov zaključi z napakami, bo nadaljnja obdelava (kot je poenotenje ali ustvarjanje dejavnosti), ki izkorišča ta vir podatkov, preskočena. Če se zaužitje zaključi z opozorili, se nadaljnja obdelava nadaljuje, vendar nekateri zapisi morda ne bodo vključeni.

Te napake so vidne v podrobnostih naloge.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Podrobnosti o opravilu prikazujejo napako poškodovanih podatkov.":::

Poškodovani zapisi so prikazani v sistemsko ustvarjenih entitetah.

### <a name="fix-corrupt-data"></a>Popravite poškodovane podatke

1. Če si želite ogledati poškodovane podatke, pojdite na **podatki** > **Entitete** in poiščite poškodovane subjekte v **Sistem** razdelek. Shema poimenovanja poškodovanih entitet: 'DataSourceName_EntityName_corrupt'.

1. Izberite pokvarjeno entiteto in nato **podatki** zavihek.

1. Identificirajte poškodovana polja v zapisu in razlog.

   :::image type="content" source="media/corruption-reason.png" alt-text="Razlog za korupcijo." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **podatki** > **Entitete** prikazuje le del poškodovanih zapisov. Če si želite ogledati vse poškodovane zapise, izvozite datoteke v vsebnik v računu za shranjevanje z uporabo [Postopek izvoza Customer Insights](export-destinations.md). Če ste uporabili svoj račun za shranjevanje, si lahko ogledate tudi mapo Customer Insights v svojem računu za shranjevanje.

1. Popravite poškodovane podatke. Na primer za vire podatkov Azure Data Lake, [popraviti podatke v shrambi podatkovnega jezera ali posodobiti vrste podatkov v datoteki manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Za Power Query vire podatkov, popravi podatke v izvorni datoteki in [popravite vrsto podatkov korak transformacije](connect-power-query.md#data-type-does-not-match-data) na **Power Query - Uredite poizvedbe** strani.

Po naslednji osvežitvi vira podatkov se popravljeni zapisi uvozijo v Customer Insights in posredujejo v postopke iz strežnika.

Na primer stolpec »rojstni dan« ima vrsto podatkov nastavljeno kot »datum«. V evidenci strank je njihov rojstni dan vpisan kot »01/01/19777«. Sistem označi ta zapis kot poškodovan. Spremenite rojstni dan v izvornem sistemu na '1977'. Po samodejni osvežitvi podatkovnih virov ima polje zdaj veljavno obliko in zapis je odstranjen iz poškodovane entitete.

[!INCLUDE [footer-include](includes/footer-banner.md)]
