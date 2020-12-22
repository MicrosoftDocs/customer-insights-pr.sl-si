---
title: Konfiguracija sistema pri vpogledih v občinstvo
description: Preberite več o sistemskih nastavitvah pri zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406991"
---
# <a name="system-configuration"></a>Konfiguracija sistema

Stran **Sistem** vključuje štiri zavihke: **Stanje**, **Razpored**, **Vizitka** in **Splošno**.

> [!div class="mx-imgBorder"]
> ![Stran sistema](media/system-tabs.png "Stran sistema")

## <a name="status-tab"></a>Zavihek stanja

**Zavihek stanja** omogoča spremljanje napredka uvoza podatkov, izvozov podatkov in več pomembnih procesov izdelkov. Preglejte informacije na tem zavihku, da zagotovite popolnost aktivnih procesov.

Ta zavihek vključuje tabele stanja za **Vire podatkov**, **Sistemske procese** in **Pripravo podatkov**. Vsaka tabela spremlja **Ime** opravila in njegove ustrezne entitete, **Stanje** njegovega zadnjega izvajanja in datum **Zadnje posodobitve**.

Oglejte si podrobnosti o zadnjih nekaj izvedbah opravila tako, da izberete njegovo ime.

### <a name="status-types"></a>Vrste stanj

Na voljo je šest vrst stanja za opravila. Na straneh *Ujemanje*, *Spajanje*, *Viri podatkov*, *Segmenti*, *Mere*, *Obogatitev*, *Dejavnosti* in *Predvidevanja* so prikazane tudi naslednje vrste stanj:

- **Obdelava:** opravilo je v teku. Stanje se lahko spremeni v »Uspešno« ali »Neuspešno«.
- **Uspešno:** opravilo je bilo uspešno dokončano.
- **Preskočeno:** opravilo je bilo preskočeno. Eden ali več nadaljnjih postopkov, od katerih je odvisno opravilo, ne uspe ali ste jih preskočili.
- **Neuspešno:** obdelava opravila ni uspela.
- **Preklicano:** uporabnik je obdelavo preklical, še preden se je končala.
- **V čakalni vrsti:** obdelava je v čakalni vrsti in se bo začela, ko bodo dokončana vsa nadaljnja opravila. Če želite več informacij, si oglejte [pravilnike o osveževanju](#refresh-policies).

### <a name="refresh-policies"></a>Pravilniki osveževanja

Ta seznam prikazuje pravilnike osveževanja za vsak glavni postopek:

- **Viri podatkov:** zagon v skladu s [konfiguriranim razporedom](#schedule-tab). Ni odvisno od nobenega drugega postopka. Ujemanje je odvisno od uspešnega dokončanja tega postopka.
- **Ujemanje:** zagon v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od obdelave virov podatkov, uporabljenih v definiciji ujemanja. Spajanje je odvisno od uspešnega dokončanja tega postopka.
- **Spajanje:** zagon v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od dokončanja postopka ujemanja. Segmenti, mere, obogatitev, iskanje, dejavnosti, predvidevanja in priprava podatkov so odvisni od uspešnega dokončanja tega postopka.
- **Segmenti**: zažene se ročno (enkratna osvežitev) in v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od spajanja. Vpogledi so odvisni od njegove obdelave.
- **Mere**: zažene se ročno (enkratna osvežitev) in v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od spajanja.
- **Dejavnosti**: zažene se ročno (enkratna osvežitev) in v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od spajanja.
- **Obogatitev**: zažene se ročno (enkratna osvežitev) in v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od spajanja.
- **Iskanje**: zažene se ročno (enkratna osvežitev) in v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od spajanja.
- **Priprava podatkov**: zagon v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno je od spajanja.
- **Vpogledi**: zažene se ročno (enkratna osvežitev) in v skladu s [konfiguriranim razporedom](#schedule-tab). Odvisno od segmentov.

Izberite stanje opravila, da si lahko ogledate podrobnosti o napredku celotnega posla, v katerega je bilo vključeno. Zgoraj navedeni pravilniki osveževanja lahko pripomorejo pri razumevanju, kaj lahko storite glede opravila, ki je bilo **Preskočeno** ali **V čakalni vrsti**.

## <a name="schedule-tab"></a>Zavihek razporeda

Uporabite zavihek **Razpored** za razporejanje samodejnih osveževanj za vse [vnesene vire podatkov](data-sources.md). Samodejno osveževanje pomaga zagotoviti, da se posodobitve iz virov podatkov odražajo v vaših poenotenih profilih strank.

1. Pri vpogledih v občinstvo odprite **Skrbnik** > **Sistem** in izberite zavihek **Razpored**.

2. Privzeto stanje za načrtovano osvežitev je **Izklopljeno**. Če želite omogočiti razporejena osveževanja, spremenite preklop na vrhu zaslona na **Vklopljeno**.

3. Za osveževanja lahko izberete **Tedensko** (privzeto) in **Dnevno**. Če nameravate razporediti tedenska osveževanja, izberite en ali več dni, ko želite zagnati osveževanje.

4. Nastavite svoj **Časovni pas**, nato uporabite spustni meni **Ura**, da nastavite uro osveževanja. Ko končate, izberite **Nastavi**. Če želite razporediti več osveževanj v enem dnevu, izberite **Dodajte drug čas**.

5. Če želite uporabiti spremembe, izberite **Shrani**.

## <a name="about-tab"></a>Zavihek vizitke

Zavihek **Več o tem** vsebuje **Prikazno ime** vaše organizacije, dejavni **ID okolja**, **Regijo** in tvoj **ID seje**. Če imate več delovnih okolij, morate vsakemu dati zlahka prepoznavno prikazno ime.

## <a name="general-tab"></a>Zavihek Splošno

V zavihku **Splošno** sta na voljo dve možnosti, **Jezik** in **Oblika zapisa države/regije**.

Aplikacija [podpira številne jezike](supported-languages.md). Če želite spremeniti izbrani jezik, na spustnem meniju izberite možnost **Jezik**.

Če želite spremeniti izbrano oblikovanje datumov, časa in številk, uporabite spustni meni **Oblika zapisa države/regije**. Pod tem poljem se prikaže predogled oblikovanja. Sistem bo samodejno predlagal izbiro, ko izberete nov jezik.

Izberite **Shrani**, da potrdite izbiro.

## <a name="api-usage-tab"></a>Zavihek uporabe API-ja

Poiščite podrobnosti o uporabi API-ja v realnem času in si oglejte, kateri dogodki so se zgodili v določenem časovnem obdobju. Za več informacij glejte [Uvoz podatkov v realnem času](real-time-data-ingestion.md).
