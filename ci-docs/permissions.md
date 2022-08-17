---
title: Dodeljevanje uporabniških dovoljenj
description: Preberite o dovoljenjih in uporabniških vlogah.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245439"
---
# <a name="assign-user-permissions"></a>Dodeljevanje uporabniških dovoljenj

Dostop do Customer Insights je omejen na uporabnike v vaši organizaciji, ki jih v aplikacijo doda skrbnik. Skrbnik lahko dodaja, ureja ali odstranjuje uporabnike. Uporabnik je lahko en sam uporabnik, skupina ali aplikacija. Obstajajo tri vrste vlog, ki jih lahko ima uporabnik:

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
- Popolna **Poenotenje podatkov** kar ima za posledico enotno entiteto profila stranke.
- Določite **odnose** in **dejavnosti**.
- Na strani **Segmenti** ustvarite segmente.
- Na strani **Mere** ustvarite mere.
- Upravljajte konfiguracijo in obogatite profile strank s strani **Obogatitev** (samo za obogatitve proizvajalca).
- Upravljajte in ustvarjajte izvoze na podlagi [povezave v skupni rabi s sodelavci](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Vsa dovoljenja, ki so na voljo sodelavcu.
- Spremenite nastavitve na **Sistem** strani, vključno z delovnim jezikom, urniki osveževanja za vaše sistemske procese in izvozom diagnostičnih dnevnikov.
- Spremenite nastavitve na **Varnost** strani, vključno z uporabniki, ključi API, zasebnimi povezavami in trezorjem ključev.
- Na strani **Kazalo za iskanje in filtriranje** (dostopna prek strani **Stranke**) nastavite definiciji iskanja in filtriranja za stran »Stranke«.
- Upravljajte povezave in jih dovolite za druge uporabniške vloge na strani **Povezave**.
- Upravljajte konfiguracijo in obogatite profile strank s strani **Obogatitev** (za vse obogatitve).
- Upravljajte in ustvarjajte izvoze na strani **Izvozi**.
- Namestite in uporabite **dodatek za kartice strank**.
- Dodajte in uporabite **povezovalnik Power Apps**.
- Omogočite uporabo [API-jev za Customer Insights](apis.md).
- [Dodelite lastništvo okolja](manage-environments.md#change-the-owner-of-an-environment) drugemu adminu.

## <a name="admin-owner"></a>Admin (lastnik)

- Vsa dovoljenja so na voljo skrbniku.
- [Ponastavi in izbriši](manage-environments.md#reset-an-existing-environment-preview) okolje.

## <a name="add-users"></a>Dodajanje uporabnikov

1. Pojdi do **skrbnik** > **Varnost** in izberite **Uporabniki** zavihek.

1. Izberite **Dodaj uporabnike**, da odprete podokno **Dodaj/uredi dovoljenja**.

1. Uporabi **Iskanje** polje za iskanje Azure Active Directory uporabnik ali skupina, ki jo želite dodati. Izberite možnost **Vloga**, da jo dodelite temu uporabniku ali skupini.

1. Izberite **Shrani**. Trenutno okolje se samodejno deli z uporabnikom ali člani skupine. Uporabniki lahko dostopajo do aplikacije Customer Insights in delajo v skladu s svojo določeno vlogo.

## <a name="view-current-permissions"></a>Prikaz trenutnih dovoljenj

Pojdi do **skrbnik** > **Varnost** in izberite **Uporabniki** za ogled seznama aktivnih uporabnikov in njihovih dodelitev vlog. Seznam uporabnikov lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete določenega uporabnika.

## <a name="manage-current-users"></a>Upravljanje trenutnih uporabnikov

Pojdi do **skrbnik** > **Varnost** in izberite **Uporabniki** zavihek. Seznam uporabnikov lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete uporabnika, ki ga želite upravljati.

Izberite uporabnika za ogled razpoložljivih dejanj.

- **Uredi** za urejanje vloge uporabnika v Customer Insights. Izberite **Shrani** za potrditev spremembe.
- **Odstrani** da uporabniku onemogočite dostop do Customer Insights. Izberite možnost **Izbriši**, da pordite izbris.

[!INCLUDE [footer-include](includes/footer-banner.md)]
