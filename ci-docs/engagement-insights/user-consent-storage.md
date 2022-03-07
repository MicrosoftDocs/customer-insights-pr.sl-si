---
title: Upravljanje piškotkov in privolitve uporabnika za shranjevanje uporabniških podatkov v aplikaciji Dynamics 365 Customer Insights
description: Preberite, kako se uporabljajo piškotki in soglasja uporabnikov za prepoznavanje obiskovalcev spletnega mesta.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229005"
---
# <a name="manage-cookies-and-user-consent"></a>Upravljanje piškotkov in soglasje uporabnikov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Možnost vpogledov v interakcije aplikacije Dynamics 365 Customer Insights uporablja piškotke in ključe (`localStorage`) za prepoznavanje obiskovalcev spletnega mesta.

Piškotki so majhne datoteke, ki shranjujejo delčke informacij o interakcijah uporabnika s spletnim mestom. Shranjeni so v spletnih brskalnikih. Ko uporabniki obiščejo spletno mesto, za katerega imajo shranjene piškotke, brskalnik te podatke pošlje strežniku, ki vrne informacije, edinstvene za uporabnika. To je tehnologija, ki omogoča na primer, da spletni nakupovalni voziček obdrži izbrane predmete, tudi če uporabnik zapusti spletno mesto.

## <a name="user-consent"></a>Soglasje uporabnika

[Splošna uredba o varstvu podatkov (GDPR)](/dynamics365/get-started/gdpr/) je uredba Evropske unije (EU), ki določa, kako naj organizacije ravnajo z zasebnostjo in varnostjo svojih uporabnikov. Piškotki pogosto shranjujejo ali zbirajo »osebne podatke«, kot je spletni identifikator, ki ga ureja GDPR. Če vaše podjetje zaposluje in/ali prodaja posameznikom v EU, na katere se nanašajo podatki, GDPR vpliva na vas. [Preberite več o tem, kako vam lahko Microsoft pomaga pri skladnosti z GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Če želite kompletu za razvoj programske opreme za vpoglede v interakcije dovoliti shranjevanje piškotkov ali drugih občutljivih informacij, morate navesti, ali so uporabniki podali soglasje. To se zgodi pri inicializaciji kompleta za razvoj programske opreme z nastavitvijo polja `userConsent` v konfiguraciji.

Če navedete, da ni soglasja uporabnika, komplet za razvoj programske opreme ne bo shranil nobenih podatkov in ne bo pošiljal dogodkov, ki jih je mogoče uporabiti za sledenje vedenju uporabnikov. Vsi predhodno shranjeni podatki bodo izbrisani iz brskalnika.

Če vrednost soglasja uporabnika ni določena, bo komplet za razvoj programske opreme domneval, da je uporabnik podal soglasje. To pomeni, da bodo podatki zbrani, če (kot naša stranka) v kompletu za razvoj programske opreme ne navedete vrednosti za soglasje uporabnika. Če pa navedete, da mora biti vrednost za soglasje uporabnika »true«, se podatki ne bodo zbirali, če uporabnik zavrne ali ne poda izrecnega soglasja.

Spodaj je izrezek kode za inicializacijo spletnega kompleta za razvoj programske opreme s privolitvijo uporabnika:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Shranjevanje podatkov o obiskovalcih v možnosti vpogledov v interakcije

### <a name="cookies"></a>Piškotki

- _msei
    - Shrani anonimni ID uporabnika. Ta piškotek se nastavi v domeni stranke in poteče v 365 dneh.

### <a name="local-storage"></a>Lokalna shramba

Možnost vpogleda v interakcije uporablja tudi ključe (`localStorage`) za sledenje neobčutljivim podatkom. Ti podatki so v celoti shranjeni v samem brskalniku, promet pa se ne pošilja na vaše strežnike ali z njih.

- *EISession.Id*
    - Shrani informacije o trenutni seji uporabnika, kot so ID seje, kdaj se je začela in kdaj poteče.
- *EISession.Previous*
    - Shrani URL prej obiskane strani v trenutni seji.

Ključi v lokalni shrambi ne potečejo samodejno in se ponastavijo med naslednjo sejo kompleta za razvoj programske opreme.

## <a name="deleting-cookies"></a>Brisanje piškotkov

Stranke lahko v nastavitvah svojih brskalnikov kadar koli ročno izbrišejo piškotke in lokalne ključe shrambe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
