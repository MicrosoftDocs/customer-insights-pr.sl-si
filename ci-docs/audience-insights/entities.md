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
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596427"
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

## <a name="exploring-a-specific-entitys-data"></a>Raziskovanje podatkov določene entitete

Izberite entiteto za raziskovanje različnih polj in zapisov, vključenih v to entiteto.

> [!div class="mx-imgBorder"]
> ![Izbira entitete](media/data-manager-entities-data.png "Izbira entitete")

- Zavihek **Podatki** je izbran privzeto in prikazuje tabelo s podrobnostmi o posameznih zapisih entitete.

> [!div class="mx-imgBorder"]
> ![Tabela s polji](media/data-manager-entities-fields.PNG "Tabela s polji")

- Zavihek **Polja** prikazuje tabelo za pregled podrobnosti za izbrano entiteto, kot so imena polj, vrste podatkov in vrste. V stolpcu **Vrste** so prikazane vrste, povezane z modelom Common Data Model, ki jih sistem samodejno identificira ali jih uporabniki [ročno preslikajo](map-entities.md). To so semantične vrste, ki se lahko razlikujejo od vrst podatkov atributov – na primer spodnje polje *E-pošta* ima vrsto podatkov *Besedilo*, vendar je lahko njena (semantična) vrsta za Common Data Model *E-pošta* ali *E-poštni naslov*.

> [!NOTE]
> Obe tabeli prikazujeta samo vzorec podatkov vaše entitete. Če si želite ogledati celoten nabor podatkov, pojdite na stran **Viri podatkov**, izberite entiteto, izberite **Uredi**, nato pa si oglejte podatke te entitete z urejevalnikom Power Query, kot je pojasnjeno v temi [Viri podatkov](data-sources.md).

Če želite izvedeti več o podatkih, uvoženih v entiteto, vam stolpec **Povzetek** zagotavlja nekatere pomembne značilnosti podatkov, kot so vrednosti nič, manjkajoče vrednosti, edinstvene vrednosti, števila in porazdelitve, kot je primerno za vaše podatke.

Izberite ikono grafikona, če želite videti povzetek podatkov.

> [!div class="mx-imgBorder"]
> ![Simbol povzetka](media/data-manager-entities-summary.png "Tabela s povzetkom podatkov")

### <a name="next-step"></a>Naslednji korak

Glejte temo [Poenotenje](data-unification.md), če želite izvedeti več o *preslikavi*, *ujemanju* in *spajanju* uvoženih podatkov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]