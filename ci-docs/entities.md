---
title: Entitete v storitvi Customer Insights
description: Oglejte si podatke na strani Entitete.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610118"
---
# <a name="entities-in-customer-insights"></a>Entitete v storitvi Customer Insights

Po [konfiguraciji virov podatkov](data-sources.md) pojdite na stran **Entitete**, da ocenite kakovost uvoženih podatkov. Entitete se štejejo za nabore podatkov. Več zmožnosti storitve Dynamics 365 Customer Insights je ustvarjenih v povezavi s temi entitetami. Njihov natančen pregled vam lahko pomaga preveriti veljavnost rezultatov teh zmogljivosti.

Ko delate v Customer Insights in bogatite svoje podatke ali ustvarjate segmente, mere in dejavnosti, se entitete, ustvarjene iz teh dejanj, prikažejo na **Entitete** strani.

## <a name="view-a-list-of-entities"></a>Oglejte si seznam entitet

Pojdi do **podatki** > **Entitete** za ogled seznama entitet. Za vsako entiteto se prikažejo naslednje informacije.

- **Ime** : Ime podatkovne entitete. Če poleg imena entitete vidite opozorilni simbol, to pomeni, da se podatki za to entiteto niso uspešno naložili.
- **Vir** : Vrsta vir podatkov, ki je zaužila entiteto.
- **Posodobljeno** : Čas, ko je bila entiteta nazadnje posodobljena.
- **Stanje** : Podrobnosti o zadnji posodobitvi entitete.

## <a name="explore-a-specific-entitys-data"></a>Raziskovanje podatkov določene entitete

1. Pojdi do **podatki** > **Entitete**.
1. Izberite entiteto, da odprete stran s podrobnostmi.  
1. Raziščite različna polja in zapise, vključene za to entiteto.

- The **Lastnosti** zavihek je privzeto izbran in prikazuje podrobnosti za izbrano entiteto, kot so imena polj, tipi podatkov in tipi. V stolpcu **Vrste** so prikazane vrste, povezane z modelom Common Data Model, ki jih sistem samodejno identificira ali jih uporabniki [ročno preslikajo](map-entities.md). Te vrste so semantične vrste, ki se lahko razlikujejo od vrst podatkov atributov. Na primer polje *E-naslov* spodaj ima vrsto podatkov *Vrvica* vendar je lahko njegov (semantični) tip skupnega podatkovnega modela *E-naslov*, *naslov*, oz *Identiteta.Storitev.E-pošta*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabela s polji.":::

   > [!NOTE]
   > Ta stran prikazuje samo vzorec podatkov vašega subjekta. Za ogled celotnega nabor podatkov pojdite na **Viri podatkov** stran, izberite entiteto, izberite **Uredi** in si nato oglejte podatke te entitete z Power Query urednik, kot je razloženo v [Viri podatkov](data-sources.md).

   Če želite izvedeti več o podatkih, zaužitih v entiteti, **Povzetek** vsebuje nekaj pomembnih značilnosti podatkov, kot so ničelne vrednosti, manjkajoče vrednosti, enolične vrednosti, štetje in porazdelitve, kar koli je uporabno za vaše podatke. Izberite ikono grafikona, če želite videti povzetek podatkov.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabela povzetka podatkov.":::

- The **podatki** zavihek prikazuje podrobnosti o posameznih zapisih subjekta. Navedene podrobnosti so odvisne od vrste podatkov entitete.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Izberite entiteto.":::

- The **Poročila** zavihek (na voljo za nekatere entitete) vam omogoča vizualizacijo podatkov z ustvarjanjem poročila, ki vključuje te stolpce:

  - **Ime poročila** : Ime poročila.
  - **Ustvaril** : ime osebe, ki je ustvarila entiteto.
  - **Ustvarjeno** : Datum in čas ustvarjanja entitete.
  - **Uredil** : ime osebe, ki je spremenila entiteto.
  - **Urejeno** : datum in čas spremembe entitete.

[!INCLUDE [footer-include](includes/footer-banner.md)]
