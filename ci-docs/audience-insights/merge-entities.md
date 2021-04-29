---
title: Združevanje entitet za poenotenje podatkov
description: Združite entitete za ustvarjanje poenotenih profilov strank.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896531"
---
# <a name="merge-entities"></a>Združevanje entitet

Faza spajanja je zadnja faza v postopku poenotenja podatkov. Njen namen je uskladitev podatkov v sporu. Primer podatkov v sporu je na primer ime stranke, ki ga najdemo v dveh zbirkah podatkov, vendar je v vsaki prikazan nekoliko drugače (»Grant Marshall« v primerjavi z »Grant Marshal«), ali telefonska številka, ki se razlikuje v obliki zapisa (617-803-091X v primerjavi s 617803091X). Spajanje teh podatkovnih točk v sporu poteka na osnovi »atribut za atributom«.

Po zaključku [faze ujemanja](match-entities.md) fazo spajanja začnete tako, da izberete ploščico **Spajanje** na strani **Poenotenje**.

## <a name="review-system-recommendations"></a>Pregled priporočil sistema

Na strani **Spajanje** izberete in izključite atribute, ki jih je treba spojiti v entiteti poenotenega profila stranke (rezultat postopka konfiguracije). Sistem samodejno spoji nekatere atribute.

### <a name="view-merged-attributes"></a>Prikaz spojenih atributov

Če si želite ogledati atribute, ki so vključeni v enega od samodejno spojenih atributov, izberite spojen atribut. Atributa, ki sestavljata ta spojeni atribut, sta prikazana v dveh novih vrsticah pod spojenim atributom.

> [!div class="mx-imgBorder"]
> ![Izbira spojenega atributa](media/configure-data-merge-profile-attributes.png "Izbira spojenega atributa")

### <a name="separate-merged-attributes"></a>Ločevanje spojenih atributov

Če želite ločiti oz. razdružiti samodejno spojene atribute, poiščite atribut v tabeli **Atributi profila**.

1. Izberite gumb treh pik (...).
  
2. V spustnem seznamu izberite **Loči polja**.

### <a name="remove-merged-attributes"></a>Odstranjevanje spojenih atributov

Če želite izključiti atribut iz entitete končnega profila stranke, ga poiščite v tabeli **Atributi profila**.

1. Izberite gumb treh pik (...).
  
2. V spustnem seznamu izberite **Ne spoji**.

   Atribut je premaknjen v razdelek **Odstranjeno iz zapisa stranke**.

## <a name="manually-add-a-merged-attribute"></a>Ročno dodajanje spojenega atributa

Če želite dodati spojeni atribut, pojdite na stran **Spajanje**.

1. Izberite **Dodaj spojeni atribut**.

2. Vnesite **ime**, da ga boste pozneje prepoznali na strani **Spajanje**.

3. Vnesete lahko tudi **Prikazno ime**, ki bo prikazano v entiteti poenotenega profila stranke.

4. Konfigurirajte možnost **Izberi podvojene atribute**, da izberete atribute, ki jih želite spojiti iz ujemajočih se entitet. Atribute lahko tudi poiščete.

5. Nastavite **Uvrstitev po pomembnosti** za prednostno obravnavanje določenega atributa pred drugimi. Če entiteta *WebAccountCSV* vključuje najbolj natančne podatke o atributu *Polna imena*, lahko prednostno obravnavate to entiteto pred entiteto *ContactCSV* tako, da izberete *WebAccountCSV*. Entiteta *WebAccountCSV* tako postane prva prioriteta, entiteta *ContactCSV* pa druga prioriteta pri klicanju vrednosti za atribut *Polno ime*.

## <a name="run-your-merge"></a>Zagon spajanja

Ne glede na to, ali atribute spajate ročno ali jih spoji sistem, lahko vedno zaženete spajanje. Za začetek postopka izberite **Zaženi** na strani **Spajanje**.

> [!div class="mx-imgBorder"]
> ![Shranjevanje in zagon spajanja podatkov](media/configure-data-merge-save-run.png "Shranjevanje in zagon spajanja podatkov")

Če želite vnesti dodatne spremembe in ponovno zagnati korak, lahko prekličete spajanje v teku. Izberite **Osveževanje ...**, nato pa **Prekliči posel** v stranskem podoknu, ki se prikaže.

Po tem, ko se napis **Osveževanje ...** se spremeni v **Uspešno**, je spajanje dokončalo in razrešilo nasprotja v vaših podatkih v skladu z določenimi pravilniki. Spojeni in nespojeni atributi so vključeni v entiteto poenotenega profila. Izključeni atributi niso vključeni v entiteto poenotenega profila.

Če to vaša prva uspešna izvedba spajanja, se bodo vsi nadaljnji postopki, vključno z obogatitvijo, segmentacijo in merami, samodejno znova zagnali. Po ponovnem zagonu vseh nadaljnjih postopkov bodo v profilih strank prikazane vaše spremembe.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="next-step"></a>Naslednji korak

Za pridobitev več vpogledov v stranke konfigurirajte možnosti [Dejavnosti](activities.md), [Obogatitev](enrichment-hub.md) ali [Odnosi](relationships.md).

Če ste že konfigurirali dejavnosti, obogatitev ali odnose ali če ste opredelili segmente, bodo samodejno obdelani za uporabo najnovejših podatkov strank.




[!INCLUDE[footer-include](../includes/footer-banner.md)]