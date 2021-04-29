---
title: Integracija spletnih podatkov iz vpogledov v interakcije z vpogledi v občinstvo
description: Prenesite spletne podatke o strankah iz vpogledov v interakcije v vpoglede v občinstvo.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896439"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integracija spletnih podatkov iz vpogledov v interakcije z vpogledi v občinstvo

Stranke pogosto opravljajo vsakodnevne transakcije prek spleta z uporabo spletnih mest. Zmožnost vpogledov v interakcije v storitvi Dynamics 365 Customer Insights je priročna rešitev za integracijo spletnih podatkov kot vira. Poleg možnosti ogleda transakcijskih, demografskih ali vedenjskih podatkov lahko dejavnosti v spletu vidimo v enotnih profilih strank. Ta profil lahko uporabimo za pridobitev dodatnih vpogledov, kot so segmenti, ukrepi ali predvidevanja za aktiviranje občinstva.

V tem članku so opisani koraki za prenos podatkov o spletnih dejavnostih vaših strank iz vpogledov v interakcije v vaše obstoječe okolje za vpoglede v občinstvo.

V tem primeru predpostavljamo okolje, ki vsebuje poenotene profile strank. Profili so poenoteni z viri iz anket, maloprodaje in sistema za izdajo zahtevkov. Prikazane so tudi povezane dejavnosti strank. 

Zdaj želimo vedeti, ali stranka obišče naše spletne lastnosti in razume njihove dejavnosti. Dejavnosti vključujejo na primer obisk spletnih mest ali ogled strani izdelkov na povezavi, prejeti v e-poštnem sporočilu.

## <a name="prerequisites"></a>Zahteve

Za vključitev podatkov iz vpogledov v interakcije je treba izpolniti nekaj predpogojev: 

- Integrirajte razvojni komplet SDK vpogledov v interakcije s svojim spletnim mestom. Za več informacij glejte razdelek [Začetek s spletnim razvojnim paketom SDK](../engagement-insights/instrument-website.md).
- Izvoz spletnih dogodkov iz vpogledov v interakcije zahteva dostop do računa za shrambo ADLS Gen 2, ki bo uporabljen za vključevanje podatkov o spletnih dogodkih v vpoglede v občinstvo. Če želite izvedeti več, glejte razdelek [Izvoz dogodkov](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfiguracija izpopolnjenih dogodkov v vpogledih v interakcije

Za tem ko skrbnik v spletno mesto vgradi razvojni paket SDK iz vpogledov v interakcije, se *osnovni dogodki* zbirajo, ko si uporabnik ogleda spletno stran ali nekam klikne. Osnovni dogodki običajno vsebujejo številne podrobnosti. Odvisno od posameznega primera uporabe potrebujete le ustrezno podmnožico podatkov iz osnovnega dogodka. Vpogledi v interakcije vam omogočajo ustvariti *izpopolnjene dogodke*, ki vsebujejo le lastnosti osnovnega dogodka, ki ga izberete.     

Za več informacij glejte razdelek [Ustvarjanje in spreminjanje izpopolnjenih dogodkov](../engagement-insights/refined-events.md).

Kaj je treba upoštevati pri ustvarjanju izpopolnjenih dogodkov: 

- Navedite smiselno ime za izpopolnjeni dogodek. Uporablja se kot ime dejavnosti v vpogledih v občinstvo.
- Izberite vsaj naslednje lastnosti, da ustvarite dejavnost v vpogledih v občinstvo: 
    - Signal.Action.Name – označuje podrobnosti o dejavnosti
    - Signal.User.Id – uporablja se za preslikavo z ID-jem stranke
    - Signal.View.Uri – uporablja se kot spletni naslov za podlago za segmente ali mere
    - Signal.Export.Id – uporablja se kot primarni ključ za dogodke
    - Signal.Timestamp – uporablja se za določitev datuma in ure dejavnosti

Izberite filtre, da se osredotočite na dogodke in strani, ki so pomembne za posamezen primer uporabe. V tem primeru bomo uporabili ime dejanja »Posredovanje e-pošte«.

## <a name="export-the-refined-web-events"></a>Izvozi izpopolnjenih spletnih dogodkov 

Po določitvi izpopolnjenega dogodka morate konfigurirati izvoz podatkov o dogodku v shrambo Azure Data Lake Storage, ki jo lahko v vpogledih v občinstvo nastavite kot vir podatkov za vključevanje. Do izvozov prihaja nenehno, ko so v povezavi s spletnimi lastnostmi ustvarjeni dogodki.

Če želite izvedeti več, glejte razdelek [Izvoz dogodkov](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Vključevanje podatkov o dogodkih v vpoglede v občinstvo

Ko določite izpopolnjeni dogodek in konfigurirate njegov izvoz, lahko nadaljujemo z vključevanjem podatkov v vpoglede v občinstvo. Na podlagi mape Common Data Model morate ustvariti nov vir podatkov. Vnesite podrobnosti za račun za shrambo, v katero izvažate dogodke. V datoteki *default.cdm.json* izberite izpopolnjeni dogodek, ki ga želite vključiti, in ustvarite entiteto v vpogledih v občinstvo.

Za več informacij glejte razdelek [Vzpostavitev povezave z mapo Common Data Model z računom Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Povezovanje podatkov o izpopolnjenih dogodkih kot dejavnost profila stranke

Po končanem vključevanju entitete lahko konfigurirate dejavnost za profil stranke.

Za več informacij glejte [Dejavnosti stranke](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Stran z dejavnosti z razširjenim podoknom za urejanje in izpolnjenimi polji.":::

Novo aktivnost konfigurirajte z naslednjim preslikavanjem: 

- **Primarni ključ:** Signal.Export.Id, edinstven ID, ki je na voljo za vsak zapis dogodka v vpogledih v interakcije. Ta lastnost se samodejno generira.

- **Časovni žig:** Signal.Timestamp v lastnosti dogodka

- **Dogodek:** Signal.Name, ime dogodka, ki mu želite slediti

- **Spletni naslov:** Signal.View.Uri, sklic na URL strani, ki je ustvarila dogodek.

- **Podrobnosti:** Signal.Action.Name za predstavljanje podatkov za povezovanje z dogodkom Izbrana lastnost v tem primeru označuje, da gre za posredovanje e-pošte.

- **Vrsta dejavnosti:** v tem primeru izberemo obstoječo vrsto dejavnosti WebLog. Ta izbira je uporabna možnost filtriranja za zagon modelov za predvidevanje ali ustvarjanje segmentov na podlagi te vrste dejavnosti.

- **Nastavitev odnosa:** ta pomembna nastavitev dejavnost veže na obstoječe profile strank. **Signal.User.Id** je identifikator, konfiguriran v razvojnem paketu SDK, ki ga je treba zbirati, in se nanaša na ID uporabnika v drugih virih podatkov, ki so konfigurirani v vpogledih v občinstvo. V tem primeru konfiguriramo odnos med elementom Signal.User.Id in elementom RetailCustomers:CustomerRetailId, ki je primarni ključ, ki je bil v določen v koraku preslikavanja v postopku poenotenja podatkov.


Po obdelavi dejavnosti lahko pregledate zapise strank in odprete kartico stranke, da si na časovnici ogledate dejavnosti iz vpogledov v interakcije. 

> [!TIP]
> Če želite poiskati ID stranke, ki ima dejavnost v vpogledih v interakcije, odprite razdelek **Entitete** in si oglejte predogled podatkov za entiteto UnifiedActivity. ActivityTypeDisplay = WebLog vsebuje dejavnosti vpogledov v interakcije, konfigurirane v zgornjem primeru. Na strani **Stranke** kopirajte ID stranke za enega od teh zapisov in za ta ID.

## <a name="next-steps"></a>Naslednji koraki

Zdaj lahko ustvarjate [segmente](segments.md), [mere](measures.md) in [predvidevanja](predictions.md), da se pomenljivo povežete s svojimi strankami.


[!INCLUDE[footer-include](../includes/footer-banner.md)]