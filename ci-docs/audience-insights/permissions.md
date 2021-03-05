---
title: Upravljanje uporabniških dovoljenj
description: Preberite o dovoljenjih in uporabniških vlogah.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f7fcecdea8dc49666dd5c45bf4109c205993f326
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268430"
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
- Izvozite segmente s strani **Segmenti**.
- Namestite in uporabite nadzorno ploščo **Power BI Customer Insights**.

## <a name="contributor"></a>Sodelavec

- Vsa dovoljenja, ki so na voljo gledalcu.
- Na strani **Viri podatkov** naložite in preoblikujte podatke.
- Izpolnite razdelke *Poenotenje podatkov* (**Preslikava**, **Ujemanje** in **Spajanje**), ki ustvarijo entiteto poenotenega profila stranke.
- Določite **odnose** in **dejavnosti**.
- Na strani **Segmenti** ustvarite segmente.
- Na strani **Mere** ustvarite mere.
- Upravljajte konfiguracijo in obogatite profile strank s strani **Obogatitev** (samo za obogatitve proizvajalca).

## <a name="administrator"></a>Skrbnik

- Vsa dovoljenja, ki so na voljo sodelavcu.
- Spremenite nastavitve na strani **Sistem**, vključno z delovnim jezikom in urniki osveževanja za sistemske procese.
- Na strani **Dovoljenja** si oglejte in dodajte dovoljenja..
- Na strani **Kazalo za iskanje in filtriranje** (dostopna prek strani **Stranke**) nastavite definiciji iskanja in filtriranja za stran »Stranke«.
- Na strani **Cilji za izvoz** določite cilje segmenta aplikacije Dynamics 365 Sales.
- Upravljajte konfiguracijo in obogatite profile strank s strani **Obogatitev** (za vse obogatitve).
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