---
title: Upravljanje uporabniških dovoljenj
description: Preberite o dovoljenjih in uporabniških vlogah.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a3d21d55d86950953611967bb66712312eb42b4b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355957"
---
# <a name="user-permissions"></a>Uporabniška dovoljenja

Stran **Dovoljenja** je kraj, kjer boste nastavili vloge in dovoljenja za uporabo vpogledov v občinstvo.

Za ogled strani morate imeti skrbniška dovoljenja. Če želite dostopati do strani z dovoljenji pri vpogledih v občinstvo, izberite **Skrbnik** > **Dovoljenja**.

Na voljo so tri vrste vlog:

## <a name="viewer"></a>Gledalec

- Raziščite vpoglede in segmente na straneh **Osnovno** in **Segmenti**.
- Na strani **Stranke** poiščite in filtrirajte profile strank. Polja morajo biti omogočena za iskanje.
- Ogled in raziskovanje strani **Obogatitev**.
- Na strani **Entitete** raziščite in izvozite entitete.
- Na strani **Sistem** si oglejte stanje sistemskih procesov.
- Oglejte si izvoze na strani **Izvozi**.
- Namestite in uporabite nadzorno ploščo **Power BI Customer Insights**.

## <a name="contributor"></a>Sodelujoči

- Vsa dovoljenja, ki so na voljo gledalcu.
- Na strani **Viri podatkov** naložite in preoblikujte podatke.
- Izpolnite razdelke *Poenotenje podatkov* (**Preslikava**, **Ujemanje** in **Spajanje**), ki ustvarijo entiteto poenotenega profila stranke.
- Določite **odnose** in **dejavnosti**.
- Na strani **Segmenti** ustvarite segmente.
- Na strani **Mere** ustvarite mere.
- Upravljajte konfiguracijo in obogatite profile strank s strani **Obogatitev** (samo za obogatitve proizvajalca).
- Upravljajte in ustvarjajte izvoze na podlagi povezav v skupni rabi s sodelavci. [Preberite več o tem, kako skrbniki dovolijo sodelavcem, da uporabljajo povezavo za izvoze](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Skrbnik

- Vsa dovoljenja, ki so na voljo sodelavcu.
- Spremenite nastavitve na strani **Sistem**, vključno z delovnim jezikom in urniki osveževanja za sistemske procese.
- Na strani **Dovoljenja** si oglejte in dodajte dovoljenja..
- Na strani **Kazalo za iskanje in filtriranje** (dostopna prek strani **Stranke**) nastavite definiciji iskanja in filtriranja za stran »Stranke«.
- Upravljajte povezave in jih dovolite za druge uporabniške vloge na strani **Povezave**.
- Upravljajte konfiguracijo in obogatite profile strank s strani **Obogatitev** (za vse obogatitve).
- Upravljajte in ustvarjajte izvoze na strani **Izvozi**.
- Namestite in uporabite **dodatek za kartice strank**.
- Dodajte in uporabite **povezovalnik Power Apps**.
- Omogočite uporabo [API-jev za Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Dodeljevanje vlog in dovoljenj

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Dovoljenja**.

1. Izberite **Dodaj uporabnike**, da odprete podokno **Dodaj/uredi dovoljenja**.

1. Uporabite polje **Iskanje**, da poiščete uporabnika ali skupino storitve Azure Active Directory, katere dovoljenja želite prilagoditi. Izberite možnost **Vloga**, da jo dodelite temu uporabniku ali skupini.

1. Izberite **Shrani**. Trenutno okolje bo samodejno v skupni rabi z uporabnikom ali člani skupine, katerih dovoljenja ste spremenili. Uporabniki lahko dostopajo do aplikacije Customer Insights in delajo v skladu s svojo določeno vlogo.

## <a name="view-current-permissions"></a>Prikaz trenutnih dovoljenj

V razdelku vpogledov v občinstvo odprite **Skrbnik** > **Dovoljenja**, da vidite, katere dodelitve vlog so trenutno aktivne.

- Stolpec **Vrsta** določa uporabnika, skupino ali aplikacijo. Sistem podpira posamezne uporabnike in skupine.
- Vloge so navedene pod stolpcem **Vloga**.
- Izberite kateri koli naslov stolpca, da rezultate razvrstite glede na vrednost tega stolpca.
- Za iskanje določenih uporabnikov uporabite polje **Iskanje** na vrhu strani.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
