---
title: Postopno osveževanje za Power Query - viri podatkov
description: Osvežite nove in posodobljene podatke za velike vire podatkov, ki temeljijo na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643661"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Postopno osveževanje za vire podatkov na podlagi Power Query

Ta članek obravnava, kako konfigurirati postopno osveževanje za vire podatkov na podlagi Power Query.

Postopno osveževanje za vire podatkov zagotavlja naslednje prednosti:

- **Hitrejša osveževanja** – Osvežijo se sami podatki, ki so spremenjeni. Na primer, morda se osveži samo zadnjih pet dni zgodovinskega nabora podatkov.
- **Povečana zanesljivost** – Z manjšimi osveževanji vam ni treba tako dolgo vzdrževati povezav do spremenljivih sistemov virov, zato se zmanjša tveganje za težave pri povezavi.
- **Zmanjšana poraba sredstev** – Osveževanje samo podnabora celotnih podatkov vodi v učinkovitejšo uporabo računalniških sredstev in zmanjša okoljski odtis.

## <a name="configure-incremental-refresh"></a>Konfiguracija postopnega osveževanja

Customer Insights omogoča postopno osveževanje virov podatkov, uvoženih prek Power Query ki podpirajo postopno zaužitje. Na primer, zbirke podatkov Azure SQL s polji datuma in časa, ki označujejo, kdaj so bili podatkovni zapisi nazadnje posodobljeni.

1. [Ustvarite nov vir podatkov na podlagi Power Query](connect-power-query.md).

1. Zagotovite a **ime** za vir podatkov.

1. Izberite vir podatkov, ki podpira postopno osveževanje, kot je npr.[Baza podatkov Azure SQL](/power-query/connectors/azuresqldatabase).

1. Izberite entitete ali tabele za zaužitje.

1. Dokončajte korake pretvorbe in izberite **Naprej**.

1. V pogovornem oknu **Nastavitev postopnega osveževanja** izberite **Nastavitev**, da odprete **Nastavitve postopnega osveževanja**. Če izberete **Preskoči**, bo vir podatkov osvežil celoten nabor podatkov.
   > [!TIP]
   > Postopno osveževanje lahko uporabite tudi pozneje z urejanjem obstoječega vira podatkov.

1. V možnosti **Nastavitve postopnega osveževanja** boste konfigurirali postopno osveževanje za vse entitete, ki ste jih izbrali ob ustvarjanju vira podatkov.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfiguracija entitet v viru podatkov za postopno osveževanje.":::

1. Izberite entiteto in podajte naslednje podrobnosti:

   - **Določitev primarnega ključa**: Izberite primarni ključ za entiteto ali tabelo.
   - **Določitev polja »zadnja posodobitev«**: To polje bo prikazovalo samo atribute vrste datuma ali časa. Izberite atribut, ki označuje, kdaj so bili zapisi nazadnje posodobljeni. Uporabil se bo za prepoznavanje zapisov, ki spadajo v časovni okvir postopnega osveževanja.
   - **Preverjanje, ali so na voljo posodobitve, in sicer na:**: Določite dolžino časovnega okvira postopnega osveževanja.

1. Izberite **Shrani** za dokončanje ustvarjanja vira podatkov. Začetno osveževanje podatkov bo popolno osveževanje. Po tem se postopno osveževanje podatkov izvaja, kot je konfigurirano v prejšnjem koraku.


[!INCLUDE [footer-include](includes/footer-banner.md)]