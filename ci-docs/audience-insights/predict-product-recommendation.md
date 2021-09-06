---
title: Predvidevanje priporočil izdelkov
description: Predvidite, katere izdelke bo stranka verjetno kupila ali imela z njimi interakcije.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 60d511181aa85e3e939eff3e5931f0de7807c01c8f38134ebca5c5604cd53871
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034976"
---
# <a name="product-recommendation-prediction-preview"></a>Predvidevanje priporočil izdelkov (predogled)

Model priporočil izdelkov ustvarja sklope predvidenih priporočil izdelkov. Priporočila temeljijo na predhodnem nakupovalnem vedenju in strankah s podobnimi vzorci nakupovanja. Na strani **Obveščanje** > **Predvidevanje** lahko ustvarite nova predvidevanja priporočil izdelkov. Izberite **Moja predvidevanja**, da si ogledate druga predvidevanja, ki ste jih ustvarili.

Za priporočila izdelkov lahko veljajo lokalni zakoni in predpisi ter pričakovanja kupcev; model ni posebej zasnovan za upoštevanje teh dejavnikov.  Kot uporabnik te funkcije predvidevanja **morate pregledati priporočila, preden jih dostavite strankam**, da se prepričate, da ste pri podajanju priporočil spoštovali vso veljavno zakonodajo in predpise ter pričakovanja strank. 

Poleg tega bodo v izhodnih podatkih tega modela podana priporočila na podlagi ID-ja izdelka. Vaš mehanizem za dostavljanje bo moral predvidene ID-je izdelkov preslikati v ustrezno vsebino za vaše stranke, da bo upoštevana lokalizacija, slikovna vsebina in druga poslovno specifična vsebina ali vedenje.

## <a name="sample-guide"></a>Vzorčni vodnik

Če vas zanima preizkus te funkcije, vendar nimate podatkov za izpolnitev spodnjih zahtev, lahko [ustvarite vzorčno uvedbo](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.

- Znanje o podjetju za razumevanje različnih vrst izdelkov vašega podjetja in načinu interakcije, ki jih imajo vaše stranke z izdelki. Podpiramo priporočila izdelkov, ki so jih vaše stranke že kupile, ali priporočila za nove izdelke.

- Podatki o transakcijah, nakupih in njihovi zgodovini:
    - Identifikatorji transakcij za razlikovanje nakupov ali transakcij.
    - Identifikatorji strank za preslikavanje transakcij v profile strank.
    - Datumi transakcijskih dogodkov, ki določajo datume, ko je prišlo do transakcije.
    - Informacije o ID-ju izdelka za transakcijo.
    - (Izbirno) Podatkovna entiteta kataloga izdelkov za uporabo filtra izdelkov.
    - (Izbirno) Če je transakcija vračilo ali ne
    - Semantična podatkovna shema potrebuje naslednje podatke:
        - **ID transakcije:** enolični identifikator nakupa ali transakcije.
        - **Datum transakcije:** datum nakupa ali transakcije.
        - **Vrednost transakcije:** številski znesek vrednosti nakupa ali transakcije
        - (Neobvezno) **Enolični ID izdelka:** ID kupljenega izdelka ali storitve, če so vaši podatki na ravni postavke
        - (Izbirno) **Nakup ali vračilo:** logično polje, kjer vrednost *true* pomeni, da je bila transakcija vračilo. Če podatki o nakupu ali vračilu niso na voljo in sta model in **Vrednost transakcije** negativna, bomo te podatke uporabili tudi za izvedbo vračila.
- Predlagane lastnosti podatkov:
    - Zadostni zgodovinski podatki: vsaj eno leto transakcijskih podatkov, po možnosti dve do tri leta, da se vključi nekaj sezonskih značilnosti.
    - Več nakupov na stranko: vsaj tri transakcije na ID stranke
    - Število strank: vsaj 100 strank, po možnosti več kot 10.000 strank. Model ne bo deloval z manj kot 100 strankami.

> [!NOTE]
> - Model potrebuje zgodovino transakcij vaših strank. Definicija transakcije je precej prilagodljiva. Vsi podatki, ki opisujejo interakcijo med uporabnikom in izdelkom, lahko delujejo kot vhodni podatki. Na primer nakup izdelka, udeležba na tečaju ali obisk dogodka.
> - Trenutno je mogoče konfigurirati samo eno entiteto zgodovine transakcij. Če je več entitet nakupov, jih pred uvozom podatkov združite v storitvi Power Query.
> - Če sta entiteti naročila in podrobnosti naročila različni, ju pred uporabo v modelu združite. Model ne deluje, če ima v entiteti samo ID naročila ali ID prejema.


## <a name="create-a-product-recommendation-prediction"></a>Ustvarjanje predvidevanja priporočil izdelkov

1. V rešitvi Customer Insights pojdite na **Obveščanje** > **Predvidevanja**.

1. Izberite ploščico **Model priporočil izdelkov (predogled)** in izberite možnost **Uporabi ta model**.
   > [!div class="mx-imgBorder"]
   > ![Ploščica modela priporočil izdelkov z gumbom Uporabi ta model.](media/product-recommendation-usethismodel.PNG "Ploščica modela priporočil izdelkov z gumbom Uporabi ta model")

1. Preglejte informacije o zahtevah modela. Če imate potrebne podatke, izberite možnost **Začetek**.

### <a name="name-model"></a>Ime modela

1. Navedite ime modela, da ga boste lahko razlikovali od drugih modelov.

1. Vnesite ime izhodne entitete samo s črkami in številkami ter brez presledkov. To je ime, ki ga bo uporabila entiteta modela. Nato izberite **Naprej**.

### <a name="define-product-recommendation-configuration"></a>Določitev konfiguracije priporočil izdelkov

1. Nastavite **število izdelkov**, ki jih želite priporočiti stranki. Ta vrednost je odvisna od tega, kako način dostavljanja izpolnjuje podatke. Če lahko priporočite tri izdelke, ustrezno nastavite to vrednost.
   
   >[!TIP]
   > Kadar koli lahko izberete možnost **Shrani in zapri**, da shranite predvidevanje kot osnutek. Osnutek predvidevanja najdete na zavihku **Moja predvidevanja**.

1. Izberite, ali želite **predlagati izdelke, ki so jih stranke nedavno kupile**.

1. Če se izbrali, da *ne* boste priporočali nedavno kupljenih izdelkov, nastavite **Okno za pogled nazaj**. Ta nastavitev določa časovni okvir, ki ga model upošteva, preden izdelek ponovno priporoči uporabniku. Napišite na primer, da stranka kupi prenosnik vsaki dve leti. To okno si bo ogledalo zgodovino nakupov v zadnjih dveh letih in če bo našlo ustrezen izdelek, ga bo filtriralo iz priporočil.

1. Izberite **Naprej**

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite možnost **Dodaj podatke** za **zgodovino transakcij stranke** in izberite entiteto, ki zagotavlja podatke o zgodovini transakcij/nakupov, kot je opisano v [zahtevah](#prerequisites).

1. Preslikajte semantična polja v atribute v entiteti vaše zgodovine nakupov in izberite **Naprej**. Za opise polj si oglejte [pogoje](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Določite odnos entitete.](media/product-recommendation-purchasehistorymapping.PNG "Stran z zgodovino nakupov, ki prikazuje semantične atribute, ki so preslikani v polja v izbrani entiteti zgodovine nakupov")

1. Če polja niso izpolnjena, konfigurirajte odnos med entiteto zgodovine nakupov in entiteto *stranke*.
    1. Izberite **Entiteta zgodovine nakupov**.
    1. Izberite **Polje**, ki prepozna kupca v entiteti zgodovine nakupov. Povezovati se mora s primarnim ID-jem stranke vaše entitete *stranke*.
    1. Izberite **Entiteto stranke**, ki se ujema z vašo primarno entiteto stranke.
    1. Vnesite ime, ki opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stran z zgodovino nakupov, ki prikazuje vzpostavitev odnosa s stranko.](media/model-purchase-join.png "Stran z zgodovino nakupov, ki prikazuje vzpostavitev odnosa s stranko")

1. Izberite **Shrani**.

1. Izberite **Naprej**.

### <a name="configure-product-filters"></a>Konfiguracija filtrov izdelkov

Včasih so samo nekateri izdelki koristni ali primerni za vrsto predvidevanja, ki ga ustvarjate. Filtri izdelkov vam omogočajo, da določite podmnožico izdelkov s posebnimi značilnostmi, ki jih boste priporočili svojim strankam. Model bo uporabil vse razpoložljive izdelke za učenje vzorcev, uporabil pa bo le izdelke, ki se ujemajo z rezultati filtra izdelka.

1. V koraku **Dodajanje informacij o izdelku** dodajte svoj katalog izdelkov z informacijami za vsak izdelek. Preslikajte zahtevane informacije in izberite **Naprej**.

3. V koraku **Filtri izdelkov** izberite eno od naslednjih možnosti.

   * **Brez filtrov**: uporabite vse izdelke v napovedi priporočila izdelka.

   * **Določitev posebnih filtrov izdelka**: uporabite določene izdelke v napovedi priporočila izdelka.

1. Izberite **Naprej**.

1. Če izberete filter izdelka, ga morate takoj definirati. V podoknu **Atributi kataloga izdelkov** izberite atribute v entiteti *Katalog izdelkov*, ki jih želite vključiti v filter.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Stransko podokno prikazuje atribute v entiteti kataloga izdelkov za izbiro filtrov izdelkov.":::

1. Izberite, ali želite, da filter izdelka uporabi povezovalnike **in** ali **ali**, ki logično kombinirajo vaš izbor atributov iz kataloga izdelkov.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Vzorčna konfiguracija filtrov izdelkov v kombinaciji z logičnimi povezovalniki IN.":::

1. Izberite **Naprej**.

### <a name="set-update-schedule-and-review-configuration"></a>Nastavitev razporeda posodobitev in pregled konfiguracije

1. Nastavite frekvenco za prekvalifikacijo modela. Ta nastavitev je pomembna za posodobitev natančnosti predvidevanj, ko se v storitev Customer Insights uvozijo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

1. Preglejte konfiguracijo. Na kateri koli del konfiguracije predvidevanja se lahko vrnete tako, da izberete možnost **Uredi** pod prikazano vrednostjo. Lahko pa izberete korak konfiguracije v prikazu napredovanja.

1. Če so vse vrednosti pravilno konfigurirane, izberite **Shrani in zaženi** za začetek postopka predvidevanja. Na zavihku **Moja predvidevanja** si lahko ogledate stanje svojih predvidevanj. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled stanja in rezultatov predvidevanj

1. Pojdite na zavihek **Moja predvidevanja** v možnosti **Obveščanje** > **Predvidevanja**.
   > [!div class="mx-imgBorder"]
   > ![Pogled strani Moja predvidevanja.](media/product-recommendation-mypredictions.PNG "Pogled strani »Moja predvidevanja«")

1. Izberite predvidevanje, ki ga želite pregledati.
   - **Ime predvidevanja:** ime predvidevanja, navedeno pri ustvarjanju.
   - **Vrsta predvidevanja:** vrsta modela, uporabljenega za predvidevanje
   - **Izhodna entiteta:** ime entitete za shranjevanje rezultatov predvidevanja. Entiteto s tem imenom lahko najdete v razdelku **Podatki** > **Entitete**.    
      *Rezultat* v izhodni enoti je kvantitativni ukrep priporočila. Model priporoča izdelke z višjo oceno pred izdelki z nižjo oceno.
   - **Polje predvidevanja:** to polje je zapolnjeno samo za nekatere vrste predvidevanj in se ne uporablja v predvidevanju priporočila izdelka.
   - **Stanje:** trenutno stanje izvajanja predvidevanja.
        - **V čakalni vrsti:** predvidevanje trenutno čaka, da se začnejo izvajati drugi postopki.
        - **Osveževanje:** predvidevanje trenutno izvaja stopnjo »rezultat« obdelave, da ustvari rezultate, ki se bodo pretakali v izhodno entiteto.
        - **Ni uspelo:** predvidevanje ni uspelo. Za več podrobnosti izberite **Dnevniki**.
        - **Uspešno:** predvidevanje je uspelo. Izberite **Pogled** pod navpičnimi tremi pikami za pregled predvidevanja
   - **Urejeno:** datum, ko je bila spremenjena konfiguracija predvidevanja.
   - **Nazadnje osveženo:** datum, ko je predvidevanje osvežilo rezultate v izhodni entiteti.

1. Izberite navpične tri pike poleg predvidevanja, za katerega želite pregledati rezultate, in izberite **Pogled**.
   > [!div class="mx-imgBorder"]
   > ![Pogled možnosti v meniju z navpičnimi tremi pikami za predvidevanje, vključno z urejanjem, osveževanjem, pogledom, dnevniki in brisanjem.](media/product-recommendation-verticalellipses.PNG "Pogled možnosti v meniju z navpičnimi tremi pikami za predvidevanje, vključno z urejanjem, osveževanjem, pogledom, dnevniki in brisanjem")

1. Na strani z rezultati je pet osnovnih skupin podatkov:
    1. **Učinkovitost modela za kvalifikacijo:** A, B ali C so možni rezultati. Ta rezultat kaže na učinkovitost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.
        - Rezultati se določijo na podlagi naslednjih pravil:
            - **A** Kakovost modela je smatrana za razred **A**, če je metrika »Success @ K« za vsaj 10 % večja od osnovnega modela. 
            - **B** Kakovost modela je smatrana za razred **B**, če je metrika "Success @ K" od 0 do 10 % večja od osnovnega modela.
            - **C** Kakovost modela je smatrana za razred **C**, če je metrika "Success @ K" manjša od osnovnega modela.
               
               > [!div class="mx-imgBorder"]
               > ![Pogled na rezultat učinkovitosti modela.](media/product-recommendation-modelperformance.PNG "Pogled na rezultat učinkovitosti modela")
            - **Osnovni model**: model upošteva najbolj priporočene izdelke glede na število nakupov pri vseh strankah in uporablja naučena pravila, ki jih določa model, da ustvari nabor priporočil za stranke. Napovedi se nato primerjajo z najboljšimi izdelki, določenimi s številom kupcev, ki so kupili izdelek. Če ima stranka v priporočenih izdelkih vsaj en izdelek, ki je bil viden tudi med najbolj kupljenimi izdelki, se stranka šteje za del osnovnega modela. Če 10 od skupno 100 strank strank kupi priporočeni izdelek, je osnovni model 10%.
            - **Uspeh @ K** : Z uporabo veljavnostnega nabora časovnega obdobja transakcij se ustvarijo priporočila za vse stranke in se primerjajo z veljavnostnim naborom transakcij. V 12-mesečnem obdobju je na primer 12. mesec lahko izbran kot veljavnostni nabor podatkov. Če model predvideva vsaj en izdelek, ki ga kupite v 12. mesecu, na podlagi tega, kar se je naučil v preteklih 11 mesecih, bi ta kupec povečal vrednost metrike "Success @ K".
    
    1. **Najpogosteje predlagani izdelki (s skupnim številom):** pet najboljših izdelkov, ki so bili predvideni za vaše stranke.
       > [!div class="mx-imgBorder"]
       > ![Graf, ki prikazuje 5 najbolj priporočenih izdelkov.](media/product-recommendation-topproducts.PNG "Graf, ki prikazuje 5 najbolj priporočenih izdelkov")
    
    1. **Ključni dejavniki priporočanja:** model uporablja zgodovino transakcij strank za podajanje priporočil izdelkov. Vzorce oblikuje na podlagi preteklih nakupov in ugotovi podobnosti med strankami in izdelki. Te podobnosti se nato uporabijo za oblikovanje priporočil izdelkov.
    Spodaj so našteti dejavniki, ki bi lahko vplivali na priporočilo izdelka, ki ga ustvari model. 
        - **Pretekle transakcije**: v preteklosti je model uporabljal vzorce nakupov za oblikovanje priporočil izdelkov. Model lahko na primer priporoči _Surface Arc Mouse_, če je nekdo pred kratkim kupil _Surface Book 3_ in _Surface Pen_. Model se je naučil, da je v preteklosti veliko kupcev kupilo _Surface Arc Mouse_ po nakupu _Surface Book 3_ in _Surface Pen_.
        - **Podobnost strank**: priporočeni izdelek so v preteklosti kupile druge stranke, ki kažejo podobne vzorce nakupovanja. Mehanizem je Janezu na primer priporočil _Surface Headphones 2_, ker sta Daša in Branko pred kratkim kupila _Surface Headphones 2_. Model verjame, da je Janez podoben Daši in Branku, ker sta v preteklosti imela podobne vzorce nakupovanja.
        - **Podobnost izdelka**: priporočeni izdelek je podoben drugim izdelkom, ki jih je stranka že kupila. Model meni, da sta si dva izdelka podobna, če sta bila kupljena skupaj ali so ju kupile podobne stranke. Nekdo lahko na primer prejme priporočilo za _USB Storage Drive_, ker je prej kupil _USB-C to USB Adapter_ in model verjame, da je _USB Storage Drive_ podoben izdelku _USB-C to USB Adapter_ na podlagi zgodovinskih vzorcev nakupovanja.

        Na vsako priporočilo izdelka vpliva eden ali več dejavnikov. Delež priporočil, kjer je vsak vplivni dejavnik igral svojo vlogo, je prikazan v grafikonu. V naslednjem primeru so na 100 % priporočil vplivale pretekle transakcije, na 60 % podobnost strank in na 22 % podobnost izdelkov. Premaknite kazalec miške nad stolpce na grafikonu, da vidite natančen delež prispevanja vplivnih dejavnikov.

        > [!div class="mx-imgBorder"]
        > ![Ključni dejavniki za priporočila.](media/product-recommendation-keyrecommendationfactors.png "Ključni dejavniki priporočil, ki se jih je model naučil za oblikovanje priporočil izdelkov")
       
     
   1. **Statistika podatkov**: zagotavlja pregled nad številom transakcij, strank in izdelkov, ki jih obravnava model. Temelji na vhodnih podatkih, ki so bili uporabljeni za učenje vzorcev in ustvarjanje priporočil izdelkov.

      > [!div class="mx-imgBorder"]
      > ![Statistika podatkov.](media/product-recommendation-datastatistics.png "Statistika podatkov o vhodnih podatkih, ki jih model uporablja za učenje vzorcev")

      Ta razdelek prikazuje statistiko o podatkovnih točkah, ki jih je model uporabil za učenje vzorcev in ustvarjanje priporočil izdelkov. Filtriranje, kot je konfigurirano v konfiguraciji modela, bo veljalo za izhod, ki ga ustvari model. Vendar pa model uporablja vse razpoložljive podatke za učenje vzorcev. Če torej v konfiguraciji modela uporabite filtriranje izdelkov, bo v tem razdelku prikazano skupno število izdelkov, ki jih je model analiziral za učenje vzorcev, ki se lahko razlikujejo od števila izdelkov, ki ustrezajo določenim merilom filtriranja.

   1. **Priporočila za izdelke z visoko zanesljivostjo:** vzorec priporočil za vaše stranke, za katere model meni, da jih bo stranka verjetno kupila.    
      Če je dodan katalog izdelkov, se ID-ji izdelkov nadomestijo z imeni izdelkov. Imena izdelkov zagotavljajo bolj uporabne in intuitivne informacije o predvidevanjih.
       > [!div class="mx-imgBorder"]
       > ![Seznam, ki prikazuje predloge z visoko zanesljivostjo za izbrani nabor posameznih strank.](media/product-recommendation-highconfidence.PNG "Seznam, ki prikazuje predloge z visoko zanesljivostjo za izbrani nabor posameznih strank")

## <a name="manage-predictions"></a>Upravljanje predvidevanj

Predvidevanja je mogoče optimizirati, zanje odpraviti napake, osvežiti ali izbrisati. Preglejte poročilo o uporabnosti vhodnih podatkov, če želite izvedeti, kako narediti predvidevanje hitrejše in zanesljivejše. Za več informacij glejte razdelek [Upravljanje predvidevanj](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
