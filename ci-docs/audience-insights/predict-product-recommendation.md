---
title: Predvidevanje priporočil izdelkov
description: Predvidite, katere izdelke bo stranka verjetno kupila ali imela z njimi interakcije.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270535"
---
# <a name="product-recommendation-prediction-preview"></a>Predvidevanje priporočil izdelkov (predogled)

Model priporočil izdelkov ustvarja sklope predvidenih priporočil izdelkov. Priporočila temeljijo na predhodnem nakupovalnem vedenju in strankah s podobnimi vzorci nakupovanja. Na strani **Obveščanje** > **Predvidevanje** lahko ustvarite nova predvidevanja priporočil izdelkov. Izberite **Moja predvidevanja**, da si ogledate druga predvidevanja, ki ste jih ustvarili.

Za priporočila izdelkov lahko veljajo lokalni zakoni in predpisi ter pričakovanja kupcev, za katere model ni zasnovan tako, da bi jih posebej upošteval.  Kot uporabnik zmožnosti predvidevanja **morate priporočila pregledati, preden jih dostavite strankam**, da zagotovite upoštevanje vse veljavne zakonodaje ali predpisov, pa tudi pričakovanja strank glede priporočil. 

Poleg tega bodo v izhodnih podatkih tega modela podana priporočila na podlagi ID-ja izdelka. Vaš mehanizem za dostavo mora prevzeti napovedane ID-je izdelkov in jih preslikati v ustrezno vsebino za vaše stranke, da lahko upošteva lokalizacijo, slikovno vsebino in drugo podjetju lastno vsebino ali vedenje.

## <a name="sample-guide"></a>Vzorčni vodnik

Če vas zanima preizkus te funkcije, vendar nimate podatkov za izpolnitev spodnjih zahtev, lahko [ustvarite vzorčno uvedbo](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Znanje o podjetju za razumevanje različnih vrst izdelkov vašega podjetja in načinu interakcije, ki jih imajo vaše stranke z izdelki. Podpiramo priporočila izdelkov, ki so jih vaše stranke že kupile, ali priporočila za nove izdelke.
- Podatki o transakcijah, nakupih in njihovi zgodovini:
    - Identifikatorji transakcij za razlikovanje nakupov ali transakcij.
    - Identifikatorji strank za preslikavanje transakcij v profile strank.
    - Datumi transakcijskih dogodkov, ki določajo datume, ko je prišlo do transakcije.
    - (Izbirno) Podatki o ID-ju izdelka za transakcijo
    - (Izbirno) Če je transakcija vračilo ali ne
    - Semantična podatkovna shema potrebuje naslednje podatke:
        - **ID transakcije:** enolični identifikator nakupa ali transakcije.
        - **Datum transakcije:** datum nakupa ali transakcije
        - **Vrednost transakcije:** številski znesek vrednosti nakupa ali transakcije
        - (Neobvezno) **Enolični ID izdelka:** ID kupljenega izdelka ali storitve, če so vaši podatki na ravni postavke
        - (Neobvezno) **Nakup ali vračilo:** polje z logičnima vrednostma true/false, ki določa, ali je bila transakcija vračilo ali ne. Če je **vrednost transakcije** negativna, bomo te podatke uporabili tudi za sklepanje o vračilu.


## <a name="create-a-product-recommendation-prediction"></a>Ustvarjanje predvidevanja priporočil izdelkov

1. V rešitvi Customer Insights pojdite na **Obveščanje** > **Predvidevanja**.

1. Izberite ploščico **Model priporočil izdelkov (predogled)** in izberite možnost **Uporabi ta model**.
   > [!div class="mx-imgBorder"]
   > ![Ploščica modela priporočil izdelkov z gumbom Uporabi ta model](media/product-recommendation-usethismodel.PNG "Ploščica modela priporočil izdelkov z gumbom Uporabi ta model")

1. Preglejte informacije o zahtevah modela. Če imate potrebne podatke, izberite možnost **Začetek**.

### <a name="name-model"></a>Ime modela

1. Navedite ime modela, da ga boste lahko razlikovali od drugih modelov.

1. Vnesite ime izhodne entitete samo s črkami in številkami ter brez presledkov. To je ime, ki ga bo uporabila entiteta modela. Nato izberite **Naprej**.

### <a name="define-product-recommendation-configuration"></a>Določitev konfiguracije priporočil izdelkov

1. Nastavite **število izdelkov**, ki jih želite priporočiti stranki. Ta vrednost je odvisna od tega, kako način dostavljanja izpolnjuje podatke. Če lahko priporočite tri izdelke, ustrezno nastavite to vrednost.
   
   >[!TIP]
   > Kadar koli lahko izberete možnost **Shrani in zapri**, da shranite predvidevanje kot osnutek. Osnutek predvidevanja najdete na zavihku **Moja predvidevanja**.

1. Izberite, ali želite **predlagati izdelke, ki so jih stranke nedavno kupile**.

1. Če se izbrali, da *ne* boste priporočali nedavno kupljenih izdelkov, nastavite **Okno za pogled nazaj**. Ta nastavitev določa časovni okvir, ki ga model upošteva, preden izdelek ponovno priporoči uporabniku. Navedite na primer, da stranka kupi prenosni računalnik vsaki dve leti. To okno si ogledala zgodovino nakupov v zadnjih dveh letih in če bodo našli izdelek, bo ta filtriran iz priporočil.

1. Izberite **Naprej**

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite možnost **Dodaj podatke** za **zgodovino transakcij stranke** in izberite entiteto, ki zagotavlja podatke o zgodovini transakcij/nakupov, kot je opisano v [zahtevah](#prerequisites).

1. Preslikajte semantična polja v atribute v entiteti vaše zgodovine nakupov in izberite **Naprej**. Za opise polj si oglejte [pogoje](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Določanje odnosa entitete](media/product-recommendation-purchasehistorymapping.PNG "Stran z zgodovino nakupov, ki prikazuje semantične atribute, ki so preslikani v polja v izbrani entiteti zgodovine nakupov")

1. Če polja niso izpolnjena, konfigurirajte odnos med entiteto zgodovine nakupov in entiteto *stranke*.
    1. Izberite **Entiteta zgodovine nakupov**.
    1. Izberite **Polje**, ki prepozna kupca v entiteti zgodovine nakupov. Povezovati se mora s primarnim ID-jem stranke vaše entitete *stranke*.
    1. Izberite **Entiteto stranke**, ki se ujema z vašo primarno entiteto stranke.
    1. Vnesite ime, ki opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stran z zgodovino nakupov, ki prikazuje vzpostavitev odnosa s stranko](media/model-purchase-join.png "Stran z zgodovino nakupov, ki prikazuje vzpostavitev odnosa s stranko")

1. Izberite **Shrani**.

1. Izberite **Naprej**.

### <a name="set-schedule-and-review-configuration"></a>Nastavitev razporeda in pregled konfiguracije

1. Nastavite frekvenco za prekvalifikacijo modela. Ta nastavitev je pomembna za posodobitev natančnosti predvidevanj, ko se v storitev Customer Insights uvozijo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

1. Preglejte konfiguracijo. Na kateri koli del konfiguracije predvidevanja se lahko vrnete tako, da izberete možnost **Uredi** pod prikazano vrednostjo. Lahko pa izberete korak konfiguracije v prikazu napredovanja.

1. Če so vse vrednosti pravilno konfigurirane, izberite **Shrani in zaženi** za začetek postopka predvidevanja. Na zavihku **Moja predvidevanja** si lahko ogledate stanje svojih predvidevanj. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled stanja in rezultatov predvidevanj

1. Pojdite na zavihek **Moja predvidevanja** v možnosti **Obveščanje** > **Predvidevanja**.
   > [!div class="mx-imgBorder"]
   > ![Pogled strani »Moja predvidevanja«](media/product-recommendation-mypredictions.PNG "Pogled strani »Moja predvidevanja«")

1. Izberite predvidevanje, ki ga želite pregledati.
   - **Ime predvidevanja:** ime predvidevanja, navedeno pri ustvarjanju.
   - **Vrsta predvidevanja:** vrsta modela, uporabljenega za predvidevanje
   - **Izhodna entiteta:** ime entitete za shranjevanje rezultatov predvidevanja. Entiteto s tem imenom lahko najdete v razdelku **Podatki** > **Entitete**.
   - **Predvideno polje:** to polje je zapolnjeno samo za nekatere vrste predvidevanj in se ne uporablja pri predvidevanju izgub.
   - **Stanje:** trenutno stanje izvajanja predvidevanja.
        - **V čakalni vrsti:** predvidevanje trenutno čaka, da se začnejo izvajati drugi postopki.
        - **Osveževanje:** predvidevanje trenutno izvaja stopnjo »rezultat« obdelave, da ustvari rezultate, ki se bodo pretakali v izhodno entiteto.
        - **Ni uspelo:** predvidevanje ni uspelo. Za več podrobnosti izberite **Dnevniki**.
        - **Uspešno:** predvidevanje je uspelo. Izberite **Pogled** pod navpičnimi tremi pikami za pregled predvidevanja
   - **Urejeno:** datum, ko je bila spremenjena konfiguracija predvidevanja.
   - **Nazadnje osveženo:** datum, ko je predvidevanje osvežilo rezultate v izhodni entiteti.

1. Izberite navpične tri pike poleg predvidevanja, za katerega želite pregledati rezultate, in izberite **Pogled**.
   > [!div class="mx-imgBorder"]
   > ![Pogled možnosti v meniju z navpičnimi tremi pikami za predvidevanje, vključno z urejanjem, osveževanjem, pogledom, dnevniki in brisanjem](media/product-recommendation-verticalellipses.PNG "Pogled možnosti v meniju z navpičnimi tremi pikami za predvidevanje, vključno z urejanjem, osveževanjem, pogledom, dnevniki in brisanjem")

1. Na strani z rezultati so trije primarni razdelki podatkov:
    1. **Učinkovitost modela za kvalifikacijo:** A, B ali C so možni rezultati. Ta rezultat kaže na učinkovitost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.
        - Rezultati se določijo na podlagi naslednjih pravil:
            - **A** Kakovost modela je smatrana za razred **A**, če je metrika »Success @ K« za vsaj 10 % večja od osnovnega modela. 
            - **B** Kakovost modela je smatrana za razred **B**, če je metrika "Success @ K" od 0 do 10 % večja od osnovnega modela.
            - **C** Kakovost modela je smatrana za razred **C**, če je metrika "Success @ K" manjša od osnovnega modela.
               
               > [!div class="mx-imgBorder"]
               > ![Pogled na rezultat učinkovitosti modela](media/product-recommendation-modelperformance.PNG "Pogled na rezultat učinkovitosti modela")
            - **Osnovni model**: model upošteva najbolj priporočene izdelke glede na število nakupov pri vseh strankah in uporablja naučena pravila, ki jih določa model, da ustvari nabor priporočil za stranke. Napovedi se nato primerjajo z najboljšimi izdelki, določenimi s številom kupcev, ki so kupili izdelek. Če ima stranka v priporočenih izdelkih vsaj en izdelek, ki je bil viden tudi med najbolj kupljenimi izdelki, se stranka šteje za del osnovnega modela. Če 10 od skupno 100 strank strank kupi priporočeni izdelek, je osnovni model 10%.
            - **Uspeh @ K** : Z uporabo veljavnostnega nabora časovnega obdobja transakcij se ustvarijo priporočila za vse stranke in se primerjajo z veljavnostnim naborom transakcij. V 12-mesečnem obdobju je na primer 12. mesec lahko izbran kot veljavnostni nabor podatkov. Če model predvideva vsaj en izdelek, ki ga kupite v 12. mesecu, na podlagi tega, kar se je naučil v preteklih 11 mesecih, bi ta kupec povečal vrednost metrike "Success @ K".
    
    1. **Najbolj predlagani izdelki (s seštevkom):** najboljših 5 izdelkov, ki so bili predvideni za vaše stranke.
       > [!div class="mx-imgBorder"]
       > ![Graf, ki prikazuje 5 najbolj priporočenih izdelkov](media/product-recommendation-topproducts.PNG "Graf, ki prikazuje 5 najbolj priporočenih izdelkov")
    
    1. **Priporočila za izdelke z visoko zanesljivostjo:** vzorec priporočil za vaše stranke, za katere model meni, da jih bo stranka verjetno kupila.
       > [!div class="mx-imgBorder"]
       > ![Seznam, ki prikazuje predloge z visoko zanesljivostjo za izbrani nabor posameznih strank](media/product-recommendation-highconfidence.PNG "Seznam, ki prikazuje predloge z visoko zanesljivostjo za izbrani nabor posameznih strank")

## <a name="fix-a-failed-prediction"></a>Popravljanje neuspelega predvidevanja

1. Pojdite na zavihek **Moja predvidevanja** v možnosti **Obveščanje** > **Predvidevanja**.

1. Izberite predvidevanje, za katerega bi si radi ogledali dnevnike napak, in izberite **Dnevniki**.

1. Preglejte vse napake. Pride lahko do več vrst napak, ki opisujejo, kakšno stanje je povzročilo napako. Primer: napaka, za katero ni dovolj podatkov za natančno predvidevanje, se običajno odpravi z nalaganjem dodatnih podatkov v storitev Customer Insights.

## <a name="refresh-a-prediction"></a>Osveževanje predvidevanja

Napovedi se samodejno osvežijo glede na isti [urnik osveževanja podatkov](system.md#schedule-tab), kot je konfiguriran v nastavitvah.

1. Pojdite na zavihek **Moja predvidevanja** v možnosti **Obveščanje** > **Predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite osvežiti.

1. Izberite **Osveži**.

## <a name="delete-a-prediction"></a>Brisanje predvidevanja

Če izbrišete predvidevanje, odstranite tudi njegovo izhodno entiteto.

1. Pojdite na zavihek **Moja predvidevanja** v možnosti **Obveščanje** > **Predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite izbrisati.

1. Izberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]