---
title: Prepoznavanje spletnih dogodkov obiskovalcev s preverjeno pristnostjo s funkcijo iz neznanega v znano
description: Funkcija iz neznanega v znano vam omogoča, da dogodke na spletnem mestu povežete z obiskovalci, katerih pristnost je v preteklosti že bila preverjena.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036803"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Prepoznavanje spletnih dogodkov obiskovalcev s preverjeno pristnostjo s funkcijo iz neznanega v znano

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcija **Iz neznanega v znano** v možnosti vpogleda v interakcije omogoča povezovanje dogodkov na spletnem mestu z obiskovalci, katerih pristnost je že bila preverjena. Če je funkcija onemogočena, obiskovalci, ki so opravili preverjanje pristnosti med prejšnjim obiskom in nato odšli, niso prepoznani, če ob prihodu znova ne preverijo svoje pristnosti. 

Na primer, oseba je prejšnji teden obiskala spletno mesto, se na spletnem mestu prijavila v svoj uporabniški račun in brskala po katalogu izdelkov. Oseba se naslednji teden vrne, da bi brskala po več izdelkih, vendar brez prijave v svoj račun. Lastnik spletnega mesta bi z uporabo funkcije **Iz neznanega v znano** vedel, da se je vrnila ista oseba in kaj je počela na spletnemu mestu. To omogoča natančnejše poročanje in analizo dejavnosti spletnega mesta.

## <a name="enable-unknown-to-known"></a>Omogočanje funkcije iz neznanega v znano

Za omogočanje te funkcije morate biti [skrbnik delovnega prostora](user-roles.md). 

1. V vpogledih v interakcije pojdite na **Skrbnik** > **Delovni prostor**. 
2. Izberite zavihek **Nastavitve**.
3. V razdelku **Iz neznanega v znano** preklopite na **Omogočeno**.

![Omogočanje funkcije iz neznanega v znano](media/U2Ktoggle.png "Omogočanje funkcije iz neznanega v znano")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Dodajanje kode JavaScript izrezku za sledenje na vašem spletnem mestu

Spletno mesto lahko zajame **user authId** z naslednjim vzorcem JavaScript, z uporabo [vpogledov v interakcije spletnega kompleta za razvoj programske opreme](advanced-SDK-implementation.md). Da bi funkcija **Iz neznanega v znano** delovala, morate zajeti authId *in* v svojem izrezku JavaScript omogočiti userMapping:True, kot je prikazano v spodnjem vzorcu.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
