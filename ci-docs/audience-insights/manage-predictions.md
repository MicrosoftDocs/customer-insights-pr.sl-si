---
title: Opravila v skupni rabi za scenarije predvidevanja
description: Naučite se upravljati, odpravljati težave in izboljšati predvidevanja.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8ff8d70ffb8489def072e5d8a6e43d062594141a
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555333"
---
# <a name="manage-predictions"></a>Upravljanje predvidevanj

Ta članek obravnava nekatere naloge, ki so skupne večini scenarijev predvidevanja.

## <a name="troubleshoot-a-failed-prediction"></a>Odpravite težave z neuspešnim predvidevanjem

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, za katere si želite ogledati dnevnike napak.

1. Izberite **Dnevniki**.

1. Preglejte vse napake. Pride lahko do več vrst napak, ki opisujejo, kakšno stanje je povzročilo napako. Primer: napaka, za katero ni dovolj podatkov za natančno predvidevanje, se običajno odpravi z nalaganjem dodatnih podatkov v storitev Customer Insights.

## <a name="input-data-usability-report"></a>Poročilo o uporabnosti vhodnih podatkov

Poročilo o uporabnosti vhodnih podatkov ponuja strnjen prikaz napak in opozoril, ki jih lahko ustvarijo vaše vnaprej pripravljene napovedi. Prav tako daje priporočila, kako izboljšati zmogljivost modela.

Poročilo je na voljo, ko model zaključi s postopkom kvalificiranja. Ustvarjeno je za vsak model posebej, ne glede na to, ali je bilo uspešno zaključeno ali ne.

### <a name="view-the-input-data-usability-report"></a>Ogled poročila o uporabnosti vhodnih podatkov

Ko vnaprej pripravljen model zaključi korak za kvalificiranje, si oglejte poročilo:
- Izberite tri pike poleg imena modela in izberite **Poročilo o uporabnosti vhodnih podatkov**.
- Izberite stanje modela in nato v stranskem podoknu kliknite **Ogled poročila o uporabnosti vhodnih podatkov**.
- Izberite enega od modelov na seznamu in izberite **Poročilo o uporabnosti vhodnih podatkov** v ukazni vrstici.
- Odprite stran z rezultati modela in nato **Poročilo o uporabnosti vhodnih podatkov** v ukazni vrstici.

### <a name="information-in-the-input-data-usability-report"></a>Podatki v poročilu o uporabnosti vhodnih podatkov

Naslednji stolpci poročila vsebujejo koristne informacije za izboljšanje podatkov za model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer poročila o uporabnosti vhodnih podatkov, ki prikazuje tabelo z napakami, opozorili in priporočili.":::

- **ime:** Opisno ime napake, opozorila ali priporočila.
- **korak:** Faza modela, vlak ali rezultat, na katerega se nanašajo informacije.
- **Država:** Resnost informacij (napaka, opozorilo, priporočilo).
- **Ime stolpca:** Stolpec v entiteti, ki ga je treba spremeniti, da se izboljša zmogljivost modela.
- **Ime subjekta:** Ime entitete, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.
- **Podrobnosti:** Podrobnosti o napaki, opozorilu ali priporočilu.

## <a name="refresh-a-prediction"></a>Osveževanje predvidevanja

Predvidevanja se bodo samodejno osvežila v istem [urniku, kot ga osvežijo vaši podatki](system.md#schedule-tab), ko se konfigurirajo v nastavitvah. Lahko jih osvežite tudi ročno.

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite osvežiti.

1. Izberite **Osveži**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Brisanje predvidevanja

Če izbrišete predvidevanje, odstranite tudi njegovo izhodno entiteto.

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite izbrisati.

1. Izberite **Izbriši**.
