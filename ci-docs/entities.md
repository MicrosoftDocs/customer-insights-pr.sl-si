---
title: Entitete v storitvi Customer Insights
description: Oglejte si podatke na strani Entitete.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183605"
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

- The **Poročila** zavihek (na voljo za nekatere subjekte) vam omogoča vizualizacijo podatkov z ustvarjanjem poročila, ki vključuje te stolpce:

  - **Ime poročila** : Ime poročila.
  - **Ustvaril** : ime osebe, ki je ustvarila entiteto.
  - **Ustvarjeno** : Datum in čas ustvarjanja entitete.
  - **Uredil** : ime osebe, ki je spremenila entiteto.
  - **Urejeno** : datum in čas spremembe entitete.

## <a name="entity-specific-information"></a>Informacije o določeni entiteti

V naslednjem razdelku najdete informacije o nekaterih entitetah, ki jih je ustvaril sistem.

### <a name="corrupted-data-sources"></a>Poškodovani viri podatkov

Polja iz uvoženega vira podatkov lahko vsebujejo poškodovane podatke. Zapisi s poškodovanimi polji so na voljo v entitetah, ki jih je ustvaril sistem. Poznavanje poškodovanih zapisov vam pomaga ugotoviti, katere podatke morate pregledati in posodobiti v izvornem sistemu. Po naslednji osvežitvi vira podatkov se popravljeni zapisi uvozijo v Customer Insights in posredujejo v postopke iz strežnika. 

Na primer stolpec »rojstni dan« ima vrsto podatkov nastavljeno kot »datum«. V evidenci strank je njihov rojstni dan vpisan kot »01/01/19777«. Sistem bo ta zapis označil kot poškodovan. Nekdo lahko v izvornem sistemu zdaj spremeni rojstni dan na »1977«. Po samodejnem osveževanju virov podatkov ima polje zdaj veljavno obliko in zapis bo odstranjen iz poškodovane entitete.

Pojdite na **Podatki** > **Entitete** in v razdelku **Sistem** poiščite poškodovane entitete. Shema poimenovanja poškodovanih entitet: »DataSourceName_EntityName_corrupt«. Izberite poškodovano entiteto, da prepoznate poškodovana polja in razlog na ravni posameznega zapisa.

   :::image type="content" source="media/corruption-reason.png" alt-text="Razlog za korupcijo.":::

Customer Insights še vedno obdeluje poškodovane zapise. Lahko pa povzročijo težave pri delu s poenotenimi podatki.

Za odkrivanje poškodovanih zapisov se izvajajo naslednja preverjanja uvoženih podatkov:

- Vrednost polja se ne ujema z vrsto podatkov njegovega stolpca.
- Polja vsebujejo znake, zaradi katerih se stolpci ne ujemajo s pričakovano shemo. Na primer: napačno oblikovani narekovaji, nespremenjeni narekovaji ali znaki nove vrstice.
- Če obstajajo stolpci datetime/date/datetimeoffset, je treba v modelu določiti njihov format, če ne sledi standardnemu formatu ISO.

[!INCLUDE [footer-include](includes/footer-banner.md)]
