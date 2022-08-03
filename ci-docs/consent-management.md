---
title: Uporabite soglasje stranke
description: Upoštevajte nastavitve soglasja svojih strank v Customer Insights z uvozom podatkov o soglasju.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188068"
---
# <a name="use-customer-consent"></a>Uporabite soglasje stranke

Predpisi o varstvu podatkov in zasebnosti dajejo posameznikom pravico do urejanja, kako organizacija uporablja njihove osebne podatke. Primeri takih predpisov so Splošna uredba o varstvu podatkov v Evropski uniji ali Kalifornijski zakon o zasebnosti potrošnikov v Združenih državah. Ti predpisi ljudem omogočajo, da zavrnejo zbiranje, obdelavo ali deljenje njihovih osebnih podatkov s tretjimi osebami.  

Stranke se lahko odločijo, da umaknejo ali zavrnejo svoje soglasje za določene oblike stika. Prav tako lahko zahtevajo, da jim onemogočite zbiranje, shranjevanje, uporabo ali prodajo njihovih osebnih podatkov. Pomembno je, da vaša organizacija spoštuje soglasje in nastavitve zasebnosti vseh strank.  

Dynamics 365 Customer Insights vam pomaga izpolniti zahteve vaših strank z uvozom in shranjevanjem njihovih preferenc kot dela poenotenih profilov strank.

Če so podatki o soglasju shranjeni ločeno od vaših profilov strank, [dodajte svoje podatke o soglasju kot nov vir podatkov](#import-and-unify-consent-data). Vir podatkov, ki vsebuje podatke o soglasju, je dodan v postopek poenotenja podatkov. Uspešno poenotenje podatkov o soglasju in profilov strank nato vodi do enotnih profilov strank, ki vsebujejo informacije o soglasju. Za profile strank, ki že vsebujejo informacije o soglasju, pojdite neposredno na [uporabi podatke o privolitvi](#use-consent-data) razdelek.

## <a name="prerequisites"></a>Zahteve

Za poenotenje podatkov o soglasju z drugimi profili strank morajo biti v vaših izvornih podatkih na voljo naslednje informacije:

- Nadomestni ključ za preslikavo informacij o soglasju v uporabniške profile v Customer Insights. Na primer e-poštni naslov ali telefonsko številko.
- Vrednost soglasja za določitev statusa soglasja stranke.

Razmislite o dodajanju naslednjega *neobvezno* informacije:

- Primarni ključ za posodobitev stanja soglasja, če stranka zahteva spremembo.
- Vrsta soglasja, če obstaja več kot en način obdelave podatkov o strankah.
- Datum privolitve ali katera koli druga vrsta podatkov, ki je pomembna za vaše scenarije privolitve.

Primer tabele preproste zbirke podatkov o soglasjih z več možnostmi soglasja:

|ID privolitve (primarni ključ)   |E-pošta (nadomestni ključ)  |Možnost privolitve  |Vrednost soglasja  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Glasilo       |  Neresnično       |
|2    |  holly@contoso.com       |  Posodobitve izdelka       |  Resnično       |
|3    |  frank@contoso.com       |  Glasilo       | Resnično        |
|4    |  frank@contoso.com       |  Posodobitve izdelka       |  Neresnično       |

## <a name="import-and-unify-consent-data"></a>Uvozite in poenotite podatke o soglasju

Uvozite podatke o soglasju na enak način, kot vnašate druge vire podatkov v Customer Insights. Za več informacij o podprtih virih podatkov in o tem, kako jih uvoziti, glejte [Pregled podatkovnih virov](data-sources.md).

Za več informacij o poenotenju virov podatkov glejte [Pregled poenotenja podatkov](data-unification.md).

## <a name="use-consent-data"></a>Uporabite podatke o soglasju

Ko so vaši podatki o soglasju del vaših poenotenih profilov strank, jih lahko uporabite v Customer Insights. Na primer, ustvarite segment s pravilom, da zagotovite, da spoštujete nastavitve zasebnosti in varstva podatkov svojih strank. Pravila, ki podpirajo nastavitve soglasja, se uporabljajo za izključitev uporabnikov iz segmenta na podlagi atributov profila. Segmentu dodajte pravilo, ki izključuje profile strank, ki niso dale soglasja za stik.

Glede na zgornjo vzorčno tabelo lahko segment vsebuje to pravilo:`Consent option=Newsletter & Consent value=True`. Posledica te konfiguracije je segment, ki upošteva nastavitve stika za pošiljanje glasila.

Za več informacij o gradnji segmentov glejte [Ustvarite segmente](segment-builder.md).

Ko je segment ustvarjen, lahko uporabite enega od mnogih [možnosti izvoza](export-destinations.md) za uporabo segmenta v drugih aplikacijah.

## <a name="ensure-updated-consent-status"></a>Zagotovite posodobljen status soglasja

Pomembno je, da status soglasja za vaše stranke posodabljate. Načrtovana osvežitev v Customer Insights vedno uvozi najnovejše stanje vaših podatkovnih virov. Te informacije se nato obdelajo s poenotenjem podatkov in povzročijo posodobljene profile strank. Ti posodobljeni profili se nato uporabijo za osveževanje segmentov, da se zagotovi, da delate z najsodobnejšimi informacijami.

Z drugimi besedami, zagotovite, da imajo izvorni podatki, ki se uvozijo v Customer Insights, vedno najnovejše informacije.

Za več informacij glejte [Ročno osveži segmente](segments.md#refresh-segments) oz [konfigurirajte načrtovano osvežitev](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
