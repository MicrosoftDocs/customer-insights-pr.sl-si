---
title: Uporabite soglasje stranke
description: Upoštevajte nastavitve privolitve strank v Customer Insights z uvozom podatkov o privolitvi.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947532"
---
# <a name="use-customer-consent"></a>Uporabite soglasje stranke

Predpisi o varstvu podatkov in zasebnosti dajejo posameznikom pravico, da urejajo, kako organizacija uporablja njihove osebne podatke. Primera takšnih predpisov sta Splošna uredba o varstvu podatkov v Evropski uniji ali Kalifornijski zakon o zasebnosti potrošnikov v Združenih državah. Ti predpisi ljudem omogočajo, da se odpovejo zbiranju, obdelavi ali delitvi njihovih osebnih podatkov s tretjimi osebami.  

Stranke se lahko odločijo, da umaknejo ali zavrnejo svoje soglasje za določene oblike stika. Prav tako lahko zahtevajo, da jih onemogočite za zbiranje, shranjevanje, uporabo ali prodajo njihovih osebnih podatkov. Pomembno je, da vaša organizacija spoštuje privolitev in preference glede zasebnosti vseh strank.  

Dynamics 365 Customer Insights vam pomaga izpolniti zahteve vaših strank z uvozom in shranjevanjem njihovih preferenc kot del enotnih profilov strank.

Če so podatki o privolitvi shranjeni ločeno od vaših profilov strank, [dodajte svoje podatke o privolitvi kot nov vir podatkov](#import-and-unify-consent-data). Vir podatkov, ki vsebuje podatke o privolitvi, je dodan v postopek združevanja podatkov. Uspešno poenotenje podatkov o privolitvi in profilov strank nato vodi do poenotenih profilov strank, ki vsebujejo informacije o privolitvi. Za profile strank, ki že vsebujejo podatke o soglasju, pojdite neposredno na [uporabite podatke o privolitvi](#use-consent-data) oddelek.

## <a name="prerequisites"></a>Zahteve

Za poenotenje podatkov o privolitvi z drugimi profili strank morajo biti v vaših izvornih podatkih na voljo naslednje informacije:

- Nadomestni ključ za preslikavo podatkov o privolitvi v uporabniške profile v storitvi Customer Insights. Na primer e-poštni naslov ali telefonska številka.
- Vrednost soglasja za določitev statusa privolitve stranke.

Razmislite o dodajanju naslednjega *neobvezno* informacije:

- Primarni ključ za posodobitev statusa privolitve, če stranka zahteva spremembo.
- Vrsta privolitve, če obstaja več načinov za obdelavo podatkov o stranki.
- Datum soglasja ali katera koli druga vrsta podatkov, ki so pomembni za vaše scenarije privolitve.

Primer tabele preproste baze podatkov o privolitvah z več možnostmi soglasja:

|ID soglasja (primarni ključ)   |E-pošta (nadomestni ključ)  |Možnost soglasja  |Vrednost soglasja  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  glasilo       |  Neresnično       |
|2    |  holly@contoso.com       |  Posodobitve izdelka       |  Resnično       |
|3    |  frank@contoso.com       |  glasilo       | Resnično        |
|4    |  frank@contoso.com       |  Posodobitve izdelka       |  Neresnično       |

## <a name="import-and-unify-consent-data"></a>Uvozite in poenotite podatke o privolitvi

Podatke o soglasju lahko uvozite na enak način, kot zaužijete druge vire podatkov v Customer Insights. Za več informacij o podprtih virih podatkov in o tem, kako jih uvoziti, glejte [Pregled virov podatkov](data-sources.md).

Za več informacij o poenotenju virov podatkov glejte [Pregled poenotenja podatkov](data-unification.md).

## <a name="use-consent-data"></a>Uporabite podatke o privolitvi

Ko so podatki o privolitvi del vaših enotnih profilov strank, jih lahko uporabite v storitvi Customer Insights. Ustvarite na primer segment s pravilom, da zagotovite, da upoštevate nastavitve zasebnosti in varstva podatkov vaših strank. Pravila, ki podpirajo nastavitve privolitve, se uporabljajo za izključitev uporabnikov iz segmenta na podlagi atributov profila. Dodajanje pravila segmentu, ki izključuje profile strank, ki niso dali soglasja za stik.

Glede na zgornjo vzorčno tabelo lahko segment vsebuje to pravilo:`Consent option=Newsletter & Consent value=True`. Rezultat te konfiguracije je segment, ki upošteva nastavitve stikov za pošiljanje glasila.

Za več informacij o gradbenih segmentih glejte [Ustvarite segmente](segment-builder.md).

Ko je segment ustvarjen, lahko uporabite enega od mnogih [možnosti izvoza](export-destinations.md) za uporabo segmenta v drugih aplikacijah.

## <a name="ensure-updated-consent-status"></a>Zagotovite posodobljeno stanje soglasja

Pomembno je, da posodobite status soglasja za vaše stranke. Načrtovana osvežitev v Customer Insights vedno uvozi najnovejše stanje vaših podatkovnih virov. Te informacije se nato obdelajo s poenotenjem podatkov in rezultirajo v posodobljenih profilih strank. Ti posodobljeni profili se nato uporabljajo za osvežitev segmentov, da zagotovimo, da delate z najnovejšimi informacijami.

Z drugimi besedami, poskrbite, da imajo izvorni podatki, ki se uvozijo v Customer Insights, vedno najnovejše informacije.

Za več informacij glejte [Ročno osvežite segmente](segments.md#refresh-segments) oz [konfigurirajte načrtovano osvežitev](system.md#schedule-tab).
