---
title: Entitete in nabori podatkov
description: Oglejte si podatke na strani Entitete.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 137de726b243b501491fcbe7866820aaee26097fcf379270c423c277374ae9a4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033835"
---
# <a name="entities-in-audience-insights"></a>Entitete pri vpogledih v občinstvo

Po [konfiguraciji virov podatkov](data-sources.md) pojdite na stran **Entitete**, da ocenite kakovost uvoženih podatkov. Entitete se štejejo za nabore podatkov. Več zmožnosti storitve Dynamics 365 Customer Insights je ustvarjenih v povezavi s temi entitetami. Njihov natančen pregled vam lahko pomaga preveriti veljavnost rezultatov teh zmogljivosti.

Na strani **Entitete** so navedene entitete, vključuje pa tudi več stolpcev:

- **Ime**: ime vaše entitete podatkov. Če poleg imena entitete vidite opozorilni simbol, to pomeni, da se podatki za to entiteto niso uspešno naložili.
- **Vir**: vrsta vira podatkov, v katerega je uvožena entiteta
- **Ustvaril/-a**: ime osebe, ki je ustvarila entiteto.
- **Ustvarjeno**: datum in ura nastanka entitete.
- **Posodobil/-a**: ime osebe, ki je posodobila entiteto.
- **Zadnja posodobitev**: datum in ura zadnje posodobitve entitete.
- **Zadnja osvežitev**: datum in ura zadnje osvežitve podatkov.

## <a name="explore-a-specific-entitys-data"></a>Raziskovanje podatkov določene entitete

Izberite entiteto za raziskovanje različnih polj in zapisov, vključenih v to entiteto.

> [!div class="mx-imgBorder"]
> ![Izberite entiteto.](media/data-manager-entities-data.png "Izberite entiteto")

- Zavihek **Podatki** prikazuje tabelo s podrobnostmi o posameznih zapisih entitete.

> [!div class="mx-imgBorder"]
> ![Tabela s polji.](media/data-manager-entities-fields.PNG "Tabela s polji")

- Zavihek **Atributi** je privzeto izbran in prikazuje tabelo za pregled podrobnosti za izbrano entiteto, kot so imena polj, vrste podatkov in vrste. V stolpcu **Vrste** so prikazane vrste, povezane z modelom Common Data Model, ki jih sistem samodejno identificira ali jih uporabniki [ročno preslikajo](map-entities.md). Te vrste so semantične vrste, ki se lahko razlikujejo od vrst podatkov atributov. Na primer spodnje polje *E-pošta* ima vrsto podatkov *Besedilo*, vendar je njegova (semantična) vrsta modela Common Data Model lahko *E-pošta* ali *E-poštni naslov*.

> [!NOTE]
> Obe tabeli prikazujeta samo vzorec podatkov vaše entitete. Če si želite ogledati celoten nabor podatkov, pojdite na stran **Viri podatkov**, izberite entiteto, izberite **Uredi**, nato pa si oglejte podatke te entitete z urejevalnikom Power Query, kot je pojasnjeno v temi [Viri podatkov](data-sources.md).

Če želite izvedeti več o podatkih, uvoženih v entiteto, vam stolpec **Povzetek** zagotavlja nekatere pomembne značilnosti podatkov, kot so vrednosti nič, manjkajoče vrednosti, edinstvene vrednosti, števila in porazdelitve, kot je primerno za vaše podatke.

Izberite ikono grafikona, če želite videti povzetek podatkov.

> [!div class="mx-imgBorder"]
> ![Simbol povzetka.](media/data-manager-entities-summary.png "Tabela s povzetkom podatkov")

## <a name="entity-specific-information"></a>Informacije o določeni entiteti

V naslednjem razdelku najdete informacije o nekaterih entitetah, ki jih je ustvaril sistem.

### <a name="corrupted-data-sources"></a>Poškodovani viri podatkov

Polja iz uvoženega vira podatkov lahko vsebujejo poškodovane podatke. Zapisi s poškodovanimi polji so na voljo v entitetah, ki jih je ustvaril sistem. Poznavanje poškodovanih zapisov vam pomaga ugotoviti, katere podatke morate pregledati in posodobiti v izvornem sistemu. Po naslednji osvežitvi vira podatkov se popravljeni zapisi uvozijo v Customer Insights in posredujejo v postopke iz strežnika. 

Na primer stolpec »rojstni dan« ima vrsto podatkov nastavljeno kot »datum«. V evidenci strank je njihov rojstni dan vpisan kot »01/01/19777«. Sistem bo ta zapis označil kot poškodovan. Nekdo lahko v izvornem sistemu zdaj spremeni rojstni dan na »1977«. Po samodejnem osveževanju virov podatkov ima polje zdaj veljavno obliko in zapis bo odstranjen iz poškodovane entitete. 

Pojdite na **Podatki** > **Entitete** in v razdelku **Sistem** poiščite poškodovane entitete. Shema poimenovanja poškodovanih entitet: »DataSourceName_EntityName_corrupt«.

Customer Insights še vedno obdeluje poškodovane zapise. Lahko pa povzročijo težave pri delu s poenotenimi podatki.

Za odkrivanje poškodovanih zapisov se izvajajo naslednja preverjanja uvoženih podatkov: 

- Vrednost polja se ne ujema z vrsto podatkov njegovega stolpca.
- Polja vsebujejo znake, zaradi katerih se stolpci ne ujemajo s pričakovano shemo. Na primer: napačno oblikovani narekovaji, nespremenjeni narekovaji ali znaki nove vrstice.
- Če obstajajo stolpci za premik datetime/date/datetimeoffset, je treba v modelu določiti njihovo obliko, če model ne sledi standardnemu formatu ISO.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
