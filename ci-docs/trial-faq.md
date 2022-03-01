---
title: Pogosta vprašanja o preskusni različici – Dynamics 365 Customer Insights
description: Rešitve za pogosta vprašanja, povezana z namestitvijo preskusne različice storitve Customer Insights in z njenim upravljanjem. Preberite več o tem, kako odpraviti težave, povezane s platformami in aplikacijami.
author: m-hartmann
ms.author: mhart
ms.date: 09/30/2021
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 2837ae13b4150310193a2d09d59aed66b4a69c69
ms.sourcegitcommit: e6020c178a61beb0ee31a031c11ded914d10d995
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/13/2021
ms.locfileid: "7642912"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Pogosta vprašanja o preskusni različici Dynamics 365 Customer Insights

## <a name="sign-up"></a>Prijava

### <a name="what-are-the-system-requirements-for-the-trial"></a>Kakšne so sistemske zahteve za preskusno različico?

Gre za storitev v oblaku, ki razen posodobljenega spletnega brskalnika ne zahteva posebne programske opreme, kljub temu pa veljajo nekatere omejitve. Za najboljšo preskusno različico se izogibajte dostopu do spletnega mesta preskusne različice v načinu brez beleženja zgodovine in izberite preskusno lokacijo, ki vam je najbližja. [Preberite več o zahtevah za spletne aplikacije.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Kako se lahko na preskušanje različice prijavim brez najemnika storitve Microsoft 365?

Vpišite nedelovni e-poštni naslov in ustvarili vam bomo račun ter najemnika.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Ali se je mogoče prijaviti na preskušanje več aplikacij Dynamics 365, kot so Sales, Marketing in Customer Service?

Da, to je mogoče. Za ogled vseh razpoložljivih preskusnih različic [obiščite stran središča za preskušanje](https://dynamics.microsoft.com/dynamics-365-free-trial). Z istim e-poštnim računom se lahko prijavite za različne preskusne različice. Vendar na istem spletnem mestu preskusne različice ni mogoče imeti več aplikacij. Vsaka preskusna različica ima svojo organizacijo in svoj URL. Aplikacije podatkov poskusne različice ne morejo souporabljati.

## <a name="trial-app"></a>Preskusna aplikacija

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Po prijavi nisem prejel/-a e-poštnega sporočila s podrobnostmi o preskusni različici. Kaj naj storim?

Ob prijavi na preskušanje boste prejeli e-poštno sporočilo s podrobnostmi o preskusni različici. Če e-poštnega sporočila ni v vašem nabiralniku, preverite mapo z neželeno pošto. Za dostop do aplikacije lahko sledite tudi naslednjim korakom:

1. Obiščite spletno mesto preskusne različice in izberite možnost **Preskusite brezplačno**.
1. Za prijavo na preskušanje vnesite uporabljeni ID e-poštnega sporočila. Preusmerjeni boste v preskusno aplikacijo.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Kako lahko v preskusno aplikacijo dodam več uporabnikov?

Za dodajanje uporabnikov s svojim skrbniškim računom za preskusno različico obiščite [skrbniško središče za Microsoft 365](https://admin.microsoft.com). Za dodajanje uporabnikov v preskusno različico sledite [navodilom skrbniškega središča](/microsoft-365/admin/add-users/add-users). Če uporabnik, ki ga želite dodati, že ima račun za storitev Microsoftov 365, mu dodelite ustrezno varnostno vlogo v preskusni organizaciji. Za več informacij glejte [Dodeljevanje varnostne vloge uporabniku](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Koliko uporabnikov lahko dodam v preskusno okolje?

V preskusno okolje lahko dodate neomejeno število uporabnikov.

### <a name="how-do-i-reset-the-trial-environment"></a>Kako lahko ponastavim preskusno okolje?

Preskusnega okolja ni mogoče ponastaviti. Lahko pa počakate, da se poskusno obdobje izteče, in se prijavite na novo preskušanje.

## <a name="trial-expiration-and-extension"></a>Potek in podaljšanje preskusnega obdobja

### <a name="how-do-i-extend-the-trial"></a>Kako lahko podaljšam preskusno obdobje?

Preskusno različico lahko podaljšate neposredno v aplikaciji. Preskusno obdobje lahko podaljšate enkrat.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Ali lahko preskusno različico pretvorim v plačano, licencirano različico?

Na splošno priporočamo, da pri nadgradnji na plačljivo različico Customer Insights začnete na novo z lastnimi podatki. 

Če uporabljate samo vpoglede v občinstvo, lahko kopirate svoje podatke iz preskusnega okolja, če kupite storitev Customer Insights. Če želite preseliti nastavitve iz preskusnega v plačljivo okolje, morate biti skrbnik preskusne različice Customer Insights in globalni skrbnik najemnika Microsoft 365 ali skrbnik Dynamics 365 v svoji organizaciji. 

Ko se prvič prijavite v plačljivi primerek storitve Customer Insights, boste morali ustvariti novo okolje. V tem postopku lahko izberete kopiranje konfiguracije iz obstoječega okolja in preselite večino nastavitev. Če imate zgoraj navedena dovoljenja, bo na tem seznamu prikazano preskusno okolje. Za več informacij glejte [Kopirajte konfiguracijo okolja](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Kakšne so omejitve in kvote preskusne različice?

- Za shranjevanje izhodnih podatkov med preskusno različico vpogledov v občinstvo ne morete uporabljati svojega računa Azure Data Lake Storage. Lahko pa uvozite podatke iz računa za shrambo Data Lake.
- V okolje Dataverse lahko shranite do 3 GB podatkov, ki so samodejno omogočeni, ko začnete s preskusno različico za storitev Customer Insights.

## <a name="customer-insights-specific-questions"></a>Vprašanja, ki se nanašajo na storitev Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Kako lahko začnem z uporabo preskusne različice?

Ko se prijavite za uporabo preskusne različice, se odpre glavni zaslon aplikacije. Na glavnem zaslonu najdete povezave do uporabniških priročnikov in vadnic. Za več informacij kliknite povezave v razdelku [Dodatni viri](trial-signup.md#additional-resources) na strani za prijavo v preskusno različico.

### <a name="what-features-are-available-in-the-trial"></a>Katere funkcije so na voljo v preskusu?

Večina funkcij zmogljivosti Customer Insights je na voljo v preskusni različici.

Naslednja funkcija ni na voljo: 
- Ne morete ustvariti novih okolij, ki uporabljajo lasten račun za Azure Data Lake Storage.

### <a name="how-long-does-the-trial-last"></a>Kako dolgo traja preskusna različica?

Preskusna različica za storitev Customer Insights traja 30 dni. Preskusno različico lahko enkrat podaljšate po 23 dneh, ko se prijavite v preskusno okolje.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Kako lahko iz preskusne različice odstranim vzorčne podatke?

Vzorčnih podatkov ne morete odstraniti iz preskusne različice.
