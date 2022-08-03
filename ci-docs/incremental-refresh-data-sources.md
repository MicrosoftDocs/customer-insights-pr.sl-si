---
title: Postopna osvežitev za Power Query in vire podatkov Azure Data Lake
description: Osveži nove in posodobljene podatke za velike vire podatkov na podlagi Power Query ali viri podatkov Azure data lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207157"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Postopna osvežitev za Power Query in vire podatkov Azure Data Lake

Postopna osvežitev za vire podatkov na podlagi Power Query ali Azure Data Lake ponuja naslednje prednosti:

- **Hitrejša osveževanja** – Osvežijo se sami podatki, ki so spremenjeni. Na primer, morda se osveži samo zadnjih pet dni zgodovinskega nabora podatkov.
- **Povečana zanesljivost** – Z manjšimi osveževanji vam ni treba tako dolgo vzdrževati povezav do spremenljivih sistemov virov, zato se zmanjša tveganje za težave pri povezavi.
- **Zmanjšana poraba sredstev** – Osveževanje samo podnabora celotnih podatkov vodi v učinkovitejšo uporabo računalniških sredstev in zmanjša okoljski odtis.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigurirajte postopno osveževanje za vire podatkov na podlagi Power Query

Customer Insights omogoča postopno osveževanje podatkovnih virov, uvoženih prek Power Query ki podpirajo postopno zaužitje. Na primer, zbirke podatkov Azure SQL s polji datuma in časa, ki označujejo, kdaj so bili podatkovni zapisi nazadnje posodobljeni.

1. [Ustvari nov vir podatkov na podlagi Power Query](connect-power-query.md).

1. Izberite vir podatkov, ki podpira postopno osveževanje, kot je npr.[Baza podatkov Azure SQL](/power-query/connectors/azuresqldatabase).

1. Izberite entitete ali tabele za zaužitje.

1. Dokončajte korake pretvorbe in izberite **Naprej**.

1. V pogovornem oknu **Nastavitev postopnega osveževanja** izberite **Nastavitev**, da odprete **Nastavitve postopnega osveževanja**. Če izberete **Preskoči**, bo vir podatkov osvežil celoten nabor podatkov.
   > [!TIP]
   > Postopno osveževanje lahko uporabite tudi pozneje z urejanjem obstoječega vira podatkov.

1. V možnosti **Nastavitve postopnega osveževanja** boste konfigurirali postopno osveževanje za vse entitete, ki ste jih izbrali ob ustvarjanju vira podatkov.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurirajte nastavitve postopnega osveževanja.":::

1. Izberite entiteto in podajte naslednje podrobnosti:

   - **Določitev primarnega ključa**: Izberite primarni ključ za entiteto ali tabelo.
   - **Določitev polja »zadnja posodobitev«**: To polje bo prikazovalo samo atribute vrste datuma ali časa. Izberite atribut, ki označuje, kdaj so bili zapisi nazadnje posodobljeni. Uporabil se bo za prepoznavanje zapisov, ki spadajo v časovni okvir postopnega osveževanja.
   - **Preverjanje, ali so na voljo posodobitve, in sicer na:**: Določite dolžino časovnega okvira postopnega osveževanja.

1. Izberite **Shrani** za dokončanje ustvarjanja vira podatkov. Začetno osveževanje podatkov bo popolno osveževanje. Po tem se postopno osveževanje podatkov izvaja, kot je konfigurirano v prejšnjem koraku.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurirajte postopno osveževanje za vire podatkov Azure Data Lake

Customer Insights omogoča postopno osveževanje za povezane vire podatkov Azure Data Lake Storage. Če želite uporabiti inkrementalno vnos in osvežitev za entiteto, konfigurirajte to entiteto, ko dodajate podatkovno jezero Azure vir podatkov ali pozneje, ko urejate vir podatkov. Mapa podatkov entitete mora vsebovati naslednje mape:

- **FullData** : Mapa s podatkovnimi datotekami, ki vsebujejo začetne zapise
- **Inkrementalni podatki** : Mapa z mapami hierarhije datuma/časa **llll/mm/dd/hh** format, ki vsebuje postopne posodobitve. **hh** predstavlja uro UTC posodobitev in vsebuje **Upserts** in **Izbriše** mape. **Upserts** vsebuje podatkovne datoteke s posodobitvami obstoječih zapisov ali novih zapisov. **Izbriše** vsebuje podatkovne datoteke z zapisi, ki jih je treba odstraniti.

1. Ko dodajate ali urejate vir podatkov, se pomaknite do **Lastnosti** podokno za entiteto.

1. Preglejte atribute. Prepričajte se, da je ustvarjen ali nazadnje posodobljen atribut datuma nastavljen z a *Datum čas* **Format podatkov** in a *Koledar. Datum* **Semantična vrsta**. Po potrebi uredite atribut in izberite **Končano**.

1. Iz **Izberite Entitete** podoknu, uredite entiteto. The **Postopno zaužitje** potrditveno polje je izbrano.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfiguracija entitet v viru podatkov za postopno osveževanje.":::

   1. Poiščite korensko mapo, ki vsebuje datoteke .csv ali .parquet za celotne podatke, prirastne vstavitve podatkov in prirastne izbrise podatkov.
   1. Vnesite končnico za celotne podatke in obe inkrementalni datoteki (\. csv oz\. parket).
   1. Za datoteke .csv izberite ločilo stolpcev in, če želite, prvo vrstico datoteke kot glavo stolpca.
   1. Izberite **Shrani**.

1. Za **Zadnja posodobitev**, izberite atribut datuma in časovnega žiga.

1. Če je **Primarni ključ** ni izbran, izberite primarni ključ. Primarni ključ je atribut, edinstven za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi podatkovnega tipa niz, celo število in GUID.

1. Izberite **Zapri** da shranite in zaprete podokno.

1. Nadaljujte z dodajanjem ali urejanjem vir podatkov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
