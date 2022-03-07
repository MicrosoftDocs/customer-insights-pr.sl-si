---
title: Opravila v skupni rabi za scenarije predvidevanja
description: Naučite se upravljati, odpravljati težave in izboljšati predvidevanja.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315898"
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

- Ime: opisno ime napake, opozorila ali priporočila.
- Korak: faza modela, kvalificiranje ali rezultat, na katerega se informacije nanašajo.
- Stanje: resnost informacij (napaka, opozorilo, priporočilo).
- Ime stolpca: stolpec v entiteti, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.
- Ime entitete: ime entitete, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.
- Podrobnosti: podrobnosti o napaki, opozorilu ali priporočilu.

## <a name="refresh-a-prediction"></a>Osveževanje predvidevanja

Predvidevanja se bodo samodejno osvežila v istem [urniku, kot ga osvežijo vaši podatki](system.md#schedule-tab), ko se konfigurirajo v nastavitvah. Lahko jih osvežite tudi ročno.

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite osvežiti.

1. Izberite **Osveži**.

## <a name="delete-a-prediction"></a>Brisanje predvidevanja

Če izbrišete predvidevanje, odstranite tudi njegovo izhodno entiteto.

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite izbrisati.

1. Izberite **Izbriši**.
