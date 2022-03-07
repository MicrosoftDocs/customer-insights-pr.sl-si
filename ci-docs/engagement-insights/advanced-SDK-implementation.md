---
title: Napredni scenariji s spletnimi kompleti za razvoj programske opreme
description: Napredni scenariji, ki jih je treba upoštevati pri instrumentaciji spletnega mesta s kompletom za razvoj programske opreme.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227218"
---
# <a name="advanced-web-sdk-instrumentation"></a>Napredna instrumentacija s spletnim kompletom za razvoj programske opreme

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ta članek vas vodi skozi napredne scenarije, ki jih je treba upoštevati pri [instrumentaciji spletnega mesta](instrument-website.md) s kompletom za razvoj programske opreme za zmogljivosti vpogledov v interakcije Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Nastavitev podrobnosti o uporabniku za vaš dogodek

Komplet za razvoj programske opreme vam omogoča, da določite podatke o uporabniku, ki jih je mogoče poslati z vsakim dogodkom. Podrobnosti o uporabniku lahko določite v lastnosti, ki se imenuje `user` (pričakovani podatki za to lastnost so predmet `IUser`), podobno kot `src`, `name` in `cfg` v konfiguraciji izrezka kode.

Predmet `IUser` vsebuje naslednje lastnosti niza:

- **localId**: uporabnikov lokalni ID.
- **authId**: ID s preverjeno pristnostjo uporabnika.
- **authType**: vrsta preverjanja pristnosti, ki se uporablja za pridobitev ID-ja s preverjeno pristnostjo uporabnika.
- **name**: ime uporabnika.
- **email**: e-poštni naslov uporabnika.

Naslednji primer prikazuje izrezek kode, ki pošilja podatke o uporabniku. Če vidite funkcijo, pred katero je zvezdica *, funkcijo zamenjajte z izvedbo po meri:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Podatke o uporabniku lahko določite tudi tako, da prikličete API `setUser(user: IUser)`. Telemetrija, poslana po priklicu API-ja `setUser`, bo vsebovala podatke o uporabniku.

## <a name="adding-custom-properties-for-each-event"></a>Dodajanje lastnosti po meri za vsak dogodek

Komplet za razvoj programske opreme vam omogoča, da določite lastnosti po meri, ki jih je mogoče poslati z vsakim dogodkom. Lastnosti po meri lahko določite kot predmet, ki vsebuje pare ključa – vrednosti (vrsta vrednosti je lahko `string | number | boolean`). Predmet lahko dodate v lastnost, imenovano `props`, podobno `src`, `name` in `cfg` v konfiguraciji izrezka kode.

Naslednji primer prikazuje izrezek kode, ki pošilja lastnosti po meri:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Lastnosti po meri lahko določite tudi posamezno tako, da prikličete API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Pošiljanje dogodkov po meri

Komplet za razvoj programske opreme lahko uporabite za pošiljanje dogodkov po meri. Določiti morate ime dogodka in lastnosti, ki jih želite poslati z dogodkom.

Naslednji primer prikazuje izrezek kode, ki sledi dogodku po meri. »NAME« je vrednost v ključu `name` v konfiguraciji izrezka. To je tudi ime spremenljivke v predmetu okna, kamor je naložen komplet za razvoj programske opreme.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
