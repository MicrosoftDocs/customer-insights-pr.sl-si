---
title: Pogosta vprašanja o preskusni različici Dynamics 365 Customer Insights
description: Rešitve za pogosta vprašanja, povezana z namestitvijo preskusne različice storitve Customer Insights in z njenim upravljanjem. Preberite več o tem, kako odpraviti težave, povezane s platformami in aplikacijami.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 41f112466d54c9923d0daf7c55d343f9b5c81d98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051519"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Pogosta vprašanja o preskusni različici Dynamics 365 Customer Insights

## <a name="sign-up"></a>Prijava

### <a name="what-are-the-system-requirements-for-the-trial"></a>Kakšne so sistemske zahteve za preskusno različico?

Gre za storitev v oblaku, ki razen posodobljenega spletnega brskalnika ne zahteva posebne programske opreme, kljub temu pa veljajo nekatere omejitve. Za najboljšo preskusno različico se izogibajte dostopu do spletnega mesta preskusne različice v načinu brez beleženja zgodovine in izberite preskusno lokacijo, ki vam je najbližja. [Preberite več o zahtevah za spletne aplikacije.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Kako se prijavim na preizkus brez a Microsoft 365 najemnik?

Vpišite nedelovni e-poštni naslov in ustvarili vam bomo račun ter najemnika.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Ali se je mogoče prijaviti na preskušanje več aplikacij Dynamics 365, kot so Sales, Marketing in Customer Service?

Da, to je mogoče. Za ogled vseh razpoložljivih preskusnih različic [obiščite stran središča za preskušanje](https://dynamics.microsoft.com/dynamics-365-free-trial). Z istim e-poštnim računom se lahko prijavite za različne preskusne različice. Vendar na istem spletnem mestu preskusne različice ni mogoče imeti več aplikacij. Vsaka preskusna različica ima svojo organizacijo in svoj URL. Aplikacije podatkov poskusne različice ne morejo souporabljati.

## <a name="trial-app"></a>Preskusna aplikacija

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Po prijavi nisem prejel/-a e-poštnega sporočila s podrobnostmi o preskusni različici. Kaj naj storim?

Ob prijavi na preskušanje boste prejeli e-poštno sporočilo s podrobnostmi o preskusni različici. Če e-poštnega sporočila ni v vašem nabiralniku, preverite mapo z neželeno pošto. Za dostop do aplikacije lahko sledite tudi naslednjim korakom:

1. Obiščite spletno mesto preskusne različice in izberite možnost **Preskusite brezplačno**.
1. Za prijavo na preskušanje vnesite uporabljeni ID e-poštnega sporočila. Preusmerjeni boste v preskusno aplikacijo.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Kako lahko v preskusno aplikacijo dodam več uporabnikov?

Če želite dodati uporabnike, s skrbniškim računom za preskusno različico obiščite skrbniško središče za [Microsoft 365](https://admin.microsoft.com). Za dodajanje uporabnikov v preskusno različico sledite [navodilom skrbniškega središča](/microsoft-365/admin/add-users/add-users). Če uporabnik, ki ga dodate, že ima Microsoft 365 račun, jim dodelite ustrezen varnostna vloga v poskusni org. Za več informacij glejte [Uporabniku dodelite varnostna vloga](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Koliko uporabnikov lahko dodam v preskusno okolje?

V preskusno okolje lahko dodate neomejeno število uporabnikov.

### <a name="how-do-i-reset-the-trial-environment"></a>Kako lahko ponastavim preskusno okolje?

Preskusnega okolja ni mogoče ponastaviti. Lahko pa počakate, da se poskusno obdobje izteče, in se prijavite na novo preskušanje.

## <a name="trial-expiration-and-extension"></a>Potek in podaljšanje preskusnega obdobja

### <a name="how-do-i-extend-the-trial"></a>Kako lahko podaljšam preskusno obdobje?

Preskusno različico lahko podaljšate neposredno v aplikaciji. Preskusno obdobje lahko podaljšate enkrat.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Ali lahko preskusno različico pretvorim v plačano, licencirano različico?

Na splošno priporočamo, da pri nadgradnji na plačljivo različico Customer Insights začnete na novo z lastnimi podatki. 

Če uporabljate samo Customer Insights, lahko po želji kopirate svoje podatke iz preskusnega okolja, če kupite Customer Insights. Biti morate skrbnik preizkusne različice Customer Insights in globalni skrbnik vašega Microsoft 365 najemnik ali skrbnik Dynamics 365 v vaši organizaciji za selitev nastavitev iz preizkusnega okolja v plačljivo okolje.

Ko se prvič prijavite v plačljivi primerek storitve Customer Insights, boste morali ustvariti novo okolje. V tem postopku lahko izberete kopiranje konfiguracije iz obstoječega okolja in preselite večino nastavitev. Če imate zgoraj navedena dovoljenja, bo na tem seznamu prikazano preskusno okolje. Za več informacij glejte [Kopirajte konfiguracijo okolja](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Kakšne so omejitve in kvote preskusne različice?

- Svojega ne morete uporabiti Azure Data Lake Storage račun za shranjevanje izhodnih podatkov med preskusno različico Customer Insights. Vendar pa lahko zaužijete podatke iz računa Data Lake Storage.
- V okolje Dataverse lahko shranite do 3 GB podatkov, ki so samodejno omogočeni, ko začnete s preskusno različico za storitev Customer Insights.

## <a name="customer-insights-specific-questions"></a>Vprašanja, ki se nanašajo na storitev Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Kako lahko začnem z uporabo preskusne različice?

Ko se prijavite za uporabo preskusne različice, se odpre glavni zaslon aplikacije. Na glavnem zaslonu najdete povezave do uporabniških priročnikov in vadnic. Za več informacij kliknite povezave v razdelku [Dodatni viri](trial-signup.md#additional-resources) na strani za prijavo v preskusno različico.

### <a name="what-features-are-available-in-the-trial"></a>Katere funkcije so na voljo v preskusu?

Večina funkcij zmogljivosti Customer Insights je na voljo v preskusni različici.

Naslednje značilnosti so **ni na voljo**:

- Ne morete ustvariti novih okolij, ki uporabljajo svoje Azure Data Lake Storage račun.
- Preizkusnega okolja ne morete izbrisati.

### <a name="how-long-does-the-trial-last"></a>Kako dolgo traja preskusna različica?

Preskusna različica za storitev Customer Insights traja 30 dni. Preskusno različico lahko enkrat podaljšate po 23 dneh, ko se prijavite v preskusno okolje.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Kako lahko iz preskusne različice odstranim vzorčne podatke?

Vzorčnih podatkov ne morete odstraniti iz preskusne različice.
