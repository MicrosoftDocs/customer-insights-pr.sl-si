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
ms.openlocfilehash: 4abb7704710ac269a4f3c9463fe905fa6eec3234
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082732"
---
# <a name="entities-in-customer-insights"></a>Entitete v storitvi Customer Insights

Po [konfiguraciji virov podatkov](data-sources.md) pojdite na stran **Entitete**, da ocenite kakovost uvoženih podatkov. Entitete se štejejo za nabore podatkov. Več zmožnosti storitve Dynamics 365 Customer Insights je ustvarjenih v povezavi s temi entitetami. Njihov natančen pregled vam lahko pomaga preveriti veljavnost rezultatov teh zmogljivosti.

The **Entitete** stran navaja entitete in vključuje te stolpce:

- **ime** : Ime podatkovne entitete. Če poleg imena entitete vidite opozorilni simbol, to pomeni, da se podatki za to entiteto niso uspešno naložili.
- **Vir** : Vrsta vir podatkov, ki je prenesla entiteto.
- **Posodobljeno** : čas, ko je bila entiteta nazadnje posodobljena.
- **Stanje** : Podrobnosti o zadnji posodobitvi entitete.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Raziskovanje podatkov določene entitete

1. Pojdi do **Podatki** > **Entitete**.
1. Iz **Entitete** strani, izberite entiteto, da odprete stran s podrobnostmi.  
1. Raziščite različna polja in zapise, vključene za to entiteto.

- Zavihek **Atributi** je privzeto izbran in prikazuje tabelo za pregled podrobnosti za izbrano entiteto, kot so imena polj, vrste podatkov in vrste. V stolpcu **Vrste** so prikazane vrste, povezane z modelom Common Data Model, ki jih sistem samodejno identificira ali jih uporabniki [ročno preslikajo](map-entities.md). Te vrste so semantične vrste, ki se lahko razlikujejo od vrst podatkov atributov. Na primer spodnje polje *E-pošta* ima vrsto podatkov *Besedilo*, vendar je njegova (semantična) vrsta modela Common Data Model lahko *E-pošta* ali *E-poštni naslov*.

> [!div class="mx-imgBorder"]
> ![Tabela s polji.](media/data-manager-entities-fields.PNG "Tabela s polji")

> [!NOTE]
> Ta stran prikazuje samo vzorec podatkov vašega subjekta. Če si želite ogledati celoten nabor podatkov, pojdite na **Viri podatkov** stran, izberite entiteto, izberite **Uredi**, nato pa si oglejte podatke te entitete z Power Query urednik, kot je razloženo v [Viri podatkov](data-sources.md).

Če želite izvedeti več o podatkih, uvoženih v entiteto, vam stolpec **Povzetek** zagotavlja nekatere pomembne značilnosti podatkov, kot so vrednosti nič, manjkajoče vrednosti, edinstvene vrednosti, števila in porazdelitve, kot je primerno za vaše podatke. Izberite ikono grafikona, če želite videti povzetek podatkov.

> [!div class="mx-imgBorder"]
> ![Simbol povzetka.](media/data-manager-entities-summary.png "Tabela s povzetkom podatkov")

- Zavihek **Podatki** prikazuje tabelo s podrobnostmi o posameznih zapisih entitete. Navedene podrobnosti so odvisne od vrste podatkov entitete.

> [!div class="mx-imgBorder"]
> ![Izberite entiteto.](media/data-manager-entities-data.png "Izberite entiteto")

- The **Poročila** zavihek (na voljo za nekatere subjekte) vam omogoča vizualizacijo vaših podatkov z ustvarjanjem poročila in vključuje te stolpce:

  - **Ime poročila** : Ime poročila.
  - **Ustvaril** : Ime osebe, ki je ustvarila entiteto.
  - **Ustvarjeno** : Datum in čas nastanka entitete.
  - **Uredil** : Ime osebe, ki je spremenila entiteto.
  - **Urejeno** : Datum in čas spremembe entitete. 

## <a name="entity-specific-information"></a>Informacije o določeni entiteti

V naslednjem razdelku najdete informacije o nekaterih entitetah, ki jih je ustvaril sistem.

### <a name="corrupted-data-sources"></a>Poškodovani viri podatkov

Polja iz uvoženega vira podatkov lahko vsebujejo poškodovane podatke. Zapisi s poškodovanimi polji so na voljo v entitetah, ki jih je ustvaril sistem. Poznavanje poškodovanih zapisov vam pomaga ugotoviti, katere podatke morate pregledati in posodobiti v izvornem sistemu. Po naslednji osvežitvi vira podatkov se popravljeni zapisi uvozijo v Customer Insights in posredujejo v postopke iz strežnika. 

Na primer stolpec »rojstni dan« ima vrsto podatkov nastavljeno kot »datum«. V evidenci strank je njihov rojstni dan vpisan kot »01/01/19777«. Sistem bo ta zapis označil kot poškodovan. Nekdo lahko v izvornem sistemu zdaj spremeni rojstni dan na »1977«. Po samodejnem osveževanju virov podatkov ima polje zdaj veljavno obliko in zapis bo odstranjen iz poškodovane entitete. 

Pojdite na **Podatki** > **Entitete** in v razdelku **Sistem** poiščite poškodovane entitete. Shema poimenovanja poškodovanih entitet: »DataSourceName_EntityName_corrupt«. Izberite poškodovan entitet, da prepoznate vsa poškodovana polja in razlog na ravni posameznega zapisa.
> [!div class="mx-imgBorder"]
> ![Razlog za korupcijo.](media/corruption-reason.png "Razlog za korupcijo")

Customer Insights še vedno obdeluje poškodovane zapise. Lahko pa povzročijo težave pri delu s poenotenimi podatki.

Za odkrivanje poškodovanih zapisov se izvajajo naslednja preverjanja uvoženih podatkov: 

- Vrednost polja se ne ujema z vrsto podatkov njegovega stolpca.
- Polja vsebujejo znake, zaradi katerih se stolpci ne ujemajo s pričakovano shemo. Na primer: napačno oblikovani narekovaji, nespremenjeni narekovaji ali znaki nove vrstice.
- Če obstajajo stolpci datetime/date/datetimeoffset, je treba njihov format določiti v modelu, če ne sledi standardnemu formatu ISO.


[!INCLUDE [footer-include](includes/footer-banner.md)]
