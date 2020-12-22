---
title: Postopno osveževanje za vire podatkov, ki temeljijo na storitvi Power Query
description: Osvežite nove in posodobljene podatke za velike vire podatkov, ki temeljijo na orodju Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406982"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Postopno osveževanje za vire podatkov, ki temeljijo na orodju Power Query

Postopno osveževanje za vire podatkov zagotavlja naslednje prednosti:

- **Hitrejša osveževanja** – Osvežijo se sami podatki, ki so spremenjeni. Na primer, morda se osveži samo zadnjih pet dni zgodovinskega nabora podatkov.
- **Povečana zanesljivost** – Z manjšimi osveževanji vam ni treba tako dolgo vzdrževati povezav do spremenljivih sistemov virov, zato se zmanjša tveganje za težave pri povezavi.
- **Zmanjšana poraba sredstev** – Osveževanje samo podnabora celotnih podatkov vodi v učinkovitejšo uporabo računalniških sredstev in zmanjša okoljski odtis.

## <a name="configure-incremental-refresh"></a>Konfiguriranje postopnega osveževanja

Vpogledi v občinstvo omogočajo postopno osveževanje za vire podatkov, uvožene prek storitve Power Query, ki podpirajo postopen uvoz. Na primer, zbirke podatkov Azure SQL s polji datuma in časa, ki označujejo, kdaj so bili podatkovni zapisi nazadnje posodobljeni.

1. [Ustvarjanje novega vira podatkov, ki temelji na orodju Power Query](connect-power-query.md).

1. Podajte ime vira podatkov.

1. Izberite vir podatkov, ki podpira postopno osveževanje, kot je zbirka podatkov Azure SQL.

1. Izberite entitete ali tabele za zaužitje.

1. Dokončajte korake pretvorbe in izberite **Naprej**.

1. V pogovornem oknu **Nastavitev postopnega osveževanja** izberite **Nastavitev**, da odprete **Nastavitve postopnega osveževanja**. Če izberete **Preskoči**, bo vir podatkov osvežil celoten nabor podatkov.
   > [!TIP]
   > Postopno osveževanje lahko uporabite tudi pozneje z urejanjem obstoječega vira podatkov.

1. V možnosti **Nastavitve postopnega osveževanja** boste konfigurirali postopno osveževanje za vse entitete, ki ste jih izbrali ob ustvarjanju vira podatkov.

   > [!div class="mx-imgBorder"]
   > ![Konfiguracija entitet v viru podatkov za postopno osveževanje](media/incremental-refresh-settings.png "Konfiguracija entitet v viru podatkov za postopno osveževanje")

1. Izberite entiteto in podajte naslednje podrobnosti:

   - **Določitev primarnega ključa**: Izberite primarni ključ za entiteto ali tabelo.
   - **Določitev polja »zadnja posodobitev«**: To polje bo prikazovalo samo atribute vrste datuma ali časa. Izberite atribut, ki označuje, kdaj so bili zapisi nazadnje posodobljeni. Uporabil se bo za prepoznavanje zapisov, ki spadajo v časovni okvir postopnega osveževanja.
   - **Preverjanje, ali so na voljo posodobitve, in sicer na:**: Določite dolžino časovnega okvira postopnega osveževanja.

1. Izberite **Shrani** za dokončanje ustvarjanja vira podatkov. Začetno osveževanje podatkov bo popolno osveževanje. Po tem se postopno osveževanje podatkov izvaja, kot je konfigurirano v prejšnjem koraku.
